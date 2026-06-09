# TMetabase_XMLtable::TLocation::`vector deleting destructor'(uint)

- ea: `0x180005c48`
- end: `0x180005c78`
- name: `??_ETLocation@TMetabase_XMLtable@@QEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(TMetabase_XMLtable::TLocation *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800057f8`
- `0x18000654c`
- `0x18000d110`

## callees

- `0x180001d84`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005c69`
- `ole32!CoTaskMemFree` at `0x180005c69`

## pseudocode

```c
char *__fastcall TMetabase_XMLtable::TLocation::`vector deleting destructor'(TMetabase_XMLtable::TLocation *this)
{
  char *v1; // rbx

  v1 = (char *)this - 8;
  `eh vector destructor iterator'(
    this,
    0x18u,
    *((_QWORD *)this - 1),
    (void (*)(void *))TGrowableBuffer::~TGrowableBuffer);
  CoTaskMemFree(v1);
  return v1;
}

```

## disassembly

```asm
0x180005c48  push    rbx
0x180005c4a  sub     rsp, 20h
0x180005c4e  lea     rbx, [rcx-8]
0x180005c52  lea     r9, ??1TGrowableBuffer@@QEAA@XZ; void (*)(void *)
0x180005c59  mov     r8, [rbx]; unsigned __int64
0x180005c5c  mov     edx, 18h; unsigned __int64
0x180005c61  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180005c66  mov     rcx, rbx; pv
0x180005c69  call    cs:__imp_CoTaskMemFree
0x180005c6f  mov     rax, rbx
0x180005c72  add     rsp, 20h
0x180005c76  pop     rbx
0x180005c77  retn
```
