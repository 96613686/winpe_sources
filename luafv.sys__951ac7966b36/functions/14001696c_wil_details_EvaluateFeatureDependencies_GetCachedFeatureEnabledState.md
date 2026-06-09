# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14001696c`
- end: `0x14001699f`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: `__int64 __fastcall(_DWORD *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001692c`
- `0x1400169a8`

## callees

- `0x14001696c`
- `0x1400169a8`

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
0x14001696c  sub     rsp, 28h
0x140016970  mov     eax, [rcx]
0x140016972  mov     [rsp+28h+arg_0], 0
0x14001697b  mov     dword ptr [rsp+28h+arg_0], eax
0x14001697f  bt      eax, 9
0x140016983  jb      short loc_14001698C
0x140016985  mov     rax, [rsp+28h+arg_0]
0x14001698a  jmp     short loc_140016999
0x14001698c  mov     r8, rdx
0x14001698f  mov     rdx, [rsp+28h+arg_0]
0x140016994  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140016999  add     rsp, 28h
0x14001699d  retn
```
