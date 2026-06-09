# GetCPrepSetupReference(wchar_t const *,IClusterSetup * *)

- ea: `0x1800395ec`
- end: `0x1800399f9`
- name: `?GetCPrepSetupReference@@YAJPEB_WPEAPEAUIClusterSetup@@@Z`
- size: `1037`
- prototype: `__int64 __fastcall(const wchar_t *, struct IClusterSetup **)`
- caller_count: `10`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003302c`
- `0x1800332b8`
- `0x180038cdc`
- `0x180038e50`
- `0x18003b03c`
- `0x18003b22c`
- `0x18003bd30`
- `0x18003d884`
- `0x18007a820`
- `0x18007a900`

## callees

- `0x180002f50`
- `0x18001cb44`
- `0x18001cc2c`
- `0x18001ecdc`
- `0x180028f30`
- `0x180029578`
- `0x18002a644`
- `0x180038494`
- `0x1800395ec`
- `0x180040418`
- `0x18006f910`
- `0x18009e638`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180039888`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180039888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039862`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180039922`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180039922`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180039858`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180039858`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800398c7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800398c7`

## string_xrefs

- `0x180039776`: `Error generating Service Principal Name for node %ws. HRESULT %0xX.`
- `0x1800397c4`: `Service Principal Name is %ws.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetCPrepSetupReference(const wchar_t *a1, struct IClusterSetup **a2)
{
  const wchar_t *v2; // rsi
  COSERVERINFO *v3; // r13
  DWORD v4; // r15d
  __int64 v5; // r8
  __int64 v6; // rax
  char v7; // di
  const WCHAR *v8; // rdx
  int ServicePrincipalName; // eax
  signed int LastError; // edi
  unsigned int i; // r12d
  HRESULT v12; // eax
  const wchar_t *v13; // rax
  __int64 result; // rax
  __int64 v15; // [rsp+30h] [rbp-338h]
  DWORD nSize; // [rsp+40h] [rbp-328h] BYREF
  __int64 v17; // [rsp+48h] [rbp-320h]
  __int128 v18; // [rsp+50h] [rbp-318h] BYREF
  __int128 v19; // [rsp+60h] [rbp-308h]
  __int64 v20; // [rsp+70h] [rbp-2F8h]
  struct IClusterSetup **v21; // [rsp+78h] [rbp-2F0h]
  MULTI_QI pResults; // [rsp+80h] [rbp-2E8h] BYREF
  __int128 v23; // [rsp+98h] [rbp-2D0h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-2C0h]
  __int64 v25; // [rsp+B8h] [rbp-2B0h]
  cxl::Exception *v26; // [rsp+C0h] [rbp-2A8h] BYREF
  std::system_error *v27; // [rsp+C8h] [rbp-2A0h] BYREF
  _BYTE v28[16]; // [rsp+D0h] [rbp-298h] BYREF
  unsigned __int64 v29; // [rsp+E0h] [rbp-288h]
  _BYTE v30[32]; // [rsp+F0h] [rbp-278h] BYREF
  _BYTE v31[32]; // [rsp+110h] [rbp-258h] BYREF
  WCHAR Buffer[256]; // [rsp+130h] [rbp-238h] BYREF

  try
  {
    v21 = a2;
    v2 = a1;
    nSize = 0;
    v23 = 0;
    v24 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v17 = 0;
    v25 = 0;
    pResults.pIID = &IID_IClusterSetup;
    pResults.pItf = 0;
    pResults.hr = 0;
    if ( !a1 )
    {
      v3 = 0;
      v4 = 4;
LABEL_20:
      LastError = 0;
      for ( i = 0; i < 5; ++i )
      {
        v12 = CoCreateInstanceEx(&CLSID_ClusterSetup, 0, v4, v3, 1u, &pResults);
        LastError = v12;
        if ( v12 >= 0 )
        {
          if ( !v2 )
            v2 = L"<LocalNode>";
          TraceMsg(
            4,
            0,
            L"GetCPrepSetupReference",
            8722,
            L"Instantiation of IClusterSetup interface to node %ws Succeeded",
            v2);
LABEL_34:
          *v21 = (struct IClusterSetup *)pResults.pItf;
          goto LABEL_35;
        }
        if ( v12 != -2146959355 )
        {
          if ( !v2 )
            v2 = L"<LocalNode>";
          LODWORD(v15) = v12;
          TraceMsg(
            2,
            0,
            L"GetCPrepSetupReference",
            8716,
            L"Cannot instantiate IClusterSetup interface to node %ws. HRESULT = %0xX.",
            v2,
            v15);
          goto LABEL_35;
        }
        v13 = v2;
        if ( !v2 )
          v13 = L"<LocalNode>";
        LODWORD(v15) = -2146959355;
        TraceMsg(
          2,
          0,
          L"GetCPrepSetupReference",
          8709,
          L"Instantiation of IClusterSetup interface to node %ws failed with HRESULT = %0xX. Retrying after 5 secs",
          v13,
          v15);
        Sleep(0x1388u);
      }
      if ( LastError < 0 )
        goto LABEL_35;
      goto LABEL_34;
    }
    std::wstring::wstring(v28, a1);
    if ( std::wstring::find(v28, L".") == -1 )
    {
      if ( v29 <= 0xF )
      {
        v6 = std::wstring::wstring(v30, v28);
        v7 = 2;
      }
      else
      {
        v6 = std::wstring::substr(v28, v31, v5, 15);
        v7 = 1;
      }
      std::wstring::operator=(v28, v6);
      if ( (v7 & 2) != 0 )
      {
        v7 &= ~2u;
        std::wstring::_Tidy_deallocate(v30);
      }
      if ( (v7 & 1) != 0 )
        std::wstring::_Tidy_deallocate(v31);
    }
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v28);
    ServicePrincipalName = ClRtlMakeServicePrincipalName(L"HOST", v8);
    LastError = ServicePrincipalName;
    if ( !ServicePrincipalName )
    {
      TraceMsg(4, 0, L"GetCPrepSetupReference", 8659, L"Service Principal Name is %ws.", &base);
      *(_QWORD *)&v18 = -4294967287LL;
      *((_QWORD *)&v18 + 1) = v17;
      v19 = 0x300000006uLL;
      LODWORD(v20) = 1;
      *((_QWORD *)&v23 + 1) = v2;
      *(_QWORD *)&v24 = &v18;
      std::wstring::_Tidy_deallocate(v28);
      nSize = 256;
      if ( !GetComputerNameW(Buffer, &nSize) )
      {
        LastError = GetLastError();
        goto LABEL_35;
      }
      v3 = (COSERVERINFO *)&v23;
      v4 = 16;
      if ( !(unsigned int)_o__wcsicmp(Buffer) )
        v4 = 4;
      goto LABEL_20;
    }
    if ( ServicePrincipalName > 0 )
      LastError = (unsigned __int16)ServicePrincipalName | 0x80070000;
    TraceMsg(
      2,
      0,
      L"GetCPrepSetupReference",
      8654,
      L"Error generating Service Principal Name for node %ws. HRESULT %0xX.",
      v2,
      LastError);
    std::wstring::_Tidy_deallocate(v28);
LABEL_35:
    CTSmartPtr_PolicyLocalMem::DestroyMem(0);
    result = (unsigned int)LastError;
  }
  catch ( cxl::Exception *v26 )
  {
    nSize = cxl::ErrorCode::GetWinError((cxl::Exception *)((char *)v26 + 88));
    goto LABEL_36;
  }
  catch ( std::system_error *v27 )
  {
    nSize = *((_DWORD *)v27 + 6);
LABEL_36:
    result = nSize;
    if ( (int)nSize > 0 )
      return (unsigned __int16)nSize | 0x80070000;
    return result;
  }
  catch ( std::bad_alloc )
  {
    nSize = 14;
    return (unsigned __int16)nSize | 0x80070000;
  }
  catch ( std::exception )
  {
    nSize = 1359;
    return (unsigned __int16)nSize | 0x80070000;
  }
  catch ( ... )
  {
    nSize = 1359;
    return (unsigned __int16)nSize | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800395ec  mov     [rsp+arg_10], rsi
0x1800395f1  push    rdi
0x1800395f2  push    r12
0x1800395f4  push    r13
0x1800395f6  push    r14
0x1800395f8  push    r15
0x1800395fa  sub     rsp, 340h
0x180039601  mov     rax, cs:__security_cookie
0x180039608  xor     rax, rsp
0x18003960b  mov     [rsp+368h+var_38], rax
0x180039613  mov     [rsp+368h+var_2F0], rdx
0x180039618  mov     rsi, rcx
0x18003961b  mov     [rsp+368h+nSize], 0
0x180039623  xorps   xmm0, xmm0
0x180039626  movups  [rsp+368h+var_2D0], xmm0
0x18003962e  movups  [rsp+368h+var_2C0], xmm0
0x180039636  xorps   xmm1, xmm1
0x180039639  xor     eax, eax
0x18003963b  movups  [rsp+368h+var_318], xmm1
0x180039640  movups  [rsp+368h+var_308], xmm1
0x180039645  mov     [rsp+368h+var_2F8], rax
0x18003964a  mov     [rsp+368h+var_320], rax
0x18003964f  mov     [rsp+368h+var_2B0], rax
0x180039657  lea     rax, IID_IClusterSetup
0x18003965e  mov     [rsp+368h+var_2E8.pIID], rax
0x180039666  mov     [rsp+368h+var_2E8.pItf], 0
0x180039672  mov     [rsp+368h+var_2E8.hr], 0
0x18003967d  test    rcx, rcx
0x180039680  jnz     short loc_180039691
0x180039682  xor     r13d, r13d
0x180039685  lea     r14d, [rcx+4]
0x180039689  mov     r15d, r14d
0x18003968c  jmp     loc_180039894
0x180039691  mov     rdx, rsi
0x180039694  lea     rcx, [rsp+368h+var_298]
0x18003969c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800396a1  nop
0x1800396a2  lea     rdx, S; "."
0x1800396a9  lea     rcx, [rsp+368h+var_298]
0x1800396b1  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find(wchar_t const * const,unsigned __int64)
0x1800396b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800396ba  jnz     short loc_18003973B
0x1800396bc  lea     r9d, [rax+10h]
0x1800396c0  cmp     [rsp+368h+var_288], r9
0x1800396c8  jbe     short loc_1800396E7
0x1800396ca  lea     rdx, [rsp+368h+var_258]
0x1800396d2  lea     rcx, [rsp+368h+var_298]
0x1800396da  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800396df  nop
0x1800396e0  mov     edi, 1
0x1800396e5  jmp     short loc_180039701
0x1800396e7  lea     rdx, [rsp+368h+var_298]
0x1800396ef  lea     rcx, [rsp+368h+var_278]
0x1800396f7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800396fc  mov     edi, 2
0x180039701  mov     rdx, rax
0x180039704  lea     rcx, [rsp+368h+var_298]
0x18003970c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180039711  test    dil, 2
0x180039715  jz      short loc_180039728
0x180039717  and     edi, 0FFFFFFFDh
0x18003971a  lea     rcx, [rsp+368h+var_278]
0x180039722  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039727  nop
0x180039728  test    dil, 1
0x18003972c  jz      short loc_18003973B
0x18003972e  lea     rcx, [rsp+368h+var_258]
0x180039736  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003973b  lea     rcx, [rsp+368h+var_298]
0x180039743  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180039748  mov     rdx, rax; ServiceName
0x18003974b  lea     r8, [rsp+368h+var_320]
0x180039750  lea     rcx, ServiceClass; "HOST"
0x180039757  call    ClRtlMakeServicePrincipalName
0x18003975c  mov     edi, eax
0x18003975e  test    eax, eax
0x180039760  jz      short loc_1800397AC
0x180039762  jle     short loc_18003976D
0x180039764  movzx   edi, ax
0x180039767  or      edi, 80070000h
0x18003976d  mov     [rsp+368h+var_338], edi
0x180039771  mov     [rsp+368h+pResults], rsi
0x180039776  lea     rax, aErrorGeneratin; "Error generating Service Principal Name"...
0x18003977d  mov     qword ptr [rsp+368h+dwCount], rax
0x180039782  mov     r9d, 21CEh
0x180039788  lea     r8, aGetcprepsetupr; "GetCPrepSetupReference"
0x18003978f  xor     edx, edx
0x180039791  lea     ecx, [rdx+2]
0x180039794  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180039799  nop
0x18003979a  lea     rcx, [rsp+368h+var_298]
0x1800397a2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800397a7  jmp     loc_1800399AA
0x1800397ac  lea     rax, base
0x1800397b3  mov     rdi, [rsp+368h+var_320]
0x1800397b8  test    rdi, rdi
0x1800397bb  cmovnz  rax, rdi
0x1800397bf  mov     [rsp+368h+pResults], rax
0x1800397c4  lea     rax, aServicePrincip; "Service Principal Name is %ws."
0x1800397cb  mov     qword ptr [rsp+368h+dwCount], rax
0x1800397d0  mov     r9d, 21D3h
0x1800397d6  lea     r8, aGetcprepsetupr; "GetCPrepSetupReference"
0x1800397dd  xor     edx, edx
0x1800397df  lea     r14d, [rdx+4]
0x1800397e3  mov     ecx, r14d
0x1800397e6  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800397eb  mov     dword ptr [rsp+368h+var_318], 9
0x1800397f3  mov     dword ptr [rsp+368h+var_318+4], 0FFFFFFFFh
0x1800397fb  mov     qword ptr [rsp+368h+var_318+8], rdi
0x180039800  mov     dword ptr [rsp+368h+var_308], 6
0x180039808  mov     dword ptr [rsp+368h+var_308+4], 3
0x180039810  mov     qword ptr [rsp+368h+var_308+8], 0
0x180039819  mov     dword ptr [rsp+368h+var_2F8], 1
0x180039821  mov     qword ptr [rsp+368h+var_2D0+8], rsi
0x180039829  lea     rax, [rsp+368h+var_318]
0x18003982e  mov     qword ptr [rsp+368h+var_2C0], rax
0x180039836  lea     rcx, [rsp+368h+var_298]
0x18003983e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039843  mov     [rsp+368h+nSize], 100h
0x18003984b  lea     rdx, [rsp+368h+nSize]; nSize
0x180039850  lea     rcx, [rsp+368h+Buffer]; lpBuffer
0x180039858  call    cs:__imp_GetComputerNameW
0x18003985e  test    eax, eax
0x180039860  jnz     short loc_18003986F
0x180039862  call    cs:__imp_GetLastError
0x180039868  mov     edi, eax
0x18003986a  jmp     loc_1800399AA
0x18003986f  lea     r13, [rsp+368h+var_2D0]
0x180039877  mov     r15d, 10h
0x18003987d  mov     rdx, rsi
0x180039880  lea     rcx, [rsp+368h+Buffer]
0x180039888  call    cs:__imp__o__wcsicmp
0x18003988e  test    eax, eax
0x180039890  cmovz   r15d, r14d
0x180039894  xor     edi, edi
0x180039896  xor     r12d, r12d
0x180039899  cmp     r12d, 5
0x18003989d  jnb     loc_180039996
0x1800398a3  lea     rax, [rsp+368h+var_2E8]
0x1800398ab  mov     [rsp+368h+pResults], rax; pResults
0x1800398b0  mov     [rsp+368h+dwCount], 1; dwCount
0x1800398b8  mov     r9, r13; pServerInfo
0x1800398bb  mov     r8d, r15d; dwClsCtx
0x1800398be  xor     edx, edx; punkOuter
0x1800398c0  lea     rcx, CLSID_ClusterSetup; Clsid
0x1800398c7  call    cs:__imp_CoCreateInstanceEx
0x1800398cd  mov     edi, eax
0x1800398cf  lea     r8, aGetcprepsetupr; "GetCPrepSetupReference"
0x1800398d6  test    eax, eax
0x1800398d8  jns     loc_180039965
0x1800398de  mov     edx, 80080005h
0x1800398e3  cmp     eax, edx
0x1800398e5  jnz     short loc_180039930
0x1800398e7  mov     rax, rsi
0x1800398ea  test    rsi, rsi
0x1800398ed  lea     rcx, aLocalnode; "<LocalNode>"
0x1800398f4  cmovz   rax, rcx
0x1800398f8  mov     [rsp+368h+var_338], edx
0x1800398fc  mov     [rsp+368h+pResults], rax
0x180039901  lea     rax, aInstantiationO_0; "Instantiation of IClusterSetup interfac"...
0x180039908  mov     qword ptr [rsp+368h+dwCount], rax
0x18003990d  mov     r9d, 2205h
0x180039913  xor     edx, edx
0x180039915  lea     ecx, [rdx+2]
0x180039918  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003991d  mov     ecx, 1388h; dwMilliseconds
0x180039922  call    cs:__imp_Sleep
0x180039928  inc     r12d
0x18003992b  jmp     loc_180039899
0x180039930  test    rsi, rsi
0x180039933  lea     rax, aLocalnode; "<LocalNode>"
0x18003993a  cmovz   rsi, rax
0x18003993e  mov     [rsp+368h+var_338], edi
0x180039942  mov     [rsp+368h+pResults], rsi
0x180039947  lea     rax, aCannotInstanti_0; "Cannot instantiate IClusterSetup interf"...
0x18003994e  mov     qword ptr [rsp+368h+dwCount], rax
0x180039953  mov     r9d, 220Ch
0x180039959  xor     edx, edx
0x18003995b  lea     ecx, [rdx+2]
0x18003995e  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180039963  jmp     short loc_1800399AA
0x180039965  test    rsi, rsi
0x180039968  lea     rax, aLocalnode; "<LocalNode>"
0x18003996f  cmovz   rsi, rax
0x180039973  mov     [rsp+368h+pResults], rsi
0x180039978  lea     rax, aInstantiationO; "Instantiation of IClusterSetup interfac"...
0x18003997f  mov     qword ptr [rsp+368h+dwCount], rax
0x180039984  mov     r9d, 2212h
0x18003998a  xor     edx, edx
0x18003998c  mov     ecx, r14d
0x18003998f  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180039994  jmp     short loc_18003999A
0x180039996  test    edi, edi
0x180039998  js      short loc_1800399AA
0x18003999a  mov     rax, [rsp+368h+var_2E8.pItf]
0x1800399a2  mov     rcx, [rsp+368h+var_2F0]
0x1800399a7  mov     [rcx], rax
0x1800399aa  xor     ecx, ecx; void *
0x1800399ac  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800399b1  mov     eax, edi
0x1800399b3  jmp     short loc_1800399CF
0x1800399b5  jmp     short $+2
0x1800399b7  mov     eax, [rsp+368h+nSize]
0x1800399bb  test    eax, eax
0x1800399bd  jg      short loc_1800399C5
0x1800399bf  jmp     short loc_1800399CF
0x1800399c1  jmp     short loc_1800399C5
0x1800399c3  jmp     short $+2
0x1800399c5  movzx   eax, word ptr [rsp+368h+nSize]
0x1800399ca  or      eax, 80070000h
0x1800399cf  mov     rcx, [rsp+368h+var_38]
0x1800399d7  xor     rcx, rsp; StackCookie
0x1800399da  call    __security_check_cookie
0x1800399df  mov     rsi, [rsp+368h+arg_10]
0x1800399e7  add     rsp, 340h
0x1800399ee  pop     r15
0x1800399f0  pop     r14
0x1800399f2  pop     r13
0x1800399f4  pop     r12
0x1800399f6  pop     rdi
0x1800399f7  retn
```
