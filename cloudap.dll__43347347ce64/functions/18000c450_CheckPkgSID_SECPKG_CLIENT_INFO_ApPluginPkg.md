# CheckPkgSID(_SECPKG_CLIENT_INFO *,_ApPluginPkg *)

- ea: `0x18000c450`
- end: `0x18000c5f0`
- name: `?CheckPkgSID@@YAJPEAU_SECPKG_CLIENT_INFO@@PEAU_ApPluginPkg@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(struct _SECPKG_CLIENT_INFO *, struct _ApPluginPkg *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800358c0`
- `0x1800476a0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000c450`
- `0x18000d780`
- `0x180081010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18000c4f8`
- `ntdll!RtlEqualSid` at `0x18000c525`
- `ntdll!RtlEqualSid` at `0x18000c4f8`
- `ntdll!RtlEqualSid` at `0x18000c525`

## string_xrefs

- `0x18000c48d`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000c55f`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000c5a6`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x18000c4c1`: `Caller doesnt have TCB privilege`
- `0x18000c586`: `GetCallerPackageSid`
- `0x18000c5d2`: `Caller's SID doesnt match the one registered by the plugin`

## pseudocode

```c
__int64 __fastcall CheckPkgSID(struct _SECPKG_CLIENT_INFO *a1, struct _ApPluginPkg *a2)
{
  PSID v2; // rbx
  void *v4; // rdx
  const char *v6; // r9
  char v7; // al
  const char *v8; // rcx
  bool v9; // zf
  unsigned int CallerPackageSid; // edi
  const char *v12; // rax
  const char *v13; // rax
  PSID Sid2; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v4 = (void *)*((_QWORD *)a2 + 19);
  Sid2 = 0;
  if ( v4 )
  {
    if ( RtlEqualSid(qword_180085590, v4) )
      return 0;
    CallerPackageSid = GetCallerPackageSid(a1->ClientToken, &Sid2);
    if ( CallerPackageSid )
    {
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CallerPackageSid, v12, 1403, "GetCallerPackageSid", &Class);
      v2 = Sid2;
      goto LABEL_14;
    }
    v2 = Sid2;
    if ( !RtlEqualSid(*((PSID *)a2 + 19), Sid2) )
    {
      CallerPackageSid = -1073741790;
      v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp");
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        3221225506LL,
        v13,
        1408,
        "Caller's SID doesnt match the one registered by the plugin",
        &Class);
      goto LABEL_14;
    }
LABEL_13:
    CallerPackageSid = 0;
LABEL_14:
    if ( v2 )
      ((void (__fastcall *)(PSID))g_pLsaFunctionTable->FreeLsaHeap)(v2);
    return CallerPackageSid;
  }
  if ( a1->HasTcbPrivilege )
    goto LABEL_13;
  v6 = "";
  while ( 1 )
  {
    v7 = *(v6 - 1);
    v8 = v6--;
    v9 = v7 == 92;
    if ( v7 == 92 )
      break;
    if ( v6 <= "onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp" )
    {
      v9 = v7 == 92;
      break;
    }
  }
  if ( v9 )
    v6 = v8;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225506LL, v6, 1386, "Caller doesnt have TCB privilege", &Class);
  return 3221225506LL;
}

```

## disassembly

```asm
0x18000c450  mov     [rsp+arg_0], rbx
0x18000c455  mov     [rsp+arg_10], rsi
0x18000c45a  push    rdi
0x18000c45b  sub     rsp, 40h
0x18000c45f  xor     ebx, ebx
0x18000c461  mov     rsi, rdx
0x18000c464  mov     rdx, [rdx+98h]; Sid2
0x18000c46b  mov     rdi, rcx
0x18000c46e  mov     [rsp+48h+Sid2], rbx
0x18000c473  test    rdx, rdx
0x18000c476  jnz     short loc_18000C4F1
0x18000c478  cmp     [rcx+10h], bl
0x18000c47b  jnz     loc_18000C52F
0x18000c481  mov     edi, 0C0000022h
0x18000c486  lea     r9, aOnecoreDsExtCl_16+26h; ""
0x18000c48d  lea     rdx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000c494  movzx   eax, byte ptr [r9-1]
0x18000c499  mov     rcx, r9
0x18000c49c  dec     r9
0x18000c49f  cmp     al, 5Ch ; '\'
0x18000c4a1  jz      short loc_18000C4AA
0x18000c4a3  cmp     r9, rdx
0x18000c4a6  ja      short loc_18000C494
0x18000c4a8  cmp     al, 5Ch ; '\'
0x18000c4aa  lea     rax, Class
0x18000c4b1  cmovz   r9, rcx
0x18000c4b5  mov     [rsp+48h+var_18], rax
0x18000c4ba  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000c4c1  lea     rax, aCallerDoesntHa; "Caller doesnt have TCB privilege"
0x18000c4c8  mov     r8d, edi
0x18000c4cb  mov     [rsp+48h+var_20], rax
0x18000c4d0  xor     ecx, ecx
0x18000c4d2  mov     [rsp+48h+var_28], 56Ah
0x18000c4da  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000c4df  mov     eax, edi
0x18000c4e1  mov     rbx, [rsp+48h+arg_0]
0x18000c4e6  mov     rsi, [rsp+48h+arg_10]
0x18000c4eb  add     rsp, 40h
0x18000c4ef  pop     rdi
0x18000c4f0  retn
0x18000c4f1  lea     rcx, qword_180085590; Sid1
0x18000c4f8  call    cs:__imp_RtlEqualSid
0x18000c4fe  test    al, al
0x18000c500  jnz     short loc_18000C55B
0x18000c502  mov     rcx, [rdi+18h]; TokenHandle
0x18000c506  lea     rdx, [rsp+48h+Sid2]; void **
0x18000c50b  call    ?GetCallerPackageSid@@YAJPEAXPEAPEAX@Z; GetCallerPackageSid(void *,void * *)
0x18000c510  mov     edi, eax
0x18000c512  test    eax, eax
0x18000c514  jnz     short loc_18000C55F
0x18000c516  mov     rbx, [rsp+48h+Sid2]
0x18000c51b  mov     rcx, [rsi+98h]; Sid1
0x18000c522  mov     rdx, rbx; Sid2
0x18000c525  call    cs:__imp_RtlEqualSid
0x18000c52b  test    al, al
0x18000c52d  jz      short loc_18000C5A6
0x18000c52f  xor     edi, edi
0x18000c531  test    rbx, rbx
0x18000c534  jz      short loc_18000C549
0x18000c536  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000c53d  mov     rcx, rbx
0x18000c540  mov     rax, [rax+30h]
0x18000c544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c549  mov     eax, edi
0x18000c54b  mov     rbx, [rsp+48h+arg_0]
0x18000c550  mov     rsi, [rsp+48h+arg_10]
0x18000c555  add     rsp, 40h
0x18000c559  pop     rdi
0x18000c55a  retn
0x18000c55b  xor     eax, eax
0x18000c55d  jmp     short loc_18000C54B
0x18000c55f  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000c566  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c56b  mov     r9, rax
0x18000c56e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000c575  lea     rax, Class
0x18000c57c  mov     r8d, edi
0x18000c57f  mov     [rsp+48h+var_18], rax
0x18000c584  xor     ecx, ecx
0x18000c586  lea     rax, aGetcallerpacka; "GetCallerPackageSid"
0x18000c58d  mov     [rsp+48h+var_20], rax
0x18000c592  mov     [rsp+48h+var_28], 57Bh
0x18000c59a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000c59f  mov     rbx, [rsp+48h+Sid2]
0x18000c5a4  jmp     short loc_18000C531
0x18000c5a6  lea     rcx, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x18000c5ad  mov     edi, 0C0000022h
0x18000c5b2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c5b7  mov     r9, rax
0x18000c5ba  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000c5c1  lea     rax, Class
0x18000c5c8  mov     r8d, edi
0x18000c5cb  mov     [rsp+48h+var_18], rax
0x18000c5d0  xor     ecx, ecx
0x18000c5d2  lea     rax, aCallerSSidDoes; "Caller's SID doesnt match the one regis"...
0x18000c5d9  mov     [rsp+48h+var_20], rax
0x18000c5de  mov     [rsp+48h+var_28], 580h
0x18000c5e6  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000c5eb  jmp     loc_18000C531
```
