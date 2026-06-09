# wistd::unique_ptr<DX12BufferCopyQueue,wistd::default_delete<DX12BufferCopyQueue>>::reset(DX12BufferCopyQueue *)

- ea: `0x18005fc8c`
- end: `0x18005fcb8`
- name: `?reset@?$unique_ptr@VDX12BufferCopyQueue@@U?$default_delete@VDX12BufferCopyQueue@@@wistd@@@wistd@@QEAAXPEAVDX12BufferCopyQueue@@@Z`
- size: `44`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180058f84`
- `0x180058fc0`
- `0x18005af70`
- `0x18005d000`

## callees

- `0x1800245f0`
- `0x1800590d4`
- `0x18005fc8c`

## pseudocode

```c
void __fastcall wistd::unique_ptr<DX12BufferCopyQueue,wistd::default_delete<DX12BufferCopyQueue>>::reset(
        DX12BufferCopyQueue **a1,
        DX12BufferCopyQueue *a2)
{
  DX12BufferCopyQueue *v2; // rbx

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    DX12BufferCopyQueue::~DX12BufferCopyQueue(v2);
    operator delete(v2, (const struct std::nothrow_t *)0x30);
  }
}

```

## disassembly

```asm
0x18005fc8c  push    rbx
0x18005fc8e  sub     rsp, 20h
0x18005fc92  mov     rbx, [rcx]
0x18005fc95  mov     [rcx], rdx
0x18005fc98  test    rbx, rbx
0x18005fc9b  jz      short loc_18005FCB2
0x18005fc9d  mov     rcx, rbx; this
0x18005fca0  call    ??1DX12BufferCopyQueue@@QEAA@XZ; DX12BufferCopyQueue::~DX12BufferCopyQueue(void)
0x18005fca5  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x18005fcaa  mov     rcx, rbx; void *
0x18005fcad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005fcb2  add     rsp, 20h
0x18005fcb6  pop     rbx
0x18005fcb7  retn
```
