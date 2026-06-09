# InitTrace(void)

- ea: `0x180018cb4`
- end: `0x180018d63`
- name: `?InitTrace@@YAXXZ`
- size: `175`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019064`

## callees

- `0x180018cb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018d57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018d57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018cfa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018cfa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018d2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018d2f`

## pseudocode

```c
void InitTrace(void)
{
  DWORD cbData; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  int Data; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSDRM", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"Trace", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
      g_fTrace = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180018cb4  push    rbp
0x180018cb6  mov     rbp, rsp
0x180018cb9  sub     rsp, 30h
0x180018cbd  lea     rax, [rbp+hKey]
0x180018cc1  mov     [rbp+hKey], 0
0x180018cc9  mov     r9d, 20019h; samDesired
0x180018ccf  mov     [rsp+30h+phkResult], rax; phkResult
0x180018cd4  xor     r8d, r8d; ulOptions
0x180018cd7  mov     [rbp+Type], 0
0x180018cde  lea     rdx, ?g_wszTR_Key@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM"
0x180018ce5  mov     [rbp+Data], 0
0x180018cec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018cf3  mov     [rbp+cbData], 0
0x180018cfa  call    cs:__imp_RegOpenKeyExW
0x180018d00  test    eax, eax
0x180018d02  jnz     short loc_180018D4E
0x180018d04  mov     rcx, [rbp+hKey]; hKey
0x180018d08  lea     rax, [rbp+cbData]
0x180018d0c  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180018d11  lea     r9, [rbp+Type]; lpType
0x180018d15  lea     rax, [rbp+Data]
0x180018d19  mov     [rbp+cbData], 4
0x180018d20  xor     r8d, r8d; lpReserved
0x180018d23  mov     [rsp+30h+phkResult], rax; lpData
0x180018d28  lea     rdx, ?g_wszTR_ValueName@@3QBGB; "Trace"
0x180018d2f  call    cs:__imp_RegQueryValueExW
0x180018d35  test    eax, eax
0x180018d37  jnz     short loc_180018D4E
0x180018d39  cmp     [rbp+Type], 4
0x180018d3d  jnz     short loc_180018D4E
0x180018d3f  cmp     [rbp+Data], eax
0x180018d42  jbe     short loc_180018D4E
0x180018d44  mov     cs:?g_fTrace@@3HA, 1; int g_fTrace
0x180018d4e  mov     rcx, [rbp+hKey]; hKey
0x180018d52  test    rcx, rcx
0x180018d55  jz      short loc_180018D5D
0x180018d57  call    cs:__imp_RegCloseKey
0x180018d5d  add     rsp, 30h
0x180018d61  pop     rbp
0x180018d62  retn
```
