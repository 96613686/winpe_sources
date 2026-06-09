# SLTConvertUnregisterServer

- ea: `0x18004a1e4`
- end: `0x18004a273`
- name: `SLTConvertUnregisterServer`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800156b0`

## callees

- `0x18003f894`
- `0x18004a1e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a223`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a223`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004a240`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004a240`

## string_xrefs

- `0x18004a20d`: `SOFTWARE\Classes\CLSID`

## pseudocode

```c
__int64 SLTConvertUnregisterServer()
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
  v1 = RegDeleteTreeW(hKey, L"{1FCE6123-B675-4790-A629-F3E8AC06F839}");
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
0x18004a1e4  mov     r11, rsp
0x18004a1e7  push    rbx
0x18004a1e8  sub     rsp, 30h
0x18004a1ec  lea     rax, [r11+8]
0x18004a1f0  mov     qword ptr [r11+8], 0
0x18004a1f8  mov     r9d, 0F003Fh; samDesired
0x18004a1fe  mov     [r11-18h], rax
0x18004a202  xor     r8d, r8d; ulOptions
0x18004a205  mov     qword ptr [r11+18h], 0
0x18004a20d  lea     rdx, ?g_wszRP_COMCLSIDS@@3PAGA; "SOFTWARE\\Classes\\CLSID"
0x18004a214  mov     qword ptr [r11+10h], 0
0x18004a21c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a223  call    cs:__imp_RegOpenKeyExW
0x18004a229  test    eax, eax
0x18004a22b  jz      short loc_18004A234
0x18004a22d  mov     eax, 8000FFFFh
0x18004a232  jmp     short loc_18004A26D
0x18004a234  mov     rcx, [rsp+38h+hKey]; hKey
0x18004a239  lea     rdx, a1fce6123B67547; "{1FCE6123-B675-4790-A629-F3E8AC06F839}"
0x18004a240  call    cs:__imp_RegDeleteTreeW
0x18004a246  xor     ebx, ebx
0x18004a248  lea     rcx, [rsp+38h+arg_8]; HKEY *
0x18004a24d  test    eax, eax
0x18004a24f  cmovs   ebx, eax
0x18004a252  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004a257  lea     rcx, [rsp+38h+arg_10]; HKEY *
0x18004a25c  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004a261  lea     rcx, [rsp+38h+hKey]; HKEY *
0x18004a266  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004a26b  mov     eax, ebx
0x18004a26d  add     rsp, 30h
0x18004a271  pop     rbx
0x18004a272  retn
```
