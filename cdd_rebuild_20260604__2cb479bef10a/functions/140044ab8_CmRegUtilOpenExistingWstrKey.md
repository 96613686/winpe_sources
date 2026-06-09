# CmRegUtilOpenExistingWstrKey

- ea: `0x140044ab8`
- end: `0x140044b3d`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140044248`
- `0x1400445c4`

## callees

- `0x14003707c`
- `0x140044ab8`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140044b17`
- `ntoskrnl!ZwOpenKey` at `0x140044b17`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilOpenExistingWstrKey(__int64 a1, const WCHAR *a2, __int64 a3, void **a4)
{
  NTSTATUS result; // eax
  ACCESS_MASK v6; // r10d
  void *v7; // r11
  void *KeyHandle; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF

  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    KeyHandle = 0;
    *a4 = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = v7;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&KeyHandle, v6, &ObjectAttributes);
    if ( result >= 0 )
      *a4 = KeyHandle;
  }
  return result;
}

```

## disassembly

```asm
0x140044ab8  mov     [rsp-8+arg_0], rbx
0x140044abd  push    rbp
0x140044abe  mov     rbp, rsp
0x140044ac1  sub     rsp, 70h
0x140044ac5  mov     r11, rcx
0x140044ac8  xorps   xmm0, xmm0
0x140044acb  lea     rcx, [rbp+DestinationString]; DestinationString
0x140044acf  mov     rbx, r9
0x140044ad2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140044ad6  mov     r10d, r8d
0x140044ad9  call    WdmlibRtlInitUnicodeStringEx
0x140044ade  test    eax, eax
0x140044ae0  js      short loc_140044B2E
0x140044ae2  xor     eax, eax
0x140044ae4  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140044aec  mov     [rbp+KeyHandle], rax
0x140044af0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140044af4  mov     [rbx], rax
0x140044af7  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140044afb  lea     rax, [rbp+DestinationString]
0x140044aff  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140044b07  mov     edx, r10d; DesiredAccess
0x140044b0a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140044b0e  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x140044b12  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140044b17  call    cs:__imp_ZwOpenKey
0x140044b1e  nop     dword ptr [rax+rax+00h]
0x140044b23  test    eax, eax
0x140044b25  js      short loc_140044B2E
0x140044b27  mov     rcx, [rbp+KeyHandle]
0x140044b2b  mov     [rbx], rcx
0x140044b2e  mov     rbx, [rsp+70h+arg_0]
0x140044b36  add     rsp, 70h
0x140044b3a  pop     rbp
0x140044b3b  retn
```
