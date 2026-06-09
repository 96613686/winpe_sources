# BapdpRegisterFwUpdateResults

- ea: `0x140c879d8`
- end: `0x140c87bf0`
- name: `BapdpRegisterFwUpdateResults`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140c86e68`

## callees

- `0x140403380`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd780`
- `0x1406ddfe0`
- `0x1409230b0`
- `0x14094b120`
- `0x140c879d8`

## string_xrefs

- `0x140c87b33`: `LastAttemptVersion`
- `0x140c87b6a`: `LastAttemptStatus`
- `0x140c87a4a`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\FirmwareResources`

## pseudocode

```c
void __fastcall BapdpRegisterFwUpdateResults(_QWORD *a1, unsigned int a2)
{
  unsigned int v3; // r14d
  const GUID *v4; // rsi
  NTSTATUS v5; // ebx
  HANDLE v6; // rcx
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  UNICODE_STRING GuidString; // [rsp+50h] [rbp-9h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  ULONG Disposition; // [rsp+C0h] [rbp+67h] BYREF
  HANDLE Handle; // [rsp+D0h] [rbp+77h] BYREF
  HANDLE KeyHandle; // [rsp+D8h] [rbp+7Fh] BYREF

  Disposition = 0;
  KeyHandle = 0;
  Handle = 0;
  GuidString = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( a1 && a2 && *a1 && a2 >= (unsigned __int64)(24LL * *a1 + 8) )
  {
    RtlInitUnicodeString(
      &DestinationString,
      L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\FirmwareResources");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    {
      v3 = 0;
      v4 = (const GUID *)(a1 + 1);
      if ( *a1 )
      {
        while ( RtlStringFromGUID(v4, &GuidString) >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, GuidString.Buffer);
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v5 = ZwCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
          RtlFreeAnsiString(&GuidString);
          if ( v5 < 0 )
            break;
          RtlInitUnicodeString(&DestinationString, L"LastAttemptVersion");
          ZwSetValueKey(Handle, &DestinationString, 0, 4u, (PVOID)&v4[1], 4u);
          RtlInitUnicodeString(&DestinationString, L"LastAttemptStatus");
          ZwSetValueKey(Handle, &DestinationString, 0, 4u, &v4[1].Data2, 4u);
          ZwClose(Handle);
          ++v3;
          v6 = 0;
          v4 = (const GUID *)((char *)v4 + 24);
          Handle = 0;
          if ( (unsigned __int64)v3 >= *a1 )
            goto LABEL_12;
        }
      }
    }
    v6 = Handle;
LABEL_12:
    if ( v6 )
      ZwClose(v6);
    if ( KeyHandle )
      ZwClose(KeyHandle);
  }
}

```

## disassembly

```asm
0x140c879d8  push    rbp
0x140c879da  push    rbx
0x140c879db  push    rsi
0x140c879dc  push    rdi
0x140c879dd  push    r14
0x140c879df  lea     rbp, [rsp-37h]
0x140c879e4  sub     rsp, 90h
0x140c879eb  xorps   xmm0, xmm0
0x140c879ee  mov     [rbp+57h+arg_0], 0
0x140c879f5  xor     eax, eax
0x140c879f7  mov     rdi, rcx
0x140c879fa  mov     [rbp+57h+KeyHandle], rax
0x140c879fe  mov     [rbp+57h+Handle], rax
0x140c87a02  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140c87a06  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140c87a0a  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x140c87a0e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140c87a12  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140c87a16  test    rcx, rcx
0x140c87a19  jz      loc_140C87BE1
0x140c87a1f  test    edx, edx
0x140c87a21  jz      loc_140C87BE1
0x140c87a27  mov     rax, [rcx]
0x140c87a2a  test    rax, rax
0x140c87a2d  jz      loc_140C87BE1
0x140c87a33  lea     rax, [rax+rax*2]
0x140c87a37  lea     rcx, ds:8[rax*8]
0x140c87a3f  mov     eax, edx
0x140c87a41  cmp     rax, rcx
0x140c87a44  jb      loc_140C87BE1
0x140c87a4a  lea     rdx, aRegistryMachin_28; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x140c87a51  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140c87a55  call    RtlInitUnicodeString
0x140c87a5a  lea     rax, [rbp+57h+DestinationString]
0x140c87a5e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140c87a65  xorps   xmm0, xmm0
0x140c87a68  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140c87a6c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140c87a70  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140c87a78  mov     edx, 20019h; DesiredAccess
0x140c87a7d  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140c87a84  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140c87a88  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c87a8d  call    ZwOpenKey
0x140c87a92  test    eax, eax
0x140c87a94  js      loc_140C87BC5
0x140c87a9a  xor     r14d, r14d
0x140c87a9d  lea     rsi, [rdi+8]
0x140c87aa1  cmp     [rdi], r14
0x140c87aa4  jbe     loc_140C87BC5
0x140c87aaa  lea     rdx, [rbp+57h+GuidString]; GuidString
0x140c87aae  mov     rcx, rsi; Guid
0x140c87ab1  call    RtlStringFromGUID
0x140c87ab6  test    eax, eax
0x140c87ab8  js      loc_140C87BC5
0x140c87abe  mov     rdx, [rbp+57h+GuidString.Buffer]; SourceString
0x140c87ac2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140c87ac6  call    RtlInitUnicodeString
0x140c87acb  mov     rax, [rbp+57h+KeyHandle]
0x140c87acf  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140c87ad3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140c87ad7  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x140c87adb  lea     rax, [rbp+57h+DestinationString]
0x140c87adf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140c87ae6  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140c87aea  xorps   xmm0, xmm0
0x140c87aed  lea     rax, [rbp+57h+arg_0]
0x140c87af1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140c87af8  mov     [rsp+0B0h+Disposition], rax; Disposition
0x140c87afd  xor     r9d, r9d; TitleIndex
0x140c87b00  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x140c87b08  mov     edx, 20019h; DesiredAccess
0x140c87b0d  mov     [rsp+0B0h+Class], 0; Class
0x140c87b16  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c87b1b  call    ZwCreateKey
0x140c87b20  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x140c87b24  mov     ebx, eax
0x140c87b26  call    RtlFreeAnsiString
0x140c87b2b  test    ebx, ebx
0x140c87b2d  js      loc_140C87BC5
0x140c87b33  lea     rdx, aLastattemptver; "LastAttemptVersion"
0x140c87b3a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140c87b3e  call    RtlInitUnicodeString
0x140c87b43  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140c87b47  lea     rax, [rsi+10h]
0x140c87b4b  mov     [rsp+0B0h+CreateOptions], 4; DataSize
0x140c87b53  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140c87b57  mov     r9d, 4; Type
0x140c87b5d  mov     [rsp+0B0h+Class], rax; Data
0x140c87b62  xor     r8d, r8d; TitleIndex
0x140c87b65  call    ZwSetValueKey
0x140c87b6a  lea     rdx, aLastattemptsta; "LastAttemptStatus"
0x140c87b71  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140c87b75  call    RtlInitUnicodeString
0x140c87b7a  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140c87b7e  lea     rax, [rsi+14h]
0x140c87b82  mov     [rsp+0B0h+CreateOptions], 4; DataSize
0x140c87b8a  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140c87b8e  mov     r9d, 4; Type
0x140c87b94  mov     [rsp+0B0h+Class], rax; Data
0x140c87b99  xor     r8d, r8d; TitleIndex
0x140c87b9c  call    ZwSetValueKey
0x140c87ba1  mov     rcx, [rbp+57h+Handle]; Handle
0x140c87ba5  call    ZwClose
0x140c87baa  inc     r14d
0x140c87bad  xor     ecx, ecx
0x140c87baf  mov     eax, r14d
0x140c87bb2  add     rsi, 18h
0x140c87bb6  mov     [rbp+57h+Handle], rcx
0x140c87bba  cmp     rax, [rdi]
0x140c87bbd  jb      loc_140C87AAA
0x140c87bc3  jmp     short loc_140C87BC9
0x140c87bc5  mov     rcx, [rbp+57h+Handle]; Handle
0x140c87bc9  test    rcx, rcx
0x140c87bcc  jz      short loc_140C87BD3
0x140c87bce  call    ZwClose
0x140c87bd3  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140c87bd7  test    rcx, rcx
0x140c87bda  jz      short loc_140C87BE1
0x140c87bdc  call    ZwClose
0x140c87be1  add     rsp, 90h
0x140c87be8  pop     r14
0x140c87bea  pop     rdi
0x140c87beb  pop     rsi
0x140c87bec  pop     rbx
0x140c87bed  pop     rbp
0x140c87bee  retn
```
