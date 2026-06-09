# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001dc84`
- end: `0x18001dcf2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d17c`

## callees

- `0x18001beec`
- `0x18001dc84`

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
0x18001dc84  push    rbx
0x18001dc86  sub     rsp, 20h
0x18001dc8a  mov     ecx, 2AF34F8h; this
0x18001dc8f  mov     rbx, rdx
0x18001dc92  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001dc97  mov     r9d, eax
0x18001dc9a  mov     qword ptr [rbx], 0
0x18001dca1  and     r9d, 0FFFFFF3Fh
0x18001dca8  mov     ecx, eax
0x18001dcaa  and     eax, 80h
0x18001dcaf  mov     r8d, r9d
0x18001dcb2  and     r8d, 3
0x18001dcb6  mov     edx, 40h ; '@'
0x18001dcbb  shl     r8d, 2
0x18001dcbf  and     ecx, edx
0x18001dcc1  or      r8d, ecx
0x18001dcc4  shl     r8d, 2
0x18001dcc8  or      r8d, eax
0x18001dccb  shl     r8d, 3
0x18001dccf  test    r9d, r9d
0x18001dcd2  jz      short loc_18001DCDF
0x18001dcd4  xor     eax, eax
0x18001dcd6  cmp     r9d, 2
0x18001dcda  cmovz   eax, edx
0x18001dcdd  mov     edx, eax
0x18001dcdf  or      r8d, edx
0x18001dce2  mov     rax, rbx
0x18001dce5  or      r8d, 1
0x18001dce9  mov     [rbx], r8d
0x18001dcec  add     rsp, 20h
0x18001dcf0  pop     rbx
0x18001dcf1  retn
```
