# AutoComMemory::~AutoComMemory(void)

- ea: `0x180027f28`
- end: `0x180027f5f`
- name: `??1AutoComMemory@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(LPVOID **this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029040`
- `0x180032cbe`

## callees

- `0x180027f28`
- `0x180029420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027f41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027f41`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AutoComMemory::~AutoComMemory(LPVOID **this)
{
  LPVOID *i; // rbx

  for ( i = *this; i != this[1]; ++i )
    CoTaskMemFree(*i);
  std::vector<void *>::_Tidy(this);
}

```

## disassembly

```asm
0x180027f28  mov     [rsp+arg_0], rbx
0x180027f2d  push    rdi
0x180027f2e  sub     rsp, 20h
0x180027f32  mov     rbx, [rcx]
0x180027f35  mov     rdi, rcx
0x180027f38  cmp     rbx, [rdi+8]
0x180027f3c  jz      short loc_180027F4D
0x180027f3e  mov     rcx, [rbx]; pv
0x180027f41  call    cs:__imp_CoTaskMemFree
0x180027f47  add     rbx, 8
0x180027f4b  jmp     short loc_180027F38
0x180027f4d  mov     rcx, rdi
0x180027f50  mov     rbx, [rsp+28h+arg_0]
0x180027f55  add     rsp, 20h
0x180027f59  pop     rdi
0x180027f5a  jmp     ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
```
