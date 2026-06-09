# wil::details::FreeProcessHeap(void *)

- ea: `0x14001801c`
- end: `0x14001803f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x1400171f0`
- `0x140017380`
- `0x140017428`
- `0x1400174b4`
- `0x1400174ec`
- `0x14001754c`
- `0x140017598`
- `0x1400190b0`
- `0x1400191dc`
- `0x140019be4`
- `0x140019eb8`
- `0x14001a594`
- `0x14001ad14`
- `0x14001bcc0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140018038`
- `KERNEL32!GetProcessHeap` at `0x140018025`
- `KERNEL32!GetProcessHeap` at `0x140018025`

## pseudocode

```c
void __fastcall wil::details::FreeProcessHeap(wil::details *this, void *a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, this);
}

```

## disassembly

```asm
0x14001801c  push    rbx
0x14001801e  sub     rsp, 20h
0x140018022  mov     rbx, rcx
0x140018025  call    cs:__imp_GetProcessHeap
0x14001802b  mov     r8, rbx
0x14001802e  xor     edx, edx
0x140018030  mov     rcx, rax
0x140018033  add     rsp, 20h
0x140018037  pop     rbx
0x140018038  jmp     cs:__imp_HeapFree
```
