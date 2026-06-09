# GetMachineDNSNames

- ea: `0x18004c4e4`
- end: `0x18004c783`
- name: `GetMachineDNSNames`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004da4c`

## callees

- `0x18000bab8`
- `0x18000cb80`
- `0x18000f35c`
- `0x18002c61c`
- `0x18004c4e4`
- `0x18009bd1c`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x18004c737`
- `msvcrt!free` at `0x18004c754`
- `msvcrt!free` at `0x18004c737`
- `msvcrt!free` at `0x18004c754`
- `KERNEL32!CompareStringW` at `0x18004c621`
- `KERNEL32!CompareStringW` at `0x18004c621`
- `WSOCK32!__imp_WSAGetLastError` at `0x18004c5d2`
- `WSOCK32!__imp_WSAGetLastError` at `0x18004c5d2`
- `WS2_32!FreeAddrInfoW` at `0x18004c71a`
- `WS2_32!FreeAddrInfoW` at `0x18004c71a`
- `WS2_32!GetAddrInfoW` at `0x18004c5a3`
- `WS2_32!GetAddrInfoW` at `0x18004c5a3`
- `mqsec!GetFalconServiceName` at `0x18004c56e`
- `mqsec!GetFalconServiceName` at `0x18004c56e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void GetMachineDNSNames()
{
  const WCHAR *v0; // rbx
  int FalconServiceName; // eax
  unsigned int Error; // eax
  int v3; // ecx
  PADDRINFOW v4; // rdx
  int v5; // eax
  __int64 v6; // rbx
  void **v7; // rdi
  PADDRINFOW v8; // rbx
  int v9; // r14d
  const wchar_t *ai_canonname; // rcx
  unsigned __int64 v11; // r15
  wchar_t *v12; // rax
  void **v13; // rbx
  void *v14; // rax
  void **v15; // rdi
  __int64 i; // rbx
  unsigned int v17; // [rsp+30h] [rbp-308h]
  struct addrinfoW *v18; // [rsp+38h] [rbp-300h]
  PADDRINFOW ppResult; // [rsp+40h] [rbp-2F8h] BYREF
  void **v20; // [rsp+48h] [rbp-2F0h]
  ADDRINFOW pHints; // [rsp+50h] [rbp-2E8h] BYREF
  _QWORD v22[4]; // [rsp+80h] [rbp-2B8h] BYREF
  WCHAR String1[304]; // [rsp+A0h] [rbp-298h] BYREF

  if ( CQueueMgr::m_Connected )
  {
    ppResult = 0;
    pHints.ai_family = 0;
    memset(&pHints.ai_addrlen, 0, 32);
    pHints.ai_flags = 2;
    pHints.ai_socktype = 1;
    pHints.ai_protocol = 6;
    memset_0(String1, 0, 0x258u);
    v0 = L"..localmachine";
    FalconServiceName = GetFalconServiceName(String1, 0x12Cu);
    if ( FalconServiceName >= 0 )
    {
      if ( CompareStringW(0x7Fu, 1u, String1, -1, L"MSMQ", -1) != 2 )
      {
        try
        {
          v0 = g_szComputerDnsName;
          if ( !g_szComputerDnsName && g_szMachineName )
            v0 = g_szMachineName;
        }
        catch ( std::bad_alloc )
        {
          LogMsgHR(-1072824281, (wchar_t *)L"qmutil", 0x3E7u);
          exception::exception((exception *)v22, &std::_bad_alloc_Message, 1);
          v22[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)v22;
        }
      }
    }
    else
    {
      LogMsgHR(FalconServiceName, (wchar_t *)L"qmutil", 0x46u);
    }
    if ( GetAddrInfoW(v0, 0, &pHints, &ppResult) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        Error = WSAGetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_192c42d8776e381393522325b4b293b0_Traceguids, Error);
      }
    }
    else
    {
      try
      {
        v3 = 1;
        v17 = 1;
        v4 = ppResult;
        if ( ppResult )
        {
          do
          {
            v5 = v3 + 1;
            if ( !v4->ai_canonname )
              v5 = v3;
            v3 = v5;
            v4 = v4->ai_next;
          }
          while ( v4 );
          v17 = v5;
        }
        v20 = 0;
        v6 = v3;
        v7 = (void **)MmAllocate(saturated_mul(v3, 8u));
        v20 = v7;
        memset_0(v7, 0, 8 * v6);
        v8 = ppResult;
        v9 = 0;
        while ( 1 )
        {
          v18 = v8;
          if ( !v8 )
            break;
          ai_canonname = v8->ai_canonname;
          if ( ai_canonname )
          {
            v11 = (int)(mqwcslen(ai_canonname) + 1);
            v12 = (wchar_t *)MmAllocate(saturated_mul(v11, 2u));
            v7[v9] = v12;
            StringCchCopyW(v12, v11, v8->ai_canonname);
            ++v9;
          }
          v8 = v8->ai_next;
        }
      }
      catch ( std::bad_alloc )
      {
        v15 = v20;
        if ( v20 )
        {
          for ( i = 0; (unsigned int)i < v17; i = (unsigned int)(i + 1) )
            free(v15[i]);
          free(v15);
        }
        LogIllegalPoint((wchar_t *)L"qmutil", 0x47u);
        FreeAddrInfoW(v18);
        return;
      }
      FreeAddrInfoW(0);
      v13 = (void **)Block;
      if ( Block )
      {
        v14 = *(void **)Block;
        if ( *(_QWORD *)Block )
        {
          do
          {
            free(v14);
            v14 = *++v13;
          }
          while ( *v13 );
          v13 = (void **)Block;
        }
        free(v13);
      }
      Block = v7;
    }
  }
}

```

## disassembly

```asm
0x18004c4e4  push    rbx
0x18004c4e6  push    rsi
0x18004c4e7  push    rdi
0x18004c4e8  push    r14
0x18004c4ea  push    r15
0x18004c4ec  sub     rsp, 310h
0x18004c4f3  mov     rax, cs:__security_cookie
0x18004c4fa  xor     rax, rsp
0x18004c4fd  mov     [rsp+338h+var_38], rax
0x18004c505  cmp     cs:?m_Connected@CQueueMgr@@0JA, 0; long CQueueMgr::m_Connected
0x18004c50c  jz      loc_18004C764
0x18004c512  mov     [rsp+338h+ppResult], 0
0x18004c51b  xorps   xmm0, xmm0
0x18004c51e  movups  xmmword ptr [rsp+338h+pHints.ai_flags], xmm0
0x18004c523  movups  xmmword ptr [rsp+338h+pHints.ai_addrlen], xmm0
0x18004c528  movups  xmmword ptr [rsp+338h+pHints.ai_addr], xmm0
0x18004c52d  mov     [rsp+338h+pHints.ai_flags], 2
0x18004c535  mov     [rsp+338h+pHints.ai_socktype], 1
0x18004c53d  mov     [rsp+338h+pHints.ai_protocol], 6
0x18004c545  xor     edx, edx; Val
0x18004c547  mov     r8d, 258h; Size
0x18004c54d  lea     rcx, [rsp+338h+String1]; void *
0x18004c555  call    memset_0
0x18004c55a  lea     rbx, pNodeName; "..localmachine"
0x18004c561  mov     edx, 12Ch
0x18004c566  lea     rcx, [rsp+338h+String1]
0x18004c56e  call    cs:__imp_?GetFalconServiceName@@YAJPEA_WK@Z; GetFalconServiceName(wchar_t *,ulong)
0x18004c574  test    eax, eax
0x18004c576  jns     loc_18004C5FC
0x18004c57c  mov     r8d, 46h ; 'F'; unsigned __int16
0x18004c582  lea     rdx, aQmutil; "qmutil"
0x18004c589  mov     ecx, eax; int
0x18004c58b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18004c590  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004c594  lea     r9, [rsp+338h+ppResult]; ppResult
0x18004c599  lea     r8, [rsp+338h+pHints]; pHints
0x18004c59e  xor     edx, edx; pServiceName
0x18004c5a0  mov     rcx, rbx; pNodeName
0x18004c5a3  call    cs:__imp_GetAddrInfoW
0x18004c5a9  test    eax, eax
0x18004c5ab  jz      loc_18004C64F
0x18004c5b1  lea     rcx, WPP_GLOBAL_Control
0x18004c5b8  mov     rax, cs:WPP_GLOBAL_Control
0x18004c5bf  cmp     rax, rcx
0x18004c5c2  jz      loc_18004C764
0x18004c5c8  test    byte ptr [rax+6Ch], 1
0x18004c5cc  jz      loc_18004C764
0x18004c5d2  call    cs:__imp_WSAGetLastError
0x18004c5d8  mov     edx, 0Ah
0x18004c5dd  mov     r9d, eax
0x18004c5e0  lea     r8, WPP_192c42d8776e381393522325b4b293b0_Traceguids
0x18004c5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c5ee  mov     rcx, [rcx+60h]
0x18004c5f2  call    WPP_SF_d
0x18004c5f7  jmp     loc_18004C764
0x18004c5fc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004c600  mov     [rsp+338h+cchCount2], esi; cchCount2
0x18004c604  lea     rax, aMsmq_0; "MSMQ"
0x18004c60b  mov     [rsp+338h+lpString2], rax; lpString2
0x18004c610  mov     r9d, esi; cchCount1
0x18004c613  lea     r8, [rsp+338h+String1]; lpString1
0x18004c61b  lea     edx, [rsi+2]; dwCmpFlags
0x18004c61e  lea     ecx, [rdx+7Eh]; Locale
0x18004c621  call    cs:__imp_CompareStringW
0x18004c627  cmp     eax, 2
0x18004c62a  jz      loc_18004C594
0x18004c630  mov     rbx, cs:?g_szComputerDnsName@@3V?$AP@_W@@A; AP<wchar_t> g_szComputerDnsName
0x18004c637  test    rbx, rbx
0x18004c63a  jnz     short loc_18004C64A
0x18004c63c  mov     rax, cs:?g_szMachineName@@3PEA_WEA; wchar_t * g_szMachineName
0x18004c643  test    rax, rax
0x18004c646  cmovnz  rbx, rax
0x18004c64a  jmp     loc_18004C594
0x18004c64f  mov     ecx, 1
0x18004c654  mov     [rsp+338h+var_308], ecx
0x18004c658  mov     rdx, [rsp+338h+ppResult]
0x18004c65d  mov     [rsp+338h+var_300], rdx
0x18004c662  test    rdx, rdx
0x18004c665  jz      short loc_18004C686
0x18004c667  lea     eax, [rcx+1]
0x18004c66a  cmp     qword ptr [rdx+18h], 0
0x18004c66f  cmovz   eax, ecx
0x18004c672  mov     ecx, eax
0x18004c674  mov     rdx, [rdx+28h]
0x18004c678  test    rdx, rdx
0x18004c67b  jnz     short loc_18004C667
0x18004c67d  mov     [rsp+338h+var_300], rdx
0x18004c682  mov     [rsp+338h+var_308], eax
0x18004c686  mov     [rsp+338h+var_2F0], 0
0x18004c68f  movsxd  rbx, ecx
0x18004c692  mov     eax, 8
0x18004c697  mul     rbx
0x18004c69a  cmovb   rax, rsi
0x18004c69e  mov     rcx, rax; unsigned __int64
0x18004c6a1  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18004c6a6  mov     rdi, rax
0x18004c6a9  mov     [rsp+338h+var_2F0], rax
0x18004c6ae  lea     r8, ds:0[rbx*8]; Size
0x18004c6b6  xor     edx, edx; Val
0x18004c6b8  mov     rcx, rax; void *
0x18004c6bb  call    memset_0
0x18004c6c0  mov     rbx, [rsp+338h+ppResult]
0x18004c6c5  xor     r14d, r14d
0x18004c6c8  mov     [rsp+338h+var_300], rbx
0x18004c6cd  test    rbx, rbx
0x18004c6d0  jz      short loc_18004C718
0x18004c6d2  mov     rcx, [rbx+18h]; wchar_t *
0x18004c6d6  test    rcx, rcx
0x18004c6d9  jz      short loc_18004C712
0x18004c6db  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18004c6e0  inc     eax
0x18004c6e2  movsxd  r15, eax
0x18004c6e5  mov     eax, 2
0x18004c6ea  mul     r15
0x18004c6ed  cmovb   rax, rsi
0x18004c6f1  mov     rcx, rax; unsigned __int64
0x18004c6f4  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18004c6f9  movsxd  rcx, r14d
0x18004c6fc  mov     [rdi+rcx*8], rax
0x18004c700  mov     r8, [rbx+18h]; wchar_t *
0x18004c704  mov     rdx, r15; unsigned __int64
0x18004c707  mov     rcx, rax; wchar_t *
0x18004c70a  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18004c70f  inc     r14d
0x18004c712  mov     rbx, [rbx+28h]
0x18004c716  jmp     short loc_18004C6C8
0x18004c718  xor     ecx, ecx; pAddrInfo
0x18004c71a  call    cs:__imp_FreeAddrInfoW
0x18004c720  mov     rbx, cs:Block
0x18004c727  test    rbx, rbx
0x18004c72a  jz      short loc_18004C75B
0x18004c72c  mov     rax, [rbx]
0x18004c72f  test    rax, rax
0x18004c732  jz      short loc_18004C751
0x18004c734  mov     rcx, rax; Block
0x18004c737  call    cs:__imp_free
0x18004c73d  nop
0x18004c73e  lea     rbx, [rbx+8]
0x18004c742  mov     rax, [rbx]
0x18004c745  test    rax, rax
0x18004c748  jnz     short loc_18004C734
0x18004c74a  mov     rbx, cs:Block
0x18004c751  mov     rcx, rbx; Block
0x18004c754  call    cs:__imp_free
0x18004c75a  nop
0x18004c75b  mov     cs:Block, rdi
0x18004c762  jmp     short $+2
0x18004c764  mov     rcx, [rsp+338h+var_38]
0x18004c76c  xor     rcx, rsp; StackCookie
0x18004c76f  call    __security_check_cookie
0x18004c774  add     rsp, 310h
0x18004c77b  pop     r15
0x18004c77d  pop     r14
0x18004c77f  pop     rdi
0x18004c780  pop     rsi
0x18004c781  pop     rbx
0x18004c782  retn
```
