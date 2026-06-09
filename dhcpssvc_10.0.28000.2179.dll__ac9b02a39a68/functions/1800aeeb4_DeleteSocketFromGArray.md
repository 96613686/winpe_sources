# DeleteSocketFromGArray

- ea: `0x1800aeeb4`
- end: `0x1800af103`
- name: `DeleteSocketFromGArray`
- size: `591`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800b02c0`
- `0x1800b0bb4`

## callees

- `0x18001c45c`
- `0x1800aeeb4`
- `0x1800cccf4`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800aef65`
- `WS2_32!WSACloseEvent` at `0x1800aefa5`
- `WS2_32!WSACloseEvent` at `0x1800aefed`
- `WS2_32!WSACloseEvent` at `0x1800aef65`
- `WS2_32!WSACloseEvent` at `0x1800aefa5`
- `WS2_32!WSACloseEvent` at `0x1800aefed`
- `WS2_32!__imp_closesocket` at `0x1800af030`
- `WS2_32!__imp_closesocket` at `0x1800af030`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aef75`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aefb5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aeffd`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af043`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aef75`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aefb5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aeffd`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af043`
- `KERNEL32!EnterCriticalSection` at `0x1800aef51`
- `KERNEL32!EnterCriticalSection` at `0x1800af0ac`
- `KERNEL32!EnterCriticalSection` at `0x1800aef51`
- `KERNEL32!EnterCriticalSection` at `0x1800af0ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800af099`
- `KERNEL32!LeaveCriticalSection` at `0x1800af0d1`
- `KERNEL32!LeaveCriticalSection` at `0x1800af099`
- `KERNEL32!LeaveCriticalSection` at `0x1800af0d1`
- `KERNEL32!HeapFree` at `0x1800af0e9`
- `KERNEL32!HeapFree` at `0x1800af0e9`

## string_xrefs

- `0x1800aef87`: `WSACloseEvent`
- `0x1800aefc7`: `WSACloseEvent`
- `0x1800af00f`: `WSACloseEvent`
- `0x1800aef90`: `DeleteSocketFromGArray`
- `0x1800aefd0`: `DeleteSocketFromGArray`
- `0x1800af018`: `DeleteSocketFromGArray`
- `0x1800af05e`: `DeleteSocketFromGArray`

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
      *(_QWORD *)((char *)&unk_1801003B8 + v3 * 8) = gSocketArray[v6];
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
  v14 = *(void **)(v4 + 24);
  *(_QWORD *)(v4 + 8) = -1;
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
0x1800aeeb4  mov     [rsp+arg_0], rbx
0x1800aeeb9  push    rdi
0x1800aeeba  sub     rsp, 20h
0x1800aeebe  mov     r8d, cs:gSocketEventTotal
0x1800aeec5  lea     r11, __ImageBase
0x1800aeecc  mov     r9d, ecx
0x1800aeecf  dec     r8d
0x1800aeed2  lea     r10, ds:0[r9*8]
0x1800aeeda  mov     rbx, [r10+r11+1003C0h]
0x1800aeee2  mov     rdi, [r10+r11+100BE0h]
0x1800aeeea  cmp     ecx, r8d
0x1800aeeed  jnb     short loc_1800AEF2A
0x1800aeeef  lea     edx, [r9+1]
0x1800aeef3  mov     rax, rva gSocketEventArray[r11+rdx*8]
0x1800aeefb  mov     [r10+r11+100BE0h], rax
0x1800aef03  lea     r10, [r10+8]
0x1800aef07  mov     rax, rva gSocketArray[r11+rdx*8]
0x1800aef0f  mov     [rax], r9d
0x1800aef12  mov     r9d, edx
0x1800aef15  mov     rax, rva gSocketArray[r11+rdx*8]
0x1800aef1d  mov     [r10+r11+1003B8h], rax
0x1800aef25  cmp     edx, r8d
0x1800aef28  jb      short loc_1800AEEEF
0x1800aef2a  mov     rva gSocketArray[r11+r8*8], 0
0x1800aef36  mov     rva gSocketEventArray[r11+r8*8], 0
0x1800aef42  mov     rcx, [rbx+10h]
0x1800aef46  add     rcx, 8; lpCriticalSection
0x1800aef4a  mov     cs:gSocketEventTotal, r8d
0x1800aef51  call    cs:__imp_EnterCriticalSection
0x1800aef58  nop     dword ptr [rax+rax+00h]
0x1800aef5d  test    rdi, rdi
0x1800aef60  jz      short loc_1800AEF9C
0x1800aef62  mov     rcx, rdi; hEvent
0x1800aef65  call    cs:__imp_WSACloseEvent
0x1800aef6c  nop     dword ptr [rax+rax+00h]
0x1800aef71  test    eax, eax
0x1800aef73  jnz     short loc_1800AEF9C
0x1800aef75  call    cs:__imp_WSAGetLastError
0x1800aef7c  nop     dword ptr [rax+rax+00h]
0x1800aef81  mov     r9d, 8Bh
0x1800aef87  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800aef8e  mov     ecx, eax
0x1800aef90  lea     rdx, aDeletesocketfr; "DeleteSocketFromGArray"
0x1800aef97  call    DhcpPrintFOErrorEx
0x1800aef9c  mov     rcx, [rbx+28h]; hEvent
0x1800aefa0  test    rcx, rcx
0x1800aefa3  jz      short loc_1800AEFE4
0x1800aefa5  call    cs:__imp_WSACloseEvent
0x1800aefac  nop     dword ptr [rax+rax+00h]
0x1800aefb1  test    eax, eax
0x1800aefb3  jnz     short loc_1800AEFDC
0x1800aefb5  call    cs:__imp_WSAGetLastError
0x1800aefbc  nop     dword ptr [rax+rax+00h]
0x1800aefc1  mov     r9d, 8Eh
0x1800aefc7  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800aefce  mov     ecx, eax
0x1800aefd0  lea     rdx, aDeletesocketfr; "DeleteSocketFromGArray"
0x1800aefd7  call    DhcpPrintFOErrorEx
0x1800aefdc  mov     qword ptr [rbx+28h], 0
0x1800aefe4  mov     rcx, [rbx+30h]; hEvent
0x1800aefe8  test    rcx, rcx
0x1800aefeb  jz      short loc_1800AF02C
0x1800aefed  call    cs:__imp_WSACloseEvent
0x1800aeff4  nop     dword ptr [rax+rax+00h]
0x1800aeff9  test    eax, eax
0x1800aeffb  jnz     short loc_1800AF024
0x1800aeffd  call    cs:__imp_WSAGetLastError
0x1800af004  nop     dword ptr [rax+rax+00h]
0x1800af009  mov     r9d, 91h
0x1800af00f  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800af016  mov     ecx, eax
0x1800af018  lea     rdx, aDeletesocketfr; "DeleteSocketFromGArray"
0x1800af01f  call    DhcpPrintFOErrorEx
0x1800af024  mov     qword ptr [rbx+30h], 0
0x1800af02c  mov     rcx, [rbx+8]; s
0x1800af030  call    cs:__imp_closesocket
0x1800af037  nop     dword ptr [rax+rax+00h]
0x1800af03c  mov     edi, eax
0x1800af03e  cmp     eax, 0FFFFFFFFh
0x1800af041  jnz     short loc_1800AF06C
0x1800af043  call    cs:__imp_WSAGetLastError
0x1800af04a  nop     dword ptr [rax+rax+00h]
0x1800af04f  mov     r9d, 94h
0x1800af055  lea     r8, aClosesocket; "closesocket"
0x1800af05c  mov     ecx, eax
0x1800af05e  lea     rdx, aDeletesocketfr; "DeleteSocketFromGArray"
0x1800af065  mov     edi, eax
0x1800af067  call    DhcpPrintFOErrorEx
0x1800af06c  mov     rcx, [rbx+18h]; lpMem
0x1800af070  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800af078  test    rcx, rcx
0x1800af07b  jz      short loc_1800AF091
0x1800af07d  call    ResetAndRestoreInFreePacketPool
0x1800af082  mov     qword ptr [rbx+18h], 0
0x1800af08a  mov     dword ptr [rbx+20h], 0
0x1800af091  mov     rcx, [rbx+10h]
0x1800af095  add     rcx, 8; lpCriticalSection
0x1800af099  call    cs:__imp_LeaveCriticalSection
0x1800af0a0  nop     dword ptr [rax+rax+00h]
0x1800af0a5  lea     rcx, gSocketLock; lpCriticalSection
0x1800af0ac  call    cs:__imp_EnterCriticalSection
0x1800af0b3  nop     dword ptr [rax+rax+00h]
0x1800af0b8  mov     rax, [rbx+10h]
0x1800af0bc  lea     rcx, gSocketLock; lpCriticalSection
0x1800af0c3  mov     dword ptr [rax], 0
0x1800af0c9  mov     qword ptr [rbx+10h], 0
0x1800af0d1  call    cs:__imp_LeaveCriticalSection
0x1800af0d8  nop     dword ptr [rax+rax+00h]
0x1800af0dd  mov     rcx, cs:gDhcpHeap; hHeap
0x1800af0e4  mov     r8, rbx; lpMem
0x1800af0e7  xor     edx, edx; dwFlags
0x1800af0e9  call    cs:__imp_HeapFree
0x1800af0f0  nop     dword ptr [rax+rax+00h]
0x1800af0f5  mov     rbx, [rsp+28h+arg_0]
0x1800af0fa  mov     eax, edi
0x1800af0fc  add     rsp, 20h
0x1800af100  pop     rdi
0x1800af101  retn
```
