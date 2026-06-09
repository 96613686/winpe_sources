# OpenAndReadElement

- ea: `0x140048db4`
- end: `0x140048e4a`
- name: `OpenAndReadElement`
- size: `150`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, __int64, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140048958`

## callees

- `0x140048db4`
- `0x1400491a0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140048e29`
- `ntoskrnl!ZwClose` at `0x140048e29`
- `ntoskrnl!ZwOpenKey` at `0x140048e00`
- `ntoskrnl!ZwOpenKey` at `0x140048e00`

## string_xrefs

- `0x140048e14`: `DataBasePath`

## pseudocode

```c
__int64 __fastcall OpenAndReadElement(struct _UNICODE_STRING *a1, __int64 a2, struct _UNICODE_STRING *a3)
{
  unsigned int Element; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+68h] [rbp+18h] BYREF

  ObjectAttributes.ObjectName = a1;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    return 3221225473LL;
  Element = ReadElement(KeyHandle, L"DataBasePath", a3);
  ZwClose(KeyHandle);
  return Element;
}

```

## disassembly

```asm
0x140048db4  mov     [rsp-8+arg_0], rbx
0x140048db9  mov     [rsp-8+KeyHandle], rdx
0x140048dbe  push    rbp
0x140048dbf  mov     rbp, rsp
0x140048dc2  sub     rsp, 50h
0x140048dc6  mov     rbx, r8
0x140048dc9  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140048dcd  xor     eax, eax
0x140048dcf  mov     [rbp+KeyHandle], 0
0x140048dd7  xorps   xmm0, xmm0
0x140048dda  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140048dde  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140048de2  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140048dea  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140048dee  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140048df6  mov     edx, 20019h; DesiredAccess
0x140048dfb  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140048e00  call    cs:__imp_ZwOpenKey
0x140048e07  nop     dword ptr [rax+rax+00h]
0x140048e0c  test    eax, eax
0x140048e0e  js      short loc_140048E43
0x140048e10  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140048e14  lea     rdx, aDatabasepath; "DataBasePath"
0x140048e1b  mov     r8, rbx; ValueName
0x140048e1e  call    ReadElement
0x140048e23  mov     rcx, [rbp+KeyHandle]; Handle
0x140048e27  mov     ebx, eax
0x140048e29  call    cs:__imp_ZwClose
0x140048e30  nop     dword ptr [rax+rax+00h]
0x140048e35  mov     eax, ebx
0x140048e37  mov     rbx, [rsp+50h+arg_0]
0x140048e3c  add     rsp, 50h
0x140048e40  pop     rbp
0x140048e41  retn
0x140048e43  mov     eax, 0C0000001h
0x140048e48  jmp     short loc_140048E37
```
