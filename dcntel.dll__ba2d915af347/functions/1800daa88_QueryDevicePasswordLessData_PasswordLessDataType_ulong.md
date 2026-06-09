# QueryDevicePasswordLessData(PasswordLessDataType,ulong *)

- ea: `0x1800daa88`
- end: `0x1800dac46`
- name: `?QueryDevicePasswordLessData@@YAJW4PasswordLessDataType@@PEAK@Z`
- size: `446`
- prototype: `int __high(enum PasswordLessDataType, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800da5fc`
- `0x1800da9f4`

## callees

- `0x180011ce4`
- `0x1800daa88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dab1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dab1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dab07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dab07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daaea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dab12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dab92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dabf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dac1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dac32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daaea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dab12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dab92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dabf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dac1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dac32`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dabc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dabc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dab49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dab49`

## string_xrefs

- `0x1800daaae`: `DevicePasswordLessUpdateType`
- `0x1800daacf`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800dab77`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800dac02`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall QueryDevicePasswordLessData(int a1, BYTE *a2)
{
  const WCHAR *v3; // rdi
  unsigned int v4; // ebx
  HKEY v6; // r14
  DWORD LastError; // ebx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  int phkResult; // [rsp+20h] [rbp-10h]
  int phkResulta; // [rsp+20h] [rbp-10h]
  int phkResultb; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  hKey = 0;
  if ( a1 )
  {
    v3 = L"DevicePasswordLessUpdateType";
    if ( a1 != 1 )
      v3 = 0;
  }
  else
  {
    v3 = L"DevicePasswordLessBuildVersion";
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)0x80004003LL,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  *(_DWORD *)a2 = 0;
  v6 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v6);
    SetLastError(LastError);
  }
  hKey = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\Device",
         0,
         0x20019u,
         &hKey);
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( v4 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v4,
        phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      return v4;
    }
    goto LABEL_22;
  }
  Type = 0;
  cbData = 4;
  v9 = RegQueryValueExW(hKey, v3, 0, &Type, a2, &cbData);
  v4 = v9;
  if ( v9 > 0 )
    v4 = (unsigned __int16)v9 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( v4 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A0,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v4,
        phkResultb);
      if ( hKey )
        RegCloseKey(hKey);
      return v4;
    }
LABEL_22:
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800daa88  push    rbp
0x1800daa8a  push    rbx
0x1800daa8b  push    rsi
0x1800daa8c  push    rdi
0x1800daa8d  push    r14
0x1800daa8f  mov     rbp, rsp
0x1800daa92  sub     rsp, 30h
0x1800daa96  mov     rsi, rdx
0x1800daa99  mov     [rbp+hKey], 0
0x1800daaa1  test    ecx, ecx
0x1800daaa3  jnz     short loc_1800DAAAE
0x1800daaa5  lea     rdi, aDevicepassword_0; "DevicePasswordLessBuildVersion"
0x1800daaac  jmp     short loc_1800DAABE
0x1800daaae  lea     rdi, aDevicepassword; "DevicePasswordLessUpdateType"
0x1800daab5  xor     eax, eax
0x1800daab7  cmp     ecx, 1
0x1800daaba  cmovnz  rdi, rax
0x1800daabe  test    rsi, rsi
0x1800daac1  jnz     short loc_1800DAAF8
0x1800daac3  mov     rcx, [rbp+28h]; this
0x1800daac7  mov     ebx, 80004003h
0x1800daacc  mov     r9d, ebx; char *
0x1800daacf  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800daad6  mov     edx, 189h; void *
0x1800daadb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800daae0  nop
0x1800daae1  mov     rcx, [rbp+hKey]; hKey
0x1800daae5  test    rcx, rcx
0x1800daae8  jz      short loc_1800DAAF1
0x1800daaea  call    cs:__imp_RegCloseKey
0x1800daaf0  nop
0x1800daaf1  mov     eax, ebx
0x1800daaf3  jmp     loc_1800DAC3B
0x1800daaf8  mov     dword ptr [rdx], 0
0x1800daafe  mov     r14, [rbp+hKey]
0x1800dab02  test    r14, r14
0x1800dab05  jz      short loc_1800DAB21
0x1800dab07  call    cs:__imp_GetLastError
0x1800dab0d  mov     ebx, eax
0x1800dab0f  mov     rcx, r14; hKey
0x1800dab12  call    cs:__imp_RegCloseKey
0x1800dab18  mov     ecx, ebx; dwErrCode
0x1800dab1a  call    cs:__imp_SetLastError
0x1800dab20  nop
0x1800dab21  mov     [rbp+hKey], 0
0x1800dab29  lea     rax, [rbp+hKey]
0x1800dab2d  mov     [rsp+30h+phkResult], rax; int
0x1800dab32  mov     r9d, 20019h; samDesired
0x1800dab38  xor     r8d, r8d; ulOptions
0x1800dab3b  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800dab42  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dab49  call    cs:__imp_RegOpenKeyExW
0x1800dab4f  mov     ebx, eax
0x1800dab51  mov     r14d, 80070000h
0x1800dab57  test    eax, eax
0x1800dab59  jle     short loc_1800DAB61
0x1800dab5b  movzx   ebx, ax
0x1800dab5e  or      ebx, r14d
0x1800dab61  test    ebx, ebx
0x1800dab63  jns     short loc_1800DAB9E
0x1800dab65  mov     edi, 80070002h
0x1800dab6a  cmp     ebx, edi
0x1800dab6c  jnz     short loc_1800DAB70
0x1800dab6e  jmp     short loc_1800DABE7
0x1800dab70  mov     rcx, [rbp+28h]; this
0x1800dab74  mov     r9d, ebx; char *
0x1800dab77  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800dab7e  mov     edx, 193h; void *
0x1800dab83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dab88  nop
0x1800dab89  mov     rcx, [rbp+hKey]; hKey
0x1800dab8d  test    rcx, rcx
0x1800dab90  jz      short loc_1800DAB99
0x1800dab92  call    cs:__imp_RegCloseKey
0x1800dab98  nop
0x1800dab99  jmp     loc_1800DAAF1
0x1800dab9e  mov     [rbp+Type], 0
0x1800daba5  mov     [rbp+cbData], 4
0x1800dabac  lea     rax, [rbp+cbData]
0x1800dabb0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800dabb5  mov     [rsp+30h+phkResult], rsi; int
0x1800dabba  lea     r9, [rbp+Type]; lpType
0x1800dabbe  xor     r8d, r8d; lpReserved
0x1800dabc1  mov     rdx, rdi; lpValueName
0x1800dabc4  mov     rcx, [rbp+hKey]; hKey
0x1800dabc8  call    cs:__imp_RegQueryValueExW
0x1800dabce  mov     ebx, eax
0x1800dabd0  test    eax, eax
0x1800dabd2  jle     short loc_1800DABDA
0x1800dabd4  movzx   ebx, ax
0x1800dabd7  or      ebx, r14d
0x1800dabda  test    ebx, ebx
0x1800dabdc  jns     short loc_1800DAC29
0x1800dabde  mov     edi, 80070002h
0x1800dabe3  cmp     ebx, edi
0x1800dabe5  jnz     short loc_1800DABFB
0x1800dabe7  mov     rcx, [rbp+hKey]; hKey
0x1800dabeb  test    rcx, rcx
0x1800dabee  jz      short loc_1800DABF7
0x1800dabf0  call    cs:__imp_RegCloseKey
0x1800dabf6  nop
0x1800dabf7  mov     eax, edi
0x1800dabf9  jmp     short loc_1800DAC3B
0x1800dabfb  mov     rcx, [rbp+28h]; this
0x1800dabff  mov     r9d, ebx; char *
0x1800dac02  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800dac09  mov     edx, 1A0h; void *
0x1800dac0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dac13  nop
0x1800dac14  mov     rcx, [rbp+hKey]; hKey
0x1800dac18  test    rcx, rcx
0x1800dac1b  jz      short loc_1800DAC24
0x1800dac1d  call    cs:__imp_RegCloseKey
0x1800dac23  nop
0x1800dac24  jmp     loc_1800DAAF1
0x1800dac29  mov     rcx, [rbp+hKey]; hKey
0x1800dac2d  test    rcx, rcx
0x1800dac30  jz      short loc_1800DAC39
0x1800dac32  call    cs:__imp_RegCloseKey
0x1800dac38  nop
0x1800dac39  xor     eax, eax
0x1800dac3b  add     rsp, 30h
0x1800dac3f  pop     r14
0x1800dac41  pop     rdi
0x1800dac42  pop     rsi
0x1800dac43  pop     rbx
0x1800dac44  pop     rbp
0x1800dac45  retn
```
