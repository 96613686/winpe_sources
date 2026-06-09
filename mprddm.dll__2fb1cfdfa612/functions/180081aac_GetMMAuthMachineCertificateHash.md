# GetMMAuthMachineCertificateHash

- ea: `0x180081aac`
- end: `0x180081b7b`
- name: `GetMMAuthMachineCertificateHash`
- size: `207`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800806f0`

## callees

- `0x180081aac`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180081b6b`
- `ADVAPI32!RegCloseKey` at `0x180081b6b`
- `ADVAPI32!RegOpenKeyExA` at `0x180081afb`
- `ADVAPI32!RegOpenKeyExA` at `0x180081afb`
- `ADVAPI32!RegQueryValueExA` at `0x180081b2a`
- `ADVAPI32!RegQueryValueExA` at `0x180081b2a`

## string_xrefs

- `0x180081ae5`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
__int64 __fastcall GetMMAuthMachineCertificateHash(LPBYTE lpData, _DWORD *a2)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  hKey = 0;
  Type = 3;
  cbData = 20;
  *a2 = 0;
  *lpData = 0;
  v4 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", 0, 1u, &hKey);
  if ( !v4 )
  {
    v5 = RegQueryValueExA(hKey, "ServerAuthCert", 0, &Type, lpData, &cbData);
    v4 = v5;
    if ( v5 == 2 )
    {
      v4 = 0;
    }
    else if ( !v5 )
    {
      if ( Type == 3 )
      {
        if ( cbData == 20 )
          *a2 = 1;
        else
          v4 = 13;
      }
      else
      {
        v4 = 1804;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180081aac  mov     rax, rsp
0x180081aaf  push    rbx
0x180081ab0  push    rsi
0x180081ab1  push    rdi
0x180081ab2  sub     rsp, 30h
0x180081ab6  mov     qword ptr [rax+18h], 0
0x180081abe  mov     rdi, rdx
0x180081ac1  mov     dword ptr [rax+8], 3
0x180081ac8  mov     rsi, rcx
0x180081acb  mov     dword ptr [rax+10h], 14h
0x180081ad2  lea     rax, [rax+18h]
0x180081ad6  mov     dword ptr [rdx], 0
0x180081adc  mov     r9d, 1; samDesired
0x180081ae2  mov     byte ptr [rcx], 0
0x180081ae5  lea     rdx, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180081aec  xor     r8d, r8d; ulOptions
0x180081aef  mov     [rsp+48h+phkResult], rax; phkResult
0x180081af4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081afb  call    cs:__imp_RegOpenKeyExA
0x180081b01  mov     ebx, eax
0x180081b03  test    eax, eax
0x180081b05  jnz     short loc_180081B61
0x180081b07  mov     rcx, [rsp+48h+hKey]; hKey
0x180081b0c  lea     rax, [rsp+48h+cbData]
0x180081b11  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180081b16  lea     r9, [rsp+48h+Type]; lpType
0x180081b1b  xor     r8d, r8d; lpReserved
0x180081b1e  mov     [rsp+48h+phkResult], rsi; lpData
0x180081b23  lea     rdx, aServerauthcert; "ServerAuthCert"
0x180081b2a  call    cs:__imp_RegQueryValueExA
0x180081b30  mov     ebx, eax
0x180081b32  cmp     eax, 2
0x180081b35  jnz     short loc_180081B3B
0x180081b37  xor     ebx, ebx
0x180081b39  jmp     short loc_180081B61
0x180081b3b  test    eax, eax
0x180081b3d  jnz     short loc_180081B61
0x180081b3f  cmp     [rsp+48h+Type], 3
0x180081b44  jz      short loc_180081B4D
0x180081b46  mov     ebx, 70Ch
0x180081b4b  jmp     short loc_180081B61
0x180081b4d  cmp     [rsp+48h+cbData], 14h
0x180081b52  jz      short loc_180081B5B
0x180081b54  mov     ebx, 0Dh
0x180081b59  jmp     short loc_180081B61
0x180081b5b  mov     dword ptr [rdi], 1
0x180081b61  mov     rcx, [rsp+48h+hKey]; hKey
0x180081b66  test    rcx, rcx
0x180081b69  jz      short loc_180081B71
0x180081b6b  call    cs:__imp_RegCloseKey
0x180081b71  mov     eax, ebx
0x180081b73  add     rsp, 30h
0x180081b77  pop     rdi
0x180081b78  pop     rsi
0x180081b79  pop     rbx
0x180081b7a  retn
```
