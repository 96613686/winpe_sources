# CLanguageBarItem::Update(ulong,ulong,ushort const *,ushort const *,HICON__ *,tagSIZE *,HBITMAP__ *,HBITMAP__ *,ushort)

- ea: `0x18002e860`
- end: `0x18002ec68`
- name: `?Update@CLanguageBarItem@@UEAAKKKPEBG0PEAUHICON__@@PEAUtagSIZE@@PEAUHBITMAP__@@3G@Z`
- size: `1032`
- prototype: `unsigned int(CLanguageBarItem *__hidden this, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, HICON, struct tagSIZE *, HBITMAP, HBITMAP, unsigned __int16)`
- caller_count: `5`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002dd14`
- `0x180073530`
- `0x1800bd538`
- `0x1800bd5d4`
- `0x1800bd678`

## callees

- `0x1800139a4`
- `0x18002e860`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002eb3c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002eb67`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002eb3c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002eb67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e938`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ea30`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e938`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ea30`
- `USER32!DestroyIcon` at `0x18002eaa9`
- `USER32!DestroyIcon` at `0x18002eaa9`
- `GDI32!DeleteObject` at `0x18002ec11`
- `GDI32!DeleteObject` at `0x18002ec2d`
- `GDI32!DeleteObject` at `0x18002ec11`
- `GDI32!DeleteObject` at `0x18002ec2d`

## pseudocode

```c
__int64 __fastcall CLanguageBarItem::Update(
        struct tagSIZE *this,
        int a2,
        LONG a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpString1,
        HICON a6,
        struct tagSIZE *a7,
        HBITMAP a8,
        HBITMAP a9,
        unsigned __int16 a10)
{
  unsigned int v13; // edi
  __int64 v14; // rbp
  const WCHAR *lpString2; // rax
  struct tagSIZE v16; // rcx
  __int64 v17; // rdx
  const unsigned __int16 *v18; // rax
  __int64 v19; // rbx
  unsigned __int64 v20; // rbx
  unsigned int v21; // eax
  _WORD *v22; // rax
  __int64 v23; // rcx
  _WORD *v24; // rcx
  const unsigned __int16 *v25; // r14
  const WCHAR *v26; // rax
  struct tagSIZE v27; // rcx
  __int64 v28; // rdx
  const unsigned __int16 *v29; // rax
  __int64 v30; // rbx
  unsigned __int64 v31; // rbx
  unsigned int v32; // eax
  _WORD *v33; // rax
  _WORD *v34; // rcx
  HICON v35; // rcx
  struct tagSIZE v37; // rcx
  bool v38; // zf
  bool v39; // zf
  void *v40; // rcx
  void **v41; // rbx
  void *v42; // rcx

  v13 = a2 & (*(__int64 (__fastcall **)(struct tagSIZE *))(*(_QWORD *)this + 152LL))(this);
  if ( (v13 & 0x10000) != 0 && this[4].cy != a3 )
    this[4].cy = a3;
  else
    v13 &= ~0x10000u;
  v14 = 2147483646;
  if ( (v13 & 4) == 0 )
    goto LABEL_65;
  lpString2 = (const WCHAR *)this[12];
  if ( !a4 )
  {
    v38 = lpString2 == 0;
LABEL_64:
    if ( !v38 )
      goto LABEL_7;
LABEL_65:
    v13 &= ~4u;
    goto LABEL_27;
  }
  if ( lpString2 )
  {
    v38 = CompareStringW(0x7Fu, 0, a4, -1, lpString2, -1) == 2;
    goto LABEL_64;
  }
LABEL_7:
  v16 = this[12];
  if ( v16 )
  {
    ((void (__fastcall *)(_QWORD))cicMemFree)(v16);
    this[12] = 0;
  }
  if ( !a4 )
    goto LABEL_27;
  v17 = 0x7FFFFFFF;
  v18 = a4;
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v17;
  }
  while ( v17 );
  v19 = (0x7FFFFFFF - v17) & -(__int64)(v17 != 0);
  if ( !v17 || !v19 )
    goto LABEL_27;
  v20 = v19 + 1;
  v21 = 2 * v20;
  if ( !is_mul_ok(v20, 2u) )
    v21 = -1;
  v22 = LocalAlloc(0x40u, v21);
  this[12] = (struct tagSIZE)v22;
  if ( !v22 )
    goto LABEL_27;
  if ( v20 )
  {
    if ( v20 > 0x7FFFFFFF )
    {
      *v22 = 0;
    }
    else
    {
      v23 = 2147483646;
      do
      {
        if ( !v23 )
          break;
        if ( !*a4 )
          break;
        *v22++ = *a4++;
        --v23;
        --v20;
      }
      while ( v20 );
      v24 = v22 - 1;
      if ( v20 )
        v24 = v22;
      *v24 = 0;
      if ( v20 )
        goto LABEL_27;
    }
  }
  **(_WORD **)&this[12] = 0;
LABEL_27:
  if ( (v13 & 0x12) == 0 )
    goto LABEL_60;
  v25 = lpString1;
  v26 = (const WCHAR *)this[13];
  if ( lpString1 )
  {
    if ( !v26 )
      goto LABEL_30;
    v39 = CompareStringW(0x7Fu, 0, lpString1, -1, v26, -1) == 2;
  }
  else
  {
    v39 = v26 == 0;
  }
  if ( v39 )
  {
LABEL_60:
    v13 &= ~2u;
    if ( (v13 & 0x10) != 0 && a10 == LOWORD(this[18].cx) )
      v13 &= ~0x10u;
    goto LABEL_49;
  }
LABEL_30:
  v27 = this[13];
  if ( v27 )
  {
    ((void (__fastcall *)(_QWORD))cicMemFree)(v27);
    this[13] = 0;
  }
  if ( lpString1 )
  {
    v28 = 0x7FFFFFFF;
    v29 = lpString1;
    do
    {
      if ( !*v29 )
        break;
      ++v29;
      --v28;
    }
    while ( v28 );
    v30 = (0x7FFFFFFF - v28) & -(__int64)(v28 != 0);
    if ( v28 )
    {
      if ( v30 )
      {
        v31 = v30 + 1;
        v32 = 2 * v31;
        if ( !is_mul_ok(v31, 2u) )
          v32 = -1;
        v33 = LocalAlloc(0x40u, v32);
        this[13] = (struct tagSIZE)v33;
        if ( v33 )
        {
          if ( v31 )
          {
            if ( v31 > 0x7FFFFFFF )
            {
              *v33 = 0;
            }
            else
            {
              do
              {
                if ( !v14 )
                  break;
                if ( !*v25 )
                  break;
                *v33++ = *v25++;
                --v14;
                --v31;
              }
              while ( v31 );
              v34 = v33 - 1;
              if ( v31 )
                v34 = v33;
              *v34 = 0;
              if ( v31 )
                goto LABEL_49;
            }
          }
          **(_WORD **)&this[13] = 0;
        }
      }
    }
  }
LABEL_49:
  if ( (v13 & 1) != 0 )
  {
    v35 = (HICON)this[14];
    if ( v35 )
    {
      DestroyIcon(v35);
LABEL_52:
      this[14] = (struct tagSIZE)a6;
      goto LABEL_53;
    }
    if ( a6 )
      goto LABEL_52;
  }
  v13 &= ~1u;
LABEL_53:
  if ( (v13 & 8) == 0 )
  {
LABEL_54:
    v13 &= ~8u;
    goto LABEL_55;
  }
  v40 = (void *)this[16];
  if ( v40 )
  {
    DeleteObject(v40);
    v41 = (void **)&this[17];
  }
  else
  {
    v41 = (void **)&this[17];
    if ( !*(_QWORD *)&this[17] && !a8 && !a9 )
      goto LABEL_54;
  }
  v42 = *v41;
  this[16] = (struct tagSIZE)a8;
  if ( v42 )
    DeleteObject(v42);
  *v41 = a9;
  if ( a7 )
    this[15] = *a7;
LABEL_55:
  if ( (v13 & 0x10) != 0 )
  {
    LOWORD(this[18].cx) = a10;
    if ( a7 )
      this[15] = *a7;
  }
  if ( v13 )
  {
    v37 = this[19];
    if ( v37 )
      (*(void (__fastcall **)(struct tagSIZE, _QWORD))(**(_QWORD **)&v37 + 24LL))(v37, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x18002e860  push    rbx
0x18002e862  push    rbp
0x18002e863  push    rsi
0x18002e864  push    rdi
0x18002e865  push    r12
0x18002e867  push    r13
0x18002e869  push    r14
0x18002e86b  push    r15
0x18002e86d  sub     rsp, 38h
0x18002e871  mov     rax, [rcx]
0x18002e874  mov     r14, r9
0x18002e877  mov     ebp, r8d
0x18002e87a  mov     ebx, edx
0x18002e87c  mov     rsi, rcx
0x18002e87f  mov     rax, [rax+98h]
0x18002e886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e88b  mov     edi, eax
0x18002e88d  and     edi, ebx
0x18002e88f  bt      edi, 10h
0x18002e893  jnb     short loc_18002E89E
0x18002e895  cmp     [rsi+24h], ebp
0x18002e898  jnz     loc_18002EB89
0x18002e89e  btr     edi, 10h
0x18002e8a2  xor     r13d, r13d
0x18002e8a5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e8a9  mov     ebp, 7FFFFFFEh
0x18002e8ae  lea     r15d, [r13+2]
0x18002e8b2  test    dil, 4
0x18002e8b6  jz      loc_18002EB4B
0x18002e8bc  mov     rax, [rsi+60h]
0x18002e8c0  test    r14, r14
0x18002e8c3  jz      loc_18002EB91
0x18002e8c9  test    rax, rax
0x18002e8cc  jnz     loc_18002EB28
0x18002e8d2  mov     rcx, [rsi+60h]
0x18002e8d6  test    rcx, rcx
0x18002e8d9  jnz     loc_18002EB96
0x18002e8df  test    r14, r14
0x18002e8e2  jz      loc_18002E999
0x18002e8e8  mov     edx, 7FFFFFFFh
0x18002e8ed  mov     rax, r14
0x18002e8f0  cmp     [rax], r13w
0x18002e8f4  jz      short loc_18002E8FF
0x18002e8f6  add     rax, r15
0x18002e8f9  sub     rdx, 1
0x18002e8fd  jnz     short loc_18002E8F0
0x18002e8ff  mov     ecx, 7FFFFFFFh
0x18002e904  mov     rax, rdx
0x18002e907  sub     rcx, rdx
0x18002e90a  neg     rax
0x18002e90d  sbb     rbx, rbx
0x18002e910  and     rbx, rcx
0x18002e913  test    rdx, rdx
0x18002e916  jz      short loc_18002E995
0x18002e918  test    rbx, rbx
0x18002e91b  jz      short loc_18002E995
0x18002e91d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002e924  inc     rbx
0x18002e927  mov     rax, r15
0x18002e92a  mul     rbx
0x18002e92d  cmovb   rax, rcx
0x18002e931  mov     ecx, 40h ; '@'; uFlags
0x18002e936  mov     edx, eax; uBytes
0x18002e938  call    cs:__imp_LocalAlloc
0x18002e93e  mov     [rsi+60h], rax
0x18002e942  test    rax, rax
0x18002e945  jz      short loc_18002E995
0x18002e947  test    rbx, rbx
0x18002e94a  jz      loc_18002EBA8
0x18002e950  cmp     rbx, 7FFFFFFFh
0x18002e957  ja      loc_18002EBA4
0x18002e95d  mov     rcx, rbp
0x18002e960  test    rcx, rcx
0x18002e963  jz      short loc_18002E980
0x18002e965  movzx   edx, word ptr [r14]
0x18002e969  test    dx, dx
0x18002e96c  jz      short loc_18002E980
0x18002e96e  mov     [rax], dx
0x18002e971  add     r14, r15
0x18002e974  add     rax, r15
0x18002e977  dec     rcx
0x18002e97a  sub     rbx, 1
0x18002e97e  jnz     short loc_18002E960
0x18002e980  test    rbx, rbx
0x18002e983  lea     rcx, [rax-2]
0x18002e987  cmovnz  rcx, rax
0x18002e98b  mov     [rcx], r13w
0x18002e98f  jz      loc_18002EBA8
0x18002e995  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e999  movzx   r12d, [rsp+78h+arg_48]
0x18002e9a2  test    dil, 12h
0x18002e9a6  jz      loc_18002EB05
0x18002e9ac  mov     r14, [rsp+78h+lpString1]
0x18002e9b4  mov     rax, [rsi+68h]
0x18002e9b8  test    r14, r14
0x18002e9bb  jz      loc_18002EBB5
0x18002e9c1  test    rax, rax
0x18002e9c4  jnz     loc_18002EB53
0x18002e9ca  mov     rcx, [rsi+68h]
0x18002e9ce  test    rcx, rcx
0x18002e9d1  jnz     loc_18002EBBA
0x18002e9d7  test    r14, r14
0x18002e9da  jz      loc_18002EA8A
0x18002e9e0  mov     edx, 7FFFFFFFh
0x18002e9e5  mov     rax, r14
0x18002e9e8  cmp     [rax], r13w
0x18002e9ec  jz      short loc_18002E9F7
0x18002e9ee  add     rax, r15
0x18002e9f1  sub     rdx, 1
0x18002e9f5  jnz     short loc_18002E9E8
0x18002e9f7  mov     ecx, 7FFFFFFFh
0x18002e9fc  mov     rax, rdx
0x18002e9ff  sub     rcx, rdx
0x18002ea02  neg     rax
0x18002ea05  sbb     rbx, rbx
0x18002ea08  and     rbx, rcx
0x18002ea0b  test    rdx, rdx
0x18002ea0e  jz      short loc_18002EA8A
0x18002ea10  test    rbx, rbx
0x18002ea13  jz      short loc_18002EA8A
0x18002ea15  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ea1c  inc     rbx
0x18002ea1f  mov     rax, r15
0x18002ea22  mul     rbx
0x18002ea25  cmovb   rax, rcx
0x18002ea29  mov     ecx, 40h ; '@'; uFlags
0x18002ea2e  mov     edx, eax; uBytes
0x18002ea30  call    cs:__imp_LocalAlloc
0x18002ea36  mov     [rsi+68h], rax
0x18002ea3a  test    rax, rax
0x18002ea3d  jz      short loc_18002EA8A
0x18002ea3f  test    rbx, rbx
0x18002ea42  jz      loc_18002EBCC
0x18002ea48  cmp     rbx, 7FFFFFFFh
0x18002ea4f  ja      loc_18002EBC8
0x18002ea55  test    rbp, rbp
0x18002ea58  jz      short loc_18002EA75
0x18002ea5a  movzx   ecx, word ptr [r14]
0x18002ea5e  test    cx, cx
0x18002ea61  jz      short loc_18002EA75
0x18002ea63  mov     [rax], cx
0x18002ea66  add     r14, r15
0x18002ea69  add     rax, r15
0x18002ea6c  dec     rbp
0x18002ea6f  sub     rbx, 1
0x18002ea73  jnz     short loc_18002EA55
0x18002ea75  test    rbx, rbx
0x18002ea78  lea     rcx, [rax-2]
0x18002ea7c  cmovnz  rcx, rax
0x18002ea80  mov     [rcx], r13w
0x18002ea84  jz      loc_18002EBCC
0x18002ea8a  test    dil, 1
0x18002ea8e  jz      loc_18002EB81
0x18002ea94  mov     rcx, [rsi+70h]; hIcon
0x18002ea98  mov     rbx, [rsp+78h+arg_28]
0x18002eaa0  test    rcx, rcx
0x18002eaa3  jz      loc_18002EB78
0x18002eaa9  call    cs:__imp_DestroyIcon
0x18002eaaf  mov     [rsi+70h], rbx
0x18002eab3  mov     r14, [rsp+78h+arg_30]
0x18002eabb  test    dil, 8
0x18002eabf  jnz     loc_18002EBD9
0x18002eac5  and     edi, 0FFFFFFF7h
0x18002eac8  test    dil, 10h
0x18002eacc  jnz     loc_18002EC4B
0x18002ead2  test    edi, edi
0x18002ead4  jnz     short loc_18002EAE9
0x18002ead6  mov     eax, edi
0x18002ead8  add     rsp, 38h
0x18002eadc  pop     r15
0x18002eade  pop     r14
0x18002eae0  pop     r13
0x18002eae2  pop     r12
0x18002eae4  pop     rdi
0x18002eae5  pop     rsi
0x18002eae6  pop     rbp
0x18002eae7  pop     rbx
0x18002eae8  retn
0x18002eae9  mov     rcx, [rsi+98h]
0x18002eaf0  test    rcx, rcx
0x18002eaf3  jz      short loc_18002EAD6
0x18002eaf5  mov     rdx, [rcx]
0x18002eaf8  mov     rax, [rdx+18h]
0x18002eafc  mov     edx, edi
0x18002eafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb03  jmp     short loc_18002EAD6
0x18002eb05  and     edi, 0FFFFFFFDh
0x18002eb08  test    dil, 10h
0x18002eb0c  jz      loc_18002EA8A
0x18002eb12  cmp     r12w, [rsi+90h]
0x18002eb1a  jnz     loc_18002EA8A
0x18002eb20  and     edi, 0FFFFFFEFh
0x18002eb23  jmp     loc_18002EA8A
0x18002eb28  xor     edx, edx; dwCmpFlags
0x18002eb2a  mov     [rsp+78h+cchCount2], ebx; cchCount2
0x18002eb2e  mov     r9d, ebx; cchCount1
0x18002eb31  mov     [rsp+78h+lpString2], rax; lpString2
0x18002eb36  mov     r8, r14; lpString1
0x18002eb39  lea     ecx, [rdx+7Fh]; Locale
0x18002eb3c  call    cs:__imp_CompareStringW
0x18002eb42  cmp     eax, r15d
0x18002eb45  jnz     loc_18002E8D2
0x18002eb4b  and     edi, 0FFFFFFFBh
0x18002eb4e  jmp     loc_18002E999
0x18002eb53  xor     edx, edx; dwCmpFlags
0x18002eb55  mov     [rsp+78h+cchCount2], ebx; cchCount2
0x18002eb59  mov     r9d, ebx; cchCount1
0x18002eb5c  mov     [rsp+78h+lpString2], rax; lpString2
0x18002eb61  mov     r8, r14; lpString1
0x18002eb64  lea     ecx, [rdx+7Fh]; Locale
0x18002eb67  call    cs:__imp_CompareStringW
0x18002eb6d  cmp     eax, r15d
0x18002eb70  jnz     loc_18002E9CA
0x18002eb76  jmp     short loc_18002EB05
0x18002eb78  test    rbx, rbx
0x18002eb7b  jnz     loc_18002EAAF
0x18002eb81  and     edi, 0FFFFFFFEh
0x18002eb84  jmp     loc_18002EAB3
0x18002eb89  mov     [rsi+24h], ebp
0x18002eb8c  jmp     loc_18002E8A2
0x18002eb91  test    rax, rax
0x18002eb94  jmp     short loc_18002EB45
0x18002eb96  call    cicMemFree
0x18002eb9b  mov     [rsi+60h], r13
0x18002eb9f  jmp     loc_18002E8DF
0x18002eba4  mov     [rax], r13w
0x18002eba8  mov     rcx, [rsi+60h]
0x18002ebac  mov     [rcx], r13w
0x18002ebb0  jmp     loc_18002E995
0x18002ebb5  test    rax, rax
0x18002ebb8  jmp     short loc_18002EB70
0x18002ebba  call    cicMemFree
0x18002ebbf  mov     [rsi+68h], r13
0x18002ebc3  jmp     loc_18002E9D7
0x18002ebc8  mov     [rax], r13w
0x18002ebcc  mov     rcx, [rsi+68h]
0x18002ebd0  mov     [rcx], r13w
0x18002ebd4  jmp     loc_18002EA8A
0x18002ebd9  mov     rcx, [rsi+80h]; ho
0x18002ebe0  mov     rbp, [rsp+78h+arg_40]
0x18002ebe8  mov     r15, [rsp+78h+arg_38]
0x18002ebf0  test    rcx, rcx
0x18002ebf3  jnz     short loc_18002EC11
0x18002ebf5  lea     rbx, [rsi+88h]
0x18002ebfc  cmp     [rbx], r13
0x18002ebff  jnz     short loc_18002EC1E
0x18002ec01  test    r15, r15
0x18002ec04  jnz     short loc_18002EC1E
0x18002ec06  test    rbp, rbp
0x18002ec09  jz      loc_18002EAC5
0x18002ec0f  jmp     short loc_18002EC1E
0x18002ec11  call    cs:__imp_DeleteObject
0x18002ec17  lea     rbx, [rsi+88h]
0x18002ec1e  mov     rcx, [rbx]; ho
0x18002ec21  mov     [rsi+80h], r15
0x18002ec28  test    rcx, rcx
0x18002ec2b  jz      short loc_18002EC33
0x18002ec2d  call    cs:__imp_DeleteObject
0x18002ec33  mov     [rbx], rbp
0x18002ec36  test    r14, r14
0x18002ec39  jz      loc_18002EAC8
0x18002ec3f  mov     rax, [r14]
0x18002ec42  mov     [rsi+78h], rax
0x18002ec46  jmp     loc_18002EAC8
0x18002ec4b  mov     [rsi+90h], r12w
0x18002ec53  test    r14, r14
0x18002ec56  jz      loc_18002EAD2
0x18002ec5c  mov     rax, [r14]
0x18002ec5f  mov     [rsi+78h], rax
0x18002ec63  jmp     loc_18002EAD2
```
