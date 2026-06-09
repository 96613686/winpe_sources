# web::json::details::JSON_Parser<ushort>::CompleteNumberLiteral(ushort,web::json::details::JSON_Parser<ushort>::Token &)

- ea: `0x140008ef0`
- end: `0x1400097ad`
- name: `?CompleteNumberLiteral@?$JSON_Parser@G@details@json@web@@AEAA_NGAEAUToken@1234@@Z`
- size: `2237`
- prototype: `char __fastcall(__int64, unsigned __int16, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400098a0`

## callees

- `0x140002f84`
- `0x140003244`
- `0x140003b1c`
- `0x140003b28`
- `0x140003c8c`
- `0x140007030`
- `0x140008ef0`
- `0x14000ae00`
- `0x14000c490`
- `0x140013dd0`
- `0x14003e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstod_l` at `0x1400096ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcstod_l` at `0x1400096ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall web::json::details::JSON_Parser<unsigned short>::CompleteNumberLiteral(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3)
{
  unsigned __int16 v4; // bx
  char v6; // r12
  __int16 v7; // ax
  unsigned __int64 v8; // r14
  unsigned __int16 v9; // ax
  __int64 v10; // rbx
  __int16 v11; // ax
  __int16 v12; // r15
  wchar_t *v13; // rax
  size_t v14; // rdi
  __crt_locale_pointers *Locale; // rax
  int v16; // eax
  __int64 v17; // r14
  wchar_t *v18; // rdi
  wchar_t *v19; // rbx
  unsigned __int64 v20; // r12
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // r13
  size_t v25; // r13
  void *v26; // rax
  wchar_t *v27; // rax
  unsigned __int64 v28; // rbx
  char v29; // r14
  __int64 v30; // r14
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // r15
  size_t v34; // r15
  _QWORD *v35; // rbx
  void *v36; // rax
  wchar_t *v37; // rdx
  char *v38; // rcx
  char *v39; // r8
  wchar_t *v40; // rax
  wchar_t v41; // ax
  wchar_t v42; // r12
  wchar_t *v43; // r14
  signed __int64 v44; // rdi
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // r15
  size_t v48; // r15
  _QWORD *v49; // rbx
  void *v50; // rax
  wchar_t *v51; // rdx
  char *v52; // rcx
  char *v53; // r8
  wchar_t *v54; // rax
  __int16 v55; // ax
  __int16 v56; // cx
  __int16 v57; // ax
  __int16 i; // ax
  wchar_t *v59; // rbx
  struct __crt_locale_pointers *v60; // rax
  double v61; // xmm0_8
  char v62; // di
  _BYTE *v63; // rcx
  wchar_t *Buffer[2]; // [rsp+30h] [rbp-20h] BYREF
  wchar_t *v65; // [rsp+40h] [rbp-10h]
  char v66; // [rsp+98h] [rbp+48h]
  __int16 v68; // [rsp+A8h] [rbp+58h] BYREF

  v4 = a2;
  if ( a2 == 45 )
  {
    v6 = 1;
    v66 = 1;
    v4 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
  }
  else
  {
    v6 = 0;
    v66 = 0;
  }
  if ( (unsigned __int16)(v4 - 48) > 9u )
    return 0;
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( v4 == 48 && v7 == 48 )
    return 0;
  v8 = v4 - 48LL;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( v9 >= 0x30u )
  {
    while ( v9 <= 0x39u )
    {
      if ( v8 > 0x1999999999999999LL
        || (v10 = (unsigned int)v9 - 48, v8 == 0x1999999999999999LL) && (unsigned int)v10 > 5 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
        goto LABEL_21;
      }
      (**(void (__fastcall ***)(__int64))a1)(a1);
      v8 = v10 + 10 * v8;
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      if ( v9 < 0x30u )
        break;
    }
  }
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v12 = v11;
  if ( v11 != 46 && v11 != 69 && v11 != 101 )
  {
    if ( v6 )
    {
      *(_BYTE *)(a3 + 64) = 1;
      if ( v8 <= 0x8000000000000000uLL )
      {
        *(_QWORD *)(a3 + 56) = -(__int64)v8;
        *(_DWORD *)a3 = 9;
      }
      else
      {
        *(double *)(a3 + 56) = 0.0 - ((double)(int)(v8 & 1 | (v8 >> 1)) + (double)(int)(v8 & 1 | (v8 >> 1)));
        *(_DWORD *)a3 = 8;
      }
      return 1;
    }
    else
    {
      *(_QWORD *)(a3 + 56) = v8;
      *(_DWORD *)a3 = 9;
      *(_BYTE *)(a3 + 64) = 0;
      return 1;
    }
  }
LABEL_21:
  v13 = (wchar_t *)operator new(0x30u);
  Buffer[0] = v13;
  v65 = v13 + 24;
  *(_OWORD *)v13 = 0;
  *((_OWORD *)v13 + 1) = 0;
  *((_OWORD *)v13 + 2) = 0;
  Buffer[1] = v13 + 24;
  v14 = v13 + 24 - Buffer[0];
  Locale = utility::details::scoped_c_thread_locale::c_locale();
  v16 = snwprintf_s_l(Buffer[0], v14, 0xFFFFFFFFFFFFFFFFuLL, L"%I64u", Locale, v8);
  v17 = v16;
  v18 = Buffer[1];
  v19 = Buffer[0];
  v20 = Buffer[1] - Buffer[0];
  if ( v16 >= v20 )
  {
    if ( v16 <= v20 )
      goto LABEL_48;
    v22 = v65 - Buffer[0];
    if ( v16 <= v22 )
    {
      v28 = v16 - v20;
      memset_0(Buffer[1], 0, v28 * 2);
      v18 = &Buffer[1][v28];
      v19 = Buffer[0];
      goto LABEL_47;
    }
    if ( (unsigned __int64)v16 > 0x7FFFFFFFFFFFFFFFLL )
LABEL_129:
      std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
    v23 = v22 >> 1;
    if ( v22 <= 0x7FFFFFFFFFFFFFFFLL - (v22 >> 1) )
    {
      v24 = v22 + v23;
      if ( v22 + v23 >= v16 )
      {
        if ( v24 > 0x7FFFFFFFFFFFFFFFLL )
          goto LABEL_130;
      }
      else
      {
        v24 = v16;
      }
      v25 = 2 * v24;
      if ( !v25 )
      {
        v19 = 0;
        goto LABEL_39;
      }
      if ( v25 < 0x1000 )
      {
        v19 = (wchar_t *)operator new(v25);
        goto LABEL_39;
      }
      if ( v25 + 39 >= v25 )
      {
        v26 = operator new(v25 + 39);
        if ( !v26 )
          goto LABEL_105;
        v19 = (wchar_t *)(((unsigned __int64)v26 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v19 - 1) = v26;
LABEL_39:
        memset_0(&v19[v20], 0, 2 * (v17 - v20));
        memmove_0(v19, Buffer[0], (char *)Buffer[1] - (char *)Buffer[0]);
        if ( !Buffer[0] )
        {
LABEL_45:
          Buffer[0] = v19;
          v18 = &v19[v17];
          v65 = &v19[v25 / 2];
          goto LABEL_47;
        }
        if ( (unsigned __int64)(2 * (v65 - Buffer[0])) < 0x1000 )
        {
          v27 = Buffer[0];
LABEL_44:
          operator delete(v27);
          goto LABEL_45;
        }
        v27 = (wchar_t *)*((_QWORD *)Buffer[0] - 1);
        if ( (unsigned __int64)((char *)Buffer[0] - (char *)v27 - 8) <= 0x1F )
          goto LABEL_44;
LABEL_105:
        __fastfail(5u);
      }
    }
LABEL_130:
    __scrt_throw_std_bad_array_new_length();
  }
  v18 = &Buffer[0][v16];
LABEL_47:
  Buffer[1] = v18;
LABEL_48:
  v29 = 0;
  if ( v12 == -1 )
    goto LABEL_116;
  while ( 1 )
  {
    if ( (unsigned __int16)(v12 - 48) <= 9u )
    {
      v68 = v12;
      std::vector<unsigned short>::push_back(Buffer, &v68);
      goto LABEL_103;
    }
    if ( v12 != 46 )
      break;
    if ( v29 )
      goto LABEL_124;
    if ( v18 == v65 )
    {
      v30 = v18 - v19;
      if ( v30 == 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_129;
      v31 = v65 - v19;
      v32 = v31 >> 1;
      if ( v31 > 0x7FFFFFFFFFFFFFFFLL - (v31 >> 1) )
        goto LABEL_130;
      v33 = v30 + 1;
      if ( v32 + v31 >= v30 + 1 )
        v33 = v32 + v31;
      if ( v33 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_130;
      v34 = 2 * v33;
      if ( v34 )
      {
        if ( v34 < 0x1000 )
        {
          v35 = operator new(v34);
        }
        else
        {
          if ( v34 + 39 < v34 )
            goto LABEL_130;
          v36 = operator new(v34 + 39);
          if ( !v36 )
            goto LABEL_105;
          v35 = (_QWORD *)(((unsigned __int64)v36 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v35 - 1) = v36;
        }
      }
      else
      {
        v35 = 0;
      }
      *((_WORD *)v35 + v30) = 46;
      v37 = Buffer[0];
      v38 = (char *)v35;
      if ( v18 == Buffer[1] )
      {
        v39 = (char *)((char *)Buffer[1] - (char *)Buffer[0]);
      }
      else
      {
        memmove_0(v35, Buffer[0], (char *)v18 - (char *)Buffer[0]);
        v39 = (char *)((char *)Buffer[1] - (char *)v18);
        v38 = (char *)v35 + 2 * v30 + 2;
        v37 = v18;
      }
      memmove_0(v38, v37, (size_t)v39);
      if ( Buffer[0] )
      {
        if ( (unsigned __int64)(2 * (v65 - Buffer[0])) < 0x1000 )
        {
          v40 = Buffer[0];
        }
        else
        {
          v40 = (wchar_t *)*((_QWORD *)Buffer[0] - 1);
          if ( (unsigned __int64)((char *)Buffer[0] - (char *)v40 - 8) > 0x1F )
            goto LABEL_105;
        }
        operator delete(v40);
      }
      Buffer[0] = (wchar_t *)v35;
      Buffer[1] = (wchar_t *)v35 + v30 + 1;
      v65 = (wchar_t *)((char *)v35 + v34);
    }
    else
    {
      *v18 = 46;
      ++Buffer[1];
    }
    (**(void (__fastcall ***)(__int64))a1)(a1);
    v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v42 = v41;
    if ( (unsigned __int16)(v41 - 48) > 9u )
      goto LABEL_123;
    v43 = Buffer[1];
    if ( Buffer[1] == v65 )
    {
      v44 = Buffer[1] - Buffer[0];
      if ( v44 == 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_129;
      v45 = v65 - Buffer[0];
      v46 = v45 >> 1;
      if ( v45 > 0x7FFFFFFFFFFFFFFFLL - (v45 >> 1) )
        goto LABEL_130;
      v47 = v44 + 1;
      if ( v46 + v45 >= v44 + 1 )
        v47 = v46 + v45;
      if ( v47 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_130;
      v48 = 2 * v47;
      if ( v48 )
      {
        if ( v48 < 0x1000 )
        {
          v49 = operator new(v48);
        }
        else
        {
          if ( v48 + 39 < v48 )
            goto LABEL_130;
          v50 = operator new(v48 + 39);
          if ( !v50 )
            goto LABEL_105;
          v49 = (_QWORD *)(((unsigned __int64)v50 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v49 - 1) = v50;
        }
      }
      else
      {
        v49 = 0;
      }
      *((_WORD *)v49 + v44) = v42;
      v51 = Buffer[0];
      v52 = (char *)v49;
      if ( v43 == Buffer[1] )
      {
        v53 = (char *)((char *)Buffer[1] - (char *)Buffer[0]);
      }
      else
      {
        memmove_0(v49, Buffer[0], (char *)v43 - (char *)Buffer[0]);
        v53 = (char *)((char *)Buffer[1] - (char *)v43);
        v52 = (char *)v49 + 2 * v44 + 2;
        v51 = v43;
      }
      memmove_0(v52, v51, (size_t)v53);
      if ( Buffer[0] )
      {
        if ( (unsigned __int64)(2 * (v65 - Buffer[0])) < 0x1000 )
        {
          v54 = Buffer[0];
        }
        else
        {
          v54 = (wchar_t *)*((_QWORD *)Buffer[0] - 1);
          if ( (unsigned __int64)((char *)Buffer[0] - (char *)v54 - 8) > 0x1F )
            goto LABEL_105;
        }
        operator delete(v54);
      }
      Buffer[0] = (wchar_t *)v49;
      Buffer[1] = (wchar_t *)v49 + v44 + 1;
      v65 = (wchar_t *)((char *)v49 + v48);
    }
    else
    {
      *Buffer[1]++ = v41;
    }
    v29 = 1;
LABEL_103:
    (**(void (__fastcall ***)(__int64))a1)(a1);
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    if ( v12 == -1 )
      goto LABEL_116;
    v18 = Buffer[1];
    v19 = Buffer[0];
  }
  if ( ((v12 - 69) & 0xFFDF) != 0 )
    goto LABEL_116;
  v68 = v12;
  std::vector<unsigned short>::push_back(Buffer, &v68);
  (**(void (__fastcall ***)(__int64))a1)(a1);
  v55 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v56 = v55;
  if ( v55 == 43 )
  {
    v57 = 43;
    goto LABEL_111;
  }
  if ( v55 == 45 )
  {
    v57 = 45;
LABEL_111:
    v68 = v57;
    std::vector<unsigned short>::push_back(Buffer, &v68);
    (**(void (__fastcall ***)(__int64))a1)(a1);
    v56 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( (unsigned __int16)(v56 - 48) > 9u )
  {
LABEL_123:
    v19 = Buffer[0];
LABEL_124:
    v62 = 0;
  }
  else
  {
    v68 = v56;
    std::vector<unsigned short>::push_back(Buffer, &v68);
    (**(void (__fastcall ***)(__int64))a1)(a1);
    for ( i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
          (unsigned __int16)i >= 0x30u;
          i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) )
    {
      if ( (unsigned __int16)i > 0x39u )
        break;
      v68 = i;
      std::vector<unsigned short>::push_back(Buffer, &v68);
      (**(void (__fastcall ***)(__int64))a1)(a1);
    }
LABEL_116:
    v68 = 0;
    std::vector<unsigned short>::push_back(Buffer, &v68);
    v59 = Buffer[0];
    v60 = utility::details::scoped_c_thread_locale::c_locale();
    v61 = _o__wcstod_l(v59, 0, v60);
    *(double *)(a3 + 56) = v61;
    if ( v66 )
      *(_QWORD *)(a3 + 56) = *(_QWORD *)&v61 ^ _xmm;
    *(_DWORD *)a3 = 8;
    v62 = 1;
    v19 = Buffer[0];
  }
  if ( !v19 )
    return v62;
  if ( (unsigned __int64)(2 * (v65 - v19)) < 0x1000 )
  {
    operator delete(v19);
    return v62;
  }
  v63 = (_BYTE *)*((_QWORD *)v19 - 1);
  if ( (unsigned __int64)((char *)v19 - v63 - 8) > 0x1F )
    __fastfail(5u);
  operator delete(v63);
  return v62;
}

```

## disassembly

```asm
0x140008ef0  mov     [rsp-38h+arg_0], rbx
0x140008ef5  mov     [rsp-38h+arg_10], r8
0x140008efa  push    rbp
0x140008efb  push    rsi
0x140008efc  push    rdi
0x140008efd  push    r12
0x140008eff  push    r13
0x140008f01  push    r14
0x140008f03  push    r15
0x140008f05  mov     rbp, rsp
0x140008f08  sub     rsp, 50h
0x140008f0c  mov     rdi, r8
0x140008f0f  movzx   ebx, dx
0x140008f12  mov     rsi, rcx
0x140008f15  cmp     dx, 2Dh ; '-'
0x140008f19  jnz     short loc_140008F32
0x140008f1b  mov     r12b, 1
0x140008f1e  mov     [rbp+arg_8], r12b
0x140008f22  mov     rax, [rcx]
0x140008f25  mov     rax, [rax]
0x140008f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f2d  movzx   ebx, ax
0x140008f30  jmp     short loc_140008F39
0x140008f32  xor     r12b, r12b
0x140008f35  mov     [rbp+arg_8], r12b
0x140008f39  lea     eax, [rbx-30h]
0x140008f3c  cmp     ax, 9
0x140008f40  ja      loc_140009787
0x140008f46  mov     rax, [rsi]
0x140008f49  mov     rcx, rsi
0x140008f4c  mov     rax, [rax+8]
0x140008f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f55  cmp     bx, 30h ; '0'
0x140008f59  jnz     short loc_140008F64
0x140008f5b  cmp     ax, bx
0x140008f5e  jz      loc_140009787
0x140008f64  movzx   r14d, bx
0x140008f68  sub     r14, 30h ; '0'
0x140008f6c  mov     rax, [rsi]
0x140008f6f  mov     rcx, rsi
0x140008f72  mov     rax, [rax+8]
0x140008f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f7b  cmp     ax, 30h ; '0'
0x140008f7f  jb      short loc_140008FDE
0x140008f81  mov     r15, 1999999999999999h
0x140008f8b  nop     dword ptr [rax+rax+00h]
0x140008f90  cmp     ax, 39h ; '9'
0x140008f94  ja      short loc_140008FDE
0x140008f96  cmp     r14, r15
0x140008f99  ja      loc_140009039
0x140008f9f  movzx   ebx, ax
0x140008fa2  add     ebx, 0FFFFFFD0h
0x140008fa5  cmp     r14, r15
0x140008fa8  jnz     short loc_140008FB3
0x140008faa  cmp     ebx, 5
0x140008fad  ja      loc_140009039
0x140008fb3  mov     rax, [rsi]
0x140008fb6  mov     rcx, rsi
0x140008fb9  mov     rax, [rax]
0x140008fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008fc1  lea     rcx, [r14+r14*4]
0x140008fc5  lea     r14, [rbx+rcx*2]
0x140008fc9  mov     rax, [rsi]
0x140008fcc  mov     rcx, rsi
0x140008fcf  mov     rax, [rax+8]
0x140008fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008fd8  cmp     ax, 30h ; '0'
0x140008fdc  jnb     short loc_140008F90
0x140008fde  mov     rax, [rsi]
0x140008fe1  mov     rcx, rsi
0x140008fe4  mov     rax, [rax+8]
0x140008fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008fed  movzx   r15d, ax
0x140008ff1  cmp     ax, 2Eh ; '.'
0x140008ff5  jz      short loc_14000904C
0x140008ff7  cmp     ax, 45h ; 'E'
0x140008ffb  jz      short loc_14000904C
0x140008ffd  cmp     ax, 65h ; 'e'
0x140009001  jz      short loc_14000904C
0x140009003  test    r12b, r12b
0x140009006  jz      loc_140009125
0x14000900c  mov     byte ptr [rdi+40h], 1
0x140009010  mov     rax, 8000000000000000h
0x14000901a  cmp     r14, rax
0x14000901d  jbe     loc_140009111
0x140009023  xorps   xmm1, xmm1
0x140009026  test    r14, r14
0x140009029  js      loc_1400090E2
0x14000902f  cvtsi2sd xmm1, r14
0x140009034  jmp     loc_1400090F8
0x140009039  mov     rax, [rsi]
0x14000903c  mov     rcx, rsi
0x14000903f  mov     rax, [rax+8]
0x140009043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009048  movzx   r15d, ax
0x14000904c  xorps   xmm0, xmm0
0x14000904f  movdqu  xmmword ptr [rbp+Buffer], xmm0
0x140009054  mov     [rbp+var_10], 0
0x14000905c  mov     ecx, 30h ; '0'; Size
0x140009061  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009066  mov     [rbp+Buffer], rax
0x14000906a  lea     rdi, [rax+30h]
0x14000906e  mov     [rbp+var_10], rdi
0x140009072  xorps   xmm0, xmm0
0x140009075  movups  xmmword ptr [rax], xmm0
0x140009078  movups  xmmword ptr [rax+10h], xmm0
0x14000907c  movups  xmmword ptr [rax+20h], xmm0
0x140009080  mov     [rbp+Buffer+8], rdi
0x140009084  mov     rbx, [rbp+Buffer]
0x140009088  sub     rdi, rbx
0x14000908b  sar     rdi, 1
0x14000908e  call    ?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ; utility::details::scoped_c_thread_locale::c_locale(void)
0x140009093  mov     [rsp+50h+var_28], r14
0x140009098  mov     [rsp+50h+Locale], rax; Locale
0x14000909d  lea     r9, aI64u; "%I64u"
0x1400090a4  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400090ab  mov     rdx, rdi; BufferCount
0x1400090ae  mov     rcx, rbx; Buffer
0x1400090b1  call    _snwprintf_s_l
0x1400090b6  movsxd  r14, eax
0x1400090b9  mov     rdi, [rbp+Buffer+8]
0x1400090bd  mov     r12, rdi
0x1400090c0  mov     rbx, [rbp+Buffer]
0x1400090c4  sub     r12, rbx
0x1400090c7  sar     r12, 1
0x1400090ca  mov     r13, 7FFFFFFFFFFFFFFFh
0x1400090d4  cmp     r14, r12
0x1400090d7  jnb     short loc_14000913A
0x1400090d9  lea     rdi, [rbx+r14*2]
0x1400090dd  jmp     loc_14000927C
0x1400090e2  mov     rax, r14
0x1400090e5  shr     rax, 1
0x1400090e8  and     r14d, 1
0x1400090ec  or      rax, r14
0x1400090ef  cvtsi2sd xmm1, rax
0x1400090f4  addsd   xmm1, xmm1
0x1400090f8  xorps   xmm0, xmm0
0x1400090fb  subsd   xmm0, xmm1
0x1400090ff  movsd   qword ptr [rdi+38h], xmm0
0x140009104  mov     dword ptr [rdi], 8
0x14000910a  mov     al, 1
0x14000910c  jmp     loc_140009789
0x140009111  neg     r14
0x140009114  mov     [rdi+38h], r14
0x140009118  mov     dword ptr [rdi], 9
0x14000911e  mov     al, 1
0x140009120  jmp     loc_140009789
0x140009125  mov     [rdi+38h], r14
0x140009129  mov     dword ptr [rdi], 9
0x14000912f  mov     byte ptr [rdi+40h], 0
0x140009133  mov     al, 1
0x140009135  jmp     loc_140009789
0x14000913a  jbe     loc_140009280
0x140009140  mov     rcx, [rbp+var_10]
0x140009144  sub     rcx, rbx
0x140009147  sar     rcx, 1
0x14000914a  cmp     r14, rcx
0x14000914d  jbe     loc_140009261
0x140009153  cmp     r14, r13
0x140009156  ja      loc_1400097A1
0x14000915c  mov     rdx, rcx
0x14000915f  shr     rdx, 1
0x140009162  mov     rax, r13
0x140009165  sub     rax, rdx
0x140009168  cmp     rcx, rax
0x14000916b  ja      loc_1400097A7
0x140009171  lea     r13, [rcx+rdx]
0x140009175  cmp     r13, r14
0x140009178  jnb     short loc_14000917F
0x14000917a  mov     r13, r14
0x14000917d  jmp     short loc_140009192
0x14000917f  mov     rax, 7FFFFFFFFFFFFFFFh
0x140009189  cmp     r13, rax
0x14000918c  ja      loc_1400097A7
0x140009192  add     r13, r13
0x140009195  jnz     short loc_14000919B
0x140009197  xor     ebx, ebx
0x140009199  jmp     short loc_1400091D8
0x14000919b  cmp     r13, 1000h
0x1400091a2  jb      short loc_1400091CD
0x1400091a4  lea     rcx, [r13+27h]; Size
0x1400091a8  cmp     rcx, r13
0x1400091ab  jbe     loc_1400097A7
0x1400091b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400091b6  test    rax, rax
0x1400091b9  jz      loc_1400095CC
0x1400091bf  lea     rbx, [rax+27h]
0x1400091c3  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1400091c7  mov     [rbx-8], rax
0x1400091cb  jmp     short loc_1400091D8
0x1400091cd  mov     rcx, r13; Size
0x1400091d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400091d5  mov     rbx, rax
0x1400091d8  mov     r8, r14
0x1400091db  sub     r8, r12
0x1400091de  add     r8, r8; Size
0x1400091e1  lea     rcx, [rbx+r12*2]; void *
0x1400091e5  xor     edx, edx; Val
0x1400091e7  call    memset_0
0x1400091ec  mov     r8, [rbp+Buffer+8]
0x1400091f0  mov     rdx, [rbp+Buffer]; Src
0x1400091f4  sub     r8, rdx; Size
0x1400091f7  mov     rcx, rbx; void *
0x1400091fa  call    memmove_0
0x1400091ff  mov     rcx, [rbp+Buffer]
0x140009203  test    rcx, rcx
0x140009206  jz      short loc_140009245
0x140009208  mov     rax, [rbp+var_10]
0x14000920c  sub     rax, rcx
0x14000920f  sar     rax, 1
0x140009212  lea     rdx, [rax+rax]
0x140009216  cmp     rdx, 1000h
0x14000921d  jb      short loc_14000923A
0x14000921f  mov     rax, [rcx-8]
0x140009223  sub     rcx, rax
0x140009226  sub     rcx, 8
0x14000922a  cmp     rcx, 1Fh
0x14000922e  ja      loc_1400095CC
0x140009234  add     rdx, 27h ; '''
0x140009238  jmp     short loc_14000923D
0x14000923a  mov     rax, rcx
0x14000923d  mov     rcx, rax; Block
0x140009240  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140009245  mov     [rbp+Buffer], rbx
0x140009249  lea     rdi, [rbx+r14*2]
0x14000924d  lea     rax, [rbx+r13]
0x140009251  mov     [rbp+var_10], rax
0x140009255  mov     r13, 7FFFFFFFFFFFFFFFh
0x14000925f  jmp     short loc_14000927C
0x140009261  sub     r14, r12
0x140009264  lea     rbx, [r14+r14]
0x140009268  mov     r8, rbx; Size
0x14000926b  xor     edx, edx; Val
0x14000926d  mov     rcx, rdi; void *
0x140009270  call    memset_0
0x140009275  add     rdi, rbx
0x140009278  mov     rbx, [rbp+Buffer]
0x14000927c  mov     [rbp+Buffer+8], rdi
0x140009280  xor     r14b, r14b
0x140009283  mov     eax, 0FFFFh
0x140009288  cmp     r15w, ax
0x14000928c  jz      loc_1400096DB
0x140009292  mov     ecx, 2Eh ; '.'
0x140009297  lea     eax, [r15-30h]
0x14000929b  cmp     ax, 9
0x14000929f  ja      short loc_1400092B8
0x1400092a1  mov     [rbp+arg_18], r15w
0x1400092a6  lea     rdx, [rbp+arg_18]
0x1400092aa  lea     rcx, [rbp+Buffer]
0x1400092ae  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x1400092b3  jmp     loc_140009585
0x1400092b8  cmp     r15w, 2Eh ; '.'
0x1400092bd  jnz     loc_1400095D3
0x1400092c3  test    r14b, r14b
0x1400092c6  jnz     loc_14000976D
0x1400092cc  cmp     rdi, [rbp+var_10]
0x1400092d0  jz      short loc_1400092DF
0x1400092d2  mov     [rdi], cx
0x1400092d5  add     [rbp+Buffer+8], 2
0x1400092da  jmp     loc_140009409
0x1400092df  mov     r14, rdi
0x1400092e2  sub     r14, rbx
0x1400092e5  sar     r14, 1
0x1400092e8  cmp     r14, r13
0x1400092eb  jz      loc_1400097A1
0x1400092f1  mov     rcx, [rbp+var_10]
0x1400092f5  sub     rcx, rbx
0x1400092f8  sar     rcx, 1
0x1400092fb  mov     rdx, rcx
0x1400092fe  shr     rdx, 1
0x140009301  mov     rax, r13
0x140009304  sub     rax, rdx
0x140009307  cmp     rcx, rax
0x14000930a  ja      loc_1400097A7
0x140009310  lea     r12, [r14+1]
0x140009314  lea     rax, [rdx+rcx]
0x140009318  mov     r15, r12
0x14000931b  cmp     rax, r12
0x14000931e  cmovnb  r15, rax
0x140009322  cmp     r15, r13
0x140009325  ja      loc_1400097A7
0x14000932b  add     r15, r15
0x14000932e  jnz     short loc_140009334
0x140009330  xor     ebx, ebx
0x140009332  jmp     short loc_140009371
0x140009334  cmp     r15, 1000h
0x14000933b  jb      short loc_140009366
0x14000933d  lea     rcx, [r15+27h]; Size
0x140009341  cmp     rcx, r15
0x140009344  jbe     loc_1400097A7
0x14000934a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000934f  test    rax, rax
0x140009352  jz      loc_1400095CC
0x140009358  lea     rbx, [rax+27h]
0x14000935c  and     rbx, 0FFFFFFFFFFFFFFE0h
0x140009360  mov     [rbx-8], rax
0x140009364  jmp     short loc_140009371
0x140009366  mov     rcx, r15; Size
0x140009369  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000936e  mov     rbx, rax
  ... truncated ...
```
