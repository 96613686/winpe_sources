# IsUserAdmin(int *)

- ea: `0x14002a418`
- end: `0x14002a6b6`
- name: `?IsUserAdmin@@YAJPEAH@Z`
- size: `670`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002aeec`

## callees

- `0x14002a418`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x14002a4c9`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14002a4c9`
- `ADVAPI32!CheckTokenMembership` at `0x14002a50d`
- `ADVAPI32!CheckTokenMembership` at `0x14002a613`
- `ADVAPI32!CheckTokenMembership` at `0x14002a50d`
- `ADVAPI32!CheckTokenMembership` at `0x14002a613`
- `ADVAPI32!OpenProcessToken` at `0x14002a56a`
- `ADVAPI32!OpenProcessToken` at `0x14002a56a`
- `ADVAPI32!GetTokenInformation` at `0x14002a5c2`
- `ADVAPI32!GetTokenInformation` at `0x14002a5c2`
- `ADVAPI32!FreeSid` at `0x14002a68f`
- `ADVAPI32!FreeSid` at `0x14002a68f`
- `KERNEL32!GetCurrentProcess` at `0x14002a552`
- `KERNEL32!GetCurrentProcess` at `0x14002a552`
- `KERNEL32!CloseHandle` at `0x14002a65d`
- `KERNEL32!CloseHandle` at `0x14002a676`
- `KERNEL32!CloseHandle` at `0x14002a65d`
- `KERNEL32!CloseHandle` at `0x14002a676`
- `KERNEL32!GetLastError` at `0x14002a4d9`
- `KERNEL32!GetLastError` at `0x14002a51d`
- `KERNEL32!GetLastError` at `0x14002a57a`
- `KERNEL32!GetLastError` at `0x14002a5d2`
- `KERNEL32!GetLastError` at `0x14002a623`
- `KERNEL32!GetLastError` at `0x14002a4d9`
- `KERNEL32!GetLastError` at `0x14002a51d`
- `KERNEL32!GetLastError` at `0x14002a57a`
- `KERNEL32!GetLastError` at `0x14002a5d2`
- `KERNEL32!GetLastError` at `0x14002a623`

## string_xrefs

- `0x14002a477`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall IsUserAdmin(int *a1)
{
  int v2; // ebx
  signed int LastError; // eax
  CEventLogger *v4; // rcx
  signed int v5; // eax
  CEventLogger *v6; // rcx
  WINBOOL v7; // eax
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  CEventLogger *v10; // rcx
  signed int v11; // eax
  CEventLogger *v12; // rcx
  signed int v13; // eax
  CEventLogger *v14; // rcx
  WINBOOL IsMember; // [rsp+60h] [rbp-9h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-1h] BYREF
  __int64 TokenInformation; // [rsp+70h] [rbp+7h] BYREF
  PSID SidToCheck; // [rsp+78h] [rbp+Fh] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+84h] [rbp+1Bh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  TokenHandle = (void *)-1LL;
  TokenInformation = -1;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    CEventLogger::LogError(
      0,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x104Fu,
      L"IsUserAdmin",
      0x80004003);
    goto LABEL_30;
  }
  *a1 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    CEventLogger::LogError(
      v4,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x105Du,
      L"IsUserAdmin",
      v2);
    goto LABEL_30;
  }
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v5 = GetLastError();
    v2 = v5;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1068u,
      L"IsUserAdmin",
      v2);
    goto LABEL_30;
  }
  v7 = IsMember;
  if ( IsMember )
  {
LABEL_29:
    *a1 = v7;
    v2 = 0;
    goto LABEL_30;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
    v9 = GetLastError();
    v2 = v9;
    if ( v9 > 0 )
      v2 = (unsigned __int16)v9 | 0x80070000;
    CEventLogger::LogError(
      v10,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x107Au,
      L"IsUserAdmin",
      v2);
    goto LABEL_30;
  }
  ReturnLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength) )
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v2 = 0;
    if ( v11 != -2147023584 )
      v2 = v11;
    if ( v2 < 0 )
      CEventLogger::LogError(
        v12,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x1098u,
        L"IsUserAdmin",
        v2);
    goto LABEL_30;
  }
  if ( CheckTokenMembership((HANDLE)TokenInformation, SidToCheck, &IsMember) )
  {
    v7 = IsMember;
    goto LABEL_29;
  }
  v13 = GetLastError();
  v2 = v13;
  if ( v13 > 0 )
    v2 = (unsigned __int16)v13 | 0x80070000;
  CEventLogger::LogError(
    v14,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
    0x10A6u,
    L"IsUserAdmin",
    v2);
LABEL_30:
  if ( TokenHandle != (void *)-1LL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = (void *)-1LL;
  }
  if ( TokenInformation != -1 )
  {
    CloseHandle((HANDLE)TokenInformation);
    TokenInformation = -1;
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002a418  push    rbp
0x14002a41a  push    rbx
0x14002a41b  push    rsi
0x14002a41c  push    rdi
0x14002a41d  lea     rbp, [rsp-3Fh]
0x14002a422  sub     rsp, 0A8h
0x14002a429  mov     rax, cs:__security_cookie
0x14002a430  xor     rax, rsp
0x14002a433  mov     [rbp+57h+var_30], rax
0x14002a437  xor     edi, edi
0x14002a439  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14002a43f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14002a443  mov     [rbp+57h+IsMember], edi
0x14002a446  mov     [rbp+57h+TokenHandle], rsi
0x14002a44a  mov     rbx, rcx
0x14002a44d  mov     [rbp+57h+TokenInformation], rsi
0x14002a451  mov     [rbp+57h+SidToCheck], rdi
0x14002a455  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x14002a458  test    rcx, rcx
0x14002a45b  jnz     short loc_14002A494
0x14002a45d  mov     ebx, 80004003h
0x14002a462  mov     [rsp+0C0h+nSubAuthority3], 80004003h; unsigned int
0x14002a46a  mov     r9d, 104Fh; unsigned int
0x14002a470  lea     rax, aIsuseradmin; "IsUserAdmin"
0x14002a477  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002a47e  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; unsigned __int16 *
0x14002a483  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002a48a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002a48f  jmp     loc_14002A654
0x14002a494  lea     rax, [rbp+57h+SidToCheck]
0x14002a498  mov     [rcx], edi
0x14002a49a  mov     [rsp+0C0h+pSid], rax; pSid
0x14002a49f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14002a4a3  mov     [rsp+0C0h+nSubAuthority7], edi; nSubAuthority7
0x14002a4a7  mov     r9d, 220h; nSubAuthority1
0x14002a4ad  mov     [rsp+0C0h+nSubAuthority6], edi; nSubAuthority6
0x14002a4b1  mov     r8d, 20h ; ' '; nSubAuthority0
0x14002a4b7  mov     [rsp+0C0h+nSubAuthority5], edi; nSubAuthority5
0x14002a4bb  mov     dl, 2; nSubAuthorityCount
0x14002a4bd  mov     [rsp+0C0h+nSubAuthority4], edi; nSubAuthority4
0x14002a4c1  mov     [rsp+0C0h+nSubAuthority3], edi; nSubAuthority3
0x14002a4c5  mov     [rsp+0C0h+nSubAuthority2], edi; nSubAuthority2
0x14002a4c9  call    cs:__imp_AllocateAndInitializeSid
0x14002a4d0  nop     dword ptr [rax+rax+00h]
0x14002a4d5  test    eax, eax
0x14002a4d7  jnz     short loc_14002A503
0x14002a4d9  call    cs:__imp_GetLastError
0x14002a4e0  nop     dword ptr [rax+rax+00h]
0x14002a4e5  mov     ebx, eax
0x14002a4e7  test    eax, eax
0x14002a4e9  jle     short loc_14002A4F4
0x14002a4eb  movzx   ebx, ax
0x14002a4ee  or      ebx, 80070000h
0x14002a4f4  mov     [rsp+0C0h+nSubAuthority3], ebx
0x14002a4f8  mov     r9d, 105Dh
0x14002a4fe  jmp     loc_14002A470
0x14002a503  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x14002a507  lea     r8, [rbp+57h+IsMember]; IsMember
0x14002a50b  xor     ecx, ecx; TokenHandle
0x14002a50d  call    cs:__imp_CheckTokenMembership
0x14002a514  nop     dword ptr [rax+rax+00h]
0x14002a519  test    eax, eax
0x14002a51b  jnz     short loc_14002A547
0x14002a51d  call    cs:__imp_GetLastError
0x14002a524  nop     dword ptr [rax+rax+00h]
0x14002a529  mov     ebx, eax
0x14002a52b  test    eax, eax
0x14002a52d  jle     short loc_14002A538
0x14002a52f  movzx   ebx, ax
0x14002a532  or      ebx, 80070000h
0x14002a538  mov     [rsp+0C0h+nSubAuthority3], ebx
0x14002a53c  mov     r9d, 1068h
0x14002a542  jmp     loc_14002A470
0x14002a547  mov     eax, [rbp+57h+IsMember]
0x14002a54a  test    eax, eax
0x14002a54c  jnz     loc_14002A650
0x14002a552  call    cs:__imp_GetCurrentProcess
0x14002a559  nop     dword ptr [rax+rax+00h]
0x14002a55e  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x14002a562  mov     edx, 0Ah; DesiredAccess
0x14002a567  mov     rcx, rax; ProcessHandle
0x14002a56a  call    cs:__imp_OpenProcessToken
0x14002a571  nop     dword ptr [rax+rax+00h]
0x14002a576  test    eax, eax
0x14002a578  jnz     short loc_14002A5A4
0x14002a57a  call    cs:__imp_GetLastError
0x14002a581  nop     dword ptr [rax+rax+00h]
0x14002a586  mov     ebx, eax
0x14002a588  test    eax, eax
0x14002a58a  jle     short loc_14002A595
0x14002a58c  movzx   ebx, ax
0x14002a58f  or      ebx, 80070000h
0x14002a595  mov     [rsp+0C0h+nSubAuthority3], ebx
0x14002a599  mov     r9d, 107Ah
0x14002a59f  jmp     loc_14002A470
0x14002a5a4  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14002a5a8  lea     rax, [rbp+57h+ReturnLength]
0x14002a5ac  mov     r9d, 8; TokenInformationLength
0x14002a5b2  mov     [rbp+57h+ReturnLength], edi
0x14002a5b5  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14002a5b9  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; ReturnLength
0x14002a5be  lea     edx, [r9+0Bh]; TokenInformationClass
0x14002a5c2  call    cs:__imp_GetTokenInformation
0x14002a5c9  nop     dword ptr [rax+rax+00h]
0x14002a5ce  test    eax, eax
0x14002a5d0  jnz     short loc_14002A607
0x14002a5d2  call    cs:__imp_GetLastError
0x14002a5d9  nop     dword ptr [rax+rax+00h]
0x14002a5de  test    eax, eax
0x14002a5e0  jle     short loc_14002A5EA
0x14002a5e2  movzx   eax, ax
0x14002a5e5  or      eax, 80070000h
0x14002a5ea  cmp     eax, 80070520h
0x14002a5ef  mov     ebx, edi
0x14002a5f1  cmovnz  ebx, eax
0x14002a5f4  test    ebx, ebx
0x14002a5f6  jns     short loc_14002A654
0x14002a5f8  mov     [rsp+0C0h+nSubAuthority3], ebx
0x14002a5fc  mov     r9d, 1098h
0x14002a602  jmp     loc_14002A470
0x14002a607  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x14002a60b  lea     r8, [rbp+57h+IsMember]; IsMember
0x14002a60f  mov     rcx, [rbp+57h+TokenInformation]; TokenHandle
0x14002a613  call    cs:__imp_CheckTokenMembership
0x14002a61a  nop     dword ptr [rax+rax+00h]
0x14002a61f  test    eax, eax
0x14002a621  jnz     short loc_14002A64D
0x14002a623  call    cs:__imp_GetLastError
0x14002a62a  nop     dword ptr [rax+rax+00h]
0x14002a62f  mov     ebx, eax
0x14002a631  test    eax, eax
0x14002a633  jle     short loc_14002A63E
0x14002a635  movzx   ebx, ax
0x14002a638  or      ebx, 80070000h
0x14002a63e  mov     [rsp+0C0h+nSubAuthority3], ebx
0x14002a642  mov     r9d, 10A6h
0x14002a648  jmp     loc_14002A470
0x14002a64d  mov     eax, [rbp+57h+IsMember]
0x14002a650  mov     [rbx], eax
0x14002a652  mov     ebx, edi
0x14002a654  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x14002a658  cmp     rcx, rsi
0x14002a65b  jz      short loc_14002A66D
0x14002a65d  call    cs:__imp_CloseHandle
0x14002a664  nop     dword ptr [rax+rax+00h]
0x14002a669  mov     [rbp+57h+TokenHandle], rsi
0x14002a66d  mov     rcx, [rbp+57h+TokenInformation]; hObject
0x14002a671  cmp     rcx, rsi
0x14002a674  jz      short loc_14002A686
0x14002a676  call    cs:__imp_CloseHandle
0x14002a67d  nop     dword ptr [rax+rax+00h]
0x14002a682  mov     [rbp+57h+TokenInformation], rsi
0x14002a686  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x14002a68a  test    rcx, rcx
0x14002a68d  jz      short loc_14002A69B
0x14002a68f  call    cs:__imp_FreeSid
0x14002a696  nop     dword ptr [rax+rax+00h]
0x14002a69b  mov     eax, ebx
0x14002a69d  mov     rcx, [rbp+57h+var_30]
0x14002a6a1  xor     rcx, rsp; StackCookie
0x14002a6a4  call    __security_check_cookie
0x14002a6a9  add     rsp, 0A8h
0x14002a6b0  pop     rdi
0x14002a6b1  pop     rsi
0x14002a6b2  pop     rbx
0x14002a6b3  pop     rbp
0x14002a6b4  retn
```
