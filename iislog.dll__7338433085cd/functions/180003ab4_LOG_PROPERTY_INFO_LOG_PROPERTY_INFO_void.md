# LOG_PROPERTY_INFO::~LOG_PROPERTY_INFO(void)

- ea: `0x180003ab4`
- end: `0x180003ad6`
- name: `??1LOG_PROPERTY_INFO@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(LOG_PROPERTY_INFO *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003918`
- `0x180003cd8`

## import_xrefs

- `IisRTL!??1STR@@QEAA@XZ` at `0x180003ac1`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180003ac1`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180003acf`

## pseudocode

```c
void __fastcall LOG_PROPERTY_INFO::~LOG_PROPERTY_INFO(LOG_PROPERTY_INFO *this)
{
  STR::~STR((LOG_PROPERTY_INFO *)((char *)this + 72));
  STR::~STR(this);
}

```

## disassembly

```asm
0x180003ab4  push    rbx
0x180003ab6  sub     rsp, 20h
0x180003aba  mov     rbx, rcx
0x180003abd  add     rcx, 48h ; 'H'
0x180003ac1  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x180003ac7  mov     rcx, rbx
0x180003aca  add     rsp, 20h
0x180003ace  pop     rbx
0x180003acf  jmp     cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
```
