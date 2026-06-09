# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000b930`
- end: `0x18000b9b2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b5b0`

## callees

- `0x180009604`
- `0x18000b930`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // r8d
  int v10; // r8d
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x344DED5, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v8 = 0;
  v9 = 8 * v7;
  if ( v6 == 2 )
    v8 = 64;
  v10 = v8 | v9;
  result = a2;
  *(_DWORD *)a2 = ((v10 & 0x40) != 0) | v10;
  return result;
}

```

## disassembly

```asm
0x18000b930  push    rbx
0x18000b932  sub     rsp, 20h
0x18000b936  mov     ecx, 344DED5h; this
0x18000b93b  mov     rbx, rdx
0x18000b93e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000b943  mov     edx, eax
0x18000b945  mov     qword ptr [rbx], 0
0x18000b94c  mov     ecx, eax
0x18000b94e  and     edx, 0FFFFFF3Fh
0x18000b954  and     eax, 80h
0x18000b959  mov     r8d, edx
0x18000b95c  and     r8d, 3
0x18000b960  mov     r9d, 40h ; '@'
0x18000b966  shl     r8d, 2
0x18000b96a  and     ecx, r9d
0x18000b96d  or      r8d, ecx
0x18000b970  shl     r8d, 2
0x18000b974  or      r8d, eax
0x18000b977  xor     eax, eax
0x18000b979  shl     r8d, 3
0x18000b97d  test    edx, edx
0x18000b97f  jz      short loc_18000B988
0x18000b981  cmp     edx, 2
0x18000b984  cmovz   eax, r9d
0x18000b988  or      r8d, eax
0x18000b98b  mov     ecx, 0C00h
0x18000b990  mov     eax, r8d
0x18000b993  and     eax, ecx
0x18000b995  test    r9b, r8b
0x18000b998  jz      short loc_18000B9A1
0x18000b99a  mov     eax, 1
0x18000b99f  jmp     short loc_18000B9A3
0x18000b9a1  xor     eax, eax
0x18000b9a3  or      r8d, eax
0x18000b9a6  mov     rax, rbx
0x18000b9a9  mov     [rbx], r8d
0x18000b9ac  add     rsp, 20h
0x18000b9b0  pop     rbx
0x18000b9b1  retn
```
