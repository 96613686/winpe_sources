# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000d860`
- end: `0x14000d8d3`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `115`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cf84`

## callees

- `0x140009c64`
- `0x14000d860`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37E2881, 3u, a3, a4);
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
0x14000d860  push    rbx
0x14000d862  sub     rsp, 20h
0x14000d866  mov     rbx, rdx
0x14000d869  mov     ecx, 37E2881h; this
0x14000d86e  mov     edx, 3; unsigned int
0x14000d873  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000d878  mov     r9d, eax
0x14000d87b  mov     qword ptr [rbx], 0
0x14000d882  and     r9d, 0FFFFFF3Fh
0x14000d889  mov     ecx, eax
0x14000d88b  and     eax, 80h
0x14000d890  mov     r8d, r9d
0x14000d893  and     r8d, 3
0x14000d897  mov     edx, 40h ; '@'
0x14000d89c  shl     r8d, 2
0x14000d8a0  and     ecx, edx
0x14000d8a2  or      r8d, ecx
0x14000d8a5  shl     r8d, 2
0x14000d8a9  or      r8d, eax
0x14000d8ac  shl     r8d, 3
0x14000d8b0  test    r9d, r9d
0x14000d8b3  jz      short loc_14000D8C0
0x14000d8b5  xor     eax, eax
0x14000d8b7  cmp     r9d, 2
0x14000d8bb  cmovz   eax, edx
0x14000d8be  mov     edx, eax
0x14000d8c0  or      r8d, edx
0x14000d8c3  mov     rax, rbx
0x14000d8c6  or      r8d, 1
0x14000d8ca  mov     [rbx], r8d
0x14000d8cd  add     rsp, 20h
0x14000d8d1  pop     rbx
0x14000d8d2  retn
```
