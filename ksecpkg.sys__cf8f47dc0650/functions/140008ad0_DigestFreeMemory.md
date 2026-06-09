# DigestFreeMemory

- ea: `0x140008ad0`
- end: `0x140008aed`
- name: `DigestFreeMemory`
- size: `29`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140008810`
- `0x1400095a0`
- `0x140009e7c`
- `0x140021590`
- `0x140028600`

## callees

- `0x140008ad0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008adb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008adb`

## pseudocode

```c
void __fastcall DigestFreeMemory(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x140008ad0  sub     rsp, 28h
0x140008ad4  test    rcx, rcx
0x140008ad7  jz      short loc_140008AE7
0x140008ad9  xor     edx, edx; Tag
0x140008adb  call    cs:__imp_ExFreePoolWithTag
0x140008ae2  nop     dword ptr [rax+rax+00h]
0x140008ae7  add     rsp, 28h
0x140008aeb  retn
```
