# LOG_PROPERTY_INFO::LOG_PROPERTY_INFO(void)

- ea: `0x1800038f0`
- end: `0x180003912`
- name: `??0LOG_PROPERTY_INFO@@QEAA@XZ`
- size: `34`
- prototype: `LOG_PROPERTY_INFO *__fastcall(LOG_PROPERTY_INFO *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004044`
- `0x180004a5c`

## import_xrefs

- `IisRTL!??0STR@@QEAA@XZ` at `0x1800038f9`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180003903`
- `IisRTL!??0STR@@QEAA@XZ` at `0x1800038f9`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180003903`

## pseudocode

```c
LOG_PROPERTY_INFO *__fastcall LOG_PROPERTY_INFO::LOG_PROPERTY_INFO(LOG_PROPERTY_INFO *this)
{
  STR::STR(this);
  STR::STR((LOG_PROPERTY_INFO *)((char *)this + 72));
  return this;
}

```

## disassembly

```asm
0x1800038f0  push    rbx
0x1800038f2  sub     rsp, 20h
0x1800038f6  mov     rbx, rcx
0x1800038f9  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x1800038ff  lea     rcx, [rbx+48h]
0x180003903  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x180003909  mov     rax, rbx
0x18000390c  add     rsp, 20h
0x180003910  pop     rbx
0x180003911  retn
```
