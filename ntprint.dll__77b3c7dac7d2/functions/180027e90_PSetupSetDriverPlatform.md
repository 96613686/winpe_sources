# PSetupSetDriverPlatform

- ea: `0x180027e90`
- end: `0x180028030`
- name: `PSetupSetDriverPlatform`
- size: `416`
- prototype: `__int64 __usercall@<rax>(HDEVINFO DeviceInfoSet@<rcx>, int, int)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18001de14`
- `0x180026c04`
- `0x180026d10`
- `0x180026df0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18001e164`
- `0x180026584`
- `0x180026f2c`
- `0x180027e90`
- `0x180036248`

## import_xrefs

- `SETUPAPI!SetupOpenFileQueue` at `0x180027f80`
- `SETUPAPI!SetupOpenFileQueue` at `0x180027f80`
- `SETUPAPI!SetupCloseFileQueue` at `0x180027efd`
- `SETUPAPI!SetupCloseFileQueue` at `0x180027ffd`
- `SETUPAPI!SetupCloseFileQueue` at `0x180027efd`
- `SETUPAPI!SetupCloseFileQueue` at `0x180027ffd`
- `SETUPAPI!SetupSetFileQueueAlternatePlatformW` at `0x180027fd7`
- `SETUPAPI!SetupSetFileQueueAlternatePlatformW` at `0x180027fd7`

## pseudocode

```c
__int64 __fastcall PSetupSetDriverPlatform(char *DeviceInfoSet, int a2, int a3, WCHAR *a4, int a5, int a6)
{
  __int64 v6; // r13
  __int64 v7; // rbx
  unsigned int OSVersion; // edi
  int dwMajorVersion; // edi
  int dwMinorVersion; // esi
  HSPFILEQ v15; // rax
  struct _SP_ALTPLATFORM_INFO_V2 AlternatePlatformInfo; // [rsp+28h] [rbp-D8h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF

  v6 = a2;
  v7 = -1;
  memset(&AlternatePlatformInfo, 0, sizeof(AlternatePlatformInfo));
  if ( (unsigned __int64)(DeviceInfoSet - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( (unsigned int)DisassociateQueueFromDeviceInfoList(DeviceInfoSet) )
      SetupCloseFileQueue((HSPFILEQ)0xFFFFFFFFFFFFFFFFLL);
    else
      v7 = -1;
    memset_0(&VersionInformation, 0, sizeof(VersionInformation));
    OSVersion = GetOSVersion(a4, &VersionInformation);
    if ( !OSVersion )
      goto LABEL_18;
    dwMajorVersion = VersionInformation.dwMajorVersion;
    dwMinorVersion = VersionInformation.dwMinorVersion;
    if ( MyPlatform == (_DWORD)v6 && (unsigned int)IsLocalMachine(a4) )
    {
      if ( !a3 || dwMajorVersion == a5 && dwMinorVersion == a6 )
        return 1;
    }
    else if ( !a3 )
    {
      goto LABEL_14;
    }
    dwMajorVersion = a5;
    dwMinorVersion = a6;
LABEL_14:
    v15 = SetupOpenFileQueue();
    v7 = (__int64)v15;
    if ( v15 == (HSPFILEQ)-1LL )
    {
      OSVersion = 0;
    }
    else
    {
      AlternatePlatformInfo.cbSize = 28;
      AlternatePlatformInfo.Platform = *(&PlatformArch + 2 * v6);
      AlternatePlatformInfo.ProcessorArchitecture = *((_WORD *)&PlatformArch + 4 * v6 + 2);
      AlternatePlatformInfo.Reserved = 0;
      AlternatePlatformInfo.MajorVersion = dwMajorVersion;
      AlternatePlatformInfo.MinorVersion = dwMinorVersion;
      AlternatePlatformInfo.FirstValidatedMajorVersion = dwMajorVersion;
      AlternatePlatformInfo.FirstValidatedMinorVersion = dwMinorVersion;
      OSVersion = SetupSetFileQueueAlternatePlatformW(v15, &AlternatePlatformInfo, 0);
      if ( OSVersion )
      {
        OSVersion = AssociateQueueWithDeviceInfoList(DeviceInfoSet);
        if ( OSVersion )
          return OSVersion;
      }
    }
LABEL_18:
    if ( v7 != -1 )
      SetupCloseFileQueue((HSPFILEQ)v7);
    return OSVersion;
  }
  return 0;
}

```

## disassembly

```asm
0x180027e90  mov     [rsp-8+arg_10], rbx
0x180027e95  push    rbp
0x180027e96  push    rsi
0x180027e97  push    rdi
0x180027e98  push    r12
0x180027e9a  push    r13
0x180027e9c  push    r14
0x180027e9e  push    r15
0x180027ea0  lea     rbp, [rsp-80h]
0x180027ea5  sub     rsp, 180h
0x180027eac  mov     rax, cs:__security_cookie
0x180027eb3  xor     rax, rsp
0x180027eb6  mov     [rbp+0B0h+var_40], rax
0x180027eba  xorps   xmm0, xmm0
0x180027ebd  movsxd  r13, edx
0x180027ec0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180027ec4  lea     rax, [rcx-1]
0x180027ec8  mov     [rsp+1B0h+QueueHandle], rbx
0x180027ecd  mov     r12, r9
0x180027ed0  mov     r15d, r8d
0x180027ed3  mov     r14, rcx
0x180027ed6  movups  xmmword ptr [rsp+1B0h+AlternatePlatformInfo.cbSize], xmm0
0x180027edb  movups  xmmword ptr [rsp+1B0h+AlternatePlatformInfo.MinorVersion], xmm0
0x180027ee0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180027ee4  ja      loc_180028007
0x180027eea  lea     rdx, [rsp+1B0h+QueueHandle]
0x180027eef  call    DisassociateQueueFromDeviceInfoList
0x180027ef4  test    eax, eax
0x180027ef6  jz      short loc_180027F05
0x180027ef8  mov     rcx, [rsp+1B0h+QueueHandle]; QueueHandle
0x180027efd  call    cs:__imp_SetupCloseFileQueue
0x180027f03  jmp     short loc_180027F0A
0x180027f05  mov     rbx, [rsp+1B0h+QueueHandle]
0x180027f0a  xor     edx, edx; Val
0x180027f0c  lea     rcx, [rsp+1B0h+VersionInformation]; void *
0x180027f11  mov     r8d, 114h; Size
0x180027f17  call    memset_0
0x180027f1c  lea     rdx, [rsp+1B0h+VersionInformation]; lpVersionInformation
0x180027f21  mov     rcx, r12; pPrinterName
0x180027f24  call    GetOSVersion
0x180027f29  mov     edi, eax
0x180027f2b  test    eax, eax
0x180027f2d  jz      loc_180027FF4
0x180027f33  cmp     cs:MyPlatform, r13d
0x180027f3a  mov     edi, [rsp+1B0h+VersionInformation.dwMajorVersion]
0x180027f3e  mov     esi, [rsp+1B0h+VersionInformation.dwMinorVersion]
0x180027f42  jnz     short loc_180027F6F
0x180027f44  mov     rcx, r12; lpString1
0x180027f47  call    IsLocalMachine
0x180027f4c  test    eax, eax
0x180027f4e  jz      short loc_180027F6F
0x180027f50  test    r15d, r15d
0x180027f53  jz      short loc_180027F65
0x180027f55  cmp     edi, [rbp+0B0h+arg_20]
0x180027f5b  jnz     short loc_180027F74
0x180027f5d  cmp     esi, [rbp+0B0h+arg_28]
0x180027f63  jnz     short loc_180027F74
0x180027f65  mov     eax, 1
0x180027f6a  jmp     loc_180028009
0x180027f6f  test    r15d, r15d
0x180027f72  jz      short loc_180027F80
0x180027f74  mov     edi, [rbp+0B0h+arg_20]
0x180027f7a  mov     esi, [rbp+0B0h+arg_28]
0x180027f80  call    cs:__imp_SetupOpenFileQueue
0x180027f86  mov     rbx, rax
0x180027f89  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027f8d  jnz     short loc_180027F93
0x180027f8f  xor     edi, edi
0x180027f91  jmp     short loc_180027FF4
0x180027f93  lea     rdx, PlatformArch
0x180027f9a  mov     [rsp+1B0h+AlternatePlatformInfo.cbSize], 1Ch
0x180027fa2  mov     eax, [rdx+r13*8]
0x180027fa6  xor     r8d, r8d; AlternateDefaultCatalogFile
0x180027fa9  mov     [rsp+1B0h+AlternatePlatformInfo.Platform], eax
0x180027fad  mov     rcx, rbx; QueueHandle
0x180027fb0  movzx   eax, word ptr [rdx+r13*8+4]
0x180027fb6  lea     rdx, [rsp+1B0h+AlternatePlatformInfo]; AlternatePlatformInfo
0x180027fbb  mov     [rsp+1B0h+AlternatePlatformInfo.ProcessorArchitecture], ax
0x180027fc0  xor     eax, eax
0x180027fc2  mov     word ptr [rsp+1B0h+AlternatePlatformInfo.12h], ax
0x180027fc7  mov     [rsp+1B0h+AlternatePlatformInfo.MajorVersion], edi
0x180027fcb  mov     [rsp+1B0h+AlternatePlatformInfo.MinorVersion], esi
0x180027fcf  mov     [rsp+1B0h+AlternatePlatformInfo.FirstValidatedMajorVersion], edi
0x180027fd3  mov     [rsp+1B0h+AlternatePlatformInfo.FirstValidatedMinorVersion], esi
0x180027fd7  call    cs:__imp_SetupSetFileQueueAlternatePlatformW
0x180027fdd  mov     edi, eax
0x180027fdf  test    eax, eax
0x180027fe1  jz      short loc_180027FF4
0x180027fe3  mov     rdx, rbx
0x180027fe6  mov     rcx, r14; DeviceInfoSet
0x180027fe9  call    AssociateQueueWithDeviceInfoList
0x180027fee  mov     edi, eax
0x180027ff0  test    eax, eax
0x180027ff2  jnz     short loc_180028003
0x180027ff4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180027ff8  jz      short loc_180028003
0x180027ffa  mov     rcx, rbx; QueueHandle
0x180027ffd  call    cs:__imp_SetupCloseFileQueue
0x180028003  mov     eax, edi
0x180028005  jmp     short loc_180028009
0x180028007  xor     eax, eax
0x180028009  mov     rcx, [rbp+0B0h+var_40]
0x18002800d  xor     rcx, rsp; StackCookie
0x180028010  call    __security_check_cookie
0x180028015  mov     rbx, [rsp+1B0h+arg_10]
0x18002801d  add     rsp, 180h
0x180028024  pop     r15
0x180028026  pop     r14
0x180028028  pop     r13
0x18002802a  pop     r12
0x18002802c  pop     rdi
0x18002802d  pop     rsi
0x18002802e  pop     rbp
0x18002802f  retn
```
