# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)

- ea: `0x180008bf4`
- end: `0x180008c1c`
- name: `??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180009120`
- `0x18000919c`
- `0x18000a728`
- `0x18000ac80`
- `0x18000b7bc`
- `0x18000ba34`
- `0x18000ccf9`
- `0x18000cd53`
- `0x18000cd65`

## callees

- `0x180008bf4`

## import_xrefs

- `msvcrt!free` at `0x180008c08`
- `msvcrt!free` at `0x180008c08`

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
0x180008bf4  push    rbx
0x180008bf6  sub     rsp, 20h
0x180008bfa  mov     rbx, rcx
0x180008bfd  mov     rcx, [rcx]
0x180008c00  jmp     short loc_180008C11
0x180008c02  mov     rax, [rcx]
0x180008c05  mov     [rbx], rax
0x180008c08  call    cs:__imp_free
0x180008c0e  mov     rcx, [rbx]; Block
0x180008c11  test    rcx, rcx
0x180008c14  jnz     short loc_180008C02
0x180008c16  add     rsp, 20h
0x180008c1a  pop     rbx
0x180008c1b  retn
```
