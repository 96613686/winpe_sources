# GetStoredValue(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant &)

- ea: `0x18001e560`
- end: `0x18001ea07`
- name: `?GetStoredValue@@YAJPEAUHKEY__@@PEBG1GAEAVCComVariant@ATL@@@Z`
- size: `1191`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16, struct ATL::CComVariant *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cc80`
- `0x18004ea70`

## callees

- `0x18001e560`
- `0x1800226f0`
- `0x180023980`
- `0x180024c20`
- `0x18004ea70`
- `0x18004eeac`
- `0x18004f08c`
- `0x18004f3a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e590`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e590`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e614`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e6ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e76c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e812`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e614`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e6ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e76c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e812`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e63e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e63e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001e871`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001e871`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e937`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e990`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e937`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e990`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e971`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e971`
- `OLEAUT32!__imp_VariantClear` at `0x18001e6f6`
- `OLEAUT32!__imp_VariantClear` at `0x18001e6f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
          ATL::CComVariant::~CComVariant(pvarg);
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
                         (unsigned int)pvarg,
                         v25);
            }
            goto LABEL_12;
          case 8204:
            String = GetMultiValueSetting(hKey, v8, pvarg);
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
          ATL::CComVariant::~CComVariant(pvarg);
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
          ATL::CComVariant::~CComVariant(pvarg);
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
0x18001e560  push    rbp
0x18001e562  push    rbx
0x18001e563  push    rsi
0x18001e564  push    rdi
0x18001e565  push    r14
0x18001e567  push    r15
0x18001e569  mov     rbp, rsp
0x18001e56c  sub     rsp, 58h
0x18001e570  movzx   ebx, r9w
0x18001e574  mov     r14, r8
0x18001e577  xor     r15d, r15d
0x18001e57a  mov     [rbp+hKey], r15
0x18001e57e  lea     rax, [rbp+hKey]
0x18001e582  mov     [rsp+58h+phkResult], rax; phkResult
0x18001e587  mov     r9d, 20019h; samDesired
0x18001e58d  xor     r8d, r8d; ulOptions
0x18001e590  call    cs:__imp_RegOpenKeyExW
0x18001e596  mov     edi, eax
0x18001e598  test    eax, eax
0x18001e59a  jg      loc_18001E653
0x18001e5a0  test    edi, edi
0x18001e5a2  js      loc_18001E635
0x18001e5a8  cmp     bx, 0Bh
0x18001e5ac  jz      loc_18001E723
0x18001e5b2  lea     eax, [rbx-3]
0x18001e5b5  mov     ecx, 0FFEFh
0x18001e5ba  test    cx, ax
0x18001e5bd  jz      loc_18001E7C7
0x18001e5c3  lea     eax, [rbx-2]
0x18001e5c6  test    cx, ax
0x18001e5c9  jz      loc_18001E9BD
0x18001e5cf  lea     eax, [rbx-10h]
0x18001e5d2  cmp     ax, 1
0x18001e5d6  jbe     loc_18001E661
0x18001e5dc  cmp     bx, 8
0x18001e5e0  jnz     loc_18001E942
0x18001e5e6  mov     rbx, r15
0x18001e5e9  mov     [rbp+pbstr], rbx
0x18001e5ed  mov     rsi, [rbp+hKey]
0x18001e5f1  mov     [rbp+Type], r15d
0x18001e5f5  mov     [rbp+cbData], r15d
0x18001e5f9  lea     rax, [rbp+cbData]
0x18001e5fd  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18001e602  mov     [rsp+58h+phkResult], r15; lpData
0x18001e607  lea     r9, [rbp+Type]; lpType
0x18001e60b  xor     r8d, r8d; lpReserved
0x18001e60e  mov     rdx, r14; lpValueName
0x18001e611  mov     rcx, rsi; hKey
0x18001e614  call    cs:__imp_RegQueryValueExW
0x18001e61a  mov     edi, eax
0x18001e61c  test    eax, eax
0x18001e61e  jg      loc_18001E70A
0x18001e624  test    edi, edi
0x18001e626  jns     loc_18001E8D8
0x18001e62c  test    rbx, rbx
0x18001e62f  jnz     loc_18001E98D
0x18001e635  mov     rcx, [rbp+hKey]; hKey
0x18001e639  test    rcx, rcx
0x18001e63c  jz      short loc_18001E644
0x18001e63e  call    cs:__imp_RegCloseKey
0x18001e644  mov     eax, edi
0x18001e646  add     rsp, 58h
0x18001e64a  pop     r15
0x18001e64c  pop     r14
0x18001e64e  pop     rdi
0x18001e64f  pop     rsi
0x18001e650  pop     rbx
0x18001e651  pop     rbp
0x18001e652  retn
0x18001e653  movzx   edi, ax
0x18001e656  or      edi, 80070000h
0x18001e65c  jmp     loc_18001E5A0
0x18001e661  mov     esi, r15d
0x18001e664  mov     rcx, [rbp+hKey]; hKey
0x18001e668  mov     ebx, 80070057h
0x18001e66d  mov     edi, ebx
0x18001e66f  test    rcx, rcx
0x18001e672  jz      loc_18001E8AB
0x18001e678  test    r14, r14
0x18001e67b  jz      loc_18001E8AB
0x18001e681  mov     dword ptr [rbp+Data], r15d
0x18001e685  mov     [rbp+Type], r15d
0x18001e689  mov     [rbp+cbData], 4
0x18001e690  lea     rax, [rbp+cbData]
0x18001e694  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18001e699  lea     rax, [rbp+Data]
0x18001e69d  mov     [rsp+58h+phkResult], rax; lpData
0x18001e6a2  lea     r9, [rbp+Type]; lpType
0x18001e6a6  xor     r8d, r8d; lpReserved
0x18001e6a9  mov     rdx, r14; lpValueName
0x18001e6ac  call    cs:__imp_RegQueryValueExW
0x18001e6b2  mov     edi, eax
0x18001e6b4  test    eax, eax
0x18001e6b6  jg      short loc_18001E718
0x18001e6b8  test    edi, edi
0x18001e6ba  js      loc_18001E635
0x18001e6c0  cmp     [rbp+Type], 4
0x18001e6c4  jnz     loc_18001E9FF
0x18001e6ca  cmp     [rbp+cbData], 4
0x18001e6ce  jnz     loc_18001E9FF
0x18001e6d4  mov     esi, dword ptr [rbp+Data]
0x18001e6d7  mov     rbx, [rbp+pvarg]
0x18001e6db  movzx   eax, word ptr [rbx]
0x18001e6de  cmp     ax, 11h
0x18001e6e2  jz      short loc_18001E701
0x18001e6e4  mov     ecx, 0FFFh
0x18001e6e9  cmp     ax, cx
0x18001e6ec  jnz     short loc_18001E6F3
0x18001e6ee  mov     word ptr [rbx], 8
0x18001e6f3  mov     rcx, rbx; pvarg
0x18001e6f6  call    cs:__imp_VariantClear
0x18001e6fc  mov     word ptr [rbx], 11h
0x18001e701  mov     [rbx+8], sil
0x18001e705  jmp     loc_18001E635
0x18001e70a  movzx   edi, ax
0x18001e70d  or      edi, 80070000h
0x18001e713  jmp     loc_18001E624
0x18001e718  movzx   edi, ax
0x18001e71b  or      edi, 80070000h
0x18001e721  jmp     short loc_18001E6B8
0x18001e723  mov     esi, r15d
0x18001e726  mov     rcx, [rbp+hKey]; hKey
0x18001e72a  mov     ebx, 80070057h
0x18001e72f  test    rcx, rcx
0x18001e732  jz      loc_18001E8B8
0x18001e738  test    r14, r14
0x18001e73b  jz      loc_18001E8B8
0x18001e741  mov     [rbp+Type], r15d
0x18001e745  mov     dword ptr [rbp+Data], r15d
0x18001e749  mov     [rbp+cbData], 4
0x18001e750  lea     rax, [rbp+cbData]
0x18001e754  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18001e759  lea     rax, [rbp+Type]
0x18001e75d  mov     [rsp+58h+phkResult], rax; lpData
0x18001e762  lea     r9, [rbp+Data]; lpType
0x18001e766  xor     r8d, r8d; lpReserved
0x18001e769  mov     rdx, r14; lpValueName
0x18001e76c  call    cs:__imp_RegQueryValueExW
0x18001e772  mov     edi, eax
0x18001e774  test    eax, eax
0x18001e776  jg      short loc_18001E7BC
0x18001e778  test    edi, edi
0x18001e77a  js      loc_18001E8D4
0x18001e780  cmp     dword ptr [rbp+Data], 4
0x18001e784  jnz     loc_18001E9FF
0x18001e78a  cmp     [rbp+cbData], 4
0x18001e78e  jnz     loc_18001E9FF
0x18001e794  mov     esi, [rbp+Type]
0x18001e797  mov     rbx, [rbp+pvarg]
0x18001e79b  cmp     word ptr [rbx], 0Bh
0x18001e79f  jz      short loc_18001E7AE
0x18001e7a1  mov     rcx, rbx; this
0x18001e7a4  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x18001e7a9  mov     word ptr [rbx], 0Bh
0x18001e7ae  neg     esi
0x18001e7b0  sbb     ax, ax
0x18001e7b3  mov     [rbx+8], ax
0x18001e7b7  jmp     loc_18001E635
0x18001e7bc  movzx   edi, ax
0x18001e7bf  or      edi, 80070000h
0x18001e7c5  jmp     short loc_18001E778
0x18001e7c7  mov     esi, r15d
0x18001e7ca  mov     rcx, [rbp+hKey]; hKey
0x18001e7ce  mov     ebx, 80070057h
0x18001e7d3  mov     edi, ebx
0x18001e7d5  test    rcx, rcx
0x18001e7d8  jz      loc_18001E8C7
0x18001e7de  test    r14, r14
0x18001e7e1  jz      loc_18001E8C7
0x18001e7e7  mov     dword ptr [rbp+Data], r15d
0x18001e7eb  mov     [rbp+Type], r15d
0x18001e7ef  mov     [rbp+cbData], 4
0x18001e7f6  lea     rax, [rbp+cbData]
0x18001e7fa  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18001e7ff  lea     rax, [rbp+Data]
0x18001e803  mov     [rsp+58h+phkResult], rax; lpData
0x18001e808  lea     r9, [rbp+Type]; lpType
0x18001e80c  xor     r8d, r8d; lpReserved
0x18001e80f  mov     rdx, r14; lpValueName
0x18001e812  call    cs:__imp_RegQueryValueExW
0x18001e818  mov     edi, eax
0x18001e81a  test    eax, eax
0x18001e81c  jg      short loc_18001E85C
0x18001e81e  test    edi, edi
0x18001e820  js      loc_18001E635
0x18001e826  cmp     [rbp+Type], 4
0x18001e82a  jnz     loc_18001E9FF
0x18001e830  cmp     [rbp+cbData], 4
0x18001e834  jnz     loc_18001E9FF
0x18001e83a  mov     esi, dword ptr [rbp+Data]
0x18001e83d  mov     rbx, [rbp+pvarg]
0x18001e841  cmp     word ptr [rbx], 3
0x18001e845  jz      short loc_18001E854
0x18001e847  mov     rcx, rbx; this
0x18001e84a  call    ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
0x18001e84f  mov     word ptr [rbx], 3
0x18001e854  mov     [rbx+8], esi
0x18001e857  jmp     loc_18001E635
0x18001e85c  movzx   edi, ax
0x18001e85f  or      edi, 80070000h
0x18001e865  jmp     short loc_18001E81E
0x18001e867  shr     edi, 1
0x18001e869  mov     qword ptr [rbp+Data], r15
0x18001e86d  mov     edx, edi; ui
0x18001e86f  xor     ecx, ecx; strIn
0x18001e871  call    cs:__imp_SysAllocStringLen
0x18001e877  mov     rdx, rax
0x18001e87a  lea     rcx, [rbp+Data]
0x18001e87e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001e883  mov     r15, qword ptr [rbp+Data]
0x18001e887  test    r15, r15
0x18001e88a  jnz     short loc_18001E908
0x18001e88c  mov     edi, 8007000Eh
0x18001e891  test    edi, edi
0x18001e893  js      loc_18001E62C
0x18001e899  mov     rax, [rbp+pvarg]
0x18001e89d  mov     [rax+8], rbx
0x18001e8a1  mov     word ptr [rax], 8
0x18001e8a6  jmp     loc_18001E635
0x18001e8ab  test    edi, edi
0x18001e8ad  jns     loc_18001E6D7
0x18001e8b3  jmp     loc_18001E635
0x18001e8b8  mov     edi, ebx
0x18001e8ba  test    ebx, ebx
0x18001e8bc  js      loc_18001E635
0x18001e8c2  jmp     loc_18001E797
0x18001e8c7  test    edi, edi
0x18001e8c9  js      loc_18001E635
0x18001e8cf  jmp     loc_18001E83D
0x18001e8d4  mov     ebx, edi
0x18001e8d6  jmp     short loc_18001E8B8
0x18001e8d8  mov     ecx, [rbp+Type]
0x18001e8db  lea     eax, [rcx-1]
0x18001e8de  cmp     eax, 1
0x18001e8e1  jbe     short loc_18001E8F2
0x18001e8e3  cmp     ecx, 7
0x18001e8e6  jz      short loc_18001E8F2
0x18001e8e8  mov     edi, 80070057h
0x18001e8ed  jmp     loc_18001E635
0x18001e8f2  mov     edi, [rbp+cbData]
0x18001e8f5  cmp     edi, 2
0x18001e8f8  ja      loc_18001E867
0x18001e8fe  mov     edi, 800700E8h
0x18001e903  jmp     loc_18001E635
0x18001e908  mov     r9d, edi; unsigned int
0x18001e90b  mov     r8, r15; unsigned __int16 *
0x18001e90e  mov     rdx, r14; unsigned __int16 *
0x18001e911  mov     rcx, rsi; HKEY
0x18001e914  call    ?UstRegQueryString@@YAJPEAUHKEY__@@PEBGPEAGK@Z; UstRegQueryString(HKEY__ *,ushort const *,ushort *,ulong)
0x18001e919  mov     edi, eax
0x18001e91b  test    eax, eax
0x18001e91d  js      short loc_18001E934
0x18001e91f  mov     rdx, r15
0x18001e922  lea     rcx, [rbp+pbstr]
0x18001e926  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001e92b  mov     rbx, [rbp+pbstr]
0x18001e92f  jmp     loc_18001E891
0x18001e934  mov     rcx, r15; bstrString
0x18001e937  call    cs:__imp_SysFreeString
0x18001e93d  jmp     loc_18001E62C
0x18001e942  mov     eax, 2008h
0x18001e947  cmp     bx, ax
0x18001e94a  jnz     short loc_18001E99B
0x18001e94c  mov     [rbp+pbstr], r15
0x18001e950  lea     r8, [rbp+pbstr]
0x18001e954  mov     rdx, r14; unsigned __int16 *
0x18001e957  mov     rcx, [rbp+hKey]; HKEY
0x18001e95b  call    ?UstRegQueryBSTRAlloc@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; UstRegQueryBSTRAlloc(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18001e960  mov     edi, eax
0x18001e962  mov     rbx, [rbp+pbstr]
0x18001e966  test    eax, eax
0x18001e968  js      loc_18001E62C
0x18001e96e  mov     rcx, rbx; pbstr
0x18001e971  call    cs:__imp_SysStringLen
0x18001e977  lea     edx, [rax+1]; unsigned __int16 *
0x18001e97a  mov     r8, [rbp+pvarg]; unsigned int
0x18001e97e  mov     rcx, rbx; psz
0x18001e981  call    ?CscVarUtil_ConvertMULTISZToVariant@UstVarLib@@YAJPEBGKPEAUtagVARIANT@@@Z; UstVarLib::CscVarUtil_ConvertMULTISZToVariant(ushort const *,ulong,tagVARIANT *)
0x18001e986  mov     edi, eax
0x18001e988  jmp     loc_18001E62C
0x18001e98d  mov     rcx, rbx; bstrString
0x18001e990  call    cs:__imp_SysFreeString
0x18001e996  jmp     loc_18001E635
0x18001e99b  mov     eax, 200Ch
0x18001e9a0  cmp     bx, ax
0x18001e9a3  jnz     loc_18001E8E8
0x18001e9a9  mov     r8, [rbp+pvarg]; struct ATL::CComVariant *
0x18001e9ad  mov     rcx, [rbp+hKey]; HKEY
0x18001e9b1  call    ?GetMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEAVCComVariant@ATL@@@Z; GetMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant &)
0x18001e9b6  mov     edi, eax
0x18001e9b8  jmp     loc_18001E635
0x18001e9bd  mov     [rbp+Type], r15d
0x18001e9c1  lea     r8, [rbp+Type]; unsigned int *
0x18001e9c5  mov     rdx, r14; unsigned __int16 *
0x18001e9c8  mov     rcx, [rbp+hKey]; HKEY
0x18001e9cc  call    ?UstRegQueryDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; UstRegQueryDword(HKEY__ *,ushort const *,ulong *)
0x18001e9d1  mov     edi, eax
0x18001e9d3  test    eax, eax
0x18001e9d5  js      loc_18001E635
0x18001e9db  movzx   esi, word ptr [rbp+Type]
  ... truncated ...
```
