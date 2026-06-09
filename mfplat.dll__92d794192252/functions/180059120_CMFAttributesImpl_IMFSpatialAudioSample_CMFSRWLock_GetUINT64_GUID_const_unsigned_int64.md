# CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetUINT64(_GUID const &,unsigned __int64 *)

- ea: `0x180059120`
- end: `0x1800592dc`
- name: `?GetUINT64@?$CMFAttributesImpl@UIMFSpatialAudioSample@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEA_K@Z`
- size: `444`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180059120`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005914f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005914f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800592be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800592be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800592c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800592c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059138`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800591c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059138`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800591c4`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetUINT64(
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

  v4 = a1 + 8;
  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
    ++*(_DWORD *)(v4 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v4);
  v7 = *(_DWORD *)(a1 + 36);
  if ( v7 )
  {
    v8 = *a2;
    if ( v7 >= 4 )
    {
      v13 = *(_QWORD *)(a1 + 24);
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
        v10 = *(_QWORD *)(a1 + 24) + 40LL * k;
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
0x180059120  push    rbx
0x180059122  push    rbp
0x180059123  push    rsi
0x180059124  push    rdi
0x180059125  push    r14
0x180059127  sub     rsp, 20h
0x18005912b  mov     r14, r8
0x18005912e  lea     rbx, [rcx+8]
0x180059132  mov     rsi, rdx
0x180059135  mov     rdi, rcx
0x180059138  call    cs:__imp_GetCurrentThreadId
0x18005913e  mov     r9d, [rbx+8]
0x180059142  cmp     r9d, eax
0x180059145  jnz     short loc_18005914C
0x180059147  inc     dword ptr [rbx+0Ch]
0x18005914a  jmp     short loc_180059155
0x18005914c  mov     rcx, rbx; SRWLock
0x18005914f  call    cs:__imp_AcquireSRWLockShared
0x180059155  mov     r8d, [rdi+24h]
0x180059159  test    r8d, r8d
0x18005915c  jz      short loc_1800591BF
0x18005915e  mov     ebp, [rsi]
0x180059160  cmp     r8d, 4
0x180059164  jge     loc_1800591EA
0x18005916a  test    r8d, r8d
0x18005916d  jle     short loc_1800591BF
0x18005916f  mov     r10, [rdi+18h]
0x180059173  xor     r9d, r9d
0x180059176  movsxd  rax, r9d
0x180059179  lea     rcx, [rax+rax*4]
0x18005917d  lea     rdx, [r10+rcx*8]
0x180059181  cmp     [rdx], ebp
0x180059183  jnz     short loc_1800591B5
0x180059185  mov     rax, [rsi]
0x180059188  cmp     rax, [rdx]
0x18005918b  jnz     short loc_1800591B7
0x18005918d  mov     rax, [rsi+8]
0x180059191  cmp     rax, [rdx+8]
0x180059195  jnz     short loc_1800591B7
0x180059197  lea     rax, [rdx+10h]
0x18005919b  test    rax, rax
0x18005919e  jz      short loc_1800591BF
0x1800591a0  cmp     word ptr [rax], 15h
0x1800591a4  jnz     loc_1800592AA
0x1800591aa  mov     rax, [rax+8]
0x1800591ae  xor     edi, edi
0x1800591b0  mov     [r14], rax
0x1800591b3  jmp     short loc_1800591C4
0x1800591b5  ja      short loc_1800591BF
0x1800591b7  inc     r9d
0x1800591ba  cmp     r9d, r8d
0x1800591bd  jl      short loc_180059176
0x1800591bf  mov     edi, 0C00D36E6h
0x1800591c4  call    cs:__imp_GetCurrentThreadId
0x1800591ca  mov     ecx, [rbx+8]
0x1800591cd  cmp     ecx, eax
0x1800591cf  jnz     loc_1800592C6
0x1800591d5  mov     eax, [rbx+0Ch]
0x1800591d8  test    eax, eax
0x1800591da  jz      loc_1800592B4
0x1800591e0  dec     eax
0x1800591e2  mov     [rbx+0Ch], eax
0x1800591e5  jmp     loc_1800592CF
0x1800591ea  mov     rdi, [rdi+18h]
0x1800591ee  xor     r9d, r9d
0x1800591f1  lea     eax, [r9+r8]
0x1800591f5  cdq
0x1800591f6  sub     eax, edx
0x1800591f8  sar     eax, 1
0x1800591fa  movsxd  r10, eax
0x1800591fd  lea     rdx, [r10+r10*4]
0x180059201  lea     rdx, [rdi+rdx*8]
0x180059205  cmp     ebp, [rdx]
0x180059207  jnb     short loc_180059213
0x180059209  cmp     r10d, r9d
0x18005920c  jz      short loc_1800591BF
0x18005920e  mov     r8d, r10d
0x180059211  jmp     short loc_1800591F1
0x180059213  jbe     short loc_180059220
0x180059215  lea     r9d, [r10+1]
0x180059219  cmp     r9d, r8d
0x18005921c  jnz     short loc_1800591F1
0x18005921e  jmp     short loc_1800591BF
0x180059220  mov     rax, [rsi]
0x180059223  cmp     rax, [rdx]
0x180059226  jnz     short loc_180059236
0x180059228  mov     rax, [rsi+8]
0x18005922c  cmp     rax, [rdx+8]
0x180059230  jz      loc_180059197
0x180059236  cmp     r10d, r9d
0x180059239  jle     short loc_18005926E
0x18005923b  lea     r11d, [r10-1]
0x18005923f  jmp     short loc_180059269
0x180059241  movsxd  rax, r11d
0x180059244  lea     rcx, [rax+rax*4]
0x180059248  lea     rdx, [rdi+rcx*8]
0x18005924c  cmp     ebp, [rdx]
0x18005924e  jnz     short loc_18005926E
0x180059250  mov     rax, [rsi]
0x180059253  cmp     rax, [rdx]
0x180059256  jnz     short loc_180059266
0x180059258  mov     rax, [rsi+8]
0x18005925c  cmp     rax, [rdx+8]
0x180059260  jz      loc_180059197
0x180059266  dec     r11d
0x180059269  cmp     r11d, r9d
0x18005926c  jge     short loc_180059241
0x18005926e  lea     r9d, [r10+1]
0x180059272  jmp     short loc_1800592A0
0x180059274  movsxd  rax, r9d
0x180059277  lea     rcx, [rax+rax*4]
0x18005927b  lea     rdx, [rdi+rcx*8]
0x18005927f  cmp     ebp, [rdx]
0x180059281  jnz     loc_1800591BF
0x180059287  mov     rax, [rsi]
0x18005928a  cmp     rax, [rdx]
0x18005928d  jnz     short loc_18005929D
0x18005928f  mov     rax, [rsi+8]
0x180059293  cmp     rax, [rdx+8]
0x180059297  jz      loc_180059197
0x18005929d  inc     r9d
0x1800592a0  cmp     r9d, r8d
0x1800592a3  jl      short loc_180059274
0x1800592a5  jmp     loc_1800591BF
0x1800592aa  mov     edi, 0C00D36BDh
0x1800592af  jmp     loc_1800591C4
0x1800592b4  mov     rcx, rbx; SRWLock
0x1800592b7  mov     dword ptr [rbx+8], 0
0x1800592be  call    cs:__imp_ReleaseSRWLockExclusive
0x1800592c4  jmp     short loc_1800592CF
0x1800592c6  mov     rcx, rbx; SRWLock
0x1800592c9  call    cs:__imp_ReleaseSRWLockShared
0x1800592cf  mov     eax, edi
0x1800592d1  add     rsp, 20h
0x1800592d5  pop     r14
0x1800592d7  pop     rdi
0x1800592d8  pop     rsi
0x1800592d9  pop     rbp
0x1800592da  pop     rbx
0x1800592db  retn
```
