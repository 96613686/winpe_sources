# CUtils::EnableChildSessionsPolicy(int)

- ea: `0x180083938`
- end: `0x180083a8c`
- name: `?EnableChildSessionsPolicy@CUtils@@SAJH@Z`
- size: `340`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005fa60`
- `0x180083938`

## callees

- `0x1800077a0`
- `0x1800834ec`
- `0x180083938`
- `0x180083bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083a72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083a72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180083a0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180083a0d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800839d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800839d9`

## string_xrefs

- `0x180083a2c`: `RegSetKeyValue failed: 0x%x in %s`

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
0x180083938  mov     rax, rsp
0x18008393b  mov     [rax+8], rbx
0x18008393f  push    rdi
0x180083940  sub     rsp, 50h
0x180083944  mov     edi, ecx
0x180083946  mov     qword ptr [rax+20h], 0
0x18008394e  lea     rcx, [rax+10h]; int *
0x180083952  mov     dword ptr [rax+10h], 0
0x180083959  mov     dword ptr [rax+18h], 0
0x180083960  call    ?IsChildSessionsPolicyEnabled@CUtils@@SAJPEAH@Z; CUtils::IsChildSessionsPolicyEnabled(int *)
0x180083965  mov     ebx, eax
0x180083967  test    eax, eax
0x180083969  jns     short loc_18008397A
0x18008396b  mov     r8d, eax
0x18008396e  lea     rdx, aCutilsIschilds_0; "CUtils::IsChildSessionsPolicyEnabled fa"...
0x180083975  jmp     loc_180083A57
0x18008397a  xor     eax, eax
0x18008397c  cmp     [rsp+58h+arg_8], eax
0x180083980  setz    al
0x180083983  xor     ecx, ecx
0x180083985  test    edi, edi
0x180083987  setz    cl
0x18008398a  cmp     eax, ecx
0x18008398c  jnz     short loc_180083995
0x18008398e  xor     ebx, ebx
0x180083990  jmp     loc_180083A68
0x180083995  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18008399e  lea     rax, [rsp+58h+hKey]
0x1800839a3  mov     [rsp+58h+phkResult], rax; phkResult
0x1800839a8  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x1800839af  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800839b8  xor     r9d, r9d; lpClass
0x1800839bb  mov     [rsp+58h+Data], ecx
0x1800839bf  xor     r8d, r8d; Reserved
0x1800839c2  mov     [rsp+58h+samDesired], 2; samDesired
0x1800839ca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800839d1  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800839d9  call    cs:__imp_RegCreateKeyExW
0x1800839e0  nop     dword ptr [rax+rax+00h]
0x1800839e5  mov     ebx, eax
0x1800839e7  test    eax, eax
0x1800839e9  jnz     short loc_180083A1B
0x1800839eb  mov     rcx, [rsp+58h+hKey]; hKey
0x1800839f0  lea     r9d, [rax+4]; dwType
0x1800839f4  lea     rax, [rsp+58h+Data]
0x1800839f9  mov     [rsp+58h+samDesired], r9d; cbData
0x1800839fe  xor     r8d, r8d; Reserved
0x180083a01  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180083a06  lea     rdx, aFdenychildconn; "fDenyChildConnections"
0x180083a0d  call    cs:__imp_RegSetValueExW
0x180083a14  nop     dword ptr [rax+rax+00h]
0x180083a19  mov     ebx, eax
0x180083a1b  test    ebx, ebx
0x180083a1d  jle     short loc_180083A2A
0x180083a1f  movzx   ebx, bx
0x180083a22  or      ebx, 80070000h
0x180083a28  test    ebx, ebx
0x180083a2a  jns     short loc_180083A35
0x180083a2c  lea     rdx, aRegsetkeyvalue; "RegSetKeyValue failed: 0x%x in %s"
0x180083a33  jmp     short loc_180083A54
0x180083a35  mov     ecx, edi; int
0x180083a37  call    ?EnableChildSessionsCredentialsDelegationPolicy@CUtils@@SAJH@Z; CUtils::EnableChildSessionsCredentialsDelegationPolicy(int)
0x180083a3c  mov     ebx, eax
0x180083a3e  test    eax, eax
0x180083a40  jns     short loc_180083A68
0x180083a42  test    edi, edi
0x180083a44  jz      short loc_180083A4D
0x180083a46  xor     ecx, ecx; int
0x180083a48  call    ?EnableChildSessionsPolicy@CUtils@@SAJH@Z; CUtils::EnableChildSessionsPolicy(int)
0x180083a4d  lea     rdx, aEnablechildses; "EnableChildSessionsCredentialsDelegatio"...
0x180083a54  mov     r8d, ebx
0x180083a57  lea     r9, aCutilsEnablech; "CUtils::EnableChildSessionsPolicy"
0x180083a5e  mov     ecx, 8; int
0x180083a63  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180083a68  mov     rcx, [rsp+58h+hKey]; hKey
0x180083a6d  test    rcx, rcx
0x180083a70  jz      short loc_180083A7E
0x180083a72  call    cs:__imp_RegCloseKey
0x180083a79  nop     dword ptr [rax+rax+00h]
0x180083a7e  mov     eax, ebx
0x180083a80  mov     rbx, [rsp+58h+arg_0]
0x180083a85  add     rsp, 50h
0x180083a89  pop     rdi
0x180083a8a  retn
```
