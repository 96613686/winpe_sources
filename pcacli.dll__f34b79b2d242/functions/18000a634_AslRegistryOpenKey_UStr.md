# AslRegistryOpenKey_UStr

- ea: `0x18000a634`
- end: `0x18000a676`
- name: `AslRegistryOpenKey_UStr`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a5b8`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18000a66b`
- `ntdll!ZwOpenKey` at `0x18000a66b`

## pseudocode

```c
NTSTATUS __fastcall AslRegistryOpenKey_UStr(void **a1, struct _UNICODE_STRING *a2, ACCESS_MASK a3)
{
  struct _OBJECT_ATTRIBUTES v4; // [rsp+20h] [rbp-38h] BYREF

  v4.ObjectName = a2;
  *(_QWORD *)&v4.Length = 48;
  v4.RootDirectory = 0;
  *a1 = 0;
  *(_QWORD *)&v4.Attributes = 64;
  *(_OWORD *)&v4.SecurityDescriptor = 0;
  return ZwOpenKey(a1, a3, &v4);
}

```

## disassembly

```asm
0x18000a634  mov     r11, rsp
0x18000a637  sub     rsp, 58h
0x18000a63b  mov     eax, r8d
0x18000a63e  mov     [r11-28h], rdx
0x18000a642  xor     r8d, r8d
0x18000a645  mov     qword ptr [r11-38h], 30h ; '0'
0x18000a64d  mov     [r11-30h], r8
0x18000a651  xorps   xmm0, xmm0
0x18000a654  mov     [rcx], r8
0x18000a657  mov     edx, eax; DesiredAccess
0x18000a659  mov     qword ptr [r11-20h], 40h ; '@'
0x18000a661  lea     r8, [r11-38h]; ObjectAttributes
0x18000a665  movdqu  [rsp+58h+var_18], xmm0
0x18000a66b  call    cs:__imp_ZwOpenKey
0x18000a671  add     rsp, 58h
0x18000a675  retn
```
