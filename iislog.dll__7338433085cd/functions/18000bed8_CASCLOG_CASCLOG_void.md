# CASCLOG::CASCLOG(void)

- ea: `0x18000bed8`
- end: `0x18000bf28`
- name: `??0CASCLOG@@QEAA@XZ`
- size: `80`
- prototype: `CASCLOG *__fastcall(CASCLOG *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800097d0`

## callees

- `0x180001f20`
- `0x18000849c`

## import_xrefs

- `IisRTL!??0ASCLOG_DATETIME_CACHE@@QEAA@XZ` at `0x18000bf14`
- `IisRTL!??0ASCLOG_DATETIME_CACHE@@QEAA@XZ` at `0x18000bf14`

## pseudocode

```c
CASCLOG *__fastcall CASCLOG::CASCLOG(CASCLOG *this)
{
  CLogFileCtrl::CLogFileCtrl(this);
  CLogScript::CLogScript((CASCLOG *)((char *)this + 408));
  *(_QWORD *)this = &CASCLOG::`vftable'{for `CLogFileCtrl'};
  *((_QWORD *)this + 51) = &CASCLOG::`vftable'{for `CLogScript'};
  ASCLOG_DATETIME_CACHE::ASCLOG_DATETIME_CACHE((CASCLOG *)((char *)this + 1576));
  return this;
}

```

## disassembly

```asm
0x18000bed8  mov     [rsp+arg_0], rbx
0x18000bedd  push    rdi
0x18000bede  sub     rsp, 20h
0x18000bee2  mov     rdi, rcx
0x18000bee5  call    ??0CLogFileCtrl@@QEAA@XZ; CLogFileCtrl::CLogFileCtrl(void)
0x18000beea  lea     rbx, [rdi+198h]
0x18000bef1  mov     rcx, rbx; this
0x18000bef4  call    ??0CLogScript@@QEAA@XZ; CLogScript::CLogScript(void)
0x18000bef9  lea     rax, ??_7CASCLOG@@6BCLogFileCtrl@@@; const CASCLOG::`vftable'{for `CLogFileCtrl'}
0x18000bf00  mov     [rdi], rax
0x18000bf03  lea     rcx, [rdi+628h]
0x18000bf0a  lea     rax, ??_7CASCLOG@@6BCLogScript@@@; const CASCLOG::`vftable'{for `CLogScript'}
0x18000bf11  mov     [rbx], rax
0x18000bf14  call    cs:__imp_??0ASCLOG_DATETIME_CACHE@@QEAA@XZ; ASCLOG_DATETIME_CACHE::ASCLOG_DATETIME_CACHE(void)
0x18000bf1a  mov     rbx, [rsp+28h+arg_0]
0x18000bf1f  mov     rax, rdi
0x18000bf22  add     rsp, 20h
0x18000bf26  pop     rdi
0x18000bf27  retn
```
