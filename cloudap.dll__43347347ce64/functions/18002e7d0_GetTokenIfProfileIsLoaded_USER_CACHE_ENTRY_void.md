# GetTokenIfProfileIsLoaded(_USER_CACHE_ENTRY *,void * *)

- ea: `0x18002e7d0`
- end: `0x18002ea62`
- name: `?GetTokenIfProfileIsLoaded@@YAJPEAU_USER_CACHE_ENTRY@@PEAPEAX@Z`
- size: `658`
- prototype: `__int64 __fastcall(struct _USER_CACHE_ENTRY *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180011960`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002e7d0`
- `0x180042410`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e862`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e9bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e9ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ea1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e862`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e9bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e9ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ea1f`
- `ntdll!NtQueryInformationToken` at `0x18002e8c8`
- `ntdll!NtQueryInformationToken` at `0x18002e907`
- `ntdll!NtQueryInformationToken` at `0x18002e8c8`
- `ntdll!NtQueryInformationToken` at `0x18002e907`
- `LSASRV!LsaIWasLogonNotifiedOfProfileLoad` at `0x18002e8d8`
- `LSASRV!LsaIWasLogonNotifiedOfProfileLoad` at `0x18002e923`
- `LSASRV!LsaIWasLogonNotifiedOfProfileLoad` at `0x18002e8d8`
- `LSASRV!LsaIWasLogonNotifiedOfProfileLoad` at `0x18002e923`

## string_xrefs

- `0x18002e95b`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18002ea2e`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18002ea49`: `NtQueryInformationToken(TokenStatistics)`

## pseudocode

```c
__int64 __fastcall GetTokenIfProfileIsLoaded(struct _USER_CACHE_ENTRY *a1, void **a2)
{
  HANDLE v2; // rax
  HANDLE v5; // rcx
  unsigned int i; // edi
  __int64 v7; // rsi
  char v8; // al
  unsigned int v9; // esi
  const char *v10; // r9
  char v11; // al
  const char *v12; // rcx
  bool v13; // zf
  const char *v15; // r9
  PULONG ReturnLength; // [rsp+28h] [rbp-49h]
  HANDLE TokenInformation; // [rsp+48h] [rbp-29h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp-21h] BYREF
  ULONG v19; // [rsp+58h] [rbp-19h] BYREF
  __int64 v20; // [rsp+60h] [rbp-11h] BYREF
  _OWORD v21[3]; // [rsp+68h] [rbp-9h] BYREF
  __int64 v22; // [rsp+98h] [rbp+27h]

  v2 = 0;
  v22 = 0;
  v5 = 0;
  *a2 = 0;
  TokenInformation = 0;
  v20 = 0;
  v19 = 0;
  memset(v21, 0, sizeof(v21));
  TokenHandle = 0;
  if ( !*((_DWORD *)a1 + 82) || !*((_QWORD *)a1 + 42) )
  {
    v9 = -1073741729;
    v10 = "";
    do
    {
      v11 = *(v10 - 1);
      v12 = v10--;
      v13 = v11 == 92;
      if ( v11 == 92 )
        goto LABEL_21;
    }
    while ( v10 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
    v13 = v11 == 92;
LABEL_21:
    if ( v13 )
      v10 = v12;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225567LL, v10, 6775, "No LogonIds found", &Class);
    goto LABEL_24;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)a1 + 82) )
    {
      v9 = 0;
      goto LABEL_26;
    }
    if ( v2 )
    {
      CloseHandle(v2);
      v5 = TokenInformation;
      TokenHandle = 0;
    }
    if ( v5 )
    {
      CloseHandle(v5);
      TokenInformation = 0;
    }
    v7 = 8LL * i;
    if ( ((int (__fastcall *)(__int64, HANDLE *))g_pLsaFunctionTable->OpenTokenByLogonId)(
           v7 + *((_QWORD *)a1 + 42),
           &TokenHandle) < 0 )
      goto LABEL_15;
    NtQueryInformationToken(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &v19);
    v8 = LsaIWasLogonNotifiedOfProfileLoad(v7 + *((_QWORD *)a1 + 42));
    v5 = TokenInformation;
    if ( v8 == 1 )
    {
      v9 = 0;
      *a2 = TokenHandle;
      TokenHandle = 0;
      goto LABEL_28;
    }
    if ( TokenInformation )
      break;
LABEL_16:
    v2 = TokenHandle;
  }
  v9 = NtQueryInformationToken(TokenInformation, TokenStatistics, v21, 0x38u, &v19);
  if ( !v9 )
  {
    v20 = *((_QWORD *)&v21[0] + 1);
    if ( (unsigned __int8)LsaIWasLogonNotifiedOfProfileLoad(&v20) == 1 )
    {
      v5 = 0;
      *a2 = TokenInformation;
      v9 = 0;
      TokenInformation = 0;
      goto LABEL_25;
    }
LABEL_15:
    v5 = TokenInformation;
    goto LABEL_16;
  }
  v15 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  LODWORD(ReturnLength) = 6833;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v15, ReturnLength, "NtQueryInformationToken(TokenStatistics)", &Class);
LABEL_24:
  v5 = TokenInformation;
LABEL_25:
  v2 = TokenHandle;
LABEL_26:
  if ( v2 )
  {
    CloseHandle(v2);
    v5 = TokenInformation;
  }
LABEL_28:
  if ( v5 )
    CloseHandle(v5);
  return v9;
}

```

## disassembly

```asm
0x18002e7d0  mov     r11, rsp
0x18002e7d3  push    rbp
0x18002e7d4  push    rsi
0x18002e7d5  lea     rbp, [r11-5Fh]
0x18002e7d9  sub     rsp, 0B8h
0x18002e7e0  mov     rax, cs:__security_cookie
0x18002e7e7  xor     rax, rsp
0x18002e7ea  mov     [rbp+57h+var_28], rax
0x18002e7ee  mov     [r11+18h], rbx
0x18002e7f2  xor     eax, eax
0x18002e7f4  xorps   xmm0, xmm0
0x18002e7f7  mov     [r11-18h], rdi
0x18002e7fb  mov     [r11-20h], r14
0x18002e7ff  mov     rbx, rcx
0x18002e802  mov     [r11-28h], r15
0x18002e806  mov     r14, rdx
0x18002e809  xor     r15d, r15d
0x18002e80c  mov     [rbp+57h+var_30], rax
0x18002e810  mov     ecx, r15d
0x18002e813  mov     [rdx], r15
0x18002e816  mov     [rbp+57h+TokenInformation], rcx
0x18002e81a  mov     [rbp+57h+var_68], r15
0x18002e81e  mov     [rbp+57h+var_70], r15d
0x18002e822  movups  [rbp+57h+var_60], xmm0
0x18002e826  mov     [rbp+57h+TokenHandle], rax
0x18002e82a  movups  [rbp+57h+var_50], xmm0
0x18002e82e  movups  [rbp+57h+var_40], xmm0
0x18002e832  cmp     [rbx+148h], eax
0x18002e838  jz      loc_18002E94F
0x18002e83e  cmp     [rbx+150h], rax
0x18002e845  jz      loc_18002E94F
0x18002e84b  mov     edi, r15d
0x18002e84e  cmp     edi, [rbx+148h]
0x18002e854  jnb     loc_18002EA0A
0x18002e85a  test    rax, rax
0x18002e85d  jz      short loc_18002E870
0x18002e85f  mov     rcx, rax; hObject
0x18002e862  call    cs:__imp_CloseHandle
0x18002e868  mov     rcx, [rbp+57h+TokenInformation]; hObject
0x18002e86c  mov     [rbp+57h+TokenHandle], r15
0x18002e870  test    rcx, rcx
0x18002e873  jnz     loc_18002EA1F
0x18002e879  mov     rcx, [rbx+150h]
0x18002e880  lea     rdx, [rbp+57h+TokenHandle]
0x18002e884  mov     eax, edi
0x18002e886  lea     rsi, ds:0[rax*8]
0x18002e88e  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002e895  add     rcx, rsi
0x18002e898  mov     rax, [rax+170h]
0x18002e89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8a4  test    eax, eax
0x18002e8a6  js      loc_18002E940
0x18002e8ac  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002e8b0  lea     rax, [rbp+57h+var_70]
0x18002e8b4  mov     r9d, 8; TokenInformationLength
0x18002e8ba  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18002e8bf  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002e8c3  mov     edx, 13h; TokenInformationClass
0x18002e8c8  call    cs:__imp_NtQueryInformationToken
0x18002e8ce  mov     rcx, [rbx+150h]
0x18002e8d5  add     rcx, rsi
0x18002e8d8  call    cs:__imp_LsaIWasLogonNotifiedOfProfileLoad
0x18002e8de  mov     rcx, [rbp+57h+TokenInformation]; TokenHandle
0x18002e8e2  cmp     al, 1
0x18002e8e4  jz      loc_18002EA0F
0x18002e8ea  test    rcx, rcx
0x18002e8ed  jz      short loc_18002E944
0x18002e8ef  lea     rax, [rbp+57h+var_70]
0x18002e8f3  mov     r9d, 38h ; '8'; TokenInformationLength
0x18002e8f9  lea     r8, [rbp+57h+var_60]; TokenInformation
0x18002e8fd  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18002e902  mov     edx, 0Ah; TokenInformationClass
0x18002e907  call    cs:__imp_NtQueryInformationToken
0x18002e90d  mov     esi, eax
0x18002e90f  test    eax, eax
0x18002e911  jnz     loc_18002EA2E
0x18002e917  mov     rax, qword ptr [rbp+57h+var_60+8]
0x18002e91b  lea     rcx, [rbp+57h+var_68]
0x18002e91f  mov     [rbp+57h+var_68], rax
0x18002e923  call    cs:__imp_LsaIWasLogonNotifiedOfProfileLoad
0x18002e929  cmp     al, 1
0x18002e92b  jnz     short loc_18002E940
0x18002e92d  mov     rax, [rbp+57h+TokenInformation]
0x18002e931  mov     rcx, r15
0x18002e934  mov     [r14], rax
0x18002e937  mov     esi, r15d
0x18002e93a  mov     [rbp+57h+TokenInformation], rcx
0x18002e93e  jmp     short loc_18002E9B1
0x18002e940  mov     rcx, [rbp+57h+TokenInformation]
0x18002e944  mov     rax, [rbp+57h+TokenHandle]
0x18002e948  inc     edi
0x18002e94a  jmp     loc_18002E84E
0x18002e94f  mov     esi, 0C000005Fh
0x18002e954  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18002e95b  lea     rdx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002e962  movzx   eax, byte ptr [r9-1]
0x18002e967  mov     rcx, r9
0x18002e96a  dec     r9
0x18002e96d  cmp     al, 5Ch ; '\'
0x18002e96f  jz      short loc_18002E978
0x18002e971  cmp     r9, rdx
0x18002e974  ja      short loc_18002E962
0x18002e976  cmp     al, 5Ch ; '\'
0x18002e978  lea     rax, Class
0x18002e97f  cmovz   r9, rcx
0x18002e983  mov     [rsp+30h], rax
0x18002e988  lea     rax, aNoLogonidsFoun; "No LogonIds found"
0x18002e98f  mov     [rsp+0C0h+var_98], rax
0x18002e994  mov     dword ptr [rsp+0C0h+ReturnLength], 1A77h
0x18002e99c  mov     r8d, esi
0x18002e99f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002e9a6  xor     ecx, ecx
0x18002e9a8  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002e9ad  mov     rcx, [rbp+57h+TokenInformation]
0x18002e9b1  mov     rax, [rbp+57h+TokenHandle]
0x18002e9b5  test    rax, rax
0x18002e9b8  jz      short loc_18002E9C7
0x18002e9ba  mov     rcx, rax; hObject
0x18002e9bd  call    cs:__imp_CloseHandle
0x18002e9c3  mov     rcx, [rbp+57h+TokenInformation]; hObject
0x18002e9c7  mov     r15, [rsp+0C0h+var_20]
0x18002e9cf  mov     r14, [rsp+0C0h+var_18]
0x18002e9d7  mov     rdi, [rsp+0B0h]
0x18002e9df  mov     rbx, [rsp+0C0h+arg_10]
0x18002e9e7  test    rcx, rcx
0x18002e9ea  jz      short loc_18002E9F2
0x18002e9ec  call    cs:__imp_CloseHandle
0x18002e9f2  mov     eax, esi
0x18002e9f4  mov     rcx, [rbp+57h+var_28]
0x18002e9f8  xor     rcx, rsp; StackCookie
0x18002e9fb  call    __security_check_cookie
0x18002ea00  add     rsp, 0B8h
0x18002ea07  pop     rsi
0x18002ea08  pop     rbp
0x18002ea09  retn
0x18002ea0a  mov     esi, r15d
0x18002ea0d  jmp     short loc_18002E9B5
0x18002ea0f  mov     rax, [rbp+57h+TokenHandle]
0x18002ea13  mov     esi, r15d
0x18002ea16  mov     [r14], rax
0x18002ea19  mov     [rbp+57h+TokenHandle], r15
0x18002ea1d  jmp     short loc_18002E9C7
0x18002ea1f  call    cs:__imp_CloseHandle
0x18002ea25  mov     [rbp+57h+TokenInformation], r15
0x18002ea29  jmp     loc_18002E879
0x18002ea2e  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002ea35  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002ea3a  mov     r9, rax
0x18002ea3d  lea     rax, Class
0x18002ea44  mov     [rsp+30h], rax
0x18002ea49  lea     rax, aNtqueryinforma_0; "NtQueryInformationToken(TokenStatistics"...
0x18002ea50  mov     [rsp+0C0h+var_98], rax
0x18002ea55  mov     dword ptr [rsp+0C0h+ReturnLength], 1AB1h
0x18002ea5d  jmp     loc_18002E99C
```
