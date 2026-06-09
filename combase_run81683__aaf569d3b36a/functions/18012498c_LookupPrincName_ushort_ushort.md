# LookupPrincName(ushort,ushort * *)

- ea: `0x18012498c`
- end: `0x180124cf1`
- name: `?LookupPrincName@@YAJGPEAPEAG@Z`
- size: `869`
- prototype: `HRESULT __fastcall(ProcessToken *wAuthnSvc, wchar_t **pPrincName)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180111200`
- `0x1801672b4`

## callees

- `0x1800521b8`
- `0x18005c640`
- `0x18005cde8`
- `0x18005ce60`
- `0x180087660`
- `0x18008db2c`
- `0x1800a6f50`
- `0x18012498c`
- `0x1801999b0`
- `0x18019a080`
- `0x1801ac6d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124c28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180124c28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180124aba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180124b19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180124bba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180124aba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180124b19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180124bba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180124b9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180124ca0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180124b9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180124ca0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180124a63`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180124a77`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180124a63`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180124a77`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180124b80`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180124c1e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180124b80`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180124c1e`

## string_xrefs

- `0x180124a37`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180124c74`: `onecore\com\combase\dcomrem\security.cxx`

## pseudocode

```c
HRESULT __fastcall LookupPrincName(ProcessToken *wAuthnSvc, wchar_t **pPrincName)
{
  __int16 v3; // si
  HRESULT result; // eax
  HRESULT FQDN; // ebx
  wchar_t *v6; // r15
  int v7; // r12d
  CRpcResolver *v8; // rcx
  unsigned int *p_lNameLen; // rsi
  wchar_t *v10; // r15
  __int64 v11; // r14
  unsigned __int64 v12; // r14
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  unsigned __int64 v15; // rcx
  wchar_t *v16; // r9
  __int64 v17; // rax
  void *v18; // rsp
  wchar_t *v19; // r9
  unsigned __int64 v20; // rcx
  __int64 v21; // rax
  void *v22; // rsp
  unsigned int lNameLen; // [rsp+30h] [rbp+0h] BYREF
  unsigned int lDomainLen; // [rsp+34h] [rbp+4h] BYREF
  _SID_NAME_USE sIgnore; // [rsp+38h] [rbp+8h] BYREF
  wchar_t *pwszFQDN; // [rsp+40h] [rbp+10h] BYREF
  void *hThread; // [rsp+48h] [rbp+18h] BYREF

  *pPrincName = 0;
  lNameLen = 80;
  v3 = (__int16)wAuthnSvc;
  lDomainLen = 80;
  sIgnore = 0;
  hThread = 0;
  pwszFQDN = 0;
  result = ProcessToken::GetSelfSid(wAuthnSvc, (void **)&pwszFQDN);
  if ( result >= 0 )
  {
    FQDN = SuspendImpersonate(&hThread);
    if ( FQDN < 0 )
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\dcomrem\\security.cxx",
          "LookupPrincName",
          6369,
          ERRORS,
          L"%!HRESULT!",
          FQDN);
      return FQDN;
    }
    v6 = pwszFQDN;
    v7 = 0;
    if ( v3 != 10 && (EqualSid(&LOCAL_SYSTEM_SID, pwszFQDN) || EqualSid(&NETWORKSERVICE_SID, v6)) )
    {
      pwszFQDN = 0;
      p_lNameLen = 0;
      FQDN = CRpcResolver::GetFQDN(v8, &pwszFQDN);
      if ( FQDN < 0 )
      {
        v12 = 0;
        goto LABEL_32;
      }
      v10 = pwszFQDN;
      v11 = -1;
      do
        ++v11;
      while ( pwszFQDN[v11] );
      v12 = v11 + 6;
      v13 = (wchar_t *)HeapAlloc(g_hHeap, 0, 2 * v12);
      *pPrincName = v13;
      if ( v13 )
      {
        StringCchCopyW(v13, v12, L"host/");
        StringCchCatW(*pPrincName, v12, v10);
        v7 = 1;
        goto LABEL_32;
      }
    }
    else
    {
      v12 = lDomainLen + 1 + lNameLen;
      v14 = (wchar_t *)HeapAlloc(g_hHeap, 0, 2 * v12);
      v15 = 2LL * lNameLen;
      *pPrincName = v14;
      v16 = v14;
      v17 = v15 + 15;
      if ( v15 + 15 < v15 )
        v17 = 0xFFFFFFFFFFFFFF0LL;
      v18 = alloca(v17 & 0xFFFFFFFFFFFFFFF0uLL);
      p_lNameLen = &lNameLen;
      if ( v16 && &lNameLen )
      {
        if ( LookupAccountSidLocalW(v6, (LPWSTR)&lNameLen, &lNameLen, v16, &lDomainLen, &sIgnore) )
          goto LABEL_32;
        HeapFree(g_hHeap, 0, *pPrincName);
        v12 = lNameLen + 1 + lDomainLen;
        v19 = (wchar_t *)HeapAlloc(g_hHeap, 0, 2 * v12);
        v20 = 2LL * lNameLen;
        *pPrincName = v19;
        v21 = v20 + 15;
        if ( v20 + 15 < v20 )
          v21 = 0xFFFFFFFFFFFFFF0LL;
        v22 = alloca(v21 & 0xFFFFFFFFFFFFFFF0uLL);
        p_lNameLen = &lNameLen;
        if ( v19 && &lNameLen )
        {
          if ( !LookupAccountSidLocalW(v6, (LPWSTR)&lNameLen, &lNameLen, v19, &lDomainLen, &sIgnore) )
            FQDN = GetLastError() | 0x80070000;
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
            ComTraceMessageT<long>(
              "onecore\\com\\combase\\dcomrem\\security.cxx",
              "LookupPrincName",
              6426,
              ERRORS,
              L"%!HRESULT!",
              FQDN);
          goto LABEL_32;
        }
      }
    }
    FQDN = -2147024882;
LABEL_32:
    ResumeImpersonate(hThread);
    if ( FQDN )
    {
      HeapFree(g_hHeap, 0, *pPrincName);
      *pPrincName = 0;
    }
    else if ( !v7 )
    {
      StringCchCatW(*pPrincName, v12, L"\\");
      return StringCchCatW(*pPrincName, v12, (const wchar_t *)p_lNameLen);
    }
    return FQDN;
  }
  return result;
}

```

## disassembly

```asm
0x18012498c  push    rbp
0x18012498e  push    rbx
0x18012498f  push    rsi
0x180124990  push    rdi
0x180124991  push    r12
0x180124993  push    r13
0x180124995  push    r14
0x180124997  push    r15
0x180124999  sub     rsp, 68h
0x18012499d  lea     rbp, [rsp+30h]
0x1801249a2  mov     rax, cs:__security_cookie
0x1801249a9  xor     rax, rbp
0x1801249ac  mov     [rbp+70h+var_50], rax
0x1801249b0  xor     r13d, r13d
0x1801249b3  mov     eax, 50h ; 'P'
0x1801249b8  mov     [pPrincName], r13
0x1801249bb  mov     rdi, pPrincName
0x1801249be  lea     pPrincName, [rbp+70h+pwszFQDN]; ppSelfSid
0x1801249c2  mov     [rbp+70h+lNameLen], eax
0x1801249c5  movzx   esi, wAuthnSvc
0x1801249c8  mov     [rbp+70h+lDomainLen], eax
0x1801249cb  mov     [rbp+70h+sIgnore], r13d
0x1801249cf  mov     [rbp+70h+hThread], r13
0x1801249d3  mov     [rbp+70h+pwszFQDN], r13
0x1801249d7  call    ?GetSelfSid@ProcessToken@@QEAAJPEAPEAX@Z; ProcessToken::GetSelfSid(void * *)
0x1801249dc  test    eax, eax
0x1801249de  js      loc_180124CD4
0x1801249e4  lea     rcx, [rbp+70h+hThread]; pHandle
0x1801249e8  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x1801249ed  mov     ebx, eax
0x1801249ef  test    eax, eax
0x1801249f1  jns     short loc_180124A48
0x1801249f3  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x1801249f9  test    ecx, ecx
0x1801249fb  jnz     short loc_180124A17
0x1801249fd  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180124a04  jz      loc_180124CD2
0x180124a0a  call    IsWppLevelEnabled
0x180124a0f  test    al, al
0x180124a11  jz      loc_180124CD2
0x180124a17  lea     rax, aHresult; "%!HRESULT!"
0x180124a1e  mov     [rsp+0A0h+var_78], ebx; <args_0>
0x180124a22  xor     r9d, r9d; level
0x180124a25  mov     [rsp+0A0h+format], rax; format
0x180124a2a  mov     r8d, 18E1h; line
0x180124a30  lea     pPrincName, aLookupprincnam; "LookupPrincName"
0x180124a37  lea     rcx, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x180124a3e  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180124a43  jmp     loc_180124CD2
0x180124a48  mov     r15, [rbp+70h+pwszFQDN]
0x180124a4c  mov     r12d, r13d
0x180124a4f  cmp     si, 0Ah
0x180124a53  jz      loc_180124AFF
0x180124a59  mov     pPrincName, r15; pSid2
0x180124a5c  lea     rcx, LOCAL_SYSTEM_SID; pSid1
0x180124a63  call    cs:__imp_EqualSid
0x180124a69  test    eax, eax
0x180124a6b  jnz     short loc_180124A81
0x180124a6d  mov     pPrincName, r15; pSid2
0x180124a70  lea     rcx, NETWORKSERVICE_SID; pSid1
0x180124a77  call    cs:__imp_EqualSid
0x180124a7d  test    eax, eax
0x180124a7f  jz      short loc_180124AFF
0x180124a81  lea     pPrincName, [rbp+70h+pwszFQDN]; ppwszFQDN
0x180124a85  mov     [rbp+70h+pwszFQDN], r13
0x180124a89  mov     rsi, r13
0x180124a8c  call    ?GetFQDN@CRpcResolver@@QEAAJPEAPEAG@Z; CRpcResolver::GetFQDN(ushort * *)
0x180124a91  mov     ebx, eax
0x180124a93  test    eax, eax
0x180124a95  js      short loc_180124AF7
0x180124a97  mov     r15, [rbp+70h+pwszFQDN]
0x180124a9b  or      r14, 0FFFFFFFFFFFFFFFFh
0x180124a9f  inc     r14
0x180124aa2  cmp     [r15+r14*2], r13w
0x180124aa7  jnz     short loc_180124A9F
0x180124aa9  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180124ab0  add     r14, 6
0x180124ab4  xor     edx, edx; dwFlags
0x180124ab6  lea     r8, [r14+r14]; dwBytes
0x180124aba  call    cs:__imp_HeapAlloc
0x180124ac0  mov     [rdi], rax
0x180124ac3  test    rax, rax
0x180124ac6  jz      loc_180124C82
0x180124acc  lea     r8, aHost; "host/"
0x180124ad3  mov     pPrincName, r14; cchDest
0x180124ad6  mov     rcx, rax; pszDest
0x180124ad9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180124ade  mov     rcx, [rdi]; pszDest
0x180124ae1  mov     r8, r15; pszSrc
0x180124ae4  mov     pPrincName, r14; cchDest
0x180124ae7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180124aec  mov     r12d, 1
0x180124af2  jmp     loc_180124C87
0x180124af7  mov     r14, r13
0x180124afa  jmp     loc_180124C87
0x180124aff  mov     ecx, [rbp+70h+lNameLen]
0x180124b02  xor     edx, edx; dwFlags
0x180124b04  mov     eax, [rbp+70h+lDomainLen]
0x180124b07  inc     eax
0x180124b09  add     ecx, eax
0x180124b0b  mov     r14d, ecx
0x180124b0e  lea     r8, [rcx+rcx]; dwBytes
0x180124b12  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180124b19  call    cs:__imp_HeapAlloc
0x180124b1f  mov     ecx, [rbp+70h+lNameLen]
0x180124b22  mov     pPrincName, 0FFFFFFFFFFFFFF0h
0x180124b2c  add     rcx, rcx
0x180124b2f  mov     [rdi], rax
0x180124b32  mov     r9, rax
0x180124b35  lea     rax, [rcx+0Fh]
0x180124b39  cmp     rax, rcx
0x180124b3c  ja      short loc_180124B41
0x180124b3e  mov     rax, pPrincName
0x180124b41  and     rax, 0FFFFFFFFFFFFFFF0h
0x180124b45  call    _alloca_probe
0x180124b4a  sub     rsp, rax
0x180124b4d  lea     rsi, [rsp+0A0h+lNameLen]
0x180124b52  test    r9, r9
0x180124b55  jz      loc_180124C82
0x180124b5b  test    rsi, rsi
0x180124b5e  jz      loc_180124C82
0x180124b64  lea     rax, [rbp+70h+sIgnore]
0x180124b68  mov     pPrincName, rsi; Name
0x180124b6b  mov     qword ptr [rsp+0A0h+var_78], rax; peUse
0x180124b70  lea     r8, [rbp+70h+lNameLen]; cchName
0x180124b74  lea     rax, [rbp+70h+lDomainLen]
0x180124b78  mov     rcx, r15; Sid
0x180124b7b  mov     [rsp+0A0h+format], rax; cchReferencedDomainName
0x180124b80  call    cs:__imp_LookupAccountSidLocalW
0x180124b86  test    eax, eax
0x180124b88  jnz     loc_180124C87
0x180124b8e  mov     r8, [rdi]; lpMem
0x180124b91  xor     edx, edx; dwFlags
0x180124b93  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180124b9a  call    cs:__imp_HeapFree
0x180124ba0  mov     ecx, [rbp+70h+lDomainLen]
0x180124ba3  xor     edx, edx; dwFlags
0x180124ba5  mov     eax, [rbp+70h+lNameLen]
0x180124ba8  inc     eax
0x180124baa  add     ecx, eax
0x180124bac  mov     r14d, ecx
0x180124baf  lea     r8, [rcx+rcx]; dwBytes
0x180124bb3  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180124bba  call    cs:__imp_HeapAlloc
0x180124bc0  mov     ecx, [rbp+70h+lNameLen]
0x180124bc3  mov     r9, rax
0x180124bc6  add     rcx, rcx
0x180124bc9  mov     [rdi], rax
0x180124bcc  lea     rax, [rcx+0Fh]
0x180124bd0  cmp     rax, rcx
0x180124bd3  ja      short loc_180124BDF
0x180124bd5  mov     rax, 0FFFFFFFFFFFFFF0h
0x180124bdf  and     rax, 0FFFFFFFFFFFFFFF0h
0x180124be3  call    _alloca_probe
0x180124be8  sub     rsp, rax
0x180124beb  lea     rsi, [rsp+0A0h+lNameLen]
0x180124bf0  test    r9, r9
0x180124bf3  jz      loc_180124C82
0x180124bf9  test    rsi, rsi
0x180124bfc  jz      loc_180124C82
0x180124c02  lea     rax, [rbp+70h+sIgnore]
0x180124c06  mov     pPrincName, rsi; Name
0x180124c09  mov     qword ptr [rsp+0A0h+var_78], rax; peUse
0x180124c0e  lea     r8, [rbp+70h+lNameLen]; cchName
0x180124c12  lea     rax, [rbp+70h+lDomainLen]
0x180124c16  mov     rcx, r15; Sid
0x180124c19  mov     [rsp+0A0h+format], rax; cchReferencedDomainName
0x180124c1e  call    cs:__imp_LookupAccountSidLocalW
0x180124c24  test    eax, eax
0x180124c26  jnz     short loc_180124C36
0x180124c28  call    cs:__imp_GetLastError
0x180124c2e  mov     ebx, eax
0x180124c30  or      ebx, 80070000h
0x180124c36  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180124c3c  test    eax, eax
0x180124c3e  jnz     short loc_180124C54
0x180124c40  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180124c47  jz      short loc_180124C87
0x180124c49  xor     ecx, ecx; level
0x180124c4b  call    IsWppLevelEnabled
0x180124c50  test    al, al
0x180124c52  jz      short loc_180124C87
0x180124c54  lea     rax, aHresult; "%!HRESULT!"
0x180124c5b  mov     [rsp+0A0h+var_78], ebx; <args_0>
0x180124c5f  xor     r9d, r9d; level
0x180124c62  mov     [rsp+0A0h+format], rax; format
0x180124c67  mov     r8d, 191Ah; line
0x180124c6d  lea     pPrincName, aLookupprincnam; "LookupPrincName"
0x180124c74  lea     rcx, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x180124c7b  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180124c80  jmp     short loc_180124C87
0x180124c82  mov     ebx, 8007000Eh
0x180124c87  mov     rcx, [rbp+70h+hThread]; hToken
0x180124c8b  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180124c90  test    ebx, ebx
0x180124c92  jz      short loc_180124CAB
0x180124c94  mov     r8, [rdi]; lpMem
0x180124c97  xor     edx, edx; dwFlags
0x180124c99  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180124ca0  call    cs:__imp_HeapFree
0x180124ca6  mov     [rdi], r13
0x180124ca9  jmp     short loc_180124CD2
0x180124cab  test    r12d, r12d
0x180124cae  jnz     short loc_180124CD2
0x180124cb0  mov     rcx, [rdi]; pszDest
0x180124cb3  lea     r8, asc_1802AFED8; "\\"
0x180124cba  mov     pPrincName, r14; cchDest
0x180124cbd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180124cc2  mov     rcx, [rdi]; pszDest
0x180124cc5  mov     r8, rsi; pszSrc
0x180124cc8  mov     pPrincName, r14; cchDest
0x180124ccb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180124cd0  mov     ebx, eax
0x180124cd2  mov     eax, ebx
0x180124cd4  mov     rcx, [rbp+70h+var_50]
0x180124cd8  xor     rcx, rbp; StackCookie
0x180124cdb  call    __security_check_cookie
0x180124ce0  lea     rsp, [rbp+38h]
0x180124ce4  pop     r15
0x180124ce6  pop     r14
0x180124ce8  pop     r13
0x180124cea  pop     r12
0x180124cec  pop     rdi
0x180124ced  pop     rsi
0x180124cee  pop     rbx
0x180124cef  pop     rbp
0x180124cf0  retn
```
