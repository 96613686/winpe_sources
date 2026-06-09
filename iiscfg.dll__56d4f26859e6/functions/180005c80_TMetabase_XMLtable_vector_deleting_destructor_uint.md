# TMetabase_XMLtable::`vector deleting destructor'(uint)

- ea: `0x180005c80`
- end: `0x180005cb0`
- name: `??_ETMetabase_XMLtable@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(TMetabase_XMLtable *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x18000593c`
- `0x180005c80`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005c9c`
- `ole32!CoTaskMemFree` at `0x180005c9c`

## pseudocode

```c
TMetabase_XMLtable *__fastcall TMetabase_XMLtable::`vector deleting destructor'(TMetabase_XMLtable *this, char a2)
{
  TMetabase_XMLtable::~TMetabase_XMLtable(this);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180005c80  mov     [rsp+arg_0], rbx
0x180005c85  push    rdi
0x180005c86  sub     rsp, 20h
0x180005c8a  mov     ebx, edx
0x180005c8c  mov     rdi, rcx
0x180005c8f  call    ??1TMetabase_XMLtable@@UEAA@XZ; TMetabase_XMLtable::~TMetabase_XMLtable(void)
0x180005c94  test    bl, 1
0x180005c97  jz      short loc_180005CA2
0x180005c99  mov     rcx, rdi; pv
0x180005c9c  call    cs:__imp_CoTaskMemFree
0x180005ca2  mov     rax, rdi
0x180005ca5  mov     rbx, [rsp+28h+arg_0]
0x180005caa  add     rsp, 20h
0x180005cae  pop     rdi
0x180005caf  retn
```
