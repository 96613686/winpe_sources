# SmbCeGetConfigurationInformation

- ea: `0x14008fb70`
- end: `0x14008ff14`
- name: `SmbCeGetConfigurationInformation`
- size: `932`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14007fd3c`
- `0x14008f7e0`

## callees

- `0x140020540`
- `0x140020930`
- `0x1400240f0`
- `0x140028fec`
- `0x14002a900`
- `0x140039fa8`
- `0x140059dc0`
- `0x14008fb70`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14008fd69`
- `ntoskrnl!ZwQueryValueKey` at `0x14008fe51`
- `ntoskrnl!ZwQueryValueKey` at `0x14008fd69`
- `ntoskrnl!ZwQueryValueKey` at `0x14008fe51`
- `ntoskrnl!ZwOpenKey` at `0x14008fd1b`
- `ntoskrnl!ZwOpenKey` at `0x14008fd1b`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14008fc61`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14008fc9f`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14008fc61`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14008fc9f`
- `ntoskrnl!VerSetConditionMask` at `0x14008fc49`
- `ntoskrnl!VerSetConditionMask` at `0x14008fc87`
- `ntoskrnl!VerSetConditionMask` at `0x14008fc49`
- `ntoskrnl!VerSetConditionMask` at `0x14008fc87`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008fcd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008fd3b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008fcd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008fd3b`
- `ntoskrnl!ExAllocatePool2` at `0x14008fe06`
- `ntoskrnl!ExAllocatePool2` at `0x14008fe06`
- `ntoskrnl!ZwClose` at `0x14008fd88`
- `ntoskrnl!ZwClose` at `0x14008fdaa`
- `ntoskrnl!ZwClose` at `0x14008fe1f`
- `ntoskrnl!ZwClose` at `0x14008fed9`
- `ntoskrnl!ZwClose` at `0x14008fd88`
- `ntoskrnl!ZwClose` at `0x14008fdaa`
- `ntoskrnl!ZwClose` at `0x14008fe1f`
- `ntoskrnl!ZwClose` at `0x14008fed9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fde0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fec8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fde0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fec8`

## string_xrefs

- `0x14008fccc`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Linkage`

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
      if ( stru_140070F60.Buffer )
      {
        ExFreePoolWithTag(stru_140070F60.Buffer - 6, 0x6D536643u);
        stru_140070F60.Buffer = 0;
        *(_DWORD *)&stru_140070F60.Length = 0;
      }
      Pool2 = (char *)ExAllocatePool2(258, Length, 1834182211);
      v7 = Pool2;
      if ( Pool2 )
      {
        v8 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Pool2, Length, &ResultLength);
        if ( v8 >= 0 && (v9 = *((_DWORD *)v7 + 2)) != 0 && *((_DWORD *)v7 + 1) == 7 )
        {
          stru_140070F60.Length = *((_DWORD *)v7 + 2);
          stru_140070F60.MaximumLength = v9;
          stru_140070F60.Buffer = (wchar_t *)(v7 + 12);
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
0x14008fb70  mov     [rsp-8+arg_8], rbx
0x14008fb75  mov     [rsp-8+arg_10], rsi
0x14008fb7a  push    rbp
0x14008fb7b  lea     rbp, [rsp-0C0h]
0x14008fb83  sub     rsp, 1C0h
0x14008fb8a  mov     rax, cs:__security_cookie
0x14008fb91  xor     rax, rsp
0x14008fb94  mov     [rbp+0C0h+var_10], rax
0x14008fb9b  xorps   xmm0, xmm0
0x14008fb9e  lea     rcx, [rsp+1C0h+var_188]
0x14008fba3  xor     esi, esi
0x14008fba5  xor     eax, eax
0x14008fba7  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.ObjectName], xmm0
0x14008fbac  mov     [rsp+1C0h+KeyHandle], rsi
0x14008fbb1  movups  xmmword ptr [rsp+1C0h+ObjectAttributes+1Ch], xmm0
0x14008fbb6  mov     [rsp+1C0h+var_184], esi
0x14008fbba  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x14008fbbf  mov     [rsp+1C0h+var_188], esi
0x14008fbc3  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.Length], xmm0
0x14008fbc8  movups  [rbp+0C0h+KeyValueInformation], xmm0
0x14008fbcc  call    ReadLanmanWorkStationPolicies
0x14008fbd1  call    ReadMiniRdrParameters
0x14008fbd6  xorps   xmm0, xmm0
0x14008fbd9  mov     dword ptr [rbp+0C0h+VersionInfo.wSuiteMask], 10h
0x14008fbe3  xor     eax, eax
0x14008fbe5  mov     [rbp+0C0h+VersionInfo.dwOSVersionInfoSize], 9Ch
0x14008fbec  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0E8h], xmm0
0x14008fbf3  mov     r8b, 6; Condition
0x14008fbf6  mov     qword ptr [rbp+0C0h+VersionInfo.szCSDVersion+80h], rax
0x14008fbfa  mov     edx, 40h ; '@'; TypeMask
0x14008fbff  xor     ecx, ecx; ConditionMask
0x14008fc01  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0F4h], xmm0
0x14008fc08  mov     ebx, 10h
0x14008fc0d  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+88h], xmm0
0x14008fc11  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+98h], xmm0
0x14008fc15  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0A8h], xmm0
0x14008fc19  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0B8h], xmm0
0x14008fc1d  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0C8h], xmm0
0x14008fc21  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+0D8h], xmm0
0x14008fc25  movups  xmmword ptr [rbp+0C0h+VersionInfo.dwMajorVersion], xmm0
0x14008fc29  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion], xmm0
0x14008fc2d  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+10h], xmm0
0x14008fc31  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+20h], xmm0
0x14008fc35  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+30h], xmm0
0x14008fc39  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+40h], xmm0
0x14008fc3d  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+50h], xmm0
0x14008fc41  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+60h], xmm0
0x14008fc45  movups  xmmword ptr [rbp+0C0h+VersionInfo.szCSDVersion+70h], xmm0
0x14008fc49  call    cs:__imp_VerSetConditionMask
0x14008fc50  nop     dword ptr [rax+rax+00h]
0x14008fc55  mov     edx, 40h ; '@'; TypeMask
0x14008fc5a  lea     rcx, [rbp+0C0h+VersionInfo]; VersionInfo
0x14008fc5e  mov     r8, rax; ConditionMask
0x14008fc61  call    cs:__imp_RtlVerifyVersionInfo
0x14008fc68  nop     dword ptr [rax+rax+00h]
0x14008fc6d  test    eax, eax
0x14008fc6f  js      short loc_14008FCB9
0x14008fc71  mov     eax, 100h
0x14008fc76  mov     r8b, 6; Condition
0x14008fc79  mov     edx, 40h ; '@'; TypeMask
0x14008fc7e  mov     [rbp+0C0h+VersionInfo.wSuiteMask], ax
0x14008fc85  xor     ecx, ecx; ConditionMask
0x14008fc87  call    cs:__imp_VerSetConditionMask
0x14008fc8e  nop     dword ptr [rax+rax+00h]
0x14008fc93  mov     edx, 40h ; '@'; TypeMask
0x14008fc98  lea     rcx, [rbp+0C0h+VersionInfo]; VersionInfo
0x14008fc9c  mov     r8, rax; ConditionMask
0x14008fc9f  call    cs:__imp_RtlVerifyVersionInfo
0x14008fca6  nop     dword ptr [rax+rax+00h]
0x14008fcab  test    eax, eax
0x14008fcad  jns     short loc_14008FCB9
0x14008fcaf  mov     cs:MRxSmbConnectionIdLevel, 2
0x14008fcb9  mov     ecx, [rsp+1C0h+var_188]
0x14008fcbd  call    ReadLanmanWorkStationParameters
0x14008fcc2  call    ReadMultiChannelContraintParameters
0x14008fcc7  call    ReadServerParameters
0x14008fccc  lea     rdx, aRegistryMachin_12; "\\Registry\\Machine\\System\\CurrentCon"...
0x14008fcd3  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x14008fcd8  call    cs:__imp_RtlInitUnicodeString
0x14008fcdf  nop     dword ptr [rax+rax+00h]
0x14008fce4  lea     rax, [rsp+1C0h+DestinationString]
0x14008fce9  mov     [rsp+1C0h+ObjectAttributes.Length], 30h ; '0'
0x14008fcf1  xorps   xmm0, xmm0
0x14008fcf4  mov     [rsp+1C0h+ObjectAttributes.ObjectName], rax
0x14008fcf9  lea     r8, [rsp+1C0h+ObjectAttributes]; ObjectAttributes
0x14008fcfe  mov     [rsp+1C0h+ObjectAttributes.RootDirectory], rsi
0x14008fd03  mov     edx, 20019h; DesiredAccess
0x14008fd08  mov     [rsp+1C0h+ObjectAttributes.Attributes], 240h
0x14008fd10  lea     rcx, [rsp+1C0h+KeyHandle]; KeyHandle
0x14008fd15  movdqu  xmmword ptr [rsp+1C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008fd1b  call    cs:__imp_ZwOpenKey
0x14008fd22  nop     dword ptr [rax+rax+00h]
0x14008fd27  test    eax, eax
0x14008fd29  js      loc_14008FEEF
0x14008fd2f  lea     rdx, aBind; "Bind"
0x14008fd36  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x14008fd3b  call    cs:__imp_RtlInitUnicodeString
0x14008fd42  nop     dword ptr [rax+rax+00h]
0x14008fd47  mov     rcx, [rsp+1C0h+KeyHandle]; KeyHandle
0x14008fd4c  lea     rax, [rsp+1C0h+var_184]
0x14008fd51  mov     [rsp+1C0h+ResultLength], rax; ResultLength
0x14008fd56  lea     r9, [rbp+0C0h+KeyValueInformation]; KeyValueInformation
0x14008fd5a  mov     r8d, 2; KeyValueInformationClass
0x14008fd60  mov     [rsp+1C0h+Length], ebx; Length
0x14008fd64  lea     rdx, [rsp+1C0h+DestinationString]; ValueName
0x14008fd69  call    cs:__imp_ZwQueryValueKey
0x14008fd70  nop     dword ptr [rax+rax+00h]
0x14008fd75  cmp     eax, 80000005h
0x14008fd7a  mov     ebx, esi
0x14008fd7c  cmovnz  ebx, eax
0x14008fd7f  test    ebx, ebx
0x14008fd81  jns     short loc_14008FD9B
0x14008fd83  mov     rcx, [rsp+1C0h+KeyHandle]; Handle
0x14008fd88  call    cs:__imp_ZwClose
0x14008fd8f  nop     dword ptr [rax+rax+00h]
0x14008fd94  mov     eax, ebx
0x14008fd96  jmp     loc_14008FEEF
0x14008fd9b  mov     eax, dword ptr [rbp+0C0h+KeyValueInformation+8]
0x14008fd9e  cmp     eax, 0FFFFh
0x14008fda3  jbe     short loc_14008FDC0
0x14008fda5  mov     rcx, [rsp+1C0h+KeyHandle]; Handle
0x14008fdaa  call    cs:__imp_ZwClose
0x14008fdb1  nop     dword ptr [rax+rax+00h]
0x14008fdb6  mov     eax, 0C000009Ah
0x14008fdbb  jmp     loc_14008FEEF
0x14008fdc0  mov     rcx, cs:stru_140070F60.Buffer
0x14008fdc7  mov     [rsp+1C0h+arg_0], rdi
0x14008fdcf  lea     edi, [rax+10h]
0x14008fdd2  test    rcx, rcx
0x14008fdd5  jz      short loc_14008FDF9
0x14008fdd7  add     rcx, 0FFFFFFFFFFFFFFF4h; P
0x14008fddb  mov     edx, 6D536643h; Tag
0x14008fde0  call    cs:__imp_ExFreePoolWithTag
0x14008fde7  nop     dword ptr [rax+rax+00h]
0x14008fdec  mov     cs:stru_140070F60.Buffer, rsi
0x14008fdf3  mov     dword ptr cs:stru_140070F60.Length, esi
0x14008fdf9  mov     edx, edi
0x14008fdfb  mov     ecx, 102h
0x14008fe00  mov     r8d, 6D536643h
0x14008fe06  call    cs:__imp_ExAllocatePool2
0x14008fe0d  nop     dword ptr [rax+rax+00h]
0x14008fe12  mov     rcx, [rsp+1C0h+KeyHandle]; KeyHandle
0x14008fe17  mov     rbx, rax
0x14008fe1a  test    rax, rax
0x14008fe1d  jnz     short loc_14008FE35
0x14008fe1f  call    cs:__imp_ZwClose
0x14008fe26  nop     dword ptr [rax+rax+00h]
0x14008fe2b  mov     eax, 0C000009Ah
0x14008fe30  jmp     loc_14008FEE7
0x14008fe35  lea     rax, [rsp+1C0h+var_184]
0x14008fe3a  mov     r9, rbx; KeyValueInformation
0x14008fe3d  mov     [rsp+1C0h+ResultLength], rax; ResultLength
0x14008fe42  lea     rdx, [rsp+1C0h+DestinationString]; ValueName
0x14008fe47  mov     r8d, 2; KeyValueInformationClass
0x14008fe4d  mov     [rsp+1C0h+Length], edi; Length
0x14008fe51  call    cs:__imp_ZwQueryValueKey
0x14008fe58  nop     dword ptr [rax+rax+00h]
0x14008fe5d  mov     edi, eax
0x14008fe5f  test    eax, eax
0x14008fe61  js      short loc_14008FE8B
0x14008fe63  mov     ecx, [rbx+8]
0x14008fe66  test    ecx, ecx
0x14008fe68  jz      short loc_14008FE8B
0x14008fe6a  cmp     dword ptr [rbx+4], 7
0x14008fe6e  jnz     short loc_14008FE8B
0x14008fe70  mov     cs:stru_140070F60.Length, cx
0x14008fe77  mov     cs:stru_140070F60.MaximumLength, cx
0x14008fe7e  lea     rcx, [rbx+0Ch]
0x14008fe82  mov     cs:stru_140070F60.Buffer, rcx
0x14008fe89  jmp     short loc_14008FED4
0x14008fe8b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008fe92  lea     rax, WPP_GLOBAL_Control
0x14008fe99  cmp     rcx, rax
0x14008fe9c  jz      short loc_14008FEC0
0x14008fe9e  mov     eax, [rcx+2Ch]
0x14008fea1  test    al, 2
0x14008fea3  jz      short loc_14008FEC0
0x14008fea5  cmp     byte ptr [rcx+29h], 2
0x14008fea9  jb      short loc_14008FEC0
0x14008feab  mov     rcx, [rcx+18h]
0x14008feaf  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14008feb6  mov     edx, 2Ch ; ','
0x14008febb  call    WPP_SF_
0x14008fec0  mov     edx, 6D536643h; Tag
0x14008fec5  mov     rcx, rbx; P
0x14008fec8  call    cs:__imp_ExFreePoolWithTag
0x14008fecf  nop     dword ptr [rax+rax+00h]
0x14008fed4  mov     rcx, [rsp+1C0h+KeyHandle]; Handle
0x14008fed9  call    cs:__imp_ZwClose
0x14008fee0  nop     dword ptr [rax+rax+00h]
0x14008fee5  mov     eax, edi
0x14008fee7  mov     rdi, [rsp+1C0h+arg_0]
0x14008feef  mov     rcx, [rbp+0C0h+var_10]
0x14008fef6  xor     rcx, rsp; StackCookie
0x14008fef9  call    __security_check_cookie
0x14008fefe  lea     r11, [rsp+1C0h+var_s0]
0x14008ff06  mov     rbx, [r11+18h]
0x14008ff0a  mov     rsi, [r11+20h]
0x14008ff0e  mov     rsp, r11
0x14008ff11  pop     rbp
0x14008ff12  retn
```
