# CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetBlob(_GUID const &,uchar *,uint,uint *)

- ea: `0x18005d3c0`
- end: `0x18005d5b1`
- name: `?GetBlob@?$CMFAttributesImpl@UIMFMediaEvent@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAEIPEAI@Z`
- size: `497`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18005d3c0`
- `0x180121581`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d3f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d3f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d59c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d59c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d3d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d47e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d3d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d47e`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetBlob(
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

  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
    ++*(_DWORD *)(a1 + 20);
  else
    AcquireSRWLockShared((PSRWLOCK)(a1 + 8));
  v9 = *(_DWORD *)(a1 + 36);
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
        v12 = (_QWORD *)(*(_QWORD *)(a1 + 24) + 40LL * v11);
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
  v16 = *(_QWORD *)(a1 + 24);
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
  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
  {
    v15 = *(_DWORD *)(a1 + 20);
    if ( v15 )
    {
      *(_DWORD *)(a1 + 20) = v15 - 1;
    }
    else
    {
      *(_DWORD *)(a1 + 16) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
    }
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)(a1 + 8));
  }
  return v14;
}

```

## disassembly

```asm
0x18005d3c0  push    rbx
0x18005d3c2  push    rbp
0x18005d3c3  push    rsi
0x18005d3c4  push    rdi
0x18005d3c5  push    r14
0x18005d3c7  push    r15
0x18005d3c9  sub     rsp, 28h
0x18005d3cd  mov     ebp, r9d
0x18005d3d0  mov     r15, r8
0x18005d3d3  mov     rdi, rdx
0x18005d3d6  mov     rsi, rcx
0x18005d3d9  call    cs:__imp_GetCurrentThreadId
0x18005d3df  mov     r10d, [rsi+10h]
0x18005d3e3  cmp     r10d, eax
0x18005d3e6  jnz     short loc_18005D3ED
0x18005d3e8  inc     dword ptr [rsi+14h]
0x18005d3eb  jmp     short loc_18005D3F7
0x18005d3ed  lea     rcx, [rsi+8]; SRWLock
0x18005d3f1  call    cs:__imp_AcquireSRWLockShared
0x18005d3f7  mov     r8d, [rsi+24h]
0x18005d3fb  test    r8d, r8d
0x18005d3fe  jz      short loc_18005D479
0x18005d400  mov     ebx, [rdi]
0x18005d402  cmp     r8d, 4
0x18005d406  jge     loc_18005D4A4
0x18005d40c  test    r8d, r8d
0x18005d40f  jle     short loc_18005D479
0x18005d411  mov     r10, [rsi+18h]
0x18005d415  xor     r9d, r9d
0x18005d418  movsxd  rax, r9d
0x18005d41b  lea     rcx, [rax+rax*4]
0x18005d41f  lea     rdx, [r10+rcx*8]
0x18005d423  cmp     [rdx], ebx
0x18005d425  jnz     short loc_18005D46F
0x18005d427  mov     rax, [rdi]
0x18005d42a  cmp     rax, [rdx]
0x18005d42d  jnz     short loc_18005D471
0x18005d42f  mov     rax, [rdi+8]
0x18005d433  cmp     rax, [rdx+8]
0x18005d437  jnz     short loc_18005D471
0x18005d439  add     rdx, 10h
0x18005d43d  jz      short loc_18005D479
0x18005d43f  mov     eax, 1011h
0x18005d444  cmp     [rdx], ax
0x18005d447  jnz     loc_18005D57B
0x18005d44d  mov     rcx, [rsp+58h+arg_20]
0x18005d455  test    rcx, rcx
0x18005d458  jz      short loc_18005D45F
0x18005d45a  mov     eax, [rdx+8]
0x18005d45d  mov     [rcx], eax
0x18005d45f  cmp     [rdx+8], ebp
0x18005d462  jbe     loc_18005D564
0x18005d468  mov     edi, 8007007Ah
0x18005d46d  jmp     short loc_18005D47E
0x18005d46f  ja      short loc_18005D479
0x18005d471  inc     r9d
0x18005d474  cmp     r9d, r8d
0x18005d477  jl      short loc_18005D418
0x18005d479  mov     edi, 0C00D36E6h
0x18005d47e  call    cs:__imp_GetCurrentThreadId
0x18005d484  mov     ecx, [rsi+10h]
0x18005d487  cmp     ecx, eax
0x18005d489  jnz     loc_18005D598
0x18005d48f  mov     eax, [rsi+14h]
0x18005d492  test    eax, eax
0x18005d494  jz      loc_18005D585
0x18005d49a  dec     eax
0x18005d49c  mov     [rsi+14h], eax
0x18005d49f  jmp     loc_18005D5A2
0x18005d4a4  mov     r14, [rsi+18h]
0x18005d4a8  xor     r9d, r9d
0x18005d4ab  lea     eax, [r9+r8]
0x18005d4af  cdq
0x18005d4b0  sub     eax, edx
0x18005d4b2  sar     eax, 1
0x18005d4b4  movsxd  r10, eax
0x18005d4b7  lea     rdx, [r10+r10*4]
0x18005d4bb  lea     rdx, [r14+rdx*8]
0x18005d4bf  cmp     ebx, [rdx]
0x18005d4c1  jnb     short loc_18005D4CD
0x18005d4c3  cmp     r10d, r9d
0x18005d4c6  jz      short loc_18005D479
0x18005d4c8  mov     r8d, r10d
0x18005d4cb  jmp     short loc_18005D4AB
0x18005d4cd  jbe     short loc_18005D4DA
0x18005d4cf  lea     r9d, [r10+1]
0x18005d4d3  cmp     r9d, r8d
0x18005d4d6  jnz     short loc_18005D4AB
0x18005d4d8  jmp     short loc_18005D479
0x18005d4da  mov     rax, [rdi]
0x18005d4dd  cmp     rax, [rdx]
0x18005d4e0  jnz     short loc_18005D4F0
0x18005d4e2  mov     rax, [rdi+8]
0x18005d4e6  cmp     rax, [rdx+8]
0x18005d4ea  jz      loc_18005D439
0x18005d4f0  cmp     r10d, r9d
0x18005d4f3  jle     short loc_18005D528
0x18005d4f5  lea     r11d, [r10-1]
0x18005d4f9  jmp     short loc_18005D523
0x18005d4fb  movsxd  rax, r11d
0x18005d4fe  lea     rcx, [rax+rax*4]
0x18005d502  lea     rdx, [r14+rcx*8]
0x18005d506  cmp     ebx, [rdx]
0x18005d508  jnz     short loc_18005D528
0x18005d50a  mov     rax, [rdi]
0x18005d50d  cmp     rax, [rdx]
0x18005d510  jnz     short loc_18005D520
0x18005d512  mov     rax, [rdi+8]
0x18005d516  cmp     rax, [rdx+8]
0x18005d51a  jz      loc_18005D439
0x18005d520  dec     r11d
0x18005d523  cmp     r11d, r9d
0x18005d526  jge     short loc_18005D4FB
0x18005d528  lea     r9d, [r10+1]
0x18005d52c  jmp     short loc_18005D55A
0x18005d52e  movsxd  rax, r9d
0x18005d531  lea     rcx, [rax+rax*4]
0x18005d535  lea     rdx, [r14+rcx*8]
0x18005d539  cmp     ebx, [rdx]
0x18005d53b  jnz     loc_18005D479
0x18005d541  mov     rax, [rdi]
0x18005d544  cmp     rax, [rdx]
0x18005d547  jnz     short loc_18005D557
0x18005d549  mov     rax, [rdi+8]
0x18005d54d  cmp     rax, [rdx+8]
0x18005d551  jz      loc_18005D439
0x18005d557  inc     r9d
0x18005d55a  cmp     r9d, r8d
0x18005d55d  jl      short loc_18005D52E
0x18005d55f  jmp     loc_18005D479
0x18005d564  mov     r8d, [rdx+8]; Size
0x18005d568  xor     edi, edi
0x18005d56a  mov     rdx, [rdx+10h]; Src
0x18005d56e  mov     rcx, r15; void *
0x18005d571  call    memcpy_0
0x18005d576  jmp     loc_18005D47E
0x18005d57b  mov     edi, 0C00D36BDh
0x18005d580  jmp     loc_18005D47E
0x18005d585  lea     rcx, [rsi+8]; SRWLock
0x18005d589  mov     dword ptr [rsi+10h], 0
0x18005d590  call    cs:__imp_ReleaseSRWLockExclusive
0x18005d596  jmp     short loc_18005D5A2
0x18005d598  lea     rcx, [rsi+8]; SRWLock
0x18005d59c  call    cs:__imp_ReleaseSRWLockShared
0x18005d5a2  mov     eax, edi
0x18005d5a4  add     rsp, 28h
0x18005d5a8  pop     r15
0x18005d5aa  pop     r14
0x18005d5ac  pop     rdi
0x18005d5ad  pop     rsi
0x18005d5ae  pop     rbp
0x18005d5af  pop     rbx
0x18005d5b0  retn
```
