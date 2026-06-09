# CMemPropStore::Read(ushort const *,tagVARIANT *,IErrorLog *)

- ea: `0x180014ef0`
- end: `0x18001515b`
- name: `?Read@CMemPropStore@@UEAAJPEBGPEAUtagVARIANT@@PEAUIErrorLog@@@Z`
- size: `619`
- prototype: `int(CMemPropStore *__hidden this, const unsigned __int16 *, struct tagVARIANT *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180013cc0`
- `0x180014ef0`
- `0x180015170`
- `0x1800156fc`
- `0x18006ed20`
- `0x18006fb74`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001505e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001505e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014f6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014f6b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001503f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18001503f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800150aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800150aa`
- `OLEAUT32!__imp_VariantClear` at `0x180015098`
- `OLEAUT32!__imp_VariantClear` at `0x180015098`

## pseudocode

```c
__int64 __fastcall CMemPropStore::Read(
        CMemPropStore *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3,
        struct IErrorLog *a4)
{
  HRESULT v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // r12d
  __int64 (__fastcall *v11)(const unsigned __int16 *, _QWORD, _QWORD); // rax
  unsigned int v12; // r8d
  unsigned __int64 i; // r9
  int v14; // edx
  unsigned int v15; // eax
  __int64 *v16; // rsi
  HRESULT PropertyFromPropertyStorage; // eax
  __int64 v18; // rcx
  const struct tagSERIALIZEDPROPSTORAGE *v20; // rcx
  int *v21; // [rsp+20h] [rbp-68h]
  PROPVARIANT pvarDest[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v23; // [rsp+40h] [rbp-48h]

  v7 = -2147467261;
  if ( !a2 )
    return (unsigned int)v7;
  if ( !a3 )
    return (unsigned int)v7;
  v7 = -2147024809;
  if ( !*a2 )
    return (unsigned int)v7;
  v8 = *((_QWORD *)this + 23);
  v23 = 0;
  *(_OWORD *)pvarDest = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64, const unsigned __int16 *, struct tagVARIANT *, struct IErrorLog *))(*(_QWORD *)v8 + 24LL))(
      v8,
      a2,
      a3,
      a4);
  else
    AcquireSRWLockShared((PSRWLOCK)this + 26);
  if ( *((_BYTE *)this + 201) || (v20 = (const struct tagSERIALIZEDPROPSTORAGE *)*((_QWORD *)this + 20)) == 0 )
  {
    v7 = 0;
    LOWORD(pvarDest[0]) = 0;
    if ( !*((_QWORD *)this + 13) )
      goto LABEL_22;
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    v10 = 2 * v9 + 2;
    v11 = (__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 11);
    if ( v11 )
    {
      v15 = v11(a2, v10, *((unsigned int *)this + 25));
    }
    else
    {
      v12 = 314159269;
      for ( i = 0; i < v10; v12 ^= (v12 >> 2) + 2080 * v12 + v14 )
        v14 = *((unsigned __int8 *)a2 + i++);
      v15 = (v12 & 0x7FFFFFFF) % *((_DWORD *)this + 25);
    }
    v16 = *(__int64 **)(*((_QWORD *)this + 13) + 8LL * v15);
    if ( !v16 )
      goto LABEL_22;
    do
    {
      if ( v10 == *((_DWORD *)v16 + 2) && !memcmp_0(a2, (char *)v16 + *((unsigned int *)this + 30), v10) )
        break;
      v16 = (__int64 *)*v16;
    }
    while ( v16 );
    if ( !v16 || *((_DWORD *)this + 28) != 8 )
      goto LABEL_22;
    PropertyFromPropertyStorage = PropVariantCopy(
                                    pvarDest,
                                    *(const PROPVARIANT **)((char *)v16 + *((unsigned int *)this + 29)));
    goto LABEL_21;
  }
  *(_OWORD *)pvarDest = 0;
  v23 = 0;
  if ( *a2 )
  {
    PropertyFromPropertyStorage = _GetPropertyFromPropertyStorage(
                                    v20,
                                    *((_DWORD *)this + 42),
                                    &PKEY_UserDefinedProperties,
                                    a2,
                                    v21,
                                    pvarDest);
LABEL_21:
    v7 = PropertyFromPropertyStorage;
  }
LABEL_22:
  v18 = *((_QWORD *)this + 23);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
  else
    ReleaseSRWLockShared((PSRWLOCK)this + 26);
  if ( v7 >= 0 )
  {
    if ( LOWORD(pvarDest[0]) )
    {
      v7 = PropVariantToVariant(pvarDest, a3);
      if ( v7 >= 0 )
      {
        v7 = VariantChangeTypeForRead(a3);
        if ( v7 < 0 )
          VariantClear(a3);
      }
    }
    else
    {
      v7 = -2147467259;
    }
    PropVariantClear(pvarDest);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180014ef0  mov     [rsp+arg_18], rbx
0x180014ef5  push    rbp
0x180014ef6  push    rsi
0x180014ef7  push    rdi
0x180014ef8  push    r12
0x180014efa  push    r13
0x180014efc  push    r14
0x180014efe  push    r15
0x180014f00  sub     rsp, 50h
0x180014f04  mov     rax, cs:__security_cookie
0x180014f0b  xor     rax, rsp
0x180014f0e  mov     [rsp+88h+var_40], rax
0x180014f13  xor     r13d, r13d
0x180014f16  mov     r14, r8
0x180014f19  mov     rbp, rdx
0x180014f1c  mov     rdi, rcx
0x180014f1f  mov     ebx, 80004003h
0x180014f24  test    rdx, rdx
0x180014f27  jz      loc_1800150B0
0x180014f2d  test    r8, r8
0x180014f30  jz      loc_1800150B0
0x180014f36  mov     ebx, 80070057h
0x180014f3b  cmp     [rdx], r13w
0x180014f3f  jz      loc_1800150B0
0x180014f45  mov     rcx, [rcx+0B8h]
0x180014f4c  xor     eax, eax
0x180014f4e  mov     [rsp+88h+var_48], rax
0x180014f53  xorps   xmm0, xmm0
0x180014f56  movups  xmmword ptr [rsp+88h+pvarDest], xmm0
0x180014f5b  test    rcx, rcx
0x180014f5e  jnz     loc_180015125
0x180014f64  lea     rcx, [rdi+0D0h]; SRWLock
0x180014f6b  call    cs:__imp_AcquireSRWLockShared
0x180014f71  cmp     [rdi+0C9h], r13b
0x180014f78  jz      loc_1800150D7
0x180014f7e  mov     ebx, r13d
0x180014f81  mov     word ptr [rsp+88h+pvarDest], r13w
0x180014f87  cmp     [rdi+68h], r13
0x180014f8b  jz      loc_180015047
0x180014f91  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014f95  inc     rax
0x180014f98  cmp     [rbp+rax*2+0], r13w
0x180014f9e  jnz     short loc_180014F95
0x180014fa0  lea     r12d, ds:2[rax*2]
0x180014fa8  mov     rax, [rdi+58h]
0x180014fac  mov     r15d, r12d
0x180014faf  test    rax, rax
0x180014fb2  jnz     loc_180015147
0x180014fb8  mov     r8d, 12B9B0A5h
0x180014fbe  mov     r9, r13
0x180014fc1  test    r12d, r12d
0x180014fc4  jz      short loc_180014FE7
0x180014fc6  movzx   edx, byte ptr [r9+rbp]
0x180014fcb  mov     ecx, r8d
0x180014fce  imul    eax, r8d, 820h
0x180014fd5  inc     r9
0x180014fd8  shr     ecx, 2
0x180014fdb  add     edx, eax
0x180014fdd  add     edx, ecx
0x180014fdf  xor     r8d, edx
0x180014fe2  cmp     r9, r15
0x180014fe5  jb      short loc_180014FC6
0x180014fe7  btr     r8d, 1Fh
0x180014fec  xor     edx, edx
0x180014fee  mov     eax, r8d
0x180014ff1  div     dword ptr [rdi+64h]
0x180014ff4  mov     eax, edx
0x180014ff6  mov     ecx, eax
0x180014ff8  mov     rax, [rdi+68h]
0x180014ffc  mov     rsi, [rax+rcx*8]
0x180015000  test    rsi, rsi
0x180015003  jz      short loc_180015047
0x180015005  cmp     r12d, [rsi+8]
0x180015009  jnz     short loc_180015020
0x18001500b  mov     edx, [rdi+78h]
0x18001500e  mov     r8, r15; Size
0x180015011  add     rdx, rsi; Buf2
0x180015014  mov     rcx, rbp; Buf1
0x180015017  call    memcmp_0
0x18001501c  test    eax, eax
0x18001501e  jz      short loc_180015028
0x180015020  mov     rsi, [rsi]
0x180015023  test    rsi, rsi
0x180015026  jnz     short loc_180015005
0x180015028  test    rsi, rsi
0x18001502b  jz      short loc_180015047
0x18001502d  cmp     dword ptr [rdi+70h], 8
0x180015031  jnz     short loc_180015047
0x180015033  mov     eax, [rdi+74h]
0x180015036  lea     rcx, [rsp+88h+pvarDest]; pvarDest
0x18001503b  mov     rdx, [rax+rsi]; pvarSrc
0x18001503f  call    cs:__imp_PropVariantCopy
0x180015045  mov     ebx, eax
0x180015047  mov     rcx, [rdi+0B8h]
0x18001504e  test    rcx, rcx
0x180015051  jnz     loc_180015136
0x180015057  lea     rcx, [rdi+0D0h]; SRWLock
0x18001505e  call    cs:__imp_ReleaseSRWLockShared
0x180015064  test    ebx, ebx
0x180015066  js      short loc_1800150B0
0x180015068  cmp     r13w, word ptr [rsp+88h+pvarDest]
0x18001506e  jz      short loc_1800150A0
0x180015070  mov     rdx, r14; pVar
0x180015073  lea     rcx, [rsp+88h+pvarDest]; pPropVar
0x180015078  call    PropVariantToVariant
0x18001507d  mov     ebx, eax
0x18001507f  test    eax, eax
0x180015081  js      short loc_1800150A5
0x180015083  movzx   edx, word ptr [r14]
0x180015087  mov     rcx, r14; pvargDest
0x18001508a  call    VariantChangeTypeForRead
0x18001508f  mov     ebx, eax
0x180015091  test    eax, eax
0x180015093  jns     short loc_1800150A5
0x180015095  mov     rcx, r14; pvarg
0x180015098  call    cs:__imp_VariantClear
0x18001509e  jmp     short loc_1800150A5
0x1800150a0  mov     ebx, 80004005h
0x1800150a5  lea     rcx, [rsp+88h+pvarDest]; pvar
0x1800150aa  call    cs:__imp_PropVariantClear
0x1800150b0  mov     eax, ebx
0x1800150b2  mov     rcx, [rsp+88h+var_40]
0x1800150b7  xor     rcx, rsp; StackCookie
0x1800150ba  call    __security_check_cookie
0x1800150bf  mov     rbx, [rsp+88h+arg_18]
0x1800150c7  add     rsp, 50h
0x1800150cb  pop     r15
0x1800150cd  pop     r14
0x1800150cf  pop     r13
0x1800150d1  pop     r12
0x1800150d3  pop     rdi
0x1800150d4  pop     rsi
0x1800150d5  pop     rbp
0x1800150d6  retn
0x1800150d7  mov     rcx, [rdi+0A0h]; struct tagSERIALIZEDPROPSTORAGE *
0x1800150de  test    rcx, rcx
0x1800150e1  jz      loc_180014F7E
0x1800150e7  xor     eax, eax
0x1800150e9  xorps   xmm0, xmm0
0x1800150ec  movups  xmmword ptr [rsp+88h+pvarDest], xmm0
0x1800150f1  mov     [rsp+88h+var_48], rax
0x1800150f6  cmp     [rbp+0], r13w
0x1800150fb  jz      loc_180015047
0x180015101  mov     edx, [rdi+0A8h]; unsigned int
0x180015107  lea     rax, [rsp+88h+pvarDest]
0x18001510c  mov     r9, rbp; unsigned __int16 *
0x18001510f  mov     [rsp+88h+var_60], rax; struct tagPROPVARIANT *
0x180015114  lea     r8, PKEY_UserDefinedProperties; struct _tagpropertykey *
0x18001511b  call    ?_GetPropertyFromPropertyStorage@@YAJPEFBUtagSERIALIZEDPROPSTORAGE@@KAEBU_tagpropertykey@@PEBGPEAHPEAUtagPROPVARIANT@@@Z; _GetPropertyFromPropertyStorage(tagSERIALIZEDPROPSTORAGE const *,ulong,_tagpropertykey const &,ushort const *,int *,tagPROPVARIANT *)
0x180015120  jmp     loc_180015045
0x180015125  mov     rax, [rcx]
0x180015128  mov     rax, [rax+18h]
0x18001512c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015131  jmp     loc_180014F71
0x180015136  mov     rax, [rcx]
0x180015139  mov     rax, [rax+20h]
0x18001513d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015142  jmp     loc_180015064
0x180015147  mov     r8d, [rdi+64h]
0x18001514b  mov     edx, r12d
0x18001514e  mov     rcx, rbp
0x180015151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015156  jmp     loc_180014FF6
```
