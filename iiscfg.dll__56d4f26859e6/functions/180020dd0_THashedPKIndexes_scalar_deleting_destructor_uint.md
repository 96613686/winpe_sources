# THashedPKIndexes::`scalar deleting destructor'(uint)

- ea: `0x180020dd0`
- end: `0x180020e00`
- name: `??_GTHashedPKIndexes@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(THashedPKIndexes *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180020d60`
- `0x180020dd0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180020dec`
- `ole32!CoTaskMemFree` at `0x180020dec`

## pseudocode

```c
THashedPKIndexes *__fastcall THashedPKIndexes::`scalar deleting destructor'(THashedPKIndexes *this, char a2)
{
  THashedPKIndexes::~THashedPKIndexes(this);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180020dd0  mov     [rsp+arg_0], rbx
0x180020dd5  push    rdi
0x180020dd6  sub     rsp, 20h
0x180020dda  mov     ebx, edx
0x180020ddc  mov     rdi, rcx
0x180020ddf  call    ??1THashedPKIndexes@@UEAA@XZ; THashedPKIndexes::~THashedPKIndexes(void)
0x180020de4  test    bl, 1
0x180020de7  jz      short loc_180020DF2
0x180020de9  mov     rcx, rdi; pv
0x180020dec  call    cs:__imp_CoTaskMemFree
0x180020df2  mov     rax, rdi
0x180020df5  mov     rbx, [rsp+28h+arg_0]
0x180020dfa  add     rsp, 20h
0x180020dfe  pop     rdi
0x180020dff  retn
```
