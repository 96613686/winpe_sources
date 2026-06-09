# FilterIPAddressList(ushort *,sockaddr_storage *)

- ea: `0x1800149bc`
- end: `0x180014c1e`
- name: `?FilterIPAddressList@@YAJPEAGPEAUsockaddr_storage@@@Z`
- size: `610`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct sockaddr_storage *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f7c8`

## callees

- `0x180012358`
- `0x180012380`
- `0x180014660`
- `0x1800149bc`
- `0x180015e18`
- `0x180015f1c`
- `0x18001a5a2`
- `0x18001a5e0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180014b76`
- `msvcrt!memcpy_s` at `0x180014b76`
- `WS2_32!FreeAddrInfoW` at `0x180014b84`
- `WS2_32!FreeAddrInfoW` at `0x180014b84`
- `WS2_32!GetAddrInfoW` at `0x180014ad4`
- `WS2_32!GetAddrInfoW` at `0x180014ad4`
- `WS2_32!__imp_WSAStartup` at `0x180014a3d`
- `WS2_32!__imp_WSAStartup` at `0x180014a3d`
- `WS2_32!__imp_WSACleanup` at `0x180014be5`
- `WS2_32!__imp_WSACleanup` at `0x180014be5`
- `KERNEL32!GetLastError` at `0x180014ade`
- `KERNEL32!GetLastError` at `0x180014ade`

## string_xrefs

- `0x180014a69`: `base\diagnosis\ra\racommon\src\fileutils.cpp`
- `0x180014bc4`: `base\diagnosis\ra\racommon\src\fileutils.cpp`

## pseudocode

```c
__int64 __fastcall FilterIPAddressList(unsigned __int16 *a1, struct sockaddr_storage *a2)
{
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  CEventLogger *v5; // rcx
  int v6; // r14d
  int v7; // ebx
  signed int v8; // eax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  int v11; // eax
  int v12; // edi
  int i; // esi
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  struct addrinfoW *v17; // r9
  struct sockaddr *ai_addr; // r8
  BOOLEAN v19; // al
  const void *v20; // r8
  int v21; // r10d
  int v22; // ecx
  rsize_t v23; // r9
  struct sockaddr *v24; // r8
  BOOLEAN v25; // al
  int v26; // r10d
  PADDRINFOW ppResult; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v29; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+40h] [rbp-C0h]
  __int128 v31; // [rsp+48h] [rbp-B8h]
  struct WSAData WSAData; // [rsp+60h] [rbp-A0h] BYREF

  v29 = 0;
  v30 = 0;
  v31 = 0;
  ppResult = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  memset_0(a2, 0, sizeof(struct sockaddr_storage));
  if ( WSAStartup(0x202u, &WSAData) )
  {
    v6 = 0;
    v7 = -2147467259;
    CEventLogger::LogError(
      v5,
      v4,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0x3D6u,
      L"FilterIPAddressList",
      0x80004005);
    goto LABEL_33;
  }
  v6 = 1;
  v8 = CRATicketInfo::InitializeTicket(&v29, a1);
  v7 = v8;
  if ( v8 < 0 )
  {
    CEventLogger::LogError(
      v10,
      v9,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0x3DBu,
      L"FilterIPAddressList",
      v8);
    goto LABEL_33;
  }
  v11 = v30;
  if ( v30 <= 0 )
  {
    CEventLogger::LogError(
      v10,
      v9,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0x3DDu,
      L"FilterIPAddressList",
      0);
    goto LABEL_32;
  }
  v12 = 0;
  for ( i = 0; i < v11; ++i )
  {
    if ( GetAddrInfoW(*(PCWSTR *)(v31 + 8LL * i), *(PCWSTR *)(*((_QWORD *)&v31 + 1) + 8LL * i), 0, &ppResult) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 < 0 )
      {
        CEventLogger::LogError(
          v16,
          v15,
          L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
          0x3E9u,
          L"FilterIPAddressList",
          v7);
        goto LABEL_33;
      }
    }
    v17 = ppResult;
    if ( ppResult )
    {
      if ( ppResult->ai_family == 2 )
      {
        ai_addr = ppResult->ai_addr;
        if ( ai_addr )
        {
          v19 = IN4_IS_ADDR_RFC1918((const IN_ADDR *)&ai_addr->sa_data[2]);
          v22 = 1;
          if ( v19 != 1 )
            v22 = v21 + 1;
          if ( v22 > v12 )
          {
            v23 = (unsigned int)(v21 + 14);
            goto LABEL_25;
          }
        }
      }
      else if ( ppResult->ai_family == 23 )
      {
        v24 = ppResult->ai_addr;
        if ( v24 )
        {
          v25 = IN6_IS_ADDR_TEREDO((const IN6_ADDR *)&v24->sa_data[6]);
          v22 = 4;
          if ( v25 != 1 )
            v22 = v26;
          if ( v22 > v12 )
          {
            v23 = 28;
LABEL_25:
            v12 = v22;
            memcpy_s(a2, 0x80u, v20, v23);
            v17 = ppResult;
          }
        }
      }
      FreeAddrInfoW(v17);
    }
    v11 = v30;
  }
  if ( !v12 )
LABEL_32:
    v7 = -2147467259;
LABEL_33:
  CRATicketInfo::Cleanup((CRATicketInfo *)&v29);
  if ( v6 == 1 )
    WSACleanup();
  CRATicketInfo::Cleanup((CRATicketInfo *)&v29);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800149bc  mov     [rsp-8+arg_10], rbx
0x1800149c1  push    rbp
0x1800149c2  push    rsi
0x1800149c3  push    rdi
0x1800149c4  push    r14
0x1800149c6  push    r15
0x1800149c8  lea     rbp, [rsp-110h]
0x1800149d0  sub     rsp, 210h
0x1800149d7  mov     rax, cs:__security_cookie
0x1800149de  xor     rax, rsp
0x1800149e1  mov     [rbp+130h+var_30], rax
0x1800149e8  mov     r15, rdx
0x1800149eb  mov     rbx, rcx
0x1800149ee  mov     [rsp+230h+var_1F8], 0
0x1800149f7  mov     [rsp+230h+var_1F0], 0
0x1800149ff  xorps   xmm0, xmm0
0x180014a02  movdqu  [rsp+230h+var_1E8], xmm0
0x180014a08  mov     [rsp+230h+ppResult], 0
0x180014a11  xor     edx, edx; Val
0x180014a13  mov     r8d, 198h; Size
0x180014a19  lea     rcx, [rsp+230h+WSAData]; void *
0x180014a1e  call    memset_0
0x180014a23  xor     edx, edx; Val
0x180014a25  mov     r8d, 80h; Size
0x180014a2b  mov     rcx, r15; void *
0x180014a2e  call    memset_0
0x180014a33  mov     ecx, 202h; wVersionRequested
0x180014a38  lea     rdx, [rsp+230h+WSAData]; lpWSAData
0x180014a3d  call    cs:__imp_WSAStartup
0x180014a43  test    eax, eax
0x180014a45  jz      short loc_180014A7A
0x180014a47  xor     r14d, r14d
0x180014a4a  mov     ebx, 80004005h
0x180014a4f  mov     [rsp+230h+var_208], 80004005h; unsigned int
0x180014a57  mov     r9d, 3D6h; unsigned int
0x180014a5d  lea     rax, aFilteripaddres; "FilterIPAddressList"
0x180014a64  mov     [rsp+230h+var_210], rax; unsigned __int16 *
0x180014a69  lea     r8, aBaseDiagnosisR_4; "base\\diagnosis\\ra\\racommon\\src\\fil"...
0x180014a70  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180014a75  jmp     loc_180014BD5
0x180014a7a  mov     r14d, 1
0x180014a80  mov     rdx, rbx; unsigned __int16 *
0x180014a83  lea     rcx, [rsp+230h+var_1F8]; this
0x180014a88  call    ?InitializeTicket@CRATicketInfo@@QEAAJPEAG@Z; CRATicketInfo::InitializeTicket(ushort *)
0x180014a8d  mov     ebx, eax
0x180014a8f  test    eax, eax
0x180014a91  jns     short loc_180014A9F
0x180014a93  mov     [rsp+230h+var_208], eax
0x180014a97  mov     r9d, 3DBh
0x180014a9d  jmp     short loc_180014A5D
0x180014a9f  mov     eax, [rsp+230h+var_1F0]
0x180014aa3  test    eax, eax
0x180014aa5  jle     loc_180014BAA
0x180014aab  xor     edi, edi
0x180014aad  xor     esi, esi
0x180014aaf  cmp     esi, eax
0x180014ab1  jge     loc_180014BA4
0x180014ab7  movsxd  rax, esi
0x180014aba  lea     r9, [rsp+230h+ppResult]; ppResult
0x180014abf  xor     r8d, r8d; pHints
0x180014ac2  mov     rdx, qword ptr [rsp+230h+var_1E8+8]
0x180014ac7  mov     rdx, [rdx+rax*8]; pServiceName
0x180014acb  mov     rcx, qword ptr [rsp+230h+var_1E8]
0x180014ad0  mov     rcx, [rcx+rax*8]; pNodeName
0x180014ad4  call    cs:__imp_GetAddrInfoW
0x180014ada  test    eax, eax
0x180014adc  jz      short loc_180014AFB
0x180014ade  call    cs:__imp_GetLastError
0x180014ae4  mov     ebx, eax
0x180014ae6  test    eax, eax
0x180014ae8  jle     short loc_180014AF3
0x180014aea  movzx   ebx, ax
0x180014aed  or      ebx, 80070000h
0x180014af3  test    ebx, ebx
0x180014af5  js      loc_180014B95
0x180014afb  mov     r9, [rsp+230h+ppResult]
0x180014b00  test    r9, r9
0x180014b03  jz      loc_180014B8A
0x180014b09  mov     r10d, 2
0x180014b0f  cmp     [r9+4], r10d
0x180014b13  jnz     short loc_180014B3D
0x180014b15  mov     r8, [r9+20h]
0x180014b19  test    r8, r8
0x180014b1c  jz      short loc_180014B81
0x180014b1e  lea     rcx, [r8+4]; a
0x180014b22  call    IN4_IS_ADDR_RFC1918
0x180014b27  mov     ecx, r14d
0x180014b2a  lea     edx, [r10+1]
0x180014b2e  cmp     al, cl
0x180014b30  cmovnz  ecx, edx
0x180014b33  cmp     ecx, edi
0x180014b35  jle     short loc_180014B81
0x180014b37  lea     r9d, [r10+0Eh]
0x180014b3b  jmp     short loc_180014B6C
0x180014b3d  cmp     dword ptr [r9+4], 17h
0x180014b42  jnz     short loc_180014B81
0x180014b44  mov     r8, [r9+20h]
0x180014b48  test    r8, r8
0x180014b4b  jz      short loc_180014B81
0x180014b4d  lea     rcx, [r8+8]; a
0x180014b51  call    IN6_IS_ADDR_TEREDO
0x180014b56  mov     ecx, 4
0x180014b5b  cmp     al, r14b
0x180014b5e  cmovnz  ecx, r10d
0x180014b62  cmp     ecx, edi
0x180014b64  jle     short loc_180014B81
0x180014b66  mov     r9d, 1Ch; SourceSize
0x180014b6c  mov     edi, ecx
0x180014b6e  mov     edx, 80h; DestinationSize
0x180014b73  mov     rcx, r15; Destination
0x180014b76  call    cs:__imp_memcpy_s
0x180014b7c  mov     r9, [rsp+230h+ppResult]
0x180014b81  mov     rcx, r9; pAddrInfo
0x180014b84  call    cs:__imp_FreeAddrInfoW
0x180014b8a  inc     esi
0x180014b8c  mov     eax, [rsp+230h+var_1F0]
0x180014b90  jmp     loc_180014AAF
0x180014b95  mov     [rsp+230h+var_208], ebx
0x180014b99  mov     r9d, 3E9h
0x180014b9f  jmp     loc_180014A5D
0x180014ba4  test    edi, edi
0x180014ba6  jnz     short loc_180014BD5
0x180014ba8  jmp     short loc_180014BD0
0x180014baa  mov     [rsp+230h+var_208], 0; unsigned int
0x180014bb2  lea     rax, aFilteripaddres; "FilterIPAddressList"
0x180014bb9  mov     [rsp+230h+var_210], rax; unsigned __int16 *
0x180014bbe  mov     r9d, 3DDh; unsigned int
0x180014bc4  lea     r8, aBaseDiagnosisR_4; "base\\diagnosis\\ra\\racommon\\src\\fil"...
0x180014bcb  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180014bd0  mov     ebx, 80004005h
0x180014bd5  lea     rcx, [rsp+230h+var_1F8]; this
0x180014bda  call    ?Cleanup@CRATicketInfo@@QEAAJXZ; CRATicketInfo::Cleanup(void)
0x180014bdf  cmp     r14d, 1
0x180014be3  jnz     short loc_180014BEC
0x180014be5  call    cs:__imp_WSACleanup
0x180014beb  nop
0x180014bec  lea     rcx, [rsp+230h+var_1F8]; this
0x180014bf1  call    ?Cleanup@CRATicketInfo@@QEAAJXZ; CRATicketInfo::Cleanup(void)
0x180014bf6  mov     eax, ebx
0x180014bf8  mov     rcx, [rbp+130h+var_30]
0x180014bff  xor     rcx, rsp; StackCookie
0x180014c02  call    __security_check_cookie
0x180014c07  mov     rbx, [rsp+230h+arg_10]
0x180014c0f  add     rsp, 210h
0x180014c16  pop     r15
0x180014c18  pop     r14
0x180014c1a  pop     rdi
0x180014c1b  pop     rsi
0x180014c1c  pop     rbp
0x180014c1d  retn
```
