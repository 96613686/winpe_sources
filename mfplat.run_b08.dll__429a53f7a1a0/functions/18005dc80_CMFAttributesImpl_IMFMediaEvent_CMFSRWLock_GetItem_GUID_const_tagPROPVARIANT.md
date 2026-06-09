# CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetItem(_GUID const &,tagPROPVARIANT *)

- ea: `0x18005dc80`
- end: `0x18005de2a`
- name: `?GetItem@?$CMFAttributesImpl@UIMFMediaEvent@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `426`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18005dc80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005dcaf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005dcaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005de0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005de0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005de17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005de17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dc98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dd1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dc98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dd1c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18005dd03`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18005dd03`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetItem(__int64 a1, unsigned int *a2, PROPVARIANT *a3)
{
  __int64 v4; // rbx
  int v7; // r8d
  unsigned int v8; // ebp
  int v9; // r9d
  _QWORD *v10; // rdx
  const PROPVARIANT *v11; // rdx
  unsigned int v12; // edi
  int v13; // eax
  __int64 v14; // rdi
  int v15; // r9d
  __int64 v16; // r10
  int i; // r11d
  int j; // r9d

  v4 = a1 + 8;
  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
    ++*(_DWORD *)(v4 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v4);
  v7 = *(_DWORD *)(a1 + 36);
  if ( !v7 )
    goto LABEL_16;
  v8 = *a2;
  if ( v7 < 4 )
  {
    if ( v7 > 0 )
    {
      v9 = 0;
      while ( 1 )
      {
        v10 = (_QWORD *)(*(_QWORD *)(a1 + 24) + 40LL * v9);
        if ( *(_DWORD *)v10 == v8 )
        {
          if ( *(_QWORD *)a2 == *v10 && *((_QWORD *)a2 + 1) == v10[1] )
            goto LABEL_11;
        }
        else if ( *(_DWORD *)v10 > v8 )
        {
          goto LABEL_16;
        }
        if ( ++v9 >= v7 )
          goto LABEL_16;
      }
    }
    goto LABEL_16;
  }
  v14 = *(_QWORD *)(a1 + 24);
  v15 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v16 = (v15 + v7) / 2;
      v10 = (_QWORD *)(v14 + 40 * v16);
      if ( v8 >= *(_DWORD *)v10 )
        break;
      if ( (_DWORD)v16 == v15 )
        goto LABEL_16;
      v7 = (v15 + v7) / 2;
    }
    if ( v8 <= *(_DWORD *)v10 )
      break;
    v15 = v16 + 1;
    if ( (_DWORD)v16 + 1 == v7 )
      goto LABEL_16;
  }
  if ( *(_QWORD *)a2 != *v10 || *((_QWORD *)a2 + 1) != v10[1] )
  {
    if ( (int)v16 > v15 )
    {
      for ( i = v16 - 1; i >= v15; --i )
      {
        v10 = (_QWORD *)(v14 + 40LL * i);
        if ( v8 != *(_DWORD *)v10 )
          break;
        if ( *(_QWORD *)a2 == *v10 && *((_QWORD *)a2 + 1) == v10[1] )
          goto LABEL_11;
      }
    }
    for ( j = v16 + 1; j < v7; ++j )
    {
      v10 = (_QWORD *)(v14 + 40LL * j);
      if ( v8 != *(_DWORD *)v10 )
        break;
      if ( *(_QWORD *)a2 == *v10 && *((_QWORD *)a2 + 1) == v10[1] )
        goto LABEL_11;
    }
    goto LABEL_16;
  }
LABEL_11:
  v11 = (const PROPVARIANT *)(v10 + 2);
  if ( !v11 )
  {
LABEL_16:
    v12 = -1072875802;
    goto LABEL_17;
  }
  v12 = 0;
  if ( a3 )
    v12 = PropVariantCopy(a3, v11);
LABEL_17:
  if ( *(_DWORD *)(v4 + 8) == GetCurrentThreadId() )
  {
    v13 = *(_DWORD *)(v4 + 12);
    if ( v13 )
    {
      *(_DWORD *)(v4 + 12) = v13 - 1;
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
  return v12;
}

```

## disassembly

```asm
0x18005dc80  push    rbx
0x18005dc82  push    rbp
0x18005dc83  push    rsi
0x18005dc84  push    rdi
0x18005dc85  push    r14
0x18005dc87  sub     rsp, 20h
0x18005dc8b  mov     r14, r8
0x18005dc8e  lea     rbx, [rcx+8]
0x18005dc92  mov     rsi, rdx
0x18005dc95  mov     rdi, rcx
0x18005dc98  call    cs:__imp_GetCurrentThreadId
0x18005dc9e  mov     r9d, [rbx+8]
0x18005dca2  cmp     r9d, eax
0x18005dca5  jnz     short loc_18005DCAC
0x18005dca7  inc     dword ptr [rbx+0Ch]
0x18005dcaa  jmp     short loc_18005DCB5
0x18005dcac  mov     rcx, rbx; SRWLock
0x18005dcaf  call    cs:__imp_AcquireSRWLockShared
0x18005dcb5  mov     r8d, [rdi+24h]
0x18005dcb9  test    r8d, r8d
0x18005dcbc  jz      short loc_18005DD17
0x18005dcbe  mov     ebp, [rsi]
0x18005dcc0  cmp     r8d, 4
0x18005dcc4  jge     short loc_18005DD42
0x18005dcc6  test    r8d, r8d
0x18005dcc9  jle     short loc_18005DD17
0x18005dccb  mov     r10, [rdi+18h]
0x18005dccf  xor     r9d, r9d
0x18005dcd2  movsxd  rax, r9d
0x18005dcd5  lea     rcx, [rax+rax*4]
0x18005dcd9  lea     rdx, [r10+rcx*8]
0x18005dcdd  cmp     [rdx], ebp
0x18005dcdf  jnz     short loc_18005DD0D
0x18005dce1  mov     rax, [rsi]
0x18005dce4  cmp     rax, [rdx]
0x18005dce7  jnz     short loc_18005DD0F
0x18005dce9  mov     rax, [rsi+8]
0x18005dced  cmp     rax, [rdx+8]
0x18005dcf1  jnz     short loc_18005DD0F
0x18005dcf3  add     rdx, 10h; pvarSrc
0x18005dcf7  jz      short loc_18005DD17
0x18005dcf9  xor     edi, edi
0x18005dcfb  test    r14, r14
0x18005dcfe  jz      short loc_18005DD1C
0x18005dd00  mov     rcx, r14; pvarDest
0x18005dd03  call    cs:__imp_PropVariantCopy
0x18005dd09  mov     edi, eax
0x18005dd0b  jmp     short loc_18005DD1C
0x18005dd0d  ja      short loc_18005DD17
0x18005dd0f  inc     r9d
0x18005dd12  cmp     r9d, r8d
0x18005dd15  jl      short loc_18005DCD2
0x18005dd17  mov     edi, 0C00D36E6h
0x18005dd1c  call    cs:__imp_GetCurrentThreadId
0x18005dd22  mov     ecx, [rbx+8]
0x18005dd25  cmp     ecx, eax
0x18005dd27  jnz     loc_18005DE14
0x18005dd2d  mov     eax, [rbx+0Ch]
0x18005dd30  test    eax, eax
0x18005dd32  jz      loc_18005DE02
0x18005dd38  dec     eax
0x18005dd3a  mov     [rbx+0Ch], eax
0x18005dd3d  jmp     loc_18005DE1D
0x18005dd42  mov     rdi, [rdi+18h]
0x18005dd46  xor     r9d, r9d
0x18005dd49  lea     eax, [r9+r8]
0x18005dd4d  cdq
0x18005dd4e  sub     eax, edx
0x18005dd50  sar     eax, 1
0x18005dd52  movsxd  r10, eax
0x18005dd55  lea     rdx, [r10+r10*4]
0x18005dd59  lea     rdx, [rdi+rdx*8]
0x18005dd5d  cmp     ebp, [rdx]
0x18005dd5f  jnb     short loc_18005DD6B
0x18005dd61  cmp     r10d, r9d
0x18005dd64  jz      short loc_18005DD17
0x18005dd66  mov     r8d, r10d
0x18005dd69  jmp     short loc_18005DD49
0x18005dd6b  jbe     short loc_18005DD78
0x18005dd6d  lea     r9d, [r10+1]
0x18005dd71  cmp     r9d, r8d
0x18005dd74  jnz     short loc_18005DD49
0x18005dd76  jmp     short loc_18005DD17
0x18005dd78  mov     rax, [rsi]
0x18005dd7b  cmp     rax, [rdx]
0x18005dd7e  jnz     short loc_18005DD8E
0x18005dd80  mov     rax, [rsi+8]
0x18005dd84  cmp     rax, [rdx+8]
0x18005dd88  jz      loc_18005DCF3
0x18005dd8e  cmp     r10d, r9d
0x18005dd91  jle     short loc_18005DDC6
0x18005dd93  lea     r11d, [r10-1]
0x18005dd97  jmp     short loc_18005DDC1
0x18005dd99  movsxd  rax, r11d
0x18005dd9c  lea     rcx, [rax+rax*4]
0x18005dda0  lea     rdx, [rdi+rcx*8]
0x18005dda4  cmp     ebp, [rdx]
0x18005dda6  jnz     short loc_18005DDC6
0x18005dda8  mov     rax, [rsi]
0x18005ddab  cmp     rax, [rdx]
0x18005ddae  jnz     short loc_18005DDBE
0x18005ddb0  mov     rax, [rsi+8]
0x18005ddb4  cmp     rax, [rdx+8]
0x18005ddb8  jz      loc_18005DCF3
0x18005ddbe  dec     r11d
0x18005ddc1  cmp     r11d, r9d
0x18005ddc4  jge     short loc_18005DD99
0x18005ddc6  lea     r9d, [r10+1]
0x18005ddca  jmp     short loc_18005DDF8
0x18005ddcc  movsxd  rax, r9d
0x18005ddcf  lea     rcx, [rax+rax*4]
0x18005ddd3  lea     rdx, [rdi+rcx*8]
0x18005ddd7  cmp     ebp, [rdx]
0x18005ddd9  jnz     loc_18005DD17
0x18005dddf  mov     rax, [rsi]
0x18005dde2  cmp     rax, [rdx]
0x18005dde5  jnz     short loc_18005DDF5
0x18005dde7  mov     rax, [rsi+8]
0x18005ddeb  cmp     rax, [rdx+8]
0x18005ddef  jz      loc_18005DCF3
0x18005ddf5  inc     r9d
0x18005ddf8  cmp     r9d, r8d
0x18005ddfb  jl      short loc_18005DDCC
0x18005ddfd  jmp     loc_18005DD17
0x18005de02  mov     rcx, rbx; SRWLock
0x18005de05  mov     dword ptr [rbx+8], 0
0x18005de0c  call    cs:__imp_ReleaseSRWLockExclusive
0x18005de12  jmp     short loc_18005DE1D
0x18005de14  mov     rcx, rbx; SRWLock
0x18005de17  call    cs:__imp_ReleaseSRWLockShared
0x18005de1d  mov     eax, edi
0x18005de1f  add     rsp, 20h
0x18005de23  pop     r14
0x18005de25  pop     rdi
0x18005de26  pop     rsi
0x18005de27  pop     rbp
0x18005de28  pop     rbx
0x18005de29  retn
```
