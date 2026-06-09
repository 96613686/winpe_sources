# GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)

- ea: `0x180022490`
- end: `0x18002297a`
- name: `?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z`
- size: `1258`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, WCHAR *, __int16, VARIANTARG *pvarg)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a7e0`
- `0x180051d64`

## callees

- `0x180022490`
- `0x180025600`
- `0x180026280`
- `0x18002744c`
- `0x180051d64`
- `0x1800521c4`
- `0x1800523d0`
- `0x180052714`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800224c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800224c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002254a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800225ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800226bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022767`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002254a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800225ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800226bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022767`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002257a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002257a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800227cc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800227cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180022898`
- `OLEAUT32!__imp_SysFreeString` at `0x1800228fd`
- `OLEAUT32!__imp_SysFreeString` at `0x180022898`
- `OLEAUT32!__imp_SysFreeString` at `0x1800228fd`
- `OLEAUT32!__imp_SysStringLen` at `0x1800228d8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800228d8`
- `OLEAUT32!__imp_VariantClear` at `0x18002263f`
- `OLEAUT32!__imp_VariantClear` at `0x18002263f`

## pseudocode

```c
__int64 __fastcall GetStoredValue(HKEY a1, const unsigned __int16 *a2, WCHAR *a3, __int16 a4, VARIANTARG *pvarg)
{
  LSTATUS v7; // eax
  const unsigned __int16 *v8; // rdx
  int String; // edi
  OLECHAR *v10; // rbx
  HKEY v11; // rsi
  LSTATUS v12; // eax
  LSTATUS v14; // eax
  BYTE v15; // si
  int v16; // ebx
  LSTATUS v17; // eax
  DWORD v18; // esi
  LSTATUS v19; // eax
  LONG v20; // esi
  DWORD v21; // edi
  BSTR v22; // rax
  OLECHAR *v23; // r15
  UINT v24; // eax
  struct tagVARIANT *v25; // r9
  SHORT v26; // si
  BYTE Data[8]; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-20h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  BSTR pbstr[2]; // [rsp+48h] [rbp-10h] BYREF

  hKey = 0;
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  String = v7;
  if ( v7 > 0 )
    String = (unsigned __int16)v7 | 0x80070000;
  if ( String < 0 )
    goto LABEL_14;
  if ( a4 == 11 )
  {
    v16 = -2147024809;
    if ( hKey && a3 )
    {
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      v17 = RegQueryValueExW(hKey, a3, 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData);
      String = v17;
      if ( v17 > 0 )
        String = (unsigned __int16)v17 | 0x80070000;
      if ( String >= 0 )
      {
        if ( *(_DWORD *)Data != 4 || cbData != 4 )
          goto LABEL_74;
        v18 = Type;
        if ( pvarg->vt != 11 )
        {
          ATL::CComVariant::~CComVariant((ATL::CComVariant *)pvarg);
          pvarg->vt = 11;
        }
        pvarg->iVal = -(v18 != 0);
        goto LABEL_14;
      }
      v16 = String;
    }
    String = v16;
    goto LABEL_14;
  }
  if ( ((a4 - 3) & 0xFFEF) != 0 )
  {
    if ( ((a4 - 2) & 0xFFEF) != 0 )
    {
      if ( (unsigned __int16)(a4 - 16) > 1u )
      {
        switch ( a4 )
        {
          case 8:
            v10 = 0;
            pbstr[0] = 0;
            v11 = hKey;
            Type = 0;
            cbData = 0;
            v12 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
            String = v12;
            if ( v12 > 0 )
              String = (unsigned __int16)v12 | 0x80070000;
            if ( String < 0 )
              goto LABEL_12;
            if ( Type - 1 <= 1 || Type == 7 )
            {
              if ( cbData <= 2 )
              {
                String = -2147024664;
                goto LABEL_14;
              }
              v21 = cbData >> 1;
              *(_QWORD *)Data = 0;
              v22 = SysAllocStringLen(0, cbData >> 1);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                Data,
                v22);
              v23 = *(OLECHAR **)Data;
              if ( *(_QWORD *)Data )
              {
                String = UstRegQueryString(v11, a3, *(unsigned __int16 **)Data, v21);
                if ( String < 0 )
                {
                  SysFreeString(v23);
LABEL_12:
                  if ( v10 )
                    SysFreeString(v10);
                  goto LABEL_14;
                }
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  pbstr,
                  v23);
                v10 = pbstr[0];
              }
              else
              {
                String = -2147024882;
              }
              if ( String >= 0 )
              {
                pvarg->llVal = (LONGLONG)v10;
                pvarg->vt = 8;
                goto LABEL_14;
              }
              goto LABEL_12;
            }
            break;
          case 8200:
            pbstr[0] = 0;
            String = UstRegQueryBSTRAlloc(hKey, a3);
            v10 = pbstr[0];
            if ( String >= 0 )
            {
              v24 = SysStringLen(pbstr[0]);
              String = UstVarLib::CscVarUtil_ConvertMULTISZToVariant(
                         v10,
                         (const unsigned __int16 *)(v24 + 1),
                         (__int64)pvarg,
                         v25);
            }
            goto LABEL_12;
          case 8204:
            String = GetMultiValueSetting(hKey, v8, (struct ATL::CComVariant *)pvarg);
            goto LABEL_14;
        }
        String = -2147024809;
        goto LABEL_14;
      }
      String = -2147024809;
      if ( hKey && a3 )
      {
        *(_DWORD *)Data = 0;
        Type = 0;
        cbData = 4;
        v14 = RegQueryValueExW(hKey, a3, 0, &Type, Data, &cbData);
        String = v14;
        if ( v14 > 0 )
          String = (unsigned __int16)v14 | 0x80070000;
        if ( String >= 0 )
        {
          if ( Type == 4 && cbData == 4 )
          {
            v15 = Data[0];
            if ( pvarg->vt != 17 )
            {
              if ( pvarg->vt == 4095 )
                pvarg->vt = 8;
              VariantClear(pvarg);
              pvarg->vt = 17;
            }
            pvarg->bVal = v15;
            goto LABEL_14;
          }
LABEL_74:
          String = -2147024809;
        }
      }
    }
    else
    {
      Type = 0;
      String = UstRegQueryDword(hKey, a3, &Type);
      if ( String >= 0 )
      {
        v26 = Type;
        if ( pvarg->vt != 2 )
        {
          ATL::CComVariant::~CComVariant((ATL::CComVariant *)pvarg);
          pvarg->vt = 2;
        }
        pvarg->iVal = v26;
      }
    }
  }
  else
  {
    String = -2147024809;
    if ( hKey && a3 )
    {
      *(_DWORD *)Data = 0;
      Type = 0;
      cbData = 4;
      v19 = RegQueryValueExW(hKey, a3, 0, &Type, Data, &cbData);
      String = v19;
      if ( v19 > 0 )
        String = (unsigned __int16)v19 | 0x80070000;
      if ( String >= 0 )
      {
        if ( Type != 4 || cbData != 4 )
          goto LABEL_74;
        v20 = *(_DWORD *)Data;
        if ( pvarg->vt != 3 )
        {
          ATL::CComVariant::~CComVariant((ATL::CComVariant *)pvarg);
          pvarg->vt = 3;
        }
        pvarg->lVal = v20;
      }
    }
  }
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180022490  push    rbp
0x180022492  push    rbx
0x180022493  push    rsi
0x180022494  push    rdi
0x180022495  push    r14
0x180022497  push    r15
0x180022499  mov     rbp, rsp
0x18002249c  sub     rsp, 58h
0x1800224a0  movzx   ebx, r9w
0x1800224a4  mov     r14, r8
0x1800224a7  xor     r15d, r15d
0x1800224aa  mov     [rbp+hKey], r15
0x1800224ae  lea     rax, [rbp+hKey]
0x1800224b2  mov     [rsp+58h+phkResult], rax; phkResult
0x1800224b7  mov     r9d, 20019h; samDesired
0x1800224bd  xor     r8d, r8d; ulOptions
0x1800224c0  call    cs:__imp_RegOpenKeyExW
0x1800224c7  nop     dword ptr [rax+rax+00h]
0x1800224cc  mov     edi, eax
0x1800224ce  test    eax, eax
0x1800224d0  jg      loc_180022596
0x1800224d6  test    edi, edi
0x1800224d8  js      loc_180022571
0x1800224de  cmp     bx, 0Bh
0x1800224e2  jz      loc_180022672
0x1800224e8  lea     eax, [rbx-3]
0x1800224eb  mov     ecx, 0FFEFh
0x1800224f0  test    cx, ax
0x1800224f3  jz      loc_18002271C
0x1800224f9  lea     eax, [rbx-2]
0x1800224fc  test    cx, ax
0x1800224ff  jz      loc_180022930
0x180022505  lea     eax, [rbx-10h]
0x180022508  cmp     ax, 1
0x18002250c  jbe     loc_1800225A4
0x180022512  cmp     bx, 8
0x180022516  jnz     loc_1800228A9
0x18002251c  mov     rbx, r15
0x18002251f  mov     [rbp+pbstr], rbx
0x180022523  mov     rsi, [rbp+hKey]
0x180022527  mov     [rbp+Type], r15d
0x18002252b  mov     [rbp+cbData], r15d
0x18002252f  lea     rax, [rbp+cbData]
0x180022533  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180022538  mov     [rsp+58h+phkResult], r15; lpData
0x18002253d  lea     r9, [rbp+Type]; lpType
0x180022541  xor     r8d, r8d; lpReserved
0x180022544  mov     rdx, r14; lpValueName
0x180022547  mov     rcx, rsi; hKey
0x18002254a  call    cs:__imp_RegQueryValueExW
0x180022551  nop     dword ptr [rax+rax+00h]
0x180022556  mov     edi, eax
0x180022558  test    eax, eax
0x18002255a  jg      loc_180022659
0x180022560  test    edi, edi
0x180022562  jns     loc_180022839
0x180022568  test    rbx, rbx
0x18002256b  jnz     loc_1800228FA
0x180022571  mov     rcx, [rbp+hKey]; hKey
0x180022575  test    rcx, rcx
0x180022578  jz      short loc_180022586
0x18002257a  call    cs:__imp_RegCloseKey
0x180022581  nop     dword ptr [rax+rax+00h]
0x180022586  mov     eax, edi
0x180022588  add     rsp, 58h
0x18002258c  pop     r15
0x18002258e  pop     r14
0x180022590  pop     rdi
0x180022591  pop     rsi
0x180022592  pop     rbx
0x180022593  pop     rbp
0x180022594  retn
0x180022596  movzx   edi, ax
0x180022599  or      edi, 80070000h
0x18002259f  jmp     loc_1800224D6
0x1800225a4  mov     esi, r15d
0x1800225a7  mov     rcx, [rbp+hKey]; hKey
0x1800225ab  mov     ebx, 80070057h
0x1800225b0  mov     edi, ebx
0x1800225b2  test    rcx, rcx
0x1800225b5  jz      loc_18002280C
0x1800225bb  test    r14, r14
0x1800225be  jz      loc_18002280C
0x1800225c4  mov     dword ptr [rbp+Data], r15d
0x1800225c8  mov     [rbp+Type], r15d
0x1800225cc  mov     [rbp+cbData], 4
0x1800225d3  lea     rax, [rbp+cbData]
0x1800225d7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800225dc  lea     rax, [rbp+Data]
0x1800225e0  mov     [rsp+58h+phkResult], rax; lpData
0x1800225e5  lea     r9, [rbp+Type]; lpType
0x1800225e9  xor     r8d, r8d; lpReserved
0x1800225ec  mov     rdx, r14; lpValueName
0x1800225ef  call    cs:__imp_RegQueryValueExW
0x1800225f6  nop     dword ptr [rax+rax+00h]
0x1800225fb  mov     edi, eax
0x1800225fd  test    eax, eax
0x1800225ff  jg      short loc_180022667
0x180022601  test    edi, edi
0x180022603  js      loc_180022571
0x180022609  cmp     [rbp+Type], 4
0x18002260d  jnz     loc_180022972
0x180022613  cmp     [rbp+cbData], 4
0x180022617  jnz     loc_180022972
0x18002261d  mov     esi, dword ptr [rbp+Data]
0x180022620  mov     rbx, [rbp+pvarg]
0x180022624  movzx   eax, word ptr [rbx]
0x180022627  cmp     ax, 11h
0x18002262b  jz      short loc_180022650
0x18002262d  mov     ecx, 0FFFh
0x180022632  cmp     ax, cx
0x180022635  jnz     short loc_18002263C
0x180022637  mov     word ptr [rbx], 8
0x18002263c  mov     rcx, rbx; pvarg
0x18002263f  call    cs:__imp_VariantClear
0x180022646  nop     dword ptr [rax+rax+00h]
0x18002264b  mov     word ptr [rbx], 11h
0x180022650  mov     [rbx+8], sil
0x180022654  jmp     loc_180022571
0x180022659  movzx   edi, ax
0x18002265c  or      edi, 80070000h
0x180022662  jmp     loc_180022560
0x180022667  movzx   edi, ax
0x18002266a  or      edi, 80070000h
0x180022670  jmp     short loc_180022601
0x180022672  mov     esi, r15d
0x180022675  mov     rcx, [rbp+hKey]; hKey
0x180022679  mov     ebx, 80070057h
0x18002267e  test    rcx, rcx
0x180022681  jz      loc_180022819
0x180022687  test    r14, r14
0x18002268a  jz      loc_180022819
0x180022690  mov     [rbp+Type], r15d
0x180022694  mov     dword ptr [rbp+Data], r15d
0x180022698  mov     [rbp+cbData], 4
0x18002269f  lea     rax, [rbp+cbData]
0x1800226a3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800226a8  lea     rax, [rbp+Type]
0x1800226ac  mov     [rsp+58h+phkResult], rax; lpData
0x1800226b1  lea     r9, [rbp+Data]; lpType
0x1800226b5  xor     r8d, r8d; lpReserved
0x1800226b8  mov     rdx, r14; lpValueName
0x1800226bb  call    cs:__imp_RegQueryValueExW
0x1800226c2  nop     dword ptr [rax+rax+00h]
0x1800226c7  mov     edi, eax
0x1800226c9  test    eax, eax
0x1800226cb  jg      short loc_180022711
0x1800226cd  test    edi, edi
0x1800226cf  js      loc_180022835
0x1800226d5  cmp     dword ptr [rbp+Data], 4
0x1800226d9  jnz     loc_180022972
0x1800226df  cmp     [rbp+cbData], 4
0x1800226e3  jnz     loc_180022972
0x1800226e9  mov     esi, [rbp+Type]
0x1800226ec  mov     rbx, [rbp+pvarg]
0x1800226f0  cmp     word ptr [rbx], 0Bh
0x1800226f4  jz      short loc_180022703
0x1800226f6  mov     rcx, rbx; this
0x1800226f9  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x1800226fe  mov     word ptr [rbx], 0Bh
0x180022703  neg     esi
0x180022705  sbb     ax, ax
0x180022708  mov     [rbx+8], ax
0x18002270c  jmp     loc_180022571
0x180022711  movzx   edi, ax
0x180022714  or      edi, 80070000h
0x18002271a  jmp     short loc_1800226CD
0x18002271c  mov     esi, r15d
0x18002271f  mov     rcx, [rbp+hKey]; hKey
0x180022723  mov     ebx, 80070057h
0x180022728  mov     edi, ebx
0x18002272a  test    rcx, rcx
0x18002272d  jz      loc_180022828
0x180022733  test    r14, r14
0x180022736  jz      loc_180022828
0x18002273c  mov     dword ptr [rbp+Data], r15d
0x180022740  mov     [rbp+Type], r15d
0x180022744  mov     [rbp+cbData], 4
0x18002274b  lea     rax, [rbp+cbData]
0x18002274f  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180022754  lea     rax, [rbp+Data]
0x180022758  mov     [rsp+58h+phkResult], rax; lpData
0x18002275d  lea     r9, [rbp+Type]; lpType
0x180022761  xor     r8d, r8d; lpReserved
0x180022764  mov     rdx, r14; lpValueName
0x180022767  call    cs:__imp_RegQueryValueExW
0x18002276e  nop     dword ptr [rax+rax+00h]
0x180022773  mov     edi, eax
0x180022775  test    eax, eax
0x180022777  jg      short loc_1800227B7
0x180022779  test    edi, edi
0x18002277b  js      loc_180022571
0x180022781  cmp     [rbp+Type], 4
0x180022785  jnz     loc_180022972
0x18002278b  cmp     [rbp+cbData], 4
0x18002278f  jnz     loc_180022972
0x180022795  mov     esi, dword ptr [rbp+Data]
0x180022798  mov     rbx, [rbp+pvarg]
0x18002279c  cmp     word ptr [rbx], 3
0x1800227a0  jz      short loc_1800227AF
0x1800227a2  mov     rcx, rbx; this
0x1800227a5  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x1800227aa  mov     word ptr [rbx], 3
0x1800227af  mov     [rbx+8], esi
0x1800227b2  jmp     loc_180022571
0x1800227b7  movzx   edi, ax
0x1800227ba  or      edi, 80070000h
0x1800227c0  jmp     short loc_180022779
0x1800227c2  shr     edi, 1
0x1800227c4  mov     qword ptr [rbp+Data], r15
0x1800227c8  mov     edx, edi; ui
0x1800227ca  xor     ecx, ecx; strIn
0x1800227cc  call    cs:__imp_SysAllocStringLen
0x1800227d3  nop     dword ptr [rax+rax+00h]
0x1800227d8  mov     rdx, rax
0x1800227db  lea     rcx, [rbp+Data]
0x1800227df  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800227e4  mov     r15, qword ptr [rbp+Data]
0x1800227e8  test    r15, r15
0x1800227eb  jnz     short loc_180022869
0x1800227ed  mov     edi, 8007000Eh
0x1800227f2  test    edi, edi
0x1800227f4  js      loc_180022568
0x1800227fa  mov     rax, [rbp+pvarg]
0x1800227fe  mov     [rax+8], rbx
0x180022802  mov     word ptr [rax], 8
0x180022807  jmp     loc_180022571
0x18002280c  test    edi, edi
0x18002280e  jns     loc_180022620
0x180022814  jmp     loc_180022571
0x180022819  mov     edi, ebx
0x18002281b  test    ebx, ebx
0x18002281d  js      loc_180022571
0x180022823  jmp     loc_1800226EC
0x180022828  test    edi, edi
0x18002282a  js      loc_180022571
0x180022830  jmp     loc_180022798
0x180022835  mov     ebx, edi
0x180022837  jmp     short loc_180022819
0x180022839  mov     ecx, [rbp+Type]
0x18002283c  lea     eax, [rcx-1]
0x18002283f  cmp     eax, 1
0x180022842  jbe     short loc_180022853
0x180022844  cmp     ecx, 7
0x180022847  jz      short loc_180022853
0x180022849  mov     edi, 80070057h
0x18002284e  jmp     loc_180022571
0x180022853  mov     edi, [rbp+cbData]
0x180022856  cmp     edi, 2
0x180022859  ja      loc_1800227C2
0x18002285f  mov     edi, 800700E8h
0x180022864  jmp     loc_180022571
0x180022869  mov     r9d, edi; unsigned int
0x18002286c  mov     r8, r15; unsigned __int16 *
0x18002286f  mov     rdx, r14; unsigned __int16 *
0x180022872  mov     rcx, rsi; HKEY
0x180022875  call    ?UstRegQueryString@@YAJPEAUHKEY__@@PEBGPEAGK@Z; UstRegQueryString(HKEY__ *,ushort const *,ushort *,ulong)
0x18002287a  mov     edi, eax
0x18002287c  test    eax, eax
0x18002287e  js      short loc_180022895
0x180022880  mov     rdx, r15
0x180022883  lea     rcx, [rbp+pbstr]
0x180022887  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002288c  mov     rbx, [rbp+pbstr]
0x180022890  jmp     loc_1800227F2
0x180022895  mov     rcx, r15; bstrString
0x180022898  call    cs:__imp_SysFreeString
0x18002289f  nop     dword ptr [rax+rax+00h]
0x1800228a4  jmp     loc_180022568
0x1800228a9  mov     eax, 2008h
0x1800228ae  cmp     bx, ax
0x1800228b1  jnz     short loc_18002290E
0x1800228b3  mov     [rbp+pbstr], r15
0x1800228b7  lea     r8, [rbp+pbstr]
0x1800228bb  mov     rdx, r14; unsigned __int16 *
0x1800228be  mov     rcx, [rbp+hKey]; HKEY
0x1800228c2  call    ?UstRegQueryBSTRAlloc@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UstRegQueryBSTRAlloc(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800228c7  mov     edi, eax
0x1800228c9  mov     rbx, [rbp+pbstr]
0x1800228cd  test    eax, eax
0x1800228cf  js      loc_180022568
0x1800228d5  mov     rcx, rbx; pbstr
0x1800228d8  call    cs:__imp_SysStringLen
0x1800228df  nop     dword ptr [rax+rax+00h]
0x1800228e4  lea     edx, [rax+1]; unsigned __int16 *
0x1800228e7  mov     r8, [rbp+pvarg]; unsigned int
0x1800228eb  mov     rcx, rbx; psz
0x1800228ee  call    ?CscVarUtil_ConvertMULTISZToVariant@UstVarLib@@YAJPEBGKPEAUtagVARIANT@@@Z; UstVarLib::CscVarUtil_ConvertMULTISZToVariant(ushort const *,ulong,tagVARIANT *)
0x1800228f3  mov     edi, eax
0x1800228f5  jmp     loc_180022568
0x1800228fa  mov     rcx, rbx; bstrString
0x1800228fd  call    cs:__imp_SysFreeString
0x180022904  nop     dword ptr [rax+rax+00h]
0x180022909  jmp     loc_180022571
0x18002290e  mov     eax, 200Ch
0x180022913  cmp     bx, ax
0x180022916  jnz     loc_180022849
0x18002291c  mov     r8, [rbp+pvarg]; struct ATL::CComVariant *
0x180022920  mov     rcx, [rbp+hKey]; HKEY
0x180022924  call    ?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z; GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)
  ... truncated ...
```
