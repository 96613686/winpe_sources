# AssociateQueueWithDeviceInfoList

- ea: `0x180026584`
- end: `0x18002662c`
- name: `AssociateQueueWithDeviceInfoList`
- size: `168`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000f698`
- `0x180027e90`
- `0x1800288a0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180026584`

## import_xrefs

- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180026601`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180026601`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800265dd`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800265dd`

## pseudocode

```c
BOOL __fastcall AssociateQueueWithDeviceInfoList(char *DeviceInfoSet, void *a2)
{
  BOOL result; // eax
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+20h] [rbp-268h] BYREF

  memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
  DeviceInstallParams.cbSize = 584;
  if ( (unsigned __int64)(DeviceInfoSet - 1) > 0xFFFFFFFFFFFFFFFDuLL || a2 == (void *)-1LL )
    return 0;
  result = SetupDiGetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams);
  if ( result )
  {
    DeviceInstallParams.FlagsEx |= 0x10000000u;
    DeviceInstallParams.Flags |= 8u;
    DeviceInstallParams.FileQueue = a2;
    return SetupDiSetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams);
  }
  return result;
}

```

## disassembly

```asm
0x180026584  mov     [rsp+arg_10], rbx
0x180026589  push    rdi
0x18002658a  sub     rsp, 280h
0x180026591  mov     rax, cs:__security_cookie
0x180026598  xor     rax, rsp
0x18002659b  mov     [rsp+288h+var_18], rax
0x1800265a3  mov     rbx, rdx
0x1800265a6  mov     rdi, rcx
0x1800265a9  xor     edx, edx; Val
0x1800265ab  lea     rcx, [rsp+288h+DeviceInstallParams.Flags]; void *
0x1800265b0  mov     r8d, 244h; Size
0x1800265b6  call    memset_0
0x1800265bb  lea     rax, [rdi-1]
0x1800265bf  mov     [rsp+288h+DeviceInstallParams.cbSize], 248h
0x1800265c7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800265cb  ja      short loc_180026609
0x1800265cd  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800265d1  jz      short loc_180026609
0x1800265d3  lea     r8, [rsp+288h+DeviceInstallParams]; DeviceInstallParams
0x1800265d8  xor     edx, edx; DeviceInfoData
0x1800265da  mov     rcx, rdi; DeviceInfoSet
0x1800265dd  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x1800265e3  test    eax, eax
0x1800265e5  jz      short loc_18002660B
0x1800265e7  bts     [rsp+288h+DeviceInstallParams.FlagsEx], 1Ch
0x1800265ed  lea     r8, [rsp+288h+DeviceInstallParams]; DeviceInstallParams
0x1800265f2  or      [rsp+288h+DeviceInstallParams.Flags], 8
0x1800265f7  xor     edx, edx; DeviceInfoData
0x1800265f9  mov     rcx, rdi; DeviceInfoSet
0x1800265fc  mov     [rsp+288h+DeviceInstallParams.FileQueue], rbx
0x180026601  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x180026607  jmp     short loc_18002660B
0x180026609  xor     eax, eax
0x18002660b  mov     rcx, [rsp+288h+var_18]
0x180026613  xor     rcx, rsp; StackCookie
0x180026616  call    __security_check_cookie
0x18002661b  mov     rbx, [rsp+288h+arg_10]
0x180026623  add     rsp, 280h
0x18002662a  pop     rdi
0x18002662b  retn
```
