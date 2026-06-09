# IsJScript9LegacyEnabled(int *)

- ea: `0x180074264`
- end: `0x1800743c3`
- name: `?IsJScript9LegacyEnabled@@YAXPEAH@Z`
- size: `351`
- prototype: `void __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074580`

## callees

- `0x180074264`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x1800742af`
- `ADVAPI32!RegOpenKeyExA` at `0x180074342`
- `ADVAPI32!RegOpenKeyExA` at `0x1800742af`
- `ADVAPI32!RegOpenKeyExA` at `0x180074342`
- `ADVAPI32!RegCloseKey` at `0x180074302`
- `ADVAPI32!RegCloseKey` at `0x180074396`
- `ADVAPI32!RegCloseKey` at `0x180074302`
- `ADVAPI32!RegCloseKey` at `0x180074396`
- `ADVAPI32!RegQueryValueExA` at `0x1800742f0`
- `ADVAPI32!RegQueryValueExA` at `0x180074380`
- `ADVAPI32!RegQueryValueExA` at `0x1800742f0`
- `ADVAPI32!RegQueryValueExA` at `0x180074380`

## string_xrefs

- `0x1800742e2`: `JScriptReplacement`
- `0x18007435d`: `JScriptReplacement`

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
0x180074264  push    rbp
0x180074266  push    rbx
0x180074267  push    rsi
0x180074268  push    rdi
0x180074269  push    r14
0x18007426b  mov     rbp, rsp
0x18007426e  sub     rsp, 40h
0x180074272  mov     r14, rcx
0x180074275  mov     [rbp+hKey], 0
0x18007427d  lea     rax, [rbp+hKey]
0x180074281  mov     [rbp+Data], 0
0x180074288  xor     esi, esi
0x18007428a  mov     [rbp+arg_8], 0
0x180074291  mov     [rcx], esi
0x180074293  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x18007429a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800742a1  mov     [rsp+40h+phkResult], rax; phkResult
0x1800742a6  mov     r9d, 20019h; samDesired
0x1800742ac  xor     r8d, r8d; ulOptions
0x1800742af  call    cs:__imp_RegOpenKeyExA
0x1800742b6  nop     dword ptr [rax+rax+00h]
0x1800742bb  lea     edi, [rsi+1]
0x1800742be  test    eax, eax
0x1800742c0  jnz     short loc_180074322
0x1800742c2  mov     rcx, [rbp+hKey]; hKey
0x1800742c6  lea     rax, [rbp+cbData]
0x1800742ca  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800742cf  lea     r9, [rbp+Type]; lpType
0x1800742d3  lea     rax, [rbp+Data]
0x1800742d7  mov     [rbp+Type], esi
0x1800742da  xor     r8d, r8d; lpReserved
0x1800742dd  mov     [rsp+40h+phkResult], rax; lpData
0x1800742e2  lea     rdx, aJscriptreplace; "JScriptReplacement"
0x1800742e9  mov     [rbp+cbData], 4
0x1800742f0  call    cs:__imp_RegQueryValueExA
0x1800742f7  nop     dword ptr [rax+rax+00h]
0x1800742fc  mov     rcx, [rbp+hKey]; hKey
0x180074300  mov     ebx, eax
0x180074302  call    cs:__imp_RegCloseKey
0x180074309  nop     dword ptr [rax+rax+00h]
0x18007430e  cmp     ebx, 2
0x180074311  setnz   sil
0x180074315  jz      short loc_180074322
0x180074317  mov     eax, [rbp+Data]
0x18007431a  test    eax, eax
0x18007431c  jnz     loc_1800743A9
0x180074322  lea     rax, [rbp+hKey]
0x180074326  mov     r9d, 20019h; samDesired
0x18007432c  xor     r8d, r8d; ulOptions
0x18007432f  mov     [rsp+40h+phkResult], rax; phkResult
0x180074334  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Internet"...
0x18007433b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180074342  call    cs:__imp_RegOpenKeyExA
0x180074349  nop     dword ptr [rax+rax+00h]
0x18007434e  test    eax, eax
0x180074350  jnz     short loc_1800743A2
0x180074352  mov     rcx, [rbp+hKey]; hKey
0x180074356  lea     r9, [rbp+Type]; lpType
0x18007435a  mov     [rbp+Type], eax
0x18007435d  lea     rdx, aJscriptreplace; "JScriptReplacement"
0x180074364  lea     rax, [rbp+cbData]
0x180074368  mov     [rbp+cbData], 4
0x18007436f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180074374  xor     r8d, r8d; lpReserved
0x180074377  lea     rax, [rbp+arg_8]
0x18007437b  mov     [rsp+40h+phkResult], rax; lpData
0x180074380  call    cs:__imp_RegQueryValueExA
0x180074387  nop     dword ptr [rax+rax+00h]
0x18007438c  mov     rcx, [rbp+hKey]; hKey
0x180074390  cmp     eax, 2
0x180074393  cmovnz  esi, edi
0x180074396  call    cs:__imp_RegCloseKey
0x18007439d  nop     dword ptr [rax+rax+00h]
0x1800743a2  test    esi, esi
0x1800743a4  jz      short loc_1800743B4
0x1800743a6  mov     eax, [rbp+Data]
0x1800743a9  cmp     eax, edi
0x1800743ab  jz      short loc_1800743B4
0x1800743ad  cmp     [rbp+arg_8], edi
0x1800743b0  jz      short loc_1800743B4
0x1800743b2  xor     edi, edi
0x1800743b4  mov     [r14], edi
0x1800743b7  add     rsp, 40h
0x1800743bb  pop     r14
0x1800743bd  pop     rdi
0x1800743be  pop     rsi
0x1800743bf  pop     rbx
0x1800743c0  pop     rbp
0x1800743c1  retn
```
