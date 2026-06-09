# ReadUserPreferences

- ea: `0x1800c3e70`
- end: `0x1800c42e4`
- name: `ReadUserPreferences`
- size: `1140`
- prototype: `__int64 __fastcall(HKEY hKey, void *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c3608`
- `0x1800c3bf4`
- `0x1800c3d0c`

## callees

- `0x180009cb4`
- `0x1800c353c`
- `0x1800c3868`
- `0x1800c3a64`
- `0x1800c3e70`
- `0x1800c4f8c`
- `0x1800c4ff0`
- `0x1800c5120`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c40e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c40e5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c418d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c4231`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c428e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c418d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c4231`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c428e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800c4239`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800c4239`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800c4279`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800c4279`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x1800c426e`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x1800c426e`
- `rtutils!TracePrintfExA` at `0x1800c3eaa`
- `rtutils!TracePrintfExA` at `0x1800c42c5`
- `rtutils!TracePrintfExA` at `0x1800c3eaa`
- `rtutils!TracePrintfExA` at `0x1800c42c5`

## string_xrefs

- `0x1800c3e9e`: `ReadUserPreferences`
- `0x1800c3fb1`: `RedialAttempts`
- `0x1800c3f9e`: `SkipConnectComplete`
- `0x1800c3fea`: `RedialOnLinkFailure`
- `0x1800c41b7`: `AlternatePhonebookPath`
- `0x1800c4163`: `PersonalPhonebookPath`
- `0x1800c42b9`: `ReadUserPreferences=%d`

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
0x1800c3e70  mov     [rsp-28h+arg_0], rbx
0x1800c3e75  mov     [rsp-28h+arg_18], rsi
0x1800c3e7a  push    rbp
0x1800c3e7b  push    rdi
0x1800c3e7c  push    r12
0x1800c3e7e  push    r14
0x1800c3e80  push    r15
0x1800c3e82  mov     rbp, rsp
0x1800c3e85  sub     rsp, 30h
0x1800c3e89  mov     rsi, rcx
0x1800c3e8c  or      r12d, 0FFFFFFFFh
0x1800c3e90  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c3e96  mov     rdi, rdx
0x1800c3e99  cmp     ecx, r12d
0x1800c3e9c  jz      short loc_1800C3EB0
0x1800c3e9e  lea     r8, aReaduserprefer; "ReadUserPreferences"
0x1800c3ea5  mov     edx, 0Ch; dwFlags
0x1800c3eaa  call    cs:__imp_TracePrintfExA
0x1800c3eb0  xor     r15d, r15d
0x1800c3eb3  test    rdi, rdi
0x1800c3eb6  jnz     short loc_1800C3EC0
0x1800c3eb8  lea     eax, [rdi+57h]
0x1800c3ebb  jmp     loc_1800C42CD
0x1800c3ec0  lea     r8, [rbp+cbData]
0x1800c3ec4  mov     dword ptr [rbp+cbData], r12d
0x1800c3ec8  lea     rdx, aPhonebookmode; "PhonebookMode"
0x1800c3ecf  mov     rcx, rsi
0x1800c3ed2  call    GetRegDword
0x1800c3ed7  mov     eax, dword ptr [rbp+cbData]
0x1800c3eda  cmp     eax, r12d
0x1800c3edd  jz      short loc_1800C3EE7
0x1800c3edf  mov     [rdi+58h], eax
0x1800c3ee2  mov     r14d, r15d
0x1800c3ee5  jmp     short loc_1800C3EED
0x1800c3ee7  mov     r14d, 1
0x1800c3eed  mov     r8, rdi
0x1800c3ef0  lea     rdx, aOperatordial; "OperatorDial"
0x1800c3ef7  mov     rcx, rsi
0x1800c3efa  call    GetRegDword
0x1800c3eff  lea     r8, [rdi+4]
0x1800c3f03  mov     rcx, rsi
0x1800c3f06  lea     rdx, aPreviewphonenu; "PreviewPhoneNumber"
0x1800c3f0d  call    GetRegDword
0x1800c3f12  lea     r8, [rdi+8]
0x1800c3f16  mov     rcx, rsi
0x1800c3f19  lea     rdx, aUselocation; "UseLocation"
0x1800c3f20  call    GetRegDword
0x1800c3f25  lea     r8, [rdi+0Ch]
0x1800c3f29  mov     rcx, rsi
0x1800c3f2c  lea     rdx, aShowlights; "ShowLights"
0x1800c3f33  call    GetRegDword
0x1800c3f38  lea     r8, [rdi+10h]
0x1800c3f3c  mov     rcx, rsi
0x1800c3f3f  lea     rdx, aShowconnectsta; "ShowConnectStatus"
0x1800c3f46  call    GetRegDword
0x1800c3f4b  lea     r8, [rdi+24h]
0x1800c3f4f  mov     rcx, rsi
0x1800c3f52  lea     rdx, aNewentrywizard; "NewEntryWizard"
0x1800c3f59  call    GetRegDword
0x1800c3f5e  lea     r8, [rdi+14h]
0x1800c3f62  mov     rcx, rsi
0x1800c3f65  lea     rdx, aCloseondial; "CloseOnDial"
0x1800c3f6c  call    GetRegDword
0x1800c3f71  lea     r8, [rdi+18h]
0x1800c3f75  mov     rcx, rsi
0x1800c3f78  lea     rdx, aAllowlogonphon; "AllowLogonPhonebookEdits"
0x1800c3f7f  call    GetRegDword
0x1800c3f84  lea     r8, [rdi+1Ch]
0x1800c3f88  mov     rcx, rsi
0x1800c3f8b  lea     rdx, aAllowlogonloca; "AllowLogonLocationEdits"
0x1800c3f92  call    GetRegDword
0x1800c3f97  lea     r8, [rdi+20h]
0x1800c3f9b  mov     rcx, rsi
0x1800c3f9e  lea     rdx, aSkipconnectcom; "SkipConnectComplete"
0x1800c3fa5  call    GetRegDword
0x1800c3faa  lea     r8, [rdi+28h]
0x1800c3fae  mov     rcx, rsi
0x1800c3fb1  lea     rdx, aRedialattempts_0; "RedialAttempts"
0x1800c3fb8  call    GetRegDword
0x1800c3fbd  lea     r8, [rdi+2Ch]
0x1800c3fc1  mov     rcx, rsi
0x1800c3fc4  lea     rdx, aRedialseconds; "RedialSeconds"
0x1800c3fcb  call    GetRegDword
0x1800c3fd0  lea     r8, [rdi+30h]
0x1800c3fd4  mov     rcx, rsi
0x1800c3fd7  lea     rdx, aIdlehangupseco; "IdleHangUpSeconds"
0x1800c3fde  call    GetRegDword
0x1800c3fe3  lea     r8, [rdi+34h]
0x1800c3fe7  mov     rcx, rsi
0x1800c3fea  lea     rdx, aRedialonlinkfa; "RedialOnLinkFailure"
0x1800c3ff1  call    GetRegDword
0x1800c3ff6  lea     r8, [rdi+38h]
0x1800c3ffa  mov     rcx, rsi
0x1800c3ffd  lea     rdx, aPopupontopwhen; "PopupOnTopWhenRedialing"
0x1800c4004  call    GetRegDword
0x1800c4009  lea     r8, [rdi+3Ch]
0x1800c400d  mov     rcx, rsi
0x1800c4010  lea     rdx, aExpandautodial; "ExpandAutoDialQuery"
0x1800c4017  call    GetRegDword
0x1800c401c  lea     r8, [rdi+40h]
0x1800c4020  mov     rcx, rsi
0x1800c4023  lea     rdx, aCallbackmode_0; "CallbackMode"
0x1800c402a  call    GetRegDword
0x1800c402f  lea     r8, [rdi+80h]
0x1800c4036  mov     rcx, rsi
0x1800c4039  lea     rdx, aUseareaandcoun; "UseAreaAndCountry"
0x1800c4040  call    GetRegDword
0x1800c4045  lea     r8, [rdi+0A0h]
0x1800c404c  mov     rcx, rsi
0x1800c404f  lea     rdx, aWindowx; "WindowX"
0x1800c4056  call    GetRegDword
0x1800c405b  lea     r8, [rdi+0A4h]
0x1800c4062  mov     rcx, rsi
0x1800c4065  lea     rdx, aWindowy; "WindowY"
0x1800c406c  call    GetRegDword
0x1800c4071  mov     dword ptr [rdi+24h], 1
0x1800c4078  lea     rdx, [rdi+48h]
0x1800c407c  mov     rcx, rsi; hKey
0x1800c407f  call    GetCallbackList
0x1800c4084  lea     r8, [rdi+70h]
0x1800c4088  mov     rcx, rsi; hKey
0x1800c408b  lea     rdx, aPhonebooks; "Phonebooks"
0x1800c4092  call    GetRegMultiSz
0x1800c4097  mov     ebx, eax
0x1800c4099  test    eax, eax
0x1800c409b  jnz     loc_1800C42A3
0x1800c40a1  lea     r8, [rdi+78h]
0x1800c40a5  mov     rcx, rsi; hKey
0x1800c40a8  lea     rdx, aAreacodes; "AreaCodes"
0x1800c40af  call    GetRegMultiSz
0x1800c40b4  mov     ebx, eax
0x1800c40b6  test    eax, eax
0x1800c40b8  jnz     loc_1800C42A3
0x1800c40be  lea     rax, [rbp+cbData]
0x1800c40c2  mov     [rbp+Type], r15d
0x1800c40c6  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800c40cb  lea     r9, [rbp+Type]; lpType
0x1800c40cf  xor     r8d, r8d; lpReserved
0x1800c40d2  mov     [rsp+30h+lpData], r15; lpData
0x1800c40d7  lea     rdx, aPrefixes; "Prefixes"
0x1800c40de  mov     dword ptr [rbp+cbData], r15d
0x1800c40e2  mov     rcx, rsi; hKey
0x1800c40e5  call    cs:__imp_RegQueryValueExW
0x1800c40eb  test    eax, eax
0x1800c40ed  jnz     short loc_1800C410F
0x1800c40ef  lea     r8, [rdi+88h]
0x1800c40f6  mov     rcx, rsi; hKey
0x1800c40f9  lea     rdx, aPrefixes; "Prefixes"
0x1800c4100  call    GetRegMultiSz
0x1800c4105  mov     ebx, eax
0x1800c4107  test    eax, eax
0x1800c4109  jnz     loc_1800C42A3
0x1800c410f  lea     r8, [rdi+90h]
0x1800c4116  mov     rcx, rsi; hKey
0x1800c4119  lea     rdx, aSuffixes; "Suffixes"
0x1800c4120  call    GetRegMultiSz
0x1800c4125  mov     ebx, eax
0x1800c4127  test    eax, eax
0x1800c4129  jnz     loc_1800C42A3
0x1800c412f  lea     rdx, [rdi+98h]
0x1800c4136  mov     rcx, rsi; hKey
0x1800c4139  call    GetLocationList
0x1800c413e  lea     r8, [rdi+50h]
0x1800c4142  mov     rcx, rsi; hKey
0x1800c4145  lea     rdx, aLastcallbackby; "LastCallbackByCaller"
0x1800c414c  call    GetRegSz
0x1800c4151  mov     ebx, eax
0x1800c4153  test    eax, eax
0x1800c4155  jnz     loc_1800C42A3
0x1800c415b  lea     r8, [rbp+cbData]
0x1800c415f  mov     [rbp+cbData], r15
0x1800c4163  lea     rdx, aPersonalphoneb; "PersonalPhonebookPath"
0x1800c416a  mov     rcx, rsi; hKey
0x1800c416d  call    GetRegSz
0x1800c4172  mov     ebx, eax
0x1800c4174  test    eax, eax
0x1800c4176  jnz     loc_1800C42A3
0x1800c417c  mov     rbx, [rbp+cbData]
0x1800c4180  mov     rcx, rbx; lpString
0x1800c4183  cmp     [rbx], r15w
0x1800c4187  jnz     loc_1800C4239
0x1800c418d  call    cs:__imp_GlobalFree
0x1800c4193  lea     r8, [rdi+60h]
0x1800c4197  mov     rcx, rsi; hKey
0x1800c419a  lea     rdx, aPersonalphoneb_0; "PersonalPhonebookFile"
0x1800c41a1  call    GetRegSz
0x1800c41a6  mov     ebx, eax
0x1800c41a8  test    eax, eax
0x1800c41aa  jnz     loc_1800C42A3
0x1800c41b0  lea     r8, [rdi+68h]
0x1800c41b4  mov     rcx, rsi; hKey
0x1800c41b7  lea     rdx, aAlternatephone; "AlternatePhonebookPath"
0x1800c41be  call    GetRegSz
0x1800c41c3  mov     ebx, eax
0x1800c41c5  test    eax, eax
0x1800c41c7  jnz     loc_1800C42A3
0x1800c41cd  lea     r8, [rdi+0A8h]
0x1800c41d4  mov     rcx, rsi; hKey
0x1800c41d7  lea     rdx, aDefaultentry; "DefaultEntry"
0x1800c41de  call    GetRegSz
0x1800c41e3  mov     ebx, eax
0x1800c41e5  test    eax, eax
0x1800c41e7  jnz     loc_1800C42A3
0x1800c41ed  test    r14d, r14d
0x1800c41f0  jz      loc_1800C42AB
0x1800c41f6  lea     r8, [rbp+cbData]
0x1800c41fa  mov     [rbp+cbData], r15
0x1800c41fe  lea     rdx, aUsepersonalpho; "UsePersonalPhonebook"
0x1800c4205  mov     rcx, rsi; hKey
0x1800c4208  call    GetRegSz
0x1800c420d  mov     ebx, eax
0x1800c420f  test    eax, eax
0x1800c4211  jnz     loc_1800C42A3
0x1800c4217  mov     rcx, [rbp+cbData]; hMem
0x1800c421b  test    rcx, rcx
0x1800c421e  jz      loc_1800C42AB
0x1800c4224  cmp     word ptr [rcx], 31h ; '1'
0x1800c4228  jnz     short loc_1800C4231
0x1800c422a  mov     dword ptr [rdi+58h], 1
0x1800c4231  call    cs:__imp_GlobalFree
0x1800c4237  jmp     short loc_1800C42AB
0x1800c4239  call    cs:__imp_lstrlenW
0x1800c423f  movsxd  rcx, eax
0x1800c4242  lea     rcx, [rbx+rcx*2]; lpsz
0x1800c4246  cmp     rcx, rbx
0x1800c4249  jbe     short loc_1800C4282
0x1800c424b  movzx   eax, word ptr [rcx]
0x1800c424e  sub     ax, 2Fh ; '/'
0x1800c4252  cmp     ax, 2Dh ; '-'
0x1800c4256  ja      short loc_1800C4268
0x1800c4258  mov     rdx, 200000000801h
0x1800c4262  bt      rdx, rax
0x1800c4266  jb      short loc_1800C4279
0x1800c4268  mov     rdx, rcx; lpszCurrent
0x1800c426b  mov     rcx, rbx; lpszStart
0x1800c426e  call    cs:__imp_CharPrevW
0x1800c4274  mov     rcx, rax
0x1800c4277  jmp     short loc_1800C4246
0x1800c4279  call    cs:__imp_CharNextW
0x1800c427f  mov     rcx, rax
0x1800c4282  call    StrDup
0x1800c4287  mov     rcx, rbx; hMem
0x1800c428a  mov     [rdi+60h], rax
0x1800c428e  call    cs:__imp_GlobalFree
0x1800c4294  cmp     [rdi+60h], r15
0x1800c4298  jnz     loc_1800C41B0
0x1800c429e  mov     ebx, 8
0x1800c42a3  mov     rcx, rdi; void *
0x1800c42a6  call    DestroyUserPreferences
0x1800c42ab  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c42b1  cmp     ecx, r12d
0x1800c42b4  jz      short loc_1800C42CB
0x1800c42b6  mov     r9d, ebx
0x1800c42b9  lea     r8, aReaduserprefer_0; "ReadUserPreferences=%d"
0x1800c42c0  mov     edx, 0Ch; dwFlags
0x1800c42c5  call    cs:__imp_TracePrintfExA
0x1800c42cb  mov     eax, ebx
0x1800c42cd  mov     rbx, [rsp+30h+arg_0]
0x1800c42d2  mov     rsi, [rsp+30h+arg_18]
0x1800c42d7  add     rsp, 30h
0x1800c42db  pop     r15
0x1800c42dd  pop     r14
0x1800c42df  pop     r12
0x1800c42e1  pop     rdi
0x1800c42e2  pop     rbp
0x1800c42e3  retn
```
