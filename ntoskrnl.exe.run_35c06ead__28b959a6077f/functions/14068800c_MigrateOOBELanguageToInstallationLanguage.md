# MigrateOOBELanguageToInstallationLanguage

- ea: `0x14068800c`
- end: `0x1406881ec`
- name: `MigrateOOBELanguageToInstallationLanguage`
- size: `480`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1407ef200`
- `0x140ac1c60`

## callees

- `0x1403f2d50`
- `0x14068800c`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406dab70`
- `0x1406db490`
- `0x1406f4880`

## string_xrefs

- `0x1406880d9`: `InstallLanguage`
- `0x14068814d`: `PreviousInstallLanguage`
- `0x140688079`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\NLS\Language`

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
0x14068800c  mov     [rsp-8+arg_0], rbx
0x140688011  mov     [rsp-8+arg_8], rsi
0x140688016  push    rbp
0x140688017  lea     rbp, [rsp-1C0h]
0x14068801f  sub     rsp, 2C0h
0x140688026  mov     rax, cs:__security_cookie
0x14068802d  xor     rax, rsp
0x140688030  mov     [rbp+1C0h+var_10], rax
0x140688037  xorps   xmm0, xmm0
0x14068803a  lea     rcx, [rbp+1C0h+KeyValueInformation]; void *
0x14068803e  xor     eax, eax
0x140688040  xor     edx, edx; Val
0x140688042  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.ObjectName], xmm0
0x140688047  mov     r8d, 210h; Size
0x14068804d  mov     [rsp+2C0h+KeyHandle], rax
0x140688052  movups  xmmword ptr [rsp+2C0h+ObjectAttributes+1Ch], xmm0
0x140688057  mov     [rbp+1C0h+var_230], rax
0x14068805b  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.Length], xmm0
0x140688060  mov     [rbp+1C0h+var_228], ax
0x140688064  movups  xmmword ptr [rsp+2C0h+DestinationString.Length], xmm0
0x140688069  call    memset_0
0x14068806e  xorps   xmm0, xmm0
0x140688071  mov     [rsp+2C0h+var_288], 0
0x140688079  lea     rdx, aRegistryMachin_90; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x140688080  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x140688085  movups  xmmword ptr [rbp+1C0h+ValueName.Length], xmm0
0x140688089  call    RtlInitUnicodeString
0x14068808e  lea     rax, [rsp+2C0h+DestinationString]
0x140688093  mov     [rsp+2C0h+ObjectAttributes.RootDirectory], 0
0x14068809c  xorps   xmm0, xmm0
0x14068809f  mov     [rsp+2C0h+ObjectAttributes.ObjectName], rax
0x1406880a4  mov     esi, 30h ; '0'
0x1406880a9  mov     [rsp+2C0h+ObjectAttributes.Attributes], 240h
0x1406880b1  lea     r8, [rsp+2C0h+ObjectAttributes]; ObjectAttributes
0x1406880b6  mov     [rsp+2C0h+ObjectAttributes.Length], esi
0x1406880ba  mov     edx, 2001Fh; DesiredAccess
0x1406880bf  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x1406880c4  movdqu  xmmword ptr [rsp+2C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1406880ca  call    ZwOpenKey
0x1406880cf  mov     ebx, eax
0x1406880d1  test    eax, eax
0x1406880d3  js      loc_1406881B6
0x1406880d9  lea     rdx, aInstalllanguag; "InstallLanguage"
0x1406880e0  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x1406880e5  call    RtlInitUnicodeString
0x1406880ea  movzx   r8d, cs:PsInstallUILanguageId
0x1406880f2  lea     edx, [rsi-2Dh]
0x1406880f5  movzx   ecx, r8w
0x1406880f9  mov     eax, 37h ; '7'
0x1406880fe  and     cx, 0Fh
0x140688102  cmp     cx, 9
0x140688106  cmovbe  ax, si
0x14068810a  shr     r8w, 4
0x14068810f  add     ax, cx
0x140688112  mov     word ptr [rbp+rdx*2+1C0h+var_230], ax
0x140688117  dec     rdx
0x14068811a  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14068811e  jnz     short loc_1406880F5
0x140688120  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x140688125  lea     rax, [rsp+2C0h+var_288]
0x14068812a  lea     r8d, [rdx+3]; KeyValueInformationClass
0x14068812e  mov     [rsp+2C0h+ResultLength], rax; ResultLength
0x140688133  lea     r9, [rbp+1C0h+KeyValueInformation]; KeyValueInformation
0x140688137  mov     [rsp+2C0h+Length], 210h; Length
0x14068813f  lea     rdx, [rsp+2C0h+DestinationString]; ValueName
0x140688144  call    ZwQueryValueKey
0x140688149  test    eax, eax
0x14068814b  js      short loc_140688184
0x14068814d  lea     rdx, aPreviousinstal; "PreviousInstallLanguage"
0x140688154  lea     rcx, [rbp+1C0h+ValueName]; DestinationString
0x140688158  call    RtlInitUnicodeString
0x14068815d  mov     eax, [rbp+1C0h+DataSize]
0x140688160  lea     rdx, [rbp+1C0h+ValueName]; ValueName
0x140688164  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x140688169  mov     r9d, 1; Type
0x14068816f  mov     dword ptr [rsp+2C0h+ResultLength], eax; DataSize
0x140688173  xor     r8d, r8d; TitleIndex
0x140688176  lea     rax, [rbp+1C0h+Data]
0x14068817a  mov     qword ptr [rsp+2C0h+Length], rax; Data
0x14068817f  call    ZwSetValueKey
0x140688184  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x140688189  lea     rax, [rbp+1C0h+var_230]
0x14068818d  mov     dword ptr [rsp+2C0h+ResultLength], 0Ah; DataSize
0x140688195  lea     rdx, [rsp+2C0h+DestinationString]; ValueName
0x14068819a  mov     r9d, 1; Type
0x1406881a0  mov     qword ptr [rsp+2C0h+Length], rax; Data
0x1406881a5  xor     r8d, r8d; TitleIndex
0x1406881a8  call    ZwSetValueKey
0x1406881ad  mov     ebx, eax
0x1406881af  xor     eax, eax
0x1406881b1  test    ebx, ebx
0x1406881b3  cmovns  ebx, eax
0x1406881b6  mov     rcx, [rsp+2C0h+KeyHandle]; Handle
0x1406881bb  test    rcx, rcx
0x1406881be  jz      short loc_1406881C5
0x1406881c0  call    ZwClose
0x1406881c5  mov     eax, ebx
0x1406881c7  mov     rcx, [rbp+1C0h+var_10]
0x1406881ce  xor     rcx, rsp; StackCookie
0x1406881d1  call    __security_check_cookie
0x1406881d6  lea     r11, [rsp+2C0h+var_s0]
0x1406881de  mov     rbx, [r11+10h]
0x1406881e2  mov     rsi, [r11+18h]
0x1406881e6  mov     rsp, r11
0x1406881e9  pop     rbp
0x1406881ea  retn
```
