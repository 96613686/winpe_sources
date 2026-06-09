# DeleteSocketFromGArray

- ea: `0x1800ae11c`
- end: `0x1800ae350`
- name: `DeleteSocketFromGArray`
- size: `564`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800af4c0`
- `0x1800afd9c`

## callees

- `0x18001ceb4`
- `0x1800ae11c`
- `0x1800cbc3c`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800ae1c7`
- `WS2_32!WSACloseEvent` at `0x1800ae207`
- `WS2_32!WSACloseEvent` at `0x1800ae24c`
- `WS2_32!WSACloseEvent` at `0x1800ae1c7`
- `WS2_32!WSACloseEvent` at `0x1800ae207`
- `WS2_32!WSACloseEvent` at `0x1800ae24c`
- `WS2_32!__imp_closesocket` at `0x1800ae28c`
- `WS2_32!__imp_closesocket` at `0x1800ae28c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae1d7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae217`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae25c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae29f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae1d7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae217`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae25c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae29f`
- `KERNEL32!EnterCriticalSection` at `0x1800ae1b3`
- `KERNEL32!EnterCriticalSection` at `0x1800ae2ff`
- `KERNEL32!EnterCriticalSection` at `0x1800ae1b3`
- `KERNEL32!EnterCriticalSection` at `0x1800ae2ff`
- `KERNEL32!LeaveCriticalSection` at `0x1800ae2ec`
- `KERNEL32!LeaveCriticalSection` at `0x1800ae31e`
- `KERNEL32!LeaveCriticalSection` at `0x1800ae2ec`
- `KERNEL32!LeaveCriticalSection` at `0x1800ae31e`
- `KERNEL32!HeapFree` at `0x1800ae336`
- `KERNEL32!HeapFree` at `0x1800ae336`

## string_xrefs

- `0x1800ae1e9`: `WSACloseEvent`
- `0x1800ae229`: `WSACloseEvent`
- `0x1800ae26e`: `WSACloseEvent`
- `0x1800ae1f2`: `DeleteSocketFromGArray`
- `0x1800ae232`: `DeleteSocketFromGArray`
- `0x1800ae277`: `DeleteSocketFromGArray`
- `0x1800ae2ba`: `DeleteSocketFromGArray`

## pseudocode

```c
__int64 __fastcall DeleteSocketFromGArray(unsigned int a1)
{
  unsigned int v1; // r9d
  __int64 v2; // r8
  __int64 v3; // r10
  __int64 v4; // rbx
  HANDLE v5; // rdi
  __int64 v6; // rdx
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  unsigned int Error; // eax
  void *v9; // rcx
  unsigned int v10; // eax
  void *v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // edi
  void *v14; // rcx

  v1 = a1;
  v2 = gSocketEventTotal - 1;
  v3 = a1;
  v4 = gSocketArray[v3];
  v5 = gSocketEventArray[v3];
  if ( a1 < (unsigned int)v2 )
  {
    do
    {
      v6 = v1 + 1;
      gSocketEventArray[v3++] = gSocketEventArray[v6];
      *(_DWORD *)gSocketArray[v6] = v1++;
      *(_QWORD *)((char *)&unk_1800FE978 + v3 * 8) = gSocketArray[v6];
    }
    while ( (unsigned int)v6 < (unsigned int)v2 );
  }
  gSocketArray[v2] = 0;
  gSocketEventArray[v2] = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v4 + 16) + 8LL);
  gSocketEventTotal = v2;
  EnterCriticalSection(v7);
  if ( v5 && !WSACloseEvent(v5) )
  {
    Error = WSAGetLastError();
    DhcpPrintFOErrorEx(Error, "DeleteSocketFromGArray", "WSACloseEvent", 139);
  }
  v9 = *(void **)(v4 + 40);
  if ( v9 )
  {
    if ( !WSACloseEvent(v9) )
    {
      v10 = WSAGetLastError();
      DhcpPrintFOErrorEx(v10, "DeleteSocketFromGArray", "WSACloseEvent", 142);
    }
    *(_QWORD *)(v4 + 40) = 0;
  }
  v11 = *(void **)(v4 + 48);
  if ( v11 )
  {
    if ( !WSACloseEvent(v11) )
    {
      v12 = WSAGetLastError();
      DhcpPrintFOErrorEx(v12, "DeleteSocketFromGArray", "WSACloseEvent", 145);
    }
    *(_QWORD *)(v4 + 48) = 0;
  }
  v13 = closesocket(*(_QWORD *)(v4 + 8));
  if ( v13 == -1 )
  {
    v13 = WSAGetLastError();
    DhcpPrintFOErrorEx(v13, "DeleteSocketFromGArray", "closesocket", 148);
  }
  *(_QWORD *)(v4 + 8) = -1;
  v14 = *(void **)(v4 + 24);
  if ( v14 )
  {
    ResetAndRestoreInFreePacketPool(v14);
    *(_QWORD *)(v4 + 24) = 0;
    *(_DWORD *)(v4 + 32) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 16) + 8LL));
  EnterCriticalSection(&gSocketLock);
  **(_DWORD **)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 16) = 0;
  LeaveCriticalSection(&gSocketLock);
  HeapFree(gDhcpHeap, 0, (LPVOID)v4);
  return v13;
}

```

## disassembly

```asm
0x1800ae11c  mov     [rsp+arg_0], rbx
0x1800ae121  push    rdi
0x1800ae122  sub     rsp, 20h
0x1800ae126  mov     r8d, cs:gSocketEventTotal
0x1800ae12d  lea     r11, __ImageBase
0x1800ae134  mov     r9d, ecx
0x1800ae137  dec     r8d
0x1800ae13a  lea     r10, ds:0[r9*8]
0x1800ae142  mov     rbx, [r10+r11+0FE980h]
0x1800ae14a  mov     rdi, [r10+r11+0FEBE0h]
0x1800ae152  cmp     ecx, r8d
0x1800ae155  jnb     short loc_1800AE192
0x1800ae157  lea     edx, [r9+1]
0x1800ae15b  mov     rax, rva gSocketEventArray[r11+rdx*8]
0x1800ae163  mov     [r10+r11+0FEBE0h], rax
0x1800ae16b  lea     r10, [r10+8]
0x1800ae16f  mov     rax, rva gSocketArray[r11+rdx*8]
0x1800ae177  mov     [rax], r9d
0x1800ae17a  mov     r9d, edx
0x1800ae17d  mov     rax, rva gSocketArray[r11+rdx*8]
0x1800ae185  mov     [r10+r11+0FE978h], rax
0x1800ae18d  cmp     edx, r8d
0x1800ae190  jb      short loc_1800AE157
0x1800ae192  and     rva gSocketArray[r11+r8*8], 0
0x1800ae19b  and     rva gSocketEventArray[r11+r8*8], 0
0x1800ae1a4  mov     rcx, [rbx+10h]
0x1800ae1a8  add     rcx, 8; lpCriticalSection
0x1800ae1ac  mov     cs:gSocketEventTotal, r8d
0x1800ae1b3  call    cs:__imp_EnterCriticalSection
0x1800ae1ba  nop     dword ptr [rax+rax+00h]
0x1800ae1bf  test    rdi, rdi
0x1800ae1c2  jz      short loc_1800AE1FE
0x1800ae1c4  mov     rcx, rdi; hEvent
0x1800ae1c7  call    cs:__imp_WSACloseEvent
0x1800ae1ce  nop     dword ptr [rax+rax+00h]
0x1800ae1d3  test    eax, eax
0x1800ae1d5  jnz     short loc_1800AE1FE
0x1800ae1d7  call    cs:__imp_WSAGetLastError
0x1800ae1de  nop     dword ptr [rax+rax+00h]
0x1800ae1e3  mov     r9d, 8Bh
0x1800ae1e9  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800ae1f0  mov     ecx, eax
0x1800ae1f2  lea     rdx, aDeletesocketfr; "DeleteSocketFromGArray"
0x1800ae1f9  call    DhcpPrintFOErrorEx
0x1800ae1fe  mov     rcx, [rbx+28h]; hEvent
0x1800ae202  test    rcx, rcx
0x1800ae205  jz      short loc_1800AE243
0x1800ae207  call    cs:__imp_WSACloseEvent
0x1800ae20e  nop     dword ptr [rax+rax+00h]
0x1800ae213  test    eax, eax
0x1800ae215  jnz     short loc_1800AE23E
0x1800ae217  call    cs:__imp_WSAGetLastError
0x1800ae21e  nop     dword ptr [rax+rax+00h]
0x1800ae223  mov     r9d, 8Eh
0x1800ae229  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800ae230  mov     ecx, eax
0x1800ae232  lea     rdx, aDeletesocketfr; "DeleteSocketFromGArray"
0x1800ae239  call    DhcpPrintFOErrorEx
0x1800ae23e  and     qword ptr [rbx+28h], 0
0x1800ae243  mov     rcx, [rbx+30h]; hEvent
0x1800ae247  test    rcx, rcx
0x1800ae24a  jz      short loc_1800AE288
0x1800ae24c  call    cs:__imp_WSACloseEvent
0x1800ae253  nop     dword ptr [rax+rax+00h]
0x1800ae258  test    eax, eax
0x1800ae25a  jnz     short loc_1800AE283
0x1800ae25c  call    cs:__imp_WSAGetLastError
0x1800ae263  nop     dword ptr [rax+rax+00h]
0x1800ae268  mov     r9d, 91h
0x1800ae26e  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800ae275  mov     ecx, eax
0x1800ae277  lea     rdx, aDeletesocketfr; "DeleteSocketFromGArray"
0x1800ae27e  call    DhcpPrintFOErrorEx
0x1800ae283  and     qword ptr [rbx+30h], 0
0x1800ae288  mov     rcx, [rbx+8]; s
0x1800ae28c  call    cs:__imp_closesocket
0x1800ae293  nop     dword ptr [rax+rax+00h]
0x1800ae298  mov     edi, eax
0x1800ae29a  cmp     eax, 0FFFFFFFFh
0x1800ae29d  jnz     short loc_1800AE2C8
0x1800ae29f  call    cs:__imp_WSAGetLastError
0x1800ae2a6  nop     dword ptr [rax+rax+00h]
0x1800ae2ab  mov     r9d, 94h
0x1800ae2b1  lea     r8, aClosesocket; "closesocket"
0x1800ae2b8  mov     ecx, eax
0x1800ae2ba  lea     rdx, aDeletesocketfr; "DeleteSocketFromGArray"
0x1800ae2c1  mov     edi, eax
0x1800ae2c3  call    DhcpPrintFOErrorEx
0x1800ae2c8  or      qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800ae2cd  mov     rcx, [rbx+18h]; lpMem
0x1800ae2d1  test    rcx, rcx
0x1800ae2d4  jz      short loc_1800AE2E4
0x1800ae2d6  call    ResetAndRestoreInFreePacketPool
0x1800ae2db  and     qword ptr [rbx+18h], 0
0x1800ae2e0  and     dword ptr [rbx+20h], 0
0x1800ae2e4  mov     rcx, [rbx+10h]
0x1800ae2e8  add     rcx, 8; lpCriticalSection
0x1800ae2ec  call    cs:__imp_LeaveCriticalSection
0x1800ae2f3  nop     dword ptr [rax+rax+00h]
0x1800ae2f8  lea     rcx, gSocketLock; lpCriticalSection
0x1800ae2ff  call    cs:__imp_EnterCriticalSection
0x1800ae306  nop     dword ptr [rax+rax+00h]
0x1800ae30b  mov     rax, [rbx+10h]
0x1800ae30f  lea     rcx, gSocketLock; lpCriticalSection
0x1800ae316  and     dword ptr [rax], 0
0x1800ae319  and     qword ptr [rbx+10h], 0
0x1800ae31e  call    cs:__imp_LeaveCriticalSection
0x1800ae325  nop     dword ptr [rax+rax+00h]
0x1800ae32a  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ae331  mov     r8, rbx; lpMem
0x1800ae334  xor     edx, edx; dwFlags
0x1800ae336  call    cs:__imp_HeapFree
0x1800ae33d  nop     dword ptr [rax+rax+00h]
0x1800ae342  mov     rbx, [rsp+28h+arg_0]
0x1800ae347  mov     eax, edi
0x1800ae349  add     rsp, 20h
0x1800ae34d  pop     rdi
0x1800ae34e  retn
```
