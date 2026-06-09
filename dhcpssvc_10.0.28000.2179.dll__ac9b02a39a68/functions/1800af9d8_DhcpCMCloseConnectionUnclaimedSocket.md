# DhcpCMCloseConnectionUnclaimedSocket

- ea: `0x1800af9d8`
- end: `0x1800afc38`
- name: `DhcpCMCloseConnectionUnclaimedSocket`
- size: `608`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800af86c`
- `0x1800b02c0`
- `0x1800b1b78`

## callees

- `0x18001c45c`
- `0x1800af9d8`
- `0x1800cccf4`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800afa2e`
- `WS2_32!WSACloseEvent` at `0x1800afa78`
- `WS2_32!WSACloseEvent` at `0x1800afabe`
- `WS2_32!WSACloseEvent` at `0x1800afa2e`
- `WS2_32!WSACloseEvent` at `0x1800afa78`
- `WS2_32!WSACloseEvent` at `0x1800afabe`
- `WS2_32!__imp_closesocket` at `0x1800afaff`
- `WS2_32!__imp_closesocket` at `0x1800afaff`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afa3e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afa88`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aface`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afb12`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afa3e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afa88`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aface`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afb12`
- `KERNEL32!EnterCriticalSection` at `0x1800af9ff`
- `KERNEL32!EnterCriticalSection` at `0x1800afb79`
- `KERNEL32!EnterCriticalSection` at `0x1800af9ff`
- `KERNEL32!EnterCriticalSection` at `0x1800afb79`
- `KERNEL32!LeaveCriticalSection` at `0x1800afb66`
- `KERNEL32!LeaveCriticalSection` at `0x1800afb9e`
- `KERNEL32!LeaveCriticalSection` at `0x1800afb66`
- `KERNEL32!LeaveCriticalSection` at `0x1800afb9e`
- `KERNEL32!HeapFree` at `0x1800afbb6`
- `KERNEL32!HeapFree` at `0x1800afbb6`

## string_xrefs

- `0x1800afa22`: `WSACloseEvent`

## pseudocode

```c
__int64 __fastcall DhcpCMCloseConnectionUnclaimedSocket(_QWORD *lpMem)
{
  __int64 v1; // rbp
  unsigned int Error; // esi
  __int64 v4; // r14
  HANDLE v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  unsigned int v8; // edi
  void *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 result; // rax

  v1 = *(unsigned int *)lpMem;
  Error = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(lpMem[2] + 8LL));
  v4 = v1;
  v5 = gSocketEventArray[v1];
  if ( v5 )
  {
    if ( !WSACloseEvent(v5) )
    {
      Error = WSAGetLastError();
      DhcpPrintFOErrorEx(Error, "DhcpCMCloseConnectionUnclaimedSocket", "WSACloseEvent", 503);
    }
    gSocketEventArray[v4] = 0;
  }
  v6 = (void *)lpMem[5];
  if ( v6 )
  {
    if ( !WSACloseEvent(v6) )
    {
      Error = WSAGetLastError();
      DhcpPrintFOErrorEx(Error, "DhcpCMCloseConnectionUnclaimedSocket", "WSACloseEvent", 506);
    }
    lpMem[5] = 0;
  }
  v7 = (void *)lpMem[6];
  if ( v7 )
  {
    if ( !WSACloseEvent(v7) )
    {
      Error = WSAGetLastError();
      DhcpPrintFOErrorEx(Error, "DhcpCMCloseConnectionUnclaimedSocket", "WSACloseEvent", 509);
    }
    lpMem[6] = 0;
  }
  v8 = closesocket(lpMem[1]);
  if ( v8 == -1 )
  {
    v8 = WSAGetLastError();
    DhcpPrintFOErrorEx(v8, "DhcpCMCloseConnectionUnclaimedSocket", "closesocket", 512);
  }
  v9 = (void *)lpMem[3];
  lpMem[1] = -1;
  if ( !v8 )
    v8 = Error;
  if ( v9 )
  {
    ResetAndRestoreInFreePacketPool(v9);
    lpMem[3] = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem[2] + 8LL));
  EnterCriticalSection(&gSocketLock);
  *(_DWORD *)lpMem[2] = 0;
  lpMem[2] = 0;
  LeaveCriticalSection(&gSocketLock);
  HeapFree(gDhcpHeap, 0, lpMem);
  v10 = gSocketEventTotal - 1;
  if ( (unsigned int)v1 < (unsigned int)v10 )
  {
    do
    {
      v11 = (unsigned int)(v1 + 1);
      gSocketEventArray[v4++] = gSocketEventArray[v11];
      *(_DWORD *)gSocketArray[v11] = v1;
      LODWORD(v1) = v1 + 1;
      *(_QWORD *)((char *)&unk_1801003B8 + v4 * 8) = gSocketArray[v11];
    }
    while ( (unsigned int)v11 < (unsigned int)v10 );
  }
  result = v8;
  gSocketEventTotal = v10;
  gSocketArray[v10] = 0;
  return result;
}

```

## disassembly

```asm
0x1800af9d8  mov     [rsp+arg_0], rbx
0x1800af9dd  mov     [rsp+arg_8], rbp
0x1800af9e2  mov     [rsp+arg_10], rsi
0x1800af9e7  push    rdi
0x1800af9e8  push    r12
0x1800af9ea  push    r14
0x1800af9ec  sub     rsp, 20h
0x1800af9f0  mov     ebp, [rcx]
0x1800af9f2  mov     rbx, rcx
0x1800af9f5  mov     rcx, [rcx+10h]
0x1800af9f9  xor     esi, esi
0x1800af9fb  add     rcx, 8; lpCriticalSection
0x1800af9ff  call    cs:__imp_EnterCriticalSection
0x1800afa06  nop     dword ptr [rax+rax+00h]
0x1800afa0b  lea     r14, ds:0[rbp*8]
0x1800afa13  lea     r12, __ImageBase
0x1800afa1a  mov     rcx, [r14+r12+100BE0h]; hEvent
0x1800afa22  lea     rdi, aWsacloseevent; "WSACloseEvent"
0x1800afa29  test    rcx, rcx
0x1800afa2c  jz      short loc_1800AFA6F
0x1800afa2e  call    cs:__imp_WSACloseEvent
0x1800afa35  nop     dword ptr [rax+rax+00h]
0x1800afa3a  test    eax, eax
0x1800afa3c  jnz     short loc_1800AFA63
0x1800afa3e  call    cs:__imp_WSAGetLastError
0x1800afa45  nop     dword ptr [rax+rax+00h]
0x1800afa4a  mov     r9d, 1F7h
0x1800afa50  lea     rdx, aDhcpcmclosecon_0; "DhcpCMCloseConnectionUnclaimedSocket"
0x1800afa57  mov     ecx, eax
0x1800afa59  mov     r8, rdi
0x1800afa5c  mov     esi, eax
0x1800afa5e  call    DhcpPrintFOErrorEx
0x1800afa63  mov     qword ptr [r14+r12+100BE0h], 0
0x1800afa6f  mov     rcx, [rbx+28h]; hEvent
0x1800afa73  test    rcx, rcx
0x1800afa76  jz      short loc_1800AFAB5
0x1800afa78  call    cs:__imp_WSACloseEvent
0x1800afa7f  nop     dword ptr [rax+rax+00h]
0x1800afa84  test    eax, eax
0x1800afa86  jnz     short loc_1800AFAAD
0x1800afa88  call    cs:__imp_WSAGetLastError
0x1800afa8f  nop     dword ptr [rax+rax+00h]
0x1800afa94  mov     r9d, 1FAh
0x1800afa9a  lea     rdx, aDhcpcmclosecon_0; "DhcpCMCloseConnectionUnclaimedSocket"
0x1800afaa1  mov     ecx, eax
0x1800afaa3  mov     r8, rdi
0x1800afaa6  mov     esi, eax
0x1800afaa8  call    DhcpPrintFOErrorEx
0x1800afaad  mov     qword ptr [rbx+28h], 0
0x1800afab5  mov     rcx, [rbx+30h]; hEvent
0x1800afab9  test    rcx, rcx
0x1800afabc  jz      short loc_1800AFAFB
0x1800afabe  call    cs:__imp_WSACloseEvent
0x1800afac5  nop     dword ptr [rax+rax+00h]
0x1800afaca  test    eax, eax
0x1800afacc  jnz     short loc_1800AFAF3
0x1800aface  call    cs:__imp_WSAGetLastError
0x1800afad5  nop     dword ptr [rax+rax+00h]
0x1800afada  mov     r9d, 1FDh
0x1800afae0  lea     rdx, aDhcpcmclosecon_0; "DhcpCMCloseConnectionUnclaimedSocket"
0x1800afae7  mov     ecx, eax
0x1800afae9  mov     r8, rdi
0x1800afaec  mov     esi, eax
0x1800afaee  call    DhcpPrintFOErrorEx
0x1800afaf3  mov     qword ptr [rbx+30h], 0
0x1800afafb  mov     rcx, [rbx+8]; s
0x1800afaff  call    cs:__imp_closesocket
0x1800afb06  nop     dword ptr [rax+rax+00h]
0x1800afb0b  mov     edi, eax
0x1800afb0d  cmp     eax, 0FFFFFFFFh
0x1800afb10  jnz     short loc_1800AFB3B
0x1800afb12  call    cs:__imp_WSAGetLastError
0x1800afb19  nop     dword ptr [rax+rax+00h]
0x1800afb1e  mov     r9d, 200h
0x1800afb24  lea     r8, aClosesocket; "closesocket"
0x1800afb2b  mov     ecx, eax
0x1800afb2d  lea     rdx, aDhcpcmclosecon_0; "DhcpCMCloseConnectionUnclaimedSocket"
0x1800afb34  mov     edi, eax
0x1800afb36  call    DhcpPrintFOErrorEx
0x1800afb3b  mov     rcx, [rbx+18h]; lpMem
0x1800afb3f  test    edi, edi
0x1800afb41  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800afb49  cmovz   edi, esi
0x1800afb4c  test    rcx, rcx
0x1800afb4f  jz      short loc_1800AFB5E
0x1800afb51  call    ResetAndRestoreInFreePacketPool
0x1800afb56  mov     qword ptr [rbx+18h], 0
0x1800afb5e  mov     rcx, [rbx+10h]
0x1800afb62  add     rcx, 8; lpCriticalSection
0x1800afb66  call    cs:__imp_LeaveCriticalSection
0x1800afb6d  nop     dword ptr [rax+rax+00h]
0x1800afb72  lea     rcx, gSocketLock; lpCriticalSection
0x1800afb79  call    cs:__imp_EnterCriticalSection
0x1800afb80  nop     dword ptr [rax+rax+00h]
0x1800afb85  mov     rax, [rbx+10h]
0x1800afb89  lea     rcx, gSocketLock; lpCriticalSection
0x1800afb90  mov     dword ptr [rax], 0
0x1800afb96  mov     qword ptr [rbx+10h], 0
0x1800afb9e  call    cs:__imp_LeaveCriticalSection
0x1800afba5  nop     dword ptr [rax+rax+00h]
0x1800afbaa  mov     rcx, cs:gDhcpHeap; hHeap
0x1800afbb1  mov     r8, rbx; lpMem
0x1800afbb4  xor     edx, edx; dwFlags
0x1800afbb6  call    cs:__imp_HeapFree
0x1800afbbd  nop     dword ptr [rax+rax+00h]
0x1800afbc2  mov     r8d, cs:gSocketEventTotal
0x1800afbc9  dec     r8d
0x1800afbcc  cmp     ebp, r8d
0x1800afbcf  jnb     short loc_1800AFC09
0x1800afbd1  lea     edx, [rbp+1]
0x1800afbd4  mov     rax, rva gSocketEventArray[r12+rdx*8]
0x1800afbdc  mov     [r14+r12+100BE0h], rax
0x1800afbe4  lea     r14, [r14+8]
0x1800afbe8  mov     rax, rva gSocketArray[r12+rdx*8]
0x1800afbf0  mov     [rax], ebp
0x1800afbf2  mov     ebp, edx
0x1800afbf4  mov     rax, rva gSocketArray[r12+rdx*8]
0x1800afbfc  mov     [r14+r12+1003B8h], rax
0x1800afc04  cmp     edx, r8d
0x1800afc07  jb      short loc_1800AFBD1
0x1800afc09  mov     rbx, [rsp+38h+arg_0]
0x1800afc0e  mov     eax, edi
0x1800afc10  mov     rbp, [rsp+38h+arg_8]
0x1800afc15  mov     rsi, [rsp+38h+arg_10]
0x1800afc1a  mov     cs:gSocketEventTotal, r8d
0x1800afc21  mov     rva gSocketArray[r12+r8*8], 0
0x1800afc2d  add     rsp, 20h
0x1800afc31  pop     r14
0x1800afc33  pop     r12
0x1800afc35  pop     rdi
0x1800afc36  retn
```
