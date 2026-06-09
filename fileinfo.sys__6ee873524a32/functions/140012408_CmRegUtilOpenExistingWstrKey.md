# CmRegUtilOpenExistingWstrKey

- ea: `0x140012408`
- end: `0x14001248d`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140011b98`
- `0x140011f14`

## callees

- `0x1400037b8`
- `0x140012408`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140012467`
- `ntoskrnl!ZwOpenKey` at `0x140012467`

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
0x140012408  mov     [rsp-8+arg_0], rbx
0x14001240d  push    rbp
0x14001240e  mov     rbp, rsp
0x140012411  sub     rsp, 70h
0x140012415  mov     r11, rcx
0x140012418  xorps   xmm0, xmm0
0x14001241b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001241f  mov     rbx, r9
0x140012422  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012426  mov     r10d, r8d
0x140012429  call    WdmlibRtlInitUnicodeStringEx
0x14001242e  test    eax, eax
0x140012430  js      short loc_14001247E
0x140012432  xor     eax, eax
0x140012434  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001243c  mov     [rbp+KeyHandle], rax
0x140012440  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012444  mov     [rbx], rax
0x140012447  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14001244b  lea     rax, [rbp+DestinationString]
0x14001244f  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140012457  mov     edx, r10d; DesiredAccess
0x14001245a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001245e  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x140012462  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140012467  call    cs:__imp_ZwOpenKey
0x14001246e  nop     dword ptr [rax+rax+00h]
0x140012473  test    eax, eax
0x140012475  js      short loc_14001247E
0x140012477  mov     rcx, [rbp+KeyHandle]
0x14001247b  mov     [rbx], rcx
0x14001247e  mov     rbx, [rsp+70h+arg_0]
0x140012486  add     rsp, 70h
0x14001248a  pop     rbp
0x14001248b  retn
```
