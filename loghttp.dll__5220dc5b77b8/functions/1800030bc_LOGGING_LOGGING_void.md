# LOGGING::LOGGING(void)

- ea: `0x1800030bc`
- end: `0x180003119`
- name: `??0LOGGING@@QEAA@XZ`
- size: `93`
- prototype: `LOGGING *__fastcall(LOGGING *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001080`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800030e5`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800030e5`

## pseudocode

```c
LOGGING *__fastcall LOGGING::LOGGING(LOGGING *this)
{
  LOGGING *result; // rax

  *((_QWORD *)this + 1) = 1195855692;
  *(_QWORD *)this = &LOGGING::`vftable';
  STRA::STRA((LOGGING *)((char *)this + 16), (char *)this + 72, 0x14u);
  result = this;
  *((_DWORD *)this + 23) = 0x10000;
  *((_DWORD *)this + 24) = 4096;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 1;
  return result;
}

```

## disassembly

```asm
0x1800030bc  push    rbx
0x1800030be  sub     rsp, 20h
0x1800030c2  lea     rax, ??_7LOGGING@@6B@; const LOGGING::`vftable'
0x1800030c9  mov     qword ptr [rcx+8], 47474F4Ch
0x1800030d1  mov     [rcx], rax
0x1800030d4  lea     rdx, [rcx+48h]
0x1800030d8  mov     rbx, rcx
0x1800030db  mov     r8d, 14h
0x1800030e1  add     rcx, 10h
0x1800030e5  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800030eb  mov     rax, rbx
0x1800030ee  mov     dword ptr [rbx+5Ch], 10000h
0x1800030f5  mov     dword ptr [rbx+60h], 1000h
0x1800030fc  mov     qword ptr [rbx+68h], 0
0x180003104  mov     qword ptr [rbx+70h], 0
0x18000310c  mov     dword ptr [rbx+78h], 1
0x180003113  add     rsp, 20h
0x180003117  pop     rbx
0x180003118  retn
```
