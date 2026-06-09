# CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetUnknown(_GUID const &,_GUID const &,void * *)

- ea: `0x180053df0`
- end: `0x18005401c`
- name: `?GetUnknown@?$CMFAttributesImpl@UIMFSpatialAudioSample@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180053df0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180053e34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180053e34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053ffb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053ffb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005400d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005400d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053e1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053ec4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053e1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053ec4`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetUnknown(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v4; // rbp
  int v9; // r10d
  unsigned int v10; // edi
  __int64 v11; // r9
  int k; // r8d
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 (__fastcall ***v15)(_QWORD, __int64, _QWORD *); // rcx
  unsigned int v16; // ebx
  int v17; // eax
  __int64 v19; // rsi
  int v20; // r8d
  int v21; // eax
  int i; // r11d
  int j; // r8d

  v4 = a1 + 8;
  *a4 = 0;
  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
    ++*(_DWORD *)(v4 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v4);
  v9 = *(_DWORD *)(a1 + 36);
  if ( v9 )
  {
    v10 = *a2;
    if ( v9 >= 4 )
    {
      v19 = *(_QWORD *)(a1 + 24);
      v20 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          v21 = (v20 + v9) / 2;
          v13 = v19 + 40LL * v21;
          if ( v10 >= *(_DWORD *)v13 )
            break;
          if ( v21 == v20 )
            goto LABEL_17;
          v9 = (v20 + v9) / 2;
        }
        if ( v10 <= *(_DWORD *)(v19 + 40LL * v21) )
          break;
        v20 = v21 + 1;
        if ( v21 + 1 == v9 )
          goto LABEL_17;
      }
      if ( *(_QWORD *)a2 == *(_QWORD *)v13 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v13 + 8) )
      {
LABEL_11:
        v14 = v13 + 16;
        if ( v14 )
        {
          if ( *(_WORD *)v14 == 13 && (v15 = *(__int64 (__fastcall ****)(_QWORD, __int64, _QWORD *))(v14 + 8)) != 0 )
            v16 = (**v15)(v15, a3, a4);
          else
            v16 = -1072875843;
          goto LABEL_18;
        }
      }
      else
      {
        if ( v21 > v20 )
        {
          for ( i = v21 - 1; i >= v20; --i )
          {
            v13 = v19 + 40LL * i;
            if ( v10 != *(_DWORD *)v13 )
              break;
            if ( *(_QWORD *)a2 == *(_QWORD *)v13 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v13 + 8) )
              goto LABEL_11;
          }
        }
        for ( j = v21 + 1; j < v9; ++j )
        {
          v13 = v19 + 40LL * j;
          if ( v10 != *(_DWORD *)v13 )
            break;
          if ( *(_QWORD *)a2 == *(_QWORD *)v13 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v13 + 8) )
            goto LABEL_11;
        }
      }
    }
    else if ( v9 > 0 )
    {
      v11 = *(_QWORD *)(a1 + 24);
      for ( k = 0; k < v9; ++k )
      {
        v13 = v11 + 40LL * k;
        if ( *(_DWORD *)v13 == v10 )
        {
          if ( *(_QWORD *)a2 == *(_QWORD *)v13 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v13 + 8) )
            goto LABEL_11;
        }
        else if ( *(_DWORD *)(v11 + 40LL * k) > v10 )
        {
          break;
        }
      }
    }
  }
LABEL_17:
  v16 = -1072875802;
LABEL_18:
  if ( *(_DWORD *)(v4 + 8) == GetCurrentThreadId() )
  {
    v17 = *(_DWORD *)(v4 + 12);
    if ( v17 )
    {
      *(_DWORD *)(v4 + 12) = v17 - 1;
    }
    else
    {
      *(_DWORD *)(v4 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v4);
    }
    return v16;
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v4);
    return v16;
  }
}

```

## disassembly

```asm
0x180053df0  push    rbx
0x180053df2  push    rbp
0x180053df3  sub     rsp, 28h
0x180053df7  mov     [rsp+38h+arg_0], rsi
0x180053dfc  lea     rbp, [rcx+8]
0x180053e00  mov     [rsp+38h+arg_10], r14
0x180053e05  mov     rbx, rdx
0x180053e08  mov     [rsp+38h+var_18], r15
0x180053e0d  mov     r14, r9
0x180053e10  mov     r15, r8
0x180053e13  mov     qword ptr [r9], 0
0x180053e1a  mov     rsi, rcx
0x180053e1d  call    cs:__imp_GetCurrentThreadId
0x180053e23  mov     r10d, [rbp+8]
0x180053e27  cmp     r10d, eax
0x180053e2a  jnz     short loc_180053E31
0x180053e2c  inc     dword ptr [rbp+0Ch]
0x180053e2f  jmp     short loc_180053E3A
0x180053e31  mov     rcx, rbp; SRWLock
0x180053e34  call    cs:__imp_AcquireSRWLockShared
0x180053e3a  mov     r10d, [rsi+24h]
0x180053e3e  mov     [rsp+38h+arg_8], rdi
0x180053e43  test    r10d, r10d
0x180053e46  jz      short loc_180053EBF
0x180053e48  mov     edi, [rbx]
0x180053e4a  cmp     r10d, 4
0x180053e4e  jge     loc_180053F02
0x180053e54  test    r10d, r10d
0x180053e57  jle     short loc_180053EBF
0x180053e59  mov     r9, [rsi+18h]
0x180053e5d  xor     r8d, r8d
0x180053e60  movsxd  rax, r8d
0x180053e63  lea     rcx, [rax+rax*4]
0x180053e67  cmp     [r9+rcx*8], edi
0x180053e6b  lea     rdx, [r9+rcx*8]
0x180053e6f  jnz     short loc_180053EB5
0x180053e71  mov     rax, [rbx]
0x180053e74  cmp     rax, [rdx]
0x180053e77  jnz     short loc_180053EB7
0x180053e79  mov     rax, [rbx+8]
0x180053e7d  cmp     rax, [rdx+8]
0x180053e81  jnz     short loc_180053EB7
0x180053e83  add     rdx, 10h
0x180053e87  jz      short loc_180053EBF
0x180053e89  cmp     word ptr [rdx], 0Dh
0x180053e8d  jnz     loc_180053FE7
0x180053e93  mov     rcx, [rdx+8]
0x180053e97  test    rcx, rcx
0x180053e9a  jz      loc_180053FE7
0x180053ea0  mov     rax, [rcx]
0x180053ea3  mov     r8, r14
0x180053ea6  mov     rdx, r15
0x180053ea9  mov     rax, [rax]
0x180053eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053eb1  mov     ebx, eax
0x180053eb3  jmp     short loc_180053EC4
0x180053eb5  ja      short loc_180053EBF
0x180053eb7  inc     r8d
0x180053eba  cmp     r8d, r10d
0x180053ebd  jl      short loc_180053E60
0x180053ebf  mov     ebx, 0C00D36E6h
0x180053ec4  call    cs:__imp_GetCurrentThreadId
0x180053eca  mov     ecx, [rbp+8]
0x180053ecd  mov     r15, [rsp+38h+var_18]
0x180053ed2  mov     r14, [rsp+38h+arg_10]
0x180053ed7  mov     rdi, [rsp+38h+arg_8]
0x180053edc  mov     rsi, [rsp+38h+arg_0]
0x180053ee1  cmp     ecx, eax
0x180053ee3  jnz     loc_18005400A
0x180053ee9  mov     eax, [rbp+0Ch]
0x180053eec  test    eax, eax
0x180053eee  jz      loc_180053FF1
0x180053ef4  dec     eax
0x180053ef6  mov     [rbp+0Ch], eax
0x180053ef9  mov     eax, ebx
0x180053efb  add     rsp, 28h
0x180053eff  pop     rbp
0x180053f00  pop     rbx
0x180053f01  retn
0x180053f02  mov     rsi, [rsi+18h]
0x180053f06  xor     r8d, r8d
0x180053f09  nop     dword ptr [rax+00000000h]
0x180053f10  lea     eax, [r8+r10]
0x180053f14  cdq
0x180053f15  sub     eax, edx
0x180053f17  sar     eax, 1
0x180053f19  movsxd  r9, eax
0x180053f1c  lea     rdx, [r9+r9*4]
0x180053f20  cmp     edi, [rsi+rdx*8]
0x180053f23  lea     rdx, [rsi+rdx*8]
0x180053f27  jnb     short loc_180053F33
0x180053f29  cmp     r9d, r8d
0x180053f2c  jz      short loc_180053EBF
0x180053f2e  mov     r10d, r9d
0x180053f31  jmp     short loc_180053F10
0x180053f33  jbe     short loc_180053F43
0x180053f35  lea     r8d, [r9+1]
0x180053f39  cmp     r8d, r10d
0x180053f3c  jnz     short loc_180053F10
0x180053f3e  jmp     loc_180053EBF
0x180053f43  mov     rax, [rbx]
0x180053f46  cmp     rax, [rdx]
0x180053f49  jnz     short loc_180053F59
0x180053f4b  mov     rax, [rbx+8]
0x180053f4f  cmp     rax, [rdx+8]
0x180053f53  jz      loc_180053E83
0x180053f59  cmp     r9d, r8d
0x180053f5c  jle     short loc_180053F9E
0x180053f5e  lea     r11d, [r9-1]
0x180053f62  cmp     r11d, r8d
0x180053f65  jl      short loc_180053F9E
0x180053f67  nop     word ptr [rax+rax+00000000h]
0x180053f70  movsxd  rax, r11d
0x180053f73  lea     rcx, [rax+rax*4]
0x180053f77  cmp     edi, [rsi+rcx*8]
0x180053f7a  lea     rdx, [rsi+rcx*8]
0x180053f7e  jnz     short loc_180053F9E
0x180053f80  mov     rax, [rbx]
0x180053f83  cmp     rax, [rdx]
0x180053f86  jnz     short loc_180053F96
0x180053f88  mov     rax, [rbx+8]
0x180053f8c  cmp     rax, [rdx+8]
0x180053f90  jz      loc_180053E83
0x180053f96  dec     r11d
0x180053f99  cmp     r11d, r8d
0x180053f9c  jge     short loc_180053F70
0x180053f9e  lea     r8d, [r9+1]
0x180053fa2  cmp     r8d, r10d
0x180053fa5  jge     loc_180053EBF
0x180053fab  nop     dword ptr [rax+rax+00h]
0x180053fb0  movsxd  rax, r8d
0x180053fb3  lea     rcx, [rax+rax*4]
0x180053fb7  cmp     edi, [rsi+rcx*8]
0x180053fba  lea     rdx, [rsi+rcx*8]
0x180053fbe  jnz     loc_180053EBF
0x180053fc4  mov     rax, [rbx]
0x180053fc7  cmp     rax, [rdx]
0x180053fca  jnz     short loc_180053FDA
0x180053fcc  mov     rax, [rbx+8]
0x180053fd0  cmp     rax, [rdx+8]
0x180053fd4  jz      loc_180053E83
0x180053fda  inc     r8d
0x180053fdd  cmp     r8d, r10d
0x180053fe0  jl      short loc_180053FB0
0x180053fe2  jmp     loc_180053EBF
0x180053fe7  mov     ebx, 0C00D36BDh
0x180053fec  jmp     loc_180053EC4
0x180053ff1  mov     rcx, rbp; SRWLock
0x180053ff4  mov     dword ptr [rbp+8], 0
0x180053ffb  call    cs:__imp_ReleaseSRWLockExclusive
0x180054001  mov     eax, ebx
0x180054003  add     rsp, 28h
0x180054007  pop     rbp
0x180054008  pop     rbx
0x180054009  retn
0x18005400a  mov     rcx, rbp; SRWLock
0x18005400d  call    cs:__imp_ReleaseSRWLockShared
0x180054013  mov     eax, ebx
0x180054015  add     rsp, 28h
0x180054019  pop     rbp
0x18005401a  pop     rbx
0x18005401b  retn
```
