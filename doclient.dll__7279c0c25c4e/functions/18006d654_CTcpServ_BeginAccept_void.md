# CTcpServ::_BeginAccept(void)

- ea: `0x18006d654`
- end: `0x18006d858`
- name: `?_BeginAccept@CTcpServ@@AEAAJXZ`
- size: `516`
- prototype: `__int64 __fastcall(CTcpServ *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006cf48`
- `0x18006d97c`

## callees

- `0x18000933c`
- `0x18006d654`
- `0x18006d860`
- `0x18006db10`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d685`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d70c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d70c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d71f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d71f`
- `WS2_32!WSASocketW` at `0x18006d6f9`
- `WS2_32!WSASocketW` at `0x18006d6f9`
- `WS2_32!__imp_closesocket` at `0x18006d717`
- `WS2_32!__imp_closesocket` at `0x18006d717`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d72f`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d7ca`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d72f`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d7ca`

## string_xrefs

- `0x18006d6ac`: `_core.GetTaskThread().IsCurrentThread()`
- `0x18006d7f3`: `_BeginAccept completed immediately`

## pseudocode

```c
__int64 __fastcall CTcpServ::_BeginAccept(struct COverlappedIoOp **this)
{
  __int64 v2; // rbx
  SOCKET v3; // rax
  SOCKET v4; // r15
  struct COverlappedIoOp *v5; // rbp
  DWORD LastError; // ebx
  int Error; // eax
  unsigned int v8; // ebx
  struct COverlappedIoOp *v9; // rax
  struct COverlappedIoOp *v10; // rdx
  struct COverlappedIoOp *v11; // rcx
  struct COverlappedIoOp *v12; // rax
  int v13; // eax
  unsigned int v15; // r8d
  int g; // [rsp+20h] [rbp-58h]
  struct COverlappedIoOp *v17; // [rsp+38h] [rbp-40h]
  int v18; // [rsp+54h] [rbp-24h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = *((_QWORD *)*this + 1);
  if ( *(_DWORD *)(v2 + 176) != GetCurrentThreadId() )
  {
    LogMessage(
      2u,
      "CTcpServ::_BeginAccept",
      0x85u,
      "TelemetryAssert (%s): %s",
      "_core.GetTaskThread().IsCurrentThread()",
      "Failed");
    DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
  }
  CTcpServ::_CloseAcceptSock((CTcpServ *)this);
  v3 = WSASocketW(23, 1, 6, 0, 0, 1u);
  v4 = (SOCKET)this[4];
  v5 = (struct COverlappedIoOp *)v3;
  if ( v4 != -1 )
  {
    LastError = GetLastError();
    closesocket(v4);
    SetLastError(LastError);
  }
  this[4] = v5;
  if ( v5 == (struct COverlappedIoOp *)-1LL )
  {
    Error = WSAGetLastError();
    if ( Error )
    {
      v8 = (unsigned __int16)Error | 0x80070000;
      if ( Error <= 0 )
        v8 = Error;
    }
    else
    {
      v8 = -2147467259;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TcpServ.cpp",
      (const char *)v8,
      g);
  }
  else
  {
    v9 = this[5];
    *(_OWORD *)v9 = 0;
    *((_OWORD *)v9 + 1) = 0;
    *((_BYTE *)v9 + 40) = 1;
    v10 = this[4];
    v17 = this[5];
    v11 = this[3];
    v12 = this[6];
    v18 = 0;
    if ( ((unsigned int (__fastcall *)(struct COverlappedIoOp *, struct COverlappedIoOp *, struct COverlappedIoOp **, _QWORD, int, int, int *, struct COverlappedIoOp *))v12)(
           v11,
           v10,
           this + 7,
           0,
           144,
           144,
           &v18,
           v17) )
    {
      v8 = 0;
    }
    else
    {
      v13 = WSAGetLastError();
      if ( v13 )
      {
        v8 = (unsigned __int16)v13 | 0x80070000;
        if ( v13 <= 0 )
          v8 = v13;
        if ( v8 == -2147023899 )
          return 0;
      }
      else
      {
        v8 = -2147467259;
      }
    }
    LogResult(3u, "CTcpServ::_BeginAccept", 0x94u, v8, "_BeginAccept completed immediately");
    *((_BYTE *)this[5] + 40) = 0;
    CTcpServ::_AcceptCompletion((CTcpServ *)this, v8, v15, this[5]);
  }
  return v8;
}

```

## disassembly

```asm
0x18006d654  mov     [rsp+arg_8], rbx
0x18006d659  mov     [rsp+arg_10], rbp
0x18006d65e  mov     [rsp+arg_18], rsi
0x18006d663  push    rdi
0x18006d664  push    r14
0x18006d666  push    r15
0x18006d668  sub     rsp, 60h
0x18006d66c  mov     rax, cs:__security_cookie
0x18006d673  xor     rax, rsp
0x18006d676  mov     [rsp+78h+var_20], rax
0x18006d67b  mov     rax, [rcx]
0x18006d67e  mov     rsi, rcx
0x18006d681  mov     rbx, [rax+8]
0x18006d685  call    cs:__imp_GetCurrentThreadId
0x18006d68b  cmp     [rbx+0B0h], eax
0x18006d691  jz      short loc_18006D6D3
0x18006d693  lea     rax, aFailed; "Failed"
0x18006d69a  mov     r8d, 85h; unsigned int
0x18006d6a0  mov     qword ptr [rsp+78h+dwFlags], rax
0x18006d6a5  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x18006d6ac  lea     rax, aCoreGettaskthr; "_core.GetTaskThread().IsCurrentThread()"
0x18006d6b3  mov     ecx, 2; unsigned __int8
0x18006d6b8  lea     rdx, aCtcpservBegina; "CTcpServ::_BeginAccept"
0x18006d6bf  mov     qword ptr [rsp+78h+g], rax
0x18006d6c4  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18006d6c9  or      ecx, 0FFFFFFFFh; unsigned int
0x18006d6cc  mov     edx, ecx; unsigned int
0x18006d6ce  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x18006d6d3  mov     rcx, rsi; this
0x18006d6d6  call    ?_CloseAcceptSock@CTcpServ@@AEAAXXZ; CTcpServ::_CloseAcceptSock(void)
0x18006d6db  mov     r14d, 1
0x18006d6e1  xor     edi, edi
0x18006d6e3  mov     [rsp+78h+dwFlags], r14d; dwFlags
0x18006d6e8  xor     r9d, r9d; lpProtocolInfo
0x18006d6eb  mov     edx, r14d; type
0x18006d6ee  mov     [rsp+78h+g], edi; int
0x18006d6f2  lea     r8d, [r14+5]; protocol
0x18006d6f6  lea     ecx, [rdi+17h]; af
0x18006d6f9  call    cs:__imp_WSASocketW
0x18006d6ff  mov     r15, [rsi+20h]
0x18006d703  mov     rbp, rax
0x18006d706  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18006d70a  jz      short loc_18006D725
0x18006d70c  call    cs:__imp_GetLastError
0x18006d712  mov     rcx, r15; s
0x18006d715  mov     ebx, eax
0x18006d717  call    cs:__imp_closesocket
0x18006d71d  mov     ecx, ebx; dwErrCode
0x18006d71f  call    cs:__imp_SetLastError
0x18006d725  mov     [rsi+20h], rbp
0x18006d729  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18006d72d  jnz     short loc_18006D774
0x18006d72f  call    cs:__imp_WSAGetLastError
0x18006d735  test    eax, eax
0x18006d737  jz      short loc_18006D751
0x18006d739  movzx   ebx, ax
0x18006d73c  or      ebx, 80070000h
0x18006d742  test    eax, eax
0x18006d744  cmovle  ebx, eax
0x18006d747  test    ebx, ebx
0x18006d749  jns     loc_18006D82F
0x18006d74f  jmp     short loc_18006D756
0x18006d751  mov     ebx, 80004005h
0x18006d756  mov     rcx, [rsp+78h]; this
0x18006d75b  lea     r8, aCW1SSrcDeliver_12; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18006d762  mov     r9d, ebx; char *
0x18006d765  mov     edx, 8Bh; void *
0x18006d76a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d76f  jmp     loc_18006D82F
0x18006d774  mov     rax, [rsi+28h]
0x18006d778  lea     r8, [rsi+38h]
0x18006d77c  xorps   xmm0, xmm0
0x18006d77f  xor     r9d, r9d
0x18006d782  movups  xmmword ptr [rax], xmm0
0x18006d785  movups  xmmword ptr [rax+10h], xmm0
0x18006d789  xchg    r14b, [rax+28h]
0x18006d78d  mov     rcx, [rsi+28h]
0x18006d791  lea     rax, [rsp+78h+var_24]
0x18006d796  mov     rdx, [rsi+20h]
0x18006d79a  mov     [rsp+78h+var_40], rcx
0x18006d79f  mov     rcx, [rsi+18h]
0x18006d7a3  mov     [rsp+78h+var_48], rax
0x18006d7a8  mov     eax, 90h
0x18006d7ad  mov     [rsp+78h+dwFlags], eax
0x18006d7b1  mov     [rsp+78h+g], eax
0x18006d7b5  mov     rax, [rsi+30h]
0x18006d7b9  mov     [rsp+78h+var_24], edi
0x18006d7bd  call    _guard_dispatch_icall
0x18006d7c2  test    eax, eax
0x18006d7c4  jz      short loc_18006D7CA
0x18006d7c6  mov     ebx, edi
0x18006d7c8  jmp     short loc_18006D7F3
0x18006d7ca  call    cs:__imp_WSAGetLastError
0x18006d7d0  test    eax, eax
0x18006d7d2  jz      short loc_18006D7EE
0x18006d7d4  movzx   ebx, ax
0x18006d7d7  or      ebx, 80070000h
0x18006d7dd  test    eax, eax
0x18006d7df  cmovle  ebx, eax
0x18006d7e2  cmp     ebx, 800703E5h
0x18006d7e8  jnz     short loc_18006D7F3
0x18006d7ea  xor     eax, eax
0x18006d7ec  jmp     short loc_18006D831
0x18006d7ee  mov     ebx, 80004005h
0x18006d7f3  lea     rax, aBeginacceptCom; "_BeginAccept completed immediately"
0x18006d7fa  mov     r9d, ebx; int
0x18006d7fd  mov     r8d, 94h; unsigned int
0x18006d803  mov     qword ptr [rsp+78h+g], rax; char *
0x18006d808  lea     rdx, aCtcpservBegina; "CTcpServ::_BeginAccept"
0x18006d80f  mov     ecx, 3; unsigned __int8
0x18006d814  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x18006d819  mov     rdx, [rsi+28h]
0x18006d81d  mov     rcx, rsi; this
0x18006d820  xchg    dil, [rdx+28h]
0x18006d824  mov     r9, [rsi+28h]; struct COverlappedIoOp *
0x18006d828  mov     edx, ebx; int
0x18006d82a  call    ?_AcceptCompletion@CTcpServ@@AEAAXJIPEAVCOverlappedIoOp@@@Z; CTcpServ::_AcceptCompletion(long,uint,COverlappedIoOp *)
0x18006d82f  mov     eax, ebx
0x18006d831  mov     rcx, [rsp+78h+var_20]
0x18006d836  xor     rcx, rsp; StackCookie
0x18006d839  call    __security_check_cookie
0x18006d83e  lea     r11, [rsp+78h+var_18]
0x18006d843  mov     rbx, [r11+28h]
0x18006d847  mov     rbp, [r11+30h]
0x18006d84b  mov     rsi, [r11+38h]
0x18006d84f  mov     rsp, r11
0x18006d852  pop     r15
0x18006d854  pop     r14
0x18006d856  pop     rdi
0x18006d857  retn
```
