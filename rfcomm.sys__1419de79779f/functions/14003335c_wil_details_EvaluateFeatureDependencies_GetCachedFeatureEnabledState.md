# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14003335c`
- end: `0x14003338f`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140033398`

## callees

- `0x14003335c`
- `0x140033398`

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
0x14003335c  sub     rsp, 28h
0x140033360  mov     eax, [rcx]
0x140033362  mov     [rsp+28h+arg_0], 0
0x14003336b  mov     dword ptr [rsp+28h+arg_0], eax
0x14003336f  bt      eax, 9
0x140033373  jb      short loc_14003337C
0x140033375  mov     rax, [rsp+28h+arg_0]
0x14003337a  jmp     short loc_140033389
0x14003337c  mov     r8, rdx
0x14003337f  mov     rdx, [rsp+28h+arg_0]
0x140033384  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140033389  add     rsp, 28h
0x14003338d  retn
```
