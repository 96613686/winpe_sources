# AutoComMemory::~AutoComMemory(void)

- ea: `0x18001776c`
- end: `0x1800177a3`
- name: `??1AutoComMemory@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(LPVOID **this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800188c0`
- `0x1800357bf`

## callees

- `0x18001776c`
- `0x180018cdc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017785`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017785`

## pseudocode

```c
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
0x18001776c  mov     [rsp+arg_0], rbx
0x180017771  push    rdi
0x180017772  sub     rsp, 20h
0x180017776  mov     rbx, [rcx]
0x180017779  mov     rdi, rcx
0x18001777c  cmp     rbx, [rdi+8]
0x180017780  jz      short loc_180017791
0x180017782  mov     rcx, [rbx]; pv
0x180017785  call    cs:__imp_CoTaskMemFree
0x18001778b  add     rbx, 8
0x18001778f  jmp     short loc_18001777C
0x180017791  mov     rcx, rdi
0x180017794  mov     rbx, [rsp+28h+arg_0]
0x180017799  add     rsp, 20h
0x18001779d  pop     rdi
0x18001779e  jmp     ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
```
