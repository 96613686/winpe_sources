# Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)

- ea: `0x180013394`
- end: `0x1800135eb`
- name: `?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z`
- size: `599`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010124`

## callees

- `0x180001540`
- `0x180012fd8`
- `0x180013394`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x180013486`
- `ntdll!NtOpenProcessToken` at `0x180013486`
- `ntdll!NtOpenThreadToken` at `0x1800133de`
- `ntdll!NtOpenThreadToken` at `0x1800133de`
- `ntdll!NtPrivilegeCheck` at `0x180013523`
- `ntdll!NtPrivilegeCheck` at `0x180013523`
- `ntdll!NtClose` at `0x180013445`
- `ntdll!NtClose` at `0x1800134dd`
- `ntdll!NtClose` at `0x18001357a`
- `ntdll!NtClose` at `0x1800135af`
- `ntdll!NtClose` at `0x180013445`
- `ntdll!NtClose` at `0x1800134dd`
- `ntdll!NtClose` at `0x18001357a`
- `ntdll!NtClose` at `0x1800135af`

## string_xrefs

- `0x1800133fa`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180013492`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001352f`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1800134b0`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())`
- `0x180013418`: `NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())`
- `0x18001354d`: `NtPrivilegeCheck(Token, &PrivilegeSet, &Result)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
        Windows::WCP::Implementation::Rtl *this,
        bool *a2)
{
  unsigned int v3; // ebx
  void *v5; // rcx
  _QWORD v6[4]; // [rsp+28h] [rbp-49h] BYREF
  _QWORD v7[4]; // [rsp+48h] [rbp-29h] BYREF
  _QWORD v8[5]; // [rsp+68h] [rbp-9h] BYREF
  unsigned __int8 Result[8]; // [rsp+90h] [rbp+1Fh] BYREF
  void *TokenHandle; // [rsp+98h] [rbp+27h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+A0h] [rbp+2Fh] BYREF

  v8[4] = -2;
  *(_BYTE *)this = 0;
  TokenHandle = 0;
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -1073741700 )
  {
    v6[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v6[1] = "Windows::WCP::Implementation::Rtl::CanSetSystemOwner";
    v6[2] = 570;
    v6[3] = "NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())";
    RtlReportErrorOrigination(v6, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v3);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      TokenHandle = 0;
    }
    return v3;
  }
  v5 = TokenHandle;
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    if ( (v3 & 0x80000000) != 0 )
    {
      v7[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v7[1] = "Windows::WCP::Implementation::Rtl::CanSetSystemOwner";
      v7[2] = 578;
      v7[3] = "NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())";
      RtlReportErrorOrigination(v7, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v3);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(TokenHandle) < 0 )
          __fastfail(7u);
        TokenHandle = 0;
      }
      return v3;
    }
    v5 = TokenHandle;
  }
  Result[0] = 0;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Luid = (LUID)18LL;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  v3 = NtPrivilegeCheck(v5, &RequiredPrivileges, Result);
  if ( (v3 & 0x80000000) != 0 )
  {
    v8[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v8[1] = "Windows::WCP::Implementation::Rtl::CanSetSystemOwner";
    v8[2] = 586;
    v8[3] = "NtPrivilegeCheck(Token, &PrivilegeSet, &Result)";
    RtlReportErrorOrigination(v8, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v3);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( NtClose(TokenHandle) < 0 )
        __fastfail(7u);
      TokenHandle = 0;
    }
    return v3;
  }
  *(_BYTE *)this = Result[0] != 0;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( NtClose(TokenHandle) < 0 )
      __fastfail(7u);
    TokenHandle = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180013394  mov     rax, rsp
0x180013397  push    rbp
0x180013398  lea     rbp, [rax-5Fh]
0x18001339c  sub     rsp, 0C0h
0x1800133a3  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x1800133ab  mov     [rax+10h], rbx
0x1800133af  mov     [rax+18h], rdi
0x1800133b3  mov     rax, cs:__security_cookie
0x1800133ba  xor     rax, rsp
0x1800133bd  mov     [rbp+57h+var_10], rax
0x1800133c1  mov     rdi, rcx
0x1800133c4  mov     byte ptr [rcx], 0
0x1800133c7  mov     [rbp+57h+TokenHandle], 0
0x1800133cf  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800133d3  xor     r8d, r8d; OpenAsSelf
0x1800133d6  lea     edx, [r8+8]; DesiredAccess
0x1800133da  lea     rcx, [r8-2]; ThreadHandle
0x1800133de  call    cs:__imp_NtOpenThreadToken
0x1800133e4  mov     ebx, eax
0x1800133e6  mov     eax, 80000000h
0x1800133eb  lea     ecx, [rbx+rax]
0x1800133ee  test    eax, ecx
0x1800133f0  jnz     short loc_180013465
0x1800133f2  cmp     ebx, 0C000007Ch
0x1800133f8  jz      short loc_180013465
0x1800133fa  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180013401  mov     [rbp+57h+var_A0], rax
0x180013405  lea     rax, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x18001340c  mov     [rbp+57h+var_98], rax
0x180013410  mov     [rbp+57h+var_90], 23Ah
0x180013418  lea     rax, aNtopenthreadto; "NtOpenThreadToken( ( (HANDLE)(LONG_PTR)"...
0x18001341f  mov     [rbp+57h+var_88], rax
0x180013423  mov     r8d, ebx
0x180013426  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001342d  lea     rcx, [rbp+57h+var_A0]
0x180013431  call    RtlReportErrorOrigination
0x180013436  nop
0x180013437  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18001343b  lea     rax, [rcx-1]
0x18001343f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013443  ja      short loc_18001345E
0x180013445  call    cs:__imp_NtClose
0x18001344b  test    eax, eax
0x18001344d  jns     short loc_180013456
0x18001344f  mov     ecx, 7
0x180013454  int     29h; Win8: RtlFailFast(ecx)
0x180013456  mov     [rbp+57h+TokenHandle], 0
0x18001345e  mov     eax, ebx
0x180013460  jmp     loc_1800135CA
0x180013465  mov     rcx, [rbp+57h+TokenHandle]
0x180013469  lea     rax, [rcx+1]
0x18001346d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180013473  jnz     loc_1800134FF
0x180013479  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001347d  mov     edx, 8; DesiredAccess
0x180013482  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180013486  call    cs:__imp_NtOpenProcessToken
0x18001348c  mov     ebx, eax
0x18001348e  test    eax, eax
0x180013490  jns     short loc_1800134FB
0x180013492  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180013499  mov     [rbp+57h+var_80], rax
0x18001349d  lea     rax, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x1800134a4  mov     [rbp+57h+var_78], rax
0x1800134a8  mov     [rbp+57h+var_70], 242h
0x1800134b0  lea     rax, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x1800134b7  mov     [rbp+57h+var_68], rax
0x1800134bb  mov     r8d, ebx
0x1800134be  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800134c5  lea     rcx, [rbp+57h+var_80]
0x1800134c9  call    RtlReportErrorOrigination
0x1800134ce  nop
0x1800134cf  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800134d3  lea     rax, [rcx-1]
0x1800134d7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800134db  ja      short loc_1800134F6
0x1800134dd  call    cs:__imp_NtClose
0x1800134e3  test    eax, eax
0x1800134e5  jns     short loc_1800134EE
0x1800134e7  mov     ecx, 7
0x1800134ec  int     29h; Win8: RtlFailFast(ecx)
0x1800134ee  mov     [rbp+57h+TokenHandle], 0
0x1800134f6  jmp     loc_18001345E
0x1800134fb  mov     rcx, [rbp+57h+TokenHandle]; ClientToken
0x1800134ff  mov     [rbp+57h+Result], 0
0x180013503  mov     eax, 1
0x180013508  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], eax
0x18001350b  mov     [rbp+57h+RequiredPrivileges.Control], eax
0x18001350e  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x180013516  xor     eax, eax
0x180013518  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x18001351b  lea     r8, [rbp+57h+Result]; Result
0x18001351f  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x180013523  call    cs:__imp_NtPrivilegeCheck
0x180013529  mov     ebx, eax
0x18001352b  test    eax, eax
0x18001352d  jns     short loc_180013598
0x18001352f  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180013536  mov     [rbp+57h+var_60], rax
0x18001353a  lea     rax, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x180013541  mov     [rbp+57h+var_58], rax
0x180013545  mov     [rbp+57h+var_50], 24Ah
0x18001354d  lea     rax, aNtprivilegeche; "NtPrivilegeCheck(Token, &PrivilegeSet, "...
0x180013554  mov     [rbp+57h+var_48], rax
0x180013558  mov     r8d, ebx
0x18001355b  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180013562  lea     rcx, [rbp+57h+var_60]
0x180013566  call    RtlReportErrorOrigination
0x18001356b  nop
0x18001356c  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180013570  lea     rax, [rcx-1]
0x180013574  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013578  ja      short loc_180013593
0x18001357a  call    cs:__imp_NtClose
0x180013580  test    eax, eax
0x180013582  jns     short loc_18001358B
0x180013584  mov     ecx, 7
0x180013589  int     29h; Win8: RtlFailFast(ecx)
0x18001358b  mov     [rbp+57h+TokenHandle], 0
0x180013593  jmp     loc_18001345E
0x180013598  cmp     [rbp+57h+Result], 0
0x18001359c  setnz   al
0x18001359f  mov     [rdi], al
0x1800135a1  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800135a5  lea     rax, [rcx-1]
0x1800135a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800135ad  ja      short loc_1800135C8
0x1800135af  call    cs:__imp_NtClose
0x1800135b5  test    eax, eax
0x1800135b7  jns     short loc_1800135C0
0x1800135b9  mov     ecx, 7
0x1800135be  int     29h; Win8: RtlFailFast(ecx)
0x1800135c0  mov     [rbp+57h+TokenHandle], 0
0x1800135c8  xor     eax, eax
0x1800135ca  mov     rcx, [rbp+57h+var_10]
0x1800135ce  xor     rcx, rsp; StackCookie
0x1800135d1  call    __security_check_cookie
0x1800135d6  lea     r11, [rsp+0C0h+var_s0]
0x1800135de  mov     rbx, [r11+18h]
0x1800135e2  mov     rdi, [r11+20h]
0x1800135e6  mov     rsp, r11
0x1800135e9  pop     rbp
0x1800135ea  retn
```
