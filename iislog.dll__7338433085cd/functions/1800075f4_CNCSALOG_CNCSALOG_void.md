# CNCSALOG::~CNCSALOG(void)

- ea: `0x1800075f4`
- end: `0x18000762a`
- name: `??1CNCSALOG@@MEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CNCSALOG *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007650`
- `0x1800096a0`
- `0x180009ab0`
- `0x18000a220`

## callees

- `0x180001fcc`
- `0x180008550`

## pseudocode

```c
void __fastcall CNCSALOG::~CNCSALOG(CNCSALOG *this)
{
  CLogScript *v2; // rcx

  *(_QWORD *)this = &CNCSALOG::`vftable'{for `CLogFileCtrl'};
  v2 = (CNCSALOG *)((char *)this + 408);
  *(_QWORD *)v2 = &CNCSALOG::`vftable'{for `CLogScript'};
  CLogScript::~CLogScript(v2);
  CLogFileCtrl::~CLogFileCtrl(this);
}

```

## disassembly

```asm
0x1800075f4  push    rbx
0x1800075f6  sub     rsp, 20h
0x1800075fa  lea     rax, ??_7CNCSALOG@@6BCLogFileCtrl@@@; const CNCSALOG::`vftable'{for `CLogFileCtrl'}
0x180007601  mov     rbx, rcx
0x180007604  mov     [rcx], rax
0x180007607  add     rcx, 198h; this
0x18000760e  lea     rax, ??_7CNCSALOG@@6BCLogScript@@@; const CNCSALOG::`vftable'{for `CLogScript'}
0x180007615  mov     [rcx], rax
0x180007618  call    ??1CLogScript@@MEAA@XZ; CLogScript::~CLogScript(void)
0x18000761d  mov     rcx, rbx; this
0x180007620  add     rsp, 20h
0x180007624  pop     rbx
0x180007625  jmp     ??1CLogFileCtrl@@MEAA@XZ; CLogFileCtrl::~CLogFileCtrl(void)
```
