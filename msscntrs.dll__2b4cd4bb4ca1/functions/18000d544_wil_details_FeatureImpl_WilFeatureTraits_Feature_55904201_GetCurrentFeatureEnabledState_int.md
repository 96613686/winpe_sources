# wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000d544`
- end: `0x18000d69b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `343`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000c984`

## callees

- `0x18000d170`
- `0x18000d544`
- `0x18000fa2c`
- `0x1800108fc`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // eax
  int v7; // ecx
  int v8; // edx
  wil::details *v9; // rcx
  int v10; // edi
  char v11; // si
  bool v12; // dl
  unsigned int v13; // r8d
  char IsEnabled; // al
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(55904201, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 0;
  v7 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  v8 = v7;
  if ( v5 )
  {
    if ( v5 == 2 )
      v6 = 64;
    v8 = v6 | v7;
  }
  v9 = (wil::details *)(v6 | (unsigned int)v7);
  *(_DWORD *)a2 = v8;
  v10 = 1;
  if ( ((unsigned __int16)v9 & 0xC00) == 0xC00 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    v12 = 0;
    if ( ((unsigned __int8)v9 & 0x40) == 0 )
      goto LABEL_17;
  }
  v13 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
  {
    v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
             v9,
             &v17);
    v13 = v17;
  }
  WORD2(v16) = 3;
  LODWORD(v16) = 0;
  wil::details::ReportUsageToService(&qword_180022110, 58599550, (v13 >> 10) & 1, (v13 >> 11) & 1, &v16, 1, 0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_58044763>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58044763>::GetImpl'::`2'::impl);
  v12 = IsEnabled != 0;
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_17:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v10 = 0;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18000d544  mov     [rsp+arg_10], rbx
0x18000d549  mov     [rsp+arg_0], rcx
0x18000d54e  push    rbp
0x18000d54f  push    rsi
0x18000d550  push    rdi
0x18000d551  sub     rsp, 40h
0x18000d555  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000d55c  mov     rbx, rdx
0x18000d55f  test    rax, rax
0x18000d562  jz      short loc_18000D577
0x18000d564  mov     edx, 3
0x18000d569  mov     ecx, 35507C9h
0x18000d56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d573  mov     edx, eax
0x18000d575  jmp     short loc_18000D585
0x18000d577  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000d57e  test    rax, rax
0x18000d581  jnz     short loc_18000D564
0x18000d583  xor     edx, edx
0x18000d585  mov     r8d, edx
0x18000d588  mov     qword ptr [rbx], 0
0x18000d58f  mov     eax, edx
0x18000d591  and     r8d, 0FFFFFF3Fh
0x18000d598  and     edx, 80h
0x18000d59e  mov     ecx, r8d
0x18000d5a1  and     ecx, 3
0x18000d5a4  mov     ebp, 40h ; '@'
0x18000d5a9  shl     ecx, 2
0x18000d5ac  and     eax, ebp
0x18000d5ae  or      ecx, eax
0x18000d5b0  xor     eax, eax
0x18000d5b2  shl     ecx, 2
0x18000d5b5  or      ecx, edx
0x18000d5b7  shl     ecx, 3
0x18000d5ba  mov     edx, ecx
0x18000d5bc  test    r8d, r8d
0x18000d5bf  jz      short loc_18000D5CA
0x18000d5c1  cmp     r8d, 2
0x18000d5c5  cmovz   eax, ebp
0x18000d5c8  or      edx, eax
0x18000d5ca  or      ecx, eax
0x18000d5cc  mov     [rbx], edx
0x18000d5ce  mov     edx, 0C00h
0x18000d5d3  mov     eax, ecx
0x18000d5d5  and     eax, edx
0x18000d5d7  mov     edi, 1
0x18000d5dc  cmp     eax, edx
0x18000d5de  jnz     short loc_18000D5E5
0x18000d5e0  mov     sil, dil
0x18000d5e3  jmp     short loc_18000D5F3
0x18000d5e5  xor     sil, sil
0x18000d5e8  xor     dl, dl
0x18000d5ea  test    bpl, cl
0x18000d5ed  jz      loc_18000D677
0x18000d5f3  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000d5fa  mov     r8d, [rax]
0x18000d5fd  test    r8b, 4
0x18000d601  jnz     short loc_18000D618
0x18000d603  lea     rdx, [rsp+58h+arg_8]
0x18000d608  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x18000d60d  mov     rcx, [rax]
0x18000d610  mov     [rsp+58h+arg_8], rcx
0x18000d615  mov     r8d, ecx
0x18000d618  xor     eax, eax
0x18000d61a  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000d621  mov     r9d, r8d
0x18000d624  mov     [rsp+58h+var_28], eax
0x18000d628  mov     dword ptr [rsp+58h+arg_0], eax
0x18000d62c  lea     rcx, qword_180022110
0x18000d633  shr     r9d, 0Bh
0x18000d637  lea     rax, [rsp+58h+arg_0]
0x18000d63c  shr     r8d, 0Ah
0x18000d640  and     r9d, edi
0x18000d643  and     r8d, edi
0x18000d646  mov     [rsp+58h+var_30], edi
0x18000d64a  mov     edx, 37E287Eh
0x18000d64f  mov     [rsp+58h+var_38], rax
0x18000d654  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000d659  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58044763@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58044763@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58044763> `wil::Feature<__WilFeatureTraits_Feature_58044763>::GetImpl(void)'::`2'::impl
0x18000d660  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58044763@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58044763>::__private_IsEnabled(wil::ReportingKind)
0x18000d665  test    al, al
0x18000d667  setnz   dl
0x18000d66a  test    sil, sil
0x18000d66d  jz      short loc_18000D677
0x18000d66f  test    dl, dl
0x18000d671  jnz     short loc_18000D677
0x18000d673  btr     dword ptr [rbx], 0Ah
0x18000d677  mov     eax, [rbx]
0x18000d679  test    bpl, al
0x18000d67c  jz      short loc_18000D682
0x18000d67e  test    dl, dl
0x18000d680  jnz     short loc_18000D684
0x18000d682  xor     edi, edi
0x18000d684  and     eax, 0FFFFFFFEh
0x18000d687  or      eax, edi
0x18000d689  mov     [rbx], eax
0x18000d68b  mov     rax, rbx
0x18000d68e  mov     rbx, [rsp+58h+arg_10]
0x18000d693  add     rsp, 40h
0x18000d697  pop     rdi
0x18000d698  pop     rsi
0x18000d699  pop     rbp
0x18000d69a  retn
```
