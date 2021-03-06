## API Report File for "@uifabricshared/foundation-compose"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

import { IComponentSettings } from '@uifabricshared/foundation-settings';
import { IComponentTokens } from '@uifabricshared/foundation-tokens';
import { IComposableDefinition } from '@uifabricshared/foundation-composable';
import { INativeSlotType } from '@uifabricshared/foundation-composable';
import { IOverrideLookup } from '@uifabricshared/foundation-settings';
import { IRenderData } from '@uifabricshared/foundation-composable';
import { ISettingsEntry } from '@uifabricshared/themed-settings';
import { ISlotProps } from '@uifabricshared/foundation-settings';
import { ISlotStyleFactories } from '@uifabricshared/foundation-tokens';
import { ISlotWithFilter } from '@uifabricshared/foundation-composable';
import { ITheme } from '@uifabricshared/theming-ramp';
import * as React from 'react';

// @public
export function compose<TProps extends object, TSlotProps extends ISlotProps = ISlotProps<TProps>, TState extends object = object, TStatics extends object = object>(inputComponent: Partial<IComposeOptions<TProps, TSlotProps, TState, TStatics>>, base?: INativeSlotType): IComposeReturnType<TProps, TSlotProps, TState, TStatics>;

// @public
export interface IComposeOptions<TProps extends object = object, TSlotProps extends ISlotProps = ISlotProps<TProps>, TState extends object = object, TStatics extends object = object> extends Omit<IComposableDefinition<TSlotProps['root'], TSlotProps, TState>, 'slots'>, IStylingSettings<TSlotProps> {
    displayName?: string;
    statics?: TStatics;
    usePrepareProps?: (props: TSlotProps['root'], useStyling: IUseComposeStyling<TSlotProps>) => IRenderData<TSlotProps, TState>;
    useStyling?: IUseComposeStyling<TSlotProps>;
}

// @public
export type IComposeReturnType<TProps extends object, TSlotProps extends ISlotProps, TState extends object = object, TStatics extends object = object> = React.FunctionComponent<TProps> & TStatics & {
    __composable: IComposeOptions<TProps, TSlotProps, TState, TStatics>;
    customize: (...settings: IComposeSettings<TSlotProps>) => IComposeReturnType<TProps, TSlotProps, TState, TStatics>;
    compose: (newOptions: Partial<IComposeOptions<TProps, TSlotProps, TState, TStatics>>) => IComposeReturnType<TProps, TSlotProps, TState, TStatics>;
};

// @public
export type IComposeSettings<TSlotProps extends ISlotProps> = ISettingsEntry<IComponentSettings<TSlotProps>, ITheme>[];

// @public
export function initializeStyling<TSlotProps extends ISlotProps>(styleSettings: IStylingSettings<TSlotProps>, name?: string): IUseComposeStyling<TSlotProps>;

// @public
export interface IStylingSettings<TSlotProps extends ISlotProps> {
    resolvedTokens?: IComponentTokens<TSlotProps['root'], ITheme>;
    settings?: IComposeSettings<TSlotProps>;
    slots: {
        [K in keyof TSlotProps]: ISlotWithFilter<ISlotStyleFactories<TSlotProps['root'], ITheme>>;
    };
}

// @public
export type IUseComposeStyling<TSlotProps extends ISlotProps> = (props: TSlotProps['root'], lookup?: IOverrideLookup) => TSlotProps;


// (No @packageDocumentation comment for this package)

```
