# CASCLOG::~CASCLOG(void)

- ea: `0x18000bf30`
- end: `0x18000bf74`
- name: `??1CASCLOG@@MEAA@XZ`
- size: `68`
- prototype: `void __fastcall(CASCLOG *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800095a0`
- `0x1800095e0`
- `0x1800097d0`
- `0x18000a100`

## callees

- `0x180001fcc`
- `0x180008550`

## import_xrefs

- `IisRTL!??_7CACHED_DATETIME_FORMATS@@6B@` at `0x18000bf54`

## pseudocode

```c
void __fastcall CASCLOG::~CASCLOG(CASCLOG *this)
{
  CLogScript *v2; // rcx

  *(_QWORD *)this = &CASCLOG::`vftable'{for `CLogFileCtrl'};
  v2 = (CASCLOG *)((char *)this + 408);
  *(_QWORD *)v2 = &CASCLOG::`vftable'{for `CLogScript'};
  *((_QWORD *)this + 197) = CACHED_DATETIME_FORMATS::`vftable';
  CLogScript::~CLogScript(v2);
  CLogFileCtrl::~CLogFileCtrl(this);
}

```

## disassembly

```asm
0x18000bf30  push    rbx
0x18000bf32  sub     rsp, 20h
0x18000bf36  mov     rbx, rcx
0x18000bf39  lea     rax, ??_7CASCLOG@@6BCLogFileCtrl@@@; const CASCLOG::`vftable'{for `CLogFileCtrl'}
0x18000bf40  mov     [rcx], rax
0x18000bf43  add     rcx, 198h; this
0x18000bf4a  lea     rax, ??_7CASCLOG@@6BCLogScript@@@; const CASCLOG::`vftable'{for `CLogScript'}
0x18000bf51  mov     [rcx], rax
0x18000bf54  mov     rax, cs:__imp_??_7CACHED_DATETIME_FORMATS@@6B@; const CACHED_DATETIME_FORMATS::`vftable'
0x18000bf5b  mov     [rbx+628h], rax
0x18000bf62  call    ??1CLogScript@@MEAA@XZ; CLogScript::~CLogScript(void)
0x18000bf67  mov     rcx, rbx; this
0x18000bf6a  add     rsp, 20h
0x18000bf6e  pop     rbx
0x18000bf6f  jmp     ??1CLogFileCtrl@@MEAA@XZ; CLogFileCtrl::~CLogFileCtrl(void)
```
