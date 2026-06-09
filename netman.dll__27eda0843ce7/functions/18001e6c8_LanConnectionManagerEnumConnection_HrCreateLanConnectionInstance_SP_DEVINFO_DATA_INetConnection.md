# LanConnectionManagerEnumConnection::HrCreateLanConnectionInstance(_SP_DEVINFO_DATA &,INetConnection * *)

- ea: `0x18001e6c8`
- end: `0x18001e7bd`
- name: `?HrCreateLanConnectionInstance@LanConnectionManagerEnumConnection@@AEAAJAEAU_SP_DEVINFO_DATA@@PEAPEAUINetConnection@@@Z`
- size: `245`
- prototype: `int(LanConnectionManagerEnumConnection *__hidden this, struct _SP_DEVINFO_DATA *, struct INetConnection **)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001eb7c`

## callees

- `0x180001710`
- `0x18000538c`
- `0x18001e6c8`
- `0x180024674`
- `0x180030b90`
- `0x180030ca0`
- `0x180030eac`

## import_xrefs

- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18001e75f`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18001e75f`

## pseudocode

```c
__int64 __fastcall LanConnectionManagerEnumConnection::HrCreateLanConnectionInstance(
        HDEVINFO *this,
        struct _SP_DEVINFO_DATA *a2,
        struct INetConnection **a3)
{
  HWND v4; // rdx
  const struct _GUID *v5; // rcx
  int v6; // ebx
  HWND v7; // r8
  const unsigned __int16 *v8; // r8
  const struct _GUID *v9; // r9
  HDEVINFO DeviceInfoSet; // [rsp+30h] [rbp-1D8h] BYREF
  struct _SP_DEVINFO_DATA v12; // [rsp+38h] [rbp-1D0h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+60h] [rbp-1A8h] BYREF

  v6 = HrSetupDiGetDeviceInstanceId(this[8], a2, DeviceInstanceId);
  if ( !v6 )
  {
    DeviceInfoSet = 0;
    memset(&v12, 0, sizeof(v12));
    v6 = HrSetupDiCreateDeviceInfoList(v5, v4, &DeviceInfoSet);
    if ( !v6 )
    {
      v6 = HrSetupDiOpenDeviceInfo(DeviceInfoSet, DeviceInstanceId, v7, 2u, &v12);
      if ( v6 )
        SetupDiDestroyDeviceInfoList(DeviceInfoSet);
      else
        v6 = LanConnection::CreateInstance(DeviceInfoSet, &v12, v8, v9, (void **)a3);
    }
  }
  if ( v6 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_35d09b3fa63b3959b71899817b9a8e52_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001e6c8  mov     [rsp+arg_18], rbx
0x18001e6cd  push    rsi
0x18001e6ce  sub     rsp, 200h
0x18001e6d5  mov     rax, cs:__security_cookie
0x18001e6dc  xor     rax, rsp
0x18001e6df  mov     [rsp+208h+var_18], rax
0x18001e6e7  mov     rcx, [rcx+40h]; DeviceInfoSet
0x18001e6eb  mov     rsi, r8
0x18001e6ee  lea     r8, [rsp+208h+DeviceInstanceId]; DeviceInstanceId
0x18001e6f3  call    ?HrSetupDiGetDeviceInstanceId@@YAJPEAXPEAU_SP_DEVINFO_DATA@@PEAGKPEAK@Z; HrSetupDiGetDeviceInstanceId(void *,_SP_DEVINFO_DATA *,ushort *,ulong,ulong *)
0x18001e6f8  mov     ebx, eax
0x18001e6fa  test    eax, eax
0x18001e6fc  jnz     short loc_18001E765
0x18001e6fe  xorps   xmm0, xmm0
0x18001e701  mov     [rsp+208h+DeviceInfoSet], 0
0x18001e70a  lea     r8, [rsp+208h+DeviceInfoSet]; void **
0x18001e70f  movups  xmmword ptr [rsp+208h+var_1D0.cbSize], xmm0
0x18001e714  movups  xmmword ptr [rsp+208h+var_1D0.ClassGuid.Data4+4], xmm0
0x18001e719  call    ?HrSetupDiCreateDeviceInfoList@@YAJPEBU_GUID@@PEAUHWND__@@PEAPEAX@Z; HrSetupDiCreateDeviceInfoList(_GUID const *,HWND__ *,void * *)
0x18001e71e  mov     ebx, eax
0x18001e720  test    eax, eax
0x18001e722  jnz     short loc_18001E765
0x18001e724  mov     rcx, [rsp+208h+DeviceInfoSet]; void *
0x18001e729  lea     rax, [rsp+208h+var_1D0]
0x18001e72e  lea     r9d, [rbx+2]; unsigned int
0x18001e732  mov     [rsp+208h+var_1E8], rax; PSP_DEVINFO_DATA
0x18001e737  lea     rdx, [rsp+208h+DeviceInstanceId]; unsigned __int16 *
0x18001e73c  call    ?HrSetupDiOpenDeviceInfo@@YAJQEAXPEBGPEAUHWND__@@KPEAU_SP_DEVINFO_DATA@@@Z; HrSetupDiOpenDeviceInfo(void * const,ushort const *,HWND__ *,ulong,_SP_DEVINFO_DATA *)
0x18001e741  mov     rcx, [rsp+208h+DeviceInfoSet]; DeviceInfoSet
0x18001e746  mov     ebx, eax
0x18001e748  test    eax, eax
0x18001e74a  jnz     short loc_18001E75F
0x18001e74c  lea     rdx, [rsp+208h+var_1D0]; struct _SP_DEVINFO_DATA *
0x18001e751  mov     [rsp+208h+var_1E8], rsi; void **
0x18001e756  call    ?CreateInstance@LanConnection@@SAJPEAXAEBU_SP_DEVINFO_DATA@@PEBGAEBU_GUID@@PEAPEAX@Z; LanConnection::CreateInstance(void *,_SP_DEVINFO_DATA const &,ushort const *,_GUID const &,void * *)
0x18001e75b  mov     ebx, eax
0x18001e75d  jmp     short loc_18001E765
0x18001e75f  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18001e765  test    ebx, ebx
0x18001e767  jns     short loc_18001E79A
0x18001e769  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e770  lea     rax, WPP_GLOBAL_Control
0x18001e777  cmp     rcx, rax
0x18001e77a  jz      short loc_18001E79A
0x18001e77c  test    byte ptr [rcx+1Ch], 1
0x18001e780  jz      short loc_18001E79A
0x18001e782  mov     rcx, [rcx+10h]
0x18001e786  lea     r8, WPP_35d09b3fa63b3959b71899817b9a8e52_Traceguids
0x18001e78d  mov     edx, 0Fh
0x18001e792  mov     r9d, ebx
0x18001e795  call    WPP_SF_d
0x18001e79a  mov     eax, ebx
0x18001e79c  mov     rcx, [rsp+208h+var_18]
0x18001e7a4  xor     rcx, rsp; StackCookie
0x18001e7a7  call    __security_check_cookie
0x18001e7ac  mov     rbx, [rsp+208h+arg_18]
0x18001e7b4  add     rsp, 200h
0x18001e7bb  pop     rsi
0x18001e7bc  retn
```
