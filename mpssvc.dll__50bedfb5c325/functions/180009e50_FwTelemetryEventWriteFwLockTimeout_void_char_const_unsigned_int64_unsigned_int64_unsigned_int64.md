# FwTelemetryEventWriteFwLockTimeout(void *,char const *,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180009e50`
- end: `0x18000a31f`
- name: `?FwTelemetryEventWriteFwLockTimeout@@YAXPEAXPEBD_K22@Z`
- size: `1231`
- prototype: `void __fastcall(void *, const char *, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180008170`
- `0x180008a80`
- `0x180008e00`

## callees

- `0x18000142c`
- `0x18000264c`
- `0x180009e50`
- `0x18000a710`
- `0x18002f3b0`
- `0x18002f5f0`
- `0x18002fa40`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180009ffd`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180009ffd`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a014`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a030`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a04c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a014`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a030`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000a04c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009ea8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009ea8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000a071`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000a071`
- `fwbase!FwFreeRpcCallersProcessInfo` at `0x18000a1fa`
- `fwbase!FwFreeRpcCallersProcessInfo` at `0x18000a1fa`
- `fwbase!FwGetRpcCallersProcessInfo` at `0x180009f21`
- `fwbase!FwGetRpcCallersProcessInfo` at `0x180009f21`
- `fwbase!FwStringCopy` at `0x180009f95`
- `fwbase!FwStringCopy` at `0x180009f95`
- `fwbase!FwFree` at `0x18000a061`
- `fwbase!FwFree` at `0x18000a086`
- `fwbase!FwFree` at `0x18000a061`
- `fwbase!FwFree` at `0x18000a086`

## string_xrefs

- `0x18000a029`: `rundll32`

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
  int v12; // ecx
  unsigned int v13; // ebx
  int RpcCallersProcessInfo; // eax
  unsigned __int64 FileNameW; // rdx
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rdx
  const wchar_t *v19; // rax
  __int64 v20; // [rsp+50h] [rbp-31h] BYREF
  __int64 v21; // [rsp+58h] [rbp-29h] BYREF
  __int64 v22; // [rsp+60h] [rbp-21h] BYREF
  __int64 v23; // [rsp+68h] [rbp-19h] BYREF
  __int64 v24; // [rsp+70h] [rbp-11h] BYREF
  _BYTE v25[4]; // [rsp+78h] [rbp-9h] BYREF
  unsigned int v26; // [rsp+7Ch] [rbp-5h]
  wchar_t *String; // [rsp+80h] [rbp-1h] BYREF
  __int128 v28; // [rsp+88h] [rbp+7h] BYREF
  LPCWSTR pszPath[2]; // [rsp+98h] [rbp+17h]

  v5 = &dword_18012C458;
  if ( !dword_18012C458 )
    v5 = 0;
  v28 = 0;
  *(_OWORD *)pszPath = 0;
  v9 = GetTickCount64() - a3;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl'::`2'::impl);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCachedVariantState(v10, v25);
  Variant = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl'::`2'::impl);
  if ( (unsigned __int8)Variant <= 0xFu && (v12 = 33824, _bittest(&v12, Variant)) )
    v13 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl'::`2'::impl);
  else
    v13 = 1;
  if ( a1 )
  {
    v28 = 0;
    LODWORD(v28) = 14;
    *(_OWORD *)pszPath = 0;
    RpcCallersProcessInfo = FwGetRpcCallersProcessInfo(a1, &v28);
    if ( RpcCallersProcessInfo < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          10,
          WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
          (unsigned int)RpcCallersProcessInfo);
      return;
    }
    if ( v9 <= 0xBB8 || !v5 )
      goto LABEL_31;
    String = 0;
    v17 = FwStringCopy(pszPath[1], &String);
    if ( v17 >= 0 )
    {
      v18 = -1;
      do
        ++v18;
      while ( String[v18] );
      _wcslwr_s(String, v18 + 1);
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
        WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
        (unsigned int)v17);
    }
    FwFree(String);
    FileNameW = (unsigned __int64)PathFindFileNameW(pszPath[0]);
LABEL_25:
    if ( (unsigned int)*v5 > 5 )
    {
      v16 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v5 + 2) & 0x400000000000LL) != 0 && (v16 & 0x400000000000LL) == v16 )
      {
        v24 = a4;
        v19 = L"NULL";
        v20 = v9;
        if ( FileNameW )
          v19 = (const wchar_t *)FileNameW;
        v21 = (__int64)a2;
        v22 = (__int64)v19;
        v23 = *((_QWORD *)&v28 + 1);
        LODWORD(String) = DWORD1(v28);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (int)v5,
          (int)&word_180115C2E,
          (__int64)&String,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)&v24);
      }
    }
LABEL_31:
    if ( a4 >= v26 )
    {
      FileNameW = a5 % v13;
      if ( !FileNameW && (unsigned int)dword_18012C3B0 > 4 )
      {
        FileNameW = 0x4000000000000LL;
        if ( (qword_18012C3C0 & 0x4000000000000LL) != 0 && (qword_18012C3C8 & 0x4000000000000LL) == qword_18012C3C8 )
        {
          v20 = (__int64)pszPath[1];
          v24 = *((_QWORD *)&v28 + 1);
          LODWORD(String) = DWORD1(v28);
          v23 = a4;
          v22 = v9;
          v21 = (__int64)a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (int)&dword_18012C3B0,
            (int)&byte_180115E37,
            (__int64)&String,
            (__int64)&v24,
            (__int64)&v20,
            (__int64)&v21,
            (__int64)&v22,
            (__int64)&v23);
        }
      }
    }
    FwFreeRpcCallersProcessInfo(&v28, FileNameW, v16);
    return;
  }
  if ( v9 > 0xBB8
    && v5
    && (unsigned int)*v5 > 5
    && (*((_QWORD *)v5 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v5 + 3) & 0x400000000000LL) == *((_QWORD *)v5 + 3) )
  {
    v23 = a4;
    v22 = v9;
    v21 = (__int64)a2;
    v20 = (__int64)L"MPSSVC";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (int)v5,
      (int)&unk_180115D68,
      (__int64)&v20,
      (__int64)&v21,
      (__int64)&v22,
      (__int64)&v23);
  }
  if ( a4 >= v26 && !(a5 % v13) && (unsigned int)dword_18012C3B0 > 4 )
  {
    v23 = a4;
    v22 = v9;
    v21 = (__int64)a2;
    v20 = (__int64)L"MPSSVC";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (int)&dword_18012C3B0,
      (int)&word_180115CDA,
      (__int64)&v20,
      (__int64)&v21,
      (__int64)&v22,
      (__int64)&v23);
  }
}

```

## disassembly

```asm
0x180009e50  mov     [rsp-8+arg_8], rbx
0x180009e55  mov     [rsp-8+arg_10], rsi
0x180009e5a  push    rbp
0x180009e5b  push    rdi
0x180009e5c  push    r12
0x180009e5e  push    r14
0x180009e60  push    r15
0x180009e62  lea     rbp, [rsp-2Fh]
0x180009e67  sub     rsp, 0B0h
0x180009e6e  mov     rax, cs:__security_cookie
0x180009e75  xor     rax, rsp
0x180009e78  mov     [rbp+4Fh+var_28], rax
0x180009e7c  xor     eax, eax
0x180009e7e  lea     rdi, dword_18012C458
0x180009e85  xorps   xmm0, xmm0
0x180009e88  mov     r15, rcx
0x180009e8b  mov     ecx, cs:dword_18012C458
0x180009e91  mov     r14, r9
0x180009e94  test    ecx, ecx
0x180009e96  mov     rbx, r8
0x180009e99  mov     r12, rdx
0x180009e9c  cmovz   rdi, rax
0x180009ea0  movups  [rbp+4Fh+var_48], xmm0
0x180009ea4  movups  xmmword ptr [rbp+4Fh+pszPath], xmm0
0x180009ea8  call    cs:__imp_GetTickCount64
0x180009eaf  nop     dword ptr [rax+rax+00h]
0x180009eb4  mov     rsi, rax
0x180009eb7  sub     rsi, rbx
0x180009eba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing> `wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl(void)'::`2'::impl
0x180009ec1  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180009ec6  lea     rdx, [rbp+4Fh+var_58]
0x180009eca  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCachedVariantState(void)
0x180009ecf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing> `wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl(void)'::`2'::impl
0x180009ed6  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@QEAA?AW4Variant_WFDiagnosticTracing@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180009edb  cmp     al, 0Fh
0x180009edd  ja      short loc_180009EFA
0x180009edf  mov     ecx, 8420h
0x180009ee4  bt      ecx, eax
0x180009ee7  jnb     short loc_180009EFA
0x180009ee9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing> `wil::Feature<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetImpl(void)'::`2'::impl
0x180009ef0  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@QEAA?AW4Variant_WFDiagnosticTracing@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180009ef5  movzx   ebx, al
0x180009ef8  jmp     short loc_180009EFF
0x180009efa  mov     ebx, 1
0x180009eff  test    r15, r15
0x180009f02  jz      loc_18000A20B
0x180009f08  xorps   xmm0, xmm0
0x180009f0b  lea     rdx, [rbp+4Fh+var_48]
0x180009f0f  movups  [rbp+4Fh+var_48], xmm0
0x180009f13  mov     rcx, r15
0x180009f16  mov     dword ptr [rbp+4Fh+var_48], 0Eh
0x180009f1d  movups  xmmword ptr [rbp+4Fh+pszPath], xmm0
0x180009f21  call    cs:__imp_FwGetRpcCallersProcessInfo
0x180009f28  nop     dword ptr [rax+rax+00h]
0x180009f2d  test    eax, eax
0x180009f2f  jns     short loc_180009F6F
0x180009f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f38  lea     rdx, WPP_GLOBAL_Control
0x180009f3f  cmp     rcx, rdx
0x180009f42  jz      loc_18000A2F6
0x180009f48  test    byte ptr [rcx+1Ch], 1
0x180009f4c  jz      loc_18000A2F6
0x180009f52  mov     rcx, [rcx+10h]
0x180009f56  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180009f5d  mov     edx, 0Ah
0x180009f62  mov     r9d, eax
0x180009f65  call    WPP_SF_d
0x180009f6a  jmp     loc_18000A2F6
0x180009f6f  cmp     rsi, 0BB8h
0x180009f76  jbe     loc_18000A134
0x180009f7c  test    rdi, rdi
0x180009f7f  jz      loc_18000A134
0x180009f85  mov     rcx, [rbp+4Fh+pszPath+8]
0x180009f89  lea     rdx, [rbp+4Fh+String]
0x180009f8d  mov     [rbp+4Fh+String], 0
0x180009f95  call    cs:__imp_FwStringCopy
0x180009f9c  nop     dword ptr [rax+rax+00h]
0x180009fa1  test    eax, eax
0x180009fa3  jns     short loc_180009FE0
0x180009fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fac  lea     rdx, WPP_GLOBAL_Control
0x180009fb3  cmp     rcx, rdx
0x180009fb6  jz      loc_18000A05D
0x180009fbc  test    byte ptr [rcx+1Ch], 1
0x180009fc0  jz      loc_18000A05D
0x180009fc6  mov     rcx, [rcx+10h]
0x180009fca  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180009fd1  mov     edx, 0Eh
0x180009fd6  mov     r9d, eax
0x180009fd9  call    WPP_SF_d
0x180009fde  jmp     short loc_18000A05D
0x180009fe0  mov     rcx, [rbp+4Fh+String]; String
0x180009fe4  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180009feb  nop     dword ptr [rax+rax+00h]
0x180009ff0  inc     rdx
0x180009ff3  cmp     word ptr [rcx+rdx*2], 0
0x180009ff8  jnz     short loc_180009FF0
0x180009ffa  inc     rdx; SizeInWords
0x180009ffd  call    cs:__imp__wcslwr_s
0x18000a004  nop     dword ptr [rax+rax+00h]
0x18000a009  mov     rcx, [rbp+4Fh+String]; Str
0x18000a00d  lea     rdx, aSvchost; "svchost"
0x18000a014  call    cs:__imp_wcsstr
0x18000a01b  nop     dword ptr [rax+rax+00h]
0x18000a020  test    rax, rax
0x18000a023  jnz     short loc_18000A082
0x18000a025  mov     rcx, [rbp+4Fh+String]; Str
0x18000a029  lea     rdx, aRundll32; "rundll32"
0x18000a030  call    cs:__imp_wcsstr
0x18000a037  nop     dword ptr [rax+rax+00h]
0x18000a03c  test    rax, rax
0x18000a03f  jnz     short loc_18000A082
0x18000a041  mov     rcx, [rbp+4Fh+String]; Str
0x18000a045  lea     rdx, aCscript; "cscript"
0x18000a04c  call    cs:__imp_wcsstr
0x18000a053  nop     dword ptr [rax+rax+00h]
0x18000a058  test    rax, rax
0x18000a05b  jnz     short loc_18000A082
0x18000a05d  mov     rcx, [rbp+4Fh+String]
0x18000a061  call    cs:__imp_FwFree
0x18000a068  nop     dword ptr [rax+rax+00h]
0x18000a06d  mov     rcx, [rbp+4Fh+pszPath]; pszPath
0x18000a071  call    cs:__imp_PathFindFileNameW
0x18000a078  nop     dword ptr [rax+rax+00h]
0x18000a07d  mov     rdx, rax
0x18000a080  jmp     short loc_18000A096
0x18000a082  mov     rcx, [rbp+4Fh+String]
0x18000a086  call    cs:__imp_FwFree
0x18000a08d  nop     dword ptr [rax+rax+00h]
0x18000a092  mov     rdx, [rbp+4Fh+pszPath+8]
0x18000a096  mov     eax, [rdi]
0x18000a098  cmp     eax, 5
0x18000a09b  jbe     loc_18000A134
0x18000a0a1  mov     r8, [rdi+18h]
0x18000a0a5  mov     rcx, 400000000000h
0x18000a0af  mov     rax, [rdi+10h]
0x18000a0b3  test    rcx, rax
0x18000a0b6  jz      short loc_18000A134
0x18000a0b8  mov     rax, r8
0x18000a0bb  and     rax, rcx
0x18000a0be  cmp     rax, r8
0x18000a0c1  jnz     short loc_18000A134
0x18000a0c3  test    rdx, rdx
0x18000a0c6  mov     [rbp+4Fh+var_60], r14
0x18000a0ca  lea     rax, aNull_2; "NULL"
0x18000a0d1  mov     [rbp+4Fh+var_80], rsi
0x18000a0d5  cmovnz  rax, rdx
0x18000a0d9  mov     [rbp+4Fh+var_78], r12
0x18000a0dd  mov     [rbp+4Fh+var_70], rax
0x18000a0e1  lea     rdx, word_180115C2E; int
0x18000a0e8  mov     rax, qword ptr [rbp+4Fh+var_48+8]
0x18000a0ec  mov     rcx, rdi; int
0x18000a0ef  mov     [rbp+4Fh+var_68], rax
0x18000a0f3  mov     eax, dword ptr [rbp+4Fh+var_48+4]
0x18000a0f6  mov     dword ptr [rbp+4Fh+String], eax
0x18000a0f9  lea     rax, [rbp+4Fh+var_60]
0x18000a0fd  mov     [rsp+0D0h+var_88], rax; __int64
0x18000a102  lea     rax, [rbp+4Fh+var_80]
0x18000a106  mov     [rsp+0D0h+var_90], rax; __int64
0x18000a10b  lea     rax, [rbp+4Fh+var_78]
0x18000a10f  mov     [rsp+0D0h+var_98], rax; __int64
0x18000a114  lea     rax, [rbp+4Fh+var_70]
0x18000a118  mov     [rsp+0D0h+var_A0], rax; __int64
0x18000a11d  lea     rax, [rbp+4Fh+var_68]
0x18000a121  mov     [rsp+0D0h+var_A8], rax; __int64
0x18000a126  lea     rax, [rbp+4Fh+String]
0x18000a12a  mov     [rsp+0D0h+var_B0], rax; __int64
0x18000a12f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000a134  mov     eax, [rbp+4Fh+var_54]
0x18000a137  cmp     r14, rax
0x18000a13a  jb      loc_18000A1F6
0x18000a140  mov     rax, [rbp+4Fh+arg_20]
0x18000a144  xor     edx, edx
0x18000a146  mov     ecx, ebx
0x18000a148  div     rcx
0x18000a14b  test    rdx, rdx
0x18000a14e  jnz     loc_18000A1F6
0x18000a154  mov     eax, cs:dword_18012C3B0
0x18000a15a  cmp     eax, 4
0x18000a15d  jbe     loc_18000A1F6
0x18000a163  mov     rcx, cs:qword_18012C3C8
0x18000a16a  mov     rdx, 4000000000000h
0x18000a174  mov     rax, cs:qword_18012C3C0
0x18000a17b  test    rdx, rax
0x18000a17e  jz      short loc_18000A1F6
0x18000a180  mov     rax, rcx
0x18000a183  and     rax, rdx
0x18000a186  cmp     rax, rcx
0x18000a189  jnz     short loc_18000A1F6
0x18000a18b  mov     rax, [rbp+4Fh+pszPath+8]
0x18000a18f  lea     rdx, byte_180115E37; int
0x18000a196  mov     [rbp+4Fh+var_80], rax
0x18000a19a  lea     rcx, dword_18012C3B0; int
0x18000a1a1  mov     rax, qword ptr [rbp+4Fh+var_48+8]
0x18000a1a5  mov     [rbp+4Fh+var_60], rax
0x18000a1a9  mov     eax, dword ptr [rbp+4Fh+var_48+4]
0x18000a1ac  mov     dword ptr [rbp+4Fh+String], eax
0x18000a1af  lea     rax, [rbp+4Fh+var_68]
0x18000a1b3  mov     [rsp+0D0h+var_88], rax; __int64
0x18000a1b8  lea     rax, [rbp+4Fh+var_70]
0x18000a1bc  mov     [rsp+0D0h+var_90], rax; __int64
0x18000a1c1  lea     rax, [rbp+4Fh+var_78]
0x18000a1c5  mov     [rsp+0D0h+var_98], rax; __int64
0x18000a1ca  lea     rax, [rbp+4Fh+var_80]
0x18000a1ce  mov     [rsp+0D0h+var_A0], rax; __int64
0x18000a1d3  lea     rax, [rbp+4Fh+var_60]
0x18000a1d7  mov     [rsp+0D0h+var_A8], rax; __int64
0x18000a1dc  lea     rax, [rbp+4Fh+String]
0x18000a1e0  mov     [rsp+0D0h+var_B0], rax; __int64
0x18000a1e5  mov     [rbp+4Fh+var_68], r14
0x18000a1e9  mov     [rbp+4Fh+var_70], rsi
0x18000a1ed  mov     [rbp+4Fh+var_78], r12
0x18000a1f1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000a1f6  lea     rcx, [rbp+4Fh+var_48]
0x18000a1fa  call    cs:__imp_FwFreeRpcCallersProcessInfo
0x18000a201  nop     dword ptr [rax+rax+00h]
0x18000a206  jmp     loc_18000A2F6
0x18000a20b  lea     r15, ServiceName; "MPSSVC"
0x18000a212  cmp     rsi, 0BB8h
0x18000a219  jbe     short loc_18000A28C
0x18000a21b  test    rdi, rdi
0x18000a21e  jz      short loc_18000A28C
0x18000a220  mov     eax, [rdi]
0x18000a222  cmp     eax, 5
0x18000a225  jbe     short loc_18000A28C
0x18000a227  mov     rdx, [rdi+18h]
0x18000a22b  mov     rcx, 400000000000h
0x18000a235  mov     rax, [rdi+10h]
0x18000a239  test    rcx, rax
0x18000a23c  jz      short loc_18000A28C
0x18000a23e  mov     rax, rdx
0x18000a241  and     rax, rcx
0x18000a244  cmp     rax, rdx
0x18000a247  jnz     short loc_18000A28C
0x18000a249  lea     rax, [rbp+4Fh+var_68]
0x18000a24d  mov     [rbp+4Fh+var_68], r14
0x18000a251  mov     [rsp+0D0h+var_98], rax; __int64
0x18000a256  lea     rdx, unk_180115D68; int
0x18000a25d  lea     rax, [rbp+4Fh+var_70]
0x18000a261  mov     [rbp+4Fh+var_70], rsi
0x18000a265  mov     [rsp+0D0h+var_A0], rax; __int64
0x18000a26a  mov     rcx, rdi; int
0x18000a26d  lea     rax, [rbp+4Fh+var_78]
0x18000a271  mov     [rbp+4Fh+var_78], r12
0x18000a275  mov     [rsp+0D0h+var_A8], rax; __int64
0x18000a27a  lea     rax, [rbp+4Fh+var_80]
0x18000a27e  mov     [rsp+0D0h+var_B0], rax; __int64
0x18000a283  mov     [rbp+4Fh+var_80], r15
0x18000a287  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000a28c  mov     eax, [rbp+4Fh+var_54]
0x18000a28f  cmp     r14, rax
0x18000a292  jb      short loc_18000A2F6
0x18000a294  mov     rax, [rbp+4Fh+arg_20]
0x18000a298  xor     edx, edx
0x18000a29a  mov     ecx, ebx
0x18000a29c  div     rcx
0x18000a29f  test    rdx, rdx
0x18000a2a2  jnz     short loc_18000A2F6
0x18000a2a4  mov     eax, cs:dword_18012C3B0
0x18000a2aa  cmp     eax, 4
0x18000a2ad  jbe     short loc_18000A2F6
0x18000a2af  lea     rax, [rbp+4Fh+var_68]
0x18000a2b3  mov     [rbp+4Fh+var_68], r14
0x18000a2b7  mov     [rsp+0D0h+var_98], rax; __int64
0x18000a2bc  lea     rdx, word_180115CDA; int
0x18000a2c3  lea     rax, [rbp+4Fh+var_70]
0x18000a2c7  mov     [rbp+4Fh+var_70], rsi
0x18000a2cb  mov     [rsp+0D0h+var_A0], rax; __int64
0x18000a2d0  lea     rcx, dword_18012C3B0; int
0x18000a2d7  lea     rax, [rbp+4Fh+var_78]
0x18000a2db  mov     [rbp+4Fh+var_78], r12
0x18000a2df  mov     [rsp+0D0h+var_A8], rax; __int64
0x18000a2e4  lea     rax, [rbp+4Fh+var_80]
0x18000a2e8  mov     [rsp+0D0h+var_B0], rax; __int64
0x18000a2ed  mov     [rbp+4Fh+var_80], r15
0x18000a2f1  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000a2f6  mov     rcx, [rbp+4Fh+var_28]
0x18000a2fa  xor     rcx, rsp; StackCookie
0x18000a2fd  call    __security_check_cookie
0x18000a302  lea     r11, [rsp+0D0h+var_20]
0x18000a30a  mov     rbx, [r11+38h]
0x18000a30e  mov     rsi, [r11+40h]
0x18000a312  mov     rsp, r11
0x18000a315  pop     r15
0x18000a317  pop     r14
0x18000a319  pop     r12
0x18000a31b  pop     rdi
0x18000a31c  pop     rbp
0x18000a31d  retn
```
