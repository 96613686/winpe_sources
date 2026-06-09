# SetExternalPropsFromInitString(IDBProperties *,CCMProviderInfo *,CCompiledInitString &)

- ea: `0x180014970`
- end: `0x1800150a6`
- name: `?SetExternalPropsFromInitString@@YAJPEAUIDBProperties@@PEAVCCMProviderInfo@@AEAVCCompiledInitString@@@Z`
- size: `1846`
- prototype: `int(struct IDBProperties *, struct CCMProviderInfo *, struct CCompiledInitString *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013ff4`
- `0x18006b430`

## callees

- `0x18000fbe0`
- `0x180013870`
- `0x180014970`
- `0x1800150ac`
- `0x180015170`
- `0x180015504`
- `0x180015704`
- `0x180029560`
- `0x1800296b0`
- `0x18002ec0c`
- `0x180062670`
- `0x180087010`

## import_xrefs

- `msvcrt!iswspace` at `0x180014dea`
- `msvcrt!iswspace` at `0x180014dea`
- `MSDART!mpMalloc` at `0x180014db7`
- `MSDART!mpMalloc` at `0x180014db7`
- `MSDART!mpFree` at `0x180014baa`
- `MSDART!mpFree` at `0x180014baa`
- `ole32!CoTaskMemFree` at `0x180014c0c`
- `ole32!CoTaskMemFree` at `0x180014c39`
- `ole32!CoTaskMemFree` at `0x180014c0c`
- `ole32!CoTaskMemFree` at `0x180014c39`

## string_xrefs

- `0x180014e8d`: `<CCompiledInitString::GatherExtendedProperties|OLEDB|ERR> `
- `0x180014a26`: `<CCompiledInitString::GatherExtendedProperties|Trace|HR> `

## pseudocode

```c
__int64 __fastcall SetExternalPropsFromInitString(
        struct IDBProperties *a1,
        struct CCMProviderInfo *a2,
        struct CCompiledInitString *a3)
{
  unsigned __int16 *v6; // r13
  struct CDSLPropertySetArray *v7; // rdx
  unsigned int SetArrayShape; // eax
  int v9; // ebx
  struct CCMProviderInfoManager *v10; // r8
  int v11; // ebx
  __int64 v12; // rbx
  __int64 v13; // rdx
  int v14; // r15d
  int v15; // r15d
  int v16; // esi
  int v17; // esi
  char *v18; // r14
  unsigned int v19; // esi
  unsigned __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23; // r15d
  unsigned __int16 *v24; // rax
  void *v25; // rsi
  char *j; // rbx
  char *v28; // rcx
  int v29; // ebx
  char *k; // rdi
  char *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rax
  unsigned __int16 *v34; // r15
  unsigned __int16 *v35; // r13
  unsigned int i; // ecx
  wint_t *v37; // rcx
  int v38; // eax
  __int64 v39; // rax
  unsigned __int16 *v40; // rax
  int v41; // eax
  bool v42; // zf
  unsigned int v43; // ebx
  __int64 v44; // [rsp+0h] [rbp-D8h] BYREF
  __int64 v45; // [rsp+30h] [rbp-A8h]
  unsigned int v46; // [rsp+40h] [rbp-98h]
  unsigned __int16 *v47; // [rsp+48h] [rbp-90h] BYREF
  wint_t *v48; // [rsp+50h] [rbp-88h]
  int v49; // [rsp+58h] [rbp-80h] BYREF
  LPVOID v50; // [rsp+60h] [rbp-78h]
  int v51; // [rsp+68h] [rbp-70h] BYREF
  int v52; // [rsp+6Ch] [rbp-6Ch] BYREF
  int v53; // [rsp+70h] [rbp-68h] BYREF
  unsigned int v54; // [rsp+74h] [rbp-64h]
  int v55; // [rsp+78h] [rbp-60h] BYREF
  int pExceptionObject; // [rsp+7Ch] [rbp-5Ch] BYREF
  int v57; // [rsp+80h] [rbp-58h] BYREF
  unsigned int v58; // [rsp+84h] [rbp-54h] BYREF
  unsigned __int64 v59; // [rsp+88h] [rbp-50h] BYREF
  unsigned __int16 *v60; // [rsp+90h] [rbp-48h] BYREF
  unsigned int v61; // [rsp+98h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-38h]
  __int64 v63; // [rsp+A8h] [rbp-30h]
  int v64; // [rsp+F8h] [rbp+20h]
  unsigned int v65; // [rsp+F8h] [rbp+20h]

  try
  {
    v6 = 0;
    v47 = 0;
    v49 = 0;
    v50 = 0;
    v61 = 0;
    pv = 0;
    v7 = (struct CCMProviderInfo *)((char *)a2 + 1208);
    if ( (bidGblFlags & 2) != 0 )
    {
      SetArrayShape = CDPOPropertySetArray::LoadSetArrayShape((CDPOPropertySetArray *)&v49, v7);
      v9 = bidTraceHR(off_1800C8430[0], 1855497, L"<CCMProviderInfo::CloneInitProps|Trace|HR> ", SetArrayShape);
    }
    else
    {
      v9 = CDPOPropertySetArray::LoadSetArrayShape((CDPOPropertySetArray *)&v49, v7);
    }
    if ( v9 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v9, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x33Au);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v9, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x33Au);
          if ( (bidGblFlags & 2) != 0 )
            v9 = bidTraceHR(off_1800C8468[0], 845833, L"<SetExternalPropsFromInitString|Trace|HR> ", (unsigned int)v9);
        }
      }
      v51 = v9;
      throw (long *)&v51;
    }
    v11 = CCompiledInitString::IndexProviderProps(a3, a2, v10);
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v11, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x33Du);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v11, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x33Du);
          if ( (bidGblFlags & 2) != 0 )
            v11 = bidTraceHR(off_1800C8468[0], 848905, L"<SetExternalPropsFromInitString|Trace|HR> ", (unsigned int)v11);
        }
      }
      v52 = v11;
      throw (long *)&v52;
    }
    v12 = -1;
    if ( !*((_QWORD *)a3 + 3) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v13 = 842761;
        v14 = 0;
        goto LABEL_9;
      }
      goto LABEL_10;
    }
    v32 = *((unsigned int *)a3 + 5);
    v54 = *((_DWORD *)a3 + 5);
    v33 = *((_QWORD *)a3 + 1);
    v34 = 0;
    v35 = 0;
    v60 = 0;
    v59 = 0;
    for ( i = 0; ; ++i )
    {
      v46 = i;
      v63 = v33;
      if ( i >= (unsigned int)v32 )
      {
        if ( v34 && *(v35 - 1) == 59 )
          *(v35 - 1) = 0;
        v6 = v34;
        v47 = v34;
        goto LABEL_10;
      }
      if ( *(_DWORD *)(v33 + 48) == -1 && *(_DWORD *)(v33 + 52) == -1 )
        break;
LABEL_63:
      v33 += 56;
    }
    v37 = *(wint_t **)v33;
    v48 = *(wint_t **)v33;
    v38 = *(_DWORD *)(v33 + 8);
    v64 = v38;
    if ( v34 )
    {
LABEL_59:
      while ( v38 )
      {
        v41 = iswspace(*v37);
        v37 = v48;
        v42 = v41 == 0;
        v38 = v64;
        if ( v42 )
          break;
        v38 = v64 - 1;
        v64 = v38;
        v37 = ++v48;
      }
      LODWORD(v45) = v38;
      StringCchPrintfExW(v35, v59, &v60, &v59, 0, L"%.*ls;", v45, v37);
      v35 = v60;
      v33 = v63;
      i = v46;
      v32 = v54;
      goto LABEL_63;
    }
    v39 = -1;
    do
      ++v39;
    while ( *(_WORD *)(*((_QWORD *)a3 + 3) + 2 * v39) );
    v59 = v39 + 2;
    v40 = (unsigned __int16 *)mpMalloc(2 * (v39 + 2), v32);
    v34 = v40;
    if ( v40 )
    {
      v35 = v40;
      v60 = v40;
      *v40 = 0;
      v38 = v64;
      v37 = v48;
      goto LABEL_59;
    }
    v14 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<CCompiledInitString::GatherExtendedProperties|OLEDB|ERR> ", 0x358u);
      if ( (bidGblFlags & 2) != 0 )
      {
        v13 = 876553;
        v6 = v47;
LABEL_9:
        v14 = bidTraceHR(
                off_1800C8430[0],
                v13,
                L"<CCompiledInitString::GatherExtendedProperties|Trace|HR> ",
                (unsigned int)v14);
        if ( v14 >= 0 )
        {
LABEL_10:
          v15 = CCompiledInitString::SetNonExtendedProperties(a3, a2, (struct CDSLPropertySetArray *)&v49, 0);
          if ( v15 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v15, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x344u);
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v15, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x344u);
                if ( (bidGblFlags & 2) != 0 )
                  v15 = bidTraceHR(
                          off_1800C8468[0],
                          856073,
                          L"<SetExternalPropsFromInitString|Trace|HR> ",
                          (unsigned int)v15);
              }
            }
            v55 = v15;
            throw (long *)&v55;
          }
          if ( v6 || *((_DWORD *)a3 + 34) || *((_QWORD *)a3 + 16) )
          {
            v16 = CCompiledInitString::SetExtendedProperties(a3, a2, (struct CDSLPropertySetArray *)&v49, &v47, 0);
            if ( v16 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v16, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x349u);
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v16, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x349u);
                  if ( (bidGblFlags & 2) != 0 )
                    v16 = bidTraceHR(
                            off_1800C8468[0],
                            861193,
                            L"<SetExternalPropsFromInitString|Trace|HR> ",
                            (unsigned int)v16);
                }
              }
              pExceptionObject = v16;
              throw (long *)&pExceptionObject;
            }
            v6 = v47;
          }
          v17 = CDPOPropertySetArray::CopyTouchedProps(
                  (CDPOPropertySetArray *)&v61,
                  (struct CDPOPropertySetArray *)&v49);
          if ( v17 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v17, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x34Cu);
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v17, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x34Cu);
                if ( (bidGblFlags & 2) != 0 )
                  v17 = bidTraceHR(
                          off_1800C8468[0],
                          864265,
                          L"<SetExternalPropsFromInitString|Trace|HR> ",
                          (unsigned int)v17);
              }
            }
            v57 = v17;
            throw (long *)&v57;
          }
          v18 = (char *)pv;
          v19 = v61;
          v23 = ((__int64 (__fastcall *)(struct IDBProperties *, _QWORD, LPVOID))a1->lpVtbl->SetProperties)(a1, v61, pv);
          if ( v23 == 265946 )
            v23 = -2147217887;
          goto LABEL_94;
        }
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v14, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x341u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v14, L"<SetExternalPropsFromInitString|OLEDB|ERR> ", 0x341u);
            if ( (bidGblFlags & 2) != 0 )
              v14 = bidTraceHR(
                      off_1800C8468[0],
                      853001,
                      L"<SetExternalPropsFromInitString|Trace|HR> ",
                      (unsigned int)v14);
          }
        }
      }
    }
    v53 = v14;
    throw (long *)&v53;
  }
  catch ( long v58 )
  {
    v20 = (unsigned __int64)&v44;
    if ( (bidGblFlags & 2) != 0 && off_1800C8AF0[0] )
    {
      v43 = v58;
      bidTraceA(off_1800C8468[0], 874496, off_1800C8AF0[0], v58);
    }
    else
    {
      v43 = v58;
    }
    v65 = v43;
    v12 = -1;
    v23 = v65;
    v18 = (char *)pv;
    v19 = v61;
    v6 = v47;
  }
LABEL_94:
  if ( v6 )
  {
    v24 = v6;
    if ( *v6 )
    {
      do
      {
        if ( !v12 )
          break;
        *v24++ = 0;
        --v12;
        v20 = *v24;
      }
      while ( (_WORD)v20 );
    }
    mpFree(v6, v20, v21, v22);
  }
  if ( v18 )
  {
    for ( j = v18; v19; --v19 )
    {
      v28 = j;
      j += 32;
      TDSLSet<tagDBPROPSET,CDSLProperty>::Free(v28, 1);
    }
    CoTaskMemFree(v18);
  }
  v25 = v50;
  if ( v50 )
  {
    v29 = v49;
    for ( k = (char *)v50; v29; --v29 )
    {
      v31 = k;
      k += 32;
      TDSLSet<tagDBPROPSET,CDSLProperty>::Free(v31, 1);
    }
    CoTaskMemFree(v25);
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8468[0], 886793, L"<SetExternalPropsFromInitString|Trace|HR> ", v23);
  return v23;
}

```

## disassembly

```asm
0x180014970  mov     rax, rsp
0x180014973  mov     [rax+8], rbx
0x180014977  mov     [rax+10h], rsi
0x18001497b  push    rdi
0x18001497c  push    r12
0x18001497e  push    r13
0x180014980  push    r14
0x180014982  push    r15
0x180014984  sub     rsp, 0B0h
0x18001498b  mov     rsi, r8
0x18001498e  mov     r14, rdx
0x180014991  mov     r12, rcx
0x180014994  xor     edi, edi
0x180014996  mov     r13d, edi
0x180014999  mov     [rsp+0D8h+var_90], rdi
0x18001499e  mov     [rax-80h], edi
0x1800149a1  mov     [rax-78h], rdi
0x1800149a5  mov     [rax-40h], edi
0x1800149a8  mov     [rax-38h], rdi
0x1800149ac  add     rdx, 4B8h; struct CDSLPropertySetArray *
0x1800149b3  lea     rcx, [rax-80h]; this
0x1800149b7  test    byte ptr cs:_bidGblFlags, 2
0x1800149be  jz      loc_180014B1B
0x1800149c4  call    ?LoadSetArrayShape@CDPOPropertySetArray@@QEAAJAEAVCDSLPropertySetArray@@@Z; CDPOPropertySetArray::LoadSetArrayShape(CDSLPropertySetArray &)
0x1800149c9  mov     rcx, cs:off_1800C8430; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800149d0  mov     r9d, eax
0x1800149d3  lea     r8, aCcmproviderinf_5; "<CCMProviderInfo::CloneInitProps|Trace|"...
0x1800149da  mov     edx, 1C5009h
0x1800149df  call    _bidTraceHR
0x1800149e4  mov     ebx, eax
0x1800149e6  test    ebx, ebx
0x1800149e8  js      loc_180014C44
0x1800149ee  mov     rdx, r14; struct CCMProviderInfo *
0x1800149f1  mov     rcx, rsi; this
0x1800149f4  call    ?IndexProviderProps@CCompiledInitString@@QEAAJPEAVCCMProviderInfo@@PEAVCCMProviderInfoManager@@@Z; CCompiledInitString::IndexProviderProps(CCMProviderInfo *,CCMProviderInfoManager *)
0x1800149f9  mov     ebx, eax
0x1800149fb  test    eax, eax
0x1800149fd  js      loc_180014CBC
0x180014a03  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180014a0a  cmp     qword ptr [rsi+18h], 0
0x180014a0f  jnz     loc_180014D34
0x180014a15  test    byte ptr cs:_bidGblFlags, 2
0x180014a1c  jz      short loc_180014A47
0x180014a1e  mov     edx, 0CDC09h
0x180014a23  mov     r15d, edi
0x180014a26  lea     r8, aCcompiledinits_8; "<CCompiledInitString::GatherExtendedPro"...
0x180014a2d  mov     rcx, cs:off_1800C8430; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180014a34  mov     r9d, r15d
0x180014a37  call    _bidTraceHR
0x180014a3c  mov     r15d, eax
0x180014a3f  test    eax, eax
0x180014a41  js      loc_180014EB5
0x180014a47  xor     r9d, r9d; int
0x180014a4a  lea     r8, [rsp+0D8h+var_80]; struct CDSLPropertySetArray *
0x180014a4f  mov     rdx, r14; struct CCMProviderInfo *
0x180014a52  mov     rcx, rsi; this
0x180014a55  call    ?SetNonExtendedProperties@CCompiledInitString@@QEAAJPEAVCCMProviderInfo@@AEAVCDSLPropertySetArray@@H@Z; CCompiledInitString::SetNonExtendedProperties(CCMProviderInfo *,CDSLPropertySetArray &,int)
0x180014a5a  mov     r15d, eax
0x180014a5d  test    eax, eax
0x180014a5f  js      loc_180014F54
0x180014a65  test    r13, r13
0x180014a68  jnz     short loc_180014A80
0x180014a6a  cmp     [rsi+88h], r13d
0x180014a71  jnz     short loc_180014A80
0x180014a73  cmp     [rsi+80h], r13
0x180014a7a  jz      loc_180014B27
0x180014a80  mov     [rsp+0D8h+var_B8], edi; int
0x180014a84  lea     r9, [rsp+0D8h+var_90]; unsigned __int16 **
0x180014a89  lea     r8, [rsp+0D8h+var_80]; struct CDSLPropertySetArray *
0x180014a8e  mov     rdx, r14; struct CCMProviderInfo *
0x180014a91  mov     rcx, rsi; this
0x180014a94  call    ?SetExtendedProperties@CCompiledInitString@@QEAAJPEAVCCMProviderInfo@@AEAVCDSLPropertySetArray@@PEAPEAGH@Z; CCompiledInitString::SetExtendedProperties(CCMProviderInfo *,CDSLPropertySetArray &,ushort * *,int)
0x180014a99  mov     esi, eax
0x180014a9b  test    eax, eax
0x180014a9d  jns     loc_180014FD0
0x180014aa3  mov     eax, cs:_bidGblFlags
0x180014aa9  test    al, 2
0x180014aab  jz      short loc_180014B06
0x180014aad  mov     r8d, 349h; unsigned int
0x180014ab3  lea     rdx, aSetexternalpro; "<SetExternalPropsFromInitString|OLEDB|E"...
0x180014aba  mov     ecx, esi; int
0x180014abc  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180014ac1  mov     eax, cs:_bidGblFlags
0x180014ac7  test    al, 2
0x180014ac9  jz      short loc_180014B06
0x180014acb  mov     r8d, 349h; unsigned int
0x180014ad1  lea     rdx, aSetexternalpro; "<SetExternalPropsFromInitString|OLEDB|E"...
0x180014ad8  mov     ecx, esi; int
0x180014ada  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180014adf  mov     eax, cs:_bidGblFlags
0x180014ae5  test    al, 2
0x180014ae7  jz      short loc_180014B06
0x180014ae9  mov     r9d, esi
0x180014aec  lea     r8, aSetexternalpro_1; "<SetExternalPropsFromInitString|Trace|H"...
0x180014af3  mov     edx, 0D2409h
0x180014af8  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180014aff  call    _bidTraceHR
0x180014b04  mov     esi, eax
0x180014b06  mov     [rsp+0D8h+pExceptionObject], esi
0x180014b0a  lea     rdx, _TI1J; pThrowInfo
0x180014b11  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180014b16  call    _CxxThrowException_0
0x180014b1b  call    ?LoadSetArrayShape@CDPOPropertySetArray@@QEAAJAEAVCDSLPropertySetArray@@@Z; CDPOPropertySetArray::LoadSetArrayShape(CDSLPropertySetArray &)
0x180014b20  mov     ebx, eax
0x180014b22  jmp     loc_1800149E6
0x180014b27  lea     rdx, [rsp+0D8h+var_80]; struct CDPOPropertySetArray *
0x180014b2c  lea     rcx, [rsp+0D8h+var_40]; this
0x180014b34  call    ?CopyTouchedProps@CDPOPropertySetArray@@QEAAJAEAV1@@Z; CDPOPropertySetArray::CopyTouchedProps(CDPOPropertySetArray &)
0x180014b39  mov     esi, eax
0x180014b3b  test    eax, eax
0x180014b3d  js      loc_180014FDA
0x180014b43  mov     rax, [r12]
0x180014b47  mov     r14, [rsp+0D8h+pv]
0x180014b4f  mov     r8, r14
0x180014b52  mov     esi, [rsp+0D8h+var_40]
0x180014b59  mov     edx, esi
0x180014b5b  mov     rcx, r12
0x180014b5e  mov     rax, [rax+28h]
0x180014b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b67  mov     r15d, eax
0x180014b6a  mov     eax, 80040E21h
0x180014b6f  cmp     r15d, 40EDAh
0x180014b76  cmovz   r15d, eax
0x180014b7a  test    r13, r13
0x180014b7d  jz      short loc_180014BB0
0x180014b7f  mov     rax, r13
0x180014b82  movzx   ecx, word ptr [r13+0]
0x180014b87  test    cx, cx
0x180014b8a  jz      short loc_180014BA7
0x180014b8c  nop     dword ptr [rax+00h]
0x180014b90  test    rbx, rbx
0x180014b93  jz      short loc_180014BA7
0x180014b95  mov     [rax], di
0x180014b98  add     rax, 2
0x180014b9c  dec     rbx
0x180014b9f  movzx   edx, word ptr [rax]
0x180014ba2  test    dx, dx
0x180014ba5  jnz     short loc_180014B90
0x180014ba7  mov     rcx, r13
0x180014baa  call    cs:__imp_mpFree
0x180014bb0  test    r14, r14
0x180014bb3  jnz     short loc_180014BEC
0x180014bb5  mov     rsi, [rsp+0D8h+var_78]
0x180014bba  test    rsi, rsi
0x180014bbd  jnz     short loc_180014C14
0x180014bbf  test    byte ptr cs:_bidGblFlags, 2
0x180014bc6  jnz     loc_180015083
0x180014bcc  mov     eax, r15d
0x180014bcf  lea     r11, [rsp+0D8h+var_28]
0x180014bd7  mov     rbx, [r11+30h]
0x180014bdb  mov     rsi, [r11+38h]
0x180014bdf  mov     rsp, r11
0x180014be2  pop     r15
0x180014be4  pop     r14
0x180014be6  pop     r13
0x180014be8  pop     r12
0x180014bea  pop     rdi
0x180014beb  retn
0x180014bec  mov     rbx, r14
0x180014bef  test    esi, esi
0x180014bf1  jz      short loc_180014C09
0x180014bf3  mov     rcx, rbx
0x180014bf6  add     rbx, 20h ; ' '
0x180014bfa  mov     edx, 1
0x180014bff  call    ?Free@?$TDSLSet@UtagDBPROPSET@@VCDSLProperty@@@@QEAAXH@Z; TDSLSet<tagDBPROPSET,CDSLProperty>::Free(int)
0x180014c04  sub     esi, 1
0x180014c07  jnz     short loc_180014BF3
0x180014c09  mov     rcx, r14; pv
0x180014c0c  call    cs:__imp_CoTaskMemFree
0x180014c12  jmp     short loc_180014BB5
0x180014c14  mov     ebx, [rsp+0D8h+var_80]
0x180014c18  mov     rdi, rsi
0x180014c1b  test    ebx, ebx
0x180014c1d  jz      short loc_180014C36
0x180014c1f  nop
0x180014c20  mov     rcx, rdi
0x180014c23  add     rdi, 20h ; ' '
0x180014c27  mov     edx, 1
0x180014c2c  call    ?Free@?$TDSLSet@UtagDBPROPSET@@VCDSLProperty@@@@QEAAXH@Z; TDSLSet<tagDBPROPSET,CDSLProperty>::Free(int)
0x180014c31  sub     ebx, 1
0x180014c34  jnz     short loc_180014C20
0x180014c36  mov     rcx, rsi; pv
0x180014c39  call    cs:__imp_CoTaskMemFree
0x180014c3f  jmp     loc_180014BBF
0x180014c44  mov     eax, cs:_bidGblFlags
0x180014c4a  test    al, 2
0x180014c4c  jz      short loc_180014CA7
0x180014c4e  mov     r8d, 33Ah; unsigned int
0x180014c54  lea     rdx, aSetexternalpro; "<SetExternalPropsFromInitString|OLEDB|E"...
0x180014c5b  mov     ecx, ebx; int
0x180014c5d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180014c62  mov     eax, cs:_bidGblFlags
0x180014c68  test    al, 2
0x180014c6a  jz      short loc_180014CA7
0x180014c6c  mov     r8d, 33Ah; unsigned int
0x180014c72  lea     rdx, aSetexternalpro; "<SetExternalPropsFromInitString|OLEDB|E"...
0x180014c79  mov     ecx, ebx; int
0x180014c7b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180014c80  mov     eax, cs:_bidGblFlags
0x180014c86  test    al, 2
0x180014c88  jz      short loc_180014CA7
0x180014c8a  mov     r9d, ebx
0x180014c8d  lea     r8, aSetexternalpro_1; "<SetExternalPropsFromInitString|Trace|H"...
0x180014c94  mov     edx, 0CE809h
0x180014c99  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180014ca0  call    _bidTraceHR
0x180014ca5  mov     ebx, eax
0x180014ca7  mov     [rsp+0D8h+var_70], ebx
0x180014cab  lea     rdx, _TI1J; pThrowInfo
0x180014cb2  lea     rcx, [rsp+0D8h+var_70]; pExceptionObject
0x180014cb7  call    _CxxThrowException_0
0x180014cbc  mov     eax, cs:_bidGblFlags
0x180014cc2  test    al, 2
0x180014cc4  jz      short loc_180014D1F
0x180014cc6  mov     r8d, 33Dh; unsigned int
0x180014ccc  lea     rdx, aSetexternalpro; "<SetExternalPropsFromInitString|OLEDB|E"...
0x180014cd3  mov     ecx, ebx; int
0x180014cd5  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180014cda  mov     eax, cs:_bidGblFlags
0x180014ce0  test    al, 2
0x180014ce2  jz      short loc_180014D1F
0x180014ce4  mov     r8d, 33Dh; unsigned int
0x180014cea  lea     rdx, aSetexternalpro; "<SetExternalPropsFromInitString|OLEDB|E"...
0x180014cf1  mov     ecx, ebx; int
0x180014cf3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180014cf8  mov     eax, cs:_bidGblFlags
0x180014cfe  test    al, 2
0x180014d00  jz      short loc_180014D1F
0x180014d02  mov     r9d, ebx
0x180014d05  lea     r8, aSetexternalpro_1; "<SetExternalPropsFromInitString|Trace|H"...
0x180014d0c  mov     edx, 0CF409h
0x180014d11  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180014d18  call    _bidTraceHR
0x180014d1d  mov     ebx, eax
0x180014d1f  mov     [rsp+0D8h+var_6C], ebx
0x180014d23  lea     rdx, _TI1J; pThrowInfo
0x180014d2a  lea     rcx, [rsp+0D8h+var_6C]; pExceptionObject
0x180014d2f  call    _CxxThrowException_0
0x180014d34  mov     edx, [rsi+14h]
0x180014d37  mov     [rsp+0D8h+var_64], edx
0x180014d3b  mov     rax, [rsi+8]
0x180014d3f  mov     r15, rdi
0x180014d42  mov     r13, rdi
0x180014d45  mov     [rsp+0D8h+var_48], rdi
0x180014d4d  mov     [rsp+0D8h+var_50], rdi
0x180014d55  mov     ecx, edi
0x180014d57  mov     [rsp+0D8h+var_98], ecx
0x180014d5b  mov     [rsp+0D8h+var_30], rax
0x180014d63  cmp     ecx, edx
0x180014d65  jnb     loc_180014F31
0x180014d6b  cmp     dword ptr [rax+30h], 0FFFFFFFFh
0x180014d6f  jnz     loc_180014E68
0x180014d75  cmp     dword ptr [rax+34h], 0FFFFFFFFh
0x180014d79  jnz     loc_180014E68
0x180014d7f  mov     rcx, [rax]
0x180014d82  mov     [rsp+0D8h+var_88], rcx
0x180014d87  mov     eax, [rax+8]
0x180014d8a  mov     [rsp+0D8h+arg_18], eax
0x180014d91  test    r15, r15
0x180014d94  jnz     short loc_180014DE3
0x180014d96  mov     rcx, [rsi+18h]
0x180014d9a  mov     rax, rbx
0x180014d9d  inc     rax
0x180014da0  cmp     word ptr [rcx+rax*2], 0
0x180014da5  jnz     short loc_180014D9D
0x180014da7  add     rax, 2
0x180014dab  mov     [rsp+0D8h+var_50], rax
0x180014db3  lea     rcx, [rax+rax]
0x180014db7  call    cs:__imp_mpMalloc
0x180014dbd  mov     r15, rax
0x180014dc0  test    rax, rax
0x180014dc3  jz      loc_180014E73
0x180014dc9  mov     r13, rax
0x180014dcc  mov     [rsp+0D8h+var_48], rax
0x180014dd4  mov     [rax], di
0x180014dd7  mov     eax, [rsp+0D8h+arg_18]
0x180014dde  mov     rcx, [rsp+0D8h+var_88]
0x180014de3  test    eax, eax
0x180014de5  jz      short loc_180014E16
0x180014de7  movzx   ecx, word ptr [rcx]; C
0x180014dea  call    cs:__imp_iswspace
0x180014df0  mov     rcx, [rsp+0D8h+var_88]
0x180014df5  test    eax, eax
0x180014df7  mov     eax, [rsp+0D8h+arg_18]
0x180014dfe  jz      short loc_180014E16
0x180014e00  dec     eax
0x180014e02  mov     [rsp+0D8h+arg_18], eax
0x180014e09  add     rcx, 2
0x180014e0d  mov     [rsp+0D8h+var_88], rcx
0x180014e12  test    eax, eax
0x180014e14  jnz     short loc_180014DE7
0x180014e16  mov     [rsp+0D8h+var_A0], rcx
0x180014e1b  mov     dword ptr [rsp+0D8h+var_A8], eax
0x180014e1f  lea     rax, aLs; "%.*ls;"
0x180014e26  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x180014e2b  mov     qword ptr [rsp+0D8h+var_B8], rdi; unsigned int
0x180014e30  lea     r9, [rsp+0D8h+var_50]; unsigned __int64 *
0x180014e38  lea     r8, [rsp+0D8h+var_48]; unsigned __int16 **
0x180014e40  mov     rdx, [rsp+0D8h+var_50]; unsigned __int64
0x180014e48  mov     rcx, r13; pszDest
  ... truncated ...
```
