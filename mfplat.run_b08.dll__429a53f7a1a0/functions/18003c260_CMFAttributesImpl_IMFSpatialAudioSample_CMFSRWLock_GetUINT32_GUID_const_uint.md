# CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetUINT32(_GUID const &,uint *)

- ea: `0x18003c260`
- end: `0x18003c474`
- name: `?GetUINT32@?$CMFAttributesImpl@UIMFSpatialAudioSample@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAI@Z`
- size: `532`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003c260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003c298`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003c298`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c44b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c44b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003c461`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003c461`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c281`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c31f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c281`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c31f`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetUINT32(
        __int64 a1,
        unsigned int *a2,
        _DWORD *a3)
{
  __int64 v3; // rbp
  int v7; // r9d
  unsigned int v8; // edi
  __int64 v9; // r10
  int k; // r8d
  __int64 v11; // rdx
  unsigned int v12; // ebx
  int v13; // ecx
  __int64 result; // rax
  __int64 v15; // rsi
  int v16; // r8d
  int v17; // eax
  int i; // r11d
  int j; // r8d

  v3 = a1 + 8;
  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
    ++*(_DWORD *)(v3 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v3);
  v7 = *(_DWORD *)(a1 + 36);
  if ( v7 )
  {
    v8 = *a2;
    if ( v7 >= 4 )
    {
      v15 = *(_QWORD *)(a1 + 24);
      v16 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          v17 = (v16 + v7) / 2;
          v11 = v15 + 40LL * v17;
          if ( v8 >= *(_DWORD *)v11 )
            break;
          if ( v17 == v16 )
            goto LABEL_16;
          v7 = (v16 + v7) / 2;
        }
        if ( v8 <= *(_DWORD *)(v15 + 40LL * v17) )
          break;
        v16 = v17 + 1;
        if ( v17 + 1 == v7 )
          goto LABEL_16;
      }
      if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
      {
LABEL_11:
        if ( v11 != -16 )
        {
          if ( *(_WORD *)(v11 + 16) == 19 )
          {
            v12 = 0;
            *a3 = *(_DWORD *)(v11 + 24);
          }
          else
          {
            v12 = -1072875843;
          }
          goto LABEL_17;
        }
      }
      else
      {
        if ( v17 > v16 )
        {
          for ( i = v17 - 1; i >= v16; --i )
          {
            v11 = v15 + 40LL * i;
            if ( v8 != *(_DWORD *)v11 )
              break;
            if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
              goto LABEL_11;
          }
        }
        for ( j = v17 + 1; j < v7; ++j )
        {
          v11 = v15 + 40LL * j;
          if ( v8 != *(_DWORD *)v11 )
            break;
          if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
            goto LABEL_11;
        }
      }
    }
    else if ( v7 > 0 )
    {
      v9 = *(_QWORD *)(a1 + 24);
      for ( k = 0; k < v7; ++k )
      {
        v11 = v9 + 40LL * k;
        if ( *(_DWORD *)v11 == v8 )
        {
          if ( *(_QWORD *)a2 == *(_QWORD *)v11 && *((_QWORD *)a2 + 1) == *(_QWORD *)(v11 + 8) )
            goto LABEL_11;
        }
        else if ( *(_DWORD *)(v9 + 40LL * k) > v8 )
        {
          break;
        }
      }
    }
  }
LABEL_16:
  v12 = -1072875802;
LABEL_17:
  if ( *(_DWORD *)(v3 + 8) == GetCurrentThreadId() )
  {
    v13 = *(_DWORD *)(v3 + 12);
    if ( v13 )
    {
      result = v12;
      *(_DWORD *)(v3 + 12) = v13 - 1;
    }
    else
    {
      *(_DWORD *)(v3 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v3);
      return v12;
    }
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v3);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18003c260  mov     [rsp+arg_18], rbx
0x18003c265  push    rbp
0x18003c266  sub     rsp, 20h
0x18003c26a  mov     [rsp+28h+arg_0], rsi
0x18003c26f  lea     rbp, [rcx+8]
0x18003c273  mov     [rsp+28h+arg_10], r14
0x18003c278  mov     rbx, rdx
0x18003c27b  mov     r14, r8
0x18003c27e  mov     rsi, rcx
0x18003c281  call    cs:__imp_GetCurrentThreadId
0x18003c287  mov     r9d, [rbp+8]
0x18003c28b  cmp     r9d, eax
0x18003c28e  jnz     short loc_18003C295
0x18003c290  inc     dword ptr [rbp+0Ch]
0x18003c293  jmp     short loc_18003C29E
0x18003c295  mov     rcx, rbp; SRWLock
0x18003c298  call    cs:__imp_AcquireSRWLockShared
0x18003c29e  mov     r9d, [rsi+24h]
0x18003c2a2  mov     [rsp+28h+arg_8], rdi
0x18003c2a7  test    r9d, r9d
0x18003c2aa  jz      short loc_18003C31A
0x18003c2ac  mov     edi, [rbx]
0x18003c2ae  cmp     r9d, 4
0x18003c2b2  jge     loc_18003C35C
0x18003c2b8  test    r9d, r9d
0x18003c2bb  jle     short loc_18003C31A
0x18003c2bd  mov     r10, [rsi+18h]
0x18003c2c1  xor     r8d, r8d
0x18003c2c4  nop     dword ptr [rax+00h]
0x18003c2c8  nop     dword ptr [rax+rax+00000000h]
0x18003c2d0  movsxd  rax, r8d
0x18003c2d3  lea     rcx, [rax+rax*4]
0x18003c2d7  cmp     [r10+rcx*8], edi
0x18003c2db  lea     rdx, [r10+rcx*8]
0x18003c2df  jnz     short loc_18003C310
0x18003c2e1  mov     rax, [rbx]
0x18003c2e4  cmp     rax, [rdx]
0x18003c2e7  jnz     short loc_18003C312
0x18003c2e9  mov     rax, [rbx+8]
0x18003c2ed  cmp     rax, [rdx+8]
0x18003c2f1  jnz     short loc_18003C312
0x18003c2f3  lea     rax, [rdx+10h]
0x18003c2f7  test    rax, rax
0x18003c2fa  jz      short loc_18003C31A
0x18003c2fc  cmp     word ptr [rax], 13h
0x18003c300  jnz     loc_18003C437
0x18003c306  mov     eax, [rax+8]
0x18003c309  xor     ebx, ebx
0x18003c30b  mov     [r14], eax
0x18003c30e  jmp     short loc_18003C31F
0x18003c310  ja      short loc_18003C31A
0x18003c312  inc     r8d
0x18003c315  cmp     r8d, r9d
0x18003c318  jl      short loc_18003C2D0
0x18003c31a  mov     ebx, 0C00D36E6h
0x18003c31f  call    cs:__imp_GetCurrentThreadId
0x18003c325  mov     ecx, [rbp+8]
0x18003c328  mov     r14, [rsp+28h+arg_10]
0x18003c32d  mov     rdi, [rsp+28h+arg_8]
0x18003c332  mov     rsi, [rsp+28h+arg_0]
0x18003c337  cmp     ecx, eax
0x18003c339  jnz     loc_18003C45E
0x18003c33f  mov     ecx, [rbp+0Ch]
0x18003c342  test    ecx, ecx
0x18003c344  jz      loc_18003C441
0x18003c34a  dec     ecx
0x18003c34c  mov     eax, ebx
0x18003c34e  mov     [rbp+0Ch], ecx
0x18003c351  mov     rbx, [rsp+28h+arg_18]
0x18003c356  add     rsp, 20h
0x18003c35a  pop     rbp
0x18003c35b  retn
0x18003c35c  mov     rsi, [rsi+18h]
0x18003c360  xor     r8d, r8d
0x18003c363  lea     eax, [r8+r9]
0x18003c367  cdq
0x18003c368  sub     eax, edx
0x18003c36a  sar     eax, 1
0x18003c36c  movsxd  r10, eax
0x18003c36f  lea     rdx, [r10+r10*4]
0x18003c373  cmp     edi, [rsi+rdx*8]
0x18003c376  lea     rdx, [rsi+rdx*8]
0x18003c37a  jnb     short loc_18003C386
0x18003c37c  cmp     r10d, r8d
0x18003c37f  jz      short loc_18003C31A
0x18003c381  mov     r9d, r10d
0x18003c384  jmp     short loc_18003C363
0x18003c386  jbe     short loc_18003C393
0x18003c388  lea     r8d, [r10+1]
0x18003c38c  cmp     r8d, r9d
0x18003c38f  jnz     short loc_18003C363
0x18003c391  jmp     short loc_18003C31A
0x18003c393  mov     rax, [rbx]
0x18003c396  cmp     rax, [rdx]
0x18003c399  jnz     short loc_18003C3A9
0x18003c39b  mov     rax, [rbx+8]
0x18003c39f  cmp     rax, [rdx+8]
0x18003c3a3  jz      loc_18003C2F3
0x18003c3a9  cmp     r10d, r8d
0x18003c3ac  jle     short loc_18003C3EE
0x18003c3ae  lea     r11d, [r10-1]
0x18003c3b2  cmp     r11d, r8d
0x18003c3b5  jl      short loc_18003C3EE
0x18003c3b7  nop     word ptr [rax+rax+00000000h]
0x18003c3c0  movsxd  rax, r11d
0x18003c3c3  lea     rcx, [rax+rax*4]
0x18003c3c7  cmp     edi, [rsi+rcx*8]
0x18003c3ca  lea     rdx, [rsi+rcx*8]
0x18003c3ce  jnz     short loc_18003C3EE
0x18003c3d0  mov     rax, [rbx]
0x18003c3d3  cmp     rax, [rdx]
0x18003c3d6  jnz     short loc_18003C3E6
0x18003c3d8  mov     rax, [rbx+8]
0x18003c3dc  cmp     rax, [rdx+8]
0x18003c3e0  jz      loc_18003C2F3
0x18003c3e6  dec     r11d
0x18003c3e9  cmp     r11d, r8d
0x18003c3ec  jge     short loc_18003C3C0
0x18003c3ee  lea     r8d, [r10+1]
0x18003c3f2  cmp     r8d, r9d
0x18003c3f5  jge     loc_18003C31A
0x18003c3fb  nop     dword ptr [rax+rax+00h]
0x18003c400  movsxd  rax, r8d
0x18003c403  lea     rcx, [rax+rax*4]
0x18003c407  cmp     edi, [rsi+rcx*8]
0x18003c40a  lea     rdx, [rsi+rcx*8]
0x18003c40e  jnz     loc_18003C31A
0x18003c414  mov     rax, [rbx]
0x18003c417  cmp     rax, [rdx]
0x18003c41a  jnz     short loc_18003C42A
0x18003c41c  mov     rax, [rbx+8]
0x18003c420  cmp     rax, [rdx+8]
0x18003c424  jz      loc_18003C2F3
0x18003c42a  inc     r8d
0x18003c42d  cmp     r8d, r9d
0x18003c430  jl      short loc_18003C400
0x18003c432  jmp     loc_18003C31A
0x18003c437  mov     ebx, 0C00D36BDh
0x18003c43c  jmp     loc_18003C31F
0x18003c441  mov     rcx, rbp; SRWLock
0x18003c444  mov     dword ptr [rbp+8], 0
0x18003c44b  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c451  mov     eax, ebx
0x18003c453  mov     rbx, [rsp+28h+arg_18]
0x18003c458  add     rsp, 20h
0x18003c45c  pop     rbp
0x18003c45d  retn
0x18003c45e  mov     rcx, rbp; SRWLock
0x18003c461  call    cs:__imp_ReleaseSRWLockShared
0x18003c467  mov     eax, ebx
0x18003c469  mov     rbx, [rsp+28h+arg_18]
0x18003c46e  add     rsp, 20h
0x18003c472  pop     rbp
0x18003c473  retn
```
