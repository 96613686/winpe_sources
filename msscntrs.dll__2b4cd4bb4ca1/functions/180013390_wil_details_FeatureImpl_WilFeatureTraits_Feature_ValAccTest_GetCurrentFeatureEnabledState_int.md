# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180013390`
- end: `0x180013534`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012b70`

## callees

- `0x18000cd14`
- `0x18000fa2c`
- `0x180012c50`
- `0x180013390`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // ebx
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  wil::details *v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+20h] BYREF
  __int64 v18; // [rsp+68h] [rbp+28h] BYREF

  v17 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048231, 3);
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
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(v11, &v18);
      v13 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180022308, 57048226, (v13 >> 10) & 1, (v13 >> 11) & 1, &v17, 1, 0);
    v15 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_1800220E0, 45036792, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x180013390  mov     [rsp-18h+arg_10], rbx
0x180013395  mov     [rsp-18h+arg_0], rcx
0x18001339a  push    rbp
0x18001339b  push    rdi
0x18001339c  push    r14
0x18001339e  mov     rbp, rsp
0x1800133a1  sub     rsp, 40h
0x1800133a5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800133ac  mov     rdi, rdx
0x1800133af  test    rax, rax
0x1800133b2  jz      short loc_1800133C7
0x1800133b4  mov     edx, 3
0x1800133b9  mov     ecx, 3667CA7h
0x1800133be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c3  mov     edx, eax
0x1800133c5  jmp     short loc_1800133D5
0x1800133c7  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800133ce  test    rax, rax
0x1800133d1  jnz     short loc_1800133B4
0x1800133d3  xor     edx, edx
0x1800133d5  mov     r8d, edx
0x1800133d8  mov     qword ptr [rdi], 0
0x1800133df  and     r8d, 0FFFFFF3Fh
0x1800133e6  mov     eax, edx
0x1800133e8  and     edx, 80h
0x1800133ee  mov     ecx, r8d
0x1800133f1  and     ecx, 3
0x1800133f4  mov     r14d, 40h ; '@'
0x1800133fa  shl     ecx, 2
0x1800133fd  and     eax, r14d
0x180013400  or      ecx, eax
0x180013402  shl     ecx, 2
0x180013405  or      ecx, edx
0x180013407  shl     ecx, 3
0x18001340a  test    r8d, r8d
0x18001340d  jnz     short loc_180013417
0x18001340f  mov     edx, r14d
0x180013412  mov     r8d, r14d
0x180013415  jmp     short loc_180013424
0x180013417  xor     edx, edx
0x180013419  cmp     r8d, 2
0x18001341d  cmovz   edx, r14d
0x180013421  mov     r8d, edx
0x180013424  mov     eax, ecx
0x180013426  mov     ebx, 1
0x18001342b  or      eax, r8d
0x18001342e  or      ecx, edx
0x180013430  mov     [rdi], eax
0x180013432  bt      ecx, 0Ah
0x180013436  jnb     short loc_180013440
0x180013438  cmp     ecx, 800h
0x18001343e  jnb     short loc_18001344B
0x180013440  xor     dl, dl
0x180013442  test    r14b, cl
0x180013445  jz      loc_18001350F
0x18001344b  mov     rax, cs:Feature_ValLabTest__descriptor
0x180013452  mov     r8d, [rax]
0x180013455  test    r8b, 4
0x180013459  jnz     short loc_18001346E
0x18001345b  lea     rdx, [rbp+arg_8]
0x18001345f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180013464  mov     rcx, [rax]
0x180013467  mov     [rbp+arg_8], rcx
0x18001346b  mov     r8d, ecx
0x18001346e  xor     eax, eax
0x180013470  mov     word ptr [rbp+arg_0+4], 3
0x180013476  mov     r9d, r8d
0x180013479  mov     [rsp+40h+var_10], eax
0x18001347d  mov     dword ptr [rbp+arg_0], eax
0x180013480  lea     rcx, qword_180022308
0x180013487  shr     r9d, 0Bh
0x18001348b  lea     rax, [rbp+arg_0]
0x18001348f  shr     r8d, 0Ah
0x180013493  and     r9d, ebx
0x180013496  and     r8d, ebx
0x180013499  mov     [rsp+40h+var_18], ebx
0x18001349d  mov     edx, 3667CA2h
0x1800134a2  mov     [rsp+40h+var_20], rax
0x1800134a7  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800134ac  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x1800134b3  mov     r8d, [rax]
0x1800134b6  test    r8b, 4
0x1800134ba  jnz     short loc_1800134CF
0x1800134bc  lea     rdx, [rbp+arg_8]
0x1800134c0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x1800134c5  mov     rcx, [rax]
0x1800134c8  mov     [rbp+arg_8], rcx
0x1800134cc  mov     r8d, ecx
0x1800134cf  xor     eax, eax
0x1800134d1  mov     word ptr [rbp+arg_0+4], 3
0x1800134d7  mov     r9d, r8d
0x1800134da  mov     [rsp+40h+var_10], eax
0x1800134de  mov     dword ptr [rbp+arg_0], eax
0x1800134e1  lea     rcx, qword_1800220E0
0x1800134e8  shr     r9d, 0Bh
0x1800134ec  lea     rax, [rbp+arg_0]
0x1800134f0  shr     r8d, 0Ah
0x1800134f4  and     r9d, ebx
0x1800134f7  and     r8d, ebx
0x1800134fa  mov     [rsp+40h+var_18], ebx
0x1800134fe  mov     edx, 2AF34F8h
0x180013503  mov     [rsp+40h+var_20], rax
0x180013508  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001350d  mov     dl, bl
0x18001350f  mov     eax, [rdi]
0x180013511  test    r14b, al
0x180013514  jz      short loc_18001351A
0x180013516  test    dl, dl
0x180013518  jnz     short loc_18001351C
0x18001351a  xor     ebx, ebx
0x18001351c  and     eax, 0FFFFFFFEh
0x18001351f  or      eax, ebx
0x180013521  mov     rbx, [rsp+40h+arg_10]
0x180013526  mov     [rdi], eax
0x180013528  mov     rax, rdi
0x18001352b  add     rsp, 40h
0x18001352f  pop     r14
0x180013531  pop     rdi
0x180013532  pop     rbp
0x180013533  retn
```
