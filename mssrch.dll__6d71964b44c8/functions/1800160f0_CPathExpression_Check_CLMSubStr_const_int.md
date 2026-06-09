# CPathExpression::Check(CLMSubStr const &,int)

- ea: `0x1800160f0`
- end: `0x180016c8d`
- name: `?Check@CPathExpression@@QEAAHAEBVCLMSubStr@@H@Z`
- size: `2973`
- prototype: `__int64 __fastcall(CPathExpression *__hidden this, const struct CLMSubStr *, int)`
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015130`
- `0x18002a7d0`

## callees

- `0x1800160f0`
- `0x180017350`
- `0x180022114`
- `0x1800252e4`
- `0x1800269b0`
- `0x1800296b0`
- `0x18003cc50`
- `0x1800495fc`
- `0x18004a0ec`
- `0x180056610`
- `0x180074aac`
- `0x1800771e0`
- `0x18008fa98`
- `0x1800cf9a4`
- `0x1800e2374`
- `0x18010a2e4`
- `0x1801244c0`
- `0x1801244f0`
- `0x1801299c7`
- `0x18013dd98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001693c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001693c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800167d2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800167d2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001684f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180016894`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800169e8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001684f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180016894`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800169e8`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800161e6`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180016234`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800164a4`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800164f2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800166c2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180016715`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800161e6`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180016234`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800164a4`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800164f2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800166c2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180016715`

## string_xrefs

- `0x18001691d`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180016c33`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180016c5e`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180016ab8`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x180016ade`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x180016b44`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x180016b68`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x180016b8c`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x180016bb0`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x180016bcf`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`
- `0x180016bf3`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPathExpression::Check(unsigned __int64 this, const struct CLMSubStr *a2, int a3)
{
  const struct CLMSubStr *v3; // r14
  unsigned __int64 v4; // rsi
  unsigned __int64 v5; // r13
  _DWORD *v6; // r10
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // r15
  __int64 v9; // r14
  unsigned __int64 v10; // rax
  unsigned int n; // ebx
  int v12; // eax
  WCHAR v13; // di
  int v14; // eax
  bool v15; // zf
  unsigned int *v16; // rdi
  unsigned __int64 v17; // r10
  unsigned __int64 v18; // rdi
  __int64 v19; // r14
  __int64 v20; // rdx
  unsigned int v21; // r8d
  __int64 j; // r9
  __int64 v23; // rax
  int k; // r8d
  __int64 v25; // rax
  int v26; // edx
  __int64 v27; // rdx
  unsigned __int64 v28; // r11
  unsigned __int64 v29; // rbx
  __int64 v30; // rdi
  unsigned int v31; // r8d
  unsigned __int64 v32; // r9
  __int64 v33; // r11
  __int16 v34; // ax
  __int16 v35; // ax
  unsigned __int64 v36; // rcx
  int v37; // r15d
  unsigned __int64 v38; // rdx
  unsigned int m; // ebx
  int v40; // eax
  WCHAR v41; // di
  int v42; // eax
  WCHAR v43; // cx
  bool v44; // zf
  __int64 result; // rax
  wchar_t *v46; // r9
  _WORD *v47; // rdi
  unsigned __int64 v48; // rbx
  unsigned __int64 v49; // r14
  __int64 v50; // rcx
  unsigned int v51; // r9d
  int v52; // r8d
  unsigned int i; // ebx
  int v54; // eax
  WCHAR v55; // di
  int v56; // eax
  bool v57; // zf
  unsigned __int64 v58; // rax
  __int64 v59; // r14
  wchar_t *v60; // rax
  wchar_t *v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rcx
  wchar_t *v64; // rax
  CDFA *v65; // rcx
  unsigned int v66; // ebx
  wchar_t *v67; // rax
  unsigned int v68; // ebx
  unsigned int v69; // eax
  __int64 v70; // rax
  __int16 v71; // dx
  unsigned int lpDestStr; // [rsp+20h] [rbp-318h]
  WCHAR SrcStr; // [rsp+30h] [rbp-308h] BYREF
  WCHAR DestStr; // [rsp+38h] [rbp-300h] BYREF
  unsigned int *v75; // [rsp+40h] [rbp-2F8h]
  const struct CLMSubStr *v76; // [rsp+48h] [rbp-2F0h]
  int v77; // [rsp+50h] [rbp-2E8h]
  int v78; // [rsp+54h] [rbp-2E4h]
  __int64 v79; // [rsp+58h] [rbp-2E0h]
  int v80; // [rsp+60h] [rbp-2D8h] BYREF
  int v81; // [rsp+64h] [rbp-2D4h]
  __int64 v82; // [rsp+68h] [rbp-2D0h]
  int v83; // [rsp+70h] [rbp-2C8h] BYREF
  unsigned int v84; // [rsp+74h] [rbp-2C4h]
  __int64 v85; // [rsp+78h] [rbp-2C0h]
  __int128 v86; // [rsp+80h] [rbp-2B8h] BYREF
  _QWORD v87[2]; // [rsp+90h] [rbp-2A8h] BYREF
  unsigned __int64 v88; // [rsp+A0h] [rbp-298h]
  const int *v89; // [rsp+B0h] [rbp-288h] BYREF
  wchar_t *v90; // [rsp+B8h] [rbp-280h]
  int v91; // [rsp+C4h] [rbp-274h]
  wchar_t v92[68]; // [rsp+C8h] [rbp-270h] BYREF
  void **v93; // [rsp+150h] [rbp-1E8h] BYREF
  wchar_t *Str; // [rsp+158h] [rbp-1E0h]
  int v95; // [rsp+160h] [rbp-1D8h]
  unsigned int v96; // [rsp+164h] [rbp-1D4h]
  _BYTE v97[392]; // [rsp+168h] [rbp-1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  v3 = a2;
  v76 = a2;
  v4 = this;
  v5 = this;
  v88 = this;
  v87[0] = a2;
  v6 = (_DWORD *)((char *)a2 + 4);
  v75 = (unsigned int *)((char *)a2 + 4);
  if ( !a3 )
  {
    if ( *(_DWORD *)(this + 444) != *v6 )
    {
      v16 = (unsigned int *)((char *)a2 + 4);
      goto LABEL_23;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= *(_DWORD *)(v4 + 444) )
        return 1;
      DestStr = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 448) + 8LL) + 2LL * (i + *(_DWORD *)(v4 + 440)));
      SrcStr = 0;
      v54 = LCMapStringW(0, 0x200u, &DestStr, 1, &SrcStr, 1);
      v55 = DestStr;
      if ( v54 )
        v55 = SrcStr;
      DestStr = *(_WORD *)(*(_QWORD *)(*((_QWORD *)v3 + 1) + 8LL) + 2LL * (i + *(_DWORD *)v3));
      SrcStr = 0;
      v56 = LCMapStringW(0, 0x200u, &DestStr, 1, &SrcStr, 1);
      this = DestStr;
      if ( v56 )
        LOWORD(this) = SrcStr;
      if ( v55 == 92 || v55 == 47 )
      {
        if ( (_WORD)this == 47 )
          continue;
        v57 = (_WORD)this == 92;
      }
      else
      {
        v57 = v55 == (WCHAR)this;
      }
      if ( !v57 )
      {
        v16 = v75;
        goto LABEL_23;
      }
    }
  }
  this = *(unsigned int *)(this + 44);
  v7 = (unsigned int)*v6;
  if ( (unsigned int)this > (unsigned int)v7 )
    goto LABEL_134;
  if ( this > v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x378,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
      (const char *)0xCE,
      lpDestStr);
  v8 = *(unsigned int *)a2;
  if ( v8 + this < v8 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(this);
  v9 = *((_QWORD *)a2 + 1);
  v10 = *(unsigned int *)(v9 + 20);
  if ( v8 + this > v10 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x40C,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
      (const char *)0xCE,
      lpDestStr);
  if ( *(_DWORD *)(v5 + 444) != (_DWORD)this )
  {
LABEL_134:
    v16 = (unsigned int *)((char *)a2 + 4);
LABEL_21:
    if ( !*(_QWORD *)(v4 + 8) || *(_QWORD *)(v4 + 16) )
    {
      v3 = v76;
    }
    else
    {
      TLMString<64,64,32767>::TLMString<64,64,32767>(&v89, v4 + 456);
      CLMString::Append((CLMString *)&v89, L"*/", 0xFFFFFFFF);
      CLMString::ReplaceAll((CLMString *)&v89, 0x5Cu, 0x2Fu, v51);
      try
      {
        *(_QWORD *)&v86 = operator new(0x68u);
        *(_QWORD *)(v4 + 16) = CRegExpr::CRegExpr((CRegExpr *)v86, v90, v52);
        v3 = v76;
      }
      catch ( ... )
      {
        v5 = v88;
        v4 = v88;
        v3 = (const struct CLMSubStr *)v87[0];
        v16 = v75;
      }
      TLMString<64,64,32767>::~TLMString<64,64,32767>(&v89);
    }
LABEL_23:
    v17 = *(unsigned int *)v3;
    v77 = v17;
    v18 = *v16;
    v78 = v18;
    v19 = *((_QWORD *)v3 + 1);
    v79 = v19;
    v20 = (unsigned int)(v17 + v18 - 1);
    v21 = v20;
    for ( j = v19; v21 >= (unsigned int)v17; --v21 )
    {
      if ( (v21 & 0x80000000) != 0 )
        break;
      j = v19;
      this = v21;
      v23 = *(_QWORD *)(v19 + 8);
      if ( *(_WORD *)(v23 + 2LL * v21) == 92 )
        break;
    }
    for ( k = v21 - v17; (unsigned int)v20 >= (unsigned int)v17; v20 = (unsigned int)(v20 - 1) )
    {
      if ( (int)v20 < 0 )
        break;
      v25 = *(_QWORD *)(j + 8);
      if ( *(_WORD *)(v25 + 2 * v20) == 47 )
        break;
    }
    v26 = v20 - v17;
    if ( k > v26 )
      v26 = k;
    try
    {
      v27 = (unsigned int)(v26 + 1);
      v28 = v18;
      if ( (unsigned int)v27 > v18 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x378,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
          (const char *)0xCE,
          lpDestStr);
      if ( v17 + v27 < v17 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(this);
      v29 = *(unsigned int *)(v19 + 20);
      if ( v17 + v27 > v29 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x40C,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
          (const char *)0xCE,
          lpDestStr);
      v80 = v17;
      v81 = v27;
      v82 = v19;
      v30 = (unsigned int)(v18 - v27);
      v31 = v30;
      if ( v30 + v27 < (unsigned __int64)(unsigned int)v27 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(this);
      if ( v30 + v27 > v28 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x378,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
          (const char *)0xCE,
          lpDestStr);
      v32 = (unsigned int)(v27 + v17);
      if ( v32 + v30 < v32 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(this);
      if ( v32 + v30 > v29 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x40C,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
          (const char *)0xCE,
          lpDestStr);
      v83 = v32;
      v84 = v30;
      v33 = v19;
      v85 = v19;
      if ( (_DWORD)v27 )
      {
        v34 = *(_WORD *)(*(_QWORD *)(v19 + 8) + 2 * v17);
        if ( v34 == 92 || v34 == 47 )
        {
          CLMSubStr::ReduceLeft((CLMSubStr *)&v80, 1u);
          v33 = v85;
          v31 = v84;
          LODWORD(v32) = v83;
          v19 = v82;
          LODWORD(v27) = v81;
          LODWORD(v17) = v80;
        }
      }
      if ( v31 )
      {
        v35 = *(_WORD *)(*(_QWORD *)(v33 + 8) + 2LL * (unsigned int)v32);
        if ( v35 == 92 || v35 == 47 )
        {
          CLMSubStr::ReduceLeft((CLMSubStr *)&v83, 1u);
          v33 = v85;
          v31 = v84;
          LODWORD(v32) = v83;
          v19 = v82;
          LODWORD(v27) = v81;
          LODWORD(v17) = v80;
        }
      }
      *(_QWORD *)&v86 = __PAIR64__(v27, v17);
      *((_QWORD *)&v86 + 1) = v19;
      v87[0] = __PAIR64__(v31, v32);
      v87[1] = v33;
      if ( !*(_QWORD *)(v4 + 8) )
      {
        if ( a3 )
        {
          v36 = *(unsigned int *)(v5 + 460);
          if ( (unsigned int)v36 <= (unsigned int)v27 )
          {
            if ( v36 > (unsigned int)v27 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x378,
                (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
                (const char *)0xCE,
                lpDestStr);
            v37 = v17;
            v38 = (unsigned int)v17 + v36;
            if ( v38 < (unsigned int)v17 )
              SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v36);
            if ( v38 > *(unsigned int *)(v19 + 20) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x40C,
                (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
                (const char *)0xCE,
                lpDestStr);
            for ( m = 0; ; ++m )
            {
              if ( m >= *(_DWORD *)(v5 + 460) )
                goto LABEL_115;
              DestStr = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 464) + 8LL) + 2LL * (m + *(_DWORD *)(v5 + 456)));
              SrcStr = 0;
              v40 = LCMapStringW(0, 0x200u, &DestStr, 1, &SrcStr, 1);
              v41 = DestStr;
              if ( v40 )
                v41 = SrcStr;
              DestStr = *(_WORD *)(*(_QWORD *)(v19 + 8) + 2LL * (m + v37));
              SrcStr = 0;
              v42 = LCMapStringW(0, 0x200u, &DestStr, 1, &SrcStr, 1);
              v43 = DestStr;
              if ( v42 )
                v43 = SrcStr;
              if ( v41 == 92 || v41 == 47 )
              {
                if ( v43 == 47 )
                  continue;
                v44 = v43 == 92;
              }
              else
              {
                v44 = v41 == v43;
              }
              if ( !v44 )
                return 0;
            }
          }
          return 0;
        }
        result = CPathParser::ComparePaths((const struct CLMSubStr *)(v5 + 456), (const struct CLMSubStr *)&v86);
        if ( !(_DWORD)result )
          return result;
LABEL_115:
        v86 = *(_OWORD *)(v4 + 472);
        CLMString::CLMString((CLMString *)&v89, 0x41u, v92, (const struct CLMSubStr *)v87);
        v89 = &CCICommonPathString::`vftable';
        if ( !(unsigned int)CLMSubStr::operator==(&v86, L"*.") || v91 )
        {
          v66 = CDFA::Recognize(*(CDFA **)v4, v90);
          if ( v66 == 1 )
          {
            TLMString<64,64,32767>::~TLMString<64,64,32767>(&v89);
            return 1;
          }
          else if ( v91 && (v67 = wcschr(v90, 0x2Eu)) != 0 && (unsigned int)(v67 - v90) != -1 )
          {
            TLMString<64,64,32767>::~TLMString<64,64,32767>(&v89);
            return v66;
          }
          else
          {
            CLMString::operator+=(&v89, 46);
            v68 = CDFA::Recognize(*(CDFA **)v4, v90);
            TLMString<64,64,32767>::~TLMString<64,64,32767>(&v89);
            return v68;
          }
        }
        else
        {
          TLMString<64,64,32767>::~TLMString<64,64,32767>(&v89);
          return 0;
        }
      }
      v93 = &CLMString::`vftable';
      v46 = (wchar_t *)v97;
      Str = (wchar_t *)v97;
      v95 = 193;
      v47 = (_WORD *)(*(_QWORD *)(v19 + 8) + 2LL * (unsigned int)v17);
      if ( !v47 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
          (const char *)0x80070057LL,
          lpDestStr);
      if ( (_DWORD)v27 == -1 )
      {
        v48 = -1;
        do
          ++v48;
        while ( v47[v48] );
        if ( v48 > 0xFFFFFFFF )
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow((unsigned int)v17);
      }
      else
      {
        LODWORD(v48) = v27;
      }
      v49 = (unsigned int)v48 + 1LL;
      v50 = 0xFFFFFFFFLL;
      if ( v49 > 0xFFFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0xFFFFFFFFLL);
      if ( (unsigned int)v49 > 0xC1 )
      {
        v58 = 2LL * (unsigned int)v49;
        if ( v58 > 0xFFFFFFFF )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x23,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
            (const char *)0x80070216LL,
            lpDestStr);
        v46 = (wchar_t *)malloc((unsigned int)v58);
        Str = v46;
        if ( !v46 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x28,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
            (const char *)0xCE,
            lpDestStr);
        v95 = v48 + 1;
      }
      v59 = (unsigned int)v48;
      if ( !is_mul_ok(2u, v48) )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v50);
      memcpy_0(v46, v47, (unsigned int)(v59 * 2));
      v96 = v48;
      Str[v59] = 0;
      v93 = &TLMString<192,64,32767>::`vftable';
      if ( v96 )
      {
        v60 = wcschr(Str, 0x5Cu);
        if ( v60 )
        {
          v61 = Str;
          v62 = v60 - Str;
          if ( (_DWORD)v62 == -1 )
            goto LABEL_105;
          while ( 1 )
          {
            v61[(unsigned int)v62] = 47;
            v63 = (unsigned int)(v62 + 1);
            if ( (unsigned int)v63 >= v96 )
              break;
            v64 = wcschr(&Str[v63], 0x5Cu);
            if ( !v64 )
              break;
            v61 = Str;
            LODWORD(v62) = v64 - Str;
            if ( (_DWORD)v62 == -1 )
              goto LABEL_105;
          }
        }
      }
      v61 = Str;
LABEL_105:
      if ( !CDFA::Recognize(*(CDFA **)(v4 + 8), v61)
        && (!a3 || (v65 = *(CDFA **)(v4 + 16)) == 0 || !CDFA::Recognize(v65, Str)) )
      {
        v93 = &TLMString<192,64,32767>::`vftable';
        if ( Str && Str != (wchar_t *)v97 )
        {
          free(Str);
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
        }
        return 0;
      }
      TLMString<192,64,32767>::~TLMString<192,64,32767>(&v93);
      goto LABEL_115;
    }
    catch ( ... )
    {
      return 0;
    }
    return result;
  }
  for ( n = 0; n < *(_DWORD *)(v4 + 444); ++n )
  {
    SrcStr = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 448) + 8LL) + 2LL * (n + *(_DWORD *)(v4 + 440)));
    DestStr = 0;
    v12 = LCMapStringW(0, 0x200u, &SrcStr, 1, &DestStr, 1);
    v13 = SrcStr;
    if ( v12 )
      v13 = DestStr;
    DestStr = *(_WORD *)(*(_QWORD *)(v9 + 8) + 2LL * (n + (unsigned int)v8));
    SrcStr = 0;
    v14 = LCMapStringW(0, 0x200u, &DestStr, 1, &SrcStr, 1);
    this = DestStr;
    if ( v14 )
      LOWORD(this) = SrcStr;
    if ( v13 == 92 || v13 == 47 )
    {
      if ( (_WORD)this == 47 )
        continue;
      v15 = (_WORD)this == 92;
    }
    else
    {
      v15 = v13 == (WCHAR)this;
    }
    if ( !v15 )
    {
      v16 = v75;
      goto LABEL_21;
    }
  }
  v69 = *(_DWORD *)(v4 + 44);
  v16 = v75;
  if ( v69 < *v75 )
  {
    if ( v69 )
    {
      this = v69 - 1;
      v70 = *(_QWORD *)(v4 + 32);
      v71 = *(_WORD *)(v70 + 2 * this);
      if ( v71 != 92 && v71 != 47 )
        goto LABEL_21;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800160f0  mov     [rsp+arg_10], r8d
0x1800160f5  push    rbx
0x1800160f6  push    rsi
0x1800160f7  push    rdi
0x1800160f8  push    r12
0x1800160fa  push    r13
0x1800160fc  push    r14
0x1800160fe  push    r15
0x180016100  sub     rsp, 300h
0x180016107  mov     rax, cs:__security_cookie
0x18001610e  xor     rax, rsp
0x180016111  mov     [rsp+338h+var_48], rax
0x180016119  mov     r14, rdx
0x18001611c  mov     [rsp+338h+var_2F0], rdx
0x180016121  mov     rsi, rcx
0x180016124  mov     r13, rcx
0x180016127  mov     [rsp+338h+var_298], rcx
0x18001612f  mov     [rsp+338h+var_2A8], rdx
0x180016137  lea     r10, [rdx+4]
0x18001613b  mov     [rsp+338h+var_2F8], r10
0x180016140  test    r8d, r8d
0x180016143  jz      loc_180016655
0x180016149  mov     ecx, [rcx+2Ch]
0x18001614c  mov     eax, [r10]
0x18001614f  cmp     ecx, eax
0x180016151  ja      loc_180016AF0
0x180016157  cmp     rcx, rax
0x18001615a  ja      loc_180016AAA
0x180016160  mov     r15d, [rdx]
0x180016163  lea     r8, [r15+rcx]
0x180016167  cmp     r8, r15
0x18001616a  jb      loc_180016ACA
0x180016170  mov     r14, [rdx+8]
0x180016174  mov     eax, [r14+14h]
0x180016178  cmp     r8, rax
0x18001617b  ja      loc_180016AD0
0x180016181  cmp     [r13+1BCh], ecx
0x180016188  jnz     loc_180016AF0
0x18001618e  xor     r12d, r12d
0x180016191  mov     ebx, r12d
0x180016194  cmp     ebx, [rsi+1BCh]
0x18001619a  jnb     loc_180016A74
0x1800161a0  mov     edx, [rsi+1B8h]
0x1800161a6  add     edx, ebx
0x1800161a8  mov     rax, [rsi+1C0h]
0x1800161af  mov     rcx, [rax+8]
0x1800161b3  movzx   eax, word ptr [rcx+rdx*2]
0x1800161b7  mov     [rsp+338h+SrcStr], ax
0x1800161bc  mov     [rsp+338h+DestStr], r12w
0x1800161c2  mov     [rsp+338h+cchDest], 1; cchDest
0x1800161ca  lea     rax, [rsp+338h+DestStr]
0x1800161cf  mov     [rsp+338h+lpDestStr], rax; lpDestStr
0x1800161d4  mov     r9d, 1; cchSrc
0x1800161da  lea     r8, [rsp+338h+SrcStr]; lpSrcStr
0x1800161df  mov     edx, 200h; dwMapFlags
0x1800161e4  xor     ecx, ecx; Locale
0x1800161e6  call    cs:__imp_LCMapStringW
0x1800161ec  movzx   edi, [rsp+338h+SrcStr]
0x1800161f1  test    eax, eax
0x1800161f3  cmovnz  di, [rsp+338h+DestStr]
0x1800161f9  lea     ecx, [rbx+r15]
0x1800161fd  mov     rax, [r14+8]
0x180016201  movzx   ecx, word ptr [rax+rcx*2]
0x180016205  mov     [rsp+338h+DestStr], cx
0x18001620a  mov     [rsp+338h+SrcStr], r12w
0x180016210  mov     [rsp+338h+cchDest], 1; cchDest
0x180016218  lea     rax, [rsp+338h+SrcStr]
0x18001621d  mov     [rsp+338h+lpDestStr], rax; unsigned int
0x180016222  mov     r9d, 1; cchSrc
0x180016228  lea     r8, [rsp+338h+DestStr]; lpSrcStr
0x18001622d  mov     edx, 200h; dwMapFlags
0x180016232  xor     ecx, ecx; Locale
0x180016234  call    cs:__imp_LCMapStringW
0x18001623a  movzx   ecx, [rsp+338h+DestStr]
0x18001623f  test    eax, eax
0x180016241  cmovnz  cx, [rsp+338h+SrcStr]
0x180016247  cmp     di, 5Ch ; '\'
0x18001624b  jz      short loc_18001625F
0x18001624d  cmp     di, 2Fh ; '/'
0x180016251  jz      short loc_18001625F
0x180016253  cmp     di, cx
0x180016256  jnz     short loc_18001626B
0x180016258  inc     ebx
0x18001625a  jmp     loc_180016194
0x18001625f  cmp     cx, 2Fh ; '/'
0x180016263  jz      short loc_180016258
0x180016265  cmp     cx, 5Ch ; '\'
0x180016269  jmp     short loc_180016256
0x18001626b  mov     rdi, [rsp+338h+var_2F8]
0x180016270  cmp     qword ptr [rsi+8], 0
0x180016275  jnz     loc_1800165CE
0x18001627b  mov     r14, [rsp+338h+var_2F0]
0x180016280  mov     r15d, 0FFFFFFFFh
0x180016286  mov     r10d, [r14]
0x180016289  mov     [rsp+338h+var_2E8], r10d
0x18001628e  mov     edi, [rdi]
0x180016290  mov     [rsp+338h+var_2E4], edi
0x180016294  mov     r14, [r14+8]
0x180016298  mov     [rsp+338h+var_2E0], r14
0x18001629d  lea     edx, [rdi-1]
0x1800162a0  add     edx, r10d
0x1800162a3  mov     r8d, edx
0x1800162a6  mov     r9, r14
0x1800162a9  cmp     edx, r10d
0x1800162ac  jb      short loc_1800162CE
0x1800162ae  xchg    ax, ax
0x1800162b0  test    r8d, r8d
0x1800162b3  js      short loc_1800162CE
0x1800162b5  mov     r9, r14
0x1800162b8  mov     ecx, r8d
0x1800162bb  mov     rax, [r14+8]
0x1800162bf  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x1800162c4  jz      short loc_1800162CE
0x1800162c6  dec     r8d
0x1800162c9  cmp     r8d, r10d
0x1800162cc  jnb     short loc_1800162B0
0x1800162ce  sub     r8d, r10d
0x1800162d1  cmp     edx, r10d
0x1800162d4  jb      short loc_1800162EC
0x1800162d6  test    edx, edx
0x1800162d8  js      short loc_1800162EC
0x1800162da  mov     rax, [r9+8]
0x1800162de  cmp     word ptr [rax+rdx*2], 2Fh ; '/'
0x1800162e3  jz      short loc_1800162EC
0x1800162e5  dec     edx
0x1800162e7  cmp     edx, r10d
0x1800162ea  jnb     short loc_1800162D6
0x1800162ec  sub     edx, r10d
0x1800162ef  cmp     r8d, edx
0x1800162f2  cmovg   edx, r8d
0x1800162f6  inc     edx
0x1800162f8  mov     eax, edx
0x1800162fa  mov     r11, rdi
0x1800162fd  cmp     rax, rdi
0x180016300  ja      loc_180016B36
0x180016306  lea     r8, [r10+rdx]
0x18001630a  cmp     r8, r10
0x18001630d  jb      loc_180016B55
0x180016313  mov     ebx, [r14+14h]
0x180016317  cmp     r8, rbx
0x18001631a  ja      loc_180016B5A
0x180016320  mov     [rsp+338h+var_2D8], r10d
0x180016325  mov     [rsp+338h+var_2D4], edx
0x180016329  mov     [rsp+338h+var_2D0], r14
0x18001632e  sub     edi, edx
0x180016330  mov     r8d, edi
0x180016333  lea     r9, [rdi+rdx]
0x180016337  cmp     r9, rax
0x18001633a  jb      loc_180016B79
0x180016340  cmp     r9, r11
0x180016343  ja      loc_180016B7E
0x180016349  lea     r9d, [rdx+r10]
0x18001634d  mov     eax, r9d
0x180016350  lea     r11, [r9+rdi]
0x180016354  cmp     r11, rax
0x180016357  jb      loc_180016B9D
0x18001635d  cmp     r11, rbx
0x180016360  ja      loc_180016BA2
0x180016366  mov     [rsp+338h+var_2C8], r9d
0x18001636b  mov     [rsp+338h+var_2C4], r8d
0x180016370  mov     r11, r14
0x180016373  mov     [rsp+338h+var_2C0], r14
0x180016378  test    edx, edx
0x18001637a  jz      short loc_180016399
0x18001637c  mov     rax, [r14+8]
0x180016380  movzx   eax, word ptr [rax+r10*2]
0x180016385  cmp     ax, 5Ch ; '\'
0x180016389  jz      loc_180016756
0x18001638f  cmp     ax, 2Fh ; '/'
0x180016393  jz      loc_180016756
0x180016399  test    r8d, r8d
0x18001639c  jz      short loc_1800163BD
0x18001639e  mov     ecx, r9d
0x1800163a1  mov     rax, [r11+8]
0x1800163a5  movzx   eax, word ptr [rax+rcx*2]
0x1800163a9  cmp     ax, 5Ch ; '\'
0x1800163ad  jz      loc_180016787
0x1800163b3  cmp     ax, 2Fh ; '/'
0x1800163b7  jz      loc_180016787
0x1800163bd  mov     dword ptr [rsp+338h+var_2B8], r10d
0x1800163c5  mov     dword ptr [rsp+338h+var_2B8+4], edx
0x1800163cc  mov     qword ptr [rsp+338h+var_2B8+8], r14
0x1800163d4  mov     dword ptr [rsp+338h+var_2A8], r9d
0x1800163dc  mov     dword ptr [rsp+338h+var_2A8+4], r8d
0x1800163e4  mov     [rsp+338h+var_2A0], r11
0x1800163ec  cmp     qword ptr [rsi+8], 0
0x1800163f1  jnz     loc_18001654E
0x1800163f7  cmp     [rsp+338h+arg_10], 0
0x1800163ff  jz      loc_180016C04
0x180016405  mov     ecx, [r13+1CCh]
0x18001640c  cmp     ecx, edx
0x18001640e  ja      loc_180016529
0x180016414  mov     eax, edx
0x180016416  cmp     rcx, rax
0x180016419  ja      loc_180016BC1
0x18001641f  mov     r15d, r10d
0x180016422  lea     rdx, [r15+rcx]
0x180016426  cmp     rdx, r15
0x180016429  jb      loc_180016BE0
0x18001642f  mov     eax, [r14+14h]
0x180016433  cmp     rdx, rax
0x180016436  ja      loc_180016BE5
0x18001643c  cmp     [r13+1CCh], ecx
0x180016443  jnz     loc_180016529
0x180016449  mov     ebx, r12d
0x18001644c  nop     dword ptr [rax+00h]
0x180016450  cmp     ebx, [r13+1CCh]
0x180016457  jnb     loc_18001695D
0x18001645d  mov     edx, [r13+1C8h]
0x180016464  add     edx, ebx
0x180016466  mov     rax, [r13+1D0h]
0x18001646d  mov     rcx, [rax+8]
0x180016471  movzx   eax, word ptr [rcx+rdx*2]
0x180016475  mov     [rsp+338h+DestStr], ax
0x18001647a  mov     [rsp+338h+SrcStr], r12w
0x180016480  mov     [rsp+338h+cchDest], 1; cchDest
0x180016488  lea     rax, [rsp+338h+SrcStr]
0x18001648d  mov     [rsp+338h+lpDestStr], rax; lpDestStr
0x180016492  mov     r9d, 1; cchSrc
0x180016498  lea     r8, [rsp+338h+DestStr]; lpSrcStr
0x18001649d  mov     edx, 200h; dwMapFlags
0x1800164a2  xor     ecx, ecx; Locale
0x1800164a4  call    cs:__imp_LCMapStringW
0x1800164aa  movzx   edi, [rsp+338h+DestStr]
0x1800164af  test    eax, eax
0x1800164b1  cmovnz  di, [rsp+338h+SrcStr]
0x1800164b7  lea     ecx, [rbx+r15]
0x1800164bb  mov     rax, [r14+8]
0x1800164bf  movzx   ecx, word ptr [rax+rcx*2]
0x1800164c3  mov     [rsp+338h+DestStr], cx
0x1800164c8  mov     [rsp+338h+SrcStr], r12w
0x1800164ce  mov     [rsp+338h+cchDest], 1; cchDest
0x1800164d6  lea     rax, [rsp+338h+SrcStr]
0x1800164db  mov     [rsp+338h+lpDestStr], rax; lpDestStr
0x1800164e0  mov     r9d, 1; cchSrc
0x1800164e6  lea     r8, [rsp+338h+DestStr]; lpSrcStr
0x1800164eb  mov     edx, 200h; dwMapFlags
0x1800164f0  xor     ecx, ecx; Locale
0x1800164f2  call    cs:__imp_LCMapStringW
0x1800164f8  movzx   ecx, [rsp+338h+DestStr]
0x1800164fd  test    eax, eax
0x1800164ff  cmovnz  cx, [rsp+338h+SrcStr]
0x180016505  cmp     di, 5Ch ; '\'
0x180016509  jz      short loc_18001651D
0x18001650b  cmp     di, 2Fh ; '/'
0x18001650f  jz      short loc_18001651D
0x180016511  cmp     di, cx
0x180016514  jnz     short loc_180016529
0x180016516  inc     ebx
0x180016518  jmp     loc_180016450
0x18001651d  cmp     cx, 2Fh ; '/'
0x180016521  jz      short loc_180016516
0x180016523  cmp     cx, 5Ch ; '\'
0x180016527  jmp     short loc_180016514
0x180016529  xor     eax, eax
0x18001652b  mov     rcx, [rsp+338h+var_48]
0x180016533  xor     rcx, rsp; StackCookie
0x180016536  call    __security_check_cookie
0x18001653b  add     rsp, 300h
0x180016542  pop     r15
0x180016544  pop     r14
0x180016546  pop     r13
0x180016548  pop     r12
0x18001654a  pop     rdi
0x18001654b  pop     rsi
0x18001654c  pop     rbx
0x18001654d  retn
0x18001654e  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180016555  mov     [rsp+338h+var_1E8], rax
0x18001655d  lea     r9, [rsp+338h+var_1D0]
0x180016565  mov     [rsp+338h+Str], r9
0x18001656d  mov     [rsp+338h+var_1D8], 0C1h
0x180016578  mov     ecx, r10d
0x18001657b  mov     rax, [r14+8]
0x18001657f  lea     rdi, [rax+rcx*2]
0x180016583  test    rdi, rdi
0x180016586  jz      loc_180016C25
0x18001658c  cmp     edx, r15d
0x18001658f  jnz     loc_180016C49
0x180016595  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001659c  nop     dword ptr [rax+00h]
0x1800165a0  inc     rbx
0x1800165a3  cmp     word ptr [rdi+rbx*2], 0
0x1800165a8  jnz     short loc_1800165A0
0x1800165aa  cmp     rbx, r15
0x1800165ad  ja      loc_180016C44
0x1800165b3  mov     r15d, ebx
0x1800165b6  lea     r14, [r15+1]
0x1800165ba  mov     ecx, 0FFFFFFFFh
0x1800165bf  cmp     r14, rcx
0x1800165c2  jbe     loc_1800167B8
0x1800165c8  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800165ce  cmp     qword ptr [rsi+10h], 0
0x1800165d3  jnz     loc_18001627B
0x1800165d9  lea     rdx, [rsi+1C8h]
0x1800165e0  lea     rcx, [rsp+338h+var_288]
0x1800165e8  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@AEBVCLMSubStr@@@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(CLMSubStr const &)
0x1800165ed  nop
0x1800165ee  mov     r15d, 0FFFFFFFFh
0x1800165f4  mov     r8d, r15d; unsigned int
  ... truncated ...
```
