# CTVP::SetupAccessors(void)

- ea: `0x1800ef7d0`
- end: `0x1800f02ab`
- name: `?SetupAccessors@CTVP@@AEAAJXZ`
- size: `2779`
- prototype: `__int64 __fastcall(CTVP *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800e3b70`

## callees

- `0x180003030`
- `0x180003d80`
- `0x180008fb0`
- `0x1800e8a20`
- `0x1800ef7d0`
- `0x1801a65e1`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800f0092`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800f00e2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800f0092`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800f00e2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800f00fb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800f00fb`

## string_xrefs

- `0x1800eff80`: `IAccessor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTVP::SetupAccessors(CTVP *this)
{
  unsigned __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rdx
  unsigned __int16 v6; // dx
  unsigned __int16 v7; // ax
  int v8; // eax
  unsigned int v9; // esi
  int inited; // eax
  unsigned __int64 v11; // rbp
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rax
  __int64 v14; // r12
  __int64 v15; // r10
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // r9
  unsigned __int64 *v19; // rdx
  unsigned __int64 *v20; // r13
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  _WORD *v23; // r8
  unsigned __int64 v24; // rdx
  _WORD *v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  __int16 v29; // ax
  __int64 v30; // rdi
  __int64 v31; // r14
  __int64 v32; // rcx
  char v33; // al
  int v34; // eax
  char v35; // al
  int v36; // eax
  char v37; // al
  int v38; // eax
  char v39; // al
  int v40; // eax
  unsigned __int64 v41; // rdx
  int v42; // r8d
  _WORD *v43; // rcx
  __int64 v44; // rax
  __int16 v45; // ax
  int v46; // eax
  int v47; // eax
  unsigned __int64 v48; // r13
  unsigned __int64 v49; // r15
  _WORD *v50; // rcx
  __int64 v51; // rdx
  unsigned __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // r12
  unsigned __int64 v56; // rdx
  __int64 v57; // r14
  _OWORD *v58; // rdi
  __int64 v59; // rsi
  unsigned __int64 v60; // rcx
  size_t v61; // r8
  int *v62; // rax
  unsigned __int64 v63; // rdi
  int v64; // eax
  __int64 v65; // rax
  __int64 v67; // [rsp+40h] [rbp-58h]
  __int64 v68; // [rsp+48h] [rbp-50h]
  unsigned __int64 v69; // [rsp+50h] [rbp-48h] BYREF
  __int64 v70; // [rsp+58h] [rbp-40h] BYREF
  __int64 v71; // [rsp+60h] [rbp-38h] BYREF

  v70 = 0;
  v2 = *((unsigned __int16 *)this + 2120) + 1LL;
  v3 = 2 * v2;
  if ( !is_mul_ok(v2, 2u) )
    v3 = -1;
  v4 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, v3);
  *((_QWORD *)this + 532) = v4;
  if ( !v4 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v5 = 6697993;
      goto LABEL_146;
    }
    goto LABEL_147;
  }
  v6 = 0;
  do
  {
    *(_WORD *)(*((_QWORD *)this + 532) + 2LL * v6++) = -1;
    v7 = *((_WORD *)this + 2120);
  }
  while ( v6 <= v7 );
  if ( *((_DWORD *)this + 1054) == 2 )
  {
    v69 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 526) + 72LL))(
           *((_QWORD *)this + 526),
           &v69);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180260508[0], 6718473, (unsigned int)v8);
      }
      goto LABEL_148;
    }
    *((_QWORD *)this + 534) = *(_QWORD *)(v69 + 8) - 1LL;
    inited = CTVP::InitAccessorsInfo(this);
    v9 = inited;
    if ( inited < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(off_180260508[0], 6725641, (unsigned int)inited);
      }
      goto LABEL_148;
    }
    _mm_lfence();
    v11 = 1;
    v12 = 1;
    LOWORD(v13) = *((_WORD *)this + 2120);
    if ( (_WORD)v13 )
    {
      do
      {
        if ( (*(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 529) + 32LL) + **((_QWORD **)this + 529) * v12 + 36) & 0x200) != 0 )
          *(_WORD *)(*((_QWORD *)this + 532) + 2 * v12) = -2;
        ++v12;
        v13 = *((unsigned __int16 *)this + 2120);
      }
      while ( v12 <= v13 );
    }
    v14 = 1;
    if ( *((_QWORD *)this + 534) )
    {
      while ( 2 )
      {
        v15 = *(_QWORD *)(*(_QWORD *)(v69 + 32) + 8 * v14);
        v16 = 1;
        v17 = 0xFFFF;
        v18 = 0;
        if ( !*(_QWORD *)(v15 + 56) )
        {
LABEL_74:
          if ( (bidGblFlags & 2) != 0 )
            v9 = bidTraceHR(off_180260508[0], 6789129, 2147549183LL);
          else
LABEL_73:
            v9 = -2147418113;
          goto LABEL_148;
        }
        v19 = (unsigned __int64 *)(v15 + 64);
        do
        {
          v20 = v19;
          v21 = *v19;
          v22 = *v19;
          if ( v16 < *v19 )
            v22 = v16;
          v16 = v22;
          if ( v17 == 0xFFFF )
          {
            v17 = *v19;
          }
          else if ( v17 <= v21 )
          {
            v17 = *v19;
          }
          if ( v21 > *((unsigned __int16 *)this + 2120) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_73;
            v9 = bidTraceHR(off_180260508[0], 6758409, 2147549183LL);
            goto LABEL_148;
          }
          v23 = (_WORD *)(*((_QWORD *)this + 532) + 2 * v21);
          if ( *v23 == 0xFFFE )
          {
            _mm_lfence();
            v37 = bidGblFlags;
            if ( (bidGblFlags & 2) != 0 )
            {
              v9 = bidTraceHR(off_180260508[0], 6763529, 2147749409LL);
              v37 = bidGblFlags;
            }
            else
            {
              v9 = -2147217887;
            }
            if ( (v37 & 2) != 0 )
              v38 = bidTraceHR(off_180260508[0], 6765577, v9);
            else
              v38 = v9;
            CErrorData::PostFormattedError((CTVP *)((char *)this + 4136), v38, 0xA102u, *v20, v14);
            goto LABEL_148;
          }
          if ( *v23 != 0xFFFF )
          {
            _mm_lfence();
            v35 = bidGblFlags;
            if ( (bidGblFlags & 2) != 0 )
            {
              v9 = bidTraceHR(off_180260508[0], 6773769, 2147749409LL);
              v35 = bidGblFlags;
            }
            else
            {
              v9 = -2147217887;
            }
            if ( (v35 & 2) != 0 )
              v36 = bidTraceHR(off_180260508[0], 6775817, v9);
            else
              v36 = v9;
            CErrorData::PostFormattedError((CTVP *)((char *)this + 4136), v36, 0xA103u, *v20);
            goto LABEL_148;
          }
          *v23 = v14 - 1;
          ++v18;
          v19 += 11;
        }
        while ( v18 < *(_QWORD *)(v15 + 56) );
        if ( v17 == 0xFFFF || v17 > *((unsigned __int16 *)this + 2120) )
          goto LABEL_74;
        v24 = v22;
        if ( v22 <= v17 )
        {
          v25 = (_WORD *)(*((_QWORD *)this + 532) + 2 * v22);
          while ( *v25 != 0xFFFF )
          {
            ++v24;
            ++v25;
            if ( v24 > v17 )
              goto LABEL_38;
          }
          _mm_lfence();
          v33 = bidGblFlags;
          if ( (bidGblFlags & 2) != 0 )
          {
            v9 = bidTraceHR(off_180260508[0], 6798345, 2147749409LL);
            v33 = bidGblFlags;
          }
          else
          {
            v9 = -2147217887;
          }
          if ( (v33 & 2) != 0 )
            v34 = bidTraceHR(off_180260508[0], 6800393, v9);
          else
            v34 = v9;
          CErrorData::PostFormattedError((CTVP *)((char *)this + 4136), v34, 0xA104u, *v20, v16, v17);
          goto LABEL_148;
        }
LABEL_38:
        if ( (unsigned __int64)++v14 <= *((_QWORD *)this + 534) )
          continue;
        break;
      }
      LOWORD(v13) = *((_WORD *)this + 2120);
    }
    if ( !(_WORD)v13 )
      goto LABEL_148;
    while ( 1 )
    {
      v26 = *((_QWORD *)this + 532);
      v27 = *(unsigned __int16 *)(v26 + 2 * v11);
      v28 = (unsigned __int16)v13;
      if ( v11 <= (unsigned __int16)v13 )
      {
        if ( v27 == 0xFFFF )
        {
          _mm_lfence();
          v39 = bidGblFlags;
          if ( (bidGblFlags & 2) != 0 )
          {
            v9 = bidTraceHR(off_180260508[0], 6821897, 2147749409LL);
            v39 = bidGblFlags;
          }
          else
          {
            v9 = -2147217887;
          }
          if ( (v39 & 2) != 0 )
            v40 = bidTraceHR(off_180260508[0], 6823945, v9);
          else
            v40 = v9;
          CErrorData::PostFormattedError((CTVP *)((char *)this + 4136), v40, 0xA105u, v11);
          goto LABEL_148;
        }
        do
        {
          v29 = *(_WORD *)(v26 + 2 * v11);
          if ( v29 == (_WORD)v27 || v29 == -2 )
            ++v11;
        }
        while ( v11 <= v28 );
      }
      v30 = *(_QWORD *)(*(_QWORD *)(v69 + 32) + 8 * v27 + 8);
      v31 = 40 * v27;
      *(_QWORD *)(v31 + *((_QWORD *)this + 533)) = v27 + 1;
      *(_QWORD *)(v31 + *((_QWORD *)this + 533) + 16) = *(_QWORD *)(v30 + 40);
      *(_QWORD *)(v31 + *((_QWORD *)this + 533) + 8) = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, _QWORD))(*(_QWORD *)g_pMO + 112LL))(
                                                         g_pMO,
                                                         *(_QWORD *)(v30 + 40));
      v32 = *((_QWORD *)this + 533);
      if ( !*(_QWORD *)(v32 + v31 + 8) )
        break;
      *(_QWORD *)(v32 + v31 + 24) = *(_QWORD *)(v30 + 56);
      *(_QWORD *)(v31 + *((_QWORD *)this + 533) + 32) = v30 + 64;
      ++v11;
      v13 = *((unsigned __int16 *)this + 2120);
      if ( v11 > v13 )
        goto LABEL_148;
    }
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_147;
    v5 = 6845449;
LABEL_146:
    v9 = bidTraceHR(off_180260508[0], v5, 2147942414LL);
    goto LABEL_148;
  }
  v41 = 1;
  if ( !*((_DWORD *)this + 1056) )
  {
    if ( v7 )
    {
      do
      {
        if ( (*(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 529) + 32LL) + **((_QWORD **)this + 529) * v41 + 36) & 0x200) != 0 )
          v45 = -2;
        else
          v45 = 0;
        *(_WORD *)(*((_QWORD *)this + 532) + 2 * v41++) = v45;
      }
      while ( v41 <= *((unsigned __int16 *)this + 2120) );
    }
    v44 = 1;
    goto LABEL_105;
  }
  v42 = 0;
  if ( v7 )
  {
    do
    {
      if ( (*(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 529) + 32LL) + **((_QWORD **)this + 529) * v41 + 36) & 0x200) != 0 )
      {
        *(_WORD *)(*((_QWORD *)this + 532) + 2 * v41) = -2;
      }
      else if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 531) + 32LL) + **((_QWORD **)this + 531) * v41 + 84) == 13 )
      {
        *(_WORD *)(*((_QWORD *)this + 532) + 2 * v41) = *((_WORD *)this + 2136);
        ++*((_QWORD *)this + 534);
        v42 = 1;
      }
      else
      {
        v43 = (_WORD *)(*((_QWORD *)this + 532) + 2 * v41);
        if ( *((_DWORD *)this + 1055) )
        {
          *v43 = 0;
        }
        else
        {
          *v43 = *((_WORD *)this + 2136);
          v42 = 0;
        }
      }
      ++v41;
    }
    while ( v41 <= *((unsigned __int16 *)this + 2120) );
    v44 = *((_QWORD *)this + 534);
    if ( v42 )
      goto LABEL_105;
  }
  else
  {
    v44 = *((_QWORD *)this + 534);
  }
  ++v44;
LABEL_105:
  *((_QWORD *)this + 534) = v44;
  v46 = CTVP::InitAccessorsInfo(this);
  v9 = v46;
  if ( v46 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_180260508[0], 6925321, (unsigned int)v46);
    }
    goto LABEL_148;
  }
  _mm_lfence();
  v71 = 0;
  v47 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this)(*(_QWORD *)this, &IID_IAccessor, &v70);
  v9 = v47;
  if ( v47 < 0 )
  {
    _mm_lfence();
    if ( (bidGblFlags & 2) != 0 )
      v47 = bidTraceHR(off_180260508[0], 6933513, (unsigned int)v47);
    CErrorData::PostFormattedError((CTVP *)((char *)this + 4136), v47, 0xA0F2u, L"IAccessor");
    goto LABEL_148;
  }
  v48 = 0;
  if ( !*((_QWORD *)this + 534) )
    goto LABEL_148;
  v67 = 0;
  while ( 1 )
  {
    v49 = 0;
    if ( *((_WORD *)this + 2120) )
    {
      v50 = (_WORD *)(*((_QWORD *)this + 532) + 2LL);
      v51 = *((unsigned __int16 *)this + 2120);
      do
      {
        v52 = v49 + 1;
        if ( *v50 != (_WORD)v48 )
          v52 = v49;
        v49 = v52;
        ++v50;
        --v51;
      }
      while ( v51 );
    }
    v53 = 88 * v49;
    if ( !is_mul_ok(v49, 0x58u) )
      v53 = -1;
    v54 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, v53);
    v68 = v54;
    if ( !v54 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_147;
      v5 = 6956041;
      goto LABEL_146;
    }
    v55 = 0;
    v56 = 0;
    v57 = 1;
    if ( *((_WORD *)this + 2120) )
    {
      v58 = (_OWORD *)v54;
      while ( *(_WORD *)(*((_QWORD *)this + 532) + 2 * v57) != (_WORD)v48 )
      {
LABEL_134:
        if ( ++v57 > (unsigned __int64)*((unsigned __int16 *)this + 2120) )
          goto LABEL_135;
      }
      v59 = *(_QWORD *)(*((_QWORD *)this + 531) + 32LL) + **((_QWORD **)this + 531) * v57;
      v60 = (v56 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      *(_QWORD *)(v59 + 16) = v60;
      *(_QWORD *)(v59 + 24) = v60 + 8;
      *(_QWORD *)(v59 + 8) = v60 + 16;
      v56 = v60 + *(_QWORD *)(v59 + 72) + 16LL;
      v69 = v56;
      v61 = 88 * (v49 - v55);
      if ( v58 )
      {
        if ( v61 >= 0x58 )
        {
          *v58 = *(_OWORD *)v59;
          v58[1] = *(_OWORD *)(v59 + 16);
          v58[2] = *(_OWORD *)(v59 + 32);
          v58[3] = *(_OWORD *)(v59 + 48);
          v58[4] = *(_OWORD *)(v59 + 64);
          *((_QWORD *)v58 + 10) = *(_QWORD *)(v59 + 80);
LABEL_133:
          ++v55;
          v58 = (_OWORD *)((char *)v58 + 88);
          goto LABEL_134;
        }
        memset_0(v58, 0, v61);
        v62 = _errno();
        if ( v59 )
          *v62 = 34;
        else
          *v62 = 22;
      }
      else
      {
        *_errno() = 22;
      }
      _invalid_parameter_noinfo();
      v56 = v69;
      goto LABEL_133;
    }
LABEL_135:
    v63 = (v56 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    v64 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int64, __int64, unsigned __int64, __int64 *, _QWORD))(*(_QWORD *)v70 + 32LL))(
            v70,
            2,
            v49,
            v68,
            v63,
            &v71,
            0);
    v9 = v64;
    _mm_lfence();
    if ( v64 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        v64 = bidTraceHR(off_180260508[0], 7015433, (unsigned int)v64);
      CErrorData::PostFormattedError((CTVP *)((char *)this + 4136), v64, 0xA106u);
      goto LABEL_148;
    }
    *(_QWORD *)(v67 + *((_QWORD *)this + 533)) = v71;
    *(_QWORD *)(*((_QWORD *)this + 533) + v67 + 16) = v63;
    *(_QWORD *)(*((_QWORD *)this + 533) + v67 + 8) = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64))(*(_QWORD *)g_pMO + 112LL))(
                                                       g_pMO,
                                                       v63);
    v65 = *((_QWORD *)this + 533);
    if ( !*(_QWORD *)(v65 + v67 + 8) )
      break;
    *(_QWORD *)(v65 + v67 + 24) = v49;
    *(_QWORD *)(*((_QWORD *)this + 533) + v67 + 32) = v68;
    ++v48;
    v67 += 40;
    if ( v48 >= *((_QWORD *)this + 534) )
      goto LABEL_148;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v5 = 7026697;
    goto LABEL_146;
  }
LABEL_147:
  v9 = -2147024882;
LABEL_148:
  if ( v70 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
  return v9;
}

```

## disassembly

```asm
0x1800ef7d0  mov     [rsp+arg_8], rbx
0x1800ef7d5  mov     [rsp+arg_10], rbp
0x1800ef7da  mov     [rsp+arg_18], rsi
0x1800ef7df  push    rdi
0x1800ef7e0  push    r12
0x1800ef7e2  push    r13
0x1800ef7e4  push    r14
0x1800ef7e6  push    r15
0x1800ef7e8  sub     rsp, 70h
0x1800ef7ec  mov     rax, cs:__security_cookie
0x1800ef7f3  xor     rax, rsp
0x1800ef7f6  mov     [rsp+98h+var_30], rax
0x1800ef7fb  mov     rbx, rcx
0x1800ef7fe  xor     edi, edi
0x1800ef800  mov     [rsp+98h+var_40], rdi
0x1800ef805  movzx   ecx, word ptr [rcx+1090h]
0x1800ef80c  inc     rcx
0x1800ef80f  mov     eax, 2
0x1800ef814  mul     rcx
0x1800ef817  mov     rdx, rax
0x1800ef81a  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800ef821  cmovb   rdx, r14
0x1800ef825  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1800ef82c  mov     rax, [rcx]
0x1800ef82f  mov     rax, [rax+70h]
0x1800ef833  call    cs:__guard_dispatch_icall_fptr
0x1800ef839  nop
0x1800ef83a  mov     [rbx+10A0h], rax
0x1800ef841  test    rax, rax
0x1800ef844  jnz     short loc_1800EF85D
0x1800ef846  test    byte ptr cs:_bidGblFlags, 2
0x1800ef84d  jz      loc_1800F0262
0x1800ef853  mov     edx, 663409h
0x1800ef858  jmp     loc_1800F024C
0x1800ef85d  movzx   edx, di
0x1800ef860  movzx   ecx, dx
0x1800ef863  mov     rax, [rbx+10A0h]
0x1800ef86a  mov     word ptr [rax+rcx*2], 0FFFFh
0x1800ef870  inc     dx
0x1800ef873  movzx   eax, word ptr [rbx+1090h]
0x1800ef87a  cmp     dx, ax
0x1800ef87d  jbe     short loc_1800EF860
0x1800ef87f  cmp     dword ptr [rbx+1078h], 2
0x1800ef886  jnz     loc_1800EFDBA
0x1800ef88c  mov     [rsp+98h+var_48], rdi
0x1800ef891  mov     rcx, [rbx+1070h]
0x1800ef898  mov     rax, [rcx]
0x1800ef89b  lea     rdx, [rsp+98h+var_48]
0x1800ef8a0  mov     rax, [rax+48h]
0x1800ef8a4  call    cs:__guard_dispatch_icall_fptr
0x1800ef8aa  mov     esi, eax
0x1800ef8ac  test    eax, eax
0x1800ef8ae  jns     short loc_1800EF8D9
0x1800ef8b0  test    byte ptr cs:_bidGblFlags, 2
0x1800ef8b7  jz      loc_1800F0267
0x1800ef8bd  lfence
0x1800ef8c0  mov     r8d, eax
0x1800ef8c3  mov     edx, 668409h
0x1800ef8c8  mov     rcx, cs:off_180260508; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800ef8cf  call    _bidTraceHR
0x1800ef8d4  jmp     loc_1800F0267
0x1800ef8d9  mov     rax, [rsp+98h+var_48]
0x1800ef8de  mov     rcx, [rax+8]
0x1800ef8e2  dec     rcx
0x1800ef8e5  mov     [rbx+10B0h], rcx
0x1800ef8ec  mov     rcx, rbx; this
0x1800ef8ef  call    ?InitAccessorsInfo@CTVP@@AEAAJXZ; CTVP::InitAccessorsInfo(void)
0x1800ef8f4  mov     esi, eax
0x1800ef8f6  test    eax, eax
0x1800ef8f8  jns     short loc_1800EF923
0x1800ef8fa  test    byte ptr cs:_bidGblFlags, 2
0x1800ef901  jz      loc_1800F0267
0x1800ef907  lfence
0x1800ef90a  mov     r8d, eax
0x1800ef90d  mov     edx, 66A009h
0x1800ef912  mov     rcx, cs:off_180260508; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800ef919  call    _bidTraceHR
0x1800ef91e  jmp     loc_1800F0267
0x1800ef923  lfence
0x1800ef926  mov     ebp, 1
0x1800ef92b  mov     edx, ebp
0x1800ef92d  movzx   eax, word ptr [rbx+1090h]
0x1800ef934  mov     r15d, 0FFFEh
0x1800ef93a  cmp     bp, ax
0x1800ef93d  ja      short loc_1800EF984
0x1800ef93f  mov     r9d, 200h
0x1800ef945  nop     word ptr [rax+rax+00000000h]
0x1800ef950  mov     rax, [rbx+1088h]
0x1800ef957  mov     rcx, rdx
0x1800ef95a  imul    rcx, [rax]
0x1800ef95e  add     rcx, [rax+20h]
0x1800ef962  test    [rcx+24h], r9w
0x1800ef967  jz      short loc_1800EF975
0x1800ef969  mov     rax, [rbx+10A0h]
0x1800ef970  mov     [rax+rdx*2], r15w
0x1800ef975  inc     rdx
0x1800ef978  movzx   eax, word ptr [rbx+1090h]
0x1800ef97f  cmp     rdx, rax
0x1800ef982  jbe     short loc_1800EF950
0x1800ef984  mov     r12, rbp
0x1800ef987  mov     r11d, 0FFFFh
0x1800ef98d  cmp     [rbx+10B0h], rbp
0x1800ef994  jb      loc_1800EFA9A
0x1800ef99a  nop     word ptr [rax+rax+00h]
0x1800ef9a0  mov     rax, [rsp+98h+var_48]
0x1800ef9a5  mov     rcx, [rax+20h]
0x1800ef9a9  mov     r10, [rcx+r12*8]
0x1800ef9ad  mov     r14, rbp
0x1800ef9b0  mov     rdi, r11
0x1800ef9b3  xor     eax, eax
0x1800ef9b5  mov     r9d, eax
0x1800ef9b8  cmp     [r10+38h], rax
0x1800ef9bc  jbe     loc_1800EFD11
0x1800ef9c2  lea     rdx, [r10+40h]
0x1800ef9c6  nop     word ptr [rax+rax+00000000h]
0x1800ef9d0  mov     r13, rdx
0x1800ef9d3  mov     rcx, [rdx]
0x1800ef9d6  mov     rax, rcx
0x1800ef9d9  cmp     r14, rcx
0x1800ef9dc  cmovb   rax, r14
0x1800ef9e0  mov     r14, rax
0x1800ef9e3  cmp     rdi, r11
0x1800ef9e6  jnz     short loc_1800EF9ED
0x1800ef9e8  mov     rdi, rcx
0x1800ef9eb  jmp     short loc_1800EF9F4
0x1800ef9ed  cmp     rdi, rcx
0x1800ef9f0  cmovbe  rdi, rcx
0x1800ef9f4  movzx   eax, word ptr [rbx+1090h]
0x1800ef9fb  cmp     rcx, rax
0x1800ef9fe  ja      loc_1800EFCE0
0x1800efa04  mov     rax, [rbx+10A0h]
0x1800efa0b  lea     r8, [rax+rcx*2]
0x1800efa0f  movzx   eax, word ptr [r8]
0x1800efa13  cmp     ax, r15w
0x1800efa17  jz      loc_1800EFC6F
0x1800efa1d  cmp     ax, r11w
0x1800efa21  jnz     loc_1800EFC03
0x1800efa27  lea     eax, [r12-1]
0x1800efa2c  mov     [r8], ax
0x1800efa30  inc     r9
0x1800efa33  add     rdx, 58h ; 'X'
0x1800efa37  cmp     r9, [r10+38h]
0x1800efa3b  jb      short loc_1800EF9D0
0x1800efa3d  cmp     rdi, r11
0x1800efa40  jz      loc_1800EFD11
0x1800efa46  movzx   r8d, word ptr [rbx+1090h]
0x1800efa4e  cmp     rdi, r8
0x1800efa51  ja      loc_1800EFD11
0x1800efa57  mov     rdx, r14
0x1800efa5a  cmp     r14, rdi
0x1800efa5d  ja      short loc_1800EFA86
0x1800efa5f  mov     rax, [rbx+10A0h]
0x1800efa66  lea     rcx, [rax+r14*2]
0x1800efa6a  nop     word ptr [rax+rax+00h]
0x1800efa70  cmp     [rcx], r11w
0x1800efa74  jz      loc_1800EFB8D
0x1800efa7a  inc     rdx
0x1800efa7d  add     rcx, 2
0x1800efa81  cmp     rdx, rdi
0x1800efa84  jbe     short loc_1800EFA70
0x1800efa86  inc     r12
0x1800efa89  cmp     r12, [rbx+10B0h]
0x1800efa90  jbe     loc_1800EF9A0
0x1800efa96  movzx   eax, r8w
0x1800efa9a  cmp     bp, ax
0x1800efa9d  ja      loc_1800F0267
0x1800efaa3  nop     dword ptr [rax+00h]
0x1800efaa7  nop     word ptr [rax+rax+00000000h]
0x1800efab0  mov     r8, [rbx+10A0h]
0x1800efab7  movzx   edx, word ptr [r8+rbp*2]
0x1800efabc  movzx   ecx, ax
0x1800efabf  cmp     rbp, rcx
0x1800efac2  ja      short loc_1800EFAE5
0x1800efac4  cmp     rdx, r11
0x1800efac7  jz      loc_1800EFD38
0x1800efacd  movzx   eax, word ptr [r8+rbp*2]
0x1800efad2  cmp     ax, dx
0x1800efad5  jz      short loc_1800EFADD
0x1800efad7  cmp     ax, r15w
0x1800efadb  jnz     short loc_1800EFAE0
0x1800efadd  inc     rbp
0x1800efae0  cmp     rbp, rcx
0x1800efae3  jbe     short loc_1800EFACD
0x1800efae5  mov     rax, [rsp+98h+var_48]
0x1800efaea  mov     rcx, [rax+20h]
0x1800efaee  mov     rdi, [rcx+rdx*8+8]
0x1800efaf3  lea     rax, [rdx+rdx*4]
0x1800efaf7  lea     r14, ds:0[rax*8]
0x1800efaff  lea     rcx, [rdx+1]
0x1800efb03  mov     rax, [rbx+10A8h]
0x1800efb0a  mov     [r14+rax], rcx
0x1800efb0e  mov     rcx, [rbx+10A8h]
0x1800efb15  mov     rax, [rdi+28h]
0x1800efb19  mov     [r14+rcx+10h], rax
0x1800efb1e  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1800efb25  mov     rax, [rcx]
0x1800efb28  mov     rdx, [rdi+28h]
0x1800efb2c  mov     rax, [rax+70h]
0x1800efb30  call    cs:__guard_dispatch_icall_fptr
0x1800efb36  nop
0x1800efb37  mov     rcx, [rbx+10A8h]
0x1800efb3e  mov     [r14+rcx+8], rax
0x1800efb43  mov     rcx, [rbx+10A8h]
0x1800efb4a  cmp     qword ptr [rcx+r14+8], 0
0x1800efb50  jz      loc_1800EFDA3
0x1800efb56  mov     rax, [rdi+38h]
0x1800efb5a  mov     [rcx+r14+18h], rax
0x1800efb5f  lea     rcx, [rdi+40h]
0x1800efb63  mov     rax, [rbx+10A8h]
0x1800efb6a  mov     [r14+rax+20h], rcx
0x1800efb6f  inc     rbp
0x1800efb72  movzx   eax, word ptr [rbx+1090h]
0x1800efb79  cmp     rbp, rax
0x1800efb7c  ja      loc_1800F0267
0x1800efb82  mov     r11d, 0FFFFh
0x1800efb88  jmp     loc_1800EFAB0
0x1800efb8d  lfence
0x1800efb90  mov     eax, cs:_bidGblFlags
0x1800efb96  test    al, 2
0x1800efb98  jz      short loc_1800EFBBB
0x1800efb9a  mov     edx, 67BC09h
0x1800efb9f  mov     r8d, 80040E21h
0x1800efba5  mov     rcx, cs:off_180260508; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800efbac  call    _bidTraceHR
0x1800efbb1  mov     esi, eax
0x1800efbb3  mov     eax, cs:_bidGblFlags
0x1800efbb9  jmp     short loc_1800EFBC0
0x1800efbbb  mov     esi, 80040E21h
0x1800efbc0  test    al, 2
0x1800efbc2  jz      short loc_1800EFBDA
0x1800efbc4  mov     r8d, esi
0x1800efbc7  mov     edx, 67C409h
0x1800efbcc  mov     rcx, cs:off_180260508; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800efbd3  call    _bidTraceHR
0x1800efbd8  jmp     short loc_1800EFBDC
0x1800efbda  mov     eax, esi
0x1800efbdc  lea     rcx, [rbx+1028h]; this
0x1800efbe3  mov     [rsp+98h+var_70], rdi
0x1800efbe8  mov     [rsp+98h+var_78], r14
0x1800efbed  mov     r9, [r13+0]
0x1800efbf1  mov     r8d, 0A104h; unsigned int
0x1800efbf7  mov     edx, eax; int
0x1800efbf9  call    ?PostFormattedError@CErrorData@@QEAAJJIZZ; CErrorData::PostFormattedError(long,uint,...)
0x1800efbfe  jmp     loc_1800F0267
0x1800efc03  lfence
0x1800efc06  mov     eax, cs:_bidGblFlags
0x1800efc0c  test    al, 2
0x1800efc0e  jz      short loc_1800EFC31
0x1800efc10  mov     edx, 675C09h
0x1800efc15  mov     r8d, 80040E21h
0x1800efc1b  mov     rcx, cs:off_180260508; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800efc22  call    _bidTraceHR
0x1800efc27  mov     esi, eax
0x1800efc29  mov     eax, cs:_bidGblFlags
0x1800efc2f  jmp     short loc_1800EFC36
0x1800efc31  mov     esi, 80040E21h
0x1800efc36  test    al, 2
0x1800efc38  jz      short loc_1800EFC50
0x1800efc3a  mov     r8d, esi
0x1800efc3d  mov     edx, 676409h
0x1800efc42  mov     rcx, cs:off_180260508; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800efc49  call    _bidTraceHR
0x1800efc4e  jmp     short loc_1800EFC52
0x1800efc50  mov     eax, esi
0x1800efc52  lea     rcx, [rbx+1028h]; this
0x1800efc59  mov     r9, [r13+0]
0x1800efc5d  mov     r8d, 0A103h; unsigned int
0x1800efc63  mov     edx, eax; int
0x1800efc65  call    ?PostFormattedError@CErrorData@@QEAAJJIZZ; CErrorData::PostFormattedError(long,uint,...)
0x1800efc6a  jmp     loc_1800F0267
0x1800efc6f  lfence
0x1800efc72  mov     eax, cs:_bidGblFlags
0x1800efc78  test    al, 2
0x1800efc7a  jz      short loc_1800EFC9D
0x1800efc7c  mov     edx, 673409h
0x1800efc81  mov     r8d, 80040E21h
0x1800efc87  mov     rcx, cs:off_180260508; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800efc8e  call    _bidTraceHR
0x1800efc93  mov     esi, eax
0x1800efc95  mov     eax, cs:_bidGblFlags
0x1800efc9b  jmp     short loc_1800EFCA2
0x1800efc9d  mov     esi, 80040E21h
0x1800efca2  test    al, 2
0x1800efca4  jz      short loc_1800EFCBC
0x1800efca6  mov     r8d, esi
0x1800efca9  mov     edx, 673C09h
0x1800efcae  mov     rcx, cs:off_180260508; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800efcb5  call    _bidTraceHR
0x1800efcba  jmp     short loc_1800EFCBE
0x1800efcbc  mov     eax, esi
0x1800efcbe  lea     rcx, [rbx+1028h]; this
0x1800efcc5  mov     [rsp+98h+var_78], r12
0x1800efcca  mov     r9, [r13+0]
0x1800efcce  mov     r8d, 0A102h; unsigned int
0x1800efcd4  mov     edx, eax; int
0x1800efcd6  call    ?PostFormattedError@CErrorData@@QEAAJJIZZ; CErrorData::PostFormattedError(long,uint,...)
0x1800efcdb  jmp     loc_1800F0267
0x1800efce0  test    byte ptr cs:_bidGblFlags, 2
0x1800efce7  jz      short loc_1800EFD07
0x1800efce9  mov     edx, 672009h
  ... truncated ...
```
