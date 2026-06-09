# DhcpCMCloseConnectionUnclaimedSocket

- ea: `0x1800aec1c`
- end: `0x1800aee64`
- name: `DhcpCMCloseConnectionUnclaimedSocket`
- size: `584`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800aeab4`
- `0x1800af4c0`
- `0x1800b0d5c`

## callees

- `0x18001ceb4`
- `0x1800aec1c`
- `0x1800cbc3c`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800aec72`
- `WS2_32!WSACloseEvent` at `0x1800aecb9`
- `WS2_32!WSACloseEvent` at `0x1800aecfc`
- `WS2_32!WSACloseEvent` at `0x1800aec72`
- `WS2_32!WSACloseEvent` at `0x1800aecb9`
- `WS2_32!WSACloseEvent` at `0x1800aecfc`
- `WS2_32!__imp_closesocket` at `0x1800aed3a`
- `WS2_32!__imp_closesocket` at `0x1800aed3a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aec82`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aecc9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aed0c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aed4d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aec82`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aecc9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aed0c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aed4d`
- `KERNEL32!EnterCriticalSection` at `0x1800aec43`
- `KERNEL32!EnterCriticalSection` at `0x1800aedae`
- `KERNEL32!EnterCriticalSection` at `0x1800aec43`
- `KERNEL32!EnterCriticalSection` at `0x1800aedae`
- `KERNEL32!LeaveCriticalSection` at `0x1800aed9b`
- `KERNEL32!LeaveCriticalSection` at `0x1800aedcd`
- `KERNEL32!LeaveCriticalSection` at `0x1800aed9b`
- `KERNEL32!LeaveCriticalSection` at `0x1800aedcd`
- `KERNEL32!HeapFree` at `0x1800aede5`
- `KERNEL32!HeapFree` at `0x1800aede5`

## string_xrefs

- `0x1800aec66`: `WSACloseEvent`

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
  lpMem[1] = -1;
  v9 = (void *)lpMem[3];
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
      *(_QWORD *)((char *)&unk_1800FE978 + v4 * 8) = gSocketArray[v11];
    }
    while ( (unsigned int)v11 < (unsigned int)v10 );
  }
  gSocketArray[v10] = 0;
  result = v8;
  gSocketEventTotal = v10;
  return result;
}

```

## disassembly

```asm
0x1800aec1c  mov     [rsp+arg_0], rbx
0x1800aec21  mov     [rsp+arg_8], rbp
0x1800aec26  mov     [rsp+arg_10], rsi
0x1800aec2b  push    rdi
0x1800aec2c  push    r13
0x1800aec2e  push    r14
0x1800aec30  sub     rsp, 20h
0x1800aec34  mov     ebp, [rcx]
0x1800aec36  mov     rbx, rcx
0x1800aec39  mov     rcx, [rcx+10h]
0x1800aec3d  xor     esi, esi
0x1800aec3f  add     rcx, 8; lpCriticalSection
0x1800aec43  call    cs:__imp_EnterCriticalSection
0x1800aec4a  nop     dword ptr [rax+rax+00h]
0x1800aec4f  lea     r14, ds:0[rbp*8]
0x1800aec57  lea     r13, __ImageBase
0x1800aec5e  mov     rcx, [r14+r13+0FEBE0h]; hEvent
0x1800aec66  lea     rdi, aWsacloseevent; "WSACloseEvent"
0x1800aec6d  test    rcx, rcx
0x1800aec70  jz      short loc_1800AECB0
0x1800aec72  call    cs:__imp_WSACloseEvent
0x1800aec79  nop     dword ptr [rax+rax+00h]
0x1800aec7e  test    eax, eax
0x1800aec80  jnz     short loc_1800AECA7
0x1800aec82  call    cs:__imp_WSAGetLastError
0x1800aec89  nop     dword ptr [rax+rax+00h]
0x1800aec8e  mov     r9d, 1F7h
0x1800aec94  lea     rdx, aDhcpcmclosecon_0; "DhcpCMCloseConnectionUnclaimedSocket"
0x1800aec9b  mov     ecx, eax
0x1800aec9d  mov     r8, rdi
0x1800aeca0  mov     esi, eax
0x1800aeca2  call    DhcpPrintFOErrorEx
0x1800aeca7  and     qword ptr [r14+r13+0FEBE0h], 0
0x1800aecb0  mov     rcx, [rbx+28h]; hEvent
0x1800aecb4  test    rcx, rcx
0x1800aecb7  jz      short loc_1800AECF3
0x1800aecb9  call    cs:__imp_WSACloseEvent
0x1800aecc0  nop     dword ptr [rax+rax+00h]
0x1800aecc5  test    eax, eax
0x1800aecc7  jnz     short loc_1800AECEE
0x1800aecc9  call    cs:__imp_WSAGetLastError
0x1800aecd0  nop     dword ptr [rax+rax+00h]
0x1800aecd5  mov     r9d, 1FAh
0x1800aecdb  lea     rdx, aDhcpcmclosecon_0; "DhcpCMCloseConnectionUnclaimedSocket"
0x1800aece2  mov     ecx, eax
0x1800aece4  mov     r8, rdi
0x1800aece7  mov     esi, eax
0x1800aece9  call    DhcpPrintFOErrorEx
0x1800aecee  and     qword ptr [rbx+28h], 0
0x1800aecf3  mov     rcx, [rbx+30h]; hEvent
0x1800aecf7  test    rcx, rcx
0x1800aecfa  jz      short loc_1800AED36
0x1800aecfc  call    cs:__imp_WSACloseEvent
0x1800aed03  nop     dword ptr [rax+rax+00h]
0x1800aed08  test    eax, eax
0x1800aed0a  jnz     short loc_1800AED31
0x1800aed0c  call    cs:__imp_WSAGetLastError
0x1800aed13  nop     dword ptr [rax+rax+00h]
0x1800aed18  mov     r9d, 1FDh
0x1800aed1e  lea     rdx, aDhcpcmclosecon_0; "DhcpCMCloseConnectionUnclaimedSocket"
0x1800aed25  mov     ecx, eax
0x1800aed27  mov     r8, rdi
0x1800aed2a  mov     esi, eax
0x1800aed2c  call    DhcpPrintFOErrorEx
0x1800aed31  and     qword ptr [rbx+30h], 0
0x1800aed36  mov     rcx, [rbx+8]; s
0x1800aed3a  call    cs:__imp_closesocket
0x1800aed41  nop     dword ptr [rax+rax+00h]
0x1800aed46  mov     edi, eax
0x1800aed48  cmp     eax, 0FFFFFFFFh
0x1800aed4b  jnz     short loc_1800AED76
0x1800aed4d  call    cs:__imp_WSAGetLastError
0x1800aed54  nop     dword ptr [rax+rax+00h]
0x1800aed59  mov     r9d, 200h
0x1800aed5f  lea     r8, aClosesocket; "closesocket"
0x1800aed66  mov     ecx, eax
0x1800aed68  lea     rdx, aDhcpcmclosecon_0; "DhcpCMCloseConnectionUnclaimedSocket"
0x1800aed6f  mov     edi, eax
0x1800aed71  call    DhcpPrintFOErrorEx
0x1800aed76  or      qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800aed7b  mov     rcx, [rbx+18h]; lpMem
0x1800aed7f  test    edi, edi
0x1800aed81  cmovz   edi, esi
0x1800aed84  test    rcx, rcx
0x1800aed87  jz      short loc_1800AED93
0x1800aed89  call    ResetAndRestoreInFreePacketPool
0x1800aed8e  and     qword ptr [rbx+18h], 0
0x1800aed93  mov     rcx, [rbx+10h]
0x1800aed97  add     rcx, 8; lpCriticalSection
0x1800aed9b  call    cs:__imp_LeaveCriticalSection
0x1800aeda2  nop     dword ptr [rax+rax+00h]
0x1800aeda7  lea     rcx, gSocketLock; lpCriticalSection
0x1800aedae  call    cs:__imp_EnterCriticalSection
0x1800aedb5  nop     dword ptr [rax+rax+00h]
0x1800aedba  mov     rax, [rbx+10h]
0x1800aedbe  lea     rcx, gSocketLock; lpCriticalSection
0x1800aedc5  and     dword ptr [rax], 0
0x1800aedc8  and     qword ptr [rbx+10h], 0
0x1800aedcd  call    cs:__imp_LeaveCriticalSection
0x1800aedd4  nop     dword ptr [rax+rax+00h]
0x1800aedd9  mov     rcx, cs:gDhcpHeap; hHeap
0x1800aede0  mov     r8, rbx; lpMem
0x1800aede3  xor     edx, edx; dwFlags
0x1800aede5  call    cs:__imp_HeapFree
0x1800aedec  nop     dword ptr [rax+rax+00h]
0x1800aedf1  mov     r8d, cs:gSocketEventTotal
0x1800aedf8  dec     r8d
0x1800aedfb  cmp     ebp, r8d
0x1800aedfe  jnb     short loc_1800AEE38
0x1800aee00  lea     edx, [rbp+1]
0x1800aee03  mov     rax, rva gSocketEventArray[r13+rdx*8]
0x1800aee0b  mov     [r14+r13+0FEBE0h], rax
0x1800aee13  lea     r14, [r14+8]
0x1800aee17  mov     rax, rva gSocketArray[r13+rdx*8]
0x1800aee1f  mov     [rax], ebp
0x1800aee21  mov     ebp, edx
0x1800aee23  mov     rax, rva gSocketArray[r13+rdx*8]
0x1800aee2b  mov     [r14+r13+0FE978h], rax
0x1800aee33  cmp     edx, r8d
0x1800aee36  jb      short loc_1800AEE00
0x1800aee38  and     rva gSocketArray[r13+r8*8], 0
0x1800aee41  mov     eax, edi
0x1800aee43  mov     rbx, [rsp+38h+arg_0]
0x1800aee48  mov     rbp, [rsp+38h+arg_8]
0x1800aee4d  mov     rsi, [rsp+38h+arg_10]
0x1800aee52  mov     cs:gSocketEventTotal, r8d
0x1800aee59  add     rsp, 20h
0x1800aee5d  pop     r14
0x1800aee5f  pop     r13
0x1800aee61  pop     rdi
0x1800aee62  retn
```
