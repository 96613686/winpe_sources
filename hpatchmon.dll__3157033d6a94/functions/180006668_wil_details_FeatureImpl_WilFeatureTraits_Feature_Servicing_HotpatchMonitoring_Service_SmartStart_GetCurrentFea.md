# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180006668`
- end: `0x1800067aa`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800060a4`

## callees

- `0x180006184`
- `0x180006668`
- `0x180009670`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57894640, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
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
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(v11, &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_18001EA58, 57048226, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x180006668  mov     [rsp+arg_10], rbx
0x18000666d  mov     [rsp+arg_18], rsi
0x180006672  mov     [rsp+arg_0], rcx
0x180006677  push    rdi
0x180006678  sub     rsp, 40h
0x18000667c  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180006683  mov     rbx, rdx
0x180006686  test    rax, rax
0x180006689  jz      short loc_18000669E
0x18000668b  mov     edx, 3
0x180006690  mov     ecx, 37366F0h
0x180006695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000669a  mov     edx, eax
0x18000669c  jmp     short loc_1800066AC
0x18000669e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800066a5  test    rax, rax
0x1800066a8  jnz     short loc_18000668B
0x1800066aa  xor     edx, edx
0x1800066ac  mov     r8d, edx
0x1800066af  mov     qword ptr [rbx], 0
0x1800066b6  and     r8d, 0FFFFFF3Fh
0x1800066bd  mov     eax, edx
0x1800066bf  and     edx, 80h
0x1800066c5  mov     ecx, r8d
0x1800066c8  and     ecx, 3
0x1800066cb  mov     esi, 40h ; '@'
0x1800066d0  shl     ecx, 2
0x1800066d3  and     eax, esi
0x1800066d5  or      ecx, eax
0x1800066d7  shl     ecx, 2
0x1800066da  or      ecx, edx
0x1800066dc  shl     ecx, 3
0x1800066df  test    r8d, r8d
0x1800066e2  jnz     short loc_1800066EB
0x1800066e4  mov     edx, esi
0x1800066e6  mov     r8d, esi
0x1800066e9  jmp     short loc_1800066F7
0x1800066eb  xor     edx, edx
0x1800066ed  cmp     r8d, 2
0x1800066f1  cmovz   edx, esi
0x1800066f4  mov     r8d, edx
0x1800066f7  mov     eax, ecx
0x1800066f9  mov     edi, 1
0x1800066fe  or      eax, r8d
0x180006701  or      ecx, edx
0x180006703  mov     [rbx], eax
0x180006705  bt      ecx, 0Ah
0x180006709  jnb     short loc_180006713
0x18000670b  cmp     ecx, 800h
0x180006711  jnb     short loc_18000671A
0x180006713  xor     dl, dl
0x180006715  test    sil, cl
0x180006718  jz      short loc_180006783
0x18000671a  mov     rax, cs:Feature_ValLabTest__descriptor
0x180006721  mov     r8d, [rax]
0x180006724  test    r8b, 4
0x180006728  jnz     short loc_18000673F
0x18000672a  lea     rdx, [rsp+48h+arg_8]
0x18000672f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180006734  mov     rcx, [rax]
0x180006737  mov     [rsp+48h+arg_8], rcx
0x18000673c  mov     r8d, ecx
0x18000673f  xor     eax, eax
0x180006741  mov     word ptr [rsp+48h+arg_0+4], 3
0x180006748  mov     r9d, r8d
0x18000674b  mov     [rsp+48h+var_18], eax
0x18000674f  mov     dword ptr [rsp+48h+arg_0], eax
0x180006753  lea     rcx, qword_18001EA58
0x18000675a  shr     r9d, 0Bh
0x18000675e  lea     rax, [rsp+48h+arg_0]
0x180006763  shr     r8d, 0Ah
0x180006767  and     r9d, edi
0x18000676a  and     r8d, edi
0x18000676d  mov     [rsp+48h+var_20], edi
0x180006771  mov     edx, 3667CA2h
0x180006776  mov     [rsp+48h+var_28], rax
0x18000677b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180006780  mov     dl, dil
0x180006783  mov     eax, [rbx]
0x180006785  test    sil, al
0x180006788  jz      short loc_18000678E
0x18000678a  test    dl, dl
0x18000678c  jnz     short loc_180006790
0x18000678e  xor     edi, edi
0x180006790  mov     rsi, [rsp+48h+arg_18]
0x180006795  and     eax, 0FFFFFFFEh
0x180006798  or      eax, edi
0x18000679a  mov     [rbx], eax
0x18000679c  mov     rax, rbx
0x18000679f  mov     rbx, [rsp+48h+arg_10]
0x1800067a4  add     rsp, 40h
0x1800067a8  pop     rdi
0x1800067a9  retn
```
