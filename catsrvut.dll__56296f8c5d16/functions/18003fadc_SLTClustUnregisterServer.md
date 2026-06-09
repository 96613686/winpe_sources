# SLTClustUnregisterServer

- ea: `0x18003fadc`
- end: `0x18003fb6b`
- name: `SLTClustUnregisterServer`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800156b0`

## callees

- `0x18003f894`
- `0x18003fadc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fb1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fb1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003fb38`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003fb38`

## string_xrefs

- `0x18003fb05`: `SOFTWARE\Classes\CLSID`

## pseudocode

```c
__int64 SLTClustUnregisterServer()
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY v4; // [rsp+48h] [rbp+10h] BYREF
  HKEY v5; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v5 = 0;
  v4 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_wszRP_COMCLSIDS, 0, 0xF003Fu, &hKey) )
    return 2147549183LL;
  v1 = RegDeleteTreeW(hKey, L"{94426DE2-3211-11d2-A0DB-00C04F8EDCEE}");
  v2 = 0;
  if ( v1 < 0 )
    v2 = v1;
  RegSafeCloseKey(&v4);
  RegSafeCloseKey(&v5);
  RegSafeCloseKey(&hKey);
  return v2;
}

```

## disassembly

```asm
0x18003fadc  mov     r11, rsp
0x18003fadf  push    rbx
0x18003fae0  sub     rsp, 30h
0x18003fae4  lea     rax, [r11+8]
0x18003fae8  mov     qword ptr [r11+8], 0
0x18003faf0  mov     r9d, 0F003Fh; samDesired
0x18003faf6  mov     [r11-18h], rax
0x18003fafa  xor     r8d, r8d; ulOptions
0x18003fafd  mov     qword ptr [r11+18h], 0
0x18003fb05  lea     rdx, ?g_wszRP_COMCLSIDS@@3PAGA; "SOFTWARE\\Classes\\CLSID"
0x18003fb0c  mov     qword ptr [r11+10h], 0
0x18003fb14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003fb1b  call    cs:__imp_RegOpenKeyExW
0x18003fb21  test    eax, eax
0x18003fb23  jz      short loc_18003FB2C
0x18003fb25  mov     eax, 8000FFFFh
0x18003fb2a  jmp     short loc_18003FB65
0x18003fb2c  mov     rcx, [rsp+38h+hKey]; hKey
0x18003fb31  lea     rdx, a94426de2321111; "{94426DE2-3211-11d2-A0DB-00C04F8EDCEE}"
0x18003fb38  call    cs:__imp_RegDeleteTreeW
0x18003fb3e  xor     ebx, ebx
0x18003fb40  lea     rcx, [rsp+38h+arg_8]; HKEY *
0x18003fb45  test    eax, eax
0x18003fb47  cmovs   ebx, eax
0x18003fb4a  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18003fb4f  lea     rcx, [rsp+38h+arg_10]; HKEY *
0x18003fb54  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18003fb59  lea     rcx, [rsp+38h+hKey]; HKEY *
0x18003fb5e  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18003fb63  mov     eax, ebx
0x18003fb65  add     rsp, 30h
0x18003fb69  pop     rbx
0x18003fb6a  retn
```
