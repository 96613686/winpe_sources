# BCP_readfmt(tagDBC *,ushort const *)

- ea: `0x10049b4a0`
- end: `0x10049c96d`
- name: `?BCP_readfmt@@YAFPEAUtagDBC@@PEBG@Z`
- size: `5325`
- prototype: `__int16 __fastcall(struct tagDBC *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config`

## callees

- `0x10040799c`
- `0x100407a60`
- `0x100408234`
- `0x1004085bc`
- `0x100408cc8`
- `0x100413190`
- `0x10046c410`
- `0x10046c7e0`
- `0x10046cc48`
- `0x10046cda4`
- `0x100499070`
- `0x10049b4a0`
- `0x10049d560`
- `0x1004a0064`
- `0x1004a9c2c`
- `0x1004abebc`
- `0x1004aca40`
- `0x1004af7ac`
- `0x1004af970`
- `0x1004afccc`
- `0x1004afda4`
- `0x1004b4cd0`
- `0x100520028`
- `0x100520370`
- `0x100525dbc`
- `0x100546894`
- `0x100546a24`
- `0x100546a7c`
- `0x100548210`
- `0x1005494dc`
- `0x1005495d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10049b5bb`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x10049b5bb`
- `api-ms-win-crt-convert-l1-1-0!atol` at `0x10049c0e8`
- `api-ms-win-crt-convert-l1-1-0!atol` at `0x10049c0e8`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x10049bdd0`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x10049bfdf`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x10049c089`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x10049c34e`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x10049bdd0`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x10049bfdf`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x10049c089`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x10049c34e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BCP_readfmt(struct tagDBC *a1, const unsigned __int16 *a2)
{
  unsigned __int16 v5; // di
  __int64 v6; // r12
  __int64 v7; // r13
  __int64 v8; // r14
  __int64 v9; // r14
  void *v10; // rax
  __int64 v11; // rdx
  int v12; // r15d
  int v13; // r14d
  unsigned __int16 v14; // ax
  int v15; // r14d
  unsigned __int16 v16; // ax
  int v17; // r13d
  unsigned __int16 *v18; // r15
  unsigned __int64 v19; // rax
  const WCHAR *v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r15
  unsigned __int16 v23; // dx
  __int64 v24; // rdx
  int v25; // r15d
  unsigned int v26; // ecx
  int v27; // edx
  __int64 v28; // rbx
  int v29; // eax
  void **v30; // rax
  int v31; // eax
  unsigned int v32; // r12d
  int v33; // r15d
  bool v34; // zf
  __int64 v35; // r15
  int v36; // eax
  __int64 v37; // r9
  unsigned __int8 *v38; // r12
  int v39; // r15d
  int v40; // edi
  int v41; // eax
  unsigned __int16 v42; // dx
  __int64 v43; // rdx
  _BYTE *v44; // rcx
  char v45; // al
  _BYTE *v46; // rax
  int v47; // eax
  int v48; // r15d
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // rcx
  int v53; // [rsp+28h] [rbp-E0h]
  __int16 v54; // [rsp+48h] [rbp-C0h]
  __int64 v55; // [rsp+50h] [rbp-B8h]
  unsigned __int8 v56[8]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v57; // [rsp+60h] [rbp-A8h]
  int v58; // [rsp+68h] [rbp-A0h] BYREF
  int v59; // [rsp+6Ch] [rbp-9Ch] BYREF
  unsigned int v60[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v61; // [rsp+78h] [rbp-90h] BYREF
  int v62; // [rsp+80h] [rbp-88h] BYREF
  int v63; // [rsp+84h] [rbp-84h] BYREF
  unsigned int v64; // [rsp+88h] [rbp-80h]
  struct BCPFIELDINFO *v65; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v66[80]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v67; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 v68; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v69; // [rsp+F8h] [rbp-10h]
  __int64 v70; // [rsp+100h] [rbp-8h]
  unsigned __int8 *v71[2]; // [rsp+108h] [rbp+0h]
  union _LARGE_INTEGER v72; // [rsp+118h] [rbp+10h] BYREF
  void **v73; // [rsp+120h] [rbp+18h] BYREF
  int v74; // [rsp+128h] [rbp+20h]
  struct tagDBC *v75; // [rsp+130h] [rbp+28h]
  __int64 v76; // [rsp+138h] [rbp+30h]
  char Str1[4]; // [rsp+140h] [rbp+38h] BYREF
  char v78; // [rsp+144h] [rbp+3Ch]
  char String; // [rsp+148h] [rbp+40h] BYREF
  char v80; // [rsp+149h] [rbp+41h]
  char v81; // [rsp+14Ah] [rbp+42h]
  _BYTE v82[144]; // [rsp+208h] [rbp+100h] BYREF
  CHAR MultiByteStr[144]; // [rsp+298h] [rbp+190h] BYREF

  v76 = -2;
  if ( !ENTERBCPFUNC(a1) )
    return 0;
  v5 = 0;
  v6 = *((_QWORD *)a1 + 15);
  v55 = v6;
  *(_DWORD *)Str1 = 0;
  v78 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  *(_OWORD *)v71 = 0;
  v60[0] = 0;
  v65 = 0;
  v7 = 0;
  v57 = 0;
  if ( *(_DWORD *)(v6 + 1900) == 1 )
  {
    if ( !*(_QWORD *)(v6 + 1872) || *(_DWORD *)(v6 + 1896) )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 4397065);
      PostSQLErrorEx(a1, 0x9CE2u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    }
    else
    {
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      if ( *(_QWORD *)(v6 + 1904) )
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
      v9 = 2 * v8 + 2;
      v10 = SQLAllocateMemoryEx(a1, v9, 1);
      *(_QWORD *)(v6 + 1904) = v10;
      if ( v10 )
      {
        memcpy_s(v10, v9, a2, v9);
        v5 = 1;
      }
    }
    goto LABEL_318;
  }
  if ( !(unsigned int)CExtByteBuffer::FInit((CExtByteBuffer *)&v67, 200, 256) )
  {
    v5 = 0;
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 4429833;
LABEL_317:
      bidTraceMark(0, v11);
      goto LABEL_318;
    }
    goto LABEL_318;
  }
  v12 = *(_DWORD *)(v6 + 52);
  v54 = v12;
  v13 = RetrieveFormatFileAttributes(a2, &v63, &v72);
  if ( v13 < 0 )
  {
    _mm_lfence();
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 4451337);
    v14 = RetCodeFromBCPHRESULT(v13);
    PostSQLErrorEx(a1, v14, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
    v5 = 0;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_318;
    v11 = 4453385;
    goto LABEL_317;
  }
  if ( v72.QuadPart < 0x2000000 )
  {
    if ( v63 )
    {
      _mm_lfence();
      v73 = &CODBCXmlFmtExceptionPoster::`vftable';
      v74 = 0;
      v75 = a1;
      *(_DWORD *)(v6 + 52) |= 0x4000u;
      v15 = ReadXmlFormatFile(
              g_pMO,
              a2,
              Str1,
              5u,
              *(_WORD *)(v6 + 24),
              (struct IXmlFmtExceptionPoster *)&v73,
              v60,
              &v65);
      if ( v15 < 0 )
      {
        v5 = 0;
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 4490249);
        if ( !v74 )
        {
          _mm_lfence();
          if ( (bidGblFlags & 2) != 0 )
            bidTraceMark(0, 4494345);
          v16 = RetCodeFromBCPHRESULT(v15);
          PostSQLErrorEx(a1, v16, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
        }
        goto LABEL_34;
      }
      if ( BCP_columns(a1, v60[0]) && v60[0] )
      {
        v17 = 1;
        while ( 1 )
        {
          *(_DWORD *)&v56[4] = v17;
          v18 = (unsigned __int16 *)((char *)v65 + 288 * (unsigned int)(v17 - 1));
          if ( *v18 && (*(_DWORD *)(v6 + 52) & 0x100) == 0 && *v18 != v17 && *(_QWORD *)(v6 + 1872) )
          {
            v5 = 0;
            if ( (bidGblFlags & 2) != 0 )
              bidTraceMark(0, 4519945);
            PostSQLErrorEx(a1, 0x9D3Cu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
            if ( (bidGblFlags & 2) != 0 )
              bidTraceMark(0, 4519945);
            v7 = v57;
            goto LABEL_69;
          }
          if ( !*((_DWORD *)v18 + 1) )
          {
            if ( *((_BYTE *)v18 + 2) == 39 )
            {
              *((_BYTE *)v18 + 2) = 47;
LABEL_46:
              *((_DWORD *)v18 + 1) = 2;
              goto LABEL_52;
            }
            if ( *((_BYTE *)v18 + 2) == 37 )
            {
              *((_BYTE *)v18 + 2) = 45;
              goto LABEL_46;
            }
            if ( !*((_DWORD *)v18 + 2) && *((int *)v18 + 3) > 0 )
              *((_DWORD *)v18 + 2) = -10;
          }
LABEL_52:
          v5 = BCP_setcolfmt(a1, v17, 5, v18, 2);
          if ( !v5 )
          {
            v7 = 0;
            goto LABEL_72;
          }
          v5 = BCP_setcolfmt(a1, v17, 2, v18 + 2, 4);
          if ( !v5 )
            goto LABEL_71;
          v5 = BCP_setcolfmt(a1, v17, 4, *((void **)v18 + 2), *((_DWORD *)v18 + 3));
          if ( !v5 )
            goto LABEL_71;
          v5 = BCP_setcolfmt(a1, v17, 3, v18 + 4, 4);
          if ( !v5 )
            goto LABEL_71;
          v5 = BCP_setcolfmt(a1, v17, 1, v18 + 1, 1);
          if ( !v5 )
            goto LABEL_71;
          v19 = 0;
          v20 = v18 + 12;
          if ( v18[12] )
          {
            v21 = -1;
            do
              ++v21;
            while ( v20[v21] );
            LODWORD(v61) = 0;
            v19 = SystemLocale::FastAsciiWideCharToMultiByte(
                    *((_DWORD *)a1 + 608),
                    v20,
                    v21,
                    MultiByteStr,
                    0x80u,
                    (int *)&v61,
                    0);
            if ( v19 - 1 > 0x7F )
            {
              v5 = 0;
LABEL_71:
              v7 = 0;
              goto LABEL_72;
            }
          }
          MultiByteStr[v19] = 0;
          v5 = BCP_setcolfmt(a1, v17, 6, MultiByteStr, v19);
          if ( !v5 )
            goto LABEL_71;
          ++v17;
          if ( *(_DWORD *)&v56[4] >= v60[0] )
            goto LABEL_71;
          v6 = v55;
        }
      }
LABEL_34:
      if ( v63 )
      {
        *(_DWORD *)(v6 + 52) &= ~0x4000u;
        *(_DWORD *)(v6 + 52) |= v12 & 0x4000;
        CleanReadXmlFormatFile(v65, v60[0]);
      }
      else
      {
        if ( v7 )
          (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
        bcpClose(a1, (struct BCPFILE *)v66);
      }
      goto LABEL_318;
    }
    v5 = 0;
    if ( !a2 || !*a2 )
    {
      v22 = 4635657;
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 4635657);
      v23 = -25371;
LABEL_315:
      PostSQLErrorEx(a1, v23, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      if ( (bidGblFlags & 2) != 0 )
      {
        v11 = v22;
        goto LABEL_317;
      }
      goto LABEL_318;
    }
    _mm_lfence();
    if ( (unsigned __int16)bcpOpen(a1, a2, 1, (struct BCPFILE *)v66) == 0xFFFF )
    {
      v22 = 4639753;
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 4639753);
      v23 = -25245;
      goto LABEL_315;
    }
    if ( (unsigned __int16)bcpRead(a1, (struct BCPFILE *)v66, 3u, (unsigned __int8 *)Str1) )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 4647945);
      PostSQLErrorEx(a1, 0x9D2Bu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_34;
      v24 = 4647945;
      goto LABEL_84;
    }
    if ( (!strcmp_0(Str1, "14.")
       || !strcmp_0(Str1, "13.")
       || !strcmp_0(Str1, "12.")
       || !strcmp_0(Str1, "11.")
       || !strcmp_0(Str1, "10."))
      && (unsigned __int16)bcpRead(a1, (struct BCPFILE *)v66, 1u, (unsigned __int8 *)&Str1[3]) )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 4661257);
      PostSQLErrorEx(a1, 0x9D2Bu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_34;
      v24 = 4661257;
      goto LABEL_84;
    }
    if ( strcmp_0(Str1, "14.0")
      && strcmp_0(Str1, "13.0")
      && strcmp_0(Str1, "12.0")
      && strcmp_0(Str1, "11.0")
      && strcmp_0(Str1, "10.0")
      && strcmp_0(Str1, "9.0")
      && strcmp_0(Str1, "8.0")
      && strcmp_0(Str1, "7.0")
      && strcmp_0(Str1, "6.0")
      && strcmp_0(Str1, "4.2") )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 4677641);
      PostSQLErrorEx(a1, 0x9D19u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_34;
      v24 = 4677641;
      goto LABEL_84;
    }
    if ( bcpSkipWhiteSp(a1, (struct BCPFILE *)v66, 1u) == -1 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 4682761);
      PostSQLErrorEx(a1, 0x9D1Au, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_34;
      v24 = 4682761;
      goto LABEL_84;
    }
    if ( bcpReadNumber(a1, (struct BCPFILE *)v66, (unsigned __int8 *)&String, 0xB2u) == -1 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 4689929);
      PostSQLErrorEx(a1, 0x9D15u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_34;
      v24 = 4689929;
LABEL_84:
      bidTraceMark(0, v24);
      goto LABEL_34;
    }
    v25 = atoi(&String);
    v64 = v25;
    v5 = BCP_columns(a1, v25);
    if ( !v5 )
      goto LABEL_308;
    v26 = *((_DWORD *)a1 + 608);
    if ( v26 >= 0xC42C
      && (v26 == 50220
       || v26 - 50221 <= 8 && (v27 = 339, _bittest(&v27, v26 - 50221))
       || v26 == 52936
       || v26 == 54936
       || v26 - 65000 <= 1
       || v26 - 57002 <= 9) )
    {
      v28 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 48);
      v57 = v28;
      v61 = v28;
      if ( v28 )
      {
        v29 = *((_DWORD *)a1 + 608);
        *(_QWORD *)v28 = &NS_BCP_ODBC::IColumnNameProcessor::`vftable';
        *(_QWORD *)(v28 + 16) = a1;
        *(_QWORD *)(v28 + 24) = v66;
        *(_DWORD *)(v28 + 32) = v29;
        *(_DWORD *)(v28 + 36) = bidObtainItemIDW(
                                  `NS_BCP_ODBC::IColumnNameProcessor::IColumnNameProcessor'::`4'::_bidPtrSA_051_1175[0],
                                  v28,
                                  *(int *)a1);
        v30 = &NS_BCP_ODBC::CColumnNameProcessor4Byte::`vftable';
LABEL_132:
        *(_QWORD *)v28 = v30;
LABEL_134:
        v7 = v57;
        if ( !v57 )
        {
          v5 = 0;
          if ( (bidGblFlags & 2) != 0 )
            bidTraceMark(0, 4707337);
          PostSQLErrorEx(a1, 0x9CDDu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
          if ( (bidGblFlags & 2) != 0 )
            bidTraceMark(0, 4707337);
LABEL_69:
          LOWORD(v12) = v54;
          goto LABEL_34;
        }
        v32 = 0;
        LODWORD(v61) = 0;
        if ( v25 )
        {
          v33 = 1;
          *(_DWORD *)&v56[4] = 1;
          while ( 1 )
          {
            if ( bcpSkipWhiteSp(a1, (struct BCPFILE *)v66, 1u) == -1 )
            {
              v35 = 4714505;
              goto LABEL_301;
            }
            if ( bcpReadNumber(a1, (struct BCPFILE *)v66, (unsigned __int8 *)&String, 0xB2u) == -1 )
            {
              v35 = 4718601;
              goto LABEL_301;
            }
            if ( atoi(&String) != v33 )
            {
              v35 = 4723721;
LABEL_301:
              v5 = 0;
              if ( (bidGblFlags & 2) != 0 )
                bidTraceMark(0, v35);
              v42 = -25318;
              goto LABEL_254;
            }
            if ( bcpSkipWhiteSp(a1, (struct BCPFILE *)v66, 0) == -1 )
            {
              v5 = 0;
              v35 = 4731913;
LABEL_295:
              if ( (bidGblFlags & 2) != 0 )
                bidTraceMark(0, v35);
              v42 = -25269;
LABEL_254:
              PostSQLErrorEx(a1, v42, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_72;
              v51 = v35;
LABEL_256:
              bidTraceMark(0, v51);
              goto LABEL_72;
            }
            if ( bcpReadChars(a1, (struct BCPFILE *)v66, (unsigned __int8 *)&String, 0xB2u) == -1 )
            {
              v5 = 0;
              v35 = 4739081;
              goto LABEL_295;
            }
            v56[1] = FieldNameToTDSTypeA(&String);
            if ( !v56[1] )
            {
              v5 = 0;
              v35 = 4746249;
              goto LABEL_295;
            }
            if ( bcpSkipWhiteSp(a1, (struct BCPFILE *)v66, 0) == -1 )
            {
              v5 = 0;
              v35 = 4751369;
              goto LABEL_265;
            }
            if ( bcpReadNumber(a1, (struct BCPFILE *)v66, (unsigned __int8 *)&String, 0xB2u) == -1 )
            {
              v5 = 0;
              v35 = 4755465;
              goto LABEL_265;
            }
            if ( String != 48 || v80 )
            {
              v58 = atoi(&String);
              if ( !v58 )
              {
                v5 = 0;
                v35 = 4767753;
                goto LABEL_273;
              }
            }
            else
            {
              v58 = 0;
            }
            if ( bcpSkipWhiteSp(a1, (struct BCPFILE *)v66, 0) == -1 )
            {
              v5 = 0;
              v35 = 4773897;
              goto LABEL_265;
            }
            if ( bcpReadNumber(a1, (struct BCPFILE *)v66, (unsigned __int8 *)&String, 0xB2u) == -1 )
            {
              v5 = 0;
              v35 = 4777993;
              goto LABEL_265;
            }
            if ( String == 48 && !v80 )
            {
              v59 = 0;
              goto LABEL_178;
            }
            v59 = atol(&String);
            if ( !v59 )
            {
              v5 = 0;
              PostFormattedError(a1, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF, 1, 0x9D64u, v32 + 1);
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_72;
              v51 = 4794377;
              goto LABEL_256;
            }
            if ( v56[1] > 0x6Du )
            {
              if ( v56[1] == 110 || v56[1] == 111 || v56[1] == 231 || v56[1] == 239 || v56[1] == 240 || v56[1] == 241 )
                goto LABEL_178;
              v34 = v56[1] == 245;
            }
            else
            {
              if ( v56[1] == 109
                || v56[1] == 34
                || v56[1] == 35
                || v56[1] == 37
                || v56[1] == 38
                || v56[1] == 39
                || v56[1] == 45
                || v56[1] == 47 )
              {
                goto LABEL_178;
              }
              v34 = v56[1] == 99;
            }
            if ( !v34 )
              v59 = -1;
LABEL_178:
            if ( bcpSkipWhiteSp(a1, (struct BCPFILE *)v66, 0) == -1 )
            {
              v5 = 0;
              v35 = 4831241;
              goto LABEL_265;
            }
            if ( (unsigned __int16)bcpRead(a1, (struct BCPFILE *)v66, 1u, (unsigned __int8 *)&String) == 0xFFFF )
            {
              v5 = 0;
              v35 = 4835337;
              goto LABEL_251;
            }
            if ( String != 34 )
            {
              v5 = 0;
              v35 = 4839433;
              goto LABEL_251;
            }
            if ( !(unsigned int)CExtBaseBuffer::ReInit((CExtBaseBuffer *)&v67, v69, 0) )
            {
              v5 = 0;
              v35 = 4848649;
              if ( (bidGblFlags & 2) != 0 )
                bidTraceMark(0, 4848649);
              v42 = -24435;
              goto LABEL_254;
            }
            v5 = bcpRead(a1, (struct BCPFILE *)v66, 1u, v56);
            if ( v5 == 0xFFFF )
            {
              v5 = 0;
              v35 = 4854793;
LABEL_251:
              if ( (bidGblFlags & 2) != 0 )
                bidTraceMark(0, v35);
              v42 = -25320;
              goto LABEL_254;
            }
            while ( v56[0] != 34 )
            {
              v36 = CExtByteBuffer::WriteByteToExtBuffer((CExtByteBuffer *)&v67, v56[0]);
              if ( v36 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_72;
                v50 = 4859913;
                goto LABEL_249;
              }
              if ( v56[0] == 92 )
              {
                v5 = bcpRead(a1, (struct BCPFILE *)v66, 1u, v56);
                if ( v5 == 0xFFFF )
                {
                  v5 = 0;
                  v35 = 4865033;
                  goto LABEL_251;
                }
                v36 = CExtByteBuffer::WriteByteToExtBuffer((CExtByteBuffer *)&v67, v56[0]);
                if ( v36 < 0 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v50 = 4867081;
                    goto LABEL_249;
                  }
LABEL_72:
                  v6 = v55;
                  goto LABEL_69;
                }
              }
              v5 = bcpRead(a1, (struct BCPFILE *)v66, 1u, v56);
              if ( v5 == 0xFFFF )
              {
                v5 = 0;
                v35 = 4871177;
                goto LABEL_251;
              }
              if ( v68 > 0x7FFFFFFF )
              {
                v5 = 0;
                v35 = 4875273;
                if ( (bidGblFlags & 2) != 0 )
                  bidTraceMark(0, 4875273);
                v42 = -25317;
                goto LABEL_254;
              }
            }
            v36 = CExtByteBuffer::WriteByteToExtBuffer((CExtByteBuffer *)&v67, 0);
            if ( v36 < 0 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_72;
              v50 = 4881417;
LABEL_249:
              _mm_lfence();
              bidTraceHR(0, v50, (unsigned int)v36, v37);
              goto LABEL_72;
            }
            v38 = v71[0];
            v39 = ConvertTerminatorToBinary(v71[0], v71[0], v68);
            if ( v39 == -1 )
            {
              v5 = 0;
              goto LABEL_72;
            }
            if ( bcpSkipWhiteSp(a1, (struct BCPFILE *)v66, 0) == -1 )
            {
              v35 = 4902921;
LABEL_264:
              v5 = 0;
LABEL_265:
              if ( (bidGblFlags & 2) != 0 )
                bidTraceMark(0, v35);
              v42 = -25315;
              goto LABEL_254;
            }
            if ( bcpReadNumber(a1, (struct BCPFILE *)v66, (unsigned __int8 *)&String, 0xB2u) == -1 )
            {
              v35 = 4907017;
              goto LABEL_264;
            }
            if ( String == 48 && !v80 )
            {
              v62 = 0;
LABEL_198:
              v40 = *(_DWORD *)&v56[4];
              goto LABEL_199;
            }
            v41 = atoi(&String);
            v62 = v41;
            if ( !v41 )
            {
              v5 = 0;
              v35 = 4919305;
LABEL_273:
              if ( (bidGblFlags & 2) != 0 )
                bidTraceMark(0, v35);
              v42 = -25378;
              goto LABEL_254;
            }
            if ( (*(_DWORD *)(v55 + 52) & 0x100) != 0 )
              goto LABEL_198;
            v40 = *(_DWORD *)&v56[4];
            if ( v41 != *(_DWORD *)&v56[4] && *(_QWORD *)(v55 + 1872) )
            {
              v5 = 0;
              v35 = 4927497;
              if ( (bidGblFlags & 2) != 0 )
                bidTraceMark(0, 4927497);
              v42 = -25284;
              goto LABEL_254;
            }
LABEL_199:
            if ( bcpSkipWhiteSp(a1, (struct BCPFILE *)v66, 0) == -1 )
            {
              v35 = 4934665;
              goto LABEL_264;
            }
            if ( (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) == 0xFFFF )
            {
              v35 = 4937737;
              goto LABEL_264;
            }
            if ( SkipChars(a1, (struct BCPFILE *)v66) == -1 )
            {
              v5 = 0;
              v35 = 4940809;
              goto LABEL_251;
            }
            if ( (unsigned __int8)(Str1[0] - 56) > 1u && Str1[0] != 49 )
              goto LABEL_217;
            if ( bcpSkipWhiteSp(a1, (struct BCPFILE *)v66, 0) == -1 )
            {
              v35 = 4947977;
              goto LABEL_264;
            }
            if ( bcpReadChars(a1, (struct BCPFILE *)v66, (unsigned __int8 *)&String, 0xB2u) == -1 )
            {
              v35 = 4952073;
              goto LABEL_264;
            }
            if ( String != 34 || v80 != 34 || v81 )
            {
              v43 = 129;
              v44 = v82;
              do
              {
                if ( v43 == -2147483517 )
                  break;
                v45 = *(v44 - 192);
                if ( !v45 )
                  break;
                *v44++ = v45;
                --v43;
              }
              while ( v43 );
              v46 = v44 - 1;
              if ( v43 )
                v46 = v44;
              *v46 = 0;
            }
            else
            {
LABEL_217:
              v82[0] = 0;
            }
            if ( !v58 )
            {
              if ( v56[1] == 39 )
              {
                v56[1] = 47;
              }
              else
              {
                if ( v56[1] != 37 )
                {
                  v47 = v59;
                  if ( !v59 )
                  {
                    if ( v39 > 0 )
                      v47 = -10;
                    v59 = v47;
                  }
                  goto LABEL_235;
                }
                v56[1] = 45;
              }
              v58 = 2;
            }
LABEL_235:
            v5 = BCP_setcolfmt(a1, v40, 5, &v62, 4);
            if ( v5 )
            {
              v5 = BCP_setcolfmt(a1, *(int *)&v56[4], 2, &v58, 4);
              if ( v5 )
              {
                v53 = v39;
                v48 = *(_DWORD *)&v56[4];
                v5 = BCP_setcolfmt(a1, *(int *)&v56[4], 4, v38, v53);
                if ( v5 )
                {
                  v5 = BCP_setcolfmt(a1, v48, 3, &v59, 4);
                  if ( v5 )
                  {
                    v5 = BCP_setcolfmt(a1, v48, 1, &v56[1], 1);
                    if ( v5 )
                    {
                      if ( (unsigned __int8)(Str1[0] - 56) > 1u && Str1[0] != 49 )
                        goto LABEL_245;
                      v49 = -1;
                      do
                        ++v49;
                      while ( v82[v49] );
                      v5 = BCP_setcolfmt(a1, v48, 6, v82, v49);
                      if ( v5 )
                      {
LABEL_245:
                        v32 = v61 + 1;
                        LODWORD(v61) = v32;
                        v33 = v48 + 1;
                        *(_DWORD *)&v56[4] = v33;
                        if ( v32 < v64 )
                          continue;
                      }
                    }
                  }
                }
              }
            }
            goto LABEL_72;
          }
        }
        v6 = v55;
LABEL_308:
        LOWORD(v12) = v54;
        goto LABEL_34;
      }
    }
    else
    {
      v28 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 48);
      v57 = v28;
      v61 = v28;
      if ( v28 )
      {
        v31 = *((_DWORD *)a1 + 608);
        *(_QWORD *)v28 = &NS_BCP_ODBC::IColumnNameProcessor::`vftable';
        *(_QWORD *)(v28 + 16) = a1;
        *(_QWORD *)(v28 + 24) = v66;
        *(_DWORD *)(v28 + 32) = v31;
        *(_DWORD *)(v28 + 36) = bidObtainItemIDW(
                                  `NS_BCP_ODBC::IColumnNameProcessor::IColumnNameProcessor'::`4'::_bidPtrSA_051_1175[0],
                                  v28,
                                  *(int *)a1);
        v30 = &NS_BCP_ODBC::CColumnNameProcessorDBCS::`vftable';
        goto LABEL_132;
      }
    }
    v57 = 0;
    goto LABEL_134;
  }
  PostFormattedError(a1, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF, 1, 0x9D67u, 0x2000000);
  v5 = 0;
  if ( (bidGblFlags & 2) != 0 )
  {
    v11 = 4463625;
    goto LABEL_317;
  }
LABEL_318:
  v52 = *(_QWORD *)(*((_QWORD *)a1 + 12) + 320LL) + 32LL;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 24LL))(v52);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)a1 + 9) + 32LL) + 24LL))(*((_QWORD *)a1 + 9) + 32LL);
  CExtBaseBuffer::~CExtBaseBuffer((CExtBaseBuffer *)&v67);
  return v5;
}

```

## disassembly

```asm
0x10049b4a0  mov     rax, rsp
0x10049b4a3  push    rbp
0x10049b4a4  push    rsi
0x10049b4a5  push    rdi
0x10049b4a6  push    r12
0x10049b4a8  push    r13
0x10049b4aa  push    r14
0x10049b4ac  push    r15
0x10049b4ae  lea     rbp, [rax-268h]
0x10049b4b5  sub     rsp, 330h
0x10049b4bc  mov     [rbp+260h+var_230], 0FFFFFFFFFFFFFFFEh
0x10049b4c4  mov     [rax+18h], rbx
0x10049b4c8  mov     rax, cs:__security_cookie
0x10049b4cf  xor     rax, rsp
0x10049b4d2  mov     [rbp+260h+var_40], rax
0x10049b4d9  mov     rbx, rdx
0x10049b4dc  mov     rsi, rcx
0x10049b4df  call    ?ENTERBCPFUNC@@YAFPEAUtagDBC@@@Z; ENTERBCPFUNC(tagDBC *)
0x10049b4e4  xor     r15d, r15d
0x10049b4e7  test    ax, ax
0x10049b4ea  jnz     short loc_10049B4F5
0x10049b4ec  movzx   eax, r15w
0x10049b4f0  jmp     loc_10049C943
0x10049b4f5  movzx   edi, r15w
0x10049b4f9  mov     r12, [rsi+78h]
0x10049b4fd  mov     qword ptr [rsp+360h+var_318], r12
0x10049b502  xor     eax, eax
0x10049b504  mov     dword ptr [rbp+260h+Str1], eax
0x10049b507  mov     [rbp+260h+var_224], al
0x10049b50a  mov     [rbp+260h+var_280], r15
0x10049b50e  mov     [rbp+260h+var_278], r15
0x10049b512  mov     [rbp+260h+var_270], r15
0x10049b516  mov     [rbp+260h+var_268], r15
0x10049b51a  xorps   xmm0, xmm0
0x10049b51d  movdqu  xmmword ptr [rbp+260h+var_260], xmm0
0x10049b522  mov     [rsp+360h+var_2F8], r15d
0x10049b527  mov     [rbp+260h+var_2D8], r15
0x10049b52b  mov     r13, r15
0x10049b52e  mov     qword ptr [rsp+360h+var_308], r15
0x10049b533  cmp     dword ptr [r12+76Ch], 1
0x10049b53c  jnz     loc_10049B602
0x10049b542  cmp     [r12+750h], r15
0x10049b54a  jz      short loc_10049B5CB
0x10049b54c  cmp     [r12+768h], r15d
0x10049b554  jnz     short loc_10049B5CB
0x10049b556  or      r14, 0FFFFFFFFFFFFFFFFh
0x10049b55a  inc     r14
0x10049b55d  cmp     [rbx+r14*2], r15w
0x10049b562  jnz     short loc_10049B55A
0x10049b564  mov     rdx, [r12+770h]
0x10049b56c  test    rdx, rdx
0x10049b56f  jz      short loc_10049B585
0x10049b571  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10049b578  mov     rax, [rcx]
0x10049b57b  mov     rax, [rax+28h]
0x10049b57f  call    cs:__guard_dispatch_icall_fptr
0x10049b585  lea     r14, ds:2[r14*2]
0x10049b58d  mov     r8d, 1; int
0x10049b593  mov     rdx, r14; dwBytes
0x10049b596  mov     rcx, rsi; struct tagOBJBASE *
0x10049b599  call    ?SQLAllocateMemoryEx@@YAPEAXPEAUtagOBJBASE@@_KH@Z; SQLAllocateMemoryEx(tagOBJBASE *,unsigned __int64,int)
0x10049b59e  mov     [r12+770h], rax
0x10049b5a6  test    rax, rax
0x10049b5a9  jz      loc_10049C905
0x10049b5af  mov     r9, r14; SourceSize
0x10049b5b2  mov     r8, rbx; Source
0x10049b5b5  mov     rdx, r14; DestinationSize
0x10049b5b8  mov     rcx, rax; Destination
0x10049b5bb  call    cs:__imp_memcpy_s
0x10049b5c1  mov     edi, 1
0x10049b5c6  jmp     loc_10049C905
0x10049b5cb  mov     ebx, 2
0x10049b5d0  test    byte ptr cs:_bidGblFlags, bl
0x10049b5d6  jz      short loc_10049B5E4
0x10049b5d8  mov     edx, 431809h
0x10049b5dd  xor     ecx, ecx
0x10049b5df  call    _bidTraceMark
0x10049b5e4  mov     edx, 9CE2h; unsigned __int16
0x10049b5e9  or      dword ptr [rsp+360h+var_340], 0FFFFFFFFh
0x10049b5ee  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x10049b5f2  xor     r8d, r8d; int
0x10049b5f5  mov     rcx, rsi; struct tagOBJBASE *
0x10049b5f8  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x10049b5fd  jmp     loc_10049C905
0x10049b602  mov     edx, 0C8h; unsigned __int64
0x10049b607  lea     r8d, [rdx+38h]; unsigned __int64
0x10049b60b  lea     rcx, [rbp+260h+var_280]; this
0x10049b60f  call    ?FInit@CExtByteBuffer@@QEAAH_K0@Z; CExtByteBuffer::FInit(unsigned __int64,unsigned __int64)
0x10049b614  test    eax, eax
0x10049b616  jnz     short loc_10049B635
0x10049b618  movzx   edi, r15w
0x10049b61c  lea     ebx, [rax+2]
0x10049b61f  test    byte ptr cs:_bidGblFlags, bl
0x10049b625  jz      loc_10049C905
0x10049b62b  mov     edx, 439809h
0x10049b630  jmp     loc_10049C8FE
0x10049b635  mov     r15d, [r12+34h]
0x10049b63a  mov     dword ptr [rsp+360h+var_320], r15d
0x10049b63f  lea     r8, [rbp+260h+var_250]; union _LARGE_INTEGER *
0x10049b643  lea     rdx, [rsp+360h+var_2E4]; int *
0x10049b648  mov     rcx, rbx; unsigned __int16 *
0x10049b64b  call    ?RetrieveFormatFileAttributes@@YAJPEBGPEAHPEAT_LARGE_INTEGER@@@Z; RetrieveFormatFileAttributes(ushort const *,int *,_LARGE_INTEGER *)
0x10049b650  mov     r14d, eax
0x10049b653  xor     ecx, ecx
0x10049b655  test    eax, eax
0x10049b657  jns     short loc_10049B6AB
0x10049b659  lfence
0x10049b65c  lea     ebx, [rcx+2]
0x10049b65f  test    byte ptr cs:_bidGblFlags, bl
0x10049b665  jz      short loc_10049B671
0x10049b667  mov     edx, 43EC09h
0x10049b66c  call    _bidTraceMark
0x10049b671  mov     ecx, r14d; int
0x10049b674  call    ?RetCodeFromBCPHRESULT@@YAGJ@Z; RetCodeFromBCPHRESULT(long)
0x10049b679  movzx   edx, ax; unsigned __int16
0x10049b67c  or      dword ptr [rsp+360h+var_340], 0FFFFFFFFh
0x10049b681  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x10049b685  xor     r8d, r8d; int
0x10049b688  mov     rcx, rsi; struct tagOBJBASE *
0x10049b68b  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x10049b690  xor     eax, eax
0x10049b692  movzx   edi, ax
0x10049b695  test    byte ptr cs:_bidGblFlags, bl
0x10049b69b  jz      loc_10049C905
0x10049b6a1  mov     edx, 43F409h
0x10049b6a6  jmp     loc_10049C8FE
0x10049b6ab  mov     edx, 2000000h
0x10049b6b0  cmp     qword ptr [rbp+260h+var_250], rdx
0x10049b6b4  jl      short loc_10049B6F8
0x10049b6b6  mov     eax, 9D67h
0x10049b6bb  mov     dword ptr [rsp+360h+var_338], edx
0x10049b6bf  mov     [rsp+360h+var_340], ax; unsigned __int16
0x10049b6c4  mov     r9d, 1; int
0x10049b6ca  or      r8d, 0FFFFFFFFh; unsigned int
0x10049b6ce  or      rdx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x10049b6d2  mov     rcx, rsi; struct tagOBJBASE *
0x10049b6d5  call    ?PostFormattedError@@YAFPEAUtagOBJBASE@@_KKHGZZ; PostFormattedError(tagOBJBASE *,unsigned __int64,ulong,int,ushort,...)
0x10049b6da  xor     eax, eax
0x10049b6dc  movzx   edi, ax
0x10049b6df  lea     ebx, [rax+2]
0x10049b6e2  test    byte ptr cs:_bidGblFlags, bl
0x10049b6e8  jz      loc_10049C905
0x10049b6ee  mov     edx, 441C09h
0x10049b6f3  jmp     loc_10049C8FE
0x10049b6f8  cmp     [rsp+360h+var_2E4], ecx
0x10049b6fc  jz      loc_10049BA57
0x10049b702  lfence
0x10049b705  lea     rax, ??_7CODBCXmlFmtExceptionPoster@@6B@; const CODBCXmlFmtExceptionPoster::`vftable'
0x10049b70c  mov     [rbp+260h+var_248], rax
0x10049b710  mov     [rbp+260h+var_240], ecx
0x10049b713  mov     [rbp+260h+var_238], rsi
0x10049b717  bts     dword ptr [r12+34h], 0Eh
0x10049b71e  lea     rax, [rbp+260h+var_2D8]
0x10049b722  mov     [rsp+360h+var_328], rax; struct BCPFIELDINFO **
0x10049b727  lea     rax, [rsp+360h+var_2F8]
0x10049b72c  mov     [rsp+360h+var_330], rax; unsigned int *
0x10049b731  lea     rax, [rbp+260h+var_248]
0x10049b735  mov     [rsp+360h+var_338], rax; struct IXmlFmtExceptionPoster *
0x10049b73a  movzx   eax, word ptr [r12+18h]
0x10049b740  mov     [rsp+360h+var_340], ax; unsigned int
0x10049b745  mov     r9d, 5; unsigned __int64
0x10049b74b  lea     r8, [rbp+260h+Str1]; char *
0x10049b74f  mov     rdx, rbx; unsigned __int16 *
0x10049b752  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; struct IMalloc *
0x10049b759  call    ?ReadXmlFormatFile@@YAJPEAUIMalloc@@PEBGPEAD_KGPEAVIXmlFmtExceptionPoster@@PEAIPEAPEAUBCPFIELDINFO@@@Z; ReadXmlFormatFile(IMalloc *,ushort const *,char *,unsigned __int64,ushort,IXmlFmtExceptionPoster *,uint *,BCPFIELDINFO * *)
0x10049b75e  mov     r14d, eax
0x10049b761  test    eax, eax
0x10049b763  jns     loc_10049B7F0
0x10049b769  xor     edi, edi
0x10049b76b  lea     ebx, [rdi+2]
0x10049b76e  test    byte ptr cs:_bidGblFlags, bl
0x10049b774  jz      short loc_10049B782
0x10049b776  mov     edx, 448409h
0x10049b77b  xor     ecx, ecx
0x10049b77d  call    _bidTraceMark
0x10049b782  xor     eax, eax
0x10049b784  cmp     [rbp+260h+var_240], eax
0x10049b787  jnz     short loc_10049B7BF
0x10049b789  lfence
0x10049b78c  test    byte ptr cs:_bidGblFlags, bl
0x10049b792  jz      short loc_10049B7A0
0x10049b794  mov     edx, 449409h
0x10049b799  xor     ecx, ecx
0x10049b79b  call    _bidTraceMark
0x10049b7a0  mov     ecx, r14d; int
0x10049b7a3  call    ?RetCodeFromBCPHRESULT@@YAGJ@Z; RetCodeFromBCPHRESULT(long)
0x10049b7a8  movzx   edx, ax; unsigned __int16
0x10049b7ab  or      dword ptr [rsp+360h+var_340], 0FFFFFFFFh
0x10049b7b0  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x10049b7b4  xor     r8d, r8d; int
0x10049b7b7  mov     rcx, rsi; struct tagOBJBASE *
0x10049b7ba  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x10049b7bf  xor     ebx, ebx
0x10049b7c1  cmp     [rsp+360h+var_2E4], ebx
0x10049b7c5  jz      loc_10049C897
0x10049b7cb  btr     dword ptr [r12+34h], 0Eh
0x10049b7d2  and     r15d, 4000h
0x10049b7d9  or      [r12+34h], r15d
0x10049b7de  mov     edx, [rsp+360h+var_2F8]; unsigned int
0x10049b7e2  mov     rcx, [rbp+260h+var_2D8]; struct BCPFIELDINFO *
0x10049b7e6  call    ?CleanReadXmlFormatFile@@YAXPEAUBCPFIELDINFO@@I@Z; CleanReadXmlFormatFile(BCPFIELDINFO *,uint)
0x10049b7eb  jmp     loc_10049C905
0x10049b7f0  mov     edx, [rsp+360h+var_2F8]; int
0x10049b7f4  mov     rcx, rsi; struct tagDBC *
0x10049b7f7  call    ?BCP_columns@@YAFPEAUtagDBC@@H@Z; BCP_columns(tagDBC *,int)
0x10049b7fc  xor     ebx, ebx
0x10049b7fe  test    ax, ax
0x10049b801  jz      short loc_10049B7C1
0x10049b803  cmp     [rsp+360h+var_2F8], ebx
0x10049b807  jbe     short loc_10049B7C1
0x10049b809  lea     r13d, [rbx+1]
0x10049b80d  or      r14, 0FFFFFFFFFFFFFFFFh
0x10049b811  lea     ebx, [r13+1]
0x10049b815  mov     edx, 0FFFFFFF6h
0x10049b81a  mov     dword ptr [rsp+360h+var_310+4], r13d
0x10049b81f  lea     eax, [r13-1]
0x10049b823  lea     r15, [rax+rax*8]
0x10049b827  shl     r15, 5
0x10049b82b  add     r15, [rbp+260h+var_2D8]
0x10049b82f  xor     ecx, ecx
0x10049b831  cmp     [r15], cx
0x10049b835  jz      short loc_10049B859
0x10049b837  test    dword ptr [r12+34h], 100h
0x10049b840  jnz     short loc_10049B859
0x10049b842  movzx   eax, word ptr [r15]
0x10049b846  cmp     eax, r13d
0x10049b849  jz      short loc_10049B859
0x10049b84b  cmp     [r12+750h], rcx
0x10049b853  jnz     loc_10049B9F7
0x10049b859  lea     r12, [r15+4]
0x10049b85d  cmp     [r12], ecx
0x10049b861  jnz     short loc_10049B893
0x10049b863  cmp     byte ptr [r15+2], 27h ; '''
0x10049b868  jnz     short loc_10049B875
0x10049b86a  mov     byte ptr [r15+2], 2Fh ; '/'
0x10049b86f  mov     [r12], ebx
0x10049b873  jmp     short loc_10049B893
0x10049b875  cmp     byte ptr [r15+2], 25h ; '%'
0x10049b87a  jnz     short loc_10049B883
0x10049b87c  mov     byte ptr [r15+2], 2Dh ; '-'
0x10049b881  jmp     short loc_10049B86F
0x10049b883  cmp     [r15+8], ecx
0x10049b887  jnz     short loc_10049B893
0x10049b889  cmp     [r15+0Ch], ecx
0x10049b88d  jle     short loc_10049B893
0x10049b88f  mov     [r15+8], edx
0x10049b893  mov     dword ptr [rsp+360h+var_340], ebx; int
0x10049b897  mov     r9, r15; void *
0x10049b89a  mov     r8d, 5; int
0x10049b8a0  mov     edx, r13d; int
0x10049b8a3  mov     rcx, rsi; struct tagDBC *
0x10049b8a6  call    ?BCP_setcolfmt@@YAFPEAUtagDBC@@HHPEAXH@Z; BCP_setcolfmt(tagDBC *,int,int,void *,int)
0x10049b8ab  movzx   edi, ax
0x10049b8ae  xor     eax, eax
0x10049b8b0  cmp     ax, di
0x10049b8b3  jz      loc_10049C880
0x10049b8b9  mov     dword ptr [rsp+360h+var_340], 4; int
0x10049b8c1  mov     r9, r12; void *
0x10049b8c4  mov     r8d, ebx; int
0x10049b8c7  mov     edx, r13d; int
0x10049b8ca  mov     rcx, rsi; struct tagDBC *
0x10049b8cd  call    ?BCP_setcolfmt@@YAFPEAUtagDBC@@HHPEAXH@Z; BCP_setcolfmt(tagDBC *,int,int,void *,int)
0x10049b8d2  movzx   edi, ax
0x10049b8d5  xor     r12d, r12d
0x10049b8d8  cmp     r12w, ax
0x10049b8dc  jz      loc_10049BA4D
0x10049b8e2  mov     eax, [r15+0Ch]
0x10049b8e6  mov     dword ptr [rsp+360h+var_340], eax; int
0x10049b8ea  mov     r9, [r15+10h]; void *
0x10049b8ee  lea     r8d, [r12+4]; int
0x10049b8f3  mov     edx, r13d; int
0x10049b8f6  mov     rcx, rsi; struct tagDBC *
0x10049b8f9  call    ?BCP_setcolfmt@@YAFPEAUtagDBC@@HHPEAXH@Z; BCP_setcolfmt(tagDBC *,int,int,void *,int)
0x10049b8fe  movzx   edi, ax
0x10049b901  cmp     r12w, ax
0x10049b905  jz      loc_10049BA4D
0x10049b90b  lea     r9, [r15+8]; void *
0x10049b90f  mov     dword ptr [rsp+360h+var_340], 4; int
0x10049b917  lea     r8d, [r12+3]; int
0x10049b91c  mov     edx, r13d; int
0x10049b91f  mov     rcx, rsi; struct tagDBC *
0x10049b922  call    ?BCP_setcolfmt@@YAFPEAUtagDBC@@HHPEAXH@Z; BCP_setcolfmt(tagDBC *,int,int,void *,int)
0x10049b927  movzx   edi, ax
0x10049b92a  cmp     r12w, ax
0x10049b92e  jz      loc_10049BA4D
0x10049b934  lea     r9, [r15+2]; void *
0x10049b938  mov     dword ptr [rsp+360h+var_340], 1; int
0x10049b940  lea     r8d, [r12+1]; int
0x10049b945  mov     edx, r13d; int
0x10049b948  mov     rcx, rsi; struct tagDBC *
0x10049b94b  call    ?BCP_setcolfmt@@YAFPEAUtagDBC@@HHPEAXH@Z; BCP_setcolfmt(tagDBC *,int,int,void *,int)
0x10049b950  movzx   edi, ax
0x10049b953  cmp     r12w, ax
0x10049b957  jz      loc_10049BA4D
0x10049b95d  mov     eax, r12d
0x10049b960  lea     rdx, [r15+18h]; lpWideCharStr
0x10049b964  cmp     [rdx], r12w
0x10049b968  jz      short loc_10049B9B4
0x10049b96a  mov     r8, r14
0x10049b96d  inc     r8; cchWideChar
  ... truncated ...
```
