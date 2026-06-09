# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14001625c`
- end: `0x1400162ca`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400153d8`

## callees

- `0x14001625c`
- `0x140017d24`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37E286C, (unsigned int)a2, a3, a4);
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
0x14001625c  push    rbx
0x14001625e  sub     rsp, 20h
0x140016262  mov     ecx, 37E286Ch; this
0x140016267  mov     rbx, rdx
0x14001626a  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14001626f  mov     r9d, eax
0x140016272  mov     qword ptr [rbx], 0
0x140016279  and     r9d, 0FFFFFF3Fh
0x140016280  mov     ecx, eax
0x140016282  and     eax, 80h
0x140016287  mov     r8d, r9d
0x14001628a  and     r8d, 3
0x14001628e  mov     edx, 40h ; '@'
0x140016293  shl     r8d, 2
0x140016297  and     ecx, edx
0x140016299  or      r8d, ecx
0x14001629c  shl     r8d, 2
0x1400162a0  or      r8d, eax
0x1400162a3  shl     r8d, 3
0x1400162a7  test    r9d, r9d
0x1400162aa  jz      short loc_1400162B7
0x1400162ac  xor     eax, eax
0x1400162ae  cmp     r9d, 2
0x1400162b2  cmovz   eax, edx
0x1400162b5  mov     edx, eax
0x1400162b7  or      r8d, edx
0x1400162ba  mov     rax, rbx
0x1400162bd  or      r8d, 1
0x1400162c1  mov     [rbx], r8d
0x1400162c4  add     rsp, 20h
0x1400162c8  pop     rbx
0x1400162c9  retn
```
