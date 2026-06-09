# DsRolepSetDCLocatorPostPromoState

- ea: `0x18000b62c`
- end: `0x18000b6a6`
- name: `DsRolepSetDCLocatorPostPromoState`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x18000b62c`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b69b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b69b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b677`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b677`

## string_xrefs

- `0x18000b643`: `System\CurrentControlSet\services\Netlogon\Parameters\LocatorDCPromoPreRebootHint`

## pseudocode

```c
LSTATUS DsRolepSetDCLocatorPostPromoState()
{
  LSTATUS v0; // eax
  LSTATUS result; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\services\\Netlogon\\Parameters\\LocatorDCPromoPreRebootHint",
         0,
         0,
         1u,
         0xF003Fu,
         0,
         &hKey,
         0);
  result = DsRolepLogPrintRoutine(
             4,
             "DsRolepSetDCLocatorPostPromoState: got %lu creating the DSROLEP_DCLOCATOR_PREREBOOT_HINT key\n",
             v0);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18000b62c  mov     r11, rsp
0x18000b62f  sub     rsp, 58h
0x18000b633  mov     qword ptr [r11-18h], 0
0x18000b63b  lea     rax, [r11+8]
0x18000b63f  mov     [r11-20h], rax
0x18000b643  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\services\\Ne"...
0x18000b64a  mov     qword ptr [r11-28h], 0
0x18000b652  xor     r9d, r9d; lpClass
0x18000b655  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18000b65d  xor     r8d, r8d; Reserved
0x18000b660  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b667  mov     [rsp+58h+dwOptions], 1; dwOptions
0x18000b66f  mov     qword ptr [r11+8], 0
0x18000b677  call    cs:__imp_RegCreateKeyExW
0x18000b67d  lea     rdx, aDsrolepsetdclo; "DsRolepSetDCLocatorPostPromoState: got "...
0x18000b684  mov     ecx, 4
0x18000b689  mov     r8d, eax
0x18000b68c  call    DsRolepLogPrintRoutine
0x18000b691  mov     rcx, [rsp+58h+hKey]; hKey
0x18000b696  test    rcx, rcx
0x18000b699  jz      short loc_18000B6A1
0x18000b69b  call    cs:__imp_RegCloseKey
0x18000b6a1  add     rsp, 58h
0x18000b6a5  retn
```
