# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x18003927c`
- end: `0x1800392af`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18003923c`
- `0x1800392b8`

## callees

- `0x18003927c`
- `0x1800392b8`

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
0x18003927c  sub     rsp, 28h
0x180039280  mov     eax, [rcx]
0x180039282  mov     [rsp+28h+arg_0], 0
0x18003928b  mov     dword ptr [rsp+28h+arg_0], eax
0x18003928f  bt      eax, 9
0x180039293  jb      short loc_18003929C
0x180039295  mov     rax, [rsp+28h+arg_0]
0x18003929a  jmp     short loc_1800392A9
0x18003929c  mov     r8, rdx
0x18003929f  mov     rdx, [rsp+28h+arg_0]
0x1800392a4  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x1800392a9  add     rsp, 28h
0x1800392ad  retn
```
