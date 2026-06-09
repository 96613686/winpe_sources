# URL_AUTHZ_RULE_ENTRY::MatchUserNameForWindowsPrincipal(FTP_USER *,void *,int *)

- ea: `0x180024954`
- end: `0x180024b61`
- name: `?MatchUserNameForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVFTP_USER@@PEAXPEAH@Z`
- size: `525`
- prototype: `static int(struct FTP_USER *, void *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024174`

## callees

- `0x180024954`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180024a2d`
- `KERNEL32!GetLastError` at `0x180024a38`
- `KERNEL32!GetLastError` at `0x180024aa3`
- `KERNEL32!GetLastError` at `0x180024ae0`
- `KERNEL32!GetLastError` at `0x180024a2d`
- `KERNEL32!GetLastError` at `0x180024a38`
- `KERNEL32!GetLastError` at `0x180024aa3`
- `KERNEL32!GetLastError` at `0x180024ae0`
- `ADVAPI32!GetTokenInformation` at `0x180024a1f`
- `ADVAPI32!GetTokenInformation` at `0x180024ad6`
- `ADVAPI32!GetTokenInformation` at `0x180024a1f`
- `ADVAPI32!GetTokenInformation` at `0x180024ad6`
- `ADVAPI32!EqualSid` at `0x180024b16`
- `ADVAPI32!EqualSid` at `0x180024b16`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180024b2e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180024b3a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180024b2e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180024b3a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180024a99`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180024a99`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800249d5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800249d5`
- `iisutil!PuDbgPrintError` at `0x180024a85`
- `iisutil!PuDbgPrintError` at `0x180024a85`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024b22`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180024b22`

## string_xrefs

- `0x180024a60`: `Failed to call GetTokenInformation() to retrieve SIDfor the user context\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall URL_AUTHZ_RULE_ENTRY::MatchUserNameForWindowsPrincipal(struct FTP_USER *a1, void *a2, int *a3)
{
  void *v6; // rbx
  unsigned int v7; // ebx
  signed int LastError; // eax
  __int64 v9; // r8
  signed int v10; // eax
  signed int v11; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[32]; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID TokenInformation; // [rsp+58h] [rbp-A8h]
  DWORD TokenInformationLength; // [rsp+60h] [rbp-A0h]
  __int16 v17; // [rsp+64h] [rbp-9Ch]
  _QWORD v18[5]; // [rsp+68h] [rbp-98h] BYREF
  int v19; // [rsp+90h] [rbp-70h]
  __int16 v20; // [rsp+94h] [rbp-6Ch]
  _BYTE v21[56]; // [rsp+98h] [rbp-68h] BYREF
  char v22; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v23[127]; // [rsp+D1h] [rbp-2Fh] BYREF

  memset_0(v23, 0, sizeof(v23));
  v22 = 0;
  TokenInformation = &v22;
  TokenInformationLength = 128;
  v17 = 256;
  ReturnLength = 0;
  v18[0] = 0;
  v18[4] = v18;
  v19 = 32;
  v20 = 256;
  STRU::STRU(v21);
  *a3 = 0;
  v6 = (void *)(*(__int64 (__fastcall **)(struct FTP_USER *))(*(_QWORD *)a1 + 56LL))(a1);
  if ( !v6 )
  {
    v7 = -2147418113;
    goto LABEL_19;
  }
  if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &ReturnLength) )
    goto LABEL_18;
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v9 = 693;
LABEL_9:
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_url_authz\\url_authz_rule_list.cxx",
        v9,
        "URL_AUTHZ_RULE_ENTRY::MatchUserNameForWindowsPrincipal",
        v7,
        "Failed to call GetTokenInformation() to retrieve SIDfor the user context\n");
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  if ( !BUFFER::Resize((BUFFER *)v14, ReturnLength) )
  {
    v10 = GetLastError();
    v7 = v10;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_19;
  }
  if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &ReturnLength) )
  {
LABEL_18:
    v7 = 0;
    *a3 = EqualSid(*(PSID *)TokenInformation, a2);
    goto LABEL_19;
  }
  v11 = GetLastError();
  v7 = v11;
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v9 = 719;
    goto LABEL_9;
  }
LABEL_19:
  STRU::~STRU(v21);
  BUFFER::~BUFFER((BUFFER *)v18);
  BUFFER::~BUFFER((BUFFER *)v14);
  return v7;
}

```

## disassembly

```asm
0x180024954  mov     [rsp-8+arg_18], rbx
0x180024959  push    rbp
0x18002495a  push    rsi
0x18002495b  push    rdi
0x18002495c  lea     rbp, [rsp-60h]
0x180024961  sub     rsp, 160h
0x180024968  mov     rax, cs:__security_cookie
0x18002496f  xor     rax, rsp
0x180024972  mov     [rbp+70h+var_20], rax
0x180024976  mov     rdi, r8
0x180024979  mov     rsi, rdx
0x18002497c  mov     rbx, rcx
0x18002497f  xor     edx, edx; Val
0x180024981  lea     r8d, [rdx+7Fh]; Size
0x180024985  lea     rcx, [rbp+70h+var_9F]; void *
0x180024989  call    memset_0
0x18002498e  mov     [rbp+70h+var_A0], 0
0x180024992  lea     rax, [rbp+70h+var_A0]
0x180024996  mov     [rsp+170h+TokenInformation], rax
0x18002499b  mov     [rsp+170h+TokenInformationLength], 80h
0x1800249a3  mov     [rsp+170h+var_10C], 100h
0x1800249aa  mov     [rsp+170h+var_140], 0
0x1800249b2  mov     [rsp+170h+var_108], 0
0x1800249bb  lea     rax, [rsp+170h+var_108]
0x1800249c0  mov     [rbp+70h+var_E8], rax
0x1800249c4  mov     [rbp+70h+var_E0], 20h ; ' '
0x1800249cb  mov     [rbp+70h+var_DC], 100h
0x1800249d1  lea     rcx, [rbp+70h+var_D8]
0x1800249d5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800249db  nop
0x1800249dc  mov     dword ptr [rdi], 0
0x1800249e2  mov     rax, [rbx]
0x1800249e5  mov     rcx, rbx
0x1800249e8  mov     rax, [rax+38h]
0x1800249ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249f1  mov     rbx, rax
0x1800249f4  test    rax, rax
0x1800249f7  jnz     short loc_180024A03
0x1800249f9  mov     ebx, 8000FFFFh
0x1800249fe  jmp     loc_180024B1E
0x180024a03  lea     rax, [rsp+170h+var_140]
0x180024a08  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x180024a0d  mov     r9d, [rsp+170h+TokenInformationLength]; TokenInformationLength
0x180024a12  mov     r8, [rsp+170h+TokenInformation]; TokenInformation
0x180024a17  mov     edx, 1; TokenInformationClass
0x180024a1c  mov     rcx, rbx; TokenHandle
0x180024a1f  call    cs:__imp_GetTokenInformation
0x180024a25  test    eax, eax
0x180024a27  jnz     loc_180024B09
0x180024a2d  call    cs:__imp_GetLastError
0x180024a33  cmp     eax, 7Ah ; 'z'
0x180024a36  jz      short loc_180024A90
0x180024a38  call    cs:__imp_GetLastError
0x180024a3e  mov     ebx, eax
0x180024a40  test    eax, eax
0x180024a42  jle     short loc_180024A4D
0x180024a44  movzx   ebx, ax
0x180024a47  or      ebx, 80070000h
0x180024a4d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024a54  jz      loc_180024B1E
0x180024a5a  mov     r8d, 2B5h
0x180024a60  lea     rax, aFailedToCallGe; "Failed to call GetTokenInformation() to"...
0x180024a67  mov     [rsp+170h+var_148], rax
0x180024a6c  lea     r9, aUrlAuthzRuleEn; "URL_AUTHZ_RULE_ENTRY::MatchUserNameForW"...
0x180024a73  mov     dword ptr [rsp+170h+ReturnLength], ebx
0x180024a77  lea     rdx, aInetsrvIisIisr_33; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180024a7e  mov     rcx, cs:g_pDebug
0x180024a85  call    cs:__imp_PuDbgPrintError
0x180024a8b  jmp     loc_180024B1E
0x180024a90  mov     edx, [rsp+170h+var_140]
0x180024a94  lea     rcx, [rsp+170h+var_138]
0x180024a99  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180024a9f  test    al, al
0x180024aa1  jnz     short loc_180024ABA
0x180024aa3  call    cs:__imp_GetLastError
0x180024aa9  mov     ebx, eax
0x180024aab  test    eax, eax
0x180024aad  jle     short loc_180024B1E
0x180024aaf  movzx   ebx, ax
0x180024ab2  or      ebx, 80070000h
0x180024ab8  jmp     short loc_180024B1E
0x180024aba  lea     rax, [rsp+170h+var_140]
0x180024abf  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x180024ac4  mov     r9d, [rsp+170h+TokenInformationLength]; TokenInformationLength
0x180024ac9  mov     r8, [rsp+170h+TokenInformation]; TokenInformation
0x180024ace  mov     edx, 1; TokenInformationClass
0x180024ad3  mov     rcx, rbx; TokenHandle
0x180024ad6  call    cs:__imp_GetTokenInformation
0x180024adc  test    eax, eax
0x180024ade  jnz     short loc_180024B09
0x180024ae0  call    cs:__imp_GetLastError
0x180024ae6  mov     ebx, eax
0x180024ae8  test    eax, eax
0x180024aea  jle     short loc_180024AF5
0x180024aec  movzx   ebx, ax
0x180024aef  or      ebx, 80070000h
0x180024af5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024afc  jz      short loc_180024B1E
0x180024afe  mov     r8d, 2CFh
0x180024b04  jmp     loc_180024A60
0x180024b09  xor     ebx, ebx
0x180024b0b  mov     rcx, [rsp+170h+TokenInformation]
0x180024b10  mov     rdx, rsi; pSid2
0x180024b13  mov     rcx, [rcx]; pSid1
0x180024b16  call    cs:__imp_EqualSid
0x180024b1c  mov     [rdi], eax
0x180024b1e  lea     rcx, [rbp+70h+var_D8]
0x180024b22  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180024b28  nop
0x180024b29  lea     rcx, [rsp+170h+var_108]
0x180024b2e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024b34  nop
0x180024b35  lea     rcx, [rsp+170h+var_138]
0x180024b3a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024b40  mov     eax, ebx
0x180024b42  mov     rcx, [rbp+70h+var_20]
0x180024b46  xor     rcx, rsp; StackCookie
0x180024b49  call    __security_check_cookie
0x180024b4e  mov     rbx, [rsp+170h+arg_18]
0x180024b56  add     rsp, 160h
0x180024b5d  pop     rdi
0x180024b5e  pop     rsi
0x180024b5f  pop     rbp
0x180024b60  retn
```
