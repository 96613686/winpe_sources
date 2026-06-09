# FREB_LOG_FILE_MANAGER::QueueWriteLogFile(uchar *,ulong)

- ea: `0x1800087a8`
- end: `0x180008952`
- name: `?QueueWriteLogFile@FREB_LOG_FILE_MANAGER@@QEAAJPEAEK@Z`
- size: `426`
- prototype: `__int64 __fastcall(FREB_SITE_META_STORED_CONTEXT **this, unsigned __int8 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005588`

## callees

- `0x180001048`
- `0x180006894`
- `0x1800087a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008939`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008939`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000892b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000892b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008891`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008891`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800087f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800087f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000889b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000889b`

## pseudocode

```c
__int64 __fastcall FREB_LOG_FILE_MANAGER::QueueWriteLogFile(
        FREB_SITE_META_STORED_CONTEXT **this,
        unsigned __int8 *a2,
        int a3)
{
  FREB_SITE_META_STORED_CONTEXT *v6; // rbp
  _QWORD *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r15
  __int64 v9; // rdx
  __int64 v10; // rcx
  volatile signed __int32 *v11; // rdi
  void *v12; // rsi
  int v13; // eax
  unsigned int v14; // edx
  int v15; // eax
  void *v16; // rcx
  signed int LastError; // eax
  signed int v18; // ebx
  HANDLE ProcessHeap; // rax
  FREB_SITE_META_STORED_CONTEXT *v20; // rdi
  HANDLE v21; // rax

  _InterlockedIncrement((volatile signed __int32 *)*this + 2);
  v6 = *this;
  if ( *((_DWORD *)*this + 18) / 0xAu > FREB_LOG_FILE_MANAGER::sm_dwThrottle )
    FREB_LOG_FILE_MANAGER::sm_dwThrottle = *((_DWORD *)*this + 18) / 0xAu;
  v7 = FREB_LOG_FILE_MANAGER::sm_pLossyQueue;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 32));
  if ( v6 && a2 )
  {
    if ( *((_DWORD *)v7 + 25) == *(_DWORD *)v7 )
    {
      v9 = *((unsigned int *)v7 + 23);
      v10 = v7[1];
      v11 = *(volatile signed __int32 **)(v10 + 8 * v9);
      v12 = *(void **)(v7[2] + 8 * v9);
      *(_QWORD *)(v10 + 8 * v9) = 0;
      *(_QWORD *)(v7[2] + 8LL * *((unsigned int *)v7 + 23)) = 0;
      LODWORD(v9) = (unsigned int)(*((_DWORD *)v7 + 23) + 1) % *(_DWORD *)v7;
      --*((_DWORD *)v7 + 25);
      *((_DWORD *)v7 + 23) = v9;
    }
    else
    {
      v11 = 0;
      v12 = 0;
    }
    *(_QWORD *)(v7[1] + 8LL * *((unsigned int *)v7 + 24)) = v6;
    *(_QWORD *)(v7[2] + 8LL * *((unsigned int *)v7 + 24)) = a2;
    *(_DWORD *)(v7[3] + 4LL * *((unsigned int *)v7 + 24)) = a3;
    v13 = *((_DWORD *)v7 + 24);
    ++*((_DWORD *)v7 + 25);
    v14 = (unsigned int)(v13 + 1) % *(_DWORD *)v7;
    v15 = *((_DWORD *)v7 + 22);
    *((_DWORD *)v7 + 24) = v14;
    if ( !v15 || (v16 = (void *)v7[9], *((_DWORD *)v7 + 22) = v15 - 1, SetEvent(v16)) )
    {
      v18 = 0;
    }
    else
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v11 = 0;
    v18 = -2147024809;
    v12 = 0;
  }
  LeaveCriticalSection(v8);
  if ( v11 && _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
  {
    FREB_SITE_META_STORED_CONTEXT::~FREB_SITE_META_STORED_CONTEXT((FREB_SITE_META_STORED_CONTEXT *)v11);
    operator delete((void *)v11);
  }
  if ( v12 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
  }
  if ( v18 < 0 )
  {
    v20 = *this;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*this + 2, 0xFFFFFFFF) == 1 && v20 )
    {
      FREB_SITE_META_STORED_CONTEXT::~FREB_SITE_META_STORED_CONTEXT(v20);
      operator delete(v20);
    }
    v21 = GetProcessHeap();
    HeapFree(v21, 0, a2);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800087a8  push    rbx
0x1800087aa  push    rbp
0x1800087ab  push    rsi
0x1800087ac  push    rdi
0x1800087ad  push    r12
0x1800087af  push    r13
0x1800087b1  push    r14
0x1800087b3  push    r15
0x1800087b5  sub     rsp, 28h
0x1800087b9  mov     rax, [rcx]
0x1800087bc  mov     r13d, r8d
0x1800087bf  mov     r12, rdx
0x1800087c2  mov     r14, rcx
0x1800087c5  lock inc dword ptr [rax+8]
0x1800087c9  mov     rbp, [rcx]
0x1800087cc  mov     eax, 0CCCCCCCDh
0x1800087d1  mul     dword ptr [rbp+48h]
0x1800087d4  shr     edx, 3
0x1800087d7  cmp     edx, cs:?sm_dwThrottle@FREB_LOG_FILE_MANAGER@@0KA; ulong FREB_LOG_FILE_MANAGER::sm_dwThrottle
0x1800087dd  jbe     short loc_1800087E5
0x1800087df  mov     cs:?sm_dwThrottle@FREB_LOG_FILE_MANAGER@@0KA, edx; ulong FREB_LOG_FILE_MANAGER::sm_dwThrottle
0x1800087e5  mov     rbx, cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x1800087ec  lea     r15, [rbx+20h]
0x1800087f0  mov     rcx, r15; lpCriticalSection
0x1800087f3  call    cs:__imp_EnterCriticalSection
0x1800087f9  test    rbp, rbp
0x1800087fc  jz      loc_1800088B6
0x180008802  test    r12, r12
0x180008805  jz      loc_1800088B6
0x18000880b  mov     eax, [rbx]
0x18000880d  cmp     [rbx+64h], eax
0x180008810  jnz     short loc_18000884D
0x180008812  mov     edx, [rbx+5Ch]
0x180008815  mov     rcx, [rbx+8]
0x180008819  mov     rax, [rbx+10h]
0x18000881d  mov     rdi, [rcx+rdx*8]
0x180008821  mov     rsi, [rax+rdx*8]
0x180008825  mov     qword ptr [rcx+rdx*8], 0
0x18000882d  xor     edx, edx
0x18000882f  mov     ecx, [rbx+5Ch]
0x180008832  mov     rax, [rbx+10h]
0x180008836  mov     qword ptr [rax+rcx*8], 0
0x18000883e  mov     eax, [rbx+5Ch]
0x180008841  inc     eax
0x180008843  div     dword ptr [rbx]
0x180008845  dec     dword ptr [rbx+64h]
0x180008848  mov     [rbx+5Ch], edx
0x18000884b  jmp     short loc_180008851
0x18000884d  xor     edi, edi
0x18000884f  xor     esi, esi
0x180008851  mov     ecx, [rbx+60h]
0x180008854  xor     edx, edx
0x180008856  mov     rax, [rbx+8]
0x18000885a  mov     [rax+rcx*8], rbp
0x18000885e  mov     ecx, [rbx+60h]
0x180008861  mov     rax, [rbx+10h]
0x180008865  mov     [rax+rcx*8], r12
0x180008869  mov     ecx, [rbx+60h]
0x18000886c  mov     rax, [rbx+18h]
0x180008870  mov     [rax+rcx*4], r13d
0x180008874  mov     eax, [rbx+60h]
0x180008877  inc     dword ptr [rbx+64h]
0x18000887a  inc     eax
0x18000887c  div     dword ptr [rbx]
0x18000887e  mov     eax, [rbx+58h]
0x180008881  mov     [rbx+60h], edx
0x180008884  test    eax, eax
0x180008886  jz      short loc_1800088B2
0x180008888  mov     rcx, [rbx+48h]; hEvent
0x18000888c  dec     eax
0x18000888e  mov     [rbx+58h], eax
0x180008891  call    cs:__imp_SetEvent
0x180008897  test    eax, eax
0x180008899  jnz     short loc_1800088B2
0x18000889b  call    cs:__imp_GetLastError
0x1800088a1  mov     ebx, eax
0x1800088a3  test    eax, eax
0x1800088a5  jle     short loc_1800088BF
0x1800088a7  movzx   ebx, ax
0x1800088aa  or      ebx, 80070000h
0x1800088b0  jmp     short loc_1800088BF
0x1800088b2  xor     ebx, ebx
0x1800088b4  jmp     short loc_1800088BF
0x1800088b6  xor     edi, edi
0x1800088b8  mov     ebx, 80070057h
0x1800088bd  xor     esi, esi
0x1800088bf  mov     rcx, r15; lpCriticalSection
0x1800088c2  call    cs:__imp_LeaveCriticalSection
0x1800088c8  or      ebp, 0FFFFFFFFh
0x1800088cb  test    rdi, rdi
0x1800088ce  jz      short loc_1800088EB
0x1800088d0  mov     eax, ebp
0x1800088d2  lock xadd [rdi+8], eax
0x1800088d7  add     eax, ebp
0x1800088d9  jnz     short loc_1800088EB
0x1800088db  mov     rcx, rdi; this
0x1800088de  call    ??1FREB_SITE_META_STORED_CONTEXT@@AEAA@XZ; FREB_SITE_META_STORED_CONTEXT::~FREB_SITE_META_STORED_CONTEXT(void)
0x1800088e3  mov     rcx, rdi; Block
0x1800088e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800088eb  test    rsi, rsi
0x1800088ee  jz      short loc_180008904
0x1800088f0  call    cs:__imp_GetProcessHeap
0x1800088f6  mov     r8, rsi; lpMem
0x1800088f9  xor     edx, edx; dwFlags
0x1800088fb  mov     rcx, rax; hHeap
0x1800088fe  call    cs:__imp_HeapFree
0x180008904  test    ebx, ebx
0x180008906  jns     short loc_18000893F
0x180008908  mov     rdi, [r14]
0x18000890b  mov     eax, ebp
0x18000890d  lock xadd [rdi+8], eax
0x180008912  add     eax, ebp
0x180008914  jnz     short loc_18000892B
0x180008916  test    rdi, rdi
0x180008919  jz      short loc_18000892B
0x18000891b  mov     rcx, rdi; this
0x18000891e  call    ??1FREB_SITE_META_STORED_CONTEXT@@AEAA@XZ; FREB_SITE_META_STORED_CONTEXT::~FREB_SITE_META_STORED_CONTEXT(void)
0x180008923  mov     rcx, rdi; Block
0x180008926  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000892b  call    cs:__imp_GetProcessHeap
0x180008931  mov     r8, r12; lpMem
0x180008934  xor     edx, edx; dwFlags
0x180008936  mov     rcx, rax; hHeap
0x180008939  call    cs:__imp_HeapFree
0x18000893f  mov     eax, ebx
0x180008941  add     rsp, 28h
0x180008945  pop     r15
0x180008947  pop     r14
0x180008949  pop     r13
0x18000894b  pop     r12
0x18000894d  pop     rdi
0x18000894e  pop     rsi
0x18000894f  pop     rbp
0x180008950  pop     rbx
0x180008951  retn
```
