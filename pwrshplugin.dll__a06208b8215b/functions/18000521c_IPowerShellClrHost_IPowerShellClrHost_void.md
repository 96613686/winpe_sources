# IPowerShellClrHost::~IPowerShellClrHost(void)

- ea: `0x18000521c`
- end: `0x180005227`
- name: `??1IPowerShellClrHost@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(IPowerShellClrHost *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180009b1d`
- `0x180009e40`

## pseudocode

```c
void __fastcall IPowerShellClrHost::~IPowerShellClrHost(IPowerShellClrHost *this)
{
  *(_QWORD *)this = &IPowerShellClrHost::`vftable';
}

```

## disassembly

```asm
0x18000521c  lea     rax, ??_7IPowerShellClrHost@@6B@; const IPowerShellClrHost::`vftable'
0x180005223  mov     [rcx], rax
0x180005226  retn
```
