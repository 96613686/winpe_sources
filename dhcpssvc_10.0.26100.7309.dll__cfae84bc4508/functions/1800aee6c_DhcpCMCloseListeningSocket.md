# DhcpCMCloseListeningSocket

- ea: `0x1800aee6c`
- end: `0x1800af199`
- name: `DhcpCMCloseListeningSocket`
- size: `813`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800ae730`
- `0x1800afd9c`

## callees

- `0x18001ceb4`
- `0x1800aee6c`
- `0x1800b2e40`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800aef0e`
- `WS2_32!WSACloseEvent` at `0x1800aef54`
- `WS2_32!WSACloseEvent` at `0x1800aefa7`
- `WS2_32!WSACloseEvent` at `0x1800aef0e`
- `WS2_32!WSACloseEvent` at `0x1800aef54`
- `WS2_32!WSACloseEvent` at `0x1800aefa7`
- `WS2_32!__imp_closesocket` at `0x1800aeef2`
- `WS2_32!__imp_closesocket` at `0x1800aeef2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aef1e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aef64`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aefb7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aef1e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aef64`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aefb7`
- `KERNEL32!EnterCriticalSection` at `0x1800aeff8`
- `KERNEL32!EnterCriticalSection` at `0x1800aeff8`
- `KERNEL32!LeaveCriticalSection` at `0x1800af015`
- `KERNEL32!LeaveCriticalSection` at `0x1800af015`
- `KERNEL32!HeapFree` at `0x1800af16d`
- `KERNEL32!HeapFree` at `0x1800af16d`

## string_xrefs

- `0x1800aef30`: `WSACloseEvent`
- `0x1800aef76`: `WSACloseEvent`
- `0x1800aefc9`: `WSACloseEvent`

## pseudocode

```c
__int64 __fastcall DhcpCMCloseListeningSocket(__int64 a1, _DWORD *a2, _DWORD *a3, _DWORD *a4, _DWORD *a5, int a6)
{
  unsigned int Error; // ebp
  unsigned int *v8; // rbx
  __int64 v9; // rdi
  STRSAFE_LPCWSTR *v12; // r8
  int *v13; // r13
  void *v15; // rcx
  void *v16; // rcx
  HANDLE v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdi
  unsigned int v22; // r8d
  __int64 v23; // rsi
  __int64 v24; // rcx
  HANDLE v25; // rax
  unsigned int v26; // eax

  Error = 0;
  v8 = 0;
  v9 = 0;
  v12 = (STRSAFE_LPCWSTR *)a1;
  if ( !gNumListeningSockets )
    return Error;
  while ( 1 )
  {
    v13 = &gListeningSockets[6 * v9];
    if ( *v13 == *(_DWORD *)(a1 + 16) )
      break;
    v9 = (unsigned int)(v9 + 1);
    if ( (unsigned int)v9 >= gNumListeningSockets )
      return Error;
  }
  if ( dword_1800FB380[6 * v9]-- == 1 )
  {
    v8 = (unsigned int *)qword_1800FB378[3 * v9];
    closesocket(*((_QWORD *)v8 + 1));
    v15 = (void *)*((_QWORD *)v8 + 5);
    *((_QWORD *)v8 + 1) = -1;
    if ( v15 )
    {
      if ( !WSACloseEvent(v15) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "DhcpCMCloseListeningSocket", "WSACloseEvent", 2275);
      }
      *((_QWORD *)v8 + 5) = 0;
    }
    v16 = (void *)*((_QWORD *)v8 + 6);
    if ( v16 )
    {
      if ( !WSACloseEvent(v16) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "DhcpCMCloseListeningSocket", "WSACloseEvent", 2278);
      }
      *((_QWORD *)v8 + 6) = 0;
    }
    v17 = gSocketEventArray[*v8];
    if ( v17 )
    {
      if ( !WSACloseEvent(v17) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "DhcpCMCloseListeningSocket", "WSACloseEvent", 2281);
      }
      gSocketEventArray[*v8] = 0;
    }
    EnterCriticalSection(&gSocketLock);
    **((_DWORD **)v8 + 2) = 0;
    *((_QWORD *)v8 + 2) = 0;
    LeaveCriticalSection(&gSocketLock);
    v18 = (unsigned int)(gNumListeningSockets - 1);
    if ( (unsigned int)v9 < (unsigned int)v18 )
      qmemcpy(v13, &gListeningSockets[6 * (unsigned int)(v9 + 1)], 24LL * (unsigned int)(v18 - v9));
    gNumListeningSockets = v18;
    qword_1800FB378[3 * v18] = 0;
    v19 = 3 * v18;
    dword_1800FB380[2 * v19] = 0;
    gListeningSockets[2 * v19] = 0;
    v20 = *v8;
    if ( a3 )
      *a3 = v20;
    if ( a4 )
      *a4 = v8[1];
    v21 = gSocketEventTotal - 1;
    if ( (_DWORD)v20 != (_DWORD)v21 )
    {
      v22 = v20;
      if ( (unsigned int)v20 < (unsigned int)v21 )
      {
        v23 = (unsigned int)(v20 + 1);
        v24 = v20;
        do
        {
          v25 = gSocketEventArray[v23++];
          gSocketEventArray[v24++] = v25;
          **(_DWORD **)((char *)&unk_1800FE978 + v23 * 8) = v22++;
          *(_QWORD *)((char *)&unk_1800FE978 + v24 * 8) = *(_QWORD *)((char *)&unk_1800FE978 + v23 * 8);
        }
        while ( v22 < (unsigned int)v21 );
      }
    }
    gSocketEventTotal = v21;
    gSocketArray[v21] = 0;
    if ( a5 )
    {
      if ( a2 && (_DWORD)v20 == *a2 )
      {
        *a5 = 1;
        goto LABEL_34;
      }
      *a5 = 0;
    }
    if ( a2 )
    {
LABEL_34:
      v12 = (STRSAFE_LPCWSTR *)a1;
      if ( (unsigned int)v20 < *a2 )
        --*a2;
      goto LABEL_37;
    }
    v12 = (STRSAFE_LPCWSTR *)a1;
  }
LABEL_37:
  if ( a6 == 1 )
  {
    v26 = DhcpCMUpdateListeningRelName(*v12);
    if ( v26 )
      Error = v26;
  }
  if ( v8 )
    HeapFree(gDhcpHeap, 0, v8);
  return Error;
}

```

## disassembly

```asm
0x1800aee6c  mov     rax, rsp
0x1800aee6f  mov     [rax+10h], rbx
0x1800aee73  mov     [rax+18h], rbp
0x1800aee77  mov     [rax+20h], rsi
0x1800aee7b  mov     [rax+8], rcx
0x1800aee7f  push    rdi
0x1800aee80  push    r12
0x1800aee82  push    r13
0x1800aee84  push    r14
0x1800aee86  push    r15
0x1800aee88  sub     rsp, 20h
0x1800aee8c  mov     r14, rdx
0x1800aee8f  xor     ebp, ebp
0x1800aee91  mov     edx, cs:gNumListeningSockets
0x1800aee97  xor     ebx, ebx
0x1800aee99  xor     edi, edi
0x1800aee9b  mov     r12, r8
0x1800aee9e  mov     r15, r9
0x1800aeea1  mov     r8, rcx
0x1800aeea4  test    edx, edx
0x1800aeea6  jz      loc_1800AF179
0x1800aeeac  mov     esi, [rcx+10h]
0x1800aeeaf  lea     r9, __ImageBase
0x1800aeeb6  lea     rcx, [rdi+rdi*2]
0x1800aeeba  lea     r13, rva gListeningSockets[r9]
0x1800aeec1  lea     r13, [r13+rcx*8+0]
0x1800aeec6  cmp     [r13+0], esi
0x1800aeeca  jz      short loc_1800AEED7
0x1800aeecc  inc     edi
0x1800aeece  cmp     edi, edx
0x1800aeed0  jb      short loc_1800AEEB6
0x1800aeed2  jmp     loc_1800AF179
0x1800aeed7  add     rva dword_1800FB380[r9+rcx*8], 0FFFFFFFFh
0x1800aeee0  jnz     loc_1800AF146
0x1800aeee6  mov     rbx, rva qword_1800FB378[r9+rcx*8]
0x1800aeeee  mov     rcx, [rbx+8]; s
0x1800aeef2  call    cs:__imp_closesocket
0x1800aeef9  nop     dword ptr [rax+rax+00h]
0x1800aeefe  mov     rcx, [rbx+28h]; hEvent
0x1800aef02  xor     esi, esi
0x1800aef04  or      qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800aef09  test    rcx, rcx
0x1800aef0c  jz      short loc_1800AEF4B
0x1800aef0e  call    cs:__imp_WSACloseEvent
0x1800aef15  nop     dword ptr [rax+rax+00h]
0x1800aef1a  test    eax, eax
0x1800aef1c  jnz     short loc_1800AEF47
0x1800aef1e  call    cs:__imp_WSAGetLastError
0x1800aef25  nop     dword ptr [rax+rax+00h]
0x1800aef2a  mov     r9d, 8E3h
0x1800aef30  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800aef37  mov     ecx, eax
0x1800aef39  lea     rdx, aDhcpcmcloselis; "DhcpCMCloseListeningSocket"
0x1800aef40  mov     ebp, eax
0x1800aef42  call    DhcpPrintFOErrorEx
0x1800aef47  mov     [rbx+28h], rsi
0x1800aef4b  mov     rcx, [rbx+30h]; hEvent
0x1800aef4f  test    rcx, rcx
0x1800aef52  jz      short loc_1800AEF91
0x1800aef54  call    cs:__imp_WSACloseEvent
0x1800aef5b  nop     dword ptr [rax+rax+00h]
0x1800aef60  test    eax, eax
0x1800aef62  jnz     short loc_1800AEF8D
0x1800aef64  call    cs:__imp_WSAGetLastError
0x1800aef6b  nop     dword ptr [rax+rax+00h]
0x1800aef70  mov     r9d, 8E6h
0x1800aef76  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800aef7d  mov     ecx, eax
0x1800aef7f  lea     rdx, aDhcpcmcloselis; "DhcpCMCloseListeningSocket"
0x1800aef86  mov     ebp, eax
0x1800aef88  call    DhcpPrintFOErrorEx
0x1800aef8d  mov     [rbx+30h], rsi
0x1800aef91  mov     eax, [rbx]
0x1800aef93  lea     rcx, __ImageBase
0x1800aef9a  mov     rcx, rva gSocketEventArray[rcx+rax*8]; hEvent
0x1800aefa2  test    rcx, rcx
0x1800aefa5  jz      short loc_1800AEFF1
0x1800aefa7  call    cs:__imp_WSACloseEvent
0x1800aefae  nop     dword ptr [rax+rax+00h]
0x1800aefb3  test    eax, eax
0x1800aefb5  jnz     short loc_1800AEFE0
0x1800aefb7  call    cs:__imp_WSAGetLastError
0x1800aefbe  nop     dword ptr [rax+rax+00h]
0x1800aefc3  mov     r9d, 8E9h
0x1800aefc9  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800aefd0  mov     ecx, eax
0x1800aefd2  lea     rdx, aDhcpcmcloselis; "DhcpCMCloseListeningSocket"
0x1800aefd9  mov     ebp, eax
0x1800aefdb  call    DhcpPrintFOErrorEx
0x1800aefe0  mov     eax, [rbx]
0x1800aefe2  lea     rcx, __ImageBase
0x1800aefe9  mov     rva gSocketEventArray[rcx+rax*8], rsi
0x1800aeff1  lea     rcx, gSocketLock; lpCriticalSection
0x1800aeff8  call    cs:__imp_EnterCriticalSection
0x1800aefff  nop     dword ptr [rax+rax+00h]
0x1800af004  mov     rax, [rbx+10h]
0x1800af008  lea     rcx, gSocketLock; lpCriticalSection
0x1800af00f  mov     [rax], esi
0x1800af011  mov     [rbx+10h], rsi
0x1800af015  call    cs:__imp_LeaveCriticalSection
0x1800af01c  nop     dword ptr [rax+rax+00h]
0x1800af021  mov     edx, cs:gNumListeningSockets
0x1800af027  dec     edx
0x1800af029  cmp     edi, edx
0x1800af02b  jnb     short loc_1800AF05E
0x1800af02d  lea     eax, [rdi+1]
0x1800af030  lea     rax, [rax+rax*2]
0x1800af034  lea     rcx, __ImageBase
0x1800af03b  lea     rsi, rva gListeningSockets[rcx]
0x1800af042  lea     rsi, [rsi+rax*8]
0x1800af046  mov     eax, edx
0x1800af048  sub     eax, edi
0x1800af04a  mov     rdi, r13
0x1800af04d  lea     rcx, [rax+rax*2]
0x1800af051  shl     rcx, 3
0x1800af055  shr     rcx, 3
0x1800af059  rep movsq
0x1800af05c  xor     esi, esi
0x1800af05e  mov     cs:gNumListeningSockets, edx
0x1800af064  lea     rcx, [rdx+rdx*2]
0x1800af068  lea     r13, __ImageBase
0x1800af06f  mov     rva qword_1800FB378[r13+rcx*8], rsi
0x1800af077  lea     rcx, [rdx+rdx*2]
0x1800af07b  mov     rva dword_1800FB380[r13+rcx*8], esi
0x1800af083  mov     rva gListeningSockets[r13+rcx*8], esi
0x1800af08b  mov     edx, [rbx]
0x1800af08d  test    r12, r12
0x1800af090  jz      short loc_1800AF096
0x1800af092  mov     [r12], edx
0x1800af096  test    r15, r15
0x1800af099  jz      short loc_1800AF0A1
0x1800af09b  mov     eax, [rbx+4]
0x1800af09e  mov     [r15], eax
0x1800af0a1  mov     edi, cs:gSocketEventTotal
0x1800af0a7  dec     edi
0x1800af0a9  cmp     edx, edi
0x1800af0ab  jz      short loc_1800AF0FD
0x1800af0ad  mov     r8d, edx
0x1800af0b0  jnb     short loc_1800AF0FD
0x1800af0b2  lea     esi, [rdx+1]
0x1800af0b5  mov     rcx, rdx
0x1800af0b8  shl     rsi, 3
0x1800af0bc  shl     rcx, 3
0x1800af0c0  mov     rax, [rsi+r13+0FEBE0h]
0x1800af0c8  lea     rsi, [rsi+8]
0x1800af0cc  mov     [rcx+r13+0FEBE0h], rax
0x1800af0d4  lea     rcx, [rcx+8]
0x1800af0d8  mov     rax, [rsi+r13+0FE978h]
0x1800af0e0  mov     [rax], r8d
0x1800af0e3  inc     r8d
0x1800af0e6  mov     rax, [rsi+r13+0FE978h]
0x1800af0ee  mov     [rcx+r13+0FE978h], rax
0x1800af0f6  cmp     r8d, edi
0x1800af0f9  jb      short loc_1800AF0C0
0x1800af0fb  xor     esi, esi
0x1800af0fd  mov     rax, [rsp+48h+arg_20]
0x1800af102  mov     cs:gSocketEventTotal, edi
0x1800af108  mov     rva gSocketArray[r13+rdi*8], rsi
0x1800af110  test    rax, rax
0x1800af113  jz      short loc_1800AF129
0x1800af115  test    r14, r14
0x1800af118  jz      short loc_1800AF127
0x1800af11a  cmp     edx, [r14]
0x1800af11d  jnz     short loc_1800AF127
0x1800af11f  mov     dword ptr [rax], 1
0x1800af125  jmp     short loc_1800AF12E
0x1800af127  mov     [rax], esi
0x1800af129  test    r14, r14
0x1800af12c  jz      short loc_1800AF141
0x1800af12e  mov     eax, [r14]
0x1800af131  mov     r8, [rsp+48h+arg_0]
0x1800af136  cmp     edx, eax
0x1800af138  jnb     short loc_1800AF146
0x1800af13a  dec     eax
0x1800af13c  mov     [r14], eax
0x1800af13f  jmp     short loc_1800AF146
0x1800af141  mov     r8, [rsp+48h+arg_0]
0x1800af146  cmp     [rsp+48h+arg_28], 1
0x1800af14b  jnz     short loc_1800AF15C
0x1800af14d  mov     rcx, [r8]; pszSrc
0x1800af150  xor     edx, edx
0x1800af152  call    DhcpCMUpdateListeningRelName
0x1800af157  test    eax, eax
0x1800af159  cmovnz  ebp, eax
0x1800af15c  test    rbx, rbx
0x1800af15f  jz      short loc_1800AF179
0x1800af161  mov     rcx, cs:gDhcpHeap; hHeap
0x1800af168  mov     r8, rbx; lpMem
0x1800af16b  xor     edx, edx; dwFlags
0x1800af16d  call    cs:__imp_HeapFree
0x1800af174  nop     dword ptr [rax+rax+00h]
0x1800af179  mov     rbx, [rsp+48h+arg_8]
0x1800af17e  mov     eax, ebp
0x1800af180  mov     rbp, [rsp+48h+arg_10]
0x1800af185  mov     rsi, [rsp+48h+arg_18]
0x1800af18a  add     rsp, 20h
0x1800af18e  pop     r15
0x1800af190  pop     r14
0x1800af192  pop     r13
0x1800af194  pop     r12
0x1800af196  pop     rdi
0x1800af197  retn
```
