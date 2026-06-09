# DsRolepQueryUpgradeInfo

- ea: `0x18001428c`
- end: `0x18001433c`
- name: `DsRolepQueryUpgradeInfo`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006c30`

## callees

- `0x18001428c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014307`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014307`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800142d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800142d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001431b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001431b`

## string_xrefs

- `0x1800142ca`: `Security\`

## pseudocode

```c
__int64 __fastcall DsRolepQueryUpgradeInfo(_BYTE *a1, BYTE *a2)
{
  unsigned int v4; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Security\\", 0, 0x2001Fu, &hKey);
  if ( !v4 )
  {
    v4 = RegQueryValueExW(hKey, L"Upgrade", 0, &Type, a2, &cbData);
    if ( !v4 )
      *a1 = 1;
    RegCloseKey(hKey);
  }
  if ( v4 == 2 )
  {
    v4 = 0;
    *a1 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18001428c  mov     rax, rsp
0x18001428f  mov     [rax+8], rbx
0x180014293  mov     [rax+10h], rsi
0x180014297  push    rdi
0x180014298  sub     rsp, 40h
0x18001429c  mov     qword ptr [rax-18h], 0
0x1800142a4  mov     rsi, rdx
0x1800142a7  mov     dword ptr [rax+20h], 0
0x1800142ae  mov     rdi, rcx
0x1800142b1  mov     dword ptr [rax+18h], 4
0x1800142b8  lea     rax, [rax-18h]
0x1800142bc  mov     r9d, 2001Fh; samDesired
0x1800142c2  mov     [rsp+48h+phkResult], rax; phkResult
0x1800142c7  xor     r8d, r8d; ulOptions
0x1800142ca  lea     rdx, aSecurity; "Security\\"
0x1800142d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800142d8  call    cs:__imp_RegOpenKeyExW
0x1800142de  mov     ebx, eax
0x1800142e0  test    eax, eax
0x1800142e2  jnz     short loc_180014321
0x1800142e4  mov     rcx, [rsp+48h+hKey]; hKey
0x1800142e9  lea     rax, [rsp+48h+cbData]
0x1800142ee  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800142f3  lea     r9, [rsp+48h+Type]; lpType
0x1800142f8  xor     r8d, r8d; lpReserved
0x1800142fb  mov     [rsp+48h+phkResult], rsi; lpData
0x180014300  lea     rdx, aUpgrade; "Upgrade"
0x180014307  call    cs:__imp_RegQueryValueExW
0x18001430d  mov     ebx, eax
0x18001430f  test    eax, eax
0x180014311  jnz     short loc_180014316
0x180014313  mov     byte ptr [rdi], 1
0x180014316  mov     rcx, [rsp+48h+hKey]; hKey
0x18001431b  call    cs:__imp_RegCloseKey
0x180014321  cmp     ebx, 2
0x180014324  jnz     short loc_18001432A
0x180014326  xor     ebx, ebx
0x180014328  mov     [rdi], bl
0x18001432a  mov     rsi, [rsp+48h+arg_8]
0x18001432f  mov     eax, ebx
0x180014331  mov     rbx, [rsp+48h+arg_0]
0x180014336  add     rsp, 40h
0x18001433a  pop     rdi
0x18001433b  retn
```
