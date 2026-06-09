# Mcast_CreateIoContext

- ea: `0x18001d230`
- end: `0x18001d6c3`
- name: `Mcast_CreateIoContext`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x18001cd24`

## callees

- `0x18001d100`
- `0x18001d230`
- `0x18001d7bc`
- `0x18001d968`
- `0x18003aef8`
- `0x180046ec0`
- `0x180047818`
- `0x18007d140`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x18001d357`
- `DNSAPI!Socket_CloseEx` at `0x18001d538`
- `DNSAPI!Socket_CloseEx` at `0x18001d538`
- `DNSAPI!Socket_Create` at `0x18001d2ec`
- `DNSAPI!Socket_Create` at `0x18001d2ec`
- `DNSAPI!Socket_JoinMulticast` at `0x18001d396`
- `DNSAPI!Socket_JoinMulticast` at `0x18001d396`
- `DNSAPI!Socket_SetMulticastLoopBack` at `0x18001d3dc`
- `DNSAPI!Socket_SetMulticastLoopBack` at `0x18001d3dc`
- `DNSAPI!Socket_TcpListen` at `0x18001d516`
- `DNSAPI!Socket_TcpListen` at `0x18001d516`
- `DNSAPI!Socket_SetTtl` at `0x18001d408`
- `DNSAPI!Socket_SetTtl` at `0x18001d408`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d55e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d55e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d69a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d69a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001d674`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001d674`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d43f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d43f`
- `WS2_32!WSAEventSelect` at `0x18001d4a3`
- `WS2_32!WSAEventSelect` at `0x18001d4a3`
- `WS2_32!WSACreateEvent` at `0x18001d479`
- `WS2_32!WSACreateEvent` at `0x18001d479`
- `WS2_32!__imp_WSAGetLastError` at `0x18001d5d0`
- `WS2_32!__imp_WSAGetLastError` at `0x18001d5d0`

## pseudocode

```c
__int64 __fastcall Mcast_CreateIoContext(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        int a7)
{
  __int64 v9; // rdi
  unsigned int v10; // r12d
  int v11; // edx
  int v12; // r8d
  __int64 v13; // r9
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // r13
  int v17; // r14d
  int v18; // ecx
  unsigned int v19; // r12d
  __int64 v20; // rdx
  unsigned int v21; // eax
  DWORD v22; // eax
  DWORD LastError; // ebx
  unsigned int v24; // eax
  __int64 MsgBuf; // rax
  __int64 v26; // rax
  HANDLE v27; // rax
  const char *v29; // rax
  unsigned int Error; // eax
  __int64 v31; // rdx
  __int64 v32; // rdx
  int v33; // [rsp+50h] [rbp-B8h]
  _BYTE v36[64]; // [rsp+70h] [rbp-98h] BYREF

  v9 = a1;
  v10 = a4;
  memset_0(v36, 0, sizeof(v36));
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v29 = "mDNS";
    if ( !a7 )
      v29 = "LLMNR";
    WPP_SF_qddqdds((unsigned int)"LLMNR", v11, v12, v9, a3, v10, a5, a6, a7, (__int64)v29);
  }
  if ( v9 && a2 )
  {
    DnsAddr_BuildMcast(v36);
    v14 = 20;
    if ( v10 != 2 )
      v14 = 0;
    LOWORD(v13) = a7 != 0 ? -5868 : -5356;
    v15 = Socket_Create(a3, v10, 0, v13, v14);
    v16 = v15;
    if ( !v15 )
    {
      Error = WSAGetLastError();
      LastError = Error;
      if ( SBYTE3(xmmword_1800AB5A0) < 0 )
        WPP_SF_d(1055, 18, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, Error);
      goto LABEL_43;
    }
    v17 = 1;
    if ( v10 == 2 )
    {
      v18 = 0;
      v33 = 0;
      if ( *(_DWORD *)(a2 + 68) )
      {
        v19 = 0;
        while ( 1 )
        {
          v20 = 160LL * v19;
          if ( a7 )
          {
            if ( !DnsGlobals[100] )
              goto LABEL_18;
          }
          else if ( (*(_DWORD *)(v20 + a2 + 172) & 0xA00000) != 0xA00000 )
          {
            goto LABEL_18;
          }
          if ( a3 == 23 )
          {
            if ( (*(_DWORD *)(v20 + a2 + 160) & 0x100) != 0 )
              goto LABEL_16;
          }
          else if ( a3 == 2 && *(char *)(v20 + a2 + 160) < 0 )
          {
LABEL_16:
            v21 = Socket_JoinMulticast(v16, *(unsigned __int16 *)(v20 + a2 + 152), v36, 1, 1);
            if ( v21 )
            {
              if ( SBYTE3(xmmword_1800AB5A0) < 0 )
                WPP_SF_d(1055, 19, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, v21);
              v18 = v33;
            }
            else
            {
              v18 = ++v33;
            }
          }
LABEL_18:
          if ( ++v19 >= *(_DWORD *)(a2 + 68) )
          {
            v9 = a1;
            v10 = a4;
            break;
          }
        }
      }
      *(_DWORD *)(v9 + 32) = v18;
      if ( a7 || (v22 = Socket_SetMulticastLoopBack(v16, a3, 0), (LastError = v22) == 0) )
      {
LABEL_22:
        v24 = Socket_SetTtl(v16, a3, 1, v10 == 2, 0);
        if ( v24 && SBYTE3(xmmword_1800AB5A0) < 0 )
          WPP_SF_d(1055, 22, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, v24);
        *(_QWORD *)(v9 + 16) = v16;
        *(_DWORD *)(v9 + 24) = a3;
        *(_DWORD *)(v9 + 28) = v10;
        MsgBuf = Packet_AllocateMsgBuf(0xFFFF);
        *(_QWORD *)(v9 + 104) = MsgBuf;
        if ( MsgBuf )
        {
          *(_DWORD *)(MsgBuf + 664) = GetCurrentProcessId();
          v26 = *(_QWORD *)(v9 + 104);
          if ( v10 == 2 )
          {
            *(_BYTE *)(v26 + 648) = 0;
            *(_BYTE *)(*(_QWORD *)(v9 + 104) + 651LL) = 1;
          }
          else
          {
            *(_BYTE *)(v26 + 648) = 1;
            *(_BYTE *)(*(_QWORD *)(v9 + 104) + 651LL) = 0;
          }
          if ( a6 )
          {
            InitializeCriticalSection((LPCRITICAL_SECTION)(v9 + 56));
            *(_DWORD *)(v9 + 96) = 1;
          }
          v27 = WSACreateEvent();
          *(_QWORD *)(v9 + 40) = v27;
          if ( v27 )
          {
            if ( v10 != 2 )
              v17 = 8;
            if ( WSAEventSelect(*(_QWORD *)(v9 + 16), v27, v17) != -1 )
            {
              Mcast_PrintIoContext(v9);
              return 0;
            }
            LastError = GetLastError();
            if ( (SBYTE3(xmmword_1800AB5A0) & 0x80u) == 0 )
              goto LABEL_43;
            v32 = 25;
            goto LABEL_62;
          }
          LastError = 14;
          if ( SBYTE3(xmmword_1800AB5A0) < 0 )
          {
            v32 = 24;
            goto LABEL_62;
          }
        }
        else
        {
          LastError = 14;
          if ( SBYTE3(xmmword_1800AB5A0) < 0 )
          {
            v32 = 23;
LABEL_62:
            WPP_SF_(1055, v32, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids);
          }
        }
LABEL_43:
        Mcast_FreeIoContext(v9, 0);
        SetLastError(LastError);
        return LastError;
      }
      if ( SBYTE3(xmmword_1800AB5A0) < 0 )
      {
        v31 = 20;
LABEL_54:
        WPP_SF_d(1055, v31, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, v22);
      }
    }
    else
    {
      v22 = Socket_TcpListen(v15);
      LastError = v22;
      if ( !v22 )
        goto LABEL_22;
      if ( SBYTE3(xmmword_1800AB5A0) < 0 )
      {
        v31 = 21;
        goto LABEL_54;
      }
    }
    Socket_CloseEx(v16, 0);
    goto LABEL_43;
  }
  return 87;
}

```

## disassembly

```asm
0x18001d230  push    rbx
0x18001d232  push    rbp
0x18001d233  push    rsi
0x18001d234  push    rdi
0x18001d235  push    r12
0x18001d237  push    r13
0x18001d239  push    r14
0x18001d23b  push    r15
0x18001d23d  sub     rsp, 0C8h
0x18001d244  mov     rax, cs:__security_cookie
0x18001d24b  xor     rax, rsp
0x18001d24e  mov     [rsp+108h+var_58], rax
0x18001d256  mov     rsi, [rsp+108h+arg_20]
0x18001d25e  mov     rbx, rdx
0x18001d261  xor     edx, edx; Val
0x18001d263  mov     [rsp+108h+var_A8], rcx
0x18001d268  mov     r15d, r8d
0x18001d26b  mov     [rsp+108h+var_B0], r9d
0x18001d270  mov     rdi, rcx
0x18001d273  mov     r12d, r9d
0x18001d276  lea     rcx, [rsp+108h+var_98]; void *
0x18001d27b  lea     r8d, [rdx+40h]; Size
0x18001d27f  call    memset_0
0x18001d284  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001d28b  mov     ebp, [rsp+108h+arg_30]
0x18001d292  jnz     loc_18001D58C
0x18001d298  test    rdi, rdi
0x18001d29b  jz      loc_18001D582
0x18001d2a1  test    rbx, rbx
0x18001d2a4  jz      loc_18001D582
0x18001d2aa  mov     r9d, ebp
0x18001d2ad  lea     rcx, [rsp+108h+var_98]; void *
0x18001d2b2  mov     r8, rsi
0x18001d2b5  mov     edx, r15d
0x18001d2b8  call    DnsAddr_BuildMcast
0x18001d2bd  xor     eax, eax
0x18001d2bf  mov     ecx, 14h
0x18001d2c4  cmp     r12d, 2
0x18001d2c8  mov     edx, r12d
0x18001d2cb  cmovnz  ecx, eax
0x18001d2ce  mov     eax, ebp
0x18001d2d0  neg     eax
0x18001d2d2  mov     [rsp+108h+var_E8], ecx
0x18001d2d6  mov     ecx, r15d
0x18001d2d9  sbb     r9w, r9w
0x18001d2dd  xor     r8d, r8d
0x18001d2e0  and     r9w, 0FE00h
0x18001d2e6  add     r9w, 0EB14h
0x18001d2ec  call    cs:__imp_Socket_Create
0x18001d2f2  mov     r13, rax
0x18001d2f5  test    rax, rax
0x18001d2f8  jz      loc_18001D5D0
0x18001d2fe  lea     rbp, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids
0x18001d305  mov     esi, 41Fh
0x18001d30a  mov     r14d, 1
0x18001d310  cmp     r12d, 2
0x18001d314  jnz     loc_18001D513
0x18001d31a  xor     ecx, ecx
0x18001d31c  mov     [rsp+108h+var_B8], ecx
0x18001d320  cmp     [rbx+44h], ecx
0x18001d323  jbe     loc_18001D3C6
0x18001d329  mov     edi, [rsp+108h+arg_30]
0x18001d330  mov     r12d, ecx
0x18001d333  mov     eax, r12d
0x18001d336  lea     rdx, [rax+rax*4]
0x18001d33a  shl     rdx, 5
0x18001d33e  test    edi, edi
0x18001d340  jnz     short loc_18001D357
0x18001d342  mov     eax, [rdx+rbx+0ACh]
0x18001d349  and     eax, 0A00000h
0x18001d34e  cmp     eax, 0A00000h
0x18001d353  jz      short loc_18001D367
0x18001d355  jmp     short loc_18001D3AF
0x18001d357  mov     rax, cs:__imp_DnsGlobals
0x18001d35e  cmp     dword ptr [rax+190h], 0
0x18001d365  jz      short loc_18001D3AF
0x18001d367  cmp     r15d, 17h
0x18001d36b  jnz     loc_18001D4E0
0x18001d371  test    dword ptr [rdx+rbx+0A0h], 100h
0x18001d37c  jz      short loc_18001D3AF
0x18001d37e  movzx   edx, word ptr [rdx+rbx+98h]
0x18001d386  lea     r8, [rsp+108h+var_98]
0x18001d38b  mov     r9d, r14d
0x18001d38e  mov     [rsp+108h+var_E8], r14d
0x18001d393  mov     rcx, r13
0x18001d396  call    cs:__imp_Socket_JoinMulticast
0x18001d39c  test    eax, eax
0x18001d39e  jnz     loc_18001D4FD
0x18001d3a4  mov     ecx, [rsp+108h+var_B8]
0x18001d3a8  add     ecx, r14d
0x18001d3ab  mov     [rsp+108h+var_B8], ecx
0x18001d3af  add     r12d, r14d
0x18001d3b2  cmp     r12d, [rbx+44h]
0x18001d3b6  jb      loc_18001D333
0x18001d3bc  mov     rdi, [rsp+108h+var_A8]
0x18001d3c1  mov     r12d, [rsp+108h+var_B0]
0x18001d3c6  cmp     [rsp+108h+arg_30], 0
0x18001d3ce  mov     [rdi+20h], ecx
0x18001d3d1  jnz     short loc_18001D3EC
0x18001d3d3  xor     r8d, r8d
0x18001d3d6  mov     edx, r15d
0x18001d3d9  mov     rcx, r13
0x18001d3dc  call    cs:__imp_Socket_SetMulticastLoopBack
0x18001d3e2  mov     ebx, eax
0x18001d3e4  test    eax, eax
0x18001d3e6  jnz     loc_18001D61A
0x18001d3ec  xor     r9d, r9d
0x18001d3ef  mov     [rsp+108h+var_E8], 0
0x18001d3f7  cmp     r12d, 2
0x18001d3fb  mov     r8d, r14d
0x18001d3fe  mov     edx, r15d
0x18001d401  mov     rcx, r13
0x18001d404  setz    r9b
0x18001d408  call    cs:__imp_Socket_SetTtl
0x18001d40e  test    eax, eax
0x18001d410  jnz     loc_18001D645
0x18001d416  mov     ecx, 0FFFFh
0x18001d41b  mov     [rdi+10h], r13
0x18001d41f  mov     [rdi+18h], r15d
0x18001d423  mov     [rdi+1Ch], r12d
0x18001d427  call    Packet_AllocateMsgBuf
0x18001d42c  xor     r15d, r15d
0x18001d42f  mov     [rdi+68h], rax
0x18001d433  test    rax, rax
0x18001d436  jz      loc_18001D540
0x18001d43c  mov     rbx, rax
0x18001d43f  call    cs:__imp_GetCurrentProcessId
0x18001d445  mov     [rbx+298h], eax
0x18001d44b  mov     rax, [rdi+68h]
0x18001d44f  cmp     r12d, 2
0x18001d453  jnz     loc_18001D56B
0x18001d459  mov     [rax+288h], r15b
0x18001d460  mov     rax, [rdi+68h]
0x18001d464  mov     [rax+28Bh], r14b
0x18001d46b  cmp     [rsp+108h+arg_28], r15d
0x18001d473  jnz     loc_18001D670
0x18001d479  call    cs:__imp_WSACreateEvent
0x18001d47f  mov     [rdi+28h], rax
0x18001d483  test    rax, rax
0x18001d486  jz      loc_18001D683
0x18001d48c  mov     ecx, 8
0x18001d491  cmp     r12d, 2
0x18001d495  mov     rdx, rax; hEventObject
0x18001d498  cmovnz  r14d, ecx
0x18001d49c  mov     rcx, [rdi+10h]; s
0x18001d4a0  mov     r8d, r14d; lNetworkEvents
0x18001d4a3  call    cs:__imp_WSAEventSelect
0x18001d4a9  cmp     eax, 0FFFFFFFFh
0x18001d4ac  jz      loc_18001D69A
0x18001d4b2  mov     rcx, rdi
0x18001d4b5  call    Mcast_PrintIoContext
0x18001d4ba  xor     eax, eax
0x18001d4bc  mov     rcx, [rsp+108h+var_58]
0x18001d4c4  xor     rcx, rsp; StackCookie
0x18001d4c7  call    __security_check_cookie
0x18001d4cc  add     rsp, 0C8h
0x18001d4d3  pop     r15
0x18001d4d5  pop     r14
0x18001d4d7  pop     r13
0x18001d4d9  pop     r12
0x18001d4db  pop     rdi
0x18001d4dc  pop     rsi
0x18001d4dd  pop     rbp
0x18001d4de  pop     rbx
0x18001d4df  retn
0x18001d4e0  cmp     r15d, 2
0x18001d4e4  jnz     loc_18001D3AF
0x18001d4ea  test    byte ptr [rdx+rbx+0A0h], 80h
0x18001d4f2  jnz     loc_18001D37E
0x18001d4f8  jmp     loc_18001D3AF
0x18001d4fd  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18001d504  jl      loc_18001D603
0x18001d50a  mov     ecx, [rsp+108h+var_B8]
0x18001d50e  jmp     loc_18001D3AF
0x18001d513  mov     rcx, r13
0x18001d516  call    cs:__imp_Socket_TcpListen
0x18001d51c  mov     ebx, eax
0x18001d51e  test    eax, eax
0x18001d520  jz      loc_18001D3EC
0x18001d526  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18001d52d  jl      loc_18001D62E
0x18001d533  xor     edx, edx
0x18001d535  mov     rcx, r13
0x18001d538  call    cs:__imp_Socket_CloseEx
0x18001d53e  jmp     short loc_18001D552
0x18001d540  mov     ebx, 0Eh
0x18001d545  cmp     byte ptr cs:xmmword_1800AB5A0+3, r15b
0x18001d54c  jl      loc_18001D669
0x18001d552  xor     edx, edx
0x18001d554  mov     rcx, rdi
0x18001d557  call    Mcast_FreeIoContext
0x18001d55c  mov     ecx, ebx; dwErrCode
0x18001d55e  call    cs:__imp_SetLastError
0x18001d564  mov     eax, ebx
0x18001d566  jmp     loc_18001D4BC
0x18001d56b  mov     [rax+288h], r14b
0x18001d572  mov     rax, [rdi+68h]
0x18001d576  mov     [rax+28Bh], r15b
0x18001d57d  jmp     loc_18001D46B
0x18001d582  mov     eax, 57h ; 'W'
0x18001d587  jmp     loc_18001D4BC
0x18001d58c  test    ebp, ebp
0x18001d58e  lea     rcx, aLlmnr; "LLMNR"
0x18001d595  lea     rax, aMdns; "mDNS"
0x18001d59c  mov     r9, rdi
0x18001d59f  cmovz   rax, rcx
0x18001d5a3  mov     [rsp+108h+var_C0], rax
0x18001d5a8  mov     eax, [rsp+108h+arg_28]
0x18001d5af  mov     [rsp+108h+var_C8], ebp
0x18001d5b3  mov     [rsp+108h+var_D0], eax
0x18001d5b7  mov     [rsp+108h+var_D8], rsi
0x18001d5bc  mov     [rsp+108h+var_E0], r12d
0x18001d5c1  mov     [rsp+108h+var_E8], r15d
0x18001d5c6  call    WPP_SF_qddqdds
0x18001d5cb  jmp     loc_18001D298
0x18001d5d0  call    cs:__imp_WSAGetLastError
0x18001d5d6  mov     ebx, eax
0x18001d5d8  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18001d5df  jge     loc_18001D552
0x18001d5e5  mov     edx, 12h
0x18001d5ea  lea     r8, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids
0x18001d5f1  mov     ecx, 41Fh
0x18001d5f6  mov     r9d, eax
0x18001d5f9  call    WPP_SF_d
0x18001d5fe  jmp     loc_18001D552
0x18001d603  mov     edx, 13h
0x18001d608  mov     ecx, esi
0x18001d60a  mov     r9d, eax
0x18001d60d  mov     r8, rbp
0x18001d610  call    WPP_SF_d
0x18001d615  jmp     loc_18001D50A
0x18001d61a  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18001d621  jge     loc_18001D533
0x18001d627  mov     edx, 14h
0x18001d62c  jmp     short loc_18001D633
0x18001d62e  mov     edx, 15h
0x18001d633  mov     r9d, eax
0x18001d636  mov     r8, rbp
0x18001d639  mov     ecx, esi
0x18001d63b  call    WPP_SF_d
0x18001d640  jmp     loc_18001D533
0x18001d645  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18001d64c  jge     loc_18001D416
0x18001d652  mov     edx, 16h
0x18001d657  mov     ecx, esi
0x18001d659  mov     r9d, eax
0x18001d65c  mov     r8, rbp
0x18001d65f  call    WPP_SF_d
0x18001d664  jmp     loc_18001D416
0x18001d669  mov     edx, 17h
0x18001d66e  jmp     short loc_18001D6B4
0x18001d670  lea     rcx, [rdi+38h]; lpCriticalSection
0x18001d674  call    cs:__imp_InitializeCriticalSection
0x18001d67a  mov     [rdi+60h], r14d
0x18001d67e  jmp     loc_18001D479
0x18001d683  mov     ebx, 0Eh
0x18001d688  cmp     byte ptr cs:xmmword_1800AB5A0+3, r15b
0x18001d68f  jge     loc_18001D552
0x18001d695  lea     edx, [rbx+0Ah]
0x18001d698  jmp     short loc_18001D6B4
0x18001d69a  call    cs:__imp_GetLastError
0x18001d6a0  mov     ebx, eax
0x18001d6a2  cmp     byte ptr cs:xmmword_1800AB5A0+3, r15b
0x18001d6a9  jge     loc_18001D552
0x18001d6af  mov     edx, 19h
0x18001d6b4  mov     r8, rbp
0x18001d6b7  mov     ecx, esi
0x18001d6b9  call    WPP_SF_
0x18001d6be  jmp     loc_18001D552
```
