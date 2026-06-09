# HrSetupDiOpenDeviceInfo(void * const,ushort const *,HWND__ *,ulong,_SP_DEVINFO_DATA *)

- ea: `0x180030eac`
- end: `0x180030eef`
- name: `?HrSetupDiOpenDeviceInfo@@YAJQEAXPEBGPEAUHWND__@@KPEAU_SP_DEVINFO_DATA@@@Z`
- size: `67`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, HWND, unsigned int, PSP_DEVINFO_DATA)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001e6c8`
- `0x1800211b4`
- `0x180025c44`

## callees

- `0x18003060c`
- `0x180030eac`

## import_xrefs

- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180030ed6`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180030ed6`

## pseudocode

```c
__int64 __fastcall HrSetupDiOpenDeviceInfo(
        void *const a1,
        const unsigned __int16 *a2,
        HWND a3,
        DWORD a4,
        PSP_DEVINFO_DATA DeviceInfoData)
{
  unsigned int v5; // ebx

  if ( DeviceInfoData )
  {
    *(_OWORD *)&DeviceInfoData->cbSize = 0;
    *(_OWORD *)&DeviceInfoData->ClassGuid.Data4[4] = 0;
    DeviceInfoData->cbSize = 32;
  }
  v5 = 0;
  if ( !SetupDiOpenDeviceInfoW(a1, a2, 0, a4, DeviceInfoData) )
    return (unsigned int)HrFromLastWin32Error();
  return v5;
}

```

## disassembly

```asm
0x180030eac  push    rbx
0x180030eae  sub     rsp, 30h
0x180030eb2  mov     rax, [rsp+38h+arg_20]
0x180030eb7  test    rax, rax
0x180030eba  jz      short loc_180030ECC
0x180030ebc  xorps   xmm0, xmm0
0x180030ebf  movups  xmmword ptr [rax], xmm0
0x180030ec2  movups  xmmword ptr [rax+10h], xmm0
0x180030ec6  mov     dword ptr [rax], 20h ; ' '
0x180030ecc  xor     r8d, r8d; hwndParent
0x180030ecf  mov     [rsp+38h+DeviceInfoData], rax; DeviceInfoData
0x180030ed4  xor     ebx, ebx
0x180030ed6  call    cs:__imp_SetupDiOpenDeviceInfoW
0x180030edc  test    eax, eax
0x180030ede  jnz     short loc_180030EE7
0x180030ee0  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180030ee5  mov     ebx, eax
0x180030ee7  mov     eax, ebx
0x180030ee9  add     rsp, 30h
0x180030eed  pop     rbx
0x180030eee  retn
```
