# CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetUINT64(_GUID const &,unsigned __int64 *)

- ea: `0x180055730`
- end: `0x180055944`
- name: `?GetUINT64@?$CMFAttributesImpl@UIMFMediaEvent@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEA_K@Z`
- size: `532`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180055730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180055768`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180055768`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005591b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005591b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180055931`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180055931`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800557f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800557f0`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetUINT64(__int64 a1, unsigned int *a2, _QWORD *a3)
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
          if ( *(_WORD *)(v11 + 16) == 21 )
          {
            v12 = 0;
            *a3 = *(_QWORD *)(v11 + 24);
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
0x180055730  mov     [rsp+arg_18], rbx
0x180055735  push    rbp
0x180055736  sub     rsp, 20h
0x18005573a  mov     [rsp+28h+arg_0], rsi
0x18005573f  lea     rbp, [rcx+8]
0x180055743  mov     [rsp+28h+arg_10], r14
0x180055748  mov     rbx, rdx
0x18005574b  mov     r14, r8
0x18005574e  mov     rsi, rcx
0x180055751  call    cs:__imp_GetCurrentThreadId
0x180055757  mov     r9d, [rbp+8]
0x18005575b  cmp     r9d, eax
0x18005575e  jnz     short loc_180055765
0x180055760  inc     dword ptr [rbp+0Ch]
0x180055763  jmp     short loc_18005576E
0x180055765  mov     rcx, rbp; SRWLock
0x180055768  call    cs:__imp_AcquireSRWLockShared
0x18005576e  mov     r9d, [rsi+24h]
0x180055772  mov     [rsp+28h+arg_8], rdi
0x180055777  test    r9d, r9d
0x18005577a  jz      short loc_1800557EB
0x18005577c  mov     edi, [rbx]
0x18005577e  cmp     r9d, 4
0x180055782  jge     loc_18005582D
0x180055788  test    r9d, r9d
0x18005578b  jle     short loc_1800557EB
0x18005578d  mov     r10, [rsi+18h]
0x180055791  xor     r8d, r8d
0x180055794  nop     dword ptr [rax+00h]
0x180055798  nop     dword ptr [rax+rax+00000000h]
0x1800557a0  movsxd  rax, r8d
0x1800557a3  lea     rcx, [rax+rax*4]
0x1800557a7  cmp     [r10+rcx*8], edi
0x1800557ab  lea     rdx, [r10+rcx*8]
0x1800557af  jnz     short loc_1800557E1
0x1800557b1  mov     rax, [rbx]
0x1800557b4  cmp     rax, [rdx]
0x1800557b7  jnz     short loc_1800557E3
0x1800557b9  mov     rax, [rbx+8]
0x1800557bd  cmp     rax, [rdx+8]
0x1800557c1  jnz     short loc_1800557E3
0x1800557c3  lea     rax, [rdx+10h]
0x1800557c7  test    rax, rax
0x1800557ca  jz      short loc_1800557EB
0x1800557cc  cmp     word ptr [rax], 15h
0x1800557d0  jnz     loc_180055907
0x1800557d6  mov     rax, [rax+8]
0x1800557da  xor     ebx, ebx
0x1800557dc  mov     [r14], rax
0x1800557df  jmp     short loc_1800557F0
0x1800557e1  ja      short loc_1800557EB
0x1800557e3  inc     r8d
0x1800557e6  cmp     r8d, r9d
0x1800557e9  jl      short loc_1800557A0
0x1800557eb  mov     ebx, 0C00D36E6h
0x1800557f0  call    cs:__imp_GetCurrentThreadId
0x1800557f6  mov     ecx, [rbp+8]
0x1800557f9  mov     r14, [rsp+28h+arg_10]
0x1800557fe  mov     rdi, [rsp+28h+arg_8]
0x180055803  mov     rsi, [rsp+28h+arg_0]
0x180055808  cmp     ecx, eax
0x18005580a  jnz     loc_18005592E
0x180055810  mov     ecx, [rbp+0Ch]
0x180055813  test    ecx, ecx
0x180055815  jz      loc_180055911
0x18005581b  dec     ecx
0x18005581d  mov     eax, ebx
0x18005581f  mov     [rbp+0Ch], ecx
0x180055822  mov     rbx, [rsp+28h+arg_18]
0x180055827  add     rsp, 20h
0x18005582b  pop     rbp
0x18005582c  retn
0x18005582d  mov     rsi, [rsi+18h]
0x180055831  xor     r8d, r8d
0x180055834  lea     eax, [r8+r9]
0x180055838  cdq
0x180055839  sub     eax, edx
0x18005583b  sar     eax, 1
0x18005583d  movsxd  r10, eax
0x180055840  lea     rdx, [r10+r10*4]
0x180055844  cmp     edi, [rsi+rdx*8]
0x180055847  lea     rdx, [rsi+rdx*8]
0x18005584b  jnb     short loc_180055857
0x18005584d  cmp     r10d, r8d
0x180055850  jz      short loc_1800557EB
0x180055852  mov     r9d, r10d
0x180055855  jmp     short loc_180055834
0x180055857  jbe     short loc_180055864
0x180055859  lea     r8d, [r10+1]
0x18005585d  cmp     r8d, r9d
0x180055860  jnz     short loc_180055834
0x180055862  jmp     short loc_1800557EB
0x180055864  mov     rax, [rbx]
0x180055867  cmp     rax, [rdx]
0x18005586a  jnz     short loc_18005587A
0x18005586c  mov     rax, [rbx+8]
0x180055870  cmp     rax, [rdx+8]
0x180055874  jz      loc_1800557C3
0x18005587a  cmp     r10d, r8d
0x18005587d  jle     short loc_1800558BE
0x18005587f  lea     r11d, [r10-1]
0x180055883  cmp     r11d, r8d
0x180055886  jl      short loc_1800558BE
0x180055888  nop     dword ptr [rax+rax+00000000h]
0x180055890  movsxd  rax, r11d
0x180055893  lea     rcx, [rax+rax*4]
0x180055897  cmp     edi, [rsi+rcx*8]
0x18005589a  lea     rdx, [rsi+rcx*8]
0x18005589e  jnz     short loc_1800558BE
0x1800558a0  mov     rax, [rbx]
0x1800558a3  cmp     rax, [rdx]
0x1800558a6  jnz     short loc_1800558B6
0x1800558a8  mov     rax, [rbx+8]
0x1800558ac  cmp     rax, [rdx+8]
0x1800558b0  jz      loc_1800557C3
0x1800558b6  dec     r11d
0x1800558b9  cmp     r11d, r8d
0x1800558bc  jge     short loc_180055890
0x1800558be  lea     r8d, [r10+1]
0x1800558c2  cmp     r8d, r9d
0x1800558c5  jge     loc_1800557EB
0x1800558cb  nop     dword ptr [rax+rax+00h]
0x1800558d0  movsxd  rax, r8d
0x1800558d3  lea     rcx, [rax+rax*4]
0x1800558d7  cmp     edi, [rsi+rcx*8]
0x1800558da  lea     rdx, [rsi+rcx*8]
0x1800558de  jnz     loc_1800557EB
0x1800558e4  mov     rax, [rbx]
0x1800558e7  cmp     rax, [rdx]
0x1800558ea  jnz     short loc_1800558FA
0x1800558ec  mov     rax, [rbx+8]
0x1800558f0  cmp     rax, [rdx+8]
0x1800558f4  jz      loc_1800557C3
0x1800558fa  inc     r8d
0x1800558fd  cmp     r8d, r9d
0x180055900  jl      short loc_1800558D0
0x180055902  jmp     loc_1800557EB
0x180055907  mov     ebx, 0C00D36BDh
0x18005590c  jmp     loc_1800557F0
0x180055911  mov     rcx, rbp; SRWLock
0x180055914  mov     dword ptr [rbp+8], 0
0x18005591b  call    cs:__imp_ReleaseSRWLockExclusive
0x180055921  mov     eax, ebx
0x180055923  mov     rbx, [rsp+28h+arg_18]
0x180055928  add     rsp, 20h
0x18005592c  pop     rbp
0x18005592d  retn
0x18005592e  mov     rcx, rbp; SRWLock
0x180055931  call    cs:__imp_ReleaseSRWLockShared
0x180055937  mov     eax, ebx
0x180055939  mov     rbx, [rsp+28h+arg_18]
0x18005593e  add     rsp, 20h
0x180055942  pop     rbp
0x180055943  retn
```
