# FwTelemetryEventWriteFwLockTimeout(void *,char const *,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x18000a6e0`
- end: `0x18000ab6e`
- name: `?FwTelemetryEventWriteFwLockTimeout@@YAXPEAXPEBD_K22@Z`
- size: `1166`
- prototype: `void __fastcall(void *, const char *, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180008bc0`
- `0x180009460`
- `0x1800097b0`

## callees

- `0x18000142c`
- `0x18000250c`
- `0x18000a6e0`
- `0x18000af3c`
- `0x18002bdb0`
- `0x18002bff0`
- `0x18002c430`
- `0x18006f520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18000a87d`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18000a87d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a88e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a8a4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a8ba`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a88e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a8a4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a8ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a738`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a738`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000a8d3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000a8d3`
- `fwbase!FwFreeRpcCallersProcessInfo` at `0x18000aa50`
- `fwbase!FwFreeRpcCallersProcessInfo` at `0x18000aa50`
- `fwbase!FwGetRpcCallersProcessInfo` at `0x18000a7ab`
- `fwbase!FwGetRpcCallersProcessInfo` at `0x18000a7ab`
- `fwbase!FwStringCopy` at `0x18000a819`
- `fwbase!FwStringCopy` at `0x18000a819`
- `fwbase!FwFree` at `0x18000a8c9`
- `fwbase!FwFree` at `0x18000a8e2`
- `fwbase!FwFree` at `0x18000a8c9`
- `fwbase!FwFree` at `0x18000a8e2`

## string_xrefs

- `0x18000a89d`: `rundll32`

## pseudocode

```c
void __fastcall FwTelemetryEventWriteFwLockTimeout(
        void *a1,
        const char *a2,
        __int64 a3,
        unsigned __int64 a4,
        unsigned __int64 a5)
{
  int *v5; // rdi
  unsigned __int64 v9; // rsi
  __int64 v10; // rcx
  unsigned int Variant; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // ecx
  unsigned int v15; // ebx
  int RpcCallersProcessInfo; // eax
  unsigned __int64 FileNameW; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  __int64 v21; // rdx
  const wchar_t *v22; // rax
  __int64 v23; // [rsp+50h] [rbp-31h] BYREF
  __int64 v24; // [rsp+58h] [rbp-29h] BYREF
  __int64 v25; // [rsp+60h] [rbp-21h] BYREF
  __int64 v26; // [rsp+68h] [rbp-19h] BYREF
  __int64 v27; // [rsp+70h] [rbp-11h] BYREF
  _BYTE v28[4]; // [rsp+78h] [rbp-9h] BYREF
  unsigned int v29; // [rsp+7Ch] [rbp-5h]
  wchar_t *String; // [rsp+80h] [rbp-1h] BYREF
  __int128 v31; // [rsp+88h] [rbp+7h] BYREF
  LPCWSTR pszPath[2]; // [rsp+98h] [rbp+17h]

  v5 = &dword_180126458;
  if ( !dword_180126458 )
    v5 = 0;
  v31 = 0;
  *(_OWORD *)pszPath = 0;
  v9 = GetTickCount64() - a3;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl'::`2'::impl);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCachedVariantState(v10, v28);
  Variant = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl'::`2'::impl);
  if ( (unsigned __int8)Variant <= 0xFu && (v14 = 33824, _bittest(&v14, Variant)) )
    v15 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl'::`2'::impl);
  else
    v15 = 1;
  if ( a1 )
  {
    v31 = 0;
    LODWORD(v31) = 14;
    *(_OWORD *)pszPath = 0;
    RpcCallersProcessInfo = FwGetRpcCallersProcessInfo(a1, &v31);
    if ( RpcCallersProcessInfo < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          10,
          WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
          (unsigned int)RpcCallersProcessInfo);
      return;
    }
    if ( v9 <= 0xBB8 || !v5 )
      goto LABEL_31;
    String = 0;
    v20 = FwStringCopy(pszPath[1], &String);
    if ( v20 >= 0 )
    {
      v21 = -1;
      do
        ++v21;
      while ( String[v21] );
      _wcslwr_s(String, v21 + 1);
      if ( wcsstr(String, L"svchost") || wcsstr(String, L"rundll32") || wcsstr(String, L"cscript") )
      {
        FwFree(String);
        FileNameW = (unsigned __int64)pszPath[1];
        goto LABEL_25;
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        14,
        WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
        (unsigned int)v20);
    }
    FwFree(String);
    FileNameW = (unsigned __int64)PathFindFileNameW(pszPath[0]);
LABEL_25:
    if ( (unsigned int)*v5 > 5 )
    {
      v18 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v5 + 2) & 0x400000000000LL) != 0 && (v18 & 0x400000000000LL) == v18 )
      {
        v27 = a4;
        v22 = L"NULL";
        v23 = v9;
        if ( FileNameW )
          v22 = (const wchar_t *)FileNameW;
        v24 = (__int64)a2;
        v25 = (__int64)v22;
        v26 = *((_QWORD *)&v31 + 1);
        LODWORD(String) = DWORD1(v31);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (int)v5,
          (int)&byte_18010FD93,
          v18,
          v19,
          (__int64)&String,
          (const unsigned __int16 **)&v26,
          (const unsigned __int16 **)&v25,
          (const char **)&v24,
          (__int64)&v23,
          (__int64)&v27);
      }
    }
LABEL_31:
    if ( a4 >= v29 )
    {
      FileNameW = a5 % v15;
      if ( !FileNameW && (unsigned int)dword_1801263B0 > 4 )
      {
        FileNameW = 0x4000000000000LL;
        if ( (qword_1801263C0 & 0x4000000000000LL) != 0 && (qword_1801263C8 & 0x4000000000000LL) == qword_1801263C8 )
        {
          v23 = (__int64)pszPath[1];
          v27 = *((_QWORD *)&v31 + 1);
          LODWORD(String) = DWORD1(v31);
          v26 = a4;
          v25 = v9;
          v24 = (__int64)a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (int)&dword_1801263B0,
            (int)&dword_18010FF9C,
            v18,
            v19,
            (__int64)&String,
            (const unsigned __int16 **)&v27,
            (const unsigned __int16 **)&v23,
            (const char **)&v24,
            (__int64)&v25,
            (__int64)&v26);
        }
      }
    }
    FwFreeRpcCallersProcessInfo(&v31, FileNameW, v18);
    return;
  }
  if ( v9 > 0xBB8
    && v5
    && (unsigned int)*v5 > 5
    && (*((_QWORD *)v5 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v5 + 3) & 0x400000000000LL) == *((_QWORD *)v5 + 3) )
  {
    v26 = a4;
    v25 = v9;
    v24 = (__int64)a2;
    v23 = (__int64)L"MPSSVC";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (int)v5,
      (int)&byte_18010FECD,
      v12,
      v13,
      (const unsigned __int16 **)&v23,
      (const char **)&v24,
      (__int64)&v25,
      (__int64)&v26);
  }
  if ( a4 >= v29 && !(a5 % v15) && (unsigned int)dword_1801263B0 > 4 )
  {
    v26 = a4;
    v25 = v9;
    v24 = (__int64)a2;
    v23 = (__int64)L"MPSSVC";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (int)&dword_1801263B0,
      (int)&byte_18010FE3F,
      v12,
      v13,
      (const unsigned __int16 **)&v23,
      (const char **)&v24,
      (__int64)&v25,
      (__int64)&v26);
  }
}

```

## disassembly

```asm
0x18000a6e0  mov     [rsp-8+arg_8], rbx
0x18000a6e5  mov     [rsp-8+arg_10], rsi
0x18000a6ea  push    rbp
0x18000a6eb  push    rdi
0x18000a6ec  push    r12
0x18000a6ee  push    r14
0x18000a6f0  push    r15
0x18000a6f2  lea     rbp, [rsp-2Fh]
0x18000a6f7  sub     rsp, 0B0h
0x18000a6fe  mov     rax, cs:__security_cookie
0x18000a705  xor     rax, rsp
0x18000a708  mov     [rbp+4Fh+var_28], rax
0x18000a70c  xor     eax, eax
0x18000a70e  lea     rdi, dword_180126458
0x18000a715  xorps   xmm0, xmm0
0x18000a718  mov     r15, rcx
0x18000a71b  mov     ecx, cs:dword_180126458
0x18000a721  mov     r14, r9
0x18000a724  test    ecx, ecx
0x18000a726  mov     rbx, r8
0x18000a729  mov     r12, rdx
0x18000a72c  cmovz   rdi, rax
0x18000a730  movups  [rbp+4Fh+var_48], xmm0
0x18000a734  movups  xmmword ptr [rbp+4Fh+pszPath], xmm0
0x18000a738  call    cs:__imp_GetTickCount64
0x18000a73e  mov     rsi, rax
0x18000a741  sub     rsi, rbx
0x18000a744  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing> `wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl(void)'::`2'::impl
0x18000a74b  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000a750  lea     rdx, [rbp+4Fh+var_58]
0x18000a754  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCachedVariantState(void)
0x18000a759  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing> `wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl(void)'::`2'::impl
0x18000a760  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@QEAA?AW4Variant_WFDiagnosticTracing@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_GetVariant(wil::VariantReportingKind,bool)
0x18000a765  cmp     al, 0Fh
0x18000a767  ja      short loc_18000A784
0x18000a769  mov     ecx, 8420h
0x18000a76e  bt      ecx, eax
0x18000a771  jnb     short loc_18000A784
0x18000a773  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing> `wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl(void)'::`2'::impl
0x18000a77a  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@QEAA?AW4Variant_WFDiagnosticTracing@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_GetVariant(wil::VariantReportingKind,bool)
0x18000a77f  movzx   ebx, al
0x18000a782  jmp     short loc_18000A789
0x18000a784  mov     ebx, 1
0x18000a789  test    r15, r15
0x18000a78c  jz      loc_18000AA5B
0x18000a792  xorps   xmm0, xmm0
0x18000a795  lea     rdx, [rbp+4Fh+var_48]
0x18000a799  movups  [rbp+4Fh+var_48], xmm0
0x18000a79d  mov     rcx, r15
0x18000a7a0  mov     dword ptr [rbp+4Fh+var_48], 0Eh
0x18000a7a7  movups  xmmword ptr [rbp+4Fh+pszPath], xmm0
0x18000a7ab  call    cs:__imp_FwGetRpcCallersProcessInfo
0x18000a7b1  test    eax, eax
0x18000a7b3  jns     short loc_18000A7F3
0x18000a7b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7bc  lea     rdx, WPP_GLOBAL_Control
0x18000a7c3  cmp     rcx, rdx
0x18000a7c6  jz      loc_18000AB46
0x18000a7cc  test    byte ptr [rcx+1Ch], 1
0x18000a7d0  jz      loc_18000AB46
0x18000a7d6  mov     rcx, [rcx+10h]
0x18000a7da  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18000a7e1  mov     edx, 0Ah
0x18000a7e6  mov     r9d, eax
0x18000a7e9  call    WPP_SF_d
0x18000a7ee  jmp     loc_18000AB46
0x18000a7f3  cmp     rsi, 0BB8h
0x18000a7fa  jbe     loc_18000A98A
0x18000a800  test    rdi, rdi
0x18000a803  jz      loc_18000A98A
0x18000a809  mov     rcx, [rbp+4Fh+pszPath+8]
0x18000a80d  lea     rdx, [rbp+4Fh+String]
0x18000a811  mov     [rbp+4Fh+String], 0
0x18000a819  call    cs:__imp_FwStringCopy
0x18000a81f  test    eax, eax
0x18000a821  jns     short loc_18000A85E
0x18000a823  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a82a  lea     rdx, WPP_GLOBAL_Control
0x18000a831  cmp     rcx, rdx
0x18000a834  jz      loc_18000A8C5
0x18000a83a  test    byte ptr [rcx+1Ch], 1
0x18000a83e  jz      loc_18000A8C5
0x18000a844  mov     rcx, [rcx+10h]
0x18000a848  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18000a84f  mov     edx, 0Eh
0x18000a854  mov     r9d, eax
0x18000a857  call    WPP_SF_d
0x18000a85c  jmp     short loc_18000A8C5
0x18000a85e  mov     rcx, [rbp+4Fh+String]; String
0x18000a862  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000a869  nop     dword ptr [rax+00000000h]
0x18000a870  inc     rdx
0x18000a873  cmp     word ptr [rcx+rdx*2], 0
0x18000a878  jnz     short loc_18000A870
0x18000a87a  inc     rdx; SizeInWords
0x18000a87d  call    cs:__imp__wcslwr_s
0x18000a883  mov     rcx, [rbp+4Fh+String]; Str
0x18000a887  lea     rdx, aSvchost; "svchost"
0x18000a88e  call    cs:__imp_wcsstr
0x18000a894  test    rax, rax
0x18000a897  jnz     short loc_18000A8DE
0x18000a899  mov     rcx, [rbp+4Fh+String]; Str
0x18000a89d  lea     rdx, aRundll32; "rundll32"
0x18000a8a4  call    cs:__imp_wcsstr
0x18000a8aa  test    rax, rax
0x18000a8ad  jnz     short loc_18000A8DE
0x18000a8af  mov     rcx, [rbp+4Fh+String]; Str
0x18000a8b3  lea     rdx, aCscript; "cscript"
0x18000a8ba  call    cs:__imp_wcsstr
0x18000a8c0  test    rax, rax
0x18000a8c3  jnz     short loc_18000A8DE
0x18000a8c5  mov     rcx, [rbp+4Fh+String]
0x18000a8c9  call    cs:__imp_FwFree
0x18000a8cf  mov     rcx, [rbp+4Fh+pszPath]; pszPath
0x18000a8d3  call    cs:__imp_PathFindFileNameW
0x18000a8d9  mov     rdx, rax
0x18000a8dc  jmp     short loc_18000A8EC
0x18000a8de  mov     rcx, [rbp+4Fh+String]
0x18000a8e2  call    cs:__imp_FwFree
0x18000a8e8  mov     rdx, [rbp+4Fh+pszPath+8]
0x18000a8ec  mov     eax, [rdi]
0x18000a8ee  cmp     eax, 5
0x18000a8f1  jbe     loc_18000A98A
0x18000a8f7  mov     r8, [rdi+18h]
0x18000a8fb  mov     rcx, 400000000000h
0x18000a905  mov     rax, [rdi+10h]
0x18000a909  test    rcx, rax
0x18000a90c  jz      short loc_18000A98A
0x18000a90e  mov     rax, r8
0x18000a911  and     rax, rcx
0x18000a914  cmp     rax, r8
0x18000a917  jnz     short loc_18000A98A
0x18000a919  test    rdx, rdx
0x18000a91c  mov     [rbp+4Fh+var_60], r14
0x18000a920  lea     rax, aNull_2; "NULL"
0x18000a927  mov     [rbp+4Fh+var_80], rsi
0x18000a92b  cmovnz  rax, rdx
0x18000a92f  mov     [rbp+4Fh+var_78], r12
0x18000a933  mov     [rbp+4Fh+var_70], rax
0x18000a937  lea     rdx, byte_18010FD93; int
0x18000a93e  mov     rax, qword ptr [rbp+4Fh+var_48+8]
0x18000a942  mov     rcx, rdi; int
0x18000a945  mov     [rbp+4Fh+var_68], rax
0x18000a949  mov     eax, dword ptr [rbp+4Fh+var_48+4]
0x18000a94c  mov     dword ptr [rbp+4Fh+String], eax
0x18000a94f  lea     rax, [rbp+4Fh+var_60]
0x18000a953  mov     [rsp+0D0h+var_88], rax; __int64
0x18000a958  lea     rax, [rbp+4Fh+var_80]
0x18000a95c  mov     [rsp+0D0h+var_90], rax; __int64
0x18000a961  lea     rax, [rbp+4Fh+var_78]
0x18000a965  mov     [rsp+0D0h+var_98], rax; __int64
0x18000a96a  lea     rax, [rbp+4Fh+var_70]
0x18000a96e  mov     [rsp+0D0h+var_A0], rax; __int64
0x18000a973  lea     rax, [rbp+4Fh+var_68]
0x18000a977  mov     [rsp+0D0h+var_A8], rax; __int64
0x18000a97c  lea     rax, [rbp+4Fh+String]
0x18000a980  mov     [rsp+0D0h+var_B0], rax; __int64
0x18000a985  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000a98a  mov     eax, [rbp+4Fh+var_54]
0x18000a98d  cmp     r14, rax
0x18000a990  jb      loc_18000AA4C
0x18000a996  mov     rax, [rbp+4Fh+arg_20]
0x18000a99a  xor     edx, edx
0x18000a99c  mov     ecx, ebx
0x18000a99e  div     rcx
0x18000a9a1  test    rdx, rdx
0x18000a9a4  jnz     loc_18000AA4C
0x18000a9aa  mov     eax, cs:dword_1801263B0
0x18000a9b0  cmp     eax, 4
0x18000a9b3  jbe     loc_18000AA4C
0x18000a9b9  mov     rcx, cs:qword_1801263C8
0x18000a9c0  mov     rdx, 4000000000000h
0x18000a9ca  mov     rax, cs:qword_1801263C0
0x18000a9d1  test    rdx, rax
0x18000a9d4  jz      short loc_18000AA4C
0x18000a9d6  mov     rax, rcx
0x18000a9d9  and     rax, rdx
0x18000a9dc  cmp     rax, rcx
0x18000a9df  jnz     short loc_18000AA4C
0x18000a9e1  mov     rax, [rbp+4Fh+pszPath+8]
0x18000a9e5  lea     rdx, dword_18010FF9C; int
0x18000a9ec  mov     [rbp+4Fh+var_80], rax
0x18000a9f0  lea     rcx, dword_1801263B0; int
0x18000a9f7  mov     rax, qword ptr [rbp+4Fh+var_48+8]
0x18000a9fb  mov     [rbp+4Fh+var_60], rax
0x18000a9ff  mov     eax, dword ptr [rbp+4Fh+var_48+4]
0x18000aa02  mov     dword ptr [rbp+4Fh+String], eax
0x18000aa05  lea     rax, [rbp+4Fh+var_68]
0x18000aa09  mov     [rsp+0D0h+var_88], rax; __int64
0x18000aa0e  lea     rax, [rbp+4Fh+var_70]
0x18000aa12  mov     [rsp+0D0h+var_90], rax; __int64
0x18000aa17  lea     rax, [rbp+4Fh+var_78]
0x18000aa1b  mov     [rsp+0D0h+var_98], rax; __int64
0x18000aa20  lea     rax, [rbp+4Fh+var_80]
0x18000aa24  mov     [rsp+0D0h+var_A0], rax; __int64
0x18000aa29  lea     rax, [rbp+4Fh+var_60]
0x18000aa2d  mov     [rsp+0D0h+var_A8], rax; __int64
0x18000aa32  lea     rax, [rbp+4Fh+String]
0x18000aa36  mov     [rsp+0D0h+var_B0], rax; __int64
0x18000aa3b  mov     [rbp+4Fh+var_68], r14
0x18000aa3f  mov     [rbp+4Fh+var_70], rsi
0x18000aa43  mov     [rbp+4Fh+var_78], r12
0x18000aa47  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000aa4c  lea     rcx, [rbp+4Fh+var_48]
0x18000aa50  call    cs:__imp_FwFreeRpcCallersProcessInfo
0x18000aa56  jmp     loc_18000AB46
0x18000aa5b  lea     r15, ServiceName; "MPSSVC"
0x18000aa62  cmp     rsi, 0BB8h
0x18000aa69  jbe     short loc_18000AADC
0x18000aa6b  test    rdi, rdi
0x18000aa6e  jz      short loc_18000AADC
0x18000aa70  mov     eax, [rdi]
0x18000aa72  cmp     eax, 5
0x18000aa75  jbe     short loc_18000AADC
0x18000aa77  mov     rdx, [rdi+18h]
0x18000aa7b  mov     rcx, 400000000000h
0x18000aa85  mov     rax, [rdi+10h]
0x18000aa89  test    rcx, rax
0x18000aa8c  jz      short loc_18000AADC
0x18000aa8e  mov     rax, rdx
0x18000aa91  and     rax, rcx
0x18000aa94  cmp     rax, rdx
0x18000aa97  jnz     short loc_18000AADC
0x18000aa99  lea     rax, [rbp+4Fh+var_68]
0x18000aa9d  mov     [rbp+4Fh+var_68], r14
0x18000aaa1  mov     [rsp+0D0h+var_98], rax; __int64
0x18000aaa6  lea     rdx, byte_18010FECD; int
0x18000aaad  lea     rax, [rbp+4Fh+var_70]
0x18000aab1  mov     [rbp+4Fh+var_70], rsi
0x18000aab5  mov     [rsp+0D0h+var_A0], rax; __int64
0x18000aaba  mov     rcx, rdi; int
0x18000aabd  lea     rax, [rbp+4Fh+var_78]
0x18000aac1  mov     [rbp+4Fh+var_78], r12
0x18000aac5  mov     [rsp+0D0h+var_A8], rax; __int64
0x18000aaca  lea     rax, [rbp+4Fh+var_80]
0x18000aace  mov     [rsp+0D0h+var_B0], rax; __int64
0x18000aad3  mov     [rbp+4Fh+var_80], r15
0x18000aad7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000aadc  mov     eax, [rbp+4Fh+var_54]
0x18000aadf  cmp     r14, rax
0x18000aae2  jb      short loc_18000AB46
0x18000aae4  mov     rax, [rbp+4Fh+arg_20]
0x18000aae8  xor     edx, edx
0x18000aaea  mov     ecx, ebx
0x18000aaec  div     rcx
0x18000aaef  test    rdx, rdx
0x18000aaf2  jnz     short loc_18000AB46
0x18000aaf4  mov     eax, cs:dword_1801263B0
0x18000aafa  cmp     eax, 4
0x18000aafd  jbe     short loc_18000AB46
0x18000aaff  lea     rax, [rbp+4Fh+var_68]
0x18000ab03  mov     [rbp+4Fh+var_68], r14
0x18000ab07  mov     [rsp+0D0h+var_98], rax; __int64
0x18000ab0c  lea     rdx, byte_18010FE3F; int
0x18000ab13  lea     rax, [rbp+4Fh+var_70]
0x18000ab17  mov     [rbp+4Fh+var_70], rsi
0x18000ab1b  mov     [rsp+0D0h+var_A0], rax; __int64
0x18000ab20  lea     rcx, dword_1801263B0; int
0x18000ab27  lea     rax, [rbp+4Fh+var_78]
0x18000ab2b  mov     [rbp+4Fh+var_78], r12
0x18000ab2f  mov     [rsp+0D0h+var_A8], rax; __int64
0x18000ab34  lea     rax, [rbp+4Fh+var_80]
0x18000ab38  mov     [rsp+0D0h+var_B0], rax; __int64
0x18000ab3d  mov     [rbp+4Fh+var_80], r15
0x18000ab41  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000ab46  mov     rcx, [rbp+4Fh+var_28]
0x18000ab4a  xor     rcx, rsp; StackCookie
0x18000ab4d  call    __security_check_cookie
0x18000ab52  lea     r11, [rsp+0D0h+var_20]
0x18000ab5a  mov     rbx, [r11+38h]
0x18000ab5e  mov     rsi, [r11+40h]
0x18000ab62  mov     rsp, r11
0x18000ab65  pop     r15
0x18000ab67  pop     r14
0x18000ab69  pop     r12
0x18000ab6b  pop     rdi
0x18000ab6c  pop     rbp
0x18000ab6d  retn
```
