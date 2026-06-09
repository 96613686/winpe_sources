# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14000f67c`
- end: `0x14000f6af`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f010`
- `0x14000f6b8`

## callees

- `0x14000f67c`
- `0x14000f6b8`

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
0x14000f67c  sub     rsp, 28h
0x14000f680  mov     eax, [rcx]
0x14000f682  mov     [rsp+28h+arg_0], 0
0x14000f68b  mov     dword ptr [rsp+28h+arg_0], eax
0x14000f68f  bt      eax, 9
0x14000f693  jb      short loc_14000F69C
0x14000f695  mov     rax, [rsp+28h+arg_0]
0x14000f69a  jmp     short loc_14000F6A9
0x14000f69c  mov     r8, rdx
0x14000f69f  mov     rdx, [rsp+28h+arg_0]
0x14000f6a4  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14000f6a9  add     rsp, 28h
0x14000f6ad  retn
```
