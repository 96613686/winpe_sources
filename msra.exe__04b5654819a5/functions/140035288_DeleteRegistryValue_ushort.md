# DeleteRegistryValue(ushort *)

- ea: `0x140035288`
- end: `0x140035321`
- name: `?DeleteRegistryValue@@YAJPEAG@Z`
- size: `153`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140024100`
- `0x140024210`
- `0x140024b5c`

## callees

- `0x140035288`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400352e5`
- `ADVAPI32!RegCloseKey` at `0x1400352e5`
- `ADVAPI32!RegOpenKeyExW` at `0x1400352be`
- `ADVAPI32!RegOpenKeyExW` at `0x1400352be`
- `ADVAPI32!RegDeleteKeyValueW` at `0x14003530b`
- `ADVAPI32!RegDeleteKeyValueW` at `0x14003530b`

## pseudocode

```c
__int64 __fastcall DeleteRegistryValue(LPCWSTR lpValueName)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Remote Assistance", 0, 2u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 <= 0 )
      goto LABEL_4;
    goto LABEL_3;
  }
  v3 = 0;
  v2 = RegDeleteKeyValueW(hKey, 0, lpValueName);
  if ( v2 )
  {
    if ( v2 > 0 )
    {
LABEL_3:
      v3 = (unsigned __int16)v2 | 0x80070000;
      goto LABEL_4;
    }
    v3 = v2;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x140035288  mov     r11, rsp
0x14003528b  mov     [r11+8], rbx
0x14003528f  push    rdi
0x140035290  sub     rsp, 30h
0x140035294  mov     rdi, rcx
0x140035297  mov     qword ptr [r11+10h], 0
0x14003529f  lea     rax, [r11+10h]
0x1400352a3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400352aa  mov     r9d, 2; samDesired
0x1400352b0  mov     [r11-18h], rax
0x1400352b4  xor     r8d, r8d; ulOptions
0x1400352b7  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Remote Assistance"
0x1400352be  call    cs:__imp_RegOpenKeyExW
0x1400352c5  nop     dword ptr [rax+rax+00h]
0x1400352ca  mov     ebx, eax
0x1400352cc  test    eax, eax
0x1400352ce  jz      short loc_1400352FF
0x1400352d0  jle     short loc_1400352DB
0x1400352d2  movzx   ebx, ax
0x1400352d5  or      ebx, 80070000h
0x1400352db  mov     rcx, [rsp+38h+hKey]; hKey
0x1400352e0  test    rcx, rcx
0x1400352e3  jz      short loc_1400352F1
0x1400352e5  call    cs:__imp_RegCloseKey
0x1400352ec  nop     dword ptr [rax+rax+00h]
0x1400352f1  mov     eax, ebx
0x1400352f3  mov     rbx, [rsp+38h+arg_0]
0x1400352f8  add     rsp, 30h
0x1400352fc  pop     rdi
0x1400352fd  retn
0x1400352ff  mov     rcx, [rsp+38h+hKey]; hKey
0x140035304  mov     r8, rdi; lpValueName
0x140035307  xor     edx, edx; lpSubKey
0x140035309  xor     ebx, ebx
0x14003530b  call    cs:__imp_RegDeleteKeyValueW
0x140035312  nop     dword ptr [rax+rax+00h]
0x140035317  test    eax, eax
0x140035319  jz      short loc_1400352DB
0x14003531b  jg      short loc_1400352D2
0x14003531d  mov     ebx, eax
0x14003531f  jmp     short loc_1400352DB
```
