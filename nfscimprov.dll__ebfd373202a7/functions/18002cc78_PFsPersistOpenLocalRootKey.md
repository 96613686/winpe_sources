# PFsPersistOpenLocalRootKey

- ea: `0x18002cc78`
- end: `0x18002cceb`
- name: `PFsPersistOpenLocalRootKey`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d2b4`
- `0x18002db34`

## callees

- `0x18002cc78`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18002ccd3`
- `ADVAPI32!RegCreateKeyExW` at `0x18002ccd3`

## pseudocode

```c
LSTATUS __fastcall PFsPersistOpenLocalRootKey(_QWORD *a1)
{
  LSTATUS result; // eax
  DWORD v3; // [rsp+68h] [rbp+10h] BYREF
  HKEY v4; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  v4 = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\ServerForNFS\\CurrentVersion\\PersistentPFs",
             0,
             0,
             0,
             0xF003Fu,
             0,
             &v4,
             &v3);
  if ( !result )
    *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x18002cc78  mov     byte ptr [rsp+arg_8], dl
0x18002cc7c  mov     r11, rsp
0x18002cc7f  push    rbx
0x18002cc80  sub     rsp, 50h
0x18002cc84  lea     rax, [r11+10h]
0x18002cc88  mov     [rsp+58h+arg_8], 0
0x18002cc90  mov     [r11-18h], rax
0x18002cc94  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\ServerForNFS\\Curr"...
0x18002cc9b  lea     rax, [r11+18h]
0x18002cc9f  mov     qword ptr [r11+18h], 0
0x18002cca7  mov     [r11-20h], rax
0x18002ccab  mov     rbx, rcx
0x18002ccae  mov     qword ptr [r11-28h], 0
0x18002ccb6  xor     r9d, r9d; lpClass
0x18002ccb9  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18002ccc1  xor     r8d, r8d; Reserved
0x18002ccc4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002cccb  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002ccd3  call    cs:__imp_RegCreateKeyExW
0x18002ccd9  test    eax, eax
0x18002ccdb  jnz     short loc_18002CCE5
0x18002ccdd  mov     rcx, [rsp+58h+arg_10]
0x18002cce2  mov     [rbx], rcx
0x18002cce5  add     rsp, 50h
0x18002cce9  pop     rbx
0x18002ccea  retn
```
