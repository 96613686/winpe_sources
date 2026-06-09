# SDTEventUnregisterServer

- ea: `0x180044a18`
- end: `0x180044aa7`
- name: `SDTEventUnregisterServer`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800156b0`

## callees

- `0x18003f894`
- `0x180044a18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044a57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044a57`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180044a74`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180044a74`

## string_xrefs

- `0x180044a41`: `SOFTWARE\Classes\CLSID`

## pseudocode

```c
__int64 SDTEventUnregisterServer()
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
  v1 = RegDeleteTreeW(hKey, L"{6131A8EC-78CE-11d2-A3F2-3078302C2030}");
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
0x180044a18  mov     r11, rsp
0x180044a1b  push    rbx
0x180044a1c  sub     rsp, 30h
0x180044a20  lea     rax, [r11+8]
0x180044a24  mov     qword ptr [r11+8], 0
0x180044a2c  mov     r9d, 0F003Fh; samDesired
0x180044a32  mov     [r11-18h], rax
0x180044a36  xor     r8d, r8d; ulOptions
0x180044a39  mov     qword ptr [r11+18h], 0
0x180044a41  lea     rdx, ?g_wszRP_COMCLSIDS@@3PAGA; "SOFTWARE\\Classes\\CLSID"
0x180044a48  mov     qword ptr [r11+10h], 0
0x180044a50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044a57  call    cs:__imp_RegOpenKeyExW
0x180044a5d  test    eax, eax
0x180044a5f  jz      short loc_180044A68
0x180044a61  mov     eax, 8000FFFFh
0x180044a66  jmp     short loc_180044AA1
0x180044a68  mov     rcx, [rsp+38h+hKey]; hKey
0x180044a6d  lea     rdx, a6131a8ec78ce11; "{6131A8EC-78CE-11d2-A3F2-3078302C2030}"
0x180044a74  call    cs:__imp_RegDeleteTreeW
0x180044a7a  xor     ebx, ebx
0x180044a7c  lea     rcx, [rsp+38h+arg_8]; HKEY *
0x180044a81  test    eax, eax
0x180044a83  cmovs   ebx, eax
0x180044a86  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x180044a8b  lea     rcx, [rsp+38h+arg_10]; HKEY *
0x180044a90  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x180044a95  lea     rcx, [rsp+38h+hKey]; HKEY *
0x180044a9a  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x180044a9f  mov     eax, ebx
0x180044aa1  add     rsp, 30h
0x180044aa5  pop     rbx
0x180044aa6  retn
```
