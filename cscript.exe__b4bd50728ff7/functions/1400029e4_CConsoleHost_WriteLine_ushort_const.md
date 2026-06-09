# CConsoleHost::WriteLine(ushort const *)

- ea: `0x1400029e4`
- end: `0x140002a17`
- name: `?WriteLine@CConsoleHost@@IEAAJPEBG@Z`
- size: `51`
- prototype: `__int64 __fastcall(CConsoleHost *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001330`

## callees

- `0x140002a70`

## import_xrefs

- `KERNEL32!GetStdHandle` at `0x1400029f9`
- `KERNEL32!GetStdHandle` at `0x1400029f9`

## pseudocode

```c
__int64 __fastcall CConsoleHost::WriteLine(CConsoleHost *this, const unsigned __int16 *a2)
{
  HANDLE StdHandle; // rax

  StdHandle = GetStdHandle(0xFFFFFFF5);
  return CConsoleHost::WriteLine(this, StdHandle, a2);
}

```

## disassembly

```asm
0x1400029e4  mov     [rsp+arg_0], rbx
0x1400029e9  push    rdi
0x1400029ea  sub     rsp, 20h
0x1400029ee  mov     rdi, rcx
0x1400029f1  mov     rbx, rdx
0x1400029f4  mov     ecx, 0FFFFFFF5h; nStdHandle
0x1400029f9  call    cs:__imp_GetStdHandle
0x1400029ff  mov     r8, rbx; unsigned __int16 *
0x140002a02  mov     rcx, rdi; this
0x140002a05  mov     rdx, rax; void *
0x140002a08  mov     rbx, [rsp+28h+arg_0]
0x140002a0d  add     rsp, 20h
0x140002a11  pop     rdi
0x140002a12  jmp     ?WriteLine@CConsoleHost@@IEAAJPEAXPEBG@Z; CConsoleHost::WriteLine(void *,ushort const *)
```
