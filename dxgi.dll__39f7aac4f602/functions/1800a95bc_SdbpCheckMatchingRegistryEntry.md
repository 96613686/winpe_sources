# SdbpCheckMatchingRegistryEntry

- ea: `0x1800a95bc`
- end: `0x1800a979c`
- name: `SdbpCheckMatchingRegistryEntry`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a9490`

## callees

- `0x18004281c`
- `0x180075fa0`
- `0x1800a7660`
- `0x1800a95bc`
- `0x1800a97a4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800a9671`
- `ntdll!RtlInitUnicodeString` at `0x1800a9671`
- `ntdll!ZwClose` at `0x1800a976d`
- `ntdll!ZwClose` at `0x1800a976d`
- `ntdll!ZwOpenKey` at `0x1800a96ad`
- `ntdll!ZwOpenKey` at `0x1800a9711`
- `ntdll!ZwOpenKey` at `0x1800a96ad`
- `ntdll!ZwOpenKey` at `0x1800a9711`
- `ntdll!ZwQuerySystemInformation` at `0x1800a96c6`
- `ntdll!ZwQuerySystemInformation` at `0x1800a96c6`

## string_xrefs

- `0x1800a961a`: `\REGISTRY\MACHINE\%s`
- `0x1800a9655`: `SdbpCheckMatchingRegistryEntry`
- `0x1800a96e1`: `SdbpCheckMatchingRegistryEntry`
- `0x1800a9648`: `Failed to construct full key path`

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
  NTSTATUS v11; // eax
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int64 SystemInformation; // [rsp+98h] [rbp-68h] BYREF
  int v17; // [rsp+A0h] [rbp-60h]
  WCHAR SourceString[264]; // [rsp+B0h] [rbp-50h] BYREF

  SourceString[0] = 0;
  SystemInformation = 0;
  v17 = 0;
  *a9 = 0;
  KeyHandle = 0;
  v10 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( (int)RtlStringCchPrintfW(SourceString, 260, L"\\REGISTRY\\MACHINE\\%s", a1) < 0 )
  {
    AslLogCallPrintf(1, "SdbpCheckMatchingRegistryEntry", 1538, "Failed to construct full key path");
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
  v11 = ZwQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0);
  if ( v11 < 0 )
  {
    AslLogCallPrintf(1, "SdbpCheckMatchingRegistryEntry", 1573, "Failed to get processor architecture [%x]", v11);
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
0x1800a95bc  mov     [rsp-8+arg_10], rsi
0x1800a95c1  push    rbp
0x1800a95c2  push    rdi
0x1800a95c3  push    r12
0x1800a95c5  push    r14
0x1800a95c7  push    r15
0x1800a95c9  lea     rbp, [rsp-1D0h]
0x1800a95d1  sub     rsp, 2D0h
0x1800a95d8  mov     rax, cs:__security_cookie
0x1800a95df  xor     rax, rsp
0x1800a95e2  mov     [rbp+1F0h+var_30], rax
0x1800a95e9  mov     rsi, [rbp+1F0h+arg_40]
0x1800a95f0  xor     eax, eax
0x1800a95f2  xorps   xmm1, xmm1
0x1800a95f5  mov     [rbp+1F0h+SourceString], ax
0x1800a95f9  mov     r12, r9
0x1800a95fc  mov     [rbp+1F0h+SystemInformation], rax
0x1800a9600  mov     r14d, r8d
0x1800a9603  mov     [rbp+1F0h+var_250], eax
0x1800a9606  mov     r15, rdx
0x1800a9609  mov     dword ptr [rsi], 0
0x1800a960f  xorps   xmm0, xmm0
0x1800a9612  mov     [rsp+2F0h+KeyHandle], rax
0x1800a9617  mov     r9, rcx
0x1800a961a  lea     r8, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\%s"
0x1800a9621  mov     edx, 104h
0x1800a9626  lea     rcx, [rbp+1F0h+SourceString]
0x1800a962a  xor     edi, edi
0x1800a962c  movups  xmmword ptr [rbp+1F0h+DestinationString.Length], xmm0
0x1800a9630  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm1
0x1800a9635  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm1
0x1800a963a  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800a963f  call    RtlStringCchPrintfW
0x1800a9644  test    eax, eax
0x1800a9646  jns     short loc_1800A9669
0x1800a9648  lea     r9, aFailedToConstr; "Failed to construct full key path"
0x1800a964f  mov     r8d, 602h
0x1800a9655  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x1800a965c  lea     ecx, [rdi+1]
0x1800a965f  call    AslLogCallPrintf
0x1800a9664  jmp     loc_1800A9763
0x1800a9669  lea     rdx, [rbp+1F0h+SourceString]; SourceString
0x1800a966d  lea     rcx, [rbp+1F0h+DestinationString]; DestinationString
0x1800a9671  call    cs:__imp_RtlInitUnicodeString
0x1800a9677  lea     rax, [rbp+1F0h+DestinationString]
0x1800a967b  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x1800a9683  xorps   xmm0, xmm0
0x1800a9686  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x1800a968b  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x1800a9690  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdi
0x1800a9695  mov     edx, 20019h; DesiredAccess
0x1800a969a  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800a96a2  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x1800a96a7  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a96ad  call    cs:__imp_ZwOpenKey
0x1800a96b3  test    eax, eax
0x1800a96b5  jns     short loc_1800A971B
0x1800a96b7  xor     r9d, r9d; ReturnLength
0x1800a96ba  lea     rdx, [rbp+1F0h+SystemInformation]; SystemInformation
0x1800a96be  lea     r8d, [r9+0Ch]; SystemInformationLength
0x1800a96c2  lea     ecx, [r9+1]; SystemInformationClass
0x1800a96c6  call    cs:__imp_ZwQuerySystemInformation
0x1800a96cc  test    eax, eax
0x1800a96ce  jns     short loc_1800A96F4
0x1800a96d0  lea     r9, aFailedToGetPro; "Failed to get processor architecture [%"...
0x1800a96d7  mov     [rsp+2F0h+var_2D0], eax
0x1800a96db  mov     r8d, 625h
0x1800a96e1  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x1800a96e8  mov     ecx, 1
0x1800a96ed  call    AslLogCallPrintf
0x1800a96f2  jmp     short loc_1800A9763
0x1800a96f4  cmp     word ptr [rbp+1F0h+SystemInformation], 9
0x1800a96f9  jz      short loc_1800A9702
0x1800a96fb  mov     edi, 1
0x1800a9700  jmp     short loc_1800A9763
0x1800a9702  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x1800a9707  mov     edx, 20219h; DesiredAccess
0x1800a970c  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x1800a9711  call    cs:__imp_ZwOpenKey
0x1800a9717  test    eax, eax
0x1800a9719  js      short loc_1800A96FB
0x1800a971b  mov     rax, [rbp+1F0h+arg_38]
0x1800a9722  mov     r9, r12
0x1800a9725  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x1800a972a  mov     r8d, r14d
0x1800a972d  mov     [rsp+2F0h+var_2B0], rsi; __int64
0x1800a9732  mov     rdx, r15; String1
0x1800a9735  mov     [rsp+2F0h+Size], rax; Size
0x1800a973a  mov     rax, [rbp+1F0h+arg_30]
0x1800a9741  mov     [rsp+2F0h+Buf1], rax; Buf1
0x1800a9746  mov     rax, [rbp+1F0h+arg_28]
0x1800a974d  mov     [rsp+2F0h+var_2C8], rax; __int64
0x1800a9752  mov     eax, [rbp+1F0h+arg_20]
0x1800a9758  mov     [rsp+2F0h+var_2D0], eax; int
0x1800a975c  call    SdbpCheckMatchingRegistryValue
0x1800a9761  mov     edi, eax
0x1800a9763  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x1800a9768  test    rcx, rcx
0x1800a976b  jz      short loc_1800A9773
0x1800a976d  call    cs:__imp_ZwClose
0x1800a9773  mov     eax, edi
0x1800a9775  mov     rcx, [rbp+1F0h+var_30]
0x1800a977c  xor     rcx, rsp; StackCookie
0x1800a977f  call    __security_check_cookie
0x1800a9784  mov     rsi, [rsp+2F0h+arg_10]
0x1800a978c  add     rsp, 2D0h
0x1800a9793  pop     r15
0x1800a9795  pop     r14
0x1800a9797  pop     r12
0x1800a9799  pop     rdi
0x1800a979a  pop     rbp
0x1800a979b  retn
```
