# CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetAllocatedBlob(_GUID const &,uchar * *,uint *)

- ea: `0x18005dfe0`
- end: `0x18005e1de`
- name: `?GetAllocatedBlob@?$CMFAttributesImpl@UIMFSpatialAudioSample@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAPEAEPEAI@Z`
- size: `510`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005dfe0`
- `0x180121581`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005e011`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005e011`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e1bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e1bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005e1c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005e1c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dff9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e0ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dff9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e0ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005e082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005e082`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetAllocatedBlob(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3,
        _DWORD *a4)
{
  int v8; // r8d
  unsigned int v9; // ebx
  int v10; // r9d
  __int64 v11; // rdx
  __int64 v12; // rbx
  void *v13; // rax
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
  v8 = *(_DWORD *)(a1 + 36);
  if ( !v8 )
    goto LABEL_19;
  v9 = *a2;
  if ( v8 < 4 )
  {
    if ( v8 > 0 )
    {
      v10 = 0;
      while ( 1 )
      {
        v11 = *(_QWORD *)(a1 + 24) + 40LL * v10;
        if ( *(_DWORD *)v11 == v9 )
        {
          if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
            goto LABEL_11;
        }
        else if ( *(_DWORD *)v11 > v9 )
        {
          goto LABEL_19;
        }
        if ( ++v10 >= v8 )
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
      v18 = (v17 + v8) / 2;
      v11 = v16 + 40 * v18;
      if ( v9 >= *(_DWORD *)v11 )
        break;
      if ( (_DWORD)v18 == v17 )
        goto LABEL_19;
      v8 = (v17 + v8) / 2;
    }
    if ( v9 <= *(_DWORD *)v11 )
      break;
    v17 = v18 + 1;
    if ( (_DWORD)v18 + 1 == v8 )
      goto LABEL_19;
  }
  if ( *(_QWORD *)a2 != *(_QWORD *)v11 || *((_QWORD *)a2 + 1) != *(_QWORD *)(v11 + 8) )
  {
    if ( (int)v18 > v17 )
    {
      for ( i = v18 - 1; i >= v17; --i )
      {
        v11 = v16 + 40LL * i;
        if ( v9 != *(_DWORD *)v11 )
          break;
        if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
          goto LABEL_11;
      }
    }
    for ( j = v18 + 1; j < v8; ++j )
    {
      v11 = v16 + 40LL * j;
      if ( v9 != *(_DWORD *)v11 )
        break;
      if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
        goto LABEL_11;
    }
    goto LABEL_19;
  }
LABEL_11:
  v12 = v11 + 16;
  if ( v11 == -16 )
  {
LABEL_19:
    v14 = -1072875802;
    goto LABEL_20;
  }
  if ( *(_WORD *)v12 == 4113 )
  {
    if ( a4 )
      *a4 = *(_DWORD *)(v11 + 24);
    v13 = CoTaskMemAlloc(*(unsigned int *)(v11 + 24));
    *a3 = v13;
    if ( v13 )
    {
      v14 = 0;
      memcpy_0(v13, *(const void **)(v12 + 16), *(unsigned int *)(v12 + 8));
    }
    else
    {
      v14 = -2147024882;
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
0x18005dfe0  push    rbx
0x18005dfe2  push    rbp
0x18005dfe3  push    rsi
0x18005dfe4  push    rdi
0x18005dfe5  push    r14
0x18005dfe7  push    r15
0x18005dfe9  sub     rsp, 28h
0x18005dfed  mov     r15, r9
0x18005dff0  mov     rbp, r8
0x18005dff3  mov     rdi, rdx
0x18005dff6  mov     rsi, rcx
0x18005dff9  call    cs:__imp_GetCurrentThreadId
0x18005dfff  mov     r10d, [rsi+10h]
0x18005e003  cmp     r10d, eax
0x18005e006  jnz     short loc_18005E00D
0x18005e008  inc     dword ptr [rsi+14h]
0x18005e00b  jmp     short loc_18005E017
0x18005e00d  lea     rcx, [rsi+8]; SRWLock
0x18005e011  call    cs:__imp_AcquireSRWLockShared
0x18005e017  mov     r8d, [rsi+24h]
0x18005e01b  test    r8d, r8d
0x18005e01e  jz      loc_18005E0A6
0x18005e024  mov     ebx, [rdi]
0x18005e026  cmp     r8d, 4
0x18005e02a  jge     loc_18005E0D1
0x18005e030  test    r8d, r8d
0x18005e033  jle     short loc_18005E0A6
0x18005e035  mov     r10, [rsi+18h]
0x18005e039  xor     r9d, r9d
0x18005e03c  movsxd  rax, r9d
0x18005e03f  lea     rcx, [rax+rax*4]
0x18005e043  lea     rdx, [r10+rcx*8]
0x18005e047  cmp     [rdx], ebx
0x18005e049  jnz     short loc_18005E09C
0x18005e04b  mov     rax, [rdi]
0x18005e04e  cmp     rax, [rdx]
0x18005e051  jnz     short loc_18005E09E
0x18005e053  mov     rax, [rdi+8]
0x18005e057  cmp     rax, [rdx+8]
0x18005e05b  jnz     short loc_18005E09E
0x18005e05d  lea     rbx, [rdx+10h]
0x18005e061  test    rbx, rbx
0x18005e064  jz      short loc_18005E0A6
0x18005e066  mov     eax, 1011h
0x18005e06b  cmp     [rbx], ax
0x18005e06e  jnz     loc_18005E1A8
0x18005e074  test    r15, r15
0x18005e077  jz      short loc_18005E07F
0x18005e079  mov     eax, [rbx+8]
0x18005e07c  mov     [r15], eax
0x18005e07f  mov     ecx, [rbx+8]; cb
0x18005e082  call    cs:__imp_CoTaskMemAlloc
0x18005e088  mov     [rbp+0], rax
0x18005e08c  test    rax, rax
0x18005e08f  jnz     loc_18005E191
0x18005e095  mov     edi, 8007000Eh
0x18005e09a  jmp     short loc_18005E0AB
0x18005e09c  ja      short loc_18005E0A6
0x18005e09e  inc     r9d
0x18005e0a1  cmp     r9d, r8d
0x18005e0a4  jl      short loc_18005E03C
0x18005e0a6  mov     edi, 0C00D36E6h
0x18005e0ab  call    cs:__imp_GetCurrentThreadId
0x18005e0b1  mov     ecx, [rsi+10h]
0x18005e0b4  cmp     ecx, eax
0x18005e0b6  jnz     loc_18005E1C5
0x18005e0bc  mov     eax, [rsi+14h]
0x18005e0bf  test    eax, eax
0x18005e0c1  jz      loc_18005E1B2
0x18005e0c7  dec     eax
0x18005e0c9  mov     [rsi+14h], eax
0x18005e0cc  jmp     loc_18005E1CF
0x18005e0d1  mov     r14, [rsi+18h]
0x18005e0d5  xor     r9d, r9d
0x18005e0d8  lea     eax, [r9+r8]
0x18005e0dc  cdq
0x18005e0dd  sub     eax, edx
0x18005e0df  sar     eax, 1
0x18005e0e1  movsxd  r10, eax
0x18005e0e4  lea     rdx, [r10+r10*4]
0x18005e0e8  lea     rdx, [r14+rdx*8]
0x18005e0ec  cmp     ebx, [rdx]
0x18005e0ee  jnb     short loc_18005E0FA
0x18005e0f0  cmp     r10d, r9d
0x18005e0f3  jz      short loc_18005E0A6
0x18005e0f5  mov     r8d, r10d
0x18005e0f8  jmp     short loc_18005E0D8
0x18005e0fa  jbe     short loc_18005E107
0x18005e0fc  lea     r9d, [r10+1]
0x18005e100  cmp     r9d, r8d
0x18005e103  jnz     short loc_18005E0D8
0x18005e105  jmp     short loc_18005E0A6
0x18005e107  mov     rax, [rdi]
0x18005e10a  cmp     rax, [rdx]
0x18005e10d  jnz     short loc_18005E11D
0x18005e10f  mov     rax, [rdi+8]
0x18005e113  cmp     rax, [rdx+8]
0x18005e117  jz      loc_18005E05D
0x18005e11d  cmp     r10d, r9d
0x18005e120  jle     short loc_18005E155
0x18005e122  lea     r11d, [r10-1]
0x18005e126  jmp     short loc_18005E150
0x18005e128  movsxd  rax, r11d
0x18005e12b  lea     rcx, [rax+rax*4]
0x18005e12f  lea     rdx, [r14+rcx*8]
0x18005e133  cmp     ebx, [rdx]
0x18005e135  jnz     short loc_18005E155
0x18005e137  mov     rax, [rdi]
0x18005e13a  cmp     rax, [rdx]
0x18005e13d  jnz     short loc_18005E14D
0x18005e13f  mov     rax, [rdi+8]
0x18005e143  cmp     rax, [rdx+8]
0x18005e147  jz      loc_18005E05D
0x18005e14d  dec     r11d
0x18005e150  cmp     r11d, r9d
0x18005e153  jge     short loc_18005E128
0x18005e155  lea     r9d, [r10+1]
0x18005e159  jmp     short loc_18005E187
0x18005e15b  movsxd  rax, r9d
0x18005e15e  lea     rcx, [rax+rax*4]
0x18005e162  lea     rdx, [r14+rcx*8]
0x18005e166  cmp     ebx, [rdx]
0x18005e168  jnz     loc_18005E0A6
0x18005e16e  mov     rax, [rdi]
0x18005e171  cmp     rax, [rdx]
0x18005e174  jnz     short loc_18005E184
0x18005e176  mov     rax, [rdi+8]
0x18005e17a  cmp     rax, [rdx+8]
0x18005e17e  jz      loc_18005E05D
0x18005e184  inc     r9d
0x18005e187  cmp     r9d, r8d
0x18005e18a  jl      short loc_18005E15B
0x18005e18c  jmp     loc_18005E0A6
0x18005e191  mov     r8d, [rbx+8]; Size
0x18005e195  xor     edi, edi
0x18005e197  mov     rdx, [rbx+10h]; Src
0x18005e19b  mov     rcx, rax; void *
0x18005e19e  call    memcpy_0
0x18005e1a3  jmp     loc_18005E0AB
0x18005e1a8  mov     edi, 0C00D36BDh
0x18005e1ad  jmp     loc_18005E0AB
0x18005e1b2  lea     rcx, [rsi+8]; SRWLock
0x18005e1b6  mov     dword ptr [rsi+10h], 0
0x18005e1bd  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e1c3  jmp     short loc_18005E1CF
0x18005e1c5  lea     rcx, [rsi+8]; SRWLock
0x18005e1c9  call    cs:__imp_ReleaseSRWLockShared
0x18005e1cf  mov     eax, edi
0x18005e1d1  add     rsp, 28h
0x18005e1d5  pop     r15
0x18005e1d7  pop     r14
0x18005e1d9  pop     rdi
0x18005e1da  pop     rsi
0x18005e1db  pop     rbp
0x18005e1dc  pop     rbx
0x18005e1dd  retn
```
