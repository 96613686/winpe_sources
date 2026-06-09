# CCharFormatArray::Cache(CCharFormat const *,short *)

- ea: `0x180058ab0`
- end: `0x180058d29`
- name: `?Cache@CCharFormatArray@@UEAAJPEBVCCharFormat@@PEAF@Z`
- size: `633`
- prototype: `int(CCharFormatArray *__hidden this, const struct CCharFormat *, __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000e2e4`
- `0x180057560`
- `0x180058ab0`
- `0x18005912c`
- `0x18005921c`
- `0x1800a0150`
- `0x18013dcc2`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180058c68`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180058c68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058ae0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058c74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058ae0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058c74`

## pseudocode

```c
__int64 __fastcall CCharFormatArray::Cache(CCharFormatArray *this, const struct CCharFormat *a2, __int16 *a3)
{
  int v3; // ebx
  _DWORD *LockTelemetry; // rax
  char v8; // r12
  __int64 v9; // rbp
  int v10; // ebx
  const void *v11; // rcx
  CFixArrayBase *v12; // rdi
  const void *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  RTL_SRWLOCK *Lock; // rax
  __int64 v19; // rax
  __int16 v20; // ax
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm2
  __int128 v24; // xmm3
  _OWORD *v25; // rax
  int v26; // r10d
  int v27; // [rsp+78h] [rbp+10h] BYREF

  v3 = (int)CLockSharedData::LockOwner;
  v27 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v3 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v19 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v19 + 4);
  }
  v8 = *((_BYTE *)a2 + 6);
  v9 = v8 & 0xF;
  if ( v8 == *((_BYTE *)qword_1802E4A80 + 4 * v9)
    && (LOWORD(v10) = *((_WORD *)qword_1802E4A80 + 2 * v9 + 1) - 1, (v10 & 0x8000u) == 0)
    && (__int16)v10 < *((_DWORD *)this + 5)
    && (*(int (__fastcall **)(CCharFormatArray *, _QWORD))(*(_QWORD *)this + 16LL))(this, (unsigned int)(__int16)v10) > 0
    && ((unsigned int)(__int16)v10 >= *((_DWORD *)this + 5)
      ? (v11 = 0)
      : (v11 = (const void *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * ((__int16)v10 / 16))
                            + *((_DWORD *)this + 7) * ((__int16)v10 % 16))),
        !memcmp_0(v11, a2, 0x44u)) )
  {
    v12 = (CCharFormatArray *)((char *)this + 8);
LABEL_20:
    v14 = *((_DWORD *)v12 + 5) * ((v10 & 0xF) + 1);
    v15 = *(_QWORD *)(*(_QWORD *)v12 + 8 * ((unsigned __int64)(unsigned __int16)v10 >> 4));
    ++*(_DWORD *)(v14 + v15 - 4);
  }
  else
  {
    for ( LOWORD(v10) = 0; ; LOWORD(v10) = v10 + 1 )
    {
      if ( (__int16)v10 >= *((_DWORD *)this + 5) )
      {
        v12 = (CCharFormatArray *)((char *)this + 8);
        goto LABEL_27;
      }
      if ( (*(int (__fastcall **)(CCharFormatArray *, _QWORD))(*(_QWORD *)this + 16LL))(
             this,
             (unsigned int)(__int16)v10) > 0 )
      {
        v13 = (unsigned int)(__int16)v10 >= *((_DWORD *)this + 5)
            ? 0LL
            : (const void *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * ((__int16)v10 / 16))
                           + *((_DWORD *)this + 7) * ((__int16)v10 % 16));
        if ( !memcmp_0(v13, a2, 0x44u) )
          break;
      }
    }
    v12 = (CCharFormatArray *)((char *)this + 8);
    *((_BYTE *)qword_1802E4A80 + 4 * v9) = v8;
    *((_WORD *)qword_1802E4A80 + 2 * v9 + 1) = v10 + 1;
    if ( (v10 & 0x8000u) == 0 )
      goto LABEL_20;
LABEL_27:
    v20 = CFixArrayBase::Add(v12);
    v10 = v20;
    if ( v20 < 0 )
    {
      v16 = -2147024882;
      goto LABEL_24;
    }
    v21 = *(_OWORD *)a2;
    v22 = *((_OWORD *)a2 + 1);
    v23 = *((_OWORD *)a2 + 2);
    v24 = *((_OWORD *)a2 + 3);
    v25 = CFixArrayBase::Elem(v12, v20);
    *v25 = v21;
    v25[1] = v22;
    v25[2] = v23;
    v25[3] = v24;
    *((_DWORD *)v25 + 16) = v26;
    *(_DWORD *)(*((_DWORD *)v12 + 5) * (v10 % 16 + 1) + *(_QWORD *)(*(_QWORD *)v12 + 8LL * (v10 / 16)) - 4LL) = 1;
  }
  if ( a3 )
    *a3 = v10;
  v16 = 0;
LABEL_24:
  CWriteLock::~CWriteLock((CWriteLock *)&v27);
  return v16;
}

```

## disassembly

```asm
0x180058ab0  push    rbx
0x180058ab2  push    rbp
0x180058ab3  push    rsi
0x180058ab4  push    rdi
0x180058ab5  push    r12
0x180058ab7  push    r13
0x180058ab9  push    r14
0x180058abb  push    r15
0x180058abd  sub     rsp, 28h
0x180058ac1  mov     ebx, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180058ac7  xor     r14d, r14d
0x180058aca  mov     [rsp+68h+arg_8], r14d
0x180058acf  mov     r13, r8
0x180058ad2  mov     r15, rdx
0x180058ad5  mov     rdi, rcx
0x180058ad8  test    ebx, ebx
0x180058ada  jz      loc_180058C5E
0x180058ae0  call    cs:__imp_GetCurrentThreadId
0x180058ae7  nop     dword ptr [rax+rax+00h]
0x180058aec  cmp     ebx, eax
0x180058aee  jnz     loc_180058C5E
0x180058af4  xor     ecx, ecx
0x180058af6  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180058afb  lea     esi, [r14+1]
0x180058aff  add     [rax], esi
0x180058b01  movzx   r12d, byte ptr [r15+6]
0x180058b06  lea     rax, qword_1802E4A80
0x180058b0d  mov     ebp, r12d
0x180058b10  and     ebp, 0Fh
0x180058b13  cmp     r12b, [rax+rbp*4]
0x180058b17  jnz     short loc_180058B8B
0x180058b19  movzx   ebx, word ptr [rax+rbp*4+2]
0x180058b1e  sub     bx, si
0x180058b21  js      short loc_180058B8B
0x180058b23  movsx   r14d, bx
0x180058b27  cmp     r14d, [rdi+14h]
0x180058b2b  jge     short loc_180058B88
0x180058b2d  mov     rax, [rdi]
0x180058b30  mov     edx, r14d
0x180058b33  mov     rcx, rdi
0x180058b36  mov     rax, [rax+10h]
0x180058b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b3f  test    eax, eax
0x180058b41  jle     short loc_180058B88
0x180058b43  cmp     r14d, [rdi+14h]
0x180058b47  jnb     loc_180058D13
0x180058b4d  mov     eax, r14d
0x180058b50  mov     ecx, 10h
0x180058b55  cdq
0x180058b56  idiv    ecx
0x180058b58  imul    edx, [rdi+1Ch]
0x180058b5c  movsxd  r8, eax
0x180058b5f  mov     rax, [rdi+8]
0x180058b63  movsxd  rcx, edx
0x180058b66  add     rcx, [rax+r8*8]; Buf1
0x180058b6a  xor     r14d, r14d
0x180058b6d  mov     r8d, 44h ; 'D'; Size
0x180058b73  mov     rdx, r15; Buf2
0x180058b76  call    memcmp_0
0x180058b7b  test    eax, eax
0x180058b7d  jnz     short loc_180058B8B
0x180058b7f  add     rdi, 8
0x180058b83  jmp     loc_180058C13
0x180058b88  xor     r14d, r14d
0x180058b8b  mov     ebx, r14d
0x180058b8e  movsx   r14d, bx
0x180058b92  cmp     r14d, [rdi+14h]
0x180058b96  jge     loc_180058C9A
0x180058b9c  mov     rax, [rdi]
0x180058b9f  mov     edx, r14d
0x180058ba2  mov     rcx, rdi
0x180058ba5  mov     rax, [rax+10h]
0x180058ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058bae  test    eax, eax
0x180058bb0  jle     short loc_180058BEE
0x180058bb2  cmp     r14d, [rdi+14h]
0x180058bb6  jnb     loc_180058D1E
0x180058bbc  mov     eax, r14d
0x180058bbf  mov     ecx, 10h
0x180058bc4  cdq
0x180058bc5  idiv    ecx
0x180058bc7  imul    edx, [rdi+1Ch]
0x180058bcb  movsxd  r8, eax
0x180058bce  mov     rax, [rdi+8]
0x180058bd2  movsxd  rcx, edx
0x180058bd5  add     rcx, [rax+r8*8]; Buf1
0x180058bd9  xor     r14d, r14d
0x180058bdc  mov     r8d, 44h ; 'D'; Size
0x180058be2  mov     rdx, r15; Buf2
0x180058be5  call    memcmp_0
0x180058bea  test    eax, eax
0x180058bec  jz      short loc_180058BF3
0x180058bee  add     bx, si
0x180058bf1  jmp     short loc_180058B8E
0x180058bf3  lea     rcx, qword_1802E4A80
0x180058bfa  add     rdi, 8
0x180058bfe  mov     [rcx+rbp*4], r12b
0x180058c02  lea     eax, [rsi+rbx]
0x180058c05  mov     [rcx+rbp*4+2], ax
0x180058c0a  test    bx, bx
0x180058c0d  js      loc_180058CA1
0x180058c13  movzx   ecx, bx
0x180058c16  mov     eax, ecx
0x180058c18  shr     rcx, 4
0x180058c1c  and     eax, 0Fh
0x180058c1f  add     eax, esi
0x180058c21  imul    eax, [rdi+14h]
0x180058c25  movsxd  rdx, eax
0x180058c28  mov     rax, [rdi]
0x180058c2b  mov     rcx, [rax+rcx*8]
0x180058c2f  add     [rdx+rcx-4], esi
0x180058c33  test    r13, r13
0x180058c36  jz      short loc_180058C3D
0x180058c38  mov     [r13+0], bx
0x180058c3d  mov     ebx, r14d
0x180058c40  lea     rcx, [rsp+68h+arg_8]; this
0x180058c45  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180058c4a  mov     eax, ebx
0x180058c4c  add     rsp, 28h
0x180058c50  pop     r15
0x180058c52  pop     r14
0x180058c54  pop     r13
0x180058c56  pop     r12
0x180058c58  pop     rdi
0x180058c59  pop     rsi
0x180058c5a  pop     rbp
0x180058c5b  pop     rbx
0x180058c5c  retn
0x180058c5e  xor     ecx, ecx
0x180058c60  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180058c65  mov     rcx, rax; SRWLock
0x180058c68  call    cs:__imp_AcquireSRWLockExclusive
0x180058c6f  nop     dword ptr [rax+rax+00h]
0x180058c74  call    cs:__imp_GetCurrentThreadId
0x180058c7b  nop     dword ptr [rax+rax+00h]
0x180058c80  xor     ecx, ecx
0x180058c82  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x180058c88  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180058c8d  mov     esi, 1
0x180058c92  add     [rax+4], esi
0x180058c95  jmp     loc_180058B01
0x180058c9a  add     rdi, 8
0x180058c9e  xor     r14d, r14d
0x180058ca1  mov     rcx, rdi; this
0x180058ca4  call    ?Add@CFixArrayBase@@QEAAFXZ; CFixArrayBase::Add(void)
0x180058ca9  movsx   ebx, ax
0x180058cac  test    bx, bx
0x180058caf  jns     short loc_180058CB8
0x180058cb1  mov     ebx, 8007000Eh
0x180058cb6  jmp     short loc_180058C40
0x180058cb8  movups  xmm0, xmmword ptr [r15]
0x180058cbc  mov     r10d, [r15+40h]
0x180058cc0  mov     edx, ebx; int
0x180058cc2  movups  xmm1, xmmword ptr [r15+10h]
0x180058cc7  mov     rcx, rdi; this
0x180058cca  movups  xmm2, xmmword ptr [r15+20h]
0x180058ccf  movups  xmm3, xmmword ptr [r15+30h]
0x180058cd4  call    ?Elem@CFixArrayBase@@QEBAPEAXJ@Z; CFixArrayBase::Elem(long)
0x180058cd9  mov     ecx, 10h
0x180058cde  movups  xmmword ptr [rax], xmm0
0x180058ce1  movups  xmmword ptr [rax+10h], xmm1
0x180058ce5  movups  xmmword ptr [rax+20h], xmm2
0x180058ce9  movups  xmmword ptr [rax+30h], xmm3
0x180058ced  mov     [rax+40h], r10d
0x180058cf1  mov     eax, ebx
0x180058cf3  cdq
0x180058cf4  idiv    ecx
0x180058cf6  movsxd  rcx, eax
0x180058cf9  inc     edx
0x180058cfb  imul    edx, [rdi+14h]
0x180058cff  mov     rax, [rdi]
0x180058d02  mov     rcx, [rax+rcx*8]
0x180058d06  movsxd  r8, edx
0x180058d09  mov     [r8+rcx-4], esi
0x180058d0e  jmp     loc_180058C33
0x180058d13  xor     r14d, r14d
0x180058d16  mov     ecx, r14d
0x180058d19  jmp     loc_180058B6D
0x180058d1e  xor     r14d, r14d
0x180058d21  mov     ecx, r14d
0x180058d24  jmp     loc_180058BDC
```
