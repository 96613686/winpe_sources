# _AcquireLogonSession(int,_LUID *,_LOGON_SESSION * *)

- ea: `0x180009bf0`
- end: `0x180009f00`
- name: `?_AcquireLogonSession@@YAJHPEAU_LUID@@PEAPEAU_LOGON_SESSION@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(int, struct _LUID *, struct _LOGON_SESSION **)`
- caller_count: `23`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007920`
- `0x1800094e0`
- `0x18000bda0`
- `0x18000e990`
- `0x18000f210`
- `0x18000fe60`
- `0x180016a10`
- `0x18001b600`
- `0x180027320`
- `0x180028430`
- `0x180033750`
- `0x1800358c0`
- `0x18003e2f0`
- `0x1800476a0`
- `0x1800479f0`
- `0x180048530`
- `0x18004a870`
- `0x18004bb2c`
- `0x18004d570`
- `0x18004d96c`
- `0x18004dd08`
- `0x1800579a0`
- `0x180058090`

## callees

- `0x180007fc0`
- `0x180009bf0`
- `0x18000a600`
- `0x180042410`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d73`
- `ntdll!RtlReleaseResource` at `0x180009d53`
- `ntdll!RtlReleaseResource` at `0x180009d53`
- `ntdll!NtQueryInformationToken` at `0x180009ce3`
- `ntdll!NtQueryInformationToken` at `0x180009dc2`
- `ntdll!NtQueryInformationToken` at `0x180009ce3`
- `ntdll!NtQueryInformationToken` at `0x180009dc2`
- `ntdll!RtlAcquireResourceShared` at `0x180009c53`
- `ntdll!RtlAcquireResourceShared` at `0x180009c53`

## string_xrefs

- `0x180009cfa`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180009e19`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180009e5f`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180009e93`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180009ec7`: `onecore\ds\ext\cloudap\dll\logonsess.cpp`
- `0x180009d27`: `NtQueryInformationToken(TokenLinkedToken)`
- `0x180009e7a`: `OpenTokenByLogonId`
- `0x180009eae`: `NtQueryInformationToken(TokenStatistics)`

## pseudocode

```c
__int64 __fastcall _AcquireLogonSession(int a1, struct _LUID *a2, struct _LOGON_SESSION **a3)
{
  struct _LOGON_SESSION *i; // rcx
  unsigned int v7; // ebx
  const char *v8; // r9
  char v9; // al
  const char *v10; // rdx
  bool v11; // zf
  struct _LOGON_SESSION *j; // rcx
  const char *v14; // r9
  char v15; // al
  const char *v16; // rdx
  bool v17; // zf
  const char *v18; // r9
  const char *v19; // r9
  const char *v20; // r9
  PULONG ReturnLength; // [rsp+20h] [rbp-98h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-98h]
  ULONG v23; // [rsp+40h] [rbp-78h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-70h] BYREF
  HANDLE TokenInformation; // [rsp+50h] [rbp-68h] BYREF
  _OWORD v26[3]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v27; // [rsp+88h] [rbp-30h]

  v23 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  memset(v26, 0, 32);
  *a3 = 0;
  v26[2] = 0;
  v27 = 0;
  RtlAcquireResourceShared(&g_LogonSessionListLock, 1u);
  for ( i = g_LogonSessionList; ; i = *(struct _LOGON_SESSION **)i )
  {
    if ( i == (struct _LOGON_SESSION *)&g_LogonSessionList )
    {
      *a3 = 0;
      goto LABEL_9;
    }
    if ( *((_DWORD *)i + 7) == a2->LowPart && *((_DWORD *)i + 8) == a2->HighPart )
      break;
  }
  *a3 = i;
  if ( i )
  {
    _InterlockedIncrement((volatile signed __int32 *)i + 4);
    v7 = 0;
    goto LABEL_19;
  }
LABEL_9:
  if ( a1 )
  {
    v7 = ((__int64 (__fastcall *)(struct _LUID *, HANDLE *))g_pLsaFunctionTable->OpenTokenByLogonId)(a2, &TokenHandle);
    if ( v7 )
    {
      v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v18, 1006, "OpenTokenByLogonId", &Class);
    }
    else
    {
      v7 = NtQueryInformationToken(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &v23);
      if ( v7 )
      {
        v8 = "";
        while ( 1 )
        {
          v9 = *(v8 - 1);
          v10 = v8--;
          v11 = v9 == 92;
          if ( v9 == 92 )
            break;
          if ( v8 <= "onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp" )
          {
            v11 = v9 == 92;
            break;
          }
        }
        if ( v11 )
          v8 = v10;
        LODWORD(ReturnLength) = 1014;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          v7,
          v8,
          ReturnLength,
          "NtQueryInformationToken(TokenLinkedToken)",
          &Class);
      }
      else
      {
        v7 = NtQueryInformationToken(TokenInformation, TokenStatistics, v26, 0x38u, &v23);
        if ( v7 )
        {
          v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
          LODWORD(ReturnLengtha) = 1026;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            v7,
            v19,
            ReturnLengtha,
            "NtQueryInformationToken(TokenStatistics)",
            &Class);
        }
        else
        {
          for ( j = g_LogonSessionList; ; j = *(struct _LOGON_SESSION **)j )
          {
            if ( j == (struct _LOGON_SESSION *)&g_LogonSessionList )
            {
              *a3 = 0;
              goto LABEL_32;
            }
            if ( *(_QWORD *)((char *)j + 28) == *((_QWORD *)&v26[0] + 1) )
              break;
          }
          *a3 = j;
          if ( j )
          {
            _InterlockedIncrement((volatile signed __int32 *)j + 4);
            v7 = 0;
            goto LABEL_19;
          }
LABEL_32:
          v7 = -1073741729;
          v14 = "";
          while ( 1 )
          {
            v15 = *(v14 - 1);
            v16 = v14--;
            v17 = v15 == 92;
            if ( v15 == 92 )
              break;
            if ( v14 <= "onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp" )
            {
              v17 = v15 == 92;
              break;
            }
          }
          if ( v17 )
            v14 = v16;
          LODWORD(ReturnLengtha) = 1034;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225567LL, v14, ReturnLengtha, "Logon Session not found", &Class);
        }
      }
    }
  }
  else
  {
    v7 = -1073741729;
    v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonsess.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225567LL, v20, 1040, "Logon Session not found", &Class);
  }
LABEL_19:
  RtlReleaseResource(&g_LogonSessionListLock);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( TokenInformation )
    CloseHandle(TokenInformation);
  return v7;
}

```

## disassembly

```asm
0x180009bf0  mov     r11, rsp
0x180009bf3  mov     [r11+8], rbx
0x180009bf7  mov     [r11+20h], rbp
0x180009bfb  push    rsi
0x180009bfc  push    rdi
0x180009bfd  push    r14
0x180009bff  sub     rsp, 0A0h
0x180009c06  mov     rax, cs:__security_cookie
0x180009c0d  xor     rax, rsp
0x180009c10  mov     [rsp+0B8h+var_28], rax
0x180009c18  xor     r14d, r14d
0x180009c1b  xorps   xmm0, xmm0
0x180009c1e  mov     rbx, rdx
0x180009c21  mov     [r11-78h], r14d
0x180009c25  mov     esi, ecx
0x180009c27  mov     [r11-70h], r14
0x180009c2b  xor     eax, eax
0x180009c2d  mov     [r11-68h], r14
0x180009c31  movups  [rsp+0B8h+var_60], xmm0
0x180009c36  mov     dl, 1; Wait
0x180009c38  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x180009c3f  movups  [rsp+0B8h+var_50], xmm0
0x180009c44  mov     rdi, r8
0x180009c47  mov     [r8], r14
0x180009c4a  movups  [rsp+0B8h+var_40], xmm0
0x180009c4f  mov     [r11-30h], rax
0x180009c53  call    cs:__imp_RtlAcquireResourceShared
0x180009c59  mov     rcx, cs:?g_LogonSessionList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_LogonSessionList
0x180009c60  lea     rbp, ?g_LogonSessionList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_LogonSessionList
0x180009c67  cmp     rcx, rbp
0x180009c6a  jz      short loc_180009C94
0x180009c6c  mov     eax, [rbx]
0x180009c6e  cmp     [rcx+1Ch], eax
0x180009c71  jz      short loc_180009C78
0x180009c73  mov     rcx, [rcx]
0x180009c76  jmp     short loc_180009C67
0x180009c78  mov     eax, [rbx+4]
0x180009c7b  cmp     [rcx+20h], eax
0x180009c7e  jnz     short loc_180009C73
0x180009c80  mov     [rdi], rcx
0x180009c83  test    rcx, rcx
0x180009c86  jz      short loc_180009C97
0x180009c88  lock inc dword ptr [rcx+10h]
0x180009c8c  mov     ebx, r14d
0x180009c8f  jmp     loc_180009D4C
0x180009c94  mov     [rdi], r14
0x180009c97  test    esi, esi
0x180009c99  jz      loc_180009EC7
0x180009c9f  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180009ca6  lea     rdx, [rsp+0B8h+TokenHandle]
0x180009cab  mov     rcx, rbx
0x180009cae  mov     rax, [rax+170h]
0x180009cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cba  mov     ebx, eax
0x180009cbc  test    eax, eax
0x180009cbe  jnz     loc_180009E5F
0x180009cc4  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x180009cc9  lea     rax, [rsp+0B8h+var_78]
0x180009cce  mov     r9d, 8; TokenInformationLength
0x180009cd4  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180009cd9  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180009cde  mov     edx, 13h; TokenInformationClass
0x180009ce3  call    cs:__imp_NtQueryInformationToken
0x180009ce9  mov     ebx, eax
0x180009ceb  test    eax, eax
0x180009ced  jz      loc_180009DA3
0x180009cf3  lea     r9, aOnecoreDsExtCl_7+28h; ""
0x180009cfa  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180009d01  movzx   eax, byte ptr [r9-1]
0x180009d06  mov     rdx, r9
0x180009d09  dec     r9
0x180009d0c  cmp     al, 5Ch ; '\'
0x180009d0e  jz      short loc_180009D17
0x180009d10  cmp     r9, rcx
0x180009d13  ja      short loc_180009D01
0x180009d15  cmp     al, 5Ch ; '\'
0x180009d17  lea     rax, Class
0x180009d1e  cmovz   r9, rdx
0x180009d22  mov     [rsp+0B8h+var_88], rax
0x180009d27  lea     rax, aNtqueryinforma_3; "NtQueryInformationToken(TokenLinkedToke"...
0x180009d2e  mov     [rsp+0B8h+var_90], rax
0x180009d33  mov     dword ptr [rsp+0B8h+ReturnLength], 3F6h
0x180009d3b  mov     r8d, ebx
0x180009d3e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180009d45  xor     ecx, ecx
0x180009d47  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180009d4c  lea     rcx, ?g_LogonSessionListLock@@3U_RTL_RESOURCE@@A; Resource
0x180009d53  call    cs:__imp_RtlReleaseResource
0x180009d59  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x180009d5e  test    rcx, rcx
0x180009d61  jz      short loc_180009D69
0x180009d63  call    cs:__imp_CloseHandle
0x180009d69  mov     rcx, [rsp+0B8h+TokenInformation]; hObject
0x180009d6e  test    rcx, rcx
0x180009d71  jz      short loc_180009D79
0x180009d73  call    cs:__imp_CloseHandle
0x180009d79  mov     eax, ebx
0x180009d7b  mov     rcx, [rsp+0B8h+var_28]
0x180009d83  xor     rcx, rsp; StackCookie
0x180009d86  call    __security_check_cookie
0x180009d8b  lea     r11, [rsp+0B8h+var_18]
0x180009d93  mov     rbx, [r11+20h]
0x180009d97  mov     rbp, [r11+38h]
0x180009d9b  mov     rsp, r11
0x180009d9e  pop     r14
0x180009da0  pop     rdi
0x180009da1  pop     rsi
0x180009da2  retn
0x180009da3  mov     rcx, [rsp+0B8h+TokenInformation]; TokenHandle
0x180009da8  lea     rax, [rsp+0B8h+var_78]
0x180009dad  mov     r9d, 38h ; '8'; TokenInformationLength
0x180009db3  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180009db8  lea     r8, [rsp+0B8h+var_60]; TokenInformation
0x180009dbd  mov     edx, 0Ah; TokenInformationClass
0x180009dc2  call    cs:__imp_NtQueryInformationToken
0x180009dc8  mov     ebx, eax
0x180009dca  test    eax, eax
0x180009dcc  jnz     loc_180009E93
0x180009dd2  mov     rcx, cs:?g_LogonSessionList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_LogonSessionList
0x180009dd9  mov     edx, dword ptr [rsp+0B8h+var_60+0Ch]
0x180009ddd  mov     rax, qword ptr [rsp+0B8h+var_60+8]
0x180009de2  cmp     rcx, rbp
0x180009de5  jz      short loc_180009E0A
0x180009de7  cmp     [rcx+1Ch], eax
0x180009dea  jz      short loc_180009DF1
0x180009dec  mov     rcx, [rcx]
0x180009def  jmp     short loc_180009DE2
0x180009df1  cmp     [rcx+20h], edx
0x180009df4  jnz     short loc_180009DEC
0x180009df6  mov     [rdi], rcx
0x180009df9  test    rcx, rcx
0x180009dfc  jz      short loc_180009E0D
0x180009dfe  lock inc dword ptr [rcx+10h]
0x180009e02  mov     ebx, r14d
0x180009e05  jmp     loc_180009D4C
0x180009e0a  mov     [rdi], r14
0x180009e0d  mov     ebx, 0C000005Fh
0x180009e12  lea     r9, aOnecoreDsExtCl_7+28h; ""
0x180009e19  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180009e20  movzx   eax, byte ptr [r9-1]
0x180009e25  mov     rdx, r9
0x180009e28  dec     r9
0x180009e2b  cmp     al, 5Ch ; '\'
0x180009e2d  jz      short loc_180009E36
0x180009e2f  cmp     r9, rcx
0x180009e32  ja      short loc_180009E20
0x180009e34  cmp     al, 5Ch ; '\'
0x180009e36  lea     rax, Class
0x180009e3d  cmovz   r9, rdx
0x180009e41  mov     [rsp+0B8h+var_88], rax
0x180009e46  lea     rax, aLogonSessionNo; "Logon Session not found"
0x180009e4d  mov     [rsp+0B8h+var_90], rax
0x180009e52  mov     dword ptr [rsp+0B8h+ReturnLength], 40Ah
0x180009e5a  jmp     loc_180009D3B
0x180009e5f  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180009e66  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009e6b  mov     r9, rax
0x180009e6e  lea     rax, Class
0x180009e75  mov     [rsp+0B8h+var_88], rax
0x180009e7a  lea     rax, aOpentokenbylog; "OpenTokenByLogonId"
0x180009e81  mov     [rsp+0B8h+var_90], rax
0x180009e86  mov     dword ptr [rsp+0B8h+ReturnLength], 3EEh
0x180009e8e  jmp     loc_180009D3B
0x180009e93  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180009e9a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009e9f  mov     r9, rax
0x180009ea2  lea     rax, Class
0x180009ea9  mov     [rsp+0B8h+var_88], rax
0x180009eae  lea     rax, aNtqueryinforma_0; "NtQueryInformationToken(TokenStatistics"...
0x180009eb5  mov     [rsp+0B8h+var_90], rax
0x180009eba  mov     dword ptr [rsp+0B8h+ReturnLength], 402h
0x180009ec2  jmp     loc_180009D3B
0x180009ec7  lea     rcx, aOnecoreDsExtCl_7; "onecore\\ds\\ext\\cloudap\\dll\\logonse"...
0x180009ece  mov     ebx, 0C000005Fh
0x180009ed3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009ed8  mov     r9, rax
0x180009edb  lea     rax, Class
0x180009ee2  mov     [rsp+0B8h+var_88], rax
0x180009ee7  lea     rax, aLogonSessionNo; "Logon Session not found"
0x180009eee  mov     [rsp+0B8h+var_90], rax
0x180009ef3  mov     dword ptr [rsp+0B8h+ReturnLength], 410h
0x180009efb  jmp     loc_180009D3B
```
