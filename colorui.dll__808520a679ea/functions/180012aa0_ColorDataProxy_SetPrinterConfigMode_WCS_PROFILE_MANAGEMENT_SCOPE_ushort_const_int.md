# ColorDataProxy::SetPrinterConfigMode(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,int)

- ea: `0x180012aa0`
- end: `0x180012b01`
- name: `?SetPrinterConfigMode@ColorDataProxy@@UEAAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGH@Z`
- size: `97`
- prototype: `signed int __fastcall(ColorDataProxy *this, unsigned int, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180012aa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012add`
- `KERNEL32!GetLastError` at `0x180012add`
- `mscms!InternalSetDeviceConfig` at `0x180012ad3`
- `mscms!InternalSetDeviceConfig` at `0x180012ad3`

## pseudocode

```c
signed int __fastcall ColorDataProxy::SetPrinterConfigMode(
        ColorDataProxy *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        int a4)
{
  signed int result; // eax
  int v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = a4;
  if ( (unsigned int)InternalSetDeviceConfig(a2, a3, 1886549106, 1, &v5, 4) )
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
0x180012aa0  mov     [rsp+arg_18], r9d
0x180012aa5  sub     rsp, 38h
0x180012aa9  lea     rcx, [rsp+38h+arg_18]
0x180012aae  mov     [rsp+38h+var_10], 4
0x180012ab6  mov     rax, r8
0x180012ab9  mov     [rsp+38h+var_18], rcx
0x180012abe  mov     r10d, edx
0x180012ac1  mov     r9d, 1
0x180012ac7  mov     ecx, r10d
0x180012aca  mov     r8d, 70727472h
0x180012ad0  mov     rdx, rax
0x180012ad3  call    cs:__imp_InternalSetDeviceConfig
0x180012ad9  test    eax, eax
0x180012adb  jnz     short loc_180012AFA
0x180012add  call    cs:__imp_GetLastError
0x180012ae3  test    eax, eax
0x180012ae5  jz      short loc_180012AF3
0x180012ae7  jle     short loc_180012AFC
0x180012ae9  movzx   eax, ax
0x180012aec  or      eax, 80070000h
0x180012af1  jmp     short loc_180012AFC
0x180012af3  mov     eax, 80004005h
0x180012af8  jmp     short loc_180012AFC
0x180012afa  xor     eax, eax
0x180012afc  add     rsp, 38h
0x180012b00  retn
```
