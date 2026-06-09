# CDiaEnumSourceLink::Init(void)

- ea: `0x1800da130`
- end: `0x1800daa1f`
- name: `?Init@CDiaEnumSourceLink@@QEAAJXZ`
- size: `2287`
- prototype: `__int64 __fastcall(CDiaEnumSourceLink *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting`

## callers

- `0x1800f3b00`

## callees

- `0x180021340`
- `0x180026980`
- `0x1800269f8`
- `0x180026e00`
- `0x180027430`
- `0x180027440`
- `0x1800b49e0`
- `0x1800b9080`
- `0x1800ba0c0`
- `0x1800c2800`
- `0x1800c95d0`
- `0x1800ca050`
- `0x1800ca240`
- `0x1800ca9a0`
- `0x1800d4540`
- `0x1800da130`
- `0x1801d6350`
- `0x1801d63b0`
- `0x1801d70f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800da685`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800da685`

## string_xrefs

- `0x1800da671`: `sourcelink$`
- `0x1800da636`: `sourcelink`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDiaEnumSourceLink::Init(CDiaEnumSourceLink *this)
{
  PSGSI1::EnumPubsByAddr *v2; // rcx
  PSGSI1::EnumPubsByAddr *v3; // rdi
  unsigned int v4; // eax
  int v5; // r15d
  PSGSI1::EnumPubsByAddr *v6; // rax
  unsigned int v7; // edi
  unsigned int v8; // edx
  PSGSI1::EnumPubsByAddr *v9; // rcx
  PSGSI1::EnumPubsByAddr **v10; // rsi
  __int64 result; // rax
  unsigned __int16 i; // r12
  __int64 v13; // r9
  SymCache *v14; // rcx
  ModCache *v15; // rax
  unsigned int v16; // edi
  const struct SymBuffer *v17; // rax
  const struct SymBuffer *v18; // r14
  unsigned __int64 v19; // r15
  const struct SYMTYPE *v20; // rcx
  unsigned __int64 v21; // r8
  unsigned __int16 *v22; // rdi
  const struct SymBuffer *v23; // rsi
  unsigned int v24; // r10d
  __int64 v25; // rdx
  unsigned int v26; // r9d
  unsigned int v27; // r8d
  PSGSI1::EnumPubsByAddr *v28; // rcx
  unsigned int v29; // esi
  unsigned int v30; // r8d
  PSGSI1::EnumPubsByAddr *v31; // rdx
  PSGSI1::EnumPubsByAddr **v32; // r14
  __int64 v33; // rax
  unsigned __int64 v34; // rdx
  unsigned int v35; // edi
  PSGSI1::EnumPubsByAddr *v36; // rcx
  unsigned int v37; // edi
  unsigned int v38; // r8d
  PSGSI1::EnumPubsByAddr *v39; // rdx
  PSGSI1::EnumPubsByAddr **v40; // rsi
  PSGSI1::EnumPubsByAddr *v41; // rcx
  unsigned int v42; // edi
  unsigned int v43; // r8d
  PSGSI1::EnumPubsByAddr *v44; // rdx
  PSGSI1::EnumPubsByAddr **v45; // rsi
  PSGSI1::EnumPubsByAddr *v46; // rcx
  unsigned int v47; // edi
  unsigned int v48; // r8d
  PSGSI1::EnumPubsByAddr *v49; // rdx
  PSGSI1::EnumPubsByAddr **v50; // rsi
  __int64 v51; // [rsp+20h] [rbp-F8h] BYREF
  PSGSI1::EnumPubsByAddr *v52; // [rsp+28h] [rbp-F0h]
  __int64 v53; // [rsp+30h] [rbp-E8h]
  PSGSI1::EnumPubsByAddr *v54; // [rsp+38h] [rbp-E0h]
  __int64 v55; // [rsp+40h] [rbp-D8h]
  PSGSI1::EnumPubsByAddr *v56; // [rsp+48h] [rbp-D0h]
  __int64 v57; // [rsp+50h] [rbp-C8h]
  int v58; // [rsp+58h] [rbp-C0h] BYREF
  _BYTE v59[16]; // [rsp+60h] [rbp-B8h] BYREF
  __int128 v60; // [rsp+70h] [rbp-A8h] BYREF
  int pExceptionObject; // [rsp+80h] [rbp-98h] BYREF
  __int64 v62; // [rsp+88h] [rbp-90h]
  PDBErrors *v63; // [rsp+90h] [rbp-88h] BYREF
  __int128 v64; // [rsp+A0h] [rbp-78h] BYREF
  char v65[16]; // [rsp+B0h] [rbp-68h] BYREF
  __int128 v66; // [rsp+C0h] [rbp-58h] BYREF
  wchar_t Buffer[8]; // [rsp+D0h] [rbp-48h] BYREF

  v62 = -2;
  try
  {
    CacheLock::CacheLock((CacheLock *)v59, *(struct SymCache **)(*((_QWORD *)this + 3) + 40LL));
    v2 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)this + 4);
    if ( v2 )
    {
      PSGSI1::EnumPubsByAddr::release(v2);
      *((_QWORD *)this + 4) = 0;
    }
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    LODWORD(v51) = 0;
    v3 = (PSGSI1::EnumPubsByAddr *)operator new[](0xFE8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v3 )
    {
      v56 = v3;
      v4 = 509;
      v57 = 0x1FD000001FDLL;
    }
    else
    {
      v4 = v57;
      v3 = v56;
    }
    memset_0(v3, 0, 8LL * v4);
    *(_QWORD *)&v60 = this;
    *((_QWORD *)&v60 + 1) = &v51;
    if ( *((_DWORD *)this + 15) )
    {
      v5 = CDiaEnumSourceLink::Init_::_4_::_lambda_1_::operator()(&v60);
      if ( v52 )
      {
        PSGSI1::EnumPubsByAddr::release(v52);
        v52 = 0;
      }
      v53 = 0;
      v6 = v54;
      if ( v54 )
      {
        PSGSI1::EnumPubsByAddr::release(v54);
        v6 = 0;
        v54 = 0;
      }
      v55 = 0;
      v7 = 0;
      v8 = v57;
      v9 = v56;
      if ( (_DWORD)v57 )
      {
        do
        {
          v10 = (PSGSI1::EnumPubsByAddr **)*((_QWORD *)v9 + v7);
          if ( v10 )
          {
            if ( *v10 )
              PSGSI1::EnumPubsByAddr::release(*v10);
            operator delete(v10);
            *((_QWORD *)v56 + v7) = 0;
            v8 = v57;
            v9 = v56;
          }
          ++v7;
        }
        while ( v7 < v8 );
        v6 = v54;
      }
      LODWORD(v51) = 0;
      if ( v9 )
      {
        PSGSI1::EnumPubsByAddr::release(v9);
        v56 = 0;
        v6 = v54;
      }
      v57 = 0;
      if ( v6 )
        PSGSI1::EnumPubsByAddr::release(v6);
      if ( !v52 )
        goto LABEL_25;
    }
    else
    {
      for ( i = 1; ; ++i )
      {
        v13 = *((_QWORD *)this + 3);
        v14 = *(SymCache **)(v13 + 40);
        if ( i > (unsigned int)((unsigned __int64)(*((_DWORD *)v14 + 26) - *((_DWORD *)v14 + 24)) >> 3) )
          break;
        v15 = SymCache::modDetails(v14, i);
        if ( !v15 )
        {
          v16 = -2140340210;
LABEL_51:
          if ( v52 )
          {
            PSGSI1::EnumPubsByAddr::release(v52);
            v52 = 0;
          }
          v53 = 0;
          v28 = v54;
          if ( v54 )
          {
            PSGSI1::EnumPubsByAddr::release(v54);
            v28 = 0;
            v54 = 0;
          }
          v55 = 0;
          v29 = 0;
          v30 = v57;
          v31 = v56;
          if ( (_DWORD)v57 )
          {
            do
            {
              v32 = (PSGSI1::EnumPubsByAddr **)*((_QWORD *)v31 + v29);
              if ( v32 )
              {
                if ( *v32 )
                  PSGSI1::EnumPubsByAddr::release(*v32);
                operator delete(v32);
                *((_QWORD *)v56 + v29) = 0;
                v30 = v57;
                v31 = v56;
              }
              ++v29;
            }
            while ( v29 < v30 );
            v28 = v54;
          }
          LODWORD(v51) = 0;
          if ( v31 )
          {
            PSGSI1::EnumPubsByAddr::release(v31);
            v56 = 0;
            v28 = v54;
          }
          v57 = 0;
          if ( v28 )
            PSGSI1::EnumPubsByAddr::release(v28);
          if ( v52 )
            PSGSI1::EnumPubsByAddr::release(v52);
          CacheLock::~CacheLock((CacheLock *)v59);
          return v16;
        }
        v17 = ModCache::pbSyms(v15, 0);
        v18 = v17;
        if ( v17 )
        {
          v19 = *((_QWORD *)v17 + 3);
          v20 = (const struct SYMTYPE *)*((_QWORD *)v17 + 2);
          if ( (unsigned __int64)v20 >= *(_QWORD *)v17
            && (v21 = *((_QWORD *)v17 + 1), (unsigned __int64)v20 + 2 <= v21)
            && (unsigned __int64)v20 + *(unsigned __int16 *)v20 + 2 <= v21
            && fCheckReclen(v20) )
          {
            v22 = (unsigned __int16 *)*((_QWORD *)v18 + 2);
          }
          else
          {
            v22 = (unsigned __int16 *)*((_QWORD *)v18 + 3);
          }
          v23 = v18;
          *((_QWORD *)&v60 + 1) = v18;
LABEL_38:
          *(_QWORD *)&v60 = v22;
          while ( (unsigned __int64)v22 < v19 )
          {
            if ( v22[1] == 4478 )
            {
              v24 = *((_DWORD *)v22 + 1);
              v25 = *((_QWORD *)v56 + (unsigned __int16)v24 % (unsigned int)v57);
              if ( v25 )
              {
                v26 = *(_DWORD *)(v25 + 8);
                if ( v26 )
                {
                  v27 = 0;
                  while ( *((_DWORD *)v52 + HIDWORD(*(_QWORD *)(*(_QWORD *)v25 + 8LL * v27))) != v24 )
                  {
                    if ( ++v27 >= v26 )
                      goto LABEL_46;
                  }
                  break;
                }
              }
LABEL_46:
              if ( (unsigned int)dia::Map<unsigned long,unsigned long,dia::HashClass<unsigned long,0>>::add(
                                   &v51,
                                   v24,
                                   0)
                && (unsigned int)dia::Array<unsigned long>::setSize(
                                   (char *)this + 32,
                                   *((unsigned int *)this + 10) + 1LL) )
              {
                *(_DWORD *)(*((_QWORD *)this + 4) + 4LL * (unsigned int)(*((_DWORD *)this + 10) - 1)) = *((_DWORD *)v22 + 1);
                break;
              }
              v16 = -2147024882;
              goto LABEL_51;
            }
            if ( SymBuffer::isBlockSym(v22[1]) )
            {
              v64 = v60;
              v33 = SymBuffer::skipblk(v18, v65, &v64);
              v22 = *(unsigned __int16 **)v33;
              v23 = *(const struct SymBuffer **)(v33 + 8);
              *((_QWORD *)&v60 + 1) = v23;
              goto LABEL_38;
            }
            if ( !v23 )
            {
              pExceptionObject = 13;
              throw (PDBErrors *)&pExceptionObject;
            }
            v22 = (unsigned __int16 *)((char *)v22 + *v22 + 2);
            *(_QWORD *)&v60 = v22;
            if ( (unsigned __int64)v22 >= *(_QWORD *)v23 )
            {
              v34 = *((_QWORD *)v23 + 1);
              if ( (unsigned __int64)(v22 + 1) <= v34
                && (unsigned __int64)v22 + *v22 + 2 <= v34
                && fCheckReclen((const struct SYMTYPE *)v22) )
              {
                continue;
              }
            }
            v22 = (unsigned __int16 *)*((_QWORD *)v23 + 1);
            goto LABEL_38;
          }
        }
      }
      v35 = 1;
      if ( !(*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, int *))(**(_QWORD **)(v13 + 56) + 104LL))(
              *(_QWORD *)(v13 + 56),
              L"sourcelink",
              &v58)
        && v58 )
      {
        *((_DWORD *)this + 12) = 1;
        ++*((_DWORD *)this + 13);
      }
      v66 = 0;
      *(_OWORD *)Buffer = 0;
      _o_wcscpy_s(&v66, 16, L"sourcelink$");
      while ( 1 )
      {
        swprintf_s(&Buffer[3], 5u, L"%u", v35, v51);
        v5 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, int *))(**(_QWORD **)(*((_QWORD *)this + 3) + 56LL) + 104LL))(
               *(_QWORD *)(*((_QWORD *)this + 3) + 56LL),
               &v66,
               &v58);
        if ( v5 < 0 )
          break;
        if ( !v58 )
        {
          if ( v52 )
          {
            PSGSI1::EnumPubsByAddr::release(v52);
            v52 = 0;
          }
          v53 = 0;
          v41 = v54;
          if ( v54 )
          {
            PSGSI1::EnumPubsByAddr::release(v54);
            v41 = 0;
            v54 = 0;
          }
          v55 = 0;
          v42 = 0;
          v43 = v57;
          v44 = v56;
          if ( (_DWORD)v57 )
          {
            do
            {
              v45 = (PSGSI1::EnumPubsByAddr **)*((_QWORD *)v44 + v42);
              if ( v45 )
              {
                if ( *v45 )
                  PSGSI1::EnumPubsByAddr::release(*v45);
                operator delete(v45);
                *((_QWORD *)v56 + v42) = 0;
                v43 = v57;
                v44 = v56;
              }
              ++v42;
            }
            while ( v42 < v43 );
            v41 = v54;
          }
          LODWORD(v51) = 0;
          if ( v44 )
          {
            PSGSI1::EnumPubsByAddr::release(v44);
            v56 = 0;
            v41 = v54;
          }
          v57 = 0;
          if ( v41 )
            PSGSI1::EnumPubsByAddr::release(v41);
          if ( v52 )
            PSGSI1::EnumPubsByAddr::release(v52);
          CacheLock::~CacheLock((CacheLock *)v59);
          return 0;
        }
        if ( v58 == -1 )
        {
          if ( v52 )
          {
            PSGSI1::EnumPubsByAddr::release(v52);
            v52 = 0;
          }
          v53 = 0;
          v46 = v54;
          if ( v54 )
          {
            PSGSI1::EnumPubsByAddr::release(v54);
            v46 = 0;
            v54 = 0;
          }
          v55 = 0;
          v47 = 0;
          v48 = v57;
          v49 = v56;
          if ( (_DWORD)v57 )
          {
            do
            {
              v50 = (PSGSI1::EnumPubsByAddr **)*((_QWORD *)v49 + v47);
              if ( v50 )
              {
                if ( *v50 )
                  PSGSI1::EnumPubsByAddr::release(*v50);
                operator delete(v50);
                *((_QWORD *)v56 + v47) = 0;
                v48 = v57;
                v49 = v56;
              }
              ++v47;
            }
            while ( v47 < v48 );
            v46 = v54;
          }
          LODWORD(v51) = 0;
          if ( v49 )
          {
            PSGSI1::EnumPubsByAddr::release(v49);
            v56 = 0;
            v46 = v54;
          }
          v57 = 0;
          if ( v46 )
            PSGSI1::EnumPubsByAddr::release(v46);
          if ( v52 )
            PSGSI1::EnumPubsByAddr::release(v52);
          CacheLock::~CacheLock((CacheLock *)v59);
          return 2154627086LL;
        }
        ++v35;
        ++*((_DWORD *)this + 13);
      }
      if ( v52 )
      {
        PSGSI1::EnumPubsByAddr::release(v52);
        v52 = 0;
      }
      v53 = 0;
      v36 = v54;
      if ( v54 )
      {
        PSGSI1::EnumPubsByAddr::release(v54);
        v36 = 0;
        v54 = 0;
      }
      v55 = 0;
      v37 = 0;
      v38 = v57;
      v39 = v56;
      if ( (_DWORD)v57 )
      {
        do
        {
          v40 = (PSGSI1::EnumPubsByAddr **)*((_QWORD *)v39 + v37);
          if ( v40 )
          {
            if ( *v40 )
              PSGSI1::EnumPubsByAddr::release(*v40);
            operator delete(v40);
            *((_QWORD *)v56 + v37) = 0;
            v38 = v57;
            v39 = v56;
          }
          ++v37;
        }
        while ( v37 < v38 );
        v36 = v54;
      }
      LODWORD(v51) = 0;
      if ( v39 )
      {
        PSGSI1::EnumPubsByAddr::release(v39);
        v56 = 0;
        v36 = v54;
      }
      v57 = 0;
      if ( v36 )
        PSGSI1::EnumPubsByAddr::release(v36);
      if ( !v52 )
        goto LABEL_25;
    }
    PSGSI1::EnumPubsByAddr::release(v52);
LABEL_25:
    CacheLock::~CacheLock((CacheLock *)v59);
    result = (unsigned int)v5;
  }
  catch ( PDBErrors *v63 )
  {
    if ( *(int *)v63 > 0 && *(int *)v63 < 36 )
      return *((unsigned int *)&ecToHresult + *(int *)v63);
    return 2147500037LL;
  }
  catch ( msl::utilities::SafeIntException )
  {
    return 2154627086LL;
  }
  catch ( std::range_error )
  {
    return 2154627086LL;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( std::exception )
  {
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800da130  mov     rax, rsp
0x1800da133  push    rdi
0x1800da134  push    r12
0x1800da136  push    r13
0x1800da138  push    r14
0x1800da13a  push    r15
0x1800da13c  sub     rsp, 0F0h
0x1800da143  mov     qword ptr [rax-90h], 0FFFFFFFFFFFFFFFEh
0x1800da14e  mov     [rax+10h], rbx
0x1800da152  mov     [rax+18h], rsi
0x1800da156  mov     rax, cs:__security_cookie
0x1800da15d  xor     rax, rsp
0x1800da160  mov     [rsp+118h+var_38], rax
0x1800da168  mov     r13, rcx
0x1800da16b  mov     rdx, [rcx+18h]
0x1800da16f  mov     rdx, [rdx+28h]; struct SymCache *
0x1800da173  lea     rcx, [rsp+118h+var_B8]; this
0x1800da178  call    ??0CacheLock@@QEAA@PEAVSymCache@@@Z; CacheLock::CacheLock(SymCache *)
0x1800da17d  nop
0x1800da17e  mov     rcx, [r13+20h]; this
0x1800da182  test    rcx, rcx
0x1800da185  jz      short loc_1800DA194
0x1800da187  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da18c  xor     ebx, ebx
0x1800da18e  mov     [r13+20h], rbx
0x1800da192  jmp     short loc_1800DA196
0x1800da194  xor     ebx, ebx
0x1800da196  mov     qword ptr [r13+28h], 0
0x1800da19e  mov     qword ptr [r13+30h], 0
0x1800da1a6  mov     [rsp+118h+var_F0], rbx
0x1800da1ab  mov     [rsp+118h+var_E8], 0
0x1800da1b4  mov     [rsp+118h+var_E0], rbx
0x1800da1b9  mov     [rsp+118h+var_D8], 0
0x1800da1c2  mov     [rsp+118h+var_D0], rbx
0x1800da1c7  mov     [rsp+118h+var_C8], 0
0x1800da1d0  mov     dword ptr [rsp+118h+var_F8], ebx
0x1800da1d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800da1db  mov     ecx, 0FE8h; unsigned __int64
0x1800da1e0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800da1e5  mov     rdi, rax
0x1800da1e8  test    rax, rax
0x1800da1eb  jz      short loc_1800DA23B
0x1800da1ed  mov     r8, [rsp+118h+var_D0]
0x1800da1f2  test    r8, r8
0x1800da1f5  jz      short loc_1800DA227
0x1800da1f7  mov     edx, ebx
0x1800da1f9  cmp     dword ptr [rsp+118h+var_C8], 0
0x1800da1fe  jbe     short loc_1800DA21F
0x1800da200  mov     eax, edx
0x1800da202  lea     rcx, ds:0[rax*8]
0x1800da20a  mov     rax, [r8+rcx]
0x1800da20e  mov     [rdi+rcx], rax
0x1800da212  inc     edx
0x1800da214  mov     r8, [rsp+118h+var_D0]
0x1800da219  cmp     edx, dword ptr [rsp+118h+var_C8]
0x1800da21d  jb      short loc_1800DA200
0x1800da21f  mov     rcx, r8; this
0x1800da222  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da227  mov     [rsp+118h+var_D0], rdi
0x1800da22c  mov     eax, 1FDh
0x1800da231  mov     dword ptr [rsp+118h+var_C8+4], eax
0x1800da235  mov     dword ptr [rsp+118h+var_C8], eax
0x1800da239  jmp     short loc_1800DA244
0x1800da23b  mov     eax, dword ptr [rsp+118h+var_C8]
0x1800da23f  mov     rdi, [rsp+118h+var_D0]
0x1800da244  mov     r8d, eax
0x1800da247  shl     r8, 3; Size
0x1800da24b  xor     edx, edx; Val
0x1800da24d  mov     rcx, rdi; void *
0x1800da250  call    memset_0
0x1800da255  nop
0x1800da256  mov     qword ptr [rsp+118h+var_A8], r13
0x1800da25b  lea     rax, [rsp+118h+var_F8]
0x1800da260  mov     qword ptr [rsp+118h+var_A8+8], rax
0x1800da265  mov     edx, [r13+3Ch]
0x1800da269  test    edx, edx
0x1800da26b  jz      loc_1800DA365
0x1800da271  lea     rcx, [rsp+118h+var_A8]
0x1800da276  call    _CDiaEnumSourceLink__Init____4____lambda_1___operator__
0x1800da27b  mov     r15d, eax
0x1800da27e  mov     rcx, [rsp+118h+var_F0]; this
0x1800da283  test    rcx, rcx
0x1800da286  jz      short loc_1800DA292
0x1800da288  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da28d  mov     [rsp+118h+var_F0], rbx
0x1800da292  mov     [rsp+118h+var_E8], 0
0x1800da29b  mov     rax, [rsp+118h+var_E0]
0x1800da2a0  test    rax, rax
0x1800da2a3  jz      short loc_1800DA2B5
0x1800da2a5  mov     rcx, rax; this
0x1800da2a8  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da2ad  mov     rax, rbx
0x1800da2b0  mov     [rsp+118h+var_E0], rbx
0x1800da2b5  mov     [rsp+118h+var_D8], 0
0x1800da2be  mov     edi, ebx
0x1800da2c0  mov     edx, dword ptr [rsp+118h+var_C8]
0x1800da2c4  mov     rcx, [rsp+118h+var_D0]
0x1800da2c9  test    edx, edx
0x1800da2cb  jz      short loc_1800DA315
0x1800da2cd  nop     dword ptr [rax]
0x1800da2d0  mov     eax, edi
0x1800da2d2  lea     r14, ds:0[rax*8]
0x1800da2da  mov     rsi, [rcx+r14]
0x1800da2de  test    rsi, rsi
0x1800da2e1  jz      short loc_1800DA30A
0x1800da2e3  mov     rcx, [rsi]; this
0x1800da2e6  test    rcx, rcx
0x1800da2e9  jz      short loc_1800DA2F0
0x1800da2eb  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da2f0  mov     rcx, rsi; Block
0x1800da2f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800da2f8  mov     rax, [rsp+118h+var_D0]
0x1800da2fd  mov     [rax+r14], rbx
0x1800da301  mov     edx, dword ptr [rsp+118h+var_C8]
0x1800da305  mov     rcx, [rsp+118h+var_D0]; this
0x1800da30a  inc     edi
0x1800da30c  cmp     edi, edx
0x1800da30e  jb      short loc_1800DA2D0
0x1800da310  mov     rax, [rsp+118h+var_E0]
0x1800da315  mov     dword ptr [rsp+118h+var_F8], ebx
0x1800da319  test    rcx, rcx
0x1800da31c  jz      short loc_1800DA32D
0x1800da31e  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da323  mov     [rsp+118h+var_D0], rbx
0x1800da328  mov     rax, [rsp+118h+var_E0]
0x1800da32d  mov     [rsp+118h+var_C8], 0
0x1800da336  test    rax, rax
0x1800da339  jz      short loc_1800DA343
0x1800da33b  mov     rcx, rax; this
0x1800da33e  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da343  mov     rcx, [rsp+118h+var_F0]; this
0x1800da348  test    rcx, rcx
0x1800da34b  jz      short loc_1800DA353
0x1800da34d  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da352  nop
0x1800da353  lea     rcx, [rsp+118h+var_B8]; this
0x1800da358  call    ??1CacheLock@@QEAA@XZ; CacheLock::~CacheLock(void)
0x1800da35d  mov     eax, r15d
0x1800da360  jmp     loc_1800DA9D1
0x1800da365  mov     r12d, 1
0x1800da36b  nop     dword ptr [rax+rax+00h]
0x1800da370  mov     r9, [r13+18h]
0x1800da374  mov     rcx, [r9+28h]; this
0x1800da378  movzx   edx, r12w; unsigned int
0x1800da37c  mov     eax, [rcx+68h]
0x1800da37f  sub     eax, [rcx+60h]
0x1800da382  movsxd  r8, eax
0x1800da385  shr     r8, 3
0x1800da389  cmp     edx, r8d
0x1800da38c  ja      loc_1800DA62A
0x1800da392  call    ?modDetails@SymCache@@QEAAPEAVModCache@@K@Z; SymCache::modDetails(ulong)
0x1800da397  test    rax, rax
0x1800da39a  jnz     short loc_1800DA3A6
0x1800da39c  mov     edi, 806D000Eh
0x1800da3a1  jmp     loc_1800DA4AF
0x1800da3a6  xor     edx, edx; unsigned int
0x1800da3a8  mov     rcx, rax; this
0x1800da3ab  call    ?pbSyms@ModCache@@QEAAPEBVSymBuffer@@K@Z; ModCache::pbSyms(ulong)
0x1800da3b0  mov     r14, rax
0x1800da3b3  test    rax, rax
0x1800da3b6  jz      loc_1800DA4A1
0x1800da3bc  mov     r15, [rax+18h]
0x1800da3c0  mov     rcx, [rax+10h]; struct SYMTYPE *
0x1800da3c4  cmp     rcx, [rax]
0x1800da3c7  jb      short loc_1800DA3F4
0x1800da3c9  mov     r8, [rax+8]
0x1800da3cd  lea     rax, [rcx+2]
0x1800da3d1  cmp     rax, r8
0x1800da3d4  ja      short loc_1800DA3F4
0x1800da3d6  movzx   edx, word ptr [rcx]
0x1800da3d9  add     rdx, 2
0x1800da3dd  add     rdx, rcx
0x1800da3e0  cmp     rdx, r8
0x1800da3e3  ja      short loc_1800DA3F4
0x1800da3e5  call    ?fCheckReclen@@YA_NPEBUSYMTYPE@@@Z; fCheckReclen(SYMTYPE const *)
0x1800da3ea  test    al, al
0x1800da3ec  jz      short loc_1800DA3F4
0x1800da3ee  mov     rdi, [r14+10h]
0x1800da3f2  jmp     short loc_1800DA3F8
0x1800da3f4  mov     rdi, [r14+18h]
0x1800da3f8  mov     rsi, r14
0x1800da3fb  mov     qword ptr [rsp+118h+var_A8+8], r14
0x1800da400  mov     qword ptr [rsp+118h+var_A8], rdi
0x1800da405  cmp     rdi, r15
0x1800da408  jnb     loc_1800DA4A1
0x1800da40e  movzx   eax, word ptr [rdi+2]
0x1800da412  mov     ecx, 117Eh
0x1800da417  cmp     ax, cx
0x1800da41a  jnz     loc_1800DA596
0x1800da420  mov     r10d, [rdi+4]
0x1800da424  movzx   eax, r10w
0x1800da428  xor     edx, edx
0x1800da42a  div     dword ptr [rsp+118h+var_C8]
0x1800da42e  mov     rax, [rsp+118h+var_D0]
0x1800da433  mov     rdx, [rax+rdx*8]
0x1800da437  test    rdx, rdx
0x1800da43a  jz      short loc_1800DA469
0x1800da43c  mov     r9d, [rdx+8]
0x1800da440  test    r9d, r9d
0x1800da443  jz      short loc_1800DA469
0x1800da445  mov     r8d, ebx
0x1800da448  mov     r11, [rdx]
0x1800da44b  mov     rdx, [rsp+118h+var_F0]
0x1800da450  mov     eax, r8d
0x1800da453  mov     rcx, [r11+rax*8]
0x1800da457  shr     rcx, 20h
0x1800da45b  cmp     [rdx+rcx*4], r10d
0x1800da45f  jz      short loc_1800DA4A1
0x1800da461  inc     r8d
0x1800da464  cmp     r8d, r9d
0x1800da467  jb      short loc_1800DA450
0x1800da469  xor     r8d, r8d
0x1800da46c  mov     edx, r10d
0x1800da46f  lea     rcx, [rsp+118h+var_F8]
0x1800da474  call    ?add@?$Map@KKV?$HashClass@K$0A@@dia@@@dia@@QEAAHKK@Z; dia::Map<ulong,ulong,dia::HashClass<ulong,0>>::add(ulong,ulong)
0x1800da479  test    eax, eax
0x1800da47b  jz      short loc_1800DA4AA
0x1800da47d  mov     edx, [r13+28h]
0x1800da481  inc     rdx
0x1800da484  lea     rcx, [r13+20h]
0x1800da488  call    ?setSize@?$Array@K@dia@@QEAAH_K@Z; dia::Array<ulong>::setSize(unsigned __int64)
0x1800da48d  test    eax, eax
0x1800da48f  jz      short loc_1800DA4AA
0x1800da491  mov     edx, [r13+28h]
0x1800da495  dec     edx
0x1800da497  mov     rcx, [r13+20h]
0x1800da49b  mov     eax, [rdi+4]
0x1800da49e  mov     [rcx+rdx*4], eax
0x1800da4a1  inc     r12w
0x1800da4a5  jmp     loc_1800DA370
0x1800da4aa  mov     edi, 8007000Eh
0x1800da4af  mov     rcx, [rsp+118h+var_F0]; this
0x1800da4b4  test    rcx, rcx
0x1800da4b7  jz      short loc_1800DA4C3
0x1800da4b9  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da4be  mov     [rsp+118h+var_F0], rbx
0x1800da4c3  mov     [rsp+118h+var_E8], 0
0x1800da4cc  mov     rcx, [rsp+118h+var_E0]; this
0x1800da4d1  test    rcx, rcx
0x1800da4d4  jz      short loc_1800DA4E3
0x1800da4d6  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da4db  mov     rcx, rbx
0x1800da4de  mov     [rsp+118h+var_E0], rbx
0x1800da4e3  mov     [rsp+118h+var_D8], 0
0x1800da4ec  mov     esi, ebx
0x1800da4ee  mov     r8d, dword ptr [rsp+118h+var_C8]
0x1800da4f3  mov     rdx, [rsp+118h+var_D0]
0x1800da4f8  test    r8d, r8d
0x1800da4fb  jz      short loc_1800DA547
0x1800da4fd  nop     dword ptr [rax]
0x1800da500  mov     eax, esi
0x1800da502  lea     r15, ds:0[rax*8]
0x1800da50a  mov     r14, [rdx+r15]
0x1800da50e  test    r14, r14
0x1800da511  jz      short loc_1800DA53B
0x1800da513  mov     rcx, [r14]; this
0x1800da516  test    rcx, rcx
0x1800da519  jz      short loc_1800DA520
0x1800da51b  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da520  mov     rcx, r14; Block
0x1800da523  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800da528  mov     rax, [rsp+118h+var_D0]
0x1800da52d  mov     [rax+r15], rbx
0x1800da531  mov     r8d, dword ptr [rsp+118h+var_C8]
0x1800da536  mov     rdx, [rsp+118h+var_D0]
0x1800da53b  inc     esi
0x1800da53d  cmp     esi, r8d
0x1800da540  jb      short loc_1800DA500
0x1800da542  mov     rcx, [rsp+118h+var_E0]
0x1800da547  mov     dword ptr [rsp+118h+var_F8], ebx
0x1800da54b  test    rdx, rdx
0x1800da54e  jz      short loc_1800DA562
0x1800da550  mov     rcx, rdx; this
0x1800da553  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da558  mov     [rsp+118h+var_D0], rbx
0x1800da55d  mov     rcx, [rsp+118h+var_E0]; this
0x1800da562  mov     [rsp+118h+var_C8], 0
0x1800da56b  test    rcx, rcx
0x1800da56e  jz      short loc_1800DA575
0x1800da570  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da575  mov     rcx, [rsp+118h+var_F0]; this
0x1800da57a  test    rcx, rcx
0x1800da57d  jz      short loc_1800DA585
0x1800da57f  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800da584  nop
0x1800da585  lea     rcx, [rsp+118h+var_B8]; this
0x1800da58a  call    ??1CacheLock@@QEAA@XZ; CacheLock::~CacheLock(void)
0x1800da58f  mov     eax, edi
0x1800da591  jmp     loc_1800DA9D1
0x1800da596  mov     ecx, eax; unsigned int
0x1800da598  call    ?isBlockSym@SymBuffer@@SA_NI@Z; SymBuffer::isBlockSym(uint)
0x1800da59d  test    al, al
0x1800da59f  jz      short loc_1800DA5D8
0x1800da5a1  movaps  xmm0, [rsp+118h+var_A8]
0x1800da5a6  movdqa  [rsp+118h+var_78], xmm0
0x1800da5af  lea     r8, [rsp+118h+var_78]
0x1800da5b7  lea     rdx, [rsp+118h+var_68]
0x1800da5bf  mov     rcx, r14
0x1800da5c2  call    ?skipblk@SymBuffer@@QEBA?AViterator@1@V21@@Z; SymBuffer::skipblk(SymBuffer::iterator)
0x1800da5c7  mov     rdi, [rax]
  ... truncated ...
```
