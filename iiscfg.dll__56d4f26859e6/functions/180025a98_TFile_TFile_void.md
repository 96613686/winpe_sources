# TFile::~TFile(void)

- ea: `0x180025a98`
- end: `0x180025acb`
- name: `??1TFile@@UEAA@XZ`
- size: `51`
- prototype: `void __fastcall(TFile *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800232f0`
- `0x180025ae0`
- `0x18002eeed`

## callees

- `0x180025a98`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180025ab4`
- `KERNEL32!CloseHandle` at `0x180025ab4`
- `ole32!CoTaskMemFree` at `0x180025abe`
- `ole32!CoTaskMemFree` at `0x180025abe`

## pseudocode

```c
void __fastcall TFile::~TFile(TFile *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &TFile::`vftable';
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    CloseHandle(v2);
  CoTaskMemFree(*((LPVOID *)this + 2));
}

```

## disassembly

```asm
0x180025a98  push    rbx
0x180025a9a  sub     rsp, 20h
0x180025a9e  mov     rbx, rcx
0x180025aa1  lea     rax, ??_7TFile@@6B@; const TFile::`vftable'
0x180025aa8  mov     [rcx], rax
0x180025aab  mov     rcx, [rcx+8]; hObject
0x180025aaf  test    rcx, rcx
0x180025ab2  jz      short loc_180025ABA
0x180025ab4  call    cs:__imp_CloseHandle
0x180025aba  mov     rcx, [rbx+10h]; pv
0x180025abe  call    cs:__imp_CoTaskMemFree
0x180025ac4  nop
0x180025ac5  add     rsp, 20h
0x180025ac9  pop     rbx
0x180025aca  retn
```
