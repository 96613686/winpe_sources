# CleanupV2Resources

- ea: `0x18000cb04`
- end: `0x18000cc69`
- name: `CleanupV2Resources`
- size: `357`
- prototype: `char()`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000a190`

## callees

- `0x1800072d0`
- `0x180007300`
- `0x180008050`
- `0x18000cb04`
- `0x1800163f4`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000cb4f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000cb4f`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000cb5b`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18000cb5b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cb6d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000cb6d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000cb3a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000cb3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cbd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cbd0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cbd9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cbd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cbc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cbc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc40`

## pseudocode

```c
char CleanupV2Resources()
{
  char v0; // si
  PVOID v1; // rax
  void *v2; // rdi
  void *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  void *v5; // rdi
  void *v6; // rcx

  v0 = 1;
  if ( g_hGlobalMutex )
  {
    if ( PerflibciLocalWaitForMutex(g_hGlobalMutex) )
    {
      return 0;
    }
    else
    {
      RtlAcquireSRWLockExclusive(&qword_18002BED0);
      while ( 1 )
      {
        v1 = RtlEnumerateGenericTableAvl(&Table, 1u);
        if ( !v1 )
          break;
        RtlDeleteElementGenericTableAvl(&Table, v1);
      }
      RtlReleaseSRWLockExclusive(&qword_18002BED0);
      v2 = g_QueryList;
      if ( g_QueryList )
      {
        do
        {
          v3 = (void *)*((_QWORD *)v2 + 1);
          PerflibciCloseLocalQueryHandle(*(struct _PERF_QUERY **)v2);
          operator delete(*((void **)v2 + 5));
          operator delete(v2);
          v2 = v3;
        }
        while ( v3 );
      }
      g_QueryList = 0;
      while ( 1 )
      {
        v5 = g_ObjectList;
        if ( !g_ObjectList )
          break;
        v4 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)g_ObjectList + 4) + 40LL);
        g_ObjectList = (void *)*((_QWORD *)g_ObjectList + 3);
        EnterCriticalSection(v4);
        LeaveCriticalSection(v4);
        DeleteCriticalSection(v4);
        operator delete(v5);
      }
      g_ObjectList = 0;
      qword_18002BEA0 = 0;
      while ( 1 )
      {
        v6 = qword_18002BEB0;
        if ( !qword_18002BEB0 )
          break;
        qword_18002BEB0 = (void *)*((_QWORD *)qword_18002BEB0 + 3);
        operator delete(v6);
      }
      qword_18002BEB0 = 0;
      qword_18002BEA8 = 0;
      PerflibciLocalReleaseMutex(g_hGlobalMutex);
      CloseHandle(g_hGlobalMutex);
      g_hGlobalMutex = 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18000cb04  mov     [rsp+arg_0], rbx
0x18000cb09  mov     [rsp+arg_8], rsi
0x18000cb0e  push    rdi
0x18000cb0f  sub     rsp, 20h
0x18000cb13  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x18000cb1a  mov     sil, 1
0x18000cb1d  test    rcx, rcx
0x18000cb20  jz      loc_18000CC56
0x18000cb26  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x18000cb2b  test    eax, eax
0x18000cb2d  jnz     loc_18000CC53
0x18000cb33  lea     rcx, qword_18002BED0
0x18000cb3a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000cb40  lea     rbx, Table
0x18000cb47  jmp     short loc_18000CB55
0x18000cb49  mov     rdx, rax; Buffer
0x18000cb4c  mov     rcx, rbx; Table
0x18000cb4f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000cb55  mov     dl, sil; Restart
0x18000cb58  mov     rcx, rbx; Table
0x18000cb5b  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18000cb61  test    rax, rax
0x18000cb64  jnz     short loc_18000CB49
0x18000cb66  lea     rcx, qword_18002BED0
0x18000cb6d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000cb73  mov     rdi, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x18000cb7a  test    rdi, rdi
0x18000cb7d  jz      short loc_18000CBA4
0x18000cb7f  mov     rcx, [rdi]; struct _PERF_QUERY *
0x18000cb82  mov     rbx, [rdi+8]
0x18000cb86  call    PerflibciCloseLocalQueryHandle
0x18000cb8b  mov     rcx, [rdi+28h]; Block
0x18000cb8f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cb94  mov     rcx, rdi; Block
0x18000cb97  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cb9c  mov     rdi, rbx
0x18000cb9f  test    rbx, rbx
0x18000cba2  jnz     short loc_18000CB7F
0x18000cba4  mov     cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA, 0; PERFI_THREAD_QUERY * g_QueryList
0x18000cbaf  jmp     short loc_18000CBE7
0x18000cbb1  mov     rbx, [rdi+20h]
0x18000cbb5  mov     rax, [rdi+18h]
0x18000cbb9  add     rbx, 28h ; '('
0x18000cbbd  mov     rcx, rbx; lpCriticalSection
0x18000cbc0  mov     cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA, rax; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x18000cbc7  call    cs:__imp_EnterCriticalSection
0x18000cbcd  mov     rcx, rbx; lpCriticalSection
0x18000cbd0  call    cs:__imp_LeaveCriticalSection
0x18000cbd6  mov     rcx, rbx; lpCriticalSection
0x18000cbd9  call    cs:__imp_DeleteCriticalSection
0x18000cbdf  mov     rcx, rdi; Block
0x18000cbe2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cbe7  mov     rdi, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x18000cbee  test    rdi, rdi
0x18000cbf1  jnz     short loc_18000CBB1
0x18000cbf3  mov     cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA, rdi; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x18000cbfa  mov     cs:qword_18002BEA0, rdi
0x18000cc01  jmp     short loc_18000CC13
0x18000cc03  mov     rax, [rcx+18h]
0x18000cc07  mov     cs:qword_18002BEB0, rax
0x18000cc0e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc13  mov     rcx, cs:qword_18002BEB0; Block
0x18000cc1a  test    rcx, rcx
0x18000cc1d  jnz     short loc_18000CC03
0x18000cc1f  mov     cs:qword_18002BEB0, rcx
0x18000cc26  mov     cs:qword_18002BEA8, rcx
0x18000cc2d  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x18000cc34  call    ?PerflibciLocalReleaseMutex@@YAKPEAX@Z; PerflibciLocalReleaseMutex(void *)
0x18000cc39  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; hObject
0x18000cc40  call    cs:__imp_CloseHandle
0x18000cc46  mov     cs:?g_hGlobalMutex@@3PEAXEA, 0; void * g_hGlobalMutex
0x18000cc51  jmp     short loc_18000CC56
0x18000cc53  xor     sil, sil
0x18000cc56  mov     rbx, [rsp+28h+arg_0]
0x18000cc5b  mov     al, sil
0x18000cc5e  mov     rsi, [rsp+28h+arg_8]
0x18000cc63  add     rsp, 20h
0x18000cc67  pop     rdi
0x18000cc68  retn
```
