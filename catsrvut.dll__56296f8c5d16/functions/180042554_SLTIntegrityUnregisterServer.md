# SLTIntegrityUnregisterServer

- ea: `0x180042554`
- end: `0x1800425e3`
- name: `SLTIntegrityUnregisterServer`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800156b0`

## callees

- `0x18003f894`
- `0x180042554`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042593`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042593`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800425b0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800425b0`

## string_xrefs

- `0x18004257d`: `SOFTWARE\Classes\CLSID`

## pseudocode

```c
__int64 SLTIntegrityUnregisterServer()
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
  v1 = RegDeleteTreeW(hKey, L"{75C9378A-7E89-11d2-B116-00805FC73204}");
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
0x180042554  mov     r11, rsp
0x180042557  push    rbx
0x180042558  sub     rsp, 30h
0x18004255c  lea     rax, [r11+8]
0x180042560  mov     qword ptr [r11+8], 0
0x180042568  mov     r9d, 0F003Fh; samDesired
0x18004256e  mov     [r11-18h], rax
0x180042572  xor     r8d, r8d; ulOptions
0x180042575  mov     qword ptr [r11+18h], 0
0x18004257d  lea     rdx, ?g_wszRP_COMCLSIDS@@3PAGA; "SOFTWARE\\Classes\\CLSID"
0x180042584  mov     qword ptr [r11+10h], 0
0x18004258c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042593  call    cs:__imp_RegOpenKeyExW
0x180042599  test    eax, eax
0x18004259b  jz      short loc_1800425A4
0x18004259d  mov     eax, 8000FFFFh
0x1800425a2  jmp     short loc_1800425DD
0x1800425a4  mov     rcx, [rsp+38h+hKey]; hKey
0x1800425a9  lea     rdx, a75c9378a7e8911; "{75C9378A-7E89-11d2-B116-00805FC73204}"
0x1800425b0  call    cs:__imp_RegDeleteTreeW
0x1800425b6  xor     ebx, ebx
0x1800425b8  lea     rcx, [rsp+38h+arg_8]; HKEY *
0x1800425bd  test    eax, eax
0x1800425bf  cmovs   ebx, eax
0x1800425c2  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800425c7  lea     rcx, [rsp+38h+arg_10]; HKEY *
0x1800425cc  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800425d1  lea     rcx, [rsp+38h+hKey]; HKEY *
0x1800425d6  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x1800425db  mov     eax, ebx
0x1800425dd  add     rsp, 30h
0x1800425e1  pop     rbx
0x1800425e2  retn
```
