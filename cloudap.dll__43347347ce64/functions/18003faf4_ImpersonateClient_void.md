# ImpersonateClient(void * *)

- ea: `0x18003faf4`
- end: `0x18003fc7f`
- name: `?ImpersonateClient@@YAJPEAPEAX@Z`
- size: `395`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001f8f0`
- `0x180029650`
- `0x180037240`
- `0x18005a62c`
- `0x180062ddc`
- `0x180063094`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18003faf4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fba9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003fba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fc6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fc6c`
- `ntdll!NtOpenThreadToken` at `0x18003fb25`
- `ntdll!NtOpenThreadToken` at `0x18003fb25`
- `ntdll!NtSetInformationThread` at `0x18003fbc8`
- `ntdll!NtSetInformationThread` at `0x18003fbc8`

## string_xrefs

- `0x18003fb74`: `NtOpenThreadToken`
- `0x18003fc36`: `ImpersonateClient`
- `0x18003fbef`: `NtSetInformationThread`

## pseudocode

```c
__int64 __fastcall ImpersonateClient(void **a1)
{
  unsigned int v2; // ebx
  const char *v3; // r9
  const char *v4; // rax
  bool v5; // zf
  void *Value; // rax
  const char *v7; // r9
  const char *v8; // r9
  int v10; // [rsp+20h] [rbp-28h]
  int v11; // [rsp+20h] [rbp-28h]
  int v12; // [rsp+20h] [rbp-28h]
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  v2 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -1073741700 )
  {
    if ( g_dwTlsCloudAPIndex == -1 || (Value = TlsGetValue(g_dwTlsCloudAPIndex)) == 0 )
    {
      v2 = g_pLsaFunctionTable->ImpersonateClient();
      if ( v2 )
      {
        v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
        v12 = 543;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v2, v8, v12, "ImpersonateClient", &Class);
        goto LABEL_18;
      }
    }
    else
    {
      v2 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, Value, 8u);
      if ( v2 )
      {
        v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
        v11 = 538;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v2, v7, v11, "NtSetInformationThread", &Class);
        goto LABEL_18;
      }
    }
    v2 = 0;
    *a1 = TokenHandle;
    TokenHandle = 0;
  }
  else
  {
    v3 = "";
    while ( 1 )
    {
      v4 = v3--;
      v5 = *v3 == 92;
      if ( *v3 == 92 )
        break;
      if ( v3 <= "onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp" )
      {
        v5 = *v3 == 92;
        break;
      }
    }
    if ( v5 )
      v3 = v4;
    v10 = 522;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v2, v3, v10, "NtOpenThreadToken", &Class);
  }
LABEL_18:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x18003faf4  mov     [rsp+arg_8], rbx
0x18003faf9  push    rdi
0x18003fafa  sub     rsp, 40h
0x18003fafe  mov     rdi, rcx
0x18003fb01  mov     qword ptr [rcx], 0
0x18003fb08  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18003fb0f  mov     [rsp+48h+TokenHandle], 0
0x18003fb18  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18003fb1d  mov     r8b, 1; OpenAsSelf
0x18003fb20  mov     edx, 0Ch; DesiredAccess
0x18003fb25  call    cs:__imp_NtOpenThreadToken
0x18003fb2b  mov     ebx, eax
0x18003fb2d  mov     eax, 80000000h
0x18003fb32  lea     edx, [rbx+rax]
0x18003fb35  test    eax, edx
0x18003fb37  jnz     short loc_18003FB9E
0x18003fb39  cmp     ebx, 0C000007Ch
0x18003fb3f  jz      short loc_18003FB9E
0x18003fb41  lea     r9, aOnecoreDsExtCl_0+43h; ""
0x18003fb48  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x18003fb4f  mov     rax, r9
0x18003fb52  dec     r9
0x18003fb55  cmp     byte ptr [r9], 5Ch ; '\'
0x18003fb59  jz      short loc_18003FB64
0x18003fb5b  cmp     r9, rcx
0x18003fb5e  ja      short loc_18003FB4F
0x18003fb60  cmp     byte ptr [r9], 5Ch ; '\'
0x18003fb64  cmovz   r9, rax
0x18003fb68  lea     rax, Class
0x18003fb6f  mov     [rsp+48h+var_18], rax
0x18003fb74  lea     rax, aNtopenthreadto; "NtOpenThreadToken"
0x18003fb7b  mov     [rsp+48h+var_20], rax
0x18003fb80  mov     [rsp+48h+var_28], 20Ah
0x18003fb88  mov     r8d, ebx
0x18003fb8b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003fb92  xor     ecx, ecx
0x18003fb94  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003fb99  jmp     loc_18003FC62
0x18003fb9e  mov     ecx, cs:?g_dwTlsCloudAPIndex@@3KA; dwTlsIndex
0x18003fba4  cmp     ecx, 0FFFFFFFFh
0x18003fba7  jz      short loc_18003FC05
0x18003fba9  call    cs:__imp_TlsGetValue
0x18003fbaf  test    rax, rax
0x18003fbb2  jz      short loc_18003FC05
0x18003fbb4  mov     r9d, 8; ThreadInformationLength
0x18003fbba  mov     r8, rax; ThreadInformation
0x18003fbbd  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18003fbc4  lea     edx, [r9-3]; ThreadInformationClass
0x18003fbc8  call    cs:__imp_NtSetInformationThread
0x18003fbce  mov     ebx, eax
0x18003fbd0  test    eax, eax
0x18003fbd2  jz      short loc_18003FC4F
0x18003fbd4  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x18003fbdb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003fbe0  mov     r9, rax
0x18003fbe3  lea     rax, Class
0x18003fbea  mov     [rsp+48h+var_18], rax
0x18003fbef  lea     rax, aNtsetinformati; "NtSetInformationThread"
0x18003fbf6  mov     [rsp+48h+var_20], rax
0x18003fbfb  mov     [rsp+48h+var_28], 21Ah
0x18003fc03  jmp     short loc_18003FB88
0x18003fc05  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18003fc0c  mov     rax, [rax+58h]
0x18003fc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc15  mov     ebx, eax
0x18003fc17  test    eax, eax
0x18003fc19  jz      short loc_18003FC4F
0x18003fc1b  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x18003fc22  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003fc27  mov     r9, rax
0x18003fc2a  lea     rax, Class
0x18003fc31  mov     [rsp+48h+var_18], rax
0x18003fc36  lea     rax, aImpersonatecli; "ImpersonateClient"
0x18003fc3d  mov     [rsp+48h+var_20], rax
0x18003fc42  mov     [rsp+48h+var_28], 21Fh
0x18003fc4a  jmp     loc_18003FB88
0x18003fc4f  mov     rax, [rsp+48h+TokenHandle]
0x18003fc54  xor     ebx, ebx
0x18003fc56  mov     [rdi], rax
0x18003fc59  mov     [rsp+48h+TokenHandle], 0
0x18003fc62  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18003fc67  test    rcx, rcx
0x18003fc6a  jz      short loc_18003FC72
0x18003fc6c  call    cs:__imp_CloseHandle
0x18003fc72  mov     eax, ebx
0x18003fc74  mov     rbx, [rsp+48h+arg_8]
0x18003fc79  add     rsp, 40h
0x18003fc7d  pop     rdi
0x18003fc7e  retn
```
