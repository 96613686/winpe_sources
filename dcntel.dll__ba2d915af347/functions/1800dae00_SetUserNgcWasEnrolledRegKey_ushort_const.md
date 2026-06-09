# SetUserNgcWasEnrolledRegKey(ushort const *)

- ea: `0x1800dae00`
- end: `0x1800db035`
- name: `?SetUserNgcWasEnrolledRegKey@@YAJPEBG@Z`
- size: `565`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800db1a4`

## callees

- `0x180008dc0`
- `0x180011ce4`
- `0x180012734`
- `0x1800a5e64`
- `0x1800dae00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800daf2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800daf2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800daf18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800daf18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daf05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daf23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daf9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daffb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800db011`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daf05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daf23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daf9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800daffb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800db011`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800dafca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800dafca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800daf69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800daf69`

## string_xrefs

- `0x1800dae9f`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800daee9`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800daf7d`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800dafde`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SetUserNgcWasEnrolledRegKey(const unsigned __int16 *a1)
{
  __int64 v2; // rax
  const wchar_t *v3; // rcx
  __int64 v4; // rdx
  WCHAR *v5; // r8
  wchar_t v6; // r9
  unsigned int v7; // ebx
  WCHAR *v8; // rcx
  int v10; // eax
  DWORD LastError; // ebx
  unsigned int v12; // eax
  unsigned int v13; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *(_DWORD *)Data = 1;
  hKey = 0;
  v2 = 2147483646;
  v3 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PasswordLess\\NgcStatus\\";
  v4 = 260;
  v5 = SubKey;
  do
  {
    if ( !v2 )
      break;
    v6 = *v3;
    if ( !*v3 )
      break;
    ++v3;
    *v5++ = v6;
    --v2;
    --v4;
  }
  while ( v4 );
  v7 = v4 == 0 ? 0x8007007A : 0;
  v8 = v5 - 1;
  if ( v4 )
    v8 = v5;
  *v8 = 0;
  if ( !v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)v7,
      dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  v10 = StringCchCatW(SubKey, 0x104u, a1);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v10,
      dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(hKey);
    SetLastError(LastError);
  }
  hKey = 0;
  v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v12 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x85,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v12,
           dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  v13 = RegSetValueExW(hKey, L"NgcSetup", 0, 4u, Data, 4u);
  if ( v13 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x87,
           (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
           (const char *)v13,
           dwOptionsb);
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800dae00  push    rbp
0x1800dae02  push    rbx
0x1800dae03  push    rsi
0x1800dae04  push    rdi
0x1800dae05  lea     rbp, [rsp-188h]
0x1800dae0d  sub     rsp, 288h
0x1800dae14  mov     rax, cs:__security_cookie
0x1800dae1b  xor     rax, rsp
0x1800dae1e  mov     [rbp+1A0h+var_30], rax
0x1800dae25  mov     r10, rcx
0x1800dae28  mov     dword ptr [rsp+2A0h+Data], 1
0x1800dae30  xor     esi, esi
0x1800dae32  mov     [rsp+2A0h+hKey], rsi
0x1800dae37  mov     eax, 7FFFFFFEh
0x1800dae3c  lea     rcx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800dae43  mov     r11d, 104h
0x1800dae49  mov     edx, r11d
0x1800dae4c  lea     r8, [rsp+2A0h+SubKey]
0x1800dae51  test    rax, rax
0x1800dae54  jz      short loc_1800DAE75
0x1800dae56  movzx   r9d, word ptr [rcx]
0x1800dae5a  test    r9w, r9w
0x1800dae5e  jz      short loc_1800DAE75
0x1800dae60  add     rcx, 2
0x1800dae64  mov     [r8], r9w
0x1800dae68  add     r8, 2
0x1800dae6c  dec     rax
0x1800dae6f  sub     rdx, 1
0x1800dae73  jnz     short loc_1800DAE51
0x1800dae75  mov     rax, rdx
0x1800dae78  neg     rax
0x1800dae7b  sbb     ebx, ebx
0x1800dae7d  not     ebx
0x1800dae7f  and     ebx, 8007007Ah
0x1800dae85  lea     rcx, [r8-2]
0x1800dae89  test    rdx, rdx
0x1800dae8c  cmovnz  rcx, r8
0x1800dae90  mov     [rcx], si
0x1800dae93  jnz     short loc_1800DAEC9
0x1800dae95  mov     rcx, [rbp+1A8h]; this
0x1800dae9c  mov     r9d, ebx; char *
0x1800dae9f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800daea6  mov     edx, 81h; void *
0x1800daeab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800daeb0  nop
0x1800daeb1  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800daeb6  test    rcx, rcx
0x1800daeb9  jz      short loc_1800DAEC2
0x1800daebb  call    cs:__imp_RegCloseKey
0x1800daec1  nop
0x1800daec2  mov     eax, ebx
0x1800daec4  jmp     loc_1800DB01A
0x1800daec9  mov     r8, r10; unsigned __int16 *
0x1800daecc  mov     rdx, r11; unsigned __int64
0x1800daecf  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x1800daed4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800daed9  mov     ebx, eax
0x1800daedb  test    eax, eax
0x1800daedd  jns     short loc_1800DAF0E
0x1800daedf  mov     rcx, [rbp+1A8h]; this
0x1800daee6  mov     r9d, eax; char *
0x1800daee9  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800daef0  mov     edx, 83h; void *
0x1800daef5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800daefa  nop
0x1800daefb  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800daf00  test    rcx, rcx
0x1800daf03  jz      short loc_1800DAF0C
0x1800daf05  call    cs:__imp_RegCloseKey
0x1800daf0b  nop
0x1800daf0c  jmp     short loc_1800DAEC2
0x1800daf0e  mov     rdi, [rsp+2A0h+hKey]
0x1800daf13  test    rdi, rdi
0x1800daf16  jz      short loc_1800DAF32
0x1800daf18  call    cs:__imp_GetLastError
0x1800daf1e  mov     ebx, eax
0x1800daf20  mov     rcx, rdi; hKey
0x1800daf23  call    cs:__imp_RegCloseKey
0x1800daf29  mov     ecx, ebx; dwErrCode
0x1800daf2b  call    cs:__imp_SetLastError
0x1800daf31  nop
0x1800daf32  mov     [rsp+2A0h+hKey], rsi
0x1800daf37  mov     [rsp+2A0h+lpdwDisposition], rsi; lpdwDisposition
0x1800daf3c  lea     rax, [rsp+2A0h+hKey]
0x1800daf41  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800daf46  mov     [rsp+2A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800daf4b  mov     [rsp+2A0h+samDesired], 20006h; samDesired
0x1800daf53  mov     [rsp+2A0h+dwOptions], esi; unsigned int
0x1800daf57  xor     r9d, r9d; lpClass
0x1800daf5a  xor     r8d, r8d; Reserved
0x1800daf5d  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800daf62  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800daf69  call    cs:__imp_RegCreateKeyExW
0x1800daf6f  test    eax, eax
0x1800daf71  jz      short loc_1800DAFA6
0x1800daf73  mov     rcx, [rbp+1A8h]; this
0x1800daf7a  mov     r9d, eax; char *
0x1800daf7d  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800daf84  mov     edx, 85h; void *
0x1800daf89  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800daf8e  mov     ebx, eax
0x1800daf90  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800daf95  test    rcx, rcx
0x1800daf98  jz      short loc_1800DAFA1
0x1800daf9a  call    cs:__imp_RegCloseKey
0x1800dafa0  nop
0x1800dafa1  jmp     loc_1800DAEC2
0x1800dafa6  mov     r9d, 4; dwType
0x1800dafac  mov     [rsp+2A0h+samDesired], r9d; cbData
0x1800dafb1  lea     rax, [rsp+2A0h+Data]
0x1800dafb6  mov     qword ptr [rsp+2A0h+dwOptions], rax; unsigned int
0x1800dafbb  xor     r8d, r8d; Reserved
0x1800dafbe  lea     rdx, aNgcsetup; "NgcSetup"
0x1800dafc5  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800dafca  call    cs:__imp_RegSetValueExW
0x1800dafd0  test    eax, eax
0x1800dafd2  jz      short loc_1800DB007
0x1800dafd4  mov     rcx, [rbp+1A8h]; this
0x1800dafdb  mov     r9d, eax; char *
0x1800dafde  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800dafe5  mov     edx, 87h; void *
0x1800dafea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800dafef  mov     ebx, eax
0x1800daff1  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800daff6  test    rcx, rcx
0x1800daff9  jz      short loc_1800DB002
0x1800daffb  call    cs:__imp_RegCloseKey
0x1800db001  nop
0x1800db002  jmp     loc_1800DAEC2
0x1800db007  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800db00c  test    rcx, rcx
0x1800db00f  jz      short loc_1800DB018
0x1800db011  call    cs:__imp_RegCloseKey
0x1800db017  nop
0x1800db018  xor     eax, eax
0x1800db01a  mov     rcx, [rbp+1A0h+var_30]
0x1800db021  xor     rcx, rsp; StackCookie
0x1800db024  call    __security_check_cookie
0x1800db029  add     rsp, 288h
0x1800db030  pop     rdi
0x1800db031  pop     rsi
0x1800db032  pop     rbx
0x1800db033  pop     rbp
0x1800db034  retn
```
