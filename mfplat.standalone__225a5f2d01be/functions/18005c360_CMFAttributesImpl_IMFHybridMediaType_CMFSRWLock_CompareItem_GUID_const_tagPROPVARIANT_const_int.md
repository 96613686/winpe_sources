# CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::CompareItem(_GUID const &,tagPROPVARIANT const &,int *)

- ea: `0x18005c360`
- end: `0x18005c5f9`
- name: `?CompareItem@?$CMFAttributesImpl@UIMFHybridMediaType@@VCMFSRWLock@@@@UEAAJAEBU_GUID@@AEBUtagPROPVARIANT@@PEAH@Z`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180148f30`

## callees

- `0x18005c360`
- `0x180121575`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005c399`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005c399`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c5d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c5d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005c5e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005c5e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c37d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c5b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c37d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c5b4`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFHybridMediaType,CMFSRWLock>::CompareItem(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        int *a4)
{
  __int64 v5; // rbx
  int v9; // ebp
  int v10; // r8d
  unsigned int v11; // r11d
  int v12; // edx
  _QWORD *v13; // rcx
  double *v14; // rcx
  __int16 v15; // ax
  unsigned int v16; // eax
  bool v17; // zf
  __int64 v18; // rdi
  int v19; // r9d
  __int64 v20; // r10
  int i; // edx
  int j; // edx
  _QWORD *v23; // rdx
  _QWORD *v24; // rcx
  unsigned __int16 *v25; // rax
  __int64 v26; // r8
  int v27; // edx
  int v28; // ecx
  int v29; // eax

  v5 = a1 + 16;
  v9 = 1;
  if ( *(_DWORD *)(a1 + 24) == GetCurrentThreadId() )
    ++*(_DWORD *)(v5 + 12);
  else
    AcquireSRWLockShared((PSRWLOCK)v5);
  v10 = *(_DWORD *)(a1 + 44);
  if ( !v10 )
    goto LABEL_59;
  v11 = *a2;
  if ( v10 < 4 )
  {
    if ( v10 > 0 )
    {
      v12 = 0;
      while ( 1 )
      {
        v13 = (_QWORD *)(*(_QWORD *)(a1 + 32) + 40LL * v12);
        if ( *(_DWORD *)v13 == v11 )
        {
          if ( *(_QWORD *)a2 == *v13 && *((_QWORD *)a2 + 1) == v13[1] )
            goto LABEL_11;
        }
        else if ( *(_DWORD *)v13 > v11 )
        {
          goto LABEL_59;
        }
        if ( ++v12 >= v10 )
          goto LABEL_59;
      }
    }
    goto LABEL_59;
  }
  v18 = *(_QWORD *)(a1 + 32);
  v19 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v20 = (v19 + v10) / 2;
      v13 = (_QWORD *)(v18 + 40 * v20);
      if ( v11 >= *(_DWORD *)v13 )
        break;
      if ( (_DWORD)v20 == v19 )
        goto LABEL_59;
      v10 = (v19 + v10) / 2;
    }
    if ( v11 <= *(_DWORD *)v13 )
      break;
    v19 = v20 + 1;
    if ( (_DWORD)v20 + 1 == v10 )
      goto LABEL_59;
  }
  if ( *(_QWORD *)a2 != *v13 || *((_QWORD *)a2 + 1) != v13[1] )
  {
    if ( (int)v20 > v19 )
    {
      for ( i = v20 - 1; i >= v19; --i )
      {
        v13 = (_QWORD *)(v18 + 40LL * i);
        if ( v11 != *(_DWORD *)v13 )
          break;
        if ( *(_QWORD *)a2 == *v13 && *((_QWORD *)a2 + 1) == v13[1] )
          goto LABEL_11;
      }
    }
    for ( j = v20 + 1; j < v10; ++j )
    {
      v13 = (_QWORD *)(v18 + 40LL * j);
      if ( v11 != *(_DWORD *)v13 )
        break;
      if ( *(_QWORD *)a2 == *v13 && *((_QWORD *)a2 + 1) == v13[1] )
        goto LABEL_11;
    }
    goto LABEL_59;
  }
LABEL_11:
  v14 = (double *)(v13 + 2);
  if ( !v14 )
    goto LABEL_59;
  v15 = *(_WORD *)v14;
  if ( *(_WORD *)a3 != *(_WORD *)v14 )
    goto LABEL_59;
  switch ( v15 )
  {
    case 5:
      if ( v14[1] == *(double *)(a3 + 8) )
        goto LABEL_60;
      goto LABEL_59;
    case 13:
      goto LABEL_60;
    case 19:
      v17 = *((_DWORD *)v14 + 2) == *(_DWORD *)(a3 + 8);
      goto LABEL_50;
    case 21:
      v17 = *((_QWORD *)v14 + 1) == *(_QWORD *)(a3 + 8);
      goto LABEL_50;
    case 31:
      v25 = (unsigned __int16 *)*((_QWORD *)v14 + 1);
      v26 = *(_QWORD *)(a3 + 8) - (_QWORD)v25;
      do
      {
        v27 = *(unsigned __int16 *)((char *)v25 + v26);
        v28 = *v25 - v27;
        if ( v28 )
          break;
        ++v25;
      }
      while ( v27 );
      v17 = v28 == 0;
      goto LABEL_50;
    case 72:
      v23 = (_QWORD *)*((_QWORD *)v14 + 1);
      v24 = *(_QWORD **)(a3 + 8);
      if ( *v23 == *v24 )
      {
        v17 = v23[1] == v24[1];
        goto LABEL_50;
      }
LABEL_59:
      v9 = 0;
      goto LABEL_60;
  }
  if ( v15 != 4113 )
    goto LABEL_60;
  v16 = *((_DWORD *)v14 + 2);
  if ( v16 != *(_DWORD *)(a3 + 8) )
    goto LABEL_59;
  v17 = memcmp_0(*((const void **)v14 + 2), *(const void **)(a3 + 16), v16) == 0;
LABEL_50:
  if ( !v17 )
    goto LABEL_59;
LABEL_60:
  *a4 = v9;
  if ( *(_DWORD *)(v5 + 8) == GetCurrentThreadId() )
  {
    v29 = *(_DWORD *)(v5 + 12);
    if ( v29 )
    {
      *(_DWORD *)(v5 + 12) = v29 - 1;
    }
    else
    {
      *(_DWORD *)(v5 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v5);
    }
  }
  else
  {
    ReleaseSRWLockShared((PSRWLOCK)v5);
  }
  return 0;
}

```

## disassembly

```asm
0x18005c360  push    rbx
0x18005c362  push    rbp
0x18005c363  push    rsi
0x18005c364  push    rdi
0x18005c365  push    r14
0x18005c367  push    r15
0x18005c369  sub     rsp, 28h
0x18005c36d  mov     r15, r9
0x18005c370  lea     rbx, [rcx+10h]
0x18005c374  mov     rsi, r8
0x18005c377  mov     r14, rdx
0x18005c37a  mov     rdi, rcx
0x18005c37d  call    cs:__imp_GetCurrentThreadId
0x18005c383  mov     r10d, [rbx+8]
0x18005c387  mov     ebp, 1
0x18005c38c  cmp     r10d, eax
0x18005c38f  jnz     short loc_18005C396
0x18005c391  add     [rbx+0Ch], ebp
0x18005c394  jmp     short loc_18005C39F
0x18005c396  mov     rcx, rbx; SRWLock
0x18005c399  call    cs:__imp_AcquireSRWLockShared
0x18005c39f  mov     r8d, [rdi+2Ch]
0x18005c3a3  test    r8d, r8d
0x18005c3a6  jz      loc_18005C5AF
0x18005c3ac  mov     r11d, [r14]
0x18005c3af  cmp     r8d, 4
0x18005c3b3  jge     loc_18005C48F
0x18005c3b9  test    r8d, r8d
0x18005c3bc  jle     loc_18005C5AF
0x18005c3c2  mov     r9, [rdi+20h]
0x18005c3c6  xor     edx, edx
0x18005c3c8  movsxd  rax, edx
0x18005c3cb  lea     rcx, [rax+rax*4]
0x18005c3cf  lea     rcx, [r9+rcx*8]
0x18005c3d3  cmp     [rcx], r11d
0x18005c3d6  jnz     loc_18005C479
0x18005c3dc  mov     rax, [r14]
0x18005c3df  cmp     rax, [rcx]
0x18005c3e2  jnz     loc_18005C47F
0x18005c3e8  mov     rax, [r14+8]
0x18005c3ec  cmp     rax, [rcx+8]
0x18005c3f0  jnz     loc_18005C47F
0x18005c3f6  add     rcx, 10h
0x18005c3fa  jz      loc_18005C5AF
0x18005c400  movzx   eax, word ptr [rcx]
0x18005c403  cmp     [rsi], ax
0x18005c406  jnz     loc_18005C5AF
0x18005c40c  cmp     ax, 5
0x18005c410  jz      loc_18005C5A1
0x18005c416  cmp     ax, 0Dh
0x18005c41a  jz      loc_18005C5B1
0x18005c420  cmp     ax, 13h
0x18005c424  jz      loc_18005C599
0x18005c42a  cmp     ax, 15h
0x18005c42e  jz      loc_18005C58F
0x18005c434  cmp     ax, 1Fh
0x18005c438  jz      loc_18005C56C
0x18005c43e  cmp     ax, 48h ; 'H'
0x18005c442  jz      loc_18005C550
0x18005c448  mov     edx, 1011h
0x18005c44d  cmp     ax, dx
0x18005c450  jnz     loc_18005C5B1
0x18005c456  mov     eax, [rcx+8]
0x18005c459  cmp     eax, [rsi+8]
0x18005c45c  jnz     loc_18005C5AF
0x18005c462  mov     rdx, [rsi+10h]; Buf2
0x18005c466  mov     r8d, eax; Size
0x18005c469  mov     rcx, [rcx+10h]; Buf1
0x18005c46d  call    memcmp_0
0x18005c472  test    eax, eax
0x18005c474  jmp     loc_18005C568
0x18005c479  ja      loc_18005C5AF
0x18005c47f  add     edx, ebp
0x18005c481  cmp     edx, r8d
0x18005c484  jl      loc_18005C3C8
0x18005c48a  jmp     loc_18005C5AF
0x18005c48f  mov     rdi, [rdi+20h]
0x18005c493  xor     r9d, r9d
0x18005c496  lea     eax, [r9+r8]
0x18005c49a  cdq
0x18005c49b  sub     eax, edx
0x18005c49d  sar     eax, 1
0x18005c49f  movsxd  r10, eax
0x18005c4a2  lea     rdx, [r10+r10*4]
0x18005c4a6  lea     rcx, [rdi+rdx*8]
0x18005c4aa  cmp     r11d, [rcx]
0x18005c4ad  jnb     short loc_18005C4BD
0x18005c4af  cmp     r10d, r9d
0x18005c4b2  jz      loc_18005C5AF
0x18005c4b8  mov     r8d, r10d
0x18005c4bb  jmp     short loc_18005C496
0x18005c4bd  jbe     short loc_18005C4CD
0x18005c4bf  lea     r9d, [r10+1]
0x18005c4c3  cmp     r9d, r8d
0x18005c4c6  jnz     short loc_18005C496
0x18005c4c8  jmp     loc_18005C5AF
0x18005c4cd  mov     rax, [r14]
0x18005c4d0  cmp     rax, [rcx]
0x18005c4d3  jnz     short loc_18005C4E3
0x18005c4d5  mov     rax, [r14+8]
0x18005c4d9  cmp     rax, [rcx+8]
0x18005c4dd  jz      loc_18005C3F6
0x18005c4e3  cmp     r10d, r9d
0x18005c4e6  jle     short loc_18005C51B
0x18005c4e8  lea     edx, [r10-1]
0x18005c4ec  jmp     short loc_18005C516
0x18005c4ee  movsxd  rax, edx
0x18005c4f1  lea     rcx, [rax+rax*4]
0x18005c4f5  lea     rcx, [rdi+rcx*8]
0x18005c4f9  cmp     r11d, [rcx]
0x18005c4fc  jnz     short loc_18005C51B
0x18005c4fe  mov     rax, [r14]
0x18005c501  cmp     rax, [rcx]
0x18005c504  jnz     short loc_18005C514
0x18005c506  mov     rax, [r14+8]
0x18005c50a  cmp     rax, [rcx+8]
0x18005c50e  jz      loc_18005C3F6
0x18005c514  sub     edx, ebp
0x18005c516  cmp     edx, r9d
0x18005c519  jge     short loc_18005C4EE
0x18005c51b  lea     edx, [r10+1]
0x18005c51f  jmp     short loc_18005C549
0x18005c521  movsxd  rax, edx
0x18005c524  lea     rcx, [rax+rax*4]
0x18005c528  lea     rcx, [rdi+rcx*8]
0x18005c52c  cmp     r11d, [rcx]
0x18005c52f  jnz     short loc_18005C5AF
0x18005c531  mov     rax, [r14]
0x18005c534  cmp     rax, [rcx]
0x18005c537  jnz     short loc_18005C547
0x18005c539  mov     rax, [r14+8]
0x18005c53d  cmp     rax, [rcx+8]
0x18005c541  jz      loc_18005C3F6
0x18005c547  add     edx, ebp
0x18005c549  cmp     edx, r8d
0x18005c54c  jl      short loc_18005C521
0x18005c54e  jmp     short loc_18005C5AF
0x18005c550  mov     rdx, [rcx+8]
0x18005c554  mov     rcx, [rsi+8]
0x18005c558  mov     rax, [rdx]
0x18005c55b  cmp     rax, [rcx]
0x18005c55e  jnz     short loc_18005C5AF
0x18005c560  mov     rax, [rdx+8]
0x18005c564  cmp     rax, [rcx+8]
0x18005c568  jnz     short loc_18005C5AF
0x18005c56a  jmp     short loc_18005C5B1
0x18005c56c  mov     rax, [rcx+8]
0x18005c570  mov     r8, [rsi+8]
0x18005c574  sub     r8, rax
0x18005c577  movzx   ecx, word ptr [rax]
0x18005c57a  movzx   edx, word ptr [rax+r8]
0x18005c57f  sub     ecx, edx
0x18005c581  jnz     short loc_18005C58B
0x18005c583  add     rax, 2
0x18005c587  test    edx, edx
0x18005c589  jnz     short loc_18005C577
0x18005c58b  test    ecx, ecx
0x18005c58d  jmp     short loc_18005C568
0x18005c58f  mov     rax, [rsi+8]
0x18005c593  cmp     [rcx+8], rax
0x18005c597  jmp     short loc_18005C568
0x18005c599  mov     eax, [rsi+8]
0x18005c59c  cmp     [rcx+8], eax
0x18005c59f  jmp     short loc_18005C568
0x18005c5a1  movsd   xmm0, qword ptr [rcx+8]
0x18005c5a6  ucomisd xmm0, qword ptr [rsi+8]
0x18005c5ab  jp      short loc_18005C5AF
0x18005c5ad  jz      short loc_18005C5B1
0x18005c5af  xor     ebp, ebp
0x18005c5b1  mov     [r15], ebp
0x18005c5b4  call    cs:__imp_GetCurrentThreadId
0x18005c5ba  mov     ecx, [rbx+8]
0x18005c5bd  cmp     ecx, eax
0x18005c5bf  jnz     short loc_18005C5E1
0x18005c5c1  mov     eax, [rbx+0Ch]
0x18005c5c4  test    eax, eax
0x18005c5c6  jz      short loc_18005C5CF
0x18005c5c8  dec     eax
0x18005c5ca  mov     [rbx+0Ch], eax
0x18005c5cd  jmp     short loc_18005C5EA
0x18005c5cf  mov     rcx, rbx; SRWLock
0x18005c5d2  mov     dword ptr [rbx+8], 0
0x18005c5d9  call    cs:__imp_ReleaseSRWLockExclusive
0x18005c5df  jmp     short loc_18005C5EA
0x18005c5e1  mov     rcx, rbx; SRWLock
0x18005c5e4  call    cs:__imp_ReleaseSRWLockShared
0x18005c5ea  xor     eax, eax
0x18005c5ec  add     rsp, 28h
0x18005c5f0  pop     r15
0x18005c5f2  pop     r14
0x18005c5f4  pop     rdi
0x18005c5f5  pop     rsi
0x18005c5f6  pop     rbp
0x18005c5f7  pop     rbx
0x18005c5f8  retn
```
