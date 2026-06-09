# PerflibciOpenKey

- ea: `0x18000d9c4`
- end: `0x18000da50`
- name: `PerflibciOpenKey`
- size: `140`
- prototype: `ULONG __fastcall(void *, const WCHAR *, ACCESS_MASK, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006bc0`
- `0x18000cc70`
- `0x18000d158`

## callees

- `0x18000d9c4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000da3a`
- `ntdll!RtlNtStatusToDosError` at `0x18000da3a`
- `ntdll!NtOpenKey` at `0x18000da32`
- `ntdll!NtOpenKey` at `0x18000da32`
- `ntdll!RtlInitUnicodeString` at `0x18000da01`
- `ntdll!RtlInitUnicodeString` at `0x18000da01`

## pseudocode

```c
ULONG __fastcall PerflibciOpenKey(void *a1, const WCHAR *a2, ACCESS_MASK a3, void **a4)
{
  NTSTATUS v7; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF

  if ( !a4 || !a2 )
    return 87;
  *a4 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenKey(a4, a3, &ObjectAttributes);
  return RtlNtStatusToDosError(v7);
}

```

## disassembly

```asm
0x18000d9c4  push    rbp
0x18000d9c6  push    rbx
0x18000d9c7  push    rsi
0x18000d9c8  push    rdi
0x18000d9c9  mov     rbp, rsp
0x18000d9cc  sub     rsp, 68h
0x18000d9d0  mov     rbx, r9
0x18000d9d3  mov     edi, r8d
0x18000d9d6  mov     rsi, rcx
0x18000d9d9  test    r9, r9
0x18000d9dc  jz      short loc_18000DA42
0x18000d9de  test    rdx, rdx
0x18000d9e1  jz      short loc_18000DA42
0x18000d9e3  xorps   xmm0, xmm0
0x18000d9e6  mov     qword ptr [r9], 0
0x18000d9ed  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000d9f1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000d9f5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000d9f9  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d9fd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000da01  call    cs:__imp_RtlInitUnicodeString
0x18000da07  lea     rax, [rbp+DestinationString]
0x18000da0b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000da12  xorps   xmm0, xmm0
0x18000da15  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000da19  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000da1d  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18000da21  mov     edx, edi; DesiredAccess
0x18000da23  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000da2a  mov     rcx, rbx; KeyHandle
0x18000da2d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000da32  call    cs:__imp_NtOpenKey
0x18000da38  mov     ecx, eax; Status
0x18000da3a  call    cs:__imp_RtlNtStatusToDosError
0x18000da40  jmp     short loc_18000DA47
0x18000da42  mov     eax, 57h ; 'W'
0x18000da47  add     rsp, 68h
0x18000da4b  pop     rdi
0x18000da4c  pop     rsi
0x18000da4d  pop     rbx
0x18000da4e  pop     rbp
0x18000da4f  retn
```
