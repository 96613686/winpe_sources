# CheckForPublicAddresses(ushort *,int *,int *,in6_addr *)

- ea: `0x180010adc`
- end: `0x180010d67`
- name: `?CheckForPublicAddresses@@YAJPEAGPEAH1PEAUin6_addr@@@Z`
- size: `651`
- prototype: `__int64 __fastcall(unsigned __int16 *, int *, int *, struct in6_addr *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18000c998`
- `0x18000cb0c`

## callees

- `0x180010adc`
- `0x180012358`
- `0x180012380`
- `0x180014660`
- `0x180015e18`
- `0x180015f1c`
- `0x180016558`
- `0x18001a5a2`
- `0x18001a5e0`

## import_xrefs

- `WS2_32!FreeAddrInfoW` at `0x180010cd0`
- `WS2_32!FreeAddrInfoW` at `0x180010d1c`
- `WS2_32!FreeAddrInfoW` at `0x180010cd0`
- `WS2_32!FreeAddrInfoW` at `0x180010d1c`
- `WS2_32!GetAddrInfoW` at `0x180010c23`
- `WS2_32!GetAddrInfoW` at `0x180010c23`
- `WS2_32!__imp_WSAStartup` at `0x180010ba8`
- `WS2_32!__imp_WSAStartup` at `0x180010ba8`
- `WS2_32!__imp_WSACleanup` at `0x180010d31`
- `WS2_32!__imp_WSACleanup` at `0x180010d31`
- `KERNEL32!GetLastError` at `0x180010c2d`
- `KERNEL32!GetLastError` at `0x180010c2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CheckForPublicAddresses(unsigned __int16 *a1, int *a2, int *a3, struct in6_addr *a4)
{
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  int v10; // ebx
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  CEventLogger *v12; // rcx
  int v13; // r12d
  signed int v14; // eax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  int i; // esi
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  PADDRINFOW v21; // rdi
  int *v22; // r12
  const IN_ADDR *ai_addr; // rcx
  struct sockaddr *v24; // rax
  struct in6_addr *v25; // r15
  unsigned int v26; // ecx
  PADDRINFOW ppResult; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+48h] [rbp-B8h]
  __int128 v32; // [rsp+50h] [rbp-B0h]
  int *v33; // [rsp+60h] [rbp-A0h]
  WSAData WSAData; // [rsp+70h] [rbp-90h] BYREF

  v33 = a3;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  ppResult = 0;
  if ( a1 )
  {
    *a2 = 0;
    *a3 = 0;
    if ( a4 )
      *a4 = 0;
    if ( WSAStartup(0x202u, &WSAData) )
    {
      v13 = 0;
      v10 = -2147467259;
      CEventLogger::LogError(
        v12,
        v11,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0x5AFu,
        L"CheckForPublicAddresses",
        0x80004005);
    }
    else
    {
      v13 = 1;
      v29 = 1;
      v14 = CRATicketInfo::InitializeTicket(&v30, a1);
      v10 = v14;
      if ( v14 >= 0 )
      {
        for ( i = 0; i < v31; ++i )
        {
          if ( GetAddrInfoW(*(PCWSTR *)(v32 + 8LL * i), *(PCWSTR *)(*((_QWORD *)&v32 + 1) + 8LL * i), 0, &ppResult) )
          {
            LastError = GetLastError();
            v10 = LastError;
            if ( LastError > 0 )
              v10 = (unsigned __int16)LastError | 0x80070000;
            if ( v10 < 0 )
            {
              CEventLogger::LogError(
                v20,
                v19,
                L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
                0x5BEu,
                L"CheckForPublicAddresses",
                v10);
              break;
            }
          }
          v21 = ppResult;
          if ( ppResult )
          {
            v22 = v33;
            do
            {
              if ( v21->ai_family == 2 )
              {
                ai_addr = (const IN_ADDR *)v21->ai_addr;
                if ( ai_addr && !IN4_IS_ADDR_RFC1918(ai_addr + 1) )
                  *a2 = 1;
              }
              else if ( v21->ai_family == 23 )
              {
                v24 = v21->ai_addr;
                if ( v24 )
                {
                  v25 = (struct in6_addr *)&v24->sa_data[6];
                  if ( IN6_IS_ADDR_TEREDO((const IN6_ADDR *)&v24->sa_data[6]) == 1
                    && (unsigned int)IsTeredoQualified(v26) == 1 )
                  {
                    *v22 = 1;
                    if ( a4 )
                      *a4 = *v25;
                  }
                }
              }
              v21 = v21->ai_next;
            }
            while ( v21 );
            v21 = ppResult;
            v13 = v29;
          }
          FreeAddrInfoW(v21);
          ppResult = 0;
        }
      }
      else
      {
        CEventLogger::LogError(
          v16,
          v15,
          L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
          0x5B5u,
          L"CheckForPublicAddresses",
          v14);
      }
    }
    CRATicketInfo::Cleanup((CRATicketInfo *)&v30);
    if ( ppResult )
    {
      FreeAddrInfoW(ppResult);
      ppResult = 0;
    }
    if ( v13 == 1 )
      WSACleanup();
  }
  else
  {
    CEventLogger::LogError(
      v9,
      v8,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x5A2u,
      L"CheckForPublicAddresses",
      0x80070057);
    v10 = -2147024809;
  }
  CRATicketInfo::Cleanup((CRATicketInfo *)&v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180010adc  push    rbp
0x180010ade  push    rbx
0x180010adf  push    rsi
0x180010ae0  push    rdi
0x180010ae1  push    r12
0x180010ae3  push    r13
0x180010ae5  push    r14
0x180010ae7  push    r15
0x180010ae9  lea     rbp, [rsp-128h]
0x180010af1  sub     rsp, 228h
0x180010af8  mov     rax, cs:__security_cookie
0x180010aff  xor     rax, rsp
0x180010b02  mov     [rbp+160h+var_50], rax
0x180010b09  mov     r14, r9
0x180010b0c  mov     rdi, r8
0x180010b0f  mov     [rsp+260h+var_200], r8
0x180010b14  mov     r13, rdx
0x180010b17  mov     rbx, rcx
0x180010b1a  mov     [rsp+260h+var_220], 0
0x180010b23  mov     [rsp+260h+var_218], 0
0x180010b2b  xorps   xmm0, xmm0
0x180010b2e  movdqu  [rsp+260h+var_210], xmm0
0x180010b34  xor     edx, edx; Val
0x180010b36  mov     r8d, 198h; Size
0x180010b3c  lea     rcx, [rsp+260h+WSAData]; void *
0x180010b41  call    memset_0
0x180010b46  mov     [rsp+260h+ppResult], 0
0x180010b4f  test    rbx, rbx
0x180010b52  jnz     short loc_180010B84
0x180010b54  mov     [rsp+260h+var_238], 80070057h; unsigned int
0x180010b5c  lea     rax, aCheckforpublic; "CheckForPublicAddresses"
0x180010b63  mov     [rsp+260h+var_240], rax; unsigned __int16 *
0x180010b68  mov     r9d, 5A2h; unsigned int
0x180010b6e  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180010b75  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180010b7a  mov     ebx, 80070057h
0x180010b7f  jmp     loc_180010D38
0x180010b84  mov     dword ptr [r13+0], 0
0x180010b8c  mov     dword ptr [rdi], 0
0x180010b92  test    r14, r14
0x180010b95  jz      short loc_180010B9E
0x180010b97  xorps   xmm0, xmm0
0x180010b9a  movups  xmmword ptr [r14], xmm0
0x180010b9e  mov     ecx, 202h; wVersionRequested
0x180010ba3  lea     rdx, [rsp+260h+WSAData]; lpWSAData
0x180010ba8  call    cs:__imp_WSAStartup
0x180010bae  test    eax, eax
0x180010bb0  jz      short loc_180010BCD
0x180010bb2  xor     r12d, r12d
0x180010bb5  mov     ebx, 80004005h
0x180010bba  mov     [rsp+260h+var_238], 80004005h
0x180010bc2  mov     r9d, 5AFh
0x180010bc8  jmp     loc_180010CF0
0x180010bcd  mov     r12d, 1
0x180010bd3  mov     [rsp+260h+var_228], r12d
0x180010bd8  mov     rdx, rbx; unsigned __int16 *
0x180010bdb  lea     rcx, [rsp+260h+var_220]; this
0x180010be0  call    ?InitializeTicket@CRATicketInfo@@QEAAJPEAG@Z; CRATicketInfo::InitializeTicket(ushort *)
0x180010be5  mov     ebx, eax
0x180010be7  test    eax, eax
0x180010be9  jns     short loc_180010BFA
0x180010beb  mov     [rsp+260h+var_238], eax
0x180010bef  mov     r9d, 5B5h
0x180010bf5  jmp     loc_180010CF0
0x180010bfa  xor     esi, esi
0x180010bfc  cmp     esi, [rsp+260h+var_218]
0x180010c00  jge     loc_180010D08
0x180010c06  movsxd  rax, esi
0x180010c09  lea     r9, [rsp+260h+ppResult]; ppResult
0x180010c0e  xor     r8d, r8d; pHints
0x180010c11  mov     rdx, qword ptr [rsp+260h+var_210+8]
0x180010c16  mov     rdx, [rdx+rax*8]; pServiceName
0x180010c1a  mov     rcx, qword ptr [rsp+260h+var_210]
0x180010c1f  mov     rcx, [rcx+rax*8]; pNodeName
0x180010c23  call    cs:__imp_GetAddrInfoW
0x180010c29  test    eax, eax
0x180010c2b  jz      short loc_180010C4A
0x180010c2d  call    cs:__imp_GetLastError
0x180010c33  mov     ebx, eax
0x180010c35  test    eax, eax
0x180010c37  jle     short loc_180010C42
0x180010c39  movzx   ebx, ax
0x180010c3c  or      ebx, 80070000h
0x180010c42  test    ebx, ebx
0x180010c44  js      loc_180010CE6
0x180010c4a  mov     rdi, [rsp+260h+ppResult]
0x180010c4f  test    rdi, rdi
0x180010c52  jz      short loc_180010CCD
0x180010c54  mov     r12, [rsp+260h+var_200]
0x180010c59  cmp     dword ptr [rdi+4], 2
0x180010c5d  jnz     short loc_180010C7F
0x180010c5f  mov     rcx, [rdi+20h]
0x180010c63  test    rcx, rcx
0x180010c66  jz      short loc_180010CBA
0x180010c68  add     rcx, 4; a
0x180010c6c  call    IN4_IS_ADDR_RFC1918
0x180010c71  test    al, al
0x180010c73  jnz     short loc_180010CBA
0x180010c75  mov     dword ptr [r13+0], 1
0x180010c7d  jmp     short loc_180010CBA
0x180010c7f  cmp     dword ptr [rdi+4], 17h
0x180010c83  jnz     short loc_180010CBA
0x180010c85  mov     rax, [rdi+20h]
0x180010c89  test    rax, rax
0x180010c8c  jz      short loc_180010CBA
0x180010c8e  lea     r15, [rax+8]
0x180010c92  mov     rcx, r15; a
0x180010c95  call    IN6_IS_ADDR_TEREDO
0x180010c9a  cmp     al, 1
0x180010c9c  jnz     short loc_180010CBA
0x180010c9e  call    ?IsTeredoQualified@@YAHK@Z; IsTeredoQualified(ulong)
0x180010ca3  cmp     eax, 1
0x180010ca6  jnz     short loc_180010CBA
0x180010ca8  mov     [r12], eax
0x180010cac  test    r14, r14
0x180010caf  jz      short loc_180010CBA
0x180010cb1  movups  xmm0, xmmword ptr [r15]
0x180010cb5  movdqu  xmmword ptr [r14], xmm0
0x180010cba  mov     rdi, [rdi+28h]
0x180010cbe  test    rdi, rdi
0x180010cc1  jnz     short loc_180010C59
0x180010cc3  mov     rdi, [rsp+260h+ppResult]
0x180010cc8  mov     r12d, [rsp+260h+var_228]
0x180010ccd  mov     rcx, rdi; pAddrInfo
0x180010cd0  call    cs:__imp_FreeAddrInfoW
0x180010cd6  mov     [rsp+260h+ppResult], 0
0x180010cdf  inc     esi
0x180010ce1  jmp     loc_180010BFC
0x180010ce6  mov     [rsp+260h+var_238], ebx; unsigned int
0x180010cea  mov     r9d, 5BEh; unsigned int
0x180010cf0  lea     rax, aCheckforpublic; "CheckForPublicAddresses"
0x180010cf7  mov     [rsp+260h+var_240], rax; unsigned __int16 *
0x180010cfc  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180010d03  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180010d08  lea     rcx, [rsp+260h+var_220]; this
0x180010d0d  call    ?Cleanup@CRATicketInfo@@QEAAJXZ; CRATicketInfo::Cleanup(void)
0x180010d12  mov     rcx, [rsp+260h+ppResult]; pAddrInfo
0x180010d17  test    rcx, rcx
0x180010d1a  jz      short loc_180010D2B
0x180010d1c  call    cs:__imp_FreeAddrInfoW
0x180010d22  mov     [rsp+260h+ppResult], 0
0x180010d2b  cmp     r12d, 1
0x180010d2f  jnz     short loc_180010D38
0x180010d31  call    cs:__imp_WSACleanup
0x180010d37  nop
0x180010d38  lea     rcx, [rsp+260h+var_220]; this
0x180010d3d  call    ?Cleanup@CRATicketInfo@@QEAAJXZ; CRATicketInfo::Cleanup(void)
0x180010d42  mov     eax, ebx
0x180010d44  mov     rcx, [rbp+160h+var_50]
0x180010d4b  xor     rcx, rsp; StackCookie
0x180010d4e  call    __security_check_cookie
0x180010d53  add     rsp, 228h
0x180010d5a  pop     r15
0x180010d5c  pop     r14
0x180010d5e  pop     r13
0x180010d60  pop     r12
0x180010d62  pop     rdi
0x180010d63  pop     rsi
0x180010d64  pop     rbx
0x180010d65  pop     rbp
0x180010d66  retn
```
