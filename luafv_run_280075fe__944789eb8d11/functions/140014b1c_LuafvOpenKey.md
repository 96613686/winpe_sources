# LuafvOpenKey

- ea: `0x140014b1c`
- end: `0x140014b65`
- name: `LuafvOpenKey`
- size: `73`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140028364`
- `0x140028714`
- `0x140028ac8`
- `0x140028d54`
- `0x140029784`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140014b53`
- `ntoskrnl!ZwOpenKey` at `0x140014b53`

## pseudocode

```c
NTSTATUS __fastcall LuafvOpenKey(void *a1, struct _UNICODE_STRING *a2, void **a3)
{
  struct _OBJECT_ATTRIBUTES v4; // [rsp+20h] [rbp-38h] BYREF

  v4.RootDirectory = a1;
  v4.ObjectName = a2;
  *(_QWORD *)&v4.Length = 48;
  *(_QWORD *)&v4.Attributes = 576;
  *(_OWORD *)&v4.SecurityDescriptor = 0;
  return ZwOpenKey(a3, 0x20019u, &v4);
}

```

## disassembly

```asm
0x140014b1c  mov     r11, rsp
0x140014b1f  sub     rsp, 58h
0x140014b23  mov     rax, r8
0x140014b26  mov     [r11-30h], rcx
0x140014b2a  mov     [r11-28h], rdx
0x140014b2e  lea     r8, [r11-38h]; ObjectAttributes
0x140014b32  xorps   xmm0, xmm0
0x140014b35  mov     qword ptr [r11-38h], 30h ; '0'
0x140014b3d  mov     qword ptr [r11-20h], 240h
0x140014b45  mov     rcx, rax; KeyHandle
0x140014b48  mov     edx, 20019h; DesiredAccess
0x140014b4d  movdqu  [rsp+58h+var_18], xmm0
0x140014b53  call    cs:__imp_ZwOpenKey
0x140014b5a  nop     dword ptr [rax+rax+00h]
0x140014b5f  add     rsp, 58h
0x140014b63  retn
```
