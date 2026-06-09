# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)

- ea: `0x18000e10c`
- end: `0x18000e134`
- name: `??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180013a1d`
- `0x180013a2f`
- `0x180013a65`
- `0x180013a89`

## callees

- `0x18000e10c`

## import_xrefs

- `msvcrt!free` at `0x18000e120`
- `msvcrt!free` at `0x18000e120`

## pseudocode

```c
void __fastcall ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(
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
0x18000e10c  push    rbx
0x18000e10e  sub     rsp, 20h
0x18000e112  mov     rbx, rcx
0x18000e115  mov     rcx, [rcx]
0x18000e118  jmp     short loc_18000E129
0x18000e11a  mov     rax, [rcx]
0x18000e11d  mov     [rbx], rax
0x18000e120  call    cs:__imp_free
0x18000e126  mov     rcx, [rbx]; Block
0x18000e129  test    rcx, rcx
0x18000e12c  jnz     short loc_18000E11A
0x18000e12e  add     rsp, 20h
0x18000e132  pop     rbx
0x18000e133  retn
```
