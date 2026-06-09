# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14000aeb0`
- end: `0x14000aee3`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000aeec`

## callees

- `0x14000aeb0`
- `0x14000aeec`

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
0x14000aeb0  sub     rsp, 28h
0x14000aeb4  mov     eax, [rcx]
0x14000aeb6  mov     [rsp+28h+arg_0], 0
0x14000aebf  mov     dword ptr [rsp+28h+arg_0], eax
0x14000aec3  bt      eax, 9
0x14000aec7  jb      short loc_14000AED0
0x14000aec9  mov     rax, [rsp+28h+arg_0]
0x14000aece  jmp     short loc_14000AEDD
0x14000aed0  mov     r8, rdx
0x14000aed3  mov     rdx, [rsp+28h+arg_0]
0x14000aed8  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14000aedd  add     rsp, 28h
0x14000aee1  retn
```
