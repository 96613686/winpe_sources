# DisassociateQueueFromDeviceInfoList

- ea: `0x180026f2c`
- end: `0x180027015`
- name: `DisassociateQueueFromDeviceInfoList`
- size: `233`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000f698`
- `0x180026ed4`
- `0x180027e90`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180026f2c`

## import_xrefs

- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180026fda`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180026fda`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180026f88`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180026f88`

## pseudocode

```c
__int64 __fastcall DisassociateQueueFromDeviceInfoList(char *DeviceInfoSet, _QWORD *a2)
{
  unsigned int v4; // ebx
  HSPFILEQ FileQueue; // rdi
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+20h] [rbp-278h] BYREF

  memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
  DeviceInstallParams.cbSize = 584;
  if ( (unsigned __int64)(DeviceInfoSet - 1) > 0xFFFFFFFFFFFFFFFDuLL || !a2 )
    return 0;
  v4 = 0;
  if ( SetupDiGetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams) )
  {
    if ( (DeviceInstallParams.FlagsEx & 0x10000000) != 0 && (DeviceInstallParams.Flags & 8) != 0 )
    {
      FileQueue = DeviceInstallParams.FileQueue;
      if ( (unsigned __int64)DeviceInstallParams.FileQueue - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        DeviceInstallParams.FileQueue = (HSPFILEQ)-1LL;
        DeviceInstallParams.FlagsEx &= ~0x10000000u;
        DeviceInstallParams.Flags &= ~8u;
        if ( SetupDiSetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams) )
        {
          v4 = 1;
          *a2 = FileQueue;
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180026f2c  mov     [rsp+arg_10], rbx
0x180026f31  push    rbp
0x180026f32  push    rsi
0x180026f33  push    rdi
0x180026f34  sub     rsp, 280h
0x180026f3b  mov     rax, cs:__security_cookie
0x180026f42  xor     rax, rsp
0x180026f45  mov     [rsp+298h+var_28], rax
0x180026f4d  mov     rsi, rdx
0x180026f50  mov     rbp, rcx
0x180026f53  xor     edx, edx; Val
0x180026f55  lea     rcx, [rsp+298h+DeviceInstallParams.Flags]; void *
0x180026f5a  mov     r8d, 244h; Size
0x180026f60  call    memset_0
0x180026f65  lea     rax, [rbp-1]
0x180026f69  mov     [rsp+298h+DeviceInstallParams.cbSize], 248h
0x180026f71  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026f75  ja      short loc_180026FF0
0x180026f77  test    rsi, rsi
0x180026f7a  jz      short loc_180026FF0
0x180026f7c  lea     r8, [rsp+298h+DeviceInstallParams]; DeviceInstallParams
0x180026f81  xor     edx, edx; DeviceInfoData
0x180026f83  mov     rcx, rbp; DeviceInfoSet
0x180026f86  xor     ebx, ebx
0x180026f88  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x180026f8e  test    eax, eax
0x180026f90  jz      short loc_180026FEC
0x180026f92  mov     edx, [rsp+298h+DeviceInstallParams.FlagsEx]
0x180026f96  bt      edx, 1Ch
0x180026f9a  jnb     short loc_180026FEC
0x180026f9c  mov     r8d, [rsp+298h+DeviceInstallParams.Flags]
0x180026fa1  test    r8b, 8
0x180026fa5  jz      short loc_180026FEC
0x180026fa7  mov     rdi, [rsp+298h+DeviceInstallParams.FileQueue]
0x180026fac  lea     rax, [rdi-1]
0x180026fb0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026fb4  ja      short loc_180026FEC
0x180026fb6  btr     edx, 1Ch
0x180026fba  mov     [rsp+298h+DeviceInstallParams.FileQueue], 0FFFFFFFFFFFFFFFFh
0x180026fc3  and     r8d, 0FFFFFFF7h
0x180026fc7  mov     [rsp+298h+DeviceInstallParams.FlagsEx], edx
0x180026fcb  mov     [rsp+298h+DeviceInstallParams.Flags], r8d
0x180026fd0  xor     edx, edx; DeviceInfoData
0x180026fd2  lea     r8, [rsp+298h+DeviceInstallParams]; DeviceInstallParams
0x180026fd7  mov     rcx, rbp; DeviceInfoSet
0x180026fda  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x180026fe0  test    eax, eax
0x180026fe2  jz      short loc_180026FEC
0x180026fe4  mov     ebx, 1
0x180026fe9  mov     [rsi], rdi
0x180026fec  mov     eax, ebx
0x180026fee  jmp     short loc_180026FF2
0x180026ff0  xor     eax, eax
0x180026ff2  mov     rcx, [rsp+298h+var_28]
0x180026ffa  xor     rcx, rsp; StackCookie
0x180026ffd  call    __security_check_cookie
0x180027002  mov     rbx, [rsp+298h+arg_10]
0x18002700a  add     rsp, 280h
0x180027011  pop     rdi
0x180027012  pop     rsi
0x180027013  pop     rbp
0x180027014  retn
```
