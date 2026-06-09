# CRPCSQLSender::SendParamList(int)

- ea: `0x1004cc170`
- end: `0x1004cd589`
- name: `?SendParamList@CRPCSQLSender@@UEAAJH@Z`
- size: `5145`
- prototype: `__int64 __fastcall(CRPCSQLSender *__hidden this, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x100405948`
- `0x100406748`
- `0x10045b6cc`
- `0x10045be64`
- `0x1004cc170`
- `0x1004cd590`
- `0x1004cdae0`
- `0x1004cdbfc`
- `0x100520370`
- `0x100523d18`
- `0x10053f614`
- `0x100546a24`
- `0x100546a7c`
- `0x100548210`
- `0x100548310`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetACP` at `0x1004cc9e8`
- `KERNEL32!GetACP` at `0x1004cca25`
- `KERNEL32!GetACP` at `0x1004cca5d`
- `KERNEL32!GetACP` at `0x1004ccbaf`
- `KERNEL32!GetACP` at `0x1004ccbec`
- `KERNEL32!GetACP` at `0x1004ccc29`
- `KERNEL32!GetACP` at `0x1004ccd9b`
- `KERNEL32!GetACP` at `0x1004ccddb`
- `KERNEL32!GetACP` at `0x1004cce10`
- `KERNEL32!GetACP` at `0x1004cc9e8`
- `KERNEL32!GetACP` at `0x1004cca25`
- `KERNEL32!GetACP` at `0x1004cca5d`
- `KERNEL32!GetACP` at `0x1004ccbaf`
- `KERNEL32!GetACP` at `0x1004ccbec`
- `KERNEL32!GetACP` at `0x1004ccc29`
- `KERNEL32!GetACP` at `0x1004ccd9b`
- `KERNEL32!GetACP` at `0x1004ccddb`
- `KERNEL32!GetACP` at `0x1004cce10`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004cc5d7`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004cc626`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004cc708`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004cc961`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004ccfed`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004cd092`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004cc5d7`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004cc626`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004cc708`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004cc961`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004ccfed`
- `api-ms-win-crt-convert-l1-1-0!_ultow_s` at `0x1004cd092`

## string_xrefs

- `0x1004cd139`: ` READONLY`

## pseudocode

```c
__int64 __fastcall CRPCSQLSender::SendParamList(CRPCSQLSender *this, int a2)
{
  __int64 v2; // rax
  CRPCSQLStream *v3; // r13
  CRPCSQLSender *v5; // r14
  errno_t v6; // eax
  __int64 v7; // r9
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r15
  const unsigned __int16 *v11; // rdx
  int v12; // r9d
  unsigned int v13; // r8d
  __int16 v14; // cx
  unsigned int v15; // eax
  unsigned __int64 v16; // rdi
  __int16 *v17; // rax
  __int16 v18; // cx
  __int64 v19; // rcx
  __int64 v20; // r15
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rdi
  unsigned __int8 v26; // bl
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r13
  __int64 v30; // r8
  const unsigned __int16 *v31; // r12
  unsigned int v32; // r8d
  unsigned int v33; // r8d
  __int64 v34; // rdi
  unsigned int v35; // ecx
  __int64 v36; // rdi
  unsigned int v37; // r8d
  unsigned int v38; // ecx
  __int64 v39; // r8
  unsigned int v40; // r8d
  __int64 v41; // rdi
  char v42; // al
  unsigned __int64 v43; // rbx
  unsigned __int8 v44; // cl
  int v45; // eax
  __int64 *v46; // rax
  unsigned __int8 v47; // cl
  unsigned __int64 VectorElementSizeInBytes; // r9
  __int64 *v49; // rcx
  __int16 *v50; // rbx
  __int64 v51; // rax
  unsigned int v52; // r8d
  unsigned int v53; // ecx
  __int64 v54; // r8
  _BYTE *v55; // r12
  UINT v56; // ebx
  unsigned int v57; // edi
  unsigned __int16 *v58; // rax
  UINT v59; // ebx
  unsigned int v60; // edi
  unsigned __int16 *v61; // rax
  UINT v62; // ebx
  unsigned int v63; // edi
  unsigned __int16 *v64; // rax
  unsigned __int16 *v65; // rcx
  __int64 v66; // rdx
  unsigned __int16 v67; // ax
  unsigned __int16 *v68; // rax
  __int64 v69; // r8
  _BYTE *v70; // r13
  UINT v71; // ebx
  unsigned int v72; // edi
  unsigned __int16 *v73; // rax
  UINT v74; // ebx
  unsigned int v75; // edi
  unsigned __int16 *v76; // rax
  UINT v77; // ebx
  unsigned int v78; // edi
  unsigned __int16 *v79; // rax
  unsigned __int16 *v80; // rcx
  __int64 v81; // rdx
  signed __int64 v82; // r12
  unsigned __int16 v83; // ax
  unsigned __int16 *v84; // rax
  __int64 v85; // r8
  UINT ACP; // ebx
  unsigned int v87; // edi
  unsigned __int16 *NameFromPool; // rax
  UINT v89; // ebx
  unsigned int v90; // edi
  unsigned __int16 *v91; // rax
  UINT v92; // ebx
  unsigned int v93; // edi
  unsigned __int16 *v94; // rax
  unsigned __int16 *v95; // rcx
  __int64 v96; // rdx
  unsigned __int16 v97; // ax
  unsigned __int16 *v98; // rax
  __int64 v99; // r8
  unsigned int v100; // r8d
  unsigned int v101; // r8d
  __int64 v102; // rcx
  __int64 v103; // r8
  unsigned int v104; // r8d
  __int64 v105; // r8
  __int64 v106; // rdx
  unsigned __int16 v107; // dx
  __int64 v108; // rdx
  unsigned __int16 v109; // dx
  _QWORD *v110; // rdx
  CRPCRequest *v111; // rcx
  int v113; // [rsp+40h] [rbp-C0h]
  unsigned int v114; // [rsp+44h] [rbp-BCh]
  int v115; // [rsp+48h] [rbp-B8h]
  __int64 v116; // [rsp+50h] [rbp-B0h]
  int v117[2]; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v118; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v119; // [rsp+68h] [rbp-98h]
  CRPCSQLSender *v120; // [rsp+70h] [rbp-90h]
  char v121[24]; // [rsp+80h] [rbp-80h] BYREF
  char v122[24]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v123; // [rsp+B0h] [rbp-50h]
  __int64 v124; // [rsp+B8h] [rbp-48h]
  int v125; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v126; // [rsp+C4h] [rbp-3Ch]
  __int16 v127; // [rsp+C6h] [rbp-3Ah] BYREF
  wchar_t v128[8]; // [rsp+C8h] [rbp-38h] BYREF
  int v129; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v130; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t v131[11]; // [rsp+E2h] [rbp-1Eh] BYREF
  unsigned __int16 v132; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t v133[11]; // [rsp+FAh] [rbp-6h] BYREF
  unsigned __int16 v134; // [rsp+110h] [rbp+10h] BYREF
  wchar_t v135[11]; // [rsp+112h] [rbp+12h] BYREF
  unsigned __int16 v136; // [rsp+128h] [rbp+28h] BYREF
  wchar_t Buffer[19]; // [rsp+12Ah] [rbp+2Ah] BYREF
  unsigned __int16 v138[904]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v139[528]; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v140[528]; // [rsp+A70h] [rbp+970h] BYREF
  _BYTE v141[528]; // [rsp+C80h] [rbp+B80h] BYREF
  _BYTE v142[528]; // [rsp+E90h] [rbp+D90h] BYREF
  _BYTE v143[528]; // [rsp+10A0h] [rbp+FA0h] BYREF
  _BYTE v144[528]; // [rsp+12B0h] [rbp+11B0h] BYREF
  _BYTE v145[528]; // [rsp+14C0h] [rbp+13C0h] BYREF
  _BYTE v146[528]; // [rsp+16D0h] [rbp+15D0h] BYREF
  _BYTE v147[528]; // [rsp+18E0h] [rbp+17E0h] BYREF

  v2 = *((_QWORD *)this + 1);
  v3 = (CRPCSQLSender *)((char *)this + 96);
  v120 = this;
  v5 = this;
  v6 = CRPCSQLStream::OnBeginSendParamList(
         (CRPCSQLSender *)((char *)this + 96),
         (CRPCSQLSender *)((char *)this + 40),
         *(_DWORD *)(v2 + 796));
  v8 = v6;
  if ( v6 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v9 = 7369737;
      goto LABEL_288;
    }
    goto LABEL_289;
  }
  _mm_lfence();
  if ( !*(_DWORD *)(*((_QWORD *)v5 + 1) + 796LL) )
    return v8;
  _mm_lfence();
  v10 = *((_QWORD *)v5 + 1);
  v11 = (const unsigned __int16 *)&v125 + 1;
  v8 = 0;
  v125 = 0x400000;
  v123 = 0;
  v124 = 0;
  v12 = 1;
  v13 = 6;
  v115 = 1;
  v126 = 80;
  v14 = 48;
  v116 = v10;
  v127 = 48;
  v15 = *(_DWORD *)(v10 + 796);
  v118 = (const unsigned __int16 *)&v125 + 1;
  v113 = 6;
  if ( v15 > 0x834 && (*(_BYTE *)(v10 + 812) & 1) == 0 && !a2 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 7396361);
    PostSQLErrorEx(*((struct tagOBJBASE **)v5 + 1), 0x9CB2u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
LABEL_11:
    v8 = -2147024809;
    goto LABEL_289;
  }
  v16 = 1;
  v114 = 1;
  if ( !v15 )
  {
LABEL_291:
    if ( *((_BYTE *)v5 + 128) && !*((_BYTE *)v5 + 129) && *((_DWORD *)v5 + 34) )
    {
      _mm_lfence();
      *(_DWORD *)(**((_QWORD **)v5 + 13) + *((_QWORD *)v5 + 18)) = *((_DWORD *)v5 + 33) - *((_DWORD *)v5 + 34);
    }
    *((_WORD *)v5 + 64) = 0;
    *(_QWORD *)((char *)v5 + 132) = 0;
    *((_QWORD *)v5 + 18) = 0;
    return v8;
  }
  while ( 1 )
  {
    if ( v16 > *(_QWORD *)(*(_QWORD *)(v10 + 456) + 8LL) )
      goto LABEL_291;
    v17 = &v127;
    while ( v14 == 57 )
    {
      *v17-- = 48;
      v14 = *v17;
    }
    v18 = v14 + 1;
    *v17 = v18;
    if ( v18 == 81 )
    {
      --v11;
      *v17 = 49;
      v13 += 2;
      v118 = v11;
      v113 = v13;
      *((_DWORD *)v17 - 1) = 5242944;
    }
    v19 = *(_QWORD *)(v10 + 456);
    v119 = v16 - 1;
    v20 = v19 + *(_QWORD *)(v19 + 24) * (v16 - 1);
    if ( *(_WORD *)(v20 + 48) )
      break;
LABEL_211:
    v10 = v116;
    v16 = v114 + 1;
    v114 = v16;
    if ( (unsigned int)v16 > *(_DWORD *)(v116 + 796) )
      goto LABEL_291;
    v14 = v127;
  }
  if ( v12 )
  {
    v115 = 0;
  }
  else
  {
    v6 = CRPCSQLStream::SendParamListPart(v3, L",", 2u);
    v8 = v6;
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_289;
      v9 = 7443465;
      goto LABEL_288;
    }
    v11 = v118;
    v13 = v113;
  }
  v6 = CRPCSQLStream::SendParamListPart(v3, v11, v13);
  v8 = v6;
  if ( v6 >= 0 )
  {
    _mm_lfence();
    v6 = CRPCSQLStream::SendParamListPart(v3, L" ", 2u);
    v8 = v6;
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v9 = 7455753;
        goto LABEL_288;
      }
      goto LABEL_289;
    }
    _mm_lfence();
    LOBYTE(v22) = Sql2SrvExtend(
                    (struct paraminfoTag *)(v20 + 32),
                    *(struct tagDBC **)(*((_QWORD *)v5 + 1) + 112LL),
                    v117);
    v23 = *(_QWORD *)(v116 + 752);
    if ( v23 )
    {
      if ( v16 <= *(_QWORD *)(v23 + 8) )
      {
        v21 = v23 + *(_QWORD *)(v23 + 24) * (v16 - 1) + 32;
        if ( v21 )
        {
          if ( *(_WORD *)(v20 + 48) == 19 )
          {
            if ( *(_QWORD *)(v21 + 32) )
              goto LABEL_36;
            v24 = *(_QWORD **)(v21 + 56);
            if ( v24 && *v24 == -1 )
            {
              *(_QWORD *)(v20 + 32) = 0;
              *(_WORD *)(v20 + 48) = 12;
              LOBYTE(v22) = -89;
              goto LABEL_36;
            }
          }
          if ( !*(_QWORD *)(v21 + 32) && !*(_QWORD *)(v21 + 56) )
            goto LABEL_11;
        }
      }
    }
LABEL_36:
    if ( *(_WORD *)(v20 + 48) == 11 && *(_QWORD *)(v20 + 32) <= 0x10u )
    {
      v25 = *(_QWORD *)(v20 + 32);
      v26 = 58;
    }
    else
    {
      v25 = *(_QWORD *)(v20 + 32);
      switch ( (_BYTE)v22 )
      {
        case 'm':
          v26 = 62;
          if ( v25 == 4 )
            v26 = 59;
          break;
        case 'n':
          if ( v25 == 4 )
            v26 = 122;
          else
            v26 = 60;
          break;
        case 'o':
          if ( v25 == 4 )
            v26 = 58;
          else
            v26 = 61;
          break;
        default:
          v26 = v22;
          if ( (_BYTE)v22 == 38 )
          {
            if ( v25 == 1 )
            {
              v26 = 48;
            }
            else if ( v25 == 2 )
            {
              v26 = 52;
            }
            else
            {
              v26 = 56;
              if ( v25 != 4 )
                v26 = 127;
            }
          }
          break;
      }
    }
    LOBYTE(v21) = v26;
    v27 = ServerTypeInfo(v121, v21, v22);
    LOBYTE(v28) = v26;
    v29 = *(_QWORD *)(v27 + 8);
    v31 = *(const unsigned __int16 **)ServerTypeInfo(v122, v28, v30);
    if ( v26 <= 0xADu )
    {
      switch ( v26 )
      {
        case 0xADu:
          goto LABEL_67;
        case 0x29u:
        case 0x2Au:
        case 0x2Bu:
          v37 = 2 * v29;
          v3 = (CRPCSQLSender *)((char *)v5 + 96);
          v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v31, v37);
          v8 = v6;
          if ( v6 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_289;
            v9 = 7834633;
          }
          else
          {
            _mm_lfence();
            v8 = 0;
            if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v5 + 1) + 112LL) + 64LL) + 440LL)
              || (_mm_lfence(), (*(_BYTE *)(*((_QWORD *)v5 + 1) + 4232LL) & 2) == 0) )
            {
LABEL_203:
              if ( (*(_BYTE *)(v20 + 54) & 6) != 0 )
              {
                v6 = CRPCSQLStream::SendParamListPart(v3, L" OUTPUT", 0xEu);
                v8 = v6;
                if ( v6 < 0 )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_289;
                  v9 = 7985161;
                  break;
                }
              }
              else
              {
                if ( *(_WORD *)(v20 + 48) != 16 )
                {
LABEL_210:
                  v11 = v118;
                  v13 = v113;
                  v12 = v115;
                  goto LABEL_211;
                }
                v6 = CRPCSQLStream::SendParamListPart(v3, L" READONLY", 0x12u);
                v8 = v6;
                if ( v6 < 0 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v9 = 7990281;
                    break;
                  }
                  goto LABEL_289;
                }
              }
              v8 = 0;
              goto LABEL_210;
            }
            _mm_lfence();
            v38 = *(__int16 *)(v20 + 50);
            v129 = 0;
            *(_OWORD *)v128 = 0;
            v128[0] = 40;
            v6 = _ultow_s(v38, &v128[1], 5u, 10);
            v8 = v6;
            if ( v6 >= 0 )
            {
              _mm_lfence();
              v39 = 1;
              if ( v128[1] )
              {
                do
                  ++v39;
                while ( v128[v39] );
              }
              v128[v39] = 41;
              v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v128, 2 * (int)v39 + 2);
              v8 = v6;
              if ( v6 < 0 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_289;
                v9 = 7852041;
                break;
              }
              goto LABEL_202;
            }
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_289;
            v9 = 7843849;
          }
          break;
        case 0x6Au:
        case 0x6Cu:
          v33 = 2 * v29;
          v3 = (CRPCSQLSender *)((char *)v5 + 96);
          v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v31, v33);
          v8 = v6;
          if ( v6 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_289;
            v9 = 7555081;
          }
          else
          {
            _mm_lfence();
            v136 = 40;
            v6 = _ultow_s(*(_DWORD *)(v20 + 32), Buffer, 5u, 10);
            v8 = v6;
            if ( v6 < 0 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_289;
              v9 = 7562249;
            }
            else
            {
              _mm_lfence();
              v34 = 1;
              if ( Buffer[0] )
              {
                do
                  ++v34;
                while ( Buffer[v34 - 1] );
              }
              v35 = *(__int16 *)(v20 + 50);
              Buffer[v34 - 1] = 44;
              v36 = v34 + 1;
              v6 = _ultow_s(v35, &Buffer[v36 - 1], 5u, 10);
              v8 = v6;
              if ( v6 >= 0 )
              {
                _mm_lfence();
                for ( ; Buffer[v36 - 1]; ++v36 )
                  ;
                Buffer[v36 - 1] = 41;
                v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), &v136, 2 * (int)v36 + 2);
                v8 = v6;
                if ( v6 < 0 )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_289;
                  v9 = 7579657;
                  break;
                }
LABEL_202:
                v8 = 0;
                goto LABEL_203;
              }
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_289;
              v9 = 7573513;
            }
          }
          break;
        case 0xA5u:
        case 0xA7u:
LABEL_67:
          if ( ((v26 + 91) & 0xFD) != 0 || v25 && !v117[0] )
          {
            v104 = 2 * v29;
            v3 = (CRPCSQLSender *)((char *)v5 + 96);
            v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v31, v104);
            v8 = v6;
            if ( v6 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                v9 = 7606281;
                break;
              }
              goto LABEL_289;
            }
            v134 = 40;
            v6 = _ultow_s(*(_DWORD *)(v20 + 32), v135, 5u, 10);
            v8 = v6;
            if ( v6 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                v9 = 7615497;
                break;
              }
              goto LABEL_289;
            }
            _mm_lfence();
            v105 = 1;
            if ( v135[0] )
            {
              do
                ++v105;
              while ( v135[v105 - 1] );
            }
            v135[v105 - 1] = 41;
            v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), &v134, 2 * (int)v105 + 2);
            v8 = v6;
            if ( v6 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                v9 = 7624713;
                break;
              }
              goto LABEL_289;
            }
          }
          else
          {
            v32 = 2 * v29;
            v3 = (CRPCSQLSender *)((char *)v5 + 96);
            v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v31, v32);
            v8 = v6;
            if ( v6 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                v9 = 7592969;
                break;
              }
              goto LABEL_289;
            }
            _mm_lfence();
            v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), L"(max)", 0xAu);
            v8 = v6;
            if ( v6 < 0 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_289;
              v9 = 7596041;
              break;
            }
          }
          goto LABEL_202;
        default:
          goto LABEL_100;
      }
LABEL_288:
      _mm_lfence();
      bidTraceHR(0, v9, (unsigned int)v6, v7);
      goto LABEL_289;
    }
    switch ( v26 )
    {
      case 0xAFu:
        goto LABEL_67;
      case 0xE7u:
      case 0xEFu:
        if ( v26 == 0xE7 && (!v25 || v117[0]) )
        {
          v100 = 2 * v29;
          v3 = (CRPCSQLSender *)((char *)v5 + 96);
          v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v31, v100);
          v8 = v6;
          if ( v6 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v9 = 7510025;
              goto LABEL_288;
            }
            goto LABEL_289;
          }
          _mm_lfence();
          v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), L"(max)", 0xAu);
          v8 = v6;
          if ( v6 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_289;
            v9 = 7513097;
            goto LABEL_288;
          }
        }
        else
        {
          v101 = 2 * v29;
          v3 = (CRPCSQLSender *)((char *)v5 + 96);
          v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v31, v101);
          v8 = v6;
          if ( v6 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v9 = 7523337;
              goto LABEL_288;
            }
            goto LABEL_289;
          }
          _mm_lfence();
          v102 = *(_QWORD *)(v20 + 32) >> 1;
          v132 = 40;
          v6 = _ultow_s(v102, v133, 5u, 10);
          v8 = v6;
          if ( v6 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v9 = 7532553;
              goto LABEL_288;
            }
            goto LABEL_289;
          }
          v103 = 1;
          if ( v133[0] )
          {
            do
              ++v103;
            while ( v133[v103 - 1] );
          }
          v133[v103 - 1] = 41;
          v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), &v132, 2 * (int)v103 + 2);
          v8 = v6;
          if ( v6 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_289;
            v9 = 7541769;
            goto LABEL_288;
          }
        }
        goto LABEL_202;
      case 0xF0u:
        if ( *(_BYTE *)(v20 + 67) )
        {
          _mm_lfence();
          ACP = GetACP();
          v87 = *(unsigned __int8 *)(v20 + 65);
          NameFromPool = GetNameFromPool(*(struct ext_buffer **)(v116 + 440), *(_DWORD *)(v20 + 72));
          QuotedIdentifier<unsigned short>::quote(NameFromPool, v87, v147, 259, ACP);
          v89 = GetACP();
          v90 = *(unsigned __int8 *)(v20 + 66);
          v91 = GetNameFromPool(*(struct ext_buffer **)(v116 + 440), *(_DWORD *)(v20 + 76));
          QuotedIdentifier<unsigned short>::quote(v91, v90, v144, 259, v89);
          v92 = GetACP();
          v93 = *(unsigned __int8 *)(v20 + 67);
          v94 = GetNameFromPool(*(struct ext_buffer **)(v116 + 440), *(_DWORD *)(v20 + 80));
          QuotedIdentifier<unsigned short>::quote(v94, v93, v141, 259, v92);
          v95 = v138;
          v96 = 902;
          if ( *(_BYTE *)(v20 + 65) )
          {
            StringCchPrintfW(v138, 0x386u, L"%s.%s.%s", v147, v144, v141);
          }
          else if ( *(_BYTE *)(v20 + 66) )
          {
            StringCchPrintfW(v138, 0x386u, L"%s.%s", v144, v141);
          }
          else
          {
            do
            {
              if ( v96 == -2147482744 )
                break;
              v97 = v95[1432];
              if ( !v97 )
                break;
              *v95++ = v97;
              --v96;
            }
            while ( v96 );
            v5 = v120;
            v98 = v95 - 1;
            if ( v96 )
              v98 = v95;
            *v98 = 0;
          }
          v99 = -1;
          do
            ++v99;
          while ( v138[v99] );
          v3 = (CRPCSQLSender *)((char *)v5 + 96);
          v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v138, 2 * (int)v99);
          v8 = v6;
          if ( v6 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_289;
            v9 = 7690249;
            goto LABEL_288;
          }
          goto LABEL_202;
        }
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 7637001);
        v109 = -25247;
        goto LABEL_262;
      case 0xF1u:
        v70 = (_BYTE *)(v20 + 66);
        if ( !*(_BYTE *)(v20 + 65) && !*v70 || *(_WORD *)(v20 + 70) )
        {
          _mm_lfence();
          v71 = GetACP();
          v72 = *(unsigned __int8 *)(v20 + 65);
          v73 = GetNameFromPool(*(struct ext_buffer **)(v116 + 440), *(_DWORD *)(v20 + 72));
          QuotedIdentifier<unsigned short>::quote(v73, v72, v146, 259, v71);
          v74 = GetACP();
          v75 = (unsigned __int8)*v70;
          v76 = GetNameFromPool(*(struct ext_buffer **)(v116 + 440), *(_DWORD *)(v20 + 76));
          QuotedIdentifier<unsigned short>::quote(v76, v75, v143, 259, v74);
          v77 = GetACP();
          v78 = *(unsigned __int16 *)(v20 + 70);
          v79 = GetNameFromPool(*(struct ext_buffer **)(v116 + 440), *(_DWORD *)(v20 + 88));
          QuotedIdentifier<unsigned short>::quote(v79, v78, v140, 259, v77);
          v80 = v138;
          v81 = 902;
          if ( *(_BYTE *)(v20 + 65) )
          {
            StringCchPrintfW(v138, 0x386u, L"%s(%s.%s.%s)", v31, v146, v143, v140);
          }
          else if ( *v70 )
          {
            StringCchPrintfW(v138, 0x386u, L"%s(%s.%s)", v31, v143, v140);
          }
          else if ( *(_DWORD *)(v20 + 88) )
          {
            StringCchPrintfW(v138, 0x386u, L"%s(%s)", v31, v140);
          }
          else
          {
            v82 = (char *)v31 - (char *)v138;
            do
            {
              if ( v81 == -2147482744 )
                break;
              v83 = *(unsigned __int16 *)((char *)v80 + v82);
              if ( !v83 )
                break;
              *v80++ = v83;
              --v81;
            }
            while ( v81 );
            v5 = v120;
            v84 = v80 - 1;
            if ( v81 )
              v84 = v80;
            *v84 = 0;
          }
          v85 = -1;
          do
            ++v85;
          while ( v138[v85] );
          v3 = (CRPCSQLSender *)((char *)v5 + 96);
          v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v138, 2 * (int)v85);
          v8 = v6;
          if ( v6 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_289;
            v9 = 7765001;
            goto LABEL_288;
          }
          goto LABEL_202;
        }
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_261;
        v108 = 7701513;
        break;
      case 0xF3u:
        v55 = (_BYTE *)(v20 + 66);
        if ( !*(_BYTE *)(v20 + 65) && !*v55 || *(_BYTE *)(v20 + 92) )
        {
          _mm_lfence();
          v56 = GetACP();
          v57 = *(unsigned __int8 *)(v20 + 65);
          v58 = GetNameFromPool(*(struct ext_buffer **)(v116 + 440), *(_DWORD *)(v20 + 72));
          QuotedIdentifier<unsigned short>::quote(v58, v57, v145, 259, v56);
          v59 = GetACP();
          v60 = (unsigned __int8)*v55;
          v61 = GetNameFromPool(*(struct ext_buffer **)(v116 + 440), *(_DWORD *)(v20 + 76));
          QuotedIdentifier<unsigned short>::quote(v61, v60, v142, 259, v59);
          v62 = GetACP();
          v63 = *(unsigned __int8 *)(v20 + 92);
          v64 = GetNameFromPool(*(struct ext_buffer **)(v116 + 440), *(_DWORD *)(v20 + 96));
          QuotedIdentifier<unsigned short>::quote(v64, v63, v139, 259, v62);
          v65 = v138;
          v66 = 902;
          if ( *(_BYTE *)(v20 + 65) )
          {
            StringCchPrintfW(v138, 0x386u, L"%s.%s.%s", v145, v142, v139);
          }
          else if ( *v55 )
          {
            StringCchPrintfW(v138, 0x386u, L"%s.%s", v142, v139);
          }
          else
          {
            do
            {
              if ( v66 == -2147482744 )
                break;
              v67 = v65[904];
              if ( !v67 )
                break;
              *v65++ = v67;
              --v66;
            }
            while ( v66 );
            v5 = v120;
            v68 = v65 - 1;
            if ( v66 )
              v68 = v65;
            *v68 = 0;
          }
          v69 = -1;
          do
            ++v69;
          while ( v138[v69] );
          v3 = (CRPCSQLSender *)((char *)v5 + 96);
          v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v138, 2 * (int)v69);
          v8 = v6;
          if ( v6 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_289;
            v9 = 7825417;
            goto LABEL_288;
          }
          goto LABEL_202;
        }
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_261;
        v108 = 7776265;
        break;
      case 0xF5u:
        v41 = *(_QWORD *)(v116 + 752);
        v42 = *(_BYTE *)(v20 + 54) & 6;
        v43 = *(_QWORD *)(v41 + 24) * v119;
        v119 = v43;
        if ( v42 == 4 )
        {
          _mm_lfence();
          v44 = *(_BYTE *)(v20 + 50);
          *(_BYTE *)(v20 + 56) = v44;
          v45 = (unsigned __int16)(*(_WORD *)(v20 + 32) - 16) / GetVectorElementSizeInBytes(v44);
          goto LABEL_119;
        }
        v46 = *(__int64 **)(v43 + v41 + 88);
        if ( v46 && (*v46 == -2 || *v46 < -100) )
        {
          _mm_lfence();
          v47 = *(_BYTE *)(v20 + 50);
          *(_BYTE *)(v20 + 56) = v47;
          VectorElementSizeInBytes = GetVectorElementSizeInBytes(v47);
          v49 = *(__int64 **)(v43 + v41 + 88);
          if ( *v49 >= -100
            || (unsigned __int16)((-116 - *v49) / VectorElementSizeInBytes) == (unsigned __int16)((unsigned __int16)(*(_WORD *)(v20 + 32) - 16)
                                                                                                / (int)VectorElementSizeInBytes) )
          {
            LOWORD(v45) = (unsigned __int16)(*(_WORD *)(v20 + 32) - 16) / (int)VectorElementSizeInBytes;
            goto LABEL_119;
          }
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_232;
          if ( off_1005E7230[0] && bidID != -1 )
            ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
              bidID,
              0,
              7896064,
              off_1005E7230[0],
              0);
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_232;
          v106 = 7897097;
        }
        else
        {
          v50 = *(__int16 **)(v43 + v41 + 64);
          if ( !v50 && v46 && *v46 != -1 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_1005E7238[0] && bidID != -1 )
                ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
                  bidID,
                  0,
                  7911424,
                  off_1005E7238[0],
                  0);
              if ( (bidGblFlags & 2) != 0 )
                bidTraceMark(0, 7912457);
            }
            v107 = -25375;
            goto LABEL_233;
          }
          if ( *((_QWORD *)v50 + 1) )
            v51 = GetVectorElementSizeInBytes(*((_BYTE *)v50 + 4)) * *v50 + 16LL;
          else
            v51 = 16;
          if ( *(_QWORD *)(v119 + v41 + 40) == v51 )
          {
            *(_BYTE *)(v20 + 56) = *((_BYTE *)v50 + 4);
            LOWORD(v45) = *v50;
LABEL_119:
            *(_WORD *)(v20 + 58) = v45;
            if ( (unsigned __int16)(v45 - 1) > 0x7CDu )
            {
              if ( (bidGblFlags & 2) != 0 )
                bidTraceMark(0, 7939081);
              v107 = -25179;
            }
            else
            {
              if ( !*(_BYTE *)(v20 + 56) )
              {
                v52 = 2 * v29;
                v3 = (CRPCSQLSender *)((char *)v5 + 96);
                v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v31, v52);
                v8 = v6;
                if ( v6 < 0 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v9 = 7952393;
                    goto LABEL_288;
                  }
                  goto LABEL_289;
                }
                _mm_lfence();
                v53 = *(unsigned __int16 *)(v20 + 58);
                v130 = 40;
                v6 = _ultow_s(v53, v131, 5u, 10);
                v8 = v6;
                if ( v6 < 0 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v9 = 7961609;
                    goto LABEL_288;
                  }
                  goto LABEL_289;
                }
                v54 = 1;
                if ( v131[0] )
                {
                  do
                    ++v54;
                  while ( v131[v54 - 1] );
                }
                v131[v54 - 1] = 41;
                v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), &v130, 2 * (int)v54 + 2);
                v8 = v6;
                if ( v6 < 0 )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_289;
                  v9 = 7970825;
                  goto LABEL_288;
                }
                goto LABEL_202;
              }
              if ( (bidGblFlags & 2) != 0 )
                bidTraceMark(0, 7944201);
              v107 = -25178;
            }
            goto LABEL_233;
          }
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_232;
          if ( off_1005E7240[0] && bidID != -1 )
            ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
              bidID,
              0,
              7926784,
              off_1005E7240[0],
              0);
          if ( (bidGblFlags & 2) == 0 )
          {
LABEL_232:
            v107 = -25180;
LABEL_233:
            PostSQLErrorEx(*((struct tagOBJBASE **)v5 + 1), v107, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
LABEL_234:
            v8 = -2147467259;
            goto LABEL_289;
          }
          v106 = 7927817;
        }
        bidTraceMark(0, v106);
        goto LABEL_232;
      default:
LABEL_100:
        v40 = 2 * v29;
        v3 = (CRPCSQLSender *)((char *)v5 + 96);
        v6 = CRPCSQLStream::SendParamListPart((CRPCSQLSender *)((char *)v5 + 96), v31, v40);
        v8 = v6;
        if ( v6 < 0 )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_289;
          v9 = 7979017;
          goto LABEL_288;
        }
        goto LABEL_202;
    }
    bidTraceMark(0, v108);
LABEL_261:
    v109 = -25062;
LABEL_262:
    PostSQLErrorEx(*((struct tagOBJBASE **)v5 + 1), v109, 0, 0xFFFFFFFFFFFFFFFEuLL, v114);
    goto LABEL_234;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v9 = 7452681;
    goto LABEL_288;
  }
LABEL_289:
  _mm_lfence();
  v110 = (_QWORD *)*((_QWORD *)v5 + 1);
  v111 = (CRPCRequest *)v110[140];
  if ( v111 )
    CRPCRequest::RemoveAllCommands(v111, v110);
  return v8;
}

```

## disassembly

```asm
0x1004cc170  mov     rax, rsp
0x1004cc173  mov     [rax+10h], rbx
0x1004cc177  mov     [rax+18h], rsi
0x1004cc17b  mov     [rax+20h], rdi
0x1004cc17f  push    rbp
0x1004cc180  push    r12
0x1004cc182  push    r13
0x1004cc184  push    r14
0x1004cc186  push    r15
0x1004cc188  lea     rbp, [rax-1A28h]
0x1004cc18f  mov     eax, 1B00h
0x1004cc194  call    _alloca_probe
0x1004cc199  sub     rsp, rax
0x1004cc19c  mov     rax, cs:__security_cookie
0x1004cc1a3  xor     rax, rsp
0x1004cc1a6  mov     [rbp+1A20h+var_30], rax
0x1004cc1ad  mov     rax, [rcx+8]
0x1004cc1b1  lea     r13, [rcx+60h]
0x1004cc1b5  mov     edi, edx
0x1004cc1b7  mov     [rsp+1B20h+var_1AB0], rcx
0x1004cc1bc  mov     r14, rcx
0x1004cc1bf  lea     rdx, [rcx+28h]; struct RPCPARAMEXINFO *
0x1004cc1c3  mov     rcx, r13; this
0x1004cc1c6  mov     r8d, [rax+31Ch]; unsigned int
0x1004cc1cd  call    ?OnBeginSendParamList@CRPCSQLStream@@QEAAJPEAVRPCPARAMEXINFO@@K@Z; CRPCSQLStream::OnBeginSendParamList(RPCPARAMEXINFO *,ulong)
0x1004cc1d2  xor     ecx, ecx
0x1004cc1d4  mov     ebx, eax
0x1004cc1d6  test    eax, eax
0x1004cc1d8  jns     short loc_1004CC1F4
0x1004cc1da  lea     esi, [rcx+2]
0x1004cc1dd  test    byte ptr cs:_bidGblFlags, sil
0x1004cc1e4  jz      loc_1004CD4E8
0x1004cc1ea  mov     edx, 707409h
0x1004cc1ef  jmp     loc_1004CD4DD
0x1004cc1f4  lfence
0x1004cc1f7  mov     rax, [r14+8]
0x1004cc1fb  cmp     [rax+31Ch], ecx
0x1004cc201  jz      loc_1004CD557
0x1004cc207  lfence
0x1004cc20a  mov     r15, [r14+8]
0x1004cc20e  lea     rdx, [rbp+1A20h+var_1A5E]
0x1004cc212  xor     ebx, ebx
0x1004cc214  mov     dword ptr [rbp-40h], 400000h
0x1004cc21b  mov     r12d, 1
0x1004cc221  mov     [rbp+1A20h+var_1A70], rbx
0x1004cc225  mov     [rbp+1A20h+var_1A68], rbx
0x1004cc229  mov     r9d, r12d
0x1004cc22c  mov     r8d, 6
0x1004cc232  lea     eax, [rbx+50h]
0x1004cc235  mov     dword ptr [rsp+1B20h+var_1AD8], r12d
0x1004cc23a  lea     r11d, [r12+2Fh]
0x1004cc23f  mov     [rbp+1A20h+var_1A5C], ax
0x1004cc243  movzx   ecx, r11w
0x1004cc247  mov     [rsp+1B20h+var_1AD0], r15
0x1004cc24c  mov     [rbp+1A20h+var_1A5A], cx
0x1004cc250  mov     eax, [r15+31Ch]
0x1004cc257  mov     [rsp+1B20h+var_1AC0], rdx
0x1004cc25c  mov     [rsp+1B20h+var_1AE0], r8d
0x1004cc261  cmp     eax, 834h
0x1004cc266  jbe     short loc_1004CC2B1
0x1004cc268  test    [r15+32Ch], r12b
0x1004cc26f  jnz     short loc_1004CC2B1
0x1004cc271  test    edi, edi
0x1004cc273  jnz     short loc_1004CC2B1
0x1004cc275  lea     esi, [rbx+2]
0x1004cc278  test    byte ptr cs:_bidGblFlags, sil
0x1004cc27f  jz      short loc_1004CC28D
0x1004cc281  mov     edx, 70DC09h
0x1004cc286  xor     ecx, ecx
0x1004cc288  call    _bidTraceMark
0x1004cc28d  or      [rsp+1B20h+var_1B00], 0FFFFFFFFh
0x1004cc292  mov     edx, 9CB2h; unsigned __int16
0x1004cc297  mov     rcx, [r14+8]; struct tagOBJBASE *
0x1004cc29b  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x1004cc29f  xor     r8d, r8d; int
0x1004cc2a2  call    ?PostSQLErrorEx@@YAFPEAUtagOBJBASE@@GJ_KK@Z; PostSQLErrorEx(tagOBJBASE *,ushort,long,unsigned __int64,ulong)
0x1004cc2a7  mov     ebx, 80070057h
0x1004cc2ac  jmp     loc_1004CD4E8
0x1004cc2b1  mov     edi, r12d
0x1004cc2b4  mov     [rsp+1B20h+var_1ADC], edi
0x1004cc2b8  cmp     eax, r12d
0x1004cc2bb  jb      loc_1004CD502
0x1004cc2c1  mov     esi, 2
0x1004cc2c6  lea     r10d, [rsi+37h]
0x1004cc2ca  mov     rax, [r15+1C8h]
0x1004cc2d1  cmp     rdi, [rax+8]
0x1004cc2d5  ja      loc_1004CD502
0x1004cc2db  lea     rax, [rbp+1A20h+var_1A5A]
0x1004cc2df  jmp     short loc_1004CC2EB
0x1004cc2e1  mov     [rax], r11w
0x1004cc2e5  sub     rax, rsi
0x1004cc2e8  movzx   ecx, word ptr [rax]
0x1004cc2eb  cmp     cx, r10w
0x1004cc2ef  jz      short loc_1004CC2E1
0x1004cc2f1  add     cx, r12w
0x1004cc2f5  mov     [rax], cx
0x1004cc2f8  cmp     cx, 51h ; 'Q'
0x1004cc2fc  jnz     short loc_1004CC320
0x1004cc2fe  sub     rdx, rsi; unsigned __int16 *
0x1004cc301  mov     ecx, 31h ; '1'
0x1004cc306  mov     [rax], cx
0x1004cc309  sub     rax, rsi
0x1004cc30c  add     r8d, esi; unsigned int
0x1004cc30f  mov     [rsp+1B20h+var_1AC0], rdx
0x1004cc314  mov     [rsp+1B20h+var_1AE0], r8d
0x1004cc319  mov     dword ptr [rax-2], 500040h
0x1004cc320  mov     rcx, [r15+1C8h]
0x1004cc327  lea     r12, [rdi-1]
0x1004cc32b  mov     r15, r12
0x1004cc32e  mov     [rsp+1B20h+var_1AB8], r12
0x1004cc333  imul    r15, [rcx+18h]
0x1004cc338  add     r15, rcx
0x1004cc33b  cmp     [r15+30h], bx
0x1004cc340  jz      loc_1004CD16C
0x1004cc346  test    r9d, r9d
0x1004cc349  jnz     short loc_1004CC375
0x1004cc34b  mov     r8, rsi; unsigned int
0x1004cc34e  lea     rdx, asc_10058AB24; ","
0x1004cc355  mov     rcx, r13; this
0x1004cc358  call    ?SendParamListPart@CRPCSQLStream@@QEAAJPEBG_K@Z; CRPCSQLStream::SendParamListPart(ushort const *,unsigned __int64)
0x1004cc35d  xor     ecx, ecx
0x1004cc35f  mov     ebx, eax
0x1004cc361  test    eax, eax
0x1004cc363  js      loc_1004CD198
0x1004cc369  mov     rdx, [rsp+1B20h+var_1AC0]
0x1004cc36e  mov     r8d, [rsp+1B20h+var_1AE0]
0x1004cc373  jmp     short loc_1004CC379
0x1004cc375  mov     dword ptr [rsp+1B20h+var_1AD8], ebx
0x1004cc379  mov     rcx, r13; this
0x1004cc37c  call    ?SendParamListPart@CRPCSQLStream@@QEAAJPEBG_K@Z; CRPCSQLStream::SendParamListPart(ushort const *,unsigned __int64)
0x1004cc381  xor     ecx, ecx
0x1004cc383  mov     ebx, eax
0x1004cc385  test    eax, eax
0x1004cc387  js      loc_1004CD4CF
0x1004cc38d  lfence
0x1004cc390  mov     r8, rsi; unsigned int
0x1004cc393  lea     rdx, asc_100559288; " "
0x1004cc39a  mov     rcx, r13; this
0x1004cc39d  call    ?SendParamListPart@CRPCSQLStream@@QEAAJPEBG_K@Z; CRPCSQLStream::SendParamListPart(ushort const *,unsigned __int64)
0x1004cc3a2  xor     ecx, ecx
0x1004cc3a4  mov     ebx, eax
0x1004cc3a6  test    eax, eax
0x1004cc3a8  js      loc_1004CD4BF
0x1004cc3ae  lfence
0x1004cc3b1  mov     rdx, [r14+8]
0x1004cc3b5  lea     r8, [rsp+1B20h+var_1AC8]; int *
0x1004cc3ba  lea     rcx, [r15+20h]; struct paraminfoTag *
0x1004cc3be  mov     rdx, [rdx+70h]; struct tagDBC *
0x1004cc3c2  call    ?Sql2SrvExtend@@YAEPEAUparaminfoTag@@PEAUtagDBC@@PEAH@Z; Sql2SrvExtend(paraminfoTag *,tagDBC *,int *)
0x1004cc3c7  mov     r8b, al
0x1004cc3ca  xor     ebx, ebx
0x1004cc3cc  mov     rax, [rsp+1B20h+var_1AD0]
0x1004cc3d1  mov     rax, [rax+2F0h]
0x1004cc3d8  test    rax, rax
0x1004cc3db  jz      short loc_1004CC432
0x1004cc3dd  cmp     rdi, [rax+8]
0x1004cc3e1  ja      short loc_1004CC432
0x1004cc3e3  mov     rdx, r12
0x1004cc3e6  imul    rdx, [rax+18h]
0x1004cc3eb  add     rdx, 20h ; ' '
0x1004cc3ef  add     rdx, rax
0x1004cc3f2  jz      short loc_1004CC432
0x1004cc3f4  cmp     word ptr [r15+30h], 13h
0x1004cc3fa  jnz     short loc_1004CC422
0x1004cc3fc  cmp     [rdx+20h], rbx
0x1004cc400  jnz     short loc_1004CC432
0x1004cc402  mov     rax, [rdx+38h]
0x1004cc406  test    rax, rax
0x1004cc409  jz      short loc_1004CC422
0x1004cc40b  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1004cc40f  jnz     short loc_1004CC422
0x1004cc411  lea     eax, [rbx+0Ch]
0x1004cc414  mov     [r15+20h], rbx
0x1004cc418  mov     [r15+30h], ax
0x1004cc41d  mov     r8b, 0A7h
0x1004cc420  jmp     short loc_1004CC432
0x1004cc422  cmp     [rdx+20h], rbx
0x1004cc426  jnz     short loc_1004CC432
0x1004cc428  cmp     [rdx+38h], rbx
0x1004cc42c  jz      loc_1004CC2A7
0x1004cc432  cmp     word ptr [r15+30h], 0Bh
0x1004cc438  jnz     short loc_1004CC44D
0x1004cc43a  mov     eax, 10h
0x1004cc43f  cmp     [r15+20h], rax
0x1004cc443  ja      short loc_1004CC44D
0x1004cc445  mov     rdi, [r15+20h]
0x1004cc449  mov     bl, 3Ah ; ':'
0x1004cc44b  jmp     short loc_1004CC4B9
0x1004cc44d  mov     rdi, [r15+20h]
0x1004cc451  mov     rax, rdi
0x1004cc454  cmp     r8b, 6Dh ; 'm'
0x1004cc458  jnz     short loc_1004CC46B
0x1004cc45a  mov     ebx, 3Eh ; '>'
0x1004cc45f  cmp     rdi, 4
0x1004cc463  lea     eax, [rbx-3]
0x1004cc466  cmovz   ebx, eax
0x1004cc469  jmp     short loc_1004CC4B9
0x1004cc46b  cmp     r8b, 6Eh ; 'n'
0x1004cc46f  jnz     short loc_1004CC47F
0x1004cc471  cmp     rax, 4
0x1004cc475  jnz     short loc_1004CC47B
0x1004cc477  mov     bl, 7Ah ; 'z'
0x1004cc479  jmp     short loc_1004CC4B9
0x1004cc47b  mov     bl, 3Ch ; '<'
0x1004cc47d  jmp     short loc_1004CC4B9
0x1004cc47f  cmp     r8b, 6Fh ; 'o'
0x1004cc483  jnz     short loc_1004CC493
0x1004cc485  cmp     rax, 4
0x1004cc489  jnz     short loc_1004CC48F
0x1004cc48b  mov     bl, 3Ah ; ':'
0x1004cc48d  jmp     short loc_1004CC4B9
0x1004cc48f  mov     bl, 3Dh ; '='
0x1004cc491  jmp     short loc_1004CC4B9
0x1004cc493  mov     bl, r8b
0x1004cc496  cmp     r8b, 26h ; '&'
0x1004cc49a  jnz     short loc_1004CC4B9
0x1004cc49c  cmp     rax, 1
0x1004cc4a0  jnz     short loc_1004CC4A6
0x1004cc4a2  mov     bl, 30h ; '0'
0x1004cc4a4  jmp     short loc_1004CC4B9
0x1004cc4a6  cmp     rax, rsi
0x1004cc4a9  jnz     short loc_1004CC4AF
0x1004cc4ab  mov     bl, 34h ; '4'
0x1004cc4ad  jmp     short loc_1004CC4B9
0x1004cc4af  mov     bl, 38h ; '8'
0x1004cc4b1  cmp     rax, 4
0x1004cc4b5  jz      short loc_1004CC4B9
0x1004cc4b7  mov     bl, 7Fh
0x1004cc4b9  mov     dl, bl
0x1004cc4bb  lea     rcx, [rbp+1A20h+var_1AA0]
0x1004cc4bf  call    ?ServerTypeInfo@@YA?BUtagTYPEINFO@@E@Z; ServerTypeInfo(uchar)
0x1004cc4c4  mov     dl, bl
0x1004cc4c6  lea     rcx, [rbp+1A20h+var_1A88]
0x1004cc4ca  mov     r13, [rax+8]
0x1004cc4ce  call    ?ServerTypeInfo@@YA?BUtagTYPEINFO@@E@Z; ServerTypeInfo(uchar)
0x1004cc4d3  movzx   ecx, bl
0x1004cc4d6  mov     r12, [rax]
0x1004cc4d9  mov     eax, 0ADh
0x1004cc4de  cmp     ecx, eax
0x1004cc4e0  ja      loc_1004CC776
0x1004cc4e6  jz      short loc_1004CC521
0x1004cc4e8  sub     ecx, 29h ; ')'
0x1004cc4eb  jz      loc_1004CC68D
0x1004cc4f1  sub     ecx, 1
0x1004cc4f4  jz      loc_1004CC68D
0x1004cc4fa  sub     ecx, 1
0x1004cc4fd  jz      loc_1004CC68D
0x1004cc503  sub     ecx, 3Fh ; '?'
0x1004cc506  jz      loc_1004CC59A
0x1004cc50c  sub     ecx, esi
0x1004cc50e  jz      loc_1004CC59A
0x1004cc514  sub     ecx, 39h ; '9'
0x1004cc517  jz      short loc_1004CC521
0x1004cc519  cmp     ecx, esi
0x1004cc51b  jnz     loc_1004CC7B2
0x1004cc521  add     bl, 5Bh ; '['
0x1004cc524  test    bl, 0FDh
0x1004cc527  jnz     loc_1004CD058
0x1004cc52d  xor     eax, eax
0x1004cc52f  test    rdi, rdi
0x1004cc532  jz      short loc_1004CC53E
0x1004cc534  cmp     [rsp+1B20h+var_1AC8], eax
0x1004cc538  jz      loc_1004CD058
0x1004cc53e  lea     r8, ds:0[r13*2]; unsigned int
0x1004cc546  mov     rdx, r12; unsigned __int16 *
0x1004cc549  lea     r13, [r14+60h]
0x1004cc54d  mov     rcx, r13; this
0x1004cc550  call    ?SendParamListPart@CRPCSQLStream@@QEAAJPEBG_K@Z; CRPCSQLStream::SendParamListPart(ushort const *,unsigned __int64)
0x1004cc555  xor     ecx, ecx
0x1004cc557  mov     ebx, eax
0x1004cc559  test    eax, eax
0x1004cc55b  js      loc_1004CD46F
0x1004cc561  lfence
0x1004cc564  lea     r8d, [rcx+0Ah]; unsigned int
0x1004cc568  mov     rcx, r13; this
0x1004cc56b  lea     rdx, aMax_1; "(max)"
0x1004cc572  call    ?SendParamListPart@CRPCSQLStream@@QEAAJPEBG_K@Z; CRPCSQLStream::SendParamListPart(ushort const *,unsigned __int64)
0x1004cc577  xor     ecx, ecx
0x1004cc579  mov     ebx, eax
0x1004cc57b  test    eax, eax
0x1004cc57d  jns     loc_1004CD0E9
0x1004cc583  test    byte ptr cs:_bidGblFlags, sil
0x1004cc58a  jz      loc_1004CD4E8
0x1004cc590  mov     edx, 73E809h
0x1004cc595  jmp     loc_1004CD4DD
0x1004cc59a  lea     r8, ds:0[r13*2]; unsigned int
0x1004cc5a2  mov     rdx, r12; unsigned __int16 *
0x1004cc5a5  lea     r13, [r14+60h]
0x1004cc5a9  mov     rcx, r13; this
0x1004cc5ac  call    ?SendParamListPart@CRPCSQLStream@@QEAAJPEBG_K@Z; CRPCSQLStream::SendParamListPart(ushort const *,unsigned __int64)
0x1004cc5b1  xor     ecx, ecx
0x1004cc5b3  mov     ebx, eax
0x1004cc5b5  test    eax, eax
0x1004cc5b7  js      loc_1004CD1DD
0x1004cc5bd  lfence
0x1004cc5c0  lea     eax, [rcx+28h]
0x1004cc5c3  lea     r9d, [rcx+0Ah]; Radix
0x1004cc5c7  mov     [rbp+1A20h+var_19F8], ax
0x1004cc5cb  lea     r8d, [rcx+5]; BufferCount
0x1004cc5cf  mov     ecx, [r15+20h]; Value
  ... truncated ...
```
