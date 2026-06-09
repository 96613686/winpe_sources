# TOKEN_KEY::TOKEN_KEY(void)

- ea: `0x18000c324`
- end: `0x18000c354`
- name: `??0TOKEN_KEY@@QEAA@XZ`
- size: `48`
- prototype: `TOKEN_KEY *__fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c898`
- `0x1800117cc`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c33b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c345`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c33b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c345`

## pseudocode

```c
TOKEN_KEY *__fastcall TOKEN_KEY::TOKEN_KEY(TOKEN_KEY *this)
{
  *(_QWORD *)this = &TOKEN_KEY::`vftable';
  STRU::STRU((TOKEN_KEY *)((char *)this + 8));
  STRU::STRU((TOKEN_KEY *)((char *)this + 64));
  return this;
}

```

## disassembly

```asm
0x18000c324  push    rbx
0x18000c326  sub     rsp, 20h
0x18000c32a  lea     rax, ??_7TOKEN_KEY@@6B@; const TOKEN_KEY::`vftable'
0x18000c331  mov     rbx, rcx
0x18000c334  mov     [rcx], rax
0x18000c337  add     rcx, 8
0x18000c33b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000c341  lea     rcx, [rbx+40h]
0x18000c345  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000c34b  mov     rax, rbx
0x18000c34e  add     rsp, 20h
0x18000c352  pop     rbx
0x18000c353  retn
```
