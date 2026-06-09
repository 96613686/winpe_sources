# ColorDataController::GetPrinterConfigMode(WCS_PROFILE_MANAGEMENT_SCOPE,Device const &,int *)

- ea: `0x180011f4c`
- end: `0x180011fad`
- name: `?GetPrinterConfigMode@ColorDataController@@QEBAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@AEBUDevice@@PEAH@Z`
- size: `97`
- prototype: `signed int __fastcall(ColorDataController *this, unsigned int, const struct Device *, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000dc0c`
- `0x18000e3fc`
- `0x18000e7ac`

## callees

- `0x180011f4c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011f89`
- `KERNEL32!GetLastError` at `0x180011f89`
- `mscms!InternalGetDeviceConfig` at `0x180011f7f`
- `mscms!InternalGetDeviceConfig` at `0x180011f7f`

## pseudocode

```c
signed int __fastcall ColorDataController::GetPrinterConfigMode(
        ColorDataController *this,
        unsigned int a2,
        const struct Device *a3,
        int *a4)
{
  signed int result; // eax
  int v5; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+44h] [rbp+Ch]

  v6 = HIDWORD(this);
  v5 = 4;
  if ( (unsigned int)InternalGetDeviceConfig(a2, (char *)a3 + 4, 1886549106, 1, a4, &v5) )
    return 0;
  result = GetLastError();
  if ( !result )
    return -2147467259;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180011f4c  mov     r11, rsp
0x180011f4f  mov     [r11+8], rcx
0x180011f53  sub     rsp, 38h
0x180011f57  lea     rcx, [r11+8]
0x180011f5b  mov     [rsp+38h+arg_0], 4
0x180011f63  mov     [r11-10h], rcx
0x180011f67  mov     eax, edx
0x180011f69  mov     [r11-18h], r9
0x180011f6d  lea     rdx, [r8+4]
0x180011f71  mov     r9d, 1
0x180011f77  mov     r8d, 70727472h
0x180011f7d  mov     ecx, eax
0x180011f7f  call    cs:__imp_InternalGetDeviceConfig
0x180011f85  test    eax, eax
0x180011f87  jnz     short loc_180011FA6
0x180011f89  call    cs:__imp_GetLastError
0x180011f8f  test    eax, eax
0x180011f91  jz      short loc_180011F9F
0x180011f93  jle     short loc_180011FA8
0x180011f95  movzx   eax, ax
0x180011f98  or      eax, 80070000h
0x180011f9d  jmp     short loc_180011FA8
0x180011f9f  mov     eax, 80004005h
0x180011fa4  jmp     short loc_180011FA8
0x180011fa6  xor     eax, eax
0x180011fa8  add     rsp, 38h
0x180011fac  retn
```
