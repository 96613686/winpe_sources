# SdbpCheckMatchingRegistryEntry

- ea: `0x18007f34c`
- end: `0x18007f54b`
- name: `SdbpCheckMatchingRegistryEntry`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007f220`

## callees

- `0x18001f138`
- `0x180044c64`
- `0x18007f34c`
- `0x18007f554`
- `0x1800827c0`

## import_xrefs

- `ntdll!ZwClose` at `0x18007f515`
- `ntdll!ZwClose` at `0x18007f515`
- `ntdll!ZwOpenKey` at `0x18007f443`
- `ntdll!ZwOpenKey` at `0x18007f4b3`
- `ntdll!ZwOpenKey` at `0x18007f443`
- `ntdll!ZwOpenKey` at `0x18007f4b3`
- `ntdll!ZwQuerySystemInformation` at `0x18007f462`
- `ntdll!ZwQuerySystemInformation` at `0x18007f462`
- `ntdll!RtlInitUnicodeString` at `0x18007f401`
- `ntdll!RtlInitUnicodeString` at `0x18007f401`

## string_xrefs

- `0x18007f3aa`: `\REGISTRY\MACHINE\%s`
- `0x18007f3d8`: `Failed to construct full key path`
- `0x18007f3e5`: `SdbpCheckMatchingRegistryEntry`
- `0x18007f483`: `SdbpCheckMatchingRegistryEntry`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingRegistryEntry(
        __int64 a1,
        wchar_t *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        void *Buf1,
        size_t Size,
        _DWORD *a9)
{
  unsigned int v10; // edi
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int64 SystemInformation; // [rsp+98h] [rbp-68h] BYREF
  int v16; // [rsp+A0h] [rbp-60h]
  WCHAR SourceString[264]; // [rsp+B0h] [rbp-50h] BYREF

  SourceString[0] = 0;
  SystemInformation = 0;
  v16 = 0;
  *a9 = 0;
  KeyHandle = 0;
  v10 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( (int)RtlStringCchPrintfW(SourceString, 260, L"\\REGISTRY\\MACHINE\\%s", a1) < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpCheckMatchingRegistryEntry",
      1538,
      (unsigned int)"Failed to construct full key path");
    goto LABEL_10;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    goto LABEL_9;
  if ( ZwQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0) < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpCheckMatchingRegistryEntry",
      1573,
      (unsigned int)"Failed to get processor architecture [%x]");
    goto LABEL_10;
  }
  if ( (_WORD)SystemInformation == 9 && ZwOpenKey(&KeyHandle, 0x20219u, &ObjectAttributes) >= 0 )
LABEL_9:
    v10 = SdbpCheckMatchingRegistryValue(KeyHandle, a2, a5, a6, Buf1, Size, (__int64)a9);
  else
    v10 = 1;
LABEL_10:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v10;
}

```

## disassembly

```asm
0x18007f34c  mov     [rsp-8+arg_10], rsi
0x18007f351  push    rbp
0x18007f352  push    rdi
0x18007f353  push    r12
0x18007f355  push    r14
0x18007f357  push    r15
0x18007f359  lea     rbp, [rsp-1D0h]
0x18007f361  sub     rsp, 2D0h
0x18007f368  mov     rax, cs:__security_cookie
0x18007f36f  xor     rax, rsp
0x18007f372  mov     [rbp+1F0h+var_30], rax
0x18007f379  mov     rsi, [rbp+1F0h+arg_40]
0x18007f380  xor     eax, eax
0x18007f382  xorps   xmm1, xmm1
0x18007f385  mov     [rbp+1F0h+SourceString], ax
0x18007f389  mov     r12, r9
0x18007f38c  mov     [rbp+1F0h+SystemInformation], rax
0x18007f390  mov     r14d, r8d
0x18007f393  mov     [rbp+1F0h+var_250], eax
0x18007f396  mov     r15, rdx
0x18007f399  mov     dword ptr [rsi], 0
0x18007f39f  xorps   xmm0, xmm0
0x18007f3a2  mov     [rsp+2F0h+KeyHandle], rax
0x18007f3a7  mov     r9, rcx
0x18007f3aa  lea     r8, aRegistryMachin_17; "\\REGISTRY\\MACHINE\\%s"
0x18007f3b1  mov     edx, 104h
0x18007f3b6  lea     rcx, [rbp+1F0h+SourceString]
0x18007f3ba  xor     edi, edi
0x18007f3bc  movups  xmmword ptr [rbp+1F0h+DestinationString.Length], xmm0
0x18007f3c0  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm1
0x18007f3c5  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm1
0x18007f3ca  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18007f3cf  call    RtlStringCchPrintfW
0x18007f3d4  test    eax, eax
0x18007f3d6  jns     short loc_18007F3F9
0x18007f3d8  lea     r9, aFailedToConstr; "Failed to construct full key path"
0x18007f3df  mov     r8d, 602h
0x18007f3e5  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x18007f3ec  lea     ecx, [rdi+1]
0x18007f3ef  call    AslLogCallPrintf
0x18007f3f4  jmp     loc_18007F50B
0x18007f3f9  lea     rdx, [rbp+1F0h+SourceString]; SourceString
0x18007f3fd  lea     rcx, [rbp+1F0h+DestinationString]; DestinationString
0x18007f401  call    cs:__imp_RtlInitUnicodeString
0x18007f408  nop     dword ptr [rax+rax+00h]
0x18007f40d  lea     rax, [rbp+1F0h+DestinationString]
0x18007f411  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18007f419  xorps   xmm0, xmm0
0x18007f41c  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x18007f421  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18007f426  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdi
0x18007f42b  mov     edx, 20019h; DesiredAccess
0x18007f430  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18007f438  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18007f43d  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007f443  call    cs:__imp_ZwOpenKey
0x18007f44a  nop     dword ptr [rax+rax+00h]
0x18007f44f  test    eax, eax
0x18007f451  jns     short loc_18007F4C3
0x18007f453  xor     r9d, r9d; ReturnLength
0x18007f456  lea     rdx, [rbp+1F0h+SystemInformation]; SystemInformation
0x18007f45a  lea     r8d, [r9+0Ch]; SystemInformationLength
0x18007f45e  lea     ecx, [r9+1]; SystemInformationClass
0x18007f462  call    cs:__imp_ZwQuerySystemInformation
0x18007f469  nop     dword ptr [rax+rax+00h]
0x18007f46e  test    eax, eax
0x18007f470  jns     short loc_18007F496
0x18007f472  lea     r9, aFailedToGetPro; "Failed to get processor architecture [%"...
0x18007f479  mov     [rsp+2F0h+var_2D0], eax
0x18007f47d  mov     r8d, 625h
0x18007f483  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x18007f48a  mov     ecx, 1
0x18007f48f  call    AslLogCallPrintf
0x18007f494  jmp     short loc_18007F50B
0x18007f496  cmp     word ptr [rbp+1F0h+SystemInformation], 9
0x18007f49b  jz      short loc_18007F4A4
0x18007f49d  mov     edi, 1
0x18007f4a2  jmp     short loc_18007F50B
0x18007f4a4  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18007f4a9  mov     edx, 20219h; DesiredAccess
0x18007f4ae  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18007f4b3  call    cs:__imp_ZwOpenKey
0x18007f4ba  nop     dword ptr [rax+rax+00h]
0x18007f4bf  test    eax, eax
0x18007f4c1  js      short loc_18007F49D
0x18007f4c3  mov     rax, [rbp+1F0h+arg_38]
0x18007f4ca  mov     r9, r12
0x18007f4cd  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18007f4d2  mov     r8d, r14d
0x18007f4d5  mov     [rsp+2F0h+var_2B0], rsi; __int64
0x18007f4da  mov     rdx, r15; String1
0x18007f4dd  mov     [rsp+2F0h+Size], rax; Size
0x18007f4e2  mov     rax, [rbp+1F0h+arg_30]
0x18007f4e9  mov     [rsp+2F0h+Buf1], rax; Buf1
0x18007f4ee  mov     rax, [rbp+1F0h+arg_28]
0x18007f4f5  mov     [rsp+2F0h+var_2C8], rax; __int64
0x18007f4fa  mov     eax, [rbp+1F0h+arg_20]
0x18007f500  mov     [rsp+2F0h+var_2D0], eax; int
0x18007f504  call    SdbpCheckMatchingRegistryValue
0x18007f509  mov     edi, eax
0x18007f50b  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x18007f510  test    rcx, rcx
0x18007f513  jz      short loc_18007F521
0x18007f515  call    cs:__imp_ZwClose
0x18007f51c  nop     dword ptr [rax+rax+00h]
0x18007f521  mov     eax, edi
0x18007f523  mov     rcx, [rbp+1F0h+var_30]
0x18007f52a  xor     rcx, rsp; StackCookie
0x18007f52d  call    __security_check_cookie
0x18007f532  mov     rsi, [rsp+2F0h+arg_10]
0x18007f53a  add     rsp, 2D0h
0x18007f541  pop     r15
0x18007f543  pop     r14
0x18007f545  pop     r12
0x18007f547  pop     rdi
0x18007f548  pop     rbp
0x18007f549  retn
```
