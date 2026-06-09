# UL_RESPONSE_CACHE_KEY::UL_RESPONSE_CACHE_KEY(void)

- ea: `0x180002610`
- end: `0x180002666`
- name: `??0UL_RESPONSE_CACHE_KEY@@QEAA@XZ`
- size: `86`
- prototype: `UL_RESPONSE_CACHE_KEY *__fastcall(UL_RESPONSE_CACHE_KEY *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800020d0`
- `0x180002940`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002623`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000263d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002657`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002623`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000263d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002657`

## pseudocode

```c
UL_RESPONSE_CACHE_KEY *__fastcall UL_RESPONSE_CACHE_KEY::UL_RESPONSE_CACHE_KEY(UL_RESPONSE_CACHE_KEY *this)
{
  STRU::STRU(this, (unsigned __int16 *)this + 28, 0x40u);
  STRU::STRU((UL_RESPONSE_CACHE_KEY *)((char *)this + 184), (unsigned __int16 *)this + 120, 0x40u);
  STRU::STRU((UL_RESPONSE_CACHE_KEY *)((char *)this + 368), (unsigned __int16 *)this + 212, 0x40u);
  return this;
}

```

## disassembly

```asm
0x180002610  push    rbx
0x180002612  sub     rsp, 20h
0x180002616  lea     rdx, [rcx+38h]
0x18000261a  mov     r8d, 40h ; '@'
0x180002620  mov     rbx, rcx
0x180002623  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002629  lea     rdx, [rbx+0F0h]
0x180002630  mov     r8d, 40h ; '@'
0x180002636  lea     rcx, [rbx+0B8h]
0x18000263d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002643  lea     rdx, [rbx+1A8h]
0x18000264a  mov     r8d, 40h ; '@'
0x180002650  lea     rcx, [rbx+170h]
0x180002657  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000265d  mov     rax, rbx
0x180002660  add     rsp, 20h
0x180002664  pop     rbx
0x180002665  retn
```
