# DnsServiceBrowse

- ea: `0x180054360`
- end: `0x180054644`
- name: `DnsServiceBrowse`
- size: `740`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012510`
- `0x18002a160`
- `0x180054144`
- `0x180054360`
- `0x18005464c`
- `0x180054684`
- `0x1800547c4`
- `0x1800550d4`
- `0x18008b1a0`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800dbc44`
- `0x1800dc9e0`
- `0x1800dfdc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800545b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800545b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005459c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005459c`

## pseudocode

```c
__int64 __fastcall DnsServiceBrowse(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  DWORD LastError; // ebx
  __int64 v6; // r9
  void *v7; // rax
  void *v8; // r15
  __int64 v9; // r14
  __int64 StringCopy_W; // rax
  int v11; // ecx
  HANDLE EventW; // rax
  __int64 v14; // [rsp+30h] [rbp-69h] BYREF
  int v15; // [rsp+40h] [rbp-59h] BYREF
  __int64 v16; // [rsp+48h] [rbp-51h]
  __int16 v17; // [rsp+50h] [rbp-49h]
  __int64 v18; // [rsp+58h] [rbp-41h]
  int v19; // [rsp+60h] [rbp-39h]
  void (__fastcall *v20)(void *, struct _MDNS_QUERY_HANDLE *, struct _DNS_QUERY_RESULT *); // [rsp+68h] [rbp-31h]
  __int64 v21; // [rsp+70h] [rbp-29h]
  _DNS_QUERY_REQUEST pQueryRequest; // [rsp+80h] [rbp-19h] BYREF

  memset_0(&pQueryRequest, 0, sizeof(pQueryRequest));
  v4 = 0;
  v14 = 0;
  memset_0(&v15, 0, 0x40u);
  LastError = 14;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qq(1035, 14, (unsigned int)WPP_5d3becedec4b303253ed7989a2efa646_Traceguids, a1, a2);
  if ( !a2 )
    goto LABEL_20;
  if ( !a1 )
    goto LABEL_20;
  if ( (unsigned int)(*(_DWORD *)a1 - 1) > 1 )
    goto LABEL_20;
  if ( !*(_QWORD *)(a1 + 16) )
    goto LABEL_20;
  v6 = *(_QWORD *)(a1 + 8);
  if ( !v6 )
    goto LABEL_20;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_SDD(
      1035,
      15,
      (unsigned int)WPP_5d3becedec4b303253ed7989a2efa646_Traceguids,
      v6,
      *(_DWORD *)a1,
      *(_DWORD *)(a1 + 4));
  if ( !(unsigned int)IsServiceNameLocal(*(STRSAFE_LPCWSTR *)(a1 + 8), 1) )
  {
    if ( *(_DWORD *)a1 == 1 )
    {
      LastError = BrowseContext::CreateInstance(0, a1, a2, &v14);
      if ( LastError )
      {
        v4 = v14;
      }
      else
      {
        EventW = CreateEventW(0, 0, 0, 0);
        v4 = v14;
        *(_QWORD *)(v14 + 720) = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
LABEL_16:
          CallbackContext::deref((CallbackContext *)v4);
          goto LABEL_17;
        }
        pQueryRequest.QueryName = *(PCWSTR *)(a1 + 8);
        pQueryRequest.InterfaceIndex = *(_DWORD *)(a1 + 4);
        pQueryRequest.pQueryCompletionCallback = (PDNS_QUERY_COMPLETION_ROUTINE)CallbackContext::StaticCallback;
        pQueryRequest.QueryType = 12;
        pQueryRequest.Version = 1;
        pQueryRequest.QueryOptions = 0;
        pQueryRequest.pQueryContext = (PVOID)v4;
        LastError = DnsQueryEx(&pQueryRequest, (PDNS_QUERY_RESULT)(v4 + 88), (PDNS_QUERY_CANCEL)(v4 + 136));
        if ( LastError == 9506 )
          goto LABEL_17;
      }
LABEL_15:
      if ( !v4 )
        goto LABEL_17;
      goto LABEL_16;
    }
LABEL_20:
    LastError = 87;
    goto LABEL_17;
  }
  v7 = operator new(0x2E0u);
  v8 = v7;
  if ( !v7 )
    goto LABEL_15;
  memset_0(v7, 0, 0x2E0u);
  v9 = BrowseContext::BrowseContext(v8, 1, a1, a2);
  if ( !v9 )
    goto LABEL_15;
  StringCopy_W = Dns_CreateStringCopy_W(*(void **)(a1 + 8));
  *(_QWORD *)(v9 + 120) = StringCopy_W;
  if ( !StringCopy_W )
  {
    CallbackContext::deref((CallbackContext *)v9);
    goto LABEL_15;
  }
  v11 = *(_DWORD *)(a1 + 4);
  v16 = *(_QWORD *)(a1 + 8);
  v4 = v9;
  v19 = v11;
  v17 = 12;
  v21 = v9;
  v20 = CallbackContext::McastStaticCallback;
  v18 = 0x20000000;
  v15 = 1;
  LastError = DnsStartMulticastQueryImpl((struct _MDNS_QUERY_REQUEST *)&v15, (struct _MDNS_QUERY_HANDLE *)(v9 + 176));
  if ( LastError )
    goto LABEL_15;
  LastError = 9506;
LABEL_17:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 16, WPP_5d3becedec4b303253ed7989a2efa646_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180054360  mov     [rsp-8+arg_10], rbx
0x180054365  push    rbp
0x180054366  push    rsi
0x180054367  push    rdi
0x180054368  push    r14
0x18005436a  push    r15
0x18005436c  lea     rbp, [rsp-37h]
0x180054371  sub     rsp, 0D0h
0x180054378  mov     rax, cs:__security_cookie
0x18005437f  xor     rax, rsp
0x180054382  mov     [rbp+57h+var_30], rax
0x180054386  mov     r14, rdx
0x180054389  mov     rdi, rcx
0x18005438c  mov     ebx, 40h ; '@'
0x180054391  lea     rcx, [rbp+57h+pQueryRequest]; void *
0x180054395  mov     r8d, ebx; Size
0x180054398  xor     edx, edx; Val
0x18005439a  call    memset_0
0x18005439f  xor     esi, esi
0x1800543a1  lea     rcx, [rbp+57h+var_B0]; void *
0x1800543a5  mov     r8d, ebx; Size
0x1800543a8  mov     [rbp+57h+var_C0], rsi
0x1800543ac  xor     edx, edx; Val
0x1800543ae  call    memset_0
0x1800543b3  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800543ba  lea     ebx, [rsi+0Eh]
0x1800543bd  jnz     loc_180054534
0x1800543c3  test    r14, r14
0x1800543c6  jz      loc_18005450B
0x1800543cc  test    rdi, rdi
0x1800543cf  jz      loc_18005450B
0x1800543d5  mov     r8d, [rdi]
0x1800543d8  lea     eax, [r8-1]
0x1800543dc  cmp     eax, 1
0x1800543df  ja      loc_18005450B
0x1800543e5  cmp     [rdi+10h], rsi
0x1800543e9  jz      loc_18005450B
0x1800543ef  mov     r9, [rdi+8]
0x1800543f3  test    r9, r9
0x1800543f6  jz      loc_18005450B
0x1800543fc  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180054403  jnz     loc_180054554
0x180054409  mov     rcx, [rdi+8]; pszSrc
0x18005440d  mov     edx, 1; int
0x180054412  call    ?IsServiceNameLocal@@YAHPEBGH@Z; IsServiceNameLocal(ushort const *,int)
0x180054417  test    eax, eax
0x180054419  jz      loc_180054512
0x18005441f  mov     ecx, 2E0h; Size
0x180054424  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054429  mov     r15, rax
0x18005442c  test    rax, rax
0x18005442f  jz      loc_1800544CB
0x180054435  xor     edx, edx; Val
0x180054437  mov     r8d, 2E0h; Size
0x18005443d  mov     rcx, rax; void *
0x180054440  call    memset_0
0x180054445  mov     r9, r14
0x180054448  mov     r8, rdi
0x18005444b  mov     edx, 1
0x180054450  mov     rcx, r15
0x180054453  call    ??0BrowseContext@@AEAA@W4QueryType@CallbackContext@@PEAU_DNS_SERVICE_BROWSE_REQUEST@@PEAU_DNS_SERVICE_CANCEL@@@Z; BrowseContext::BrowseContext(CallbackContext::QueryType,_DNS_SERVICE_BROWSE_REQUEST *,_DNS_SERVICE_CANCEL *)
0x180054458  mov     r14, rax
0x18005445b  test    rax, rax
0x18005445e  jz      short loc_1800544CB
0x180054460  mov     rcx, [rdi+8]; Src
0x180054464  call    Dns_CreateStringCopy_W
0x180054469  mov     [r14+78h], rax
0x18005446d  test    rax, rax
0x180054470  jz      loc_180054585
0x180054476  mov     rax, [rdi+8]
0x18005447a  lea     rdx, [r14+0B0h]; struct _MDNS_QUERY_HANDLE *
0x180054481  mov     ecx, [rdi+4]
0x180054484  xor     r8d, r8d
0x180054487  mov     [rbp+57h+var_A8], rax
0x18005448b  mov     rsi, r14
0x18005448e  mov     eax, 0Ch
0x180054493  mov     [rbp+57h+var_90], ecx
0x180054496  mov     [rbp+57h+var_A0], ax
0x18005449a  lea     rcx, [rbp+57h+var_B0]; struct _MDNS_QUERY_REQUEST *
0x18005449e  lea     rax, ?McastStaticCallback@CallbackContext@@SAXPEAXPEAU_MDNS_QUERY_HANDLE@@PEAU_DNS_QUERY_RESULT@@@Z; CallbackContext::McastStaticCallback(void *,_MDNS_QUERY_HANDLE *,_DNS_QUERY_RESULT *)
0x1800544a5  mov     [rbp+57h+var_80], r14
0x1800544a9  mov     [rbp+57h+var_88], rax
0x1800544ad  mov     [rbp+57h+var_98], 20000000h
0x1800544b5  mov     [rbp+57h+var_B0], 1
0x1800544bc  call    DnsStartMulticastQueryImpl
0x1800544c1  mov     ebx, eax
0x1800544c3  test    eax, eax
0x1800544c5  jz      loc_18005457B
0x1800544cb  test    rsi, rsi
0x1800544ce  jz      short loc_1800544D8
0x1800544d0  mov     rcx, rsi; this
0x1800544d3  call    ?deref@CallbackContext@@QEAAKXZ; CallbackContext::deref(void)
0x1800544d8  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800544df  jnz     loc_180054626
0x1800544e5  mov     eax, ebx
0x1800544e7  mov     rcx, [rbp+57h+var_30]
0x1800544eb  xor     rcx, rsp; StackCookie
0x1800544ee  call    __security_check_cookie
0x1800544f3  mov     rbx, [rsp+0F0h+arg_10]
0x1800544fb  add     rsp, 0D0h
0x180054502  pop     r15
0x180054504  pop     r14
0x180054506  pop     rdi
0x180054507  pop     rsi
0x180054508  pop     rbp
0x180054509  retn
0x18005450b  mov     ebx, 57h ; 'W'
0x180054510  jmp     short loc_1800544D8
0x180054512  cmp     dword ptr [rdi], 1
0x180054515  jnz     short loc_18005450B
0x180054517  lea     r9, [rbp+57h+var_C0]
0x18005451b  mov     r8, r14
0x18005451e  mov     rdx, rdi
0x180054521  xor     ecx, ecx
0x180054523  call    ?CreateInstance@BrowseContext@@SAKW4QueryType@CallbackContext@@PEAU_DNS_SERVICE_BROWSE_REQUEST@@PEAU_DNS_SERVICE_CANCEL@@PEAPEAV1@@Z; BrowseContext::CreateInstance(CallbackContext::QueryType,_DNS_SERVICE_BROWSE_REQUEST *,_DNS_SERVICE_CANCEL *,BrowseContext * *)
0x180054528  mov     ebx, eax
0x18005452a  test    eax, eax
0x18005452c  jz      short loc_180054592
0x18005452e  mov     rsi, [rbp+57h+var_C0]
0x180054532  jmp     short loc_1800544CB
0x180054534  mov     edx, ebx
0x180054536  mov     [rsp+0F0h+var_D0], r14
0x18005453b  mov     ecx, 40Bh
0x180054540  lea     r8, WPP_5d3becedec4b303253ed7989a2efa646_Traceguids
0x180054547  mov     r9, rdi
0x18005454a  call    WPP_SF_qq
0x18005454f  jmp     loc_1800543C3
0x180054554  mov     eax, [rdi+4]
0x180054557  mov     edx, 0Fh
0x18005455c  mov     [rsp+0F0h+var_C8], eax
0x180054560  mov     ecx, 40Bh
0x180054565  mov     dword ptr [rsp+0F0h+var_D0], r8d
0x18005456a  lea     r8, WPP_5d3becedec4b303253ed7989a2efa646_Traceguids
0x180054571  call    WPP_SF_SDD
0x180054576  jmp     loc_180054409
0x18005457b  mov     ebx, 2522h
0x180054580  jmp     loc_1800544D8
0x180054585  mov     rcx, r14; this
0x180054588  call    ?deref@CallbackContext@@QEAAKXZ; CallbackContext::deref(void)
0x18005458d  jmp     loc_1800544CB
0x180054592  xor     r9d, r9d; lpName
0x180054595  xor     r8d, r8d; bInitialState
0x180054598  xor     edx, edx; bManualReset
0x18005459a  xor     ecx, ecx; lpEventAttributes
0x18005459c  call    cs:__imp_CreateEventW
0x1800545a3  nop     dword ptr [rax+rax+00h]
0x1800545a8  mov     rsi, [rbp+57h+var_C0]
0x1800545ac  mov     [rsi+2D0h], rax
0x1800545b3  test    rax, rax
0x1800545b6  jnz     short loc_1800545CB
0x1800545b8  call    cs:__imp_GetLastError
0x1800545bf  nop     dword ptr [rax+rax+00h]
0x1800545c4  mov     ebx, eax
0x1800545c6  jmp     loc_1800544D0
0x1800545cb  mov     rax, [rdi+8]
0x1800545cf  lea     r8, [rsi+88h]; pCancelHandle
0x1800545d6  mov     [rbp+57h+pQueryRequest.QueryName], rax
0x1800545da  lea     rdx, [rsi+58h]; pQueryResults
0x1800545de  mov     eax, [rdi+4]
0x1800545e1  lea     rcx, [rbp+57h+pQueryRequest]; pQueryRequest
0x1800545e5  mov     [rbp+57h+pQueryRequest.InterfaceIndex], eax
0x1800545e8  lea     rax, ?StaticCallback@CallbackContext@@SAXPEAXPEAU_DNS_QUERY_RESULT@@@Z; CallbackContext::StaticCallback(void *,_DNS_QUERY_RESULT *)
0x1800545ef  mov     [rbp+57h+pQueryRequest.pQueryCompletionCallback], rax
0x1800545f3  mov     eax, 0Ch
0x1800545f8  mov     [rbp+57h+pQueryRequest.QueryType], ax
0x1800545fc  mov     [rbp+57h+pQueryRequest.Version], 1
0x180054603  mov     [rbp+57h+pQueryRequest.QueryOptions], 0
0x18005460b  mov     [rbp+57h+pQueryRequest.pQueryContext], rsi
0x18005460f  call    DnsQueryEx
0x180054614  mov     ebx, eax
0x180054616  cmp     eax, 2522h
0x18005461b  jz      loc_1800544D8
0x180054621  jmp     loc_1800544CB
0x180054626  mov     edx, 10h
0x18005462b  lea     r8, WPP_5d3becedec4b303253ed7989a2efa646_Traceguids
0x180054632  mov     ecx, 40Bh
0x180054637  mov     r9d, ebx
0x18005463a  call    WPP_SF_d
0x18005463f  jmp     loc_1800544E5
```
