# MigrateOOBELanguageToInstallationLanguage

- ea: `0x14068d9dc`
- end: `0x14068dbbc`
- name: `MigrateOOBELanguageToInstallationLanguage`
- size: `480`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1407f2060`
- `0x140ac70e0`

## callees

- `0x140403380`
- `0x14068d9dc`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd6c0`
- `0x1406ddfe0`
- `0x1406f7380`

## string_xrefs

- `0x14068da49`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\NLS\Language`
- `0x14068db1d`: `PreviousInstallLanguage`
- `0x14068daa9`: `InstallLanguage`

## pseudocode

```c
__int64 MigrateOOBELanguageToInstallationLanguage()
{
  NTSTATUS v0; // ebx
  unsigned __int16 v1; // r8
  __int64 i; // rdx
  __int16 v3; // ax
  unsigned __int16 v4; // cx
  HANDLE KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING ValueName; // [rsp+80h] [rbp-80h] BYREF
  __int64 v11; // [rsp+90h] [rbp-70h] BYREF
  __int16 v12; // [rsp+98h] [rbp-68h]
  _BYTE KeyValueInformation[8]; // [rsp+A0h] [rbp-60h] BYREF
  ULONG DataSize; // [rsp+A8h] [rbp-58h]
  _BYTE Data[516]; // [rsp+ACh] [rbp-54h] BYREF

  KeyHandle = 0;
  v11 = 0;
  memset(&ObjectAttributes, 0, 44);
  v12 = 0;
  DestinationString = 0;
  memset_0(KeyValueInformation, 0, 0x210u);
  ResultLength = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\NLS\\Language");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
  if ( v0 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"InstallLanguage");
    v1 = PsInstallUILanguageId;
    for ( i = 3; i != -1; --i )
    {
      v3 = 55;
      v4 = v1 & 0xF;
      if ( v4 <= 9u )
        v3 = 48;
      v1 >>= 4;
      *((_WORD *)&v11 + i) = v4 + v3;
    }
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x210u,
           &ResultLength) >= 0 )
    {
      RtlInitUnicodeString(&ValueName, L"PreviousInstallLanguage");
      ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, Data, DataSize);
    }
    v0 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 1u, &v11, 0xAu);
    if ( v0 >= 0 )
      v0 = 0;
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14068d9dc  mov     [rsp-8+arg_0], rbx
0x14068d9e1  mov     [rsp-8+arg_8], rsi
0x14068d9e6  push    rbp
0x14068d9e7  lea     rbp, [rsp-1C0h]
0x14068d9ef  sub     rsp, 2C0h
0x14068d9f6  mov     rax, cs:__security_cookie
0x14068d9fd  xor     rax, rsp
0x14068da00  mov     [rbp+1C0h+var_10], rax
0x14068da07  xorps   xmm0, xmm0
0x14068da0a  lea     rcx, [rbp+1C0h+KeyValueInformation]; void *
0x14068da0e  xor     eax, eax
0x14068da10  xor     edx, edx; Val
0x14068da12  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.ObjectName], xmm0
0x14068da17  mov     r8d, 210h; Size
0x14068da1d  mov     [rsp+2C0h+KeyHandle], rax
0x14068da22  movups  xmmword ptr [rsp+2C0h+ObjectAttributes+1Ch], xmm0
0x14068da27  mov     [rbp+1C0h+var_230], rax
0x14068da2b  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.Length], xmm0
0x14068da30  mov     [rbp+1C0h+var_228], ax
0x14068da34  movups  xmmword ptr [rsp+2C0h+DestinationString.Length], xmm0
0x14068da39  call    memset_0
0x14068da3e  xorps   xmm0, xmm0
0x14068da41  mov     [rsp+2C0h+var_288], 0
0x14068da49  lea     rdx, aRegistryMachin_90; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x14068da50  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x14068da55  movups  xmmword ptr [rbp+1C0h+ValueName.Length], xmm0
0x14068da59  call    RtlInitUnicodeString
0x14068da5e  lea     rax, [rsp+2C0h+DestinationString]
0x14068da63  mov     [rsp+2C0h+ObjectAttributes.RootDirectory], 0
0x14068da6c  xorps   xmm0, xmm0
0x14068da6f  mov     [rsp+2C0h+ObjectAttributes.ObjectName], rax
0x14068da74  mov     esi, 30h ; '0'
0x14068da79  mov     [rsp+2C0h+ObjectAttributes.Attributes], 240h
0x14068da81  lea     r8, [rsp+2C0h+ObjectAttributes]; ObjectAttributes
0x14068da86  mov     [rsp+2C0h+ObjectAttributes.Length], esi
0x14068da8a  mov     edx, 2001Fh; DesiredAccess
0x14068da8f  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x14068da94  movdqu  xmmword ptr [rsp+2C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14068da9a  call    ZwOpenKey
0x14068da9f  mov     ebx, eax
0x14068daa1  test    eax, eax
0x14068daa3  js      loc_14068DB86
0x14068daa9  lea     rdx, aInstalllanguag; "InstallLanguage"
0x14068dab0  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x14068dab5  call    RtlInitUnicodeString
0x14068daba  movzx   r8d, cs:PsInstallUILanguageId
0x14068dac2  lea     edx, [rsi-2Dh]
0x14068dac5  movzx   ecx, r8w
0x14068dac9  mov     eax, 37h ; '7'
0x14068dace  and     cx, 0Fh
0x14068dad2  cmp     cx, 9
0x14068dad6  cmovbe  ax, si
0x14068dada  shr     r8w, 4
0x14068dadf  add     ax, cx
0x14068dae2  mov     word ptr [rbp+rdx*2+1C0h+var_230], ax
0x14068dae7  dec     rdx
0x14068daea  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14068daee  jnz     short loc_14068DAC5
0x14068daf0  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x14068daf5  lea     rax, [rsp+2C0h+var_288]
0x14068dafa  lea     r8d, [rdx+3]; KeyValueInformationClass
0x14068dafe  mov     [rsp+2C0h+ResultLength], rax; ResultLength
0x14068db03  lea     r9, [rbp+1C0h+KeyValueInformation]; KeyValueInformation
0x14068db07  mov     [rsp+2C0h+Length], 210h; Length
0x14068db0f  lea     rdx, [rsp+2C0h+DestinationString]; ValueName
0x14068db14  call    ZwQueryValueKey
0x14068db19  test    eax, eax
0x14068db1b  js      short loc_14068DB54
0x14068db1d  lea     rdx, aPreviousinstal; "PreviousInstallLanguage"
0x14068db24  lea     rcx, [rbp+1C0h+ValueName]; DestinationString
0x14068db28  call    RtlInitUnicodeString
0x14068db2d  mov     eax, [rbp+1C0h+DataSize]
0x14068db30  lea     rdx, [rbp+1C0h+ValueName]; ValueName
0x14068db34  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x14068db39  mov     r9d, 1; Type
0x14068db3f  mov     dword ptr [rsp+2C0h+ResultLength], eax; DataSize
0x14068db43  xor     r8d, r8d; TitleIndex
0x14068db46  lea     rax, [rbp+1C0h+Data]
0x14068db4a  mov     qword ptr [rsp+2C0h+Length], rax; Data
0x14068db4f  call    ZwSetValueKey
0x14068db54  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x14068db59  lea     rax, [rbp+1C0h+var_230]
0x14068db5d  mov     dword ptr [rsp+2C0h+ResultLength], 0Ah; DataSize
0x14068db65  lea     rdx, [rsp+2C0h+DestinationString]; ValueName
0x14068db6a  mov     r9d, 1; Type
0x14068db70  mov     qword ptr [rsp+2C0h+Length], rax; Data
0x14068db75  xor     r8d, r8d; TitleIndex
0x14068db78  call    ZwSetValueKey
0x14068db7d  mov     ebx, eax
0x14068db7f  xor     eax, eax
0x14068db81  test    ebx, ebx
0x14068db83  cmovns  ebx, eax
0x14068db86  mov     rcx, [rsp+2C0h+KeyHandle]; Handle
0x14068db8b  test    rcx, rcx
0x14068db8e  jz      short loc_14068DB95
0x14068db90  call    ZwClose
0x14068db95  mov     eax, ebx
0x14068db97  mov     rcx, [rbp+1C0h+var_10]
0x14068db9e  xor     rcx, rsp; StackCookie
0x14068dba1  call    __security_check_cookie
0x14068dba6  lea     r11, [rsp+2C0h+var_s0]
0x14068dbae  mov     rbx, [r11+10h]
0x14068dbb2  mov     rsi, [r11+18h]
0x14068dbb6  mov     rsp, r11
0x14068dbb9  pop     rbp
0x14068dbba  retn
```
