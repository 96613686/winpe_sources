# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800274f8`
- end: `0x180027645`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `333`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180026ca8`

## callees

- `0x1800188c4`
- `0x18002331c`
- `0x180026828`
- `0x1800274f8`
- `0x180029130`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
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
  char v12; // si
  char v13; // cl
  wil::details *v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v17 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419AC, 3u, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_18;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_18003E3F0, 58599532, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_18:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800274f8  mov     [rsp+arg_10], rbx
0x1800274fd  mov     [rsp+arg_0], rcx
0x180027502  push    rbp
0x180027503  push    rsi
0x180027504  push    rdi
0x180027505  sub     rsp, 40h
0x180027509  mov     rbx, rdx
0x18002750c  mov     ecx, 38419ACh; this
0x180027511  mov     edx, 3; unsigned int
0x180027516  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18002751b  mov     edx, eax
0x18002751d  mov     qword ptr [rbx], 0
0x180027524  and     edx, 0FFFFFF3Fh
0x18002752a  mov     ecx, eax
0x18002752c  and     eax, 80h
0x180027531  mov     r8d, edx
0x180027534  and     r8d, 3
0x180027538  mov     ebp, 40h ; '@'
0x18002753d  shl     r8d, 2
0x180027541  and     ecx, ebp
0x180027543  or      r8d, ecx
0x180027546  shl     r8d, 2
0x18002754a  or      r8d, eax
0x18002754d  shl     r8d, 3
0x180027551  test    edx, edx
0x180027553  jnz     short loc_18002755B
0x180027555  mov     ecx, ebp
0x180027557  mov     edx, ebp
0x180027559  jmp     short loc_180027565
0x18002755b  xor     ecx, ecx
0x18002755d  cmp     edx, 2
0x180027560  cmovz   ecx, ebp
0x180027563  mov     edx, ecx
0x180027565  mov     eax, r8d
0x180027568  mov     edi, 1
0x18002756d  or      eax, edx
0x18002756f  or      r8d, ecx
0x180027572  mov     [rbx], eax
0x180027574  bt      r8d, 0Ah
0x180027579  jnb     short loc_180027589
0x18002757b  cmp     r8d, 800h
0x180027582  jb      short loc_180027589
0x180027584  mov     sil, dil
0x180027587  jmp     short loc_180027597
0x180027589  xor     sil, sil
0x18002758c  xor     cl, cl
0x18002758e  test    bpl, r8b
0x180027591  jz      loc_180027621
0x180027597  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18002759e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x1800275a3  test    al, al
0x1800275a5  jz      short loc_180027612
0x1800275a7  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x1800275ae  mov     r8d, [rax]
0x1800275b1  test    r8b, 4
0x1800275b5  jnz     short loc_1800275CC
0x1800275b7  lea     rdx, [rsp+58h+arg_8]
0x1800275bc  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x1800275c1  mov     rcx, [rax]
0x1800275c4  mov     [rsp+58h+arg_8], rcx
0x1800275c9  mov     r8d, ecx
0x1800275cc  xor     eax, eax
0x1800275ce  mov     word ptr [rsp+58h+arg_0+4], 3
0x1800275d5  mov     r9d, r8d
0x1800275d8  mov     [rsp+58h+var_28], eax
0x1800275dc  mov     dword ptr [rsp+58h+arg_0], eax
0x1800275e0  lea     rcx, qword_18003E3F0
0x1800275e7  shr     r9d, 0Bh
0x1800275eb  lea     rax, [rsp+58h+arg_0]
0x1800275f0  shr     r8d, 0Ah
0x1800275f4  and     r9d, edi
0x1800275f7  and     r8d, edi
0x1800275fa  mov     [rsp+58h+var_30], edi
0x1800275fe  mov     edx, 37E286Ch
0x180027603  mov     [rsp+58h+var_38], rax
0x180027608  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18002760d  mov     cl, dil
0x180027610  jmp     short loc_180027614
0x180027612  xor     cl, cl
0x180027614  test    sil, sil
0x180027617  jz      short loc_180027621
0x180027619  test    cl, cl
0x18002761b  jnz     short loc_180027621
0x18002761d  btr     dword ptr [rbx], 0Ah
0x180027621  mov     eax, [rbx]
0x180027623  test    bpl, al
0x180027626  jz      short loc_18002762C
0x180027628  test    cl, cl
0x18002762a  jnz     short loc_18002762E
0x18002762c  xor     edi, edi
0x18002762e  and     eax, 0FFFFFFFEh
0x180027631  or      eax, edi
0x180027633  mov     [rbx], eax
0x180027635  mov     rax, rbx
0x180027638  mov     rbx, [rsp+58h+arg_10]
0x18002763d  add     rsp, 40h
0x180027641  pop     rdi
0x180027642  pop     rsi
0x180027643  pop     rbp
0x180027644  retn
```
