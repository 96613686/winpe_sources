# CMsftDiscInformation::~CMsftDiscInformation(void)

- ea: `0x180017f24`
- end: `0x180017f50`
- name: `??1CMsftDiscInformation@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CMsftDiscInformation *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800134e8`
- `0x180014288`
- `0x1800171d8`
- `0x18001891c`

## callees

- `0x180017f24`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180017f35`
- `KERNEL32!LocalFree` at `0x180017f35`

## pseudocode

```c
void __fastcall CMsftDiscInformation::~CMsftDiscInformation(CMsftDiscInformation *this)
{
  void *v2; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    LocalFree(v2);
    *(_QWORD *)this = 0;
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x180017f24  push    rbx
0x180017f26  sub     rsp, 20h
0x180017f2a  mov     rbx, rcx
0x180017f2d  mov     rcx, [rcx]; hMem
0x180017f30  test    rcx, rcx
0x180017f33  jz      short loc_180017F42
0x180017f35  call    cs:__imp_LocalFree
0x180017f3b  mov     qword ptr [rbx], 0
0x180017f42  mov     qword ptr [rbx+8], 0
0x180017f4a  add     rsp, 20h
0x180017f4e  pop     rbx
0x180017f4f  retn
```
