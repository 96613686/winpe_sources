# FilterIPAddressList(ushort *,sockaddr_storage *)

- ea: `0x140035328`
- end: `0x1400355f9`
- name: `?FilterIPAddressList@@YAJPEAGPEAUsockaddr_storage@@@Z`
- size: `721`
- prototype: `__int64 __fastcall(unsigned __int16 *Src, struct sockaddr_storage *Destination)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400311b8`

## callees

- `0x140002463`
- `0x140034ce4`
- `0x140035328`
- `0x140039268`
- `0x1400393ac`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003545d`
- `KERNEL32!GetLastError` at `0x14003545d`
- `msvcrt!memcpy_s` at `0x140035539`
- `msvcrt!memcpy_s` at `0x140035539`
- `WS2_32!FreeAddrInfoW` at `0x14003554a`
- `WS2_32!FreeAddrInfoW` at `0x14003554a`
- `WS2_32!GetAddrInfoW` at `0x14003544d`
- `WS2_32!GetAddrInfoW` at `0x14003544d`
- `WS2_32!__imp_WSAStartup` at `0x1400353a9`
- `WS2_32!__imp_WSAStartup` at `0x1400353a9`
- `WS2_32!__imp_WSACleanup` at `0x1400355b9`
- `WS2_32!__imp_WSACleanup` at `0x1400355b9`

## string_xrefs

- `0x1400353db`: `base\diagnosis\ra\racommon\src\fileutils.cpp`
- `0x140035591`: `base\diagnosis\ra\racommon\src\fileutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilterIPAddressList(unsigned __int16 *Src, struct sockaddr_storage *Destination)
{
  CEventLogger *v4; // rcx
  int v5; // r14d
  int v6; // ebx
  signed int v7; // eax
  CEventLogger *v8; // rcx
  int v9; // edi
  int i; // esi
  signed int LastError; // eax
  CEventLogger *v12; // rcx
  struct addrinfoW *v13; // rcx
  struct sockaddr *ai_addr; // r8
  int v15; // eax
  rsize_t v16; // r9
  PADDRINFOW ppResult; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+40h] [rbp-C0h]
  __int128 v21; // [rsp+48h] [rbp-B8h]
  struct WSAData WSAData; // [rsp+60h] [rbp-A0h] BYREF

  v19 = 0;
  v20 = 0;
  v21 = 0;
  ppResult = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  memset_0(Destination, 0, sizeof(struct sockaddr_storage));
  if ( WSAStartup(0x202u, &WSAData) )
  {
    v5 = 0;
    v6 = -2147467259;
    CEventLogger::LogError(
      v4,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0x3D6u,
      L"FilterIPAddressList",
      0x80004005);
    goto LABEL_36;
  }
  v5 = 1;
  v7 = CRATicketInfo::InitializeTicket(&v19, Src);
  v6 = v7;
  if ( v7 < 0 )
  {
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0x3DBu,
      L"FilterIPAddressList",
      v7);
    goto LABEL_36;
  }
  if ( v20 <= 0 )
  {
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0x3DDu,
      L"FilterIPAddressList",
      0);
    goto LABEL_35;
  }
  v9 = 0;
  for ( i = 0; i < v20; ++i )
  {
    if ( GetAddrInfoW(*(PCWSTR *)(v21 + 8LL * i), *(PCWSTR *)(*((_QWORD *)&v21 + 1) + 8LL * i), 0, &ppResult) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
      {
        CEventLogger::LogError(
          v12,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
          0x3E9u,
          L"FilterIPAddressList",
          v6);
        goto LABEL_36;
      }
    }
    v13 = ppResult;
    if ( ppResult )
    {
      if ( ppResult->ai_family == 2 )
      {
        ai_addr = ppResult->ai_addr;
        if ( !ai_addr )
          goto LABEL_29;
        if ( ai_addr->sa_data[2] == 10
          || (*(_DWORD *)&ai_addr->sa_data[2] & 0xF0FF) == 0x10AC
          || (v15 = 3, *(_WORD *)&ai_addr->sa_data[2] == 0xA8C0) )
        {
          v15 = 1;
        }
        if ( v15 <= v9 )
          goto LABEL_29;
        v16 = 16;
      }
      else
      {
        if ( ppResult->ai_family != 23 )
          goto LABEL_29;
        ai_addr = ppResult->ai_addr;
        if ( !ai_addr )
          goto LABEL_29;
        v15 = *(_DWORD *)&ai_addr->sa_data[6] == *(_DWORD *)in6addr_teredoprefix.u.Byte
           || *(_DWORD *)&ai_addr->sa_data[6] == *(_DWORD *)in6addr_teredoprefix_old.u.Byte
            ? 4
            : 2;
        if ( v15 <= v9 )
          goto LABEL_29;
        v16 = 28;
      }
      v9 = v15;
      memcpy_s(Destination, 0x80u, ai_addr, v16);
      v13 = ppResult;
LABEL_29:
      FreeAddrInfoW(v13);
      continue;
    }
  }
  if ( v9 )
    goto LABEL_36;
LABEL_35:
  v6 = -2147467259;
LABEL_36:
  CRATicketInfo::Cleanup((CRATicketInfo *)&v19);
  if ( v5 == 1 )
    WSACleanup();
  CRATicketInfo::Cleanup((CRATicketInfo *)&v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140035328  mov     [rsp-8+arg_10], rbx
0x14003532d  push    rbp
0x14003532e  push    rsi
0x14003532f  push    rdi
0x140035330  push    r14
0x140035332  push    r15
0x140035334  lea     rbp, [rsp-110h]
0x14003533c  sub     rsp, 210h
0x140035343  mov     rax, cs:__security_cookie
0x14003534a  xor     rax, rsp
0x14003534d  mov     [rbp+130h+var_30], rax
0x140035354  mov     r15, rdx
0x140035357  mov     rbx, rcx
0x14003535a  mov     [rsp+230h+var_1F8], 0
0x140035363  mov     [rsp+230h+var_1F0], 0
0x14003536b  xorps   xmm0, xmm0
0x14003536e  movdqu  [rsp+230h+var_1E8], xmm0
0x140035374  mov     [rsp+230h+ppResult], 0
0x14003537d  xor     edx, edx; Val
0x14003537f  mov     r8d, 198h; Size
0x140035385  lea     rcx, [rsp+230h+WSAData]; void *
0x14003538a  call    memset_0
0x14003538f  xor     edx, edx; Val
0x140035391  mov     r8d, 80h; Size
0x140035397  mov     rcx, r15; void *
0x14003539a  call    memset_0
0x14003539f  mov     ecx, 202h; wVersionRequested
0x1400353a4  lea     rdx, [rsp+230h+WSAData]; lpWSAData
0x1400353a9  call    cs:__imp_WSAStartup
0x1400353b0  nop     dword ptr [rax+rax+00h]
0x1400353b5  test    eax, eax
0x1400353b7  jz      short loc_1400353F3
0x1400353b9  xor     r14d, r14d
0x1400353bc  mov     ebx, 80004005h
0x1400353c1  mov     [rsp+230h+var_208], 80004005h; unsigned int
0x1400353c9  mov     r9d, 3D6h; unsigned int
0x1400353cf  lea     rax, aFilteripaddres; "FilterIPAddressList"
0x1400353d6  mov     [rsp+230h+var_210], rax; unsigned __int16 *
0x1400353db  lea     r8, aBaseDiagnosisR_16; "base\\diagnosis\\ra\\racommon\\src\\fil"...
0x1400353e2  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400353e9  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400353ee  jmp     loc_1400355A9
0x1400353f3  mov     r14d, 1
0x1400353f9  mov     rdx, rbx; Src
0x1400353fc  lea     rcx, [rsp+230h+var_1F8]; this
0x140035401  call    ?InitializeTicket@CRATicketInfo@@QEAAJPEAG@Z; CRATicketInfo::InitializeTicket(ushort *)
0x140035406  mov     ebx, eax
0x140035408  test    eax, eax
0x14003540a  jns     short loc_140035418
0x14003540c  mov     [rsp+230h+var_208], eax
0x140035410  mov     r9d, 3DBh
0x140035416  jmp     short loc_1400353CF
0x140035418  mov     eax, [rsp+230h+var_1F0]
0x14003541c  test    eax, eax
0x14003541e  jle     loc_140035577
0x140035424  xor     edi, edi
0x140035426  xor     esi, esi
0x140035428  test    eax, eax
0x14003542a  jle     loc_1400355A4
0x140035430  movsxd  rax, esi
0x140035433  lea     r9, [rsp+230h+ppResult]; ppResult
0x140035438  xor     r8d, r8d; pHints
0x14003543b  mov     rdx, qword ptr [rsp+230h+var_1E8+8]
0x140035440  mov     rdx, [rdx+rax*8]; pServiceName
0x140035444  mov     rcx, qword ptr [rsp+230h+var_1E8]
0x140035449  mov     rcx, [rcx+rax*8]; pNodeName
0x14003544d  call    cs:__imp_GetAddrInfoW
0x140035454  nop     dword ptr [rax+rax+00h]
0x140035459  test    eax, eax
0x14003545b  jz      short loc_140035480
0x14003545d  call    cs:__imp_GetLastError
0x140035464  nop     dword ptr [rax+rax+00h]
0x140035469  mov     ebx, eax
0x14003546b  test    eax, eax
0x14003546d  jle     short loc_140035478
0x14003546f  movzx   ebx, ax
0x140035472  or      ebx, 80070000h
0x140035478  test    ebx, ebx
0x14003547a  js      loc_140035568
0x140035480  mov     rcx, [rsp+230h+ppResult]
0x140035485  test    rcx, rcx
0x140035488  jz      loc_140035556
0x14003548e  cmp     dword ptr [rcx+4], 2
0x140035492  jnz     short loc_1400354D5
0x140035494  mov     r8, [rcx+20h]
0x140035498  test    r8, r8
0x14003549b  jz      loc_14003554A
0x1400354a1  cmp     byte ptr [r8+4], 0Ah
0x1400354a6  jz      short loc_1400354C6
0x1400354a8  mov     eax, [r8+4]
0x1400354ac  and     eax, 0F0FFh
0x1400354b1  cmp     eax, 10ACh
0x1400354b6  jz      short loc_1400354C6
0x1400354b8  cmp     word ptr [r8+4], 0A8C0h
0x1400354bf  mov     eax, 3
0x1400354c4  jnz     short loc_1400354C9
0x1400354c6  mov     eax, r14d
0x1400354c9  cmp     eax, edi
0x1400354cb  jle     short loc_14003554A
0x1400354cd  mov     r9d, 10h
0x1400354d3  jmp     short loc_14003552F
0x1400354d5  cmp     dword ptr [rcx+4], 17h
0x1400354d9  jnz     short loc_14003554A
0x1400354db  mov     r8, [rcx+20h]; Source
0x1400354df  test    r8, r8
0x1400354e2  jz      short loc_14003554A
0x1400354e4  movzx   r9d, word ptr [r8+8]
0x1400354e9  cmp     r9w, word ptr cs:in6addr_teredoprefix.u
0x1400354f1  jnz     short loc_140035501
0x1400354f3  movzx   eax, word ptr cs:in6addr_teredoprefix.u+2
0x1400354fa  cmp     [r8+0Ah], ax
0x1400354ff  jz      short loc_140035519
0x140035501  cmp     r9w, word ptr cs:in6addr_teredoprefix_old.u
0x140035509  jnz     short loc_140035520
0x14003550b  movzx   eax, word ptr cs:in6addr_teredoprefix_old.u+2
0x140035512  cmp     [r8+0Ah], ax
0x140035517  jnz     short loc_140035520
0x140035519  mov     eax, 4
0x14003551e  jmp     short loc_140035525
0x140035520  mov     eax, 2
0x140035525  cmp     eax, edi
0x140035527  jle     short loc_14003554A
0x140035529  mov     r9d, 1Ch; SourceSize
0x14003552f  mov     edi, eax
0x140035531  mov     edx, 80h; DestinationSize
0x140035536  mov     rcx, r15; Destination
0x140035539  call    cs:__imp_memcpy_s
0x140035540  nop     dword ptr [rax+rax+00h]
0x140035545  mov     rcx, [rsp+230h+ppResult]; pAddrInfo
0x14003554a  call    cs:__imp_FreeAddrInfoW
0x140035551  nop     dword ptr [rax+rax+00h]
0x140035556  inc     esi
0x140035558  cmp     esi, [rsp+230h+var_1F0]
0x14003555c  jl      loc_140035430
0x140035562  test    edi, edi
0x140035564  jnz     short loc_1400355A9
0x140035566  jmp     short loc_1400355A4
0x140035568  mov     [rsp+230h+var_208], ebx
0x14003556c  mov     r9d, 3E9h
0x140035572  jmp     loc_1400353CF
0x140035577  mov     [rsp+230h+var_208], 0; unsigned int
0x14003557f  lea     rax, aFilteripaddres; "FilterIPAddressList"
0x140035586  mov     [rsp+230h+var_210], rax; unsigned __int16 *
0x14003558b  mov     r9d, 3DDh; unsigned int
0x140035591  lea     r8, aBaseDiagnosisR_16; "base\\diagnosis\\ra\\racommon\\src\\fil"...
0x140035598  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003559f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400355a4  mov     ebx, 80004005h
0x1400355a9  lea     rcx, [rsp+230h+var_1F8]; this
0x1400355ae  call    ?Cleanup@CRATicketInfo@@QEAAJXZ; CRATicketInfo::Cleanup(void)
0x1400355b3  cmp     r14d, 1
0x1400355b7  jnz     short loc_1400355C6
0x1400355b9  call    cs:__imp_WSACleanup
0x1400355c0  nop     dword ptr [rax+rax+00h]
0x1400355c5  nop
0x1400355c6  lea     rcx, [rsp+230h+var_1F8]; this
0x1400355cb  call    ?Cleanup@CRATicketInfo@@QEAAJXZ; CRATicketInfo::Cleanup(void)
0x1400355d0  mov     eax, ebx
0x1400355d2  mov     rcx, [rbp+130h+var_30]
0x1400355d9  xor     rcx, rsp; StackCookie
0x1400355dc  call    __security_check_cookie
0x1400355e1  mov     rbx, [rsp+230h+arg_10]
0x1400355e9  add     rsp, 210h
0x1400355f0  pop     r15
0x1400355f2  pop     r14
0x1400355f4  pop     rdi
0x1400355f5  pop     rsi
0x1400355f6  pop     rbp
0x1400355f7  retn
```
