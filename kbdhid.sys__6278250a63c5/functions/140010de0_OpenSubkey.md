# OpenSubkey

- ea: `0x140010de0`
- end: `0x140010e25`
- name: `OpenSubkey`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140004f80`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140010e13`
- `ntoskrnl!ZwOpenKey` at `0x140010e13`

## pseudocode

```c
NTSTATUS __fastcall OpenSubkey(void **a1, void *a2, struct _UNICODE_STRING *a3)
{
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-38h] BYREF

  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.ObjectName = a3;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  return ZwOpenKey(a1, 0x20019u, &ObjectAttributes);
}

```

## disassembly

```asm
0x140010de0  sub     rsp, 58h
0x140010de4  mov     [rsp+58h+ObjectAttributes.RootDirectory], rdx
0x140010de9  xorps   xmm0, xmm0
0x140010dec  mov     [rsp+58h+ObjectAttributes.ObjectName], r8
0x140010df1  mov     edx, 20019h; DesiredAccess
0x140010df6  lea     r8, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x140010dfb  mov     qword ptr [rsp+58h+ObjectAttributes.Length], 30h ; '0'
0x140010e04  movdqu  xmmword ptr [rsp+58h+ObjectAttributes.SecurityDescriptor], xmm0
0x140010e0a  mov     qword ptr [rsp+58h+ObjectAttributes.Attributes], 240h
0x140010e13  call    cs:__imp_ZwOpenKey
0x140010e1a  nop     dword ptr [rax+rax+00h]
0x140010e1f  add     rsp, 58h
0x140010e23  retn
```
