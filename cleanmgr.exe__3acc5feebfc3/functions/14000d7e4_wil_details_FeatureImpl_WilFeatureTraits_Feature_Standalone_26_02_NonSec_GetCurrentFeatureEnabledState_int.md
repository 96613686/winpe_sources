# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000d7e4`
- end: `0x14000d857`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `115`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cea4`

## callees

- `0x140009c64`
- `0x14000d7e4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37E287E, 3u, a3, a4);
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
0x14000d7e4  push    rbx
0x14000d7e6  sub     rsp, 20h
0x14000d7ea  mov     rbx, rdx
0x14000d7ed  mov     ecx, 37E287Eh; this
0x14000d7f2  mov     edx, 3; unsigned int
0x14000d7f7  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000d7fc  mov     r9d, eax
0x14000d7ff  mov     qword ptr [rbx], 0
0x14000d806  and     r9d, 0FFFFFF3Fh
0x14000d80d  mov     ecx, eax
0x14000d80f  and     eax, 80h
0x14000d814  mov     r8d, r9d
0x14000d817  and     r8d, 3
0x14000d81b  mov     edx, 40h ; '@'
0x14000d820  shl     r8d, 2
0x14000d824  and     ecx, edx
0x14000d826  or      r8d, ecx
0x14000d829  shl     r8d, 2
0x14000d82d  or      r8d, eax
0x14000d830  shl     r8d, 3
0x14000d834  test    r9d, r9d
0x14000d837  jz      short loc_14000D844
0x14000d839  xor     eax, eax
0x14000d83b  cmp     r9d, 2
0x14000d83f  cmovz   eax, edx
0x14000d842  mov     edx, eax
0x14000d844  or      r8d, edx
0x14000d847  mov     rax, rbx
0x14000d84a  or      r8d, 1
0x14000d84e  mov     [rbx], r8d
0x14000d851  add     rsp, 20h
0x14000d855  pop     rbx
0x14000d856  retn
```
