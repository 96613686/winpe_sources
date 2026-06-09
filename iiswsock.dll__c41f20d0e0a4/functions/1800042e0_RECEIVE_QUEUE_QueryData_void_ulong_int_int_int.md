# RECEIVE_QUEUE::QueryData(void *,ulong *,int *,int *,int *)

- ea: `0x1800042e0`
- end: `0x1800044d0`
- name: `?QueryData@RECEIVE_QUEUE@@QEAAXPEAXPEAKPEAH22@Z`
- size: `496`
- prototype: `void __fastcall(RECEIVE_QUEUE *this, char *, unsigned int *, int *, int *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180005ae8`
- `0x1800063d0`

## callees

- `0x180004040`
- `0x1800042e0`
- `0x1800085b6`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000442b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004477`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000442b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004477`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800043de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004467`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800043de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004467`
- `iisutil!WriteRefTraceLog` at `0x1800043f6`
- `iisutil!WriteRefTraceLog` at `0x1800043f6`

## pseudocode

```c
void __fastcall RECEIVE_QUEUE::QueryData(RECEIVE_QUEUE *this, char *a2, unsigned int *a3, int *a4, int *a5, int *a6)
{
  unsigned int v6; // r12d
  struct _RTL_CRITICAL_SECTION *v7; // rsi
  int v8; // ebp
  unsigned int v9; // r13d
  char *i; // rdi
  struct QUEUE_RECORD *v12; // rax
  struct QUEUE_RECORD *v13; // rbx
  int v14; // eax
  bool v15; // zf
  int *v16; // rax
  __int64 v17; // rdx
  size_t v18; // r8
  const void *v19; // rdx
  char *v20; // rcx
  HANDLE LockSemaphore; // rcx
  struct _RTL_CRITICAL_SECTION *v22; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  char *v24; // rbx
  BOOL v25; // edi

  v6 = *a3;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v8 = 0;
  v9 = 0;
  for ( i = a2; ; i = a2 )
  {
    v12 = QUEUE::Dequeue(v7);
    v13 = v12;
    if ( !a4 || !a5 )
      goto LABEL_16;
    v14 = *((_DWORD *)v12 + 8);
    switch ( v14 )
    {
      case -2147483648:
        *a4 = 1;
        goto LABEL_15;
      case -2147483647:
        *a4 = 1;
        goto LABEL_11;
      case -2147483646:
        *a4 = 0;
LABEL_15:
        *a5 = 1;
        goto LABEL_16;
      case -2147483645:
        *a4 = 0;
LABEL_11:
        *a5 = 0;
LABEL_16:
        v16 = a6;
        goto LABEL_17;
    }
    v15 = v14 == -2147483644;
    v16 = a6;
    if ( v15 )
    {
      *a6 = 1;
      *a5 = 1;
      *a4 = 1;
    }
LABEL_17:
    if ( *v16 )
    {
      if ( v13 )
        goto LABEL_26;
    }
    else
    {
      v17 = *((unsigned int *)v13 + 9);
      v18 = (unsigned int)(*((_DWORD *)v13 + 6) - v17);
      v19 = (const void *)(*((_QWORD *)v13 + 5) + v17);
      v20 = &i[v9];
      if ( v6 >= (unsigned int)v18 )
      {
        memcpy_0(v20, v19, v18);
        v8 = *((_DWORD *)v13 + 6) - *((_DWORD *)v13 + 9);
LABEL_26:
        (**(void (__fastcall ***)(struct QUEUE_RECORD *, __int64))v13)(v13, 1);
        goto LABEL_27;
      }
      memcpy_0(v20, v19, v6);
      *a5 = 0;
      *((_DWORD *)v13 + 9) += v6;
      EnterCriticalSection(v7);
      LockSemaphore = v7[1].LockSemaphore;
      ++LODWORD(v7[1].OwningThread);
      if ( LockSemaphore )
        WriteRefTraceLog(LockSemaphore, LODWORD(v7[1].OwningThread), v7);
      v22 = v7 + 1;
      DebugInfo = v7[1].DebugInfo;
      if ( DebugInfo->CriticalSection != &v7[1] )
        __fastfail(3u);
      v8 = v6;
      *((_QWORD *)v13 + 2) = v22;
      *((_QWORD *)v13 + 1) = DebugInfo;
      DebugInfo->CriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)v13 + 8);
      v22->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)v13 + 8);
      HIDWORD(v7[1].OwningThread) += *((_DWORD *)v13 + 6);
      LeaveCriticalSection(v7);
    }
LABEL_27:
    v25 = 1;
    if ( !*a6 && !*a5 )
    {
      EnterCriticalSection(v7);
      v24 = (char *)v7[1].DebugInfo;
      LeaveCriticalSection(v7);
      if ( v24 != (char *)&v7[1] )
        v25 = 0;
    }
    v9 += v8;
    v6 -= v8;
    if ( !v6 )
      break;
    v8 = 0;
    if ( v25 )
      break;
  }
  *a3 = v9;
}

```

## disassembly

```asm
0x1800042e0  mov     [rsp+arg_0], rbx
0x1800042e5  mov     [rsp+arg_10], r8
0x1800042ea  mov     [rsp+arg_8], rdx
0x1800042ef  push    rbp
0x1800042f0  push    rsi
0x1800042f1  push    rdi
0x1800042f2  push    r12
0x1800042f4  push    r13
0x1800042f6  push    r14
0x1800042f8  push    r15
0x1800042fa  sub     rsp, 30h
0x1800042fe  mov     r12d, [r8]
0x180004301  lea     rsi, [rcx+10h]
0x180004305  mov     r14, [rsp+68h+arg_20]
0x18000430d  xor     ebp, ebp
0x18000430f  mov     r13d, ebp
0x180004312  mov     [rsp+68h+var_48], ebp
0x180004316  mov     r15, r9
0x180004319  mov     rdi, rdx
0x18000431c  mov     rcx, rsi; lpCriticalSection
0x18000431f  call    ?Dequeue@QUEUE@@QEAAPEAVQUEUE_RECORD@@XZ; QUEUE::Dequeue(void)
0x180004324  mov     rbx, rax
0x180004327  test    r15, r15
0x18000432a  jz      short loc_180004399
0x18000432c  test    r14, r14
0x18000432f  jz      short loc_180004399
0x180004331  mov     eax, [rax+20h]
0x180004334  cmp     eax, 80000000h
0x180004339  jz      short loc_18000438B
0x18000433b  cmp     eax, 80000001h
0x180004340  jz      short loc_180004382
0x180004342  cmp     eax, 80000002h
0x180004347  jz      short loc_18000437D
0x180004349  cmp     eax, 80000003h
0x18000434e  jz      short loc_180004375
0x180004350  cmp     eax, 80000004h
0x180004355  mov     rax, [rsp+68h+arg_28]
0x18000435d  jnz     short loc_1800043A1
0x18000435f  mov     dword ptr [rax], 1
0x180004365  mov     dword ptr [r14], 1
0x18000436c  mov     dword ptr [r15], 1
0x180004373  jmp     short loc_1800043A1
0x180004375  mov     [r15], ebp
0x180004378  mov     [r14], ebp
0x18000437b  jmp     short loc_180004399
0x18000437d  mov     [r15], ebp
0x180004380  jmp     short loc_180004392
0x180004382  mov     dword ptr [r15], 1
0x180004389  jmp     short loc_180004378
0x18000438b  mov     dword ptr [r15], 1
0x180004392  mov     dword ptr [r14], 1
0x180004399  mov     rax, [rsp+68h+arg_28]
0x1800043a1  cmp     [rax], ebp
0x1800043a3  jz      short loc_1800043B3
0x1800043a5  test    rbx, rbx
0x1800043a8  jz      loc_180004451
0x1800043ae  jmp     loc_18000443E
0x1800043b3  mov     edx, [rbx+24h]
0x1800043b6  mov     r8d, [rbx+18h]
0x1800043ba  sub     r8d, edx; Size
0x1800043bd  mov     ecx, r13d
0x1800043c0  add     rdx, [rbx+28h]; Src
0x1800043c4  add     rcx, rdi; void *
0x1800043c7  cmp     r12d, r8d
0x1800043ca  jnb     short loc_180004433
0x1800043cc  mov     r8d, r12d; Size
0x1800043cf  call    memcpy_0
0x1800043d4  mov     [r14], ebp
0x1800043d7  mov     rcx, rsi; lpCriticalSection
0x1800043da  add     [rbx+24h], r12d
0x1800043de  call    cs:__imp_EnterCriticalSection
0x1800043e4  mov     rcx, [rsi+40h]
0x1800043e8  inc     dword ptr [rsi+38h]
0x1800043eb  test    rcx, rcx
0x1800043ee  jz      short loc_1800043FC
0x1800043f0  mov     edx, [rsi+38h]
0x1800043f3  mov     r8, rsi
0x1800043f6  call    cs:__imp_WriteRefTraceLog
0x1800043fc  lea     rcx, [rsi+28h]
0x180004400  mov     rdx, [rcx]
0x180004403  cmp     [rdx+8], rcx
0x180004407  jnz     loc_1800044A9
0x18000440d  lea     rax, [rbx+8]
0x180004411  mov     ebp, r12d
0x180004414  mov     [rax+8], rcx
0x180004418  mov     [rax], rdx
0x18000441b  mov     [rdx+8], rax
0x18000441f  mov     [rcx], rax
0x180004422  mov     rcx, rsi; lpCriticalSection
0x180004425  mov     eax, [rbx+18h]
0x180004428  add     [rsi+3Ch], eax
0x18000442b  call    cs:__imp_LeaveCriticalSection
0x180004431  jmp     short loc_180004451
0x180004433  call    memcpy_0
0x180004438  mov     ebp, [rbx+18h]
0x18000443b  sub     ebp, [rbx+24h]
0x18000443e  mov     rax, [rbx]
0x180004441  mov     edx, 1
0x180004446  mov     rcx, rbx
0x180004449  mov     rax, [rax]
0x18000444c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004451  mov     rax, [rsp+68h+arg_28]
0x180004459  cmp     dword ptr [rax], 0
0x18000445c  jnz     short loc_180004482
0x18000445e  cmp     dword ptr [r14], 0
0x180004462  jnz     short loc_180004482
0x180004464  mov     rcx, rsi; lpCriticalSection
0x180004467  call    cs:__imp_EnterCriticalSection
0x18000446d  lea     rdi, [rsi+28h]
0x180004471  mov     rcx, rsi; lpCriticalSection
0x180004474  mov     rbx, [rdi]
0x180004477  call    cs:__imp_LeaveCriticalSection
0x18000447d  cmp     rbx, rdi
0x180004480  jnz     short loc_180004489
0x180004482  mov     edi, 1
0x180004487  jmp     short loc_18000448D
0x180004489  mov     edi, [rsp+68h+var_48]
0x18000448d  add     r13d, ebp
0x180004490  sub     r12d, ebp
0x180004493  jz      short loc_1800044B0
0x180004495  xor     ebp, ebp
0x180004497  mov     [rsp+68h+var_48], edi
0x18000449b  test    edi, edi
0x18000449d  jnz     short loc_1800044B0
0x18000449f  mov     rdi, [rsp+68h+arg_8]
0x1800044a4  jmp     loc_18000431C
0x1800044a9  mov     ecx, 3
0x1800044ae  int     29h; Win8: RtlFailFast(ecx)
0x1800044b0  mov     rax, [rsp+68h+arg_10]
0x1800044b8  mov     rbx, [rsp+68h+arg_0]
0x1800044bd  mov     [rax], r13d
0x1800044c0  add     rsp, 30h
0x1800044c4  pop     r15
0x1800044c6  pop     r14
0x1800044c8  pop     r13
0x1800044ca  pop     r12
0x1800044cc  pop     rdi
0x1800044cd  pop     rsi
0x1800044ce  pop     rbp
0x1800044cf  retn
```
