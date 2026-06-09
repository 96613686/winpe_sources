# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetBlob(_GUID const &,uchar *,uint,uint *)

- ea: `0x18005d080`
- end: `0x18005d271`
- name: `?GetBlob@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAEIPEAI@Z`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180149160`

## callees

- `0x18005d080`
- `0x180121581`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d0b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d0b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d250`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d250`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d25c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d25c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d099`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d13e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d099`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d13e`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetBlob(
        __int64 a1,
        unsigned int *a2,
        void *a3,
        unsigned int a4,
        _DWORD *a5)
{
  int v9; // r8d
  unsigned int v10; // ebx
  int v11; // r9d
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  unsigned int v14; // edi
  int v15; // eax
  __int64 v16; // r14
  int v17; // r9d
  __int64 v18; // r10
  int i; // r11d
  int j; // r9d

  if ( *(_DWORD *)(a1 + 24) == GetCurrentThreadId() )
    ++*(_DWORD *)(a1 + 28);
  else
    AcquireSRWLockShared((PSRWLOCK)(a1 + 16));
  v9 = *(_DWORD *)(a1 + 44);
  if ( !v9 )
    goto LABEL_19;
  v10 = *a2;
  if ( v9 < 4 )
  {
    if ( v9 > 0 )
    {
      v11 = 0;
      while ( 1 )
      {
        v12 = (_QWORD *)(*(_QWORD *)(a1 + 32) + 40LL * v11);
        if ( *(_DWORD *)v12 == v10 )
        {
          if ( *(_QWORD *)a2 == *v12 && *((_QWORD *)a2 + 1) == v12[1] )
            goto LABEL_11;
        }
        else if ( *(_DWORD *)v12 > v10 )
        {
          goto LABEL_19;
        }
        if ( ++v11 >= v9 )
          goto LABEL_19;
      }
    }
    goto LABEL_19;
  }
  v16 = *(_QWORD *)(a1 + 32);
  v17 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v18 = (v17 + v9) / 2;
      v12 = (_QWORD *)(v16 + 40 * v18);
      if ( v10 >= *(_DWORD *)v12 )
        break;
      if ( (_DWORD)v18 == v17 )
        goto LABEL_19;
      v9 = (v17 + v9) / 2;
    }
    if ( v10 <= *(_DWORD *)v12 )
      break;
    v17 = v18 + 1;
    if ( (_DWORD)v18 + 1 == v9 )
      goto LABEL_19;
  }
  if ( *(_QWORD *)a2 != *v12 || *((_QWORD *)a2 + 1) != v12[1] )
  {
    if ( (int)v18 > v17 )
    {
      for ( i = v18 - 1; i >= v17; --i )
      {
        v12 = (_QWORD *)(v16 + 40LL * i);
        if ( v10 != *(_DWORD *)v12 )
          break;
        if ( *(_QWORD *)a2 == *v12 && *((_QWORD *)a2 + 1) == v12[1] )
          goto LABEL_11;
      }
    }
    for ( j = v18 + 1; j < v9; ++j )
    {
      v12 = (_QWORD *)(v16 + 40LL * j);
      if ( v10 != *(_DWORD *)v12 )
        break;
      if ( *(_QWORD *)a2 == *v12 && *((_QWORD *)a2 + 1) == v12[1] )
        goto LABEL_11;
    }
    goto LABEL_19;
  }
LABEL_11:
  v13 = v12 + 2;
  if ( !v13 )
  {
LABEL_19:
    v14 = -1072875802;
    goto LABEL_20;
  }
  if ( *(_WORD *)v13 == 4113 )
  {
    if ( a5 )
      *a5 = *((_DWORD *)v13 + 2);
    if ( *((_DWORD *)v13 + 2) <= a4 )
    {
      v14 = 0;
      memcpy_0(a3, (const void *)v13[2], *((unsigned int *)v13 + 2));
    }
    else
    {
      v14 = -2147024774;
    }
  }
  else
  {
    v14 = -1072875843;
  }
LABEL_20:
  if ( *(_DWORD *)(a1 + 24) == GetCurrentThreadId() )
  {
    v15 = *(_DWORD *)(a1 + 28);
    if ( v15 )
    {
      *(_DWORD *)(a1 + 28) = v15 - 1;
    }
    else
    {
      *(_DWORD *)(a1 + 24) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 16));
    }
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)(a1 + 16));
  }
  return v14;
}

```

## disassembly

```asm
0x18005d080  push    rbx
0x18005d082  push    rbp
0x18005d083  push    rsi
0x18005d084  push    rdi
0x18005d085  push    r14
0x18005d087  push    r15
0x18005d089  sub     rsp, 28h
0x18005d08d  mov     ebp, r9d
0x18005d090  mov     r15, r8
0x18005d093  mov     rdi, rdx
0x18005d096  mov     rsi, rcx
0x18005d099  call    cs:__imp_GetCurrentThreadId
0x18005d09f  mov     r10d, [rsi+18h]
0x18005d0a3  cmp     r10d, eax
0x18005d0a6  jnz     short loc_18005D0AD
0x18005d0a8  inc     dword ptr [rsi+1Ch]
0x18005d0ab  jmp     short loc_18005D0B7
0x18005d0ad  lea     rcx, [rsi+10h]; SRWLock
0x18005d0b1  call    cs:__imp_AcquireSRWLockShared
0x18005d0b7  mov     r8d, [rsi+2Ch]
0x18005d0bb  test    r8d, r8d
0x18005d0be  jz      short loc_18005D139
0x18005d0c0  mov     ebx, [rdi]
0x18005d0c2  cmp     r8d, 4
0x18005d0c6  jge     loc_18005D164
0x18005d0cc  test    r8d, r8d
0x18005d0cf  jle     short loc_18005D139
0x18005d0d1  mov     r10, [rsi+20h]
0x18005d0d5  xor     r9d, r9d
0x18005d0d8  movsxd  rax, r9d
0x18005d0db  lea     rcx, [rax+rax*4]
0x18005d0df  lea     rdx, [r10+rcx*8]
0x18005d0e3  cmp     [rdx], ebx
0x18005d0e5  jnz     short loc_18005D12F
0x18005d0e7  mov     rax, [rdi]
0x18005d0ea  cmp     rax, [rdx]
0x18005d0ed  jnz     short loc_18005D131
0x18005d0ef  mov     rax, [rdi+8]
0x18005d0f3  cmp     rax, [rdx+8]
0x18005d0f7  jnz     short loc_18005D131
0x18005d0f9  add     rdx, 10h
0x18005d0fd  jz      short loc_18005D139
0x18005d0ff  mov     eax, 1011h
0x18005d104  cmp     [rdx], ax
0x18005d107  jnz     loc_18005D23B
0x18005d10d  mov     rcx, [rsp+58h+arg_20]
0x18005d115  test    rcx, rcx
0x18005d118  jz      short loc_18005D11F
0x18005d11a  mov     eax, [rdx+8]
0x18005d11d  mov     [rcx], eax
0x18005d11f  cmp     [rdx+8], ebp
0x18005d122  jbe     loc_18005D224
0x18005d128  mov     edi, 8007007Ah
0x18005d12d  jmp     short loc_18005D13E
0x18005d12f  ja      short loc_18005D139
0x18005d131  inc     r9d
0x18005d134  cmp     r9d, r8d
0x18005d137  jl      short loc_18005D0D8
0x18005d139  mov     edi, 0C00D36E6h
0x18005d13e  call    cs:__imp_GetCurrentThreadId
0x18005d144  mov     ecx, [rsi+18h]
0x18005d147  cmp     ecx, eax
0x18005d149  jnz     loc_18005D258
0x18005d14f  mov     eax, [rsi+1Ch]
0x18005d152  test    eax, eax
0x18005d154  jz      loc_18005D245
0x18005d15a  dec     eax
0x18005d15c  mov     [rsi+1Ch], eax
0x18005d15f  jmp     loc_18005D262
0x18005d164  mov     r14, [rsi+20h]
0x18005d168  xor     r9d, r9d
0x18005d16b  lea     eax, [r9+r8]
0x18005d16f  cdq
0x18005d170  sub     eax, edx
0x18005d172  sar     eax, 1
0x18005d174  movsxd  r10, eax
0x18005d177  lea     rdx, [r10+r10*4]
0x18005d17b  lea     rdx, [r14+rdx*8]
0x18005d17f  cmp     ebx, [rdx]
0x18005d181  jnb     short loc_18005D18D
0x18005d183  cmp     r10d, r9d
0x18005d186  jz      short loc_18005D139
0x18005d188  mov     r8d, r10d
0x18005d18b  jmp     short loc_18005D16B
0x18005d18d  jbe     short loc_18005D19A
0x18005d18f  lea     r9d, [r10+1]
0x18005d193  cmp     r9d, r8d
0x18005d196  jnz     short loc_18005D16B
0x18005d198  jmp     short loc_18005D139
0x18005d19a  mov     rax, [rdi]
0x18005d19d  cmp     rax, [rdx]
0x18005d1a0  jnz     short loc_18005D1B0
0x18005d1a2  mov     rax, [rdi+8]
0x18005d1a6  cmp     rax, [rdx+8]
0x18005d1aa  jz      loc_18005D0F9
0x18005d1b0  cmp     r10d, r9d
0x18005d1b3  jle     short loc_18005D1E8
0x18005d1b5  lea     r11d, [r10-1]
0x18005d1b9  jmp     short loc_18005D1E3
0x18005d1bb  movsxd  rax, r11d
0x18005d1be  lea     rcx, [rax+rax*4]
0x18005d1c2  lea     rdx, [r14+rcx*8]
0x18005d1c6  cmp     ebx, [rdx]
0x18005d1c8  jnz     short loc_18005D1E8
0x18005d1ca  mov     rax, [rdi]
0x18005d1cd  cmp     rax, [rdx]
0x18005d1d0  jnz     short loc_18005D1E0
0x18005d1d2  mov     rax, [rdi+8]
0x18005d1d6  cmp     rax, [rdx+8]
0x18005d1da  jz      loc_18005D0F9
0x18005d1e0  dec     r11d
0x18005d1e3  cmp     r11d, r9d
0x18005d1e6  jge     short loc_18005D1BB
0x18005d1e8  lea     r9d, [r10+1]
0x18005d1ec  jmp     short loc_18005D21A
0x18005d1ee  movsxd  rax, r9d
0x18005d1f1  lea     rcx, [rax+rax*4]
0x18005d1f5  lea     rdx, [r14+rcx*8]
0x18005d1f9  cmp     ebx, [rdx]
0x18005d1fb  jnz     loc_18005D139
0x18005d201  mov     rax, [rdi]
0x18005d204  cmp     rax, [rdx]
0x18005d207  jnz     short loc_18005D217
0x18005d209  mov     rax, [rdi+8]
0x18005d20d  cmp     rax, [rdx+8]
0x18005d211  jz      loc_18005D0F9
0x18005d217  inc     r9d
0x18005d21a  cmp     r9d, r8d
0x18005d21d  jl      short loc_18005D1EE
0x18005d21f  jmp     loc_18005D139
0x18005d224  mov     r8d, [rdx+8]; Size
0x18005d228  xor     edi, edi
0x18005d22a  mov     rdx, [rdx+10h]; Src
0x18005d22e  mov     rcx, r15; void *
0x18005d231  call    memcpy_0
0x18005d236  jmp     loc_18005D13E
0x18005d23b  mov     edi, 0C00D36BDh
0x18005d240  jmp     loc_18005D13E
0x18005d245  lea     rcx, [rsi+10h]; SRWLock
0x18005d249  mov     dword ptr [rsi+18h], 0
0x18005d250  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d256  jmp     short loc_18005D262
0x18005d258  lea     rcx, [rsi+10h]; SRWLock
0x18005d25c  call    cs:__imp_ReleaseSRWLockShared
0x18005d262  mov     eax, edi
0x18005d264  add     rsp, 28h
0x18005d268  pop     r15
0x18005d26a  pop     r14
0x18005d26c  pop     rdi
0x18005d26d  pop     rsi
0x18005d26e  pop     rbp
0x18005d26f  pop     rbx
0x18005d270  retn
```
