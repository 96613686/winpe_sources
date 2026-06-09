# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140011d5c`
- end: `0x140011d8f`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140011d1c`
- `0x140011d98`

## callees

- `0x140011d5c`
- `0x140011d98`

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
0x140011d5c  sub     rsp, 28h
0x140011d60  mov     eax, [rcx]
0x140011d62  mov     [rsp+28h+arg_0], 0
0x140011d6b  mov     dword ptr [rsp+28h+arg_0], eax
0x140011d6f  bt      eax, 9
0x140011d73  jb      short loc_140011D7C
0x140011d75  mov     rax, [rsp+28h+arg_0]
0x140011d7a  jmp     short loc_140011D89
0x140011d7c  mov     r8, rdx
0x140011d7f  mov     rdx, [rsp+28h+arg_0]
0x140011d84  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140011d89  add     rsp, 28h
0x140011d8d  retn
```
