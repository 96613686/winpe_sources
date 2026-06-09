# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x1800020f4`
- end: `0x18000211c`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009e3e`
- `0x180009f50`

## callees

- `0x1800020f4`

## import_xrefs

- `msvcrt!free` at `0x180002108`
- `msvcrt!free` at `0x180002108`

## pseudocode

```c
void __fastcall ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(
        _QWORD **a1)
{
  _QWORD *i; // rcx

  for ( i = *a1; i; i = *a1 )
  {
    *a1 = (_QWORD *)*i;
    free(i);
  }
}

```

## disassembly

```asm
0x1800020f4  push    rbx
0x1800020f6  sub     rsp, 20h
0x1800020fa  mov     rbx, rcx
0x1800020fd  mov     rcx, [rcx]
0x180002100  jmp     short loc_180002111
0x180002102  mov     rax, [rcx]
0x180002105  mov     [rbx], rax
0x180002108  call    cs:__imp_free
0x18000210e  mov     rcx, [rbx]; Block
0x180002111  test    rcx, rcx
0x180002114  jnz     short loc_180002102
0x180002116  add     rsp, 20h
0x18000211a  pop     rbx
0x18000211b  retn
```
