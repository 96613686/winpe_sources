# CheckGPOAccess(ldap *,void *,ldapmsg *,ushort *,ulong,void * *,ulong *,int *,void *)

- ea: `0x18003d000`
- end: `0x18003d56e`
- name: `?CheckGPOAccess@@YAHPEAUldap@@PEAXPEAUldapmsg@@PEAGKPEAPEAXPEAKPEAH1@Z`
- size: `1390`
- prototype: `__int64 __fastcall(LDAP *ExternalHandle, void *, struct ldapmsg *, unsigned __int16 *, unsigned int, void **, unsigned int *, int *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a810`

## callees

- `0x18003d000`
- `0x180075ec0`
- `0x18007d320`
- `0x1800a9e10`
- `0x1800bb958`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d545`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d0d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d25d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d0d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d1fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d25d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d1e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d1e9`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18003d446`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18003d446`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003d1ac`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003d522`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003d1ac`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18003d522`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18003d532`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18003d532`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003d0ec`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18003d0ec`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18003d1c2`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18003d1c2`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003d53c`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18003d53c`

## string_xrefs

- `0x18003d11f`: `CheckGPOAccess:  Object can not be accessed.`
- `0x18003d143`: `CheckGPOAccess:  Object can not be accessed.`
- `0x18003d173`: `CheckGPOAccess:  ldap_get_values failed with 0x%x`
- `0x18003d198`: `CheckGPOAccess:  ldap_get_values failed with 0x%x`
- `0x18003d4e5`: `CheckGPOAccess:  ldap_get_values_len failed with 0x%x`
- `0x18003d50e`: `CheckGPOAccess:  ldap_get_values_len failed with 0x%x`
- `0x18003d227`: `CheckGPOAccess:  Failed to allocate memory for SD with  %d`
- `0x18003d263`: `CheckGPOAccess:  Failed to allocate memory for SD with  %d`
- `0x18003d340`: `CheckGPOAccess:  RsopAccessCheckByType failed with  0x%08X`
- `0x18003d369`: `CheckGPOAccess:  RsopAccessCheckByType failed with  0x%08X`
- `0x18003d3b7`: `CheckGPOAccess:  AccessMask 0x%x, Looking for 0x%x`
- `0x18003d3e7`: `CheckGPOAccess:  AccessMask 0x%x, Looking for 0x%x`
- `0x18003d47b`: `CheckGPOAccess:  AccessCheckByType failed with  %d`
- `0x18003d4a7`: `CheckGPOAccess:  AccessCheckByType failed with  %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CheckGPOAccess(
        LDAP *ExternalHandle,
        void *a2,
        struct ldapmsg *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7,
        int *a8,
        void *a9)
{
  unsigned int v12; // r15d
  DWORD LastError; // ebx
  struct berval **values_lenW; // rax
  struct berval **v15; // rsi
  struct berval *v16; // rax
  HLOCAL v17; // rax
  void (*v18)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v19; // eax
  const wchar_t *v20; // rdx
  DWORD v21; // eax
  int v22; // eax
  __int64 v23; // r8
  DWORD v24; // eax
  WINBOOL AccessStatus; // [rsp+60h] [rbp-A0h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD v28; // [rsp+68h] [rbp-98h]
  DWORD PrivilegeSetLength; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int *v30; // [rsp+70h] [rbp-90h]
  void *v31; // [rsp+78h] [rbp-88h]
  HANDLE ClientToken; // [rsp+80h] [rbp-80h]
  PWCHAR *vals; // [rsp+88h] [rbp-78h]
  struct _OBJECT_TYPE_LIST ObjectTypeList; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+A0h] [rbp-60h]
  _DWORD *v36; // [rsp+A8h] [rbp-58h]
  _DWORD v37[4]; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v38[4]; // [rsp+C0h] [rbp-40h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+D0h] [rbp-30h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+E0h] [rbp-20h] BYREF

  ClientToken = a2;
  v30 = a7;
  v31 = a9;
  v12 = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  PrivilegeSetLength = 20;
  GrantedAccess = 0;
  AccessStatus = 1;
  v37[0] = 833811264;
  v37[1] = 298975597;
  v37[2] = -1073717356;
  v37[3] = -108742321;
  v38[0] = -307430001;
  v38[1] = 298975155;
  v38[2] = -1610605132;
  v38[3] = 972646601;
  GenericMapping.GenericRead = 131220;
  GenericMapping.GenericWrite = 131112;
  GenericMapping.GenericExecute = 131076;
  GenericMapping.GenericAll = 983551;
  LastError = GetLastError();
  v28 = LastError;
  *a8 = 0;
  vals = ldap_get_valuesW(ExternalHandle, a3, a4);
  if ( !vals )
  {
    if ( ExternalHandle->ld_errno == 16 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CheckGPOAccess:  Object can not be accessed.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CheckGPOAccess:  Object can not be accessed.");
        }
      }
      v12 = 1;
    }
    else
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CheckGPOAccess:  ldap_get_values failed with 0x%x");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CheckGPOAccess:  ldap_get_values failed with 0x%x");
        }
      }
      LastError = LdapMapErrorToWin32(ExternalHandle->ld_errno);
    }
    goto LABEL_68;
  }
  values_lenW = ldap_get_values_lenW(ExternalHandle, a3, a4);
  v15 = values_lenW;
  if ( !values_lenW || (v16 = *values_lenW) == 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CheckGPOAccess:  ldap_get_values_len failed with 0x%x", ExternalHandle->ld_errno);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CheckGPOAccess:  ldap_get_values_len failed with 0x%x", ExternalHandle->ld_errno);
      }
    }
    LastError = LdapMapErrorToWin32(ExternalHandle->ld_errno);
    goto LABEL_65;
  }
  v17 = LocalAlloc(0x40u, v16->bv_len);
  *a6 = v17;
  if ( !v17 )
  {
    LastError = GetLastError();
    v28 = LastError;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v18 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v21 = GetLastError();
          RedirectDebugMsg(2u, L"CheckGPOAccess:  Failed to allocate memory for SD with  %d", v21);
        }
        goto LABEL_65;
      }
      v19 = GetLastError();
      v20 = L"CheckGPOAccess:  Failed to allocate memory for SD with  %d";
      goto LABEL_23;
    }
    goto LABEL_65;
  }
  memcpy_0(v17, (*v15)->bv_val, (*v15)->bv_len);
  *v30 = (*v15)->bv_len;
  *(_DWORD *)&ObjectTypeList.Level = 0;
  ObjectTypeList.ObjectType = (GUID *)v37;
  v35 = 1;
  v36 = v38;
  if ( v31 )
  {
    v22 = RsopAccessCheckByTypeInternal(
            *a6,
            &ObjectTypeList,
            2u,
            &GenericMapping,
            (int)&PrivilegeSet,
            (int)&PrivilegeSetLength,
            (bool)&GrantedAccess,
            (__int64)&AccessStatus);
    if ( v22 < 0 )
    {
      LastError = (unsigned __int16)v22;
      v28 = (unsigned __int16)v22;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CheckGPOAccess:  RsopAccessCheckByType failed with  0x%08X", (unsigned int)v22);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CheckGPOAccess:  RsopAccessCheckByType failed with  0x%08X", (unsigned int)v22);
        }
      }
      goto LABEL_65;
    }
    v23 = GrantedAccess;
    if ( AccessStatus && (GrantedAccess & 0x20114) == 0x20114 )
      *a8 = 1;
    if ( !*a8 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CheckGPOAccess:  AccessMask 0x%x, Looking for 0x%x", v23, 131348);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CheckGPOAccess:  AccessMask 0x%x, Looking for 0x%x", v23, 131348);
      }
    }
    goto LABEL_57;
  }
  if ( AccessCheckByType(
         *a6,
         0,
         ClientToken,
         0x2000000u,
         &ObjectTypeList,
         2u,
         &GenericMapping,
         &PrivilegeSet,
         &PrivilegeSetLength,
         &GrantedAccess,
         &AccessStatus) )
  {
    if ( AccessStatus && (GrantedAccess & 0x100) != 0 )
      *a8 = 1;
LABEL_57:
    v12 = 1;
    goto LABEL_65;
  }
  LastError = GetLastError();
  v28 = LastError;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v18 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v24 = GetLastError();
        RedirectDebugMsg(2u, L"CheckGPOAccess:  AccessCheckByType failed with  %d", v24);
      }
      goto LABEL_65;
    }
    v19 = GetLastError();
    v20 = L"CheckGPOAccess:  AccessCheckByType failed with  %d";
LABEL_23:
    v18(2u, v20, v19);
  }
LABEL_65:
  if ( v15 )
    ldap_value_free_len(v15);
  ldap_value_freeW(vals);
LABEL_68:
  SetLastError(LastError);
  return v12;
}

```

## disassembly

```asm
0x18003d000  push    rbp
0x18003d002  push    rbx
0x18003d003  push    rsi
0x18003d004  push    rdi
0x18003d005  push    r12
0x18003d007  push    r13
0x18003d009  push    r14
0x18003d00b  push    r15
0x18003d00d  lea     rbp, [rsp-8]
0x18003d012  sub     rsp, 108h
0x18003d019  mov     rax, cs:__security_cookie
0x18003d020  xor     rax, rsp
0x18003d023  mov     [rbp+40h+var_48], rax
0x18003d027  mov     r13, r9
0x18003d02a  mov     rsi, r8
0x18003d02d  mov     [rbp+40h+ClientToken], rdx
0x18003d031  mov     rdi, rcx
0x18003d034  mov     r12, [rbp+40h+arg_28]
0x18003d038  mov     rax, [rbp+40h+arg_30]
0x18003d03f  mov     [rsp+140h+var_D0], rax
0x18003d044  mov     r14, [rbp+40h+arg_38]
0x18003d04b  mov     rax, [rbp+40h+arg_40]
0x18003d052  mov     [rsp+140h+var_C8], rax
0x18003d057  xor     ecx, ecx
0x18003d059  mov     r15d, ecx
0x18003d05c  xorps   xmm0, xmm0
0x18003d05f  xor     eax, eax
0x18003d061  movups  xmmword ptr [rbp+40h+var_60.PrivilegeCount], xmm0
0x18003d065  mov     [rbp+40h+var_60.Privilege.Attributes], eax
0x18003d068  mov     [rsp+140h+var_D4], 14h
0x18003d070  mov     [rsp+140h+var_DC], ecx
0x18003d074  mov     [rsp+140h+var_E0], 1
0x18003d07c  mov     [rbp+40h+var_90], 31B2F340h
0x18003d083  mov     [rbp+40h+var_8C], 11D2016Dh
0x18003d08a  mov     [rbp+40h+var_88], 0C0005F94h
0x18003d091  mov     [rbp+40h+var_84], 0F984B94Fh
0x18003d098  mov     [rbp+40h+var_80], 0EDACFD8Fh
0x18003d09f  mov     [rbp+40h+var_7C], 11D1FFB3h
0x18003d0a6  mov     [rbp+40h+var_78], 0A0001DB4h
0x18003d0ad  mov     [rbp+40h+var_74], 39F968C9h
0x18003d0b4  mov     [rbp+40h+var_70.GenericRead], 20094h
0x18003d0bb  mov     [rbp+40h+var_70.GenericWrite], 20028h
0x18003d0c2  mov     [rbp+40h+var_70.GenericExecute], 20004h
0x18003d0c9  mov     [rbp+40h+var_70.GenericAll], 0F01FFh
0x18003d0d0  call    cs:__imp_GetLastError
0x18003d0d6  mov     ebx, eax
0x18003d0d8  mov     [rsp+140h+var_D8], eax
0x18003d0dc  mov     dword ptr [r14], 0
0x18003d0e3  mov     r8, r13; attr
0x18003d0e6  mov     rdx, rsi; entry
0x18003d0e9  mov     rcx, rdi; ld
0x18003d0ec  call    cs:__imp_ldap_get_valuesW
0x18003d0f2  mov     [rbp+40h+vals], rax
0x18003d0f6  xor     ecx, ecx
0x18003d0f8  test    rax, rax
0x18003d0fb  jnz     loc_18003D1B9
0x18003d101  mov     r8d, [rdi+74h]
0x18003d105  cmp     r8d, 10h
0x18003d109  jnz     short loc_18003D15F
0x18003d10b  cmp     cs:?g_dwDebugLevel@@3KA, ecx; ulong g_dwDebugLevel
0x18003d111  jz      short loc_18003D154
0x18003d113  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003d11a  test    rax, rax
0x18003d11d  jz      short loc_18003D131
0x18003d11f  lea     rdx, aCheckgpoaccess_0; "CheckGPOAccess:  Object can not be acce"...
0x18003d126  lea     ecx, [r8-0Ch]
0x18003d12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d12f  jmp     short loc_18003D154
0x18003d131  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rcx; void * g_lpDebugMsgContextInstance
0x18003d138  jz      short loc_18003D154
0x18003d13a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rcx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003d141  jz      short loc_18003D154
0x18003d143  lea     rdx, aCheckgpoaccess_0; "CheckGPOAccess:  Object can not be acce"...
0x18003d14a  mov     ecx, 4; unsigned int
0x18003d14f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003d154  mov     r15d, 1
0x18003d15a  jmp     loc_18003D543
0x18003d15f  cmp     cs:?g_dwDebugLevel@@3KA, ecx; ulong g_dwDebugLevel
0x18003d165  jz      short loc_18003D1A9
0x18003d167  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003d16e  test    rax, rax
0x18003d171  jz      short loc_18003D186
0x18003d173  lea     rdx, aCheckgpoaccess_3; "CheckGPOAccess:  ldap_get_values failed"...
0x18003d17a  mov     ecx, 2
0x18003d17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d184  jmp     short loc_18003D1A9
0x18003d186  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rcx; void * g_lpDebugMsgContextInstance
0x18003d18d  jz      short loc_18003D1A9
0x18003d18f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rcx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003d196  jz      short loc_18003D1A9
0x18003d198  lea     rdx, aCheckgpoaccess_3; "CheckGPOAccess:  ldap_get_values failed"...
0x18003d19f  mov     ecx, 2; unsigned int
0x18003d1a4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003d1a9  mov     ecx, [rdi+74h]; LdapError
0x18003d1ac  call    cs:__imp_LdapMapErrorToWin32
0x18003d1b2  mov     ebx, eax
0x18003d1b4  jmp     loc_18003D543
0x18003d1b9  mov     r8, r13; attr
0x18003d1bc  mov     rdx, rsi; Message
0x18003d1bf  mov     rcx, rdi; ExternalHandle
0x18003d1c2  call    cs:__imp_ldap_get_values_lenW
0x18003d1c8  mov     rsi, rax
0x18003d1cb  xor     r13d, r13d
0x18003d1ce  test    rax, rax
0x18003d1d1  jz      loc_18003D4CC
0x18003d1d7  mov     rax, [rax]
0x18003d1da  test    rax, rax
0x18003d1dd  jz      loc_18003D4CC
0x18003d1e3  mov     edx, [rax]; uBytes
0x18003d1e5  lea     ecx, [r13+40h]; uFlags
0x18003d1e9  call    cs:__imp_LocalAlloc
0x18003d1ef  mov     [r12], rax
0x18003d1f3  test    rax, rax
0x18003d1f6  jnz     loc_18003D27C
0x18003d1fc  call    cs:__imp_GetLastError
0x18003d202  mov     ebx, eax
0x18003d204  mov     [rsp+140h+var_D8], eax
0x18003d208  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18003d20f  jz      loc_18003D52A
0x18003d215  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003d21c  test    rdi, rdi
0x18003d21f  jz      short loc_18003D243
0x18003d221  call    cs:__imp_GetLastError
0x18003d227  lea     rdx, aCheckgpoaccess_2; "CheckGPOAccess:  Failed to allocate mem"...
0x18003d22e  mov     r8d, eax
0x18003d231  mov     rax, rdi
0x18003d234  mov     ecx, 2
0x18003d239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d23e  jmp     loc_18003D52A
0x18003d243  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18003d24a  jz      loc_18003D52A
0x18003d250  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003d257  jz      loc_18003D52A
0x18003d25d  call    cs:__imp_GetLastError
0x18003d263  lea     rdx, aCheckgpoaccess_2; "CheckGPOAccess:  Failed to allocate mem"...
0x18003d26a  mov     r8d, eax
0x18003d26d  mov     ecx, 2; unsigned int
0x18003d272  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003d277  jmp     loc_18003D52A
0x18003d27c  mov     rdx, [rsi]
0x18003d27f  mov     r8d, [rdx]; Size
0x18003d282  mov     rdx, [rdx+8]; Src
0x18003d286  mov     rcx, rax; void *
0x18003d289  call    memcpy_0
0x18003d28e  mov     rax, [rsi]
0x18003d291  mov     ecx, [rax]
0x18003d293  mov     rax, [rsp+140h+var_D0]
0x18003d298  mov     [rax], ecx
0x18003d29a  mov     dword ptr [rbp+40h+var_B0.Level], r13d
0x18003d29e  lea     rax, [rbp+40h+var_90]
0x18003d2a2  mov     [rbp+40h+var_B0.ObjectType], rax
0x18003d2a6  mov     edi, 1
0x18003d2ab  mov     [rbp+40h+var_A0], edi
0x18003d2ae  lea     rax, [rbp+40h+var_80]
0x18003d2b2  mov     [rbp+40h+var_98], rax
0x18003d2b6  mov     rax, [rsp+140h+var_C8]
0x18003d2bb  mov     r9d, 2000000h; DesiredAccess
0x18003d2c1  xor     edx, edx; PrincipalSelfSid
0x18003d2c3  test    rax, rax
0x18003d2c6  jz      loc_18003D3FD
0x18003d2cc  lea     rcx, [rsp+140h+var_E0]
0x18003d2d1  mov     [rsp+140h+AccessStatus], rcx; __int64
0x18003d2d6  lea     rcx, [rsp+140h+var_DC]
0x18003d2db  mov     [rsp+140h+GrantedAccess], rcx; bool
0x18003d2e0  lea     rcx, [rsp+140h+var_D4]
0x18003d2e5  mov     [rsp+140h+PrivilegeSetLength], rcx; int
0x18003d2ea  lea     rcx, [rbp+40h+var_60]
0x18003d2ee  mov     [rsp+140h+PrivilegeSet], rcx; int
0x18003d2f3  lea     rcx, [rbp+40h+var_70]
0x18003d2f7  mov     [rsp+140h+GenericMapping], rcx; GenericMapping
0x18003d2fc  mov     [rsp+140h+ObjectTypeListLength], 2; unsigned int
0x18003d304  lea     rcx, [rbp+40h+var_B0]
0x18003d308  mov     [rsp+140h+ObjectTypeList], rcx; struct _OBJECT_TYPE_LIST *
0x18003d30d  mov     r8, rax
0x18003d310  mov     rcx, [r12]; pSecurityDescriptor
0x18003d314  call    RsopAccessCheckByTypeInternal
0x18003d319  test    eax, eax
0x18003d31b  jns     short loc_18003D375
0x18003d31d  movzx   ebx, ax
0x18003d320  mov     [rsp+140h+var_D8], ebx
0x18003d324  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18003d32b  jz      loc_18003D52A
0x18003d331  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003d338  test    r9, r9
0x18003d33b  jz      short loc_18003D34F
0x18003d33d  mov     r8d, eax
0x18003d340  lea     rdx, aCheckgpoaccess_5; "CheckGPOAccess:  RsopAccessCheckByType "...
0x18003d347  mov     rax, r9
0x18003d34a  jmp     loc_18003D234
0x18003d34f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18003d356  jz      loc_18003D52A
0x18003d35c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003d363  jz      loc_18003D52A
0x18003d369  lea     rdx, aCheckgpoaccess_5; "CheckGPOAccess:  RsopAccessCheckByType "...
0x18003d370  jmp     loc_18003D26A
0x18003d375  mov     r9d, 20114h
0x18003d37b  mov     r8d, [rsp+140h+var_DC]
0x18003d380  cmp     [rsp+140h+var_E0], r13d
0x18003d385  jz      short loc_18003D395
0x18003d387  mov     eax, r8d
0x18003d38a  and     eax, r9d
0x18003d38d  cmp     eax, r9d
0x18003d390  jnz     short loc_18003D395
0x18003d392  mov     [r14], edi
0x18003d395  cmp     [r14], r13d
0x18003d398  jnz     loc_18003D4C7
0x18003d39e  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18003d3a5  jz      loc_18003D4C7
0x18003d3ab  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003d3b2  test    rax, rax
0x18003d3b5  jz      short loc_18003D3CD
0x18003d3b7  lea     rdx, aCheckgpoaccess_1; "CheckGPOAccess:  AccessMask 0x%x, Looki"...
0x18003d3be  mov     ecx, 4
0x18003d3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3c8  jmp     loc_18003D4C7
0x18003d3cd  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18003d3d4  jz      loc_18003D4C7
0x18003d3da  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003d3e1  jz      loc_18003D4C7
0x18003d3e7  lea     rdx, aCheckgpoaccess_1; "CheckGPOAccess:  AccessMask 0x%x, Looki"...
0x18003d3ee  mov     ecx, 4; unsigned int
0x18003d3f3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003d3f8  jmp     loc_18003D4C7
0x18003d3fd  lea     rax, [rsp+140h+var_E0]
0x18003d402  mov     [rsp+140h+AccessStatus], rax; AccessStatus
0x18003d407  lea     rax, [rsp+140h+var_DC]
0x18003d40c  mov     [rsp+140h+GrantedAccess], rax; GrantedAccess
0x18003d411  lea     rax, [rsp+140h+var_D4]
0x18003d416  mov     [rsp+140h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18003d41b  lea     rax, [rbp+40h+var_60]
0x18003d41f  mov     [rsp+140h+PrivilegeSet], rax; PrivilegeSet
0x18003d424  lea     rax, [rbp+40h+var_70]
0x18003d428  mov     [rsp+140h+GenericMapping], rax; GenericMapping
0x18003d42d  mov     [rsp+140h+ObjectTypeListLength], 2; ObjectTypeListLength
0x18003d435  lea     rax, [rbp+40h+var_B0]
0x18003d439  mov     [rsp+140h+ObjectTypeList], rax; ObjectTypeList
0x18003d43e  mov     r8, [rbp+40h+ClientToken]; ClientToken
0x18003d442  mov     rcx, [r12]; pSecurityDescriptor
0x18003d446  call    cs:__imp_AccessCheckByType
0x18003d44c  test    eax, eax
0x18003d44e  jnz     short loc_18003D4B3
0x18003d450  call    cs:__imp_GetLastError
0x18003d456  mov     ebx, eax
0x18003d458  mov     [rsp+140h+var_D8], eax
0x18003d45c  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18003d463  jz      loc_18003D52A
0x18003d469  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003d470  test    rdi, rdi
0x18003d473  jz      short loc_18003D487
0x18003d475  call    cs:__imp_GetLastError
0x18003d47b  lea     rdx, aCheckgpoaccess; "CheckGPOAccess:  AccessCheckByType fail"...
0x18003d482  jmp     loc_18003D22E
0x18003d487  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18003d48e  jz      loc_18003D52A
0x18003d494  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003d49b  jz      loc_18003D52A
0x18003d4a1  call    cs:__imp_GetLastError
0x18003d4a7  lea     rdx, aCheckgpoaccess; "CheckGPOAccess:  AccessCheckByType fail"...
0x18003d4ae  jmp     loc_18003D26A
0x18003d4b3  cmp     [rsp+140h+var_E0], r13d
0x18003d4b8  jz      short loc_18003D4C7
0x18003d4ba  test    [rsp+140h+var_DC], 100h
0x18003d4c2  jz      short loc_18003D4C7
0x18003d4c4  mov     [r14], edi
0x18003d4c7  mov     r15d, edi
0x18003d4ca  jmp     short loc_18003D52A
0x18003d4cc  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18003d4d3  jz      short loc_18003D51F
0x18003d4d5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003d4dc  test    rax, rax
0x18003d4df  jz      short loc_18003D4F8
0x18003d4e1  mov     r8d, [rdi+74h]
0x18003d4e5  lea     rdx, aCheckgpoaccess_4; "CheckGPOAccess:  ldap_get_values_len fa"...
0x18003d4ec  mov     ecx, 2
0x18003d4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4f6  jmp     short loc_18003D51F
0x18003d4f8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18003d4ff  jz      short loc_18003D51F
0x18003d501  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003d508  jz      short loc_18003D51F
0x18003d50a  mov     r8d, [rdi+74h]
0x18003d50e  lea     rdx, aCheckgpoaccess_4; "CheckGPOAccess:  ldap_get_values_len fa"...
0x18003d515  mov     ecx, 2; unsigned int
0x18003d51a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003d51f  mov     ecx, [rdi+74h]; LdapError
0x18003d522  call    cs:__imp_LdapMapErrorToWin32
0x18003d528  mov     ebx, eax
0x18003d52a  test    rsi, rsi
0x18003d52d  jz      short loc_18003D538
0x18003d52f  mov     rcx, rsi; vals
0x18003d532  call    cs:__imp_ldap_value_free_len
0x18003d538  mov     rcx, [rbp+40h+vals]; vals
0x18003d53c  call    cs:__imp_ldap_value_freeW
0x18003d542  nop
0x18003d543  mov     ecx, ebx; dwErrCode
0x18003d545  call    cs:__imp_SetLastError
0x18003d54b  mov     eax, r15d
0x18003d54e  mov     rcx, [rbp+40h+var_48]
0x18003d552  xor     rcx, rsp; StackCookie
0x18003d555  call    __security_check_cookie
  ... truncated ...
```
