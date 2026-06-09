# CKernelFilterFile::~CKernelFilterFile(void)

- ea: `0x14000a318`
- end: `0x14000a338`
- name: `??1CKernelFilterFile@@UEAA@XZ`
- size: `32`
- prototype: `void __fastcall(CKernelFilterFile *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400012b0`

## callees

- `0x14000183c`

## pseudocode

```c
void __fastcall CKernelFilterFile::~CKernelFilterFile(KSPIN_LOCK **this)
{
  *this = (KSPIN_LOCK *)&CKernelFilterFile::`vftable';
  CKernelFilterDevice::NotifyDestroyFile(this[4], (struct CKernelFilterFile *)this);
}

```

## disassembly

```asm
0x14000a318  sub     rsp, 28h
0x14000a31c  lea     rax, ??_7CKernelFilterFile@@6B@; const CKernelFilterFile::`vftable'
0x14000a323  mov     rdx, rcx; struct CKernelFilterFile *
0x14000a326  mov     [rcx], rax
0x14000a329  mov     rcx, [rcx+20h]; this
0x14000a32d  call    ?NotifyDestroyFile@CKernelFilterDevice@@QEAAJPEAVCKernelFilterFile@@@Z; CKernelFilterDevice::NotifyDestroyFile(CKernelFilterFile *)
0x14000a332  add     rsp, 28h
0x14000a336  retn
```
