# SmbCeGetConfigurationInformation

- ea: `0x14008fbc0`
- end: `0x14008ff64`
- name: `SmbCeGetConfigurationInformation`
- size: `932`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14007fd3c`
- `0x14008f830`

## callees

- `0x140020540`
- `0x140020930`
- `0x1400240f0`
- `0x140028fec`
- `0x14002a900`
- `0x140039fa8`
- `0x140059dc0`
- `0x14008fbc0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14008fdb9`
- `ntoskrnl!ZwQueryValueKey` at `0x14008fea1`
- `ntoskrnl!ZwQueryValueKey` at `0x14008fdb9`
- `ntoskrnl!ZwQueryValueKey` at `0x14008fea1`
- `ntoskrnl!ZwOpenKey` at `0x14008fd6b`
- `ntoskrnl!ZwOpenKey` at `0x14008fd6b`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14008fcb1`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14008fcef`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14008fcb1`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14008fcef`
- `ntoskrnl!VerSetConditionMask` at `0x14008fc99`
- `ntoskrnl!VerSetConditionMask` at `0x14008fcd7`
- `ntoskrnl!VerSetConditionMask` at `0x14008fc99`
- `ntoskrnl!VerSetConditionMask` at `0x14008fcd7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008fd28`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008fd8b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008fd28`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008fd8b`
- `ntoskrnl!ExAllocatePool2` at `0x14008fe56`
- `ntoskrnl!ExAllocatePool2` at `0x14008fe56`
- `ntoskrnl!ZwClose` at `0x14008fdd8`
- `ntoskrnl!ZwClose` at `0x14008fdfa`
- `ntoskrnl!ZwClose` at `0x14008fe6f`
- `ntoskrnl!ZwClose` at `0x14008ff29`
- `ntoskrnl!ZwClose` at `0x14008fdd8`
- `ntoskrnl!ZwClose` at `0x14008fdfa`
- `ntoskrnl!ZwClose` at `0x14008fe6f`
- `ntoskrnl!ZwClose` at `0x14008ff29`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fe30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ff18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fe30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ff18`

## string_xrefs

- `0x14008fd1c`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Linkage`

## pseudocode

```c
NTSTATUS SmbCeGetConfigurationInformation()
{
  ULONGLONG v0; // rax
  ULONGLONG v1; // rax
  NTSTATUS result; // eax
  NTSTATUS v3; // eax
  int v4; // ebx
  ULONG Length; // edi
  char *Pool2; // rax
  char *v7; // rbx
  NTSTATUS v8; // edi
  int v9; // ecx
  void *KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ResultLength; // [rsp+3Ch] [rbp-C4h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp-80h] BYREF
  _OSVERSIONINFOEXW VersionInfo; // [rsp+90h] [rbp-70h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  v11 = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  ReadLanmanWorkStationPolicies(&v11);
  ReadMiniRdrParameters();
  *(_DWORD *)&VersionInfo.wSuiteMask = 16;
  VersionInfo.dwOSVersionInfoSize = 156;
  memset(&VersionInfo.dwMajorVersion, 0, 276);
  v0 = VerSetConditionMask(0, 0x40u, 6u);
  if ( RtlVerifyVersionInfo(&VersionInfo, 0x40u, v0) >= 0 )
  {
    VersionInfo.wSuiteMask = 256;
    v1 = VerSetConditionMask(0, 0x40u, 6u);
    if ( RtlVerifyVersionInfo(&VersionInfo, 0x40u, v1) < 0 )
      MRxSmbConnectionIdLevel = 2;
  }
  ReadLanmanWorkStationParameters(v11);
  ReadMultiChannelContraintParameters();
  ReadServerParameters();
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Linkage");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Bind");
    v3 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x10u,
           &ResultLength);
    v4 = 0;
    if ( v3 != -2147483643 )
      v4 = v3;
    if ( v4 >= 0 )
    {
      if ( DWORD2(KeyValueInformation) > 0xFFFF )
        goto LABEL_10;
      Length = DWORD2(KeyValueInformation) + 16;
      if ( stru_140070F80.Buffer )
      {
        ExFreePoolWithTag(stru_140070F80.Buffer - 6, 0x6D536643u);
        stru_140070F80.Buffer = 0;
        *(_DWORD *)&stru_140070F80.Length = 0;
      }
      Pool2 = (char *)ExAllocatePool2(258, Length, 1834182211);
      v7 = Pool2;
      if ( Pool2 )
      {
        v8 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Pool2, Length, &ResultLength);
        if ( v8 >= 0 && (v9 = *((_DWORD *)v7 + 2)) != 0 && *((_DWORD *)v7 + 1) == 7 )
        {
          stru_140070F80.Length = *((_DWORD *)v7 + 2);
          stru_140070F80.MaximumLength = v9;
          stru_140070F80.Buffer = (wchar_t *)(v7 + 12);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids);
          }
          ExFreePoolWithTag(v7, 0x6D536643u);
        }
        ZwClose(KeyHandle);
        return v8;
      }
      else
      {
LABEL_10:
        ZwClose(KeyHandle);
        return -1073741670;
      }
    }
    else
    {
      ZwClose(KeyHandle);
      return v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14008fbc0  mov     [rsp-8+arg_8], rbx
0x14008fbc5  mov     [rsp-8+arg_10], rsi
0x14008fbca  push    rbp
0x14008fbcb  lea     rbp, [rsp-0C0h]
0x14008fbd3  sub     rsp, 1C0h
0x14008fbda  mov     rax, cs:__security_cookie
0x14008fbe1  xor     rax, rsp
0x14008fbe4  mov     [rbp+0C0h+var_10], rax
0x14008fbeb  xorps   xmm0, xmm0
0x14008fbee  lea     rcx, [rsp+1C0h+var_188]
0x14008fbf3  xor     esi, esi
0x14008fbf5  xor     eax, eax
0x14008fbf7  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.ObjectName], xmm0
0x14008fbfc  mov     [rsp+1C0h+KeyHandle], rsi
0x14008fc01  movups  xmmword ptr [rsp+1C0h+ObjectAttributes+1Ch], xmm0
0x14008fc06  mov     [rsp+1C0h+var_184], esi
0x14008fc0a  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x14008fc0f  mov     [rsp+1C0h+var_188], esi
0x14008fc13  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.Length], xmm0
0x14008fc18  movups  [rbp+0C0h+KeyValueInformation], xmm0
0x14008fc1c  call    ReadLanmanWorkStationPolicies
0x14008fc21  call    ReadMiniRdrParameters
0x14008fc26  xorps   xmm0, xmm0
0x14008fc29  mov     dword ptr [rbp+0C0h+VersionInfo.wSuiteMask], 10h
0x14008fc33  xor     eax, eax
0x14008fc35  mov     [rbp+0C0h+VersionInfo.dwOSVersionInfoSize], 9Ch
0x14008fc3c  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0E8h], xmm0
0x14008fc43  mov     r8b, 6; Condition
0x14008fc46  mov     qword ptr [rbp+0C0h+VersionInfo.szCSDVersion+80h], rax
0x14008fc4a  mov     edx, 40h ; '@'; TypeMask
0x14008fc4f  xor     ecx, ecx; ConditionMask
0x14008fc51  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0F4h], xmm0
0x14008fc58  mov     ebx, 10h
0x14008fc5d  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+88h], xmm0
0x14008fc61  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+98h], xmm0
0x14008fc65  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0A8h], xmm0
0x14008fc69  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0B8h], xmm0
0x14008fc6d  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0C8h], xmm0
0x14008fc71  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0D8h], xmm0
0x14008fc75  movups  xmmword ptr [rbp+0C0h+VersionInfo.dwMajorVersion], xmm0
0x14008fc79  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion], xmm0
0x14008fc7d  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+10h], xmm0
0x14008fc81  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+20h], xmm0
0x14008fc85  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+30h], xmm0
0x14008fc89  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+40h], xmm0
0x14008fc8d  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+50h], xmm0
0x14008fc91  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+60h], xmm0
0x14008fc95  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+70h], xmm0
0x14008fc99  call    cs:__imp_VerSetConditionMask
0x14008fca0  nop     dword ptr [rax+rax+00h]
0x14008fca5  mov     edx, 40h ; '@'; TypeMask
0x14008fcaa  lea     rcx, [rbp+0C0h+VersionInfo]; VersionInfo
0x14008fcae  mov     r8, rax; ConditionMask
0x14008fcb1  call    cs:__imp_RtlVerifyVersionInfo
0x14008fcb8  nop     dword ptr [rax+rax+00h]
0x14008fcbd  test    eax, eax
0x14008fcbf  js      short loc_14008FD09
0x14008fcc1  mov     eax, 100h
0x14008fcc6  mov     r8b, 6; Condition
0x14008fcc9  mov     edx, 40h ; '@'; TypeMask
0x14008fcce  mov     [rbp+0C0h+VersionInfo.wSuiteMask], ax
0x14008fcd5  xor     ecx, ecx; ConditionMask
0x14008fcd7  call    cs:__imp_VerSetConditionMask
0x14008fcde  nop     dword ptr [rax+rax+00h]
0x14008fce3  mov     edx, 40h ; '@'; TypeMask
0x14008fce8  lea     rcx, [rbp+0C0h+VersionInfo]; VersionInfo
0x14008fcec  mov     r8, rax; ConditionMask
0x14008fcef  call    cs:__imp_RtlVerifyVersionInfo
0x14008fcf6  nop     dword ptr [rax+rax+00h]
0x14008fcfb  test    eax, eax
0x14008fcfd  jns     short loc_14008FD09
0x14008fcff  mov     cs:MRxSmbConnectionIdLevel, 2
0x14008fd09  mov     ecx, [rsp+1C0h+var_188]
0x14008fd0d  call    ReadLanmanWorkStationParameters
0x14008fd12  call    ReadMultiChannelContraintParameters
0x14008fd17  call    ReadServerParameters
0x14008fd1c  lea     rdx, aRegistryMachin_12; "\\Registry\\Machine\\System\\CurrentCon"...
0x14008fd23  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x14008fd28  call    cs:__imp_RtlInitUnicodeString
0x14008fd2f  nop     dword ptr [rax+rax+00h]
0x14008fd34  lea     rax, [rsp+1C0h+DestinationString]
0x14008fd39  mov     [rsp+1C0h+ObjectAttributes.Length], 30h ; '0'
0x14008fd41  xorps   xmm0, xmm0
0x14008fd44  mov     [rsp+1C0h+ObjectAttributes.ObjectName], rax
0x14008fd49  lea     r8, [rsp+1C0h+ObjectAttributes]; ObjectAttributes
0x14008fd4e  mov     [rsp+1C0h+ObjectAttributes.RootDirectory], rsi
0x14008fd53  mov     edx, 20019h; DesiredAccess
0x14008fd58  mov     [rsp+1C0h+ObjectAttributes.Attributes], 240h
0x14008fd60  lea     rcx, [rsp+1C0h+KeyHandle]; KeyHandle
0x14008fd65  movdqu  xmmword ptr [rsp+1C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008fd6b  call    cs:__imp_ZwOpenKey
0x14008fd72  nop     dword ptr [rax+rax+00h]
0x14008fd77  test    eax, eax
0x14008fd79  js      loc_14008FF3F
0x14008fd7f  lea     rdx, aBind; "Bind"
0x14008fd86  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x14008fd8b  call    cs:__imp_RtlInitUnicodeString
0x14008fd92  nop     dword ptr [rax+rax+00h]
0x14008fd97  mov     rcx, [rsp+1C0h+KeyHandle]; KeyHandle
0x14008fd9c  lea     rax, [rsp+1C0h+var_184]
0x14008fda1  mov     [rsp+1C0h+ResultLength], rax; ResultLength
0x14008fda6  lea     r9, [rbp+0C0h+KeyValueInformation]; KeyValueInformation
0x14008fdaa  mov     r8d, 2; KeyValueInformationClass
0x14008fdb0  mov     [rsp+1C0h+Length], ebx; Length
0x14008fdb4  lea     rdx, [rsp+1C0h+DestinationString]; ValueName
0x14008fdb9  call    cs:__imp_ZwQueryValueKey
0x14008fdc0  nop     dword ptr [rax+rax+00h]
0x14008fdc5  cmp     eax, 80000005h
0x14008fdca  mov     ebx, esi
0x14008fdcc  cmovnz  ebx, eax
0x14008fdcf  test    ebx, ebx
0x14008fdd1  jns     short loc_14008FDEB
0x14008fdd3  mov     rcx, [rsp+1C0h+KeyHandle]; Handle
0x14008fdd8  call    cs:__imp_ZwClose
0x14008fddf  nop     dword ptr [rax+rax+00h]
0x14008fde4  mov     eax, ebx
0x14008fde6  jmp     loc_14008FF3F
0x14008fdeb  mov     eax, dword ptr [rbp+0C0h+KeyValueInformation+8]
0x14008fdee  cmp     eax, 0FFFFh
0x14008fdf3  jbe     short loc_14008FE10
0x14008fdf5  mov     rcx, [rsp+1C0h+KeyHandle]; Handle
0x14008fdfa  call    cs:__imp_ZwClose
0x14008fe01  nop     dword ptr [rax+rax+00h]
0x14008fe06  mov     eax, 0C000009Ah
0x14008fe0b  jmp     loc_14008FF3F
0x14008fe10  mov     rcx, cs:stru_140070F80.Buffer
0x14008fe17  mov     [rsp+1C0h+arg_0], rdi
0x14008fe1f  lea     edi, [rax+10h]
0x14008fe22  test    rcx, rcx
0x14008fe25  jz      short loc_14008FE49
0x14008fe27  add     rcx, 0FFFFFFFFFFFFFFF4h; P
0x14008fe2b  mov     edx, 6D536643h; Tag
0x14008fe30  call    cs:__imp_ExFreePoolWithTag
0x14008fe37  nop     dword ptr [rax+rax+00h]
0x14008fe3c  mov     cs:stru_140070F80.Buffer, rsi
0x14008fe43  mov     dword ptr cs:stru_140070F80.Length, esi
0x14008fe49  mov     edx, edi
0x14008fe4b  mov     ecx, 102h
0x14008fe50  mov     r8d, 6D536643h
0x14008fe56  call    cs:__imp_ExAllocatePool2
0x14008fe5d  nop     dword ptr [rax+rax+00h]
0x14008fe62  mov     rcx, [rsp+1C0h+KeyHandle]; KeyHandle
0x14008fe67  mov     rbx, rax
0x14008fe6a  test    rax, rax
0x14008fe6d  jnz     short loc_14008FE85
0x14008fe6f  call    cs:__imp_ZwClose
0x14008fe76  nop     dword ptr [rax+rax+00h]
0x14008fe7b  mov     eax, 0C000009Ah
0x14008fe80  jmp     loc_14008FF37
0x14008fe85  lea     rax, [rsp+1C0h+var_184]
0x14008fe8a  mov     r9, rbx; KeyValueInformation
0x14008fe8d  mov     [rsp+1C0h+ResultLength], rax; ResultLength
0x14008fe92  lea     rdx, [rsp+1C0h+DestinationString]; ValueName
0x14008fe97  mov     r8d, 2; KeyValueInformationClass
0x14008fe9d  mov     [rsp+1C0h+Length], edi; Length
0x14008fea1  call    cs:__imp_ZwQueryValueKey
0x14008fea8  nop     dword ptr [rax+rax+00h]
0x14008fead  mov     edi, eax
0x14008feaf  test    eax, eax
0x14008feb1  js      short loc_14008FEDB
0x14008feb3  mov     ecx, [rbx+8]
0x14008feb6  test    ecx, ecx
0x14008feb8  jz      short loc_14008FEDB
0x14008feba  cmp     dword ptr [rbx+4], 7
0x14008febe  jnz     short loc_14008FEDB
0x14008fec0  mov     cs:stru_140070F80.Length, cx
0x14008fec7  mov     cs:stru_140070F80.MaximumLength, cx
0x14008fece  lea     rcx, [rbx+0Ch]
0x14008fed2  mov     cs:stru_140070F80.Buffer, rcx
0x14008fed9  jmp     short loc_14008FF24
0x14008fedb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008fee2  lea     rax, WPP_GLOBAL_Control
0x14008fee9  cmp     rcx, rax
0x14008feec  jz      short loc_14008FF10
0x14008feee  mov     eax, [rcx+2Ch]
0x14008fef1  test    al, 2
0x14008fef3  jz      short loc_14008FF10
0x14008fef5  cmp     byte ptr [rcx+29h], 2
0x14008fef9  jb      short loc_14008FF10
0x14008fefb  mov     rcx, [rcx+18h]
0x14008feff  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14008ff06  mov     edx, 2Ch ; ','
0x14008ff0b  call    WPP_SF_
0x14008ff10  mov     edx, 6D536643h; Tag
0x14008ff15  mov     rcx, rbx; P
0x14008ff18  call    cs:__imp_ExFreePoolWithTag
0x14008ff1f  nop     dword ptr [rax+rax+00h]
0x14008ff24  mov     rcx, [rsp+1C0h+KeyHandle]; Handle
0x14008ff29  call    cs:__imp_ZwClose
0x14008ff30  nop     dword ptr [rax+rax+00h]
0x14008ff35  mov     eax, edi
0x14008ff37  mov     rdi, [rsp+1C0h+arg_0]
0x14008ff3f  mov     rcx, [rbp+0C0h+var_10]
0x14008ff46  xor     rcx, rsp; StackCookie
0x14008ff49  call    __security_check_cookie
0x14008ff4e  lea     r11, [rsp+1C0h+var_s0]
0x14008ff56  mov     rbx, [r11+18h]
0x14008ff5a  mov     rsi, [r11+20h]
0x14008ff5e  mov     rsp, r11
0x14008ff61  pop     rbp
0x14008ff62  retn
```
