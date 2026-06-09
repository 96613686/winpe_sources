# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x1800214dc`
- end: `0x18002150f`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180021424`
- `0x180021518`

## callees

- `0x1800214dc`
- `0x180021518`

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
0x1800214dc  sub     rsp, 28h
0x1800214e0  mov     eax, [rcx]
0x1800214e2  mov     [rsp+28h+arg_0], 0
0x1800214eb  mov     dword ptr [rsp+28h+arg_0], eax
0x1800214ef  bt      eax, 9
0x1800214f3  jb      short loc_1800214FC
0x1800214f5  mov     rax, [rsp+28h+arg_0]
0x1800214fa  jmp     short loc_180021509
0x1800214fc  mov     r8, rdx
0x1800214ff  mov     rdx, [rsp+28h+arg_0]
0x180021504  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x180021509  add     rsp, 28h
0x18002150d  retn
```
