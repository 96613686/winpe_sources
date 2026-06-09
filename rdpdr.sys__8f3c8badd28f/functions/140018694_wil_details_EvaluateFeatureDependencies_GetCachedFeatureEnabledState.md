# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140018694`
- end: `0x1400186c7`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400185dc`
- `0x1400186d0`

## callees

- `0x140018694`
- `0x1400186d0`

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
0x140018694  sub     rsp, 28h
0x140018698  mov     eax, [rcx]
0x14001869a  mov     [rsp+28h+arg_0], 0
0x1400186a3  mov     dword ptr [rsp+28h+arg_0], eax
0x1400186a7  bt      eax, 9
0x1400186ab  jb      short loc_1400186B4
0x1400186ad  mov     rax, [rsp+28h+arg_0]
0x1400186b2  jmp     short loc_1400186C1
0x1400186b4  mov     r8, rdx
0x1400186b7  mov     rdx, [rsp+28h+arg_0]
0x1400186bc  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x1400186c1  add     rsp, 28h
0x1400186c5  retn
```
