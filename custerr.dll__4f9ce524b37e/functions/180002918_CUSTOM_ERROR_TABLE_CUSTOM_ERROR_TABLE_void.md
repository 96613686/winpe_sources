# CUSTOM_ERROR_TABLE::CUSTOM_ERROR_TABLE(void)

- ea: `0x180002918`
- end: `0x180002986`
- name: `??0CUSTOM_ERROR_TABLE@@QEAA@XZ`
- size: `110`
- prototype: `CUSTOM_ERROR_TABLE *__fastcall(CUSTOM_ERROR_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800012c0`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18000292f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002939`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002946`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002953`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000292f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002939`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002946`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002953`

## pseudocode

```c
CUSTOM_ERROR_TABLE *__fastcall CUSTOM_ERROR_TABLE::CUSTOM_ERROR_TABLE(CUSTOM_ERROR_TABLE *this)
{
  *(_QWORD *)this = &CUSTOM_ERROR_TABLE::`vftable';
  STRU::STRU((CUSTOM_ERROR_TABLE *)((char *)this + 24));
  STRU::STRU((CUSTOM_ERROR_TABLE *)((char *)this + 80));
  STRU::STRU((CUSTOM_ERROR_TABLE *)((char *)this + 136));
  STRU::STRU((CUSTOM_ERROR_TABLE *)((char *)this + 192));
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 33) = &MIME_MAP::`vftable';
  *((_QWORD *)this + 2) = (char *)this + 8;
  *((_QWORD *)this + 1) = (char *)this + 8;
  return this;
}

```

## disassembly

```asm
0x180002918  push    rbx
0x18000291a  sub     rsp, 20h
0x18000291e  lea     rax, ??_7CUSTOM_ERROR_TABLE@@6B@; const CUSTOM_ERROR_TABLE::`vftable'
0x180002925  mov     rbx, rcx
0x180002928  mov     [rcx], rax
0x18000292b  add     rcx, 18h
0x18000292f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002935  lea     rcx, [rbx+50h]
0x180002939  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000293f  lea     rcx, [rbx+88h]
0x180002946  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000294c  lea     rcx, [rbx+0C0h]
0x180002953  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002959  lea     rax, ??_7MIME_MAP@@6B@; const MIME_MAP::`vftable'
0x180002960  mov     qword ptr [rbx+118h], 0
0x18000296b  mov     [rbx+108h], rax
0x180002972  lea     rax, [rbx+8]
0x180002976  mov     [rax+8], rax
0x18000297a  mov     [rax], rax
0x18000297d  mov     rax, rbx
0x180002980  add     rsp, 20h
0x180002984  pop     rbx
0x180002985  retn
```
