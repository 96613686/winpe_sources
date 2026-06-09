# ConnectThread

- ea: `0x180046790`
- end: `0x180046c2b`
- name: `ConnectThread`
- size: `1179`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180008250`
- `0x1800222f0`
- `0x1800389d8`
- `0x18003ae8c`
- `0x18003b344`
- `0x180044800`
- `0x180046790`
- `0x18004b024`
- `0x180051b7c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180046817`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180046817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800467f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800467f0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180046802`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180046802`
- `ntdll!NtWaitForMultipleObjects` at `0x180046895`
- `ntdll!NtWaitForMultipleObjects` at `0x180046895`
- `ntdll!NtClose` at `0x180046bde`
- `ntdll!NtClose` at `0x180046bde`
- `ntdll!RtlFreeHeap` at `0x180046b64`
- `ntdll!RtlFreeHeap` at `0x180046b93`
- `ntdll!RtlFreeHeap` at `0x180046b64`
- `ntdll!RtlFreeHeap` at `0x180046b93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046b48`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046c0d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046b48`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046c0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800469fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046b2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800469fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046b2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046938`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046aed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046938`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046aed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800467be`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800468c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800468db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800467be`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800468c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800468db`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180046c1e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180046c1e`

## pseudocode

```c
__int64 __fastcall ConnectThread(_QWORD *Parameter)
{
  DWORD TickCount; // eax
  HMODULE v3; // r13
  DWORD v4; // r12d
  HANDLE CurrentThread; // rax
  __int64 v7; // rcx
  __int64 v8; // rdi
  char *v9; // rbx
  char *v10; // rsi
  char *v11; // r14
  char *v12; // rcx
  void *v13; // rax
  bool v14; // zf
  volatile signed __int32 *v15; // rbp
  char *v16; // rbx
  HMODULE v17; // r13
  signed int i; // edi
  __int64 v19; // rbx
  unsigned int v20; // [rsp+30h] [rbp-98h] BYREF
  HMODULE hLibModule; // [rsp+38h] [rbp-90h]
  _OWORD v22[3]; // [rsp+40h] [rbp-88h] BYREF

  v20 = 0;
  TickCount = GetTickCount();
  v3 = (HMODULE)Parameter[3];
  memset(&v22[1], 0, 28);
  hLibModule = v3;
  v4 = TickCount;
  Parameter[3] = -1;
  v22[0] = 0;
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 1);
  if ( TlsSetValue(MSAFD_SockTlsSlot, Parameter) )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          _InterlockedExchange(&SockSanCurrentWaitEvents, SockSanNumWaitEvents);
          v8 = NtWaitForMultipleObjects(
                 SockSanNumWaitEvents,
                 ConnectData,
                 WaitAny,
                 1u,
                 (PLARGE_INTEGER)((unsigned __int64)&qword_180056010 & -(__int64)(ConnectThreadWaitTimeout != 0)));
          if ( ExitConnectThread )
          {
            LOBYTE(v7) = 1;
            CheckForStuckLargeSends(v7);
            v17 = hLibModule;
            for ( i = 0; i < (int)SockSanNumWaitEvents; ConnectData[v19] = 0 )
            {
              v19 = i;
              NtClose(ConnectData[i++]);
            }
            SockSanNumWaitEvents = 0;
            DeleteCriticalSection(&ConnCritSec);
            FreeLibraryAndExitThread(v17, 0);
          }
          _InterlockedExchange(&SockSanCurrentWaitEvents, SockSanNumWaitEvents);
          if ( (_DWORD)v8 != 258 && GetTickCount() - v4 <= 0x258 )
            break;
          v4 = GetTickCount();
          CheckForStuckLargeSends(0);
        }
        while ( (_DWORD)v8 == 258 );
        if ( (unsigned int)v8 <= 0x3F )
          break;
        if ( (_DWORD)v8 == 257 )
          ConnectThreadWaitTimeout = 1;
      }
      if ( (BYTE1(xmmword_180063D60) & 0x40) != 0 )
        WPP_SF_dq(1038, 260, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, (unsigned int)v8, ConnectData[v8]);
      EnterCriticalSection(&ConnCritSec);
      v9 = (char *)ConnectData[v8 + 64];
      v10 = 0;
      if ( v9 )
        break;
LABEL_40:
      LeaveCriticalSection(&ConnCritSec);
      while ( v10 )
      {
        v16 = v10;
        v10 = (char *)*((_QWORD *)v10 + 117);
        DeleteCriticalSection((LPCRITICAL_SECTION)(v16 + 48));
        RtlFreeHeap(SockPrivateHeap, 0, *((PVOID *)v16 + 27));
        if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)v16 + 1), 0xFFFFFFFF) == 1 )
          SockDestroySocket(*((_QWORD *)v16 + 1));
        RtlFreeHeap(SockPrivateHeap, 0, v16);
      }
    }
    while ( 1 )
    {
      v11 = (char *)*((_QWORD *)v9 + 117);
      if ( (v9[802] & 2) == 0 )
        break;
      v12 = v9 + 944;
      if ( v11 )
        *((_QWORD *)v11 + 118) = *(_QWORD *)v12;
      v13 = (void *)*((_QWORD *)v9 + 117);
      if ( *(_QWORD *)v12 )
        *(_QWORD *)(*(_QWORD *)v12 + 936LL) = v13;
      else
        ConnectData[v8 + 64] = v13;
      v9[802] &= ~2u;
      v14 = (v9[802] & 4) == 0;
      *((_QWORD *)v9 + 117) = -1;
      *(_QWORD *)v12 = -1;
      if ( v14 )
      {
        if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)v9 + 1), 0xFFFFFFFF) == 1 )
          SockDestroySocket(*((_QWORD *)v9 + 1));
      }
      else
      {
        *((_QWORD *)v9 + 117) = v10;
        v10 = v9;
      }
LABEL_39:
      v9 = v11;
      if ( !v11 )
        goto LABEL_40;
    }
    v15 = *(volatile signed __int32 **)v9;
    _InterlockedIncrement(*(volatile signed __int32 **)v9);
    LeaveCriticalSection(&ConnCritSec);
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _OWORD *, unsigned int *))(*((_QWORD *)v9 + 2) + 136LL))(
           *((_QWORD *)v9 + 13),
           0,
           v22,
           &v20) )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 261, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v20);
      if ( *((_DWORD *)v9 + 38) != 2 )
        goto LABEL_37;
    }
    else
    {
      if ( LODWORD(v22[0]) != 16 )
      {
        if ( LODWORD(v22[0]) == 8 )
        {
          if ( LODWORD(v22[1]) )
          {
            if ( (xmmword_180063D60 & 2) != 0 )
              WPP_SF_d(1025, 262, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, LODWORD(v22[1]));
          }
          else
          {
            HandleSanAcceptIndication(v9);
          }
        }
        else if ( LODWORD(v22[0]) && (xmmword_180063D60 & 2) != 0 )
        {
          WPP_SF_d(1025, 263, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, LODWORD(v22[0]));
        }
        goto LABEL_37;
      }
      HandleSanConnectIndication(v9);
      if ( DWORD1(v22[1]) )
      {
LABEL_37:
        EnterCriticalSection(&ConnCritSec);
        if ( _InterlockedExchangeAdd(v15, 0xFFFFFFFF) == 1 )
          SockDestroySocket(v15);
        goto LABEL_39;
      }
    }
    SockSanRemoveFromWaitList(v9, (unsigned int)v8);
    goto LABEL_37;
  }
  MSAFD_SockTlsSlot = -1;
  return 1;
}

```

## disassembly

```asm
0x180046790  push    rbx
0x180046792  push    rbp
0x180046793  push    rsi
0x180046794  push    rdi
0x180046795  push    r12
0x180046797  push    r13
0x180046799  push    r14
0x18004679b  push    r15
0x18004679d  sub     rsp, 88h
0x1800467a4  mov     rax, cs:__security_cookie
0x1800467ab  xor     rax, rsp
0x1800467ae  mov     [rsp+0C8h+var_58], rax
0x1800467b3  mov     rbx, rcx
0x1800467b6  mov     [rsp+0C8h+var_98], 0
0x1800467be  call    cs:__imp_GetTickCount
0x1800467c5  nop     dword ptr [rax+rax+00h]
0x1800467ca  mov     r13, [rbx+18h]
0x1800467ce  xorps   xmm0, xmm0
0x1800467d1  movups  xmmword ptr [rsp+0C8h+var_78], xmm0
0x1800467d6  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800467da  mov     [rsp+0C8h+hLibModule], r13
0x1800467df  movups  xmmword ptr [rsp+0C8h+var_78+0Ch], xmm0
0x1800467e4  mov     r12d, eax
0x1800467e7  mov     [rbx+18h], rbp
0x1800467eb  movups  [rsp+0C8h+var_88], xmm0
0x1800467f0  call    cs:__imp_GetCurrentThread
0x1800467f7  nop     dword ptr [rax+rax+00h]
0x1800467fc  mov     rcx, rax; hThread
0x1800467ff  lea     edx, [rbp+2]; nPriority
0x180046802  call    cs:__imp_SetThreadPriority
0x180046809  nop     dword ptr [rax+rax+00h]
0x18004680e  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180046814  mov     rdx, rbx; lpTlsValue
0x180046817  call    cs:__imp_TlsSetValue
0x18004681e  nop     dword ptr [rax+rax+00h]
0x180046823  test    eax, eax
0x180046825  jnz     short loc_180046856
0x180046827  mov     cs:MSAFD_SockTlsSlot, 0FFFFFFFFh
0x180046831  lea     eax, [rbp+2]
0x180046834  mov     rcx, [rsp+0C8h+var_58]
0x180046839  xor     rcx, rsp; StackCookie
0x18004683c  call    __security_check_cookie
0x180046841  add     rsp, 88h
0x180046848  pop     r15
0x18004684a  pop     r14
0x18004684c  pop     r13
0x18004684e  pop     r12
0x180046850  pop     rdi
0x180046851  pop     rsi
0x180046852  pop     rbp
0x180046853  pop     rbx
0x180046854  retn
0x180046856  lea     r14, ConnectData
0x18004685d  mov     eax, cs:SockSanNumWaitEvents
0x180046863  mov     r9b, 1; Alertable
0x180046866  xchg    eax, cs:SockSanCurrentWaitEvents
0x18004686c  mov     cl, cs:ConnectThreadWaitTimeout
0x180046872  mov     r8d, 1; WaitType
0x180046878  neg     cl
0x18004687a  mov     rdx, r14; Object
0x18004687d  lea     rcx, qword_180056010
0x180046884  sbb     rax, rax
0x180046887  and     rax, rcx
0x18004688a  mov     ecx, cs:SockSanNumWaitEvents; Count
0x180046890  mov     [rsp+0C8h+Time], rax; Time
0x180046895  call    cs:__imp_NtWaitForMultipleObjects
0x18004689c  nop     dword ptr [rax+rax+00h]
0x1800468a1  cmp     cs:ExitConnectThread, 0
0x1800468a8  movsxd  rdi, eax
0x1800468ab  jnz     loc_180046BC1
0x1800468b1  mov     ecx, cs:SockSanNumWaitEvents
0x1800468b7  xchg    ecx, cs:SockSanCurrentWaitEvents
0x1800468bd  cmp     edi, 102h
0x1800468c3  jz      short loc_1800468DB
0x1800468c5  call    cs:__imp_GetTickCount
0x1800468cc  nop     dword ptr [rax+rax+00h]
0x1800468d1  sub     eax, r12d
0x1800468d4  cmp     eax, 258h
0x1800468d9  jbe     short loc_1800468FD
0x1800468db  call    cs:__imp_GetTickCount
0x1800468e2  nop     dword ptr [rax+rax+00h]
0x1800468e7  xor     ecx, ecx
0x1800468e9  mov     r12d, eax
0x1800468ec  call    CheckForStuckLargeSends
0x1800468f1  cmp     edi, 102h
0x1800468f7  jz      loc_18004685D
0x1800468fd  cmp     edi, 3Fh ; '?'
0x180046900  ja      loc_180046BA9
0x180046906  test    byte ptr cs:xmmword_180063D60+1, 40h
0x18004690d  jz      short loc_180046931
0x18004690f  mov     rax, [r14+rdi*8]
0x180046913  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004691a  mov     edx, 104h
0x18004691f  mov     [rsp+0C8h+Time], rax
0x180046924  mov     ecx, 40Eh
0x180046929  mov     r9d, edi
0x18004692c  call    WPP_SF_dq
0x180046931  lea     rcx, ConnCritSec; lpCriticalSection
0x180046938  call    cs:__imp_EnterCriticalSection
0x18004693f  nop     dword ptr [rax+rax+00h]
0x180046944  mov     rbx, [r14+rdi*8+200h]
0x18004694c  xor     esi, esi
0x18004694e  test    rbx, rbx
0x180046951  jz      loc_180046B25
0x180046957  lea     r13, ConnectData
0x18004695e  test    byte ptr [rbx+322h], 2
0x180046965  mov     r14, [rbx+3A8h]
0x18004696c  jz      short loc_1800469ED
0x18004696e  lea     rcx, [rbx+3B0h]
0x180046975  test    r14, r14
0x180046978  jz      short loc_180046984
0x18004697a  mov     rax, [rcx]
0x18004697d  mov     [r14+3B0h], rax
0x180046984  mov     rdx, [rcx]
0x180046987  mov     rax, [rbx+3A8h]
0x18004698e  test    rdx, rdx
0x180046991  jz      short loc_18004699C
0x180046993  mov     [rdx+3A8h], rax
0x18004699a  jmp     short loc_1800469A4
0x18004699c  mov     [r13+rdi*8+200h], rax
0x1800469a4  and     byte ptr [rbx+322h], 0FDh
0x1800469ab  test    byte ptr [rbx+322h], 4
0x1800469b2  mov     [rbx+3A8h], rbp
0x1800469b9  mov     [rcx], rbp
0x1800469bc  jz      short loc_1800469CD
0x1800469be  mov     [rbx+3A8h], rsi
0x1800469c5  mov     rsi, rbx
0x1800469c8  jmp     loc_180046B12
0x1800469cd  mov     rax, [rbx+8]
0x1800469d1  mov     ecx, ebp
0x1800469d3  lock xadd [rax], ecx
0x1800469d7  add     ecx, ebp
0x1800469d9  jnz     loc_180046B12
0x1800469df  mov     rcx, [rbx+8]
0x1800469e3  call    SockDestroySocket
0x1800469e8  jmp     loc_180046B12
0x1800469ed  mov     rbp, [rbx]
0x1800469f0  lock inc dword ptr [rbp+0]
0x1800469f4  lea     rcx, ConnCritSec; lpCriticalSection
0x1800469fb  call    cs:__imp_LeaveCriticalSection
0x180046a02  nop     dword ptr [rax+rax+00h]
0x180046a07  mov     rax, [rbx+10h]
0x180046a0b  lea     r9, [rsp+0C8h+var_98]
0x180046a10  mov     rcx, [rbx+68h]
0x180046a14  lea     r8, [rsp+0C8h+var_88]
0x180046a19  xor     edx, edx
0x180046a1b  mov     rax, [rax+88h]
0x180046a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a27  test    eax, eax
0x180046a29  jz      short loc_180046A5D
0x180046a2b  test    byte ptr cs:xmmword_180063D60, 2
0x180046a32  jz      short loc_180046A4F
0x180046a34  mov     r9d, [rsp+0C8h+var_98]
0x180046a39  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180046a40  mov     edx, 105h
0x180046a45  mov     ecx, 401h
0x180046a4a  call    WPP_SF_d
0x180046a4f  cmp     dword ptr [rbx+98h], 2
0x180046a56  jz      short loc_180046A7B
0x180046a58  jmp     loc_180046AE6
0x180046a5d  mov     r9d, dword ptr [rsp+0C8h+var_88]
0x180046a62  cmp     r9d, 10h
0x180046a66  jnz     short loc_180046A87
0x180046a68  mov     edx, dword ptr [rsp+0C8h+var_78+4]
0x180046a6c  mov     rcx, rbx
0x180046a6f  call    HandleSanConnectIndication
0x180046a74  cmp     dword ptr [rsp+0C8h+var_78+4], 0
0x180046a79  jnz     short loc_180046AE6
0x180046a7b  mov     edx, edi
0x180046a7d  mov     rcx, rbx
0x180046a80  call    SockSanRemoveFromWaitList
0x180046a85  jmp     short loc_180046AE6
0x180046a87  cmp     r9d, 8
0x180046a8b  jnz     short loc_180046AC2
0x180046a8d  mov     r9d, dword ptr [rsp+0C8h+var_78]
0x180046a92  test    r9d, r9d
0x180046a95  jnz     short loc_180046AA1
0x180046a97  mov     rcx, rbx
0x180046a9a  call    HandleSanAcceptIndication
0x180046a9f  jmp     short loc_180046AE6
0x180046aa1  test    byte ptr cs:xmmword_180063D60, 2
0x180046aa8  jz      short loc_180046AE6
0x180046aaa  mov     edx, 106h
0x180046aaf  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180046ab6  mov     ecx, 401h
0x180046abb  call    WPP_SF_d
0x180046ac0  jmp     short loc_180046AE6
0x180046ac2  test    r9d, r9d
0x180046ac5  jz      short loc_180046AE6
0x180046ac7  test    byte ptr cs:xmmword_180063D60, 2
0x180046ace  jz      short loc_180046AE6
0x180046ad0  mov     edx, 107h
0x180046ad5  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180046adc  mov     ecx, 401h
0x180046ae1  call    WPP_SF_d
0x180046ae6  lea     rcx, ConnCritSec; lpCriticalSection
0x180046aed  call    cs:__imp_EnterCriticalSection
0x180046af4  nop     dword ptr [rax+rax+00h]
0x180046af9  or      eax, 0FFFFFFFFh
0x180046afc  lock xadd [rbp+0], eax
0x180046b01  cmp     eax, 1
0x180046b04  jnz     short loc_180046B0E
0x180046b06  mov     rcx, rbp
0x180046b09  call    SockDestroySocket
0x180046b0e  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180046b12  mov     rbx, r14
0x180046b15  test    r14, r14
0x180046b18  jnz     loc_18004695E
0x180046b1e  lea     r14, ConnectData
0x180046b25  lea     rcx, ConnCritSec; lpCriticalSection
0x180046b2c  call    cs:__imp_LeaveCriticalSection
0x180046b33  nop     dword ptr [rax+rax+00h]
0x180046b38  jmp     short loc_180046B9F
0x180046b3a  mov     rbx, rsi
0x180046b3d  mov     rsi, [rsi+3A8h]
0x180046b44  lea     rcx, [rbx+30h]; lpCriticalSection
0x180046b48  call    cs:__imp_DeleteCriticalSection
0x180046b4f  nop     dword ptr [rax+rax+00h]
0x180046b54  mov     r8, [rbx+0D8h]; P
0x180046b5b  xor     edx, edx; Flags
0x180046b5d  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180046b64  call    cs:__imp_RtlFreeHeap
0x180046b6b  nop     dword ptr [rax+rax+00h]
0x180046b70  mov     rax, [rbx+8]
0x180046b74  mov     ecx, ebp
0x180046b76  lock xadd [rax], ecx
0x180046b7a  add     ecx, ebp
0x180046b7c  jnz     short loc_180046B87
0x180046b7e  mov     rcx, [rbx+8]
0x180046b82  call    SockDestroySocket
0x180046b87  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180046b8e  mov     r8, rbx; P
0x180046b91  xor     edx, edx; Flags
0x180046b93  call    cs:__imp_RtlFreeHeap
0x180046b9a  nop     dword ptr [rax+rax+00h]
0x180046b9f  test    rsi, rsi
0x180046ba2  jnz     short loc_180046B3A
0x180046ba4  jmp     loc_18004685D
0x180046ba9  cmp     edi, 101h
0x180046baf  jnz     loc_18004685D
0x180046bb5  mov     cs:ConnectThreadWaitTimeout, 1
0x180046bbc  jmp     loc_18004685D
0x180046bc1  mov     cl, 1
0x180046bc3  call    CheckForStuckLargeSends
0x180046bc8  mov     r13, [rsp+0C8h+hLibModule]
0x180046bcd  xor     edi, edi
0x180046bcf  cmp     cs:SockSanNumWaitEvents, edi
0x180046bd5  jle     short loc_180046BFC
0x180046bd7  movsxd  rbx, edi
0x180046bda  mov     rcx, [r14+rbx*8]; Handle
0x180046bde  call    cs:__imp_NtClose
0x180046be5  nop     dword ptr [rax+rax+00h]
0x180046bea  inc     edi
0x180046bec  mov     qword ptr [r14+rbx*8], 0
0x180046bf4  cmp     edi, cs:SockSanNumWaitEvents
0x180046bfa  jl      short loc_180046BD7
0x180046bfc  lea     rcx, ConnCritSec; lpCriticalSection
0x180046c03  mov     cs:SockSanNumWaitEvents, 0
0x180046c0d  call    cs:__imp_DeleteCriticalSection
0x180046c14  nop     dword ptr [rax+rax+00h]
0x180046c19  xor     edx, edx; dwExitCode
0x180046c1b  mov     rcx, r13; hLibModule
0x180046c1e  call    cs:__imp_FreeLibraryAndExitThread
0x180046c25  nop     dword ptr [rax+rax+00h]
0x180046c2a  int     3; Trap to Debugger
```
