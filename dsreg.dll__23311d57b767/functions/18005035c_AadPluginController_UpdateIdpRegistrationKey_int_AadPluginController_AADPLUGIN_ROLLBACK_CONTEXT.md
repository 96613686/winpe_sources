# AadPluginController::UpdateIdpRegistrationKey(int,AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *)

- ea: `0x18005035c`
- end: `0x18005053b`
- name: `?UpdateIdpRegistrationKey@AadPluginController@@AEAAJHPEAU_AADPLUGIN_ROLLBACK_CONTEXT@1@@Z`
- size: `479`
- prototype: `__int64 __fastcall(AadPluginController *__hidden this, int, struct AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004ecc0`
- `0x18004f068`
- `0x180054738`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x1800372c4`
- `0x18005035c`
- `0x18008cf20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800503da`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800503da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050446`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050446`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050509`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050509`

## string_xrefs

- `0x1800503ac`: `AadPluginController::OpenAadIdpRegistrationKey`
- `0x1800504b5`: `RegDeleteValueW`
- `0x180050381`: `AadPluginController::UpdateIdpRegistrationKey`
- `0x1800503b3`: `AadPluginController::UpdateIdpRegistrationKey`
- `0x180050404`: `AadPluginController::UpdateIdpRegistrationKey`
- `0x180050473`: `AadPluginController::UpdateIdpRegistrationKey`
- `0x1800504d3`: `AadPluginController::UpdateIdpRegistrationKey`
- `0x180050512`: `AadPluginController::UpdateIdpRegistrationKey`
- `0x180050388`: `%s: AadPluginController::UpdateIdpRegistrationKey does not disable the AAD plugin on unjoin.`
- `0x1800503d0`: `LoginUri`
- `0x18005040b`: `%s: The registry value "%s\%s@%s"does not exist. Nothing to delete.`
- `0x1800504da`: `%s: RegDeleteValueW failed with error code: 0x%08x. Path: "%s\%s@%s".`
- `0x180050461`: `RegSetValueExW`
- `0x18005047e`: `%s: RegSetValueExW failed with error code: 0x%08x. Path: "%s\%s@%s". Value: %d.`

## pseudocode

```c
__int64 __fastcall AadPluginController::UpdateIdpRegistrationKey(
        AadPluginController *this,
        int a2,
        struct AadPluginController::_AADPLUGIN_ROLLBACK_CONTEXT *a3)
{
  unsigned int v3; // ebx
  unsigned int v5; // edi
  int v6; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+78h] [rbp+10h] BYREF

  v3 = 0;
  hKey = 0;
  if ( !a2 )
  {
    v5 = 0;
    Logger::TraceVerbose(
      (wchar_t *)L"%s: AadPluginController::UpdateIdpRegistrationKey does not disable the AAD plugin on unjoin.",
      L"AadPluginController::UpdateIdpRegistrationKey");
    goto LABEL_16;
  }
  v6 = AadPluginController::OpenAadIdpRegistrationKey(&hKey);
  v5 = v6;
  if ( v6 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"AadPluginController::UpdateIdpRegistrationKey",
      L"AadPluginController::OpenAadIdpRegistrationKey",
      (unsigned int)v6);
    goto LABEL_16;
  }
  v7 = RegDeleteValueW(hKey, L"LoginUri");
  v3 = v7;
  if ( v7 == 2 )
  {
    Logger::TraceVerbose(
      (wchar_t *)L"%s: The registry value \"%s\\%s@%s\"does not exist. Nothing to delete.",
      L"AadPluginController::UpdateIdpRegistrationKey",
      L"HKEY_LOCAL_MACHINE",
      L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
      L"LoginUri");
  }
  else if ( v7 )
  {
    Logger::WriteRegistryFailureEvent(
      v7,
      L"RegDeleteValueW",
      L"HKEY_LOCAL_MACHINE",
      L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
      L"LoginUri");
    Logger::TraceError(
      L"%s: RegDeleteValueW failed with error code: 0x%08x. Path: \"%s\\%s@%s\".",
      L"AadPluginController::UpdateIdpRegistrationKey",
      v3,
      L"HKEY_LOCAL_MACHINE",
      L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
      L"LoginUri");
LABEL_9:
    if ( (int)v3 > 0 )
      v5 = (unsigned __int16)v3 | 0x80070000;
    else
      v5 = v3;
    goto LABEL_16;
  }
  Data = 1;
  v8 = RegSetValueExW(hKey, L"Enabled", 0, 4u, (const BYTE *)&Data, 4u);
  v3 = v8;
  if ( v8 )
  {
    Logger::WriteRegistryFailureEvent(
      v8,
      L"RegSetValueExW",
      L"HKEY_LOCAL_MACHINE",
      L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
      L"Enabled");
    Logger::TraceError(
      L"%s: RegSetValueExW failed with error code: 0x%08x. Path: \"%s\\%s@%s\". Value: %d.",
      L"AadPluginController::UpdateIdpRegistrationKey",
      v3,
      L"HKEY_LOCAL_MACHINE",
      L"Software\\Microsoft\\IdentityStore\\LoadParameters\\{B16898C6-A148-4967-9171-64D755DA8520}",
      L"Enabled",
      Data);
    goto LABEL_9;
  }
  if ( a3 )
    *((_DWORD *)a3 + 4) = 0;
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"AadPluginController::UpdateIdpRegistrationKey", v5);
  return v3;
}

```

## disassembly

```asm
0x18005035c  mov     [rsp+arg_10], rbx
0x180050361  mov     [rsp+hKey], rcx
0x180050366  push    rbp
0x180050367  push    rsi
0x180050368  push    rdi
0x180050369  push    r14
0x18005036b  push    r15
0x18005036d  sub     rsp, 40h
0x180050371  xor     ebx, ebx
0x180050373  mov     rsi, r8
0x180050376  mov     [rsp+68h+hKey], rbx
0x18005037b  test    edx, edx
0x18005037d  jnz     short loc_180050399
0x18005037f  xor     edi, edi
0x180050381  lea     rdx, aAadplugincontr_8; "AadPluginController::UpdateIdpRegistrat"...
0x180050388  lea     rcx, aSAadplugincont_1; "%s: AadPluginController::UpdateIdpRegis"...
0x18005038f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180050394  jmp     loc_1800504FF
0x180050399  lea     rcx, [rsp+68h+hKey]; HKEY *
0x18005039e  call    ?OpenAadIdpRegistrationKey@AadPluginController@@CAJPEAPEAUHKEY__@@@Z; AadPluginController::OpenAadIdpRegistrationKey(HKEY__ * *)
0x1800503a3  mov     edi, eax
0x1800503a5  test    eax, eax
0x1800503a7  jns     short loc_1800503CB
0x1800503a9  mov     r9d, eax
0x1800503ac  lea     r8, aAadplugincontr_1; "AadPluginController::OpenAadIdpRegistra"...
0x1800503b3  lea     rdx, aAadplugincontr_8; "AadPluginController::UpdateIdpRegistrat"...
0x1800503ba  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800503c1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800503c6  jmp     loc_1800504FF
0x1800503cb  mov     rcx, [rsp+68h+hKey]; hKey
0x1800503d0  lea     rbp, aLoginuri; "LoginUri"
0x1800503d7  mov     rdx, rbp; lpValueName
0x1800503da  call    cs:__imp_RegDeleteValueW
0x1800503e0  lea     r15, aSoftwareMicros_7; "Software\\Microsoft\\IdentityStore\\Loa"...
0x1800503e7  mov     ebx, eax
0x1800503e9  lea     r14, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x1800503f0  cmp     eax, 2
0x1800503f3  jnz     loc_1800504A2
0x1800503f9  mov     r9, r15
0x1800503fc  mov     [rsp+68h+lpData], rbp
0x180050401  mov     r8, r14
0x180050404  lea     rdx, aAadplugincontr_8; "AadPluginController::UpdateIdpRegistrat"...
0x18005040b  lea     rcx, aSTheRegistryVa_0; "%s: The registry value \"%s\\%s@%s\"doe"...
0x180050412  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180050417  mov     rcx, [rsp+68h+hKey]; hKey
0x18005041c  lea     rax, [rsp+68h+Data]
0x180050421  mov     r9d, 4; dwType
0x180050427  mov     [rsp+68h+Data], 1
0x18005042f  mov     [rsp+68h+cbData], r9d; cbData
0x180050434  lea     rbp, aEnabled; "Enabled"
0x18005043b  mov     rdx, rbp; lpValueName
0x18005043e  mov     [rsp+68h+lpData], rax; lpData
0x180050443  xor     r8d, r8d; Reserved
0x180050446  call    cs:__imp_RegSetValueExW
0x18005044c  mov     ebx, eax
0x18005044e  test    eax, eax
0x180050450  jz      loc_1800504F3
0x180050456  mov     r9, r15; unsigned __int16 *
0x180050459  mov     [rsp+68h+lpData], rbp; unsigned __int16 *
0x18005045e  mov     r8, r14; unsigned __int16 *
0x180050461  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x180050468  mov     ecx, eax; unsigned int
0x18005046a  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG000@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x18005046f  mov     eax, [rsp+68h+Data]
0x180050473  lea     rdx, aAadplugincontr_8; "AadPluginController::UpdateIdpRegistrat"...
0x18005047a  mov     [rsp+68h+var_38], eax
0x18005047e  lea     rcx, aSRegsetvalueex; "%s: RegSetValueExW failed with error co"...
0x180050485  mov     qword ptr [rsp+68h+cbData], rbp
0x18005048a  mov     r9, r14
0x18005048d  mov     r8d, ebx
0x180050490  mov     [rsp+68h+lpData], r15
0x180050495  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005049a  test    ebx, ebx
0x18005049c  jg      short loc_1800504E8
0x18005049e  mov     edi, ebx
0x1800504a0  jmp     short loc_1800504FF
0x1800504a2  test    ebx, ebx
0x1800504a4  jz      loc_180050417
0x1800504aa  mov     r9, r15; unsigned __int16 *
0x1800504ad  mov     [rsp+68h+lpData], rbp; unsigned __int16 *
0x1800504b2  mov     r8, r14; unsigned __int16 *
0x1800504b5  lea     rdx, aRegdeletevalue; "RegDeleteValueW"
0x1800504bc  mov     ecx, ebx; unsigned int
0x1800504be  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG000@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800504c3  mov     r9, r14
0x1800504c6  mov     qword ptr [rsp+68h+cbData], rbp
0x1800504cb  mov     r8d, ebx
0x1800504ce  mov     [rsp+68h+lpData], r15
0x1800504d3  lea     rdx, aAadplugincontr_8; "AadPluginController::UpdateIdpRegistrat"...
0x1800504da  lea     rcx, aSRegdeletevalu; "%s: RegDeleteValueW failed with error c"...
0x1800504e1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800504e6  jmp     short loc_18005049A
0x1800504e8  movzx   edi, bx
0x1800504eb  or      edi, 80070000h
0x1800504f1  jmp     short loc_1800504FF
0x1800504f3  test    rsi, rsi
0x1800504f6  jz      short loc_1800504FF
0x1800504f8  mov     dword ptr [rsi+10h], 0
0x1800504ff  mov     rcx, [rsp+68h+hKey]; hKey
0x180050504  test    rcx, rcx
0x180050507  jz      short loc_18005050F
0x180050509  call    cs:__imp_RegCloseKey
0x18005050f  mov     r8d, edi
0x180050512  lea     rdx, aAadplugincontr_8; "AadPluginController::UpdateIdpRegistrat"...
0x180050519  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180050520  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180050525  mov     eax, ebx
0x180050527  mov     rbx, [rsp+68h+arg_10]
0x18005052f  add     rsp, 40h
0x180050533  pop     r15
0x180050535  pop     r14
0x180050537  pop     rdi
0x180050538  pop     rsi
0x180050539  pop     rbp
0x18005053a  retn
```
