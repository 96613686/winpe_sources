# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180027250`
- end: `0x18002739d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `333`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180026ae8`

## callees

- `0x1800188c4`
- `0x18002331c`
- `0x180026988`
- `0x180027250`
- `0x18002916c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
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
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419CA, 3u, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_18003E410, 58599550, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x180027250  mov     [rsp+arg_10], rbx
0x180027255  mov     [rsp+arg_0], rcx
0x18002725a  push    rbp
0x18002725b  push    rsi
0x18002725c  push    rdi
0x18002725d  sub     rsp, 40h
0x180027261  mov     rbx, rdx
0x180027264  mov     ecx, 38419CAh; this
0x180027269  mov     edx, 3; unsigned int
0x18002726e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180027273  mov     edx, eax
0x180027275  mov     qword ptr [rbx], 0
0x18002727c  and     edx, 0FFFFFF3Fh
0x180027282  mov     ecx, eax
0x180027284  and     eax, 80h
0x180027289  mov     r8d, edx
0x18002728c  and     r8d, 3
0x180027290  mov     ebp, 40h ; '@'
0x180027295  shl     r8d, 2
0x180027299  and     ecx, ebp
0x18002729b  or      r8d, ecx
0x18002729e  shl     r8d, 2
0x1800272a2  or      r8d, eax
0x1800272a5  shl     r8d, 3
0x1800272a9  test    edx, edx
0x1800272ab  jnz     short loc_1800272B3
0x1800272ad  mov     ecx, ebp
0x1800272af  mov     edx, ebp
0x1800272b1  jmp     short loc_1800272BD
0x1800272b3  xor     ecx, ecx
0x1800272b5  cmp     edx, 2
0x1800272b8  cmovz   ecx, ebp
0x1800272bb  mov     edx, ecx
0x1800272bd  mov     eax, r8d
0x1800272c0  mov     edi, 1
0x1800272c5  or      eax, edx
0x1800272c7  or      r8d, ecx
0x1800272ca  mov     [rbx], eax
0x1800272cc  bt      r8d, 0Ah
0x1800272d1  jnb     short loc_1800272E1
0x1800272d3  cmp     r8d, 800h
0x1800272da  jb      short loc_1800272E1
0x1800272dc  mov     sil, dil
0x1800272df  jmp     short loc_1800272EF
0x1800272e1  xor     sil, sil
0x1800272e4  xor     cl, cl
0x1800272e6  test    bpl, r8b
0x1800272e9  jz      loc_180027379
0x1800272ef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x1800272f6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x1800272fb  test    al, al
0x1800272fd  jz      short loc_18002736A
0x1800272ff  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180027306  mov     r8d, [rax]
0x180027309  test    r8b, 4
0x18002730d  jnz     short loc_180027324
0x18002730f  lea     rdx, [rsp+58h+arg_8]
0x180027314  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180027319  mov     rcx, [rax]
0x18002731c  mov     [rsp+58h+arg_8], rcx
0x180027321  mov     r8d, ecx
0x180027324  xor     eax, eax
0x180027326  mov     word ptr [rsp+58h+arg_0+4], 3
0x18002732d  mov     r9d, r8d
0x180027330  mov     [rsp+58h+var_28], eax
0x180027334  mov     dword ptr [rsp+58h+arg_0], eax
0x180027338  lea     rcx, qword_18003E410
0x18002733f  shr     r9d, 0Bh
0x180027343  lea     rax, [rsp+58h+arg_0]
0x180027348  shr     r8d, 0Ah
0x18002734c  and     r9d, edi
0x18002734f  and     r8d, edi
0x180027352  mov     [rsp+58h+var_30], edi
0x180027356  mov     edx, 37E287Eh
0x18002735b  mov     [rsp+58h+var_38], rax
0x180027360  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180027365  mov     cl, dil
0x180027368  jmp     short loc_18002736C
0x18002736a  xor     cl, cl
0x18002736c  test    sil, sil
0x18002736f  jz      short loc_180027379
0x180027371  test    cl, cl
0x180027373  jnz     short loc_180027379
0x180027375  btr     dword ptr [rbx], 0Ah
0x180027379  mov     eax, [rbx]
0x18002737b  test    bpl, al
0x18002737e  jz      short loc_180027384
0x180027380  test    cl, cl
0x180027382  jnz     short loc_180027386
0x180027384  xor     edi, edi
0x180027386  and     eax, 0FFFFFFFEh
0x180027389  or      eax, edi
0x18002738b  mov     [rbx], eax
0x18002738d  mov     rax, rbx
0x180027390  mov     rbx, [rsp+58h+arg_10]
0x180027395  add     rsp, 40h
0x180027399  pop     rdi
0x18002739a  pop     rsi
0x18002739b  pop     rbp
0x18002739c  retn
```
