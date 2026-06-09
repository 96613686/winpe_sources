# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140024888`
- end: `0x1400248bb`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: `__int64 __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400248c4`

## callees

- `0x140024888`
- `0x1400248c4`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(_DWORD *a1, __int64 a2)
{
  __int64 result; // rax

  LODWORD(result) = *a1;
  if ( (*a1 & 0x200) != 0 )
    return wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(a1, (unsigned int)result, a2);
  else
    return (unsigned int)result;
}

```

## disassembly

```asm
0x140024888  sub     rsp, 28h
0x14002488c  mov     eax, [rcx]
0x14002488e  mov     [rsp+28h+arg_0], 0
0x140024897  mov     dword ptr [rsp+28h+arg_0], eax
0x14002489b  bt      eax, 9
0x14002489f  jb      short loc_1400248A8
0x1400248a1  mov     rax, [rsp+28h+arg_0]
0x1400248a6  jmp     short loc_1400248B5
0x1400248a8  mov     r8, rdx
0x1400248ab  mov     rdx, [rsp+28h+arg_0]
0x1400248b0  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x1400248b5  add     rsp, 28h
0x1400248b9  retn
```
