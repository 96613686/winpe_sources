# GetCPrepCapacityNodeReference(wchar_t const *,IClusterCapacityNode * *)

- ea: `0x18008d69c`
- end: `0x18008dab0`
- name: `?GetCPrepCapacityNodeReference@@YAJPEB_WPEAPEAUIClusterCapacityNode@@@Z`
- size: `1044`
- prototype: `__int64 __fastcall(const wchar_t *, struct IClusterCapacityNode **)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18008d178`
- `0x18008e8dc`

## callees

- `0x180002f50`
- `0x18001cb44`
- `0x18001cc2c`
- `0x18001ecdc`
- `0x180028f30`
- `0x180029578`
- `0x18002a644`
- `0x180038494`
- `0x180040418`
- `0x18006f910`
- `0x18008d69c`
- `0x18009e638`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008d93c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008d93c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d916`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008d9d8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008d9d8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18008d90c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18008d90c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18008d97b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18008d97b`

## string_xrefs

- `0x18008d826`: `Error generating Service Principal Name for node %ws. HRESULT %0xX.`
- `0x18008d876`: `Service Principal Name is %ws.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetCPrepCapacityNodeReference(const wchar_t *a1, struct IClusterCapacityNode **a2)
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
  struct IClusterCapacityNode **v21; // [rsp+78h] [rbp-2F0h]
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
    pResults.pIID = &IID_IClusterCapacityNode;
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
        v12 = CoCreateInstanceEx(&CLSID_ClusterCapacityNode, 0, v4, v3, 1u, &pResults);
        LastError = v12;
        if ( v12 >= 0 )
        {
          if ( !v2 )
            v2 = L"<LocalNode>";
          TraceMsg(
            4,
            11,
            L"GetCPrepCapacityNodeReference",
            152,
            L"Instantiation of IClusterCapacityNode interface to node %ws Succeeded",
            v2);
LABEL_34:
          *v21 = (struct IClusterCapacityNode *)pResults.pItf;
          goto LABEL_35;
        }
        if ( v12 != -2146959355 )
        {
          if ( !v2 )
            v2 = L"<LocalNode>";
          LODWORD(v15) = v12;
          TraceMsg(
            2,
            11,
            L"GetCPrepCapacityNodeReference",
            144,
            L"Cannot instantiate IClusterCapacityNode interface to node %ws. HRESULT = %0xX.",
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
          11,
          L"GetCPrepCapacityNodeReference",
          136,
          L"Instantiation of IClusterCapacityNode interface to node %ws failed with HRESULT = %0xX. Retrying after 5 secs",
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
      TraceMsg(4, 11, L"GetCPrepCapacityNodeReference", 88, L"Service Principal Name is %ws.", &base);
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
      11,
      L"GetCPrepCapacityNodeReference",
      83,
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
0x18008d69c  mov     [rsp+arg_10], rsi
0x18008d6a1  push    rdi
0x18008d6a2  push    r12
0x18008d6a4  push    r13
0x18008d6a6  push    r14
0x18008d6a8  push    r15
0x18008d6aa  sub     rsp, 340h
0x18008d6b1  mov     rax, cs:__security_cookie
0x18008d6b8  xor     rax, rsp
0x18008d6bb  mov     [rsp+368h+var_38], rax
0x18008d6c3  mov     [rsp+368h+var_2F0], rdx
0x18008d6c8  mov     rsi, rcx
0x18008d6cb  mov     [rsp+368h+nSize], 0
0x18008d6d3  xorps   xmm0, xmm0
0x18008d6d6  movups  [rsp+368h+var_2D0], xmm0
0x18008d6de  movups  [rsp+368h+var_2C0], xmm0
0x18008d6e6  xorps   xmm1, xmm1
0x18008d6e9  xor     eax, eax
0x18008d6eb  movups  [rsp+368h+var_318], xmm1
0x18008d6f0  movups  [rsp+368h+var_308], xmm1
0x18008d6f5  mov     [rsp+368h+var_2F8], rax
0x18008d6fa  mov     [rsp+368h+var_320], rax
0x18008d6ff  mov     [rsp+368h+var_2B0], rax
0x18008d707  lea     rax, IID_IClusterCapacityNode
0x18008d70e  mov     [rsp+368h+var_2E8.pIID], rax
0x18008d716  mov     [rsp+368h+var_2E8.pItf], 0
0x18008d722  mov     [rsp+368h+var_2E8.hr], 0
0x18008d72d  test    rcx, rcx
0x18008d730  jnz     short loc_18008D741
0x18008d732  xor     r13d, r13d
0x18008d735  lea     r14d, [rcx+4]
0x18008d739  mov     r15d, r14d
0x18008d73c  jmp     loc_18008D948
0x18008d741  mov     rdx, rsi
0x18008d744  lea     rcx, [rsp+368h+var_298]
0x18008d74c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008d751  nop
0x18008d752  lea     rdx, S; "."
0x18008d759  lea     rcx, [rsp+368h+var_298]
0x18008d761  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find(wchar_t const * const,unsigned __int64)
0x18008d766  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008d76a  jnz     short loc_18008D7EB
0x18008d76c  lea     r9d, [rax+10h]
0x18008d770  cmp     [rsp+368h+var_288], r9
0x18008d778  jbe     short loc_18008D797
0x18008d77a  lea     rdx, [rsp+368h+var_258]
0x18008d782  lea     rcx, [rsp+368h+var_298]
0x18008d78a  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18008d78f  nop
0x18008d790  mov     edi, 1
0x18008d795  jmp     short loc_18008D7B1
0x18008d797  lea     rdx, [rsp+368h+var_298]
0x18008d79f  lea     rcx, [rsp+368h+var_278]
0x18008d7a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008d7ac  mov     edi, 2
0x18008d7b1  mov     rdx, rax
0x18008d7b4  lea     rcx, [rsp+368h+var_298]
0x18008d7bc  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008d7c1  test    dil, 2
0x18008d7c5  jz      short loc_18008D7D8
0x18008d7c7  and     edi, 0FFFFFFFDh
0x18008d7ca  lea     rcx, [rsp+368h+var_278]
0x18008d7d2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d7d7  nop
0x18008d7d8  test    dil, 1
0x18008d7dc  jz      short loc_18008D7EB
0x18008d7de  lea     rcx, [rsp+368h+var_258]
0x18008d7e6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d7eb  lea     rcx, [rsp+368h+var_298]
0x18008d7f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18008d7f8  mov     rdx, rax; ServiceName
0x18008d7fb  lea     r8, [rsp+368h+var_320]
0x18008d800  lea     rcx, ServiceClass; "HOST"
0x18008d807  call    ClRtlMakeServicePrincipalName
0x18008d80c  mov     edi, eax
0x18008d80e  test    eax, eax
0x18008d810  jz      short loc_18008D85E
0x18008d812  jle     short loc_18008D81D
0x18008d814  movzx   edi, ax
0x18008d817  or      edi, 80070000h
0x18008d81d  mov     [rsp+368h+var_338], edi
0x18008d821  mov     [rsp+368h+pResults], rsi
0x18008d826  lea     rax, aErrorGeneratin; "Error generating Service Principal Name"...
0x18008d82d  mov     qword ptr [rsp+368h+dwCount], rax
0x18008d832  mov     r9d, 53h ; 'S'
0x18008d838  lea     r8, aGetcprepcapaci; "GetCPrepCapacityNodeReference"
0x18008d83f  lea     edx, [r9-48h]
0x18008d843  lea     ecx, [rdx-9]
0x18008d846  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008d84b  nop
0x18008d84c  lea     rcx, [rsp+368h+var_298]
0x18008d854  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d859  jmp     loc_18008DA66
0x18008d85e  lea     rax, base
0x18008d865  mov     rdi, [rsp+368h+var_320]
0x18008d86a  test    rdi, rdi
0x18008d86d  cmovnz  rax, rdi
0x18008d871  mov     [rsp+368h+pResults], rax
0x18008d876  lea     rax, aServicePrincip; "Service Principal Name is %ws."
0x18008d87d  mov     qword ptr [rsp+368h+dwCount], rax
0x18008d882  mov     r9d, 58h ; 'X'
0x18008d888  lea     r8, aGetcprepcapaci; "GetCPrepCapacityNodeReference"
0x18008d88f  lea     edx, [r9-4Dh]
0x18008d893  lea     r14d, [r9-54h]
0x18008d897  mov     ecx, r14d
0x18008d89a  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008d89f  mov     dword ptr [rsp+368h+var_318], 9
0x18008d8a7  mov     dword ptr [rsp+368h+var_318+4], 0FFFFFFFFh
0x18008d8af  mov     qword ptr [rsp+368h+var_318+8], rdi
0x18008d8b4  mov     dword ptr [rsp+368h+var_308], 6
0x18008d8bc  mov     dword ptr [rsp+368h+var_308+4], 3
0x18008d8c4  mov     qword ptr [rsp+368h+var_308+8], 0
0x18008d8cd  mov     dword ptr [rsp+368h+var_2F8], 1
0x18008d8d5  mov     qword ptr [rsp+368h+var_2D0+8], rsi
0x18008d8dd  lea     rax, [rsp+368h+var_318]
0x18008d8e2  mov     qword ptr [rsp+368h+var_2C0], rax
0x18008d8ea  lea     rcx, [rsp+368h+var_298]
0x18008d8f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d8f7  mov     [rsp+368h+nSize], 100h
0x18008d8ff  lea     rdx, [rsp+368h+nSize]; nSize
0x18008d904  lea     rcx, [rsp+368h+Buffer]; lpBuffer
0x18008d90c  call    cs:__imp_GetComputerNameW
0x18008d912  test    eax, eax
0x18008d914  jnz     short loc_18008D923
0x18008d916  call    cs:__imp_GetLastError
0x18008d91c  mov     edi, eax
0x18008d91e  jmp     loc_18008DA66
0x18008d923  lea     r13, [rsp+368h+var_2D0]
0x18008d92b  mov     r15d, 10h
0x18008d931  mov     rdx, rsi
0x18008d934  lea     rcx, [rsp+368h+Buffer]
0x18008d93c  call    cs:__imp__o__wcsicmp
0x18008d942  test    eax, eax
0x18008d944  cmovz   r15d, r14d
0x18008d948  xor     edi, edi
0x18008d94a  xor     r12d, r12d
0x18008d94d  cmp     r12d, 5
0x18008d951  jnb     loc_18008DA52
0x18008d957  lea     rax, [rsp+368h+var_2E8]
0x18008d95f  mov     [rsp+368h+pResults], rax; pResults
0x18008d964  mov     [rsp+368h+dwCount], 1; dwCount
0x18008d96c  mov     r9, r13; pServerInfo
0x18008d96f  mov     r8d, r15d; dwClsCtx
0x18008d972  xor     edx, edx; punkOuter
0x18008d974  lea     rcx, CLSID_ClusterCapacityNode; Clsid
0x18008d97b  call    cs:__imp_CoCreateInstanceEx
0x18008d981  mov     edi, eax
0x18008d983  lea     r8, aGetcprepcapaci; "GetCPrepCapacityNodeReference"
0x18008d98a  test    eax, eax
0x18008d98c  jns     loc_18008DA1E
0x18008d992  mov     edx, 80080005h
0x18008d997  cmp     eax, edx
0x18008d999  jnz     short loc_18008D9E6
0x18008d99b  mov     rax, rsi
0x18008d99e  test    rsi, rsi
0x18008d9a1  lea     rcx, aLocalnode; "<LocalNode>"
0x18008d9a8  cmovz   rax, rcx
0x18008d9ac  mov     [rsp+368h+var_338], edx
0x18008d9b0  mov     [rsp+368h+pResults], rax
0x18008d9b5  lea     rax, aInstantiationO_1; "Instantiation of IClusterCapacityNode i"...
0x18008d9bc  mov     qword ptr [rsp+368h+dwCount], rax
0x18008d9c1  mov     r9d, 88h
0x18008d9c7  lea     edx, [r9-7Dh]
0x18008d9cb  lea     ecx, [rdx-9]
0x18008d9ce  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008d9d3  mov     ecx, 1388h; dwMilliseconds
0x18008d9d8  call    cs:__imp_Sleep
0x18008d9de  inc     r12d
0x18008d9e1  jmp     loc_18008D94D
0x18008d9e6  test    rsi, rsi
0x18008d9e9  lea     rax, aLocalnode; "<LocalNode>"
0x18008d9f0  cmovz   rsi, rax
0x18008d9f4  mov     [rsp+368h+var_338], edi
0x18008d9f8  mov     [rsp+368h+pResults], rsi
0x18008d9fd  lea     rax, aCannotInstanti; "Cannot instantiate IClusterCapacityNode"...
0x18008da04  mov     qword ptr [rsp+368h+dwCount], rax
0x18008da09  mov     r9d, 90h
0x18008da0f  mov     edx, 0Bh
0x18008da14  lea     ecx, [rdx-9]
0x18008da17  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008da1c  jmp     short loc_18008DA66
0x18008da1e  test    rsi, rsi
0x18008da21  lea     rax, aLocalnode; "<LocalNode>"
0x18008da28  cmovz   rsi, rax
0x18008da2c  mov     [rsp+368h+pResults], rsi
0x18008da31  lea     rax, aInstantiationO_2; "Instantiation of IClusterCapacityNode i"...
0x18008da38  mov     qword ptr [rsp+368h+dwCount], rax
0x18008da3d  mov     r9d, 98h
0x18008da43  mov     edx, 0Bh
0x18008da48  mov     ecx, r14d
0x18008da4b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18008da50  jmp     short loc_18008DA56
0x18008da52  test    edi, edi
0x18008da54  js      short loc_18008DA66
0x18008da56  mov     rax, [rsp+368h+var_2E8.pItf]
0x18008da5e  mov     rcx, [rsp+368h+var_2F0]
0x18008da63  mov     [rcx], rax
0x18008da66  xor     ecx, ecx; void *
0x18008da68  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x18008da6d  mov     eax, edi
0x18008da6f  jmp     short loc_18008DA85
0x18008da71  mov     eax, [rsp+368h+nSize]
0x18008da75  test    eax, eax
0x18008da77  jg      short loc_18008DA7B
0x18008da79  jmp     short loc_18008DA85
0x18008da7b  movzx   eax, word ptr [rsp+368h+nSize]
0x18008da80  or      eax, 80070000h
0x18008da85  mov     rcx, [rsp+368h+var_38]
0x18008da8d  xor     rcx, rsp; StackCookie
0x18008da90  call    __security_check_cookie
0x18008da95  mov     rsi, [rsp+368h+arg_10]
0x18008da9d  add     rsp, 340h
0x18008daa4  pop     r15
0x18008daa6  pop     r14
0x18008daa8  pop     r13
0x18008daaa  pop     r12
0x18008daac  pop     rdi
0x18008daad  retn
0x18008daae  jmp     short loc_18008DA7B
```
