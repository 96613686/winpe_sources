# CUSTOM_LOG_FIELDS::CUSTOM_LOG_FIELDS(void)

- ea: `0x180004afc`
- end: `0x180004b28`
- name: `??0CUSTOM_LOG_FIELDS@@QEAA@XZ`
- size: `44`
- prototype: `CUSTOM_LOG_FIELDS *__fastcall(CUSTOM_LOG_FIELDS *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001cd0`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180004b05`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004b19`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004b05`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004b19`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180004b0f`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180004b0f`

## pseudocode

```c
CUSTOM_LOG_FIELDS *__fastcall CUSTOM_LOG_FIELDS::CUSTOM_LOG_FIELDS(CUSTOM_LOG_FIELDS *this)
{
  STRU::STRU(this);
  STRA::STRA((CUSTOM_LOG_FIELDS *)((char *)this + 56));
  STRU::STRU((CUSTOM_LOG_FIELDS *)((char *)this + 112));
  return this;
}

```

## disassembly

```asm
0x180004afc  push    rbx
0x180004afe  sub     rsp, 20h
0x180004b02  mov     rbx, rcx
0x180004b05  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004b0b  lea     rcx, [rbx+38h]
0x180004b0f  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180004b15  lea     rcx, [rbx+70h]
0x180004b19  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004b1f  mov     rax, rbx
0x180004b22  add     rsp, 20h
0x180004b26  pop     rbx
0x180004b27  retn
```
