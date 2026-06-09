# CmRegUtilOpenExistingWstrKey

- ea: `0x14000a628`
- end: `0x14000a6ad`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140009db8`
- `0x14000a134`

## callees

- `0x140002350`
- `0x14000a628`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14000a687`
- `ntoskrnl!ZwOpenKey` at `0x14000a687`

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
0x14000a628  mov     [rsp-8+arg_0], rbx
0x14000a62d  push    rbp
0x14000a62e  mov     rbp, rsp
0x14000a631  sub     rsp, 70h
0x14000a635  mov     r11, rcx
0x14000a638  xorps   xmm0, xmm0
0x14000a63b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a63f  mov     rbx, r9
0x14000a642  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000a646  mov     r10d, r8d
0x14000a649  call    WdmlibRtlInitUnicodeStringEx
0x14000a64e  test    eax, eax
0x14000a650  js      short loc_14000A69E
0x14000a652  xor     eax, eax
0x14000a654  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000a65c  mov     [rbp+KeyHandle], rax
0x14000a660  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000a664  mov     [rbx], rax
0x14000a667  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000a66b  lea     rax, [rbp+DestinationString]
0x14000a66f  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000a677  mov     edx, r10d; DesiredAccess
0x14000a67a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000a67e  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x14000a682  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a687  call    cs:__imp_ZwOpenKey
0x14000a68e  nop     dword ptr [rax+rax+00h]
0x14000a693  test    eax, eax
0x14000a695  js      short loc_14000A69E
0x14000a697  mov     rcx, [rbp+KeyHandle]
0x14000a69b  mov     [rbx], rcx
0x14000a69e  mov     rbx, [rsp+70h+arg_0]
0x14000a6a6  add     rsp, 70h
0x14000a6aa  pop     rbp
0x14000a6ab  retn
```
