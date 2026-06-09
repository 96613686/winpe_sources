# CmRegUtilOpenExistingWstrKey

- ea: `0x140044110`
- end: `0x140044195`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400438d8`
- `0x140043c54`

## callees

- `0x14002811c`
- `0x140044110`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14004416f`
- `ntoskrnl!ZwOpenKey` at `0x14004416f`

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
0x140044110  mov     [rsp-8+arg_0], rbx
0x140044115  push    rbp
0x140044116  mov     rbp, rsp
0x140044119  sub     rsp, 70h
0x14004411d  mov     r11, rcx
0x140044120  xorps   xmm0, xmm0
0x140044123  lea     rcx, [rbp+DestinationString]; DestinationString
0x140044127  mov     rbx, r9
0x14004412a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004412e  mov     r10d, r8d
0x140044131  call    WdmlibRtlInitUnicodeStringEx
0x140044136  test    eax, eax
0x140044138  js      short loc_140044186
0x14004413a  xor     eax, eax
0x14004413c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140044144  mov     [rbp+KeyHandle], rax
0x140044148  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14004414c  mov     [rbx], rax
0x14004414f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140044153  lea     rax, [rbp+DestinationString]
0x140044157  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14004415f  mov     edx, r10d; DesiredAccess
0x140044162  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140044166  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x14004416a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14004416f  call    cs:__imp_ZwOpenKey
0x140044176  nop     dword ptr [rax+rax+00h]
0x14004417b  test    eax, eax
0x14004417d  js      short loc_140044186
0x14004417f  mov     rcx, [rbp+KeyHandle]
0x140044183  mov     [rbx], rcx
0x140044186  mov     rbx, [rsp+70h+arg_0]
0x14004418e  add     rsp, 70h
0x140044192  pop     rbp
0x140044193  retn
```
