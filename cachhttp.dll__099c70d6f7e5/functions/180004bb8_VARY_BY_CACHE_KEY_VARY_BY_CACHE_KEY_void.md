# VARY_BY_CACHE_KEY::VARY_BY_CACHE_KEY(void)

- ea: `0x180004bb8`
- end: `0x180004bf4`
- name: `??0VARY_BY_CACHE_KEY@@QEAA@XZ`
- size: `60`
- prototype: `VARY_BY_CACHE_KEY *__fastcall(VARY_BY_CACHE_KEY *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180004b0c`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004bcb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004be5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004bcb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004be5`

## pseudocode

```c
VARY_BY_CACHE_KEY *__fastcall VARY_BY_CACHE_KEY::VARY_BY_CACHE_KEY(VARY_BY_CACHE_KEY *this)
{
  STRU::STRU(this, (unsigned __int16 *)this + 28, 0x80u);
  STRU::STRU((VARY_BY_CACHE_KEY *)((char *)this + 312), (unsigned __int16 *)this + 184, 0x80u);
  return this;
}

```

## disassembly

```asm
0x180004bb8  push    rbx
0x180004bba  sub     rsp, 20h
0x180004bbe  lea     rdx, [rcx+38h]
0x180004bc2  mov     r8d, 80h
0x180004bc8  mov     rbx, rcx
0x180004bcb  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004bd1  lea     rdx, [rbx+170h]
0x180004bd8  mov     r8d, 80h
0x180004bde  lea     rcx, [rbx+138h]
0x180004be5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004beb  mov     rax, rbx
0x180004bee  add     rsp, 20h
0x180004bf2  pop     rbx
0x180004bf3  retn
```
