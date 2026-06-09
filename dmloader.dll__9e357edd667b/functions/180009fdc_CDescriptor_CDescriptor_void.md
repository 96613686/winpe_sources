# CDescriptor::CDescriptor(void)

- ea: `0x180009fdc`
- end: `0x18000a058`
- name: `??0CDescriptor@@QEAA@XZ`
- size: `124`
- prototype: `CDescriptor *__fastcall(CDescriptor *__hidden this)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x1800080f0`
- `0x18000828c`
- `0x180008450`
- `0x1800085b0`
- `0x180008710`
- `0x1800089e4`
- `0x180008bc0`
- `0x180008e90`
- `0x1800099e0`
- `0x180009b20`
- `0x180009d30`
- `0x18000a060`
- `0x18000ae74`
- `0x18000b45c`
- `0x18000b668`
- `0x18000b81c`
- `0x18000bbc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009ff3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009ff3`

## pseudocode

```c
CDescriptor *__fastcall CDescriptor::CDescriptor(CDescriptor *this)
{
  *((_DWORD *)this + 42) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  *((_DWORD *)this + 42) = 1;
  *(_QWORD *)this = 0;
  *(GUID *)((char *)this + 12) = GUID_NULL;
  *((_QWORD *)this + 12) = 0;
  *(GUID *)((char *)this + 28) = GUID_NULL;
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)((char *)this + 44) = 0;
  *(_QWORD *)((char *)this + 52) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  return this;
}

```

## disassembly

```asm
0x180009fdc  push    rbx
0x180009fde  sub     rsp, 20h
0x180009fe2  mov     rbx, rcx
0x180009fe5  mov     dword ptr [rcx+0A8h], 0
0x180009fef  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x180009ff3  call    cs:__imp_InitializeCriticalSection
0x180009ff9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000a000  xor     eax, eax
0x18000a002  mov     dword ptr [rbx+0A8h], 1
0x18000a00c  mov     qword ptr [rbx], 0
0x18000a013  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x18000a018  mov     qword ptr [rbx+60h], 0
0x18000a020  movdqu  xmmword ptr [rbx+1Ch], xmm0
0x18000a025  mov     dword ptr [rbx+8], 0
0x18000a02c  mov     [rbx+2Ch], rax
0x18000a030  mov     [rbx+34h], rax
0x18000a034  mov     [rbx+40h], rax
0x18000a038  mov     [rbx+48h], rax
0x18000a03c  mov     [rbx+50h], rax
0x18000a040  mov     [rbx+58h], eax
0x18000a043  mov     [rbx+68h], rax
0x18000a047  mov     [rbx+70h], rax
0x18000a04b  mov     [rbx+78h], rax
0x18000a04f  mov     rax, rbx
0x18000a052  add     rsp, 20h
0x18000a056  pop     rbx
0x18000a057  retn
```
