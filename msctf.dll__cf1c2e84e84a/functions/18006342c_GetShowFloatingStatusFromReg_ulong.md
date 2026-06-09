# GetShowFloatingStatusFromReg(ulong *)

- ea: `0x18006342c`
- end: `0x180063703`
- name: `?GetShowFloatingStatusFromReg@@YAJPEAK@Z`
- size: `727`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800632bc`
- `0x180063310`

## callees

- `0x18006342c`
- `0x180091e84`
- `0x1800943c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006351d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063573`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800635d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063636`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006351d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063573`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800635d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180063636`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063488`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063488`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800634a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800634d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800634a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800634d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180063462`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180063462`

## pseudocode

```c
__int64 __fastcall GetShowFloatingStatusFromReg(unsigned int *a1)
{
  HKEY v2; // rsi
  HKEY v3; // rbx
  LSTATUS v4; // ebx
  unsigned __int16 v5; // ax
  int v7; // edi
  int v8; // ebx
  int v9; // ebx
  unsigned __int16 v10; // ax
  int v11; // eax
  int v12; // ebx
  unsigned __int16 v13; // ax
  int v14; // eax
  unsigned __int16 PlatformResourceLangID; // ax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  DWORD Type; // [rsp+80h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+48h] BYREF

  if ( !a1 )
    return 2147942487LL;
  v2 = 0;
  hKey = 0;
  phkResult = 0;
  v3 = HKEY_CURRENT_USER;
  if ( !RegOpenCurrentUser(0x20019u, &phkResult) )
    v3 = phkResult;
  v4 = RegOpenKeyExW(v3, L"SOFTWARE\\Microsoft\\CTF\\LangBar\\", 0, 0x20019u, &hKey);
  if ( !v4 )
    v2 = hKey;
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( !v4 )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(v2, L"ShowStatus", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      PlatformResourceLangID = GetPlatformResourceLangID();
      v7 = (unsigned int)IsFELangId(PlatformResourceLangID) != 0 ? 1 : 2048;
    }
    else
    {
      if ( !Data )
      {
LABEL_15:
        v7 = 1;
        goto LABEL_16;
      }
      if ( Data == 1 || Data == 2 )
        goto LABEL_30;
      if ( Data != 3 )
      {
        if ( Data != 4 )
          goto LABEL_15;
LABEL_30:
        v7 = 2048;
        goto LABEL_16;
      }
      v7 = 8;
    }
LABEL_16:
    Data = 0;
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(v2, L"Transparency", 0, &Type, (LPBYTE)&Data, &cbData)
      || (v8 = 64, Data != 64) && (v8 = 32, Data != 128) )
    {
      v8 = 16;
    }
    Data = 0;
    Type = 0;
    cbData = 4;
    v9 = v7 | v8;
    if ( RegQueryValueExW(v2, L"Label", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      v10 = GetPlatformResourceLangID();
      v11 = (unsigned int)IsFELangId(v10) != 0 ? 256 : 128;
    }
    else if ( Data == 1 )
    {
      v11 = 128;
    }
    else
    {
      v11 = 256;
    }
    v12 = v11 | v9;
    Data = 0;
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(v2, L"ExtraIconsOnMinimized", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      v13 = GetPlatformResourceLangID();
      v14 = (unsigned int)IsFELangId(v13) != 0 ? 512 : 1024;
    }
    else if ( Data == 1 )
    {
      v14 = 512;
    }
    else
    {
      v14 = 1024;
    }
    *a1 = v14 | v12;
    goto LABEL_10;
  }
  v5 = GetPlatformResourceLangID();
  *a1 = (unsigned int)IsFELangId(v5) != 0 ? 785 : 3216;
LABEL_10:
  if ( v2 )
    RegCloseKey(v2);
  return 0;
}

```

## disassembly

```asm
0x18006342c  push    rbp
0x18006342e  push    rbx
0x18006342f  push    rsi
0x180063430  push    rdi
0x180063431  push    r14
0x180063433  mov     rbp, rsp
0x180063436  sub     rsp, 40h
0x18006343a  mov     r14, rcx
0x18006343d  test    rcx, rcx
0x180063440  jz      loc_18006366C
0x180063446  xor     esi, esi
0x180063448  lea     rdx, [rbp+phkResult]; phkResult
0x18006344c  mov     edi, 20019h
0x180063451  mov     [rbp+hKey], rsi
0x180063455  mov     ecx, edi; samDesired
0x180063457  mov     [rbp+phkResult], rsi
0x18006345b  mov     rbx, 0FFFFFFFF80000001h
0x180063462  call    cs:__imp_RegOpenCurrentUser
0x180063468  mov     r9d, edi; samDesired
0x18006346b  lea     rdx, ?c_szLangBarKey@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\LangBar\\"
0x180063472  test    eax, eax
0x180063474  lea     rax, [rbp+hKey]
0x180063478  mov     [rsp+40h+var_20], rax; phkResult
0x18006347d  cmovz   rbx, [rbp+phkResult]
0x180063482  xor     r8d, r8d; ulOptions
0x180063485  mov     rcx, rbx; hKey
0x180063488  call    cs:__imp_RegOpenKeyExW
0x18006348e  mov     rcx, [rbp+phkResult]; hKey
0x180063492  test    eax, eax
0x180063494  mov     ebx, eax
0x180063496  cmovz   rsi, [rbp+hKey]
0x18006349b  test    rcx, rcx
0x18006349e  jz      short loc_1800634A6
0x1800634a0  call    cs:__imp_RegCloseKey
0x1800634a6  test    ebx, ebx
0x1800634a8  jz      short loc_1800634E5
0x1800634aa  call    ?GetPlatformResourceLangID@@YAGXZ; GetPlatformResourceLangID(void)
0x1800634af  movzx   ecx, ax; unsigned __int16
0x1800634b2  call    ?IsFELangId@@YAHG@Z; IsFELangId(ushort)
0x1800634b7  neg     eax
0x1800634b9  sbb     edx, edx
0x1800634bb  and     edx, 0FFFFF681h
0x1800634c1  add     edx, 0C90h
0x1800634c7  mov     [r14], edx
0x1800634ca  test    rsi, rsi
0x1800634cd  jz      short loc_1800634D8
0x1800634cf  mov     rcx, rsi; hKey
0x1800634d2  call    cs:__imp_RegCloseKey
0x1800634d8  xor     eax, eax
0x1800634da  add     rsp, 40h
0x1800634de  pop     r14
0x1800634e0  pop     rdi
0x1800634e1  pop     rsi
0x1800634e2  pop     rbx
0x1800634e3  pop     rbp
0x1800634e4  retn
0x1800634e5  lea     rax, [rbp+cbData]
0x1800634e9  mov     [rbp+Data], 0
0x1800634f0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800634f5  lea     r9, [rbp+Type]; lpType
0x1800634f9  lea     rax, [rbp+Data]
0x1800634fd  mov     [rbp+Type], 0
0x180063504  xor     r8d, r8d; lpReserved
0x180063507  mov     [rsp+40h+var_20], rax; lpData
0x18006350c  lea     rdx, ?c_szShowStatus@@3QBGB; "ShowStatus"
0x180063513  mov     [rbp+cbData], 4
0x18006351a  mov     rcx, rsi; hKey
0x18006351d  call    cs:__imp_RegQueryValueExW
0x180063523  test    eax, eax
0x180063525  jnz     loc_1800636AC
0x18006352b  mov     eax, [rbp+Data]
0x18006352e  test    eax, eax
0x180063530  jnz     loc_180063680
0x180063536  mov     edi, 1
0x18006353b  lea     rax, [rbp+cbData]
0x18006353f  mov     [rbp+Data], 0
0x180063546  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18006354b  lea     r9, [rbp+Type]; lpType
0x18006354f  lea     rax, [rbp+Data]
0x180063553  mov     [rbp+Type], 0
0x18006355a  xor     r8d, r8d; lpReserved
0x18006355d  mov     [rsp+40h+var_20], rax; lpData
0x180063562  lea     rdx, ?c_szTransparency@@3QBGB; "Transparency"
0x180063569  mov     [rbp+cbData], 4
0x180063570  mov     rcx, rsi; hKey
0x180063573  call    cs:__imp_RegQueryValueExW
0x180063579  test    eax, eax
0x18006357b  jnz     loc_180063676
0x180063581  mov     eax, [rbp+Data]
0x180063584  mov     ebx, 40h ; '@'
0x180063589  sub     eax, ebx
0x18006358b  jz      short loc_18006359A
0x18006358d  sub     eax, ebx
0x18006358f  mov     ebx, 20h ; ' '
0x180063594  jnz     loc_180063676
0x18006359a  lea     rax, [rbp+cbData]
0x18006359e  mov     [rbp+Data], 0
0x1800635a5  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800635aa  lea     r9, [rbp+Type]; lpType
0x1800635ae  lea     rax, [rbp+Data]
0x1800635b2  mov     [rbp+Type], 0
0x1800635b9  xor     r8d, r8d; lpReserved
0x1800635bc  mov     [rsp+40h+var_20], rax; lpData
0x1800635c1  lea     rdx, ?c_szLabel@@3QBGB; "Label"
0x1800635c8  mov     [rbp+cbData], 4
0x1800635cf  mov     rcx, rsi; hKey
0x1800635d2  or      ebx, edi
0x1800635d4  call    cs:__imp_RegQueryValueExW
0x1800635da  test    eax, eax
0x1800635dc  jz      loc_1800636CF
0x1800635e2  call    ?GetPlatformResourceLangID@@YAGXZ; GetPlatformResourceLangID(void)
0x1800635e7  movzx   ecx, ax; unsigned __int16
0x1800635ea  call    ?IsFELangId@@YAHG@Z; IsFELangId(ushort)
0x1800635ef  neg     eax
0x1800635f1  mov     eax, 80h
0x1800635f6  sbb     ecx, ecx
0x1800635f8  and     ecx, eax
0x1800635fa  add     eax, ecx
0x1800635fc  or      ebx, eax
0x1800635fe  mov     [rbp+Data], 0
0x180063605  lea     rax, [rbp+cbData]
0x180063609  mov     [rbp+Type], 0
0x180063610  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180063615  lea     r9, [rbp+Type]; lpType
0x180063619  lea     rax, [rbp+Data]
0x18006361d  mov     [rbp+cbData], 4
0x180063624  xor     r8d, r8d; lpReserved
0x180063627  mov     [rsp+40h+var_20], rax; lpData
0x18006362c  lea     rdx, ?c_szExtraIconsOnMinimized@@3QBGB; "ExtraIconsOnMinimized"
0x180063633  mov     rcx, rsi; hKey
0x180063636  call    cs:__imp_RegQueryValueExW
0x18006363c  test    eax, eax
0x18006363e  jz      loc_1800636E9
0x180063644  call    ?GetPlatformResourceLangID@@YAGXZ; GetPlatformResourceLangID(void)
0x180063649  movzx   ecx, ax; unsigned __int16
0x18006364c  call    ?IsFELangId@@YAHG@Z; IsFELangId(ushort)
0x180063651  neg     eax
0x180063653  mov     eax, 400h
0x180063658  sbb     ecx, ecx
0x18006365a  and     ecx, 0FFFFFE00h
0x180063660  add     eax, ecx
0x180063662  or      ebx, eax
0x180063664  mov     [r14], ebx
0x180063667  jmp     loc_1800634CA
0x18006366c  mov     eax, 80070057h
0x180063671  jmp     loc_1800634DA
0x180063676  mov     ebx, 10h
0x18006367b  jmp     loc_18006359A
0x180063680  sub     eax, 1
0x180063683  jz      short loc_180063698
0x180063685  sub     eax, 1
0x180063688  jz      short loc_180063698
0x18006368a  sub     eax, 1
0x18006368d  jz      short loc_1800636A2
0x18006368f  cmp     eax, 1
0x180063692  jnz     loc_180063536
0x180063698  mov     edi, 800h
0x18006369d  jmp     loc_18006353B
0x1800636a2  mov     edi, 8
0x1800636a7  jmp     loc_18006353B
0x1800636ac  call    ?GetPlatformResourceLangID@@YAGXZ; GetPlatformResourceLangID(void)
0x1800636b1  movzx   ecx, ax; unsigned __int16
0x1800636b4  call    ?IsFELangId@@YAHG@Z; IsFELangId(ushort)
0x1800636b9  neg     eax
0x1800636bb  mov     edi, 800h
0x1800636c0  sbb     ecx, ecx
0x1800636c2  and     ecx, 0FFFFF801h
0x1800636c8  add     edi, ecx
0x1800636ca  jmp     loc_18006353B
0x1800636cf  cmp     [rbp+Data], 1
0x1800636d3  jz      short loc_1800636DF
0x1800636d5  mov     eax, 100h
0x1800636da  jmp     loc_1800635FC
0x1800636df  mov     eax, 80h
0x1800636e4  jmp     loc_1800635FC
0x1800636e9  cmp     [rbp+Data], 1
0x1800636ed  jz      short loc_1800636F9
0x1800636ef  mov     eax, 400h
0x1800636f4  jmp     loc_180063662
0x1800636f9  mov     eax, 200h
0x1800636fe  jmp     loc_180063662
```
