# COMPRESSION_SCHEME::COMPRESSION_SCHEME(void)

- ea: `0x180003c30`
- end: `0x180003cb4`
- name: `??0COMPRESSION_SCHEME@@QEAA@XZ`
- size: `132`
- prototype: `COMPRESSION_SCHEME *__fastcall(COMPRESSION_SCHEME *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800012b0`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180003c39`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003c4d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003c39`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003c4d`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003c43`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180003c43`

## pseudocode

```c
COMPRESSION_SCHEME *__fastcall COMPRESSION_SCHEME::COMPRESSION_SCHEME(COMPRESSION_SCHEME *this)
{
  COMPRESSION_SCHEME *result; // rax

  STRU::STRU(this);
  STRA::STRA((COMPRESSION_SCHEME *)((char *)this + 56));
  STRU::STRU((COMPRESSION_SCHEME *)((char *)this + 112));
  *(_QWORD *)((char *)this + 228) = 10;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 0;
  result = this;
  *((_DWORD *)this + 59) = 1;
  *((_DWORD *)this + 60) = 1;
  return result;
}

```

## disassembly

```asm
0x180003c30  push    rbx
0x180003c32  sub     rsp, 20h
0x180003c36  mov     rbx, rcx
0x180003c39  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003c3f  lea     rcx, [rbx+38h]
0x180003c43  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180003c49  lea     rcx, [rbx+70h]
0x180003c4d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003c53  xor     eax, eax
0x180003c55  mov     qword ptr [rbx+0E4h], 0Ah
0x180003c60  mov     [rbx+0A8h], rax
0x180003c67  mov     [rbx+0B0h], rax
0x180003c6e  mov     [rbx+0B8h], rax
0x180003c75  mov     [rbx+0C0h], rax
0x180003c7c  mov     [rbx+0C8h], rax
0x180003c83  mov     [rbx+0D0h], rax
0x180003c8a  mov     [rbx+0D8h], rax
0x180003c91  mov     [rbx+0E0h], eax
0x180003c97  mov     rax, rbx
0x180003c9a  mov     dword ptr [rbx+0ECh], 1
0x180003ca4  mov     dword ptr [rbx+0F0h], 1
0x180003cae  add     rsp, 20h
0x180003cb2  pop     rbx
0x180003cb3  retn
```
