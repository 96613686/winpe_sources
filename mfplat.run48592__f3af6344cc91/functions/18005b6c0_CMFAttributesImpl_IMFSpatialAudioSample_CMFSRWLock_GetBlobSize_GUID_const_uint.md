# CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetBlobSize(_GUID const &,uint *)

- ea: `0x18005b6c0`
- end: `0x18005b87f`
- name: `?GetBlobSize@?$CMFAttributesImpl@UIMFSpatialAudioSample@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAI@Z`
- size: `447`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18005b6c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005b6ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005b6ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005b86c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005b86c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b6d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b767`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b6d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b767`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetBlobSize(
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
0x18005b6c0  push    rbx
0x18005b6c2  push    rbp
0x18005b6c3  push    rsi
0x18005b6c4  push    rdi
0x18005b6c5  push    r14
0x18005b6c7  sub     rsp, 20h
0x18005b6cb  mov     r14, r8
0x18005b6ce  lea     rbx, [rcx+8]
0x18005b6d2  mov     rsi, rdx
0x18005b6d5  mov     rdi, rcx
0x18005b6d8  call    cs:__imp_GetCurrentThreadId
0x18005b6de  mov     r9d, [rbx+8]
0x18005b6e2  cmp     r9d, eax
0x18005b6e5  jnz     short loc_18005B6EC
0x18005b6e7  inc     dword ptr [rbx+0Ch]
0x18005b6ea  jmp     short loc_18005B6F5
0x18005b6ec  mov     rcx, rbx; SRWLock
0x18005b6ef  call    cs:__imp_AcquireSRWLockShared
0x18005b6f5  mov     r8d, [rdi+24h]
0x18005b6f9  test    r8d, r8d
0x18005b6fc  jz      short loc_18005B762
0x18005b6fe  mov     ebp, [rsi]
0x18005b700  cmp     r8d, 4
0x18005b704  jge     loc_18005B78D
0x18005b70a  test    r8d, r8d
0x18005b70d  jle     short loc_18005B762
0x18005b70f  mov     r10, [rdi+18h]
0x18005b713  xor     r9d, r9d
0x18005b716  movsxd  rax, r9d
0x18005b719  lea     rcx, [rax+rax*4]
0x18005b71d  lea     rdx, [r10+rcx*8]
0x18005b721  cmp     [rdx], ebp
0x18005b723  jnz     short loc_18005B758
0x18005b725  mov     rax, [rsi]
0x18005b728  cmp     rax, [rdx]
0x18005b72b  jnz     short loc_18005B75A
0x18005b72d  mov     rax, [rsi+8]
0x18005b731  cmp     rax, [rdx+8]
0x18005b735  jnz     short loc_18005B75A
0x18005b737  lea     rax, [rdx+10h]
0x18005b73b  test    rax, rax
0x18005b73e  jz      short loc_18005B762
0x18005b740  mov     ecx, 1011h
0x18005b745  cmp     [rax], cx
0x18005b748  jnz     loc_18005B84D
0x18005b74e  mov     eax, [rax+8]
0x18005b751  xor     edi, edi
0x18005b753  mov     [r14], eax
0x18005b756  jmp     short loc_18005B767
0x18005b758  ja      short loc_18005B762
0x18005b75a  inc     r9d
0x18005b75d  cmp     r9d, r8d
0x18005b760  jl      short loc_18005B716
0x18005b762  mov     edi, 0C00D36E6h
0x18005b767  call    cs:__imp_GetCurrentThreadId
0x18005b76d  mov     ecx, [rbx+8]
0x18005b770  cmp     ecx, eax
0x18005b772  jnz     loc_18005B869
0x18005b778  mov     eax, [rbx+0Ch]
0x18005b77b  test    eax, eax
0x18005b77d  jz      loc_18005B857
0x18005b783  dec     eax
0x18005b785  mov     [rbx+0Ch], eax
0x18005b788  jmp     loc_18005B872
0x18005b78d  mov     rdi, [rdi+18h]
0x18005b791  xor     r9d, r9d
0x18005b794  lea     eax, [r9+r8]
0x18005b798  cdq
0x18005b799  sub     eax, edx
0x18005b79b  sar     eax, 1
0x18005b79d  movsxd  r10, eax
0x18005b7a0  lea     rdx, [r10+r10*4]
0x18005b7a4  lea     rdx, [rdi+rdx*8]
0x18005b7a8  cmp     ebp, [rdx]
0x18005b7aa  jnb     short loc_18005B7B6
0x18005b7ac  cmp     r10d, r9d
0x18005b7af  jz      short loc_18005B762
0x18005b7b1  mov     r8d, r10d
0x18005b7b4  jmp     short loc_18005B794
0x18005b7b6  jbe     short loc_18005B7C3
0x18005b7b8  lea     r9d, [r10+1]
0x18005b7bc  cmp     r9d, r8d
0x18005b7bf  jnz     short loc_18005B794
0x18005b7c1  jmp     short loc_18005B762
0x18005b7c3  mov     rax, [rsi]
0x18005b7c6  cmp     rax, [rdx]
0x18005b7c9  jnz     short loc_18005B7D9
0x18005b7cb  mov     rax, [rsi+8]
0x18005b7cf  cmp     rax, [rdx+8]
0x18005b7d3  jz      loc_18005B737
0x18005b7d9  cmp     r10d, r9d
0x18005b7dc  jle     short loc_18005B811
0x18005b7de  lea     r11d, [r10-1]
0x18005b7e2  jmp     short loc_18005B80C
0x18005b7e4  movsxd  rax, r11d
0x18005b7e7  lea     rcx, [rax+rax*4]
0x18005b7eb  lea     rdx, [rdi+rcx*8]
0x18005b7ef  cmp     ebp, [rdx]
0x18005b7f1  jnz     short loc_18005B811
0x18005b7f3  mov     rax, [rsi]
0x18005b7f6  cmp     rax, [rdx]
0x18005b7f9  jnz     short loc_18005B809
0x18005b7fb  mov     rax, [rsi+8]
0x18005b7ff  cmp     rax, [rdx+8]
0x18005b803  jz      loc_18005B737
0x18005b809  dec     r11d
0x18005b80c  cmp     r11d, r9d
0x18005b80f  jge     short loc_18005B7E4
0x18005b811  lea     r9d, [r10+1]
0x18005b815  jmp     short loc_18005B843
0x18005b817  movsxd  rax, r9d
0x18005b81a  lea     rcx, [rax+rax*4]
0x18005b81e  lea     rdx, [rdi+rcx*8]
0x18005b822  cmp     ebp, [rdx]
0x18005b824  jnz     loc_18005B762
0x18005b82a  mov     rax, [rsi]
0x18005b82d  cmp     rax, [rdx]
0x18005b830  jnz     short loc_18005B840
0x18005b832  mov     rax, [rsi+8]
0x18005b836  cmp     rax, [rdx+8]
0x18005b83a  jz      loc_18005B737
0x18005b840  inc     r9d
0x18005b843  cmp     r9d, r8d
0x18005b846  jl      short loc_18005B817
0x18005b848  jmp     loc_18005B762
0x18005b84d  mov     edi, 0C00D36BDh
0x18005b852  jmp     loc_18005B767
0x18005b857  mov     rcx, rbx; SRWLock
0x18005b85a  mov     dword ptr [rbx+8], 0
0x18005b861  call    cs:__imp_ReleaseSRWLockExclusive
0x18005b867  jmp     short loc_18005B872
0x18005b869  mov     rcx, rbx; SRWLock
0x18005b86c  call    cs:__imp_ReleaseSRWLockShared
0x18005b872  mov     eax, edi
0x18005b874  add     rsp, 20h
0x18005b878  pop     r14
0x18005b87a  pop     rdi
0x18005b87b  pop     rsi
0x18005b87c  pop     rbp
0x18005b87d  pop     rbx
0x18005b87e  retn
```
