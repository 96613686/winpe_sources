# FreeCallObj

- ea: `0x1800028d0`
- end: `0x180002923`
- name: `FreeCallObj`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ba8`
- `0x1800063b0`

## callees

- `0x180001c7e`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002917`
- `KERNEL32!EnterCriticalSection` at `0x1800028ee`
- `KERNEL32!EnterCriticalSection` at `0x1800028ee`

## pseudocode

```c
void __fastcall FreeCallObj(_QWORD *a1)
{
  memset_0(a1, 0, (unsigned int)Size);
  EnterCriticalSection(&stru_18000E388);
  *a1 = qword_18000E380;
  qword_18000E380 = a1;
  LeaveCriticalSection(&stru_18000E388);
}

```

## disassembly

```asm
0x1800028d0  push    rbx
0x1800028d2  sub     rsp, 20h
0x1800028d6  mov     r8d, cs:Size; Size
0x1800028dd  xor     edx, edx; Val
0x1800028df  mov     rbx, rcx
0x1800028e2  call    memset_0
0x1800028e7  lea     rcx, stru_18000E388; lpCriticalSection
0x1800028ee  call    cs:__imp_EnterCriticalSection
0x1800028f5  nop     dword ptr [rax+rax+00h]
0x1800028fa  mov     rax, cs:qword_18000E380
0x180002901  lea     rcx, stru_18000E388
0x180002908  mov     [rbx], rax
0x18000290b  mov     cs:qword_18000E380, rbx
0x180002912  add     rsp, 20h
0x180002916  pop     rbx
0x180002917  jmp     cs:__imp_LeaveCriticalSection
```
