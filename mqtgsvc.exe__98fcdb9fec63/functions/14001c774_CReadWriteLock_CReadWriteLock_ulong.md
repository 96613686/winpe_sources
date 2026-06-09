# CReadWriteLock::CReadWriteLock(ulong)

- ea: `0x14001c774`
- end: `0x14001c7de`
- name: `??0CReadWriteLock@@QEAA@K@Z`
- size: `106`
- prototype: `CReadWriteLock *__fastcall(CReadWriteLock *this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005c08`
- `0x140005cdc`
- `0x14000bdc0`

## callees

- `0x14001c774`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x14001c7b2`
- `KERNEL32!GetSystemInfo` at `0x14001c7b2`

## pseudocode

```c
CReadWriteLock *__fastcall CReadWriteLock::CReadWriteLock(CReadWriteLock *this)
{
  bool v1; // zf
  struct _SYSTEM_INFO v4; // [rsp+20h] [rbp-38h] BYREF

  v1 = dword_14002B130 == 0;
  *((_DWORD *)this + 1) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( v1 )
  {
    memset(&v4, 0, sizeof(v4));
    GetSystemInfo(&v4);
    dword_14002B130 = 1;
    dword_14002B250 = -(v4.dwNumberOfProcessors > 1);
  }
  *(_DWORD *)this = 0;
  return this;
}

```

## disassembly

```asm
0x14001c774  mov     rax, rsp
0x14001c777  push    rbx
0x14001c778  sub     rsp, 50h
0x14001c77c  cmp     cs:dword_14002B130, 0
0x14001c783  mov     rbx, rcx
0x14001c786  mov     dword ptr [rcx+4], 0
0x14001c78d  mov     qword ptr [rcx+8], 0
0x14001c795  mov     qword ptr [rcx+10h], 0
0x14001c79d  jnz     short loc_14001C7CF
0x14001c79f  xorps   xmm0, xmm0
0x14001c7a2  lea     rcx, [rax-38h]; lpSystemInfo
0x14001c7a6  movups  xmmword ptr [rax-38h], xmm0
0x14001c7aa  movups  xmmword ptr [rax-28h], xmm0
0x14001c7ae  movups  xmmword ptr [rax-18h], xmm0
0x14001c7b2  call    cs:__imp_GetSystemInfo
0x14001c7b8  mov     ecx, 1
0x14001c7bd  cmp     ecx, [rsp+58h+var_18]
0x14001c7c1  mov     cs:dword_14002B130, ecx
0x14001c7c7  sbb     eax, eax
0x14001c7c9  mov     cs:dword_14002B250, eax
0x14001c7cf  mov     dword ptr [rbx], 0
0x14001c7d5  mov     rax, rbx
0x14001c7d8  add     rsp, 50h
0x14001c7dc  pop     rbx
0x14001c7dd  retn
```
