# SDTIMetaDataUnregisterServer

- ea: `0x1800402f8`
- end: `0x180040387`
- name: `SDTIMetaDataUnregisterServer`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800156b0`

## callees

- `0x18003f894`
- `0x1800402f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040337`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040337`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180040354`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180040354`

## string_xrefs

- `0x180040321`: `SOFTWARE\Classes\CLSID`

## pseudocode

```c
__int64 SDTIMetaDataUnregisterServer()
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
  v1 = RegDeleteTreeW(hKey, L"{22EE26E5-2289-11d2-8F43-00C04FC2E0C7}");
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
0x1800402f8  mov     r11, rsp
0x1800402fb  push    rbx
0x1800402fc  sub     rsp, 30h
0x180040300  lea     rax, [r11+8]
0x180040304  mov     qword ptr [r11+8], 0
0x18004030c  mov     r9d, 0F003Fh; samDesired
0x180040312  mov     [r11-18h], rax
0x180040316  xor     r8d, r8d; ulOptions
0x180040319  mov     qword ptr [r11+18h], 0
0x180040321  lea     rdx, ?g_wszRP_COMCLSIDS@@3PAGA; "SOFTWARE\\Classes\\CLSID"
0x180040328  mov     qword ptr [r11+10h], 0
0x180040330  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040337  call    cs:__imp_RegOpenKeyExW
0x18004033d  test    eax, eax
0x18004033f  jz      short loc_180040348
0x180040341  mov     eax, 8000FFFFh
0x180040346  jmp     short loc_180040381
0x180040348  mov     rcx, [rsp+38h+hKey]; hKey
0x18004034d  lea     rdx, a22ee26e5228911; "{22EE26E5-2289-11d2-8F43-00C04FC2E0C7}"
0x180040354  call    cs:__imp_RegDeleteTreeW
0x18004035a  xor     ebx, ebx
0x18004035c  lea     rcx, [rsp+38h+arg_8]; HKEY *
0x180040361  test    eax, eax
0x180040363  cmovs   ebx, eax
0x180040366  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004036b  lea     rcx, [rsp+38h+arg_10]; HKEY *
0x180040370  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x180040375  lea     rcx, [rsp+38h+hKey]; HKEY *
0x18004037a  call    ?RegSafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ * &)
0x18004037f  mov     eax, ebx
0x180040381  add     rsp, 30h
0x180040385  pop     rbx
0x180040386  retn
```
