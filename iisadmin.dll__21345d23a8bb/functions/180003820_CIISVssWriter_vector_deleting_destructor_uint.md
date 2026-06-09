# CIISVssWriter::`vector deleting destructor'(uint)

- ea: `0x180003820`
- end: `0x18000384f`
- name: `??_ECIISVssWriter@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CIISVssWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x1800037a4`
- `0x180003820`

## pseudocode

```c
CIISVssWriter *__fastcall CIISVssWriter::`vector deleting destructor'(CIISVssWriter *this, char a2)
{
  CIISVssWriter::~CIISVssWriter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003820  mov     [rsp+arg_0], rbx
0x180003825  push    rdi
0x180003826  sub     rsp, 20h
0x18000382a  mov     ebx, edx
0x18000382c  mov     rdi, rcx
0x18000382f  call    ??1CIISVssWriter@@UEAA@XZ; CIISVssWriter::~CIISVssWriter(void)
0x180003834  test    bl, 1
0x180003837  jz      short loc_180003841
0x180003839  mov     rcx, rdi; Block
0x18000383c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003841  mov     rbx, [rsp+28h+arg_0]
0x180003846  mov     rax, rdi
0x180003849  add     rsp, 20h
0x18000384d  pop     rdi
0x18000384e  retn
```
