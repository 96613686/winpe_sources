# CsrCreateSessionObjectDirectory

- ea: `0x180003f20`
- end: `0x1800042a0`
- name: `CsrCreateSessionObjectDirectory`
- size: `896`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005180`

## callees

- `0x1800035c0`
- `0x180003f20`
- `0x1800042b0`
- `0x1800049b0`
- `0x18000ab80`

## import_xrefs

- `ntdll!NtCreateDirectoryObject` at `0x180003ff0`
- `ntdll!NtCreateDirectoryObject` at `0x18000419f`
- `ntdll!NtCreateDirectoryObject` at `0x180004253`
- `ntdll!NtCreateDirectoryObject` at `0x180003ff0`
- `ntdll!NtCreateDirectoryObject` at `0x18000419f`
- `ntdll!NtCreateDirectoryObject` at `0x180004253`
- `ntdll!NtSetInformationObject` at `0x1800041cd`
- `ntdll!NtSetInformationObject` at `0x1800041cd`
- `ntdll!RtlInitUnicodeString` at `0x180003fab`
- `ntdll!RtlInitUnicodeString` at `0x180004045`
- `ntdll!RtlInitUnicodeString` at `0x180004098`
- `ntdll!RtlInitUnicodeString` at `0x180004155`
- `ntdll!RtlInitUnicodeString` at `0x180004202`
- `ntdll!RtlInitUnicodeString` at `0x180003fab`
- `ntdll!RtlInitUnicodeString` at `0x180004045`
- `ntdll!RtlInitUnicodeString` at `0x180004098`
- `ntdll!RtlInitUnicodeString` at `0x180004155`
- `ntdll!RtlInitUnicodeString` at `0x180004202`
- `ntdll!swprintf_s` at `0x180003f96`
- `ntdll!swprintf_s` at `0x180004030`
- `ntdll!swprintf_s` at `0x180004080`
- `ntdll!swprintf_s` at `0x180004140`
- `ntdll!swprintf_s` at `0x180003f96`
- `ntdll!swprintf_s` at `0x180004030`
- `ntdll!swprintf_s` at `0x180004080`
- `ntdll!swprintf_s` at `0x180004140`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1800040e7`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1800040e7`

## string_xrefs

- `0x180003f55`: `%ws\BNOLINKS`
- `0x180004005`: `CsrCreateSessionObjectDirectory`
- `0x1800040fc`: `CsrCreateSessionObjectDirectory`
- `0x18000426d`: `CsrCreateSessionObjectDirectory`

## pseudocode

```c
__int64 CsrCreateSessionObjectDirectory()
{
  unsigned int v0; // ebx
  NTSTATUS v1; // edi
  __int64 result; // rax
  wchar_t *v3; // rdx
  NTSTATUS v4; // ebx
  __int64 v5; // [rsp+20h] [rbp-E0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  void *SymbolicLinkHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING Name; // [rsp+78h] [rbp-88h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v11; // [rsp+A8h] [rbp-58h]
  wchar_t Dst[256]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t SourceString[256]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v0 = g_SessionId;
  SymbolicLinkHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  v11 = 0;
  DestinationString = 0;
  Name = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  swprintf_s(Dst, 0x100u, L"%ws\\BNOLINKS", L"\\Sessions");
  RtlInitUnicodeString(&DestinationString, Dst);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 192;
  v1 = NtCreateDirectoryObject(&BNOLinksDirectory, 0xF000Fu, &ObjectAttributes);
  if ( v1 < 0 )
    goto LABEL_2;
  swprintf_s(Dst, 0x100u, L"%ld", v0);
  RtlInitUnicodeString(&DestinationString, Dst);
  if ( v0 == ServiceSessionId )
  {
    v3 = L"\\BaseNamedObjects";
  }
  else
  {
    swprintf_s(SourceString, 0x100u, L"%ws\\%ld\\BaseNamedObjects", L"\\Sessions", v0);
    v3 = SourceString;
  }
  RtlInitUnicodeString(&Name, v3);
  ObjectAttributes.RootDirectory = BNOLinksDirectory;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 192;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = NtCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes, &Name);
  if ( v1 < 0 )
  {
LABEL_2:
    CsrpLogFailure("CsrCreateSessionObjectDirectory");
    return (unsigned int)v1;
  }
  else
  {
    result = GetDosDevicesProtection(SecurityDescriptor);
    if ( (int)result >= 0 )
    {
      LODWORD(v5) = v0;
      swprintf_s(Dst, 0x100u, L"%ws\\%ld", L"\\Sessions", v5);
      RtlInitUnicodeString(&DestinationString, Dst);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
      ObjectAttributes.Attributes = 192;
      ObjectAttributes.SecurityQualityOfService = 0;
      v4 = NtCreateDirectoryObject(&SessionObjectDirectory, 0xF000Fu, &ObjectAttributes);
      if ( v4 < 0 )
        goto LABEL_12;
      v4 = NtSetInformationObject(SessionObjectDirectory, MaxObjectInfoClass, 0, 0);
      if ( (int)(v4 + 0x80000000) >= 0 && v4 != -1073740715 )
        goto LABEL_12;
      RtlInitUnicodeString(&DestinationString, L"DosDevices");
      ObjectAttributes.RootDirectory = SessionObjectDirectory;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
      ObjectAttributes.SecurityQualityOfService = 0;
      v4 = NtCreateDirectoryObject(&DosDevicesDirectory, 0xF000Fu, &ObjectAttributes);
      if ( v4 < 0 )
LABEL_12:
        CsrpLogFailure("CsrCreateSessionObjectDirectory");
      FreeDosDevicesProtection(SecurityDescriptor);
      return (unsigned int)v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003f20  push    rbp
0x180003f22  push    rbx
0x180003f23  push    rsi
0x180003f24  push    rdi
0x180003f25  lea     rbp, [rsp-3C8h]
0x180003f2d  sub     rsp, 4C8h
0x180003f34  mov     rax, cs:__security_cookie
0x180003f3b  xor     rax, rsp
0x180003f3e  mov     [rbp+3E0h+var_30], rax
0x180003f45  mov     ebx, cs:g_SessionId
0x180003f4b  lea     r9, aSessions; "\\Sessions"
0x180003f52  xorps   xmm0, xmm0
0x180003f55  lea     r8, aWsBnolinks; "%ws\\BNOLINKS"
0x180003f5c  xorps   xmm1, xmm1
0x180003f5f  lea     rcx, [rbp+3E0h+Dst]; Dst
0x180003f63  xor     eax, eax
0x180003f65  xor     esi, esi
0x180003f67  movups  xmmword ptr [rsp+4E0h+ObjectAttributes.ObjectName], xmm0
0x180003f6c  mov     edx, 100h; SizeInWords
0x180003f71  mov     [rsp+4E0h+SymbolicLinkHandle], rsi
0x180003f76  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+1Ch], xmm0
0x180003f7b  mov     [rbp+3E0h+var_438], rax
0x180003f7f  movups  xmmword ptr [rsp+4E0h+DestinationString.Length], xmm0
0x180003f84  movups  xmmword ptr [rsp+4E0h+Name.Length], xmm1
0x180003f89  movups  xmmword ptr [rsp+4E0h+ObjectAttributes.Length], xmm0
0x180003f8e  movups  [rbp+3E0h+SecurityDescriptor], xmm0
0x180003f92  movups  [rbp+3E0h+var_448], xmm0
0x180003f96  call    cs:__imp_swprintf_s
0x180003f9d  nop     dword ptr [rax+rax+00h]
0x180003fa2  lea     rdx, [rbp+3E0h+Dst]; SourceString
0x180003fa6  lea     rcx, [rsp+4E0h+DestinationString]; DestinationString
0x180003fab  call    cs:__imp_RtlInitUnicodeString
0x180003fb2  nop     dword ptr [rax+rax+00h]
0x180003fb7  lea     rax, [rsp+4E0h+DestinationString]
0x180003fbc  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x180003fc4  xorps   xmm0, xmm0
0x180003fc7  mov     [rsp+4E0h+ObjectAttributes.ObjectName], rax
0x180003fcc  lea     r8, [rsp+4E0h+ObjectAttributes]; ObjectAttributes
0x180003fd1  mov     [rsp+4E0h+ObjectAttributes.RootDirectory], rsi
0x180003fd6  mov     edx, 0F000Fh; DesiredAccess
0x180003fdb  mov     [rsp+4E0h+ObjectAttributes.Attributes], 0C0h
0x180003fe3  lea     rcx, BNOLinksDirectory; DirectoryHandle
0x180003fea  movdqu  xmmword ptr [rsp+4E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003ff0  call    cs:__imp_NtCreateDirectoryObject
0x180003ff7  nop     dword ptr [rax+rax+00h]
0x180003ffc  mov     edi, eax
0x180003ffe  test    eax, eax
0x180004000  jns     short loc_18000401D
0x180004002  mov     r8d, eax
0x180004005  lea     rcx, aCsrcreatesessi; "CsrCreateSessionObjectDirectory"
0x18000400c  mov     edx, 5C9h
0x180004011  call    CsrpLogFailure
0x180004016  mov     eax, edi
0x180004018  jmp     loc_180004284
0x18000401d  mov     r9d, ebx
0x180004020  lea     r8, aLd; "%ld"
0x180004027  mov     edx, 100h; SizeInWords
0x18000402c  lea     rcx, [rbp+3E0h+Dst]; Dst
0x180004030  call    cs:__imp_swprintf_s
0x180004037  nop     dword ptr [rax+rax+00h]
0x18000403c  lea     rdx, [rbp+3E0h+Dst]; SourceString
0x180004040  lea     rcx, [rsp+4E0h+DestinationString]; DestinationString
0x180004045  call    cs:__imp_RtlInitUnicodeString
0x18000404c  nop     dword ptr [rax+rax+00h]
0x180004051  cmp     ebx, cs:ServiceSessionId
0x180004057  jnz     short loc_180004062
0x180004059  lea     rdx, aBasenamedobjec; "\\BaseNamedObjects"
0x180004060  jmp     short loc_180004093
0x180004062  lea     r9, aSessions; "\\Sessions"
0x180004069  mov     [rsp+4E0h+var_4C0], ebx
0x18000406d  lea     r8, aWsLdBasenamedo; "%ws\\%ld\\BaseNamedObjects"
0x180004074  mov     edx, 100h; SizeInWords
0x180004079  lea     rcx, [rbp+3E0h+SourceString]; Dst
0x180004080  call    cs:__imp_swprintf_s
0x180004087  nop     dword ptr [rax+rax+00h]
0x18000408c  lea     rdx, [rbp+3E0h+SourceString]; SourceString
0x180004093  lea     rcx, [rsp+4E0h+Name]; DestinationString
0x180004098  call    cs:__imp_RtlInitUnicodeString
0x18000409f  nop     dword ptr [rax+rax+00h]
0x1800040a4  mov     rax, cs:BNOLinksDirectory
0x1800040ab  lea     r9, [rsp+4E0h+Name]; Name
0x1800040b0  mov     [rsp+4E0h+ObjectAttributes.RootDirectory], rax
0x1800040b5  lea     r8, [rsp+4E0h+ObjectAttributes]; ObjectAttributes
0x1800040ba  lea     rax, [rsp+4E0h+DestinationString]
0x1800040bf  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x1800040c7  xorps   xmm0, xmm0
0x1800040ca  mov     [rsp+4E0h+ObjectAttributes.ObjectName], rax
0x1800040cf  mov     edx, 0F0001h; DesiredAccess
0x1800040d4  mov     [rsp+4E0h+ObjectAttributes.Attributes], 0C0h
0x1800040dc  lea     rcx, [rsp+4E0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x1800040e1  movdqu  xmmword ptr [rsp+4E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800040e7  call    cs:__imp_NtCreateSymbolicLinkObject
0x1800040ee  nop     dword ptr [rax+rax+00h]
0x1800040f3  mov     edi, eax
0x1800040f5  test    eax, eax
0x1800040f7  jns     short loc_180004114
0x1800040f9  mov     r8d, eax
0x1800040fc  lea     rcx, aCsrcreatesessi; "CsrCreateSessionObjectDirectory"
0x180004103  mov     edx, 5F4h
0x180004108  call    CsrpLogFailure
0x18000410d  mov     eax, edi
0x18000410f  jmp     loc_180004284
0x180004114  lea     rcx, [rbp+3E0h+SecurityDescriptor]; SecurityDescriptor
0x180004118  call    GetDosDevicesProtection
0x18000411d  test    eax, eax
0x18000411f  js      loc_180004284
0x180004125  lea     r9, aSessions; "\\Sessions"
0x18000412c  mov     [rsp+4E0h+var_4C0], ebx
0x180004130  lea     r8, aWsLd; "%ws\\%ld"
0x180004137  mov     edx, 100h; SizeInWords
0x18000413c  lea     rcx, [rbp+3E0h+Dst]; Dst
0x180004140  call    cs:__imp_swprintf_s
0x180004147  nop     dword ptr [rax+rax+00h]
0x18000414c  lea     rdx, [rbp+3E0h+Dst]; SourceString
0x180004150  lea     rcx, [rsp+4E0h+DestinationString]; DestinationString
0x180004155  call    cs:__imp_RtlInitUnicodeString
0x18000415c  nop     dword ptr [rax+rax+00h]
0x180004161  lea     rax, [rsp+4E0h+DestinationString]
0x180004166  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x18000416e  mov     [rsp+4E0h+ObjectAttributes.ObjectName], rax
0x180004173  lea     r8, [rsp+4E0h+ObjectAttributes]; ObjectAttributes
0x180004178  lea     rax, [rbp+3E0h+SecurityDescriptor]
0x18000417c  mov     [rsp+4E0h+ObjectAttributes.RootDirectory], rsi
0x180004181  mov     edx, 0F000Fh; DesiredAccess
0x180004186  mov     [rsp+4E0h+ObjectAttributes.SecurityDescriptor], rax
0x18000418b  lea     rcx, SessionObjectDirectory; DirectoryHandle
0x180004192  mov     [rsp+4E0h+ObjectAttributes.Attributes], 0C0h
0x18000419a  mov     [rsp+4E0h+ObjectAttributes.SecurityQualityOfService], rsi
0x18000419f  call    cs:__imp_NtCreateDirectoryObject
0x1800041a6  nop     dword ptr [rax+rax+00h]
0x1800041ab  mov     ebx, eax
0x1800041ad  test    eax, eax
0x1800041af  jns     short loc_1800041BB
0x1800041b1  mov     edx, 620h
0x1800041b6  jmp     loc_18000426A
0x1800041bb  mov     rcx, cs:SessionObjectDirectory; ObjectHandle
0x1800041c2  xor     r9d, r9d; Length
0x1800041c5  xor     r8d, r8d; ObjectInformation
0x1800041c8  mov     edx, 6; ObjectInformationClass
0x1800041cd  call    cs:__imp_NtSetInformationObject
0x1800041d4  nop     dword ptr [rax+rax+00h]
0x1800041d9  mov     ebx, eax
0x1800041db  mov     eax, 80000000h
0x1800041e0  lea     ecx, [rbx+rax]
0x1800041e3  test    eax, ecx
0x1800041e5  jnz     short loc_1800041F6
0x1800041e7  cmp     ebx, 0C0000455h
0x1800041ed  jz      short loc_1800041F6
0x1800041ef  mov     edx, 645h
0x1800041f4  jmp     short loc_18000426A
0x1800041f6  lea     rdx, aDosdevices_0; "DosDevices"
0x1800041fd  lea     rcx, [rsp+4E0h+DestinationString]; DestinationString
0x180004202  call    cs:__imp_RtlInitUnicodeString
0x180004209  nop     dword ptr [rax+rax+00h]
0x18000420e  mov     rax, cs:SessionObjectDirectory
0x180004215  lea     r8, [rsp+4E0h+ObjectAttributes]; ObjectAttributes
0x18000421a  mov     [rsp+4E0h+ObjectAttributes.RootDirectory], rax
0x18000421f  lea     rcx, DosDevicesDirectory; DirectoryHandle
0x180004226  lea     rax, [rsp+4E0h+DestinationString]
0x18000422b  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x180004233  mov     [rsp+4E0h+ObjectAttributes.ObjectName], rax
0x180004238  mov     edx, 0F000Fh; DesiredAccess
0x18000423d  lea     rax, [rbp+3E0h+SecurityDescriptor]
0x180004241  mov     [rsp+4E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180004249  mov     [rsp+4E0h+ObjectAttributes.SecurityDescriptor], rax
0x18000424e  mov     [rsp+4E0h+ObjectAttributes.SecurityQualityOfService], rsi
0x180004253  call    cs:__imp_NtCreateDirectoryObject
0x18000425a  nop     dword ptr [rax+rax+00h]
0x18000425f  mov     ebx, eax
0x180004261  test    eax, eax
0x180004263  jns     short loc_180004279
0x180004265  mov     edx, 661h
0x18000426a  mov     r8d, ebx
0x18000426d  lea     rcx, aCsrcreatesessi; "CsrCreateSessionObjectDirectory"
0x180004274  call    CsrpLogFailure
0x180004279  lea     rcx, [rbp+3E0h+SecurityDescriptor]
0x18000427d  call    FreeDosDevicesProtection
0x180004282  mov     eax, ebx
0x180004284  mov     rcx, [rbp+3E0h+var_30]
0x18000428b  xor     rcx, rsp; StackCookie
0x18000428e  call    __security_check_cookie
0x180004293  add     rsp, 4C8h
0x18000429a  pop     rdi
0x18000429b  pop     rsi
0x18000429c  pop     rbx
0x18000429d  pop     rbp
0x18000429e  retn
```
