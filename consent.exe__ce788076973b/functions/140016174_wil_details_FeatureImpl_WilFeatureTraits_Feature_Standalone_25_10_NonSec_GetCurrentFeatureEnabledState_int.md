# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140016174`
- end: `0x1400161e2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140015178`

## callees

- `0x140016174`
- `0x140017d24`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2AF34F8, (unsigned int)a2, a3, a4);
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
0x140016174  push    rbx
0x140016176  sub     rsp, 20h
0x14001617a  mov     ecx, 2AF34F8h; this
0x14001617f  mov     rbx, rdx
0x140016182  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x140016187  mov     r9d, eax
0x14001618a  mov     qword ptr [rbx], 0
0x140016191  and     r9d, 0FFFFFF3Fh
0x140016198  mov     ecx, eax
0x14001619a  and     eax, 80h
0x14001619f  mov     r8d, r9d
0x1400161a2  and     r8d, 3
0x1400161a6  mov     edx, 40h ; '@'
0x1400161ab  shl     r8d, 2
0x1400161af  and     ecx, edx
0x1400161b1  or      r8d, ecx
0x1400161b4  shl     r8d, 2
0x1400161b8  or      r8d, eax
0x1400161bb  shl     r8d, 3
0x1400161bf  test    r9d, r9d
0x1400161c2  jz      short loc_1400161CF
0x1400161c4  xor     eax, eax
0x1400161c6  cmp     r9d, 2
0x1400161ca  cmovz   eax, edx
0x1400161cd  mov     edx, eax
0x1400161cf  or      r8d, edx
0x1400161d2  mov     rax, rbx
0x1400161d5  or      r8d, 1
0x1400161d9  mov     [rbx], r8d
0x1400161dc  add     rsp, 20h
0x1400161e0  pop     rbx
0x1400161e1  retn
```
