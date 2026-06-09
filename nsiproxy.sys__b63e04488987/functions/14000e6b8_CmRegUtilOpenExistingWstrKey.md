# CmRegUtilOpenExistingWstrKey

- ea: `0x14000e6b8`
- end: `0x14000e73d`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000de48`
- `0x14000e1c4`

## callees

- `0x140006430`
- `0x14000e6b8`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14000e717`
- `ntoskrnl!ZwOpenKey` at `0x14000e717`

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
0x14000e6b8  mov     [rsp-8+arg_0], rbx
0x14000e6bd  push    rbp
0x14000e6be  mov     rbp, rsp
0x14000e6c1  sub     rsp, 70h
0x14000e6c5  mov     r11, rcx
0x14000e6c8  xorps   xmm0, xmm0
0x14000e6cb  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e6cf  mov     rbx, r9
0x14000e6d2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e6d6  mov     r10d, r8d
0x14000e6d9  call    WdmlibRtlInitUnicodeStringEx
0x14000e6de  test    eax, eax
0x14000e6e0  js      short loc_14000E72E
0x14000e6e2  xor     eax, eax
0x14000e6e4  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000e6ec  mov     [rbp+KeyHandle], rax
0x14000e6f0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000e6f4  mov     [rbx], rax
0x14000e6f7  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e6fb  lea     rax, [rbp+DestinationString]
0x14000e6ff  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000e707  mov     edx, r10d; DesiredAccess
0x14000e70a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000e70e  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x14000e712  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e717  call    cs:__imp_ZwOpenKey
0x14000e71e  nop     dword ptr [rax+rax+00h]
0x14000e723  test    eax, eax
0x14000e725  js      short loc_14000E72E
0x14000e727  mov     rcx, [rbp+KeyHandle]
0x14000e72b  mov     [rbx], rcx
0x14000e72e  mov     rbx, [rsp+70h+arg_0]
0x14000e736  add     rsp, 70h
0x14000e73a  pop     rbp
0x14000e73b  retn
```
