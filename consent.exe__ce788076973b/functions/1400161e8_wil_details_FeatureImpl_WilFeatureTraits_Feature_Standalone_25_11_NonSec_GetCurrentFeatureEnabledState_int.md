# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1400161e8`
- end: `0x140016256`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400152a8`

## callees

- `0x1400161e8`
- `0x140017d24`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2AF34FD, (unsigned int)a2, a3, a4);
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
0x1400161e8  push    rbx
0x1400161ea  sub     rsp, 20h
0x1400161ee  mov     ecx, 2AF34FDh; this
0x1400161f3  mov     rbx, rdx
0x1400161f6  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1400161fb  mov     r9d, eax
0x1400161fe  mov     qword ptr [rbx], 0
0x140016205  and     r9d, 0FFFFFF3Fh
0x14001620c  mov     ecx, eax
0x14001620e  and     eax, 80h
0x140016213  mov     r8d, r9d
0x140016216  and     r8d, 3
0x14001621a  mov     edx, 40h ; '@'
0x14001621f  shl     r8d, 2
0x140016223  and     ecx, edx
0x140016225  or      r8d, ecx
0x140016228  shl     r8d, 2
0x14001622c  or      r8d, eax
0x14001622f  shl     r8d, 3
0x140016233  test    r9d, r9d
0x140016236  jz      short loc_140016243
0x140016238  xor     eax, eax
0x14001623a  cmp     r9d, 2
0x14001623e  cmovz   eax, edx
0x140016241  mov     edx, eax
0x140016243  or      r8d, edx
0x140016246  mov     rax, rbx
0x140016249  or      r8d, 1
0x14001624d  mov     [rbx], r8d
0x140016250  add     rsp, 20h
0x140016254  pop     rbx
0x140016255  retn
```
