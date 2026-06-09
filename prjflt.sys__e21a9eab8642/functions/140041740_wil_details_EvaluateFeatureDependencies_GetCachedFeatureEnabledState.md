# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140041740`
- end: `0x140041773`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14004177c`

## callees

- `0x140041740`
- `0x14004177c`

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
0x140041740  sub     rsp, 28h
0x140041744  mov     eax, [rcx]
0x140041746  mov     [rsp+28h+arg_0], 0
0x14004174f  mov     dword ptr [rsp+28h+arg_0], eax
0x140041753  bt      eax, 9
0x140041757  jb      short loc_140041760
0x140041759  mov     rax, [rsp+28h+arg_0]
0x14004175e  jmp     short loc_14004176D
0x140041760  mov     r8, rdx
0x140041763  mov     rdx, [rsp+28h+arg_0]
0x140041768  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14004176d  add     rsp, 28h
0x140041771  retn
```
