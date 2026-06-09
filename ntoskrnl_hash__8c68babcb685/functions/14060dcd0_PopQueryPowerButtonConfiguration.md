# PopQueryPowerButtonConfiguration

- ea: `0x14060dcd0`
- end: `0x14060dfe5`
- name: `PopQueryPowerButtonConfiguration`
- size: `789`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14079d954`

## callees

- `0x1402a2f90`
- `0x140403380`
- `0x14060dcd0`
- `0x1406dc8c0`
- `0x1406dd6c0`

## string_xrefs

- `0x14060de50`: `%s (Bugcheck) completed with Status: %08x, ManualBugcheckConfig: %08x, OneSettingBugcheckConfig: %08x\n`
- `0x14060de45`: `PopQueryPowerButtonConfiguration`
- `0x14060df37`: `PopQueryPowerButtonConfiguration`
- `0x14060df98`: `PopQueryPowerButtonConfiguration`
- `0x14060dfa3`: `%s completed with settings: PopPowerButtonBugcheckConfig: %08x, PopPowerButtonLiveDumpConfig: %08x\n`
- `0x14060df42`: `%s (LiveDump) completed with Status: %08x, ManualLiveDumpConfig %08x, OneSettingLiveDumpConfig: %08x\n`

## pseudocode

```c
__int64 __fastcall PopQueryPowerButtonConfiguration(HANDLE KeyHandle, _BYTE *a2)
{
  NTSTATUS v4; // edx
  int v5; // ecx
  int v6; // eax
  NTSTATUS v7; // ebx
  int v8; // ecx
  ULONG ResultLength; // [rsp+40h] [rbp-29h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-21h] BYREF
  UNICODE_STRING ValueName; // [rsp+58h] [rbp-11h] BYREF
  UNICODE_STRING v13; // [rsp+68h] [rbp-1h] BYREF
  UNICODE_STRING v14; // [rsp+78h] [rbp+Fh] BYREF
  __int128 KeyValueInformation; // [rsp+88h] [rbp+1Fh] BYREF
  int v16; // [rsp+98h] [rbp+2Fh]

  v16 = 0;
  ResultLength = 0;
  DestinationString = 0;
  ValueName = 0;
  v13 = 0;
  v14 = 0;
  KeyValueInformation = 0;
  RtlInitUnicodeString(&DestinationString, L"PowerButtonBugcheck");
  RtlInitUnicodeString(&ValueName, L"OneSettingPowerButtonBugcheck");
  RtlInitUnicodeString(&v13, L"PowerButtonLiveDump");
  RtlInitUnicodeString(&v14, L"OneSettingPowerButtonLiveDump");
  v4 = ZwQueryValueKey(
         KeyHandle,
         &DestinationString,
         KeyValuePartialInformation,
         &KeyValueInformation,
         0x14u,
         &ResultLength);
  if ( v4 < 0 || *(_QWORD *)((char *)&KeyValueInformation + 4) != 0x400000004LL )
  {
    LODWORD(qword_140EF63B0) = 0;
    v4 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength);
    if ( v4 < 0 || *(_QWORD *)((char *)&KeyValueInformation + 4) != 0x400000004LL )
    {
      HIDWORD(qword_140EF63B0) = 0;
      v4 = -1073741823;
      PopPowerButtonBugcheckConfig = 0;
      goto LABEL_14;
    }
    v6 = HIDWORD(KeyValueInformation);
    *a2 = 1;
    if ( v6 )
    {
      HIDWORD(qword_140EF63B0) = 2;
      goto LABEL_10;
    }
    HIDWORD(qword_140EF63B0) = 1;
LABEL_12:
    PopPowerButtonBugcheckConfig = 1;
    goto LABEL_14;
  }
  v5 = HIDWORD(KeyValueInformation);
  *a2 = 1;
  if ( !v5 )
  {
    LODWORD(qword_140EF63B0) = 1;
    goto LABEL_12;
  }
  LODWORD(qword_140EF63B0) = 2;
LABEL_10:
  PopPowerButtonBugcheckConfig = 2;
LABEL_14:
  DbgPrintEx(
    0x92u,
    2u,
    "%s (Bugcheck) completed with Status: %08x, ManualBugcheckConfig: %08x, OneSettingBugcheckConfig: %08x\n",
    "PopQueryPowerButtonConfiguration",
    v4,
    qword_140EF63B0,
    HIDWORD(qword_140EF63B0));
  v7 = ZwQueryValueKey(KeyHandle, &v13, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength);
  if ( v7 >= 0 && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
  {
    v8 = WORD6(KeyValueInformation) & 0x1FF;
    HIBYTE(word_140EF63B8) = 1;
    dword_140EF63BC = v8;
  }
  else
  {
    HIBYTE(word_140EF63B8) = 0;
    dword_140EF63BC = 0;
    v7 = ZwQueryValueKey(KeyHandle, &v14, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength);
    if ( v7 < 0 || *(_QWORD *)((char *)&KeyValueInformation + 4) != 0x400000004LL )
    {
      v8 = 0;
      v7 = -1073741823;
      byte_140EF63C0 = 0;
      LODWORD(qword_140EF63C4) = 0;
      goto LABEL_22;
    }
    v8 = WORD6(KeyValueInformation) & 0x1FF;
    byte_140EF63C0 = 1;
    LODWORD(qword_140EF63C4) = v8;
  }
  *a2 = 1;
LABEL_22:
  PopPowerButtonLiveDumpConfig = v8;
  DbgPrintEx(
    0x92u,
    2u,
    "%s (LiveDump) completed with Status: %08x, ManualLiveDumpConfig %08x, OneSettingLiveDumpConfig: %08x\n",
    "PopQueryPowerButtonConfiguration",
    v7,
    dword_140EF63BC,
    qword_140EF63C4);
  if ( (dword_140EF63BC & 1) != 0 && !(_DWORD)qword_140EF63B0 && PopPowerButtonBugcheckConfig == 2 )
    PopPowerButtonBugcheckConfig = 1;
  DbgPrintEx(
    0x92u,
    2u,
    "%s completed with settings: PopPowerButtonBugcheckConfig: %08x, PopPowerButtonLiveDumpConfig: %08x\n",
    "PopQueryPowerButtonConfiguration",
    PopPowerButtonBugcheckConfig,
    PopPowerButtonLiveDumpConfig);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14060dcd0  mov     [rsp-8+arg_10], rbx
0x14060dcd5  mov     [rsp-8+arg_18], rsi
0x14060dcda  push    rbp
0x14060dcdb  push    rdi
0x14060dcdc  push    r12
0x14060dcde  lea     rbp, [rsp-47h]
0x14060dce3  sub     rsp, 0B0h
0x14060dcea  mov     rax, cs:__security_cookie
0x14060dcf1  xor     rax, rsp
0x14060dcf4  mov     [rbp+57h+var_20], rax
0x14060dcf8  xorps   xmm0, xmm0
0x14060dcfb  xorps   xmm1, xmm1
0x14060dcfe  xor     eax, eax
0x14060dd00  mov     rdi, rdx
0x14060dd03  mov     rsi, rcx
0x14060dd06  mov     [rbp+57h+var_28], eax
0x14060dd09  lea     rdx, PopPowerButtonBugcheckRegName; "PowerButtonBugcheck"
0x14060dd10  mov     [rbp+57h+var_80], eax
0x14060dd13  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14060dd17  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14060dd1b  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x14060dd1f  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x14060dd23  movups  xmmword ptr [rbp+57h+var_48.Length], xmm1
0x14060dd27  movups  [rbp+57h+KeyValueInformation], xmm0
0x14060dd2b  call    RtlInitUnicodeString
0x14060dd30  lea     rdx, PopOneSettingPowerButtonBugcheckRegName; "OneSettingPowerButtonBugcheck"
0x14060dd37  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14060dd3b  call    RtlInitUnicodeString
0x14060dd40  lea     rdx, PopPowerButtonLiveDumpRegName; "PowerButtonLiveDump"
0x14060dd47  lea     rcx, [rbp+57h+var_58]; DestinationString
0x14060dd4b  call    RtlInitUnicodeString
0x14060dd50  lea     rdx, PopOneSettingPowerButtonLiveDumpRegName; "OneSettingPowerButtonLiveDump"
0x14060dd57  lea     rcx, [rbp+57h+var_48]; DestinationString
0x14060dd5b  call    RtlInitUnicodeString
0x14060dd60  mov     ebx, 14h
0x14060dd65  lea     rax, [rbp+57h+var_80]
0x14060dd69  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14060dd6e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14060dd72  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14060dd76  mov     [rsp+0C0h+Length], ebx; Length
0x14060dd7a  mov     rcx, rsi; KeyHandle
0x14060dd7d  lea     r12d, [rbx-12h]
0x14060dd81  mov     r8d, r12d; KeyValueInformationClass
0x14060dd84  call    ZwQueryValueKey
0x14060dd89  mov     edx, eax
0x14060dd8b  test    eax, eax
0x14060dd8d  js      short loc_14060DDBA
0x14060dd8f  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x14060dd93  jnz     short loc_14060DDBA
0x14060dd95  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x14060dd99  jnz     short loc_14060DDBA
0x14060dd9b  mov     ecx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x14060dd9e  mov     byte ptr [rdi], 1
0x14060dda1  test    ecx, ecx
0x14060dda3  jz      short loc_14060DDAE
0x14060dda5  mov     dword ptr cs:qword_140EF63B0, r12d
0x14060ddac  jmp     short loc_14060DE07
0x14060ddae  mov     dword ptr cs:qword_140EF63B0, 1
0x14060ddb8  jmp     short loc_14060DE1A
0x14060ddba  lea     rax, [rbp+57h+var_80]
0x14060ddbe  mov     dword ptr cs:qword_140EF63B0, 0
0x14060ddc8  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14060ddcd  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14060ddd1  mov     r8d, r12d; KeyValueInformationClass
0x14060ddd4  mov     [rsp+0C0h+Length], ebx; Length
0x14060ddd8  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14060dddc  mov     rcx, rsi; KeyHandle
0x14060dddf  call    ZwQueryValueKey
0x14060dde4  mov     edx, eax
0x14060dde6  test    eax, eax
0x14060dde8  js      short loc_14060DE26
0x14060ddea  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x14060ddee  jnz     short loc_14060DE26
0x14060ddf0  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x14060ddf4  jnz     short loc_14060DE26
0x14060ddf6  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x14060ddf9  mov     byte ptr [rdi], 1
0x14060ddfc  test    eax, eax
0x14060ddfe  jz      short loc_14060DE10
0x14060de00  mov     dword ptr cs:qword_140EF63B0+4, r12d
0x14060de07  mov     cs:PopPowerButtonBugcheckConfig, r12d
0x14060de0e  jmp     short loc_14060DE3F
0x14060de10  mov     dword ptr cs:qword_140EF63B0+4, 1
0x14060de1a  mov     cs:PopPowerButtonBugcheckConfig, 1
0x14060de24  jmp     short loc_14060DE3F
0x14060de26  mov     dword ptr cs:qword_140EF63B0+4, 0
0x14060de30  mov     edx, 0C0000001h
0x14060de35  mov     cs:PopPowerButtonBugcheckConfig, 0
0x14060de3f  mov     eax, dword ptr cs:qword_140EF63B0+4
0x14060de45  lea     r9, aPopquerypowerb; "PopQueryPowerButtonConfiguration"
0x14060de4c  mov     [rsp+0C0h+var_90], eax
0x14060de50  lea     r8, aSBugcheckCompl; "%s (Bugcheck) completed with Status: %0"...
0x14060de57  mov     eax, dword ptr cs:qword_140EF63B0
0x14060de5d  mov     ecx, 92h; ComponentId
0x14060de62  mov     dword ptr [rsp+0C0h+ResultLength], eax
0x14060de66  mov     [rsp+0C0h+Length], edx
0x14060de6a  mov     edx, r12d; Level
0x14060de6d  call    DbgPrintEx
0x14060de72  lea     rax, [rbp+57h+var_80]
0x14060de76  mov     r8d, r12d; KeyValueInformationClass
0x14060de79  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14060de7e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14060de82  lea     rdx, [rbp+57h+var_58]; ValueName
0x14060de86  mov     [rsp+0C0h+Length], ebx; Length
0x14060de8a  mov     rcx, rsi; KeyHandle
0x14060de8d  call    ZwQueryValueKey
0x14060de92  mov     ebx, eax
0x14060de94  test    eax, eax
0x14060de96  js      short loc_14060DEBC
0x14060de98  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x14060de9c  jnz     short loc_14060DEBC
0x14060de9e  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x14060dea2  jnz     short loc_14060DEBC
0x14060dea4  mov     ecx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x14060dea7  and     ecx, 1FFh
0x14060dead  mov     byte ptr cs:word_140EF63B8+1, 1
0x14060deb4  mov     cs:dword_140EF63BC, ecx
0x14060deba  jmp     short loc_14060DF19
0x14060debc  lea     rax, [rbp+57h+var_80]
0x14060dec0  mov     byte ptr cs:word_140EF63B8+1, 0
0x14060dec7  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14060decc  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14060ded0  mov     r8d, r12d; KeyValueInformationClass
0x14060ded3  mov     [rsp+0C0h+Length], 14h; Length
0x14060dedb  lea     rdx, [rbp+57h+var_48]; ValueName
0x14060dedf  mov     cs:dword_140EF63BC, 0
0x14060dee9  mov     rcx, rsi; KeyHandle
0x14060deec  call    ZwQueryValueKey
0x14060def1  mov     ebx, eax
0x14060def3  test    eax, eax
0x14060def5  js      short loc_14060DF1E
0x14060def7  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x14060defb  jnz     short loc_14060DF1E
0x14060defd  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x14060df01  jnz     short loc_14060DF1E
0x14060df03  mov     ecx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x14060df06  and     ecx, 1FFh
0x14060df0c  mov     cs:byte_140EF63C0, 1
0x14060df13  mov     dword ptr cs:qword_140EF63C4, ecx
0x14060df19  mov     byte ptr [rdi], 1
0x14060df1c  jmp     short loc_14060DF31
0x14060df1e  xor     ecx, ecx
0x14060df20  mov     ebx, 0C0000001h
0x14060df25  mov     cs:byte_140EF63C0, cl
0x14060df2b  mov     dword ptr cs:qword_140EF63C4, ecx
0x14060df31  mov     eax, dword ptr cs:qword_140EF63C4
0x14060df37  lea     r9, aPopquerypowerb; "PopQueryPowerButtonConfiguration"
0x14060df3e  mov     [rsp+0C0h+var_90], eax
0x14060df42  lea     r8, aSLivedumpCompl; "%s (LiveDump) completed with Status: %0"...
0x14060df49  mov     eax, cs:dword_140EF63BC
0x14060df4f  mov     edi, 92h
0x14060df54  mov     cs:PopPowerButtonLiveDumpConfig, ecx
0x14060df5a  mov     edx, r12d; Level
0x14060df5d  mov     dword ptr [rsp+0C0h+ResultLength], eax
0x14060df61  mov     ecx, edi; ComponentId
0x14060df63  mov     [rsp+0C0h+Length], ebx
0x14060df67  call    DbgPrintEx
0x14060df6c  mov     eax, cs:dword_140EF63BC
0x14060df72  test    al, 1
0x14060df74  jz      short loc_14060DF92
0x14060df76  cmp     dword ptr cs:qword_140EF63B0, 0
0x14060df7d  jnz     short loc_14060DF92
0x14060df7f  cmp     cs:PopPowerButtonBugcheckConfig, r12d
0x14060df86  jnz     short loc_14060DF92
0x14060df88  mov     cs:PopPowerButtonBugcheckConfig, 1
0x14060df92  mov     eax, cs:PopPowerButtonLiveDumpConfig
0x14060df98  lea     r9, aPopquerypowerb; "PopQueryPowerButtonConfiguration"
0x14060df9f  mov     dword ptr [rsp+0C0h+ResultLength], eax
0x14060dfa3  lea     r8, aSCompletedWith; "%s completed with settings: PopPowerBut"...
0x14060dfaa  mov     eax, cs:PopPowerButtonBugcheckConfig
0x14060dfb0  mov     edx, r12d; Level
0x14060dfb3  mov     ecx, edi; ComponentId
0x14060dfb5  mov     [rsp+0C0h+Length], eax
0x14060dfb9  call    DbgPrintEx
0x14060dfbe  mov     eax, ebx
0x14060dfc0  mov     rcx, [rbp+57h+var_20]
0x14060dfc4  xor     rcx, rsp; StackCookie
0x14060dfc7  call    __security_check_cookie
0x14060dfcc  lea     r11, [rsp+0C0h+var_10]
0x14060dfd4  mov     rbx, [r11+30h]
0x14060dfd8  mov     rsi, [r11+38h]
0x14060dfdc  mov     rsp, r11
0x14060dfdf  pop     r12
0x14060dfe1  pop     rdi
0x14060dfe2  pop     rbp
0x14060dfe3  retn
```
