# CreateASFReaderInstance(IUnknown *,long *)

- ea: `0x1800090f0`
- end: `0x180009128`
- name: `?CreateASFReaderInstance@@YAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `56`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001020`
- `0x180007bb0`
- `0x1800090f0`

## pseudocode

```c
struct CUnknown *__fastcall CreateASFReaderInstance(struct IUnknown *a1, int *a2)
{
  struct CUnknown *result; // rax

  result = (struct CUnknown *)operator new(0x1F0u);
  if ( result )
    return CASFReader::CASFReader(result, a1, a2);
  return result;
}

```

## disassembly

```asm
0x1800090f0  mov     [rsp+arg_0], rbx
0x1800090f5  push    rdi
0x1800090f6  sub     rsp, 20h
0x1800090fa  mov     rdi, rcx
0x1800090fd  mov     rbx, rdx
0x180009100  mov     ecx, 1F0h; Size
0x180009105  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000910a  test    rax, rax
0x18000910d  jz      short loc_18000911D
0x18000910f  mov     r8, rbx; int *
0x180009112  mov     rdx, rdi; struct IUnknown *
0x180009115  mov     rcx, rax; this
0x180009118  call    ??0CASFReader@@QEAA@PEAUIUnknown@@PEAJ@Z; CASFReader::CASFReader(IUnknown *,long *)
0x18000911d  mov     rbx, [rsp+28h+arg_0]
0x180009122  add     rsp, 20h
0x180009126  pop     rdi
0x180009127  retn
```
