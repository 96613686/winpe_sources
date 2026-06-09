# LocalPrintConfigData::GetFileByRole(PrinterDriverRole,bool,bool)

- ea: `0x1400587c0`
- end: `0x140058dbe`
- name: `?GetFileByRole@LocalPrintConfigData@@UEAAPEBGW4PrinterDriverRole@@_N1@Z`
- size: `1534`
- prototype: `const wchar_t *__fastcall(__int64, unsigned int, __int64, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x140003ecc`
- `0x1400576c8`
- `0x140058508`
- `0x1400587c0`
- `0x1400592e4`
- `0x140063010`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x1400588e8`
- `WINSPOOL!GetPrinterDataW` at `0x140058956`
- `WINSPOOL!GetPrinterDataW` at `0x140058c87`
- `WINSPOOL!GetPrinterDataW` at `0x140058cfd`
- `WINSPOOL!GetPrinterDataW` at `0x1400588e8`
- `WINSPOOL!GetPrinterDataW` at `0x140058956`
- `WINSPOOL!GetPrinterDataW` at `0x140058c87`
- `WINSPOOL!GetPrinterDataW` at `0x140058cfd`

## string_xrefs

- `0x140058a7c`: `unires.dll`
- `0x140058aa6`: `unires.dll`
- `0x140058aec`: `PCLXL.dll`
- `0x1400588dd`: `PrintQueueV4DriverDirectory`
- `0x140058c71`: `PrintQueueV4DriverDirectory`
- `0x140058926`: `V4_Merged_ConfigFile_Name`
- `0x140058d55`: `PCL5URES.dll`
- `0x140058d5e`: `PCL4RES.dll`
- `0x140058bfb`: `PCL5ERES.dll`

## pseudocode

```c
const wchar_t *__fastcall LocalPrintConfigData::GetFileByRole(__int64 a1, unsigned int a2, __int64 a3, char a4)
{
  char v5; // cl
  char v7; // r9
  int v8; // r10d
  int v9; // eax
  __int64 v11; // rdi
  char v12; // si
  int v13; // r10d
  int v14; // r10d
  int v15; // r10d
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  void *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r13
  signed int PrinterDataW; // eax
  bool v23; // sf
  __int64 v24; // rax
  int v25; // r10d
  int v26; // r10d
  int v27; // r10d
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // r10d
  int v33; // r10d
  int v34; // r10d
  int v35; // r10d
  const wchar_t *v36; // rdx
  wchar_t *v37; // rsi
  __int64 v38; // rcx
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  int v46; // r10d
  int v47; // r10d
  int v48; // r10d
  BYTE *v49; // rax
  void *v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rax
  int v54; // r14d
  void *v55; // rcx
  BYTE *v56; // r15
  signed int v57; // eax
  bool v58; // sf
  __int64 v59; // rax
  DWORD pType; // [rsp+30h] [rbp-10h] BYREF
  DWORD v61; // [rsp+34h] [rbp-Ch] BYREF
  DWORD v62; // [rsp+38h] [rbp-8h] BYREF
  DWORD pcbNeeded; // [rsp+88h] [rbp+48h] BYREF
  char v64; // [rsp+90h] [rbp+50h]

  v64 = a3;
  v5 = 0;
  LOBYTE(pcbNeeded) = 0;
  v7 = a3;
  v8 = a2;
  if ( a2 > 0x15 || (v9 = 2146308, !_bittest(&v9, a2)) )
  {
    if ( !IsValidQuery(*(_DWORD *)(a1 + 120), a3, (bool *)&pcbNeeded) )
      return 0;
    v5 = pcbNeeded;
  }
  v11 = 0;
  v12 = 0;
  if ( v8 <= 11 )
  {
    if ( v8 == 11 )
    {
      LOBYTE(a3) = v7;
      v11 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, __int64))a1)(a1, L"unires.dll", a3);
      if ( v11 )
      {
        if ( !a4 )
          return L"unires.dll";
        return (const wchar_t *)v11;
      }
    }
    else
    {
      if ( v8 > 5 )
      {
        v25 = v8 - 6;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( v26 )
          {
            v27 = v26 - 2;
            if ( v27 )
            {
              if ( v27 != 1 )
                goto LABEL_139;
              if ( v5 )
                v28 = *(_QWORD *)(a1 + 104);
              else
                v28 = *(_QWORD *)(a1 + 96);
              if ( v28 )
                v11 = *(_QWORD *)(v28 + 80);
            }
            else
            {
              if ( v5 )
                v29 = *(_QWORD *)(a1 + 104);
              else
                v29 = *(_QWORD *)(a1 + 96);
              if ( v29 )
                v11 = *(_QWORD *)(v29 + 72);
            }
          }
          else
          {
            if ( v5 )
              v30 = *(_QWORD *)(a1 + 104);
            else
              v30 = *(_QWORD *)(a1 + 96);
            if ( v30 )
              v11 = *(_QWORD *)(v30 + 64);
          }
        }
        else
        {
          if ( v5 )
            v31 = *(_QWORD *)(a1 + 104);
          else
            v31 = *(_QWORD *)(a1 + 96);
          if ( v31 )
            v11 = *(_QWORD *)(v31 + 56);
        }
        goto LABEL_25;
      }
      if ( v8 == 5 )
      {
        if ( v5 )
          v24 = *(_QWORD *)(a1 + 104);
        else
          v24 = *(_QWORD *)(a1 + 96);
        if ( v24 )
          v11 = *(_QWORD *)(v24 + 40);
        goto LABEL_25;
      }
      if ( !v8 )
      {
        if ( **(_DWORD **)(a1 + 8) >= 4u && v5 )
          v11 = *(_QWORD *)(a1 + 64);
        else
          v11 = *(_QWORD *)(a1 + 32);
        goto LABEL_139;
      }
      v13 = v8 - 1;
      if ( !v13 )
      {
        v11 = *(_QWORD *)((v5 != 0 ? 0x20 : 0) + a1 + 40);
        goto LABEL_139;
      }
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          if ( v15 != 1 )
          {
LABEL_139:
            if ( a4 && v12 )
            {
              if ( v11 )
              {
                LOBYTE(a3) = v7;
                return (const wchar_t *)(**(__int64 (__fastcall ***)(__int64, __int64, __int64))a1)(a1, v11, a3);
              }
            }
            return (const wchar_t *)v11;
          }
          if ( v5 )
            v16 = *(_QWORD *)(a1 + 104);
          else
            v16 = *(_QWORD *)(a1 + 96);
          if ( v16 )
            v11 = *(_QWORD *)(v16 + 48);
        }
        else
        {
          if ( v5 )
            v17 = *(_QWORD *)(a1 + 104);
          else
            v17 = *(_QWORD *)(a1 + 96);
          if ( v17 )
            v11 = *(_QWORD *)(v17 + 32);
        }
LABEL_25:
        v12 = 1;
        goto LABEL_139;
      }
      v18 = *(_QWORD *)(a1 + 8);
      if ( *(_DWORD *)v18 < 4u )
      {
        v11 = *(_QWORD *)(v18 + 32);
        goto LABEL_139;
      }
      v19 = *(void **)(a1 + 112);
      pcbNeeded = 0;
      pType = 0;
      if ( !GetPrinterDataW(v19, (LPWSTR)L"PrintQueueV4DriverDirectory", &pType, (LPBYTE)(a1 + 144), 0x208u, &pcbNeeded)
        && StringCchCatW((STRSAFE_LPWSTR)(a1 + 144), 0x104u, L"\\") >= 0 )
      {
        v20 = -1;
        do
          ++v20;
        while ( *(_WORD *)(a1 + 144 + 2 * v20) );
        v61 = 0;
        v21 = a1 + 2LL * (unsigned int)v20;
        PrinterDataW = GetPrinterDataW(
                         *(HANDLE *)(a1 + 112),
                         (LPWSTR)L"V4_Merged_ConfigFile_Name",
                         0,
                         (LPBYTE)(v21 + 144),
                         2 * (260 - v20),
                         &v61);
        v23 = PrinterDataW < 0;
        if ( PrinterDataW > 0 )
          v23 = 1;
        if ( !v23 )
        {
          v11 = v21 + 144;
          *(_WORD *)(a1 + 662) = 0;
          if ( a4 )
            return (const wchar_t *)(a1 + 144);
          return (const wchar_t *)v11;
        }
      }
    }
LABEL_138:
    v7 = v64;
    goto LABEL_139;
  }
  if ( v8 > 17 )
  {
    v46 = v8 - 18;
    if ( v46 )
    {
      v47 = v46 - 1;
      if ( v47 )
      {
        v48 = v47 - 1;
        if ( !v48 )
        {
          if ( v5 )
            v59 = *(_QWORD *)(a1 + 104);
          else
            v59 = *(_QWORD *)(a1 + 96);
          if ( v59 )
            v11 = *(_QWORD *)(v59 + 112);
          goto LABEL_25;
        }
        if ( v48 != 1 )
          goto LABEL_139;
        v49 = *(BYTE **)(a1 + 664);
        if ( !v49 )
        {
          v49 = (BYTE *)operator new(0x208u, (const struct std::nothrow_t *)byte_14006F740);
          *(_QWORD *)(a1 + 664) = v49;
          if ( !v49 )
            goto LABEL_138;
        }
        v61 = 0;
        v50 = *(void **)(a1 + 112);
        v62 = 0;
        if ( GetPrinterDataW(v50, (LPWSTR)L"PrintQueueV4DriverDirectory", &v62, v49, 0x208u, &v61)
          || StringCchCatW(*(STRSAFE_LPWSTR *)(a1 + 664), 0x104u, L"\\") < 0 )
        {
          goto LABEL_138;
        }
        v51 = *(_QWORD *)(a1 + 664);
        v52 = -1;
        do
          ++v52;
        while ( *(_WORD *)(v51 + 2 * v52) );
        v53 = (unsigned int)v52;
        v54 = 260 - v52;
        v55 = *(void **)(a1 + 112);
        pcbNeeded = 0;
        v56 = (BYTE *)(v51 + 2 * v53);
        v57 = GetPrinterDataW(v55, (LPWSTR)L"V4_PrintDeviceCapabilities", 0, v56, 2 * v54, &pcbNeeded);
        v58 = v57 < 0;
        if ( v57 > 0 )
          v58 = 1;
        if ( v58 )
          goto LABEL_138;
        *(_WORD *)(*(_QWORD *)(a1 + 664) + 518LL) = 0;
        if ( a4 )
          return *(const wchar_t **)(a1 + 664);
        else
          return (const wchar_t *)v56;
      }
      v36 = L"PCL5URES.dll";
    }
    else
    {
      v36 = L"PCL4RES.dll";
    }
LABEL_137:
    LOBYTE(a3) = v7;
    v11 = (**(__int64 (__fastcall ***)(__int64, const wchar_t *, __int64))a1)(a1, v36, a3);
    goto LABEL_138;
  }
  if ( v8 == 17 )
  {
    v36 = L"PCL5ERES.dll";
    goto LABEL_137;
  }
  v32 = v8 - 12;
  if ( !v32 )
  {
    if ( v5 )
      v45 = *(_QWORD *)(a1 + 104);
    else
      v45 = *(_QWORD *)(a1 + 96);
    if ( v45 )
      v11 = *(_QWORD *)(v45 + 88);
    goto LABEL_25;
  }
  v33 = v32 - 1;
  if ( !v33 )
  {
    if ( v5 )
      v44 = *(_QWORD *)(a1 + 104);
    else
      v44 = *(_QWORD *)(a1 + 96);
    if ( v44 )
      v11 = *(_QWORD *)(v44 + 104);
    goto LABEL_25;
  }
  v34 = v33 - 1;
  if ( v34 )
  {
    v35 = v34 - 1;
    if ( v35 )
    {
      if ( v35 != 1 )
        goto LABEL_139;
      v36 = L"PCLXL.dll";
      goto LABEL_137;
    }
    if ( !a4 )
      return (const wchar_t *)v11;
    v37 = (wchar_t *)(a1 + 1192);
    v38 = -1;
    do
      ++v38;
    while ( v37[v38] );
    if ( v38 )
      return v37;
    v39 = (const unsigned __int16 *)(a1 + 2232);
  }
  else
  {
    if ( !a4 )
      return (const wchar_t *)v11;
    v40 = -1;
    v37 = (wchar_t *)(a1 + 672);
    v41 = -1;
    do
      ++v41;
    while ( v37[v41] );
    if ( v41 )
      return v37;
    v42 = *(_QWORD *)(a1 + 96);
    if ( v42 && *(_QWORD *)(v42 + 72) )
    {
      v39 = *(const unsigned __int16 **)(a1 + 128);
      if ( !v39 )
        return (const wchar_t *)v11;
    }
    else
    {
      v43 = *(_QWORD *)(a1 + 104);
      if ( !v43 || !*(_QWORD *)(v43 + 72) )
        return (const wchar_t *)v11;
      do
        ++v40;
      while ( *(_WORD *)(a1 + 2 * v40 + 1712) );
      if ( !v40 )
        return (const wchar_t *)v11;
      v39 = (const unsigned __int16 *)(a1 + 1712);
    }
  }
  if ( (int)GetCatalogPathFromInfPath(v39, v37, a3) >= 0 )
    return v37;
  return (const wchar_t *)v11;
}

```

## disassembly

```asm
0x1400587c0  mov     [rsp-38h+arg_0], rbx
0x1400587c5  mov     [rsp-38h+arg_10], r8b
0x1400587ca  push    rbp
0x1400587cb  push    rsi
0x1400587cc  push    rdi
0x1400587cd  push    r12
0x1400587cf  push    r13
0x1400587d1  push    r14
0x1400587d3  push    r15
0x1400587d5  mov     rbp, rsp
0x1400587d8  sub     rsp, 40h
0x1400587dc  xor     r13d, r13d
0x1400587df  mov     rbx, rcx
0x1400587e2  mov     cl, r13b
0x1400587e5  mov     r12b, r9b
0x1400587e8  mov     byte ptr [rbp+arg_8], cl
0x1400587eb  mov     r9b, r8b
0x1400587ee  mov     r10d, edx
0x1400587f1  cmp     edx, 15h
0x1400587f4  ja      short loc_140058800
0x1400587f6  mov     eax, 20C004h
0x1400587fb  bt      eax, edx
0x1400587fe  jb      short loc_14005881D
0x140058800  mov     ecx, [rbx+78h]; unsigned int
0x140058803  lea     r8, [rbp+arg_8]; bool *
0x140058807  mov     dl, r9b; bool
0x14005880a  call    ?IsValidQuery@@YA_NK_NPEA_N@Z; IsValidQuery(ulong,bool,bool *)
0x14005880f  test    al, al
0x140058811  jnz     short loc_14005881A
0x140058813  xor     eax, eax
0x140058815  jmp     loc_140058DA6
0x14005881a  mov     cl, byte ptr [rbp+arg_8]
0x14005881d  mov     rdi, r13
0x140058820  mov     sil, r13b
0x140058823  cmp     r10d, 0Bh
0x140058827  jg      loc_140058AB2
0x14005882d  jz      loc_140058A79
0x140058833  cmp     r10d, 5
0x140058837  jg      loc_1400589DD
0x14005883d  jz      loc_1400589BD
0x140058843  test    r10d, r10d
0x140058846  jz      loc_14005899E
0x14005884c  sub     r10d, 1
0x140058850  jz      loc_14005898C
0x140058856  sub     r10d, 1
0x14005885a  jz      short loc_1400588A4
0x14005885c  sub     r10d, 1
0x140058860  jz      short loc_140058885
0x140058862  cmp     r10d, 1
0x140058866  jnz     loc_140058D7D
0x14005886c  test    cl, cl
0x14005886e  jnz     short loc_140058876
0x140058870  mov     rax, [rbx+60h]
0x140058874  jmp     short loc_14005887A
0x140058876  mov     rax, [rbx+68h]
0x14005887a  test    rax, rax
0x14005887d  jz      short loc_14005889C
0x14005887f  mov     rdi, [rax+30h]
0x140058883  jmp     short loc_14005889C
0x140058885  test    cl, cl
0x140058887  jnz     short loc_14005888F
0x140058889  mov     rax, [rbx+60h]
0x14005888d  jmp     short loc_140058893
0x14005888f  mov     rax, [rbx+68h]
0x140058893  test    rax, rax
0x140058896  jz      short loc_14005889C
0x140058898  mov     rdi, [rax+20h]
0x14005889c  mov     sil, 1
0x14005889f  jmp     loc_140058D7D
0x1400588a4  mov     rax, [rbx+8]
0x1400588a8  cmp     dword ptr [rax], 4
0x1400588ab  jnb     short loc_1400588B6
0x1400588ad  mov     rdi, [rax+20h]
0x1400588b1  jmp     loc_140058D7D
0x1400588b6  mov     rcx, [rbx+70h]; hPrinter
0x1400588ba  lea     rax, [rbp+arg_8]
0x1400588be  mov     [rsp+40h+pcbNeeded], rax; pcbNeeded
0x1400588c3  lea     r15, [rbx+90h]
0x1400588ca  mov     r9, r15; pData
0x1400588cd  mov     [rsp+40h+nSize], 208h; nSize
0x1400588d5  lea     r8, [rbp+pType]; pType
0x1400588d9  mov     [rbp+arg_8], r13d
0x1400588dd  lea     rdx, aPrintqueuev4dr; "PrintQueueV4DriverDirectory"
0x1400588e4  mov     [rbp+pType], r13d
0x1400588e8  call    cs:__imp_GetPrinterDataW
0x1400588ee  test    eax, eax
0x1400588f0  jnz     loc_140058D79
0x1400588f6  mov     r14d, 104h
0x1400588fc  lea     r8, asc_1400691D8; "\\"
0x140058903  mov     edx, r14d; cchDest
0x140058906  mov     rcx, r15; pszDest
0x140058909  call    StringCchCatW
0x14005890e  test    eax, eax
0x140058910  js      loc_140058D79
0x140058916  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14005891a  inc     rcx
0x14005891d  cmp     [r15+rcx*2], r13w
0x140058922  jnz     short loc_14005891A
0x140058924  mov     eax, ecx
0x140058926  lea     rdx, aV4MergedConfig; "V4_Merged_ConfigFile_Name"
0x14005892d  sub     r14d, ecx
0x140058930  mov     [rbp+var_C], edi
0x140058933  mov     rcx, [rbx+70h]; hPrinter
0x140058937  add     r14d, r14d
0x14005893a  xor     r8d, r8d; pType
0x14005893d  lea     r13, [rbx+rax*2]
0x140058941  lea     rax, [rbp+var_C]
0x140058945  mov     [rsp+40h+pcbNeeded], rax; pcbNeeded
0x14005894a  lea     r9, [r13+90h]; pData
0x140058951  mov     [rsp+40h+nSize], r14d; nSize
0x140058956  call    cs:__imp_GetPrinterDataW
0x14005895c  test    eax, eax
0x14005895e  jle     short loc_14005896A
0x140058960  movzx   eax, ax
0x140058963  or      eax, 80070000h
0x140058968  test    eax, eax
0x14005896a  js      loc_140058D79
0x140058970  xor     eax, eax
0x140058972  lea     rdi, [r13+90h]
0x140058979  test    r12b, r12b
0x14005897c  mov     [rbx+296h], ax
0x140058983  cmovnz  rdi, r15
0x140058987  jmp     loc_140058DA3
0x14005898c  neg     cl
0x14005898e  sbb     rax, rax
0x140058991  and     eax, 20h
0x140058994  mov     rdi, [rax+rbx+28h]
0x140058999  jmp     loc_140058D7D
0x14005899e  mov     rax, [rbx+8]
0x1400589a2  cmp     dword ptr [rax], 4
0x1400589a5  jb      short loc_1400589B4
0x1400589a7  test    cl, cl
0x1400589a9  jz      short loc_1400589B4
0x1400589ab  mov     rdi, [rbx+40h]
0x1400589af  jmp     loc_140058D7D
0x1400589b4  mov     rdi, [rbx+20h]
0x1400589b8  jmp     loc_140058D7D
0x1400589bd  test    cl, cl
0x1400589bf  jnz     short loc_1400589C7
0x1400589c1  mov     rax, [rbx+60h]
0x1400589c5  jmp     short loc_1400589CB
0x1400589c7  mov     rax, [rbx+68h]
0x1400589cb  test    rax, rax
0x1400589ce  jz      loc_14005889C
0x1400589d4  mov     rdi, [rax+28h]
0x1400589d8  jmp     loc_14005889C
0x1400589dd  sub     r10d, 6
0x1400589e1  jz      short loc_140058A59
0x1400589e3  sub     r10d, 1
0x1400589e7  jz      short loc_140058A39
0x1400589e9  sub     r10d, 2
0x1400589ed  jz      short loc_140058A19
0x1400589ef  cmp     r10d, 1
0x1400589f3  jnz     loc_140058D7D
0x1400589f9  test    cl, cl
0x1400589fb  jnz     short loc_140058A03
0x1400589fd  mov     rax, [rbx+60h]
0x140058a01  jmp     short loc_140058A07
0x140058a03  mov     rax, [rbx+68h]
0x140058a07  test    rax, rax
0x140058a0a  jz      loc_14005889C
0x140058a10  mov     rdi, [rax+50h]
0x140058a14  jmp     loc_14005889C
0x140058a19  test    cl, cl
0x140058a1b  jnz     short loc_140058A23
0x140058a1d  mov     rax, [rbx+60h]
0x140058a21  jmp     short loc_140058A27
0x140058a23  mov     rax, [rbx+68h]
0x140058a27  test    rax, rax
0x140058a2a  jz      loc_14005889C
0x140058a30  mov     rdi, [rax+48h]
0x140058a34  jmp     loc_14005889C
0x140058a39  test    cl, cl
0x140058a3b  jnz     short loc_140058A43
0x140058a3d  mov     rax, [rbx+60h]
0x140058a41  jmp     short loc_140058A47
0x140058a43  mov     rax, [rbx+68h]
0x140058a47  test    rax, rax
0x140058a4a  jz      loc_14005889C
0x140058a50  mov     rdi, [rax+40h]
0x140058a54  jmp     loc_14005889C
0x140058a59  test    cl, cl
0x140058a5b  jnz     short loc_140058A63
0x140058a5d  mov     rax, [rbx+60h]
0x140058a61  jmp     short loc_140058A67
0x140058a63  mov     rax, [rbx+68h]
0x140058a67  test    rax, rax
0x140058a6a  jz      loc_14005889C
0x140058a70  mov     rdi, [rax+38h]
0x140058a74  jmp     loc_14005889C
0x140058a79  mov     rax, [rbx]
0x140058a7c  lea     rdx, aUniresDll; "unires.dll"
0x140058a83  mov     r8b, r9b
0x140058a86  mov     rcx, rbx
0x140058a89  mov     rax, [rax]
0x140058a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058a91  mov     rdi, rax
0x140058a94  test    rax, rax
0x140058a97  jz      loc_140058D79
0x140058a9d  test    r12b, r12b
0x140058aa0  jnz     loc_140058DA3
0x140058aa6  lea     rdi, aUniresDll; "unires.dll"
0x140058aad  jmp     loc_140058DA3
0x140058ab2  cmp     r10d, 11h
0x140058ab6  jg      loc_140058C07
0x140058abc  jz      loc_140058BFB
0x140058ac2  sub     r10d, 0Ch
0x140058ac6  jz      loc_140058BDB
0x140058acc  sub     r10d, 1
0x140058ad0  jz      loc_140058BBB
0x140058ad6  sub     r10d, 1
0x140058ada  jz      short loc_140058B3A
0x140058adc  sub     r10d, 1
0x140058ae0  jz      short loc_140058AF8
0x140058ae2  cmp     r10d, 1
0x140058ae6  jnz     loc_140058D7D
0x140058aec  lea     rdx, aPclxlDll; "PCLXL.dll"
0x140058af3  jmp     loc_140058D65
0x140058af8  test    r12b, r12b
0x140058afb  jz      loc_140058DA3
0x140058b01  lea     rsi, [rbx+4A8h]
0x140058b08  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140058b0c  inc     rcx
0x140058b0f  cmp     [rsi+rcx*2], r13w
0x140058b14  jnz     short loc_140058B0C
0x140058b16  test    rcx, rcx
0x140058b19  jnz     short loc_140058B32
0x140058b1b  lea     rcx, [rbx+8B8h]; unsigned __int16 *
0x140058b22  mov     rdx, rsi; wchar_t *
0x140058b25  call    ?GetCatalogPathFromInfPath@@YAJPEBGPEAGK@Z; GetCatalogPathFromInfPath(ushort const *,ushort *,ulong)
0x140058b2a  test    eax, eax
0x140058b2c  js      loc_140058DA3
0x140058b32  mov     rdi, rsi
0x140058b35  jmp     loc_140058DA3
0x140058b3a  test    r12b, r12b
0x140058b3d  jz      loc_140058DA3
0x140058b43  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140058b47  lea     rsi, [rbx+2A0h]
0x140058b4e  mov     rax, rcx
0x140058b51  inc     rax
0x140058b54  cmp     [rsi+rax*2], r13w
0x140058b59  jnz     short loc_140058B51
0x140058b5b  test    rax, rax
0x140058b5e  jnz     short loc_140058B32
0x140058b60  mov     rax, [rbx+60h]
0x140058b64  test    rax, rax
0x140058b67  jz      short loc_140058B81
0x140058b69  cmp     [rax+48h], r13
0x140058b6d  jz      short loc_140058B81
0x140058b6f  mov     rcx, [rbx+80h]
0x140058b76  test    rcx, rcx
0x140058b79  jz      loc_140058DA3
0x140058b7f  jmp     short loc_140058B22
0x140058b81  mov     rax, [rbx+68h]
0x140058b85  test    rax, rax
0x140058b88  jz      loc_140058DA3
0x140058b8e  cmp     [rax+48h], r13
0x140058b92  jz      loc_140058DA3
0x140058b98  inc     rcx
0x140058b9b  cmp     [rbx+rcx*2+6B0h], r13w
0x140058ba4  jnz     short loc_140058B98
0x140058ba6  test    rcx, rcx
0x140058ba9  jz      loc_140058DA3
0x140058baf  lea     rcx, [rbx+6B0h]
0x140058bb6  jmp     loc_140058B22
0x140058bbb  test    cl, cl
0x140058bbd  jnz     short loc_140058BC5
0x140058bbf  mov     rax, [rbx+60h]
0x140058bc3  jmp     short loc_140058BC9
0x140058bc5  mov     rax, [rbx+68h]
0x140058bc9  test    rax, rax
0x140058bcc  jz      loc_14005889C
0x140058bd2  mov     rdi, [rax+68h]
0x140058bd6  jmp     loc_14005889C
0x140058bdb  test    cl, cl
0x140058bdd  jnz     short loc_140058BE5
0x140058bdf  mov     rax, [rbx+60h]
0x140058be3  jmp     short loc_140058BE9
0x140058be5  mov     rax, [rbx+68h]
0x140058be9  test    rax, rax
0x140058bec  jz      loc_14005889C
0x140058bf2  mov     rdi, [rax+58h]
0x140058bf6  jmp     loc_14005889C
0x140058bfb  lea     rdx, aPcl5eresDll; "PCL5ERES.dll"
0x140058c02  jmp     loc_140058D65
0x140058c07  sub     r10d, 12h
0x140058c0b  jz      loc_140058D5E
0x140058c11  sub     r10d, 1
0x140058c15  jz      loc_140058D55
0x140058c1b  sub     r10d, 1
0x140058c1f  jz      loc_140058D35
0x140058c25  cmp     r10d, 1
0x140058c29  jnz     loc_140058D7D
0x140058c2f  mov     rax, [rbx+298h]
0x140058c36  test    rax, rax
0x140058c39  jnz     short loc_140058C5C
0x140058c3b  lea     rdx, byte_14006F740; struct std::nothrow_t *
0x140058c42  mov     ecx, 208h; unsigned __int64
0x140058c47  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140058c4c  mov     [rbx+298h], rax
  ... truncated ...
```
