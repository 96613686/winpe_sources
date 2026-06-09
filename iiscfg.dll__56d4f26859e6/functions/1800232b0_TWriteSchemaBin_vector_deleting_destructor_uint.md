# TWriteSchemaBin::`vector deleting destructor'(uint)

- ea: `0x1800232b0`
- end: `0x1800232e0`
- name: `??_ETWriteSchemaBin@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(TWriteSchemaBin *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18002324c`
- `0x1800232b0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800232cc`
- `ole32!CoTaskMemFree` at `0x1800232cc`

## pseudocode

```c
TWriteSchemaBin *__fastcall TWriteSchemaBin::`vector deleting destructor'(TWriteSchemaBin *this, char a2)
{
  TWriteSchemaBin::~TWriteSchemaBin(this);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x1800232b0  mov     [rsp+arg_0], rbx
0x1800232b5  push    rdi
0x1800232b6  sub     rsp, 20h
0x1800232ba  mov     ebx, edx
0x1800232bc  mov     rdi, rcx
0x1800232bf  call    ??1TWriteSchemaBin@@UEAA@XZ; TWriteSchemaBin::~TWriteSchemaBin(void)
0x1800232c4  test    bl, 1
0x1800232c7  jz      short loc_1800232D2
0x1800232c9  mov     rcx, rdi; pv
0x1800232cc  call    cs:__imp_CoTaskMemFree
0x1800232d2  mov     rax, rdi
0x1800232d5  mov     rbx, [rsp+28h+arg_0]
0x1800232da  add     rsp, 20h
0x1800232de  pop     rdi
0x1800232df  retn
```
