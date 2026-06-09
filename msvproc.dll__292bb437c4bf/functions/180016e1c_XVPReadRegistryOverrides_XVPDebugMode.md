# XVPReadRegistryOverrides(XVPDebugMode &)

- ea: `0x180016e1c`
- end: `0x180016f8c`
- name: `?XVPReadRegistryOverrides@@YAXAEAW4XVPDebugMode@@@Z`
- size: `368`
- prototype: `void __fastcall(enum XVPDebugMode *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800166c0`
- `0x180060600`

## callees

- `0x180016e1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016f29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016f29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016e6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016e6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ea7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ee1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016f1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ea7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ee1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016f1b`

## string_xrefs

- `0x180016e94`: `EnforceSoftwarePath`

## pseudocode

```c
void __fastcall XVPReadRegistryOverrides(enum XVPDebugMode *a1)
{
  int v2; // r14d
  int v3; // esi
  int v4; // edi
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  cbData = 4;
  Type = 4;
  Data = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Media Foundation\\Platform\\XVP", 0, 1u, &hKey) )
  {
LABEL_13:
    *(_DWORD *)a1 = 0;
    return;
  }
  v2 = 0;
  v3 = 0;
  v4 = 0;
  if ( !RegQueryValueExW(hKey, L"EnforceSoftwarePath", 0, &Type, (LPBYTE)&Data, &cbData) )
    LOBYTE(v2) = Data != 0;
  Type = 4;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"DisableShaderFallback", 0, &Type, (LPBYTE)&Data, &cbData) )
    LOBYTE(v3) = Data != 0;
  Type = 4;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"forceShaderFallback", 0, &Type, (LPBYTE)&Data, &cbData) )
    LOBYTE(v4) = Data != 0;
  RegCloseKey(hKey);
  if ( v2 )
  {
    *(_DWORD *)a1 = 1;
    return;
  }
  if ( !v4 )
  {
    if ( v3 )
    {
      *(_DWORD *)a1 = 2;
      return;
    }
    goto LABEL_13;
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x180016e1c  mov     [rsp-28h+arg_0], rbx
0x180016e21  push    rbp
0x180016e22  push    rsi
0x180016e23  push    rdi
0x180016e24  push    r12
0x180016e26  push    r14
0x180016e28  mov     rbp, rsp
0x180016e2b  sub     rsp, 40h
0x180016e2f  mov     r12d, 4
0x180016e35  mov     [rbp+hKey], 0
0x180016e3d  mov     rbx, rcx
0x180016e40  mov     [rbp+cbData], r12d
0x180016e44  lea     rax, [rbp+hKey]
0x180016e48  mov     [rbp+Type], r12d
0x180016e4c  xor     r8d, r8d; ulOptions
0x180016e4f  mov     [rbp+Data], 0
0x180016e56  lea     r9d, [r12-3]; samDesired
0x180016e5b  mov     [rsp+40h+phkResult], rax; phkResult
0x180016e60  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Media Foun"...
0x180016e67  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016e6e  call    cs:__imp_RegOpenKeyExW
0x180016e74  test    eax, eax
0x180016e76  jnz     loc_180016F5B
0x180016e7c  mov     rcx, [rbp+hKey]; hKey
0x180016e80  lea     rax, [rbp+cbData]
0x180016e84  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180016e89  lea     r9, [rbp+Type]; lpType
0x180016e8d  lea     rax, [rbp+Data]
0x180016e91  xor     r8d, r8d; lpReserved
0x180016e94  lea     rdx, aEnforcesoftwar; "EnforceSoftwarePath"
0x180016e9b  mov     [rsp+40h+phkResult], rax; lpData
0x180016ea0  xor     r14d, r14d
0x180016ea3  xor     esi, esi
0x180016ea5  xor     edi, edi
0x180016ea7  call    cs:__imp_RegQueryValueExW
0x180016ead  test    eax, eax
0x180016eaf  jz      loc_180016F63
0x180016eb5  mov     rcx, [rbp+hKey]; hKey
0x180016eb9  lea     rax, [rbp+cbData]
0x180016ebd  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180016ec2  lea     r9, [rbp+Type]; lpType
0x180016ec6  lea     rax, [rbp+Data]
0x180016eca  mov     [rbp+Type], r12d
0x180016ece  xor     r8d, r8d; lpReserved
0x180016ed1  mov     [rsp+40h+phkResult], rax; lpData
0x180016ed6  lea     rdx, aDisableshaderf; "DisableShaderFallback"
0x180016edd  mov     [rbp+cbData], r12d
0x180016ee1  call    cs:__imp_RegQueryValueExW
0x180016ee7  test    eax, eax
0x180016ee9  jz      loc_180016F6F
0x180016eef  mov     rcx, [rbp+hKey]; hKey
0x180016ef3  lea     rax, [rbp+cbData]
0x180016ef7  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180016efc  lea     r9, [rbp+Type]; lpType
0x180016f00  lea     rax, [rbp+Data]
0x180016f04  mov     [rbp+Type], r12d
0x180016f08  xor     r8d, r8d; lpReserved
0x180016f0b  mov     [rsp+40h+phkResult], rax; lpData
0x180016f10  lea     rdx, aForceshaderfal; "forceShaderFallback"
0x180016f17  mov     [rbp+cbData], r12d
0x180016f1b  call    cs:__imp_RegQueryValueExW
0x180016f21  test    eax, eax
0x180016f23  jz      short loc_180016F7B
0x180016f25  mov     rcx, [rbp+hKey]; hKey
0x180016f29  call    cs:__imp_RegCloseKey
0x180016f2f  test    r14d, r14d
0x180016f32  jz      short loc_180016F4B
0x180016f34  mov     dword ptr [rbx], 1
0x180016f3a  mov     rbx, [rsp+40h+arg_0]
0x180016f3f  add     rsp, 40h
0x180016f43  pop     r14
0x180016f45  pop     r12
0x180016f47  pop     rdi
0x180016f48  pop     rsi
0x180016f49  pop     rbp
0x180016f4a  retn
0x180016f4b  test    edi, edi
0x180016f4d  jnz     short loc_180016F84
0x180016f4f  test    esi, esi
0x180016f51  jz      short loc_180016F5B
0x180016f53  mov     dword ptr [rbx], 2
0x180016f59  jmp     short loc_180016F3A
0x180016f5b  mov     dword ptr [rbx], 0
0x180016f61  jmp     short loc_180016F3A
0x180016f63  cmp     [rbp+Data], esi
0x180016f66  setnz   r14b
0x180016f6a  jmp     loc_180016EB5
0x180016f6f  cmp     [rbp+Data], esi
0x180016f72  setnz   sil
0x180016f76  jmp     loc_180016EEF
0x180016f7b  cmp     [rbp+Data], edi
0x180016f7e  setnz   dil
0x180016f82  jmp     short loc_180016F25
0x180016f84  mov     dword ptr [rbx], 3
0x180016f8a  jmp     short loc_180016F3A
```
