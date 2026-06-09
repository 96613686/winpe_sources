# CMFAttributesImpl<IMFAttributes,CMFSRWLock>::GetUnknown(_GUID const &,_GUID const &,void * *)

- ea: `0x18002f740`
- end: `0x18002f90c`
- name: `?GetUnknown@?$CMFAttributesImpl@UIMFAttributes@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002f740`
- `0x18002fac0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002f776`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002f776`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002f829`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002f829`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f764`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f819`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f764`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f819`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFSRWLock>::GetUnknown(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        _QWORD *a4)
{
  CMFSRWLock *v6; // rdi
  int v9; // r10d
  unsigned int v10; // ebp
  __int64 v11; // rbx
  int v12; // r9d
  __int64 v13; // r8
  __int64 v14; // rdx
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 (__fastcall ***v18)(_QWORD, __int64, _QWORD *); // rcx
  int j; // r11d
  __int64 v21; // rax
  int i; // r8d
  __int64 v23; // rax
  int k; // r8d
  __int64 v25; // rax

  *a4 = 0;
  v6 = (CMFSRWLock *)(a1 + 8);
  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
    ++v6->m_dwRecursionCount;
  else
    AcquireSRWLockShared(&v6->m_SRWLock);
  v9 = *(_DWORD *)(a1 + 36);
  if ( !v9 )
    goto LABEL_9;
  v10 = *a2;
  if ( v9 < 4 )
  {
    for ( i = 0; i < v9; ++i )
    {
      v14 = *(_QWORD *)(a1 + 24) + 40LL * i;
      if ( *(_DWORD *)v14 > v10 )
        break;
      if ( *(_DWORD *)v14 == v10 )
      {
        v23 = *(_QWORD *)a2 - *(_QWORD *)v14;
        if ( *(_QWORD *)a2 == *(_QWORD *)v14 )
          v23 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v14 + 8);
        if ( !v23 )
          goto LABEL_16;
      }
    }
    goto LABEL_9;
  }
  v11 = *(_QWORD *)(a1 + 24);
  v12 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v13 = (v12 + v9) / 2;
      v14 = v11 + 40 * v13;
      if ( v10 >= *(_DWORD *)v14 )
        break;
      if ( (_DWORD)v13 == v12 )
        goto LABEL_9;
      v9 = (v12 + v9) / 2;
    }
    if ( v10 <= *(_DWORD *)v14 )
      break;
    v12 = v13 + 1;
    if ( (_DWORD)v13 + 1 == v9 )
      goto LABEL_9;
  }
  v16 = *(_QWORD *)a2 - *(_QWORD *)v14;
  if ( *(_QWORD *)a2 == *(_QWORD *)v14 )
    v16 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v14 + 8);
  if ( v16 )
  {
    if ( (int)v13 > v12 )
    {
      for ( j = v13 - 1; j >= v12; --j )
      {
        v14 = v11 + 40LL * j;
        if ( v10 != *(_DWORD *)v14 )
          break;
        v21 = *(_QWORD *)a2 - *(_QWORD *)v14;
        if ( *(_QWORD *)a2 == *(_QWORD *)v14 )
          v21 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v14 + 8);
        if ( !v21 )
          goto LABEL_16;
      }
    }
    for ( k = v13 + 1; k < v9; ++k )
    {
      v14 = v11 + 40LL * k;
      if ( v10 != *(_DWORD *)v14 )
        break;
      v25 = *(_QWORD *)a2 - *(_QWORD *)v14;
      if ( *(_QWORD *)a2 == *(_QWORD *)v14 )
        v25 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v14 + 8);
      if ( !v25 )
        goto LABEL_16;
    }
    goto LABEL_9;
  }
LABEL_16:
  v17 = v14 + 16;
  if ( !v17 )
  {
LABEL_9:
    v15 = -1072875802;
    goto LABEL_20;
  }
  if ( *(_WORD *)v17 == 13 && (v18 = *(__int64 (__fastcall ****)(_QWORD, __int64, _QWORD *))(v17 + 8)) != 0 )
    v15 = (**v18)(v18, a3, a4);
  else
    v15 = -1072875843;
LABEL_20:
  if ( v6->m_OwningThreadId == GetCurrentThreadId() )
    CMFSRWLock::UnlockExclusive(v6);
  else
    ReleaseSRWLockShared(&v6->m_SRWLock);
  return v15;
}

```

## disassembly

```asm
0x18002f740  push    rbx
0x18002f742  push    rbp
0x18002f743  push    rsi
0x18002f744  push    rdi
0x18002f745  push    r14
0x18002f747  push    r15
0x18002f749  sub     rsp, 28h
0x18002f74d  mov     r14, r9
0x18002f750  mov     qword ptr [r9], 0
0x18002f757  mov     r15, r8
0x18002f75a  lea     rdi, [rcx+8]
0x18002f75e  mov     rsi, rdx
0x18002f761  mov     rbx, rcx
0x18002f764  call    cs:__imp_GetCurrentThreadId
0x18002f76a  mov     r10d, [rdi+8]
0x18002f76e  cmp     r10d, eax
0x18002f771  jz      short loc_18002F7C5
0x18002f773  mov     rcx, rdi; SRWLock
0x18002f776  call    cs:__imp_AcquireSRWLockShared
0x18002f77c  mov     r10d, [rbx+24h]
0x18002f780  test    r10d, r10d
0x18002f783  jz      short loc_18002F7BE
0x18002f785  mov     ebp, [rsi]
0x18002f787  cmp     r10d, 4
0x18002f78b  jl      loc_18002F880
0x18002f791  mov     rbx, [rbx+18h]
0x18002f795  xor     r9d, r9d
0x18002f798  lea     eax, [r9+r10]
0x18002f79c  mov     ecx, 2
0x18002f7a1  cdq
0x18002f7a2  idiv    ecx
0x18002f7a4  movsxd  r8, eax
0x18002f7a7  lea     rdx, [r8+r8*4]
0x18002f7ab  lea     rdx, [rbx+rdx*8]
0x18002f7af  cmp     ebp, [rdx]
0x18002f7b1  jb      short loc_18002F7CA
0x18002f7b3  jbe     short loc_18002F7D4
0x18002f7b5  lea     r9d, [r8+1]
0x18002f7b9  cmp     r9d, r10d
0x18002f7bc  jnz     short loc_18002F798
0x18002f7be  mov     ebx, 0C00D36E6h
0x18002f7c3  jmp     short loc_18002F819
0x18002f7c5  inc     dword ptr [rdi+0Ch]
0x18002f7c8  jmp     short loc_18002F77C
0x18002f7ca  cmp     r8d, r9d
0x18002f7cd  jz      short loc_18002F7BE
0x18002f7cf  mov     r10d, r8d
0x18002f7d2  jmp     short loc_18002F798
0x18002f7d4  mov     rax, [rsi]
0x18002f7d7  sub     rax, [rdx]
0x18002f7da  jnz     short loc_18002F7E4
0x18002f7dc  mov     rax, [rsi+8]
0x18002f7e0  sub     rax, [rdx+8]
0x18002f7e4  test    rax, rax
0x18002f7e7  jnz     short loc_18002F845
0x18002f7e9  add     rdx, 10h
0x18002f7ed  jz      short loc_18002F7BE
0x18002f7ef  cmp     word ptr [rdx], 0Dh
0x18002f7f3  jnz     loc_18002F902
0x18002f7f9  mov     rcx, [rdx+8]
0x18002f7fd  test    rcx, rcx
0x18002f800  jz      loc_18002F902
0x18002f806  mov     rax, [rcx]
0x18002f809  mov     r8, r14
0x18002f80c  mov     rdx, r15
0x18002f80f  mov     rax, [rax]
0x18002f812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f817  mov     ebx, eax
0x18002f819  call    cs:__imp_GetCurrentThreadId
0x18002f81f  mov     edx, [rdi+8]
0x18002f822  mov     rcx, rdi; this
0x18002f825  cmp     edx, eax
0x18002f827  jz      short loc_18002F83E
0x18002f829  call    cs:__imp_ReleaseSRWLockShared
0x18002f82f  mov     eax, ebx
0x18002f831  add     rsp, 28h
0x18002f835  pop     r15
0x18002f837  pop     r14
0x18002f839  pop     rdi
0x18002f83a  pop     rsi
0x18002f83b  pop     rbp
0x18002f83c  pop     rbx
0x18002f83d  retn
0x18002f83e  call    ?UnlockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::UnlockExclusive(void)
0x18002f843  jmp     short loc_18002F82F
0x18002f845  cmp     r8d, r9d
0x18002f848  jle     short loc_18002F8C5
0x18002f84a  lea     r11d, [r8-1]
0x18002f84e  cmp     r11d, r9d
0x18002f851  jl      short loc_18002F8C5
0x18002f853  movsxd  rax, r11d
0x18002f856  lea     rcx, [rax+rax*4]
0x18002f85a  lea     rdx, [rbx+rcx*8]
0x18002f85e  cmp     ebp, [rdx]
0x18002f860  jnz     short loc_18002F8C5
0x18002f862  mov     rax, [rsi]
0x18002f865  sub     rax, [rdx]
0x18002f868  jnz     short loc_18002F872
0x18002f86a  mov     rax, [rsi+8]
0x18002f86e  sub     rax, [rdx+8]
0x18002f872  test    rax, rax
0x18002f875  jz      loc_18002F7E9
0x18002f87b  dec     r11d
0x18002f87e  jmp     short loc_18002F84E
0x18002f880  xor     r8d, r8d
0x18002f883  cmp     r8d, r10d
0x18002f886  jge     loc_18002F7BE
0x18002f88c  movsxd  rax, r8d
0x18002f88f  lea     rcx, [rax+rax*4]
0x18002f893  mov     rax, [rbx+18h]
0x18002f897  lea     rdx, [rax+rcx*8]
0x18002f89b  cmp     [rdx], ebp
0x18002f89d  ja      loc_18002F7BE
0x18002f8a3  jz      short loc_18002F8AA
0x18002f8a5  inc     r8d
0x18002f8a8  jmp     short loc_18002F883
0x18002f8aa  mov     rax, [rsi]
0x18002f8ad  sub     rax, [rdx]
0x18002f8b0  jnz     short loc_18002F8BA
0x18002f8b2  mov     rax, [rsi+8]
0x18002f8b6  sub     rax, [rdx+8]
0x18002f8ba  test    rax, rax
0x18002f8bd  jz      loc_18002F7E9
0x18002f8c3  jmp     short loc_18002F8A5
0x18002f8c5  inc     r8d
0x18002f8c8  cmp     r8d, r10d
0x18002f8cb  jge     loc_18002F7BE
0x18002f8d1  movsxd  rax, r8d
0x18002f8d4  lea     rcx, [rax+rax*4]
0x18002f8d8  lea     rdx, [rbx+rcx*8]
0x18002f8dc  cmp     ebp, [rdx]
0x18002f8de  jnz     loc_18002F7BE
0x18002f8e4  mov     rax, [rsi]
0x18002f8e7  sub     rax, [rdx]
0x18002f8ea  jnz     short loc_18002F8F4
0x18002f8ec  mov     rax, [rsi+8]
0x18002f8f0  sub     rax, [rdx+8]
0x18002f8f4  test    rax, rax
0x18002f8f7  jz      loc_18002F7E9
0x18002f8fd  inc     r8d
0x18002f900  jmp     short loc_18002F8C8
0x18002f902  mov     ebx, 0C00D36BDh
0x18002f907  jmp     loc_18002F819
```
