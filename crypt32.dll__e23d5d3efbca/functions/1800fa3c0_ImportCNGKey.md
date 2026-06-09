# ImportCNGKey

- ea: `0x1800fa3c0`
- end: `0x1800fa7b7`
- name: `ImportCNGKey`
- size: `1015`
- prototype: `__int64(__int64, __int64, __int64, BYTE *, DWORD cbData, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f94ec`

## callees

- `0x1800bbfb0`
- `0x1800f61a8`
- `0x1800fa3c0`
- `0x1800fb008`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x1800fa449`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800fa449`
- `ncrypt!NCryptOpenKey` at `0x1800fa4c4`
- `ncrypt!NCryptOpenKey` at `0x1800fa4c4`
- `ncrypt!NCryptFreeObject` at `0x1800fa4d2`
- `ncrypt!NCryptFreeObject` at `0x1800fa6f9`
- `ncrypt!NCryptFreeObject` at `0x1800fa727`
- `ncrypt!NCryptFreeObject` at `0x1800fa736`
- `ncrypt!NCryptFreeObject` at `0x1800fa4d2`
- `ncrypt!NCryptFreeObject` at `0x1800fa6f9`
- `ncrypt!NCryptFreeObject` at `0x1800fa727`
- `ncrypt!NCryptFreeObject` at `0x1800fa736`
- `ncrypt!NCryptImportKey` at `0x1800fa5ab`
- `ncrypt!NCryptImportKey` at `0x1800fa5ab`
- `ncrypt!NCryptGetProperty` at `0x1800fa5f5`
- `ncrypt!NCryptGetProperty` at `0x1800fa5f5`
- `ncrypt!NCryptSetProperty` at `0x1800fa47d`
- `ncrypt!NCryptSetProperty` at `0x1800fa629`
- `ncrypt!NCryptSetProperty` at `0x1800fa64f`
- `ncrypt!NCryptSetProperty` at `0x1800fa69f`
- `ncrypt!NCryptSetProperty` at `0x1800fa6cb`
- `ncrypt!NCryptSetProperty` at `0x1800fa47d`
- `ncrypt!NCryptSetProperty` at `0x1800fa629`
- `ncrypt!NCryptSetProperty` at `0x1800fa64f`
- `ncrypt!NCryptSetProperty` at `0x1800fa69f`
- `ncrypt!NCryptSetProperty` at `0x1800fa6cb`
- `ncrypt!NCryptFinalizeKey` at `0x1800fa6e4`
- `ncrypt!NCryptFinalizeKey` at `0x1800fa6e4`

## pseudocode

```c
__int64 ImportCNGKey(__int64 a1, __int64 a2, __int64 a3, BYTE *a4, DWORD cbData, ...)
{
  unsigned __int16 **v5; // rdi
  const WCHAR *v7; // rdx
  int v9; // r14d
  DWORD v10; // r12d
  SECURITY_STATUS Property; // ebx
  __int64 v12; // r8
  ULONG v13; // edx
  const WCHAR *v14; // r8
  DWORD v15; // r9d
  SECURITY_STATUS v16; // eax
  unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rcx
  NCRYPT_HANDLE v21; // rcx
  int v22; // eax
  DWORD dwFlags; // [rsp+28h] [rbp-79h]
  NCRYPT_KEY_HANDLE hObject; // [rsp+48h] [rbp-59h] BYREF
  SECURITY_STATUS v26; // [rsp+50h] [rbp-51h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+58h] [rbp-49h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-41h] BYREF
  NCryptBufferDesc pParameterList; // [rsp+68h] [rbp-39h] BYREF
  int v30; // [rsp+78h] [rbp-29h] BYREF
  _DWORD v31[7]; // [rsp+7Ch] [rbp-25h] BYREF
  BYTE v32[16]; // [rsp+98h] [rbp-9h] BYREF
  __int128 v33; // [rsp+A8h] [rbp+7h]
  __int64 pbInput; // [rsp+F8h] [rbp+57h] BYREF
  int v35; // [rsp+100h] [rbp+5Fh] BYREF
  PBYTE pbData; // [rsp+110h] [rbp+6Fh]
  __int64 pbOutput; // [rsp+120h] [rbp+7Fh] BYREF
  va_list pbOutputa; // [rsp+120h] [rbp+7Fh]
  va_list va1; // [rsp+128h] [rbp+87h] BYREF

  va_start(va1, cbData);
  va_start(pbOutputa, cbData);
  pbOutput = va_arg(va1, _QWORD);
  pbData = a4;
  pbInput = a1;
  v5 = (unsigned __int16 **)(a2 + 16);
  phProvider = 0;
  hObject = 0;
  v30 = 0;
  v7 = *(const WCHAR **)(a2 + 24);
  v35 = 0;
  memset(v31, 0, sizeof(v31));
  *(_OWORD *)v32 = 0;
  *(_DWORD *)v32 = 1;
  pParameterList = 0;
  v33 = 0;
  if ( !v7 )
  {
    v7 = L"Microsoft Software Key Storage Provider";
    *(_QWORD *)(a2 + 24) = L"Microsoft Software Key Storage Provider";
  }
  v9 = pbOutput;
  v10 = pbOutput & 0x40;
  Property = NCryptOpenStorageProvider(&phProvider, v7, v10);
  if ( Property < 0 )
    goto LABEL_43;
  v26 = 0;
  if ( pbInput )
    v26 = NCryptSetProperty(phProvider, L"HWND Handle", (PBYTE)&pbInput, 8u, 0);
  v13 = 0;
  if ( (v9 & 0x8000) == 0 )
  {
    if ( (v9 & 0x4000) == 0 )
    {
      v14 = *v5;
      if ( !*v5 )
        goto LABEL_13;
      v15 = *(_DWORD *)(a2 + 56);
      dwFlags = *(_DWORD *)(a2 + 36) | 0x40;
      phKey = 0;
      v16 = NCryptOpenKey(phProvider, &phKey, v14, v15, dwFlags);
      if ( v16 >= 0 )
      {
        NCryptFreeObject(phKey);
        goto LABEL_13;
      }
      if ( v16 != -2146893802 && v16 != -2146893807 )
      {
LABEL_13:
        Property = AssignRandomUuidContainerName(v5);
        if ( Property < 0 )
          goto LABEL_43;
      }
    }
    v17 = *v5;
    v31[0] = 45;
    *(_QWORD *)&v31[1] = v17;
    if ( v17 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v17[v18] );
    }
    else
    {
      LODWORD(v18) = 0;
    }
    v13 = 1;
    v30 = 2 * v18 + 2;
  }
  v19 = *(_QWORD *)(a3 + 24);
  if ( v19 )
  {
    v20 = 2LL * v13++;
    v31[2 * v20] = 46;
    *(_QWORD *)&v31[2 * v20 + 1] = *(_QWORD *)(v19 + 8);
    v31[2 * v20 - 1] = *(_DWORD *)v19;
  }
  pParameterList.pBuffers = (PBCryptBuffer)&v30;
  pParameterList.cBuffers = v13;
  pParameterList.ulVersion = 0;
  Property = NCryptImportKey(
               phProvider,
               0,
               L"PKCS8_PRIVATEKEY",
               &pParameterList,
               &hObject,
               pbData,
               cbData,
               v10 | *(_DWORD *)(a2 + 36) | (2 * (v9 & 0x10000 | 0x200)));
  if ( Property < 0 )
    goto LABEL_43;
  v21 = hObject;
  if ( (v9 & 0x8000) != 0 )
  {
    LODWORD(pbOutput) = 0xFFFFFF;
LABEL_28:
    NCryptSetProperty(v21, L"Key Usage", (PBYTE)pbOutputa, 4u, 0);
    goto LABEL_29;
  }
  LODWORD(pbOutput) = 0;
  LODWORD(phKey) = 4;
  Property = NCryptGetProperty(hObject, L"Key Usage", (PBYTE)pbOutputa, 4u, (DWORD *)&phKey, 0);
  if ( Property < 0 )
    goto LABEL_43;
  if ( (pbOutput & 1) != 0 )
  {
    v21 = hObject;
    LODWORD(pbOutput) = pbOutput | 2;
    goto LABEL_28;
  }
LABEL_29:
  v35 = v9 & 1;
  Property = NCryptSetProperty(hObject, L"Export Policy", (PBYTE)&v35, 4u, 0);
  if ( Property < 0 )
    goto LABEL_43;
  v22 = v9 & 0x100000;
  if ( (v9 & 2) != 0 )
  {
    *(_DWORD *)&v32[4] = 1;
    if ( !v22 )
      goto LABEL_35;
    goto LABEL_34;
  }
  if ( v22 )
  {
LABEL_34:
    *(_DWORD *)&v32[4] = 2;
LABEL_35:
    Property = NCryptSetProperty(hObject, L"UI Policy", v32, 0x20u, 0);
    if ( Property < 0 )
      goto LABEL_43;
  }
  if ( !pbInput || (Property = NCryptSetProperty(hObject, L"HWND Handle", (PBYTE)&pbInput, 8u, 0)) == 0 || !v26 )
  {
    Property = NCryptFinalizeKey(hObject, v10);
    if ( Property >= 0 )
    {
      if ( (v9 & 0x8000) != 0 )
      {
        *(_QWORD *)(a2 + 8) = hObject;
        hObject = 0;
      }
      else
      {
        NCryptFreeObject(hObject);
        hObject = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 84) = 1;
      }
      goto LABEL_45;
    }
  }
LABEL_43:
  if ( hObject )
    NCryptFreeObject(hObject);
LABEL_45:
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( Property )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v12, (unsigned int)Property);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_dc3d9b1f72b2343e6ef12ad6b8d70f74_Traceguids);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800fa3c0  mov     rax, rsp
0x1800fa3c3  mov     [rax+18h], rbx
0x1800fa3c7  mov     [rax+20h], r9
0x1800fa3cb  mov     [rax+8], rcx
0x1800fa3cf  push    rbp
0x1800fa3d0  push    rsi
0x1800fa3d1  push    rdi
0x1800fa3d2  push    r12
0x1800fa3d4  push    r13
0x1800fa3d6  push    r14
0x1800fa3d8  push    r15
0x1800fa3da  lea     rbp, [rax-4Fh]
0x1800fa3de  sub     rsp, 0B0h
0x1800fa3e5  xor     r15d, r15d
0x1800fa3e8  lea     rdi, [rdx+10h]
0x1800fa3ec  xorps   xmm0, xmm0
0x1800fa3ef  mov     [rbp+47h+phProvider], r15
0x1800fa3f3  xorps   xmm1, xmm1
0x1800fa3f6  mov     [rbp+47h+hObject], r15
0x1800fa3fa  mov     rsi, rdx
0x1800fa3fd  mov     [rbp+47h+var_70], r15d
0x1800fa401  mov     rdx, [rdi+8]
0x1800fa405  mov     r13, r8
0x1800fa408  mov     [rbp+47h+arg_8], r15d
0x1800fa40c  movups  xmmword ptr [rbp+47h+var_6C], xmm1
0x1800fa410  movups  xmmword ptr [rbp+47h+var_50], xmm0
0x1800fa414  mov     dword ptr [rbp+47h+var_50], 1
0x1800fa41b  movups  xmmword ptr [rbp+47h+pParameterList.ulVersion], xmm0
0x1800fa41f  movups  xmmword ptr [rbp+47h+var_6C+0Ch], xmm1
0x1800fa423  movups  [rbp+47h+var_40], xmm0
0x1800fa427  test    rdx, rdx
0x1800fa42a  jnz     short loc_1800FA437
0x1800fa42c  lea     rdx, ?DEFAULT_CNG_PROV_NAME@@3QBGB; "Microsoft Software Key Storage Provider"
0x1800fa433  mov     [rsi+18h], rdx
0x1800fa437  mov     r14d, dword ptr [rbp+47h+pbOutput]
0x1800fa43b  lea     rcx, [rbp+47h+phProvider]; phProvider
0x1800fa43f  mov     r12d, r14d
0x1800fa442  and     r12d, 40h
0x1800fa446  mov     r8d, r12d; dwFlags
0x1800fa449  call    cs:__imp_NCryptOpenStorageProvider
0x1800fa44f  mov     ebx, eax
0x1800fa451  test    eax, eax
0x1800fa453  js      loc_1800FA71E
0x1800fa459  mov     [rbp+47h+var_98], r15d
0x1800fa45d  cmp     [rbp+47h+pbInput], r15
0x1800fa461  jz      short loc_1800FA486
0x1800fa463  mov     rcx, [rbp+47h+phProvider]; hObject
0x1800fa467  lea     r8, [rbp+47h+pbInput]; pbInput
0x1800fa46b  mov     r9d, 8; cbInput
0x1800fa471  mov     [rsp+0E0h+dwFlags], r15d; dwFlags
0x1800fa476  lea     rdx, aHwndHandle; "HWND Handle"
0x1800fa47d  call    cs:__imp_NCryptSetProperty
0x1800fa483  mov     [rbp+47h+var_98], eax
0x1800fa486  mov     edx, r15d
0x1800fa489  mov     r15d, r14d
0x1800fa48c  and     r15d, 8000h
0x1800fa493  jnz     loc_1800FA52F
0x1800fa499  xor     ebx, ebx
0x1800fa49b  bt      r14d, 0Eh
0x1800fa4a0  jb      short loc_1800FA4FC
0x1800fa4a2  mov     r8, [rdi]; pszKeyName
0x1800fa4a5  test    r8, r8
0x1800fa4a8  jz      short loc_1800FA4E8
0x1800fa4aa  mov     eax, [rsi+24h]
0x1800fa4ad  lea     rdx, [rbp+47h+phKey]; phKey
0x1800fa4b1  mov     r9d, [rsi+38h]; dwLegacyKeySpec
0x1800fa4b5  or      eax, 40h
0x1800fa4b8  mov     rcx, [rbp+47h+phProvider]; hProvider
0x1800fa4bc  mov     [rsp+0E0h+dwFlags], eax; dwFlags
0x1800fa4c0  mov     [rbp+47h+phKey], rbx
0x1800fa4c4  call    cs:__imp_NCryptOpenKey
0x1800fa4ca  test    eax, eax
0x1800fa4cc  js      short loc_1800FA4DA
0x1800fa4ce  mov     rcx, [rbp+47h+phKey]; hObject
0x1800fa4d2  call    cs:__imp_NCryptFreeObject
0x1800fa4d8  jmp     short loc_1800FA4E8
0x1800fa4da  cmp     eax, 80090016h
0x1800fa4df  jz      short loc_1800FA4FC
0x1800fa4e1  cmp     eax, 80090011h
0x1800fa4e6  jz      short loc_1800FA4FC
0x1800fa4e8  mov     rcx, rdi; unsigned __int16 **
0x1800fa4eb  call    ?AssignRandomUuidContainerName@@YAJPEAPEAG@Z; AssignRandomUuidContainerName(ushort * *)
0x1800fa4f0  mov     ebx, eax
0x1800fa4f2  test    eax, eax
0x1800fa4f4  js      loc_1800FA71E
0x1800fa4fa  xor     ebx, ebx
0x1800fa4fc  mov     rcx, [rdi]
0x1800fa4ff  mov     dword ptr [rbp+47h+var_6C], 2Dh ; '-'
0x1800fa506  mov     qword ptr [rbp+47h+var_6C+4], rcx
0x1800fa50a  test    rcx, rcx
0x1800fa50d  jz      short loc_1800FA51E
0x1800fa50f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800fa513  inc     rax
0x1800fa516  cmp     [rcx+rax*2], bx
0x1800fa51a  jnz     short loc_1800FA513
0x1800fa51c  jmp     short loc_1800FA520
0x1800fa51e  mov     eax, ebx
0x1800fa520  lea     eax, ds:2[rax*2]
0x1800fa527  mov     edx, 1
0x1800fa52c  mov     [rbp+47h+var_70], eax
0x1800fa52f  mov     r8, [r13+18h]
0x1800fa533  xor     r13d, r13d
0x1800fa536  test    r8, r8
0x1800fa539  jz      short loc_1800FA55A
0x1800fa53b  mov     ecx, edx
0x1800fa53d  add     rcx, rcx
0x1800fa540  inc     edx
0x1800fa542  mov     dword ptr [rbp+rcx*8+47h+var_6C], 2Eh ; '.'
0x1800fa54a  mov     rax, [r8+8]
0x1800fa54e  mov     qword ptr [rbp+rcx*8+47h+var_6C+4], rax
0x1800fa553  mov     eax, [r8]
0x1800fa556  mov     [rbp+rcx*8+47h+var_70], eax
0x1800fa55a  mov     rcx, [rbp+47h+phProvider]; hProvider
0x1800fa55e  lea     rax, [rbp+47h+var_70]
0x1800fa562  mov     [rbp+47h+pParameterList.pBuffers], rax
0x1800fa566  lea     r9, [rbp+47h+pParameterList]; pParameterList
0x1800fa56a  mov     eax, r14d
0x1800fa56d  mov     [rbp+47h+pParameterList.cBuffers], edx
0x1800fa570  and     eax, 10000h
0x1800fa575  mov     [rbp+47h+pParameterList.ulVersion], r13d
0x1800fa579  bts     eax, 9
0x1800fa57d  lea     r8, pszBlobType; "PKCS8_PRIVATEKEY"
0x1800fa584  add     eax, eax
0x1800fa586  xor     edx, edx; hImportKey
0x1800fa588  or      eax, [rsi+24h]
0x1800fa58b  or      eax, r12d
0x1800fa58e  mov     [rsp+38h], eax; dwFlags
0x1800fa592  mov     eax, [rbp+47h+arg_20]
0x1800fa595  mov     [rsp+0E0h+cbData], eax; cbData
0x1800fa599  mov     rax, [rbp+47h+arg_18]
0x1800fa59d  mov     [rsp+0E0h+pbData], rax; pbData
0x1800fa5a2  lea     rax, [rbp+47h+hObject]
0x1800fa5a6  mov     qword ptr [rsp+0E0h+dwFlags], rax; phKey
0x1800fa5ab  call    cs:__imp_NCryptImportKey
0x1800fa5b1  mov     ebx, eax
0x1800fa5b3  test    eax, eax
0x1800fa5b5  js      loc_1800FA71E
0x1800fa5bb  mov     rcx, [rbp+47h+hObject]; hObject
0x1800fa5bf  mov     edi, 4
0x1800fa5c4  lea     r8, [rbp+47h+pbOutput]; pbOutput
0x1800fa5c8  mov     r9d, edi; cbOutput
0x1800fa5cb  lea     rdx, aKeyUsage; "Key Usage"
0x1800fa5d2  test    r15d, r15d
0x1800fa5d5  jz      short loc_1800FA5E0
0x1800fa5d7  mov     dword ptr [rbp+47h+pbOutput], 0FFFFFFh
0x1800fa5de  jmp     short loc_1800FA624
0x1800fa5e0  lea     rax, [rbp+47h+phKey]
0x1800fa5e4  mov     dword ptr [rsp+0E0h+pbData], r13d; dwFlags
0x1800fa5e9  mov     qword ptr [rsp+0E0h+dwFlags], rax; pcbResult
0x1800fa5ee  mov     dword ptr [rbp+47h+pbOutput], r13d
0x1800fa5f2  mov     dword ptr [rbp+47h+phKey], edi
0x1800fa5f5  call    cs:__imp_NCryptGetProperty
0x1800fa5fb  mov     ebx, eax
0x1800fa5fd  test    eax, eax
0x1800fa5ff  js      loc_1800FA71E
0x1800fa605  mov     eax, dword ptr [rbp+47h+pbOutput]
0x1800fa608  test    al, 1
0x1800fa60a  jz      short loc_1800FA62F
0x1800fa60c  mov     rcx, [rbp+47h+hObject]; hObject
0x1800fa610  lea     r8, [rbp+47h+pbOutput]; pbInput
0x1800fa614  or      eax, 2
0x1800fa617  lea     rdx, aKeyUsage; "Key Usage"
0x1800fa61e  mov     dword ptr [rbp+47h+pbOutput], eax
0x1800fa621  mov     r9d, edi; cbInput
0x1800fa624  mov     [rsp+0E0h+dwFlags], r13d; dwFlags
0x1800fa629  call    cs:__imp_NCryptSetProperty
0x1800fa62f  mov     rcx, [rbp+47h+hObject]; hObject
0x1800fa633  lea     r8, [rbp+47h+arg_8]; pbInput
0x1800fa637  mov     eax, r14d
0x1800fa63a  mov     [rsp+0E0h+dwFlags], r13d; dwFlags
0x1800fa63f  and     eax, 1
0x1800fa642  lea     rdx, aExportPolicy; "Export Policy"
0x1800fa649  mov     r9d, edi; cbInput
0x1800fa64c  mov     [rbp+47h+arg_8], eax
0x1800fa64f  call    cs:__imp_NCryptSetProperty
0x1800fa655  mov     ebx, eax
0x1800fa657  test    eax, eax
0x1800fa659  js      loc_1800FA71E
0x1800fa65f  mov     eax, r14d
0x1800fa662  and     eax, 100000h
0x1800fa667  test    r14b, 2
0x1800fa66b  jnz     short loc_1800FA673
0x1800fa66d  test    eax, eax
0x1800fa66f  jz      short loc_1800FA6AB
0x1800fa671  jmp     short loc_1800FA67E
0x1800fa673  mov     dword ptr [rbp+47h+var_50+4], 1
0x1800fa67a  test    eax, eax
0x1800fa67c  jz      short loc_1800FA685
0x1800fa67e  mov     dword ptr [rbp+47h+var_50+4], 2
0x1800fa685  mov     rcx, [rbp+47h+hObject]; hObject
0x1800fa689  lea     r8, [rbp+47h+var_50]; pbInput
0x1800fa68d  mov     r9d, 20h ; ' '; cbInput
0x1800fa693  mov     [rsp+0E0h+dwFlags], r13d; dwFlags
0x1800fa698  lea     rdx, aUiPolicy; "UI Policy"
0x1800fa69f  call    cs:__imp_NCryptSetProperty
0x1800fa6a5  mov     ebx, eax
0x1800fa6a7  test    eax, eax
0x1800fa6a9  js      short loc_1800FA71E
0x1800fa6ab  cmp     [rbp+47h+pbInput], r13
0x1800fa6af  jz      short loc_1800FA6DD
0x1800fa6b1  mov     rcx, [rbp+47h+hObject]; hObject
0x1800fa6b5  lea     r8, [rbp+47h+pbInput]; pbInput
0x1800fa6b9  mov     r9d, 8; cbInput
0x1800fa6bf  mov     [rsp+0E0h+dwFlags], r13d; dwFlags
0x1800fa6c4  lea     rdx, aHwndHandle; "HWND Handle"
0x1800fa6cb  call    cs:__imp_NCryptSetProperty
0x1800fa6d1  mov     ebx, eax
0x1800fa6d3  test    eax, eax
0x1800fa6d5  jz      short loc_1800FA6DD
0x1800fa6d7  cmp     [rbp+47h+var_98], r13d
0x1800fa6db  jnz     short loc_1800FA71E
0x1800fa6dd  mov     rcx, [rbp+47h+hObject]; hKey
0x1800fa6e1  mov     edx, r12d; dwFlags
0x1800fa6e4  call    cs:__imp_NCryptFinalizeKey
0x1800fa6ea  mov     ebx, eax
0x1800fa6ec  test    eax, eax
0x1800fa6ee  js      short loc_1800FA71E
0x1800fa6f0  test    r15d, r15d
0x1800fa6f3  jnz     short loc_1800FA710
0x1800fa6f5  mov     rcx, [rbp+47h+hObject]; hObject
0x1800fa6f9  call    cs:__imp_NCryptFreeObject
0x1800fa6ff  mov     [rbp+47h+hObject], r13
0x1800fa703  mov     [rsi+8], r13
0x1800fa707  mov     dword ptr [rsi+54h], 1
0x1800fa70e  jmp     short loc_1800FA72D
0x1800fa710  mov     rax, [rbp+47h+hObject]
0x1800fa714  mov     [rsi+8], rax
0x1800fa718  mov     [rbp+47h+hObject], r13
0x1800fa71c  jmp     short loc_1800FA72D
0x1800fa71e  mov     rcx, [rbp+47h+hObject]; hObject
0x1800fa722  test    rcx, rcx
0x1800fa725  jz      short loc_1800FA72D
0x1800fa727  call    cs:__imp_NCryptFreeObject
0x1800fa72d  mov     rcx, [rbp+47h+phProvider]; hObject
0x1800fa731  test    rcx, rcx
0x1800fa734  jz      short loc_1800FA73C
0x1800fa736  call    cs:__imp_NCryptFreeObject
0x1800fa73c  test    ebx, ebx
0x1800fa73e  jz      short loc_1800FA76C
0x1800fa740  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa747  lea     rax, WPP_GLOBAL_Control
0x1800fa74e  cmp     rcx, rax
0x1800fa751  jz      short loc_1800FA79A
0x1800fa753  test    byte ptr [rcx+1Ch], 1
0x1800fa757  jz      short loc_1800FA79A
0x1800fa759  mov     rcx, [rcx+10h]
0x1800fa75d  mov     edx, 0Fh
0x1800fa762  mov     r9d, ebx
0x1800fa765  call    WPP_SF_d
0x1800fa76a  jmp     short loc_1800FA79A
0x1800fa76c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa773  lea     rax, WPP_GLOBAL_Control
0x1800fa77a  cmp     rcx, rax
0x1800fa77d  jz      short loc_1800FA79A
0x1800fa77f  test    byte ptr [rcx+1Ch], 2
0x1800fa783  jz      short loc_1800FA79A
0x1800fa785  mov     rcx, [rcx+10h]
0x1800fa789  lea     r8, WPP_dc3d9b1f72b2343e6ef12ad6b8d70f74_Traceguids
0x1800fa790  mov     edx, 10h
0x1800fa795  call    WPP_SF_
0x1800fa79a  mov     eax, ebx
0x1800fa79c  mov     rbx, [rsp+0E0h+arg_10]
0x1800fa7a4  add     rsp, 0B0h
0x1800fa7ab  pop     r15
0x1800fa7ad  pop     r14
0x1800fa7af  pop     r13
0x1800fa7b1  pop     r12
0x1800fa7b3  pop     rdi
0x1800fa7b4  pop     rsi
0x1800fa7b5  pop     rbp
0x1800fa7b6  retn
```
