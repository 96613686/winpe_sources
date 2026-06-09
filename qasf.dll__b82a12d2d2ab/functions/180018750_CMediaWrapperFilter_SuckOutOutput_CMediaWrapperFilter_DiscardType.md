# CMediaWrapperFilter::SuckOutOutput(CMediaWrapperFilter::DiscardType)

- ea: `0x180018750`
- end: `0x180018eb5`
- name: `?SuckOutOutput@CMediaWrapperFilter@@IEAAJW4DiscardType@1@@Z`
- size: `1893`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x1800165e8`
- `0x1800174e4`
- `0x18001b4f0`

## callees

- `0x180001460`
- `0x1800071e8`
- `0x180015a10`
- `0x180015c64`
- `0x180016874`
- `0x180017324`
- `0x180018750`
- `0x180018ebc`
- `0x18001a88c`
- `0x18001aab8`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CMediaWrapperFilter::SuckOutOutput(__int64 a1, int a2)
{
  __int64 v2; // r8
  __int64 *v3; // r15
  __int64 v4; // r9
  __int64 v6; // rcx
  bool v7; // al
  struct _AMMediaType **v8; // rdx
  char v9; // r12
  __int64 v10; // r13
  struct _AMMediaType **v11; // rcx
  __int64 v12; // rbx
  char v13; // bl
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  CWrapperOutputPin *v17; // rdi
  int v18; // ebx
  __int64 v19; // rcx
  char v20; // al
  int v21; // edi
  struct _AMMediaType *v22; // r9
  unsigned int v23; // r8d
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  bool v27; // al
  _QWORD *v28; // rdi
  __int64 v29; // rbx
  unsigned int v30; // eax
  _QWORD *v31; // rbx
  __int64 v32; // rdi
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // eax
  unsigned int v36; // edi
  int v37; // eax
  int v38; // edi
  char v39; // r13
  __int64 v40; // r14
  __int64 v41; // rbx
  __int64 v42; // rdi
  __int64 v43; // rcx
  struct _AMMediaType *v44; // rcx
  _QWORD *v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  bool *v57; // [rsp+20h] [rbp-48h]
  bool v58; // [rsp+30h] [rbp-38h] BYREF
  bool v59; // [rsp+31h] [rbp-37h] BYREF
  int v60; // [rsp+34h] [rbp-34h]
  struct _AMMediaType *pv; // [rsp+38h] [rbp-30h] BYREF
  __int64 v62; // [rsp+40h] [rbp-28h] BYREF
  int i; // [rsp+48h] [rbp-20h] BYREF
  int v64; // [rsp+4Ch] [rbp-1Ch] BYREF

  v2 = *(unsigned int *)(a1 + 196);
  v3 = (__int64 *)(a1 + 144);
  v4 = 0;
  v60 = a2;
  for ( i = 0; (unsigned int)v4 < (unsigned int)v2; v2 = *(unsigned int *)(a1 + 196) )
  {
    *(_QWORD *)(*(_QWORD *)(*v3 + 8 * v4) + 360LL) = 0;
    v6 = *(_QWORD *)(*v3 + 8 * v4);
    v7 = *(_QWORD *)(v6 + 48) && ((_DWORD)v4 || a2 != 1);
    v4 = (unsigned int)(v4 + 1);
    *(_BYTE *)(v6 + 416) = v7;
  }
  v8 = (struct _AMMediaType **)(a1 + 152);
  while ( 1 )
  {
    v9 = 0;
    v10 = 0;
    v11 = v8;
    if ( (_DWORD)v2 )
      break;
LABEL_52:
    v31 = (_QWORD *)(a1 + 160);
LABEL_53:
    v34 = *(_QWORD *)(a1 + 208);
    if ( v34 )
    {
      pv = *v8;
      v35 = (*(__int64 (__fastcall **)(__int64, struct _AMMediaType **, __int64))(*(_QWORD *)v34 + 96LL))(v34, &pv, 8);
      v36 = v35;
      if ( v35 < 0 )
      {
        v54 = *(_QWORD *)(a1 + 104);
        *(_DWORD *)(a1 + 304) = 1;
        if ( v54 )
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v54 + 24LL))(v54, 3, v35);
        return v36;
      }
      v37 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct _AMMediaType *, int *))(*(_QWORD *)*v31 + 176LL))(
              *v31,
              1,
              *(unsigned int *)(a1 + 196),
              pv,
              &i);
    }
    else
    {
      v37 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, struct _AMMediaType *, int *))(*(_QWORD *)*v31 + 176LL))(
              *v31,
              1,
              v2,
              *v8,
              &i);
    }
    v38 = TranslateDMOError(v37);
    if ( v9 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v31 + 184LL))(*v31, 0);
    if ( v38 < 0 )
    {
      CMediaWrapperFilter::FreeOutputSamples((CMediaWrapperFilter *)a1);
      v18 = -2147024882;
      if ( v38 == -2147024882 )
      {
        v55 = *(_QWORD *)(a1 + 104);
        *(_DWORD *)(a1 + 304) = 1;
        if ( v55 )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v55 + 24LL))(v55, 3, -2147024882);
        return (unsigned int)v18;
      }
      if ( v38 == -2147467259 && !*(_DWORD *)(a1 + 308) )
      {
        v56 = *(_QWORD *)(a1 + 104);
        *(_DWORD *)(a1 + 308) = 1;
        if ( v56 )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v56 + 24LL))(v56, 7, -2147467259);
      }
      return 0;
    }
    v39 = 0;
    v40 = 0;
    if ( !*(_DWORD *)(a1 + 196) )
      return 0;
    v8 = (struct _AMMediaType **)(a1 + 152);
    do
    {
      v41 = 8 * v40;
      v42 = 32LL * (unsigned int)v40;
      if ( *(_QWORD *)((char *)&(*v8)->majortype.Data1 + v42) )
      {
        if ( ((*v8)->majortype.Data4[v42] & 1) != 0 )
        {
          v43 = *(_QWORD *)(*(_QWORD *)(*v3 + 8 * v40) + 360LL);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 64LL))(v43, 1);
          v8 = (struct _AMMediaType **)(a1 + 152);
        }
        v44 = *v8;
        if ( ((*v8)->majortype.Data4[v42] & 2) != 0 )
        {
          v45 = (_QWORD *)((char *)&v44->subtype.Data1 + v42);
          if ( (v44->majortype.Data4[v42] & 4) != 0 )
          {
            *(_QWORD *)&v44->subtype.Data4[v42] += *v45;
            v46 = *(_QWORD *)(a1 + 152);
            v47 = v42 + v46 + 24;
            v45 = (_QWORD *)(v42 + v46 + 16);
          }
          else
          {
            v47 = 0;
          }
          v48 = *(_QWORD *)(*(_QWORD *)(v41 + *(_QWORD *)(a1 + 144)) + 360LL);
          (*(void (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)v48 + 48LL))(v48, v45, v47);
        }
        v49 = *(_QWORD *)(a1 + 152);
        v64 = 0;
        (*(void (__fastcall **)(_QWORD, _QWORD, int *))(**(_QWORD **)(v42 + v49) + 40LL))(
          *(_QWORD *)(v42 + v49),
          0,
          &v64);
        if ( v64 && (!v60 || (_DWORD)v40) )
        {
          v50 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 8 * v40) + 360LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 96LL))(v50);
          v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v41 + *(_QWORD *)(a1 + 144)) + 136LL))(
                  *(_QWORD *)(v41 + *(_QWORD *)(a1 + 144)),
                  *(_QWORD *)(*(_QWORD *)(v41 + *(_QWORD *)(a1 + 144)) + 360LL));
          if ( v36 )
          {
            CMediaWrapperFilter::FreeOutputSamples((CMediaWrapperFilter *)a1);
            *(_DWORD *)(a1 + 448) = 1;
            return v36;
          }
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 144) + 8 * v40) + 420LL) = 0;
        }
        v41 = 8 * v40;
        v51 = *(_QWORD *)(*(_QWORD *)(8 * v40 + *(_QWORD *)(a1 + 144)) + 360LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v8 = (struct _AMMediaType **)(a1 + 152);
        *(_QWORD *)(*(_QWORD *)(8 * v40 + *(_QWORD *)(a1 + 144)) + 360LL) = 0;
      }
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 152) + 32LL * (unsigned int)v40 + 8) & 0x1000000) != 0
        && (v52 = *(_QWORD *)(v41 + *(_QWORD *)(a1 + 144)), *(_QWORD *)(v52 + 48))
        && ((_DWORD)v40 || v60 != 1) )
      {
        *(_BYTE *)(v52 + 416) = 1;
        v39 = 1;
      }
      else
      {
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 144) + v41) + 416LL) = 0;
      }
      v2 = *(unsigned int *)(a1 + 196);
      v40 = (unsigned int)(v40 + 1);
    }
    while ( (unsigned int)v40 < (unsigned int)v2 );
    if ( !v39 )
      return 0;
  }
  do
  {
    v12 = *(_QWORD *)(*v3 + 8 * v10);
    if ( !*(_BYTE *)(v12 + 416) )
    {
      *((_QWORD *)&(*v11)->majortype.Data1 + 4 * (unsigned int)v10) = 0;
      goto LABEL_45;
    }
    v13 = *(_BYTE *)(v12 + 418);
    if ( v13 )
    {
      v14 = *(_QWORD *)(a1 + 184);
      LODWORD(pv) = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, struct _AMMediaType **))(*(_QWORD *)v14 + 48LL))(
             v14,
             (unsigned int)v10,
             &pv) >= 0 )
        v13 = ((unsigned __int8)pv & 1) != 0 ? v13 : 0;
    }
    LODWORD(v57) = v13 != 0 ? 2 : 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, bool *))(**(_QWORD **)(*v3 + 8 * v10) + 128LL))(
            *(_QWORD *)(*v3 + 8 * v10),
            *(_QWORD *)(*v3 + 8 * v10) + 360LL,
            0,
            0,
            v57);
    if ( v15 < 0 )
    {
LABEL_85:
      v18 = v15;
      goto LABEL_87;
    }
    pv = 0;
    if ( !(_DWORD)v10 && *(_DWORD *)(a1 + 444) )
    {
      v16 = CMediaWrapperFilter::ChangeOutputFormatWhenUsingVideoInfoHeader2HackIfNecessary(
              (CMediaWrapperFilter *)a1,
              0);
      goto LABEL_34;
    }
    v17 = *(CWrapperOutputPin **)(*v3 + 8 * v10);
    if ( !CWrapperOutputPin::UsingDXVATransport(v17) )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD *, struct _AMMediaType **))(**((_QWORD **)v17 + 45) + 104LL))(
              *((_QWORD **)v17 + 45),
              &pv);
      if ( v18 < 0 )
        goto LABEL_35;
      v19 = *(_QWORD *)(*v3 + 8 * v10);
      v20 = *(_BYTE *)(v19 + 420);
      if ( v20 && *(_QWORD *)(v19 + 48) )
        goto LABEL_25;
      if ( !pv )
        goto LABEL_37;
      if ( v20 && *(_QWORD *)(v19 + 48) )
      {
LABEL_25:
        v21 = 0;
        v22 = pv;
        v58 = 0;
        v23 = 0;
        v59 = 0;
        while ( 1 )
        {
          v18 = CMediaWrapperFilter::ChangeOutputFormat((CMediaWrapperFilter *)a1, v10, v23, v22, &v58, &v59);
          if ( v18 < 0 )
            goto LABEL_35;
          if ( v59 )
          {
            if ( !v58 )
              v18 = -2147220967;
            goto LABEL_35;
          }
          if ( v58 )
            goto LABEL_35;
          v22 = pv;
          v23 = ++v21;
        }
      }
      v16 = CWrapperOutputPin::SetMediaType(v17, pv);
LABEL_34:
      v18 = v16;
LABEL_35:
      if ( pv )
        DeleteMediaType(pv);
LABEL_37:
      if ( v18 < 0 )
        goto LABEL_87;
    }
    v24 = *v3;
    v62 = 0;
    v25 = *(_QWORD *)(*(_QWORD *)(v24 + 8 * v10) + 360LL);
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 24LL))(v25, &v62);
    if ( v15 < 0 )
      goto LABEL_85;
    v26 = *(_QWORD *)(*v3 + 8 * v10);
    if ( *(_BYTE *)(v26 + 422) )
    {
      v27 = LockUnlockSurface(*(struct IMediaSample **)(v26 + 360), 0);
      *(_BYTE *)(*(_QWORD *)(*v3 + 8 * v10) + 421LL) = v27;
      if ( v27 )
        v9 = 1;
    }
    else
    {
      *(_BYTE *)(v26 + 421) = 0;
    }
    v28 = *(_QWORD **)(*v3 + 8 * v10);
    v29 = v28[45];
    v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 32LL))(v29);
    v8 = (struct _AMMediaType **)(a1 + 152);
    v28[47] = v62;
    v28[48] = v30;
    v28[50] = v29;
    *(_QWORD *)(32LL * (unsigned int)v10 + *(_QWORD *)(a1 + 152)) = *(_QWORD *)(*v3 + 8 * v10) + 368LL;
LABEL_45:
    v2 = *(unsigned int *)(a1 + 196);
    v10 = (unsigned int)(v10 + 1);
    v11 = v8;
  }
  while ( (unsigned int)v10 < (unsigned int)v2 );
  if ( !v9 )
    goto LABEL_52;
  v31 = (_QWORD *)(a1 + 160);
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 160) + 184LL))(*(_QWORD *)(a1 + 160), 1);
  v2 = *(unsigned int *)(a1 + 196);
  v32 = 0;
  if ( !(_DWORD)v2 )
  {
LABEL_51:
    v8 = (struct _AMMediaType **)(a1 + 152);
    goto LABEL_53;
  }
  while ( 1 )
  {
    v33 = *(_QWORD *)(*v3 + 8 * v32);
    if ( *(_BYTE *)(v33 + 421) )
    {
      *(_BYTE *)(v33 + 421) = 0;
      if ( !LockUnlockSurface(*(struct IMediaSample **)(*(_QWORD *)(*v3 + 8 * v32) + 360LL), 1) )
        break;
    }
    v2 = *(unsigned int *)(a1 + 196);
    v32 = (unsigned int)(v32 + 1);
    if ( (unsigned int)v32 >= (unsigned int)v2 )
      goto LABEL_51;
  }
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 160) + 184LL))(*(_QWORD *)(a1 + 160), 0);
  v18 = -2147467259;
LABEL_87:
  CMediaWrapperFilter::FreeOutputSamples((CMediaWrapperFilter *)a1);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180018750  push    rbp
0x180018752  push    rbx
0x180018753  push    rsi
0x180018754  push    rdi
0x180018755  push    r12
0x180018757  push    r13
0x180018759  push    r14
0x18001875b  push    r15
0x18001875d  mov     rbp, rsp
0x180018760  sub     rsp, 68h
0x180018764  mov     rax, cs:__security_cookie
0x18001876b  xor     rax, rsp
0x18001876e  mov     [rbp+var_18], rax
0x180018772  mov     r8d, [rcx+0C4h]
0x180018779  lea     r15, [rcx+90h]
0x180018780  xor     r9d, r9d
0x180018783  mov     [rbp+var_34], edx
0x180018786  mov     [rbp+var_20], 0
0x18001878d  mov     r10d, edx
0x180018790  mov     rsi, rcx
0x180018793  lea     r14d, [r9+1]
0x180018797  test    r8d, r8d
0x18001879a  jz      short loc_1800187E8
0x18001879c  mov     r11d, 1A0h
0x1800187a2  mov     rax, [r15]
0x1800187a5  mov     rcx, [rax+r9*8]
0x1800187a9  mov     qword ptr [rcx+168h], 0
0x1800187b4  mov     rax, [r15]
0x1800187b7  mov     rcx, [rax+r9*8]
0x1800187bb  cmp     qword ptr [rcx+30h], 0
0x1800187c0  jz      short loc_1800187D1
0x1800187c2  test    r9d, r9d
0x1800187c5  jnz     short loc_1800187CC
0x1800187c7  cmp     r10d, r14d
0x1800187ca  jz      short loc_1800187D1
0x1800187cc  mov     al, r14b
0x1800187cf  jmp     short loc_1800187D3
0x1800187d1  xor     al, al
0x1800187d3  mov     rdx, r11
0x1800187d6  add     r9d, r14d
0x1800187d9  mov     [rcx+rdx], al
0x1800187dc  mov     r8d, [rsi+0C4h]
0x1800187e3  cmp     r9d, r8d
0x1800187e6  jb      short loc_1800187A2
0x1800187e8  lea     rdx, [rsi+98h]
0x1800187ef  xor     r12b, r12b
0x1800187f2  xor     r13d, r13d
0x1800187f5  mov     rcx, rdx
0x1800187f8  test    r8d, r8d
0x1800187fb  jz      loc_180018B02
0x180018801  mov     rax, [r15]
0x180018804  mov     r14d, r13d
0x180018807  mov     rbx, [rax+r13*8]
0x18001880b  cmp     byte ptr [rbx+1A0h], 0
0x180018812  jz      loc_180018A5B
0x180018818  mov     bl, [rbx+1A2h]
0x18001881e  test    bl, bl
0x180018820  jz      short loc_180018852
0x180018822  mov     rcx, [rsi+0B8h]
0x180018829  lea     r8, [rbp+pv]
0x18001882d  mov     dword ptr [rbp+pv], 0
0x180018834  mov     edx, r13d
0x180018837  mov     rax, [rcx]
0x18001883a  mov     rax, [rax+30h]
0x18001883e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018843  test    eax, eax
0x180018845  js      short loc_180018852
0x180018847  mov     al, byte ptr [rbp+pv]
0x18001884a  and     al, 1
0x18001884c  neg     al
0x18001884e  sbb     al, al
0x180018850  and     bl, al
0x180018852  mov     rax, [r15]
0x180018855  neg     bl
0x180018857  sbb     ecx, ecx
0x180018859  xor     r9d, r9d
0x18001885c  and     ecx, 2
0x18001885f  xor     r8d, r8d
0x180018862  mov     r10, [rax+r13*8]
0x180018866  mov     dword ptr [rsp+68h+var_48], ecx
0x18001886a  mov     rcx, r10
0x18001886d  mov     rax, [r10]
0x180018870  lea     rdx, [r10+168h]
0x180018877  mov     rax, [rax+80h]
0x18001887e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018883  test    eax, eax
0x180018885  js      loc_180018DAC
0x18001888b  mov     [rbp+pv], 0
0x180018893  test    r13d, r13d
0x180018896  jnz     short loc_1800188B0
0x180018898  cmp     [rsi+1BCh], r13d
0x18001889f  jz      short loc_1800188B0
0x1800188a1  xor     edx, edx; unsigned int
0x1800188a3  mov     rcx, rsi; this
0x1800188a6  call    ?ChangeOutputFormatWhenUsingVideoInfoHeader2HackIfNecessary@CMediaWrapperFilter@@IEAAJK@Z; CMediaWrapperFilter::ChangeOutputFormatWhenUsingVideoInfoHeader2HackIfNecessary(ulong)
0x1800188ab  jmp     loc_180018975
0x1800188b0  mov     rax, [r15]
0x1800188b3  mov     rdi, [rax+r13*8]
0x1800188b7  mov     rcx, rdi; this
0x1800188ba  call    ?UsingDXVATransport@CWrapperOutputPin@@IEAA_NXZ; CWrapperOutputPin::UsingDXVATransport(void)
0x1800188bf  test    al, al
0x1800188c1  jnz     loc_18001898D
0x1800188c7  mov     rcx, [rdi+168h]
0x1800188ce  lea     rdx, [rbp+pv]
0x1800188d2  mov     rax, [rcx]
0x1800188d5  mov     rax, [rax+68h]
0x1800188d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188de  mov     ebx, eax
0x1800188e0  test    eax, eax
0x1800188e2  js      loc_180018977
0x1800188e8  mov     rax, [r15]
0x1800188eb  mov     rdx, [rbp+pv]; struct _AMMediaType *
0x1800188ef  mov     rcx, [rax+r13*8]
0x1800188f3  mov     al, [rcx+1A4h]
0x1800188f9  test    al, al
0x1800188fb  jz      short loc_180018904
0x1800188fd  cmp     qword ptr [rcx+30h], 0
0x180018902  jnz     short loc_180018914
0x180018904  test    rdx, rdx
0x180018907  jz      short loc_180018985
0x180018909  test    al, al
0x18001890b  jz      short loc_18001896D
0x18001890d  cmp     qword ptr [rcx+30h], 0
0x180018912  jz      short loc_18001896D
0x180018914  xor     edi, edi
0x180018916  mov     r9, rdx
0x180018919  mov     [rbp+var_38], dil
0x18001891d  xor     r8d, r8d
0x180018920  mov     [rbp+var_37], dil
0x180018924  jmp     short loc_18001893B
0x180018926  cmp     [rbp+var_37], 0
0x18001892a  jnz     short loc_180018960
0x18001892c  cmp     [rbp+var_38], 0
0x180018930  jnz     short loc_180018977
0x180018932  mov     r9, [rbp+pv]; struct _AMMediaType *
0x180018936  inc     edi
0x180018938  mov     r8d, edi; unsigned int
0x18001893b  lea     rax, [rbp+var_37]
0x18001893f  mov     edx, r13d; unsigned int
0x180018942  mov     [rsp+68h+var_40], rax; bool *
0x180018947  mov     rcx, rsi; this
0x18001894a  lea     rax, [rbp+var_38]
0x18001894e  mov     [rsp+68h+var_48], rax; bool *
0x180018953  call    ?ChangeOutputFormat@CMediaWrapperFilter@@IEAAJKKPEBU_AMMediaType@@PEA_N1@Z; CMediaWrapperFilter::ChangeOutputFormat(ulong,ulong,_AMMediaType const *,bool *,bool *)
0x180018958  mov     ebx, eax
0x18001895a  test    eax, eax
0x18001895c  jns     short loc_180018926
0x18001895e  jmp     short loc_180018977
0x180018960  cmp     [rbp+var_38], 0
0x180018964  jnz     short loc_180018977
0x180018966  mov     ebx, 80040219h
0x18001896b  jmp     short loc_180018977
0x18001896d  mov     rcx, rdi; this
0x180018970  call    ?SetMediaType@CWrapperOutputPin@@QEAAJPEBU_AMMediaType@@@Z; CWrapperOutputPin::SetMediaType(_AMMediaType const *)
0x180018975  mov     ebx, eax
0x180018977  mov     rcx, [rbp+pv]; pv
0x18001897b  test    rcx, rcx
0x18001897e  jz      short loc_180018985
0x180018980  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180018985  test    ebx, ebx
0x180018987  js      loc_180018DCD
0x18001898d  mov     rax, [r15]
0x180018990  lea     rdx, [rbp+var_28]
0x180018994  mov     [rbp+var_28], 0
0x18001899c  mov     rcx, [rax+r13*8]
0x1800189a0  mov     rcx, [rcx+168h]
0x1800189a7  mov     rax, [rcx]
0x1800189aa  mov     rax, [rax+18h]
0x1800189ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189b3  test    eax, eax
0x1800189b5  js      loc_180018DAC
0x1800189bb  mov     rax, [r15]
0x1800189be  mov     rcx, [rax+r13*8]
0x1800189c2  cmp     byte ptr [rcx+1A6h], 0
0x1800189c9  jz      short loc_1800189EF
0x1800189cb  mov     rcx, [rcx+168h]; struct IMediaSample *
0x1800189d2  xor     edx, edx; bool
0x1800189d4  call    ?LockUnlockSurface@@YA_NPEAUIMediaSample@@_N@Z; LockUnlockSurface(IMediaSample *,bool)
0x1800189d9  mov     rcx, [r15]
0x1800189dc  mov     rdx, [rcx+r13*8]
0x1800189e0  mov     [rdx+1A5h], al
0x1800189e6  test    al, al
0x1800189e8  jz      short loc_1800189F6
0x1800189ea  mov     r12b, 1
0x1800189ed  jmp     short loc_1800189F6
0x1800189ef  mov     byte ptr [rcx+1A5h], 0
0x1800189f6  mov     rax, [r15]
0x1800189f9  mov     rdi, [rax+r13*8]
0x1800189fd  mov     rbx, [rdi+168h]
0x180018a04  mov     rcx, rbx
0x180018a07  mov     rax, [rbx]
0x180018a0a  mov     rax, [rax+20h]
0x180018a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a13  mov     rcx, [rbp+var_28]
0x180018a17  lea     rdx, [rsi+98h]
0x180018a1e  mov     [rdi+178h], rcx
0x180018a25  mov     [rdi+180h], eax
0x180018a2b  mov     dword ptr [rdi+184h], 0
0x180018a35  mov     [rdi+190h], rbx
0x180018a3c  mov     rax, [r15]
0x180018a3f  mov     rcx, [rax+r13*8]
0x180018a43  mov     rax, [rsi+98h]
0x180018a4a  add     rcx, 170h
0x180018a51  shl     r14, 5
0x180018a55  mov     [r14+rax], rcx
0x180018a59  jmp     short loc_180018A6A
0x180018a5b  mov     rax, [rcx]
0x180018a5e  shl     r14, 5
0x180018a62  mov     qword ptr [r14+rax], 0
0x180018a6a  mov     r8d, [rsi+0C4h]
0x180018a71  mov     r14d, 1
0x180018a77  add     r13d, r14d
0x180018a7a  mov     rcx, rdx
0x180018a7d  cmp     r13d, r8d
0x180018a80  jb      loc_180018801
0x180018a86  test    r12b, r12b
0x180018a89  jz      short loc_180018B02
0x180018a8b  lea     rbx, [rsi+0A0h]
0x180018a92  mov     edx, r14d
0x180018a95  mov     rcx, [rbx]
0x180018a98  mov     rax, [rcx]
0x180018a9b  mov     rax, [rax+0B8h]
0x180018aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018aa7  mov     r8d, [rsi+0C4h]
0x180018aae  xor     edi, edi
0x180018ab0  test    r8d, r8d
0x180018ab3  jz      short loc_180018AF9
0x180018ab5  mov     rax, [r15]
0x180018ab8  mov     rdx, [rax+rdi*8]
0x180018abc  cmp     byte ptr [rdx+1A5h], 0
0x180018ac3  jz      short loc_180018AEA
0x180018ac5  mov     byte ptr [rdx+1A5h], 0
0x180018acc  mov     dl, r14b; bool
0x180018acf  mov     rax, [r15]
0x180018ad2  mov     rcx, [rax+rdi*8]
0x180018ad6  mov     rcx, [rcx+168h]; struct IMediaSample *
0x180018add  call    ?LockUnlockSurface@@YA_NPEAUIMediaSample@@_N@Z; LockUnlockSurface(IMediaSample *,bool)
0x180018ae2  test    al, al
0x180018ae4  jz      loc_180018DB0
0x180018aea  mov     r8d, [rsi+0C4h]
0x180018af1  add     edi, r14d
0x180018af4  cmp     edi, r8d
0x180018af7  jb      short loc_180018AB5
0x180018af9  lea     rdx, [rsi+98h]
0x180018b00  jmp     short loc_180018B09
0x180018b02  lea     rbx, [rsi+0A0h]
0x180018b09  mov     rcx, [rsi+0D0h]
0x180018b10  test    rcx, rcx
0x180018b13  jz      short loc_180018B53
0x180018b15  mov     rax, [rdx]
0x180018b18  mov     r8d, 8
0x180018b1e  mov     [rbp+pv], rax
0x180018b22  lea     rdx, [rbp+pv]
0x180018b26  mov     rax, [rcx]
0x180018b29  mov     rax, [rax+60h]
0x180018b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b32  movsxd  rdi, eax
0x180018b35  test    eax, eax
0x180018b37  js      loc_180018DDC
0x180018b3d  mov     r9, [rbp+pv]
0x180018b41  lea     rdx, [rbp+var_20]
0x180018b45  mov     r8d, [rsi+0C4h]
0x180018b4c  mov     [rsp+68h+var_48], rdx
0x180018b51  jmp     short loc_180018B5F
0x180018b53  lea     r9, [rbp+var_20]
0x180018b57  mov     [rsp+68h+var_48], r9
0x180018b5c  mov     r9, [rdx]
0x180018b5f  mov     rcx, [rbx]
0x180018b62  mov     edx, r14d
0x180018b65  mov     rax, [rcx]
0x180018b68  mov     rax, [rax+0B0h]
0x180018b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b74  mov     ecx, eax; int
0x180018b76  call    ?TranslateDMOError@@YAJJ@Z; TranslateDMOError(long)
0x180018b7b  mov     edi, eax
0x180018b7d  test    r12b, r12b
0x180018b80  jz      short loc_180018B99
0x180018b82  mov     r8, [rbx]
0x180018b85  xor     edx, edx
0x180018b87  mov     rcx, [r8]
0x180018b8a  mov     rax, [rcx+0B8h]
0x180018b91  mov     rcx, r8
0x180018b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b99  test    edi, edi
0x180018b9b  js      loc_180018E1D
0x180018ba1  xor     r13b, r13b
0x180018ba4  xor     r14d, r14d
0x180018ba7  cmp     [rsi+0C4h], r14d
0x180018bae  jbe     loc_180018E96
0x180018bb4  lea     rdx, [rsi+98h]
0x180018bbb  mov     rax, [rdx]
0x180018bbe  lea     rbx, ds:0[r14*8]
0x180018bc6  mov     edi, r14d
0x180018bc9  shl     rdi, 5
0x180018bcd  mov     r12d, r14d
0x180018bd0  cmp     qword ptr [rdi+rax], 0
0x180018bd5  jz      loc_180018D34
0x180018bdb  test    byte ptr [rdi+rax+8], 1
0x180018be0  jz      short loc_180018C08
0x180018be2  mov     rax, [r15]
  ... truncated ...
```
