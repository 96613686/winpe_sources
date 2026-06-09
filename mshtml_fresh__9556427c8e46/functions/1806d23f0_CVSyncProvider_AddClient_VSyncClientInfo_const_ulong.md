# CVSyncProvider::AddClient(VSyncClientInfo const *,ulong *)

- ea: `0x1806d23f0`
- end: `0x1806d2730`
- name: `?AddClient@CVSyncProvider@@UEAAJPEBUVSyncClientInfo@@PEAK@Z`
- size: `832`
- prototype: `__int64 __fastcall(CVSyncProvider *__hidden this, const struct VSyncClientInfo *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x18006b2e8`
- `0x180542708`
- `0x1806821c8`
- `0x1806d23f0`
- `0x180730768`
- `0x1810a7dc0`
- `0x1810a7e80`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x1806d257e`
- `KERNEL32!MapViewOfFile` at `0x1806d257e`
- `KERNEL32!OpenProcess` at `0x1806d2483`
- `KERNEL32!OpenProcess` at `0x1806d2483`
- `KERNEL32!UnmapViewOfFile` at `0x1806d2596`
- `KERNEL32!UnmapViewOfFile` at `0x1806d2596`
- `KERNEL32!LeaveCriticalSection` at `0x1806d26f2`
- `KERNEL32!LeaveCriticalSection` at `0x1806d26f2`
- `KERNEL32!EnterCriticalSection` at `0x1806d2631`
- `KERNEL32!EnterCriticalSection` at `0x1806d2631`
- `KERNEL32!SetEvent` at `0x1806d26e3`
- `KERNEL32!SetEvent` at `0x1806d26e3`
- `KERNEL32!GetCurrentProcess` at `0x1806d2521`
- `KERNEL32!GetCurrentProcess` at `0x1806d25d0`
- `KERNEL32!GetCurrentProcess` at `0x1806d2521`
- `KERNEL32!GetCurrentProcess` at `0x1806d25d0`
- `USER32!PostMessageW` at `0x1806d26a1`
- `USER32!PostMessageW` at `0x1806d26a1`
- `USER32!GetWindowThreadProcessId` at `0x1806d2504`
- `USER32!GetWindowThreadProcessId` at `0x1806d2504`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1806d254d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1806d25fc`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1806d254d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1806d25fc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1806d24e8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1806d24e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1806d24b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1806d24b5`

## pseudocode

```c
__int64 __fastcall CVSyncProvider::AddClient(CVSyncProvider *this, const struct VSyncClientInfo *a2, unsigned int *a3)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rsi
  __int128 v5; // xmm1
  unsigned int v6; // edx
  void *v7; // rbx
  unsigned int v8; // ebx
  void *v9; // rcx
  int v10; // edi
  DWORD WindowThreadProcessId; // eax
  HANDLE CurrentProcess; // rax
  _DWORD *v13; // rax
  const void *v14; // rcx
  _DWORD *v15; // rdi
  HANDLE v16; // rax
  unsigned int v17; // edx
  __int64 v18; // rdx
  DWORD dwProcessId; // [rsp+40h] [rbp-30h] BYREF
  _QWORD *v21; // [rsp+48h] [rbp-28h] BYREF
  HANDLE v22; // [rsp+50h] [rbp-20h] BYREF
  HANDLE TargetHandle; // [rsp+58h] [rbp-18h] BYREF
  HANDLE v24[2]; // [rsp+60h] [rbp-10h] BYREF

  v3 = (_QWORD *)MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 88);
  v4 = v3;
  if ( v3 )
  {
    *v3 = v3;
    v3[1] = v3;
    v3[2] = 0;
    v3[3] = 0;
    v3[4] = 0;
    v3[5] = 0;
    v3[7] = 0;
    v3[9] = 0;
    v3[10] = 0;
  }
  else
  {
    v4 = 0;
  }
  v21 = v4;
  v5 = *((_OWORD *)a2 + 1);
  *((_OWORD *)v4 + 1) = *(_OWORD *)a2;
  *((_OWORD *)v4 + 2) = v5;
  v4[4] = 0;
  v4[3] = 0;
  v22 = OpenProcess(0x100040u, 0, *((_DWORD *)v4 + 4));
  v7 = v22;
  if ( v22 )
  {
    v24[0] = OpenThread(0x100040u, 0, *((_DWORD *)v4 + 5));
    TSmartHandle<void *,&int CloseHandle(void *)>::operator=(v4 + 9, v24);
    v9 = (void *)v4[9];
    if ( v9
      && (v10 = *((_DWORD *)v4 + 4), GetProcessIdOfThread(v9) == v10)
      && (dwProcessId = 0,
          WindowThreadProcessId = GetWindowThreadProcessId((HWND)v4[5], &dwProcessId),
          dwProcessId == *((_DWORD *)v4 + 4))
      && WindowThreadProcessId == *((_DWORD *)v4 + 5) )
    {
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !DuplicateHandle(v7, *((HANDLE *)a2 + 1), CurrentProcess, &TargetHandle, 0, 0, 2u) )
        goto LABEL_12;
      v13 = MapViewOfFile(TargetHandle, 6u, 0, 0, 0x28u);
      v14 = (const void *)v4[7];
      v15 = v13;
      if ( v14 )
        UnmapViewOfFile(v14);
      v4[7] = v15;
      if ( v15
        && (v4[8] = v15, *v15 == -838796627)
        && *(_DWORD *)(v4[8] + 4LL) == 1
        && *(_DWORD *)(v4[8] + 8LL) >= 0x28u
        && (v16 = GetCurrentProcess(), DuplicateHandle(v7, *((HANDLE *)a2 + 2), v16, (LPHANDLE)v4 + 10, 0, 0, 2u)) )
      {
        v4[4] = v4[10];
        if ( *((_DWORD *)this + 20) >= 0x3Eu )
          CVSyncProvider::PruneDeadClients(this);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
        if ( *((_DWORD *)this + 20) < 0x3Eu )
        {
          v8 = 0;
          if ( *((_BYTE *)this + 104) )
          {
            *(_DWORD *)(v4[8] + 20LL) = *((_DWORD *)this + 27);
            *(_DWORD *)(v4[8] + 16LL) = 1;
            if ( *(int *)(v4[8] + 20LL) < 0 )
              PostMessageW((HWND)v4[5], 0x402u, *(int *)(v4[8] + 20LL), *(unsigned int *)(v4[8] + 36LL));
          }
          v17 = *((_DWORD *)this + 21);
          v21 = 0;
          *((_DWORD *)this + 21) = v17 + 1;
          *((_DWORD *)v4 + 12) = v17;
          *a3 = v17;
          v18 = *((_QWORD *)this + 7);
          v4[1] = (char *)this + 56;
          *v4 = v18;
          *(_QWORD *)(v18 + 8) = v4;
          *(_QWORD *)v4[1] = v4;
          ++*((_DWORD *)this + 20);
          SetEvent(*((HANDLE *)this + 12));
        }
        else
        {
          v8 = -2147467259;
          *(_DWORD *)(v4[8] + 16LL) = 1;
          *(_DWORD *)(v4[8] + 20LL) = -2147467259;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      }
      else
      {
LABEL_12:
        v8 = -2147418113;
      }
      TSmartHandle<void *,&int CloseHandle(void *)>::~TSmartHandle<void *,&int CloseHandle(void *)>(&TargetHandle);
    }
    else
    {
      v8 = -2147418113;
    }
    TSmartHandle<void *,&int CloseHandle(void *)>::~TSmartHandle<void *,&int CloseHandle(void *)>(&v22);
    TSmartMemory<CVSyncProvider::VSyncClient>::~TSmartMemory<CVSyncProvider::VSyncClient>(&v21);
  }
  else
  {
    v8 = -2147418113;
    CVSyncProvider::VSyncClient::`scalar deleting destructor'((CVSyncProvider::VSyncClient *)v4, v6);
  }
  return v8;
}

```

## disassembly

```asm
0x1806d23f0  mov     rax, rsp
0x1806d23f3  mov     [rax+20h], rbx
0x1806d23f7  mov     [rax+18h], r8
0x1806d23fb  mov     [rax+10h], rdx
0x1806d23ff  mov     [rax+8], rcx
0x1806d2403  push    rbp
0x1806d2404  push    rsi
0x1806d2405  push    rdi
0x1806d2406  push    r14
0x1806d2408  push    r15
0x1806d240a  mov     rbp, rsp
0x1806d240d  sub     rsp, 70h
0x1806d2411  mov     rcx, cs:g_hProcessHeap
0x1806d2418  mov     edx, 58h ; 'X'
0x1806d241d  call    ??$HeapAllocClear@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAllocClear<1>(void *,unsigned __int64)
0x1806d2422  xor     r15d, r15d
0x1806d2425  mov     rsi, rax
0x1806d2428  test    rax, rax
0x1806d242b  jz      short loc_1806D2452
0x1806d242d  mov     [rax], rax
0x1806d2430  mov     [rax+8], rax
0x1806d2434  mov     [rax+10h], r15
0x1806d2438  mov     [rax+18h], r15
0x1806d243c  mov     [rax+20h], r15
0x1806d2440  mov     [rax+28h], r15
0x1806d2444  mov     [rax+38h], r15
0x1806d2448  mov     [rax+48h], r15
0x1806d244c  mov     [rax+50h], r15
0x1806d2450  jmp     short loc_1806D2455
0x1806d2452  mov     rsi, r15
0x1806d2455  mov     r14, [rbp+arg_8]
0x1806d2459  mov     edi, 100040h
0x1806d245e  xor     edx, edx; bInheritHandle
0x1806d2460  mov     [rbp+var_28], rsi
0x1806d2464  mov     ecx, edi; dwDesiredAccess
0x1806d2466  movups  xmm0, xmmword ptr [r14]
0x1806d246a  movups  xmm1, xmmword ptr [r14+10h]
0x1806d246f  movups  xmmword ptr [rsi+10h], xmm0
0x1806d2473  movups  xmmword ptr [rsi+20h], xmm1
0x1806d2477  mov     [rsi+20h], r15
0x1806d247b  mov     [rsi+18h], r15
0x1806d247f  mov     r8d, [rsi+10h]; dwProcessId
0x1806d2483  call    cs:__imp_OpenProcess
0x1806d248a  nop     dword ptr [rax+rax+00h]
0x1806d248f  mov     [rbp+var_20], rax
0x1806d2493  mov     rbx, rax
0x1806d2496  test    rax, rax
0x1806d2499  jnz     short loc_1806D24AD
0x1806d249b  mov     rcx, rsi; this
0x1806d249e  mov     ebx, 8000FFFFh
0x1806d24a3  call    ??_GVSyncClient@CVSyncProvider@@QEAAPEAXI@Z; CVSyncProvider::VSyncClient::`scalar deleting destructor'(uint)
0x1806d24a8  jmp     loc_1806D2719
0x1806d24ad  mov     r8d, [rsi+14h]; dwThreadId
0x1806d24b1  xor     edx, edx; bInheritHandle
0x1806d24b3  mov     ecx, edi; dwDesiredAccess
0x1806d24b5  call    cs:__imp_OpenThread
0x1806d24bc  nop     dword ptr [rax+rax+00h]
0x1806d24c1  lea     rdx, [rbp+var_10]
0x1806d24c5  mov     [rbp+var_10], rax
0x1806d24c9  lea     rcx, [rsi+48h]
0x1806d24cd  call    ??4?$TSmartHandle@PEAX$1?CloseHandle@@YAHPEAX@Z@@QEAAAEAPEAXAEBQEAX@Z; TSmartHandle<void *,&CloseHandle(void *)>::operator=(void * const &)
0x1806d24d2  mov     rcx, [rsi+48h]; Thread
0x1806d24d6  test    rcx, rcx
0x1806d24d9  jnz     short loc_1806D24E5
0x1806d24db  mov     ebx, 8000FFFFh
0x1806d24e0  jmp     loc_1806D2707
0x1806d24e5  mov     edi, [rsi+10h]
0x1806d24e8  call    cs:__imp_GetProcessIdOfThread
0x1806d24ef  nop     dword ptr [rax+rax+00h]
0x1806d24f4  cmp     eax, edi
0x1806d24f6  jnz     short loc_1806D24DB
0x1806d24f8  mov     [rbp+dwProcessId], r15d
0x1806d24fc  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1806d2500  mov     rcx, [rsi+28h]; hWnd
0x1806d2504  call    cs:__imp_GetWindowThreadProcessId
0x1806d250b  nop     dword ptr [rax+rax+00h]
0x1806d2510  mov     ecx, [rsi+10h]
0x1806d2513  cmp     [rbp+dwProcessId], ecx
0x1806d2516  jnz     short loc_1806D24DB
0x1806d2518  cmp     eax, [rsi+14h]
0x1806d251b  jnz     short loc_1806D24DB
0x1806d251d  mov     [rbp+TargetHandle], r15
0x1806d2521  call    cs:__imp_GetCurrentProcess
0x1806d2528  nop     dword ptr [rax+rax+00h]
0x1806d252d  mov     rdx, [r14+8]; hSourceHandle
0x1806d2531  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x1806d2535  mov     [rsp+70h+dwOptions], 2; dwOptions
0x1806d253d  mov     r8, rax; hTargetProcessHandle
0x1806d2540  mov     [rsp+70h+bInheritHandle], r15d; bInheritHandle
0x1806d2545  mov     rcx, rbx; hSourceProcessHandle
0x1806d2548  mov     [rsp+70h+dwDesiredAccess], r15d; dwDesiredAccess
0x1806d254d  call    cs:__imp_DuplicateHandle
0x1806d2554  nop     dword ptr [rax+rax+00h]
0x1806d2559  test    eax, eax
0x1806d255b  jnz     short loc_1806D2567
0x1806d255d  mov     ebx, 8000FFFFh
0x1806d2562  jmp     loc_1806D26FE
0x1806d2567  mov     rcx, [rbp+TargetHandle]; hFileMappingObject
0x1806d256b  xor     r9d, r9d; dwFileOffsetLow
0x1806d256e  xor     r8d, r8d; dwFileOffsetHigh
0x1806d2571  mov     qword ptr [rsp+70h+dwDesiredAccess], 28h ; '('; dwNumberOfBytesToMap
0x1806d257a  lea     edx, [r9+6]; dwDesiredAccess
0x1806d257e  call    cs:__imp_MapViewOfFile
0x1806d2585  nop     dword ptr [rax+rax+00h]
0x1806d258a  mov     rcx, [rsi+38h]; lpBaseAddress
0x1806d258e  mov     rdi, rax
0x1806d2591  test    rcx, rcx
0x1806d2594  jz      short loc_1806D25A2
0x1806d2596  call    cs:__imp_UnmapViewOfFile
0x1806d259d  nop     dword ptr [rax+rax+00h]
0x1806d25a2  mov     [rsi+38h], rdi
0x1806d25a6  test    rdi, rdi
0x1806d25a9  jz      short loc_1806D255D
0x1806d25ab  mov     [rsi+40h], rdi
0x1806d25af  mov     eax, [rdi]
0x1806d25b1  cmp     eax, 0CE00FAADh
0x1806d25b6  jnz     short loc_1806D255D
0x1806d25b8  mov     rax, [rsi+40h]
0x1806d25bc  mov     ecx, [rax+4]
0x1806d25bf  cmp     ecx, 1
0x1806d25c2  jnz     short loc_1806D255D
0x1806d25c4  mov     rax, [rsi+40h]
0x1806d25c8  mov     ecx, [rax+8]
0x1806d25cb  cmp     ecx, 28h ; '('
0x1806d25ce  jb      short loc_1806D255D
0x1806d25d0  call    cs:__imp_GetCurrentProcess
0x1806d25d7  nop     dword ptr [rax+rax+00h]
0x1806d25dc  mov     rdx, [r14+10h]; hSourceHandle
0x1806d25e0  lea     r9, [rsi+50h]; lpTargetHandle
0x1806d25e4  mov     [rsp+70h+dwOptions], 2; dwOptions
0x1806d25ec  mov     r8, rax; hTargetProcessHandle
0x1806d25ef  mov     [rsp+70h+bInheritHandle], r15d; bInheritHandle
0x1806d25f4  mov     rcx, rbx; hSourceProcessHandle
0x1806d25f7  mov     [rsp+70h+dwDesiredAccess], r15d; dwDesiredAccess
0x1806d25fc  call    cs:__imp_DuplicateHandle
0x1806d2603  nop     dword ptr [rax+rax+00h]
0x1806d2608  test    eax, eax
0x1806d260a  jz      loc_1806D255D
0x1806d2610  mov     rdi, [rbp+arg_0]
0x1806d2614  mov     rax, [rsi+50h]
0x1806d2618  mov     [rsi+20h], rax
0x1806d261c  cmp     dword ptr [rdi+50h], 3Eh ; '>'
0x1806d2620  jb      short loc_1806D262A
0x1806d2622  mov     rcx, rdi; this
0x1806d2625  call    ?PruneDeadClients@CVSyncProvider@@AEAAXXZ; CVSyncProvider::PruneDeadClients(void)
0x1806d262a  lea     r14, [rdi+8]
0x1806d262e  mov     rcx, r14; lpCriticalSection
0x1806d2631  call    cs:__imp_EnterCriticalSection
0x1806d2638  nop     dword ptr [rax+rax+00h]
0x1806d263d  cmp     dword ptr [rdi+50h], 3Eh ; '>'
0x1806d2641  jb      short loc_1806D265F
0x1806d2643  mov     rax, [rsi+40h]
0x1806d2647  mov     ebx, 80004005h
0x1806d264c  mov     dword ptr [rax+10h], 1
0x1806d2653  mov     rax, [rsi+40h]
0x1806d2657  mov     [rax+14h], ebx
0x1806d265a  jmp     loc_1806D26EF
0x1806d265f  mov     ebx, r15d
0x1806d2662  cmp     [rdi+68h], r15b
0x1806d2666  jz      short loc_1806D26AD
0x1806d2668  mov     rcx, [rsi+40h]
0x1806d266c  mov     eax, [rdi+6Ch]
0x1806d266f  mov     [rcx+14h], eax
0x1806d2672  mov     rax, [rsi+40h]
0x1806d2676  mov     dword ptr [rax+10h], 1
0x1806d267d  mov     rax, [rsi+40h]
0x1806d2681  mov     ecx, [rax+14h]
0x1806d2684  test    ecx, ecx
0x1806d2686  jns     short loc_1806D26AD
0x1806d2688  mov     rax, [rsi+40h]
0x1806d268c  mov     edx, 402h; Msg
0x1806d2691  mov     r9d, [rax+24h]; lParam
0x1806d2695  mov     rax, [rsi+40h]
0x1806d2699  movsxd  r8, dword ptr [rax+14h]; wParam
0x1806d269d  mov     rcx, [rsi+28h]; hWnd
0x1806d26a1  call    cs:__imp_PostMessageW
0x1806d26a8  nop     dword ptr [rax+rax+00h]
0x1806d26ad  mov     edx, [rdi+54h]
0x1806d26b0  mov     [rbp+var_28], r15
0x1806d26b4  lea     eax, [rdx+1]
0x1806d26b7  mov     [rdi+54h], eax
0x1806d26ba  mov     rax, [rbp+arg_10]
0x1806d26be  mov     [rsi+30h], edx
0x1806d26c1  mov     [rax], edx
0x1806d26c3  lea     rax, [rdi+38h]
0x1806d26c7  mov     rdx, [rax]
0x1806d26ca  mov     [rsi+8], rax
0x1806d26ce  mov     [rsi], rdx
0x1806d26d1  mov     [rdx+8], rsi
0x1806d26d5  mov     rax, [rsi+8]
0x1806d26d9  mov     [rax], rsi
0x1806d26dc  inc     dword ptr [rdi+50h]
0x1806d26df  mov     rcx, [rdi+60h]; hEvent
0x1806d26e3  call    cs:__imp_SetEvent
0x1806d26ea  nop     dword ptr [rax+rax+00h]
0x1806d26ef  mov     rcx, r14; lpCriticalSection
0x1806d26f2  call    cs:__imp_LeaveCriticalSection
0x1806d26f9  nop     dword ptr [rax+rax+00h]
0x1806d26fe  lea     rcx, [rbp+TargetHandle]
0x1806d2702  call    ??1?$TSmartHandle@PEAX$1?CloseHandle@@YAHPEAX@Z@@QEAA@XZ; TSmartHandle<void *,&CloseHandle(void *)>::~TSmartHandle<void *,&CloseHandle(void *)>(void)
0x1806d2707  lea     rcx, [rbp+var_20]
0x1806d270b  call    ??1?$TSmartHandle@PEAX$1?CloseHandle@@YAHPEAX@Z@@QEAA@XZ; TSmartHandle<void *,&CloseHandle(void *)>::~TSmartHandle<void *,&CloseHandle(void *)>(void)
0x1806d2710  lea     rcx, [rbp+var_28]
0x1806d2714  call    ??1?$TSmartMemory@UVSyncClient@CVSyncProvider@@@@QEAA@XZ; TSmartMemory<CVSyncProvider::VSyncClient>::~TSmartMemory<CVSyncProvider::VSyncClient>(void)
0x1806d2719  mov     eax, ebx
0x1806d271b  mov     rbx, [rsp+70h+arg_18]
0x1806d2723  add     rsp, 70h
0x1806d2727  pop     r15
0x1806d2729  pop     r14
0x1806d272b  pop     rdi
0x1806d272c  pop     rsi
0x1806d272d  pop     rbp
0x1806d272e  retn
```
