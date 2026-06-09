# ReadSmbDeviceInfo

- ea: `0x14004b384`
- end: `0x14004b484`
- name: `ReadSmbDeviceInfo`
- size: `256`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400493c4`

## callees

- `0x14004b260`
- `0x14004b384`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004b476`
- `ntoskrnl!ZwClose` at `0x14004b476`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004b3c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004b3c1`
- `ntoskrnl!ZwOpenKey` at `0x14004b3fc`
- `ntoskrnl!ZwOpenKey` at `0x14004b3fc`

## pseudocode

```c
__int64 __fastcall ReadSmbDeviceInfo(void *a1)
{
  NTSTATUS v2; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"Parameters\\Smb");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    LOWORD(dword_14003969C) = NbtReadSingleParameter(KeyHandle);
    HIWORD(dword_14003969C) = NbtReadSingleParameter(KeyHandle);
    ZwClose(KeyHandle);
  }
  else
  {
    dword_14003969C = 29163965;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14004b384  mov     [rsp-8+arg_8], rbx
0x14004b389  mov     [rsp-8+arg_10], rdi
0x14004b38e  push    rbp
0x14004b38f  mov     rbp, rsp
0x14004b392  sub     rsp, 60h
0x14004b396  xorps   xmm0, xmm0
0x14004b399  mov     [rbp+KeyHandle], 0
0x14004b3a1  mov     rbx, rcx
0x14004b3a4  lea     rdx, aParametersSmb; "Parameters\\Smb"
0x14004b3ab  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14004b3af  xor     eax, eax
0x14004b3b1  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004b3b5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14004b3b9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004b3bd  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14004b3c1  call    cs:__imp_RtlInitUnicodeString
0x14004b3c8  nop     dword ptr [rax+rax+00h]
0x14004b3cd  lea     rax, [rbp+DestinationString]
0x14004b3d1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14004b3d8  xorps   xmm0, xmm0
0x14004b3db  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14004b3df  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14004b3e3  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x14004b3e7  mov     edx, 20019h; DesiredAccess
0x14004b3ec  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14004b3f3  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14004b3f7  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14004b3fc  call    cs:__imp_ZwOpenKey
0x14004b403  nop     dword ptr [rax+rax+00h]
0x14004b408  mov     edi, eax
0x14004b40a  test    eax, eax
0x14004b40c  jns     short loc_14004B42D
0x14004b40e  mov     cs:dword_14003969C, 1BD01BDh
0x14004b418  lea     r11, [rsp+60h+var_s0]
0x14004b41d  mov     eax, edi
0x14004b41f  mov     rbx, [r11+18h]
0x14004b423  mov     rdi, [r11+20h]
0x14004b427  mov     rsp, r11
0x14004b42a  pop     rbp
0x14004b42b  retn
0x14004b42d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14004b431  lea     rdx, aSessionport; "SessionPort"
0x14004b438  mov     ebx, 1BDh
0x14004b43d  mov     r9d, 1
0x14004b443  mov     r8d, ebx
0x14004b446  call    NbtReadSingleParameter
0x14004b44b  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14004b44f  lea     rdx, aDatagramport; "DatagramPort"
0x14004b456  mov     r9d, 1
0x14004b45c  mov     word ptr cs:dword_14003969C, ax
0x14004b463  mov     r8d, ebx
0x14004b466  call    NbtReadSingleParameter
0x14004b46b  mov     rcx, [rbp+KeyHandle]; Handle
0x14004b46f  mov     word ptr cs:dword_14003969C+2, ax
0x14004b476  call    cs:__imp_ZwClose
0x14004b47d  nop     dword ptr [rax+rax+00h]
0x14004b482  jmp     short loc_14004B418
```
