# SdbpCheckMatchingRegistryEntry

- ea: `0x18007754c`
- end: `0x18007772c`
- name: `SdbpCheckMatchingRegistryEntry`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180077420`

## callees

- `0x1800212e4`
- `0x180040fb0`
- `0x18007754c`
- `0x180077734`
- `0x18007a840`

## import_xrefs

- `ntdll!ZwClose` at `0x1800776fd`
- `ntdll!ZwClose` at `0x1800776fd`
- `ntdll!ZwOpenKey` at `0x18007763d`
- `ntdll!ZwOpenKey` at `0x1800776a1`
- `ntdll!ZwOpenKey` at `0x18007763d`
- `ntdll!ZwOpenKey` at `0x1800776a1`
- `ntdll!ZwQuerySystemInformation` at `0x180077656`
- `ntdll!ZwQuerySystemInformation` at `0x180077656`
- `ntdll!RtlInitUnicodeString` at `0x180077601`
- `ntdll!RtlInitUnicodeString` at `0x180077601`

## string_xrefs

- `0x1800775e5`: `SdbpCheckMatchingRegistryEntry`
- `0x180077671`: `SdbpCheckMatchingRegistryEntry`
- `0x1800775aa`: `\REGISTRY\MACHINE\%s`
- `0x1800775d8`: `Failed to construct full key path`

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
0x18007754c  mov     [rsp-8+arg_10], rsi
0x180077551  push    rbp
0x180077552  push    rdi
0x180077553  push    r12
0x180077555  push    r14
0x180077557  push    r15
0x180077559  lea     rbp, [rsp-1D0h]
0x180077561  sub     rsp, 2D0h
0x180077568  mov     rax, cs:__security_cookie
0x18007756f  xor     rax, rsp
0x180077572  mov     [rbp+1F0h+var_30], rax
0x180077579  mov     rsi, [rbp+1F0h+arg_40]
0x180077580  xor     eax, eax
0x180077582  xorps   xmm1, xmm1
0x180077585  mov     [rbp+1F0h+SourceString], ax
0x180077589  mov     r12, r9
0x18007758c  mov     [rbp+1F0h+SystemInformation], rax
0x180077590  mov     r14d, r8d
0x180077593  mov     [rbp+1F0h+var_250], eax
0x180077596  mov     r15, rdx
0x180077599  mov     dword ptr [rsi], 0
0x18007759f  xorps   xmm0, xmm0
0x1800775a2  mov     [rsp+2F0h+KeyHandle], rax
0x1800775a7  mov     r9, rcx
0x1800775aa  lea     r8, aRegistryMachin_17; "\\REGISTRY\\MACHINE\\%s"
0x1800775b1  mov     edx, 104h
0x1800775b6  lea     rcx, [rbp+1F0h+SourceString]
0x1800775ba  xor     edi, edi
0x1800775bc  movups  xmmword ptr [rbp+1F0h+DestinationString.Length], xmm0
0x1800775c0  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm1
0x1800775c5  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm1
0x1800775ca  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800775cf  call    RtlStringCchPrintfW
0x1800775d4  test    eax, eax
0x1800775d6  jns     short loc_1800775F9
0x1800775d8  lea     r9, aFailedToConstr; "Failed to construct full key path"
0x1800775df  mov     r8d, 602h
0x1800775e5  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x1800775ec  lea     ecx, [rdi+1]
0x1800775ef  call    AslLogCallPrintf
0x1800775f4  jmp     loc_1800776F3
0x1800775f9  lea     rdx, [rbp+1F0h+SourceString]; SourceString
0x1800775fd  lea     rcx, [rbp+1F0h+DestinationString]; DestinationString
0x180077601  call    cs:__imp_RtlInitUnicodeString
0x180077607  lea     rax, [rbp+1F0h+DestinationString]
0x18007760b  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x180077613  xorps   xmm0, xmm0
0x180077616  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x18007761b  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x180077620  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdi
0x180077625  mov     edx, 20019h; DesiredAccess
0x18007762a  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x180077632  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x180077637  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007763d  call    cs:__imp_ZwOpenKey
0x180077643  test    eax, eax
0x180077645  jns     short loc_1800776AB
0x180077647  xor     r9d, r9d; ReturnLength
0x18007764a  lea     rdx, [rbp+1F0h+SystemInformation]; SystemInformation
0x18007764e  lea     r8d, [r9+0Ch]; SystemInformationLength
0x180077652  lea     ecx, [r9+1]; SystemInformationClass
0x180077656  call    cs:__imp_ZwQuerySystemInformation
0x18007765c  test    eax, eax
0x18007765e  jns     short loc_180077684
0x180077660  lea     r9, aFailedToGetPro; "Failed to get processor architecture [%"...
0x180077667  mov     [rsp+2F0h+var_2D0], eax
0x18007766b  mov     r8d, 625h
0x180077671  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x180077678  mov     ecx, 1
0x18007767d  call    AslLogCallPrintf
0x180077682  jmp     short loc_1800776F3
0x180077684  cmp     word ptr [rbp+1F0h+SystemInformation], 9
0x180077689  jz      short loc_180077692
0x18007768b  mov     edi, 1
0x180077690  jmp     short loc_1800776F3
0x180077692  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x180077697  mov     edx, 20219h; DesiredAccess
0x18007769c  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x1800776a1  call    cs:__imp_ZwOpenKey
0x1800776a7  test    eax, eax
0x1800776a9  js      short loc_18007768B
0x1800776ab  mov     rax, [rbp+1F0h+arg_38]
0x1800776b2  mov     r9, r12
0x1800776b5  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x1800776ba  mov     r8d, r14d
0x1800776bd  mov     [rsp+2F0h+var_2B0], rsi; __int64
0x1800776c2  mov     rdx, r15; String1
0x1800776c5  mov     [rsp+2F0h+Size], rax; Size
0x1800776ca  mov     rax, [rbp+1F0h+arg_30]
0x1800776d1  mov     [rsp+2F0h+Buf1], rax; Buf1
0x1800776d6  mov     rax, [rbp+1F0h+arg_28]
0x1800776dd  mov     [rsp+2F0h+var_2C8], rax; __int64
0x1800776e2  mov     eax, [rbp+1F0h+arg_20]
0x1800776e8  mov     [rsp+2F0h+var_2D0], eax; int
0x1800776ec  call    SdbpCheckMatchingRegistryValue
0x1800776f1  mov     edi, eax
0x1800776f3  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x1800776f8  test    rcx, rcx
0x1800776fb  jz      short loc_180077703
0x1800776fd  call    cs:__imp_ZwClose
0x180077703  mov     eax, edi
0x180077705  mov     rcx, [rbp+1F0h+var_30]
0x18007770c  xor     rcx, rsp; StackCookie
0x18007770f  call    __security_check_cookie
0x180077714  mov     rsi, [rsp+2F0h+arg_10]
0x18007771c  add     rsp, 2D0h
0x180077723  pop     r15
0x180077725  pop     r14
0x180077727  pop     r12
0x180077729  pop     rdi
0x18007772a  pop     rbp
0x18007772b  retn
```
