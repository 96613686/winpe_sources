# CmRegUtilOpenExistingWstrKey

- ea: `0x140018bf0`
- end: `0x140018c75`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400183b8`
- `0x140018734`

## callees

- `0x140007e0c`
- `0x140018bf0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140018c4f`
- `ntoskrnl!ZwOpenKey` at `0x140018c4f`

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
0x140018bf0  mov     [rsp-8+arg_0], rbx
0x140018bf5  push    rbp
0x140018bf6  mov     rbp, rsp
0x140018bf9  sub     rsp, 70h
0x140018bfd  mov     r11, rcx
0x140018c00  xorps   xmm0, xmm0
0x140018c03  lea     rcx, [rbp+DestinationString]; DestinationString
0x140018c07  mov     rbx, r9
0x140018c0a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140018c0e  mov     r10d, r8d
0x140018c11  call    WdmlibRtlInitUnicodeStringEx
0x140018c16  test    eax, eax
0x140018c18  js      short loc_140018C66
0x140018c1a  xor     eax, eax
0x140018c1c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140018c24  mov     [rbp+KeyHandle], rax
0x140018c28  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140018c2c  mov     [rbx], rax
0x140018c2f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140018c33  lea     rax, [rbp+DestinationString]
0x140018c37  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140018c3f  mov     edx, r10d; DesiredAccess
0x140018c42  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140018c46  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x140018c4a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140018c4f  call    cs:__imp_ZwOpenKey
0x140018c56  nop     dword ptr [rax+rax+00h]
0x140018c5b  test    eax, eax
0x140018c5d  js      short loc_140018C66
0x140018c5f  mov     rcx, [rbp+KeyHandle]
0x140018c63  mov     [rbx], rcx
0x140018c66  mov     rbx, [rsp+70h+arg_0]
0x140018c6e  add     rsp, 70h
0x140018c72  pop     rbp
0x140018c73  retn
```
