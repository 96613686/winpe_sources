# BthOpenKeyEx

- ea: `0x140034118`
- end: `0x140034161`
- name: `BthOpenKeyEx`
- size: `73`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000916c`
- `0x14001f2f4`
- `0x1400340cc`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14003414f`
- `ntoskrnl!ZwOpenKey` at `0x14003414f`

## pseudocode

```c
NTSTATUS __fastcall BthOpenKeyEx(void *a1, struct _UNICODE_STRING *a2, void **a3)
{
  struct _OBJECT_ATTRIBUTES v4; // [rsp+20h] [rbp-38h] BYREF

  v4.RootDirectory = a1;
  v4.ObjectName = a2;
  *(_QWORD *)&v4.Length = 48;
  *(_QWORD *)&v4.Attributes = 576;
  *(_OWORD *)&v4.SecurityDescriptor = 0;
  return ZwOpenKey(a3, 0xF003Fu, &v4);
}

```

## disassembly

```asm
0x140034118  mov     r11, rsp
0x14003411b  sub     rsp, 58h
0x14003411f  mov     rax, r8
0x140034122  mov     [r11-30h], rcx
0x140034126  mov     [r11-28h], rdx
0x14003412a  lea     r8, [r11-38h]; ObjectAttributes
0x14003412e  xorps   xmm0, xmm0
0x140034131  mov     qword ptr [r11-38h], 30h ; '0'
0x140034139  mov     qword ptr [r11-20h], 240h
0x140034141  mov     rcx, rax; KeyHandle
0x140034144  mov     edx, 0F003Fh; DesiredAccess
0x140034149  movdqu  [rsp+58h+var_18], xmm0
0x14003414f  call    cs:__imp_ZwOpenKey
0x140034156  nop     dword ptr [rax+rax+00h]
0x14003415b  add     rsp, 58h
0x14003415f  retn
```
