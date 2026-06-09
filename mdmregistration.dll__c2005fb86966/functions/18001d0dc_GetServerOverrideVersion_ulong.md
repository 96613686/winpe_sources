# GetServerOverrideVersion(ulong &)

- ea: `0x18001d0dc`
- end: `0x18001d1b3`
- name: `?GetServerOverrideVersion@@YA_NAEAK@Z`
- size: `215`
- prototype: `bool __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001afd8`

## callees

- `0x18001d0dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d184`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d19d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d184`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d19d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d117`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d117`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d160`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d160`

## pseudocode

```c
char __fastcall GetServerOverrideVersion(unsigned int *a1)
{
  HKEY v2; // rcx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  *a1 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollment", 0, 0x20019u, &hKey) >= 0
    && (Type = 0,
        Data = 0,
        cbData = 4,
        RegQueryValueExW(hKey, L"OverrideServerVersion", 0, &Type, (LPBYTE)&Data, &cbData) >= 0)
    && Type == 4 )
  {
    v2 = hKey;
    *a1 = Data;
    if ( v2 )
      RegCloseKey(v2);
    return 1;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x18001d0dc  push    rbp
0x18001d0de  push    rbx
0x18001d0df  mov     rbp, rsp
0x18001d0e2  sub     rsp, 38h
0x18001d0e6  mov     rbx, rcx
0x18001d0e9  mov     dword ptr [rcx], 0
0x18001d0ef  lea     rax, [rbp+hKey]
0x18001d0f3  mov     [rbp+hKey], 0
0x18001d0fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d102  mov     [rsp+38h+phkResult], rax; phkResult
0x18001d107  mov     r9d, 20019h; samDesired
0x18001d10d  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Enrollment"
0x18001d114  xor     r8d, r8d; ulOptions
0x18001d117  call    cs:__imp_RegOpenKeyExW
0x18001d11e  nop     dword ptr [rax+rax+00h]
0x18001d123  test    eax, eax
0x18001d125  js      short loc_18001D194
0x18001d127  mov     rcx, [rbp+hKey]; hKey
0x18001d12b  lea     rax, [rbp+cbData]
0x18001d12f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001d134  lea     r9, [rbp+Type]; lpType
0x18001d138  lea     rax, [rbp+Data]
0x18001d13c  mov     [rbp+Type], 0
0x18001d143  xor     r8d, r8d; lpReserved
0x18001d146  mov     [rsp+38h+phkResult], rax; lpData
0x18001d14b  lea     rdx, aOverrideserver; "OverrideServerVersion"
0x18001d152  mov     [rbp+Data], 0
0x18001d159  mov     [rbp+cbData], 4
0x18001d160  call    cs:__imp_RegQueryValueExW
0x18001d167  nop     dword ptr [rax+rax+00h]
0x18001d16c  test    eax, eax
0x18001d16e  js      short loc_18001D194
0x18001d170  cmp     [rbp+Type], 4
0x18001d174  jnz     short loc_18001D194
0x18001d176  mov     rcx, [rbp+hKey]; hKey
0x18001d17a  mov     eax, [rbp+Data]
0x18001d17d  mov     [rbx], eax
0x18001d17f  test    rcx, rcx
0x18001d182  jz      short loc_18001D190
0x18001d184  call    cs:__imp_RegCloseKey
0x18001d18b  nop     dword ptr [rax+rax+00h]
0x18001d190  mov     al, 1
0x18001d192  jmp     short loc_18001D1AB
0x18001d194  mov     rcx, [rbp+hKey]; hKey
0x18001d198  test    rcx, rcx
0x18001d19b  jz      short loc_18001D1A9
0x18001d19d  call    cs:__imp_RegCloseKey
0x18001d1a4  nop     dword ptr [rax+rax+00h]
0x18001d1a9  xor     al, al
0x18001d1ab  add     rsp, 38h
0x18001d1af  pop     rbx
0x18001d1b0  pop     rbp
0x18001d1b1  retn
```
