# FREB_LOG_FILE_MANAGER::WriterThread(void *)

- ea: `0x180009050`
- end: `0x180009275`
- name: `?WriterThread@FREB_LOG_FILE_MANAGER@@SAKPEAX@Z`
- size: `549`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180006894`
- `0x180008d98`
- `0x180009050`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009132`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009132`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009124`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009124`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800090de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009216`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800090de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009216`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000907e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009168`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800091fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000907e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009168`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800091fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000923a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000923a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009154`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009154`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000922f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000922f`

## pseudocode

```c
__int64 __fastcall FREB_LOG_FILE_MANAGER::WriterThread(PVOID Parameter)
{
  unsigned int *v1; // rdi
  __int64 v2; // rbx
  void *v3; // rbp
  DWORD v4; // r14d
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // esi
  HANDLE ProcessHeap; // rax
  unsigned int *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  _DWORD *v12; // rbx
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  int v14; // ebx
  DWORD v15; // eax
  signed int LastError; // eax
  bool v17; // sf
  HANDLE Handles[9]; // [rsp+20h] [rbp-48h] BYREF

  if ( !FREB_LOG_FILE_MANAGER::sm_fShutdown )
  {
    while ( 1 )
    {
      v1 = (unsigned int *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 32));
      if ( v1[25] )
      {
        v5 = v1[23];
        v6 = *((_QWORD *)v1 + 1);
        v3 = *(void **)(*((_QWORD *)v1 + 2) + 8 * v5);
        v2 = *(_QWORD *)(v6 + 8 * v5);
        v4 = *(_DWORD *)(*((_QWORD *)v1 + 3) + 4 * v5);
        *(_QWORD *)(v6 + 8 * v5) = 0;
        *(_QWORD *)(*((_QWORD *)v1 + 2) + 8LL * v1[23]) = 0;
        *(_DWORD *)(*((_QWORD *)v1 + 3) + 4LL * v1[23]) = 0;
        LODWORD(v5) = (v1[23] + 1) % *v1;
        --v1[25];
        v1[23] = v5;
      }
      else
      {
        v2 = 0;
        v3 = 0;
        v4 = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
      v7 = 0;
      if ( v2 )
        break;
LABEL_15:
      v12 = FREB_LOG_FILE_MANAGER::sm_pLossyQueue;
      v13 = (struct _RTL_CRITICAL_SECTION *)((char *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 32);
      Handles[0] = *((HANDLE *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 9);
      Handles[1] = *((HANDLE *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 10);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 32));
      if ( v12[25] )
      {
        v14 = 0;
      }
      else
      {
        ++v12[22];
        v14 = 1;
      }
      LeaveCriticalSection(v13);
      if ( v14 )
      {
        v15 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
        if ( v15 == -1 )
        {
          LastError = GetLastError();
          v17 = LastError < 0;
          if ( LastError > 0 )
            v17 = 1;
          if ( v17 )
            return 0;
        }
        else if ( v15 > 1 )
        {
          return 0;
        }
      }
      if ( FREB_LOG_FILE_MANAGER::sm_fShutdown )
        return 0;
    }
    while ( 1 )
    {
      FREB_LOG_FILE_MANAGER::WriteLogFile((FREB_SITE_META_STORED_CONTEXT **)(v2 + 144), v3, v4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF) == 1 )
      {
        FREB_SITE_META_STORED_CONTEXT::~FREB_SITE_META_STORED_CONTEXT((FREB_SITE_META_STORED_CONTEXT *)v2);
        operator delete((void *)v2);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      if ( FREB_LOG_FILE_MANAGER::sm_fShutdown )
        break;
      if ( ++v7 > FREB_LOG_FILE_MANAGER::sm_dwThrottle )
      {
        Sleep(0x3E8u);
        v7 = 0;
      }
      v9 = (unsigned int *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 32));
      if ( v9[25] )
      {
        v10 = v9[23];
        v11 = *((_QWORD *)v9 + 1);
        v3 = *(void **)(*((_QWORD *)v9 + 2) + 8 * v10);
        v2 = *(_QWORD *)(v11 + 8 * v10);
        v4 = *(_DWORD *)(*((_QWORD *)v9 + 3) + 4 * v10);
        *(_QWORD *)(v11 + 8 * v10) = 0;
        *(_QWORD *)(*((_QWORD *)v9 + 2) + 8LL * v9[23]) = 0;
        *(_DWORD *)(*((_QWORD *)v9 + 3) + 4LL * v9[23]) = 0;
        LODWORD(v10) = (v9[23] + 1) % *v9;
        --v9[25];
        v9[23] = v10;
      }
      else
      {
        v2 = 0;
        v3 = 0;
        v4 = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
      if ( !v2 )
        goto LABEL_15;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009050  push    rbx
0x180009052  push    rbp
0x180009053  push    rsi
0x180009054  push    rdi
0x180009055  push    r12
0x180009057  push    r14
0x180009059  push    r15
0x18000905b  sub     rsp, 30h
0x18000905f  xor     r12d, r12d
0x180009062  cmp     cs:?sm_fShutdown@FREB_LOG_FILE_MANAGER@@0HA, r12d; int FREB_LOG_FILE_MANAGER::sm_fShutdown
0x180009069  jnz     loc_180009264
0x18000906f  or      r15d, 0FFFFFFFFh
0x180009073  mov     rdi, cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x18000907a  lea     rcx, [rdi+20h]; lpCriticalSection
0x18000907e  call    cs:__imp_EnterCriticalSection
0x180009084  cmp     [rdi+64h], r12d
0x180009088  jnz     short loc_180009095
0x18000908a  mov     rbx, r12
0x18000908d  mov     rbp, r12
0x180009090  mov     r14d, r12d
0x180009093  jmp     short loc_1800090DA
0x180009095  mov     edx, [rdi+5Ch]
0x180009098  mov     rax, [rdi+10h]
0x18000909c  mov     rcx, [rdi+8]
0x1800090a0  mov     rbp, [rax+rdx*8]
0x1800090a4  mov     rbx, [rcx+rdx*8]
0x1800090a8  mov     rax, [rdi+18h]
0x1800090ac  mov     r14d, [rax+rdx*4]
0x1800090b0  mov     [rcx+rdx*8], r12
0x1800090b4  mov     edx, [rdi+5Ch]
0x1800090b7  mov     rax, [rdi+10h]
0x1800090bb  mov     [rax+rdx*8], r12
0x1800090bf  mov     edx, [rdi+5Ch]
0x1800090c2  mov     rax, [rdi+18h]
0x1800090c6  mov     [rax+rdx*4], r12d
0x1800090ca  xor     edx, edx
0x1800090cc  mov     eax, [rdi+5Ch]
0x1800090cf  inc     eax
0x1800090d1  div     dword ptr [rdi]
0x1800090d3  add     [rdi+64h], r15d
0x1800090d7  mov     [rdi+5Ch], edx
0x1800090da  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800090de  call    cs:__imp_LeaveCriticalSection
0x1800090e4  mov     esi, r12d
0x1800090e7  test    rbx, rbx
0x1800090ea  jz      loc_1800091DA
0x1800090f0  lea     rcx, [rbx+90h]; this
0x1800090f7  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800090fa  mov     rdx, rbp; lpBuffer
0x1800090fd  call    ?WriteLogFile@FREB_LOG_FILE_MANAGER@@QEAAJPEAEK@Z; FREB_LOG_FILE_MANAGER::WriteLogFile(uchar *,ulong)
0x180009102  or      eax, 0FFFFFFFFh
0x180009105  lock xadd [rbx+8], eax
0x18000910a  cmp     eax, 1
0x18000910d  jnz     short loc_180009124
0x18000910f  test    rbx, rbx
0x180009112  jz      short loc_180009124
0x180009114  mov     rcx, rbx; this
0x180009117  call    ??1FREB_SITE_META_STORED_CONTEXT@@AEAA@XZ; FREB_SITE_META_STORED_CONTEXT::~FREB_SITE_META_STORED_CONTEXT(void)
0x18000911c  mov     rcx, rbx; Block
0x18000911f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009124  call    cs:__imp_GetProcessHeap
0x18000912a  mov     r8, rbp; lpMem
0x18000912d  xor     edx, edx; dwFlags
0x18000912f  mov     rcx, rax; hHeap
0x180009132  call    cs:__imp_HeapFree
0x180009138  cmp     cs:?sm_fShutdown@FREB_LOG_FILE_MANAGER@@0HA, r12d; int FREB_LOG_FILE_MANAGER::sm_fShutdown
0x18000913f  jnz     loc_180009264
0x180009145  inc     esi
0x180009147  cmp     esi, cs:?sm_dwThrottle@FREB_LOG_FILE_MANAGER@@0KA; ulong FREB_LOG_FILE_MANAGER::sm_dwThrottle
0x18000914d  jbe     short loc_18000915D
0x18000914f  mov     ecx, 3E8h; dwMilliseconds
0x180009154  call    cs:__imp_Sleep
0x18000915a  mov     esi, r12d
0x18000915d  mov     rdi, cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x180009164  lea     rcx, [rdi+20h]; lpCriticalSection
0x180009168  call    cs:__imp_EnterCriticalSection
0x18000916e  cmp     [rdi+64h], r12d
0x180009172  jnz     short loc_18000917F
0x180009174  mov     rbx, r12
0x180009177  mov     rbp, r12
0x18000917a  mov     r14d, r12d
0x18000917d  jmp     short loc_1800091C3
0x18000917f  mov     edx, [rdi+5Ch]
0x180009182  mov     rax, [rdi+10h]
0x180009186  mov     rcx, [rdi+8]
0x18000918a  mov     rbp, [rax+rdx*8]
0x18000918e  mov     rbx, [rcx+rdx*8]
0x180009192  mov     rax, [rdi+18h]
0x180009196  mov     r14d, [rax+rdx*4]
0x18000919a  mov     [rcx+rdx*8], r12
0x18000919e  mov     edx, [rdi+5Ch]
0x1800091a1  mov     rax, [rdi+10h]
0x1800091a5  mov     [rax+rdx*8], r12
0x1800091a9  mov     edx, [rdi+5Ch]
0x1800091ac  mov     rax, [rdi+18h]
0x1800091b0  mov     [rax+rdx*4], r12d
0x1800091b4  xor     edx, edx
0x1800091b6  mov     eax, [rdi+5Ch]
0x1800091b9  inc     eax
0x1800091bb  div     dword ptr [rdi]
0x1800091bd  dec     dword ptr [rdi+64h]
0x1800091c0  mov     [rdi+5Ch], edx
0x1800091c3  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800091c7  call    cs:__imp_LeaveCriticalSection
0x1800091cd  test    rbx, rbx
0x1800091d0  jnz     loc_1800090F0
0x1800091d6  or      r15d, 0FFFFFFFFh
0x1800091da  mov     rbx, cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x1800091e1  mov     rax, [rbx+48h]
0x1800091e5  lea     rdi, [rbx+20h]
0x1800091e9  mov     [rsp+68h+Handles], rax
0x1800091ee  mov     rcx, rdi; lpCriticalSection
0x1800091f1  mov     rax, [rbx+50h]
0x1800091f5  mov     [rsp+68h+var_40], rax
0x1800091fa  call    cs:__imp_EnterCriticalSection
0x180009200  cmp     [rbx+64h], r12d
0x180009204  jz      short loc_18000920B
0x180009206  mov     ebx, r12d
0x180009209  jmp     short loc_180009213
0x18000920b  inc     dword ptr [rbx+58h]
0x18000920e  mov     ebx, 1
0x180009213  mov     rcx, rdi; lpCriticalSection
0x180009216  call    cs:__imp_LeaveCriticalSection
0x18000921c  test    ebx, ebx
0x18000921e  jz      short loc_180009257
0x180009220  xor     r8d, r8d; bWaitAll
0x180009223  lea     rdx, [rsp+68h+Handles]; lpHandles
0x180009228  mov     r9d, r15d; dwMilliseconds
0x18000922b  lea     ecx, [r8+2]; nCount
0x18000922f  call    cs:__imp_WaitForMultipleObjects
0x180009235  cmp     eax, r15d
0x180009238  jnz     short loc_180009252
0x18000923a  call    cs:__imp_GetLastError
0x180009240  test    eax, eax
0x180009242  jle     short loc_18000924E
0x180009244  movzx   eax, ax
0x180009247  or      eax, 80070000h
0x18000924c  test    eax, eax
0x18000924e  js      short loc_180009264
0x180009250  jmp     short loc_180009257
0x180009252  cmp     eax, 1
0x180009255  ja      short loc_180009264
0x180009257  cmp     cs:?sm_fShutdown@FREB_LOG_FILE_MANAGER@@0HA, r12d; int FREB_LOG_FILE_MANAGER::sm_fShutdown
0x18000925e  jz      loc_180009073
0x180009264  xor     eax, eax
0x180009266  add     rsp, 30h
0x18000926a  pop     r15
0x18000926c  pop     r14
0x18000926e  pop     r12
0x180009270  pop     rdi
0x180009271  pop     rsi
0x180009272  pop     rbp
0x180009273  pop     rbx
0x180009274  retn
```
