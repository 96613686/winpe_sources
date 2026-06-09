# DsRolepSetExtensionKey

- ea: `0x18000fdd4`
- end: `0x18000fea2`
- name: `DsRolepSetExtensionKey`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000f584`
- `0x18000fea8`

## callees

- `0x18000fdd4`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fe28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fe28`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fe4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fe4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe87`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18000fe61`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18000fe61`

## string_xrefs

- `0x18000fe1a`: `SYSTEM\CurrentControlSet\Services\NTDS`

## pseudocode

```c
__int64 __fastcall DsRolepSetExtensionKey(HKEY a1, const WCHAR *a2, const BYTE *a3)
{
  __int64 v3; // rbx
  unsigned int v6; // edi
  unsigned int v7; // eax
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = a1;
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&a3[2 * v3] );
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\NTDS", 0, 3u, &hKey);
  if ( !v6 )
    v6 = RegSetValueExW(hKey, a2, 0, 2u, a3, 2 * v3);
  if ( hKey )
  {
    v7 = RegFlushKey(hKey);
    if ( v7 )
      DsRolepLogPrintRoutine(4, "Flushing the %ws key failed with error 0x%x\n", a2, v7);
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x18000fdd4  mov     [rsp+arg_8], rbx
0x18000fdd9  mov     [rsp+arg_10], rbp
0x18000fdde  mov     [rsp+hKey], rcx
0x18000fde3  push    rsi
0x18000fde4  push    rdi
0x18000fde5  push    r14
0x18000fde7  sub     rsp, 30h
0x18000fdeb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000fdef  mov     rsi, r8
0x18000fdf2  xor     r14d, r14d
0x18000fdf5  mov     rbp, rdx
0x18000fdf8  inc     rbx
0x18000fdfb  cmp     [r8+rbx*2], r14w
0x18000fe00  jnz     short loc_18000FDF8
0x18000fe02  lea     rax, [rsp+48h+hKey]
0x18000fe07  mov     [rsp+48h+hKey], r14
0x18000fe0c  mov     r9d, 3; samDesired
0x18000fe12  mov     [rsp+48h+phkResult], rax; phkResult
0x18000fe17  xor     r8d, r8d; ulOptions
0x18000fe1a  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\NT"...
0x18000fe21  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fe28  call    cs:__imp_RegOpenKeyExW
0x18000fe2e  mov     edi, eax
0x18000fe30  test    eax, eax
0x18000fe32  jnz     short loc_18000FE57
0x18000fe34  mov     rcx, [rsp+48h+hKey]; hKey
0x18000fe39  lea     eax, [rbx+rbx]
0x18000fe3c  mov     [rsp+48h+cbData], eax; cbData
0x18000fe40  lea     r9d, [rdi+2]; dwType
0x18000fe44  xor     r8d, r8d; Reserved
0x18000fe47  mov     [rsp+48h+phkResult], rsi; lpData
0x18000fe4c  mov     rdx, rbp; lpValueName
0x18000fe4f  call    cs:__imp_RegSetValueExW
0x18000fe55  mov     edi, eax
0x18000fe57  mov     rcx, [rsp+48h+hKey]; hKey
0x18000fe5c  test    rcx, rcx
0x18000fe5f  jz      short loc_18000FE8D
0x18000fe61  call    cs:__imp_RegFlushKey
0x18000fe67  test    eax, eax
0x18000fe69  jz      short loc_18000FE82
0x18000fe6b  mov     r9d, eax
0x18000fe6e  lea     rdx, aFlushingTheWsK; "Flushing the %ws key failed with error "...
0x18000fe75  mov     r8, rbp
0x18000fe78  mov     ecx, 4
0x18000fe7d  call    DsRolepLogPrintRoutine
0x18000fe82  mov     rcx, [rsp+48h+hKey]; hKey
0x18000fe87  call    cs:__imp_RegCloseKey
0x18000fe8d  mov     rbx, [rsp+48h+arg_8]
0x18000fe92  mov     eax, edi
0x18000fe94  mov     rbp, [rsp+48h+arg_10]
0x18000fe99  add     rsp, 30h
0x18000fe9d  pop     r14
0x18000fe9f  pop     rdi
0x18000fea0  pop     rsi
0x18000fea1  retn
```
