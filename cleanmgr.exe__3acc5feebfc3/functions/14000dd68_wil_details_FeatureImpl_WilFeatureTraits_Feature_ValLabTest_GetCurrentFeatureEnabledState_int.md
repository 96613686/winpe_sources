# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000dd68`
- end: `0x14000dddb`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `115`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d4c4`

## callees

- `0x140009c64`
- `0x14000dd68`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // r9d
  int v7; // edx
  int v8; // r8d
  int v9; // eax
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA2, 3u, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 64;
  v8 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v9 = 0;
    if ( v6 == 2 )
      v9 = 64;
    v7 = v9;
  }
  result = a2;
  *(_DWORD *)a2 = v7 | v8 | 1;
  return result;
}

```

## disassembly

```asm
0x14000dd68  push    rbx
0x14000dd6a  sub     rsp, 20h
0x14000dd6e  mov     rbx, rdx
0x14000dd71  mov     ecx, 3667CA2h; this
0x14000dd76  mov     edx, 3; unsigned int
0x14000dd7b  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000dd80  mov     r9d, eax
0x14000dd83  mov     qword ptr [rbx], 0
0x14000dd8a  and     r9d, 0FFFFFF3Fh
0x14000dd91  mov     ecx, eax
0x14000dd93  and     eax, 80h
0x14000dd98  mov     r8d, r9d
0x14000dd9b  and     r8d, 3
0x14000dd9f  mov     edx, 40h ; '@'
0x14000dda4  shl     r8d, 2
0x14000dda8  and     ecx, edx
0x14000ddaa  or      r8d, ecx
0x14000ddad  shl     r8d, 2
0x14000ddb1  or      r8d, eax
0x14000ddb4  shl     r8d, 3
0x14000ddb8  test    r9d, r9d
0x14000ddbb  jz      short loc_14000DDC8
0x14000ddbd  xor     eax, eax
0x14000ddbf  cmp     r9d, 2
0x14000ddc3  cmovz   eax, edx
0x14000ddc6  mov     edx, eax
0x14000ddc8  or      r8d, edx
0x14000ddcb  mov     rax, rbx
0x14000ddce  or      r8d, 1
0x14000ddd2  mov     [rbx], r8d
0x14000ddd5  add     rsp, 20h
0x14000ddd9  pop     rbx
0x14000ddda  retn
```
