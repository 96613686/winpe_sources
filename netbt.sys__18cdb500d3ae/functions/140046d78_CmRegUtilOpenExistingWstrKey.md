# CmRegUtilOpenExistingWstrKey

- ea: `0x140046d78`
- end: `0x140046dfd`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140046508`
- `0x140046884`

## callees

- `0x140030d6c`
- `0x140046d78`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140046dd7`
- `ntoskrnl!ZwOpenKey` at `0x140046dd7`

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
0x140046d78  mov     [rsp-8+arg_0], rbx
0x140046d7d  push    rbp
0x140046d7e  mov     rbp, rsp
0x140046d81  sub     rsp, 70h
0x140046d85  mov     r11, rcx
0x140046d88  xorps   xmm0, xmm0
0x140046d8b  lea     rcx, [rbp+DestinationString]; DestinationString
0x140046d8f  mov     rbx, r9
0x140046d92  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140046d96  mov     r10d, r8d
0x140046d99  call    WdmlibRtlInitUnicodeStringEx
0x140046d9e  test    eax, eax
0x140046da0  js      short loc_140046DEE
0x140046da2  xor     eax, eax
0x140046da4  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140046dac  mov     [rbp+KeyHandle], rax
0x140046db0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140046db4  mov     [rbx], rax
0x140046db7  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140046dbb  lea     rax, [rbp+DestinationString]
0x140046dbf  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140046dc7  mov     edx, r10d; DesiredAccess
0x140046dca  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140046dce  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x140046dd2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140046dd7  call    cs:__imp_ZwOpenKey
0x140046dde  nop     dword ptr [rax+rax+00h]
0x140046de3  test    eax, eax
0x140046de5  js      short loc_140046DEE
0x140046de7  mov     rcx, [rbp+KeyHandle]
0x140046deb  mov     [rbx], rcx
0x140046dee  mov     rbx, [rsp+70h+arg_0]
0x140046df6  add     rsp, 70h
0x140046dfa  pop     rbp
0x140046dfb  retn
```
