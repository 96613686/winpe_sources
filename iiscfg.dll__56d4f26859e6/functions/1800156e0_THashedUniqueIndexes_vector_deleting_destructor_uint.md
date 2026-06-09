# THashedUniqueIndexes::`vector deleting destructor'(uint)

- ea: `0x1800156e0`
- end: `0x180015707`
- name: `??_ETHashedUniqueIndexes@@UEAAPEAXI@Z`
- size: `39`
- prototype: `void *__fastcall(THashedUniqueIndexes *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800156e0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800156f8`
- `ole32!CoTaskMemFree` at `0x1800156f8`

## pseudocode

```c
THashedUniqueIndexes *__fastcall THashedUniqueIndexes::`vector deleting destructor'(
        THashedUniqueIndexes *this,
        char a2)
{
  *(_QWORD *)this = &ICompilationPlugin::`vftable';
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x1800156e0  push    rbx
0x1800156e2  sub     rsp, 20h
0x1800156e6  mov     rbx, rcx
0x1800156e9  lea     rax, ??_7ICompilationPlugin@@6B@; const ICompilationPlugin::`vftable'
0x1800156f0  mov     [rcx], rax
0x1800156f3  test    dl, 1
0x1800156f6  jz      short loc_1800156FE
0x1800156f8  call    cs:__imp_CoTaskMemFree
0x1800156fe  mov     rax, rbx
0x180015701  add     rsp, 20h
0x180015705  pop     rbx
0x180015706  retn
```
