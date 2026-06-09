# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140044d80`
- end: `0x140044db3`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140044d40`
- `0x140044dbc`

## callees

- `0x140044d80`
- `0x140044dbc`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2)
{
  if ( (*a1 & 0x200) != 0 )
    return wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(a1, *a1, a2);
  else
    return *(unsigned int *)a1;
}

```

## disassembly

```asm
0x140044d80  sub     rsp, 28h
0x140044d84  mov     eax, [rcx]
0x140044d86  mov     [rsp+28h+arg_0], 0
0x140044d8f  mov     dword ptr [rsp+28h+arg_0], eax
0x140044d93  bt      eax, 9
0x140044d97  jb      short loc_140044DA0
0x140044d99  mov     rax, [rsp+28h+arg_0]
0x140044d9e  jmp     short loc_140044DAD
0x140044da0  mov     r8, rdx
0x140044da3  mov     rdx, [rsp+28h+arg_0]
0x140044da8  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140044dad  add     rsp, 28h
0x140044db1  retn
```
