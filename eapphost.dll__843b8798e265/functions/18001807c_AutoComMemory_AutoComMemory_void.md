# AutoComMemory::~AutoComMemory(void)

- ea: `0x18001807c`
- end: `0x1800180b9`
- name: `??1AutoComMemory@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(AutoComMemory *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019260`
- `0x180036b7a`

## callees

- `0x18001807c`
- `0x180019684`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018095`

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
0x18001807c  mov     [rsp+arg_0], rbx
0x180018081  push    rdi
0x180018082  sub     rsp, 20h
0x180018086  mov     rbx, [rcx]
0x180018089  mov     rdi, rcx
0x18001808c  cmp     rbx, [rdi+8]
0x180018090  jz      short loc_1800180A7
0x180018092  mov     rcx, [rbx]; pv
0x180018095  call    cs:__imp_CoTaskMemFree
0x18001809c  nop     dword ptr [rax+rax+00h]
0x1800180a1  add     rbx, 8
0x1800180a5  jmp     short loc_18001808C
0x1800180a7  mov     rcx, rdi
0x1800180aa  mov     rbx, [rsp+28h+arg_0]
0x1800180af  add     rsp, 20h
0x1800180b3  pop     rdi
0x1800180b4  jmp     ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
```
