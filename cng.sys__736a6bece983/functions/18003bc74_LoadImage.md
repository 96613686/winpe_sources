# _LoadImage

- ea: `0x18003bc74`
- end: `0x18003be44`
- name: `_LoadImage`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18003af6c`

## callees

- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x18003bc74`
- `0x18003be4c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18003bcc5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bcc5`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18003bde3`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18003bde3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18003bd1d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18003bd1d`
- `ntoskrnl!ZwLoadDriver` at `0x18003bdab`
- `ntoskrnl!ZwLoadDriver` at `0x18003bdab`

## string_xrefs

- `0x18003bd81`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003bdfb`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall LoadImage(__int64 a1, __int64 a2)
{
  PCWSTR *v3; // rdx
  int v4; // ebx
  int v5; // edx
  NTSTATUS DeviceObjectPointer; // eax
  __int64 v7; // r9
  struct _UNICODE_STRING DriverServiceName; // [rsp+40h] [rbp+7h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+50h] [rbp+17h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp+27h] BYREF
  UNICODE_STRING String1; // [rsp+70h] [rbp+37h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+47h] BYREF

  *(_QWORD *)&String2.Length = 1048590;
  String2.Buffer = L"cng.sys";
  v3 = *(PCWSTR **)(a1 + 48);
  *(_QWORD *)&DriverServiceName.Length = 0;
  DriverServiceName.Buffer = 0;
  *(_QWORD *)&ObjectName.Length = 0;
  ObjectName.Buffer = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, *v3);
  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  if ( DestinationString.Length >= 0xEu )
  {
    String1.Length = String2.Length;
    String1.MaximumLength = String2.Length;
    String1.Buffer = &DestinationString.Buffer[(DestinationString.Length - (unsigned __int64)String2.Length) >> 1];
    if ( (DestinationString.Length <= String2.Length
       || DestinationString.Buffer[((DestinationString.Length - (unsigned __int64)String2.Length) >> 1) - 1] == 92)
      && !RtlCompareUnicodeString(&String1, &String2, 1u) )
    {
      *(_QWORD *)a2 = 0;
      v4 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      goto LABEL_17;
    }
  }
  v4 = ResolveDriverNamesFromImage((__int64)&DestinationString, (__int64)&DriverServiceName, (__int64)&ObjectName);
  if ( v4 >= 0 )
  {
    DeviceObjectPointer = ZwLoadDriver(&DriverServiceName);
    v4 = DeviceObjectPointer;
    if ( DeviceObjectPointer == -1073741554 || DeviceObjectPointer == -1073741771 || DeviceObjectPointer >= 0 )
    {
      DeviceObjectPointer = IoGetDeviceObjectPointer(&ObjectName, 1u, (PFILE_OBJECT *)a2, (PDEVICE_OBJECT *)(a2 + 8));
      v4 = DeviceObjectPointer;
      if ( DeviceObjectPointer >= 0 )
        goto LABEL_17;
      v7 = 1184;
    }
    else
    {
      v7 = 1167;
    }
    DebugTraceError(
      (unsigned int)DeviceObjectPointer,
      "sResult",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
      v7);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v5 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v5 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v5,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        (unsigned int)"sResult",
        v4,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        125);
  }
LABEL_17:
  if ( DriverServiceName.Buffer )
    MSCryptFree(DriverServiceName.Buffer);
  if ( ObjectName.Buffer )
    MSCryptFree(ObjectName.Buffer);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003bc74  mov     [rsp-8+arg_0], rbx
0x18003bc79  mov     [rsp-8+arg_8], rdi
0x18003bc7e  push    rbp
0x18003bc7f  lea     rbp, [rsp-57h]
0x18003bc84  sub     rsp, 90h
0x18003bc8b  lea     rax, aCngSys; "cng.sys"
0x18003bc92  mov     qword ptr [rbp+57h+String2.Length], 10000Eh
0x18003bc9a  mov     rdi, rdx
0x18003bc9d  mov     [rbp+57h+String2.Buffer], rax
0x18003bca1  mov     rdx, [rcx+30h]
0x18003bca5  xor     eax, eax
0x18003bca7  xorps   xmm0, xmm0
0x18003bcaa  mov     qword ptr [rbp+57h+DriverServiceName.Length], rax
0x18003bcae  mov     [rbp+57h+DriverServiceName.Buffer], rax
0x18003bcb2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003bcb6  mov     qword ptr [rbp+57h+ObjectName.Length], rax
0x18003bcba  mov     [rbp+57h+ObjectName.Buffer], rax
0x18003bcbe  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003bcc2  mov     rdx, [rdx]; SourceString
0x18003bcc5  call    cs:__imp_RtlInitUnicodeString
0x18003bccc  nop     dword ptr [rax+rax+00h]
0x18003bcd1  movzx   r9d, [rbp+57h+DestinationString.Length]
0x18003bcd6  movzx   edx, [rbp+57h+String2.Length]
0x18003bcda  mov     dword ptr [rbp+57h+String1+4], 0
0x18003bce1  cmp     r9w, dx
0x18003bce5  jb      short loc_18003BD43
0x18003bce7  mov     rax, [rbp+57h+DestinationString.Buffer]
0x18003bceb  mov     ecx, r9d
0x18003bcee  sub     rcx, rdx
0x18003bcf1  mov     [rbp+57h+String1.Length], dx
0x18003bcf5  shr     rcx, 1
0x18003bcf8  mov     [rbp+57h+String1.MaximumLength], dx
0x18003bcfc  lea     r8, [rax+rcx*2]
0x18003bd00  mov     [rbp+57h+String1.Buffer], r8
0x18003bd04  cmp     r9w, dx
0x18003bd08  jbe     short loc_18003BD12
0x18003bd0a  cmp     word ptr [r8-2], 5Ch ; '\'
0x18003bd10  jnz     short loc_18003BD43
0x18003bd12  mov     r8b, 1; CaseInSensitive
0x18003bd15  lea     rdx, [rbp+57h+String2]; String2
0x18003bd19  lea     rcx, [rbp+57h+String1]; String1
0x18003bd1d  call    cs:__imp_RtlCompareUnicodeString
0x18003bd24  nop     dword ptr [rax+rax+00h]
0x18003bd29  test    eax, eax
0x18003bd2b  jnz     short loc_18003BD43
0x18003bd2d  mov     qword ptr [rdi], 0
0x18003bd34  xor     ebx, ebx
0x18003bd36  mov     qword ptr [rdi+8], 0
0x18003bd3e  jmp     loc_18003BE10
0x18003bd43  lea     r8, [rbp+57h+ObjectName]
0x18003bd47  lea     rdx, [rbp+57h+DriverServiceName]
0x18003bd4b  lea     rcx, [rbp+57h+DestinationString]
0x18003bd4f  call    _ResolveDriverNamesFromImage
0x18003bd54  mov     ebx, eax
0x18003bd56  test    eax, eax
0x18003bd58  jns     short loc_18003BDA7
0x18003bd5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bd61  lea     rax, WPP_GLOBAL_Control
0x18003bd68  cmp     rcx, rax
0x18003bd6b  jz      loc_18003BE10
0x18003bd71  mov     edx, [rcx+2Ch]
0x18003bd74  test    dl, 1
0x18003bd77  jz      loc_18003BE10
0x18003bd7d  mov     rcx, [rcx+18h]
0x18003bd81  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003bd88  mov     [rsp+90h+var_60], 47Dh
0x18003bd90  lea     r9, aSresult; "sResult"
0x18003bd97  mov     [rsp+90h+var_68], r8
0x18003bd9c  mov     [rsp+90h+var_70], ebx
0x18003bda0  call    WPP_SF_sDsd
0x18003bda5  jmp     short loc_18003BE10
0x18003bda7  lea     rcx, [rbp+57h+DriverServiceName]; DriverServiceName
0x18003bdab  call    cs:__imp_ZwLoadDriver
0x18003bdb2  nop     dword ptr [rax+rax+00h]
0x18003bdb7  mov     ebx, eax
0x18003bdb9  cmp     eax, 0C000010Eh
0x18003bdbe  jz      short loc_18003BDD3
0x18003bdc0  cmp     eax, 0C0000035h
0x18003bdc5  jz      short loc_18003BDD3
0x18003bdc7  test    eax, eax
0x18003bdc9  jns     short loc_18003BDD3
0x18003bdcb  mov     r9d, 48Fh
0x18003bdd1  jmp     short loc_18003BDFB
0x18003bdd3  lea     r9, [rdi+8]; DeviceObject
0x18003bdd7  mov     r8, rdi; FileObject
0x18003bdda  mov     edx, 1; DesiredAccess
0x18003bddf  lea     rcx, [rbp+57h+ObjectName]; ObjectName
0x18003bde3  call    cs:__imp_IoGetDeviceObjectPointer
0x18003bdea  nop     dword ptr [rax+rax+00h]
0x18003bdef  mov     ebx, eax
0x18003bdf1  test    eax, eax
0x18003bdf3  jns     short loc_18003BE10
0x18003bdf5  mov     r9d, 4A0h
0x18003bdfb  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003be02  mov     ecx, eax
0x18003be04  lea     rdx, aSresult; "sResult"
0x18003be0b  call    DebugTraceError
0x18003be10  mov     rcx, [rbp+57h+DriverServiceName.Buffer]; P
0x18003be14  test    rcx, rcx
0x18003be17  jz      short loc_18003BE1E
0x18003be19  call    MSCryptFree
0x18003be1e  mov     rcx, [rbp+57h+ObjectName.Buffer]; P
0x18003be22  test    rcx, rcx
0x18003be25  jz      short loc_18003BE2C
0x18003be27  call    MSCryptFree
0x18003be2c  lea     r11, [rsp+90h+var_s0]
0x18003be34  mov     eax, ebx
0x18003be36  mov     rbx, [r11+10h]
0x18003be3a  mov     rdi, [r11+18h]
0x18003be3e  mov     rsp, r11
0x18003be41  pop     rbp
0x18003be42  retn
```
