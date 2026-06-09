# FlushIdentityCache(void *)

- ea: `0x18004e1b8`
- end: `0x18004e336`
- name: `?FlushIdentityCache@@YAJPEAX@Z`
- size: `382`
- prototype: `__int64 __fastcall(PSID SourceSid)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000477c`
- `0x18000498c`
- `0x180018a20`
- `0x1800307d0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18004e1b8`
- `0x18004e340`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e2ae`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18004e28c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18004e28c`
- `ntdll!RtlLengthSid` at `0x18004e1ca`
- `ntdll!RtlLengthSid` at `0x18004e1ca`
- `ntdll!RtlCopySid` at `0x18004e23e`
- `ntdll!RtlCopySid` at `0x18004e23e`

## string_xrefs

- `0x18004e1ec`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e24d`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e2c0`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e263`: `RtlCopySid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FlushIdentityCache(PSID SourceSid)
{
  __int64 v2; // rsi
  void *v3; // rax
  void *v4; // rdi
  unsigned int LastError; // ebx
  const char *v6; // rax
  const char *v7; // rax
  __int64 v8; // r8
  const char *v9; // r10
  __int64 v10; // r11
  const char *v11; // rdx
  int v12; // ecx

  v2 = RtlLengthSid(SourceSid);
  v3 = (void *)((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(v2);
  v4 = v3;
  if ( v3 )
  {
    LastError = RtlCopySid(v2, v3, SourceSid);
    if ( LastError )
    {
      v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      v11 = "RtlCopySid";
      v12 = 2226;
LABEL_11:
      WPPTraceLogA(v10, v9, v8, v7, v12, v11, &Class);
      ((void (__fastcall *)(void *))g_pLsaFunctionTable->FreeLsaHeap)(v4);
      return LastError;
    }
    if ( (g_ulTestFlags & 1) != 0 )
    {
      FlushIdentityCacheWkItem(v4);
    }
    else if ( !QueueUserWorkItem(FlushIdentityCacheWkItem, v4, 0) )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      v11 = "QueueUserWorkItem";
      v12 = 2236;
      goto LABEL_11;
    }
    return 0;
  }
  LastError = -1073741801;
  v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v6, 2222, "AllocateLsaHeap", &Class);
  return LastError;
}

```

## disassembly

```asm
0x18004e1b8  mov     [rsp+arg_0], rbx
0x18004e1bd  mov     [rsp+arg_8], rsi
0x18004e1c2  push    rdi
0x18004e1c3  sub     rsp, 40h
0x18004e1c7  mov     rbx, rcx
0x18004e1ca  call    cs:__imp_RtlLengthSid
0x18004e1d0  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004e1d7  mov     esi, eax
0x18004e1d9  mov     ecx, eax
0x18004e1db  mov     rax, [rdx+28h]
0x18004e1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1e4  mov     rdi, rax
0x18004e1e7  test    rax, rax
0x18004e1ea  jnz     short loc_18004E236
0x18004e1ec  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e1f3  mov     ebx, 0C0000017h
0x18004e1f8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004e1fd  mov     r9, rax
0x18004e200  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004e207  lea     rax, Class
0x18004e20e  mov     r8d, ebx
0x18004e211  mov     [rsp+48h+var_18], rax
0x18004e216  xor     ecx, ecx
0x18004e218  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18004e21f  mov     [rsp+48h+var_20], rax
0x18004e224  mov     [rsp+48h+var_28], 8AEh
0x18004e22c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004e231  jmp     loc_18004E324
0x18004e236  mov     r8, rbx; SourceSid
0x18004e239  mov     rdx, rdi; DestinationSid
0x18004e23c  mov     ecx, esi; DestinationSidLength
0x18004e23e  call    cs:__imp_RtlCopySid
0x18004e244  mov     ebx, eax
0x18004e246  test    eax, eax
0x18004e248  jz      short loc_18004E271
0x18004e24a  xor     r11d, r11d
0x18004e24d  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e254  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004e25b  mov     r8d, eax
0x18004e25e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004e263  lea     rdx, aRtlcopysid; "RtlCopySid"
0x18004e26a  mov     ecx, 8B2h
0x18004e26f  jmp     short loc_18004E2E2
0x18004e271  mov     eax, cs:?g_ulTestFlags@@3KA; ulong g_ulTestFlags
0x18004e277  test    al, 1
0x18004e279  jnz     loc_18004E31A
0x18004e27f  xor     r8d, r8d; Flags
0x18004e282  lea     rcx, ?FlushIdentityCacheWkItem@@YAKPEAX@Z; Function
0x18004e289  mov     rdx, rdi; Context
0x18004e28c  call    cs:__imp_QueueUserWorkItem
0x18004e292  test    eax, eax
0x18004e294  jnz     loc_18004E322
0x18004e29a  call    cs:__imp_GetLastError
0x18004e2a0  test    eax, eax
0x18004e2a2  jg      short loc_18004E2AE
0x18004e2a4  call    cs:__imp_GetLastError
0x18004e2aa  mov     ebx, eax
0x18004e2ac  jmp     short loc_18004E2BD
0x18004e2ae  call    cs:__imp_GetLastError
0x18004e2b4  movzx   ebx, ax
0x18004e2b7  or      ebx, 0C0070000h
0x18004e2bd  xor     r11d, r11d
0x18004e2c0  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e2c7  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004e2ce  mov     r8d, ebx
0x18004e2d1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004e2d6  lea     rdx, aQueueuserworki; "QueueUserWorkItem"
0x18004e2dd  mov     ecx, 8BCh
0x18004e2e2  mov     r9, rax
0x18004e2e5  lea     rax, Class
0x18004e2ec  mov     [rsp+48h+var_18], rax
0x18004e2f1  mov     [rsp+48h+var_20], rdx
0x18004e2f6  mov     rdx, r10
0x18004e2f9  mov     [rsp+48h+var_28], ecx
0x18004e2fd  mov     rcx, r11
0x18004e300  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004e305  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004e30c  mov     rcx, rdi
0x18004e30f  mov     rax, [rax+30h]
0x18004e313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e318  jmp     short loc_18004E324
0x18004e31a  mov     rcx, rdi; Parameter
0x18004e31d  call    ?FlushIdentityCacheWkItem@@YAKPEAX@Z; FlushIdentityCacheWkItem(void *)
0x18004e322  xor     ebx, ebx
0x18004e324  mov     rsi, [rsp+48h+arg_8]
0x18004e329  mov     eax, ebx
0x18004e32b  mov     rbx, [rsp+48h+arg_0]
0x18004e330  add     rsp, 40h
0x18004e334  pop     rdi
0x18004e335  retn
```
