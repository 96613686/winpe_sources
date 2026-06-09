# TlsCloseRegKey

- ea: `0x14000c7f0`
- end: `0x14000c81b`
- name: `TlsCloseRegKey`
- size: `43`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bff0`
- `0x14000ca84`
- `0x14000ce40`
- `0x14000d200`
- `0x14000d5d8`

## callees

- `0x14000c7f0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000c801`
- `ntoskrnl!ZwClose` at `0x14000c801`

## pseudocode

```c
NTSTATUS __fastcall TlsCloseRegKey(void **a1)
{
  void *v2; // rcx
  NTSTATUS result; // eax

  v2 = *a1;
  if ( v2 )
  {
    result = ZwClose(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000c7f0  push    rbx
0x14000c7f2  sub     rsp, 20h
0x14000c7f6  mov     rbx, rcx
0x14000c7f9  mov     rcx, [rcx]; Handle
0x14000c7fc  test    rcx, rcx
0x14000c7ff  jz      short loc_14000C814
0x14000c801  call    cs:__imp_ZwClose
0x14000c808  nop     dword ptr [rax+rax+00h]
0x14000c80d  mov     qword ptr [rbx], 0
0x14000c814  add     rsp, 20h
0x14000c818  pop     rbx
0x14000c819  retn
```
