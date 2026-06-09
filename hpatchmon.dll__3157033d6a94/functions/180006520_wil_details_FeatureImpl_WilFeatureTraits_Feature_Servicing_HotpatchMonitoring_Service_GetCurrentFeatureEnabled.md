# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180006520`
- end: `0x180006662`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180005fc4`

## callees

- `0x180005e44`
- `0x180006520`
- `0x180009670`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetCurrentFeatureEnabledState(
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
    v4 = v2(55856256, 3);
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
    v13 = *(_DWORD *)Feature_ImplVal__descriptor;
    if ( (*(_DWORD *)Feature_ImplVal__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(v11, &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_18001E8D0, 54237993, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x180006520  mov     [rsp+arg_10], rbx
0x180006525  mov     [rsp+arg_18], rsi
0x18000652a  mov     [rsp+arg_0], rcx
0x18000652f  push    rdi
0x180006530  sub     rsp, 40h
0x180006534  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000653b  mov     rbx, rdx
0x18000653e  test    rax, rax
0x180006541  jz      short loc_180006556
0x180006543  mov     edx, 3
0x180006548  mov     ecx, 3544C80h
0x18000654d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006552  mov     edx, eax
0x180006554  jmp     short loc_180006564
0x180006556  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000655d  test    rax, rax
0x180006560  jnz     short loc_180006543
0x180006562  xor     edx, edx
0x180006564  mov     r8d, edx
0x180006567  mov     qword ptr [rbx], 0
0x18000656e  and     r8d, 0FFFFFF3Fh
0x180006575  mov     eax, edx
0x180006577  and     edx, 80h
0x18000657d  mov     ecx, r8d
0x180006580  and     ecx, 3
0x180006583  mov     esi, 40h ; '@'
0x180006588  shl     ecx, 2
0x18000658b  and     eax, esi
0x18000658d  or      ecx, eax
0x18000658f  shl     ecx, 2
0x180006592  or      ecx, edx
0x180006594  shl     ecx, 3
0x180006597  test    r8d, r8d
0x18000659a  jnz     short loc_1800065A3
0x18000659c  mov     edx, esi
0x18000659e  mov     r8d, esi
0x1800065a1  jmp     short loc_1800065AF
0x1800065a3  xor     edx, edx
0x1800065a5  cmp     r8d, 2
0x1800065a9  cmovz   edx, esi
0x1800065ac  mov     r8d, edx
0x1800065af  mov     eax, ecx
0x1800065b1  mov     edi, 1
0x1800065b6  or      eax, r8d
0x1800065b9  or      ecx, edx
0x1800065bb  mov     [rbx], eax
0x1800065bd  bt      ecx, 0Ah
0x1800065c1  jnb     short loc_1800065CB
0x1800065c3  cmp     ecx, 800h
0x1800065c9  jnb     short loc_1800065D2
0x1800065cb  xor     dl, dl
0x1800065cd  test    sil, cl
0x1800065d0  jz      short loc_18000663B
0x1800065d2  mov     rax, cs:Feature_ImplVal__descriptor
0x1800065d9  mov     r8d, [rax]
0x1800065dc  test    r8b, 4
0x1800065e0  jnz     short loc_1800065F7
0x1800065e2  lea     rdx, [rsp+48h+arg_8]
0x1800065e7  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImplVal@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(void)
0x1800065ec  mov     rcx, [rax]
0x1800065ef  mov     [rsp+48h+arg_8], rcx
0x1800065f4  mov     r8d, ecx
0x1800065f7  xor     eax, eax
0x1800065f9  mov     word ptr [rsp+48h+arg_0+4], 3
0x180006600  mov     r9d, r8d
0x180006603  mov     [rsp+48h+var_18], eax
0x180006607  mov     dword ptr [rsp+48h+arg_0], eax
0x18000660b  lea     rcx, qword_18001E8D0
0x180006612  shr     r9d, 0Bh
0x180006616  lea     rax, [rsp+48h+arg_0]
0x18000661b  shr     r8d, 0Ah
0x18000661f  and     r9d, edi
0x180006622  and     r8d, edi
0x180006625  mov     [rsp+48h+var_20], edi
0x180006629  mov     edx, 33B9B29h
0x18000662e  mov     [rsp+48h+var_28], rax
0x180006633  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180006638  mov     dl, dil
0x18000663b  mov     eax, [rbx]
0x18000663d  test    sil, al
0x180006640  jz      short loc_180006646
0x180006642  test    dl, dl
0x180006644  jnz     short loc_180006648
0x180006646  xor     edi, edi
0x180006648  mov     rsi, [rsp+48h+arg_18]
0x18000664d  and     eax, 0FFFFFFFEh
0x180006650  or      eax, edi
0x180006652  mov     [rbx], eax
0x180006654  mov     rax, rbx
0x180006657  mov     rbx, [rsp+48h+arg_10]
0x18000665c  add     rsp, 40h
0x180006660  pop     rdi
0x180006661  retn
```
