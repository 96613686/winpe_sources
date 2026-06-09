# SpIsConnected(void *,int *)

- ea: `0x1800586b0`
- end: `0x180058987`
- name: `?SpIsConnected@@YAJPEAXPEAH@Z`
- size: `727`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000e900`
- `0x18000ee60`
- `0x180042410`
- `0x18004317c`
- `0x1800586b0`
- `0x180081010`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180058842`
- `ntdll!NtQueryInformationToken` at `0x180058842`
- `ntdll!NtClose` at `0x180058960`
- `ntdll!NtClose` at `0x180058960`
- `ntdll!NtOpenThreadToken` at `0x1800587e7`
- `ntdll!NtOpenThreadToken` at `0x1800587e7`

## string_xrefs

- `0x180058722`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180058769`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800587f3`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005884e`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800588a3`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x1800588d4`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18005890a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180058869`: `NtQueryInformationToken`
- `0x18005880e`: `NtOpenThreadToken`
- `0x18005892a`: `Not supported for this type of plugin`

## pseudocode

```c
__int64 __fastcall SpIsConnected(void *a1, int *a2)
{
  struct _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE *v4; // rax
  struct _ApPluginPkg *v5; // rdi
  unsigned int v6; // ebx
  const char *v7; // r9
  const char *v8; // rax
  const char *v9; // r9
  const char *v10; // r9
  const char *v11; // r9
  const char *v12; // r9
  const char *v13; // r9
  PULONG ReturnLength; // [rsp+20h] [rbp-79h]
  ULONG v16; // [rsp+40h] [rbp-59h] BYREF
  struct _ApPluginPkg *v17; // [rsp+48h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-49h] BYREF
  _QWORD TokenInformation[12]; // [rsp+60h] [rbp-39h] BYREF
  struct _GUID v20; // [rsp+C0h] [rbp+27h] BYREF

  v16 = 0;
  v20 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  v4 = g_pLsaIdProvHostFunctionTable;
  v5 = 0;
  TokenHandle = 0;
  *a2 = 0;
  v17 = 0;
  v6 = (*((__int64 (__fastcall **)(void *, struct _GUID *))v4 + 10))(a1, &v20);
  if ( v6 )
  {
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v7, 9056, "GetProvInfo", &Class);
  }
  else
  {
    v6 = RefPackage(&v20, &v17);
    if ( v6 )
    {
      v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v8, 9059, "RefPackage", &Class);
      v5 = v17;
    }
    else
    {
      v5 = v17;
      if ( (*((_BYTE *)v17 + 160) & 5) == 1 )
      {
        if ( *((_QWORD *)v17 + 27) )
        {
          v6 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
          if ( v6 )
          {
            v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v9, 9077, "NtOpenThreadToken", &Class);
          }
          else
          {
            v6 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, &v16);
            if ( v6 )
            {
              v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(ReturnLength) = 9085;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v10, ReturnLength, "NtQueryInformationToken", &Class);
            }
            else
            {
              v6 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, int *))v5 + 27))(
                     *((_QWORD *)v5 + 1),
                     TokenInformation[0],
                     a2);
              if ( v6 )
              {
                v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
                LODWORD(ReturnLength) = 9091;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v6, v11, ReturnLength, "IsConnected", &Class);
              }
            }
          }
        }
        else
        {
          v6 = -1073741822;
          v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225474LL, v12, 9096, "Not Implemented", &Class);
        }
      }
      else
      {
        v6 = -1073741637;
        v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          3221225659LL,
          v13,
          9066,
          "Not supported for this type of plugin",
          &Class);
      }
    }
  }
  DerefPackage(v5);
  if ( TokenHandle )
    NtClose(TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x1800586b0  mov     [rsp-8+arg_10], rbx
0x1800586b5  push    rbp
0x1800586b6  push    rsi
0x1800586b7  push    rdi
0x1800586b8  lea     rbp, [rsp-47h]
0x1800586bd  sub     rsp, 0E0h
0x1800586c4  mov     rax, cs:__security_cookie
0x1800586cb  xor     rax, rsp
0x1800586ce  mov     [rbp+57h+var_20], rax
0x1800586d2  mov     rsi, rdx
0x1800586d5  mov     [rbp+57h+var_B0], 0
0x1800586dc  xor     edx, edx; Val
0x1800586de  mov     rbx, rcx
0x1800586e1  xorps   xmm0, xmm0
0x1800586e4  lea     rcx, [rbp+57h+TokenInformation]; void *
0x1800586e8  movups  xmmword ptr [rbp+57h+var_30.Data1], xmm0
0x1800586ec  lea     r8d, [rdx+58h]; Size
0x1800586f0  call    memset_0
0x1800586f5  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x1800586fc  lea     rdx, [rbp+57h+var_30]
0x180058700  xor     edi, edi
0x180058702  mov     [rbp+57h+TokenHandle], 0
0x18005870a  mov     [rsi], edi
0x18005870c  mov     rcx, rbx
0x18005870f  mov     [rbp+57h+var_A8], rdi
0x180058713  mov     rax, [rax+50h]
0x180058717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005871c  mov     ebx, eax
0x18005871e  test    eax, eax
0x180058720  jz      short loc_180058756
0x180058722  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180058729  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005872e  mov     r9, rax
0x180058731  lea     rax, Class
0x180058738  mov     [rsp+0F0h+var_C0], rax
0x18005873d  lea     rax, aGetprovinfo; "GetProvInfo"
0x180058744  mov     [rsp+0F0h+var_C8], rax
0x180058749  mov     dword ptr [rsp+0F0h+ReturnLength], 2360h
0x180058751  jmp     loc_18005893E
0x180058756  lea     rdx, [rbp+57h+var_A8]; struct _ApPluginPkg **
0x18005875a  lea     rcx, [rbp+57h+var_30]; struct _GUID *
0x18005875e  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x180058763  mov     ebx, eax
0x180058765  test    eax, eax
0x180058767  jz      short loc_1800587B2
0x180058769  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180058770  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180058775  mov     r9, rax
0x180058778  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005877f  lea     rax, Class
0x180058786  mov     r8d, ebx
0x180058789  mov     [rsp+0F0h+var_C0], rax
0x18005878e  xor     ecx, ecx
0x180058790  lea     rax, aRefpackage; "RefPackage"
0x180058797  mov     [rsp+0F0h+var_C8], rax
0x18005879c  mov     dword ptr [rsp+0F0h+ReturnLength], 2363h
0x1800587a4  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800587a9  mov     rdi, [rbp+57h+var_A8]
0x1800587ad  jmp     loc_18005894F
0x1800587b2  mov     rdi, [rbp+57h+var_A8]
0x1800587b6  mov     eax, [rdi+0A0h]
0x1800587bc  and     al, 5
0x1800587be  cmp     al, 1
0x1800587c0  jnz     loc_18005890A
0x1800587c6  cmp     qword ptr [rdi+0D8h], 0
0x1800587ce  jz      loc_1800588D4
0x1800587d4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800587d8  mov     r8b, al; OpenAsSelf
0x1800587db  mov     edx, 8; DesiredAccess
0x1800587e0  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800587e7  call    cs:__imp_NtOpenThreadToken
0x1800587ed  mov     ebx, eax
0x1800587ef  test    eax, eax
0x1800587f1  jz      short loc_180058827
0x1800587f3  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800587fa  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800587ff  mov     r9, rax
0x180058802  lea     rax, Class
0x180058809  mov     [rsp+0F0h+var_C0], rax
0x18005880e  lea     rax, aNtopenthreadto; "NtOpenThreadToken"
0x180058815  mov     [rsp+0F0h+var_C8], rax
0x18005881a  mov     dword ptr [rsp+0F0h+ReturnLength], 2375h
0x180058822  jmp     loc_18005893E
0x180058827  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18005882b  lea     rax, [rbp+57h+var_B0]
0x18005882f  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180058835  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x18005883a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18005883e  lea     edx, [r9-57h]; TokenInformationClass
0x180058842  call    cs:__imp_NtQueryInformationToken
0x180058848  mov     ebx, eax
0x18005884a  test    eax, eax
0x18005884c  jz      short loc_180058882
0x18005884e  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180058855  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005885a  mov     r9, rax
0x18005885d  lea     rax, Class
0x180058864  mov     [rsp+0F0h+var_C0], rax
0x180058869  lea     rax, aNtqueryinforma_1; "NtQueryInformationToken"
0x180058870  mov     [rsp+0F0h+var_C8], rax
0x180058875  mov     dword ptr [rsp+0F0h+ReturnLength], 237Dh
0x18005887d  jmp     loc_18005893E
0x180058882  mov     rdx, [rbp+57h+TokenInformation]
0x180058886  mov     r8, rsi
0x180058889  mov     rcx, [rdi+8]
0x18005888d  mov     rax, [rdi+0D8h]
0x180058894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058899  mov     ebx, eax
0x18005889b  test    eax, eax
0x18005889d  jz      loc_18005894F
0x1800588a3  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800588aa  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800588af  mov     r9, rax
0x1800588b2  lea     rax, Class
0x1800588b9  mov     [rsp+0F0h+var_C0], rax
0x1800588be  lea     rax, aIsconnected; "IsConnected"
0x1800588c5  mov     [rsp+0F0h+var_C8], rax
0x1800588ca  mov     dword ptr [rsp+0F0h+ReturnLength], 2383h
0x1800588d2  jmp     short loc_18005893E
0x1800588d4  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x1800588db  mov     ebx, 0C0000002h
0x1800588e0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800588e5  mov     r9, rax
0x1800588e8  lea     rax, Class
0x1800588ef  mov     [rsp+0F0h+var_C0], rax
0x1800588f4  lea     rax, aNotImplemented; "Not Implemented"
0x1800588fb  mov     [rsp+0F0h+var_C8], rax
0x180058900  mov     dword ptr [rsp+0F0h+ReturnLength], 2388h
0x180058908  jmp     short loc_18005893E
0x18005890a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180058911  mov     ebx, 0C00000BBh
0x180058916  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005891b  mov     r9, rax
0x18005891e  lea     rax, Class
0x180058925  mov     [rsp+0F0h+var_C0], rax
0x18005892a  lea     rax, aNotSupportedFo; "Not supported for this type of plugin"
0x180058931  mov     [rsp+0F0h+var_C8], rax
0x180058936  mov     dword ptr [rsp+0F0h+ReturnLength], 236Ah
0x18005893e  mov     r8d, ebx
0x180058941  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180058948  xor     ecx, ecx
0x18005894a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005894f  mov     rcx, rdi; struct _ApPluginPkg *
0x180058952  call    ?DerefPackage@@YAXPEAU_ApPluginPkg@@@Z; DerefPackage(_ApPluginPkg *)
0x180058957  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18005895b  test    rcx, rcx
0x18005895e  jz      short loc_180058966
0x180058960  call    cs:__imp_NtClose
0x180058966  mov     eax, ebx
0x180058968  mov     rcx, [rbp+57h+var_20]
0x18005896c  xor     rcx, rsp; StackCookie
0x18005896f  call    __security_check_cookie
0x180058974  mov     rbx, [rsp+0F0h+arg_10]
0x18005897c  add     rsp, 0E0h
0x180058983  pop     rdi
0x180058984  pop     rsi
0x180058985  pop     rbp
0x180058986  retn
```
