# ReadUserPreferences

- ea: `0x18005d988`
- end: `0x18005dde0`
- name: `ReadUserPreferences`
- size: `1112`
- prototype: `__int64 __fastcall(HKEY hKey, void *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d1c0`
- `0x18005d77c`
- `0x18005d87c`

## callees

- `0x18005d0c4`
- `0x18005d398`
- `0x18005d5c4`
- `0x18005d988`
- `0x18005fbf4`
- `0x180060954`
- `0x1800609c0`
- `0x180060b20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005dbd4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005dbd4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dc82`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dd2c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dda9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dc82`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dd2c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dda9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005dd3d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005dd3d`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18005dd78`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18005dd78`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18005dd8e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18005dd8e`

## string_xrefs

- `0x18005da8d`: `SkipConnectComplete`
- `0x18005daa0`: `RedialAttempts`
- `0x18005dad9`: `RedialOnLinkFailure`
- `0x18005dc58`: `PersonalPhonebookPath`
- `0x18005dcb2`: `AlternatePhonebookPath`

## pseudocode

```c
__int64 __fastcall ReadUserPreferences(HKEY hKey, char *a2)
{
  int v5; // r14d
  unsigned int RegMultiSz; // ebx
  WCHAR *v7; // rbx
  WCHAR *v8; // rcx
  const WCHAR *v9; // rcx
  unsigned __int64 v10; // rax
  __int64 v11; // rdx
  WCHAR *cbData; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF

  if ( !a2 )
    return 87;
  LODWORD(cbData) = -1;
  GetRegDword(hKey, L"PhonebookMode", &cbData);
  if ( (_DWORD)cbData == -1 )
  {
    v5 = 1;
  }
  else
  {
    *((_DWORD *)a2 + 22) = (_DWORD)cbData;
    v5 = 0;
  }
  GetRegDword(hKey, L"OperatorDial", a2);
  GetRegDword(hKey, L"PreviewPhoneNumber", a2 + 4);
  GetRegDword(hKey, L"UseLocation", a2 + 8);
  GetRegDword(hKey, L"ShowLights", a2 + 12);
  GetRegDword(hKey, L"ShowConnectStatus", a2 + 16);
  GetRegDword(hKey, L"NewEntryWizard", a2 + 36);
  GetRegDword(hKey, L"CloseOnDial", a2 + 20);
  GetRegDword(hKey, L"AllowLogonPhonebookEdits", a2 + 24);
  GetRegDword(hKey, L"AllowLogonLocationEdits", a2 + 28);
  GetRegDword(hKey, L"SkipConnectComplete", a2 + 32);
  GetRegDword(hKey, L"RedialAttempts", a2 + 40);
  GetRegDword(hKey, L"RedialSeconds", a2 + 44);
  GetRegDword(hKey, L"IdleHangUpSeconds", a2 + 48);
  GetRegDword(hKey, L"RedialOnLinkFailure", a2 + 52);
  GetRegDword(hKey, L"PopupOnTopWhenRedialing", a2 + 56);
  GetRegDword(hKey, L"ExpandAutoDialQuery", a2 + 60);
  GetRegDword(hKey, L"CallbackMode", a2 + 64);
  GetRegDword(hKey, L"UseAreaAndCountry", a2 + 128);
  GetRegDword(hKey, L"WindowX", a2 + 160);
  GetRegDword(hKey, L"WindowY", a2 + 164);
  *((_DWORD *)a2 + 9) = 1;
  GetCallbackList(hKey, (HGLOBAL *)a2 + 9);
  RegMultiSz = GetRegMultiSz(hKey, L"Phonebooks");
  if ( RegMultiSz )
    goto LABEL_31;
  RegMultiSz = GetRegMultiSz(hKey, L"AreaCodes");
  if ( RegMultiSz )
    goto LABEL_31;
  Type = 0;
  LODWORD(cbData) = 0;
  if ( !RegQueryValueExW(hKey, L"Prefixes", 0, &Type, 0, (LPDWORD)&cbData) )
  {
    RegMultiSz = GetRegMultiSz(hKey, L"Prefixes");
    if ( RegMultiSz )
      goto LABEL_31;
  }
  RegMultiSz = GetRegMultiSz(hKey, L"Suffixes");
  if ( RegMultiSz )
    goto LABEL_31;
  GetLocationList(hKey, (HGLOBAL *)a2 + 19);
  RegMultiSz = GetRegSz(hKey, L"LastCallbackByCaller");
  if ( RegMultiSz )
    goto LABEL_31;
  cbData = 0;
  RegMultiSz = GetRegSz(hKey, L"PersonalPhonebookPath");
  if ( RegMultiSz )
    goto LABEL_31;
  v7 = cbData;
  if ( !*cbData )
  {
    GlobalFree(cbData);
    RegMultiSz = GetRegSz(hKey, L"PersonalPhonebookFile");
    if ( !RegMultiSz )
      goto LABEL_15;
LABEL_31:
    DestroyUserPreferences(a2);
    return RegMultiSz;
  }
  v9 = &v7[lstrlenW(cbData)];
  if ( v9 > v7 )
  {
    while ( 1 )
    {
      v10 = *v9;
      LOWORD(v10) = v10 - 47;
      if ( (unsigned __int16)v10 <= 0x2Du )
      {
        v11 = 0x200000000801LL;
        if ( _bittest64(&v11, v10) )
          break;
      }
      v9 = CharPrevW(v7, v9);
      if ( v9 <= v7 )
        goto LABEL_29;
    }
    v9 = CharNextW(v9);
  }
LABEL_29:
  *((_QWORD *)a2 + 12) = StrDup(v9);
  GlobalFree(v7);
  if ( !*((_QWORD *)a2 + 12) )
  {
    RegMultiSz = 8;
    goto LABEL_31;
  }
LABEL_15:
  RegMultiSz = GetRegSz(hKey, L"AlternatePhonebookPath");
  if ( RegMultiSz )
    goto LABEL_31;
  RegMultiSz = GetRegSz(hKey, L"DefaultEntry");
  if ( RegMultiSz )
    goto LABEL_31;
  if ( v5 )
  {
    cbData = 0;
    RegMultiSz = GetRegSz(hKey, L"UsePersonalPhonebook");
    if ( !RegMultiSz )
    {
      v8 = cbData;
      if ( cbData )
      {
        if ( *cbData == 49 )
          *((_DWORD *)a2 + 22) = 1;
        GlobalFree(v8);
      }
      return RegMultiSz;
    }
    goto LABEL_31;
  }
  return RegMultiSz;
}

```

## disassembly

```asm
0x18005d988  mov     [rsp-28h+arg_0], rbx
0x18005d98d  push    rbp
0x18005d98e  push    rsi
0x18005d98f  push    rdi
0x18005d990  push    r14
0x18005d992  push    r15
0x18005d994  mov     rbp, rsp
0x18005d997  sub     rsp, 30h
0x18005d99b  xor     r15d, r15d
0x18005d99e  mov     rdi, rdx
0x18005d9a1  mov     rsi, rcx
0x18005d9a4  test    rdx, rdx
0x18005d9a7  jnz     short loc_18005D9B1
0x18005d9a9  lea     eax, [rdx+57h]
0x18005d9ac  jmp     loc_18005DDCE
0x18005d9b1  or      ebx, 0FFFFFFFFh
0x18005d9b4  lea     r8, [rbp+cbData]
0x18005d9b8  lea     rdx, aPhonebookmode; "PhonebookMode"
0x18005d9bf  mov     dword ptr [rbp+cbData], ebx
0x18005d9c2  call    GetRegDword
0x18005d9c7  mov     eax, dword ptr [rbp+cbData]
0x18005d9ca  cmp     eax, ebx
0x18005d9cc  jz      short loc_18005D9D6
0x18005d9ce  mov     [rdi+58h], eax
0x18005d9d1  mov     r14d, r15d
0x18005d9d4  jmp     short loc_18005D9DC
0x18005d9d6  mov     r14d, 1
0x18005d9dc  mov     r8, rdi
0x18005d9df  lea     rdx, aOperatordial; "OperatorDial"
0x18005d9e6  mov     rcx, rsi
0x18005d9e9  call    GetRegDword
0x18005d9ee  lea     r8, [rdi+4]
0x18005d9f2  mov     rcx, rsi
0x18005d9f5  lea     rdx, aPreviewphonenu; "PreviewPhoneNumber"
0x18005d9fc  call    GetRegDword
0x18005da01  lea     r8, [rdi+8]
0x18005da05  mov     rcx, rsi
0x18005da08  lea     rdx, aUselocation; "UseLocation"
0x18005da0f  call    GetRegDword
0x18005da14  lea     r8, [rdi+0Ch]
0x18005da18  mov     rcx, rsi
0x18005da1b  lea     rdx, aShowlights; "ShowLights"
0x18005da22  call    GetRegDword
0x18005da27  lea     r8, [rdi+10h]
0x18005da2b  mov     rcx, rsi
0x18005da2e  lea     rdx, aShowconnectsta; "ShowConnectStatus"
0x18005da35  call    GetRegDword
0x18005da3a  lea     r8, [rdi+24h]
0x18005da3e  mov     rcx, rsi
0x18005da41  lea     rdx, aNewentrywizard; "NewEntryWizard"
0x18005da48  call    GetRegDword
0x18005da4d  lea     r8, [rdi+14h]
0x18005da51  mov     rcx, rsi
0x18005da54  lea     rdx, aCloseondial; "CloseOnDial"
0x18005da5b  call    GetRegDword
0x18005da60  lea     r8, [rdi+18h]
0x18005da64  mov     rcx, rsi
0x18005da67  lea     rdx, aAllowlogonphon; "AllowLogonPhonebookEdits"
0x18005da6e  call    GetRegDword
0x18005da73  lea     r8, [rdi+1Ch]
0x18005da77  mov     rcx, rsi
0x18005da7a  lea     rdx, aAllowlogonloca; "AllowLogonLocationEdits"
0x18005da81  call    GetRegDword
0x18005da86  lea     r8, [rdi+20h]
0x18005da8a  mov     rcx, rsi
0x18005da8d  lea     rdx, aSkipconnectcom; "SkipConnectComplete"
0x18005da94  call    GetRegDword
0x18005da99  lea     r8, [rdi+28h]
0x18005da9d  mov     rcx, rsi
0x18005daa0  lea     rdx, aRedialattempts_0; "RedialAttempts"
0x18005daa7  call    GetRegDword
0x18005daac  lea     r8, [rdi+2Ch]
0x18005dab0  mov     rcx, rsi
0x18005dab3  lea     rdx, aRedialseconds; "RedialSeconds"
0x18005daba  call    GetRegDword
0x18005dabf  lea     r8, [rdi+30h]
0x18005dac3  mov     rcx, rsi
0x18005dac6  lea     rdx, aIdlehangupseco; "IdleHangUpSeconds"
0x18005dacd  call    GetRegDword
0x18005dad2  lea     r8, [rdi+34h]
0x18005dad6  mov     rcx, rsi
0x18005dad9  lea     rdx, aRedialonlinkfa; "RedialOnLinkFailure"
0x18005dae0  call    GetRegDword
0x18005dae5  lea     r8, [rdi+38h]
0x18005dae9  mov     rcx, rsi
0x18005daec  lea     rdx, aPopupontopwhen; "PopupOnTopWhenRedialing"
0x18005daf3  call    GetRegDword
0x18005daf8  lea     r8, [rdi+3Ch]
0x18005dafc  mov     rcx, rsi
0x18005daff  lea     rdx, aExpandautodial; "ExpandAutoDialQuery"
0x18005db06  call    GetRegDword
0x18005db0b  lea     r8, [rdi+40h]
0x18005db0f  mov     rcx, rsi
0x18005db12  lea     rdx, aCallbackmode_0; "CallbackMode"
0x18005db19  call    GetRegDword
0x18005db1e  lea     r8, [rdi+80h]
0x18005db25  mov     rcx, rsi
0x18005db28  lea     rdx, aUseareaandcoun; "UseAreaAndCountry"
0x18005db2f  call    GetRegDword
0x18005db34  lea     r8, [rdi+0A0h]
0x18005db3b  mov     rcx, rsi
0x18005db3e  lea     rdx, aWindowx; "WindowX"
0x18005db45  call    GetRegDword
0x18005db4a  lea     r8, [rdi+0A4h]
0x18005db51  mov     rcx, rsi
0x18005db54  lea     rdx, aWindowy; "WindowY"
0x18005db5b  call    GetRegDword
0x18005db60  mov     dword ptr [rdi+24h], 1
0x18005db67  lea     rdx, [rdi+48h]
0x18005db6b  mov     rcx, rsi; hKey
0x18005db6e  call    GetCallbackList
0x18005db73  lea     r8, [rdi+70h]
0x18005db77  mov     rcx, rsi; hKey
0x18005db7a  lea     rdx, aPhonebooks; "Phonebooks"
0x18005db81  call    GetRegMultiSz
0x18005db86  mov     ebx, eax
0x18005db88  test    eax, eax
0x18005db8a  jnz     loc_18005DDC4
0x18005db90  lea     r8, [rdi+78h]
0x18005db94  mov     rcx, rsi; hKey
0x18005db97  lea     rdx, aAreacodes; "AreaCodes"
0x18005db9e  call    GetRegMultiSz
0x18005dba3  mov     ebx, eax
0x18005dba5  test    eax, eax
0x18005dba7  jnz     loc_18005DDC4
0x18005dbad  lea     rax, [rbp+cbData]
0x18005dbb1  mov     [rbp+Type], r15d
0x18005dbb5  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18005dbba  lea     r9, [rbp+Type]; lpType
0x18005dbbe  xor     r8d, r8d; lpReserved
0x18005dbc1  mov     [rsp+30h+lpData], r15; lpData
0x18005dbc6  lea     rdx, aPrefixes; "Prefixes"
0x18005dbcd  mov     dword ptr [rbp+cbData], r15d
0x18005dbd1  mov     rcx, rsi; hKey
0x18005dbd4  call    cs:__imp_RegQueryValueExW
0x18005dbdb  nop     dword ptr [rax+rax+00h]
0x18005dbe0  test    eax, eax
0x18005dbe2  jnz     short loc_18005DC04
0x18005dbe4  lea     r8, [rdi+88h]
0x18005dbeb  mov     rcx, rsi; hKey
0x18005dbee  lea     rdx, aPrefixes; "Prefixes"
0x18005dbf5  call    GetRegMultiSz
0x18005dbfa  mov     ebx, eax
0x18005dbfc  test    eax, eax
0x18005dbfe  jnz     loc_18005DDC4
0x18005dc04  lea     r8, [rdi+90h]
0x18005dc0b  mov     rcx, rsi; hKey
0x18005dc0e  lea     rdx, aSuffixes; "Suffixes"
0x18005dc15  call    GetRegMultiSz
0x18005dc1a  mov     ebx, eax
0x18005dc1c  test    eax, eax
0x18005dc1e  jnz     loc_18005DDC4
0x18005dc24  lea     rdx, [rdi+98h]
0x18005dc2b  mov     rcx, rsi; hKey
0x18005dc2e  call    GetLocationList
0x18005dc33  lea     r8, [rdi+50h]
0x18005dc37  mov     rcx, rsi; hKey
0x18005dc3a  lea     rdx, aLastcallbackby; "LastCallbackByCaller"
0x18005dc41  call    GetRegSz
0x18005dc46  mov     ebx, eax
0x18005dc48  test    eax, eax
0x18005dc4a  jnz     loc_18005DDC4
0x18005dc50  lea     r8, [rbp+cbData]
0x18005dc54  mov     [rbp+cbData], r15
0x18005dc58  lea     rdx, aPersonalphoneb; "PersonalPhonebookPath"
0x18005dc5f  mov     rcx, rsi; hKey
0x18005dc62  call    GetRegSz
0x18005dc67  mov     ebx, eax
0x18005dc69  test    eax, eax
0x18005dc6b  jnz     loc_18005DDC4
0x18005dc71  mov     rbx, [rbp+cbData]
0x18005dc75  mov     rcx, rbx; lpString
0x18005dc78  cmp     [rbx], r15w
0x18005dc7c  jnz     loc_18005DD3D
0x18005dc82  call    cs:__imp_GlobalFree
0x18005dc89  nop     dword ptr [rax+rax+00h]
0x18005dc8e  lea     r8, [rdi+60h]
0x18005dc92  mov     rcx, rsi; hKey
0x18005dc95  lea     rdx, aPersonalphoneb_0; "PersonalPhonebookFile"
0x18005dc9c  call    GetRegSz
0x18005dca1  mov     ebx, eax
0x18005dca3  test    eax, eax
0x18005dca5  jnz     loc_18005DDC4
0x18005dcab  lea     r8, [rdi+68h]
0x18005dcaf  mov     rcx, rsi; hKey
0x18005dcb2  lea     rdx, aAlternatephone; "AlternatePhonebookPath"
0x18005dcb9  call    GetRegSz
0x18005dcbe  mov     ebx, eax
0x18005dcc0  test    eax, eax
0x18005dcc2  jnz     loc_18005DDC4
0x18005dcc8  lea     r8, [rdi+0A8h]
0x18005dccf  mov     rcx, rsi; hKey
0x18005dcd2  lea     rdx, aDefaultentry; "DefaultEntry"
0x18005dcd9  call    GetRegSz
0x18005dcde  mov     ebx, eax
0x18005dce0  test    eax, eax
0x18005dce2  jnz     loc_18005DDC4
0x18005dce8  test    r14d, r14d
0x18005dceb  jz      loc_18005DDCC
0x18005dcf1  lea     r8, [rbp+cbData]
0x18005dcf5  mov     [rbp+cbData], r15
0x18005dcf9  lea     rdx, aUsepersonalpho; "UsePersonalPhonebook"
0x18005dd00  mov     rcx, rsi; hKey
0x18005dd03  call    GetRegSz
0x18005dd08  mov     ebx, eax
0x18005dd0a  test    eax, eax
0x18005dd0c  jnz     loc_18005DDC4
0x18005dd12  mov     rcx, [rbp+cbData]; hMem
0x18005dd16  test    rcx, rcx
0x18005dd19  jz      loc_18005DDCC
0x18005dd1f  cmp     word ptr [rcx], 31h ; '1'
0x18005dd23  jnz     short loc_18005DD2C
0x18005dd25  mov     dword ptr [rdi+58h], 1
0x18005dd2c  call    cs:__imp_GlobalFree
0x18005dd33  nop     dword ptr [rax+rax+00h]
0x18005dd38  jmp     loc_18005DDCC
0x18005dd3d  call    cs:__imp_lstrlenW
0x18005dd44  nop     dword ptr [rax+rax+00h]
0x18005dd49  movsxd  rcx, eax
0x18005dd4c  lea     rcx, [rbx+rcx*2]; lpsz
0x18005dd50  cmp     rcx, rbx
0x18005dd53  jbe     short loc_18005DD9D
0x18005dd55  movzx   eax, word ptr [rcx]
0x18005dd58  sub     ax, 2Fh ; '/'
0x18005dd5c  cmp     ax, 2Dh ; '-'
0x18005dd60  ja      short loc_18005DD72
0x18005dd62  mov     rdx, 200000000801h
0x18005dd6c  bt      rdx, rax
0x18005dd70  jb      short loc_18005DD8E
0x18005dd72  mov     rdx, rcx; lpszCurrent
0x18005dd75  mov     rcx, rbx; lpszStart
0x18005dd78  call    cs:__imp_CharPrevW
0x18005dd7f  nop     dword ptr [rax+rax+00h]
0x18005dd84  mov     rcx, rax
0x18005dd87  cmp     rax, rbx
0x18005dd8a  ja      short loc_18005DD55
0x18005dd8c  jmp     short loc_18005DD9D
0x18005dd8e  call    cs:__imp_CharNextW
0x18005dd95  nop     dword ptr [rax+rax+00h]
0x18005dd9a  mov     rcx, rax; pszSrc
0x18005dd9d  call    StrDup
0x18005dda2  mov     rcx, rbx; hMem
0x18005dda5  mov     [rdi+60h], rax
0x18005dda9  call    cs:__imp_GlobalFree
0x18005ddb0  nop     dword ptr [rax+rax+00h]
0x18005ddb5  cmp     [rdi+60h], r15
0x18005ddb9  jnz     loc_18005DCAB
0x18005ddbf  mov     ebx, 8
0x18005ddc4  mov     rcx, rdi; void *
0x18005ddc7  call    DestroyUserPreferences
0x18005ddcc  mov     eax, ebx
0x18005ddce  mov     rbx, [rsp+30h+arg_0]
0x18005ddd3  add     rsp, 30h
0x18005ddd7  pop     r15
0x18005ddd9  pop     r14
0x18005dddb  pop     rdi
0x18005dddc  pop     rsi
0x18005dddd  pop     rbp
0x18005ddde  retn
```
