# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14000e7e0`
- end: `0x14000e813`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e7a0`
- `0x14000e81c`

## callees

- `0x14000e7e0`
- `0x14000e81c`

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
0x14000e7e0  sub     rsp, 28h
0x14000e7e4  mov     eax, [rcx]
0x14000e7e6  mov     [rsp+28h+arg_0], 0
0x14000e7ef  mov     dword ptr [rsp+28h+arg_0], eax
0x14000e7f3  bt      eax, 9
0x14000e7f7  jb      short loc_14000E800
0x14000e7f9  mov     rax, [rsp+28h+arg_0]
0x14000e7fe  jmp     short loc_14000E80D
0x14000e800  mov     r8, rdx
0x14000e803  mov     rdx, [rsp+28h+arg_0]
0x14000e808  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14000e80d  add     rsp, 28h
0x14000e811  retn
```
