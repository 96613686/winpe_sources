# AllocatedUnicodeString::~AllocatedUnicodeString(void)

- ea: `0x1400099e0`
- end: `0x140009a01`
- name: `??1AllocatedUnicodeString@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(AllocatedUnicodeString *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x14000930c`
- `0x140009d40`
- `0x14000a1e0`
- `0x14000a3c0`
- `0x14000a500`
- `0x14000a7e0`
- `0x14000a9b0`
- `0x14000aa80`
- `0x14000ce18`
- `0x14000d0b8`

## callees

- `0x1400099e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400099ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400099ef`

## pseudocode

```c
void __fastcall AllocatedUnicodeString::~AllocatedUnicodeString(AllocatedUnicodeString *this)
{
  void *v1; // rcx

  v1 = (void *)*((_QWORD *)this + 1);
  if ( v1 )
    ExFreePoolWithTag(v1, 0);
}

```

## disassembly

```asm
0x1400099e0  sub     rsp, 28h
0x1400099e4  mov     rcx, [rcx+8]; P
0x1400099e8  test    rcx, rcx
0x1400099eb  jz      short loc_1400099FB
0x1400099ed  xor     edx, edx; Tag
0x1400099ef  call    cs:__imp_ExFreePoolWithTag
0x1400099f6  nop     dword ptr [rax+rax+00h]
0x1400099fb  add     rsp, 28h
0x1400099ff  retn
```
