# BluetoothConnectionManagerEnumConnection::HrCreateBluetoothConnectionInstance(_SP_DEVINFO_DATA &,INetConnection * *,ulong)

- ea: `0x1800211b4`
- end: `0x1800212ad`
- name: `?HrCreateBluetoothConnectionInstance@BluetoothConnectionManagerEnumConnection@@AEAAJAEAU_SP_DEVINFO_DATA@@PEAPEAUINetConnection@@K@Z`
- size: `249`
- prototype: `__int64 __fastcall(BluetoothConnectionManagerEnumConnection *__hidden this, struct _SP_DEVINFO_DATA *, struct INetConnection **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800212b4`

## callees

- `0x180001710`
- `0x18000538c`
- `0x1800211b4`
- `0x1800275bc`
- `0x180030b90`
- `0x180030ca0`
- `0x180030eac`

## import_xrefs

- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180021255`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180021255`

## pseudocode

```c
__int64 __fastcall BluetoothConnectionManagerEnumConnection::HrCreateBluetoothConnectionInstance(
        HDEVINFO *this,
        struct _SP_DEVINFO_DATA *a2,
        struct INetConnection **a3,
        unsigned int a4)
{
  __int64 v5; // rbp
  HWND v6; // rdx
  const struct _GUID *v7; // rcx
  int v8; // ebx
  HWND v9; // r8
  const struct _GUID *v10; // r9
  HDEVINFO DeviceInfoSet; // [rsp+30h] [rbp-1E8h] BYREF
  struct _SP_DEVINFO_DATA v13; // [rsp+38h] [rbp-1E0h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+60h] [rbp-1B8h] BYREF

  v5 = a4;
  v8 = HrSetupDiGetDeviceInstanceId(this[8], a2, DeviceInstanceId);
  if ( !v8 )
  {
    DeviceInfoSet = 0;
    memset(&v13, 0, sizeof(v13));
    v8 = HrSetupDiCreateDeviceInfoList(v7, v6, &DeviceInfoSet);
    if ( !v8 )
    {
      v8 = HrSetupDiOpenDeviceInfo(DeviceInfoSet, DeviceInstanceId, v9, 2u, &v13);
      if ( v8 )
        SetupDiDestroyDeviceInfoList(DeviceInfoSet);
      else
        v8 = BluetoothConnection::CreateInstance(DeviceInfoSet, &v13, DeviceInstanceId, v10, (void **)&a3[v5]);
    }
  }
  if ( v8 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_832bef7587b634ab7f982ca3c856be86_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800211b4  push    rbx
0x1800211b6  push    rbp
0x1800211b7  push    rsi
0x1800211b8  sub     rsp, 200h
0x1800211bf  mov     rax, cs:__security_cookie
0x1800211c6  xor     rax, rsp
0x1800211c9  mov     [rsp+218h+var_28], rax
0x1800211d1  mov     rcx, [rcx+40h]; DeviceInfoSet
0x1800211d5  mov     rsi, r8
0x1800211d8  lea     r8, [rsp+218h+DeviceInstanceId]; DeviceInstanceId
0x1800211dd  mov     ebp, r9d
0x1800211e0  call    ?HrSetupDiGetDeviceInstanceId@@YAJPEAXPEAU_SP_DEVINFO_DATA@@PEAGKPEAK@Z; HrSetupDiGetDeviceInstanceId(void *,_SP_DEVINFO_DATA *,ushort *,ulong,ulong *)
0x1800211e5  mov     ebx, eax
0x1800211e7  test    eax, eax
0x1800211e9  jnz     short loc_18002125B
0x1800211eb  xorps   xmm0, xmm0
0x1800211ee  mov     [rsp+218h+DeviceInfoSet], 0
0x1800211f7  lea     r8, [rsp+218h+DeviceInfoSet]; void **
0x1800211fc  movups  xmmword ptr [rsp+218h+var_1E0.cbSize], xmm0
0x180021201  movups  xmmword ptr [rsp+218h+var_1E0.ClassGuid.Data4+4], xmm0
0x180021206  call    ?HrSetupDiCreateDeviceInfoList@@YAJPEBU_GUID@@PEAUHWND__@@PEAPEAX@Z; HrSetupDiCreateDeviceInfoList(_GUID const *,HWND__ *,void * *)
0x18002120b  mov     ebx, eax
0x18002120d  test    eax, eax
0x18002120f  jnz     short loc_18002125B
0x180021211  mov     rcx, [rsp+218h+DeviceInfoSet]; void *
0x180021216  lea     rax, [rsp+218h+var_1E0]
0x18002121b  lea     r9d, [rbx+2]; unsigned int
0x18002121f  mov     [rsp+218h+var_1F8], rax; PSP_DEVINFO_DATA
0x180021224  lea     rdx, [rsp+218h+DeviceInstanceId]; unsigned __int16 *
0x180021229  call    ?HrSetupDiOpenDeviceInfo@@YAJQEAXPEBGPEAUHWND__@@KPEAU_SP_DEVINFO_DATA@@@Z; HrSetupDiOpenDeviceInfo(void * const,ushort const *,HWND__ *,ulong,_SP_DEVINFO_DATA *)
0x18002122e  mov     rcx, [rsp+218h+DeviceInfoSet]; void *
0x180021233  mov     ebx, eax
0x180021235  test    eax, eax
0x180021237  jnz     short loc_180021255
0x180021239  lea     rdx, [rsi+rbp*8]
0x18002123d  mov     [rsp+218h+var_1F8], rdx; void **
0x180021242  lea     r8, [rsp+218h+DeviceInstanceId]; unsigned __int16 *
0x180021247  lea     rdx, [rsp+218h+var_1E0]; struct _SP_DEVINFO_DATA *
0x18002124c  call    ?CreateInstance@BluetoothConnection@@SAJPEAXPEAU_SP_DEVINFO_DATA@@PEAGAEBU_GUID@@PEAPEAX@Z; BluetoothConnection::CreateInstance(void *,_SP_DEVINFO_DATA *,ushort *,_GUID const &,void * *)
0x180021251  mov     ebx, eax
0x180021253  jmp     short loc_18002125B
0x180021255  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18002125b  test    ebx, ebx
0x18002125d  jns     short loc_180021290
0x18002125f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021266  lea     rax, WPP_GLOBAL_Control
0x18002126d  cmp     rcx, rax
0x180021270  jz      short loc_180021290
0x180021272  test    byte ptr [rcx+1Ch], 1
0x180021276  jz      short loc_180021290
0x180021278  mov     rcx, [rcx+10h]
0x18002127c  lea     r8, WPP_832bef7587b634ab7f982ca3c856be86_Traceguids
0x180021283  mov     edx, 0Fh
0x180021288  mov     r9d, ebx
0x18002128b  call    WPP_SF_d
0x180021290  mov     eax, ebx
0x180021292  mov     rcx, [rsp+218h+var_28]
0x18002129a  xor     rcx, rsp; StackCookie
0x18002129d  call    __security_check_cookie
0x1800212a2  add     rsp, 200h
0x1800212a9  pop     rsi
0x1800212aa  pop     rbp
0x1800212ab  pop     rbx
0x1800212ac  retn
```
