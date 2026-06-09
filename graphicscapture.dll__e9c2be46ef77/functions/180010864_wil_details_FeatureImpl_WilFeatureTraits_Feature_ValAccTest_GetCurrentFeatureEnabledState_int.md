# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180010864`
- end: `0x180010937`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180010334`

## callees

- `0x180010864`
- `0x18001198c`
- `0x180011ba4`
- `0x180012298`

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
0x180010864  mov     [rsp+arg_0], rbx
0x180010869  mov     [rsp+arg_8], rsi
0x18001086e  push    rdi
0x18001086f  sub     rsp, 20h
0x180010873  mov     rbx, rdx
0x180010876  mov     ecx, 3667CA7h; this
0x18001087b  mov     edx, 3; unsigned int
0x180010880  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180010885  mov     edx, eax
0x180010887  mov     qword ptr [rbx], 0
0x18001088e  and     edx, 0FFFFFF3Fh
0x180010894  mov     ecx, eax
0x180010896  and     eax, 80h
0x18001089b  mov     r8d, edx
0x18001089e  and     r8d, 3
0x1800108a2  mov     esi, 40h ; '@'
0x1800108a7  shl     r8d, 2
0x1800108ab  and     ecx, esi
0x1800108ad  or      r8d, ecx
0x1800108b0  shl     r8d, 2
0x1800108b4  or      r8d, eax
0x1800108b7  shl     r8d, 3
0x1800108bb  test    edx, edx
0x1800108bd  jnz     short loc_1800108C5
0x1800108bf  mov     ecx, esi
0x1800108c1  mov     edx, esi
0x1800108c3  jmp     short loc_1800108CF
0x1800108c5  xor     ecx, ecx
0x1800108c7  cmp     edx, 2
0x1800108ca  cmovz   ecx, esi
0x1800108cd  mov     edx, ecx
0x1800108cf  mov     eax, r8d
0x1800108d2  mov     edi, 1
0x1800108d7  or      eax, edx
0x1800108d9  or      r8d, ecx
0x1800108dc  mov     [rbx], eax
0x1800108de  bt      r8d, 0Ah
0x1800108e3  jnb     short loc_1800108EE
0x1800108e5  cmp     r8d, 800h
0x1800108ec  jnb     short loc_1800108F5
0x1800108ee  xor     cl, cl
0x1800108f0  test    sil, r8b
0x1800108f3  jz      short loc_180010910
0x1800108f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x1800108fc  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180010901  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x180010908  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001090d  mov     cl, dil
0x180010910  mov     eax, [rbx]
0x180010912  test    sil, al
0x180010915  jz      short loc_18001091B
0x180010917  test    cl, cl
0x180010919  jnz     short loc_18001091D
0x18001091b  xor     edi, edi
0x18001091d  mov     rsi, [rsp+28h+arg_8]
0x180010922  and     eax, 0FFFFFFFEh
0x180010925  or      eax, edi
0x180010927  mov     [rbx], eax
0x180010929  mov     rax, rbx
0x18001092c  mov     rbx, [rsp+28h+arg_0]
0x180010931  add     rsp, 20h
0x180010935  pop     rdi
0x180010936  retn
```
