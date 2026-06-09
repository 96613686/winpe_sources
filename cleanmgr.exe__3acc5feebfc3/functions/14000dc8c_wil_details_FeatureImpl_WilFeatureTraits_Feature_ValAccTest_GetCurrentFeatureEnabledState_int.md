# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000dc8c`
- end: `0x14000dd5f`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `211`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d3e4`

## callees

- `0x140009c64`
- `0x14000dc8c`
- `0x14000e4e8`
- `0x14000ea24`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA7, 3u, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (v12 = 0, (v11 & 0x40) != 0) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl'::`2'::impl);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl'::`2'::impl);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x14000dc8c  mov     [rsp+arg_0], rbx
0x14000dc91  mov     [rsp+arg_8], rsi
0x14000dc96  push    rdi
0x14000dc97  sub     rsp, 20h
0x14000dc9b  mov     rbx, rdx
0x14000dc9e  mov     ecx, 3667CA7h; this
0x14000dca3  mov     edx, 3; unsigned int
0x14000dca8  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000dcad  mov     edx, eax
0x14000dcaf  mov     qword ptr [rbx], 0
0x14000dcb6  and     edx, 0FFFFFF3Fh
0x14000dcbc  mov     ecx, eax
0x14000dcbe  and     eax, 80h
0x14000dcc3  mov     r8d, edx
0x14000dcc6  and     r8d, 3
0x14000dcca  mov     esi, 40h ; '@'
0x14000dccf  shl     r8d, 2
0x14000dcd3  and     ecx, esi
0x14000dcd5  or      r8d, ecx
0x14000dcd8  shl     r8d, 2
0x14000dcdc  or      r8d, eax
0x14000dcdf  shl     r8d, 3
0x14000dce3  test    edx, edx
0x14000dce5  jnz     short loc_14000DCED
0x14000dce7  mov     ecx, esi
0x14000dce9  mov     edx, esi
0x14000dceb  jmp     short loc_14000DCF7
0x14000dced  xor     ecx, ecx
0x14000dcef  cmp     edx, 2
0x14000dcf2  cmovz   ecx, esi
0x14000dcf5  mov     edx, ecx
0x14000dcf7  mov     eax, r8d
0x14000dcfa  mov     edi, 1
0x14000dcff  or      eax, edx
0x14000dd01  or      r8d, ecx
0x14000dd04  mov     [rbx], eax
0x14000dd06  bt      r8d, 0Ah
0x14000dd0b  jnb     short loc_14000DD16
0x14000dd0d  cmp     r8d, 800h
0x14000dd14  jnb     short loc_14000DD1D
0x14000dd16  xor     cl, cl
0x14000dd18  test    sil, r8b
0x14000dd1b  jz      short loc_14000DD38
0x14000dd1d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x14000dd24  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000dd29  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x14000dd30  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000dd35  mov     cl, dil
0x14000dd38  mov     eax, [rbx]
0x14000dd3a  test    sil, al
0x14000dd3d  jz      short loc_14000DD43
0x14000dd3f  test    cl, cl
0x14000dd41  jnz     short loc_14000DD45
0x14000dd43  xor     edi, edi
0x14000dd45  mov     rsi, [rsp+28h+arg_8]
0x14000dd4a  and     eax, 0FFFFFFFEh
0x14000dd4d  or      eax, edi
0x14000dd4f  mov     [rbx], eax
0x14000dd51  mov     rax, rbx
0x14000dd54  mov     rbx, [rsp+28h+arg_0]
0x14000dd59  add     rsp, 20h
0x14000dd5d  pop     rdi
0x14000dd5e  retn
```
