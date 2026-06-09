# DhcpCMCloseConnection

- ea: `0x1800ae730`
- end: `0x1800aeaac`
- name: `DhcpCMCloseConnection`
- size: `892`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800aeab4`
- `0x1800af4c0`
- `0x1800afd9c`

## callees

- `0x18001ceb4`
- `0x1800ae730`
- `0x1800aee6c`
- `0x1800cbc3c`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800ae87a`
- `WS2_32!WSACloseEvent` at `0x1800ae8c4`
- `WS2_32!WSACloseEvent` at `0x1800ae90a`
- `WS2_32!WSACloseEvent` at `0x1800ae87a`
- `WS2_32!WSACloseEvent` at `0x1800ae8c4`
- `WS2_32!WSACloseEvent` at `0x1800ae90a`
- `WS2_32!WSASetEvent` at `0x1800ae777`
- `WS2_32!WSASetEvent` at `0x1800ae777`
- `WS2_32!__imp_closesocket` at `0x1800ae94d`
- `WS2_32!__imp_closesocket` at `0x1800ae94d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae787`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae88a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae8d4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae91a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae960`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae787`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae88a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae8d4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae91a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae960`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ae9c8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800ae9c8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800ae9ab`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800ae9ab`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800ae825`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800ae839`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800ae825`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800ae839`
- `KERNEL32!AcquireSRWLockShared` at `0x1800ae809`
- `KERNEL32!AcquireSRWLockShared` at `0x1800ae809`
- `KERNEL32!EnterCriticalSection` at `0x1800ae84d`
- `KERNEL32!EnterCriticalSection` at `0x1800ae9ef`
- `KERNEL32!EnterCriticalSection` at `0x1800ae84d`
- `KERNEL32!EnterCriticalSection` at `0x1800ae9ef`
- `KERNEL32!LeaveCriticalSection` at `0x1800ae9dc`
- `KERNEL32!LeaveCriticalSection` at `0x1800aea0c`
- `KERNEL32!LeaveCriticalSection` at `0x1800ae9dc`
- `KERNEL32!LeaveCriticalSection` at `0x1800aea0c`
- `KERNEL32!HeapFree` at `0x1800aea24`
- `KERNEL32!HeapFree` at `0x1800aea24`

## string_xrefs

- `0x1800ae89c`: `WSACloseEvent`
- `0x1800ae8e6`: `WSACloseEvent`
- `0x1800ae92c`: `WSACloseEvent`

## pseudocode

```c
__int64 __fastcall DhcpCMCloseConnection(_QWORD *lpMem, unsigned int a2, int a3)
{
  int v3; // ebp
  unsigned int Error; // ebx
  unsigned int v6; // r14d
  __int64 v9; // r13
  void *v10; // rcx
  int v11; // esi
  __int64 v12; // r12
  HANDLE v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  unsigned int v16; // esi
  void *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rdx
  int v20; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v21; // [rsp+78h] [rbp+10h] BYREF
  char v22; // [rsp+88h] [rbp+20h] BYREF

  v21 = a2;
  v3 = 0;
  Error = 0;
  v20 = 0;
  v6 = a2;
  if ( !lpMem )
    return 87;
  v9 = lpMem[7];
  v10 = (void *)lpMem[6];
  v11 = *(_DWORD *)(v9 + 8);
  if ( v10 && !WSASetEvent(v10) )
  {
    Error = WSAGetLastError();
    DhcpPrintFOErrorEx(Error, "DhcpCMCloseConnection", "WSASetEvent", 582);
  }
  if ( v11 == 1 )
  {
    Error = DhcpCMCloseListeningSocket(v9, (unsigned int)&v21, (unsigned int)&v22, 0, (__int64)&v20, a3);
    DhcpPrintFOErrorEx(Error, "DhcpCMCloseConnection", "DhcpCMCloseListeningSocket", 592);
    v6 = v21;
    v3 = v20;
  }
  AcquireSRWLockShared((PSRWLOCK)(v9 + 72));
  if ( v11 && (v11 != 1 || v3) )
  {
    ReleaseSRWLockShared((PSRWLOCK)(v9 + 72));
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)(v9 + 72));
    EnterCriticalSection((LPCRITICAL_SECTION)(lpMem[2] + 8LL));
    v12 = v6;
    v13 = gSocketEventArray[v12];
    if ( v13 )
    {
      if ( !WSACloseEvent(v13) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "DhcpCMCloseConnection", "WSACloseEvent", 608);
      }
      gSocketEventArray[v12] = 0;
    }
    v14 = (void *)lpMem[5];
    if ( v14 )
    {
      if ( !WSACloseEvent(v14) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "DhcpCMCloseConnection", "WSACloseEvent", 611);
      }
      lpMem[5] = 0;
    }
    v15 = (void *)lpMem[6];
    if ( v15 )
    {
      if ( !WSACloseEvent(v15) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "DhcpCMCloseConnection", "WSACloseEvent", 614);
      }
      lpMem[6] = 0;
    }
    v16 = Error;
    Error = closesocket(lpMem[1]);
    if ( Error == -1 )
    {
      Error = WSAGetLastError();
      DhcpPrintFOErrorEx(Error, "DhcpCMCloseConnection", "closesocket", 617);
    }
    lpMem[1] = -1;
    v17 = (void *)lpMem[3];
    if ( !Error )
      Error = v16;
    if ( v17 )
    {
      ResetAndRestoreInFreePacketPool(v17);
      lpMem[3] = 0;
      *((_DWORD *)lpMem + 8) = 0;
    }
    AcquireSRWLockExclusive((PSRWLOCK)(v9 + 72));
    *(_QWORD *)(v9 + 480) = 0;
    *(_QWORD *)(v9 + 488) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(v9 + 72));
    LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem[2] + 8LL));
    EnterCriticalSection(&gSocketLock);
    *(_DWORD *)lpMem[2] = 0;
    lpMem[2] = 0;
    LeaveCriticalSection(&gSocketLock);
    HeapFree(gDhcpHeap, 0, lpMem);
    v18 = gSocketEventTotal - 1;
    if ( v6 < (unsigned int)v18 )
    {
      do
      {
        v19 = v6 + 1;
        gSocketEventArray[v12++] = gSocketEventArray[v19];
        *(_DWORD *)gSocketArray[v19] = v6++;
        *(_QWORD *)((char *)&unk_1800FE978 + v12 * 8) = gSocketArray[v19];
      }
      while ( (unsigned int)v19 < (unsigned int)v18 );
    }
    gSocketEventTotal = v18;
    gSocketArray[v18] = 0;
  }
  return Error;
}

```

## disassembly

```asm
0x1800ae730  mov     [rsp+arg_10], rbx
0x1800ae735  mov     [rsp+arg_8], edx
0x1800ae739  push    rbp
0x1800ae73a  push    rsi
0x1800ae73b  push    rdi
0x1800ae73c  push    r12
0x1800ae73e  push    r13
0x1800ae740  push    r14
0x1800ae742  push    r15
0x1800ae744  sub     rsp, 30h
0x1800ae748  xor     ebp, ebp
0x1800ae74a  xor     ebx, ebx
0x1800ae74c  mov     [rsp+68h+arg_0], ebp
0x1800ae750  mov     r15d, r8d
0x1800ae753  mov     r14d, edx
0x1800ae756  mov     rdi, rcx
0x1800ae759  test    rcx, rcx
0x1800ae75c  jnz     short loc_1800AE766
0x1800ae75e  lea     eax, [rcx+57h]
0x1800ae761  jmp     loc_1800AEA93
0x1800ae766  mov     r13, [rcx+38h]
0x1800ae76a  mov     rcx, [rcx+30h]; hEvent
0x1800ae76e  mov     esi, [r13+8]
0x1800ae772  test    rcx, rcx
0x1800ae775  jz      short loc_1800AE7B0
0x1800ae777  call    cs:__imp_WSASetEvent
0x1800ae77e  nop     dword ptr [rax+rax+00h]
0x1800ae783  test    eax, eax
0x1800ae785  jnz     short loc_1800AE7B0
0x1800ae787  call    cs:__imp_WSAGetLastError
0x1800ae78e  nop     dword ptr [rax+rax+00h]
0x1800ae793  mov     r9d, 246h
0x1800ae799  lea     r8, aWsasetevent; "WSASetEvent"
0x1800ae7a0  mov     ecx, eax
0x1800ae7a2  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800ae7a9  mov     ebx, eax
0x1800ae7ab  call    DhcpPrintFOErrorEx
0x1800ae7b0  cmp     esi, 1
0x1800ae7b3  jnz     short loc_1800AE802
0x1800ae7b5  lea     rax, [rsp+68h+arg_0]
0x1800ae7ba  mov     [rsp+68h+var_40], r15d
0x1800ae7bf  xor     r9d, r9d
0x1800ae7c2  mov     [rsp+68h+var_48], rax
0x1800ae7c7  lea     r8, [rsp+68h+arg_18]
0x1800ae7cf  mov     rcx, r13
0x1800ae7d2  lea     rdx, [rsp+68h+arg_8]
0x1800ae7d7  call    DhcpCMCloseListeningSocket
0x1800ae7dc  mov     r9d, 250h
0x1800ae7e2  lea     r8, aDhcpcmcloselis; "DhcpCMCloseListeningSocket"
0x1800ae7e9  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800ae7f0  mov     ecx, eax
0x1800ae7f2  mov     ebx, eax
0x1800ae7f4  call    DhcpPrintFOErrorEx
0x1800ae7f9  mov     r14d, [rsp+68h+arg_8]
0x1800ae7fe  mov     ebp, [rsp+68h+arg_0]
0x1800ae802  lea     r15, [r13+48h]
0x1800ae806  mov     rcx, r15; SRWLock
0x1800ae809  call    cs:__imp_AcquireSRWLockShared
0x1800ae810  nop     dword ptr [rax+rax+00h]
0x1800ae815  test    esi, esi
0x1800ae817  jz      short loc_1800AE836
0x1800ae819  cmp     esi, 1
0x1800ae81c  jnz     short loc_1800AE822
0x1800ae81e  test    ebp, ebp
0x1800ae820  jz      short loc_1800AE836
0x1800ae822  mov     rcx, r15; SRWLock
0x1800ae825  call    cs:__imp_ReleaseSRWLockShared
0x1800ae82c  nop     dword ptr [rax+rax+00h]
0x1800ae831  jmp     loc_1800AEA91
0x1800ae836  mov     rcx, r15; SRWLock
0x1800ae839  call    cs:__imp_ReleaseSRWLockShared
0x1800ae840  nop     dword ptr [rax+rax+00h]
0x1800ae845  mov     rcx, [rdi+10h]
0x1800ae849  add     rcx, 8; lpCriticalSection
0x1800ae84d  call    cs:__imp_EnterCriticalSection
0x1800ae854  nop     dword ptr [rax+rax+00h]
0x1800ae859  mov     eax, r14d
0x1800ae85c  lea     rsi, __ImageBase
0x1800ae863  xor     ebp, ebp
0x1800ae865  lea     r12, ds:0[rax*8]
0x1800ae86d  mov     rcx, [r12+rsi+0FEBE0h]; hEvent
0x1800ae875  test    rcx, rcx
0x1800ae878  jz      short loc_1800AE8BB
0x1800ae87a  call    cs:__imp_WSACloseEvent
0x1800ae881  nop     dword ptr [rax+rax+00h]
0x1800ae886  test    eax, eax
0x1800ae888  jnz     short loc_1800AE8B3
0x1800ae88a  call    cs:__imp_WSAGetLastError
0x1800ae891  nop     dword ptr [rax+rax+00h]
0x1800ae896  mov     r9d, 260h
0x1800ae89c  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800ae8a3  mov     ecx, eax
0x1800ae8a5  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800ae8ac  mov     ebx, eax
0x1800ae8ae  call    DhcpPrintFOErrorEx
0x1800ae8b3  mov     [r12+rsi+0FEBE0h], rbp
0x1800ae8bb  mov     rcx, [rdi+28h]; hEvent
0x1800ae8bf  test    rcx, rcx
0x1800ae8c2  jz      short loc_1800AE901
0x1800ae8c4  call    cs:__imp_WSACloseEvent
0x1800ae8cb  nop     dword ptr [rax+rax+00h]
0x1800ae8d0  test    eax, eax
0x1800ae8d2  jnz     short loc_1800AE8FD
0x1800ae8d4  call    cs:__imp_WSAGetLastError
0x1800ae8db  nop     dword ptr [rax+rax+00h]
0x1800ae8e0  mov     r9d, 263h
0x1800ae8e6  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800ae8ed  mov     ecx, eax
0x1800ae8ef  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800ae8f6  mov     ebx, eax
0x1800ae8f8  call    DhcpPrintFOErrorEx
0x1800ae8fd  mov     [rdi+28h], rbp
0x1800ae901  mov     rcx, [rdi+30h]; hEvent
0x1800ae905  test    rcx, rcx
0x1800ae908  jz      short loc_1800AE947
0x1800ae90a  call    cs:__imp_WSACloseEvent
0x1800ae911  nop     dword ptr [rax+rax+00h]
0x1800ae916  test    eax, eax
0x1800ae918  jnz     short loc_1800AE943
0x1800ae91a  call    cs:__imp_WSAGetLastError
0x1800ae921  nop     dword ptr [rax+rax+00h]
0x1800ae926  mov     r9d, 266h
0x1800ae92c  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800ae933  mov     ecx, eax
0x1800ae935  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800ae93c  mov     ebx, eax
0x1800ae93e  call    DhcpPrintFOErrorEx
0x1800ae943  mov     [rdi+30h], rbp
0x1800ae947  mov     rcx, [rdi+8]; s
0x1800ae94b  mov     esi, ebx
0x1800ae94d  call    cs:__imp_closesocket
0x1800ae954  nop     dword ptr [rax+rax+00h]
0x1800ae959  mov     ebx, eax
0x1800ae95b  cmp     eax, 0FFFFFFFFh
0x1800ae95e  jnz     short loc_1800AE989
0x1800ae960  call    cs:__imp_WSAGetLastError
0x1800ae967  nop     dword ptr [rax+rax+00h]
0x1800ae96c  mov     r9d, 269h
0x1800ae972  lea     r8, aClosesocket; "closesocket"
0x1800ae979  mov     ecx, eax
0x1800ae97b  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800ae982  mov     ebx, eax
0x1800ae984  call    DhcpPrintFOErrorEx
0x1800ae989  or      qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1800ae98e  mov     rcx, [rdi+18h]; lpMem
0x1800ae992  test    ebx, ebx
0x1800ae994  cmovz   ebx, esi
0x1800ae997  test    rcx, rcx
0x1800ae99a  jz      short loc_1800AE9A8
0x1800ae99c  call    ResetAndRestoreInFreePacketPool
0x1800ae9a1  mov     [rdi+18h], rbp
0x1800ae9a5  mov     [rdi+20h], ebp
0x1800ae9a8  mov     rcx, r15; SRWLock
0x1800ae9ab  call    cs:__imp_AcquireSRWLockExclusive
0x1800ae9b2  nop     dword ptr [rax+rax+00h]
0x1800ae9b7  mov     rcx, r15; SRWLock
0x1800ae9ba  mov     [r13+1E0h], rbp
0x1800ae9c1  mov     [r13+1E8h], rbp
0x1800ae9c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ae9cf  nop     dword ptr [rax+rax+00h]
0x1800ae9d4  mov     rcx, [rdi+10h]
0x1800ae9d8  add     rcx, 8; lpCriticalSection
0x1800ae9dc  call    cs:__imp_LeaveCriticalSection
0x1800ae9e3  nop     dword ptr [rax+rax+00h]
0x1800ae9e8  lea     rcx, gSocketLock; lpCriticalSection
0x1800ae9ef  call    cs:__imp_EnterCriticalSection
0x1800ae9f6  nop     dword ptr [rax+rax+00h]
0x1800ae9fb  mov     rax, [rdi+10h]
0x1800ae9ff  lea     rcx, gSocketLock; lpCriticalSection
0x1800aea06  mov     [rax], ebp
0x1800aea08  mov     [rdi+10h], rbp
0x1800aea0c  call    cs:__imp_LeaveCriticalSection
0x1800aea13  nop     dword ptr [rax+rax+00h]
0x1800aea18  mov     rcx, cs:gDhcpHeap; hHeap
0x1800aea1f  mov     r8, rdi; lpMem
0x1800aea22  xor     edx, edx; dwFlags
0x1800aea24  call    cs:__imp_HeapFree
0x1800aea2b  nop     dword ptr [rax+rax+00h]
0x1800aea30  mov     r8d, cs:gSocketEventTotal
0x1800aea37  lea     r9, __ImageBase
0x1800aea3e  dec     r8d
0x1800aea41  cmp     r14d, r8d
0x1800aea44  jnb     short loc_1800AEA82
0x1800aea46  lea     edx, [r14+1]
0x1800aea4a  mov     rax, rva gSocketEventArray[r9+rdx*8]
0x1800aea52  mov     [r12+r9+0FEBE0h], rax
0x1800aea5a  lea     r12, [r12+8]
0x1800aea5f  mov     rax, rva gSocketArray[r9+rdx*8]
0x1800aea67  mov     [rax], r14d
0x1800aea6a  mov     r14d, edx
0x1800aea6d  mov     rax, rva gSocketArray[r9+rdx*8]
0x1800aea75  mov     [r12+r9+0FE978h], rax
0x1800aea7d  cmp     edx, r8d
0x1800aea80  jb      short loc_1800AEA46
0x1800aea82  mov     cs:gSocketEventTotal, r8d
0x1800aea89  mov     rva gSocketArray[r9+r8*8], rbp
0x1800aea91  mov     eax, ebx
0x1800aea93  mov     rbx, [rsp+68h+arg_10]
0x1800aea9b  add     rsp, 30h
0x1800aea9f  pop     r15
0x1800aeaa1  pop     r14
0x1800aeaa3  pop     r13
0x1800aeaa5  pop     r12
0x1800aeaa7  pop     rdi
0x1800aeaa8  pop     rsi
0x1800aeaa9  pop     rbp
0x1800aeaaa  retn
```
