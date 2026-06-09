# BthOpenKey

- ea: `0x1400340cc`
- end: `0x140034111`
- name: `BthOpenKey`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000916c`

## callees

- `0x140034118`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400340e9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400340e9`

## pseudocode

```c
NTSTATUS __fastcall BthOpenKey(void *a1, const WCHAR *a2, void **a3)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  return BthOpenKeyEx(a1, &DestinationString, a3);
}

```

## disassembly

```asm
0x1400340cc  mov     [rsp+arg_0], rbx
0x1400340d1  push    rdi
0x1400340d2  sub     rsp, 30h
0x1400340d6  mov     rdi, rcx
0x1400340d9  xorps   xmm0, xmm0
0x1400340dc  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400340e1  mov     rbx, r8
0x1400340e4  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400340e9  call    cs:__imp_RtlInitUnicodeString
0x1400340f0  nop     dword ptr [rax+rax+00h]
0x1400340f5  mov     r8, rbx
0x1400340f8  lea     rdx, [rsp+38h+DestinationString]
0x1400340fd  mov     rcx, rdi
0x140034100  call    BthOpenKeyEx
0x140034105  mov     rbx, [rsp+38h+arg_0]
0x14003410a  add     rsp, 30h
0x14003410e  pop     rdi
0x14003410f  retn
```
