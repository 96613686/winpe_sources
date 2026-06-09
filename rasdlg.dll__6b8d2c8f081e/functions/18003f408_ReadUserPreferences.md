# ReadUserPreferences

- ea: `0x18003f408`
- end: `0x18003f828`
- name: `ReadUserPreferences`
- size: `1056`
- prototype: `__int64 __fastcall(HKEY hKey, void *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003eab8`
- `0x18003f18c`
- `0x18003f2a4`

## callees

- `0x18003c860`
- `0x18003cc14`
- `0x18003e9ec`
- `0x18003ed18`
- `0x18003ef14`
- `0x18003f408`
- `0x18004146c`
- `0x180041580`
- `0x1800416b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003f727`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003f7ba`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003f7d5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003f727`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003f7ba`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003f7d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f67b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f67b`
- `rtutils!TracePrintfExA` at `0x18003f440`
- `rtutils!TracePrintfExA` at `0x18003f80b`
- `rtutils!TracePrintfExA` at `0x18003f440`
- `rtutils!TracePrintfExA` at `0x18003f80b`

## string_xrefs

- `0x18003f434`: `ReadUserPreferences`
- `0x18003f537`: `SkipConnectComplete`
- `0x18003f54a`: `RedialAttempts`
- `0x18003f583`: `RedialOnLinkFailure`
- `0x18003f6f9`: `PersonalPhonebookPath`
- `0x18003f750`: `AlternatePhonebookPath`
- `0x18003f7ff`: `ReadUserPreferences=%d`

## pseudocode

```c
__int64 __fastcall ReadUserPreferences(HKEY hKey, char *a2)
{
  int v5; // r15d
  unsigned int RegMultiSz; // ebx
  WCHAR *v7; // rbx
  _QWORD *v8; // r14
  WCHAR *v9; // rcx
  const wchar_t *v10; // rax
  WCHAR *cbData; // [rsp+78h] [rbp+48h] BYREF
  DWORD Type; // [rsp+80h] [rbp+50h] BYREF

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
  GetCallbackList(hKey, (__int64 **)a2 + 9);
  RegMultiSz = GetRegMultiSz(hKey, L"Phonebooks");
  if ( RegMultiSz )
    goto LABEL_27;
  RegMultiSz = GetRegMultiSz(hKey, L"AreaCodes");
  if ( RegMultiSz )
    goto LABEL_27;
  Type = 0;
  LODWORD(cbData) = 0;
  if ( !RegQueryValueExW(hKey, L"Prefixes", 0, &Type, 0, (LPDWORD)&cbData) )
  {
    RegMultiSz = GetRegMultiSz(hKey, L"Prefixes");
    if ( RegMultiSz )
      goto LABEL_27;
  }
  RegMultiSz = GetRegMultiSz(hKey, L"Suffixes");
  if ( RegMultiSz )
    goto LABEL_27;
  GetLocationList(hKey, (__int64 **)a2 + 19);
  RegMultiSz = GetRegSz(hKey, L"LastCallbackByCaller");
  if ( RegMultiSz )
    goto LABEL_27;
  cbData = 0;
  RegMultiSz = GetRegSz(hKey, L"PersonalPhonebookPath");
  if ( RegMultiSz )
    goto LABEL_27;
  v7 = cbData;
  v8 = a2 + 96;
  if ( *cbData )
  {
    v10 = (const wchar_t *)StripPath(cbData);
    *v8 = StrDup(v10);
    GlobalFree(v7);
    if ( *v8 )
      goto LABEL_17;
    RegMultiSz = 8;
LABEL_27:
    DestroyUserPreferences(a2);
    goto LABEL_28;
  }
  GlobalFree(cbData);
  RegMultiSz = GetRegSz(hKey, L"PersonalPhonebookFile");
  if ( RegMultiSz )
    goto LABEL_27;
LABEL_17:
  RegMultiSz = GetRegSz(hKey, L"AlternatePhonebookPath");
  if ( RegMultiSz )
    goto LABEL_27;
  RegMultiSz = GetRegSz(hKey, L"DefaultEntry");
  if ( RegMultiSz )
    goto LABEL_27;
  if ( v5 )
  {
    cbData = 0;
    RegMultiSz = GetRegSz(hKey, L"UsePersonalPhonebook");
    if ( !RegMultiSz )
    {
      v9 = cbData;
      if ( cbData )
      {
        if ( *cbData == 49 )
          *((_DWORD *)a2 + 22) = 1;
        GlobalFree(v9);
      }
      goto LABEL_28;
    }
    goto LABEL_27;
  }
LABEL_28:
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "ReadUserPreferences=%d", RegMultiSz);
  return RegMultiSz;
}

```

## disassembly

```asm
0x18003f408  mov     [rsp-38h+arg_0], rbx
0x18003f40d  push    rbp
0x18003f40e  push    rsi
0x18003f40f  push    rdi
0x18003f410  push    r12
0x18003f412  push    r13
0x18003f414  push    r14
0x18003f416  push    r15
0x18003f418  mov     rbp, rsp
0x18003f41b  sub     rsp, 30h
0x18003f41f  mov     rsi, rcx
0x18003f422  or      r13d, 0FFFFFFFFh
0x18003f426  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003f42c  mov     rdi, rdx
0x18003f42f  cmp     ecx, r13d
0x18003f432  jz      short loc_18003F446
0x18003f434  lea     r8, aReaduserprefer; "ReadUserPreferences"
0x18003f43b  mov     edx, 0Ch; dwFlags
0x18003f440  call    cs:__imp_TracePrintfExA
0x18003f446  xor     r12d, r12d
0x18003f449  test    rdi, rdi
0x18003f44c  jnz     short loc_18003F456
0x18003f44e  lea     eax, [rdi+57h]
0x18003f451  jmp     loc_18003F813
0x18003f456  lea     r8, [rbp+cbData]
0x18003f45a  mov     dword ptr [rbp+cbData], r13d
0x18003f45e  lea     rdx, aPhonebookmode; "PhonebookMode"
0x18003f465  mov     rcx, rsi
0x18003f468  call    GetRegDword
0x18003f46d  mov     eax, dword ptr [rbp+cbData]
0x18003f470  mov     r14d, 1
0x18003f476  cmp     eax, r13d
0x18003f479  jz      short loc_18003F483
0x18003f47b  mov     [rdi+58h], eax
0x18003f47e  mov     r15d, r12d
0x18003f481  jmp     short loc_18003F486
0x18003f483  mov     r15d, r14d
0x18003f486  mov     r8, rdi
0x18003f489  lea     rdx, aOperatordial; "OperatorDial"
0x18003f490  mov     rcx, rsi
0x18003f493  call    GetRegDword
0x18003f498  lea     r8, [rdi+4]
0x18003f49c  mov     rcx, rsi
0x18003f49f  lea     rdx, aPreviewphonenu; "PreviewPhoneNumber"
0x18003f4a6  call    GetRegDword
0x18003f4ab  lea     r8, [rdi+8]
0x18003f4af  mov     rcx, rsi
0x18003f4b2  lea     rdx, aUselocation; "UseLocation"
0x18003f4b9  call    GetRegDword
0x18003f4be  lea     r8, [rdi+0Ch]
0x18003f4c2  mov     rcx, rsi
0x18003f4c5  lea     rdx, aShowlights; "ShowLights"
0x18003f4cc  call    GetRegDword
0x18003f4d1  lea     r8, [rdi+10h]
0x18003f4d5  mov     rcx, rsi
0x18003f4d8  lea     rdx, aShowconnectsta; "ShowConnectStatus"
0x18003f4df  call    GetRegDword
0x18003f4e4  lea     r8, [rdi+24h]
0x18003f4e8  mov     rcx, rsi
0x18003f4eb  lea     rdx, aNewentrywizard; "NewEntryWizard"
0x18003f4f2  call    GetRegDword
0x18003f4f7  lea     r8, [rdi+14h]
0x18003f4fb  mov     rcx, rsi
0x18003f4fe  lea     rdx, aCloseondial; "CloseOnDial"
0x18003f505  call    GetRegDword
0x18003f50a  lea     r8, [rdi+18h]
0x18003f50e  mov     rcx, rsi
0x18003f511  lea     rdx, aAllowlogonphon; "AllowLogonPhonebookEdits"
0x18003f518  call    GetRegDword
0x18003f51d  lea     r8, [rdi+1Ch]
0x18003f521  mov     rcx, rsi
0x18003f524  lea     rdx, aAllowlogonloca; "AllowLogonLocationEdits"
0x18003f52b  call    GetRegDword
0x18003f530  lea     r8, [rdi+20h]
0x18003f534  mov     rcx, rsi
0x18003f537  lea     rdx, aSkipconnectcom; "SkipConnectComplete"
0x18003f53e  call    GetRegDword
0x18003f543  lea     r8, [rdi+28h]
0x18003f547  mov     rcx, rsi
0x18003f54a  lea     rdx, aRedialattempts; "RedialAttempts"
0x18003f551  call    GetRegDword
0x18003f556  lea     r8, [rdi+2Ch]
0x18003f55a  mov     rcx, rsi
0x18003f55d  lea     rdx, aRedialseconds; "RedialSeconds"
0x18003f564  call    GetRegDword
0x18003f569  lea     r8, [rdi+30h]
0x18003f56d  mov     rcx, rsi
0x18003f570  lea     rdx, aIdlehangupseco; "IdleHangUpSeconds"
0x18003f577  call    GetRegDword
0x18003f57c  lea     r8, [rdi+34h]
0x18003f580  mov     rcx, rsi
0x18003f583  lea     rdx, aRedialonlinkfa; "RedialOnLinkFailure"
0x18003f58a  call    GetRegDword
0x18003f58f  lea     r8, [rdi+38h]
0x18003f593  mov     rcx, rsi
0x18003f596  lea     rdx, aPopupontopwhen; "PopupOnTopWhenRedialing"
0x18003f59d  call    GetRegDword
0x18003f5a2  lea     r8, [rdi+3Ch]
0x18003f5a6  mov     rcx, rsi
0x18003f5a9  lea     rdx, aExpandautodial; "ExpandAutoDialQuery"
0x18003f5b0  call    GetRegDword
0x18003f5b5  lea     r8, [rdi+40h]
0x18003f5b9  mov     rcx, rsi
0x18003f5bc  lea     rdx, aCallbackmode; "CallbackMode"
0x18003f5c3  call    GetRegDword
0x18003f5c8  lea     r8, [rdi+80h]
0x18003f5cf  mov     rcx, rsi
0x18003f5d2  lea     rdx, aUseareaandcoun; "UseAreaAndCountry"
0x18003f5d9  call    GetRegDword
0x18003f5de  lea     r8, [rdi+0A0h]
0x18003f5e5  mov     rcx, rsi
0x18003f5e8  lea     rdx, aWindowx; "WindowX"
0x18003f5ef  call    GetRegDword
0x18003f5f4  lea     r8, [rdi+0A4h]
0x18003f5fb  mov     rcx, rsi
0x18003f5fe  lea     rdx, aWindowy; "WindowY"
0x18003f605  call    GetRegDword
0x18003f60a  mov     [rdi+24h], r14d
0x18003f60e  lea     rdx, [rdi+48h]
0x18003f612  mov     rcx, rsi; hKey
0x18003f615  call    GetCallbackList
0x18003f61a  lea     r8, [rdi+70h]
0x18003f61e  mov     rcx, rsi; hKey
0x18003f621  lea     rdx, aPhonebooks; "Phonebooks"
0x18003f628  call    GetRegMultiSz
0x18003f62d  mov     ebx, eax
0x18003f62f  test    eax, eax
0x18003f631  jnz     loc_18003F7E9
0x18003f637  lea     r8, [rdi+78h]
0x18003f63b  mov     rcx, rsi; hKey
0x18003f63e  lea     rdx, aAreacodes; "AreaCodes"
0x18003f645  call    GetRegMultiSz
0x18003f64a  mov     ebx, eax
0x18003f64c  test    eax, eax
0x18003f64e  jnz     loc_18003F7E9
0x18003f654  lea     rax, [rbp+cbData]
0x18003f658  mov     [rbp+Type], r12d
0x18003f65c  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18003f661  lea     r9, [rbp+Type]; lpType
0x18003f665  xor     r8d, r8d; lpReserved
0x18003f668  mov     [rsp+30h+lpData], r12; lpData
0x18003f66d  lea     rdx, aPrefixes; "Prefixes"
0x18003f674  mov     dword ptr [rbp+cbData], r12d
0x18003f678  mov     rcx, rsi; hKey
0x18003f67b  call    cs:__imp_RegQueryValueExW
0x18003f681  test    eax, eax
0x18003f683  jnz     short loc_18003F6A5
0x18003f685  lea     r8, [rdi+88h]
0x18003f68c  mov     rcx, rsi; hKey
0x18003f68f  lea     rdx, aPrefixes; "Prefixes"
0x18003f696  call    GetRegMultiSz
0x18003f69b  mov     ebx, eax
0x18003f69d  test    eax, eax
0x18003f69f  jnz     loc_18003F7E9
0x18003f6a5  lea     r8, [rdi+90h]
0x18003f6ac  mov     rcx, rsi; hKey
0x18003f6af  lea     rdx, aSuffixes; "Suffixes"
0x18003f6b6  call    GetRegMultiSz
0x18003f6bb  mov     ebx, eax
0x18003f6bd  test    eax, eax
0x18003f6bf  jnz     loc_18003F7E9
0x18003f6c5  lea     rdx, [rdi+98h]
0x18003f6cc  mov     rcx, rsi; hKey
0x18003f6cf  call    GetLocationList
0x18003f6d4  lea     r8, [rdi+50h]
0x18003f6d8  mov     rcx, rsi; hKey
0x18003f6db  lea     rdx, aLastcallbackby; "LastCallbackByCaller"
0x18003f6e2  call    GetRegSz
0x18003f6e7  mov     ebx, eax
0x18003f6e9  test    eax, eax
0x18003f6eb  jnz     loc_18003F7E9
0x18003f6f1  lea     r8, [rbp+cbData]
0x18003f6f5  mov     [rbp+cbData], r12
0x18003f6f9  lea     rdx, aPersonalphoneb; "PersonalPhonebookPath"
0x18003f700  mov     rcx, rsi; hKey
0x18003f703  call    GetRegSz
0x18003f708  mov     ebx, eax
0x18003f70a  test    eax, eax
0x18003f70c  jnz     loc_18003F7E9
0x18003f712  mov     rbx, [rbp+cbData]
0x18003f716  lea     r14, [rdi+60h]
0x18003f71a  mov     rcx, rbx; lpszStart
0x18003f71d  cmp     [rbx], r12w
0x18003f721  jnz     loc_18003F7C2
0x18003f727  call    cs:__imp_GlobalFree
0x18003f72d  mov     r8, r14
0x18003f730  lea     rdx, aPersonalphoneb_0; "PersonalPhonebookFile"
0x18003f737  mov     rcx, rsi; hKey
0x18003f73a  call    GetRegSz
0x18003f73f  mov     ebx, eax
0x18003f741  test    eax, eax
0x18003f743  jnz     loc_18003F7E9
0x18003f749  lea     r8, [rdi+68h]
0x18003f74d  mov     rcx, rsi; hKey
0x18003f750  lea     rdx, aAlternatephone_0; "AlternatePhonebookPath"
0x18003f757  call    GetRegSz
0x18003f75c  mov     ebx, eax
0x18003f75e  test    eax, eax
0x18003f760  jnz     loc_18003F7E9
0x18003f766  lea     r8, [rdi+0A8h]
0x18003f76d  mov     rcx, rsi; hKey
0x18003f770  lea     rdx, aDefaultentry; "DefaultEntry"
0x18003f777  call    GetRegSz
0x18003f77c  mov     ebx, eax
0x18003f77e  test    eax, eax
0x18003f780  jnz     short loc_18003F7E9
0x18003f782  test    r15d, r15d
0x18003f785  jz      short loc_18003F7F1
0x18003f787  lea     r8, [rbp+cbData]
0x18003f78b  mov     [rbp+cbData], r12
0x18003f78f  lea     rdx, aUsepersonalpho; "UsePersonalPhonebook"
0x18003f796  mov     rcx, rsi; hKey
0x18003f799  call    GetRegSz
0x18003f79e  mov     ebx, eax
0x18003f7a0  test    eax, eax
0x18003f7a2  jnz     short loc_18003F7E9
0x18003f7a4  mov     rcx, [rbp+cbData]; hMem
0x18003f7a8  test    rcx, rcx
0x18003f7ab  jz      short loc_18003F7F1
0x18003f7ad  cmp     word ptr [rcx], 31h ; '1'
0x18003f7b1  jnz     short loc_18003F7BA
0x18003f7b3  mov     dword ptr [rdi+58h], 1
0x18003f7ba  call    cs:__imp_GlobalFree
0x18003f7c0  jmp     short loc_18003F7F1
0x18003f7c2  call    StripPath
0x18003f7c7  mov     rcx, rax; pszSrc
0x18003f7ca  call    StrDup
0x18003f7cf  mov     rcx, rbx; hMem
0x18003f7d2  mov     [r14], rax
0x18003f7d5  call    cs:__imp_GlobalFree
0x18003f7db  cmp     [r14], r12
0x18003f7de  jnz     loc_18003F749
0x18003f7e4  mov     ebx, 8
0x18003f7e9  mov     rcx, rdi; void *
0x18003f7ec  call    DestroyUserPreferences
0x18003f7f1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003f7f7  cmp     ecx, r13d
0x18003f7fa  jz      short loc_18003F811
0x18003f7fc  mov     r9d, ebx
0x18003f7ff  lea     r8, aReaduserprefer_0; "ReadUserPreferences=%d"
0x18003f806  mov     edx, 0Ch; dwFlags
0x18003f80b  call    cs:__imp_TracePrintfExA
0x18003f811  mov     eax, ebx
0x18003f813  mov     rbx, [rsp+30h+arg_0]
0x18003f818  add     rsp, 30h
0x18003f81c  pop     r15
0x18003f81e  pop     r14
0x18003f820  pop     r13
0x18003f822  pop     r12
0x18003f824  pop     rdi
0x18003f825  pop     rsi
0x18003f826  pop     rbp
0x18003f827  retn
```
