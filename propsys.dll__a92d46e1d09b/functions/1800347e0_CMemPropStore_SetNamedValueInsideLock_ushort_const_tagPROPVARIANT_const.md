# CMemPropStore::_SetNamedValueInsideLock(ushort const *,tagPROPVARIANT const &)

- ea: `0x1800347e0`
- end: `0x180034c0a`
- name: `?_SetNamedValueInsideLock@CMemPropStore@@AEAAJPEBGAEBUtagPROPVARIANT@@@Z`
- size: `1066`
- prototype: `int(CMemPropStore *__hidden this, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800113a0`

## callees

- `0x18000f050`
- `0x1800347e0`
- `0x180034c10`
- `0x18006fb74`
- `0x18006fb80`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034960`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003497d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034b54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034960`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003497d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034b54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800349c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034b03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800349c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034b03`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800349ef`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800349ef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800349bf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034afa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800349bf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034afa`

## pseudocode

```c
__int64 __fastcall CMemPropStore::_SetNamedValueInsideLock(
        CMemPropStore *this,
        const unsigned __int16 *a2,
        const PROPVARIANT *a3)
{
  __int64 v6; // rbp
  unsigned int v7; // ebx
  __int64 v8; // rax
  bool v9; // zf
  unsigned int v10; // r9d
  unsigned int v11; // r15d
  __int64 (__fastcall *v12)(const unsigned __int16 *, _QWORD, _QWORD); // rax
  unsigned __int64 v13; // r8
  unsigned int i; // eax
  int v15; // edx
  unsigned int v16; // eax
  __int64 *v17; // r14
  _QWORD *v18; // r15
  HLOCAL v19; // rax
  PROPVARIANT *v20; // rax
  PROPVARIANT *v21; // rsi
  HRESULT v23; // r14d
  unsigned int v24; // r9d
  unsigned int v25; // r10d
  size_t v26; // rsi
  unsigned __int64 v27; // r8
  int v28; // edx
  unsigned int v29; // ebp
  __int64 v30; // r12
  __int64 *v31; // rbx
  PROPVARIANT *v32; // rdi
  __int64 v33; // rax
  _DWORD *v34; // rbx
  unsigned int v35; // eax
  unsigned int v36; // [rsp+20h] [rbp-58h]
  PROPVARIANT *v37; // [rsp+28h] [rbp-50h]
  PROPVARIANT *Src; // [rsp+30h] [rbp-48h] BYREF
  PROPVARIANT *pvar; // [rsp+38h] [rbp-40h]

  v6 = -1;
  v7 = 314159269;
  if ( (*((_BYTE *)this + 184) & 2) == 0 )
    goto LABEL_14;
  if ( !*((_QWORD *)this + 18) )
    goto LABEL_21;
  v8 = -1;
  do
    v9 = a2[++v8] == 0;
  while ( !v9 );
  v10 = *((_DWORD *)this + 35);
  v11 = 2 * v8 + 2;
  v12 = (__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 16);
  Src = 0;
  if ( v12 )
  {
    v16 = v12(a2, v11, v10);
  }
  else
  {
    v13 = 0;
    for ( i = 314159269; v13 < v11; i ^= (i >> 2) + 2080 * i + v15 )
      v15 = *((unsigned __int8 *)a2 + v13++);
    v16 = (i & 0x7FFFFFFF) % v10;
  }
  v17 = *(__int64 **)(*((_QWORD *)this + 18) + 8LL * v16);
  if ( !v17 )
    goto LABEL_21;
  while ( v11 != *((_DWORD *)v17 + 2) || memcmp_0(a2, (char *)v17 + *((unsigned int *)this + 40), v11) )
  {
    v17 = (__int64 *)*v17;
    if ( !v17 )
      goto LABEL_21;
  }
  if ( *((_DWORD *)this + 38) != 8 )
  {
LABEL_21:
    if ( !*(_WORD *)a3 )
      return 1;
LABEL_14:
    v18 = (_QWORD *)((char *)this + 128);
    if ( !*((_QWORD *)this + 18) )
    {
      *((_DWORD *)this + 38) = 8;
      *v18 = 0;
      *((_DWORD *)this + 39) = 16;
      *((_DWORD *)this + 40) = 24;
      *((_QWORD *)this + 18) = 0;
      Src = 0;
      if ( !is_mul_ok(0x17u, 8u) )
        return 2147942414LL;
      v19 = LocalAlloc(0x40u, 0xB8u);
      *((_QWORD *)this + 18) = v19;
      if ( !v19 )
        return 2147942414LL;
      *((_DWORD *)this + 35) = 23;
    }
    v20 = (PROPVARIANT *)LocalAlloc(0x40u, 0x18u);
    v37 = v20;
    v21 = v20;
    if ( !v20 )
      return 2147942414LL;
    v23 = PropVariantCopy(v20, a3);
    if ( v23 < 0 )
      goto LABEL_24;
    Src = v21;
    do
      v9 = a2[++v6] == 0;
    while ( !v9 );
    pvar = 0;
    if ( !*((_QWORD *)this + 18) )
    {
      v23 = -2147467259;
LABEL_24:
      PropVariantClear(v21);
      LocalFree(v21);
      return (unsigned int)v23;
    }
    v24 = 2 * v6 + 2;
    v25 = *((_DWORD *)this + 35);
    v36 = v24;
    v26 = v24;
    if ( *v18 )
    {
      v35 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, _QWORD))*v18)(a2, v24, v25);
      v24 = 2 * v6 + 2;
      v29 = v35;
    }
    else
    {
      v27 = 0;
      if ( 2 * (_DWORD)v6 != -2 )
      {
        do
        {
          v28 = *((unsigned __int8 *)a2 + v27++);
          v7 ^= (v7 >> 2) + 2080 * v7 + v28;
        }
        while ( v27 < v24 );
      }
      v29 = (v7 & 0x7FFFFFFF) % v25;
    }
    v30 = 8LL * v29;
    v31 = *(__int64 **)(v30 + *((_QWORD *)this + 18));
    if ( !v31 )
      goto LABEL_40;
    do
    {
      if ( v24 == *((_DWORD *)v31 + 2) )
      {
        if ( !memcmp_0(a2, (char *)v31 + *((unsigned int *)this + 40), v26) )
          break;
        v24 = v36;
      }
      v31 = (__int64 *)*v31;
    }
    while ( v31 );
    v24 = v36;
    if ( v31 )
    {
      if ( *((_DWORD *)this + 38) == 8 )
      {
        v33 = *((unsigned int *)this + 39);
        v23 = 0;
        v32 = *(PROPVARIANT **)((char *)v31 + v33);
        *(__int64 *)((char *)v31 + v33) = (__int64)v37;
        goto LABEL_43;
      }
      v23 = -2147319765;
    }
    else
    {
LABEL_40:
      v23 = -2147467259;
      if ( *((_DWORD *)this + 38) == 8 && v29 < *((_DWORD *)this + 35) )
      {
        v34 = LocalAlloc(0x40u, v24 + *((_DWORD *)this + 40));
        if ( !v34 )
        {
          v23 = -2147024882;
LABEL_50:
          v21 = v37;
          goto LABEL_24;
        }
        v34[2] = v36;
        v23 = 0;
        memcpy_0((char *)v34 + *((unsigned int *)this + 40), a2, v26);
        memcpy_0((char *)v34 + *((unsigned int *)this + 39), &Src, *((unsigned int *)this + 38));
        *(_QWORD *)v34 = *(_QWORD *)(v30 + *((_QWORD *)this + 18));
        *(_QWORD *)(v30 + *((_QWORD *)this + 18)) = v34;
        if ( ++*((_DWORD *)this + 34) > *((_DWORD *)this + 35) )
        {
          CByteHashTable::_GrowTable((CMemPropStore *)((char *)this + 128));
          v32 = 0;
LABEL_43:
          if ( !*((_BYTE *)this + 240) )
            *((_BYTE *)this + 188) = 1;
          if ( v32 )
          {
            PropVariantClear(v32);
            LocalFree(v32);
            return (unsigned int)v23;
          }
          return (unsigned int)v23;
        }
      }
    }
    if ( v23 >= 0 )
    {
      v32 = pvar;
      goto LABEL_43;
    }
    goto LABEL_50;
  }
  if ( PropVariantCompareEx(
         *(const PROPVARIANT *const *)((char *)v17 + *((unsigned int *)this + 39)),
         a3,
         PVCU_DEFAULT,
         2) )
  {
    goto LABEL_14;
  }
  return 1;
}

```

## disassembly

```asm
0x1800347e0  mov     [rsp+arg_18], rbx
0x1800347e5  push    rbp
0x1800347e6  push    rsi
0x1800347e7  push    rdi
0x1800347e8  push    r12
0x1800347ea  push    r13
0x1800347ec  push    r14
0x1800347ee  push    r15
0x1800347f0  sub     rsp, 40h
0x1800347f4  test    byte ptr [rcx+0B8h], 2
0x1800347fb  mov     r12, r8
0x1800347fe  mov     rdi, rdx
0x180034801  mov     r13, rcx
0x180034804  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18003480b  mov     ebx, 12B9B0A5h
0x180034810  jz      loc_180034908
0x180034816  cmp     qword ptr [rcx+90h], 0
0x18003481e  jz      loc_1800349A3
0x180034824  mov     rax, rbp
0x180034827  nop     word ptr [rax+rax+00000000h]
0x180034830  cmp     word ptr [rdx+rax*2+2], 0
0x180034836  lea     rax, [rax+1]
0x18003483a  jnz     short loc_180034830
0x18003483c  mov     r9d, [r13+8Ch]
0x180034843  lea     r15d, ds:2[rax*2]
0x18003484b  mov     rax, [r13+80h]
0x180034852  xor     ecx, ecx
0x180034854  mov     [rsp+78h+Src], rcx
0x180034859  mov     esi, r15d
0x18003485c  test    rax, rax
0x18003485f  jnz     loc_180034BC8
0x180034865  xor     r8d, r8d
0x180034868  mov     eax, ebx
0x18003486a  test    r15d, r15d
0x18003486d  jz      short loc_18003488E
0x18003486f  nop
0x180034870  movzx   edx, byte ptr [rdi+r8]
0x180034875  inc     r8
0x180034878  imul    ecx, eax, 820h
0x18003487e  add     edx, ecx
0x180034880  mov     ecx, eax
0x180034882  shr     ecx, 2
0x180034885  add     edx, ecx
0x180034887  xor     eax, edx
0x180034889  cmp     r8, rsi
0x18003488c  jb      short loc_180034870
0x18003488e  btr     eax, 1Fh
0x180034892  xor     edx, edx
0x180034894  div     r9d
0x180034897  mov     eax, edx
0x180034899  mov     ecx, eax
0x18003489b  mov     rax, [r13+90h]
0x1800348a2  mov     r14, [rax+rcx*8]
0x1800348a6  test    r14, r14
0x1800348a9  jz      loc_1800349A3
0x1800348af  cmp     r15d, [r14+8]
0x1800348b3  jnz     loc_180034997
0x1800348b9  mov     edx, [r13+0A0h]
0x1800348c0  mov     r8, rsi; Size
0x1800348c3  add     rdx, r14; Buf2
0x1800348c6  mov     rcx, rdi; Buf1
0x1800348c9  call    memcmp_0
0x1800348ce  test    eax, eax
0x1800348d0  jnz     loc_180034997
0x1800348d6  cmp     dword ptr [r13+98h], 8
0x1800348de  jnz     loc_1800349A3
0x1800348e4  mov     ecx, [r13+9Ch]
0x1800348eb  mov     r9d, 2; flags
0x1800348f1  xor     r8d, r8d; unit
0x1800348f4  mov     rdx, r12; propvar2
0x1800348f7  mov     rcx, [rcx+r14]; propvar1
0x1800348fb  call    PropVariantCompareEx
0x180034900  test    eax, eax
0x180034902  jz      loc_180034C00
0x180034908  lea     r15, [r13+80h]
0x18003490f  cmp     qword ptr [r15+10h], 0
0x180034914  jnz     short loc_180034973
0x180034916  mov     esi, 17h
0x18003491b  mov     dword ptr [r15+18h], 8
0x180034923  mov     eax, 8
0x180034928  mov     qword ptr [r15], 0
0x18003492f  mul     rsi
0x180034932  mov     dword ptr [r15+1Ch], 10h
0x18003493a  mov     dword ptr [r15+20h], 18h
0x180034942  mov     qword ptr [r15+10h], 0
0x18003494a  mov     [rsp+78h+Src], 0
0x180034953  test    rdx, rdx
0x180034956  jnz     short loc_180034990
0x180034958  mov     rdx, rax; uBytes
0x18003495b  mov     ecx, 40h ; '@'; uFlags
0x180034960  call    cs:__imp_LocalAlloc
0x180034966  mov     [r15+10h], rax
0x18003496a  test    rax, rax
0x18003496d  jz      short loc_180034990
0x18003496f  mov     [r15+0Ch], esi
0x180034973  mov     edx, 18h; uBytes
0x180034978  mov     ecx, 40h ; '@'; uFlags
0x18003497d  call    cs:__imp_LocalAlloc
0x180034983  mov     [rsp+78h+var_50], rax
0x180034988  mov     rsi, rax
0x18003498b  test    rax, rax
0x18003498e  jnz     short loc_1800349E9
0x180034990  mov     eax, 8007000Eh
0x180034995  jmp     short loc_1800349D1
0x180034997  mov     r14, [r14]
0x18003499a  test    r14, r14
0x18003499d  jnz     loc_1800348AF
0x1800349a3  cmp     word ptr [r12], 0
0x1800349a9  jnz     loc_180034908
0x1800349af  mov     eax, 1
0x1800349b4  jmp     short loc_1800349D1
0x1800349b6  mov     r14d, 80004005h
0x1800349bc  mov     rcx, rsi; pvar
0x1800349bf  call    cs:__imp_PropVariantClear
0x1800349c5  mov     rcx, rsi; hMem
0x1800349c8  call    cs:__imp_LocalFree
0x1800349ce  mov     eax, r14d
0x1800349d1  mov     rbx, [rsp+78h+arg_18]
0x1800349d9  add     rsp, 40h
0x1800349dd  pop     r15
0x1800349df  pop     r14
0x1800349e1  pop     r13
0x1800349e3  pop     r12
0x1800349e5  pop     rdi
0x1800349e6  pop     rsi
0x1800349e7  pop     rbp
0x1800349e8  retn
0x1800349e9  mov     rdx, r12; pvarSrc
0x1800349ec  mov     rcx, rsi; pvarDest
0x1800349ef  call    cs:__imp_PropVariantCopy
0x1800349f5  mov     r14d, eax
0x1800349f8  test    eax, eax
0x1800349fa  js      short loc_1800349BC
0x1800349fc  mov     [rsp+78h+Src], rsi
0x180034a01  cmp     word ptr [rdi+rbp*2+2], 0
0x180034a07  lea     rbp, [rbp+1]
0x180034a0b  jnz     short loc_180034A01
0x180034a0d  xor     eax, eax
0x180034a0f  mov     [rsp+78h+pvar], rax
0x180034a14  cmp     [r15+10h], rax
0x180034a18  jz      short loc_1800349B6
0x180034a1a  mov     rax, [r15]
0x180034a1d  lea     r9d, ds:2[rbp*2]
0x180034a25  mov     r10d, [r15+0Ch]
0x180034a29  mov     [rsp+78h+var_58], r9d
0x180034a2e  mov     esi, r9d
0x180034a31  test    rax, rax
0x180034a34  jnz     loc_180034BDB
0x180034a3a  xor     r8d, r8d
0x180034a3d  test    r9d, r9d
0x180034a40  jz      short loc_180034A6E
0x180034a42  nop     dword ptr [rax+00h]
0x180034a46  nop     word ptr [rax+rax+00000000h]
0x180034a50  movzx   edx, byte ptr [rdi+r8]
0x180034a55  mov     ecx, ebx
0x180034a57  imul    eax, ebx, 820h
0x180034a5d  inc     r8
0x180034a60  shr     ecx, 2
0x180034a63  add     edx, eax
0x180034a65  add     edx, ecx
0x180034a67  xor     ebx, edx
0x180034a69  cmp     r8, rsi
0x180034a6c  jb      short loc_180034A50
0x180034a6e  btr     ebx, 1Fh
0x180034a72  xor     edx, edx
0x180034a74  mov     eax, ebx
0x180034a76  div     r10d
0x180034a79  mov     ebp, edx
0x180034a7b  mov     eax, ebp
0x180034a7d  lea     r12, ds:0[rax*8]
0x180034a85  mov     rax, [r15+10h]
0x180034a89  mov     rbx, [r12+rax]
0x180034a8d  test    rbx, rbx
0x180034a90  jz      short loc_180034AC5
0x180034a92  cmp     r9d, [rbx+8]
0x180034a96  jnz     short loc_180034AB3
0x180034a98  mov     edx, [r15+20h]
0x180034a9c  mov     r8, rsi; Size
0x180034a9f  add     rdx, rbx; Buf2
0x180034aa2  mov     rcx, rdi; Buf1
0x180034aa5  call    memcmp_0
0x180034aaa  test    eax, eax
0x180034aac  jz      short loc_180034ABB
0x180034aae  mov     r9d, [rsp+78h+var_58]
0x180034ab3  mov     rbx, [rbx]
0x180034ab6  test    rbx, rbx
0x180034ab9  jnz     short loc_180034A92
0x180034abb  mov     r9d, [rsp+78h+var_58]
0x180034ac0  test    rbx, rbx
0x180034ac3  jnz     short loc_180034B11
0x180034ac5  cmp     dword ptr [r15+18h], 8
0x180034aca  mov     r14d, 80004005h
0x180034ad0  jz      short loc_180034B42
0x180034ad2  test    r14d, r14d
0x180034ad5  js      short loc_180034B38
0x180034ad7  mov     rdi, [rsp+78h+pvar]
0x180034adc  cmp     byte ptr [r13+0F0h], 0
0x180034ae4  jnz     short loc_180034AEE
0x180034ae6  mov     byte ptr [r13+0BCh], 1
0x180034aee  test    rdi, rdi
0x180034af1  jz      loc_1800349CE
0x180034af7  mov     rcx, rdi; pvar
0x180034afa  call    cs:__imp_PropVariantClear
0x180034b00  mov     rcx, rdi; hMem
0x180034b03  call    cs:__imp_LocalFree
0x180034b09  mov     eax, r14d
0x180034b0c  jmp     loc_1800349D1
0x180034b11  cmp     dword ptr [r15+18h], 8
0x180034b16  jnz     loc_180034BF5
0x180034b1c  mov     eax, [r15+1Ch]
0x180034b20  xor     r14d, r14d
0x180034b23  mov     rcx, [rsp+78h+var_50]
0x180034b28  mov     rdi, [rax+rbx]
0x180034b2c  mov     [rax+rbx], rcx
0x180034b30  jmp     short loc_180034ADC
0x180034b32  mov     r14d, 8007000Eh
0x180034b38  mov     rsi, [rsp+78h+var_50]
0x180034b3d  jmp     loc_1800349BC
0x180034b42  cmp     ebp, [r15+0Ch]
0x180034b46  jnb     short loc_180034AD2
0x180034b48  mov     edx, [r15+20h]
0x180034b4c  mov     ecx, 40h ; '@'; uFlags
0x180034b51  add     edx, r9d; uBytes
0x180034b54  call    cs:__imp_LocalAlloc
0x180034b5a  mov     rbx, rax
0x180034b5d  test    rax, rax
0x180034b60  jz      short loc_180034B32
0x180034b62  mov     eax, [rsp+78h+var_58]
0x180034b66  mov     r8, rsi; Size
0x180034b69  mov     [rbx+8], eax
0x180034b6c  mov     rdx, rdi; Src
0x180034b6f  mov     ecx, [r15+20h]
0x180034b73  xor     r14d, r14d
0x180034b76  add     rcx, rbx; void *
0x180034b79  call    memcpy_0
0x180034b7e  mov     ecx, [r15+1Ch]
0x180034b82  lea     rdx, [rsp+78h+Src]; Src
0x180034b87  mov     r8d, [r15+18h]; Size
0x180034b8b  add     rcx, rbx; void *
0x180034b8e  call    memcpy_0
0x180034b93  mov     rax, [r15+10h]
0x180034b97  mov     rdx, [r12+rax]
0x180034b9b  mov     [rbx], rdx
0x180034b9e  mov     rax, [r15+10h]
0x180034ba2  mov     [r12+rax], rbx
0x180034ba6  inc     dword ptr [r15+8]
0x180034baa  mov     eax, [r15+8]
0x180034bae  cmp     eax, [r15+0Ch]
0x180034bb2  jbe     loc_180034AD2
0x180034bb8  mov     rcx, r15; this
0x180034bbb  call    ?_GrowTable@CByteHashTable@@AEAAXXZ; CByteHashTable::_GrowTable(void)
0x180034bc0  mov     edi, r14d
0x180034bc3  jmp     loc_180034ADC
0x180034bc8  mov     r8d, r9d
0x180034bcb  mov     edx, r15d
0x180034bce  mov     rcx, rdi
0x180034bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bd6  jmp     loc_180034899
0x180034bdb  mov     r8d, r10d
0x180034bde  mov     edx, r9d
0x180034be1  mov     rcx, rdi
0x180034be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034be9  mov     r9d, [rsp+78h+var_58]
0x180034bee  mov     ebp, eax
0x180034bf0  jmp     loc_180034A7B
0x180034bf5  mov     r14d, 8002802Bh
0x180034bfb  jmp     loc_180034AD2
0x180034c00  mov     eax, 1
0x180034c05  jmp     loc_1800349D1
```
