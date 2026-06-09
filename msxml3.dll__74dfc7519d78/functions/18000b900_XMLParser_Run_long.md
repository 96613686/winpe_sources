# XMLParser::Run(long)

- ea: `0x18000b900`
- end: `0x18000d5ba`
- name: `?Run@XMLParser@@UEAAJJ@Z`
- size: `7354`
- prototype: `__int64 __fastcall(XMLParser *__hidden this, int)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config`

## callees

- `0x18000b478`
- `0x18000b540`
- `0x18000b6c4`
- `0x18000b8c0`
- `0x18000b900`
- `0x18000d5c0`
- `0x18000d840`
- `0x18000da60`
- `0x18000dbf0`
- `0x18000fb70`
- `0x180029da0`
- `0x18002bd20`
- `0x18002c2c0`
- `0x18002d7e0`
- `0x18002f4a0`
- `0x180030810`
- `0x18003d0e4`
- `0x18003f234`
- `0x18004b488`
- `0x18004b50c`
- `0x180064034`
- `0x1800f8750`
- `0x1800f8fc0`
- `0x1801007e0`
- `0x180102cba`
- `0x180102cde`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18000d2be`
- `msvcrt!_resetstkoflw` at `0x18000d2be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b963`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d388`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d402`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d388`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d402`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d315`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d315`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b97c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d2ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d321`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b97c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d2ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000d321`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18000ce02`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18000d032`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18000ce02`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18000d032`

## pseudocode

```c
__int64 __fastcall XMLParser::Run(XMLParser *this, int a2)
{
  int v4; // edi
  unsigned __int64 v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edx
  void *v8; // rcx
  unsigned int *Value; // rax
  struct TLSDATA *v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r11
  __int64 v13; // rcx
  _BYTE *v14; // rsi
  int NextTokenInDTD; // r15d
  __int64 v16; // r8
  char i; // r12
  __int64 v18; // r13
  int v19; // eax
  unsigned int *v20; // rcx
  unsigned int v21; // eax
  char v22; // r12
  __int64 v23; // rcx
  unsigned int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  char v27; // r12
  int v28; // r13d
  unsigned int v29; // edx
  _DWORD *v30; // r12
  int v31; // eax
  int v32; // eax
  __int64 v33; // r12
  struct TLSDATA *v34; // r13
  unsigned int v35; // r8d
  _OWORD *v36; // rdx
  __int64 v37; // rax
  char v38; // dl
  unsigned int v39; // r8d
  _OWORD *v40; // rdx
  int v41; // eax
  unsigned int v42; // r12d
  unsigned __int64 n; // r13
  __int64 v44; // rcx
  unsigned int v45; // r13d
  unsigned __int64 k; // rcx
  __int64 v47; // rcx
  unsigned int v48; // eax
  unsigned __int64 ii; // r15
  unsigned int v50; // ecx
  unsigned int v51; // r12d
  unsigned __int64 m; // r15
  unsigned int v53; // eax
  const WCHAR *v54; // r9
  const WCHAR *v55; // rdx
  const WCHAR *v56; // r9
  const WCHAR *v57; // rdx
  __int64 v58; // rax
  unsigned int v59; // eax
  __int64 v60; // rcx
  int v61; // ecx
  int v62; // eax
  unsigned int v63; // r8d
  _OWORD *v64; // rdx
  XMLParser *v65; // rcx
  int v66; // ecx
  XMLStream *v67; // r15
  char v68; // r12
  struct BufferedStream *CurrentStream; // rax
  __int64 v70; // rax
  unsigned int j; // edx
  struct TLSDATA *v72; // rsi
  struct BufferedStream *v74; // rax
  int v75; // edx
  int v76; // r8d
  int v77; // eax
  char v78; // r12
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 (__fastcall *v81)(__int64, XMLParser *, __int64, __int64, unsigned int **); // rax
  __int64 v82; // rax
  int v83; // eax
  __int64 v84; // rax
  int v85; // r8d
  __int64 v86; // rcx
  __int64 v87; // r9
  void *v88; // rcx
  void *v89; // rcx
  unsigned int v90; // ebx
  unsigned int v91[4]; // [rsp+38h] [rbp-100h] BYREF
  unsigned __int16 *v92[2]; // [rsp+48h] [rbp-F0h] BYREF
  __int128 v93; // [rsp+58h] [rbp-E0h]
  char v94; // [rsp+68h] [rbp-D0h]
  struct TLSDATA *v95; // [rsp+70h] [rbp-C8h] BYREF
  unsigned int v96; // [rsp+78h] [rbp-C0h]
  unsigned int v97; // [rsp+80h] [rbp-B8h]
  __int64 v98; // [rsp+88h] [rbp-B0h] BYREF
  unsigned int *v99; // [rsp+90h] [rbp-A8h] BYREF
  int v100; // [rsp+98h] [rbp-A0h]
  int v101; // [rsp+9Ch] [rbp-9Ch]
  unsigned int v102; // [rsp+A0h] [rbp-98h]
  unsigned int v103; // [rsp+A4h] [rbp-94h]
  unsigned int v104; // [rsp+A8h] [rbp-90h]
  const WCHAR *v105; // [rsp+B0h] [rbp-88h]
  unsigned int v106; // [rsp+B8h] [rbp-80h]
  unsigned int v107; // [rsp+BCh] [rbp-7Ch]
  unsigned __int64 v108; // [rsp+C0h] [rbp-78h]
  const WCHAR *v109; // [rsp+C8h] [rbp-70h]
  unsigned __int64 v110; // [rsp+D0h] [rbp-68h]
  const WCHAR *v111; // [rsp+D8h] [rbp-60h]
  unsigned __int64 v112; // [rsp+E0h] [rbp-58h]
  unsigned __int64 v113; // [rsp+E8h] [rbp-50h]
  char *v114; // [rsp+F0h] [rbp-48h]
  char *v115; // [rsp+F8h] [rbp-40h]
  char v116; // [rsp+140h] [rbp+8h]
  char v117; // [rsp+150h] [rbp+18h]
  unsigned int v118; // [rsp+150h] [rbp+18h]
  unsigned int v119; // [rsp+150h] [rbp+18h]
  unsigned int v120; // [rsp+158h] [rbp+20h]

  v4 = *((_DWORD *)this + 72);
  v5 = (__int64)g_pfnEntry();
  v98 = v5;
  if ( !v5 )
  {
    ModelInit::~ModelInit((ModelInit *)&v98);
    return 2147500037LL;
  }
  v6 = v5 | (3LL - (*(_DWORD *)(v5 + 76) != 0));
  v98 = v6;
  *(_DWORD *)(v5 + 76) = v4;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v8 = (void *)*((_QWORD *)this + 35);
  if ( v8 )
    CaptureStackContext(v8, v7);
  Value = (unsigned int *)TlsGetValue(g_dwTlsIndex);
  v10 = (struct TLSDATA *)Value;
  v95 = (struct TLSDATA *)Value;
  v11 = Value[18];
  v120 = Value[18];
  v96 = v120;
  *(_OWORD *)v91 = 0;
  *(_OWORD *)v92 = 0;
  v93 = 0;
  v12 = 0;
  v99 = 0;
  if ( *((_BYTE *)this + 57) )
    *((_BYTE *)this + 57) = 0;
  v13 = *((_QWORD *)this + 28);
  if ( !v13 )
  {
    if ( Value[18] > (unsigned int)v11 )
      Base::freeRentalObjects((struct TLSDATA *)Value, 1, v11);
    v89 = (void *)*((_QWORD *)this + 35);
    if ( v89 )
      memset_0(v89, 0, 0x200u);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    if ( (v6 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
    {
      *(_DWORD *)((v6 & 0xFFFFFFFFFFFFFFFCuLL) + 76) = (v6 & 1) == 0;
      ((void (*)(void))g_pfnExit)();
    }
    return 2147500037LL;
  }
  if ( *((_BYTE *)this + 58) )
  {
    ScopeGC::release((ScopeGC *)&v95);
    X_CRITICAL_SECTION::Leave((XMLParser *)((char *)this + 232));
    ModelInit::~ModelInit((ModelInit *)&v98);
    return 3222070609LL;
  }
  if ( !*((_QWORD *)this + 3) )
  {
    v90 = *((_DWORD *)this + 10);
    ScopeGC::release((ScopeGC *)&v95);
    X_CRITICAL_SECTION::Leave((XMLParser *)((char *)this + 232));
    ModelInit::~ModelInit((ModelInit *)&v98);
    if ( v90 )
      return v90;
    else
      return 0;
  }
  v114 = (char *)this + 232;
  v14 = (char *)this + 81;
  if ( *((_BYTE *)this + 81) || !a2 )
  {
    ScopeGC::release((ScopeGC *)&v95);
    X_CRITICAL_SECTION::Leave((XMLParser *)((char *)this + 232));
    ModelInit::~ModelInit((ModelInit *)&v98);
    return 2147483658LL;
  }
  NextTokenInDTD = 0;
  v116 = 0;
  v115 = (char *)this + 81;
  *v14 = 1;
  if ( *((_DWORD *)this + 10) )
  {
    NextTokenInDTD = *((_DWORD *)this + 10);
LABEL_36:
    v22 = 0;
    goto LABEL_37;
  }
  if ( !*((_BYTE *)this + 59) )
  {
    *((_BYTE *)this + 59) = 1;
    NextTokenInDTD = (*(__int64 (__fastcall **)(__int64, XMLParser *, _QWORD, unsigned int *))(*(_QWORD *)v13 + 24LL))(
                       v13,
                       this,
                       0,
                       Value);
    if ( NextTokenInDTD )
      goto LABEL_35;
    if ( *((_BYTE *)this + 58) )
    {
      *v14 = 0;
      ScopeGC::release((ScopeGC *)&v95);
      X_CRITICAL_SECTION::Leave((XMLParser *)((char *)this + 232));
      ModelInit::~ModelInit((ModelInit *)&v98);
      return 0;
    }
    v12 = 0;
  }
  *((_BYTE *)this + 56) = 0;
  if ( *((_BYTE *)this + 87) )
  {
    *((_BYTE *)this + 87) = 0;
    NextTokenInDTD = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, struct TLSDATA *))(**((_QWORD **)this + 28)
                                                                                              + 32LL))(
                       *((_QWORD *)this + 28),
                       this,
                       *((_QWORD *)this + 21),
                       v10);
    if ( NextTokenInDTD )
      goto LABEL_35;
    v12 = 0;
  }
  if ( *((_BYTE *)this + 88) )
  {
    *((_BYTE *)this + 88) = 0;
    NextTokenInDTD = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64, _QWORD))(**((_QWORD **)this + 28) + 40LL))(
                       *((_QWORD *)this + 28),
                       this,
                       1,
                       *((_QWORD *)this + 21));
    if ( !NextTokenInDTD )
      NextTokenInDTD = XMLParser::pop(this);
    if ( NextTokenInDTD )
      goto LABEL_35;
    v12 = 0;
  }
  *(_QWORD *)v91 = 48;
  v91[2] = 0;
  v92[0] = 0;
  v92[1] = 0;
  v93 = 0;
  v99 = v91;
  while ( 2 )
  {
    ++*((_DWORD *)this + 18);
LABEL_17:
    v16 = 2147500037LL;
    if ( NextTokenInDTD || *((_BYTE *)this + 57) )
      goto LABEL_33;
    v91[2] = 0;
    for ( i = 1; ; i = 0 )
    {
      v18 = *((_QWORD *)this + 3);
      if ( *(_BYTE *)(v18 + 276) )
      {
        NextTokenInDTD = XMLStream::GetNextTokenInDTD(
                           (XMLStream *)v18,
                           &v91[1],
                           (const unsigned __int16 **)v92,
                           (int *)&v92[1],
                           (int *)&v92[1] + 1);
        v12 = 0;
        goto LABEL_72;
      }
      NextTokenInDTD = *(_DWORD *)(v18 + 312);
      if ( NextTokenInDTD )
        goto LABEL_72;
      if ( *(_BYTE *)(v18 + 152) )
      {
        v19 = *(_DWORD *)(v18 + 148);
        v20 = *(unsigned int **)(v18 + 120);
        v11 = v20[10];
        if ( (int)v11 <= v19 )
          v21 = v12;
        else
          v21 = v11 + ~v19;
        v20[12] = v21;
        v16 = v20[17];
        if ( (_DWORD)v16 != (_DWORD)v11 )
        {
          v20[18] = v20[15];
          if ( v20[19] != (_DWORD)v16 )
          {
            v20[16] = 1;
            v20[19] = v16;
          }
        }
        *(_DWORD *)(v18 + 148) = v12;
        *(_BYTE *)(v18 + 152) = 0;
      }
      for ( NextTokenInDTD = (*(__int64 (__fastcall **)(__int64, __int64, __int64, struct TLSDATA *))(v18 + 24))(
                               v18 + *(int *)(v18 + 32),
                               v11,
                               v16,
                               v10);
            !NextTokenInDTD;
            NextTokenInDTD = (*(__int64 (__fastcall **)(__int64))(v18 + 24))(v18 + *(int *)(v18 + 32)) )
      {
        if ( *(_DWORD *)(v18 + 140) )
        {
          v91[1] = *(_DWORD *)(v18 + 140);
          v12 = 0;
          goto LABEL_175;
        }
      }
      v12 = 0;
      v91[1] = 0;
      if ( NextTokenInDTD == -2147483638 )
      {
        v92[1] = 0;
        v92[0] = 0;
        goto LABEL_72;
      }
LABEL_175:
      if ( *(_BYTE *)(v18 + 273) )
      {
        v92[0] = *(unsigned __int16 **)(v18 + 256);
        LODWORD(v92[1]) = *(_DWORD *)(v18 + 264);
        *(_WORD *)(v18 + 272) = 0;
        *(_DWORD *)(v18 + 264) = 0;
LABEL_68:
        *(_DWORD *)(v18 + 144) = 0;
        goto LABEL_69;
      }
      v11 = *(_QWORD *)(v18 + 120);
      v60 = *(_QWORD *)(v11 + 32);
      if ( v60 )
      {
        v92[0] = (unsigned __int16 *)(v60 + 2LL * *(int *)(v11 + 48));
        v61 = *(_DWORD *)(v11 + 40) + ~*(_DWORD *)(v11 + 48);
        LODWORD(v92[1]) = v61;
      }
      else
      {
        v92[0] = (unsigned __int16 *)&word_18012A048;
        LODWORD(v92[1]) = 0;
        v61 = 0;
      }
      v62 = *(_DWORD *)(v18 + 144);
      if ( v62 )
      {
        LODWORD(v92[1]) = v61 + v62;
        goto LABEL_68;
      }
LABEL_69:
      if ( NextTokenInDTD && (unsigned int)(NextTokenInDTD + 1072896688) > 0x36 )
      {
        XMLStream::mark((XMLStream *)v18, *(_DWORD *)(v18 + 148));
        *(_DWORD *)(v18 + 148) = v12;
      }
      else
      {
        *(_BYTE *)(v18 + 152) = 1;
      }
      *(_DWORD *)(v18 + 140) = v12;
      HIDWORD(v92[1]) = *(_DWORD *)(v18 + 168);
      *(_QWORD *)(v18 + 168) = 0;
LABEL_72:
      if ( NextTokenInDTD == -1072896750 )
        goto LABEL_33;
      if ( NextTokenInDTD != -2147483638 )
      {
        if ( !*((_BYTE *)this + 86) )
        {
          if ( v91[1] > 0x12 || (v66 = 262161, !_bittest(&v66, v91[1])) )
            *((_BYTE *)this + 86) = 1;
        }
        if ( *((_BYTE *)this + 58) )
        {
          *v14 = 0;
          v72 = v95;
          if ( *((_DWORD *)v95 + 18) > v120 )
          {
            Base::freeRentalObjects(v95, 1, v120);
            v96 = *((_DWORD *)v72 + 18);
          }
          X_CRITICAL_SECTION::Leave((XMLParser *)((char *)this + 232));
          if ( (v6 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
          {
            *(_DWORD *)((v6 & 0xFFFFFFFFFFFFFFFCuLL) + 76) = (v6 & 1) == 0;
            ((void (*)(void))g_pfnExit)();
          }
          return 3222070609LL;
        }
        switch ( v91[1] )
        {
          case 0xEu:
LABEL_84:
            if ( *((_BYTE *)this + 85) )
            {
              if ( !*((_BYTE *)this + 92) )
              {
LABEL_86:
                NextTokenInDTD = -1072896682;
                goto LABEL_91;
              }
              *((_BYTE *)this + 82) = 1;
            }
LABEL_93:
            v91[3] = 1;
            if ( *((_DWORD *)this + 48) )
            {
              v35 = *((_DWORD *)this + 45);
              if ( v35 >= *((_DWORD *)this + 44) )
              {
                NextTokenInDTD = XMLParser::GrowNodeInfo(this, (struct _XML_NODE_INFO *)v91);
                if ( NextTokenInDTD < 0 )
                  goto LABEL_91;
                LODWORD(v12) = 0;
              }
              else
              {
                v36 = (_OWORD *)(*((_QWORD *)this + 19) + ((unsigned __int64)v35 << 6));
                *((_DWORD *)this + 45) = v35 + 1;
                *((_QWORD *)this + 21) = v36;
                *v36 = *(_OWORD *)v91;
                v36[1] = *(_OWORD *)v92;
                v36[2] = v93;
              }
              *((_QWORD *)&v93 + 1) = *(unsigned __int16 *)(*((_QWORD *)this + 3) + 158LL);
              *(_QWORD *)(*((_QWORD *)this + 21) + 40LL) = *((_QWORD *)&v93 + 1);
              ++*((_DWORD *)this + 48);
              NextTokenInDTD = v12;
              goto LABEL_91;
            }
            v32 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, __int64, unsigned int **))(**((_QWORD **)this + 28) + 56LL))(
                    *((_QWORD *)this + 28),
                    this,
                    *((_QWORD *)this + 27),
                    1,
                    &v99);
LABEL_145:
            *(_QWORD *)&v93 = 0;
LABEL_90:
            NextTokenInDTD = v32;
            goto LABEL_91;
          case 0x3Fu:
            if ( !*((_DWORD *)this + 45) )
            {
              NextTokenInDTD = -1072896686;
              goto LABEL_91;
            }
            v33 = *((_QWORD *)this + 21);
            NextTokenInDTD = XMLParser::pop(this, v92[0], (unsigned int)v92[1]);
            if ( NextTokenInDTD )
              goto LABEL_91;
            v32 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, __int64))(**((_QWORD **)this + 28) + 40LL))(
                    *((_QWORD *)this + 28),
                    this,
                    0,
                    v33);
            goto LABEL_90;
          case 3u:
LABEL_100:
            v38 = v116;
LABEL_101:
            if ( *((_BYTE *)this + 85) )
            {
              if ( v91[1] == 1 )
              {
                if ( *((_BYTE *)this + 82) )
                {
                  if ( !*((_BYTE *)this + 92) )
                  {
                    NextTokenInDTD = -1072896683;
                    goto LABEL_91;
                  }
                }
                else
                {
                  *((_BYTE *)this + 82) = 1;
                }
              }
              else if ( v91[1] - 3 > 2 && !*((_BYTE *)this + 92) )
              {
                goto LABEL_86;
              }
            }
            v91[3] = v12;
            if ( !v38 )
            {
              v32 = XMLParser::push(this, (struct _XML_NODE_INFO *)v91);
              goto LABEL_90;
            }
            if ( (!v91[2] || v91[2] == 31) && *((_DWORD *)this + 47) >= *((_DWORD *)this + 85) )
            {
              NextTokenInDTD = -2147467260;
              goto LABEL_118;
            }
            ++*((_DWORD *)this + 48);
            ++*((_DWORD *)this + 47);
            v39 = *((_DWORD *)this + 45);
            if ( v39 >= *((_DWORD *)this + 44) )
            {
              NextTokenInDTD = XMLParser::GrowNodeInfo(this, (struct _XML_NODE_INFO *)v91);
              if ( NextTokenInDTD < 0 )
              {
LABEL_118:
                if ( !NextTokenInDTD )
                  v116 = 0;
                goto LABEL_91;
              }
              LODWORD(v12) = 0;
            }
            else
            {
              v40 = (_OWORD *)(*((_QWORD *)this + 19) + ((unsigned __int64)v39 << 6));
              *((_DWORD *)this + 45) = v39 + 1;
              *((_QWORD *)this + 21) = v40;
              *v40 = *(_OWORD *)v91;
              v40[1] = *(_OWORD *)v92;
              v40[2] = v93;
            }
            NextTokenInDTD = v12;
            goto LABEL_118;
        }
        if ( v91[1] != 61 )
        {
          switch ( v91[1] )
          {
            case 0u:
              goto LABEL_91;
            case 1u:
              goto LABEL_100;
            case 2u:
              goto LABEL_186;
            case 4u:
              if ( *((_BYTE *)this + 89) || *((_BYTE *)this + 90) )
                goto LABEL_375;
              v67 = (XMLStream *)*((_QWORD *)this + 3);
              v68 = *((_BYTE *)this + 91);
              CurrentStream = XMLStream::getCurrentStream(v67, v68);
              if ( CurrentStream )
              {
                if ( *((_DWORD *)CurrentStream + 18) == 1 )
                {
                  v74 = XMLStream::getCurrentStream(v67, v68);
                  if ( v74 )
                  {
                    v75 = *((_DWORD *)v74 + 12);
                    v76 = *((_DWORD *)v74 + 19);
                    if ( v76 <= v75 + 1 )
                    {
                      v77 = v75 + *((_DWORD *)v74 + 16) - v76;
                      LODWORD(v12) = 0;
                    }
                    else
                    {
                      LODWORD(v12) = 0;
                      v77 = 0;
                    }
                    if ( v77 == 3 && !*((_BYTE *)this + 86) )
                    {
LABEL_375:
                      v37 = *((_QWORD *)this + 18);
                      if ( !*(_BYTE *)(v37 + 26) || !*(_BYTE *)(v37 + 32) )
                        goto LABEL_100;
                    }
                  }
                }
              }
              goto LABEL_206;
            case 5u:
              if ( *((_BYTE *)this + 84) )
              {
                NextTokenInDTD = -1072896639;
                goto LABEL_91;
              }
              *((_BYTE *)this + 84) = 1;
              *((_BYTE *)this + 92) = 0;
              if ( *((_DWORD *)this + 19) )
              {
                NextTokenInDTD = -1072896645;
                goto LABEL_91;
              }
              if ( *((_BYTE *)this + 82) )
              {
                NextTokenInDTD = -1072896642;
                goto LABEL_91;
              }
              if ( (*((_DWORD *)this + 16) & 0x8000) != 0 )
              {
                NextTokenInDTD = -1072896682;
                goto LABEL_91;
              }
LABEL_262:
              v78 = v116;
LABEL_263:
              if ( !*((_BYTE *)this + 83) )
                goto LABEL_266;
              NextTokenInDTD = XMLParser::popDTDAttribute(this);
              if ( NextTokenInDTD )
                goto LABEL_91;
              LODWORD(v12) = 0;
LABEL_266:
              v91[3] = v12;
              v79 = *((_QWORD *)this + 28);
              v80 = *((_QWORD *)this + 27);
              v81 = *(__int64 (__fastcall **)(__int64, XMLParser *, __int64, __int64, unsigned int **))(*(_QWORD *)v79 + 56LL);
              if ( v78 )
              {
                v116 = 0;
                NextTokenInDTD = v81(v79, this, v80, 1, &v99);
                if ( NextTokenInDTD )
                  goto LABEL_91;
                v32 = XMLParser::AllocNodeInfo(this, (struct _XML_NODE_INFO *)v91);
                if ( v32 < 0 )
                  goto LABEL_90;
                *((_BYTE *)this + 83) = 1;
              }
              else
              {
                NextTokenInDTD = v81(v79, this, v80, 1, &v99);
                if ( NextTokenInDTD )
                  goto LABEL_91;
                v32 = XMLParser::push(this, (struct _XML_NODE_INFO *)v91);
                if ( v32 )
                  goto LABEL_90;
              }
              *((_QWORD *)this + 27) = v93;
              *(_QWORD *)&v93 = 0;
              goto LABEL_91;
            case 7u:
            case 8u:
            case 9u:
            case 0xAu:
            case 0xBu:
            case 0xCu:
              goto LABEL_260;
            case 0xDu:
              goto LABEL_84;
            case 0xFu:
            case 0x16u:
            case 0x18u:
              goto LABEL_277;
            case 0x10u:
            case 0x12u:
              goto LABEL_93;
            case 0x11u:
              if ( !*((_BYTE *)this + 85) )
                goto LABEL_84;
              NextTokenInDTD = -1072896682;
              goto LABEL_91;
            case 0x13u:
            case 0x14u:
            case 0x15u:
            case 0x1Bu:
              v91[3] = 1;
              NextTokenInDTD = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, __int64, unsigned int **))(**((_QWORD **)this + 28) + 56LL))(
                                 *((_QWORD *)this + 28),
                                 this,
                                 *((_QWORD *)this + 27),
                                 1,
                                 &v99);
              *(_QWORD *)&v93 = 0;
              if ( NextTokenInDTD || v91[1] != 27 )
                goto LABEL_91;
              --*((_DWORD *)this + 19);
              v32 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64))(**((_QWORD **)this + 28) + 24LL))(
                      *((_QWORD *)this + 28),
                      this,
                      4);
              goto LABEL_90;
            case 0x1Cu:
              v91[2] = v91[1];
              v91[1] = 2;
              *((_BYTE *)this + 71) = 1;
              v38 = 1;
              v116 = 1;
              goto LABEL_101;
            case 0x1Du:
            case 0x1Eu:
              if ( !*((_BYTE *)this + 71) && *((_DWORD *)this + 32) == 1 )
              {
                NextTokenInDTD = -1072896663;
                goto LABEL_91;
              }
              if ( v91[1] == 30 && *((int *)this + 32) > 1 )
              {
                NextTokenInDTD = -1072896646;
                goto LABEL_91;
              }
LABEL_185:
              v91[2] = v91[1];
              v91[1] = 2;
LABEL_186:
              v38 = 1;
              v116 = 1;
              goto LABEL_101;
            case 0x1Fu:
              v91[2] = v91[1];
              v91[1] = 2;
              v38 = 1;
              v116 = 1;
              v59 = *((_DWORD *)this + 46);
              if ( v59 < *((_DWORD *)this + 44) )
              {
                *(_QWORD *)(((unsigned __int64)v59 << 6) + *((_QWORD *)this + 19) + 40) = 1;
                goto LABEL_101;
              }
              failure_tracing::record();
              NextTokenInDTD = -2147024774;
              goto LABEL_91;
            case 0x20u:
            case 0x21u:
              goto LABEL_185;
            case 0x22u:
            case 0x23u:
            case 0x24u:
              v91[2] = v91[1];
              v91[1] = 6;
              v78 = 1;
              v116 = 1;
              goto LABEL_263;
            case 0x25u:
            case 0x26u:
            case 0x27u:
            case 0x28u:
            case 0x29u:
            case 0x2Au:
            case 0x2Bu:
            case 0x2Cu:
            case 0x2Du:
              v91[2] = v91[1];
              v91[1] = 25;
              goto LABEL_277;
            case 0x2Eu:
            case 0x2Fu:
            case 0x30u:
              v91[2] = v91[1];
              v91[1] = 26;
              goto LABEL_277;
            case 0x31u:
              v91[2] = v91[1];
              v91[1] = 7;
LABEL_260:
              if ( *((_DWORD *)this + 19) )
                goto LABEL_262;
              NextTokenInDTD = -1072896640;
              goto LABEL_91;
            case 0x32u:
            case 0x33u:
            case 0x34u:
            case 0x35u:
            case 0x36u:
            case 0x37u:
            case 0x38u:
            case 0x39u:
              v91[2] = v91[1];
              v91[1] = 23;
LABEL_277:
              if ( *((_DWORD *)this + 19) )
                goto LABEL_84;
              NextTokenInDTD = -1072896640;
              goto LABEL_91;
            case 0x3Au:
            case 0x3Bu:
            case 0x3Cu:
              if ( *((_BYTE *)this + 85) && !*((_BYTE *)this + 92) )
              {
                NextTokenInDTD = -1072896682;
                goto LABEL_91;
              }
              v91[2] = v91[1];
              v91[1] = 13;
              if ( !*((_DWORD *)this + 48) )
                goto LABEL_93;
              v91[3] = 1;
              v63 = *((_DWORD *)this + 45);
              if ( v63 >= *((_DWORD *)this + 44) )
              {
                NextTokenInDTD = XMLParser::GrowNodeInfo(this, (struct _XML_NODE_INFO *)v91);
                if ( NextTokenInDTD < 0 )
                {
LABEL_201:
                  if ( NextTokenInDTD < 0 )
                    goto LABEL_91;
                  v32 = XMLParser::CopyText(v65, *((struct XMLParser::_MY_XML_NODE_INFO **)this + 21));
                  goto LABEL_90;
                }
                LODWORD(v12) = 0;
              }
              else
              {
                v64 = (_OWORD *)(*((_QWORD *)this + 19) + ((unsigned __int64)v63 << 6));
                *((_DWORD *)this + 45) = v63 + 1;
                *((_QWORD *)this + 21) = v64;
                *v64 = *(_OWORD *)v91;
                v64[1] = *(_OWORD *)v92;
                v64[2] = v93;
              }
              v65 = (XMLParser *)*(unsigned __int16 *)(*((_QWORD *)this + 3) + 158LL);
              *((_QWORD *)&v93 + 1) = v65;
              *(_QWORD *)(*((_QWORD *)this + 21) + 40LL) = v65;
              ++*((_DWORD *)this + 48);
              NextTokenInDTD = v12;
              goto LABEL_201;
            case 0x3Eu:
              goto LABEL_109;
            case 0x40u:
              v91[1] = 14;
              v91[2] = 3;
              v91[3] = 1;
              NextTokenInDTD = XMLParser::AllocNodeInfo(this, (struct _XML_NODE_INFO *)v91);
              if ( NextTokenInDTD )
                goto LABEL_91;
              ++*((_DWORD *)this + 48);
              NextTokenInDTD = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, __int64, __int64))(**((_QWORD **)this + 28) + 56LL))(
                                 *((_QWORD *)this + 28),
                                 this,
                                 *((_QWORD *)this + 27),
                                 2,
                                 *((_QWORD *)this + 20) + 8LL * (unsigned int)(*((_DWORD *)this + 45) - 2));
              if ( NextTokenInDTD )
              {
                *((_BYTE *)this + 88) = 1;
                goto LABEL_91;
              }
              --*((_DWORD *)this + 48);
              XMLParser::PopNodeInfo(this);
LABEL_302:
              NextTokenInDTD = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, _QWORD))(**((_QWORD **)this + 28)
                                                                                              + 40LL))(
                                 *((_QWORD *)this + 28),
                                 this,
                                 0,
                                 *((_QWORD *)this + 21));
              if ( !NextTokenInDTD )
                goto LABEL_113;
              goto LABEL_91;
            case 0x41u:
              *((_BYTE *)this + 71) = 0;
              v70 = *((_QWORD *)this + 18);
              if ( *(_BYTE *)(v70 + 25) || *(_BYTE *)(v70 + 26) )
              {
                if ( !*((_BYTE *)this + 90) )
                {
                  for ( j = 1; ; ++j )
                  {
                    v102 = j;
                    if ( j > *((_DWORD *)this + 48) )
                    {
LABEL_206:
                      NextTokenInDTD = -1072896681;
                      goto LABEL_91;
                    }
                    if ( *(_DWORD *)(((unsigned __int64)(*((_DWORD *)this + 45) - j) << 6) + *((_QWORD *)this + 19) + 8) == 29 )
                      break;
                  }
                }
                if ( !*((_DWORD *)this + 48) || (NextTokenInDTD = XMLParser::popAttributes(this)) == 0 )
                  XMLParser::pop(this);
                goto LABEL_91;
              }
LABEL_109:
              v41 = *((_DWORD *)this + 48);
              v10 = (struct TLSDATA *)(unsigned int)(v41 + 1);
              v97 = v41 + 1;
              if ( !v41 )
                goto LABEL_110;
              NextTokenInDTD = v12;
              v100 = v12;
              if ( *((_BYTE *)this + 89) )
                goto LABEL_142;
              if ( *((_BYTE *)this + 68) || *((_DWORD *)this + 47) < 0x1Eu )
              {
                v45 = *((_DWORD *)this + 46) + 1;
                for ( k = *((_QWORD *)this + 19) + ((unsigned __int64)v45 << 6); ; k += 64LL )
                {
                  v104 = v45;
                  v108 = k;
                  if ( v45 >= *((_DWORD *)this + 45) )
                    break;
                  if ( *(_DWORD *)(k + 4) == 2 )
                  {
                    v51 = *((_DWORD *)this + 46) + 1;
                    for ( m = *((_QWORD *)this + 19) + ((unsigned __int64)v51 << 6); ; m += 64LL )
                    {
                      v103 = v51;
                      v110 = m;
                      if ( v51 >= v45 )
                        break;
                      if ( *(_DWORD *)(m + 4) == 2 )
                      {
                        v53 = *(_DWORD *)(k + 24);
                        v119 = v53;
                        if ( v53 == *(_DWORD *)(m + 24) )
                        {
                          v56 = *(const WCHAR **)(k + 16);
                          v105 = v56;
                          v57 = *(const WCHAR **)(m + 16);
                          v109 = v57;
                          if ( !*((_BYTE *)this + 68) )
                            goto LABEL_164;
                          if ( !StrCmpNIW(v56, v57, v53) )
                          {
LABEL_292:
                            NextTokenInDTD = -1072896684;
                            goto LABEL_140;
                          }
                          k = v108;
                          v53 = v119;
                          v56 = v105;
                          v57 = v109;
                          if ( !*((_BYTE *)this + 68) )
                          {
LABEL_164:
                            if ( !memcmp_0(v56, v57, 2LL * v53) )
                              goto LABEL_292;
                            k = v108;
                          }
                        }
                      }
                      ++v51;
                    }
                  }
                  ++v45;
                }
                NextTokenInDTD = 0;
LABEL_140:
                v100 = NextTokenInDTD;
                goto LABEL_141;
              }
              NextTokenInDTD = XMLParser::HashCheckDupAttributes(this);
              v100 = NextTokenInDTD;
LABEL_141:
              v10 = (struct TLSDATA *)v97;
LABEL_142:
              *(_QWORD *)((char *)this + 188) = 0;
              v47 = *((unsigned int *)this + 46);
              *((_DWORD *)this + 45) = v47 + 1;
              *((_QWORD *)this + 21) = *((_QWORD *)this + 19) + (v47 << 6);
              if ( NextTokenInDTD )
                goto LABEL_91;
LABEL_110:
              if ( (unsigned int)v10 > 0xFFFF )
              {
                NextTokenInDTD = -1072896750;
                goto LABEL_91;
              }
              NextTokenInDTD = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD))(**((_QWORD **)this + 28) + 56LL))(
                                 *((_QWORD *)this + 28),
                                 this,
                                 *((_QWORD *)this + 27));
              if ( NextTokenInDTD )
              {
                *((_BYTE *)this + 88) = 1;
                goto LABEL_91;
              }
LABEL_112:
              NextTokenInDTD = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64, _QWORD))(**((_QWORD **)this + 28)
                                                                                               + 40LL))(
                                 *((_QWORD *)this + 28),
                                 this,
                                 1,
                                 *((_QWORD *)this + 21));
              if ( NextTokenInDTD )
                goto LABEL_91;
LABEL_113:
              v32 = XMLParser::pop(this);
              goto LABEL_90;
            case 0x42u:
              if ( !*((_BYTE *)this + 83) )
                goto LABEL_112;
              NextTokenInDTD = XMLParser::popDTDAttribute(this);
              if ( !NextTokenInDTD )
                goto LABEL_112;
              goto LABEL_91;
            case 0x43u:
            case 0x44u:
              goto LABEL_302;
            case 0x45u:
              ++*((_DWORD *)this + 19);
              if ( *((_BYTE *)this + 83) )
              {
                NextTokenInDTD = XMLParser::popDTDAttribute(this);
                if ( NextTokenInDTD )
                  goto LABEL_91;
              }
              v32 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64, struct TLSDATA *))(**((_QWORD **)this + 28)
                                                                                              + 24LL))(
                      *((_QWORD *)this + 28),
                      this,
                      3,
                      v10);
              goto LABEL_90;
            case 0x46u:
              if ( !*((_BYTE *)this + 85) )
                goto LABEL_91;
              v58 = *((_QWORD *)this + 18);
              if ( *(_BYTE *)(v58 + 26) || *(_BYTE *)(v58 + 25) )
                goto LABEL_91;
              v32 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64, struct TLSDATA *))(**((_QWORD **)this + 28)
                                                                                              + 24LL))(
                      *((_QWORD *)this + 28),
                      this,
                      5,
                      v10);
              goto LABEL_90;
            case 0x49u:
              if ( *((_BYTE *)this + 85) && !*((_BYTE *)this + 92) )
              {
                NextTokenInDTD = -1072896682;
                goto LABEL_91;
              }
              v91[1] = 14;
              v91[3] = 1;
              v82 = v12;
              LOBYTE(v82) = LODWORD(v92[1]) == 0;
              *((_QWORD *)&v93 + 1) = v82 + 1;
              v32 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD, __int64, unsigned int **))(**((_QWORD **)this + 28) + 56LL))(
                      *((_QWORD *)this + 28),
                      this,
                      *((_QWORD *)this + 27),
                      1,
                      &v99);
              *((_QWORD *)&v93 + 1) = 0;
              goto LABEL_145;
            default:
              NextTokenInDTD = -2147467259;
              goto LABEL_91;
          }
        }
        v30 = (_DWORD *)((char *)this + 192);
        v31 = *((_DWORD *)this + 48);
        v10 = (struct TLSDATA *)(unsigned int)(v31 + 1);
        v97 = v31 + 1;
        if ( !v31 )
          goto LABEL_81;
        NextTokenInDTD = v12;
        v101 = v12;
        if ( !*((_BYTE *)this + 89) )
        {
          if ( *((_BYTE *)this + 68) || *((_DWORD *)this + 47) < 0x1Eu )
          {
            v42 = *((_DWORD *)this + 46) + 1;
            for ( n = *((_QWORD *)this + 19) + ((unsigned __int64)v42 << 6); ; n += 64LL )
            {
              v107 = v42;
              v113 = n;
              if ( v42 >= *((_DWORD *)this + 45) )
                break;
              if ( *(_DWORD *)(n + 4) == 2 )
              {
                v48 = *((_DWORD *)this + 46) + 1;
                for ( ii = *((_QWORD *)this + 19) + ((unsigned __int64)v48 << 6); ; ii += 64LL )
                {
                  v106 = v48;
                  v112 = ii;
                  v118 = v48;
                  if ( v48 >= v42 )
                    break;
                  if ( *(_DWORD *)(ii + 4) == 2 )
                  {
                    v50 = *(_DWORD *)(n + 24);
                    LODWORD(v105) = v50;
                    if ( v50 == *(_DWORD *)(ii + 24) )
                    {
                      v54 = *(const WCHAR **)(n + 16);
                      v109 = v54;
                      v55 = *(const WCHAR **)(ii + 16);
                      v111 = v55;
                      if ( !*((_BYTE *)this + 68) )
                        goto LABEL_161;
                      if ( !StrCmpNIW(v54, v55, v50) )
                      {
LABEL_314:
                        NextTokenInDTD = -1072896684;
                        LODWORD(v12) = 0;
                        goto LABEL_128;
                      }
                      v48 = v118;
                      v50 = (unsigned int)v105;
                      v54 = v109;
                      v55 = v111;
                      if ( !*((_BYTE *)this + 68) )
                      {
LABEL_161:
                        if ( !memcmp_0(v54, v55, 2LL * v50) )
                          goto LABEL_314;
                        v48 = v118;
                      }
                    }
                  }
                  ++v48;
                }
              }
              ++v42;
            }
            LODWORD(v12) = 0;
            NextTokenInDTD = 0;
LABEL_128:
            v101 = NextTokenInDTD;
            v30 = (_DWORD *)((char *)this + 192);
          }
          else
          {
            NextTokenInDTD = XMLParser::HashCheckDupAttributes(this);
            v101 = NextTokenInDTD;
            LODWORD(v12) = 0;
          }
          v10 = (struct TLSDATA *)v97;
        }
        *v30 = v12;
        *((_DWORD *)this + 47) = v12;
        v44 = *((unsigned int *)this + 46);
        *((_DWORD *)this + 45) = v44 + 1;
        *((_QWORD *)this + 21) = *((_QWORD *)this + 19) + (v44 << 6);
        if ( !NextTokenInDTD )
        {
LABEL_81:
          if ( (unsigned int)v10 > 0xFFFF )
          {
            NextTokenInDTD = -1072896750;
            goto LABEL_91;
          }
          NextTokenInDTD = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD))(**((_QWORD **)this + 28) + 56LL))(
                             *((_QWORD *)this + 28),
                             this,
                             *((_QWORD *)this + 27));
          *((_QWORD *)this + 27) = *(_QWORD *)(*((_QWORD *)this + 21) + 32LL);
          if ( NextTokenInDTD )
          {
            *((_BYTE *)this + 87) = 1;
            goto LABEL_91;
          }
          v32 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *))(**((_QWORD **)this + 28) + 32LL))(
                  *((_QWORD *)this + 28),
                  this);
          goto LABEL_90;
        }
LABEL_91:
        v34 = v95;
        v11 = v120;
        if ( *((_DWORD *)v95 + 18) - v120 > 0x100 && *((_DWORD *)v95 + 18) > v120 )
        {
          Base::freeRentalObjects(v95, 1, v120);
          v120 = *((_DWORD *)v34 + 18);
          v96 = v120;
        }
        v12 = 0;
        goto LABEL_17;
      }
      if ( !i )
        break;
    }
    *((_BYTE *)this + 56) = 1;
LABEL_33:
    --*((_DWORD *)this + 18);
    if ( NextTokenInDTD != -1072896768 )
    {
      if ( NextTokenInDTD == -1072896735 )
      {
        --*(_DWORD *)(*((_QWORD *)this + 18) + 28LL);
        v84 = *((_QWORD *)this + 18);
        if ( !*(_QWORD *)v84 && !*(_DWORD *)(v84 + 28) )
          XMLParser::PopDownload(this);
        NextTokenInDTD = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64, struct TLSDATA *))(**((_QWORD **)this + 28) + 24LL))(
                           *((_QWORD *)this + 28),
                           this,
                           7,
                           v10);
        if ( !NextTokenInDTD )
        {
          if ( !*((_BYTE *)this + 58) )
            goto LABEL_332;
          goto LABEL_342;
        }
      }
      goto LABEL_35;
    }
    NextTokenInDTD = v12;
    v26 = *((_QWORD *)this + 18);
    v27 = *(_BYTE *)(v26 + 26);
    if ( v27 )
    {
      v29 = *(_DWORD *)(v26 + 40);
      if ( v29 != *((_DWORD *)this + 45) )
      {
        NextTokenInDTD = XMLParser::ReportUnclosedTags(this, v29);
        goto LABEL_35;
      }
    }
    v117 = *(_BYTE *)(v26 + 25);
    v28 = *(_DWORD *)(v26 + 28);
    if ( !(unsigned int)XMLParser::PopDownload(this) )
    {
      if ( !v28 )
      {
        if ( v27 )
        {
          v83 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64))(**((_QWORD **)this + 28) + 24LL))(
                  *((_QWORD *)this + 28),
                  this,
                  7);
LABEL_327:
          NextTokenInDTD = v83;
          goto LABEL_328;
        }
        if ( v117 )
        {
          v83 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, __int64))(**((_QWORD **)this + 28) + 24LL))(
                  *((_QWORD *)this + 28),
                  this,
                  2);
          --*((_DWORD *)this + 19);
          goto LABEL_327;
        }
      }
LABEL_328:
      if ( !NextTokenInDTD )
      {
        if ( *((int *)this + 18) <= 0 && !*((_BYTE *)this + 58) )
        {
LABEL_332:
          v12 = 0;
          continue;
        }
LABEL_342:
        *v14 = 0;
        ScopeGC::release((ScopeGC *)&v95);
        X_CRITICAL_SECTION::Leave((XMLParser *)((char *)this + 232));
        ModelInit::~ModelInit((ModelInit *)&v98);
        return 0;
      }
LABEL_35:
      v10 = v95;
      LODWORD(v11) = v120;
      goto LABEL_36;
    }
    break;
  }
  if ( *((_DWORD *)this + 45) )
  {
    NextTokenInDTD = XMLParser::ReportUnclosedTags(this, 0);
  }
  else if ( !*((_BYTE *)this + 82) && !*((_BYTE *)this + 92) )
  {
    NextTokenInDTD = -1072896680;
  }
  v22 = 1;
  v94 = 1;
  v10 = v95;
  LODWORD(v11) = v120;
LABEL_37:
  if ( NextTokenInDTD && NextTokenInDTD != -2147483638 )
  {
    if ( XMLParser::IsCrossDomainDownload(this) )
      NextTokenInDTD = v85;
    v22 = 1;
    v94 = 1;
    *((_DWORD *)this + 10) = NextTokenInDTD;
    v86 = *((_QWORD *)this + 28);
    if ( v86 )
    {
      if ( *((_QWORD *)this + 20) )
        v87 = (unsigned int)(*((_DWORD *)this + 46) + 1);
      else
        v87 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, XMLParser *, _QWORD, __int64, _QWORD))(*(_QWORD *)v86 + 48LL))(
             v86,
             this,
             (unsigned int)NextTokenInDTD,
             v87,
             *((_QWORD *)this + 20)) )
      {
        *((_DWORD *)this + 10) = NextTokenInDTD;
      }
      LODWORD(v11) = v120;
      v10 = v95;
    }
  }
  if ( v22 )
  {
    if ( !*((_BYTE *)this + 58) )
    {
      *((_DWORD *)this + 10) = NextTokenInDTD;
      *((_WORD *)this + 29) = 1;
      v23 = *((_QWORD *)this + 28);
      if ( v23 )
      {
        v24 = (*(__int64 (__fastcall **)(__int64, XMLParser *, __int64, struct TLSDATA *))(*(_QWORD *)v23 + 24LL))(
                v23,
                this,
                8,
                v10);
        if ( v24 )
        {
          NextTokenInDTD = v24;
          if ( !*((_DWORD *)this + 10) )
          {
            v25 = (*(__int64 (__fastcall **)(_QWORD, XMLParser *, _QWORD))(**((_QWORD **)this + 28) + 48LL))(
                    *((_QWORD *)this + 28),
                    this,
                    v24);
            if ( v25 )
              NextTokenInDTD = v25;
          }
          *((_DWORD *)this + 10) = NextTokenInDTD;
        }
        LODWORD(v11) = v120;
        v10 = v95;
      }
    }
  }
  *v14 = 0;
  if ( *((_DWORD *)v10 + 18) > (unsigned int)v11 )
    Base::freeRentalObjects(v10, 1, v11);
  v88 = (void *)*((_QWORD *)this + 35);
  if ( v88 )
    memset_0(v88, 0, 0x200u);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( (v6 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
  {
    *(_DWORD *)((v6 & 0xFFFFFFFFFFFFFFFCuLL) + 76) = (v6 & 1) == 0;
    ((void (*)(void))g_pfnExit)();
  }
  return (unsigned int)NextTokenInDTD;
}

```

## disassembly

```asm
0x18000b900  push    rbx
0x18000b902  push    rsi
0x18000b903  push    rdi
0x18000b904  push    r12
0x18000b906  push    r13
0x18000b908  push    r14
0x18000b90a  push    r15
0x18000b90c  sub     rsp, 100h
0x18000b913  mov     r15d, edx
0x18000b916  mov     r14, rcx
0x18000b919  mov     edi, [rcx+120h]
0x18000b91f  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x18000b926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b92b  mov     rcx, rax
0x18000b92e  mov     [rsp+138h+var_B0], rax
0x18000b936  test    rax, rax
0x18000b939  jz      loc_18000D42C
0x18000b93f  mov     eax, [rax+4Ch]
0x18000b942  neg     eax
0x18000b944  sbb     rbx, rbx
0x18000b947  add     rbx, 3
0x18000b94b  or      rbx, rcx
0x18000b94e  mov     [rsp+138h+var_B0], rbx
0x18000b956  mov     [rcx+4Ch], edi
0x18000b959  lea     rdi, [r14+0E8h]
0x18000b960  mov     rcx, rdi; lpCriticalSection
0x18000b963  call    cs:__imp_EnterCriticalSection
0x18000b969  mov     rcx, [rdi+30h]; void *
0x18000b96d  test    rcx, rcx
0x18000b970  jnz     loc_18000D443
0x18000b976  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18000b97c  call    cs:__imp_TlsGetValue
0x18000b982  mov     r9, rax
0x18000b985  mov     [rsp+138h+var_C8], rax
0x18000b98a  mov     edx, [rax+48h]
0x18000b98d  mov     [rsp+138h+arg_18], edx
0x18000b994  mov     [rsp+138h+var_C0], edx
0x18000b998  xorps   xmm0, xmm0
0x18000b99b  movups  xmmword ptr [rsp+138h+var_100], xmm0
0x18000b9a0  movups  xmmword ptr [rsp+138h+var_F0], xmm0
0x18000b9a5  movups  [rsp+138h+var_E0], xmm0
0x18000b9aa  xor     r11d, r11d
0x18000b9ad  mov     [rsp+138h+var_A8], r11
0x18000b9b5  cmp     [r14+39h], r11b
0x18000b9b9  jz      short loc_18000B9BF
0x18000b9bb  mov     [r14+39h], r11b
0x18000b9bf  mov     rcx, [r14+0E0h]
0x18000b9c6  test    rcx, rcx
0x18000b9c9  jz      loc_18000D3E4
0x18000b9cf  cmp     [r14+3Ah], r11b
0x18000b9d3  jnz     loc_18000D45C
0x18000b9d9  cmp     [r14+18h], r11
0x18000b9dd  jz      loc_18000D485
0x18000b9e3  mov     [rsp+138h+var_48], rdi
0x18000b9eb  lea     rsi, [r14+51h]
0x18000b9ef  cmp     [rsi], r11b
0x18000b9f2  jnz     loc_18000D4CC
0x18000b9f8  test    r15d, r15d
0x18000b9fb  jz      loc_18000D4CC
0x18000ba01  mov     r15d, r11d
0x18000ba04  xor     r10b, r10b
0x18000ba07  mov     [rsp+138h+arg_0], r10b
0x18000ba0f  mov     [rsp+138h+var_40], rsi
0x18000ba17  mov     byte ptr [rsi], 1
0x18000ba1a  mov     eax, [r14+28h]
0x18000ba1e  test    eax, eax
0x18000ba20  jnz     loc_18000C9E7
0x18000ba26  cmp     [r14+3Bh], al
0x18000ba2a  jz      loc_18000BC37
0x18000ba30  mov     byte ptr [r14+38h], 0
0x18000ba35  cmp     byte ptr [r14+57h], 0
0x18000ba3a  jnz     loc_18000BCB4
0x18000ba40  cmp     byte ptr [r14+58h], 0
0x18000ba45  jnz     loc_18000BC70
0x18000ba4b  mov     qword ptr [rsp+138h+var_100], 30h ; '0'
0x18000ba54  mov     [rsp+138h+var_100+8], r11d
0x18000ba59  mov     [rsp+138h+var_F0], r11
0x18000ba5e  mov     [rsp+138h+var_F0+8], 0
0x18000ba67  xorps   xmm0, xmm0
0x18000ba6a  movdqu  [rsp+138h+var_E0], xmm0
0x18000ba70  lea     rax, [rsp+138h+var_100]
0x18000ba75  mov     [rsp+138h+var_A8], rax
0x18000ba7d  nop     dword ptr [rax]
0x18000ba80  inc     dword ptr [r14+48h]
0x18000ba84  mov     r8d, 80004005h
0x18000ba8a  test    r15d, r15d
0x18000ba8d  jnz     loc_18000BB64
0x18000ba93  cmp     [r14+39h], r15b
0x18000ba97  jnz     loc_18000BB64
0x18000ba9d  mov     [rsp+138h+var_100+8], r11d
0x18000baa2  mov     r12b, 1
0x18000baa5  mov     r13, [r14+18h]
0x18000baa9  cmp     byte ptr [r13+114h], 0
0x18000bab1  jnz     loc_18000CA36
0x18000bab7  mov     r15d, [r13+138h]
0x18000babe  test    r15d, r15d
0x18000bac1  jnz     loc_18000BE1A
0x18000bac7  cmp     [r13+98h], r15b
0x18000bace  jz      short loc_18000BB05
0x18000bad0  mov     eax, [r13+94h]
0x18000bad7  mov     rcx, [r13+78h]
0x18000badb  mov     edx, [rcx+28h]
0x18000bade  cmp     edx, eax
0x18000bae0  jle     loc_18000BC68
0x18000bae6  not     eax
0x18000bae8  add     eax, edx
0x18000baea  mov     [rcx+30h], eax
0x18000baed  mov     r8d, [rcx+44h]
0x18000baf1  cmp     r8d, edx
0x18000baf4  jnz     short loc_18000BB4B
0x18000baf6  mov     [r13+94h], r11d
0x18000bafd  mov     byte ptr [r13+98h], 0
0x18000bb05  movsxd  rcx, dword ptr [r13+20h]
0x18000bb09  add     rcx, r13
0x18000bb0c  mov     rax, [r13+18h]
0x18000bb10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb15  mov     r15d, eax
0x18000bb18  nop     dword ptr [rax+rax+00000000h]
0x18000bb20  test    r15d, r15d
0x18000bb23  jnz     loc_18000BD9C
0x18000bb29  cmp     [r13+8Ch], r15d
0x18000bb30  jnz     loc_18000C601
0x18000bb36  movsxd  rcx, dword ptr [r13+20h]
0x18000bb3a  add     rcx, r13
0x18000bb3d  mov     rax, [r13+18h]
0x18000bb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb46  mov     r15d, eax
0x18000bb49  jmp     short loc_18000BB20
0x18000bb4b  mov     eax, [rcx+3Ch]
0x18000bb4e  mov     [rcx+48h], eax
0x18000bb51  cmp     [rcx+4Ch], r8d
0x18000bb55  jz      short loc_18000BAF6
0x18000bb57  mov     dword ptr [rcx+40h], 1
0x18000bb5e  mov     [rcx+4Ch], r8d
0x18000bb62  jmp     short loc_18000BAF6
0x18000bb64  mov     eax, [r14+48h]
0x18000bb68  dec     eax
0x18000bb6a  mov     [r14+48h], eax
0x18000bb6e  cmp     r15d, 0C00CE500h
0x18000bb75  jz      loc_18000BCED
0x18000bb7b  cmp     r15d, 0C00CE521h
0x18000bb82  jz      loc_18000D195
0x18000bb88  mov     r9, [rsp+138h+var_C8]
0x18000bb8d  mov     edx, [rsp+138h+arg_18]
0x18000bb94  xor     r12b, r12b
0x18000bb97  test    r15d, r15d
0x18000bb9a  jnz     loc_18000D217
0x18000bba0  test    r12b, r12b
0x18000bba3  jz      loc_18000D2A1
0x18000bba9  cmp     byte ptr [r14+3Ah], 0
0x18000bbae  jnz     loc_18000D2A1
0x18000bbb4  mov     [r14+28h], r15d
0x18000bbb8  mov     word ptr [r14+3Ah], 1
0x18000bbbf  mov     rcx, [r14+0E0h]
0x18000bbc6  test    rcx, rcx
0x18000bbc9  jz      loc_18000D2A1
0x18000bbcf  mov     rax, [rcx]
0x18000bbd2  mov     r8d, 8
0x18000bbd8  mov     rdx, r14
0x18000bbdb  mov     rax, [rax+18h]
0x18000bbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbe4  mov     r8d, eax
0x18000bbe7  test    eax, eax
0x18000bbe9  jz      short loc_18000BC26
0x18000bbeb  mov     r15d, eax
0x18000bbee  mov     [rsp+138h+var_108], eax
0x18000bbf2  cmp     dword ptr [r14+28h], 0
0x18000bbf7  jnz     short loc_18000BC22
0x18000bbf9  mov     rcx, [r14+0E0h]
0x18000bc00  mov     rdx, [rcx]
0x18000bc03  xor     r9d, r9d
0x18000bc06  mov     rax, [rdx+30h]
0x18000bc0a  mov     [rsp+138h+var_118], r9
0x18000bc0f  mov     rdx, r14
0x18000bc12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc17  test    eax, eax
0x18000bc19  cmovnz  r15d, eax
0x18000bc1d  mov     [rsp+138h+var_108], r15d
0x18000bc22  mov     [r14+28h], r15d
0x18000bc26  mov     edx, [rsp+138h+arg_18]
0x18000bc2d  mov     r9, [rsp+138h+var_C8]
0x18000bc32  jmp     loc_18000D2A1
0x18000bc37  mov     byte ptr [r14+3Bh], 1
0x18000bc3c  mov     rax, [rcx]
0x18000bc3f  xor     r8d, r8d
0x18000bc42  mov     rdx, r14
0x18000bc45  mov     rax, [rax+18h]
0x18000bc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc4e  mov     r15d, eax
0x18000bc51  mov     [rsp+138h+var_108], eax
0x18000bc55  test    eax, eax
0x18000bc57  jz      loc_18000BD63
0x18000bc5d  mov     r8d, 80004005h
0x18000bc63  jmp     loc_18000BB88
0x18000bc68  mov     eax, r11d
0x18000bc6b  jmp     loc_18000BAEA
0x18000bc70  mov     byte ptr [r14+58h], 0
0x18000bc75  mov     rcx, [r14+0E0h]
0x18000bc7c  mov     rax, [rcx]
0x18000bc7f  mov     r9, [r14+0A8h]
0x18000bc86  mov     r8d, 1
0x18000bc8c  mov     rdx, r14
0x18000bc8f  mov     rax, [rax+28h]
0x18000bc93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc98  mov     r15d, eax
0x18000bc9b  mov     [rsp+138h+var_108], eax
0x18000bc9f  test    eax, eax
0x18000bca1  jz      loc_18000CA22
0x18000bca7  test    r15d, r15d
0x18000bcaa  jnz     short loc_18000BC5D
0x18000bcac  xor     r11d, r11d
0x18000bcaf  jmp     loc_18000BA4B
0x18000bcb4  mov     byte ptr [r14+57h], 0
0x18000bcb9  mov     rcx, [r14+0E0h]
0x18000bcc0  mov     rax, [rcx]
0x18000bcc3  mov     r8, [r14+0A8h]
0x18000bcca  mov     rdx, r14
0x18000bccd  mov     rax, [rax+20h]
0x18000bcd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcd6  mov     r15d, eax
0x18000bcd9  mov     [rsp+138h+var_108], eax
0x18000bcdd  test    eax, eax
0x18000bcdf  jnz     loc_18000BC5D
0x18000bce5  xor     r11d, r11d
0x18000bce8  jmp     loc_18000BA40
0x18000bced  mov     r15d, r11d
0x18000bcf0  mov     [rsp+138h+var_108], r11d
0x18000bcf5  mov     rax, [r14+90h]
0x18000bcfc  movzx   r12d, byte ptr [rax+1Ah]
0x18000bd01  test    r12b, r12b
0x18000bd04  jnz     short loc_18000BD76
0x18000bd06  movzx   ecx, byte ptr [rax+19h]
0x18000bd0a  mov     byte ptr [rsp+138h+arg_10], cl
0x18000bd11  mov     r13d, [rax+1Ch]
0x18000bd15  mov     rcx, r14; this
0x18000bd18  call    ?PopDownload@XMLParser@@AEAAJXZ; XMLParser::PopDownload(void)
0x18000bd1d  test    eax, eax
0x18000bd1f  jz      loc_18000D0A5
0x18000bd25  cmp     dword ptr [r14+0B4h], 0
0x18000bd2d  jbe     loc_18000D172
0x18000bd33  xor     edx, edx; unsigned int
0x18000bd35  mov     rcx, r14; this
0x18000bd38  call    ?ReportUnclosedTags@XMLParser@@AEAAJK@Z; XMLParser::ReportUnclosedTags(ulong)
0x18000bd3d  mov     r15d, eax
0x18000bd40  mov     [rsp+138h+var_108], eax
0x18000bd44  mov     r12b, 1
0x18000bd47  mov     [rsp+138h+var_D0], r12b
0x18000bd4c  mov     r9, [rsp+138h+var_C8]
0x18000bd51  mov     edx, [rsp+138h+arg_18]
0x18000bd58  mov     r8d, 80004005h
0x18000bd5e  jmp     loc_18000BB97
0x18000bd63  cmp     byte ptr [r14+3Ah], 0
0x18000bd68  jnz     loc_18000C9F9
0x18000bd6e  xor     r11d, r11d
0x18000bd71  jmp     loc_18000BA30
0x18000bd76  mov     edx, [rax+28h]; unsigned int
0x18000bd79  cmp     edx, [r14+0B4h]
0x18000bd80  jz      short loc_18000BD06
0x18000bd82  mov     rcx, r14; this
0x18000bd85  call    ?ReportUnclosedTags@XMLParser@@AEAAJK@Z; XMLParser::ReportUnclosedTags(ulong)
0x18000bd8a  mov     r15d, eax
0x18000bd8d  mov     [rsp+138h+var_108], eax
0x18000bd91  mov     r8d, 80004005h
0x18000bd97  jmp     loc_18000BB88
0x18000bd9c  xor     r11d, r11d
0x18000bd9f  mov     [rsp+138h+var_100+4], r11d
0x18000bda4  cmp     r15d, 8000000Ah
0x18000bdab  jnz     loc_18000C618
0x18000bdb1  mov     [rsp+138h+var_F0+8], r11
0x18000bdb6  mov     [rsp+138h+var_F0], r11
0x18000bdbb  jmp     short loc_18000BE1A
0x18000bdbd  mov     rax, [r13+100h]
0x18000bdc4  mov     [rsp+138h+var_F0], rax
0x18000bdc9  mov     eax, [r13+108h]
0x18000bdd0  mov     dword ptr [rsp+138h+var_F0+8], eax
0x18000bdd4  mov     word ptr [r13+110h], 0
0x18000bdde  mov     [r13+108h], r11d
0x18000bde5  mov     [r13+90h], r11d
0x18000bdec  test    r15d, r15d
0x18000bdef  jnz     loc_18000CA7B
0x18000bdf5  mov     byte ptr [r13+98h], 1
0x18000bdfd  mov     [r13+8Ch], r11d
0x18000be04  mov     eax, [r13+0A8h]
0x18000be0b  mov     dword ptr [rsp+138h+var_F0+0Ch], eax
0x18000be0f  mov     qword ptr [r13+0A8h], 0
0x18000be1a  mov     [rsp+138h+var_108], r15d
0x18000be1f  cmp     r15d, 0C00CE512h
0x18000be26  jz      loc_18000CAAB
0x18000be2c  cmp     r15d, 8000000Ah
0x18000be33  jz      loc_18000C853
0x18000be39  cmp     byte ptr [r14+56h], 0
0x18000be3e  jz      loc_18000C777
0x18000be44  cmp     byte ptr [r14+3Ah], 0
0x18000be49  jnz     loc_18000C8E3
0x18000be4f  mov     eax, [rsp+138h+var_100+4]
0x18000be53  cmp     eax, 0Eh
0x18000be56  jz      loc_18000BF15; jumptable 000000018000C11E case 13
0x18000be5c  cmp     eax, 3Fh ; '?'
0x18000be5f  jz      loc_18000BF38
0x18000be65  cmp     eax, 3
  ... truncated ...
```
