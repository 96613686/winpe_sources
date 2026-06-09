# std::unique_ptr<LPA_SERVICE_INFO,ESIMPM::CustomDeleter>::~unique_ptr<LPA_SERVICE_INFO,ESIMPM::CustomDeleter>(void)

- ea: `0x140023a00`
- end: `0x140023a16`
- name: `??1?$unique_ptr@ULPA_SERVICE_INFO@@UCustomDeleter@ESIMPM@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x14003d17e`
- `0x14003d190`
- `0x14003d21a`
- `0x14003d261`
- `0x14003d2ba`
- `0x14003d2ef`
- `0x14003d322`
- `0x14003d3c0`

## callees

- `0x140003244`
- `0x140023a00`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::unique_ptr<LPA_SERVICE_INFO,ESIMPM::CustomDeleter>::~unique_ptr<LPA_SERVICE_INFO,ESIMPM::CustomDeleter>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x140023a00  sub     rsp, 28h
0x140023a04  mov     rcx, [rcx]; Block
0x140023a07  test    rcx, rcx
0x140023a0a  jz      short loc_140023A11
0x140023a0c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140023a11  add     rsp, 28h
0x140023a15  retn
```
