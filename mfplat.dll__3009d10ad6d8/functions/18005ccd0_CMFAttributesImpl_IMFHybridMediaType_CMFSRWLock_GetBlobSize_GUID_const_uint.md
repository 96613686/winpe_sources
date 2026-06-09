# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetBlobSize(_GUID const &,uint *)

- ea: `0x18005ccd0`
- end: `0x18005ce8f`
- name: `?GetBlobSize@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAI@Z`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180149170`

## callees

- `0x18005ccd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005ccff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005ccff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ce71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ce71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ce7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ce7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cce8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cd77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cce8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cd77`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::GetBlobSize(
        __int64 a1,
        unsigned int *a2,
        _DWORD *a3)
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
          if ( *(_WORD *)(v10 + 16) == 4113 )
          {
            v11 = 0;
            *a3 = *(_DWORD *)(v10 + 24);
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
0x18005ccd0  push    rbx
0x18005ccd2  push    rbp
0x18005ccd3  push    rsi
0x18005ccd4  push    rdi
0x18005ccd5  push    r14
0x18005ccd7  sub     rsp, 20h
0x18005ccdb  mov     r14, r8
0x18005ccde  lea     rbx, [rcx+10h]
0x18005cce2  mov     rsi, rdx
0x18005cce5  mov     rdi, rcx
0x18005cce8  call    cs:__imp_GetCurrentThreadId
0x18005ccee  mov     r9d, [rbx+8]
0x18005ccf2  cmp     r9d, eax
0x18005ccf5  jnz     short loc_18005CCFC
0x18005ccf7  inc     dword ptr [rbx+0Ch]
0x18005ccfa  jmp     short loc_18005CD05
0x18005ccfc  mov     rcx, rbx; SRWLock
0x18005ccff  call    cs:__imp_AcquireSRWLockShared
0x18005cd05  mov     r8d, [rdi+2Ch]
0x18005cd09  test    r8d, r8d
0x18005cd0c  jz      short loc_18005CD72
0x18005cd0e  mov     ebp, [rsi]
0x18005cd10  cmp     r8d, 4
0x18005cd14  jge     loc_18005CD9D
0x18005cd1a  test    r8d, r8d
0x18005cd1d  jle     short loc_18005CD72
0x18005cd1f  mov     r10, [rdi+20h]
0x18005cd23  xor     r9d, r9d
0x18005cd26  movsxd  rax, r9d
0x18005cd29  lea     rcx, [rax+rax*4]
0x18005cd2d  lea     rdx, [r10+rcx*8]
0x18005cd31  cmp     [rdx], ebp
0x18005cd33  jnz     short loc_18005CD68
0x18005cd35  mov     rax, [rsi]
0x18005cd38  cmp     rax, [rdx]
0x18005cd3b  jnz     short loc_18005CD6A
0x18005cd3d  mov     rax, [rsi+8]
0x18005cd41  cmp     rax, [rdx+8]
0x18005cd45  jnz     short loc_18005CD6A
0x18005cd47  lea     rax, [rdx+10h]
0x18005cd4b  test    rax, rax
0x18005cd4e  jz      short loc_18005CD72
0x18005cd50  mov     ecx, 1011h
0x18005cd55  cmp     [rax], cx
0x18005cd58  jnz     loc_18005CE5D
0x18005cd5e  mov     eax, [rax+8]
0x18005cd61  xor     edi, edi
0x18005cd63  mov     [r14], eax
0x18005cd66  jmp     short loc_18005CD77
0x18005cd68  ja      short loc_18005CD72
0x18005cd6a  inc     r9d
0x18005cd6d  cmp     r9d, r8d
0x18005cd70  jl      short loc_18005CD26
0x18005cd72  mov     edi, 0C00D36E6h
0x18005cd77  call    cs:__imp_GetCurrentThreadId
0x18005cd7d  mov     ecx, [rbx+8]
0x18005cd80  cmp     ecx, eax
0x18005cd82  jnz     loc_18005CE79
0x18005cd88  mov     eax, [rbx+0Ch]
0x18005cd8b  test    eax, eax
0x18005cd8d  jz      loc_18005CE67
0x18005cd93  dec     eax
0x18005cd95  mov     [rbx+0Ch], eax
0x18005cd98  jmp     loc_18005CE82
0x18005cd9d  mov     rdi, [rdi+20h]
0x18005cda1  xor     r9d, r9d
0x18005cda4  lea     eax, [r9+r8]
0x18005cda8  cdq
0x18005cda9  sub     eax, edx
0x18005cdab  sar     eax, 1
0x18005cdad  movsxd  r10, eax
0x18005cdb0  lea     rdx, [r10+r10*4]
0x18005cdb4  lea     rdx, [rdi+rdx*8]
0x18005cdb8  cmp     ebp, [rdx]
0x18005cdba  jnb     short loc_18005CDC6
0x18005cdbc  cmp     r10d, r9d
0x18005cdbf  jz      short loc_18005CD72
0x18005cdc1  mov     r8d, r10d
0x18005cdc4  jmp     short loc_18005CDA4
0x18005cdc6  jbe     short loc_18005CDD3
0x18005cdc8  lea     r9d, [r10+1]
0x18005cdcc  cmp     r9d, r8d
0x18005cdcf  jnz     short loc_18005CDA4
0x18005cdd1  jmp     short loc_18005CD72
0x18005cdd3  mov     rax, [rsi]
0x18005cdd6  cmp     rax, [rdx]
0x18005cdd9  jnz     short loc_18005CDE9
0x18005cddb  mov     rax, [rsi+8]
0x18005cddf  cmp     rax, [rdx+8]
0x18005cde3  jz      loc_18005CD47
0x18005cde9  cmp     r10d, r9d
0x18005cdec  jle     short loc_18005CE21
0x18005cdee  lea     r11d, [r10-1]
0x18005cdf2  jmp     short loc_18005CE1C
0x18005cdf4  movsxd  rax, r11d
0x18005cdf7  lea     rcx, [rax+rax*4]
0x18005cdfb  lea     rdx, [rdi+rcx*8]
0x18005cdff  cmp     ebp, [rdx]
0x18005ce01  jnz     short loc_18005CE21
0x18005ce03  mov     rax, [rsi]
0x18005ce06  cmp     rax, [rdx]
0x18005ce09  jnz     short loc_18005CE19
0x18005ce0b  mov     rax, [rsi+8]
0x18005ce0f  cmp     rax, [rdx+8]
0x18005ce13  jz      loc_18005CD47
0x18005ce19  dec     r11d
0x18005ce1c  cmp     r11d, r9d
0x18005ce1f  jge     short loc_18005CDF4
0x18005ce21  lea     r9d, [r10+1]
0x18005ce25  jmp     short loc_18005CE53
0x18005ce27  movsxd  rax, r9d
0x18005ce2a  lea     rcx, [rax+rax*4]
0x18005ce2e  lea     rdx, [rdi+rcx*8]
0x18005ce32  cmp     ebp, [rdx]
0x18005ce34  jnz     loc_18005CD72
0x18005ce3a  mov     rax, [rsi]
0x18005ce3d  cmp     rax, [rdx]
0x18005ce40  jnz     short loc_18005CE50
0x18005ce42  mov     rax, [rsi+8]
0x18005ce46  cmp     rax, [rdx+8]
0x18005ce4a  jz      loc_18005CD47
0x18005ce50  inc     r9d
0x18005ce53  cmp     r9d, r8d
0x18005ce56  jl      short loc_18005CE27
0x18005ce58  jmp     loc_18005CD72
0x18005ce5d  mov     edi, 0C00D36BDh
0x18005ce62  jmp     loc_18005CD77
0x18005ce67  mov     rcx, rbx; SRWLock
0x18005ce6a  mov     dword ptr [rbx+8], 0
0x18005ce71  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ce77  jmp     short loc_18005CE82
0x18005ce79  mov     rcx, rbx; SRWLock
0x18005ce7c  call    cs:__imp_ReleaseSRWLockShared
0x18005ce82  mov     eax, edi
0x18005ce84  add     rsp, 20h
0x18005ce88  pop     r14
0x18005ce8a  pop     rdi
0x18005ce8b  pop     rsi
0x18005ce8c  pop     rbp
0x18005ce8d  pop     rbx
0x18005ce8e  retn
```
