# CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetItem(_GUID const &,tagPROPVARIANT *)

- ea: `0x180053840`
- end: `0x180053a4a`
- name: `?GetItem@?$CMFAttributesImpl@UIMFSpatialAudioSample@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@PEAUtagPROPVARIANT@@@Z`
- size: `522`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180053840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180053878`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180053878`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053a21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053a21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180053a37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180053a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053861`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800538fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053861`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800538fc`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800538e3`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800538e3`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFSpatialAudioSample,CMFSRWLock>::GetItem(
        __int64 a1,
        unsigned int *a2,
        PROPVARIANT *a3)
{
  __int64 v3; // rbp
  int v7; // r9d
  unsigned int v8; // edi
  __int64 v9; // r10
  int v10; // r8d
  _QWORD *v11; // rdx
  const PROPVARIANT *v12; // rdx
  unsigned int v13; // ebx
  int v14; // eax
  __int64 v16; // rsi
  int v17; // r8d
  int v18; // eax
  int i; // r11d
  int v20; // r8d

  v3 = a1 + 8;
  if ( *(_DWORD *)(a1 + 16) == GetCurrentThreadId() )
    ++*(_DWORD *)(v3 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v3);
  v7 = *(_DWORD *)(a1 + 36);
  if ( !v7 )
    goto LABEL_16;
  v8 = *a2;
  if ( v7 < 4 )
  {
    if ( v7 > 0 )
    {
      v9 = *(_QWORD *)(a1 + 24);
      v10 = 0;
      while ( 1 )
      {
        v11 = (_QWORD *)(v9 + 40LL * v10);
        if ( *(_DWORD *)v11 == v8 )
        {
          if ( *(_QWORD *)a2 == *v11 && *((_QWORD *)a2 + 1) == v11[1] )
            goto LABEL_11;
        }
        else if ( *(_DWORD *)(v9 + 40LL * v10) > v8 )
        {
          goto LABEL_16;
        }
        if ( ++v10 >= v7 )
          goto LABEL_16;
      }
    }
    goto LABEL_16;
  }
  v16 = *(_QWORD *)(a1 + 24);
  v17 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v18 = (v17 + v7) / 2;
      v11 = (_QWORD *)(v16 + 40LL * v18);
      if ( v8 >= *(_DWORD *)v11 )
        break;
      if ( v18 == v17 )
        goto LABEL_16;
      v7 = (v17 + v7) / 2;
    }
    if ( v8 <= *(_DWORD *)(v16 + 40LL * v18) )
      break;
    v17 = v18 + 1;
    if ( v18 + 1 == v7 )
      goto LABEL_16;
  }
  if ( *(_QWORD *)a2 != *v11 || *((_QWORD *)a2 + 1) != v11[1] )
  {
    if ( v18 > v17 )
    {
      for ( i = v18 - 1; i >= v17; --i )
      {
        v11 = (_QWORD *)(v16 + 40LL * i);
        if ( v8 != *(_DWORD *)v11 )
          break;
        if ( *(_QWORD *)a2 == *v11 && *((_QWORD *)a2 + 1) == v11[1] )
          goto LABEL_11;
      }
    }
    v20 = v18 + 1;
    if ( v18 + 1 < v7 )
    {
      while ( 1 )
      {
        v11 = (_QWORD *)(v16 + 40LL * v20);
        if ( v8 != *(_DWORD *)v11 )
          break;
        if ( *(_QWORD *)a2 == *v11 && *((_QWORD *)a2 + 1) == v11[1] )
          goto LABEL_11;
        if ( ++v20 >= v7 )
          goto LABEL_16;
      }
    }
    goto LABEL_16;
  }
LABEL_11:
  v12 = (const PROPVARIANT *)(v11 + 2);
  if ( !v12 )
  {
LABEL_16:
    v13 = -1072875802;
    goto LABEL_17;
  }
  v13 = 0;
  if ( a3 )
    v13 = PropVariantCopy(a3, v12);
LABEL_17:
  if ( *(_DWORD *)(v3 + 8) == GetCurrentThreadId() )
  {
    v14 = *(_DWORD *)(v3 + 12);
    if ( v14 )
    {
      *(_DWORD *)(v3 + 12) = v14 - 1;
    }
    else
    {
      *(_DWORD *)(v3 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v3);
    }
    return v13;
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v3);
    return v13;
  }
}

```

## disassembly

```asm
0x180053840  mov     [rsp+arg_18], rbx
0x180053845  push    rbp
0x180053846  sub     rsp, 20h
0x18005384a  mov     [rsp+28h+arg_0], rsi
0x18005384f  lea     rbp, [rcx+8]
0x180053853  mov     [rsp+28h+arg_10], r14
0x180053858  mov     rbx, rdx
0x18005385b  mov     r14, r8
0x18005385e  mov     rsi, rcx
0x180053861  call    cs:__imp_GetCurrentThreadId
0x180053867  mov     r9d, [rbp+8]
0x18005386b  cmp     r9d, eax
0x18005386e  jnz     short loc_180053875
0x180053870  inc     dword ptr [rbp+0Ch]
0x180053873  jmp     short loc_18005387E
0x180053875  mov     rcx, rbp; SRWLock
0x180053878  call    cs:__imp_AcquireSRWLockShared
0x18005387e  mov     r9d, [rsi+24h]
0x180053882  mov     [rsp+28h+arg_8], rdi
0x180053887  test    r9d, r9d
0x18005388a  jz      short loc_1800538F7
0x18005388c  mov     edi, [rbx]
0x18005388e  cmp     r9d, 4
0x180053892  jge     loc_180053939
0x180053898  test    r9d, r9d
0x18005389b  jle     short loc_1800538F7
0x18005389d  mov     r10, [rsi+18h]
0x1800538a1  xor     r8d, r8d
0x1800538a4  nop     dword ptr [rax+00h]
0x1800538a8  nop     dword ptr [rax+rax+00000000h]
0x1800538b0  movsxd  rax, r8d
0x1800538b3  lea     rcx, [rax+rax*4]
0x1800538b7  cmp     [r10+rcx*8], edi
0x1800538bb  lea     rdx, [r10+rcx*8]
0x1800538bf  jnz     short loc_1800538ED
0x1800538c1  mov     rax, [rbx]
0x1800538c4  cmp     rax, [rdx]
0x1800538c7  jnz     short loc_1800538EF
0x1800538c9  mov     rax, [rbx+8]
0x1800538cd  cmp     rax, [rdx+8]
0x1800538d1  jnz     short loc_1800538EF
0x1800538d3  add     rdx, 10h; pvarSrc
0x1800538d7  jz      short loc_1800538F7
0x1800538d9  xor     ebx, ebx
0x1800538db  test    r14, r14
0x1800538de  jz      short loc_1800538FC
0x1800538e0  mov     rcx, r14; pvarDest
0x1800538e3  call    cs:__imp_PropVariantCopy
0x1800538e9  mov     ebx, eax
0x1800538eb  jmp     short loc_1800538FC
0x1800538ed  ja      short loc_1800538F7
0x1800538ef  inc     r8d
0x1800538f2  cmp     r8d, r9d
0x1800538f5  jl      short loc_1800538B0
0x1800538f7  mov     ebx, 0C00D36E6h
0x1800538fc  call    cs:__imp_GetCurrentThreadId
0x180053902  mov     ecx, [rbp+8]
0x180053905  mov     r14, [rsp+28h+arg_10]
0x18005390a  mov     rdi, [rsp+28h+arg_8]
0x18005390f  mov     rsi, [rsp+28h+arg_0]
0x180053914  cmp     ecx, eax
0x180053916  jnz     loc_180053A34
0x18005391c  mov     eax, [rbp+0Ch]
0x18005391f  test    eax, eax
0x180053921  jz      loc_180053A17
0x180053927  dec     eax
0x180053929  mov     [rbp+0Ch], eax
0x18005392c  mov     eax, ebx
0x18005392e  mov     rbx, [rsp+28h+arg_18]
0x180053933  add     rsp, 20h
0x180053937  pop     rbp
0x180053938  retn
0x180053939  mov     rsi, [rsi+18h]
0x18005393d  xor     r8d, r8d
0x180053940  lea     eax, [r8+r9]
0x180053944  cdq
0x180053945  sub     eax, edx
0x180053947  sar     eax, 1
0x180053949  movsxd  r10, eax
0x18005394c  lea     rdx, [r10+r10*4]
0x180053950  cmp     edi, [rsi+rdx*8]
0x180053953  lea     rdx, [rsi+rdx*8]
0x180053957  jnb     short loc_180053963
0x180053959  cmp     r10d, r8d
0x18005395c  jz      short loc_1800538F7
0x18005395e  mov     r9d, r10d
0x180053961  jmp     short loc_180053940
0x180053963  jbe     short loc_180053970
0x180053965  lea     r8d, [r10+1]
0x180053969  cmp     r8d, r9d
0x18005396c  jnz     short loc_180053940
0x18005396e  jmp     short loc_1800538F7
0x180053970  mov     rax, [rbx]
0x180053973  cmp     rax, [rdx]
0x180053976  jnz     short loc_180053986
0x180053978  mov     rax, [rbx+8]
0x18005397c  cmp     rax, [rdx+8]
0x180053980  jz      loc_1800538D3
0x180053986  cmp     r10d, r8d
0x180053989  jle     short loc_1800539CE
0x18005398b  lea     r11d, [r10-1]
0x18005398f  cmp     r11d, r8d
0x180053992  jl      short loc_1800539CE
0x180053994  nop     dword ptr [rax+00h]
0x180053998  nop     dword ptr [rax+rax+00000000h]
0x1800539a0  movsxd  rax, r11d
0x1800539a3  lea     rcx, [rax+rax*4]
0x1800539a7  cmp     edi, [rsi+rcx*8]
0x1800539aa  lea     rdx, [rsi+rcx*8]
0x1800539ae  jnz     short loc_1800539CE
0x1800539b0  mov     rax, [rbx]
0x1800539b3  cmp     rax, [rdx]
0x1800539b6  jnz     short loc_1800539C6
0x1800539b8  mov     rax, [rbx+8]
0x1800539bc  cmp     rax, [rdx+8]
0x1800539c0  jz      loc_1800538D3
0x1800539c6  dec     r11d
0x1800539c9  cmp     r11d, r8d
0x1800539cc  jge     short loc_1800539A0
0x1800539ce  lea     r8d, [r10+1]
0x1800539d2  cmp     r8d, r9d
0x1800539d5  jge     loc_1800538F7
0x1800539db  nop     dword ptr [rax+rax+00h]
0x1800539e0  movsxd  rax, r8d
0x1800539e3  lea     rcx, [rax+rax*4]
0x1800539e7  cmp     edi, [rsi+rcx*8]
0x1800539ea  lea     rdx, [rsi+rcx*8]
0x1800539ee  jnz     loc_1800538F7
0x1800539f4  mov     rax, [rbx]
0x1800539f7  cmp     rax, [rdx]
0x1800539fa  jnz     short loc_180053A0A
0x1800539fc  mov     rax, [rbx+8]
0x180053a00  cmp     rax, [rdx+8]
0x180053a04  jz      loc_1800538D3
0x180053a0a  inc     r8d
0x180053a0d  cmp     r8d, r9d
0x180053a10  jl      short loc_1800539E0
0x180053a12  jmp     loc_1800538F7
0x180053a17  mov     rcx, rbp; SRWLock
0x180053a1a  mov     dword ptr [rbp+8], 0
0x180053a21  call    cs:__imp_ReleaseSRWLockExclusive
0x180053a27  mov     eax, ebx
0x180053a29  mov     rbx, [rsp+28h+arg_18]
0x180053a2e  add     rsp, 20h
0x180053a32  pop     rbp
0x180053a33  retn
0x180053a34  mov     rcx, rbp; SRWLock
0x180053a37  call    cs:__imp_ReleaseSRWLockShared
0x180053a3d  mov     eax, ebx
0x180053a3f  mov     rbx, [rsp+28h+arg_18]
0x180053a44  add     rsp, 20h
0x180053a48  pop     rbp
0x180053a49  retn
```
