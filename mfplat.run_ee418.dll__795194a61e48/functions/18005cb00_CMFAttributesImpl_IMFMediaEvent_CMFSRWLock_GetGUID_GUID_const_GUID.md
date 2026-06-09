# CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetGUID(_GUID const &,_GUID *)

- ea: `0x18005cb00`
- end: `0x18005ccc1`
- name: `?GetGUID@?$CMFAttributesImpl@UIMFMediaEvent@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAU2@@Z`
- size: `449`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18005cb00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005cb2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005cb2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005cca3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005cca3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ccae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ccae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cb18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cba9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cb18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cba9`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFMediaEvent,CMFSRWLock>::GetGUID(__int64 a1, unsigned int *a2, _OWORD *a3)
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
          if ( *(_WORD *)(v10 + 16) == 72 )
          {
            v11 = 0;
            *a3 = *(_OWORD *)*(_QWORD *)(v10 + 24);
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
0x18005cb00  push    rbx
0x18005cb02  push    rbp
0x18005cb03  push    rsi
0x18005cb04  push    rdi
0x18005cb05  push    r14
0x18005cb07  sub     rsp, 20h
0x18005cb0b  mov     r14, r8
0x18005cb0e  lea     rbx, [rcx+8]
0x18005cb12  mov     rsi, rdx
0x18005cb15  mov     rdi, rcx
0x18005cb18  call    cs:__imp_GetCurrentThreadId
0x18005cb1e  mov     r9d, [rbx+8]
0x18005cb22  cmp     r9d, eax
0x18005cb25  jnz     short loc_18005CB2C
0x18005cb27  inc     dword ptr [rbx+0Ch]
0x18005cb2a  jmp     short loc_18005CB35
0x18005cb2c  mov     rcx, rbx; SRWLock
0x18005cb2f  call    cs:__imp_AcquireSRWLockShared
0x18005cb35  mov     r8d, [rdi+24h]
0x18005cb39  test    r8d, r8d
0x18005cb3c  jz      short loc_18005CBA4
0x18005cb3e  mov     ebp, [rsi]
0x18005cb40  cmp     r8d, 4
0x18005cb44  jge     loc_18005CBCF
0x18005cb4a  test    r8d, r8d
0x18005cb4d  jle     short loc_18005CBA4
0x18005cb4f  mov     r10, [rdi+18h]
0x18005cb53  xor     r9d, r9d
0x18005cb56  movsxd  rax, r9d
0x18005cb59  lea     rcx, [rax+rax*4]
0x18005cb5d  lea     rdx, [r10+rcx*8]
0x18005cb61  cmp     [rdx], ebp
0x18005cb63  jnz     short loc_18005CB9A
0x18005cb65  mov     rax, [rsi]
0x18005cb68  cmp     rax, [rdx]
0x18005cb6b  jnz     short loc_18005CB9C
0x18005cb6d  mov     rax, [rsi+8]
0x18005cb71  cmp     rax, [rdx+8]
0x18005cb75  jnz     short loc_18005CB9C
0x18005cb77  lea     rax, [rdx+10h]
0x18005cb7b  test    rax, rax
0x18005cb7e  jz      short loc_18005CBA4
0x18005cb80  cmp     word ptr [rax], 48h ; 'H'
0x18005cb84  jnz     loc_18005CC8F
0x18005cb8a  mov     rax, [rax+8]
0x18005cb8e  xor     edi, edi
0x18005cb90  movups  xmm0, xmmword ptr [rax]
0x18005cb93  movdqu  xmmword ptr [r14], xmm0
0x18005cb98  jmp     short loc_18005CBA9
0x18005cb9a  ja      short loc_18005CBA4
0x18005cb9c  inc     r9d
0x18005cb9f  cmp     r9d, r8d
0x18005cba2  jl      short loc_18005CB56
0x18005cba4  mov     edi, 0C00D36E6h
0x18005cba9  call    cs:__imp_GetCurrentThreadId
0x18005cbaf  mov     ecx, [rbx+8]
0x18005cbb2  cmp     ecx, eax
0x18005cbb4  jnz     loc_18005CCAB
0x18005cbba  mov     eax, [rbx+0Ch]
0x18005cbbd  test    eax, eax
0x18005cbbf  jz      loc_18005CC99
0x18005cbc5  dec     eax
0x18005cbc7  mov     [rbx+0Ch], eax
0x18005cbca  jmp     loc_18005CCB4
0x18005cbcf  mov     rdi, [rdi+18h]
0x18005cbd3  xor     r9d, r9d
0x18005cbd6  lea     eax, [r9+r8]
0x18005cbda  cdq
0x18005cbdb  sub     eax, edx
0x18005cbdd  sar     eax, 1
0x18005cbdf  movsxd  r10, eax
0x18005cbe2  lea     rdx, [r10+r10*4]
0x18005cbe6  lea     rdx, [rdi+rdx*8]
0x18005cbea  cmp     ebp, [rdx]
0x18005cbec  jnb     short loc_18005CBF8
0x18005cbee  cmp     r10d, r9d
0x18005cbf1  jz      short loc_18005CBA4
0x18005cbf3  mov     r8d, r10d
0x18005cbf6  jmp     short loc_18005CBD6
0x18005cbf8  jbe     short loc_18005CC05
0x18005cbfa  lea     r9d, [r10+1]
0x18005cbfe  cmp     r9d, r8d
0x18005cc01  jnz     short loc_18005CBD6
0x18005cc03  jmp     short loc_18005CBA4
0x18005cc05  mov     rax, [rsi]
0x18005cc08  cmp     rax, [rdx]
0x18005cc0b  jnz     short loc_18005CC1B
0x18005cc0d  mov     rax, [rsi+8]
0x18005cc11  cmp     rax, [rdx+8]
0x18005cc15  jz      loc_18005CB77
0x18005cc1b  cmp     r10d, r9d
0x18005cc1e  jle     short loc_18005CC53
0x18005cc20  lea     r11d, [r10-1]
0x18005cc24  jmp     short loc_18005CC4E
0x18005cc26  movsxd  rax, r11d
0x18005cc29  lea     rcx, [rax+rax*4]
0x18005cc2d  lea     rdx, [rdi+rcx*8]
0x18005cc31  cmp     ebp, [rdx]
0x18005cc33  jnz     short loc_18005CC53
0x18005cc35  mov     rax, [rsi]
0x18005cc38  cmp     rax, [rdx]
0x18005cc3b  jnz     short loc_18005CC4B
0x18005cc3d  mov     rax, [rsi+8]
0x18005cc41  cmp     rax, [rdx+8]
0x18005cc45  jz      loc_18005CB77
0x18005cc4b  dec     r11d
0x18005cc4e  cmp     r11d, r9d
0x18005cc51  jge     short loc_18005CC26
0x18005cc53  lea     r9d, [r10+1]
0x18005cc57  jmp     short loc_18005CC85
0x18005cc59  movsxd  rax, r9d
0x18005cc5c  lea     rcx, [rax+rax*4]
0x18005cc60  lea     rdx, [rdi+rcx*8]
0x18005cc64  cmp     ebp, [rdx]
0x18005cc66  jnz     loc_18005CBA4
0x18005cc6c  mov     rax, [rsi]
0x18005cc6f  cmp     rax, [rdx]
0x18005cc72  jnz     short loc_18005CC82
0x18005cc74  mov     rax, [rsi+8]
0x18005cc78  cmp     rax, [rdx+8]
0x18005cc7c  jz      loc_18005CB77
0x18005cc82  inc     r9d
0x18005cc85  cmp     r9d, r8d
0x18005cc88  jl      short loc_18005CC59
0x18005cc8a  jmp     loc_18005CBA4
0x18005cc8f  mov     edi, 0C00D36BDh
0x18005cc94  jmp     loc_18005CBA9
0x18005cc99  mov     rcx, rbx; SRWLock
0x18005cc9c  mov     dword ptr [rbx+8], 0
0x18005cca3  call    cs:__imp_ReleaseSRWLockExclusive
0x18005cca9  jmp     short loc_18005CCB4
0x18005ccab  mov     rcx, rbx; SRWLock
0x18005ccae  call    cs:__imp_ReleaseSRWLockShared
0x18005ccb4  mov     eax, edi
0x18005ccb6  add     rsp, 20h
0x18005ccba  pop     r14
0x18005ccbc  pop     rdi
0x18005ccbd  pop     rsi
0x18005ccbe  pop     rbp
0x18005ccbf  pop     rbx
0x18005ccc0  retn
```
