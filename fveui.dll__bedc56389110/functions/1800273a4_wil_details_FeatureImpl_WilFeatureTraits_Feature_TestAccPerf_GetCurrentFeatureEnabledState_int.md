# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800273a4`
- end: `0x1800274f1`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `333`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180026bc8`

## callees

- `0x1800188c4`
- `0x18002331c`
- `0x1800266c8`
- `0x1800273a4`
- `0x1800291a8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, 3u, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_18003E400, 45036797, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x1800273a4  mov     [rsp+arg_10], rbx
0x1800273a9  mov     [rsp+arg_0], rcx
0x1800273ae  push    rbp
0x1800273af  push    rsi
0x1800273b0  push    rdi
0x1800273b1  sub     rsp, 40h
0x1800273b5  mov     rbx, rdx
0x1800273b8  mov     ecx, 3667CADh; this
0x1800273bd  mov     edx, 3; unsigned int
0x1800273c2  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800273c7  mov     edx, eax
0x1800273c9  mov     qword ptr [rbx], 0
0x1800273d0  and     edx, 0FFFFFF3Fh
0x1800273d6  mov     ecx, eax
0x1800273d8  and     eax, 80h
0x1800273dd  mov     r8d, edx
0x1800273e0  and     r8d, 3
0x1800273e4  mov     ebp, 40h ; '@'
0x1800273e9  shl     r8d, 2
0x1800273ed  and     ecx, ebp
0x1800273ef  or      r8d, ecx
0x1800273f2  shl     r8d, 2
0x1800273f6  or      r8d, eax
0x1800273f9  shl     r8d, 3
0x1800273fd  test    edx, edx
0x1800273ff  jnz     short loc_180027407
0x180027401  mov     ecx, ebp
0x180027403  mov     edx, ebp
0x180027405  jmp     short loc_180027411
0x180027407  xor     ecx, ecx
0x180027409  cmp     edx, 2
0x18002740c  cmovz   ecx, ebp
0x18002740f  mov     edx, ecx
0x180027411  mov     eax, r8d
0x180027414  mov     edi, 1
0x180027419  or      eax, edx
0x18002741b  or      r8d, ecx
0x18002741e  mov     [rbx], eax
0x180027420  bt      r8d, 0Ah
0x180027425  jnb     short loc_180027435
0x180027427  cmp     r8d, 800h
0x18002742e  jb      short loc_180027435
0x180027430  mov     sil, dil
0x180027433  jmp     short loc_180027443
0x180027435  xor     sil, sil
0x180027438  xor     cl, cl
0x18002743a  test    bpl, r8b
0x18002743d  jz      loc_1800274CD
0x180027443  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18002744a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18002744f  test    al, al
0x180027451  jz      short loc_1800274BE
0x180027453  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18002745a  mov     r8d, [rax]
0x18002745d  test    r8b, 4
0x180027461  jnz     short loc_180027478
0x180027463  lea     rdx, [rsp+58h+arg_8]
0x180027468  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18002746d  mov     rcx, [rax]
0x180027470  mov     [rsp+58h+arg_8], rcx
0x180027475  mov     r8d, ecx
0x180027478  xor     eax, eax
0x18002747a  mov     word ptr [rsp+58h+arg_0+4], 3
0x180027481  mov     r9d, r8d
0x180027484  mov     [rsp+58h+var_28], eax
0x180027488  mov     dword ptr [rsp+58h+arg_0], eax
0x18002748c  lea     rcx, qword_18003E400
0x180027493  shr     r9d, 0Bh
0x180027497  lea     rax, [rsp+58h+arg_0]
0x18002749c  shr     r8d, 0Ah
0x1800274a0  and     r9d, edi
0x1800274a3  and     r8d, edi
0x1800274a6  mov     [rsp+58h+var_30], edi
0x1800274aa  mov     edx, 2AF34FDh
0x1800274af  mov     [rsp+58h+var_38], rax
0x1800274b4  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800274b9  mov     cl, dil
0x1800274bc  jmp     short loc_1800274C0
0x1800274be  xor     cl, cl
0x1800274c0  test    sil, sil
0x1800274c3  jz      short loc_1800274CD
0x1800274c5  test    cl, cl
0x1800274c7  jnz     short loc_1800274CD
0x1800274c9  btr     dword ptr [rbx], 0Ah
0x1800274cd  mov     eax, [rbx]
0x1800274cf  test    bpl, al
0x1800274d2  jz      short loc_1800274D8
0x1800274d4  test    cl, cl
0x1800274d6  jnz     short loc_1800274DA
0x1800274d8  xor     edi, edi
0x1800274da  and     eax, 0FFFFFFFEh
0x1800274dd  or      eax, edi
0x1800274df  mov     [rbx], eax
0x1800274e1  mov     rax, rbx
0x1800274e4  mov     rbx, [rsp+58h+arg_10]
0x1800274e9  add     rsp, 40h
0x1800274ed  pop     rdi
0x1800274ee  pop     rsi
0x1800274ef  pop     rbp
0x1800274f0  retn
```
