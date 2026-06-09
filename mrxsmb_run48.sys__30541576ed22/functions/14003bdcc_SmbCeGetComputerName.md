# SmbCeGetComputerName

- ea: `0x14003bdcc`
- end: `0x14003c17c`
- name: `SmbCeGetComputerName`
- size: `944`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001f0e0`

## callees

- `0x14001c5f0`
- `0x14001e960`
- `0x14003838c`
- `0x140039fa8`
- `0x14003bdcc`
- `0x140059dc0`
- `0x140059f00`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14003c0af`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c0af`
- `ntoskrnl!ZwOpenKey` at `0x14003bf60`
- `ntoskrnl!ZwOpenKey` at `0x14003c05b`
- `ntoskrnl!ZwOpenKey` at `0x14003bf60`
- `ntoskrnl!ZwOpenKey` at `0x14003c05b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003beba`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c07b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003beba`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c07b`
- `ntoskrnl!ExAllocatePool2` at `0x14003c105`
- `ntoskrnl!ExAllocatePool2` at `0x14003c105`
- `ntoskrnl!ZwClose` at `0x14003c0c2`
- `ntoskrnl!ZwClose` at `0x14003c0c2`

## string_xrefs

- `0x14003be2c`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName`
- `0x14003bf86`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName`
- `0x14003be33`: `ComputerName`
- `0x14003bf8d`: `ComputerName`
- `0x14003c06f`: `ComputerName`
- `0x14003bed4`: `\ComputerName`
- `0x14003bfd6`: `\ComputerName`
- `0x14003becd`: `\ActiveComputerName`

## pseudocode

```c
NTSTATUS SmbCeGetComputerName()
{
  NTSTATUS inited; // ebx
  PDEVICE_OBJECT v1; // r10
  __int64 v2; // rdx
  NTSTATUS result; // eax
  const wchar_t *v4; // rdx
  unsigned int v5; // edi
  wchar_t *Pool2; // rax
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE KeyValueInformation[8]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int Size; // [rsp+88h] [rbp-78h]
  size_t Size_4; // [rsp+8Ch] [rbp-74h] BYREF
  char v14; // [rsp+2A0h] [rbp+1A0h] BYREF

  *(_QWORD *)&DestinationString.Length = 34078720;
  KeyHandle = 0;
  DestinationString.Buffer = (wchar_t *)&v14;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  inited = MRxSmbInitRedirectedPath(
             L"ComputerName",
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName",
             &DestinationString);
  if ( inited < 0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return inited;
    }
    v2 = 45;
    goto LABEL_6;
  }
  RtlInitUnicodeString(&::DestinationString, 0);
  v4 = L"\\ComputerName";
  if ( !MRxSmbBootedRemotely )
    v4 = L"\\ActiveComputerName";
  inited = RtlUnicodeStringCatString(&DestinationString, v4);
  if ( inited < 0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return inited;
    }
    v2 = 46;
    goto LABEL_6;
  }
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
    goto LABEL_29;
  if ( !MRxSmbBootedRemotely )
  {
    inited = MRxSmbInitRedirectedPath(
               L"ComputerName",
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName",
               &DestinationString);
    if ( inited < 0 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return inited;
      }
      v2 = 47;
      goto LABEL_6;
    }
    inited = RtlUnicodeStringCatString(&DestinationString, L"\\ComputerName");
    if ( inited < 0 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return inited;
      }
      v2 = 48;
LABEL_6:
      WPP_SF_d(v1->AttachedDevice, v2, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, (unsigned int)inited);
      return inited;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( result >= 0 )
    {
LABEL_29:
      RtlInitUnicodeString(&DestinationString, L"ComputerName");
      inited = ZwQueryValueKey(
                 KeyHandle,
                 &DestinationString,
                 KeyValuePartialInformation,
                 KeyValueInformation,
                 0x220u,
                 &ResultLength);
      ZwClose(KeyHandle);
      if ( inited < 0 )
        return inited;
      if ( Size - 2 <= 0xFFFD )
      {
        ::DestinationString.MaximumLength = Size;
        ::DestinationString.Length = Size - 2;
        v5 = Size;
        Pool2 = (wchar_t *)ExAllocatePool2(66, Size, 1834182211);
        ::DestinationString.Buffer = Pool2;
        if ( !Pool2 )
          return -1073741670;
        memmove(Pool2, &Size_4, v5);
        return inited;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids);
      }
      return -1073741811;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003bdcc  mov     [rsp-8+arg_0], rbx
0x14003bdd1  mov     [rsp-8+arg_8], rdi
0x14003bdd6  push    rbp
0x14003bdd7  lea     rbp, [rsp-3C0h]
0x14003bddf  sub     rsp, 4C0h
0x14003bde6  mov     rax, cs:__security_cookie
0x14003bded  xor     rax, rsp
0x14003bdf0  mov     [rbp+3C0h+var_10], rax
0x14003bdf7  xorps   xmm0, xmm0
0x14003bdfa  mov     qword ptr [rsp+4C0h+DestinationString.Length], 2080000h
0x14003be03  lea     rax, [rbp+3C0h+var_220]
0x14003be0a  mov     [rsp+4C0h+KeyHandle], 0
0x14003be13  mov     [rsp+4C0h+DestinationString.Buffer], rax
0x14003be18  lea     r8, [rsp+4C0h+DestinationString]
0x14003be1d  movups  xmmword ptr [rsp+4C0h+ObjectAttributes.ObjectName], xmm0
0x14003be22  xor     eax, eax
0x14003be24  mov     [rsp+4C0h+var_478], 0
0x14003be2c  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14003be33  lea     rcx, aComputername; "ComputerName"
0x14003be3a  movups  xmmword ptr [rsp+4C0h+ObjectAttributes.Length], xmm0
0x14003be3f  movups  xmmword ptr [rsp+4C0h+ObjectAttributes+1Ch], xmm0
0x14003be44  call    MRxSmbInitRedirectedPath
0x14003be49  mov     ebx, eax
0x14003be4b  test    eax, eax
0x14003be4d  jns     short loc_14003BEB1
0x14003be4f  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003be56  lea     rcx, WPP_GLOBAL_Control
0x14003be5d  cmp     r10, rcx
0x14003be60  jz      short loc_14003BE8A
0x14003be62  mov     edx, [r10+2Ch]
0x14003be66  test    dl, 1
0x14003be69  jz      short loc_14003BE8A
0x14003be6b  cmp     byte ptr [r10+29h], 1
0x14003be70  jb      short loc_14003BE8A
0x14003be72  mov     edx, 2Dh ; '-'
0x14003be77  mov     rcx, [r10+18h]
0x14003be7b  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14003be82  mov     r9d, ebx
0x14003be85  call    WPP_SF_d
0x14003be8a  mov     eax, ebx
0x14003be8c  mov     rcx, [rbp+3C0h+var_10]
0x14003be93  xor     rcx, rsp; StackCookie
0x14003be96  call    __security_check_cookie
0x14003be9b  lea     r11, [rsp+4C0h+var_s0]
0x14003bea3  mov     rbx, [r11+10h]
0x14003bea7  mov     rdi, [r11+18h]
0x14003beab  mov     rsp, r11
0x14003beae  pop     rbp
0x14003beaf  retn
0x14003beb1  xor     edx, edx; SourceString
0x14003beb3  lea     rcx, DestinationString; DestinationString
0x14003beba  call    cs:__imp_RtlInitUnicodeString
0x14003bec1  nop     dword ptr [rax+rax+00h]
0x14003bec6  cmp     cs:MRxSmbBootedRemotely, 0
0x14003becd  lea     rax, pszSrc; "\\ActiveComputerName"
0x14003bed4  lea     rdx, aComputername_0; "\\ComputerName"
0x14003bedb  cmovz   rdx, rax; pszSrc
0x14003bedf  lea     rcx, [rsp+4C0h+DestinationString]; DestinationString
0x14003bee4  call    RtlUnicodeStringCatString
0x14003bee9  mov     ebx, eax
0x14003beeb  test    eax, eax
0x14003beed  jns     short loc_14003BF24
0x14003beef  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003bef6  lea     rcx, WPP_GLOBAL_Control
0x14003befd  cmp     r10, rcx
0x14003bf00  jz      short loc_14003BE8A
0x14003bf02  mov     edx, [r10+2Ch]
0x14003bf06  test    dl, 1
0x14003bf09  jz      loc_14003BE8A
0x14003bf0f  cmp     byte ptr [r10+29h], 1
0x14003bf14  jb      loc_14003BE8A
0x14003bf1a  mov     edx, 2Eh ; '.'
0x14003bf1f  jmp     loc_14003BE77
0x14003bf24  lea     rax, [rsp+4C0h+DestinationString]
0x14003bf29  mov     [rsp+4C0h+ObjectAttributes.RootDirectory], 0
0x14003bf32  xorps   xmm0, xmm0
0x14003bf35  mov     [rsp+4C0h+ObjectAttributes.ObjectName], rax
0x14003bf3a  mov     edi, 30h ; '0'
0x14003bf3f  mov     [rsp+4C0h+ObjectAttributes.Attributes], 240h
0x14003bf47  lea     r8, [rsp+4C0h+ObjectAttributes]; ObjectAttributes
0x14003bf4c  mov     [rsp+4C0h+ObjectAttributes.Length], edi
0x14003bf50  mov     edx, 20019h; DesiredAccess
0x14003bf55  lea     rcx, [rsp+4C0h+KeyHandle]; KeyHandle
0x14003bf5a  movdqu  xmmword ptr [rsp+4C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003bf60  call    cs:__imp_ZwOpenKey
0x14003bf67  nop     dword ptr [rax+rax+00h]
0x14003bf6c  test    eax, eax
0x14003bf6e  jns     loc_14003C06F
0x14003bf74  cmp     cs:MRxSmbBootedRemotely, 0
0x14003bf7b  jnz     loc_14003BE8C
0x14003bf81  lea     r8, [rsp+4C0h+DestinationString]
0x14003bf86  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14003bf8d  lea     rcx, aComputername; "ComputerName"
0x14003bf94  call    MRxSmbInitRedirectedPath
0x14003bf99  mov     ebx, eax
0x14003bf9b  test    eax, eax
0x14003bf9d  jns     short loc_14003BFD6
0x14003bf9f  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003bfa6  lea     rcx, WPP_GLOBAL_Control
0x14003bfad  cmp     r10, rcx
0x14003bfb0  jz      loc_14003BE8A
0x14003bfb6  mov     edx, [r10+2Ch]
0x14003bfba  test    dl, 1
0x14003bfbd  jz      loc_14003BE8A
0x14003bfc3  cmp     byte ptr [r10+29h], 1
0x14003bfc8  jb      loc_14003BE8A
0x14003bfce  lea     edx, [rdi-1]
0x14003bfd1  jmp     loc_14003BE77
0x14003bfd6  lea     rdx, aComputername_0; "\\ComputerName"
0x14003bfdd  lea     rcx, [rsp+4C0h+DestinationString]; DestinationString
0x14003bfe2  call    RtlUnicodeStringCatString
0x14003bfe7  mov     ebx, eax
0x14003bfe9  test    eax, eax
0x14003bfeb  jns     short loc_14003C024
0x14003bfed  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003bff4  lea     rcx, WPP_GLOBAL_Control
0x14003bffb  cmp     r10, rcx
0x14003bffe  jz      loc_14003BE8A
0x14003c004  mov     r8d, [r10+2Ch]
0x14003c008  test    r8b, 1
0x14003c00c  jz      loc_14003BE8A
0x14003c012  cmp     byte ptr [r10+29h], 1
0x14003c017  jb      loc_14003BE8A
0x14003c01d  mov     edx, edi
0x14003c01f  jmp     loc_14003BE77
0x14003c024  lea     rax, [rsp+4C0h+DestinationString]
0x14003c029  mov     [rsp+4C0h+ObjectAttributes.Length], edi
0x14003c02d  xorps   xmm0, xmm0
0x14003c030  mov     [rsp+4C0h+ObjectAttributes.ObjectName], rax
0x14003c035  lea     r8, [rsp+4C0h+ObjectAttributes]; ObjectAttributes
0x14003c03a  mov     [rsp+4C0h+ObjectAttributes.RootDirectory], 0
0x14003c043  mov     edx, 20019h; DesiredAccess
0x14003c048  mov     [rsp+4C0h+ObjectAttributes.Attributes], 240h
0x14003c050  lea     rcx, [rsp+4C0h+KeyHandle]; KeyHandle
0x14003c055  movdqu  xmmword ptr [rsp+4C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003c05b  call    cs:__imp_ZwOpenKey
0x14003c062  nop     dword ptr [rax+rax+00h]
0x14003c067  test    eax, eax
0x14003c069  js      loc_14003BE8C
0x14003c06f  lea     rdx, aComputername; "ComputerName"
0x14003c076  lea     rcx, [rsp+4C0h+DestinationString]; DestinationString
0x14003c07b  call    cs:__imp_RtlInitUnicodeString
0x14003c082  nop     dword ptr [rax+rax+00h]
0x14003c087  mov     rcx, [rsp+4C0h+KeyHandle]; KeyHandle
0x14003c08c  lea     rax, [rsp+4C0h+var_478]
0x14003c091  mov     [rsp+4C0h+ResultLength], rax; ResultLength
0x14003c096  lea     r9, [rbp+3C0h+KeyValueInformation]; KeyValueInformation
0x14003c09a  mov     edi, 2
0x14003c09f  mov     [rsp+4C0h+Length], 220h; Length
0x14003c0a7  mov     r8d, edi; KeyValueInformationClass
0x14003c0aa  lea     rdx, [rsp+4C0h+DestinationString]; ValueName
0x14003c0af  call    cs:__imp_ZwQueryValueKey
0x14003c0b6  nop     dword ptr [rax+rax+00h]
0x14003c0bb  mov     rcx, [rsp+4C0h+KeyHandle]; Handle
0x14003c0c0  mov     ebx, eax
0x14003c0c2  call    cs:__imp_ZwClose
0x14003c0c9  nop     dword ptr [rax+rax+00h]
0x14003c0ce  test    ebx, ebx
0x14003c0d0  js      loc_14003BE8A
0x14003c0d6  mov     edx, dword ptr [rbp+3C0h+Size]
0x14003c0d9  lea     ecx, [rdx-2]
0x14003c0dc  cmp     ecx, 0FFFDh
0x14003c0e2  ja      short loc_14003C13B
0x14003c0e4  movzx   ecx, dx
0x14003c0e7  mov     cs:DestinationString.MaximumLength, dx
0x14003c0ee  sub     cx, di
0x14003c0f1  mov     r8d, 6D536643h
0x14003c0f7  mov     cs:DestinationString.Length, cx
0x14003c0fe  mov     edi, edx
0x14003c100  mov     ecx, 42h ; 'B'
0x14003c105  call    cs:__imp_ExAllocatePool2
0x14003c10c  nop     dword ptr [rax+rax+00h]
0x14003c111  mov     cs:DestinationString.Buffer, rax
0x14003c118  test    rax, rax
0x14003c11b  jz      short loc_14003C131
0x14003c11d  mov     r8d, edi; Size
0x14003c120  lea     rdx, [rbp+3C0h+Size+4]; Src
0x14003c124  mov     rcx, rax; void *
0x14003c127  call    memmove
0x14003c12c  jmp     loc_14003BE8A
0x14003c131  mov     ebx, 0C000009Ah
0x14003c136  jmp     loc_14003BE8A
0x14003c13b  mov     r9, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c142  lea     rcx, WPP_GLOBAL_Control
0x14003c149  cmp     r9, rcx
0x14003c14c  jz      short loc_14003C172
0x14003c14e  mov     eax, [r9+2Ch]
0x14003c152  test    al, 1
0x14003c154  jz      short loc_14003C172
0x14003c156  cmp     byte ptr [r9+29h], 1
0x14003c15b  jb      short loc_14003C172
0x14003c15d  mov     rcx, [r9+18h]
0x14003c161  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14003c168  mov     edx, 31h ; '1'
0x14003c16d  call    WPP_SF_
0x14003c172  mov     eax, 0C000000Dh
0x14003c177  jmp     loc_14003BE8C
```
