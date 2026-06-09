# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140017c4c`
- end: `0x140017c7f`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140017c0c`
- `0x140017c88`

## callees

- `0x140017c4c`
- `0x140017c88`

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
0x140017c4c  sub     rsp, 28h
0x140017c50  mov     eax, [rcx]
0x140017c52  mov     [rsp+28h+arg_0], 0
0x140017c5b  mov     dword ptr [rsp+28h+arg_0], eax
0x140017c5f  bt      eax, 9
0x140017c63  jb      short loc_140017C6C
0x140017c65  mov     rax, [rsp+28h+arg_0]
0x140017c6a  jmp     short loc_140017C79
0x140017c6c  mov     r8, rdx
0x140017c6f  mov     rdx, [rsp+28h+arg_0]
0x140017c74  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140017c79  add     rsp, 28h
0x140017c7d  retn
```
