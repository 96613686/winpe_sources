# GetMMAuthMachineCertificateHash

- ea: `0x1800875b8`
- end: `0x180087694`
- name: `GetMMAuthMachineCertificateHash`
- size: `220`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180086080`

## callees

- `0x1800875b8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18008767d`
- `ADVAPI32!RegCloseKey` at `0x18008767d`
- `ADVAPI32!RegOpenKeyExA` at `0x180087601`
- `ADVAPI32!RegOpenKeyExA` at `0x180087601`
- `ADVAPI32!RegQueryValueExA` at `0x180087636`
- `ADVAPI32!RegQueryValueExA` at `0x180087636`

## string_xrefs

- `0x1800875eb`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

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
  *a2 = 0;
  Type = 3;
  cbData = 20;
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
0x1800875b8  mov     rax, rsp
0x1800875bb  push    rbx
0x1800875bc  push    rsi
0x1800875bd  push    rdi
0x1800875be  sub     rsp, 30h
0x1800875c2  and     qword ptr [rax+18h], 0
0x1800875c7  mov     rdi, rdx
0x1800875ca  and     dword ptr [rdx], 0
0x1800875cd  mov     rsi, rcx
0x1800875d0  mov     dword ptr [rax+8], 3
0x1800875d7  mov     r9d, 1; samDesired
0x1800875dd  mov     dword ptr [rax+10h], 14h
0x1800875e4  lea     rax, [rax+18h]
0x1800875e8  mov     byte ptr [rcx], 0
0x1800875eb  lea     rdx, aSystemCurrentc_17; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x1800875f2  xor     r8d, r8d; ulOptions
0x1800875f5  mov     [rsp+48h+phkResult], rax; phkResult
0x1800875fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180087601  call    cs:__imp_RegOpenKeyExA
0x180087608  nop     dword ptr [rax+rax+00h]
0x18008760d  mov     ebx, eax
0x18008760f  test    eax, eax
0x180087611  jnz     short loc_180087673
0x180087613  mov     rcx, [rsp+48h+hKey]; hKey
0x180087618  lea     rax, [rsp+48h+cbData]
0x18008761d  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180087622  lea     r9, [rsp+48h+Type]; lpType
0x180087627  xor     r8d, r8d; lpReserved
0x18008762a  mov     [rsp+48h+phkResult], rsi; lpData
0x18008762f  lea     rdx, aServerauthcert; "ServerAuthCert"
0x180087636  call    cs:__imp_RegQueryValueExA
0x18008763d  nop     dword ptr [rax+rax+00h]
0x180087642  mov     ebx, eax
0x180087644  cmp     eax, 2
0x180087647  jnz     short loc_18008764D
0x180087649  xor     ebx, ebx
0x18008764b  jmp     short loc_180087673
0x18008764d  test    eax, eax
0x18008764f  jnz     short loc_180087673
0x180087651  cmp     [rsp+48h+Type], 3
0x180087656  jz      short loc_18008765F
0x180087658  mov     ebx, 70Ch
0x18008765d  jmp     short loc_180087673
0x18008765f  cmp     [rsp+48h+cbData], 14h
0x180087664  jz      short loc_18008766D
0x180087666  mov     ebx, 0Dh
0x18008766b  jmp     short loc_180087673
0x18008766d  mov     dword ptr [rdi], 1
0x180087673  mov     rcx, [rsp+48h+hKey]; hKey
0x180087678  test    rcx, rcx
0x18008767b  jz      short loc_180087689
0x18008767d  call    cs:__imp_RegCloseKey
0x180087684  nop     dword ptr [rax+rax+00h]
0x180087689  mov     eax, ebx
0x18008768b  add     rsp, 30h
0x18008768f  pop     rdi
0x180087690  pop     rsi
0x180087691  pop     rbx
0x180087692  retn
```
