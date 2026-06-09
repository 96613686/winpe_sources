# DhcpCMCloseConnection

- ea: `0x1800af4e4`
- end: `0x1800af863`
- name: `DhcpCMCloseConnection`
- size: `895`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800af86c`
- `0x1800b02c0`
- `0x1800b0bb4`

## callees

- `0x18001c45c`
- `0x1800af4e4`
- `0x1800afc40`
- `0x1800cccf4`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800af62e`
- `WS2_32!WSACloseEvent` at `0x1800af678`
- `WS2_32!WSACloseEvent` at `0x1800af6be`
- `WS2_32!WSACloseEvent` at `0x1800af62e`
- `WS2_32!WSACloseEvent` at `0x1800af678`
- `WS2_32!WSACloseEvent` at `0x1800af6be`
- `WS2_32!WSASetEvent` at `0x1800af52b`
- `WS2_32!WSASetEvent` at `0x1800af52b`
- `WS2_32!__imp_closesocket` at `0x1800af6ff`
- `WS2_32!__imp_closesocket` at `0x1800af6ff`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af53b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af63e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af688`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af6ce`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af712`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af53b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af63e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af688`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af6ce`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af712`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800af77f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800af77f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800af762`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800af762`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800af5d9`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800af5ed`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800af5d9`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800af5ed`
- `KERNEL32!AcquireSRWLockShared` at `0x1800af5bd`
- `KERNEL32!AcquireSRWLockShared` at `0x1800af5bd`
- `KERNEL32!EnterCriticalSection` at `0x1800af601`
- `KERNEL32!EnterCriticalSection` at `0x1800af7a6`
- `KERNEL32!EnterCriticalSection` at `0x1800af601`
- `KERNEL32!EnterCriticalSection` at `0x1800af7a6`
- `KERNEL32!LeaveCriticalSection` at `0x1800af793`
- `KERNEL32!LeaveCriticalSection` at `0x1800af7c3`
- `KERNEL32!LeaveCriticalSection` at `0x1800af793`
- `KERNEL32!LeaveCriticalSection` at `0x1800af7c3`
- `KERNEL32!HeapFree` at `0x1800af7db`
- `KERNEL32!HeapFree` at `0x1800af7db`

## string_xrefs

- `0x1800af650`: `WSACloseEvent`
- `0x1800af69a`: `WSACloseEvent`
- `0x1800af6e0`: `WSACloseEvent`

## pseudocode

```c
__int64 __fastcall DhcpCMCloseConnection(_QWORD *lpMem, unsigned int a2, int a3)
{
  int v3; // ebp
  unsigned int Error; // edi
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
    v16 = closesocket(lpMem[1]);
    if ( v16 == -1 )
    {
      v16 = WSAGetLastError();
      DhcpPrintFOErrorEx(v16, "DhcpCMCloseConnection", "closesocket", 617);
    }
    v17 = (void *)lpMem[3];
    lpMem[1] = -1;
    if ( !v16 )
      v16 = Error;
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
        *(_QWORD *)((char *)&unk_1801003B8 + v12 * 8) = gSocketArray[v19];
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
0x1800af4e4  mov     [rsp+arg_10], rbx
0x1800af4e9  mov     [rsp+arg_8], edx
0x1800af4ed  push    rbp
0x1800af4ee  push    rsi
0x1800af4ef  push    rdi
0x1800af4f0  push    r12
0x1800af4f2  push    r13
0x1800af4f4  push    r14
0x1800af4f6  push    r15
0x1800af4f8  sub     rsp, 30h
0x1800af4fc  xor     ebp, ebp
0x1800af4fe  xor     edi, edi
0x1800af500  mov     [rsp+68h+arg_0], ebp
0x1800af504  mov     r15d, r8d
0x1800af507  mov     r14d, edx
0x1800af50a  mov     rbx, rcx
0x1800af50d  test    rcx, rcx
0x1800af510  jnz     short loc_1800AF51A
0x1800af512  lea     eax, [rcx+57h]
0x1800af515  jmp     loc_1800AF84A
0x1800af51a  mov     r13, [rcx+38h]
0x1800af51e  mov     rcx, [rcx+30h]; hEvent
0x1800af522  mov     esi, [r13+8]
0x1800af526  test    rcx, rcx
0x1800af529  jz      short loc_1800AF564
0x1800af52b  call    cs:__imp_WSASetEvent
0x1800af532  nop     dword ptr [rax+rax+00h]
0x1800af537  test    eax, eax
0x1800af539  jnz     short loc_1800AF564
0x1800af53b  call    cs:__imp_WSAGetLastError
0x1800af542  nop     dword ptr [rax+rax+00h]
0x1800af547  mov     r9d, 246h
0x1800af54d  lea     r8, aWsasetevent; "WSASetEvent"
0x1800af554  mov     ecx, eax
0x1800af556  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800af55d  mov     edi, eax
0x1800af55f  call    DhcpPrintFOErrorEx
0x1800af564  cmp     esi, 1
0x1800af567  jnz     short loc_1800AF5B6
0x1800af569  lea     rax, [rsp+68h+arg_0]
0x1800af56e  mov     [rsp+68h+var_40], r15d
0x1800af573  xor     r9d, r9d
0x1800af576  mov     [rsp+68h+var_48], rax
0x1800af57b  lea     r8, [rsp+68h+arg_18]
0x1800af583  mov     rcx, r13
0x1800af586  lea     rdx, [rsp+68h+arg_8]
0x1800af58b  call    DhcpCMCloseListeningSocket
0x1800af590  mov     r9d, 250h
0x1800af596  lea     r8, aDhcpcmcloselis; "DhcpCMCloseListeningSocket"
0x1800af59d  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800af5a4  mov     ecx, eax
0x1800af5a6  mov     edi, eax
0x1800af5a8  call    DhcpPrintFOErrorEx
0x1800af5ad  mov     r14d, [rsp+68h+arg_8]
0x1800af5b2  mov     ebp, [rsp+68h+arg_0]
0x1800af5b6  lea     r15, [r13+48h]
0x1800af5ba  mov     rcx, r15; SRWLock
0x1800af5bd  call    cs:__imp_AcquireSRWLockShared
0x1800af5c4  nop     dword ptr [rax+rax+00h]
0x1800af5c9  test    esi, esi
0x1800af5cb  jz      short loc_1800AF5EA
0x1800af5cd  cmp     esi, 1
0x1800af5d0  jnz     short loc_1800AF5D6
0x1800af5d2  test    ebp, ebp
0x1800af5d4  jz      short loc_1800AF5EA
0x1800af5d6  mov     rcx, r15; SRWLock
0x1800af5d9  call    cs:__imp_ReleaseSRWLockShared
0x1800af5e0  nop     dword ptr [rax+rax+00h]
0x1800af5e5  jmp     loc_1800AF848
0x1800af5ea  mov     rcx, r15; SRWLock
0x1800af5ed  call    cs:__imp_ReleaseSRWLockShared
0x1800af5f4  nop     dword ptr [rax+rax+00h]
0x1800af5f9  mov     rcx, [rbx+10h]
0x1800af5fd  add     rcx, 8; lpCriticalSection
0x1800af601  call    cs:__imp_EnterCriticalSection
0x1800af608  nop     dword ptr [rax+rax+00h]
0x1800af60d  mov     eax, r14d
0x1800af610  lea     rsi, __ImageBase
0x1800af617  xor     ebp, ebp
0x1800af619  lea     r12, ds:0[rax*8]
0x1800af621  mov     rcx, [r12+rsi+100BE0h]; hEvent
0x1800af629  test    rcx, rcx
0x1800af62c  jz      short loc_1800AF66F
0x1800af62e  call    cs:__imp_WSACloseEvent
0x1800af635  nop     dword ptr [rax+rax+00h]
0x1800af63a  test    eax, eax
0x1800af63c  jnz     short loc_1800AF667
0x1800af63e  call    cs:__imp_WSAGetLastError
0x1800af645  nop     dword ptr [rax+rax+00h]
0x1800af64a  mov     r9d, 260h
0x1800af650  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800af657  mov     ecx, eax
0x1800af659  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800af660  mov     edi, eax
0x1800af662  call    DhcpPrintFOErrorEx
0x1800af667  mov     [r12+rsi+100BE0h], rbp
0x1800af66f  mov     rcx, [rbx+28h]; hEvent
0x1800af673  test    rcx, rcx
0x1800af676  jz      short loc_1800AF6B5
0x1800af678  call    cs:__imp_WSACloseEvent
0x1800af67f  nop     dword ptr [rax+rax+00h]
0x1800af684  test    eax, eax
0x1800af686  jnz     short loc_1800AF6B1
0x1800af688  call    cs:__imp_WSAGetLastError
0x1800af68f  nop     dword ptr [rax+rax+00h]
0x1800af694  mov     r9d, 263h
0x1800af69a  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800af6a1  mov     ecx, eax
0x1800af6a3  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800af6aa  mov     edi, eax
0x1800af6ac  call    DhcpPrintFOErrorEx
0x1800af6b1  mov     [rbx+28h], rbp
0x1800af6b5  mov     rcx, [rbx+30h]; hEvent
0x1800af6b9  test    rcx, rcx
0x1800af6bc  jz      short loc_1800AF6FB
0x1800af6be  call    cs:__imp_WSACloseEvent
0x1800af6c5  nop     dword ptr [rax+rax+00h]
0x1800af6ca  test    eax, eax
0x1800af6cc  jnz     short loc_1800AF6F7
0x1800af6ce  call    cs:__imp_WSAGetLastError
0x1800af6d5  nop     dword ptr [rax+rax+00h]
0x1800af6da  mov     r9d, 266h
0x1800af6e0  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800af6e7  mov     ecx, eax
0x1800af6e9  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800af6f0  mov     edi, eax
0x1800af6f2  call    DhcpPrintFOErrorEx
0x1800af6f7  mov     [rbx+30h], rbp
0x1800af6fb  mov     rcx, [rbx+8]; s
0x1800af6ff  call    cs:__imp_closesocket
0x1800af706  nop     dword ptr [rax+rax+00h]
0x1800af70b  mov     esi, eax
0x1800af70d  cmp     eax, 0FFFFFFFFh
0x1800af710  jnz     short loc_1800AF73B
0x1800af712  call    cs:__imp_WSAGetLastError
0x1800af719  nop     dword ptr [rax+rax+00h]
0x1800af71e  mov     r9d, 269h
0x1800af724  lea     r8, aClosesocket; "closesocket"
0x1800af72b  mov     ecx, eax
0x1800af72d  lea     rdx, aDhcpcmclosecon; "DhcpCMCloseConnection"
0x1800af734  mov     esi, eax
0x1800af736  call    DhcpPrintFOErrorEx
0x1800af73b  mov     rcx, [rbx+18h]; lpMem
0x1800af73f  test    esi, esi
0x1800af741  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800af749  cmovz   esi, edi
0x1800af74c  mov     edi, esi
0x1800af74e  test    rcx, rcx
0x1800af751  jz      short loc_1800AF75F
0x1800af753  call    ResetAndRestoreInFreePacketPool
0x1800af758  mov     [rbx+18h], rbp
0x1800af75c  mov     [rbx+20h], ebp
0x1800af75f  mov     rcx, r15; SRWLock
0x1800af762  call    cs:__imp_AcquireSRWLockExclusive
0x1800af769  nop     dword ptr [rax+rax+00h]
0x1800af76e  mov     rcx, r15; SRWLock
0x1800af771  mov     [r13+1E0h], rbp
0x1800af778  mov     [r13+1E8h], rbp
0x1800af77f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800af786  nop     dword ptr [rax+rax+00h]
0x1800af78b  mov     rcx, [rbx+10h]
0x1800af78f  add     rcx, 8; lpCriticalSection
0x1800af793  call    cs:__imp_LeaveCriticalSection
0x1800af79a  nop     dword ptr [rax+rax+00h]
0x1800af79f  lea     rcx, gSocketLock; lpCriticalSection
0x1800af7a6  call    cs:__imp_EnterCriticalSection
0x1800af7ad  nop     dword ptr [rax+rax+00h]
0x1800af7b2  mov     rax, [rbx+10h]
0x1800af7b6  lea     rcx, gSocketLock; lpCriticalSection
0x1800af7bd  mov     [rax], ebp
0x1800af7bf  mov     [rbx+10h], rbp
0x1800af7c3  call    cs:__imp_LeaveCriticalSection
0x1800af7ca  nop     dword ptr [rax+rax+00h]
0x1800af7cf  mov     rcx, cs:gDhcpHeap; hHeap
0x1800af7d6  mov     r8, rbx; lpMem
0x1800af7d9  xor     edx, edx; dwFlags
0x1800af7db  call    cs:__imp_HeapFree
0x1800af7e2  nop     dword ptr [rax+rax+00h]
0x1800af7e7  mov     r8d, cs:gSocketEventTotal
0x1800af7ee  lea     r9, __ImageBase
0x1800af7f5  dec     r8d
0x1800af7f8  cmp     r14d, r8d
0x1800af7fb  jnb     short loc_1800AF839
0x1800af7fd  lea     edx, [r14+1]
0x1800af801  mov     rax, rva gSocketEventArray[r9+rdx*8]
0x1800af809  mov     [r12+r9+100BE0h], rax
0x1800af811  lea     r12, [r12+8]
0x1800af816  mov     rax, rva gSocketArray[r9+rdx*8]
0x1800af81e  mov     [rax], r14d
0x1800af821  mov     r14d, edx
0x1800af824  mov     rax, rva gSocketArray[r9+rdx*8]
0x1800af82c  mov     [r12+r9+1003B8h], rax
0x1800af834  cmp     edx, r8d
0x1800af837  jb      short loc_1800AF7FD
0x1800af839  mov     cs:gSocketEventTotal, r8d
0x1800af840  mov     rva gSocketArray[r9+r8*8], rbp
0x1800af848  mov     eax, edi
0x1800af84a  mov     rbx, [rsp+68h+arg_10]
0x1800af852  add     rsp, 30h
0x1800af856  pop     r15
0x1800af858  pop     r14
0x1800af85a  pop     r13
0x1800af85c  pop     r12
0x1800af85e  pop     rdi
0x1800af85f  pop     rsi
0x1800af860  pop     rbp
0x1800af861  retn
```
