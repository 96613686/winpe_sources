# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14000a96c`
- end: `0x14000a99f`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a9a8`

## callees

- `0x14000a96c`
- `0x14000a9a8`

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
0x14000a96c  sub     rsp, 28h
0x14000a970  mov     eax, [rcx]
0x14000a972  mov     [rsp+28h+arg_0], 0
0x14000a97b  mov     dword ptr [rsp+28h+arg_0], eax
0x14000a97f  bt      eax, 9
0x14000a983  jb      short loc_14000A98C
0x14000a985  mov     rax, [rsp+28h+arg_0]
0x14000a98a  jmp     short loc_14000A999
0x14000a98c  mov     r8, rdx
0x14000a98f  mov     rdx, [rsp+28h+arg_0]
0x14000a994  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14000a999  add     rsp, 28h
0x14000a99d  retn
```
