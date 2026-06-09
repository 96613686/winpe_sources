# CUtils::EnableChildSessionsPolicy(int)

- ea: `0x18007edc0`
- end: `0x18007ef01`
- name: `?EnableChildSessionsPolicy@CUtils@@SAJH@Z`
- size: `321`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005c020`
- `0x18007edc0`

## callees

- `0x1800074c0`
- `0x18007e9dc`
- `0x18007edc0`
- `0x18007f030`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007eeee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007eeee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007ee8f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007ee8f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007ee61`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007ee61`

## string_xrefs

- `0x18007eea8`: `RegSetKeyValue failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::EnableChildSessionsPolicy(int a1)
{
  int IsChildSessionsPolicyEnabled; // eax
  int v3; // ebx
  bool v4; // sf
  const char *v5; // rdx
  int v7; // [rsp+68h] [rbp+10h] BYREF
  BOOL Data; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v7 = 0;
  Data = 0;
  IsChildSessionsPolicyEnabled = CUtils::IsChildSessionsPolicyEnabled(&v7);
  v3 = IsChildSessionsPolicyEnabled;
  if ( IsChildSessionsPolicyEnabled < 0 )
  {
    _DbgPrintMessage(
      8,
      "CUtils::IsChildSessionsPolicyEnabled failed: 0x%x in %s",
      (unsigned int)IsChildSessionsPolicyEnabled,
      "CUtils::EnableChildSessionsPolicy");
    goto LABEL_16;
  }
  if ( (v7 == 0) == (a1 == 0) )
  {
    v3 = 0;
    goto LABEL_16;
  }
  Data = a1 == 0;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  if ( !v3 )
    v3 = RegSetValueExW(hKey, L"fDenyChildConnections", 0, 4u, (const BYTE *)&Data, 4u);
  v4 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3 | 0x80070000;
    v4 = v3 < 0;
  }
  if ( v4 )
  {
    v5 = "RegSetKeyValue failed: 0x%x in %s";
  }
  else
  {
    v3 = CUtils::EnableChildSessionsCredentialsDelegationPolicy(a1);
    if ( v3 >= 0 )
      goto LABEL_16;
    if ( a1 )
      CUtils::EnableChildSessionsPolicy(0);
    v5 = "EnableChildSessionsCredentialsDelegationPolicy failed: 0x%x in %s";
  }
  _DbgPrintMessage(8, v5, (unsigned int)v3, "CUtils::EnableChildSessionsPolicy");
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18007edc0  mov     rax, rsp
0x18007edc3  mov     [rax+8], rbx
0x18007edc7  push    rdi
0x18007edc8  sub     rsp, 50h
0x18007edcc  mov     edi, ecx
0x18007edce  mov     qword ptr [rax+20h], 0
0x18007edd6  lea     rcx, [rax+10h]; int *
0x18007edda  mov     dword ptr [rax+10h], 0
0x18007ede1  mov     dword ptr [rax+18h], 0
0x18007ede8  call    ?IsChildSessionsPolicyEnabled@CUtils@@SAJPEAH@Z; CUtils::IsChildSessionsPolicyEnabled(int *)
0x18007eded  mov     ebx, eax
0x18007edef  test    eax, eax
0x18007edf1  jns     short loc_18007EE02
0x18007edf3  mov     r8d, eax
0x18007edf6  lea     rdx, aCutilsIschilds_0; "CUtils::IsChildSessionsPolicyEnabled fa"...
0x18007edfd  jmp     loc_18007EED3
0x18007ee02  xor     eax, eax
0x18007ee04  cmp     [rsp+58h+arg_8], eax
0x18007ee08  setz    al
0x18007ee0b  xor     ecx, ecx
0x18007ee0d  test    edi, edi
0x18007ee0f  setz    cl
0x18007ee12  cmp     eax, ecx
0x18007ee14  jnz     short loc_18007EE1D
0x18007ee16  xor     ebx, ebx
0x18007ee18  jmp     loc_18007EEE4
0x18007ee1d  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18007ee26  lea     rax, [rsp+58h+hKey]
0x18007ee2b  mov     [rsp+58h+phkResult], rax; phkResult
0x18007ee30  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18007ee37  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007ee40  xor     r9d, r9d; lpClass
0x18007ee43  mov     [rsp+58h+Data], ecx
0x18007ee47  xor     r8d, r8d; Reserved
0x18007ee4a  mov     [rsp+58h+samDesired], 2; samDesired
0x18007ee52  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007ee59  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18007ee61  call    cs:__imp_RegCreateKeyExW
0x18007ee67  mov     ebx, eax
0x18007ee69  test    eax, eax
0x18007ee6b  jnz     short loc_18007EE97
0x18007ee6d  mov     rcx, [rsp+58h+hKey]; hKey
0x18007ee72  lea     r9d, [rax+4]; dwType
0x18007ee76  lea     rax, [rsp+58h+Data]
0x18007ee7b  mov     [rsp+58h+samDesired], r9d; cbData
0x18007ee80  xor     r8d, r8d; Reserved
0x18007ee83  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18007ee88  lea     rdx, aFdenychildconn; "fDenyChildConnections"
0x18007ee8f  call    cs:__imp_RegSetValueExW
0x18007ee95  mov     ebx, eax
0x18007ee97  test    ebx, ebx
0x18007ee99  jle     short loc_18007EEA6
0x18007ee9b  movzx   ebx, bx
0x18007ee9e  or      ebx, 80070000h
0x18007eea4  test    ebx, ebx
0x18007eea6  jns     short loc_18007EEB1
0x18007eea8  lea     rdx, aRegsetkeyvalue; "RegSetKeyValue failed: 0x%x in %s"
0x18007eeaf  jmp     short loc_18007EED0
0x18007eeb1  mov     ecx, edi; int
0x18007eeb3  call    ?EnableChildSessionsCredentialsDelegationPolicy@CUtils@@SAJH@Z; CUtils::EnableChildSessionsCredentialsDelegationPolicy(int)
0x18007eeb8  mov     ebx, eax
0x18007eeba  test    eax, eax
0x18007eebc  jns     short loc_18007EEE4
0x18007eebe  test    edi, edi
0x18007eec0  jz      short loc_18007EEC9
0x18007eec2  xor     ecx, ecx; int
0x18007eec4  call    ?EnableChildSessionsPolicy@CUtils@@SAJH@Z; CUtils::EnableChildSessionsPolicy(int)
0x18007eec9  lea     rdx, aEnablechildses; "EnableChildSessionsCredentialsDelegatio"...
0x18007eed0  mov     r8d, ebx
0x18007eed3  lea     r9, aCutilsEnablech; "CUtils::EnableChildSessionsPolicy"
0x18007eeda  mov     ecx, 8; int
0x18007eedf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007eee4  mov     rcx, [rsp+58h+hKey]; hKey
0x18007eee9  test    rcx, rcx
0x18007eeec  jz      short loc_18007EEF4
0x18007eeee  call    cs:__imp_RegCloseKey
0x18007eef4  mov     eax, ebx
0x18007eef6  mov     rbx, [rsp+58h+arg_0]
0x18007eefb  add     rsp, 50h
0x18007eeff  pop     rdi
0x18007ef00  retn
```
