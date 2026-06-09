# ReadUserPreferences

- ea: `0x180009a30`
- end: `0x180009ea4`
- name: `ReadUserPreferences`
- size: `1140`
- prototype: `__int64 __fastcall(HKEY hKey, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009368`
- `0x180009918`

## callees

- `0x180008b94`
- `0x18000929c`
- `0x180009588`
- `0x180009784`
- `0x180009a30`
- `0x18000ac40`
- `0x18000aca4`
- `0x18000add4`

## import_xrefs

- `USER32!CharPrevW` at `0x180009e2e`
- `USER32!CharPrevW` at `0x180009e2e`
- `USER32!CharNextW` at `0x180009e39`
- `USER32!CharNextW` at `0x180009e39`
- `KERNEL32!lstrlenW` at `0x180009df9`
- `KERNEL32!lstrlenW` at `0x180009df9`
- `KERNEL32!GlobalFree` at `0x180009d4d`
- `KERNEL32!GlobalFree` at `0x180009df1`
- `KERNEL32!GlobalFree` at `0x180009e4e`
- `KERNEL32!GlobalFree` at `0x180009d4d`
- `KERNEL32!GlobalFree` at `0x180009df1`
- `KERNEL32!GlobalFree` at `0x180009e4e`
- `KERNEL32!RegQueryValueExW` at `0x180009ca5`
- `KERNEL32!RegQueryValueExW` at `0x180009ca5`
- `rtutils!TracePrintfExA` at `0x180009a6a`
- `rtutils!TracePrintfExA` at `0x180009e85`
- `rtutils!TracePrintfExA` at `0x180009a6a`
- `rtutils!TracePrintfExA` at `0x180009e85`

## string_xrefs

- `0x180009a5e`: `ReadUserPreferences`
- `0x180009b5e`: `SkipConnectComplete`
- `0x180009b71`: `RedialAttempts`
- `0x180009baa`: `RedialOnLinkFailure`
- `0x180009d23`: `PersonalPhonebookPath`
- `0x180009d77`: `AlternatePhonebookPath`
- `0x180009e79`: `ReadUserPreferences=%d`

## pseudocode

```c
__int64 __fastcall ReadUserPreferences(HKEY hKey, char *a2)
{
  int v5; // r14d
  unsigned int RegMultiSz; // ebx
  WCHAR *v7; // rbx
  WCHAR *v8; // rcx
  const WCHAR *i; // rcx
  unsigned __int64 v10; // rax
  __int64 v11; // rdx
  WCHAR *cbData; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "ReadUserPreferences");
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
    goto LABEL_33;
  RegMultiSz = GetRegMultiSz(hKey, L"AreaCodes");
  if ( RegMultiSz )
    goto LABEL_33;
  Type = 0;
  LODWORD(cbData) = 0;
  if ( !RegQueryValueExW(hKey, L"Prefixes", 0, &Type, 0, (LPDWORD)&cbData) )
  {
    RegMultiSz = GetRegMultiSz(hKey, L"Prefixes");
    if ( RegMultiSz )
      goto LABEL_33;
  }
  RegMultiSz = GetRegMultiSz(hKey, L"Suffixes");
  if ( RegMultiSz )
    goto LABEL_33;
  GetLocationList(hKey, (HGLOBAL *)a2 + 19);
  RegMultiSz = GetRegSz(hKey, L"LastCallbackByCaller");
  if ( RegMultiSz )
    goto LABEL_33;
  cbData = 0;
  RegMultiSz = GetRegSz(hKey, L"PersonalPhonebookPath");
  if ( RegMultiSz )
    goto LABEL_33;
  v7 = cbData;
  if ( !*cbData )
  {
    GlobalFree(cbData);
    RegMultiSz = GetRegSz(hKey, L"PersonalPhonebookFile");
    if ( !RegMultiSz )
      goto LABEL_17;
LABEL_33:
    DestroyUserPreferences(a2);
    goto LABEL_34;
  }
  for ( i = &v7[lstrlenW(cbData)]; i > v7; i = CharPrevW(v7, i) )
  {
    v10 = *i;
    LOWORD(v10) = v10 - 47;
    if ( (unsigned __int16)v10 <= 0x2Du )
    {
      v11 = 0x200000000801LL;
      if ( _bittest64(&v11, v10) )
      {
        i = CharNextW(i);
        break;
      }
    }
  }
  *((_QWORD *)a2 + 12) = StrDup(i);
  GlobalFree(v7);
  if ( !*((_QWORD *)a2 + 12) )
  {
    RegMultiSz = 8;
    goto LABEL_33;
  }
LABEL_17:
  RegMultiSz = GetRegSz(hKey, L"AlternatePhonebookPath");
  if ( RegMultiSz )
    goto LABEL_33;
  RegMultiSz = GetRegSz(hKey, L"DefaultEntry");
  if ( RegMultiSz )
    goto LABEL_33;
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
      goto LABEL_34;
    }
    goto LABEL_33;
  }
LABEL_34:
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "ReadUserPreferences=%d", RegMultiSz);
  return RegMultiSz;
}

```

## disassembly

```asm
0x180009a30  mov     [rsp-28h+arg_0], rbx
0x180009a35  mov     [rsp-28h+arg_18], rsi
0x180009a3a  push    rbp
0x180009a3b  push    rdi
0x180009a3c  push    r12
0x180009a3e  push    r14
0x180009a40  push    r15
0x180009a42  mov     rbp, rsp
0x180009a45  sub     rsp, 30h
0x180009a49  mov     rsi, rcx
0x180009a4c  or      r12d, 0FFFFFFFFh
0x180009a50  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180009a56  mov     rdi, rdx
0x180009a59  cmp     ecx, r12d
0x180009a5c  jz      short loc_180009A70
0x180009a5e  lea     r8, aReaduserprefer; "ReadUserPreferences"
0x180009a65  mov     edx, 0Ch; dwFlags
0x180009a6a  call    cs:__imp_TracePrintfExA
0x180009a70  xor     r15d, r15d
0x180009a73  test    rdi, rdi
0x180009a76  jnz     short loc_180009A80
0x180009a78  lea     eax, [rdi+57h]
0x180009a7b  jmp     loc_180009E8D
0x180009a80  lea     r8, [rbp+cbData]
0x180009a84  mov     dword ptr [rbp+cbData], r12d
0x180009a88  lea     rdx, aPhonebookmode; "PhonebookMode"
0x180009a8f  mov     rcx, rsi
0x180009a92  call    GetRegDword
0x180009a97  mov     eax, dword ptr [rbp+cbData]
0x180009a9a  cmp     eax, r12d
0x180009a9d  jz      short loc_180009AA7
0x180009a9f  mov     [rdi+58h], eax
0x180009aa2  mov     r14d, r15d
0x180009aa5  jmp     short loc_180009AAD
0x180009aa7  mov     r14d, 1
0x180009aad  mov     r8, rdi
0x180009ab0  lea     rdx, aOperatordial; "OperatorDial"
0x180009ab7  mov     rcx, rsi
0x180009aba  call    GetRegDword
0x180009abf  lea     r8, [rdi+4]
0x180009ac3  mov     rcx, rsi
0x180009ac6  lea     rdx, aPreviewphonenu; "PreviewPhoneNumber"
0x180009acd  call    GetRegDword
0x180009ad2  lea     r8, [rdi+8]
0x180009ad6  mov     rcx, rsi
0x180009ad9  lea     rdx, aUselocation; "UseLocation"
0x180009ae0  call    GetRegDword
0x180009ae5  lea     r8, [rdi+0Ch]
0x180009ae9  mov     rcx, rsi
0x180009aec  lea     rdx, aShowlights; "ShowLights"
0x180009af3  call    GetRegDword
0x180009af8  lea     r8, [rdi+10h]
0x180009afc  mov     rcx, rsi
0x180009aff  lea     rdx, aShowconnectsta; "ShowConnectStatus"
0x180009b06  call    GetRegDword
0x180009b0b  lea     r8, [rdi+24h]
0x180009b0f  mov     rcx, rsi
0x180009b12  lea     rdx, aNewentrywizard; "NewEntryWizard"
0x180009b19  call    GetRegDword
0x180009b1e  lea     r8, [rdi+14h]
0x180009b22  mov     rcx, rsi
0x180009b25  lea     rdx, aCloseondial; "CloseOnDial"
0x180009b2c  call    GetRegDword
0x180009b31  lea     r8, [rdi+18h]
0x180009b35  mov     rcx, rsi
0x180009b38  lea     rdx, aAllowlogonphon; "AllowLogonPhonebookEdits"
0x180009b3f  call    GetRegDword
0x180009b44  lea     r8, [rdi+1Ch]
0x180009b48  mov     rcx, rsi
0x180009b4b  lea     rdx, aAllowlogonloca; "AllowLogonLocationEdits"
0x180009b52  call    GetRegDword
0x180009b57  lea     r8, [rdi+20h]
0x180009b5b  mov     rcx, rsi
0x180009b5e  lea     rdx, aSkipconnectcom; "SkipConnectComplete"
0x180009b65  call    GetRegDword
0x180009b6a  lea     r8, [rdi+28h]
0x180009b6e  mov     rcx, rsi
0x180009b71  lea     rdx, aRedialattempts; "RedialAttempts"
0x180009b78  call    GetRegDword
0x180009b7d  lea     r8, [rdi+2Ch]
0x180009b81  mov     rcx, rsi
0x180009b84  lea     rdx, aRedialseconds; "RedialSeconds"
0x180009b8b  call    GetRegDword
0x180009b90  lea     r8, [rdi+30h]
0x180009b94  mov     rcx, rsi
0x180009b97  lea     rdx, aIdlehangupseco; "IdleHangUpSeconds"
0x180009b9e  call    GetRegDword
0x180009ba3  lea     r8, [rdi+34h]
0x180009ba7  mov     rcx, rsi
0x180009baa  lea     rdx, aRedialonlinkfa; "RedialOnLinkFailure"
0x180009bb1  call    GetRegDword
0x180009bb6  lea     r8, [rdi+38h]
0x180009bba  mov     rcx, rsi
0x180009bbd  lea     rdx, aPopupontopwhen; "PopupOnTopWhenRedialing"
0x180009bc4  call    GetRegDword
0x180009bc9  lea     r8, [rdi+3Ch]
0x180009bcd  mov     rcx, rsi
0x180009bd0  lea     rdx, aExpandautodial; "ExpandAutoDialQuery"
0x180009bd7  call    GetRegDword
0x180009bdc  lea     r8, [rdi+40h]
0x180009be0  mov     rcx, rsi
0x180009be3  lea     rdx, aCallbackmode; "CallbackMode"
0x180009bea  call    GetRegDword
0x180009bef  lea     r8, [rdi+80h]
0x180009bf6  mov     rcx, rsi
0x180009bf9  lea     rdx, aUseareaandcoun; "UseAreaAndCountry"
0x180009c00  call    GetRegDword
0x180009c05  lea     r8, [rdi+0A0h]
0x180009c0c  mov     rcx, rsi
0x180009c0f  lea     rdx, aWindowx; "WindowX"
0x180009c16  call    GetRegDword
0x180009c1b  lea     r8, [rdi+0A4h]
0x180009c22  mov     rcx, rsi
0x180009c25  lea     rdx, aWindowy; "WindowY"
0x180009c2c  call    GetRegDword
0x180009c31  mov     dword ptr [rdi+24h], 1
0x180009c38  lea     rdx, [rdi+48h]
0x180009c3c  mov     rcx, rsi; hKey
0x180009c3f  call    GetCallbackList
0x180009c44  lea     r8, [rdi+70h]
0x180009c48  mov     rcx, rsi; hKey
0x180009c4b  lea     rdx, aPhonebooks; "Phonebooks"
0x180009c52  call    GetRegMultiSz
0x180009c57  mov     ebx, eax
0x180009c59  test    eax, eax
0x180009c5b  jnz     loc_180009E63
0x180009c61  lea     r8, [rdi+78h]
0x180009c65  mov     rcx, rsi; hKey
0x180009c68  lea     rdx, aAreacodes; "AreaCodes"
0x180009c6f  call    GetRegMultiSz
0x180009c74  mov     ebx, eax
0x180009c76  test    eax, eax
0x180009c78  jnz     loc_180009E63
0x180009c7e  lea     rax, [rbp+cbData]
0x180009c82  mov     [rbp+Type], r15d
0x180009c86  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180009c8b  lea     r9, [rbp+Type]; lpType
0x180009c8f  xor     r8d, r8d; lpReserved
0x180009c92  mov     [rsp+30h+lpData], r15; lpData
0x180009c97  lea     rdx, aPrefixes; "Prefixes"
0x180009c9e  mov     dword ptr [rbp+cbData], r15d
0x180009ca2  mov     rcx, rsi; hKey
0x180009ca5  call    cs:__imp_RegQueryValueExW
0x180009cab  test    eax, eax
0x180009cad  jnz     short loc_180009CCF
0x180009caf  lea     r8, [rdi+88h]
0x180009cb6  mov     rcx, rsi; hKey
0x180009cb9  lea     rdx, aPrefixes; "Prefixes"
0x180009cc0  call    GetRegMultiSz
0x180009cc5  mov     ebx, eax
0x180009cc7  test    eax, eax
0x180009cc9  jnz     loc_180009E63
0x180009ccf  lea     r8, [rdi+90h]
0x180009cd6  mov     rcx, rsi; hKey
0x180009cd9  lea     rdx, aSuffixes; "Suffixes"
0x180009ce0  call    GetRegMultiSz
0x180009ce5  mov     ebx, eax
0x180009ce7  test    eax, eax
0x180009ce9  jnz     loc_180009E63
0x180009cef  lea     rdx, [rdi+98h]
0x180009cf6  mov     rcx, rsi; hKey
0x180009cf9  call    GetLocationList
0x180009cfe  lea     r8, [rdi+50h]
0x180009d02  mov     rcx, rsi; hKey
0x180009d05  lea     rdx, aLastcallbackby; "LastCallbackByCaller"
0x180009d0c  call    GetRegSz
0x180009d11  mov     ebx, eax
0x180009d13  test    eax, eax
0x180009d15  jnz     loc_180009E63
0x180009d1b  lea     r8, [rbp+cbData]
0x180009d1f  mov     [rbp+cbData], r15
0x180009d23  lea     rdx, aPersonalphoneb; "PersonalPhonebookPath"
0x180009d2a  mov     rcx, rsi; hKey
0x180009d2d  call    GetRegSz
0x180009d32  mov     ebx, eax
0x180009d34  test    eax, eax
0x180009d36  jnz     loc_180009E63
0x180009d3c  mov     rbx, [rbp+cbData]
0x180009d40  mov     rcx, rbx; lpString
0x180009d43  cmp     [rbx], r15w
0x180009d47  jnz     loc_180009DF9
0x180009d4d  call    cs:__imp_GlobalFree
0x180009d53  lea     r8, [rdi+60h]
0x180009d57  mov     rcx, rsi; hKey
0x180009d5a  lea     rdx, aPersonalphoneb_0; "PersonalPhonebookFile"
0x180009d61  call    GetRegSz
0x180009d66  mov     ebx, eax
0x180009d68  test    eax, eax
0x180009d6a  jnz     loc_180009E63
0x180009d70  lea     r8, [rdi+68h]
0x180009d74  mov     rcx, rsi; hKey
0x180009d77  lea     rdx, aAlternatephone; "AlternatePhonebookPath"
0x180009d7e  call    GetRegSz
0x180009d83  mov     ebx, eax
0x180009d85  test    eax, eax
0x180009d87  jnz     loc_180009E63
0x180009d8d  lea     r8, [rdi+0A8h]
0x180009d94  mov     rcx, rsi; hKey
0x180009d97  lea     rdx, aDefaultentry; "DefaultEntry"
0x180009d9e  call    GetRegSz
0x180009da3  mov     ebx, eax
0x180009da5  test    eax, eax
0x180009da7  jnz     loc_180009E63
0x180009dad  test    r14d, r14d
0x180009db0  jz      loc_180009E6B
0x180009db6  lea     r8, [rbp+cbData]
0x180009dba  mov     [rbp+cbData], r15
0x180009dbe  lea     rdx, aUsepersonalpho; "UsePersonalPhonebook"
0x180009dc5  mov     rcx, rsi; hKey
0x180009dc8  call    GetRegSz
0x180009dcd  mov     ebx, eax
0x180009dcf  test    eax, eax
0x180009dd1  jnz     loc_180009E63
0x180009dd7  mov     rcx, [rbp+cbData]; hMem
0x180009ddb  test    rcx, rcx
0x180009dde  jz      loc_180009E6B
0x180009de4  cmp     word ptr [rcx], 31h ; '1'
0x180009de8  jnz     short loc_180009DF1
0x180009dea  mov     dword ptr [rdi+58h], 1
0x180009df1  call    cs:__imp_GlobalFree
0x180009df7  jmp     short loc_180009E6B
0x180009df9  call    cs:__imp_lstrlenW
0x180009dff  movsxd  rcx, eax
0x180009e02  lea     rcx, [rbx+rcx*2]; lpsz
0x180009e06  cmp     rcx, rbx
0x180009e09  jbe     short loc_180009E42
0x180009e0b  movzx   eax, word ptr [rcx]
0x180009e0e  sub     ax, 2Fh ; '/'
0x180009e12  cmp     ax, 2Dh ; '-'
0x180009e16  ja      short loc_180009E28
0x180009e18  mov     rdx, 200000000801h
0x180009e22  bt      rdx, rax
0x180009e26  jb      short loc_180009E39
0x180009e28  mov     rdx, rcx; lpszCurrent
0x180009e2b  mov     rcx, rbx; lpszStart
0x180009e2e  call    cs:__imp_CharPrevW
0x180009e34  mov     rcx, rax
0x180009e37  jmp     short loc_180009E06
0x180009e39  call    cs:__imp_CharNextW
0x180009e3f  mov     rcx, rax; pszSrc
0x180009e42  call    StrDup
0x180009e47  mov     rcx, rbx; hMem
0x180009e4a  mov     [rdi+60h], rax
0x180009e4e  call    cs:__imp_GlobalFree
0x180009e54  cmp     [rdi+60h], r15
0x180009e58  jnz     loc_180009D70
0x180009e5e  mov     ebx, 8
0x180009e63  mov     rcx, rdi; void *
0x180009e66  call    DestroyUserPreferences
0x180009e6b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180009e71  cmp     ecx, r12d
0x180009e74  jz      short loc_180009E8B
0x180009e76  mov     r9d, ebx
0x180009e79  lea     r8, aReaduserprefer_0; "ReadUserPreferences=%d"
0x180009e80  mov     edx, 0Ch; dwFlags
0x180009e85  call    cs:__imp_TracePrintfExA
0x180009e8b  mov     eax, ebx
0x180009e8d  mov     rbx, [rsp+30h+arg_0]
0x180009e92  mov     rsi, [rsp+30h+arg_18]
0x180009e97  add     rsp, 30h
0x180009e9b  pop     r15
0x180009e9d  pop     r14
0x180009e9f  pop     r12
0x180009ea1  pop     rdi
0x180009ea2  pop     rbp
0x180009ea3  retn
```
