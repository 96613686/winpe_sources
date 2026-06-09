# PuUninstallDevice(ushort *)

- ea: `0x1801a92a0`
- end: `0x1801a940f`
- name: `?PuUninstallDevice@@YAHPEAG@Z`
- size: `367`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18019ba98`
- `0x18019ec54`

## callees

- `0x180006350`
- `0x1801a92a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a9376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a9376`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x1801a9391`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x1801a9391`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a92f8`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a92f8`
- `DEVOBJ!DevObjDeleteDevice` at `0x1801a93b5`
- `DEVOBJ!DevObjDeleteDevice` at `0x1801a93b5`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801a9364`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801a9364`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a93df`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a93df`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x1801a9328`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x1801a9328`
- `CFGMGR32!CM_Reenumerate_DevNode` at `0x1801a93d0`
- `CFGMGR32!CM_Reenumerate_DevNode` at `0x1801a93d0`

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
0x1801a92a0  mov     r11, rsp
0x1801a92a3  mov     [r11+10h], rbx
0x1801a92a7  mov     [r11+18h], rdi
0x1801a92ab  push    rbp
0x1801a92ac  lea     rbp, [r11-5Fh]
0x1801a92b0  sub     rsp, 90h
0x1801a92b7  mov     rax, cs:__security_cookie
0x1801a92be  xor     rax, rsp
0x1801a92c1  mov     [rbp+57h+var_8], rax
0x1801a92c5  xorps   xmm0, xmm0
0x1801a92c8  mov     [rbp+57h+pdnDevInst], 0
0x1801a92cf  mov     rbx, rcx
0x1801a92d2  mov     qword ptr [r11-78h], 0
0x1801a92da  xor     ecx, ecx
0x1801a92dc  xor     r9d, r9d
0x1801a92df  xor     r8d, r8d
0x1801a92e2  xor     edx, edx
0x1801a92e4  movups  [rbp+57h+var_38], xmm0
0x1801a92e8  movups  xmmword ptr [rbp+57h+dnDevInst], xmm0
0x1801a92ec  movups  [rbp+57h+var_18], xmm0
0x1801a92f0  movups  [rbp+57h+var_58], xmm0
0x1801a92f4  movups  [rbp+57h+var_48], xmm0
0x1801a92f8  call    cs:__imp_DevObjCreateDeviceInfoList
0x1801a92ff  nop     dword ptr [rax+rax+00h]
0x1801a9304  mov     rdi, rax
0x1801a9307  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a930b  jnz     short loc_1801A9314
0x1801a930d  xor     ebx, ebx
0x1801a930f  jmp     loc_1801A93EB
0x1801a9314  lea     r9, [rbp+57h+var_58]
0x1801a9318  mov     dword ptr [rbp+57h+var_58], 20h ; ' '
0x1801a931f  xor     r8d, r8d
0x1801a9322  mov     rdx, rbx
0x1801a9325  mov     rcx, rdi
0x1801a9328  call    cs:__imp_DevObjOpenDeviceInterface
0x1801a932f  nop     dword ptr [rax+rax+00h]
0x1801a9334  mov     ebx, eax
0x1801a9336  test    eax, eax
0x1801a9338  jz      loc_1801A93DC
0x1801a933e  lea     rax, [rbp+57h+var_38]
0x1801a9342  mov     dword ptr [rbp+57h+var_38], 30h ; '0'
0x1801a9349  mov     [rsp+90h+var_68], rax
0x1801a934e  lea     rdx, [rbp+57h+var_58]
0x1801a9352  xor     r9d, r9d
0x1801a9355  mov     [rsp+90h+var_70], 0
0x1801a935e  xor     r8d, r8d
0x1801a9361  mov     rcx, rdi
0x1801a9364  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1801a936b  nop     dword ptr [rax+rax+00h]
0x1801a9370  mov     ebx, eax
0x1801a9372  test    eax, eax
0x1801a9374  jnz     short loc_1801A9387
0x1801a9376  call    cs:__imp_GetLastError
0x1801a937d  nop     dword ptr [rax+rax+00h]
0x1801a9382  cmp     eax, 7Ah ; 'z'
0x1801a9385  jnz     short loc_1801A93DC
0x1801a9387  mov     edx, [rbp+57h+dnDevInst+4]; dnDevInst
0x1801a938a  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x1801a938e  xor     r8d, r8d; ulFlags
0x1801a9391  call    cs:__imp_CM_Get_Parent
0x1801a9398  nop     dword ptr [rax+rax+00h]
0x1801a939d  test    eax, eax
0x1801a939f  jz      short loc_1801A93A8
0x1801a93a1  mov     [rbp+57h+pdnDevInst], 0
0x1801a93a8  xor     r9d, r9d
0x1801a93ab  lea     rdx, [rbp+57h+var_38]
0x1801a93af  xor     r8d, r8d
0x1801a93b2  mov     rcx, rdi
0x1801a93b5  call    cs:__imp_DevObjDeleteDevice
0x1801a93bc  nop     dword ptr [rax+rax+00h]
0x1801a93c1  mov     ebx, eax
0x1801a93c3  test    eax, eax
0x1801a93c5  jz      short loc_1801A93DC
0x1801a93c7  mov     ecx, [rbp+57h+pdnDevInst]; dnDevInst
0x1801a93ca  test    ecx, ecx
0x1801a93cc  jz      short loc_1801A93DC
0x1801a93ce  xor     edx, edx; ulFlags
0x1801a93d0  call    cs:__imp_CM_Reenumerate_DevNode
0x1801a93d7  nop     dword ptr [rax+rax+00h]
0x1801a93dc  mov     rcx, rdi
0x1801a93df  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1801a93e6  nop     dword ptr [rax+rax+00h]
0x1801a93eb  mov     eax, ebx
0x1801a93ed  mov     rcx, [rbp+57h+var_8]
0x1801a93f1  xor     rcx, rsp; StackCookie
0x1801a93f4  call    __security_check_cookie
0x1801a93f9  lea     r11, [rsp+90h+var_s0]
0x1801a9401  mov     rbx, [r11+18h]
0x1801a9405  mov     rdi, [r11+20h]
0x1801a9409  mov     rsp, r11
0x1801a940c  pop     rbp
0x1801a940d  retn
```
