# SetRegString(ushort const *,ushort const *,ushort const *)

- ea: `0x1800183a0`
- end: `0x18001848e`
- name: `?SetRegString@@YAHPEBG00@Z`
- size: `238`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800182e8`

## callees

- `0x1800183a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018476`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018476`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800183e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800183e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018423`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018423`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018461`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018461`

## string_xrefs

- `0x18001844a`: `lastUpdatedTime`
- `0x1800183d7`: `SOFTWARE\Microsoft\MSDRM\TemplateManagement`
- `0x1800183fe`: `SOFTWARE\Microsoft\MSDRM\TemplateManagement`

## pseudocode

```c
__int64 __fastcall SetRegString(const unsigned __int16 *a1, const unsigned __int16 *a2, const BYTE *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v4 = 0;
  if ( a3 )
  {
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\MSDRM\\TemplateManagement", 0, 2u, &hKey)
      || !RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\MSDRM\\TemplateManagement",
            0,
            0,
            0,
            2u,
            0,
            &hKey,
            0) )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)&a3[2 * v5] );
      if ( !RegSetValueExW(hKey, L"lastUpdatedTime", 0, 1u, a3, 2 * v5 + 2) )
        v4 = 1;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x1800183a0  mov     r11, rsp
0x1800183a3  mov     [r11+8], rbx
0x1800183a7  mov     [r11+18h], rsi
0x1800183ab  mov     [r11+10h], rdx
0x1800183af  push    rdi
0x1800183b0  sub     rsp, 50h
0x1800183b4  xor     esi, esi
0x1800183b6  mov     rdi, r8
0x1800183b9  mov     [r11+10h], rsi
0x1800183bd  mov     ebx, esi
0x1800183bf  test    r8, r8
0x1800183c2  jz      loc_18001847C
0x1800183c8  lea     rax, [r11+10h]
0x1800183cc  xor     r8d, r8d; ulOptions
0x1800183cf  lea     r9d, [rsi+2]; samDesired
0x1800183d3  mov     [r11-38h], rax
0x1800183d7  lea     rdx, ?g_wszTM_Key@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM\\TemplateMan"...
0x1800183de  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800183e5  call    cs:__imp_RegOpenKeyExW
0x1800183eb  test    eax, eax
0x1800183ed  jz      short loc_18001842D
0x1800183ef  mov     [rsp+58h+lpdwDisposition], rsi; lpdwDisposition
0x1800183f4  lea     rax, [rsp+58h+hKey]
0x1800183f9  mov     [rsp+58h+phkResult], rax; phkResult
0x1800183fe  lea     rdx, ?g_wszTM_Key@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM\\TemplateMan"...
0x180018405  mov     [rsp+58h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18001840a  xor     r9d, r9d; lpClass
0x18001840d  mov     [rsp+58h+samDesired], 2; samDesired
0x180018415  xor     r8d, r8d; Reserved
0x180018418  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001841f  mov     [rsp+58h+dwOptions], esi; dwOptions
0x180018423  call    cs:__imp_RegCreateKeyExW
0x180018429  test    eax, eax
0x18001842b  jnz     short loc_18001846C
0x18001842d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018431  inc     rax
0x180018434  cmp     [rdi+rax*2], si
0x180018438  jnz     short loc_180018431
0x18001843a  mov     rcx, [rsp+58h+hKey]; hKey
0x18001843f  lea     eax, ds:2[rax*2]
0x180018446  mov     [rsp+58h+samDesired], eax; cbData
0x18001844a  lea     rdx, ?g_wszTM_Value_lastUpdatedTime@@3QBGB; "lastUpdatedTime"
0x180018451  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x180018456  xor     r8d, r8d; Reserved
0x180018459  mov     edi, 1
0x18001845e  mov     r9d, edi; dwType
0x180018461  call    cs:__imp_RegSetValueExW
0x180018467  test    eax, eax
0x180018469  cmovz   ebx, edi
0x18001846c  mov     rcx, [rsp+58h+hKey]; hKey
0x180018471  test    rcx, rcx
0x180018474  jz      short loc_18001847C
0x180018476  call    cs:__imp_RegCloseKey
0x18001847c  mov     rsi, [rsp+58h+arg_10]
0x180018481  mov     eax, ebx
0x180018483  mov     rbx, [rsp+58h+arg_0]
0x180018488  add     rsp, 50h
0x18001848c  pop     rdi
0x18001848d  retn
```
