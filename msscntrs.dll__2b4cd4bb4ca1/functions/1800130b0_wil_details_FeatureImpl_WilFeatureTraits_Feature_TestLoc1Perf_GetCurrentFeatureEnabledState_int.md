# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800130b0`
- end: `0x180013219`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800129b0`

## callees

- `0x18000cffc`
- `0x18000fa2c`
- `0x1800130b0`
- `0x180013778`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58988972, 3);
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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180022100, 58599532, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800130b0  mov     [rsp+arg_10], rbx
0x1800130b5  mov     [rsp+arg_0], rcx
0x1800130ba  push    rbp
0x1800130bb  push    rsi
0x1800130bc  push    rdi
0x1800130bd  sub     rsp, 40h
0x1800130c1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800130c8  mov     rbx, rdx
0x1800130cb  test    rax, rax
0x1800130ce  jz      short loc_1800130E3
0x1800130d0  mov     edx, 3
0x1800130d5  mov     ecx, 38419ACh
0x1800130da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130df  mov     edx, eax
0x1800130e1  jmp     short loc_1800130F1
0x1800130e3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800130ea  test    rax, rax
0x1800130ed  jnz     short loc_1800130D0
0x1800130ef  xor     edx, edx
0x1800130f1  mov     r8d, edx
0x1800130f4  mov     qword ptr [rbx], 0
0x1800130fb  and     r8d, 0FFFFFF3Fh
0x180013102  mov     eax, edx
0x180013104  and     edx, 80h
0x18001310a  mov     ecx, r8d
0x18001310d  and     ecx, 3
0x180013110  mov     ebp, 40h ; '@'
0x180013115  shl     ecx, 2
0x180013118  and     eax, ebp
0x18001311a  or      ecx, eax
0x18001311c  shl     ecx, 2
0x18001311f  or      ecx, edx
0x180013121  shl     ecx, 3
0x180013124  test    r8d, r8d
0x180013127  jnz     short loc_180013130
0x180013129  mov     edx, ebp
0x18001312b  mov     r8d, ebp
0x18001312e  jmp     short loc_18001313C
0x180013130  xor     edx, edx
0x180013132  cmp     r8d, 2
0x180013136  cmovz   edx, ebp
0x180013139  mov     r8d, edx
0x18001313c  mov     eax, ecx
0x18001313e  mov     edi, 1
0x180013143  or      eax, r8d
0x180013146  or      ecx, edx
0x180013148  mov     [rbx], eax
0x18001314a  bt      ecx, 0Ah
0x18001314e  jnb     short loc_18001315D
0x180013150  cmp     ecx, 800h
0x180013156  jb      short loc_18001315D
0x180013158  mov     sil, dil
0x18001315b  jmp     short loc_18001316B
0x18001315d  xor     sil, sil
0x180013160  xor     dl, dl
0x180013162  test    bpl, cl
0x180013165  jz      loc_1800131F5
0x18001316b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x180013172  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x180013177  test    al, al
0x180013179  jz      short loc_1800131E6
0x18001317b  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180013182  mov     r8d, [rax]
0x180013185  test    r8b, 4
0x180013189  jnz     short loc_1800131A0
0x18001318b  lea     rdx, [rsp+58h+arg_8]
0x180013190  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x180013195  mov     rcx, [rax]
0x180013198  mov     [rsp+58h+arg_8], rcx
0x18001319d  mov     r8d, ecx
0x1800131a0  xor     eax, eax
0x1800131a2  mov     word ptr [rsp+58h+arg_0+4], 3
0x1800131a9  mov     r9d, r8d
0x1800131ac  mov     [rsp+58h+var_28], eax
0x1800131b0  mov     dword ptr [rsp+58h+arg_0], eax
0x1800131b4  lea     rcx, qword_180022100
0x1800131bb  shr     r9d, 0Bh
0x1800131bf  lea     rax, [rsp+58h+arg_0]
0x1800131c4  shr     r8d, 0Ah
0x1800131c8  and     r9d, edi
0x1800131cb  and     r8d, edi
0x1800131ce  mov     [rsp+58h+var_30], edi
0x1800131d2  mov     edx, 37E286Ch
0x1800131d7  mov     [rsp+58h+var_38], rax
0x1800131dc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800131e1  mov     dl, dil
0x1800131e4  jmp     short loc_1800131E8
0x1800131e6  xor     dl, dl
0x1800131e8  test    sil, sil
0x1800131eb  jz      short loc_1800131F5
0x1800131ed  test    dl, dl
0x1800131ef  jnz     short loc_1800131F5
0x1800131f1  btr     dword ptr [rbx], 0Ah
0x1800131f5  mov     eax, [rbx]
0x1800131f7  test    bpl, al
0x1800131fa  jz      short loc_180013200
0x1800131fc  test    dl, dl
0x1800131fe  jnz     short loc_180013202
0x180013200  xor     edi, edi
0x180013202  and     eax, 0FFFFFFFEh
0x180013205  or      eax, edi
0x180013207  mov     [rbx], eax
0x180013209  mov     rax, rbx
0x18001320c  mov     rbx, [rsp+58h+arg_10]
0x180013211  add     rsp, 40h
0x180013215  pop     rdi
0x180013216  pop     rsi
0x180013217  pop     rbp
0x180013218  retn
```
