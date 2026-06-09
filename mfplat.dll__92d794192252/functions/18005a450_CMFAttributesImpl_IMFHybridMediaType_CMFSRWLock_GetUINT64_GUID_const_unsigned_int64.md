# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetUINT64(_GUID const &,unsigned __int64 *)

- ea: `0x18005a450`
- end: `0x18005a60c`
- name: `?GetUINT64@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEA_K@Z`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180149730`

## callees

- `0x18005a450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005a47f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005a47f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a5ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a5ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005a5f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005a5f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a468`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a4f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a468`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a4f4`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetUINT64(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v4; // rbx
  int v7; // r8d
  unsigned int v8; // ebp
  int k; // r9d
  __int64 v10; // rdx
  unsigned int v11; // edi
  int v12; // eax
  __int64 v13; // rdi
  int v14; // r9d
  __int64 v15; // r10
  int i; // r11d
  int j; // r9d

  v4 = a1 + 16;
  if ( *(_DWORD *)(a1 + 24) == GetCurrentThreadId() )
    ++*(_DWORD *)(v4 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v4);
  v7 = *(_DWORD *)(a1 + 44);
  if ( v7 )
  {
    v8 = *a2;
    if ( v7 >= 4 )
    {
      v13 = *(_QWORD *)(a1 + 32);
      v14 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          v15 = (v14 + v7) / 2;
          v10 = v13 + 40 * v15;
          if ( v8 >= *(_DWORD *)v10 )
            break;
          if ( (_DWORD)v15 == v14 )
            goto LABEL_16;
          v7 = (v14 + v7) / 2;
        }
        if ( v8 <= *(_DWORD *)v10 )
          break;
        v14 = v15 + 1;
        if ( (_DWORD)v15 + 1 == v7 )
          goto LABEL_16;
      }
      if ( *(_QWORD *)a2 == *(_QWORD *)v10 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v10 + 8) )
      {
LABEL_11:
        if ( v10 != -16 )
        {
          if ( *(_WORD *)(v10 + 16) == 21 )
          {
            v11 = 0;
            *a3 = *(_QWORD *)(v10 + 24);
          }
          else
          {
            v11 = -1072875843;
          }
          goto LABEL_17;
        }
      }
      else
      {
        if ( (int)v15 > v14 )
        {
          for ( i = v15 - 1; i >= v14; --i )
          {
            v10 = v13 + 40LL * i;
            if ( v8 != *(_DWORD *)v10 )
              break;
            if ( *(_QWORD *)a2 == *(_QWORD *)v10 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v10 + 8) )
              goto LABEL_11;
          }
        }
        for ( j = v15 + 1; j < v7; ++j )
        {
          v10 = v13 + 40LL * j;
          if ( v8 != *(_DWORD *)v10 )
            break;
          if ( *(_QWORD *)a2 == *(_QWORD *)v10 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v10 + 8) )
            goto LABEL_11;
        }
      }
    }
    else if ( v7 > 0 )
    {
      for ( k = 0; k < v7; ++k )
      {
        v10 = *(_QWORD *)(a1 + 32) + 40LL * k;
        if ( *(_DWORD *)v10 == v8 )
        {
          if ( *(_QWORD *)a2 == *(_QWORD *)v10 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v10 + 8) )
            goto LABEL_11;
        }
        else if ( *(_DWORD *)v10 > v8 )
        {
          break;
        }
      }
    }
  }
LABEL_16:
  v11 = -1072875802;
LABEL_17:
  if ( *(_DWORD *)(v4 + 8) == GetCurrentThreadId() )
  {
    v12 = *(_DWORD *)(v4 + 12);
    if ( v12 )
    {
      *(_DWORD *)(v4 + 12) = v12 - 1;
    }
    else
    {
      *(_DWORD *)(v4 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v4);
    }
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v4);
  }
  return v11;
}

```

## disassembly

```asm
0x18005a450  push    rbx
0x18005a452  push    rbp
0x18005a453  push    rsi
0x18005a454  push    rdi
0x18005a455  push    r14
0x18005a457  sub     rsp, 20h
0x18005a45b  mov     r14, r8
0x18005a45e  lea     rbx, [rcx+10h]
0x18005a462  mov     rsi, rdx
0x18005a465  mov     rdi, rcx
0x18005a468  call    cs:__imp_GetCurrentThreadId
0x18005a46e  mov     r9d, [rbx+8]
0x18005a472  cmp     r9d, eax
0x18005a475  jnz     short loc_18005A47C
0x18005a477  inc     dword ptr [rbx+0Ch]
0x18005a47a  jmp     short loc_18005A485
0x18005a47c  mov     rcx, rbx; SRWLock
0x18005a47f  call    cs:__imp_AcquireSRWLockShared
0x18005a485  mov     r8d, [rdi+2Ch]
0x18005a489  test    r8d, r8d
0x18005a48c  jz      short loc_18005A4EF
0x18005a48e  mov     ebp, [rsi]
0x18005a490  cmp     r8d, 4
0x18005a494  jge     loc_18005A51A
0x18005a49a  test    r8d, r8d
0x18005a49d  jle     short loc_18005A4EF
0x18005a49f  mov     r10, [rdi+20h]
0x18005a4a3  xor     r9d, r9d
0x18005a4a6  movsxd  rax, r9d
0x18005a4a9  lea     rcx, [rax+rax*4]
0x18005a4ad  lea     rdx, [r10+rcx*8]
0x18005a4b1  cmp     [rdx], ebp
0x18005a4b3  jnz     short loc_18005A4E5
0x18005a4b5  mov     rax, [rsi]
0x18005a4b8  cmp     rax, [rdx]
0x18005a4bb  jnz     short loc_18005A4E7
0x18005a4bd  mov     rax, [rsi+8]
0x18005a4c1  cmp     rax, [rdx+8]
0x18005a4c5  jnz     short loc_18005A4E7
0x18005a4c7  lea     rax, [rdx+10h]
0x18005a4cb  test    rax, rax
0x18005a4ce  jz      short loc_18005A4EF
0x18005a4d0  cmp     word ptr [rax], 15h
0x18005a4d4  jnz     loc_18005A5DA
0x18005a4da  mov     rax, [rax+8]
0x18005a4de  xor     edi, edi
0x18005a4e0  mov     [r14], rax
0x18005a4e3  jmp     short loc_18005A4F4
0x18005a4e5  ja      short loc_18005A4EF
0x18005a4e7  inc     r9d
0x18005a4ea  cmp     r9d, r8d
0x18005a4ed  jl      short loc_18005A4A6
0x18005a4ef  mov     edi, 0C00D36E6h
0x18005a4f4  call    cs:__imp_GetCurrentThreadId
0x18005a4fa  mov     ecx, [rbx+8]
0x18005a4fd  cmp     ecx, eax
0x18005a4ff  jnz     loc_18005A5F6
0x18005a505  mov     eax, [rbx+0Ch]
0x18005a508  test    eax, eax
0x18005a50a  jz      loc_18005A5E4
0x18005a510  dec     eax
0x18005a512  mov     [rbx+0Ch], eax
0x18005a515  jmp     loc_18005A5FF
0x18005a51a  mov     rdi, [rdi+20h]
0x18005a51e  xor     r9d, r9d
0x18005a521  lea     eax, [r9+r8]
0x18005a525  cdq
0x18005a526  sub     eax, edx
0x18005a528  sar     eax, 1
0x18005a52a  movsxd  r10, eax
0x18005a52d  lea     rdx, [r10+r10*4]
0x18005a531  lea     rdx, [rdi+rdx*8]
0x18005a535  cmp     ebp, [rdx]
0x18005a537  jnb     short loc_18005A543
0x18005a539  cmp     r10d, r9d
0x18005a53c  jz      short loc_18005A4EF
0x18005a53e  mov     r8d, r10d
0x18005a541  jmp     short loc_18005A521
0x18005a543  jbe     short loc_18005A550
0x18005a545  lea     r9d, [r10+1]
0x18005a549  cmp     r9d, r8d
0x18005a54c  jnz     short loc_18005A521
0x18005a54e  jmp     short loc_18005A4EF
0x18005a550  mov     rax, [rsi]
0x18005a553  cmp     rax, [rdx]
0x18005a556  jnz     short loc_18005A566
0x18005a558  mov     rax, [rsi+8]
0x18005a55c  cmp     rax, [rdx+8]
0x18005a560  jz      loc_18005A4C7
0x18005a566  cmp     r10d, r9d
0x18005a569  jle     short loc_18005A59E
0x18005a56b  lea     r11d, [r10-1]
0x18005a56f  jmp     short loc_18005A599
0x18005a571  movsxd  rax, r11d
0x18005a574  lea     rcx, [rax+rax*4]
0x18005a578  lea     rdx, [rdi+rcx*8]
0x18005a57c  cmp     ebp, [rdx]
0x18005a57e  jnz     short loc_18005A59E
0x18005a580  mov     rax, [rsi]
0x18005a583  cmp     rax, [rdx]
0x18005a586  jnz     short loc_18005A596
0x18005a588  mov     rax, [rsi+8]
0x18005a58c  cmp     rax, [rdx+8]
0x18005a590  jz      loc_18005A4C7
0x18005a596  dec     r11d
0x18005a599  cmp     r11d, r9d
0x18005a59c  jge     short loc_18005A571
0x18005a59e  lea     r9d, [r10+1]
0x18005a5a2  jmp     short loc_18005A5D0
0x18005a5a4  movsxd  rax, r9d
0x18005a5a7  lea     rcx, [rax+rax*4]
0x18005a5ab  lea     rdx, [rdi+rcx*8]
0x18005a5af  cmp     ebp, [rdx]
0x18005a5b1  jnz     loc_18005A4EF
0x18005a5b7  mov     rax, [rsi]
0x18005a5ba  cmp     rax, [rdx]
0x18005a5bd  jnz     short loc_18005A5CD
0x18005a5bf  mov     rax, [rsi+8]
0x18005a5c3  cmp     rax, [rdx+8]
0x18005a5c7  jz      loc_18005A4C7
0x18005a5cd  inc     r9d
0x18005a5d0  cmp     r9d, r8d
0x18005a5d3  jl      short loc_18005A5A4
0x18005a5d5  jmp     loc_18005A4EF
0x18005a5da  mov     edi, 0C00D36BDh
0x18005a5df  jmp     loc_18005A4F4
0x18005a5e4  mov     rcx, rbx; SRWLock
0x18005a5e7  mov     dword ptr [rbx+8], 0
0x18005a5ee  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a5f4  jmp     short loc_18005A5FF
0x18005a5f6  mov     rcx, rbx; SRWLock
0x18005a5f9  call    cs:__imp_ReleaseSRWLockShared
0x18005a5ff  mov     eax, edi
0x18005a601  add     rsp, 20h
0x18005a605  pop     r14
0x18005a607  pop     rdi
0x18005a608  pop     rsi
0x18005a609  pop     rbp
0x18005a60a  pop     rbx
0x18005a60b  retn
```
