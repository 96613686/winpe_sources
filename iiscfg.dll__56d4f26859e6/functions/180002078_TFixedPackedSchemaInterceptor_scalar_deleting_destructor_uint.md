# TFixedPackedSchemaInterceptor::`scalar deleting destructor'(uint)

- ea: `0x180002078`
- end: `0x1800020b0`
- name: `??_GTFixedPackedSchemaInterceptor@@QEAAPEAXI@Z`
- size: `56`
- prototype: `void *__fastcall(TFixedPackedSchemaInterceptor *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180002314`
- `0x18002a0c0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800020a1`
- `ole32!CoTaskMemFree` at `0x1800020a1`

## pseudocode

```c
TFixedPackedSchemaInterceptor *__fastcall TFixedPackedSchemaInterceptor::`scalar deleting destructor'(
        TFixedPackedSchemaInterceptor *this)
{
  *(_QWORD *)this = &TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableInterceptor'};
  *((_QWORD *)this + 1) = &TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableRead2'};
  *((_QWORD *)this + 2) = &TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableAdvanced'};
  CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180002078  push    rbx
0x18000207a  sub     rsp, 20h
0x18000207e  lea     rax, ??_7TFixedPackedSchemaInterceptor@@6BISimpleTableInterceptor@@@; const TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableInterceptor'}
0x180002085  mov     rbx, rcx
0x180002088  mov     [rcx], rax
0x18000208b  lea     rax, ??_7TFixedPackedSchemaInterceptor@@6BISimpleTableRead2@@@; const TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableRead2'}
0x180002092  mov     [rcx+8], rax
0x180002096  lea     rax, ??_7TFixedPackedSchemaInterceptor@@6BISimpleTableAdvanced@@@; const TFixedPackedSchemaInterceptor::`vftable'{for `ISimpleTableAdvanced'}
0x18000209d  mov     [rcx+10h], rax
0x1800020a1  call    cs:__imp_CoTaskMemFree
0x1800020a7  mov     rax, rbx
0x1800020aa  add     rsp, 20h
0x1800020ae  pop     rbx
0x1800020af  retn
```
