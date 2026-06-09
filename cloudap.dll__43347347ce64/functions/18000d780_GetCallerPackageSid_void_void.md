# GetCallerPackageSid(void *,void * *)

- ea: `0x18000d780`
- end: `0x18000db62`
- name: `?GetCallerPackageSid@@YAJPEAXPEAPEAX@Z`
- size: `994`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000bda0`
- `0x18000c450`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000d780`
- `0x180081010`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000d7bb`
- `ntdll!NtQueryInformationToken` at `0x18000d7fb`
- `ntdll!NtQueryInformationToken` at `0x18000d84e`
- `ntdll!NtQueryInformationToken` at `0x18000d7bb`
- `ntdll!NtQueryInformationToken` at `0x18000d7fb`
- `ntdll!NtQueryInformationToken` at `0x18000d84e`
- `ntdll!RtlLengthSid` at `0x18000d95e`
- `ntdll!RtlLengthSid` at `0x18000d95e`
- `ntdll!RtlCopySid` at `0x18000d992`
- `ntdll!RtlCopySid` at `0x18000d992`

## string_xrefs

- `0x18000d868`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000d8f8`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000d9b7`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000da15`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000da90`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000dac9`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000db15`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000d895`: `NtQueryInformationToken(TokenAppContainerSid)`
- `0x18000da33`: `NtQueryInformationToken(TokenAppContainerSid)`
- `0x18000d9d4`: `NtQueryInformationToken(TokenIsAppContainer)`
- `0x18000dae4`: `RtlCopySid`

## pseudocode

```c
__int64 __fastcall GetCallerPackageSid(HANDLE TokenHandle, void **a2)
{
  unsigned int v4; // esi
  __int64 v5; // rdx
  PSID *v6; // rsi
  unsigned int v7; // ebx
  void *v8; // rbp
  const char *v9; // r9
  char v10; // al
  const char *v11; // rcx
  bool v12; // zf
  const char *v14; // r9
  char v15; // al
  const char *v16; // rcx
  bool v17; // zf
  void *v18; // rax
  const char *v19; // r9
  char v20; // al
  const char *v21; // rcx
  bool v22; // zf
  const char *v23; // rax
  __int64 v24; // r8
  const char *v25; // rax
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-48h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-48h]
  PULONG ReturnLengthb; // [rsp+20h] [rbp-48h]
  PULONG ReturnLengthc; // [rsp+20h] [rbp-48h]
  ULONG TokenInformationLength; // [rsp+78h] [rbp+10h] BYREF
  int v34; // [rsp+80h] [rbp+18h] BYREF

  TokenInformationLength = 4;
  *a2 = 0;
  v34 = 0;
  v4 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &v34, 4u, &TokenInformationLength);
  if ( v4 )
  {
    v19 = "";
    while ( 1 )
    {
      v20 = *(v19 - 1);
      v21 = v19--;
      v22 = v20 == 92;
      if ( v20 == 92 )
        break;
      if ( v19 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
      {
        v22 = v20 == 92;
        break;
      }
    }
    if ( v22 )
      v19 = v21;
    LODWORD(ReturnLength) = 1304;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      v4,
      v19,
      ReturnLength,
      "NtQueryInformationToken(TokenIsAppContainer)",
      &Class);
    return v4;
  }
  else if ( v34 )
  {
    TokenInformationLength = 0;
    if ( NtQueryInformationToken(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) == -1073741789 )
    {
      v6 = (PSID *)((__int64 (__fastcall *)(_QWORD, __int64, __int64))g_pLsaFunctionTable->AllocateLsaHeap)(
                     TokenInformationLength,
                     v5,
                     3221225507LL);
      if ( v6 )
      {
        v7 = NtQueryInformationToken(
               TokenHandle,
               TokenAppContainerSid,
               v6,
               TokenInformationLength,
               &TokenInformationLength);
        if ( v7 )
        {
          v8 = 0;
          v9 = "";
          while ( 1 )
          {
            v10 = *(v9 - 1);
            v11 = v9--;
            v12 = v10 == 92;
            if ( v10 == 92 )
              break;
            if ( v9 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
            {
              v12 = v10 == 92;
              break;
            }
          }
          if ( v12 )
            v9 = v11;
          LODWORD(ReturnLengthb) = 1333;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            v7,
            v9,
            ReturnLengthb,
            "NtQueryInformationToken(TokenAppContainerSid)",
            &Class);
        }
        else
        {
          TokenInformationLength = RtlLengthSid(*v6);
          v18 = (void *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(TokenInformationLength);
          v8 = v18;
          if ( v18 )
          {
            v7 = RtlCopySid(TokenInformationLength, v18, *v6);
            if ( v7 )
            {
              v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
              LODWORD(ReturnLengthb) = 1345;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v27, ReturnLengthb, "RtlCopySid", &Class);
            }
            else
            {
              *a2 = v8;
              v7 = 0;
              v8 = 0;
            }
          }
          else
          {
            v7 = -1073741801;
            v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
            LODWORD(ReturnLengthb) = 1341;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v26, ReturnLengthb, "AllocateLsaHeap", &Class);
          }
        }
        ((void (__fastcall *)(PSID *))g_pLsaFunctionTable->FreeLsaHeap)(v6);
        if ( v8 )
          ((void (__fastcall *)(void *))g_pLsaFunctionTable->FreeLsaHeap)(v8);
        return v7;
      }
      else
      {
        v14 = "";
        while ( 1 )
        {
          v15 = *(v14 - 1);
          v16 = v14--;
          v17 = v15 == 92;
          if ( v15 == 92 )
            break;
          if ( v14 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
          {
            v17 = v15 == 92;
            break;
          }
        }
        if ( v17 )
          v14 = v16;
        LODWORD(ReturnLengtha) = 1325;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v14, ReturnLengtha, "AllocateLsaHeap", &Class);
        return 3221225495LL;
      }
    }
    else
    {
      v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(ReturnLengtha) = 1316;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        v24,
        v23,
        ReturnLengtha,
        "NtQueryInformationToken(TokenAppContainerSid)",
        &Class);
      v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      LODWORD(ReturnLengthc) = 1318;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        3221225701LL,
        v25,
        ReturnLengthc,
        "NtQueryInformationToken(TokenAppContainerSid)",
        &Class);
      return 3221225701LL;
    }
  }
  else
  {
    v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
    LODWORD(ReturnLength) = 1350;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225506LL, v28, ReturnLength, "Caller is not an appcontainer", &Class);
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x18000d780  mov     r11, rsp
0x18000d783  push    rbx
0x18000d784  push    rsi
0x18000d785  push    rdi
0x18000d786  push    r14
0x18000d788  sub     rsp, 48h
0x18000d78c  xor     r14d, r14d
0x18000d78f  mov     [rsp+68h+TokenInformationLength], 4
0x18000d797  mov     [rdx], r14
0x18000d79a  lea     rax, [r11+10h]
0x18000d79e  mov     rdi, rdx
0x18000d7a1  mov     [r11+18h], r14d
0x18000d7a5  mov     edx, 1Dh; TokenInformationClass
0x18000d7aa  mov     [r11-48h], rax
0x18000d7ae  mov     r9d, 4; TokenInformationLength
0x18000d7b4  lea     r8, [r11+18h]; TokenInformation
0x18000d7b8  mov     rbx, rcx
0x18000d7bb  call    cs:__imp_NtQueryInformationToken
0x18000d7c1  mov     esi, eax
0x18000d7c3  test    eax, eax
0x18000d7c5  jnz     loc_18000D9B0
0x18000d7cb  cmp     [rsp+68h+arg_10], r14d
0x18000d7d3  jz      loc_18000DB15
0x18000d7d9  lea     rax, [rsp+68h+TokenInformationLength]
0x18000d7de  mov     [rsp+68h+var_28], r15
0x18000d7e3  xor     r9d, r9d; TokenInformationLength
0x18000d7e6  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18000d7eb  xor     r8d, r8d; TokenInformation
0x18000d7ee  mov     [rsp+68h+TokenInformationLength], r14d
0x18000d7f3  mov     edx, 1Fh; TokenInformationClass
0x18000d7f8  mov     rcx, rbx; TokenHandle
0x18000d7fb  call    cs:__imp_NtQueryInformationToken
0x18000d801  mov     r8d, eax
0x18000d804  cmp     eax, 0C0000023h
0x18000d809  jnz     loc_18000DA15
0x18000d80f  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000d816  mov     ecx, [rsp+68h+TokenInformationLength]
0x18000d81a  mov     rax, [rax+28h]
0x18000d81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d823  mov     rsi, rax
0x18000d826  test    rax, rax
0x18000d829  jz      loc_18000D8EC
0x18000d82f  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18000d834  lea     rax, [rsp+68h+TokenInformationLength]
0x18000d839  mov     r8, rsi; TokenInformation
0x18000d83c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18000d841  mov     edx, 1Fh; TokenInformationClass
0x18000d846  mov     [rsp+68h+arg_0], rbp
0x18000d84b  mov     rcx, rbx; TokenHandle
0x18000d84e  call    cs:__imp_NtQueryInformationToken
0x18000d854  mov     ebx, eax
0x18000d856  test    eax, eax
0x18000d858  jz      loc_18000D95B
0x18000d85e  mov     ebp, r14d
0x18000d861  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x18000d868  lea     rdi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000d86f  movzx   eax, byte ptr [r9-1]
0x18000d874  mov     rcx, r9
0x18000d877  dec     r9
0x18000d87a  cmp     al, 5Ch ; '\'
0x18000d87c  jz      short loc_18000D885
0x18000d87e  cmp     r9, rdi
0x18000d881  ja      short loc_18000D86F
0x18000d883  cmp     al, 5Ch ; '\'
0x18000d885  lea     r14, Class
0x18000d88c  cmovz   r9, rcx
0x18000d890  mov     [rsp+68h+var_38], r14
0x18000d895  lea     r15, aNtqueryinforma_2; "NtQueryInformationToken(TokenAppContain"...
0x18000d89c  mov     [rsp+68h+var_40], r15
0x18000d8a1  mov     dword ptr [rsp+68h+ReturnLength], 535h
0x18000d8a9  mov     r8d, ebx
0x18000d8ac  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000d8b3  xor     ecx, ecx
0x18000d8b5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000d8ba  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000d8c1  mov     rcx, rsi
0x18000d8c4  mov     rax, [rax+30h]
0x18000d8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8cd  test    rbp, rbp
0x18000d8d0  jnz     loc_18000DAFD
0x18000d8d6  mov     rbp, [rsp+68h+arg_0]
0x18000d8db  mov     eax, ebx
0x18000d8dd  mov     r15, [rsp+68h+var_28]
0x18000d8e2  add     rsp, 48h
0x18000d8e6  pop     r14
0x18000d8e8  pop     rdi
0x18000d8e9  pop     rsi
0x18000d8ea  pop     rbx
0x18000d8eb  retn
0x18000d8ec  mov     ebx, 0C0000017h
0x18000d8f1  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x18000d8f8  lea     rdi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000d8ff  movzx   eax, byte ptr [r9-1]
0x18000d904  mov     rcx, r9
0x18000d907  dec     r9
0x18000d90a  cmp     al, 5Ch ; '\'
0x18000d90c  jz      short loc_18000D915
0x18000d90e  cmp     r9, rdi
0x18000d911  ja      short loc_18000D8FF
0x18000d913  cmp     al, 5Ch ; '\'
0x18000d915  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18000d91c  cmovz   r9, rcx
0x18000d920  lea     r14, Class
0x18000d927  mov     r8d, ebx
0x18000d92a  mov     [rsp+68h+var_38], r14
0x18000d92f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000d936  mov     [rsp+68h+var_40], rax
0x18000d93b  xor     ecx, ecx
0x18000d93d  mov     dword ptr [rsp+68h+ReturnLength], 52Dh
0x18000d945  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000d94a  mov     r15, [rsp+68h+var_28]
0x18000d94f  mov     eax, ebx
0x18000d951  add     rsp, 48h
0x18000d955  pop     r14
0x18000d957  pop     rdi
0x18000d958  pop     rsi
0x18000d959  pop     rbx
0x18000d95a  retn
0x18000d95b  mov     rcx, [rsi]; Sid
0x18000d95e  call    cs:__imp_RtlLengthSid
0x18000d964  mov     rcx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000d96b  mov     edx, eax
0x18000d96d  mov     [rsp+68h+TokenInformationLength], eax
0x18000d971  mov     rax, [rcx+28h]
0x18000d975  mov     ecx, edx
0x18000d977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d97c  mov     rbp, rax
0x18000d97f  test    rax, rax
0x18000d982  jz      loc_18000DA90
0x18000d988  mov     r8, [rsi]; SourceSid
0x18000d98b  mov     rdx, rax; DestinationSid
0x18000d98e  mov     ecx, [rsp+68h+TokenInformationLength]; DestinationSidLength
0x18000d992  call    cs:__imp_RtlCopySid
0x18000d998  mov     ebx, eax
0x18000d99a  test    eax, eax
0x18000d99c  jnz     loc_18000DAC9
0x18000d9a2  mov     [rdi], rbp
0x18000d9a5  mov     ebx, r14d
0x18000d9a8  mov     rbp, r14
0x18000d9ab  jmp     loc_18000D8BA
0x18000d9b0  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x18000d9b7  lea     rdi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000d9be  movzx   eax, byte ptr [r9-1]
0x18000d9c3  mov     rcx, r9
0x18000d9c6  dec     r9
0x18000d9c9  cmp     al, 5Ch ; '\'
0x18000d9cb  jz      short loc_18000D9D4
0x18000d9cd  cmp     r9, rdi
0x18000d9d0  ja      short loc_18000D9BE
0x18000d9d2  cmp     al, 5Ch ; '\'
0x18000d9d4  lea     rax, aNtqueryinforma; "NtQueryInformationToken(TokenIsAppConta"...
0x18000d9db  cmovz   r9, rcx
0x18000d9df  lea     r14, Class
0x18000d9e6  mov     r8d, esi
0x18000d9e9  mov     [rsp+68h+var_38], r14
0x18000d9ee  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000d9f5  mov     [rsp+68h+var_40], rax
0x18000d9fa  xor     ecx, ecx
0x18000d9fc  mov     dword ptr [rsp+68h+ReturnLength], 518h
0x18000da04  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000da09  mov     eax, esi
0x18000da0b  add     rsp, 48h
0x18000da0f  pop     r14
0x18000da11  pop     rdi
0x18000da12  pop     rsi
0x18000da13  pop     rbx
0x18000da14  retn
0x18000da15  lea     rdi, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000da1c  mov     rcx, rdi; char *
0x18000da1f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000da24  lea     r14, Class
0x18000da2b  mov     r9, rax
0x18000da2e  mov     [rsp+68h+var_38], r14
0x18000da33  lea     r15, aNtqueryinforma_2; "NtQueryInformationToken(TokenAppContain"...
0x18000da3a  mov     [rsp+68h+var_40], r15
0x18000da3f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000da46  xor     ecx, ecx
0x18000da48  mov     dword ptr [rsp+68h+ReturnLength], 524h
0x18000da50  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000da55  mov     rcx, rdi; char *
0x18000da58  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000da5d  mov     [rsp+68h+var_38], r14
0x18000da62  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000da69  mov     r9, rax
0x18000da6c  mov     [rsp+68h+var_40], r15
0x18000da71  mov     r8d, 0C00000E5h
0x18000da77  mov     dword ptr [rsp+68h+ReturnLength], 526h
0x18000da7f  xor     ecx, ecx
0x18000da81  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000da86  mov     eax, 0C00000E5h
0x18000da8b  jmp     loc_18000D8DD
0x18000da90  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000da97  mov     ebx, 0C0000017h
0x18000da9c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000daa1  mov     r9, rax
0x18000daa4  lea     r14, Class
0x18000daab  mov     [rsp+68h+var_38], r14
0x18000dab0  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18000dab7  mov     [rsp+68h+var_40], rax
0x18000dabc  mov     dword ptr [rsp+68h+ReturnLength], 53Dh
0x18000dac4  jmp     loc_18000D8A9
0x18000dac9  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000dad0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000dad5  mov     r9, rax
0x18000dad8  lea     r14, Class
0x18000dadf  mov     [rsp+68h+var_38], r14
0x18000dae4  lea     rax, aRtlcopysid; "RtlCopySid"
0x18000daeb  mov     [rsp+68h+var_40], rax
0x18000daf0  mov     dword ptr [rsp+68h+ReturnLength], 541h
0x18000daf8  jmp     loc_18000D8A9
0x18000dafd  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000db04  mov     rcx, rbp
0x18000db07  mov     rax, [rax+30h]
0x18000db0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db10  jmp     loc_18000D8D6
0x18000db15  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000db1c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000db21  lea     rcx, aCallerIsNotAnA; "Caller is not an appcontainer"
0x18000db28  mov     r9, rax
0x18000db2b  lea     r14, Class
0x18000db32  mov     r8d, 0C0000022h
0x18000db38  mov     [rsp+68h+var_38], r14
0x18000db3d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000db44  mov     [rsp+68h+var_40], rcx
0x18000db49  xor     ecx, ecx
0x18000db4b  mov     dword ptr [rsp+68h+ReturnLength], 546h
0x18000db53  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000db58  mov     eax, 0C0000022h
0x18000db5d  jmp     loc_18000D8E2
```
