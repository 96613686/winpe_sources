# AslLogGetDefaultFlags

- ea: `0x180004bf0`
- end: `0x1800050d5`
- name: `AslLogGetDefaultFlags`
- size: `1253`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004790`

## callees

- `0x180004bf0`
- `0x1800068a0`
- `0x180007738`
- `0x18000c030`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180004c61`
- `ntdll!RtlInitUnicodeString` at `0x180004dbe`
- `ntdll!RtlInitUnicodeString` at `0x180004c61`
- `ntdll!RtlInitUnicodeString` at `0x180004dbe`
- `ntdll!ZwClose` at `0x180004f74`
- `ntdll!ZwClose` at `0x1800050ca`
- `ntdll!ZwClose` at `0x180004f74`
- `ntdll!ZwClose` at `0x1800050ca`
- `ntdll!RtlAppendUnicodeToString` at `0x180004cc4`
- `ntdll!RtlAppendUnicodeToString` at `0x180004e1f`
- `ntdll!RtlAppendUnicodeToString` at `0x180004cc4`
- `ntdll!RtlAppendUnicodeToString` at `0x180004e1f`
- `ntdll!ZwOpenKey` at `0x180004cf9`
- `ntdll!ZwOpenKey` at `0x180004e54`
- `ntdll!ZwOpenKey` at `0x180004cf9`
- `ntdll!ZwOpenKey` at `0x180004e54`
- `ntdll!RtlInitUnicodeStringEx` at `0x180004d50`
- `ntdll!RtlInitUnicodeStringEx` at `0x180004d50`
- `ntdll!ZwQueryValueKey` at `0x180004f2f`
- `ntdll!ZwQueryValueKey` at `0x180004f2f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180004cb0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180004e0b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180004cb0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180004e0b`
- `ntdll!RtlAllocateHeap` at `0x180004c8f`
- `ntdll!RtlAllocateHeap` at `0x180004df0`
- `ntdll!RtlAllocateHeap` at `0x180004c8f`
- `ntdll!RtlAllocateHeap` at `0x180004df0`
- `ntdll!RtlFreeHeap` at `0x180004d34`
- `ntdll!RtlFreeHeap` at `0x180004ea6`
- `ntdll!RtlFreeHeap` at `0x180004d34`
- `ntdll!RtlFreeHeap` at `0x180004ea6`

## string_xrefs

- `0x180004cb6`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x180004fdc`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x180004e11`: `\OSDATA\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x180005067`: `\OSDATA\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x180004c31`: `\Registry\Machine`
- `0x180004da0`: `\Registry\Machine`
- `0x180004fcb`: `AslRegistryBuildMachinePath`
- `0x180005056`: `AslRegistryBuildMachinePath`
- `0x180004d71`: `AslRegistryGetUInt32`
- `0x180004f5b`: `AslRegistryGetUInt32_UStr`
- `0x180005026`: `AslRegistryGetUInt32_UStr`
- `0x180004feb`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x180005079`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x180004fa0`: `AslRegistryGetKey`
- `0x18000509d`: `AslRegistryGetKey`
- `0x180004f8f`: `NtOpenKey failed %x for %ws`
- `0x18000508c`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 AslLogGetDefaultFlags()
{
  unsigned int Buffer_high; // ebx
  void *v1; // rsi
  int v2; // r14d
  NTSTATUS v3; // eax
  int v4; // edi
  NTSTATUS inited; // eax
  int v6; // edi
  NTSTATUS v7; // eax
  __int64 result; // rax
  NTSTATUS v9; // eax
  ULONG Length[2]; // [rsp+28h] [rbp-89h]
  ULONG Lengtha[2]; // [rsp+28h] [rbp-89h]
  ULONG Lengthb[2]; // [rsp+28h] [rbp-89h]
  unsigned int v13; // [rsp+38h] [rbp-79h] BYREF
  ULONG ResultLength[2]; // [rsp+40h] [rbp-71h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-69h] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-59h] BYREF
  UNICODE_STRING Source; // [rsp+60h] [rbp-51h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES v19; // [rsp+A0h] [rbp-11h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp+1Fh] BYREF
  int v21; // [rsp+E0h] [rbp+2Fh]

  Buffer_high = 0;
  v13 = 0;
  if ( byte_180014818 )
  {
    result = (unsigned int)dword_180014810;
    byte_180014818 = 1;
  }
  else
  {
    v1 = 0;
    KeyHandle = 0;
    memset(&ObjectAttributes, 0, 44);
    Destination = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine");
    Destination.Length = 0;
    Destination.MaximumLength = DestinationString.Length + 122;
    Destination.Buffer = (PWSTR)RtlAllocateHeap(
                                  NtCurrentPeb()->ProcessHeap,
                                  8u,
                                  (unsigned __int16)(DestinationString.Length + 122));
    v2 = -1073741801;
    if ( Destination.Buffer )
    {
      RtlAppendUnicodeStringToString(&Destination, &DestinationString);
      RtlAppendUnicodeToString(&Destination, L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &Destination;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v3 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
      v4 = v3;
      if ( v3 < 0 )
      {
        if ( v3 != -1073741772 )
          AslLogCallPrintf(
            1,
            "AslRegistryGetKey",
            1761,
            "NtOpenKey failed %x for %ws",
            v3,
            L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
      }
      else
      {
        v1 = KeyHandle;
        v4 = 0;
        KeyHandle = 0;
      }
    }
    else
    {
      AslLogCallPrintf(
        1,
        "AslRegistryBuildMachinePath",
        1582,
        "Failed to allocate %d bytes for user key buffer",
        Destination.MaximumLength);
      v4 = -1073741801;
      Lengtha[0] = -1073741801;
      AslLogCallPrintf(
        1,
        "AslRegistryGetKey",
        1718,
        "AslRegistryBuildMachinePath failed %x for %ws",
        *(_QWORD *)Lengtha,
        L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
    }
    if ( Destination.Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
    if ( v4 < 0 )
      goto LABEL_11;
    Source = 0;
    inited = RtlInitUnicodeStringEx(&Source, L"LogFlags");
    v6 = inited;
    if ( inited >= 0 )
    {
      ResultLength[0] = 0;
      v21 = 0;
      DestinationString = 0;
      v9 = ZwQueryValueKey(v1, &Source, KeyValuePartialInformation, &DestinationString, 0x14u, ResultLength);
      v6 = v9;
      if ( v9 >= 0 )
      {
        if ( *(_DWORD *)(&DestinationString.MaximumLength + 1) == 4 && LODWORD(DestinationString.Buffer) == 4 )
        {
          Buffer_high = HIDWORD(DestinationString.Buffer);
          v6 = 0;
          v13 = HIDWORD(DestinationString.Buffer);
        }
        else
        {
          AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1098, "Invalid value type");
          v6 = -1073741788;
        }
      }
      else if ( v9 != -1073741772 )
      {
        AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1091, "Failed to query key value [%x]", v9);
      }
    }
    else
    {
      AslLogCallPrintf(1, "AslRegistryGetUInt32", 1148, "RtlInitUnicodeStringEx failed [%x]", inited);
    }
    if ( v6 < 0 )
    {
LABEL_11:
      if ( v1 )
        ZwClose(v1);
      *(_QWORD *)ResultLength = 0;
      v1 = 0;
      memset(&v19, 0, 44);
      DestinationString = 0;
      Source = 0;
      RtlInitUnicodeString(&Source, L"\\Registry\\Machine");
      DestinationString.Length = 0;
      DestinationString.MaximumLength = Source.Length + 136;
      DestinationString.Buffer = (PWSTR)RtlAllocateHeap(
                                          NtCurrentPeb()->ProcessHeap,
                                          8u,
                                          (unsigned __int16)(Source.Length + 136));
      if ( DestinationString.Buffer )
      {
        RtlAppendUnicodeStringToString(&DestinationString, &Source);
        RtlAppendUnicodeToString(
          &DestinationString,
          L"\\OSDATA\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
        v19.Length = 48;
        v19.ObjectName = &DestinationString;
        v19.RootDirectory = 0;
        v19.Attributes = 64;
        *(_OWORD *)&v19.SecurityDescriptor = 0;
        v7 = ZwOpenKey((PHANDLE)ResultLength, 1u, &v19);
        v2 = v7;
        if ( v7 < 0 )
        {
          if ( v7 != -1073741772 )
          {
            Length[0] = v7;
            AslLogCallPrintf(
              1,
              "AslRegistryGetKey",
              1761,
              "NtOpenKey failed %x for %ws",
              *(_QWORD *)Length,
              L"\\OSDATA\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
          }
        }
        else
        {
          v1 = *(void **)ResultLength;
          v2 = 0;
          *(_QWORD *)ResultLength = 0;
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          "AslRegistryBuildMachinePath",
          1582,
          "Failed to allocate %d bytes for user key buffer",
          DestinationString.MaximumLength);
        Lengthb[0] = -1073741801;
        AslLogCallPrintf(
          1,
          "AslRegistryGetKey",
          1718,
          "AslRegistryBuildMachinePath failed %x for %ws",
          *(_QWORD *)Lengthb,
          L"\\OSDATA\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
      }
      if ( DestinationString.Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
      if ( v2 >= 0 )
      {
        AslRegistryGetUInt32(&v13, v1);
        Buffer_high = v13;
      }
    }
    dword_180014810 = Buffer_high;
    byte_180014818 = 1;
    if ( v1 )
      ZwClose(v1);
    return Buffer_high;
  }
  return result;
}

```

## disassembly

```asm
0x180004bf0  mov     r11, rsp
0x180004bf3  push    rbp
0x180004bf4  push    rbx
0x180004bf5  push    r12
0x180004bf7  lea     rbp, [r11-5Fh]
0x180004bfb  sub     rsp, 0F0h
0x180004c02  mov     rax, cs:__security_cookie
0x180004c09  xor     rax, rsp
0x180004c0c  mov     [rbp+57h+var_20], rax
0x180004c10  xor     r12d, r12d
0x180004c13  cmp     cs:byte_180014818, r12b
0x180004c1a  mov     ebx, r12d
0x180004c1d  mov     [rbp+57h+var_D0], ebx
0x180004c20  jnz     loc_180004E6E
0x180004c26  xorps   xmm0, xmm0
0x180004c29  mov     [r11+8], rsi
0x180004c2d  mov     [r11+10h], rdi
0x180004c31  lea     rdx, SourceString; "\\Registry\\Machine"
0x180004c38  mov     [r11+18h], r14
0x180004c3c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180004c40  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180004c44  xor     eax, eax
0x180004c46  mov     [r11+20h], r15
0x180004c4a  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180004c4e  mov     esi, r12d
0x180004c51  mov     [rbp+57h+KeyHandle], r12
0x180004c55  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180004c59  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x180004c5d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180004c61  call    cs:__imp_RtlInitUnicodeString
0x180004c67  movzx   eax, [rbp+57h+DestinationString.Length]
0x180004c6b  mov     edx, 8; Flags
0x180004c70  mov     [rbp+57h+Destination.Length], r12w
0x180004c75  add     ax, 7Ah ; 'z'
0x180004c79  movzx   r8d, ax; Size
0x180004c7d  mov     [rbp+57h+Destination.MaximumLength], r8w
0x180004c82  mov     rcx, gs:60h
0x180004c8b  mov     rcx, [rcx+30h]; HeapHandle
0x180004c8f  call    cs:__imp_RtlAllocateHeap
0x180004c95  mov     [rbp+57h+Destination.Buffer], rax
0x180004c99  mov     r14d, 0C0000017h
0x180004c9f  test    rax, rax
0x180004ca2  jz      loc_180004FB6
0x180004ca8  lea     rdx, [rbp+57h+DestinationString]; Source
0x180004cac  lea     rcx, [rbp+57h+Destination]; Destination
0x180004cb0  call    cs:__imp_RtlAppendUnicodeStringToString
0x180004cb6  lea     r15, aSoftwareMicros; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x180004cbd  mov     rdx, r15; Source
0x180004cc0  lea     rcx, [rbp+57h+Destination]; Destination
0x180004cc4  call    cs:__imp_RtlAppendUnicodeToString
0x180004cca  lea     rax, [rbp+57h+Destination]
0x180004cce  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180004cd5  xorps   xmm0, xmm0
0x180004cd8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180004cdc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180004ce0  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180004ce4  mov     edx, 1; DesiredAccess
0x180004ce9  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180004cf0  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180004cf4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180004cf9  call    cs:__imp_ZwOpenKey
0x180004cff  mov     edi, eax
0x180004d01  test    eax, eax
0x180004d03  js      loc_180004F7F
0x180004d09  mov     rsi, [rbp+57h+KeyHandle]
0x180004d0d  mov     edi, r12d
0x180004d10  mov     [rbp+57h+KeyHandle], r12
0x180004d14  mov     r8, [rbp+57h+Destination.Buffer]; P
0x180004d18  mov     r15, [rsp+100h+arg_18]
0x180004d20  test    r8, r8
0x180004d23  jz      short loc_180004D3A
0x180004d25  mov     rcx, gs:60h
0x180004d2e  xor     edx, edx; Flags
0x180004d30  mov     rcx, [rcx+30h]; HeapHandle
0x180004d34  call    cs:__imp_RtlFreeHeap
0x180004d3a  test    edi, edi
0x180004d3c  js      short loc_180004D8A
0x180004d3e  xorps   xmm0, xmm0
0x180004d41  lea     rdx, aLogflags; "LogFlags"
0x180004d48  lea     rcx, [rbp+57h+Source]; DestinationString
0x180004d4c  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x180004d50  call    cs:__imp_RtlInitUnicodeStringEx
0x180004d56  mov     edi, eax
0x180004d58  test    eax, eax
0x180004d5a  jns     loc_180004EFD
0x180004d60  lea     r9, aRtlinitunicode; "RtlInitUnicodeStringEx failed [%x]"
0x180004d67  mov     [rsp+100h+Length], eax
0x180004d6b  mov     r8d, 47Ch
0x180004d71  lea     rdx, aAslregistryget_2; "AslRegistryGetUInt32"
0x180004d78  mov     ecx, 1
0x180004d7d  call    AslLogCallPrintf
0x180004d82  test    edi, edi
0x180004d84  jns     loc_180004EB5
0x180004d8a  test    rsi, rsi
0x180004d8d  jnz     loc_180004F71
0x180004d93  xorps   xmm0, xmm0
0x180004d96  mov     qword ptr [rbp+57h+ResultLength], r12
0x180004d9a  movups  xmmword ptr [rbp+57h+var_68.ObjectName], xmm0
0x180004d9e  xor     eax, eax
0x180004da0  lea     rdx, SourceString; "\\Registry\\Machine"
0x180004da7  lea     rcx, [rbp+57h+Source]; DestinationString
0x180004dab  mov     rsi, r12
0x180004dae  movups  xmmword ptr [rbp+57h+var_68+1Ch], xmm0
0x180004db2  movups  xmmword ptr [rbp+57h+var_68.Length], xmm0
0x180004db6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180004dba  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x180004dbe  call    cs:__imp_RtlInitUnicodeString
0x180004dc4  movzx   eax, [rbp+57h+Source.Length]
0x180004dc8  mov     ecx, 88h
0x180004dcd  add     ax, cx
0x180004dd0  mov     [rbp+57h+DestinationString.Length], r12w
0x180004dd5  movzx   r8d, ax; Size
0x180004dd9  mov     edx, 8; Flags
0x180004dde  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x180004de3  mov     rcx, gs:60h
0x180004dec  mov     rcx, [rcx+30h]; HeapHandle
0x180004df0  call    cs:__imp_RtlAllocateHeap
0x180004df6  mov     [rbp+57h+DestinationString.Buffer], rax
0x180004dfa  test    rax, rax
0x180004dfd  jz      loc_180005041
0x180004e03  lea     rdx, [rbp+57h+Source]; Source
0x180004e07  lea     rcx, [rbp+57h+DestinationString]; Destination
0x180004e0b  call    cs:__imp_RtlAppendUnicodeStringToString
0x180004e11  lea     rdi, aOsdataSoftware; "\\OSDATA\\Software\\Microsoft\\Windows "...
0x180004e18  mov     rdx, rdi; Source
0x180004e1b  lea     rcx, [rbp+57h+DestinationString]; Destination
0x180004e1f  call    cs:__imp_RtlAppendUnicodeToString
0x180004e25  lea     rax, [rbp+57h+DestinationString]
0x180004e29  mov     [rbp+57h+var_68.Length], 30h ; '0'
0x180004e30  xorps   xmm0, xmm0
0x180004e33  mov     [rbp+57h+var_68.ObjectName], rax
0x180004e37  lea     r8, [rbp+57h+var_68]; ObjectAttributes
0x180004e3b  mov     [rbp+57h+var_68.RootDirectory], r12
0x180004e3f  mov     edx, 1; DesiredAccess
0x180004e44  mov     [rbp+57h+var_68.Attributes], 40h ; '@'
0x180004e4b  lea     rcx, [rbp+57h+ResultLength]; KeyHandle
0x180004e4f  movdqu  xmmword ptr [rbp+57h+var_68.SecurityDescriptor], xmm0
0x180004e54  call    cs:__imp_ZwOpenKey
0x180004e5a  mov     r14d, eax
0x180004e5d  test    eax, eax
0x180004e5f  js      short loc_180004E83
0x180004e61  mov     rsi, qword ptr [rbp+57h+ResultLength]
0x180004e65  mov     r14d, r12d
0x180004e68  mov     qword ptr [rbp+57h+ResultLength], r12
0x180004e6c  jmp     short loc_180004E8E
0x180004e6e  mov     eax, cs:dword_180014810
0x180004e74  mov     cs:dword_180014810, eax
0x180004e7a  mov     cs:byte_180014818, 1
0x180004e81  jmp     short loc_180004EE5
0x180004e83  cmp     eax, 0C0000034h
0x180004e88  jnz     loc_180005087
0x180004e8e  mov     r8, [rbp+57h+DestinationString.Buffer]; P
0x180004e92  test    r8, r8
0x180004e95  jz      short loc_180004EAC
0x180004e97  mov     rcx, gs:60h
0x180004ea0  xor     edx, edx; Flags
0x180004ea2  mov     rcx, [rcx+30h]; HeapHandle
0x180004ea6  call    cs:__imp_RtlFreeHeap
0x180004eac  test    r14d, r14d
0x180004eaf  jns     loc_1800050B3
0x180004eb5  mov     r14, [rsp+100h+arg_10]
0x180004ebd  mov     rdi, [rsp+100h+arg_8]
0x180004ec5  mov     cs:dword_180014810, ebx
0x180004ecb  mov     cs:byte_180014818, 1
0x180004ed2  test    rsi, rsi
0x180004ed5  jnz     loc_1800050C7
0x180004edb  mov     rsi, [rsp+100h+arg_0]
0x180004ee3  mov     eax, ebx
0x180004ee5  mov     rcx, [rbp+57h+var_20]
0x180004ee9  xor     rcx, rsp; StackCookie
0x180004eec  call    __security_check_cookie
0x180004ef1  add     rsp, 0F0h
0x180004ef8  pop     r12
0x180004efa  pop     rbx
0x180004efb  pop     rbp
0x180004efc  retn
0x180004efd  xor     eax, eax
0x180004eff  mov     [rbp+57h+ResultLength], r12d
0x180004f03  mov     [rbp+57h+var_28], eax
0x180004f06  lea     r9, [rbp+57h+DestinationString]; KeyValueInformation
0x180004f0a  lea     rax, [rbp+57h+ResultLength]
0x180004f0e  xorps   xmm0, xmm0
0x180004f11  mov     qword ptr [rsp+100h+Length+8], rax; ResultLength
0x180004f16  lea     rdx, [rbp+57h+Source]; ValueName
0x180004f1a  mov     r8d, 2; KeyValueInformationClass
0x180004f20  mov     [rsp+100h+Length], 14h; Length
0x180004f28  mov     rcx, rsi; KeyHandle
0x180004f2b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180004f2f  call    cs:__imp_ZwQueryValueKey
0x180004f35  mov     edi, eax
0x180004f37  test    eax, eax
0x180004f39  jns     loc_180004FFF
0x180004f3f  cmp     eax, 0C0000034h
0x180004f44  jz      loc_180004D82
0x180004f4a  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180004f51  mov     [rsp+100h+Length], eax
0x180004f55  mov     r8d, 443h
0x180004f5b  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x180004f62  mov     ecx, 1
0x180004f67  call    AslLogCallPrintf
0x180004f6c  jmp     loc_180004D82
0x180004f71  mov     rcx, rsi; Handle
0x180004f74  call    cs:__imp_ZwClose
0x180004f7a  jmp     loc_180004D93
0x180004f7f  cmp     eax, 0C0000034h
0x180004f84  jz      loc_180004D14
0x180004f8a  mov     qword ptr [rsp+100h+Length+8], r15
0x180004f8f  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x180004f96  mov     [rsp+100h+Length], eax
0x180004f9a  mov     r8d, 6E1h
0x180004fa0  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x180004fa7  mov     ecx, 1
0x180004fac  call    AslLogCallPrintf
0x180004fb1  jmp     loc_180004D14
0x180004fb6  movzx   eax, [rbp+57h+Destination.MaximumLength]
0x180004fba  lea     r9, aFailedToAlloca; "Failed to allocate %d bytes for user ke"...
0x180004fc1  mov     r8d, 62Eh
0x180004fc7  mov     [rsp+100h+Length], eax
0x180004fcb  lea     rdx, aAslregistrybui_0; "AslRegistryBuildMachinePath"
0x180004fd2  mov     ecx, 1
0x180004fd7  call    AslLogCallPrintf
0x180004fdc  lea     r15, aSoftwareMicros; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x180004fe3  mov     edi, r14d
0x180004fe6  mov     qword ptr [rsp+100h+Length+8], r15
0x180004feb  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x180004ff2  mov     [rsp+100h+Length], r14d
0x180004ff7  mov     r8d, 6B6h
0x180004ffd  jmp     short loc_180004FA0
0x180004fff  cmp     dword ptr [rbp+57h+DestinationString+4], 4
0x180005003  jnz     short loc_180005019
0x180005005  cmp     dword ptr [rbp+57h+DestinationString.Buffer], 4
0x180005009  jnz     short loc_180005019
0x18000500b  mov     ebx, dword ptr [rbp+57h+DestinationString.Buffer+4]
0x18000500e  mov     edi, r12d
0x180005011  mov     [rbp+57h+var_D0], ebx
0x180005014  jmp     loc_180004D82
0x180005019  lea     r9, aInvalidValueTy; "Invalid value type"
0x180005020  mov     r8d, 44Ah
0x180005026  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x18000502d  mov     ecx, 1
0x180005032  call    AslLogCallPrintf
0x180005037  mov     edi, 0C0000024h
0x18000503c  jmp     loc_180004D82
0x180005041  movzx   eax, [rbp+57h+DestinationString.MaximumLength]
0x180005045  lea     r9, aFailedToAlloca; "Failed to allocate %d bytes for user ke"...
0x18000504c  mov     r8d, 62Eh
0x180005052  mov     [rsp+100h+Length], eax
0x180005056  lea     rdx, aAslregistrybui_0; "AslRegistryBuildMachinePath"
0x18000505d  mov     ecx, 1
0x180005062  call    AslLogCallPrintf
0x180005067  lea     rdi, aOsdataSoftware; "\\OSDATA\\Software\\Microsoft\\Windows "...
0x18000506e  mov     r8d, 6B6h
0x180005074  mov     qword ptr [rsp+100h+Length+8], rdi
0x180005079  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x180005080  mov     [rsp+100h+Length], r14d
0x180005085  jmp     short loc_18000509D
0x180005087  mov     qword ptr [rsp+100h+Length+8], rdi
0x18000508c  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x180005093  mov     [rsp+100h+Length], eax
0x180005097  mov     r8d, 6E1h
0x18000509d  lea     rdx, aAslregistryget; "AslRegistryGetKey"
0x1800050a4  mov     ecx, 1
0x1800050a9  call    AslLogCallPrintf
0x1800050ae  jmp     loc_180004E8E
0x1800050b3  mov     rdx, rsi
0x1800050b6  lea     rcx, [rbp+57h+var_D0]
0x1800050ba  call    AslRegistryGetUInt32
0x1800050bf  mov     ebx, [rbp+57h+var_D0]
0x1800050c2  jmp     loc_180004EB5
0x1800050c7  mov     rcx, rsi; Handle
0x1800050ca  call    cs:__imp_ZwClose
0x1800050d0  jmp     loc_180004EDB
```
