# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x180023b00`
- end: `0x180023b32`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `50`
- prototype: `int(CFileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!fread` at `0x180023b1b`
- `msvcrt!fread` at `0x180023b1b`

## pseudocode

```c
__int64 __fastcall CFileStream::Read(FILE **this, void *a2, unsigned int a3, unsigned int *a4)
{
  *a4 = fread(a2, 1u, a3, this[3]);
  return 0;
}

```

## disassembly

```asm
0x180023b00  push    rbx
0x180023b02  sub     rsp, 20h
0x180023b06  mov     rax, rdx
0x180023b09  mov     r8d, r8d; ElementCount
0x180023b0c  mov     rbx, r9
0x180023b0f  mov     edx, 1; ElementSize
0x180023b14  mov     r9, [rcx+18h]; Stream
0x180023b18  mov     rcx, rax; Buffer
0x180023b1b  call    cs:__imp_fread
0x180023b22  nop     dword ptr [rax+rax+00h]
0x180023b27  mov     [rbx], eax
0x180023b29  xor     eax, eax
0x180023b2b  add     rsp, 20h
0x180023b2f  pop     rbx
0x180023b30  retn
```
