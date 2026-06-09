# CCommand::GetMetadataQuery(wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *)

- ea: `0x180089230`
- end: `0x180089d78`
- name: `?GetMetadataQuery@CCommand@@QEAAJPEB_W_KPEAPEA_WPEA_K@Z`
- size: `2888`
- prototype: `__int64 __usercall@<rax>(CCommand *__hidden this@<rcx>, const wchar_t *Src@<rdx>, unsigned __int64@<r8>, wchar_t **@<r9>, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a8ee0`
- `0x1800d6570`

## callees

- `0x180003030`
- `0x180003824`
- `0x180003d80`
- `0x180009de0`
- `0x18000aaa0`
- `0x18007f1b0`
- `0x1800806a0`
- `0x1800844c0`
- `0x1800845d0`
- `0x180085360`
- `0x180089230`
- `0x18008b6a0`
- `0x1800e01f0`
- `0x1800e07d0`
- `0x1800e09b0`
- `0x1801336f4`
- `0x180133bcc`
- `0x180134658`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800892e5`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180089358`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180089377`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800899cf`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800892e5`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180089358`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180089377`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800899cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCommand::GetMetadataQuery(
        CCommand *this,
        wchar_t *Src,
        unsigned __int64 a3,
        wchar_t **a4,
        unsigned __int64 *a5)
{
  wchar_t *v5; // r12
  unsigned __int64 v7; // r14
  unsigned int v8; // ebx
  unsigned __int64 v9; // rax
  const wchar_t *v10; // rdi
  unsigned __int64 v11; // r8
  bool v12; // zf
  unsigned __int64 v13; // rax
  int v14; // esi
  unsigned int LexToken; // eax
  wchar_t v16; // cx
  unsigned __int64 v17; // r15
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // rdx
  int v21; // ebx
  char v22; // al
  wchar_t *v23; // rdi
  wchar_t *v24; // rsi
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rbx
  __int64 v28; // rdx
  wchar_t *v29; // rax
  char v30; // al
  int v31; // esi
  unsigned __int64 v32; // rdx
  unsigned int v33; // eax
  unsigned __int64 v34; // rcx
  wchar_t v35; // ax
  int v36; // ebx
  unsigned __int64 v37; // rsi
  int v38; // eax
  wchar_t *v39; // r9
  __int16 v40; // r8
  wchar_t v41; // ax
  size_t v42; // rdi
  CExtBaseBuffer *v43; // rsi
  CExtBaseBuffer *v44; // rax
  CExtBaseBuffer *v45; // rbx
  __int64 v46; // rdx
  int v47; // eax
  int v48; // ebx
  char v49; // al
  wchar_t **v50; // r13
  wchar_t *v51; // rcx
  wchar_t *v52; // rcx
  char v53; // al
  CExtBaseBuffer *v54; // rdi
  wchar_t *v56; // [rsp+40h] [rbp-71h] BYREF
  wchar_t *v57[2]; // [rsp+48h] [rbp-69h] BYREF
  int v58; // [rsp+58h] [rbp-59h]
  wchar_t *v59; // [rsp+60h] [rbp-51h]
  CExtBaseBuffer *v60; // [rsp+68h] [rbp-49h]
  wchar_t **v61; // [rsp+70h] [rbp-41h]
  unsigned __int64 *v62; // [rsp+78h] [rbp-39h]
  unsigned __int64 v63; // [rsp+80h] [rbp-31h] BYREF
  unsigned __int64 v64; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int64 v65; // [rsp+90h] [rbp-21h] BYREF
  wchar_t *v66; // [rsp+98h] [rbp-19h] BYREF
  unsigned __int64 *v67; // [rsp+A0h] [rbp-11h] BYREF
  unsigned __int64 *v68; // [rsp+A8h] [rbp-9h] BYREF
  unsigned __int64 v69; // [rsp+B0h] [rbp-1h] BYREF

  v61 = a4;
  v5 = Src;
  v69 = a3;
  v62 = a5;
  v64 = 0;
  v63 = 0;
  v65 = 0;
  v66 = 0;
  v60 = 0;
  v59 = 0;
  v7 = 0;
  v56 = 0;
  LODWORD(v57[0]) = 0;
  v8 = 0;
  v58 = 1;
  *a4 = 0;
  *a5 = 0;
  if ( GetLexToken(Src, a3, &v63, &v64) != 1 )
    goto LABEL_94;
  v9 = v64;
  if ( v64 != 6 )
  {
LABEL_95:
    v58 = 0;
    if ( v9 != 1 || v5[v63] != 123 )
    {
LABEL_120:
      v17 = CCommand::CountParamMarkers(this, v5, v69);
      if ( !v17 )
        goto LABEL_39;
      if ( !(unsigned int)CCommand::FParamInfoComplete(this) )
      {
        v69 = IndexWChar(0x3Fu, v5, v69);
        goto LABEL_39;
      }
      v67 = 0;
      v47 = CCommand::ComputeParamOffsets(this, v5, v69, *((_QWORD *)this + 176), &v67);
      v8 = v47;
      _mm_lfence();
      if ( v47 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v47 = bidTraceHR(off_1802603F0[0], 1763337, (unsigned int)v47);
        goto LABEL_152;
      }
      v48 = CStmt::FillInDummyParams(*((CStmt **)this + 150), v5, v69, v17, v67, &v66, &v69, 1);
      if ( v67 )
      {
        (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
        v67 = 0;
      }
      if ( v48 == -1 )
      {
        _mm_lfence();
        v49 = bidGblFlags;
        if ( (bidGblFlags & 2) != 0 )
        {
          v8 = bidTraceHR(off_1802603F0[0], 1781769, 2147942414LL);
          v49 = bidGblFlags;
        }
        else
        {
          v8 = -2147024882;
        }
        if ( (v49 & 2) != 0 )
        {
          v47 = bidTraceHR(off_1802603F0[0], 1782793, v8);
          goto LABEL_152;
        }
        goto LABEL_151;
      }
LABEL_38:
      v5 = v66;
LABEL_39:
      v23 = v56;
      v24 = v56;
      goto LABEL_40;
    }
    v42 = 2 * v69;
    v43 = 0;
    v60 = 0;
    v44 = (CExtBaseBuffer *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                              g_pMO,
                              48);
    v45 = v44;
    if ( v44 )
    {
      *(_QWORD *)v44 = 0;
      *((_QWORD *)v44 + 1) = 0;
      *((_QWORD *)v44 + 2) = 0;
      *((_QWORD *)v44 + 3) = 0;
      *((_QWORD *)v44 + 4) = 0;
      *((_QWORD *)v44 + 5) = 0;
      if ( (unsigned int)CExtByteBuffer::FInit(v44, v42, 0x64u) )
      {
        if ( !v42 || (int)CExtByteBuffer::WriteIntoExtBuffer(v45, v5, v42) >= 0 )
        {
          v43 = v45;
          v60 = v45;
          v8 = 0;
LABEL_106:
          if ( (unsigned int)CCommand::SubstituteECodes(this, v43, 0, 1u) == -1 )
          {
            if ( (bidGblFlags & 2) != 0 )
              v8 = bidTraceHR(off_1802603F0[0], 1733641, 2147500037LL);
            else
              v8 = -2147467259;
            goto LABEL_153;
          }
          v5 = (wchar_t *)*((_QWORD *)v43 + 4);
          v69 = *((_QWORD *)v43 + 1) >> 1;
          if ( GetLexToken(v5, v69, &v63, &v64) != 1 || v64 != 4 || _wcsnicmp(&v5[v63], L"exec", 4u) )
            goto LABEL_153;
          goto LABEL_120;
        }
        _mm_lfence();
        CExtBaseBuffer::~CExtBaseBuffer(v45);
        _mm_lfence();
        operator delete(v45, 0x30u);
        if ( (bidGblFlags & 2) != 0 )
        {
          v46 = 120841;
          goto LABEL_111;
        }
      }
      else
      {
        CExtBaseBuffer::~CExtBaseBuffer(v45);
        operator delete(v45, 0x30u);
        if ( (bidGblFlags & 2) != 0 )
        {
          v46 = 112649;
LABEL_111:
          v8 = bidTraceHR(off_1802603F0[0], v46, 2147942414LL);
          goto LABEL_113;
        }
      }
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      v46 = 108553;
      goto LABEL_111;
    }
    v8 = -2147024882;
LABEL_113:
    if ( (v8 & 0x80000000) != 0 )
    {
      _mm_lfence();
      if ( (bidGblFlags & 2) != 0 )
      {
        v47 = bidTraceHR(off_1802603F0[0], 1728521, v8);
        goto LABEL_152;
      }
      goto LABEL_151;
    }
    goto LABEL_106;
  }
  if ( _wcsnicmp(&v5[v63], L"select", 6u) )
  {
LABEL_94:
    v9 = v64;
    goto LABEL_95;
  }
  v10 = &v5[v63 + v64];
  v11 = v69;
  v13 = v69 - v63 - v64;
  v12 = v69 - v63 == v64;
  v64 = v13;
  v14 = 0;
  if ( !v12 )
  {
    do
    {
      LexToken = GetLexToken(v10, v13, &v63, &v65);
      if ( LexToken == 1 )
      {
        if ( v65 == 4 && !v14 )
        {
          if ( !_wcsnicmp(&v10[v63], L"from", 4u) )
            break;
          if ( !_wcsnicmp(&v10[v63], L"into", 4u) )
            goto LABEL_155;
        }
      }
      else if ( LexToken == 3 )
      {
        v16 = v10[v63];
        if ( v16 == 40 )
        {
          ++v14;
        }
        else if ( v16 == 41 )
        {
          --v14;
        }
      }
      v10 += v63 + v65;
      if ( v64 < v63 + v65 )
      {
        v64 = -1;
        if ( (bidGblFlags & 2) != 0 )
          v8 = bidTraceHR(off_1802603F0[0], 1833993, 2147500037LL);
        else
          v8 = -2147467259;
        goto LABEL_155;
      }
      v13 = v64 - (v63 + v65);
      v64 = v13;
    }
    while ( v13 );
    v11 = v69;
  }
  v17 = CCommand::CountParamMarkers(this, v5, v11);
  if ( v17 )
  {
    if ( !(unsigned int)CCommand::FParamInfoComplete(this) )
      goto LABEL_155;
    v68 = 0;
    v18 = CCommand::ComputeParamOffsets(this, v5, v69, v17, &v68);
    v8 = v18;
    _mm_lfence();
    if ( v18 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_25:
        CErrorData::PostStandardError((CCommand *)((char *)this + 1136), 0x9CDDu, v18, 0);
        goto LABEL_155;
      }
      v19 = (unsigned int)v18;
      v20 = 1853449;
LABEL_24:
      v18 = bidTraceHR(off_1802603F0[0], v20, v19);
      goto LABEL_25;
    }
    v21 = CStmt::FillInDummyParams(*((CStmt **)this + 150), v5, v69, v17, v68, &v66, &v69, 0);
    if ( v68 )
    {
      (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
      v68 = 0;
    }
    if ( v21 == -1 )
    {
      _mm_lfence();
      v22 = bidGblFlags;
      if ( (bidGblFlags & 2) != 0 )
      {
        v8 = bidTraceHR(off_1802603F0[0], 1871881, 2147942414LL);
        v22 = bidGblFlags;
      }
      else
      {
        v8 = -2147024882;
      }
      if ( (v22 & 2) == 0 )
      {
        v18 = v8;
        goto LABEL_25;
      }
      v19 = v8;
      v20 = 1872905;
      goto LABEL_24;
    }
    goto LABEL_38;
  }
  v31 = 0;
  v32 = v64;
  if ( v64 )
  {
    while ( 1 )
    {
      v33 = GetLexToken(v10, v32, &v63, &v65);
      if ( v33 != 1 )
        break;
      if ( v8 || v31 || !(unsigned int)FIsEndFromClause(&v10[v63], v65) )
        goto LABEL_65;
      v34 = v63;
      if ( (v10[v63] | 0x20) != 0x75 )
      {
        v32 = v64;
        if ( v64 )
          v69 -= v64;
        goto LABEL_69;
      }
LABEL_66:
      v10 += v65 + v34;
      v32 = v64 - (v65 + v34);
      v64 = v32;
      if ( !v32 )
        goto LABEL_69;
    }
    if ( v33 == 3 )
    {
      v34 = v63;
      v35 = v10[v63];
      switch ( v35 )
      {
        case '(':
          ++v8;
          break;
        case ')':
          --v8;
          break;
        case '{':
          ++v31;
          break;
        case '}':
          --v31;
          break;
      }
      goto LABEL_66;
    }
LABEL_65:
    v34 = v63;
    goto LABEL_66;
  }
  v34 = v63;
LABEL_69:
  v36 = 0;
  if ( !v32 )
  {
    v23 = 0;
    v24 = 0;
    goto LABEL_40;
  }
  while ( 1 )
  {
    v37 = v7;
    if ( v36 || (v38 = FIsEndFromClause(&v10[v34], v32 - v34), v32 = v64, v34 = v63, !v38) )
    {
      if ( v65 == 1 )
      {
        v41 = v10[v34];
        if ( v41 == 40 )
        {
          ++v36;
        }
        else if ( v41 == 41 )
        {
          --v36;
        }
      }
      goto LABEL_89;
    }
    if ( !v64 )
      goto LABEL_89;
    v39 = (wchar_t *)&v10[v63];
    v40 = *v39 | 0x20;
    if ( v40 == 119 )
      goto LABEL_89;
    if ( ((v40 - 102) & 0xFFFD) == 0 )
    {
      LODWORD(v57[0]) = 1;
      if ( v7 )
        v7 -= v64;
      goto LABEL_89;
    }
    if ( v40 == 117 )
      break;
    if ( v7 )
    {
      if ( LODWORD(v57[0]) )
      {
        v24 = (wchar_t *)&v10[v63];
        v23 = (wchar_t *)(v64 - v63);
        goto LABEL_40;
      }
    }
    else
    {
      v7 = v64 - v63;
      if ( v37 )
        v39 = v59;
      v59 = v39;
    }
LABEL_89:
    v10 += v65 + v34;
    v64 = v32 - (v65 + v34);
    GetLexToken(v10, v64, &v63, &v65);
    v32 = v64;
    if ( !v64 )
      goto LABEL_39;
    v34 = v63;
  }
  v23 = v56;
  v24 = v56;
  if ( v7 )
    v7 -= v64;
LABEL_40:
  v25 = v69 + g_cwchFmtOnlyOn + 3 + g_cwchFmtOnlyOff + g_cwchWhere1Eq2;
  if ( v25 < v69
    || (v26 = v25 + v7, v25 + v7 < v25)
    || (v27 = (unsigned __int64)v23 + v26, (unsigned __int64)v23 + v26 < v26) )
  {
    v53 = bidGblFlags;
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = bidTraceHR(off_1802603F0[0], 2002953, 2147942414LL);
      v53 = bidGblFlags;
    }
    else
    {
      v8 = -2147024882;
    }
    if ( (v53 & 2) == 0 )
      goto LABEL_151;
    v47 = bidTraceHR(off_1802603F0[0], 2003977, v8);
    goto LABEL_152;
  }
  v56 = (wchar_t *)((char *)v23 + v26);
  v28 = 2 * v27;
  if ( !is_mul_ok(v27, 2u) )
    v28 = -1;
  v29 = (wchar_t *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, v28);
  v57[0] = v29;
  if ( v29 )
  {
    v50 = v61;
    *v61 = v29;
    StringCchCopyExW(v29, v27, g_wszFmtOnlyOn, v57, (unsigned __int64 *)&v56, 0);
    StringCchCopyNExW(v57[0], (unsigned __int64)v56, v5, v69, v57, (unsigned __int64 *)&v56, 0);
    if ( v58 && !v17 )
      StringCchCopyExW(v57[0], (unsigned __int64)v56, g_wszWhere1Eq2, v57, (unsigned __int64 *)&v56, 0);
    if ( v7 )
    {
      v51 = v57[0];
      *v57[0] = 32;
      v57[0] = v51 + 1;
      v56 = (wchar_t *)((char *)v56 - 1);
      StringCchCopyNExW(v51 + 1, (unsigned __int64)v56, v59, v7, v57, (unsigned __int64 *)&v56, 0);
    }
    if ( v23 )
    {
      v52 = v57[0];
      *v57[0] = 32;
      v57[0] = v52 + 1;
      v56 = (wchar_t *)((char *)v56 - 1);
      StringCchCopyNExW(v52 + 1, (unsigned __int64)v56, v24, (unsigned __int64)v23, v57, (unsigned __int64 *)&v56, 0);
    }
    v8 = StringCchCopyExW(v57[0], (unsigned __int64)v56, g_wszFmtOnlyOff, v57, (unsigned __int64 *)&v56, 0);
    *v62 = v57[0] - *v50;
  }
  else
  {
    v30 = bidGblFlags;
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = bidTraceHR(off_1802603F0[0], 2012169, 2147942414LL);
      v30 = bidGblFlags;
    }
    else
    {
      v8 = -2147024882;
    }
    if ( (v30 & 2) != 0 )
    {
      v47 = bidTraceHR(off_1802603F0[0], 2013193, v8);
      goto LABEL_152;
    }
LABEL_151:
    v47 = v8;
LABEL_152:
    CErrorData::PostStandardError((CCommand *)((char *)this + 1136), 0x9CDDu, v47, 0);
  }
LABEL_153:
  v54 = v60;
  if ( v60 )
  {
    CExtBaseBuffer::~CExtBaseBuffer(v60);
    operator delete(v54, 0x30u);
  }
LABEL_155:
  if ( v66 )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
  return v8;
}

```

## disassembly

```asm
0x180089230  push    rbp
0x180089232  push    rbx
0x180089233  push    rsi
0x180089234  push    rdi
0x180089235  push    r12
0x180089237  push    r13
0x180089239  push    r14
0x18008923b  push    r15
0x18008923d  lea     rbp, [rsp-17h]
0x180089242  sub     rsp, 0C8h
0x180089249  mov     rax, cs:__security_cookie
0x180089250  xor     rax, rsp
0x180089253  mov     [rbp+4Fh+var_48], rax
0x180089257  mov     [rbp+4Fh+var_90], r9
0x18008925b  mov     rax, r8
0x18008925e  mov     r12, rdx
0x180089261  mov     r13, rcx
0x180089264  mov     [rbp+4Fh+var_50], rax
0x180089268  mov     rcx, [rbp+4Fh+arg_20]
0x18008926c  mov     [rbp+4Fh+var_88], rcx
0x180089270  xor     r15d, r15d
0x180089273  mov     [rbp+4Fh+var_78], r15
0x180089277  mov     [rbp+4Fh+var_80], r15
0x18008927b  mov     [rbp+4Fh+var_70], r15
0x18008927f  mov     [rbp+4Fh+var_68], r15
0x180089283  mov     [rbp+4Fh+var_98], r15
0x180089287  mov     [rbp+4Fh+var_A0], r15
0x18008928b  mov     r14d, r15d
0x18008928e  mov     [rbp+4Fh+var_C0], r15
0x180089292  mov     dword ptr [rbp+4Fh+var_B8], r15d
0x180089296  mov     ebx, r15d
0x180089299  mov     [rbp+4Fh+var_A8], 1
0x1800892a0  mov     [r9], r15
0x1800892a3  mov     [rcx], r15
0x1800892a6  lea     r9, [rbp+4Fh+var_78]; unsigned __int64 *
0x1800892aa  lea     r8, [rbp+4Fh+var_80]; unsigned __int64 *
0x1800892ae  mov     rdx, rax; unsigned __int64
0x1800892b1  mov     rcx, r12; wchar_t *
0x1800892b4  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x1800892b9  cmp     eax, 1
0x1800892bc  jnz     loc_1800897E9
0x1800892c2  mov     rax, [rbp+4Fh+var_78]
0x1800892c6  cmp     rax, 6
0x1800892ca  jnz     loc_1800897ED
0x1800892d0  mov     rax, [rbp+4Fh+var_80]
0x1800892d4  lea     rcx, [r12+rax*2]; String1
0x1800892d8  mov     r8d, 6; MaxCount
0x1800892de  lea     rdx, aSelect_0; "select"
0x1800892e5  call    cs:__imp__wcsnicmp
0x1800892eb  test    eax, eax
0x1800892ed  jnz     loc_1800897E9
0x1800892f3  mov     rcx, [rbp+4Fh+var_80]
0x1800892f7  mov     rdx, [rbp+4Fh+var_78]
0x1800892fb  lea     rax, [rcx+rdx]
0x1800892ff  lea     rdi, [r12+rax*2]
0x180089303  mov     r8, [rbp+4Fh+var_50]
0x180089307  mov     rax, r8
0x18008930a  sub     rax, rcx
0x18008930d  sub     rax, rdx
0x180089310  mov     [rbp+4Fh+var_78], rax
0x180089314  mov     esi, r15d
0x180089317  jz      loc_1800893D0
0x18008931d  nop     dword ptr [rax]
0x180089320  lea     r9, [rbp+4Fh+var_70]; unsigned __int64 *
0x180089324  lea     r8, [rbp+4Fh+var_80]; unsigned __int64 *
0x180089328  mov     rdx, rax; unsigned __int64
0x18008932b  mov     rcx, rdi; wchar_t *
0x18008932e  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x180089333  cmp     eax, 1
0x180089336  jnz     short loc_180089387
0x180089338  cmp     [rbp+4Fh+var_70], 4
0x18008933d  jnz     short loc_1800893A6
0x18008933f  test    esi, esi
0x180089341  jnz     short loc_1800893A6
0x180089343  mov     rax, [rbp+4Fh+var_80]
0x180089347  lea     rcx, [rdi+rax*2]; String1
0x18008934b  mov     r8d, 4; MaxCount
0x180089351  lea     rdx, aFrom_0; "from"
0x180089358  call    cs:__imp__wcsnicmp
0x18008935e  test    eax, eax
0x180089360  jz      short loc_1800893CC
0x180089362  mov     rax, [rbp+4Fh+var_80]
0x180089366  lea     rcx, [rdi+rax*2]; String1
0x18008936a  mov     r8d, 4; MaxCount
0x180089370  lea     rdx, aInto; "into"
0x180089377  call    cs:__imp__wcsnicmp
0x18008937d  test    eax, eax
0x18008937f  jz      loc_180089D35
0x180089385  jmp     short loc_1800893A6
0x180089387  cmp     eax, 3
0x18008938a  jnz     short loc_1800893A6
0x18008938c  mov     rax, [rbp+4Fh+var_80]
0x180089390  movzx   ecx, word ptr [rdi+rax*2]
0x180089394  cmp     cx, 28h ; '('
0x180089398  jnz     short loc_18008939E
0x18008939a  inc     esi
0x18008939c  jmp     short loc_1800893A6
0x18008939e  cmp     cx, 29h ; ')'
0x1800893a2  jnz     short loc_1800893A6
0x1800893a4  dec     esi
0x1800893a6  mov     rdx, [rbp+4Fh+var_70]
0x1800893aa  add     rdx, [rbp+4Fh+var_80]
0x1800893ae  lea     rdi, [rdi+rdx*2]
0x1800893b2  mov     rax, [rbp+4Fh+var_78]
0x1800893b6  cmp     rax, rdx
0x1800893b9  jb      loc_18008945A
0x1800893bf  sub     rax, rdx
0x1800893c2  mov     [rbp+4Fh+var_78], rax
0x1800893c6  jnz     loc_180089320
0x1800893cc  mov     r8, [rbp+4Fh+var_50]; unsigned __int64
0x1800893d0  mov     rdx, r12; wchar_t *
0x1800893d3  mov     rcx, r13; this
0x1800893d6  call    ?CountParamMarkers@CCommand@@QEAA_KPEB_W_K@Z; CCommand::CountParamMarkers(wchar_t const *,unsigned __int64)
0x1800893db  mov     r15, rax
0x1800893de  test    rax, rax
0x1800893e1  jz      loc_1800895FF
0x1800893e7  mov     rcx, r13; this
0x1800893ea  call    ?FParamInfoComplete@CCommand@@QEAAHXZ; CCommand::FParamInfoComplete(void)
0x1800893ef  test    eax, eax
0x1800893f1  jz      loc_180089D35
0x1800893f7  xor     edi, edi
0x1800893f9  mov     [rbp+4Fh+var_58], rdi
0x1800893fd  lea     rax, [rbp+4Fh+var_58]
0x180089401  mov     [rsp+100h+var_E0], rax; unsigned __int64 **
0x180089406  mov     r9, r15; unsigned __int64
0x180089409  mov     r8, [rbp+4Fh+var_50]; unsigned __int64
0x18008940d  mov     rdx, r12; wchar_t *
0x180089410  mov     rcx, r13; this
0x180089413  call    ?ComputeParamOffsets@CCommand@@QEAAJPEB_W_K1PEAPEA_K@Z; CCommand::ComputeParamOffsets(wchar_t const *,unsigned __int64,unsigned __int64,unsigned __int64 * *)
0x180089418  mov     ebx, eax
0x18008941a  lfence
0x18008941d  test    eax, eax
0x18008941f  jns     short loc_180089496
0x180089421  test    byte ptr cs:_bidGblFlags, 2
0x180089428  jz      short loc_18008943E
0x18008942a  mov     r8d, eax
0x18008942d  mov     edx, 1C4809h
0x180089432  mov     rcx, cs:off_1802603F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180089439  call    _bidTraceHR
0x18008943e  lea     rcx, [r13+470h]; this
0x180089445  xor     r9d, r9d; int
0x180089448  mov     r8d, eax; int
0x18008944b  mov     edx, 9CDDh; unsigned int
0x180089450  call    ?PostStandardError@CErrorData@@QEAAJIJJ@Z; CErrorData::PostStandardError(uint,long,long)
0x180089455  jmp     loc_180089D35
0x18008945a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180089461  mov     [rbp+4Fh+var_78], rax
0x180089465  test    byte ptr cs:_bidGblFlags, 2
0x18008946c  jz      short loc_18008948C
0x18008946e  mov     edx, 1BFC09h
0x180089473  mov     r8d, 80004005h
0x180089479  mov     rcx, cs:off_1802603F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180089480  call    _bidTraceHR
0x180089485  mov     ebx, eax
0x180089487  jmp     loc_180089D35
0x18008948c  mov     ebx, 80004005h
0x180089491  jmp     loc_180089D35
0x180089496  mov     [rsp+100h+var_C8], edi; int
0x18008949a  lea     rax, [rbp+4Fh+var_50]
0x18008949e  mov     [rsp+100h+var_D0], rax; unsigned __int64 *
0x1800894a3  lea     rax, [rbp+4Fh+var_68]
0x1800894a7  mov     [rsp+100h+var_D8], rax; wchar_t **
0x1800894ac  mov     rax, [rbp+4Fh+var_58]
0x1800894b0  mov     [rsp+100h+var_E0], rax; unsigned __int64 *
0x1800894b5  mov     r9, r15; unsigned __int64
0x1800894b8  mov     r8, [rbp+4Fh+var_50]; unsigned __int64
0x1800894bc  mov     rdx, r12; wchar_t *
0x1800894bf  mov     rcx, [r13+4B0h]; this
0x1800894c6  call    ?FillInDummyParams@CStmt@@QEAAHPEB_W_K1PEB_KPEAPEA_WPEA_KH@Z; CStmt::FillInDummyParams(wchar_t const *,unsigned __int64,unsigned __int64,unsigned __int64 const *,wchar_t * *,unsigned __int64 *,int)
0x1800894cb  mov     ebx, eax
0x1800894cd  mov     rdx, [rbp+4Fh+var_58]
0x1800894d1  test    rdx, rdx
0x1800894d4  jz      short loc_1800894F2
0x1800894d6  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1800894dd  mov     r8, [rcx]
0x1800894e0  mov     rax, [r8+80h]
0x1800894e7  call    cs:__guard_dispatch_icall_fptr
0x1800894ed  nop
0x1800894ee  mov     [rbp+4Fh+var_58], rdi
0x1800894f2  cmp     ebx, 0FFFFFFFFh
0x1800894f5  jnz     short loc_180089542
0x1800894f7  lfence
0x1800894fa  mov     eax, cs:_bidGblFlags
0x180089500  test    al, 2
0x180089502  jz      short loc_180089525
0x180089504  mov     edx, 1C9009h
0x180089509  mov     r8d, 8007000Eh
0x18008950f  mov     rcx, cs:off_1802603F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180089516  call    _bidTraceHR
0x18008951b  mov     ebx, eax
0x18008951d  mov     eax, cs:_bidGblFlags
0x180089523  jmp     short loc_18008952A
0x180089525  mov     ebx, 8007000Eh
0x18008952a  test    al, 2
0x18008952c  jz      short loc_18008953B
0x18008952e  mov     r8d, ebx
0x180089531  mov     edx, 1C9409h
0x180089536  jmp     loc_180089432
0x18008953b  mov     eax, ebx
0x18008953d  jmp     loc_18008943E
0x180089542  mov     r12, [rbp+4Fh+var_68]
0x180089546  mov     rdi, [rbp+4Fh+var_C0]
0x18008954a  mov     rsi, rdi
0x18008954d  mov     rdx, cs:g_cwchWhere1Eq2
0x180089554  add     rdx, cs:g_cwchFmtOnlyOff
0x18008955b  mov     rax, cs:g_cwchFmtOnlyOn
0x180089562  add     rax, 3
0x180089566  add     rdx, rax
0x180089569  add     rdx, [rbp+4Fh+var_50]
0x18008956d  cmp     rdx, [rbp+4Fh+var_50]
0x180089571  jb      loc_180089CB4
0x180089577  lea     rax, [rdx+r14]
0x18008957b  cmp     rax, rdx
0x18008957e  jb      loc_180089CB4
0x180089584  lea     rbx, [rdi+rax]
0x180089588  cmp     rbx, rax
0x18008958b  jb      loc_180089CB4
0x180089591  mov     [rbp+4Fh+var_C0], rbx
0x180089595  mov     eax, 2
0x18008959a  mul     rbx
0x18008959d  mov     rdx, rax
0x1800895a0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800895a7  cmovb   rdx, rax
0x1800895ab  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1800895b2  mov     rax, [rcx]
0x1800895b5  mov     rax, [rax+70h]
0x1800895b9  call    cs:__guard_dispatch_icall_fptr
0x1800895bf  nop
0x1800895c0  mov     [rbp+4Fh+var_B8], rax
0x1800895c4  test    rax, rax
0x1800895c7  jnz     loc_180089B5D
0x1800895cd  mov     eax, cs:_bidGblFlags
0x1800895d3  test    al, 2
0x1800895d5  jz      loc_180089B37
0x1800895db  mov     edx, 1EB409h
0x1800895e0  mov     r8d, 8007000Eh
0x1800895e6  mov     rcx, cs:off_1802603F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800895ed  call    _bidTraceHR
0x1800895f2  mov     ebx, eax
0x1800895f4  mov     eax, cs:_bidGblFlags
0x1800895fa  jmp     loc_180089B3C
0x1800895ff  xor     esi, esi
0x180089601  mov     rdx, [rbp+4Fh+var_78]; unsigned __int64
0x180089605  test    rdx, rdx
0x180089608  jz      loc_1800896BF
0x18008960e  xchg    ax, ax
0x180089610  lea     r9, [rbp+4Fh+var_70]; unsigned __int64 *
0x180089614  lea     r8, [rbp+4Fh+var_80]; unsigned __int64 *
0x180089618  mov     rcx, rdi; wchar_t *
0x18008961b  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x180089620  cmp     eax, 1
0x180089623  jnz     short loc_180089663
0x180089625  test    ebx, ebx
0x180089627  jnz     short loc_180089698
0x180089629  test    esi, esi
0x18008962b  jnz     short loc_180089698
0x18008962d  mov     rax, [rbp+4Fh+var_80]
0x180089631  lea     rcx, [rdi+rax*2]; String2
0x180089635  mov     rdx, [rbp+4Fh+var_70]; unsigned __int64
0x180089639  call    ?FIsEndFromClause@@YAHPEB_W_K@Z; FIsEndFromClause(wchar_t const *,unsigned __int64)
0x18008963e  test    eax, eax
0x180089640  jz      short loc_180089698
0x180089642  mov     rcx, [rbp+4Fh+var_80]
0x180089646  movzx   eax, word ptr [rdi+rcx*2]
0x18008964a  or      ax, 20h
0x18008964e  cmp     ax, 75h ; 'u'
0x180089652  jz      short loc_18008969C
0x180089654  mov     rdx, [rbp+4Fh+var_78]
0x180089658  test    rdx, rdx
0x18008965b  jz      short loc_1800896C3
0x18008965d  sub     [rbp+4Fh+var_50], rdx
0x180089661  jmp     short loc_1800896C3
0x180089663  cmp     eax, 3
0x180089666  jnz     short loc_180089698
0x180089668  mov     rcx, [rbp+4Fh+var_80]
0x18008966c  movzx   eax, word ptr [rdi+rcx*2]
0x180089670  cmp     ax, 28h ; '('
0x180089674  jnz     short loc_18008967A
0x180089676  inc     ebx
0x180089678  jmp     short loc_18008969C
0x18008967a  cmp     ax, 29h ; ')'
0x18008967e  jnz     short loc_180089684
0x180089680  dec     ebx
0x180089682  jmp     short loc_18008969C
0x180089684  cmp     ax, 7Bh ; '{'
0x180089688  jnz     short loc_18008968E
0x18008968a  inc     esi
0x18008968c  jmp     short loc_18008969C
0x18008968e  cmp     ax, 7Dh ; '}'
0x180089692  jnz     short loc_18008969C
0x180089694  dec     esi
0x180089696  jmp     short loc_18008969C
0x180089698  mov     rcx, [rbp+4Fh+var_80]
0x18008969c  mov     r8, [rbp+4Fh+var_70]
0x1800896a0  lea     rax, [r8+rcx]
0x1800896a4  lea     rdi, [rdi+rax*2]
0x1800896a8  lea     rax, [r8+rcx]
0x1800896ac  mov     rdx, [rbp+4Fh+var_78]
0x1800896b0  sub     rdx, rax
0x1800896b3  mov     [rbp+4Fh+var_78], rdx
  ... truncated ...
```
