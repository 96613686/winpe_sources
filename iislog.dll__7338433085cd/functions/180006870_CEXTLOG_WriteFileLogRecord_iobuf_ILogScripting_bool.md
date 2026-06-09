# CEXTLOG::WriteFileLogRecord(_iobuf *,ILogScripting *,bool)

- ea: `0x180006870`
- end: `0x180007248`
- name: `?WriteFileLogRecord@CEXTLOG@@MEAAJPEAU_iobuf@@PEAUILogScripting@@_N@Z`
- size: `2520`
- prototype: `__int64 __fastcall(CEXTLOG *this, struct _iobuf *, struct ILogScripting *, char)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180002114`
- `0x1800022a8`
- `0x180006870`
- `0x18000eca0`
- `0x18000ed30`
- `0x180010010`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180006a05`
- `msvcrt!strcpy_s` at `0x180006d73`
- `msvcrt!strcpy_s` at `0x180006a05`
- `msvcrt!strcpy_s` at `0x180006d73`
- `msvcrt!strcat_s` at `0x180006da2`
- `msvcrt!strcat_s` at `0x180006dc0`
- `msvcrt!strcat_s` at `0x180006e36`
- `msvcrt!strcat_s` at `0x180006e9b`
- `msvcrt!strcat_s` at `0x180006f94`
- `msvcrt!strcat_s` at `0x180006fab`
- `msvcrt!strcat_s` at `0x180006fd9`
- `msvcrt!strcat_s` at `0x180007027`
- `msvcrt!strcat_s` at `0x1800070d3`
- `msvcrt!strcat_s` at `0x180007129`
- `msvcrt!strcat_s` at `0x180007179`
- `msvcrt!strcat_s` at `0x1800071e9`
- `msvcrt!strcat_s` at `0x180006da2`
- `msvcrt!strcat_s` at `0x180006dc0`
- `msvcrt!strcat_s` at `0x180006e36`
- `msvcrt!strcat_s` at `0x180006e9b`
- `msvcrt!strcat_s` at `0x180006f94`
- `msvcrt!strcat_s` at `0x180006fab`
- `msvcrt!strcat_s` at `0x180006fd9`
- `msvcrt!strcat_s` at `0x180007027`
- `msvcrt!strcat_s` at `0x1800070d3`
- `msvcrt!strcat_s` at `0x180007129`
- `msvcrt!strcat_s` at `0x180007179`
- `msvcrt!strcat_s` at `0x1800071e9`
- `msvcrt!sprintf_s` at `0x180006f7d`
- `msvcrt!sprintf_s` at `0x180006f7d`
- `msvcrt!fprintf` at `0x180007215`
- `msvcrt!fprintf` at `0x180007215`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x180006ece`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x180006ece`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180006f1e`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180006f1e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180006e01`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180007158`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180006e01`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180007158`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180006eb3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800071fd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180006eb3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800071fd`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180006d43`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180006d43`

## string_xrefs

- `0x180006913`: `s-computername`
- `0x180006934`: `cs-uri-stem`
- `0x180006942`: `cs-uri-query`
- `0x1800069b2`: `cs(User-Agent)`
- `0x180006f56`: `#Software: Microsoft Internet Information Services 5.0\n#Version: %s\n#Date: %s %s\n#Fields: %s\n`

## pseudocode

```c
__int64 __fastcall CEXTLOG::WriteFileLogRecord(CEXTLOG *this, struct _iobuf *a2, struct ILogScripting *a3, char a4)
{
  __int64 v4; // r14
  void *v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdx
  unsigned int v12; // ebx
  int v13; // r12d
  __int64 i; // rbx
  SAFEARRAY *v15; // r15
  int v16; // ebx
  const unsigned __int16 *v17; // rdx
  const char *v18; // rax
  __int64 v19; // rax
  int v20; // r8d
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rbx
  __int16 v28; // cx
  __int64 v29; // rax
  const unsigned __int16 **v30; // rcx
  unsigned __int16 v31; // r9
  const unsigned __int16 **v32; // r8
  const unsigned __int16 *v33; // rdx
  char *v34; // rax
  const unsigned __int16 **v35; // rax
  const unsigned __int16 *v36; // rdx
  __int64 v37; // rax
  int v38; // edi
  const unsigned __int16 *v39; // rdx
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rcx
  void *v42; // rsp
  void *v43; // rsp
  const char *v44; // r8
  __int64 v45; // rax
  __int64 v46; // rdx
  char *v47; // rcx
  int v48; // r12d
  SAFEARRAY *v49; // r15
  int v50; // ebx
  const unsigned __int16 *v51; // rdx
  const char *v52; // rax
  __int64 v53; // rax
  int v54; // r8d
  unsigned __int64 v55; // rcx
  unsigned __int64 v56; // rcx
  void *v57; // rsp
  void *v58; // rsp
  char v59[4]; // [rsp+40h] [rbp+0h] BYREF
  void *ppvData; // [rsp+48h] [rbp+8h] BYREF
  SAFEARRAY *v61; // [rsp+50h] [rbp+10h]
  FILE *Stream; // [rsp+58h] [rbp+18h]
  SAFEARRAY *psa[2]; // [rsp+60h] [rbp+20h] BYREF
  __int64 v64; // [rsp+70h] [rbp+30h]
  DOUBLE vtime[2]; // [rsp+78h] [rbp+38h] BYREF
  __int64 v66; // [rsp+88h] [rbp+48h]
  char *Source[18]; // [rsp+90h] [rbp+50h]
  struct _SYSTEMTIME SystemTime; // [rsp+120h] [rbp+E0h] BYREF
  char v69[32]; // [rsp+130h] [rbp+F0h] BYREF
  char Destination[4096]; // [rsp+150h] [rbp+110h] BYREF

  Stream = a2;
  v66 = 0;
  v4 = 0;
  v64 = 0;
  *(_OWORD *)vtime = 0;
  *(_OWORD *)psa = 0;
  SystemTime = 0;
  if ( !*((_DWORD *)this + 733) )
  {
    *((_DWORD *)this + 733) = 1;
    Source[0] = "c-ip";
    Source[1] = "cs-username";
    Source[2] = "s-sitename";
    Source[3] = "s-computername";
    Source[4] = "s-ip";
    Source[5] = "cs-method";
    Source[6] = "cs-uri-stem";
    Source[7] = "cs-uri-query";
    Source[8] = "sc-status";
    Source[9] = "sc-win32-status";
    Source[10] = "sc-bytes";
    Source[11] = "cs-bytes";
    Source[12] = "time-taken";
    Source[13] = "s-port";
    Source[14] = "cs-version";
    Source[15] = "cs(User-Agent)";
    Source[16] = "cs(Cookie)";
    Source[17] = "cs(Referer)";
    v8 = operator new(0x3F0u);
    *((_QWORD *)this + 296) = v8;
    if ( v8 )
    {
      do
      {
        v9 = 56 * v4;
        strcpy_s((char *)(56 * v4 + *((_QWORD *)this + 296)), 0x20u, Source[v4]);
        ++v4;
        *(_DWORD *)(*((_QWORD *)this + 296) + v9 + 40) = 0;
      }
      while ( v4 != 18 );
      v4 = 0;
    }
  }
  v10 = *((_QWORD *)this + 296);
  if ( !v10 )
    return 2147942414LL;
  v12 = -2147467259;
  if ( (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 128LL))(a3, v10 + 32) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 136LL))(
         a3,
         *((_QWORD *)this + 296) + 88LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 112LL))(
         a3,
         *((_QWORD *)this + 296) + 144LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 120LL))(
         a3,
         *((_QWORD *)this + 296) + 200LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 144LL))(
         a3,
         *((_QWORD *)this + 296) + 256LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 152LL))(
         a3,
         *((_QWORD *)this + 296) + 312LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 160LL))(
         a3,
         *((_QWORD *)this + 296) + 368LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 168LL))(
         a3,
         *((_QWORD *)this + 296) + 424LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 208LL))(
         a3,
         *((_QWORD *)this + 296) + 480LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 200LL))(
         a3,
         *((_QWORD *)this + 296) + 536LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 184LL))(
         a3,
         *((_QWORD *)this + 296) + 592LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 192LL))(
         a3,
         *((_QWORD *)this + 296) + 648LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 176LL))(
         a3,
         *((_QWORD *)this + 296) + 704LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 216LL))(
         a3,
         *((_QWORD *)this + 296) + 760LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 224LL))(
         a3,
         *((_QWORD *)this + 296) + 816LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 232LL))(
         a3,
         *((_QWORD *)this + 296) + 872LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 240LL))(
         a3,
         *((_QWORD *)this + 296) + 928LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, __int64))(*(_QWORD *)a3 + 248LL))(
         a3,
         *((_QWORD *)this + 296) + 984LL) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, SAFEARRAY **))(*(_QWORD *)a3 + 256LL))(a3, psa) < 0
    || (*(int (__fastcall **)(struct ILogScripting *, DOUBLE *))(*(_QWORD *)a3 + 104LL))(a3, vtime) < 0
    || !VariantTimeToSystemTime(vtime[1], &SystemTime) )
  {
    return v12;
  }
  v61 = 0;
  *(_DWORD *)v59 = 0;
  ppvData = 0;
  v13 = 0;
  strcpy_s(Destination, 0x1000u, "date time");
  for ( i = 0; i != 18; ++i )
  {
    if ( *(_WORD *)(56 * i + *((_QWORD *)this + 296) + 32) != 1 )
    {
      strcat_s(Destination, 0x1000u, " ");
      strcat_s(Destination, 0x1000u, (const char *)(56 * i + *((_QWORD *)this + 296)));
    }
  }
  if ( LOWORD(psa[0]) == 8200 )
  {
    v15 = psa[1];
    v61 = psa[1];
    if ( psa[1] )
    {
      v13 = *(_DWORD *)&psa[1][1].cDims;
      *(_DWORD *)v59 = v13;
    }
    if ( SafeArrayAccessData(psa[1], &ppvData) >= 0 )
    {
      v16 = 0;
      if ( v13 > 0 )
      {
        do
        {
          strcat_s(Destination, 0x1000u, " ");
          v17 = (const unsigned __int16 *)*((_QWORD *)ppvData + (unsigned int)v16);
          if ( v17 )
          {
            v19 = -1;
            do
              ++v19;
            while ( v17[v19] );
            v20 = 2 * v19 + 2;
            v21 = v20 + 15LL;
            if ( v21 <= v20 )
              v21 = 0xFFFFFFFFFFFFFF0LL;
            v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
            v23 = alloca(v22);
            v24 = alloca(v22);
            v18 = AtlW2AHelper(v59, v17, v20);
          }
          else
          {
            v18 = 0;
          }
          strcat_s(Destination, 0x1000u, v18);
          ++v16;
        }
        while ( v16 < v13 );
        v15 = v61;
      }
      SafeArrayUnaccessData(v15);
    }
  }
  CACHED_DATETIME_FORMATS::GetFormattedDateTime((CEXTLOG *)((char *)this + 1176), &SystemTime, v69);
  if ( a4 || strcmp(Destination, *((const char **)this + 301)) )
  {
    STR::Copy((CEXTLOG *)((char *)this + 2376), Destination);
    v25 = -1;
    do
      ++v25;
    while ( v69[v25] );
    sprintf_s(
      Destination,
      0x1000u,
      "#Software: Microsoft Internet Information Services 5.0\n#Version: %s\n#Date: %s %s\n#Fields: %s\n",
      "1.0",
      v69,
      &v69[v25 + 1],
      *((const char **)this + 301));
  }
  else
  {
    Destination[0] = 0;
  }
  strcat_s(Destination, 0x1000u, v69);
  strcat_s(Destination, 0x1000u, " ");
  v26 = -1;
  do
    ++v26;
  while ( v69[v26] );
  strcat_s(Destination, 0x1000u, &v69[v26 + 1]);
  v27 = 0;
  do
  {
    v28 = *(_WORD *)(v27 + *((_QWORD *)this + 296) + 32);
    if ( !v28 )
    {
      v44 = " -";
LABEL_80:
      strcat_s(Destination, 0x1000u, v44);
      goto LABEL_81;
    }
    if ( v28 != 3 )
    {
      if ( v28 != 8 )
        goto LABEL_81;
      strcat_s(Destination, 0x1000u, " ");
      v29 = *((_QWORD *)this + 296);
      v30 = (const unsigned __int16 **)((char *)this + 1160);
      v31 = *(_WORD *)(v29 + v27 + 32);
      v32 = (const unsigned __int16 **)(v27 + v29 + 40);
      if ( v31 < 2u )
        v33 = *v30;
      else
        v33 = *v32;
      if ( v33 )
      {
        v35 = (const unsigned __int16 **)((char *)this + 1160);
        if ( v31 >= 2u )
          v35 = v32;
        v36 = *v35;
        v37 = -1;
        do
          ++v37;
        while ( v36[v37] );
        v38 = 2 * v37 + 2;
        if ( v31 >= 2u )
          v30 = v32;
        v39 = *v30;
        v40 = v38 + 15LL;
        if ( v40 < v38 )
          v40 = 0xFFFFFFFFFFFFFF0LL;
        v41 = v40 & 0xFFFFFFFFFFFFFFF0uLL;
        v42 = alloca(v41);
        v43 = alloca(v41);
        v34 = AtlW2AHelper(v59, v39, v38);
      }
      else
      {
        v34 = 0;
      }
      v44 = v34;
      goto LABEL_80;
    }
    strcat_s(Destination, 0x1000u, " ");
    v45 = -1;
    do
      ++v45;
    while ( Destination[v45] );
    v46 = *((_QWORD *)this + 296);
    v47 = &Destination[v45];
    if ( *(_WORD *)(v46 + v27 + 32) < 2u )
      *(_WORD *)v47 = 45;
    else
      FastDwToA(v47, *(_DWORD *)(v46 + v27 + 40));
LABEL_81:
    ++v4;
    v27 += 56;
  }
  while ( v4 != 18 );
  v48 = *(_DWORD *)v59;
  v49 = v61;
  if ( *(int *)v59 > 0 && SafeArrayAccessData(v61, &ppvData) >= 0 )
  {
    v50 = 0;
    do
    {
      strcat_s(Destination, 0x1000u, " ");
      v51 = (const unsigned __int16 *)*((_QWORD *)ppvData + v48 + v50);
      if ( v51 )
      {
        v53 = -1;
        do
          ++v53;
        while ( v51[v53] );
        v54 = 2 * v53 + 2;
        v55 = v54 + 15LL;
        if ( v55 <= v54 )
          v55 = 0xFFFFFFFFFFFFFF0LL;
        v56 = v55 & 0xFFFFFFFFFFFFFFF0uLL;
        v57 = alloca(v56);
        v58 = alloca(v56);
        v52 = AtlW2AHelper(v59, v51, v54);
      }
      else
      {
        v52 = 0;
      }
      strcat_s(Destination, 0x1000u, v52);
      ++v50;
    }
    while ( v50 < v48 );
    SafeArrayUnaccessData(v49);
  }
  fprintf(Stream, "%s\n", Destination);
  return 0;
}

```

## disassembly

```asm
0x180006870  push    rbp
0x180006872  push    rsi
0x180006873  push    rdi
0x180006874  push    r12
0x180006876  push    r13
0x180006878  push    r14
0x18000687a  push    r15
0x18000687c  mov     eax, 1160h
0x180006881  call    _alloca_probe
0x180006886  sub     rsp, rax
0x180006889  lea     rbp, [rsp+40h]
0x18000688e  mov     [rbp+1150h+arg_18], rbx
0x180006895  mov     rax, cs:__security_cookie
0x18000689c  xor     rax, rbp
0x18000689f  mov     [rbp+1150h+var_40], rax
0x1800068a6  xor     eax, eax
0x1800068a8  mov     [rbp+1150h+Stream], rdx
0x1800068ac  xorps   xmm0, xmm0
0x1800068af  mov     [rbp+1150h+var_1108], rax
0x1800068b3  xor     r14d, r14d
0x1800068b6  mov     [rbp+1150h+var_1120], rax
0x1800068ba  xorps   xmm1, xmm1
0x1800068bd  mov     r13b, r9b
0x1800068c0  lea     r15d, [rax+1]
0x1800068c4  mov     rdi, r8
0x1800068c7  mov     rsi, rcx
0x1800068ca  movups  xmmword ptr [rbp+1150h+vtime], xmm0
0x1800068ce  movups  xmmword ptr [rbp+1150h+psa], xmm1
0x1800068d2  movups  xmmword ptr [rbp+1150h+SystemTime.wYear], xmm0
0x1800068d9  cmp     [rcx+0B74h], r14d
0x1800068e0  jnz     loc_180006A26
0x1800068e6  lea     rax, aCIp; "c-ip"
0x1800068ed  mov     [rcx+0B74h], r15d
0x1800068f4  mov     [rbp+1150h+Source], rax
0x1800068f8  mov     ecx, 3F0h; Size
0x1800068fd  lea     rax, aCsUsername; "cs-username"
0x180006904  mov     [rbp+1150h+var_10F8], rax
0x180006908  lea     rax, aSSitename; "s-sitename"
0x18000690f  mov     [rbp+1150h+var_10F0], rax
0x180006913  lea     rax, aSComputername; "s-computername"
0x18000691a  mov     [rbp+1150h+var_10E8], rax
0x18000691e  lea     rax, aSIp; "s-ip"
0x180006925  mov     [rbp+1150h+var_10E0], rax
0x180006929  lea     rax, aCsMethod; "cs-method"
0x180006930  mov     [rbp+1150h+var_10D8], rax
0x180006934  lea     rax, aCsUriStem; "cs-uri-stem"
0x18000693b  mov     [rbp+1150h+var_10D0], rax
0x180006942  lea     rax, aCsUriQuery; "cs-uri-query"
0x180006949  mov     [rbp+1150h+var_10C8], rax
0x180006950  lea     rax, aScStatus; "sc-status"
0x180006957  mov     [rbp+1150h+var_10C0], rax
0x18000695e  lea     rax, aScWin32Status; "sc-win32-status"
0x180006965  mov     [rbp+1150h+var_10B8], rax
0x18000696c  lea     rax, aScBytes; "sc-bytes"
0x180006973  mov     [rbp+1150h+var_10B0], rax
0x18000697a  lea     rax, aCsBytes; "cs-bytes"
0x180006981  mov     [rbp+1150h+var_10A8], rax
0x180006988  lea     rax, aTimeTaken; "time-taken"
0x18000698f  mov     [rbp+1150h+var_10A0], rax
0x180006996  lea     rax, aSPort; "s-port"
0x18000699d  mov     [rbp+1150h+var_1098], rax
0x1800069a4  lea     rax, aCsVersion; "cs-version"
0x1800069ab  mov     [rbp+1150h+var_1090], rax
0x1800069b2  lea     rax, aCsUserAgent; "cs(User-Agent)"
0x1800069b9  mov     [rbp+1150h+var_1088], rax
0x1800069c0  lea     rax, aCsCookie; "cs(Cookie)"
0x1800069c7  mov     [rbp+1150h+var_1080], rax
0x1800069ce  lea     rax, aCsReferer; "cs(Referer)"
0x1800069d5  mov     [rbp+1150h+var_1078], rax
0x1800069dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800069e1  mov     [rsi+940h], rax
0x1800069e8  test    rax, rax
0x1800069eb  jz      short loc_180006A26
0x1800069ed  mov     rcx, [rsi+940h]
0x1800069f4  mov     edx, 20h ; ' '; SizeInBytes
0x1800069f9  mov     r8, [rbp+r14*8+1150h+Source]; Source
0x1800069fe  imul    rbx, r14, 38h ; '8'
0x180006a02  add     rcx, rbx; Destination
0x180006a05  call    cs:__imp_strcpy_s
0x180006a0b  mov     rax, [rsi+940h]
0x180006a12  add     r14, r15
0x180006a15  mov     dword ptr [rax+rbx+28h], 0
0x180006a1d  cmp     r14, 12h
0x180006a21  jnz     short loc_1800069ED
0x180006a23  xor     r14d, r14d
0x180006a26  mov     rdx, [rsi+940h]
0x180006a2d  test    rdx, rdx
0x180006a30  jnz     short loc_180006A3C
0x180006a32  mov     eax, 8007000Eh
0x180006a37  jmp     loc_18000721F
0x180006a3c  mov     rax, [rdi]
0x180006a3f  add     rdx, 20h ; ' '
0x180006a43  mov     rcx, rdi
0x180006a46  mov     ebx, 80004005h
0x180006a4b  mov     rax, [rax+80h]
0x180006a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a57  test    eax, eax
0x180006a59  js      loc_18000721D
0x180006a5f  mov     rax, [rdi]
0x180006a62  mov     rcx, rdi
0x180006a65  mov     rdx, [rsi+940h]
0x180006a6c  add     rdx, 58h ; 'X'
0x180006a70  mov     rax, [rax+88h]
0x180006a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a7c  test    eax, eax
0x180006a7e  js      loc_18000721D
0x180006a84  mov     rax, [rdi]
0x180006a87  mov     rcx, rdi
0x180006a8a  mov     rdx, [rsi+940h]
0x180006a91  add     rdx, 90h
0x180006a98  mov     rax, [rax+70h]
0x180006a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aa1  test    eax, eax
0x180006aa3  js      loc_18000721D
0x180006aa9  mov     rax, [rdi]
0x180006aac  mov     rcx, rdi
0x180006aaf  mov     rdx, [rsi+940h]
0x180006ab6  add     rdx, 0C8h
0x180006abd  mov     rax, [rax+78h]
0x180006ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ac6  test    eax, eax
0x180006ac8  js      loc_18000721D
0x180006ace  mov     rax, [rdi]
0x180006ad1  mov     rcx, rdi
0x180006ad4  mov     rdx, [rsi+940h]
0x180006adb  add     rdx, 100h
0x180006ae2  mov     rax, [rax+90h]
0x180006ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aee  test    eax, eax
0x180006af0  js      loc_18000721D
0x180006af6  mov     rax, [rdi]
0x180006af9  mov     rcx, rdi
0x180006afc  mov     rdx, [rsi+940h]
0x180006b03  add     rdx, 138h
0x180006b0a  mov     rax, [rax+98h]
0x180006b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b16  test    eax, eax
0x180006b18  js      loc_18000721D
0x180006b1e  mov     rax, [rdi]
0x180006b21  mov     rcx, rdi
0x180006b24  mov     rdx, [rsi+940h]
0x180006b2b  add     rdx, 170h
0x180006b32  mov     rax, [rax+0A0h]
0x180006b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b3e  test    eax, eax
0x180006b40  js      loc_18000721D
0x180006b46  mov     rax, [rdi]
0x180006b49  mov     rcx, rdi
0x180006b4c  mov     rdx, [rsi+940h]
0x180006b53  add     rdx, 1A8h
0x180006b5a  mov     rax, [rax+0A8h]
0x180006b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b66  test    eax, eax
0x180006b68  js      loc_18000721D
0x180006b6e  mov     rax, [rdi]
0x180006b71  mov     rcx, rdi
0x180006b74  mov     rdx, [rsi+940h]
0x180006b7b  add     rdx, 1E0h
0x180006b82  mov     rax, [rax+0D0h]
0x180006b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b8e  test    eax, eax
0x180006b90  js      loc_18000721D
0x180006b96  mov     rax, [rdi]
0x180006b99  mov     rcx, rdi
0x180006b9c  mov     rdx, [rsi+940h]
0x180006ba3  add     rdx, 218h
0x180006baa  mov     rax, [rax+0C8h]
0x180006bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb6  test    eax, eax
0x180006bb8  js      loc_18000721D
0x180006bbe  mov     rax, [rdi]
0x180006bc1  mov     rcx, rdi
0x180006bc4  mov     rdx, [rsi+940h]
0x180006bcb  add     rdx, 250h
0x180006bd2  mov     rax, [rax+0B8h]
0x180006bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bde  test    eax, eax
0x180006be0  js      loc_18000721D
0x180006be6  mov     rax, [rdi]
0x180006be9  mov     rcx, rdi
0x180006bec  mov     rdx, [rsi+940h]
0x180006bf3  add     rdx, 288h
0x180006bfa  mov     rax, [rax+0C0h]
0x180006c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c06  test    eax, eax
0x180006c08  js      loc_18000721D
0x180006c0e  mov     rax, [rdi]
0x180006c11  mov     rcx, rdi
0x180006c14  mov     rdx, [rsi+940h]
0x180006c1b  add     rdx, 2C0h
0x180006c22  mov     rax, [rax+0B0h]
0x180006c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c2e  test    eax, eax
0x180006c30  js      loc_18000721D
0x180006c36  mov     rax, [rdi]
0x180006c39  mov     rcx, rdi
0x180006c3c  mov     rdx, [rsi+940h]
0x180006c43  add     rdx, 2F8h
0x180006c4a  mov     rax, [rax+0D8h]
0x180006c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c56  test    eax, eax
0x180006c58  js      loc_18000721D
0x180006c5e  mov     rax, [rdi]
0x180006c61  mov     rcx, rdi
0x180006c64  mov     rdx, [rsi+940h]
0x180006c6b  add     rdx, 330h
0x180006c72  mov     rax, [rax+0E0h]
0x180006c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7e  test    eax, eax
0x180006c80  js      loc_18000721D
0x180006c86  mov     rax, [rdi]
0x180006c89  mov     rcx, rdi
0x180006c8c  mov     rdx, [rsi+940h]
0x180006c93  add     rdx, 368h
0x180006c9a  mov     rax, [rax+0E8h]
0x180006ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ca6  test    eax, eax
0x180006ca8  js      loc_18000721D
0x180006cae  mov     rax, [rdi]
0x180006cb1  mov     rcx, rdi
0x180006cb4  mov     rdx, [rsi+940h]
0x180006cbb  add     rdx, 3A0h
0x180006cc2  mov     rax, [rax+0F0h]
0x180006cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cce  test    eax, eax
0x180006cd0  js      loc_18000721D
0x180006cd6  mov     rax, [rdi]
0x180006cd9  mov     rcx, rdi
0x180006cdc  mov     rdx, [rsi+940h]
0x180006ce3  add     rdx, 3D8h
0x180006cea  mov     rax, [rax+0F8h]
0x180006cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cf6  test    eax, eax
0x180006cf8  js      loc_18000721D
0x180006cfe  mov     rax, [rdi]
0x180006d01  lea     rdx, [rbp+1150h+psa]
0x180006d05  mov     rcx, rdi
0x180006d08  mov     rax, [rax+100h]
0x180006d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d14  test    eax, eax
0x180006d16  js      loc_18000721D
0x180006d1c  mov     rax, [rdi]
0x180006d1f  lea     rdx, [rbp+1150h+vtime]
0x180006d23  mov     rcx, rdi
0x180006d26  mov     rax, [rax+68h]
0x180006d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d2f  test    eax, eax
0x180006d31  js      loc_18000721D
0x180006d37  movsd   xmm0, [rbp+1150h+vtime+8]; vtime
0x180006d3c  lea     rdx, [rbp+1150h+SystemTime]; lpSystemTime
0x180006d43  call    cs:__imp_VariantTimeToSystemTime
0x180006d49  test    eax, eax
0x180006d4b  jz      loc_18000721D
0x180006d51  lea     r8, aDateTime; "date time"
0x180006d58  mov     [rbp+1150h+var_1140], r14
0x180006d5c  mov     edx, 1000h; SizeInBytes
0x180006d61  mov     dword ptr [rbp+1150h+var_1150], r14d
0x180006d65  lea     rcx, [rbp+1150h+Destination]; Destination
0x180006d6c  mov     [rbp+1150h+ppvData], r14
0x180006d70  mov     r12d, r14d
0x180006d73  call    cs:__imp_strcpy_s
0x180006d79  mov     rbx, r14
0x180006d7c  mov     rax, [rsi+940h]
0x180006d83  imul    rdi, rbx, 38h ; '8'
0x180006d87  cmp     r15w, [rdi+rax+20h]
0x180006d8d  jz      short loc_180006DC8
0x180006d8f  lea     r8, asc_18001360C; " "
0x180006d96  mov     edx, 1000h; SizeInBytes
0x180006d9b  lea     rcx, [rbp+1150h+Destination]; Destination
0x180006da2  call    cs:__imp_strcat_s
0x180006da8  mov     r8, [rsi+940h]
0x180006daf  lea     rcx, [rbp+1150h+Destination]; Destination
0x180006db6  add     r8, rdi; Source
0x180006db9  mov     edi, 1000h
0x180006dbe  mov     edx, edi; SizeInBytes
0x180006dc0  call    cs:__imp_strcat_s
0x180006dc6  jmp     short loc_180006DCD
0x180006dc8  mov     edi, 1000h
0x180006dcd  add     rbx, r15
0x180006dd0  cmp     rbx, 12h
0x180006dd4  jnz     short loc_180006D7C
0x180006dd6  mov     eax, 2008h
0x180006ddb  cmp     ax, word ptr [rbp+1150h+psa]
0x180006ddf  jnz     loc_180006EB9
0x180006de5  mov     r15, [rbp+1150h+psa+8]
0x180006de9  mov     [rbp+1150h+var_1140], r15
0x180006ded  test    r15, r15
0x180006df0  jz      short loc_180006DFA
0x180006df2  mov     r12d, [r15+20h]
0x180006df6  mov     dword ptr [rbp+1150h+var_1150], r12d
0x180006dfa  lea     rdx, [rbp+1150h+ppvData]; ppvData
0x180006dfe  mov     rcx, r15; psa
0x180006e01  call    cs:__imp_SafeArrayAccessData
0x180006e07  test    eax, eax
0x180006e09  js      loc_180006EB9
0x180006e0f  mov     ebx, r14d
0x180006e12  test    r12d, r12d
0x180006e15  jle     loc_180006EB0
0x180006e1b  mov     r15, 0FFFFFFFFFFFFFF0h
0x180006e25  lea     r8, asc_18001360C; " "
  ... truncated ...
```
