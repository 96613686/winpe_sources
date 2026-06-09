# CCatalogServer::CreateShare(ushort const *,ushort const *)

- ea: `0x18000cd80`
- end: `0x18000d106`
- name: `?CreateShare@CCatalogServer@@UEAAJPEBG0@Z`
- size: `902`
- prototype: `int(CCatalogServer *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180009098`
- `0x18000cd80`
- `0x18000f048`
- `0x18005551a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ceea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ceea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf51`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ce96`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000ce96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ce81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ce81`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000cdf2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000cdf2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000cedc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000cf47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000cedc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000cf47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d08a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d08a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cf19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cf19`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d095`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000d095`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000ce5f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000ce5f`
- `srvcli!NetShareAdd` at `0x18000d00a`
- `srvcli!NetShareAdd` at `0x18000d00a`
- `srvcli!NetShareDel` at `0x18000cf96`
- `srvcli!NetShareDel` at `0x18000cf96`

## string_xrefs

- `0x18000ce30`: `com\complus\src\comcat\catsrv\reputil.cpp`
- `0x18000d05c`: `com\complus\src\comcat\catsrv\reputil.cpp`
- `0x18000d0b6`: `com\complus\src\comcat\catsrv\reputil.cpp`
- `0x18000ceb5`: `'CreateShare:OpenThreadToken'`
- `0x18000cf04`: `'CreateShare:GetTokenInformation(size)'`
- `0x18000cf66`: `'CreateShare:GetTokenInformation(data)'`
- `0x18000ce11`: `'CreateShare:InitializeSecurityDescriptor'`
- `0x18000d023`: `'CreateShare:NetShareAdd'`
- `0x18000cfb8`: `'CreateShare:NetShareDel'`
- `0x18000d035`: `'CreateShare'`
- `0x18000ce6f`: `'CreateShare:CoImpersonateClient'`
- `0x18000d0a1`: `'CreateShare:CoRevertToSelf'`

## pseudocode

```c
__int64 __fastcall CCatalogServer::CreateShare(CCatalogServer *this, WCHAR *a2, const unsigned __int16 *a3)
{
  void **v5; // r15
  int v6; // r12d
  signed int v7; // eax
  int v8; // ebx
  const unsigned __int16 *v9; // r9
  unsigned int v10; // r8d
  HRESULT v11; // eax
  HANDLE CurrentThread; // rax
  signed int v13; // eax
  CCatalogServer *v14; // rcx
  signed int LastError; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  HRESULT v19; // eax
  unsigned int v20; // esi
  int v22; // [rsp+30h] [rbp-89h] BYREF
  __int16 v23; // [rsp+34h] [rbp-85h]
  int v24; // [rsp+38h] [rbp-81h]
  const unsigned __int16 *v25; // [rsp+40h] [rbp-79h]
  __int64 v26; // [rsp+48h] [rbp-71h]
  __int64 v27; // [rsp+50h] [rbp-69h]
  int v28; // [rsp+58h] [rbp-61h]
  int v29; // [rsp+5Ch] [rbp-5Dh]
  BYTE buf[8]; // [rsp+60h] [rbp-59h] BYREF
  int v31; // [rsp+68h] [rbp-51h]
  __int64 v32; // [rsp+70h] [rbp-49h]
  int v33; // [rsp+78h] [rbp-41h]
  int v34; // [rsp+7Ch] [rbp-3Dh]
  int v35; // [rsp+80h] [rbp-39h]
  const unsigned __int16 *v36; // [rsp+88h] [rbp-31h]
  __int64 v37; // [rsp+90h] [rbp-29h]
  int v38; // [rsp+98h] [rbp-21h]
  struct _SECURITY_DESCRIPTOR *v39; // [rsp+A0h] [rbp-19h]
  struct _SECURITY_DESCRIPTOR pSecurityDescriptor[2]; // [rsp+B0h] [rbp-9h] BYREF
  DWORD TokenInformationLength; // [rsp+128h] [rbp+6Fh] BYREF
  void *TokenHandle; // [rsp+138h] [rbp+7Fh] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  v5 = 0;
  memset(pSecurityDescriptor, 0, 40);
  memset_0(buf, 0, 0x48u);
  v6 = 0;
  if ( !a2 || !a3 )
  {
    v23 = 22;
    v8 = -2147024809;
    v25 = L"'CreateShare'";
    v22 = -2147024809;
    v29 = 1;
    v24 = -1073737001;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    CError::WriteToLog((CError *)&v22, L"com\\complus\\src\\comcat\\catsrv\\reputil.cpp", 0x1FAu, L"'CreateShare'");
    goto LABEL_39;
  }
  if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    v11 = CoImpersonateClient();
    v8 = v11;
    if ( v11 < 0 )
    {
      v22 = v11;
      v9 = L"'CreateShare:CoImpersonateClient'";
      v10 = 524;
      goto LABEL_8;
    }
    v6 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError != 122 )
        {
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          v9 = L"'CreateShare:GetTokenInformation(size)'";
          v10 = 543;
          goto LABEL_7;
        }
        v5 = (void **)CoTaskMemAlloc(TokenInformationLength);
        if ( !v5 )
        {
          v8 = -2147024882;
          goto LABEL_39;
        }
        if ( !GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
        {
          v16 = GetLastError();
          v8 = v16;
          if ( v16 > 0 )
            v8 = (unsigned __int16)v16 | 0x80070000;
          v9 = L"'CreateShare:GetTokenInformation(data)'";
          v10 = 561;
          goto LABEL_7;
        }
      }
      v8 = CCatalogServer::AddAccessAllowedACEToSd(v14, pSecurityDescriptor, *v5);
      if ( v8 < 0 )
        goto LABEL_39;
      v17 = NetShareDel(0, a2, 0);
      if ( !v17 || v17 == 2310 )
      {
        *(_QWORD *)buf = a2;
        v39 = pSecurityDescriptor;
        v31 = 0;
        v32 = 0;
        v33 = 0;
        v34 = -1;
        v35 = 10;
        v36 = a3;
        v37 = 0;
        v38 = 0;
        v18 = NetShareAdd(0, 0x1F6u, buf, 0);
        if ( !v18 )
          goto LABEL_39;
        if ( v18 > 0 )
          v8 = (unsigned __int16)v18 | 0x80070000;
        else
          v8 = v18;
        v9 = L"'CreateShare:NetShareAdd'";
        v10 = 600;
      }
      else
      {
        if ( v17 > 0 )
          v8 = (unsigned __int16)v17 | 0x80070000;
        else
          v8 = v17;
        v9 = L"'CreateShare:NetShareDel'";
        v10 = 579;
      }
      goto LABEL_7;
    }
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    v9 = L"'CreateShare:OpenThreadToken'";
    v10 = 532;
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    v9 = L"'CreateShare:InitializeSecurityDescriptor'";
    v10 = 514;
  }
LABEL_7:
  v22 = v8;
LABEL_8:
  v24 = -1073737001;
  v23 = 22;
  v25 = v9;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 1;
  CError::WriteToLog((CError *)&v22, L"com\\complus\\src\\comcat\\catsrv\\reputil.cpp", v10, v9);
LABEL_39:
  CoTaskMemFree(v5);
  if ( v6 )
  {
    v19 = CoRevertToSelf();
    v20 = v19;
    if ( v19 < 0 )
    {
      v22 = v19;
      v25 = L"'CreateShare:CoRevertToSelf'";
      v23 = 22;
      v24 = -1073737001;
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v29 = 1;
      CError::WriteToLog(
        (CError *)&v22,
        L"com\\complus\\src\\comcat\\catsrv\\reputil.cpp",
        0x267u,
        L"'CreateShare:CoRevertToSelf'");
      if ( v8 >= 0 )
        return v20;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000cd80  mov     [rsp-8+arg_0], rbx
0x18000cd85  push    rbp
0x18000cd86  push    rsi
0x18000cd87  push    rdi
0x18000cd88  push    r12
0x18000cd8a  push    r13
0x18000cd8c  push    r14
0x18000cd8e  push    r15
0x18000cd90  lea     rbp, [rsp-27h]
0x18000cd95  sub     rsp, 0E0h
0x18000cd9c  xor     eax, eax
0x18000cd9e  lea     rcx, [rbp+57h+buf]; void *
0x18000cda2  xorps   xmm0, xmm0
0x18000cda5  mov     [rbp+57h+var_40], rax
0x18000cda9  xor     r13d, r13d
0x18000cdac  mov     rsi, r8
0x18000cdaf  mov     r14, rdx
0x18000cdb2  mov     [rbp+57h+TokenHandle], r13
0x18000cdb6  lea     r8d, [rax+48h]; Size
0x18000cdba  mov     [rbp+57h+TokenInformationLength], r13d
0x18000cdbe  xor     edx, edx; Val
0x18000cdc0  mov     r15d, r13d
0x18000cdc3  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x18000cdc7  movups  [rbp+57h+var_50], xmm0
0x18000cdcb  call    memset_0
0x18000cdd0  lea     eax, [r13+16h]
0x18000cdd4  mov     r12d, r13d
0x18000cdd7  test    r14, r14
0x18000cdda  jz      loc_18000D035
0x18000cde0  test    rsi, rsi
0x18000cde3  jz      loc_18000D035
0x18000cde9  lea     edi, [rax-15h]
0x18000cdec  mov     edx, edi; dwRevision
0x18000cdee  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000cdf2  call    cs:__imp_InitializeSecurityDescriptor
0x18000cdf8  test    eax, eax
0x18000cdfa  jnz     short loc_18000CE5F
0x18000cdfc  call    cs:__imp_GetLastError
0x18000ce02  mov     ebx, eax
0x18000ce04  test    eax, eax
0x18000ce06  jle     short loc_18000CE11
0x18000ce08  movzx   ebx, ax
0x18000ce0b  or      ebx, 80070000h
0x18000ce11  lea     r9, aCreateshareIni; "'CreateShare:InitializeSecurityDescript"...
0x18000ce18  mov     r8d, 202h; unsigned int
0x18000ce1e  mov     [rsp+110h+var_E0], ebx
0x18000ce22  mov     r14d, 16h
0x18000ce28  mov     [rsp+110h+var_D8], 0C00012D7h
0x18000ce30  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrv\\repu"...
0x18000ce37  mov     [rsp+110h+var_DC], r14w
0x18000ce3d  lea     rcx, [rsp+110h+var_E0]; this
0x18000ce42  mov     [rbp+57h+var_D0], r9
0x18000ce46  mov     [rbp+57h+var_C8], r13
0x18000ce4a  mov     [rbp+57h+var_C0], r13
0x18000ce4e  mov     [rbp+57h+var_B8], r13d
0x18000ce52  mov     [rbp+57h+var_B4], edi
0x18000ce55  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000ce5a  jmp     loc_18000D087
0x18000ce5f  call    cs:__imp_CoImpersonateClient
0x18000ce65  mov     ebx, eax
0x18000ce67  test    eax, eax
0x18000ce69  jns     short loc_18000CE7E
0x18000ce6b  mov     [rsp+110h+var_E0], eax
0x18000ce6f  lea     r9, aCreateshareCoi; "'CreateShare:CoImpersonateClient'"
0x18000ce76  mov     r8d, 20Ch
0x18000ce7c  jmp     short loc_18000CE22
0x18000ce7e  mov     r12d, edi
0x18000ce81  call    cs:__imp_GetCurrentThread
0x18000ce87  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000ce8b  mov     r8d, edi; OpenAsSelf
0x18000ce8e  mov     rcx, rax; ThreadHandle
0x18000ce91  mov     edx, 0F01FFh; DesiredAccess
0x18000ce96  call    cs:__imp_OpenThreadToken
0x18000ce9c  test    eax, eax
0x18000ce9e  jnz     short loc_18000CEC7
0x18000cea0  call    cs:__imp_GetLastError
0x18000cea6  mov     ebx, eax
0x18000cea8  test    eax, eax
0x18000ceaa  jle     short loc_18000CEB5
0x18000ceac  movzx   ebx, ax
0x18000ceaf  or      ebx, 80070000h
0x18000ceb5  lea     r9, aCreateshareOpe; "'CreateShare:OpenThreadToken'"
0x18000cebc  mov     r8d, 214h
0x18000cec2  jmp     loc_18000CE1E
0x18000cec7  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000cecb  lea     rax, [rbp+57h+TokenInformationLength]
0x18000cecf  xor     r9d, r9d; TokenInformationLength
0x18000ced2  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18000ced7  xor     r8d, r8d; TokenInformation
0x18000ceda  mov     edx, edi; TokenInformationClass
0x18000cedc  call    cs:__imp_GetTokenInformation
0x18000cee2  test    eax, eax
0x18000cee4  jnz     loc_18000CF78
0x18000ceea  call    cs:__imp_GetLastError
0x18000cef0  mov     ebx, eax
0x18000cef2  cmp     eax, 7Ah ; 'z'
0x18000cef5  jz      short loc_18000CF16
0x18000cef7  test    eax, eax
0x18000cef9  jle     short loc_18000CF04
0x18000cefb  movzx   ebx, ax
0x18000cefe  or      ebx, 80070000h
0x18000cf04  lea     r9, aCreateshareGet_0; "'CreateShare:GetTokenInformation(size)'"
0x18000cf0b  mov     r8d, 21Fh
0x18000cf11  jmp     loc_18000CE1E
0x18000cf16  mov     ecx, [rbp+57h+TokenInformationLength]; cb
0x18000cf19  call    cs:__imp_CoTaskMemAlloc
0x18000cf1f  mov     r15, rax
0x18000cf22  test    rax, rax
0x18000cf25  jnz     short loc_18000CF31
0x18000cf27  mov     ebx, 8007000Eh
0x18000cf2c  jmp     loc_18000D081
0x18000cf31  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18000cf35  lea     rax, [rbp+57h+TokenInformationLength]
0x18000cf39  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000cf3d  mov     r8, r15; TokenInformation
0x18000cf40  mov     edx, edi; TokenInformationClass
0x18000cf42  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18000cf47  call    cs:__imp_GetTokenInformation
0x18000cf4d  test    eax, eax
0x18000cf4f  jnz     short loc_18000CF78
0x18000cf51  call    cs:__imp_GetLastError
0x18000cf57  mov     ebx, eax
0x18000cf59  test    eax, eax
0x18000cf5b  jle     short loc_18000CF66
0x18000cf5d  movzx   ebx, ax
0x18000cf60  or      ebx, 80070000h
0x18000cf66  lea     r9, aCreateshareGet; "'CreateShare:GetTokenInformation(data)'"
0x18000cf6d  mov     r8d, 231h
0x18000cf73  jmp     loc_18000CE1E
0x18000cf78  mov     r8, [r15]; void *
0x18000cf7b  lea     rdx, [rbp+57h+pSecurityDescriptor]; struct _SECURITY_DESCRIPTOR *
0x18000cf7f  call    ?AddAccessAllowedACEToSd@CCatalogServer@@AEAAJPEAU_SECURITY_DESCRIPTOR@@PEAXK@Z; CCatalogServer::AddAccessAllowedACEToSd(_SECURITY_DESCRIPTOR *,void *,ulong)
0x18000cf84  mov     ebx, eax
0x18000cf86  test    eax, eax
0x18000cf88  js      loc_18000D081
0x18000cf8e  xor     r8d, r8d; reserved
0x18000cf91  mov     rdx, r14; netname
0x18000cf94  xor     ecx, ecx; servername
0x18000cf96  call    cs:__imp_NetShareDel
0x18000cf9c  test    eax, eax
0x18000cf9e  jz      short loc_18000CFCA
0x18000cfa0  cmp     eax, 906h
0x18000cfa5  jz      short loc_18000CFCA
0x18000cfa7  test    eax, eax
0x18000cfa9  jg      short loc_18000CFAF
0x18000cfab  mov     ebx, eax
0x18000cfad  jmp     short loc_18000CFB8
0x18000cfaf  movzx   ebx, ax
0x18000cfb2  or      ebx, 80070000h
0x18000cfb8  lea     r9, aCreateshareNet; "'CreateShare:NetShareDel'"
0x18000cfbf  mov     r8d, 243h
0x18000cfc5  jmp     loc_18000CE1E
0x18000cfca  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18000cfce  mov     qword ptr [rbp+57h+buf], r14
0x18000cfd2  xor     r9d, r9d; parm_err
0x18000cfd5  mov     [rbp+57h+var_70], rax
0x18000cfd9  lea     r8, [rbp+57h+buf]; buf
0x18000cfdd  mov     [rbp+57h+var_A8], r13d
0x18000cfe1  mov     edx, 1F6h; level
0x18000cfe6  mov     [rbp+57h+var_A0], r13
0x18000cfea  xor     ecx, ecx; servername
0x18000cfec  mov     [rbp+57h+var_98], r13d
0x18000cff0  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18000cff7  mov     [rbp+57h+var_90], 0Ah
0x18000cffe  mov     [rbp+57h+var_88], rsi
0x18000d002  mov     [rbp+57h+var_80], r13
0x18000d006  mov     [rbp+57h+var_78], r13d
0x18000d00a  call    cs:__imp_NetShareAdd
0x18000d010  test    eax, eax
0x18000d012  jz      short loc_18000D081
0x18000d014  jg      short loc_18000D01A
0x18000d016  mov     ebx, eax
0x18000d018  jmp     short loc_18000D023
0x18000d01a  movzx   ebx, ax
0x18000d01d  or      ebx, 80070000h
0x18000d023  lea     r9, aCreateshareNet_0; "'CreateShare:NetShareAdd'"
0x18000d02a  mov     r8d, 258h
0x18000d030  jmp     loc_18000CE1E
0x18000d035  lea     r9, aCreateshare; "'CreateShare'"
0x18000d03c  mov     [rsp+110h+var_DC], ax
0x18000d041  mov     ebx, 80070057h
0x18000d046  mov     [rbp+57h+var_D0], r9
0x18000d04a  mov     edi, 1
0x18000d04f  mov     [rsp+110h+var_E0], ebx
0x18000d053  mov     r8d, 1FAh; unsigned int
0x18000d059  mov     [rbp+57h+var_B4], edi
0x18000d05c  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrv\\repu"...
0x18000d063  mov     [rsp+110h+var_D8], 0C00012D7h
0x18000d06b  lea     rcx, [rsp+110h+var_E0]; this
0x18000d070  mov     [rbp+57h+var_C8], r13
0x18000d074  mov     [rbp+57h+var_C0], r13
0x18000d078  mov     [rbp+57h+var_B8], r13d
0x18000d07c  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000d081  mov     r14d, 16h
0x18000d087  mov     rcx, r15; pv
0x18000d08a  call    cs:__imp_CoTaskMemFree
0x18000d090  test    r12d, r12d
0x18000d093  jz      short loc_18000D0E9
0x18000d095  call    cs:__imp_CoRevertToSelf
0x18000d09b  mov     esi, eax
0x18000d09d  test    eax, eax
0x18000d09f  jns     short loc_18000D0E9
0x18000d0a1  lea     r9, aCreateshareCor; "'CreateShare:CoRevertToSelf'"
0x18000d0a8  mov     [rsp+110h+var_E0], eax
0x18000d0ac  mov     r8d, 267h; unsigned int
0x18000d0b2  mov     [rbp+57h+var_D0], r9
0x18000d0b6  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrv\\repu"...
0x18000d0bd  mov     [rsp+110h+var_DC], r14w
0x18000d0c3  lea     rcx, [rsp+110h+var_E0]; this
0x18000d0c8  mov     [rsp+110h+var_D8], 0C00012D7h
0x18000d0d0  mov     [rbp+57h+var_C8], r13
0x18000d0d4  mov     [rbp+57h+var_C0], r13
0x18000d0d8  mov     [rbp+57h+var_B8], r13d
0x18000d0dc  mov     [rbp+57h+var_B4], edi
0x18000d0df  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000d0e4  test    ebx, ebx
0x18000d0e6  cmovns  ebx, esi
0x18000d0e9  mov     eax, ebx
0x18000d0eb  mov     rbx, [rsp+110h+arg_0]
0x18000d0f3  add     rsp, 0E0h
0x18000d0fa  pop     r15
0x18000d0fc  pop     r14
0x18000d0fe  pop     r13
0x18000d100  pop     r12
0x18000d102  pop     rdi
0x18000d103  pop     rsi
0x18000d104  pop     rbp
0x18000d105  retn
```
