# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180012f40`
- end: `0x1800130a9`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800128d0`

## callees

- `0x18000ce88`
- `0x18000fa2c`
- `0x180012f40`
- `0x18001394c`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
    v4 = v2(57048237, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_1800220F0, 45036797, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180012f40  mov     [rsp+arg_10], rbx
0x180012f45  mov     [rsp+arg_0], rcx
0x180012f4a  push    rbp
0x180012f4b  push    rsi
0x180012f4c  push    rdi
0x180012f4d  sub     rsp, 40h
0x180012f51  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180012f58  mov     rbx, rdx
0x180012f5b  test    rax, rax
0x180012f5e  jz      short loc_180012F73
0x180012f60  mov     edx, 3
0x180012f65  mov     ecx, 3667CADh
0x180012f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f6f  mov     edx, eax
0x180012f71  jmp     short loc_180012F81
0x180012f73  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180012f7a  test    rax, rax
0x180012f7d  jnz     short loc_180012F60
0x180012f7f  xor     edx, edx
0x180012f81  mov     r8d, edx
0x180012f84  mov     qword ptr [rbx], 0
0x180012f8b  and     r8d, 0FFFFFF3Fh
0x180012f92  mov     eax, edx
0x180012f94  and     edx, 80h
0x180012f9a  mov     ecx, r8d
0x180012f9d  and     ecx, 3
0x180012fa0  mov     ebp, 40h ; '@'
0x180012fa5  shl     ecx, 2
0x180012fa8  and     eax, ebp
0x180012faa  or      ecx, eax
0x180012fac  shl     ecx, 2
0x180012faf  or      ecx, edx
0x180012fb1  shl     ecx, 3
0x180012fb4  test    r8d, r8d
0x180012fb7  jnz     short loc_180012FC0
0x180012fb9  mov     edx, ebp
0x180012fbb  mov     r8d, ebp
0x180012fbe  jmp     short loc_180012FCC
0x180012fc0  xor     edx, edx
0x180012fc2  cmp     r8d, 2
0x180012fc6  cmovz   edx, ebp
0x180012fc9  mov     r8d, edx
0x180012fcc  mov     eax, ecx
0x180012fce  mov     edi, 1
0x180012fd3  or      eax, r8d
0x180012fd6  or      ecx, edx
0x180012fd8  mov     [rbx], eax
0x180012fda  bt      ecx, 0Ah
0x180012fde  jnb     short loc_180012FED
0x180012fe0  cmp     ecx, 800h
0x180012fe6  jb      short loc_180012FED
0x180012fe8  mov     sil, dil
0x180012feb  jmp     short loc_180012FFB
0x180012fed  xor     sil, sil
0x180012ff0  xor     dl, dl
0x180012ff2  test    bpl, cl
0x180012ff5  jz      loc_180013085
0x180012ffb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180013002  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180013007  test    al, al
0x180013009  jz      short loc_180013076
0x18001300b  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180013012  mov     r8d, [rax]
0x180013015  test    r8b, 4
0x180013019  jnz     short loc_180013030
0x18001301b  lea     rdx, [rsp+58h+arg_8]
0x180013020  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x180013025  mov     rcx, [rax]
0x180013028  mov     [rsp+58h+arg_8], rcx
0x18001302d  mov     r8d, ecx
0x180013030  xor     eax, eax
0x180013032  mov     word ptr [rsp+58h+arg_0+4], 3
0x180013039  mov     r9d, r8d
0x18001303c  mov     [rsp+58h+var_28], eax
0x180013040  mov     dword ptr [rsp+58h+arg_0], eax
0x180013044  lea     rcx, qword_1800220F0
0x18001304b  shr     r9d, 0Bh
0x18001304f  lea     rax, [rsp+58h+arg_0]
0x180013054  shr     r8d, 0Ah
0x180013058  and     r9d, edi
0x18001305b  and     r8d, edi
0x18001305e  mov     [rsp+58h+var_30], edi
0x180013062  mov     edx, 2AF34FDh
0x180013067  mov     [rsp+58h+var_38], rax
0x18001306c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180013071  mov     dl, dil
0x180013074  jmp     short loc_180013078
0x180013076  xor     dl, dl
0x180013078  test    sil, sil
0x18001307b  jz      short loc_180013085
0x18001307d  test    dl, dl
0x18001307f  jnz     short loc_180013085
0x180013081  btr     dword ptr [rbx], 0Ah
0x180013085  mov     eax, [rbx]
0x180013087  test    bpl, al
0x18001308a  jz      short loc_180013090
0x18001308c  test    dl, dl
0x18001308e  jnz     short loc_180013092
0x180013090  xor     edi, edi
0x180013092  and     eax, 0FFFFFFFEh
0x180013095  or      eax, edi
0x180013097  mov     [rbx], eax
0x180013099  mov     rax, rbx
0x18001309c  mov     rbx, [rsp+58h+arg_10]
0x1800130a1  add     rsp, 40h
0x1800130a5  pop     rdi
0x1800130a6  pop     rsi
0x1800130a7  pop     rbp
0x1800130a8  retn
```
