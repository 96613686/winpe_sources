# CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetUnknown(_GUID const &,_GUID const &,void * *)

- ea: `0x18005d5c0`
- end: `0x18005d79e`
- name: `?GetUnknown@?$CMFAttributesImpl@UIMFMediaEvent@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `478`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18005d5c0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d5fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d5fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d77e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d77e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d789`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d789`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d5e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d684`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d5e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d684`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetUnknown(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v6; // rdi
  int v9; // r8d
  unsigned int v10; // ebp
  int v11; // r9d
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  __int64 (__fastcall ***v14)(_QWORD, __int64, _QWORD *); // rcx
  unsigned int v15; // ebx
  int v16; // eax
  __int64 v17; // rbx
  int v18; // r9d
  __int64 v19; // r10
  int i; // r11d
  int j; // r9d

  *a4 = 0;
  v6 = a1 + 8;
  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
    ++*(_DWORD *)(v6 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v6);
  v9 = *(_DWORD *)(a1 + 36);
  if ( !v9 )
    goto LABEL_17;
  v10 = *a2;
  if ( v9 < 4 )
  {
    if ( v9 > 0 )
    {
      v11 = 0;
      while ( 1 )
      {
        v12 = (_QWORD *)(*(_QWORD *)(a1 + 24) + 40LL * v11);
        if ( *(_DWORD *)v12 == v10 )
        {
          if ( *(_QWORD *)a2 == *v12 && *((_QWORD *)a2 + 1) == v12[1] )
            goto LABEL_11;
        }
        else if ( *(_DWORD *)v12 > v10 )
        {
          goto LABEL_17;
        }
        if ( ++v11 >= v9 )
          goto LABEL_17;
      }
    }
    goto LABEL_17;
  }
  v17 = *(_QWORD *)(a1 + 24);
  v18 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v19 = (v18 + v9) / 2;
      v12 = (_QWORD *)(v17 + 40 * v19);
      if ( v10 >= *(_DWORD *)v12 )
        break;
      if ( (_DWORD)v19 == v18 )
        goto LABEL_17;
      v9 = (v18 + v9) / 2;
    }
    if ( v10 <= *(_DWORD *)v12 )
      break;
    v18 = v19 + 1;
    if ( (_DWORD)v19 + 1 == v9 )
      goto LABEL_17;
  }
  if ( *(_QWORD *)a2 != *v12 || *((_QWORD *)a2 + 1) != v12[1] )
  {
    if ( (int)v19 > v18 )
    {
      for ( i = v19 - 1; i >= v18; --i )
      {
        v12 = (_QWORD *)(v17 + 40LL * i);
        if ( v10 != *(_DWORD *)v12 )
          break;
        if ( *(_QWORD *)a2 == *v12 && *((_QWORD *)a2 + 1) == v12[1] )
          goto LABEL_11;
      }
    }
    for ( j = v19 + 1; j < v9; ++j )
    {
      v12 = (_QWORD *)(v17 + 40LL * j);
      if ( v10 != *(_DWORD *)v12 )
        break;
      if ( *(_QWORD *)a2 == *v12 && *((_QWORD *)a2 + 1) == v12[1] )
        goto LABEL_11;
    }
    goto LABEL_17;
  }
LABEL_11:
  v13 = v12 + 2;
  if ( !v13 )
  {
LABEL_17:
    v15 = -1072875802;
    goto LABEL_18;
  }
  if ( *(_WORD *)v13 == 13 && (v14 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))v13[1]) != 0 )
    v15 = (**v14)(v14, a3, a4);
  else
    v15 = -1072875843;
LABEL_18:
  if ( *(_DWORD *)(v6 + 8) == GetCurrentThreadId() )
  {
    v16 = *(_DWORD *)(v6 + 12);
    if ( v16 )
    {
      *(_DWORD *)(v6 + 12) = v16 - 1;
    }
    else
    {
      *(_DWORD *)(v6 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v6);
    }
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v6);
  }
  return v15;
}

```

## disassembly

```asm
0x18005d5c0  push    rbx
0x18005d5c2  push    rbp
0x18005d5c3  push    rsi
0x18005d5c4  push    rdi
0x18005d5c5  push    r14
0x18005d5c7  push    r15
0x18005d5c9  sub     rsp, 28h
0x18005d5cd  mov     r14, r9
0x18005d5d0  mov     qword ptr [r9], 0
0x18005d5d7  mov     r15, r8
0x18005d5da  lea     rdi, [rcx+8]
0x18005d5de  mov     rsi, rdx
0x18005d5e1  mov     rbx, rcx
0x18005d5e4  call    cs:__imp_GetCurrentThreadId
0x18005d5ea  mov     r10d, [rdi+8]
0x18005d5ee  cmp     r10d, eax
0x18005d5f1  jnz     short loc_18005D5F8
0x18005d5f3  inc     dword ptr [rdi+0Ch]
0x18005d5f6  jmp     short loc_18005D601
0x18005d5f8  mov     rcx, rdi; SRWLock
0x18005d5fb  call    cs:__imp_AcquireSRWLockShared
0x18005d601  mov     r8d, [rbx+24h]
0x18005d605  test    r8d, r8d
0x18005d608  jz      short loc_18005D67F
0x18005d60a  mov     ebp, [rsi]
0x18005d60c  cmp     r8d, 4
0x18005d610  jge     loc_18005D6AA
0x18005d616  test    r8d, r8d
0x18005d619  jle     short loc_18005D67F
0x18005d61b  mov     r10, [rbx+18h]
0x18005d61f  xor     r9d, r9d
0x18005d622  movsxd  rax, r9d
0x18005d625  lea     rcx, [rax+rax*4]
0x18005d629  lea     rdx, [r10+rcx*8]
0x18005d62d  cmp     [rdx], ebp
0x18005d62f  jnz     short loc_18005D675
0x18005d631  mov     rax, [rsi]
0x18005d634  cmp     rax, [rdx]
0x18005d637  jnz     short loc_18005D677
0x18005d639  mov     rax, [rsi+8]
0x18005d63d  cmp     rax, [rdx+8]
0x18005d641  jnz     short loc_18005D677
0x18005d643  add     rdx, 10h
0x18005d647  jz      short loc_18005D67F
0x18005d649  cmp     word ptr [rdx], 0Dh
0x18005d64d  jnz     loc_18005D76A
0x18005d653  mov     rcx, [rdx+8]
0x18005d657  test    rcx, rcx
0x18005d65a  jz      loc_18005D76A
0x18005d660  mov     rax, [rcx]
0x18005d663  mov     r8, r14
0x18005d666  mov     rdx, r15
0x18005d669  mov     rax, [rax]
0x18005d66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d671  mov     ebx, eax
0x18005d673  jmp     short loc_18005D684
0x18005d675  ja      short loc_18005D67F
0x18005d677  inc     r9d
0x18005d67a  cmp     r9d, r8d
0x18005d67d  jl      short loc_18005D622
0x18005d67f  mov     ebx, 0C00D36E6h
0x18005d684  call    cs:__imp_GetCurrentThreadId
0x18005d68a  mov     ecx, [rdi+8]
0x18005d68d  cmp     ecx, eax
0x18005d68f  jnz     loc_18005D786
0x18005d695  mov     eax, [rdi+0Ch]
0x18005d698  test    eax, eax
0x18005d69a  jz      loc_18005D774
0x18005d6a0  dec     eax
0x18005d6a2  mov     [rdi+0Ch], eax
0x18005d6a5  jmp     loc_18005D78F
0x18005d6aa  mov     rbx, [rbx+18h]
0x18005d6ae  xor     r9d, r9d
0x18005d6b1  lea     eax, [r9+r8]
0x18005d6b5  cdq
0x18005d6b6  sub     eax, edx
0x18005d6b8  sar     eax, 1
0x18005d6ba  movsxd  r10, eax
0x18005d6bd  lea     rdx, [r10+r10*4]
0x18005d6c1  lea     rdx, [rbx+rdx*8]
0x18005d6c5  cmp     ebp, [rdx]
0x18005d6c7  jnb     short loc_18005D6D3
0x18005d6c9  cmp     r10d, r9d
0x18005d6cc  jz      short loc_18005D67F
0x18005d6ce  mov     r8d, r10d
0x18005d6d1  jmp     short loc_18005D6B1
0x18005d6d3  jbe     short loc_18005D6E0
0x18005d6d5  lea     r9d, [r10+1]
0x18005d6d9  cmp     r9d, r8d
0x18005d6dc  jnz     short loc_18005D6B1
0x18005d6de  jmp     short loc_18005D67F
0x18005d6e0  mov     rax, [rsi]
0x18005d6e3  cmp     rax, [rdx]
0x18005d6e6  jnz     short loc_18005D6F6
0x18005d6e8  mov     rax, [rsi+8]
0x18005d6ec  cmp     rax, [rdx+8]
0x18005d6f0  jz      loc_18005D643
0x18005d6f6  cmp     r10d, r9d
0x18005d6f9  jle     short loc_18005D72E
0x18005d6fb  lea     r11d, [r10-1]
0x18005d6ff  jmp     short loc_18005D729
0x18005d701  movsxd  rax, r11d
0x18005d704  lea     rcx, [rax+rax*4]
0x18005d708  lea     rdx, [rbx+rcx*8]
0x18005d70c  cmp     ebp, [rdx]
0x18005d70e  jnz     short loc_18005D72E
0x18005d710  mov     rax, [rsi]
0x18005d713  cmp     rax, [rdx]
0x18005d716  jnz     short loc_18005D726
0x18005d718  mov     rax, [rsi+8]
0x18005d71c  cmp     rax, [rdx+8]
0x18005d720  jz      loc_18005D643
0x18005d726  dec     r11d
0x18005d729  cmp     r11d, r9d
0x18005d72c  jge     short loc_18005D701
0x18005d72e  lea     r9d, [r10+1]
0x18005d732  jmp     short loc_18005D760
0x18005d734  movsxd  rax, r9d
0x18005d737  lea     rcx, [rax+rax*4]
0x18005d73b  lea     rdx, [rbx+rcx*8]
0x18005d73f  cmp     ebp, [rdx]
0x18005d741  jnz     loc_18005D67F
0x18005d747  mov     rax, [rsi]
0x18005d74a  cmp     rax, [rdx]
0x18005d74d  jnz     short loc_18005D75D
0x18005d74f  mov     rax, [rsi+8]
0x18005d753  cmp     rax, [rdx+8]
0x18005d757  jz      loc_18005D643
0x18005d75d  inc     r9d
0x18005d760  cmp     r9d, r8d
0x18005d763  jl      short loc_18005D734
0x18005d765  jmp     loc_18005D67F
0x18005d76a  mov     ebx, 0C00D36BDh
0x18005d76f  jmp     loc_18005D684
0x18005d774  mov     rcx, rdi; SRWLock
0x18005d777  mov     dword ptr [rdi+8], 0
0x18005d77e  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d784  jmp     short loc_18005D78F
0x18005d786  mov     rcx, rdi; SRWLock
0x18005d789  call    cs:__imp_ReleaseSRWLockShared
0x18005d78f  mov     eax, ebx
0x18005d791  add     rsp, 28h
0x18005d795  pop     r15
0x18005d797  pop     r14
0x18005d799  pop     rdi
0x18005d79a  pop     rsi
0x18005d79b  pop     rbp
0x18005d79c  pop     rbx
0x18005d79d  retn
```
