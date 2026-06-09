# IsJScript9LegacyEnabled(int *)

- ea: `0x180072e14`
- end: `0x180072f4a`
- name: `?IsJScript9LegacyEnabled@@YAXPEAH@Z`
- size: `310`
- prototype: `void __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073100`

## callees

- `0x180072e14`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180072e5f`
- `ADVAPI32!RegOpenKeyExA` at `0x180072edc`
- `ADVAPI32!RegOpenKeyExA` at `0x180072e5f`
- `ADVAPI32!RegOpenKeyExA` at `0x180072edc`
- `ADVAPI32!RegCloseKey` at `0x180072ea6`
- `ADVAPI32!RegCloseKey` at `0x180072f24`
- `ADVAPI32!RegCloseKey` at `0x180072ea6`
- `ADVAPI32!RegCloseKey` at `0x180072f24`
- `ADVAPI32!RegQueryValueExA` at `0x180072e9a`
- `ADVAPI32!RegQueryValueExA` at `0x180072f14`
- `ADVAPI32!RegQueryValueExA` at `0x180072e9a`
- `ADVAPI32!RegQueryValueExA` at `0x180072f14`

## string_xrefs

- `0x180072e8c`: `JScriptReplacement`
- `0x180072ef1`: `JScriptReplacement`

## pseudocode

```c
void __fastcall IsJScript9LegacyEnabled(int *a1)
{
  int v2; // esi
  int v3; // edi
  LSTATUS v4; // ebx
  int v5; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  int v8; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  hKey[0] = 0;
  Data = 0;
  v2 = 0;
  v8 = 0;
  *a1 = 0;
  v3 = 1;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, hKey) )
  {
    Type = 0;
    cbData = 4;
    v4 = RegQueryValueExA(hKey[0], "JScriptReplacement", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey[0]);
    LOBYTE(v2) = v4 != 2;
    if ( v4 != 2 )
    {
      v5 = Data;
      if ( Data )
      {
LABEL_10:
        if ( v5 != 1 && v8 != 1 )
          v3 = 0;
        goto LABEL_13;
      }
    }
  }
  if ( !RegOpenKeyExA(HKEY_CURRENT_USER, "Software\\Policies\\Microsoft\\Internet Explorer\\Main", 0, 0x20019u, hKey) )
  {
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExA(hKey[0], "JScriptReplacement", 0, &Type, (LPBYTE)&v8, &cbData) != 2 )
      v2 = 1;
    RegCloseKey(hKey[0]);
  }
  if ( v2 )
  {
    v5 = Data;
    goto LABEL_10;
  }
LABEL_13:
  *a1 = v3;
}

```

## disassembly

```asm
0x180072e14  push    rbp
0x180072e16  push    rbx
0x180072e17  push    rsi
0x180072e18  push    rdi
0x180072e19  push    r14
0x180072e1b  mov     rbp, rsp
0x180072e1e  sub     rsp, 40h
0x180072e22  mov     r14, rcx
0x180072e25  mov     [rbp+hKey], 0
0x180072e2d  lea     rax, [rbp+hKey]
0x180072e31  mov     [rbp+Data], 0
0x180072e38  xor     esi, esi
0x180072e3a  mov     [rbp+arg_8], 0
0x180072e41  mov     [rcx], esi
0x180072e43  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x180072e4a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072e51  mov     [rsp+40h+phkResult], rax; phkResult
0x180072e56  mov     r9d, 20019h; samDesired
0x180072e5c  xor     r8d, r8d; ulOptions
0x180072e5f  call    cs:__imp_RegOpenKeyExA
0x180072e65  lea     edi, [rsi+1]
0x180072e68  test    eax, eax
0x180072e6a  jnz     short loc_180072EBC
0x180072e6c  mov     rcx, [rbp+hKey]; hKey
0x180072e70  lea     rax, [rbp+cbData]
0x180072e74  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180072e79  lea     r9, [rbp+Type]; lpType
0x180072e7d  lea     rax, [rbp+Data]
0x180072e81  mov     [rbp+Type], esi
0x180072e84  xor     r8d, r8d; lpReserved
0x180072e87  mov     [rsp+40h+phkResult], rax; lpData
0x180072e8c  lea     rdx, aJscriptreplace; "JScriptReplacement"
0x180072e93  mov     [rbp+cbData], 4
0x180072e9a  call    cs:__imp_RegQueryValueExA
0x180072ea0  mov     rcx, [rbp+hKey]; hKey
0x180072ea4  mov     ebx, eax
0x180072ea6  call    cs:__imp_RegCloseKey
0x180072eac  cmp     ebx, 2
0x180072eaf  setnz   sil
0x180072eb3  jz      short loc_180072EBC
0x180072eb5  mov     eax, [rbp+Data]
0x180072eb8  test    eax, eax
0x180072eba  jnz     short loc_180072F31
0x180072ebc  lea     rax, [rbp+hKey]
0x180072ec0  mov     r9d, 20019h; samDesired
0x180072ec6  xor     r8d, r8d; ulOptions
0x180072ec9  mov     [rsp+40h+phkResult], rax; phkResult
0x180072ece  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x180072ed5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180072edc  call    cs:__imp_RegOpenKeyExA
0x180072ee2  test    eax, eax
0x180072ee4  jnz     short loc_180072F2A
0x180072ee6  mov     rcx, [rbp+hKey]; hKey
0x180072eea  lea     r9, [rbp+Type]; lpType
0x180072eee  mov     [rbp+Type], eax
0x180072ef1  lea     rdx, aJscriptreplace; "JScriptReplacement"
0x180072ef8  lea     rax, [rbp+cbData]
0x180072efc  mov     [rbp+cbData], 4
0x180072f03  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180072f08  xor     r8d, r8d; lpReserved
0x180072f0b  lea     rax, [rbp+arg_8]
0x180072f0f  mov     [rsp+40h+phkResult], rax; lpData
0x180072f14  call    cs:__imp_RegQueryValueExA
0x180072f1a  mov     rcx, [rbp+hKey]; hKey
0x180072f1e  cmp     eax, 2
0x180072f21  cmovnz  esi, edi
0x180072f24  call    cs:__imp_RegCloseKey
0x180072f2a  test    esi, esi
0x180072f2c  jz      short loc_180072F3C
0x180072f2e  mov     eax, [rbp+Data]
0x180072f31  cmp     eax, edi
0x180072f33  jz      short loc_180072F3C
0x180072f35  cmp     [rbp+arg_8], edi
0x180072f38  jz      short loc_180072F3C
0x180072f3a  xor     edi, edi
0x180072f3c  mov     [r14], edi
0x180072f3f  add     rsp, 40h
0x180072f43  pop     r14
0x180072f45  pop     rdi
0x180072f46  pop     rsi
0x180072f47  pop     rbx
0x180072f48  pop     rbp
0x180072f49  retn
```
