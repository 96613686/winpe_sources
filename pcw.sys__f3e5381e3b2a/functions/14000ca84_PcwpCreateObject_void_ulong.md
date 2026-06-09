# PcwpCreateObject(void * *,ulong)

- ea: `0x14000ca84`
- end: `0x14000cac5`
- name: `?PcwpCreateObject@@YAJPEAPEAXK@Z`
- size: `65`
- prototype: `__int64 __fastcall(void **, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140009558`
- `0x14000bbb0`
- `0x14000bc80`

## import_xrefs

- `ntoskrnl!ObCreateObject` at `0x14000cab3`
- `ntoskrnl!ObCreateObject` at `0x14000cab3`

## pseudocode

```c
__int64 __fastcall PcwpCreateObject(void **a1, int a2, __int64 a3, __int64 a4)
{
  LOBYTE(a4) = 1;
  return ObCreateObject(0, PcwObjectType, 0, a4, 0, a2, a2, 0, a1);
}

```

## disassembly

```asm
0x14000ca84  mov     rax, rsp
0x14000ca87  sub     rsp, 58h
0x14000ca8b  mov     [rax-18h], rcx
0x14000ca8f  mov     r9b, 1
0x14000ca92  mov     dword ptr [rax-20h], 0
0x14000ca99  xor     r8d, r8d
0x14000ca9c  mov     [rax-28h], edx
0x14000ca9f  xor     ecx, ecx
0x14000caa1  mov     [rax-30h], edx
0x14000caa4  mov     rdx, cs:?PcwObjectType@@3PEAU_OBJECT_TYPE@@EA; _OBJECT_TYPE * PcwObjectType
0x14000caab  mov     qword ptr [rax-38h], 0
0x14000cab3  call    cs:__imp_ObCreateObject
0x14000caba  nop     dword ptr [rax+rax+00h]
0x14000cabf  add     rsp, 58h
0x14000cac3  retn
```
