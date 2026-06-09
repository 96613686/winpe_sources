# GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)

- ea: `0x180003290`
- end: `0x18000353e`
- name: `?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z`
- size: `686`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16, struct ATL::CComVariant *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002950`
- `0x18004afd8`

## callees

- `0x180003290`
- `0x180008aa8`
- `0x18004adc4`
- `0x18004afd8`
- `0x18004b650`
- `0x18004bc98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800032be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800032be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003454`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003454`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000352a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000352a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800033c3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800033c3`
- `OLEAUT32!__imp_VariantClear` at `0x18000331c`
- `OLEAUT32!__imp_VariantClear` at `0x18000349c`
- `OLEAUT32!__imp_VariantClear` at `0x1800034d8`
- `OLEAUT32!__imp_VariantClear` at `0x180003513`
- `OLEAUT32!__imp_VariantClear` at `0x18000331c`
- `OLEAUT32!__imp_VariantClear` at `0x18000349c`
- `OLEAUT32!__imp_VariantClear` at `0x1800034d8`
- `OLEAUT32!__imp_VariantClear` at `0x180003513`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetStoredValue(
        HKEY a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int16 a4,
        VARIANTARG *pvarg)
{
  LSTATUS v7; // eax
  const unsigned __int16 *v8; // rdx
  int BSTRAlloc; // ebx
  __int16 v10; // si
  BSTR v11; // rax
  UINT v12; // eax
  struct tagVARIANT *v13; // r9
  BYTE v14; // di
  int v15; // eax
  bool v16; // sf
  SHORT v17; // si
  LONG v18; // esi
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-1Ch] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF

  hKey = 0;
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  BSTRAlloc = v7;
  if ( v7 > 0 )
    BSTRAlloc = (unsigned __int16)v7 | 0x80070000;
  if ( BSTRAlloc >= 0 )
  {
    if ( a4 == 11 )
    {
      Type = 0;
      BSTRAlloc = UstRegQueryDword(hKey, a3, &Type);
      if ( BSTRAlloc >= 0 )
      {
        v10 = 0;
        if ( Type )
          v10 = -1;
        if ( pvarg->vt != 11 )
        {
          VariantClear(pvarg);
          pvarg->vt = 11;
        }
        pvarg->iVal = v10;
      }
    }
    else if ( ((a4 - 3) & 0xFFEF) != 0 )
    {
      if ( ((a4 - 2) & 0xFFEF) != 0 )
      {
        if ( (unsigned __int16)(a4 - 16) > 1u )
        {
          if ( a4 == 8 )
          {
            pbstr = 0;
            BSTRAlloc = UstRegQueryBSTRAlloc(hKey, a3);
            if ( BSTRAlloc >= 0 )
            {
              v11 = pbstr;
              pbstr = 0;
              pvarg->llVal = (LONGLONG)v11;
              pvarg->vt = 8;
            }
          }
          else
          {
            if ( a4 != 8200 )
            {
              if ( a4 == 8204 )
                BSTRAlloc = GetMultiValueSetting(hKey, v8, pvarg);
              else
                BSTRAlloc = -2147024809;
              goto LABEL_45;
            }
            pbstr = 0;
            BSTRAlloc = UstRegQueryBSTRAlloc(hKey, a3);
            if ( BSTRAlloc >= 0 )
            {
              v12 = SysStringLen(pbstr);
              BSTRAlloc = UstVarLib::CscVarUtil_ConvertMULTISZToVariant(
                            pbstr,
                            (const unsigned __int16 *)(v12 + 1),
                            (__int64)pvarg,
                            v13);
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
          goto LABEL_45;
        }
        v14 = 0;
        BSTRAlloc = -2147024809;
        v15 = -2147024809;
        if ( !hKey || !a3 )
          goto LABEL_33;
        LODWORD(pbstr) = 0;
        Type = 0;
        cbData = 4;
        v15 = RegQueryValueExW(hKey, a3, 0, &Type, (LPBYTE)&pbstr, &cbData);
        v16 = v15 < 0;
        if ( v15 > 0 )
        {
          v15 = (unsigned __int16)v15 | 0x80070000;
          v16 = v15 < 0;
        }
        if ( !v16 )
        {
          if ( Type != 4 || cbData != 4 )
            goto LABEL_45;
          v14 = (unsigned __int8)pbstr;
          BSTRAlloc = v15;
        }
        else
        {
LABEL_33:
          BSTRAlloc = v15;
          if ( v15 < 0 )
            goto LABEL_45;
        }
        if ( pvarg->vt != 17 )
        {
          VariantClear(pvarg);
          pvarg->vt = 17;
        }
        pvarg->bVal = v14;
      }
      else
      {
        LODWORD(pbstr) = 0;
        BSTRAlloc = UstRegQueryDword(hKey, a3, (unsigned int *)&pbstr);
        if ( BSTRAlloc >= 0 )
        {
          v17 = (__int16)pbstr;
          if ( pvarg->vt != 2 )
          {
            VariantClear(pvarg);
            pvarg->vt = 2;
          }
          pvarg->iVal = v17;
        }
      }
    }
    else
    {
      LODWORD(pbstr) = 0;
      BSTRAlloc = UstRegQueryDword(hKey, a3, (unsigned int *)&pbstr);
      if ( BSTRAlloc >= 0 )
      {
        v18 = (int)pbstr;
        if ( pvarg->vt != 3 )
        {
          VariantClear(pvarg);
          pvarg->vt = 3;
        }
        pvarg->lVal = v18;
      }
    }
  }
LABEL_45:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)BSTRAlloc;
}

```

## disassembly

```asm
0x180003290  push    rbp
0x180003292  push    rbx
0x180003293  push    rsi
0x180003294  push    rdi
0x180003295  push    r14
0x180003297  mov     rbp, rsp
0x18000329a  sub     rsp, 50h
0x18000329e  movzx   edi, r9w
0x1800032a2  mov     rsi, r8
0x1800032a5  xor     r14d, r14d
0x1800032a8  mov     [rbp+hKey], r14
0x1800032ac  lea     rax, [rbp+hKey]
0x1800032b0  mov     [rsp+50h+phkResult], rax; phkResult
0x1800032b5  mov     r9d, 20019h; samDesired
0x1800032bb  xor     r8d, r8d; ulOptions
0x1800032be  call    cs:__imp_RegOpenKeyExW
0x1800032c4  mov     ebx, eax
0x1800032c6  test    eax, eax
0x1800032c8  jle     short loc_1800032D3
0x1800032ca  movzx   ebx, ax
0x1800032cd  or      ebx, 80070000h
0x1800032d3  test    ebx, ebx
0x1800032d5  js      loc_180003521
0x1800032db  cmp     di, 0Bh
0x1800032df  jnz     short loc_180003330
0x1800032e1  mov     [rbp+Type], r14d
0x1800032e5  lea     r8, [rbp+Type]; unsigned int *
0x1800032e9  mov     rdx, rsi; unsigned __int16 *
0x1800032ec  mov     rcx, [rbp+hKey]; HKEY
0x1800032f0  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x1800032f5  mov     ebx, eax
0x1800032f7  test    eax, eax
0x1800032f9  js      loc_180003521
0x1800032ff  mov     eax, 0FFFFFFFFh
0x180003304  mov     esi, r14d
0x180003307  cmp     [rbp+Type], r14d
0x18000330b  cmovnz  si, ax
0x18000330f  mov     rdi, [rbp+pvarg]
0x180003313  cmp     word ptr [rdi], 0Bh
0x180003317  jz      short loc_180003327
0x180003319  mov     rcx, rdi; pvarg
0x18000331c  call    cs:__imp_VariantClear
0x180003322  mov     word ptr [rdi], 0Bh
0x180003327  mov     [rdi+8], si
0x18000332b  jmp     loc_180003521
0x180003330  lea     eax, [rdi-3]
0x180003333  mov     ecx, 0FFEFh
0x180003338  test    cx, ax
0x18000333b  jz      loc_1800034E9
0x180003341  lea     eax, [rdi-2]
0x180003344  test    cx, ax
0x180003347  jz      loc_1800034AD
0x18000334d  lea     eax, [rdi-10h]
0x180003350  cmp     ax, 1
0x180003354  jbe     loc_180003411
0x18000335a  cmp     di, 8
0x18000335e  jnz     short loc_18000339B
0x180003360  mov     [rbp+pbstr], r14
0x180003364  lea     r8, [rbp+pbstr]
0x180003368  mov     rdx, rsi; unsigned __int16 *
0x18000336b  mov     rcx, [rbp+hKey]; HKEY
0x18000336f  call    ?UstRegQueryBSTRAlloc@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UstRegQueryBSTRAlloc(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180003374  mov     ebx, eax
0x180003376  test    eax, eax
0x180003378  js      short loc_18000338D
0x18000337a  mov     rax, [rbp+pbstr]
0x18000337e  mov     [rbp+pbstr], r14
0x180003382  mov     rcx, [rbp+pvarg]
0x180003386  mov     [rcx+8], rax
0x18000338a  mov     [rcx], di
0x18000338d  lea     rcx, [rbp+pbstr]
0x180003391  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180003396  jmp     loc_180003521
0x18000339b  mov     eax, 2008h
0x1800033a0  cmp     di, ax
0x1800033a3  jnz     short loc_1800033E9
0x1800033a5  mov     [rbp+pbstr], r14
0x1800033a9  lea     r8, [rbp+pbstr]
0x1800033ad  mov     rdx, rsi; unsigned __int16 *
0x1800033b0  mov     rcx, [rbp+hKey]; HKEY
0x1800033b4  call    ?UstRegQueryBSTRAlloc@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UstRegQueryBSTRAlloc(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800033b9  mov     ebx, eax
0x1800033bb  test    eax, eax
0x1800033bd  js      short loc_1800033DB
0x1800033bf  mov     rcx, [rbp+pbstr]; pbstr
0x1800033c3  call    cs:__imp_SysStringLen
0x1800033c9  lea     edx, [rax+1]; unsigned __int16 *
0x1800033cc  mov     r8, [rbp+pvarg]; unsigned int
0x1800033d0  mov     rcx, [rbp+pbstr]; psz
0x1800033d4  call    ?CscVarUtil_ConvertMULTISZToVariant@UstVarLib@@YAJPEBGKPEAUtagVARIANT@@@Z; UstVarLib::CscVarUtil_ConvertMULTISZToVariant(ushort const *,ulong,tagVARIANT *)
0x1800033d9  mov     ebx, eax
0x1800033db  lea     rcx, [rbp+pbstr]
0x1800033df  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800033e4  jmp     loc_180003521
0x1800033e9  mov     eax, 200Ch
0x1800033ee  cmp     di, ax
0x1800033f1  jnz     short loc_180003407
0x1800033f3  mov     r8, [rbp+pvarg]; struct ATL::CComVariant *
0x1800033f7  mov     rcx, [rbp+hKey]; HKEY
0x1800033fb  call    ?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z; GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)
0x180003400  mov     ebx, eax
0x180003402  jmp     loc_180003521
0x180003407  mov     ebx, 80070057h
0x18000340c  jmp     loc_180003521
0x180003411  mov     edi, r14d
0x180003414  mov     rcx, [rbp+hKey]; hKey
0x180003418  mov     ebx, 80070057h
0x18000341d  mov     eax, ebx
0x18000341f  test    rcx, rcx
0x180003422  jz      short loc_180003485
0x180003424  test    rsi, rsi
0x180003427  jz      short loc_180003485
0x180003429  mov     dword ptr [rbp+pbstr], r14d
0x18000342d  mov     [rbp+Type], r14d
0x180003431  mov     [rbp+cbData], 4
0x180003438  lea     rax, [rbp+cbData]
0x18000343c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180003441  lea     rax, [rbp+pbstr]
0x180003445  mov     [rsp+50h+phkResult], rax; lpData
0x18000344a  lea     r9, [rbp+Type]; lpType
0x18000344e  xor     r8d, r8d; lpReserved
0x180003451  mov     rdx, rsi; lpValueName
0x180003454  call    cs:__imp_RegQueryValueExW
0x18000345a  test    eax, eax
0x18000345c  jle     short loc_180003468
0x18000345e  movzx   eax, ax
0x180003461  or      eax, 80070000h
0x180003466  test    eax, eax
0x180003468  js      short loc_180003485
0x18000346a  cmp     [rbp+Type], 4
0x18000346e  jnz     loc_180003521
0x180003474  cmp     [rbp+cbData], 4
0x180003478  jnz     loc_180003521
0x18000347e  mov     edi, dword ptr [rbp+pbstr]
0x180003481  mov     ebx, eax
0x180003483  jmp     short loc_18000348F
0x180003485  mov     ebx, eax
0x180003487  test    eax, eax
0x180003489  js      loc_180003521
0x18000348f  mov     rsi, [rbp+pvarg]
0x180003493  cmp     word ptr [rsi], 11h
0x180003497  jz      short loc_1800034A7
0x180003499  mov     rcx, rsi; pvarg
0x18000349c  call    cs:__imp_VariantClear
0x1800034a2  mov     word ptr [rsi], 11h
0x1800034a7  mov     [rsi+8], dil
0x1800034ab  jmp     short loc_180003521
0x1800034ad  mov     dword ptr [rbp+pbstr], r14d
0x1800034b1  lea     r8, [rbp+pbstr]; unsigned int *
0x1800034b5  mov     rdx, rsi; unsigned __int16 *
0x1800034b8  mov     rcx, [rbp+hKey]; HKEY
0x1800034bc  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x1800034c1  mov     ebx, eax
0x1800034c3  test    eax, eax
0x1800034c5  js      short loc_180003521
0x1800034c7  movzx   esi, word ptr [rbp+pbstr]
0x1800034cb  mov     rdi, [rbp+pvarg]
0x1800034cf  cmp     word ptr [rdi], 2
0x1800034d3  jz      short loc_1800034E3
0x1800034d5  mov     rcx, rdi; pvarg
0x1800034d8  call    cs:__imp_VariantClear
0x1800034de  mov     word ptr [rdi], 2
0x1800034e3  mov     [rdi+8], si
0x1800034e7  jmp     short loc_180003521
0x1800034e9  mov     dword ptr [rbp+pbstr], r14d
0x1800034ed  lea     r8, [rbp+pbstr]; unsigned int *
0x1800034f1  mov     rdx, rsi; unsigned __int16 *
0x1800034f4  mov     rcx, [rbp+hKey]; HKEY
0x1800034f8  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x1800034fd  mov     ebx, eax
0x1800034ff  test    eax, eax
0x180003501  js      short loc_180003521
0x180003503  mov     esi, dword ptr [rbp+pbstr]
0x180003506  mov     rdi, [rbp+pvarg]
0x18000350a  cmp     word ptr [rdi], 3
0x18000350e  jz      short loc_18000351E
0x180003510  mov     rcx, rdi; pvarg
0x180003513  call    cs:__imp_VariantClear
0x180003519  mov     word ptr [rdi], 3
0x18000351e  mov     [rdi+8], esi
0x180003521  mov     rcx, [rbp+hKey]; hKey
0x180003525  test    rcx, rcx
0x180003528  jz      short loc_180003531
0x18000352a  call    cs:__imp_RegCloseKey
0x180003530  nop
0x180003531  mov     eax, ebx
0x180003533  add     rsp, 50h
0x180003537  pop     r14
0x180003539  pop     rdi
0x18000353a  pop     rsi
0x18000353b  pop     rbx
0x18000353c  pop     rbp
0x18000353d  retn
```
