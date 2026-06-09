# EfsDeleteEdpUserDecryptionContext(_EFS_DECRYPTION_CONTEXT *)

- ea: `0x180053198`
- end: `0x18005336d`
- name: `?EfsDeleteEdpUserDecryptionContext@@YAXPEAU_EFS_DECRYPTION_CONTEXT@@@Z`
- size: `469`
- prototype: `void __fastcall(struct _EFS_DECRYPTION_CONTEXT *lpMem)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800530c0`
- `0x180053970`

## callees

- `0x180052330`
- `0x180052fb4`
- `0x180053198`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180053225`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800532bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180053225`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800532bb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800531bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053259`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800531bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053259`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005320f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800532d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005320f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800532d6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005324c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005324c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800532e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053346`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800532e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053346`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800532f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053354`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800532f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053354`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180053234`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180053234`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005323c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005323c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800531f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005330a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053321`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053338`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800531f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005330a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053321`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053338`

## pseudocode

```c
void __fastcall EfsDeleteEdpUserDecryptionContext(struct _EFS_DECRYPTION_CONTEXT *lpMem)
{
  __int64 v2; // rax
  struct _EFS_DECRYPTION_CONTEXT **v3; // rcx
  bool v4; // zf
  void *v5; // rcx
  void *v6; // rcx
  DWORD ThreadId; // ebx
  struct _EFS_DECRYPT_REQUEST **v8; // rbx
  int i; // esi
  struct _EFS_DECRYPT_REQUEST *v10; // rdx
  __int64 v11; // rax
  int v12; // ebx
  void *v13; // rsi
  HANDLE ProcessHeap; // rax
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  HANDLE v18; // rax

  if ( lpMem )
  {
    if ( *(struct _EFS_DECRYPTION_CONTEXT **)lpMem != lpMem )
    {
      AcquireSRWLockExclusive(&stru_1801173D0);
      v2 = *(_QWORD *)lpMem;
      if ( *(struct _EFS_DECRYPTION_CONTEXT **)(*(_QWORD *)lpMem + 8LL) != lpMem
        || (v3 = (struct _EFS_DECRYPTION_CONTEXT **)*((_QWORD *)lpMem + 1), *v3 != lpMem) )
      {
LABEL_19:
        __fastfail(3u);
      }
      v4 = dword_1801173C0-- == 1;
      *v3 = (struct _EFS_DECRYPTION_CONTEXT *)v2;
      *(_QWORD *)(v2 + 8) = v3;
      if ( v4 && hHandle )
      {
        CloseHandle(hHandle);
        hHandle = 0;
      }
      ReleaseSRWLockExclusive(&stru_1801173D0);
      *((_QWORD *)lpMem + 1) = lpMem;
      *(_QWORD *)lpMem = lpMem;
    }
    v5 = (void *)*((_QWORD *)lpMem + 6);
    if ( v5 )
      SetEvent(v5);
    v6 = (void *)*((_QWORD *)lpMem + 7);
    if ( v6 )
    {
      ThreadId = GetThreadId(v6);
      if ( GetCurrentThreadId() != ThreadId )
        WaitForSingleObject(*((HANDLE *)lpMem + 7), 0xFFFFFFFF);
    }
    AcquireSRWLockExclusive(&stru_1801173D0);
    v8 = (struct _EFS_DECRYPT_REQUEST **)((char *)lpMem + 16);
    for ( i = 1;
          ;
          i = (unsigned int)EfsCheckUpdateFreeDecryptionReuestForUser(*((const unsigned __int16 **)lpMem + 4), v10) != 0
            ? i
            : 0 )
    {
      v10 = *v8;
      if ( *v8 == (struct _EFS_DECRYPT_REQUEST *)v8 )
        break;
      if ( *((struct _EFS_DECRYPT_REQUEST ***)v10 + 1) != v8 )
        goto LABEL_19;
      v11 = *(_QWORD *)v10;
      if ( *(struct _EFS_DECRYPT_REQUEST **)(*(_QWORD *)v10 + 8LL) != v10 )
        goto LABEL_19;
      *v8 = (struct _EFS_DECRYPT_REQUEST *)v11;
      *(_QWORD *)(v11 + 8) = v8;
      *((_QWORD *)v10 + 1) = v10;
      *(_QWORD *)v10 = v10;
    }
    v12 = 0;
    if ( i && hHandle )
      SetEvent(hHandle);
    if ( !dword_1801173C0 && i )
      v12 = 1;
    ReleaseSRWLockExclusive(&stru_1801173D0);
    v13 = (void *)*((_QWORD *)lpMem + 4);
    if ( v13 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *((_QWORD *)lpMem + 4) = 0;
    }
    v15 = (void *)*((_QWORD *)lpMem + 5);
    if ( v15 )
    {
      CloseHandle(v15);
      *((_QWORD *)lpMem + 5) = 0;
    }
    v16 = (void *)*((_QWORD *)lpMem + 6);
    if ( v16 )
    {
      CloseHandle(v16);
      *((_QWORD *)lpMem + 6) = 0;
    }
    v17 = (void *)*((_QWORD *)lpMem + 7);
    if ( v17 )
    {
      CloseHandle(v17);
      *((_QWORD *)lpMem + 7) = 0;
    }
    v18 = GetProcessHeap();
    HeapFree(v18, 0, lpMem);
    if ( v12 )
      EfsCleanupDecryptionProcessing();
  }
}

```

## disassembly

```asm
0x180053198  test    rcx, rcx
0x18005319b  jz      locret_18005336C
0x1800531a1  push    rbx
0x1800531a2  push    rsi
0x1800531a3  push    rdi
0x1800531a4  push    r15
0x1800531a6  sub     rsp, 28h
0x1800531aa  or      esi, 0FFFFFFFFh
0x1800531ad  mov     rdi, rcx
0x1800531b0  cmp     [rcx], rcx
0x1800531b3  jz      short loc_18005321C
0x1800531b5  lea     rcx, stru_1801173D0; SRWLock
0x1800531bc  call    cs:__imp_AcquireSRWLockExclusive
0x1800531c2  mov     rax, [rdi]
0x1800531c5  cmp     [rax+8], rdi
0x1800531c9  jnz     loc_1800532A2
0x1800531cf  mov     rcx, [rdi+8]
0x1800531d3  cmp     [rcx], rdi
0x1800531d6  jnz     loc_1800532A2
0x1800531dc  add     cs:dword_1801173C0, esi
0x1800531e2  mov     [rcx], rax
0x1800531e5  mov     [rax+8], rcx
0x1800531e9  jnz     short loc_180053208
0x1800531eb  mov     rcx, cs:hHandle; hObject
0x1800531f2  test    rcx, rcx
0x1800531f5  jz      short loc_180053208
0x1800531f7  call    cs:__imp_CloseHandle
0x1800531fd  mov     cs:hHandle, 0
0x180053208  lea     rcx, stru_1801173D0; SRWLock
0x18005320f  call    cs:__imp_ReleaseSRWLockExclusive
0x180053215  mov     [rdi+8], rdi
0x180053219  mov     [rdi], rdi
0x18005321c  mov     rcx, [rdi+30h]; hEvent
0x180053220  test    rcx, rcx
0x180053223  jz      short loc_18005322B
0x180053225  call    cs:__imp_SetEvent
0x18005322b  mov     rcx, [rdi+38h]; Thread
0x18005322f  test    rcx, rcx
0x180053232  jz      short loc_180053252
0x180053234  call    cs:__imp_GetThreadId
0x18005323a  mov     ebx, eax
0x18005323c  call    cs:__imp_GetCurrentThreadId
0x180053242  cmp     eax, ebx
0x180053244  jz      short loc_180053252
0x180053246  mov     rcx, [rdi+38h]; hHandle
0x18005324a  mov     edx, esi; dwMilliseconds
0x18005324c  call    cs:__imp_WaitForSingleObject
0x180053252  lea     rcx, stru_1801173D0; SRWLock
0x180053259  call    cs:__imp_AcquireSRWLockExclusive
0x18005325f  mov     r15d, 1
0x180053265  lea     rbx, [rdi+10h]
0x180053269  mov     esi, r15d
0x18005326c  mov     rdx, [rbx]; lpMem
0x18005326f  cmp     rdx, rbx
0x180053272  jz      short loc_1800532A9
0x180053274  cmp     [rdx+8], rbx
0x180053278  jnz     short loc_1800532A2
0x18005327a  mov     rax, [rdx]
0x18005327d  cmp     [rax+8], rdx
0x180053281  jnz     short loc_1800532A2
0x180053283  mov     [rbx], rax
0x180053286  mov     [rax+8], rbx
0x18005328a  mov     [rdx+8], rdx
0x18005328e  mov     [rdx], rdx
0x180053291  mov     rcx, [rdi+20h]; unsigned __int16 *
0x180053295  call    ?EfsCheckUpdateFreeDecryptionReuestForUser@@YAHPEBGPEAU_EFS_DECRYPT_REQUEST@@@Z; EfsCheckUpdateFreeDecryptionReuestForUser(ushort const *,_EFS_DECRYPT_REQUEST *)
0x18005329a  neg     eax
0x18005329c  sbb     ecx, ecx
0x18005329e  and     esi, ecx
0x1800532a0  jmp     short loc_18005326C
0x1800532a2  mov     ecx, 3
0x1800532a7  int     29h; Win8: RtlFailFast(ecx)
0x1800532a9  xor     ebx, ebx
0x1800532ab  test    esi, esi
0x1800532ad  jz      short loc_1800532C1
0x1800532af  mov     rcx, cs:hHandle; hEvent
0x1800532b6  test    rcx, rcx
0x1800532b9  jz      short loc_1800532C1
0x1800532bb  call    cs:__imp_SetEvent
0x1800532c1  cmp     cs:dword_1801173C0, ebx
0x1800532c7  jnz     short loc_1800532CF
0x1800532c9  test    esi, esi
0x1800532cb  cmovnz  ebx, r15d
0x1800532cf  lea     rcx, stru_1801173D0; SRWLock
0x1800532d6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800532dc  mov     rsi, [rdi+20h]
0x1800532e0  test    rsi, rsi
0x1800532e3  jz      short loc_180053301
0x1800532e5  call    cs:__imp_GetProcessHeap
0x1800532eb  mov     r8, rsi; lpMem
0x1800532ee  xor     edx, edx; dwFlags
0x1800532f0  mov     rcx, rax; hHeap
0x1800532f3  call    cs:__imp_HeapFree
0x1800532f9  mov     qword ptr [rdi+20h], 0
0x180053301  mov     rcx, [rdi+28h]; hObject
0x180053305  test    rcx, rcx
0x180053308  jz      short loc_180053318
0x18005330a  call    cs:__imp_CloseHandle
0x180053310  mov     qword ptr [rdi+28h], 0
0x180053318  mov     rcx, [rdi+30h]; hObject
0x18005331c  test    rcx, rcx
0x18005331f  jz      short loc_18005332F
0x180053321  call    cs:__imp_CloseHandle
0x180053327  mov     qword ptr [rdi+30h], 0
0x18005332f  mov     rcx, [rdi+38h]; hObject
0x180053333  test    rcx, rcx
0x180053336  jz      short loc_180053346
0x180053338  call    cs:__imp_CloseHandle
0x18005333e  mov     qword ptr [rdi+38h], 0
0x180053346  call    cs:__imp_GetProcessHeap
0x18005334c  mov     r8, rdi; lpMem
0x18005334f  xor     edx, edx; dwFlags
0x180053351  mov     rcx, rax; hHeap
0x180053354  call    cs:__imp_HeapFree
0x18005335a  test    ebx, ebx
0x18005335c  jz      short loc_180053363
0x18005335e  call    ?EfsCleanupDecryptionProcessing@@YAXXZ; EfsCleanupDecryptionProcessing(void)
0x180053363  add     rsp, 28h
0x180053367  pop     r15
0x180053369  pop     rdi
0x18005336a  pop     rsi
0x18005336b  pop     rbx
0x18005336c  retn
```
