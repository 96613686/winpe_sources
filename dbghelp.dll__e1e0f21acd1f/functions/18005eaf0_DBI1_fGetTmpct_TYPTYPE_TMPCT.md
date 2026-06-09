# DBI1::fGetTmpct(TYPTYPE *,TMPCT * *)

- ea: `0x18005eaf0`
- end: `0x18005f3bc`
- name: `?fGetTmpct@DBI1@@AEAAHPEAUTYPTYPE@@PEAPEAVTMPCT@@@Z`
- size: `2252`
- prototype: `int(DBI1 *__hidden this, struct TYPTYPE *, struct TMPCT **)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800619e0`
- `0x18009e6e0`
- `0x1800a01b0`

## callees

- `0x180026980`
- `0x180027226`
- `0x18002723e`
- `0x180029c40`
- `0x180031c30`
- `0x180038b90`
- `0x18005b890`
- `0x18005eaf0`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005eebf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005ef1b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005ef69`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005efc7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005f0fc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005f16c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005f29c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005f302`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005eebf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005ef1b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005ef69`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005efc7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005f0fc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005f16c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005f29c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005f302`
- `api-ms-win-crt-private-l1-1-0!_o__wdupenv_s` at `0x18005eca5`
- `api-ms-win-crt-private-l1-1-0!_o__wdupenv_s` at `0x18005eca5`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005eee7`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005ef02`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005ef93`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005efae`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005eee7`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005ef02`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005ef93`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18005efae`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005ee02`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005ee02`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005ede8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005edf7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005ede8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005edf7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005ec8d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005eda9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005ec8d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005eda9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DBI1::fGetTmpct(DBI1 *this, struct TYPTYPE *a2, struct TMPCT **a3)
{
  struct TYPTYPE *v3; // rdi
  unsigned __int64 v5; // rdx
  WCHAR *v6; // rax
  __int64 v7; // rax
  const wchar_t *v8; // r12
  const wchar_t *v9; // r13
  int v10; // edx
  wchar_t *v11; // rax
  wchar_t *v12; // rsi
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rdx
  char *v16; // rdi
  __int64 v17; // rax
  void *v18; // r8
  DBI1 *v19; // rsi
  unsigned int v20; // edi
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rbx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  PDB1 *v28; // rcx
  DBI1 *v29; // rcx
  __int64 *v30; // r15
  const wchar_t *v31; // rbx
  char v32; // si
  int v33; // edi
  const wchar_t **v34; // rbx
  const wchar_t **v35; // r12
  const wchar_t *v36; // rdi
  char v37; // r14
  int v38; // esi
  __int64 *v39; // rdi
  __int64 v40; // rcx
  __int64 v41; // rax
  unsigned __int64 v42; // rdx
  __int64 v43; // rax
  unsigned __int64 v44; // rax
  __int64 *v45; // rbx
  __int64 *v46; // rsi
  __int64 v47; // rcx
  __int64 v48; // rax
  unsigned __int64 v49; // rdx
  __int64 v50; // rax
  unsigned __int64 v51; // rax
  wchar_t *v52; // rbx
  __int64 *v53; // rsi
  __int64 v54; // rcx
  __int64 v55; // rax
  unsigned __int64 v56; // rdx
  __int64 v57; // rax
  unsigned __int64 v58; // rax
  __int64 *v59; // rdi
  __int64 *v60; // r14
  __int64 v61; // rcx
  __int64 v62; // rax
  unsigned __int64 v63; // rdx
  __int64 v64; // rax
  unsigned __int64 v65; // rax
  PSGSI1::EnumPubsByAddr *v66; // rbx
  PSGSI1::EnumPubsByAddr *v67; // rcx
  char v69; // [rsp+20h] [rbp-E0h]
  int v71; // [rsp+30h] [rbp-D0h]
  wchar_t *Path; // [rsp+38h] [rbp-C8h]
  __int128 v73; // [rsp+40h] [rbp-C0h]
  __int128 v74; // [rsp+40h] [rbp-C0h]
  __int128 v75; // [rsp+40h] [rbp-C0h]
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  struct TMPCT **v77; // [rsp+58h] [rbp-A8h]
  struct TYPTYPE *v78; // [rsp+60h] [rbp-A0h]
  __int64 v79; // [rsp+68h] [rbp-98h]
  void **v80; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v81; // [rsp+78h] [rbp-88h]
  PSGSI1::EnumPubsByAddr *v82; // [rsp+80h] [rbp-80h]
  WCHAR WideCharStr[196]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t v84[264]; // [rsp+210h] [rbp+110h] BYREF
  wchar_t Buffer[264]; // [rsp+420h] [rbp+320h] BYREF

  v79 = -2;
  v77 = a3;
  v3 = a2;
  v78 = a2;
  v80 = &SafeStackAllocator<384>::`vftable';
  v82 = 0;
  v81 = 0;
  v5 = (2LL * *(unsigned __int16 *)a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( v5 > 0x180 )
  {
    v6 = (WCHAR *)SafeStackAllocator<528>::AllocInHeap(&v80);
    if ( !v6 )
    {
LABEL_133:
      v28 = (PDB1 *)*((_QWORD *)this + 18);
      goto LABEL_134;
    }
  }
  else
  {
    v6 = WideCharStr;
    v81 = v5;
  }
  v7 = SZNameFromTSRecord(v3, v6, *(unsigned __int16 *)v3);
  v8 = (const wchar_t *)v7;
  Path = (wchar_t *)v7;
  if ( !v7 )
    goto LABEL_133;
  v69 = 0;
  v9 = 0;
  v10 = *((_DWORD *)v3 + 1) + *((_DWORD *)v3 + 2);
  v71 = v10;
  if ( *(_WORD *)v7 != 37 )
  {
LABEL_44:
    v73 = 0;
    LODWORD(v73) = *((_DWORD *)v3 + 3);
    v29 = this;
    v30 = (__int64 *)*((_QWORD *)this + 20);
    if ( v30 )
    {
      while ( 1 )
      {
        if ( *((_DWORD *)v30 + 16) == v10 && *(_OWORD *)(v30 + 1) == v73 )
        {
          v31 = (const wchar_t *)v30[3];
          if ( v31 )
          {
            v32 = *(_BYTE *)(*((_QWORD *)v29 + 18) + 945LL);
            v33 = *((_DWORD *)v29 + 456);
            if ( !(unsigned int)_o__wcsicmp(v30[3], v8)
              || !v33
              && (v32 & 2) != 0
              && _wfullpath(Buffer, v8, 0x104u)
              && _wfullpath(v84, v31, 0x104u)
              && !(unsigned int)_o__wcsicmp(Buffer, v84) )
            {
              if ( v77 )
                *v77 = (struct TMPCT *)v30[7];
              v20 = 1;
              goto LABEL_74;
            }
            v29 = this;
          }
          v34 = (const wchar_t **)v30[4];
          v35 = (const wchar_t **)v30[5];
          if ( v34 != v35 )
            break;
        }
LABEL_64:
        v30 = (__int64 *)*v30;
        if ( !v30 )
          goto LABEL_72;
        v8 = Path;
        v29 = this;
        v10 = v71;
      }
      while ( 1 )
      {
        v36 = *v34;
        if ( *v34 )
        {
          v37 = *(_BYTE *)(*((_QWORD *)v29 + 18) + 945LL);
          v38 = *((_DWORD *)v29 + 456);
          if ( !(unsigned int)_o__wcsicmp(*v34, Path)
            || !v38
            && (v37 & 2) != 0
            && _wfullpath(v84, Path, 0x104u)
            && _wfullpath(Buffer, v36, 0x104u)
            && !(unsigned int)_o__wcsicmp(v84, Buffer) )
          {
            break;
          }
        }
        ++v34;
        v29 = this;
        if ( v34 == v35 )
          goto LABEL_64;
      }
      if ( v77 )
        *v77 = (struct TMPCT *)v30[7];
      v20 = 1;
    }
    else
    {
LABEL_72:
      v20 = 0;
    }
    v8 = Path;
LABEL_74:
    if ( !v69 )
      goto LABEL_98;
    if ( v20 )
      goto LABEL_136;
    v19 = this;
LABEL_77:
    v74 = 0;
    LODWORD(v74) = *((_DWORD *)v78 + 3);
    v39 = (__int64 *)*((_QWORD *)v19 + 20);
    if ( v39 )
    {
      while ( 1 )
      {
        if ( *((_DWORD *)v39 + 16) == v71 && *(_OWORD *)(v39 + 1) == v74 )
        {
          v40 = v39[3];
          if ( v40 )
          {
            v41 = -1;
            do
              ++v41;
            while ( v9[v41] );
            v42 = v41 + 1;
            v43 = -1;
            do
              ++v43;
            while ( *(_WORD *)(v40 + 2 * v43) );
            v44 = v43 + 1;
            if ( v44 >= v42 && !(unsigned int)_o__wcsicmp(v9, v40 + 2 * (v44 - v42)) )
              goto LABEL_127;
          }
          v45 = (__int64 *)v39[4];
          v46 = (__int64 *)v39[5];
          if ( v45 != v46 )
            break;
        }
LABEL_96:
        v39 = (__int64 *)*v39;
        if ( !v39 )
          goto LABEL_97;
      }
      while ( 1 )
      {
        v47 = *v45;
        if ( *v45 )
        {
          v48 = -1;
          do
            ++v48;
          while ( v9[v48] );
          v49 = v48 + 1;
          v50 = -1;
          do
            ++v50;
          while ( *(_WORD *)(v47 + 2 * v50) );
          v51 = v50 + 1;
          if ( v51 >= v49 && !(unsigned int)_o__wcsicmp(v9, v47 + 2 * (v51 - v49)) )
            break;
        }
        if ( ++v45 == v46 )
          goto LABEL_96;
      }
LABEL_127:
      if ( v77 )
        *v77 = (struct TMPCT *)v39[7];
      v20 = 1;
    }
    else
    {
LABEL_97:
      v20 = 0;
    }
LABEL_98:
    if ( v20 )
      goto LABEL_136;
    v19 = this;
    goto LABEL_100;
  }
  v11 = wcschr_0((const wchar_t *)(v7 + 2), 0x25u);
  v12 = v11;
  if ( !v11 )
  {
LABEL_43:
    v10 = v71;
    goto LABEL_44;
  }
  v13 = v11 - v8;
  if ( v13 > 0x7FFFFFFFFFFFFFF8LL )
    goto LABEL_42;
  v14 = 2 * v13;
  if ( *v80 == SafeStackAllocator<384>::AllocBytes )
  {
    if ( v14 >= 0xFFFFFFFFFFFFFFF0uLL )
    {
      v16 = 0;
      goto LABEL_16;
    }
    v15 = (v14 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( 384 - v81 >= v15 )
    {
      v16 = (char *)WideCharStr + v81;
      v81 += v15;
      goto LABEL_16;
    }
    v17 = SafeStackAllocator<528>::AllocInHeap(&v80);
  }
  else
  {
    v17 = ((__int64 (__fastcall *)(void ***, unsigned __int64))*v80)(&v80, v14);
  }
  v16 = (char *)v17;
LABEL_16:
  if ( !v16 )
  {
LABEL_42:
    PDB1::setOOMError(*((PDB1 **)this + 18));
LABEL_135:
    v20 = 0;
    goto LABEL_136;
  }
  v69 = 1;
  *v12 = 0;
  v9 = v12 + 1;
  _o_wcscpy_s(v16, v13, v8 + 1);
  Block = 0;
  _o__wdupenv_s(&Block, 0, v16);
  v18 = Block;
  if ( Block )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)Block + v21) );
    v22 = -1;
    do
      ++v22;
    while ( v9[v22] );
    v23 = v21 + v22 + 2;
    if ( v23 > 0x7FFFFFFFFFFFFFF8LL )
    {
LABEL_41:
      v28 = (PDB1 *)*((_QWORD *)this + 18);
LABEL_134:
      PDB1::setOOMError(v28);
      goto LABEL_135;
    }
    v24 = 2 * v23;
    if ( *v80 == SafeStackAllocator<384>::AllocBytes )
    {
      if ( v24 >= 0xFFFFFFFFFFFFFFF0uLL )
      {
        v8 = 0;
        Path = 0;
        goto LABEL_34;
      }
      v25 = (v24 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( 384 - v81 >= v25 )
      {
        v8 = (WCHAR *)((char *)WideCharStr + v81);
        Path = (WCHAR *)((char *)WideCharStr + v81);
        v81 += v25;
        goto LABEL_34;
      }
      v26 = SafeStackAllocator<528>::AllocInHeap(&v80);
    }
    else
    {
      v26 = ((__int64 (__fastcall *)(void ***, unsigned __int64))*v80)(&v80, v24);
    }
    v18 = Block;
    Path = (wchar_t *)v26;
    v8 = (const wchar_t *)v26;
LABEL_34:
    if ( v8 )
    {
      _o_wcscpy_s(v8, v23, v18);
      v27 = -1;
      do
        ++v27;
      while ( *((_WORD *)Block + v27) );
      if ( *((_WORD *)Block + v27 - 1) != 92 && *v9 != 92 )
        _o_wcscat_s(v8, v23);
      _o_wcscat_s(v8, v23);
      free(Block);
      v3 = v78;
      goto LABEL_43;
    }
    goto LABEL_41;
  }
  v19 = this;
  if ( *((_DWORD *)this + 456) || !(unsigned int)PDB1::FMinimal(*((PDB1 **)this + 18)) )
    goto LABEL_77;
  v20 = 0;
LABEL_100:
  if ( !*((_DWORD *)v19 + 456) && (unsigned int)PDB1::FMinimal(*((PDB1 **)v19 + 18)) )
  {
    if ( v69 )
      v8 = v9;
    v52 = wcsrchr_0(v8, 0x5Cu);
    if ( v52 || (v52 = wcsrchr_0(v8, 0x2Fu)) != 0 )
    {
      v75 = 0;
      LODWORD(v75) = *((_DWORD *)v78 + 3);
      v53 = (__int64 *)*((_QWORD *)v19 + 20);
      if ( v53 )
      {
        while ( 1 )
        {
          if ( *((_DWORD *)v53 + 16) == v71 && *(_OWORD *)(v53 + 1) == v75 )
          {
            v54 = v53[3];
            if ( v54 )
            {
              v55 = -1;
              do
                ++v55;
              while ( v52[v55] );
              v56 = v55 + 1;
              v57 = -1;
              do
                ++v57;
              while ( *(_WORD *)(v54 + 2 * v57) );
              v58 = v57 + 1;
              if ( v58 >= v56 && !(unsigned int)_o__wcsicmp(v52, v54 + 2 * (v58 - v56)) )
                goto LABEL_130;
            }
            v59 = (__int64 *)v53[4];
            v60 = (__int64 *)v53[5];
            if ( v59 != v60 )
              break;
          }
LABEL_125:
          v53 = (__int64 *)*v53;
          if ( !v53 )
            goto LABEL_126;
        }
        while ( 1 )
        {
          v61 = *v59;
          if ( *v59 )
          {
            v62 = -1;
            do
              ++v62;
            while ( v52[v62] );
            v63 = v62 + 1;
            v64 = -1;
            do
              ++v64;
            while ( *(_WORD *)(v61 + 2 * v64) );
            v65 = v64 + 1;
            if ( v65 >= v63 && !(unsigned int)_o__wcsicmp(v52, v61 + 2 * (v65 - v63)) )
              break;
          }
          if ( ++v59 == v60 )
            goto LABEL_125;
        }
LABEL_130:
        if ( v77 )
          *v77 = (struct TMPCT *)v53[7];
        v20 = 1;
      }
      else
      {
LABEL_126:
        v20 = 0;
      }
    }
  }
LABEL_136:
  v80 = &SafeStackAllocator<384>::`vftable';
  v66 = v82;
  while ( v66 )
  {
    v67 = v66;
    v66 = *(PSGSI1::EnumPubsByAddr **)v66;
    PSGSI1::EnumPubsByAddr::release(v67);
  }
  return v20;
}

```

## disassembly

```asm
0x18005eaf0  push    rbp
0x18005eaf2  push    rsi
0x18005eaf3  push    rdi
0x18005eaf4  push    r12
0x18005eaf6  push    r13
0x18005eaf8  push    r14
0x18005eafa  push    r15
0x18005eafc  lea     rbp, [rsp-540h]
0x18005eb04  sub     rsp, 640h
0x18005eb0b  mov     [rsp+670h+var_608], 0FFFFFFFFFFFFFFFEh
0x18005eb14  mov     [rsp+670h+arg_18], rbx
0x18005eb1c  mov     rax, cs:__security_cookie
0x18005eb23  xor     rax, rsp
0x18005eb26  mov     [rbp+570h+var_40], rax
0x18005eb2d  mov     [rsp+670h+var_618], r8
0x18005eb32  mov     rdi, rdx
0x18005eb35  mov     [rsp+670h+var_610], rdx
0x18005eb3a  mov     rbx, rcx
0x18005eb3d  mov     [rsp+670h+var_648], rcx
0x18005eb42  lea     rax, ??_7?$SafeStackAllocator@$0BIA@@@6B@; const SafeStackAllocator<384>::`vftable'
0x18005eb49  mov     [rsp+670h+var_600], rax
0x18005eb4e  xor     r14d, r14d
0x18005eb51  mov     [rbp+570h+var_5F0], r14
0x18005eb55  mov     [rsp+670h+var_5F8], r14
0x18005eb5a  movzx   eax, word ptr [rdx]
0x18005eb5d  lea     rdx, ds:7[rax*2]
0x18005eb65  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005eb69  mov     r15d, 180h
0x18005eb6f  cmp     rdx, r15
0x18005eb72  ja      short loc_18005EB7F
0x18005eb74  lea     rax, [rbp+570h+WideCharStr]
0x18005eb78  mov     [rsp+670h+var_5F8], rdx
0x18005eb7d  jmp     short loc_18005EB92
0x18005eb7f  lea     rcx, [rsp+670h+var_600]
0x18005eb84  call    ?AllocInHeap@?$SafeStackAllocator@$0CBA@@@IEAAPEAX_K@Z; SafeStackAllocator<528>::AllocInHeap(unsigned __int64)
0x18005eb89  test    rax, rax
0x18005eb8c  jz      loc_18005F35A
0x18005eb92  movzx   r8d, word ptr [rdi]; cchWideChar
0x18005eb96  mov     rdx, rax; lpWideCharStr
0x18005eb99  mov     rcx, rdi; struct TYPTYPE *
0x18005eb9c  call    SZNameFromTSRecord
0x18005eba1  mov     r12, rax
0x18005eba4  mov     [rsp+670h+Path], rax
0x18005eba9  test    rax, rax
0x18005ebac  jz      loc_18005F35A
0x18005ebb2  mov     [rsp+670h+var_650], 0
0x18005ebb7  mov     r13, r14
0x18005ebba  mov     edx, [rdi+8]
0x18005ebbd  add     edx, [rdi+4]
0x18005ebc0  mov     [rsp+670h+var_640], edx
0x18005ebc4  cmp     word ptr [rax], 25h ; '%'
0x18005ebc8  jnz     loc_18005EE40
0x18005ebce  mov     edx, 25h ; '%'; Ch
0x18005ebd3  lea     rcx, [rax+2]; Str
0x18005ebd7  call    wcschr_0
0x18005ebdc  mov     rsi, rax
0x18005ebdf  test    rax, rax
0x18005ebe2  jz      loc_18005EE39
0x18005ebe8  mov     rbx, rax
0x18005ebeb  sub     rbx, r12
0x18005ebee  sar     rbx, 1
0x18005ebf1  mov     rax, 7FFFFFFFFFFFFFF8h
0x18005ebfb  cmp     rbx, rax
0x18005ebfe  ja      loc_18005EE20
0x18005ec04  mov     rcx, [rsp+670h+var_600]
0x18005ec09  mov     rax, [rcx]
0x18005ec0c  lea     rdx, [rbx+rbx]
0x18005ec10  lea     rcx, ?AllocBytes@?$SafeStackAllocator@$0BIA@@@UEAAPEAX_K@Z; SafeStackAllocator<384>::AllocBytes(unsigned __int64)
0x18005ec17  cmp     rax, rcx
0x18005ec1a  jnz     short loc_18005EC5D
0x18005ec1c  cmp     rdx, 0FFFFFFFFFFFFFFF0h
0x18005ec20  jnb     short loc_18005EC57
0x18005ec22  add     rdx, 7
0x18005ec26  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005ec2a  mov     rax, r15
0x18005ec2d  mov     rcx, [rsp+670h+var_5F8]
0x18005ec32  sub     rax, rcx
0x18005ec35  cmp     rax, rdx
0x18005ec38  jb      short loc_18005EC4B
0x18005ec3a  lea     rdi, [rbp+570h+WideCharStr]
0x18005ec3e  add     rdi, rcx
0x18005ec41  add     rcx, rdx
0x18005ec44  mov     [rsp+670h+var_5F8], rcx
0x18005ec49  jmp     short loc_18005EC6B
0x18005ec4b  lea     rcx, [rsp+670h+var_600]
0x18005ec50  call    ?AllocInHeap@?$SafeStackAllocator@$0CBA@@@IEAAPEAX_K@Z; SafeStackAllocator<528>::AllocInHeap(unsigned __int64)
0x18005ec55  jmp     short loc_18005EC68
0x18005ec57  xor     eax, eax
0x18005ec59  mov     edi, eax
0x18005ec5b  jmp     short loc_18005EC6D
0x18005ec5d  lea     rcx, [rsp+670h+var_600]
0x18005ec62  call    cs:__guard_dispatch_icall_fptr
0x18005ec68  mov     rdi, rax
0x18005ec6b  xor     eax, eax
0x18005ec6d  test    rdi, rdi
0x18005ec70  jz      loc_18005EE20
0x18005ec76  mov     [rsp+670h+var_650], 1
0x18005ec7b  mov     [rsi], ax
0x18005ec7e  lea     r13, [rsi+2]
0x18005ec82  lea     r8, [r12+2]
0x18005ec87  mov     rdx, rbx
0x18005ec8a  mov     rcx, rdi
0x18005ec8d  call    cs:__imp__o_wcscpy_s
0x18005ec93  xor     r14d, r14d
0x18005ec96  mov     [rsp+670h+Block], r14
0x18005ec9b  mov     r8, rdi
0x18005ec9e  xor     edx, edx
0x18005eca0  lea     rcx, [rsp+670h+Block]
0x18005eca5  call    cs:__imp__o__wdupenv_s
0x18005ecab  mov     r8, [rsp+670h+Block]
0x18005ecb0  test    r8, r8
0x18005ecb3  jnz     short loc_18005ECE3
0x18005ecb5  mov     rsi, [rsp+670h+var_648]
0x18005ecba  cmp     [rsi+720h], r14d
0x18005ecc1  jnz     loc_18005F051
0x18005ecc7  mov     rcx, [rsi+90h]; this
0x18005ecce  call    ?FMinimal@PDB1@@UEAAHXZ; PDB1::FMinimal(void)
0x18005ecd3  test    eax, eax
0x18005ecd5  jz      loc_18005F051
0x18005ecdb  mov     edi, r14d
0x18005ecde  jmp     loc_18005F1A0
0x18005ece3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005ecea  nop     word ptr [rax+rax+00h]
0x18005ecf0  inc     rcx
0x18005ecf3  cmp     [r8+rcx*2], r14w
0x18005ecf8  jnz     short loc_18005ECF0
0x18005ecfa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005ed01  lea     rax, [rax+1]
0x18005ed05  cmp     [r13+rax*2+0], r14w
0x18005ed0b  jnz     short loc_18005ED01
0x18005ed0d  lea     rbx, [rax+2]
0x18005ed11  add     rbx, rcx
0x18005ed14  mov     rax, 7FFFFFFFFFFFFFF8h
0x18005ed1e  cmp     rbx, rax
0x18005ed21  ja      loc_18005EE0F
0x18005ed27  mov     rax, [rsp+670h+var_600]
0x18005ed2c  mov     rax, [rax]
0x18005ed2f  lea     rdx, [rbx+rbx]
0x18005ed33  lea     rcx, ?AllocBytes@?$SafeStackAllocator@$0BIA@@@UEAAPEAX_K@Z; SafeStackAllocator<384>::AllocBytes(unsigned __int64)
0x18005ed3a  cmp     rax, rcx
0x18005ed3d  jnz     short loc_18005ED86
0x18005ed3f  cmp     rdx, 0FFFFFFFFFFFFFFF0h
0x18005ed43  jnb     short loc_18005ED7C
0x18005ed45  add     rdx, 7
0x18005ed49  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005ed4d  mov     rax, [rsp+670h+var_5F8]
0x18005ed52  sub     r15, rax
0x18005ed55  cmp     r15, rdx
0x18005ed58  jb      short loc_18005ED70
0x18005ed5a  lea     r12, [rbp+570h+WideCharStr]
0x18005ed5e  add     r12, rax
0x18005ed61  mov     [rsp+670h+Path], r12
0x18005ed66  add     rax, rdx
0x18005ed69  mov     [rsp+670h+var_5F8], rax
0x18005ed6e  jmp     short loc_18005ED9E
0x18005ed70  lea     rcx, [rsp+670h+var_600]
0x18005ed75  call    ?AllocInHeap@?$SafeStackAllocator@$0CBA@@@IEAAPEAX_K@Z; SafeStackAllocator<528>::AllocInHeap(unsigned __int64)
0x18005ed7a  jmp     short loc_18005ED91
0x18005ed7c  mov     r12, r14
0x18005ed7f  mov     [rsp+670h+Path], r14
0x18005ed84  jmp     short loc_18005ED9E
0x18005ed86  lea     rcx, [rsp+670h+var_600]
0x18005ed8b  call    cs:__guard_dispatch_icall_fptr
0x18005ed91  mov     r8, [rsp+670h+Block]
0x18005ed96  mov     [rsp+670h+Path], rax
0x18005ed9b  mov     r12, rax
0x18005ed9e  test    r12, r12
0x18005eda1  jz      short loc_18005EE0F
0x18005eda3  mov     rdx, rbx
0x18005eda6  mov     rcx, r12
0x18005eda9  call    cs:__imp__o_wcscpy_s
0x18005edaf  mov     rcx, [rsp+670h+Block]
0x18005edb4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005edbb  nop     dword ptr [rax+rax+00h]
0x18005edc0  lea     rax, [rax+1]
0x18005edc4  cmp     [rcx+rax*2], r14w
0x18005edc9  jnz     short loc_18005EDC0
0x18005edcb  cmp     word ptr [rcx+rax*2-2], 5Ch ; '\'
0x18005edd1  jz      short loc_18005EDEE
0x18005edd3  cmp     word ptr [r13+0], 5Ch ; '\'
0x18005edd9  jz      short loc_18005EDEE
0x18005eddb  lea     r8, asc_180249970; "\\"
0x18005ede2  mov     rdx, rbx
0x18005ede5  mov     rcx, r12
0x18005ede8  call    cs:__imp__o_wcscat_s
0x18005edee  mov     r8, r13
0x18005edf1  mov     rdx, rbx
0x18005edf4  mov     rcx, r12
0x18005edf7  call    cs:__imp__o_wcscat_s
0x18005edfd  mov     rcx, [rsp+670h+Block]; Block
0x18005ee02  call    cs:__imp_free
0x18005ee08  mov     rdi, [rsp+670h+var_610]
0x18005ee0d  jmp     short loc_18005EE3C
0x18005ee0f  mov     rcx, [rsp+670h+var_648]
0x18005ee14  mov     rcx, [rcx+90h]
0x18005ee1b  jmp     loc_18005F361
0x18005ee20  mov     rcx, [rsp+670h+var_648]
0x18005ee25  mov     rcx, [rcx+90h]; this
0x18005ee2c  call    ?setOOMError@PDB1@@QEAAXXZ; PDB1::setOOMError(void)
0x18005ee31  xor     r14d, r14d
0x18005ee34  jmp     loc_18005F366
0x18005ee39  xor     r14d, r14d
0x18005ee3c  mov     edx, [rsp+670h+var_640]
0x18005ee40  xorps   xmm0, xmm0
0x18005ee43  movups  [rsp+670h+var_630], xmm0
0x18005ee48  mov     eax, [rdi+0Ch]
0x18005ee4b  mov     dword ptr [rsp+670h+var_630], eax
0x18005ee4f  movaps  xmm0, [rsp+670h+var_630]
0x18005ee54  movdqa  [rsp+670h+var_630], xmm0
0x18005ee5a  mov     rcx, [rsp+670h+var_648]
0x18005ee5f  mov     r15, [rcx+0A0h]
0x18005ee66  test    r15, r15
0x18005ee69  jz      loc_18005F031
0x18005ee6f  nop
0x18005ee70  cmp     [r15+40h], edx
0x18005ee74  jnz     loc_18005EFE3
0x18005ee7a  mov     rax, qword ptr [rsp+670h+var_630]
0x18005ee7f  cmp     [r15+8], rax
0x18005ee83  jnz     loc_18005EFE3
0x18005ee89  mov     rax, qword ptr [rsp+670h+var_630+8]
0x18005ee8e  cmp     [r15+10h], rax
0x18005ee92  jnz     loc_18005EFE3
0x18005ee98  mov     rbx, [r15+18h]
0x18005ee9c  test    rbx, rbx
0x18005ee9f  jz      loc_18005EF2E
0x18005eea5  mov     rax, [rcx+90h]
0x18005eeac  movzx   esi, byte ptr [rax+3B1h]
0x18005eeb3  mov     edi, [rcx+720h]
0x18005eeb9  mov     rdx, r12
0x18005eebc  mov     rcx, rbx
0x18005eebf  call    cs:__imp__o__wcsicmp
0x18005eec5  test    eax, eax
0x18005eec7  jz      loc_18005EFFE
0x18005eecd  test    edi, edi
0x18005eecf  jnz     short loc_18005EF29
0x18005eed1  test    sil, 2
0x18005eed5  jz      short loc_18005EF29
0x18005eed7  mov     r8d, 104h; BufferCount
0x18005eedd  mov     rdx, r12; Path
0x18005eee0  lea     rcx, [rbp+570h+Buffer]; Buffer
0x18005eee7  call    cs:__imp__wfullpath
0x18005eeed  test    rax, rax
0x18005eef0  jz      short loc_18005EF29
0x18005eef2  mov     r8d, 104h; BufferCount
0x18005eef8  mov     rdx, rbx; Path
0x18005eefb  lea     rcx, [rbp+570h+var_460]; Buffer
0x18005ef02  call    cs:__imp__wfullpath
0x18005ef08  test    rax, rax
0x18005ef0b  jz      short loc_18005EF29
0x18005ef0d  lea     rdx, [rbp+570h+var_460]
0x18005ef14  lea     rcx, [rbp+570h+Buffer]
0x18005ef1b  call    cs:__imp__o__wcsicmp
0x18005ef21  test    eax, eax
0x18005ef23  jz      loc_18005EFFE
0x18005ef29  mov     rcx, [rsp+670h+var_648]
0x18005ef2e  mov     rbx, [r15+20h]
0x18005ef32  mov     r12, [r15+28h]
0x18005ef36  cmp     rbx, r12
0x18005ef39  jz      loc_18005EFE3
0x18005ef3f  nop
0x18005ef40  mov     rdi, [rbx]
0x18005ef43  test    rdi, rdi
0x18005ef46  jz      loc_18005EFD1
0x18005ef4c  mov     rax, [rcx+90h]
0x18005ef53  movzx   r14d, byte ptr [rax+3B1h]
0x18005ef5b  mov     esi, [rcx+720h]
0x18005ef61  mov     rdx, [rsp+670h+Path]
0x18005ef66  mov     rcx, rdi
0x18005ef69  call    cs:__imp__o__wcsicmp
0x18005ef6f  test    eax, eax
0x18005ef71  jz      loc_18005F016
0x18005ef77  test    esi, esi
0x18005ef79  jnz     short loc_18005EFD1
0x18005ef7b  test    r14b, 2
0x18005ef7f  jz      short loc_18005EFD1
0x18005ef81  mov     r8d, 104h; BufferCount
0x18005ef87  mov     rdx, [rsp+670h+Path]; Path
0x18005ef8c  lea     rcx, [rbp+570h+var_460]; Buffer
0x18005ef93  call    cs:__imp__wfullpath
0x18005ef99  test    rax, rax
0x18005ef9c  jz      short loc_18005EFD1
0x18005ef9e  mov     r8d, 104h; BufferCount
0x18005efa4  mov     rdx, rdi; Path
0x18005efa7  lea     rcx, [rbp+570h+Buffer]; Buffer
0x18005efae  call    cs:__imp__wfullpath
0x18005efb4  test    rax, rax
0x18005efb7  jz      short loc_18005EFD1
0x18005efb9  lea     rdx, [rbp+570h+Buffer]
0x18005efc0  lea     rcx, [rbp+570h+var_460]
0x18005efc7  call    cs:__imp__o__wcsicmp
0x18005efcd  test    eax, eax
0x18005efcf  jz      short loc_18005F016
0x18005efd1  add     rbx, 8
0x18005efd5  cmp     rbx, r12
0x18005efd8  mov     rcx, [rsp+670h+var_648]
0x18005efdd  jnz     loc_18005EF40
0x18005efe3  mov     r15, [r15]
0x18005efe6  test    r15, r15
0x18005efe9  jz      short loc_18005F02E
0x18005efeb  mov     r12, [rsp+670h+Path]
  ... truncated ...
```
