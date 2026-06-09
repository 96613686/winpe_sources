# PuUninstallDevice(ushort *)

- ea: `0x1801a3e68`
- end: `0x1801a3fa6`
- name: `?PuUninstallDevice@@YAHPEAG@Z`
- size: `318`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180196f6c`
- `0x180199f2c`

## callees

- `0x180006290`
- `0x1801a3e68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3f2c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x1801a3f41`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x1801a3f41`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a3ec0`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a3ec0`
- `DEVOBJ!DevObjDeleteDevice` at `0x1801a3f5f`
- `DEVOBJ!DevObjDeleteDevice` at `0x1801a3f5f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801a3f20`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801a3f20`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a3f7d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a3f7d`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x1801a3eea`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x1801a3eea`
- `CFGMGR32!CM_Reenumerate_DevNode` at `0x1801a3f74`
- `CFGMGR32!CM_Reenumerate_DevNode` at `0x1801a3f74`

## pseudocode

```c
__int64 __fastcall PuUninstallDevice(unsigned __int16 *a1)
{
  __int64 DeviceInfoList; // rax
  __int64 v3; // rdi
  unsigned int DeviceInterfaceDetail; // ebx
  DEVNODE pdnDevInst; // [rsp+38h] [rbp-9h] BYREF
  _OWORD v7[2]; // [rsp+40h] [rbp-1h] BYREF
  __int128 v8; // [rsp+60h] [rbp+1Fh] BYREF
  DEVINST dnDevInst[4]; // [rsp+70h] [rbp+2Fh]
  __int128 v10; // [rsp+80h] [rbp+3Fh]

  pdnDevInst = 0;
  v8 = 0;
  *(_OWORD *)dnDevInst = 0;
  v10 = 0;
  memset(v7, 0, sizeof(v7));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v3 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    return 0;
  }
  else
  {
    LODWORD(v7[0]) = 32;
    DeviceInterfaceDetail = DevObjOpenDeviceInterface(DeviceInfoList, a1, 0, v7);
    if ( DeviceInterfaceDetail )
    {
      LODWORD(v8) = 48;
      DeviceInterfaceDetail = DevObjGetDeviceInterfaceDetail(v3, v7, 0, 0, 0, &v8);
      if ( DeviceInterfaceDetail || GetLastError() == 122 )
      {
        if ( CM_Get_Parent(&pdnDevInst, dnDevInst[1], 0) )
          pdnDevInst = 0;
        DeviceInterfaceDetail = DevObjDeleteDevice(v3, &v8, 0, 0);
        if ( DeviceInterfaceDetail && pdnDevInst )
          CM_Reenumerate_DevNode(pdnDevInst, 0);
      }
    }
    DevObjDestroyDeviceInfoList(v3);
  }
  return DeviceInterfaceDetail;
}

```

## disassembly

```asm
0x1801a3e68  mov     r11, rsp
0x1801a3e6b  mov     [r11+10h], rbx
0x1801a3e6f  mov     [r11+18h], rdi
0x1801a3e73  push    rbp
0x1801a3e74  lea     rbp, [r11-5Fh]
0x1801a3e78  sub     rsp, 90h
0x1801a3e7f  mov     rax, cs:__security_cookie
0x1801a3e86  xor     rax, rsp
0x1801a3e89  mov     [rbp+57h+var_8], rax
0x1801a3e8d  xorps   xmm0, xmm0
0x1801a3e90  mov     [rbp+57h+pdnDevInst], 0
0x1801a3e97  mov     rbx, rcx
0x1801a3e9a  mov     qword ptr [r11-78h], 0
0x1801a3ea2  xor     ecx, ecx
0x1801a3ea4  xor     r9d, r9d
0x1801a3ea7  xor     r8d, r8d
0x1801a3eaa  xor     edx, edx
0x1801a3eac  movups  [rbp+57h+var_38], xmm0
0x1801a3eb0  movups  xmmword ptr [rbp+57h+dnDevInst], xmm0
0x1801a3eb4  movups  [rbp+57h+var_18], xmm0
0x1801a3eb8  movups  [rbp+57h+var_58], xmm0
0x1801a3ebc  movups  [rbp+57h+var_48], xmm0
0x1801a3ec0  call    cs:__imp_DevObjCreateDeviceInfoList
0x1801a3ec6  mov     rdi, rax
0x1801a3ec9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a3ecd  jnz     short loc_1801A3ED6
0x1801a3ecf  xor     ebx, ebx
0x1801a3ed1  jmp     loc_1801A3F83
0x1801a3ed6  lea     r9, [rbp+57h+var_58]
0x1801a3eda  mov     dword ptr [rbp+57h+var_58], 20h ; ' '
0x1801a3ee1  xor     r8d, r8d
0x1801a3ee4  mov     rdx, rbx
0x1801a3ee7  mov     rcx, rdi
0x1801a3eea  call    cs:__imp_DevObjOpenDeviceInterface
0x1801a3ef0  mov     ebx, eax
0x1801a3ef2  test    eax, eax
0x1801a3ef4  jz      loc_1801A3F7A
0x1801a3efa  lea     rax, [rbp+57h+var_38]
0x1801a3efe  mov     dword ptr [rbp+57h+var_38], 30h ; '0'
0x1801a3f05  mov     [rsp+90h+var_68], rax
0x1801a3f0a  lea     rdx, [rbp+57h+var_58]
0x1801a3f0e  xor     r9d, r9d
0x1801a3f11  mov     [rsp+90h+var_70], 0
0x1801a3f1a  xor     r8d, r8d
0x1801a3f1d  mov     rcx, rdi
0x1801a3f20  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1801a3f26  mov     ebx, eax
0x1801a3f28  test    eax, eax
0x1801a3f2a  jnz     short loc_1801A3F37
0x1801a3f2c  call    cs:__imp_GetLastError
0x1801a3f32  cmp     eax, 7Ah ; 'z'
0x1801a3f35  jnz     short loc_1801A3F7A
0x1801a3f37  mov     edx, [rbp+57h+dnDevInst+4]; dnDevInst
0x1801a3f3a  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x1801a3f3e  xor     r8d, r8d; ulFlags
0x1801a3f41  call    cs:__imp_CM_Get_Parent
0x1801a3f47  test    eax, eax
0x1801a3f49  jz      short loc_1801A3F52
0x1801a3f4b  mov     [rbp+57h+pdnDevInst], 0
0x1801a3f52  xor     r9d, r9d
0x1801a3f55  lea     rdx, [rbp+57h+var_38]
0x1801a3f59  xor     r8d, r8d
0x1801a3f5c  mov     rcx, rdi
0x1801a3f5f  call    cs:__imp_DevObjDeleteDevice
0x1801a3f65  mov     ebx, eax
0x1801a3f67  test    eax, eax
0x1801a3f69  jz      short loc_1801A3F7A
0x1801a3f6b  mov     ecx, [rbp+57h+pdnDevInst]; dnDevInst
0x1801a3f6e  test    ecx, ecx
0x1801a3f70  jz      short loc_1801A3F7A
0x1801a3f72  xor     edx, edx; ulFlags
0x1801a3f74  call    cs:__imp_CM_Reenumerate_DevNode
0x1801a3f7a  mov     rcx, rdi
0x1801a3f7d  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1801a3f83  mov     eax, ebx
0x1801a3f85  mov     rcx, [rbp+57h+var_8]
0x1801a3f89  xor     rcx, rsp; StackCookie
0x1801a3f8c  call    __security_check_cookie
0x1801a3f91  lea     r11, [rsp+90h+var_s0]
0x1801a3f99  mov     rbx, [r11+18h]
0x1801a3f9d  mov     rdi, [r11+20h]
0x1801a3fa1  mov     rsp, r11
0x1801a3fa4  pop     rbp
0x1801a3fa5  retn
```
