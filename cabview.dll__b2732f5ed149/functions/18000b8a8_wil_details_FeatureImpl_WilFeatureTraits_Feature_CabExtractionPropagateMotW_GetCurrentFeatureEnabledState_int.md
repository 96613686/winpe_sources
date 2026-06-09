# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CabExtractionPropagateMotW>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000b8a8`
- end: `0x18000b92a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CabExtractionPropagateMotW@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b454`

## callees

- `0x180009604`
- `0x18000b8a8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CabExtractionPropagateMotW>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x36CAFBC, (unsigned int)a2, a3, a4);
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
0x18000b8a8  push    rbx
0x18000b8aa  sub     rsp, 20h
0x18000b8ae  mov     ecx, 36CAFBCh; this
0x18000b8b3  mov     rbx, rdx
0x18000b8b6  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000b8bb  mov     edx, eax
0x18000b8bd  mov     qword ptr [rbx], 0
0x18000b8c4  mov     ecx, eax
0x18000b8c6  and     edx, 0FFFFFF3Fh
0x18000b8cc  and     eax, 80h
0x18000b8d1  mov     r8d, edx
0x18000b8d4  and     r8d, 3
0x18000b8d8  mov     r9d, 40h ; '@'
0x18000b8de  shl     r8d, 2
0x18000b8e2  and     ecx, r9d
0x18000b8e5  or      r8d, ecx
0x18000b8e8  shl     r8d, 2
0x18000b8ec  or      r8d, eax
0x18000b8ef  xor     eax, eax
0x18000b8f1  shl     r8d, 3
0x18000b8f5  test    edx, edx
0x18000b8f7  jz      short loc_18000B900
0x18000b8f9  cmp     edx, 2
0x18000b8fc  cmovz   eax, r9d
0x18000b900  or      r8d, eax
0x18000b903  mov     ecx, 0C00h
0x18000b908  mov     eax, r8d
0x18000b90b  and     eax, ecx
0x18000b90d  test    r9b, r8b
0x18000b910  jz      short loc_18000B919
0x18000b912  mov     eax, 1
0x18000b917  jmp     short loc_18000B91B
0x18000b919  xor     eax, eax
0x18000b91b  or      r8d, eax
0x18000b91e  mov     rax, rbx
0x18000b921  mov     [rbx], r8d
0x18000b924  add     rsp, 20h
0x18000b928  pop     rbx
0x18000b929  retn
```
