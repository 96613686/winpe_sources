# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x1400203d4`
- end: `0x140020407`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002031c`
- `0x140020410`

## callees

- `0x1400203d4`
- `0x140020410`

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
0x1400203d4  sub     rsp, 28h
0x1400203d8  mov     eax, [rcx]
0x1400203da  mov     [rsp+28h+arg_0], 0
0x1400203e3  mov     dword ptr [rsp+28h+arg_0], eax
0x1400203e7  bt      eax, 9
0x1400203eb  jb      short loc_1400203F4
0x1400203ed  mov     rax, [rsp+28h+arg_0]
0x1400203f2  jmp     short loc_140020401
0x1400203f4  mov     r8, rdx
0x1400203f7  mov     rdx, [rsp+28h+arg_0]
0x1400203fc  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140020401  add     rsp, 28h
0x140020405  retn
```
