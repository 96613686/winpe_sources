# GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)

- ea: `0x1800025b0`
- end: `0x18000293a`
- name: `?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z`
- size: `906`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned __int16 *, __int16, VARIANTARG *pvarg)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800019b0`
- `0x18001a91c`

## callees

- `0x1800025b0`
- `0x180002940`
- `0x180003fa0`
- `0x180004030`
- `0x18001a518`
- `0x18001a91c`
- `0x18001adb4`
- `0x18001b408`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002922`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002922`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800026b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000283c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800026b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000283c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800025e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800025e2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180002705`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180002705`
- `OLEAUT32!__imp_SysFreeString` at `0x180002759`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180002759`
- `OLEAUT32!__imp_SysFreeString` at `0x1800027c6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800027a3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800027a3`
- `OLEAUT32!__imp_VariantClear` at `0x180002896`
- `OLEAUT32!__imp_VariantClear` at `0x180002896`

## pseudocode

```c
__int64 __fastcall GetStoredValue(
        HKEY a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int16 a4,
        VARIANTARG *pvarg)
{
  LSTATUS v7; // eax
  const unsigned __int16 *v8; // rdx
  signed int String; // esi
  __int16 v10; // di
  OLECHAR *v11; // rbx
  HKEY v12; // r15
  LSTATUS v13; // eax
  DWORD v14; // esi
  BSTR v15; // rax
  OLECHAR *v16; // rdi
  OLECHAR *v17; // rdx
  OLECHAR *v18; // rax
  UINT v19; // eax
  struct tagVARIANT *v20; // r9
  BYTE v21; // di
  int v22; // eax
  bool v23; // sf
  SHORT v24; // di
  LONG v25; // edi
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-1Ch] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-8h] BYREF

  hKey = 0;
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  String = v7;
  if ( v7 > 0 )
    String = (unsigned __int16)v7 | 0x80070000;
  if ( String >= 0 )
  {
    if ( a4 == 11 )
    {
      Type = 0;
      String = UstRegQueryDword(hKey, a3, &Type);
      if ( String >= 0 )
      {
        v10 = 0;
        if ( Type )
          v10 = -1;
        if ( pvarg->vt != 11 )
        {
          ATL::CComVariant::Clear((ATL::CComVariant *)pvarg);
          pvarg->vt = 11;
        }
        pvarg->iVal = v10;
      }
    }
    else if ( ((a4 - 3) & 0xFFEF) != 0 )
    {
      if ( ((a4 - 2) & 0xFFEF) != 0 )
      {
        if ( (unsigned __int16)(a4 - 16) <= 1u )
        {
          v21 = 0;
          String = -2147024809;
          v22 = -2147024809;
          if ( !hKey || !a3 )
            goto LABEL_48;
          LODWORD(bstrString) = 0;
          cbData = 0;
          Type = 4;
          v22 = RegQueryValueExW(hKey, a3, 0, &cbData, (LPBYTE)&bstrString, &Type);
          v23 = v22 < 0;
          if ( v22 > 0 )
          {
            v22 = (unsigned __int16)v22 | 0x80070000;
            v23 = v22 < 0;
          }
          if ( !v23 )
          {
            if ( cbData != 4 || Type != 4 )
              goto LABEL_62;
            v21 = (unsigned __int8)bstrString;
            String = v22;
          }
          else
          {
LABEL_48:
            String = v22;
            if ( v22 < 0 )
              goto LABEL_62;
          }
          if ( pvarg->vt != 17 )
          {
            if ( pvarg->vt == 4095 )
              pvarg->vt = 8;
            VariantClear(pvarg);
            pvarg->vt = 17;
          }
          pvarg->bVal = v21;
        }
        else
        {
          if ( a4 == 8 )
          {
            v11 = 0;
            pbstr = 0;
            v12 = hKey;
            Type = 0;
            cbData = 0;
            v13 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
            String = v13;
            if ( v13 > 0 )
              String = (unsigned __int16)v13 | 0x80070000;
            if ( String >= 0 )
            {
              if ( Type - 1 <= 1 || Type == 7 )
              {
                if ( cbData > 2 )
                {
                  v14 = cbData >> 1;
                  bstrString = 0;
                  v15 = SysAllocStringLen(0, cbData >> 1);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                    &bstrString,
                    v15);
                  v16 = bstrString;
                  if ( bstrString )
                  {
                    String = UstRegQueryString(v12, a3, bstrString, v14);
                    if ( String >= 0 )
                    {
                      v17 = v16;
                      v16 = 0;
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                        &pbstr,
                        v17);
                      v11 = pbstr;
                    }
                  }
                  else
                  {
                    String = -2147024882;
                  }
                  if ( v16 )
                    SysFreeString(v16);
                  if ( String >= 0 )
                  {
                    v18 = v11;
                    v11 = 0;
                    pvarg->llVal = (LONGLONG)v18;
                    pvarg->vt = 8;
                  }
                }
                else
                {
                  String = -2147024664;
                }
              }
              else
              {
                String = -2147024809;
              }
            }
          }
          else
          {
            if ( a4 != 8200 )
            {
              if ( a4 == 8204 )
                String = GetMultiValueSetting(hKey, v8, (struct ATL::CComVariant *)pvarg);
              else
                String = -2147024809;
              goto LABEL_62;
            }
            pbstr = 0;
            String = UstRegQueryBSTRAlloc(hKey, a3);
            v11 = pbstr;
            if ( String >= 0 )
            {
              v19 = SysStringLen(pbstr);
              String = UstVarLib::CscVarUtil_ConvertMULTISZToVariant(
                         v11,
                         (const unsigned __int16 *)(v19 + 1),
                         (unsigned int)pvarg,
                         v20);
            }
          }
          if ( v11 )
            SysFreeString(v11);
        }
      }
      else
      {
        LODWORD(bstrString) = 0;
        String = UstRegQueryDword(hKey, a3, (unsigned int *)&bstrString);
        if ( String >= 0 )
        {
          v24 = (__int16)bstrString;
          if ( pvarg->vt != 2 )
          {
            ATL::CComVariant::Clear((ATL::CComVariant *)pvarg);
            pvarg->vt = 2;
          }
          pvarg->iVal = v24;
        }
      }
    }
    else
    {
      LODWORD(bstrString) = 0;
      String = UstRegQueryDword(hKey, a3, (unsigned int *)&bstrString);
      if ( String >= 0 )
      {
        v25 = (int)bstrString;
        if ( pvarg->vt != 3 )
        {
          ATL::CComVariant::Clear((ATL::CComVariant *)pvarg);
          pvarg->vt = 3;
        }
        pvarg->lVal = v25;
      }
    }
  }
LABEL_62:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800025b0  push    rbp
0x1800025b2  push    rbx
0x1800025b3  push    rsi
0x1800025b4  push    rdi
0x1800025b5  push    r12
0x1800025b7  push    r14
0x1800025b9  push    r15
0x1800025bb  mov     rbp, rsp
0x1800025be  sub     rsp, 50h
0x1800025c2  movzx   ebx, r9w
0x1800025c6  mov     r14, r8
0x1800025c9  xor     r12d, r12d
0x1800025cc  mov     [rbp+hKey], r12
0x1800025d0  lea     rax, [rbp+hKey]
0x1800025d4  mov     [rsp+50h+phkResult], rax; phkResult
0x1800025d9  mov     r9d, 20019h; samDesired
0x1800025df  xor     r8d, r8d; ulOptions
0x1800025e2  call    cs:__imp_RegOpenKeyExW
0x1800025e8  mov     esi, eax
0x1800025ea  test    eax, eax
0x1800025ec  jle     short loc_1800025F7
0x1800025ee  movzx   esi, ax
0x1800025f1  or      esi, 80070000h
0x1800025f7  test    esi, esi
0x1800025f9  js      loc_180002919
0x1800025ff  cmp     bx, 0Bh
0x180002603  jnz     short loc_180002653
0x180002605  mov     [rbp+Type], r12d
0x180002609  lea     r8, [rbp+Type]; unsigned int *
0x18000260d  mov     rdx, r14; unsigned __int16 *
0x180002610  mov     rcx, [rbp+hKey]; HKEY
0x180002614  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x180002619  mov     esi, eax
0x18000261b  test    eax, eax
0x18000261d  js      loc_180002919
0x180002623  mov     eax, 0FFFFFFFFh
0x180002628  mov     edi, r12d
0x18000262b  cmp     [rbp+Type], r12d
0x18000262f  cmovnz  di, ax
0x180002633  mov     rbx, [rbp+pvarg]
0x180002637  cmp     word ptr [rbx], 0Bh
0x18000263b  jz      short loc_18000264A
0x18000263d  mov     rcx, rbx; this
0x180002640  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x180002645  mov     word ptr [rbx], 0Bh
0x18000264a  mov     [rbx+8], di
0x18000264e  jmp     loc_180002919
0x180002653  lea     eax, [rbx-3]
0x180002656  mov     ecx, 0FFEFh
0x18000265b  test    cx, ax
0x18000265e  jz      loc_1800028E2
0x180002664  lea     eax, [rbx-2]
0x180002667  test    cx, ax
0x18000266a  jz      loc_1800028A7
0x180002670  lea     eax, [rbx-10h]
0x180002673  cmp     ax, 1
0x180002677  jbe     loc_1800027F9
0x18000267d  cmp     bx, 8
0x180002681  jnz     loc_180002778
0x180002687  mov     rbx, r12
0x18000268a  mov     [rbp+pbstr], rbx
0x18000268e  mov     r15, [rbp+hKey]
0x180002692  mov     [rbp+Type], r12d
0x180002696  mov     [rbp+cbData], r12d
0x18000269a  lea     rax, [rbp+cbData]
0x18000269e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800026a3  mov     [rsp+50h+phkResult], r12; lpData
0x1800026a8  lea     r9, [rbp+Type]; lpType
0x1800026ac  xor     r8d, r8d; lpReserved
0x1800026af  mov     rdx, r14; lpValueName
0x1800026b2  mov     rcx, r15; hKey
0x1800026b5  call    cs:__imp_RegQueryValueExW
0x1800026bb  mov     esi, eax
0x1800026bd  test    eax, eax
0x1800026bf  jle     short loc_1800026CA
0x1800026c1  movzx   esi, ax
0x1800026c4  or      esi, 80070000h
0x1800026ca  test    esi, esi
0x1800026cc  js      loc_180002776
0x1800026d2  mov     ecx, [rbp+Type]
0x1800026d5  lea     eax, [rcx-1]
0x1800026d8  cmp     eax, 1
0x1800026db  jbe     short loc_1800026EC
0x1800026dd  cmp     ecx, 7
0x1800026e0  jz      short loc_1800026EC
0x1800026e2  mov     esi, 80070057h
0x1800026e7  jmp     loc_180002776
0x1800026ec  mov     esi, [rbp+cbData]
0x1800026ef  cmp     esi, 2
0x1800026f2  ja      short loc_1800026FB
0x1800026f4  mov     esi, 800700E8h
0x1800026f9  jmp     short loc_180002776
0x1800026fb  shr     esi, 1
0x1800026fd  mov     [rbp+bstrString], r12
0x180002701  mov     edx, esi; ui
0x180002703  xor     ecx, ecx; strIn
0x180002705  call    cs:__imp_SysAllocStringLen
0x18000270b  mov     rdx, rax
0x18000270e  lea     rcx, [rbp+bstrString]
0x180002712  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180002717  mov     rdi, [rbp+bstrString]
0x18000271b  test    rdi, rdi
0x18000271e  jz      short loc_18000274C
0x180002720  mov     r9d, esi; unsigned int
0x180002723  mov     r8, rdi; unsigned __int16 *
0x180002726  mov     rdx, r14; unsigned __int16 *
0x180002729  mov     rcx, r15; HKEY
0x18000272c  call    ?UstRegQueryString@@YAJPEAUHKEY__@@PEBGPEAGK@Z; UstRegQueryString(HKEY__ *,ushort const *,ushort *,ulong)
0x180002731  mov     esi, eax
0x180002733  test    eax, eax
0x180002735  js      short loc_180002751
0x180002737  mov     rdx, rdi
0x18000273a  mov     rdi, r12
0x18000273d  lea     rcx, [rbp+pbstr]
0x180002741  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180002746  mov     rbx, [rbp+pbstr]
0x18000274a  jmp     short loc_180002751
0x18000274c  mov     esi, 8007000Eh
0x180002751  test    rdi, rdi
0x180002754  jz      short loc_18000275F
0x180002756  mov     rcx, rdi; bstrString
0x180002759  call    cs:__imp_SysFreeString
0x18000275f  test    esi, esi
0x180002761  js      short loc_180002776
0x180002763  mov     rax, rbx
0x180002766  mov     rbx, r12
0x180002769  mov     rcx, [rbp+pvarg]
0x18000276d  mov     [rcx+8], rax
0x180002771  mov     word ptr [rcx], 8
0x180002776  jmp     short loc_1800027BA
0x180002778  mov     eax, 2008h
0x18000277d  cmp     bx, ax
0x180002780  jnz     short loc_1800027D1
0x180002782  mov     [rbp+pbstr], r12
0x180002786  lea     r8, [rbp+pbstr]
0x18000278a  mov     rdx, r14; unsigned __int16 *
0x18000278d  mov     rcx, [rbp+hKey]; HKEY
0x180002791  call    ?UstRegQueryBSTRAlloc@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UstRegQueryBSTRAlloc(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180002796  mov     esi, eax
0x180002798  mov     rbx, [rbp+pbstr]
0x18000279c  test    eax, eax
0x18000279e  js      short loc_1800027BA
0x1800027a0  mov     rcx, rbx; pbstr
0x1800027a3  call    cs:__imp_SysStringLen
0x1800027a9  lea     edx, [rax+1]; unsigned __int16 *
0x1800027ac  mov     r8, [rbp+pvarg]; unsigned int
0x1800027b0  mov     rcx, rbx; psz
0x1800027b3  call    ?CscVarUtil_ConvertMULTISZToVariant@UstVarLib@@YAJPEBGKPEAUtagVARIANT@@@Z; UstVarLib::CscVarUtil_ConvertMULTISZToVariant(ushort const *,ulong,tagVARIANT *)
0x1800027b8  mov     esi, eax
0x1800027ba  test    rbx, rbx
0x1800027bd  jz      loc_180002919
0x1800027c3  mov     rcx, rbx; bstrString
0x1800027c6  call    cs:__imp_SysFreeString
0x1800027cc  jmp     loc_180002919
0x1800027d1  mov     eax, 200Ch
0x1800027d6  cmp     bx, ax
0x1800027d9  jnz     short loc_1800027EF
0x1800027db  mov     r8, [rbp+pvarg]; struct ATL::CComVariant *
0x1800027df  mov     rcx, [rbp+hKey]; HKEY
0x1800027e3  call    ?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z; GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)
0x1800027e8  mov     esi, eax
0x1800027ea  jmp     loc_180002919
0x1800027ef  mov     esi, 80070057h
0x1800027f4  jmp     loc_180002919
0x1800027f9  mov     edi, r12d
0x1800027fc  mov     rcx, [rbp+hKey]; hKey
0x180002800  mov     esi, 80070057h
0x180002805  mov     eax, esi
0x180002807  test    rcx, rcx
0x18000280a  jz      short loc_18000286D
0x18000280c  test    r14, r14
0x18000280f  jz      short loc_18000286D
0x180002811  mov     dword ptr [rbp+bstrString], r12d
0x180002815  mov     [rbp+cbData], r12d
0x180002819  mov     [rbp+Type], 4
0x180002820  lea     rax, [rbp+Type]
0x180002824  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180002829  lea     rax, [rbp+bstrString]
0x18000282d  mov     [rsp+50h+phkResult], rax; lpData
0x180002832  lea     r9, [rbp+cbData]; lpType
0x180002836  xor     r8d, r8d; lpReserved
0x180002839  mov     rdx, r14; lpValueName
0x18000283c  call    cs:__imp_RegQueryValueExW
0x180002842  test    eax, eax
0x180002844  jle     short loc_180002850
0x180002846  movzx   eax, ax
0x180002849  or      eax, 80070000h
0x18000284e  test    eax, eax
0x180002850  js      short loc_18000286D
0x180002852  cmp     [rbp+cbData], 4
0x180002856  jnz     loc_180002919
0x18000285c  cmp     [rbp+Type], 4
0x180002860  jnz     loc_180002919
0x180002866  mov     edi, dword ptr [rbp+bstrString]
0x180002869  mov     esi, eax
0x18000286b  jmp     short loc_180002877
0x18000286d  mov     esi, eax
0x18000286f  test    eax, eax
0x180002871  js      loc_180002919
0x180002877  mov     rbx, [rbp+pvarg]
0x18000287b  movzx   eax, word ptr [rbx]
0x18000287e  cmp     ax, 11h
0x180002882  jz      short loc_1800028A1
0x180002884  mov     ecx, 0FFFh
0x180002889  cmp     ax, cx
0x18000288c  jnz     short loc_180002893
0x18000288e  mov     word ptr [rbx], 8
0x180002893  mov     rcx, rbx; pvarg
0x180002896  call    cs:__imp_VariantClear
0x18000289c  mov     word ptr [rbx], 11h
0x1800028a1  mov     [rbx+8], dil
0x1800028a5  jmp     short loc_180002919
0x1800028a7  mov     dword ptr [rbp+bstrString], r12d
0x1800028ab  lea     r8, [rbp+bstrString]; unsigned int *
0x1800028af  mov     rdx, r14; unsigned __int16 *
0x1800028b2  mov     rcx, [rbp+hKey]; HKEY
0x1800028b6  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x1800028bb  mov     esi, eax
0x1800028bd  test    eax, eax
0x1800028bf  js      short loc_180002919
0x1800028c1  movzx   edi, word ptr [rbp+bstrString]
0x1800028c5  mov     rbx, [rbp+pvarg]
0x1800028c9  cmp     word ptr [rbx], 2
0x1800028cd  jz      short loc_1800028DC
0x1800028cf  mov     rcx, rbx; this
0x1800028d2  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1800028d7  mov     word ptr [rbx], 2
0x1800028dc  mov     [rbx+8], di
0x1800028e0  jmp     short loc_180002919
0x1800028e2  mov     dword ptr [rbp+bstrString], r12d
0x1800028e6  lea     r8, [rbp+bstrString]; unsigned int *
0x1800028ea  mov     rdx, r14; unsigned __int16 *
0x1800028ed  mov     rcx, [rbp+hKey]; HKEY
0x1800028f1  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x1800028f6  mov     esi, eax
0x1800028f8  test    eax, eax
0x1800028fa  js      short loc_180002919
0x1800028fc  mov     edi, dword ptr [rbp+bstrString]
0x1800028ff  mov     rbx, [rbp+pvarg]
0x180002903  cmp     word ptr [rbx], 3
0x180002907  jz      short loc_180002916
0x180002909  mov     rcx, rbx; this
0x18000290c  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x180002911  mov     word ptr [rbx], 3
0x180002916  mov     [rbx+8], edi
0x180002919  mov     rcx, [rbp+hKey]; hKey
0x18000291d  test    rcx, rcx
0x180002920  jz      short loc_180002929
0x180002922  call    cs:__imp_RegCloseKey
0x180002928  nop
0x180002929  mov     eax, esi
0x18000292b  add     rsp, 50h
0x18000292f  pop     r15
0x180002931  pop     r14
0x180002933  pop     r12
0x180002935  pop     rdi
0x180002936  pop     rsi
0x180002937  pop     rbx
0x180002938  pop     rbp
0x180002939  retn
```
