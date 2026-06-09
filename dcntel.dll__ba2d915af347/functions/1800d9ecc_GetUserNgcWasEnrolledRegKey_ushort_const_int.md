# GetUserNgcWasEnrolledRegKey(ushort const *,int *)

- ea: `0x1800d9ecc`
- end: `0x1800da168`
- name: `?GetUserNgcWasEnrolledRegKey@@YAJPEBGPEAH@Z`
- size: `668`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800db1a4`

## callees

- `0x180008dc0`
- `0x180011ce4`
- `0x180012734`
- `0x1800d9ecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800da012`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800da012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9fff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9fa2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9fec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da00a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da0e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da115`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da138`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9fa2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d9fec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da00a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da0e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da115`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800da138`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800da0bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800da0bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800da03d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800da03d`

## string_xrefs

- `0x1800d9f86`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800d9fd0`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800da06c`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800da0f9`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUserNgcWasEnrolledRegKey(const unsigned __int16 *a1, int *a2)
{
  __int64 v4; // rax
  const wchar_t *v5; // rcx
  __int64 v6; // rdx
  WCHAR *v7; // r8
  wchar_t v8; // r9
  unsigned int v9; // ebx
  WCHAR *v10; // rcx
  int v12; // eax
  DWORD LastError; // ebx
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD Type[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *(_DWORD *)Data = 0;
  cbData = 4;
  Type[0] = 0;
  hKey = 0;
  *a2 = 0;
  v4 = 2147483646;
  v5 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\NgcStatus\\";
  v6 = 260;
  v7 = SubKey;
  do
  {
    if ( !v4 )
      break;
    v8 = *v5;
    if ( !*v5 )
      break;
    ++v5;
    *v7++ = v8;
    --v4;
    --v6;
  }
  while ( v6 );
  v9 = v6 == 0 ? 0x8007007A : 0;
  v10 = v7 - 1;
  if ( v6 )
    v10 = v7;
  *v10 = 0;
  if ( !v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)v9,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v9;
  }
  v12 = StringCchCatW(SubKey, 0x104u, a1);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v12,
      phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v9;
  }
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(hKey);
    SetLastError(LastError);
  }
  hKey = 0;
  v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v9 = v14;
  if ( v14 > 0 )
    v9 = (unsigned __int16)v14 | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( v9 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v9,
        phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      return v9;
    }
    goto LABEL_28;
  }
  v15 = RegQueryValueExW(hKey, L"NgcSetup", 0, Type, Data, &cbData);
  v9 = v15;
  if ( v15 > 0 )
    v9 = (unsigned __int16)v15 | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( v9 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)v9,
        phkResultb);
      if ( hKey )
        RegCloseKey(hKey);
      return v9;
    }
LABEL_28:
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
  *a2 = *(_DWORD *)Data == 1;
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800d9ecc  mov     [rsp-8+arg_10], rbx
0x1800d9ed1  mov     [rsp-8+arg_18], rsi
0x1800d9ed6  push    rbp
0x1800d9ed7  push    rdi
0x1800d9ed8  push    r14
0x1800d9eda  lea     rbp, [rsp-170h]
0x1800d9ee2  sub     rsp, 270h
0x1800d9ee9  mov     rax, cs:__security_cookie
0x1800d9ef0  xor     rax, rsp
0x1800d9ef3  mov     [rbp+180h+var_20], rax
0x1800d9efa  mov     rsi, rdx
0x1800d9efd  mov     r10, rcx
0x1800d9f00  xor     r14d, r14d
0x1800d9f03  mov     dword ptr [rsp+280h+Data], r14d
0x1800d9f08  mov     [rsp+280h+cbData], 4
0x1800d9f10  mov     [rsp+280h+Type], r14d
0x1800d9f15  mov     [rsp+280h+hKey], r14
0x1800d9f1a  mov     [rdx], r14d
0x1800d9f1d  mov     eax, 7FFFFFFEh
0x1800d9f22  lea     rcx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800d9f29  mov     r11d, 104h
0x1800d9f2f  mov     edx, r11d
0x1800d9f32  lea     r8, [rsp+280h+SubKey]
0x1800d9f37  test    rax, rax
0x1800d9f3a  jz      short loc_1800D9F5B
0x1800d9f3c  movzx   r9d, word ptr [rcx]
0x1800d9f40  test    r9w, r9w
0x1800d9f44  jz      short loc_1800D9F5B
0x1800d9f46  add     rcx, 2
0x1800d9f4a  mov     [r8], r9w
0x1800d9f4e  add     r8, 2
0x1800d9f52  dec     rax
0x1800d9f55  sub     rdx, 1
0x1800d9f59  jnz     short loc_1800D9F37
0x1800d9f5b  mov     rax, rdx
0x1800d9f5e  neg     rax
0x1800d9f61  sbb     ebx, ebx
0x1800d9f63  not     ebx
0x1800d9f65  and     ebx, 8007007Ah
0x1800d9f6b  lea     rcx, [r8-2]
0x1800d9f6f  test    rdx, rdx
0x1800d9f72  cmovnz  rcx, r8
0x1800d9f76  mov     [rcx], r14w
0x1800d9f7a  jnz     short loc_1800D9FB0
0x1800d9f7c  mov     rcx, [rbp+188h]; this
0x1800d9f83  mov     r9d, ebx; char *
0x1800d9f86  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800d9f8d  mov     edx, 96h; void *
0x1800d9f92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9f97  nop
0x1800d9f98  mov     rcx, [rsp+280h+hKey]; hKey
0x1800d9f9d  test    rcx, rcx
0x1800d9fa0  jz      short loc_1800D9FA9
0x1800d9fa2  call    cs:__imp_RegCloseKey
0x1800d9fa8  nop
0x1800d9fa9  mov     eax, ebx
0x1800d9fab  jmp     loc_1800DA141
0x1800d9fb0  mov     r8, r10; unsigned __int16 *
0x1800d9fb3  mov     rdx, r11; unsigned __int64
0x1800d9fb6  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x1800d9fbb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d9fc0  mov     ebx, eax
0x1800d9fc2  test    eax, eax
0x1800d9fc4  jns     short loc_1800D9FF5
0x1800d9fc6  mov     rcx, [rbp+188h]; this
0x1800d9fcd  mov     r9d, eax; char *
0x1800d9fd0  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800d9fd7  mov     edx, 98h; void *
0x1800d9fdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9fe1  nop
0x1800d9fe2  mov     rcx, [rsp+280h+hKey]; hKey
0x1800d9fe7  test    rcx, rcx
0x1800d9fea  jz      short loc_1800D9FF3
0x1800d9fec  call    cs:__imp_RegCloseKey
0x1800d9ff2  nop
0x1800d9ff3  jmp     short loc_1800D9FA9
0x1800d9ff5  mov     rdi, [rsp+280h+hKey]
0x1800d9ffa  test    rdi, rdi
0x1800d9ffd  jz      short loc_1800DA019
0x1800d9fff  call    cs:__imp_GetLastError
0x1800da005  mov     ebx, eax
0x1800da007  mov     rcx, rdi; hKey
0x1800da00a  call    cs:__imp_RegCloseKey
0x1800da010  mov     ecx, ebx; dwErrCode
0x1800da012  call    cs:__imp_SetLastError
0x1800da018  nop
0x1800da019  mov     [rsp+280h+hKey], r14
0x1800da01e  lea     rax, [rsp+280h+hKey]
0x1800da023  mov     [rsp+280h+phkResult], rax; int
0x1800da028  mov     r9d, 20019h; samDesired
0x1800da02e  xor     r8d, r8d; ulOptions
0x1800da031  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x1800da036  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800da03d  call    cs:__imp_RegOpenKeyExW
0x1800da043  mov     ebx, eax
0x1800da045  mov     edi, 80070000h
0x1800da04a  test    eax, eax
0x1800da04c  jle     short loc_1800DA053
0x1800da04e  movzx   ebx, ax
0x1800da051  or      ebx, edi
0x1800da053  test    ebx, ebx
0x1800da055  jns     short loc_1800DA094
0x1800da057  mov     edi, 80070002h
0x1800da05c  cmp     ebx, edi
0x1800da05e  jnz     short loc_1800DA062
0x1800da060  jmp     short loc_1800DA0DA
0x1800da062  mov     rcx, [rbp+188h]; this
0x1800da069  mov     r9d, ebx; char *
0x1800da06c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800da073  mov     edx, 9Ch; void *
0x1800da078  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da07d  nop
0x1800da07e  mov     rcx, [rsp+280h+hKey]; hKey
0x1800da083  test    rcx, rcx
0x1800da086  jz      short loc_1800DA08F
0x1800da088  call    cs:__imp_RegCloseKey
0x1800da08e  nop
0x1800da08f  jmp     loc_1800D9FA9
0x1800da094  lea     rax, [rsp+280h+cbData]
0x1800da099  mov     [rsp+280h+lpcbData], rax; lpcbData
0x1800da09e  lea     rax, [rsp+280h+Data]
0x1800da0a3  mov     [rsp+280h+phkResult], rax; int
0x1800da0a8  lea     r9, [rsp+280h+Type]; lpType
0x1800da0ad  xor     r8d, r8d; lpReserved
0x1800da0b0  lea     rdx, aNgcsetup; "NgcSetup"
0x1800da0b7  mov     rcx, [rsp+280h+hKey]; hKey
0x1800da0bc  call    cs:__imp_RegQueryValueExW
0x1800da0c2  mov     ebx, eax
0x1800da0c4  test    eax, eax
0x1800da0c6  jle     short loc_1800DA0CD
0x1800da0c8  movzx   ebx, ax
0x1800da0cb  or      ebx, edi
0x1800da0cd  test    ebx, ebx
0x1800da0cf  jns     short loc_1800DA121
0x1800da0d1  mov     edi, 80070002h
0x1800da0d6  cmp     ebx, edi
0x1800da0d8  jnz     short loc_1800DA0EF
0x1800da0da  mov     rcx, [rsp+280h+hKey]; hKey
0x1800da0df  test    rcx, rcx
0x1800da0e2  jz      short loc_1800DA0EB
0x1800da0e4  call    cs:__imp_RegCloseKey
0x1800da0ea  nop
0x1800da0eb  mov     eax, edi
0x1800da0ed  jmp     short loc_1800DA141
0x1800da0ef  mov     rcx, [rbp+188h]; this
0x1800da0f6  mov     r9d, ebx; char *
0x1800da0f9  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800da100  mov     edx, 0A0h; void *
0x1800da105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da10a  nop
0x1800da10b  mov     rcx, [rsp+280h+hKey]; hKey
0x1800da110  test    rcx, rcx
0x1800da113  jz      short loc_1800DA11C
0x1800da115  call    cs:__imp_RegCloseKey
0x1800da11b  nop
0x1800da11c  jmp     loc_1800D9FA9
0x1800da121  mov     eax, r14d
0x1800da124  cmp     dword ptr [rsp+280h+Data], 1
0x1800da129  setz    al
0x1800da12c  mov     [rsi], eax
0x1800da12e  mov     rcx, [rsp+280h+hKey]; hKey
0x1800da133  test    rcx, rcx
0x1800da136  jz      short loc_1800DA13F
0x1800da138  call    cs:__imp_RegCloseKey
0x1800da13e  nop
0x1800da13f  xor     eax, eax
0x1800da141  mov     rcx, [rbp+180h+var_20]
0x1800da148  xor     rcx, rsp; StackCookie
0x1800da14b  call    __security_check_cookie
0x1800da150  lea     r11, [rsp+280h+var_10]
0x1800da158  mov     rbx, [r11+30h]
0x1800da15c  mov     rsi, [r11+38h]
0x1800da160  mov     rsp, r11
0x1800da163  pop     r14
0x1800da165  pop     rdi
0x1800da166  pop     rbp
0x1800da167  retn
```
