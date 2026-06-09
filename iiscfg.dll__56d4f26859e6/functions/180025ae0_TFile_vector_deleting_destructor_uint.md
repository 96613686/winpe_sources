# TFile::`vector deleting destructor'(uint)

- ea: `0x180025ae0`
- end: `0x180025b10`
- name: `??_ETFile@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(TFile *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180025a98`
- `0x180025ae0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180025afc`
- `ole32!CoTaskMemFree` at `0x180025afc`

## pseudocode

```c
TFile *__fastcall TFile::`vector deleting destructor'(TFile *this, char a2)
{
  TFile::~TFile(this);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180025ae0  mov     [rsp+arg_0], rbx
0x180025ae5  push    rdi
0x180025ae6  sub     rsp, 20h
0x180025aea  mov     ebx, edx
0x180025aec  mov     rdi, rcx
0x180025aef  call    ??1TFile@@UEAA@XZ; TFile::~TFile(void)
0x180025af4  test    bl, 1
0x180025af7  jz      short loc_180025B02
0x180025af9  mov     rcx, rdi; pv
0x180025afc  call    cs:__imp_CoTaskMemFree
0x180025b02  mov     rax, rdi
0x180025b05  mov     rbx, [rsp+28h+arg_0]
0x180025b0a  add     rsp, 20h
0x180025b0e  pop     rdi
0x180025b0f  retn
```
