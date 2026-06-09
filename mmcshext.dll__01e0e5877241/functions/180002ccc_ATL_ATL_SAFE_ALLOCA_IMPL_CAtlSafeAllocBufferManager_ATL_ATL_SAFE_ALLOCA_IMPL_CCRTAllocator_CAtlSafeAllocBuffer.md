# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)

- ea: `0x180002ccc`
- end: `0x180002cf4`
- name: `??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ab1c`
- `0x18000ab2e`
- `0x18000ab64`
- `0x18000ab88`

## callees

- `0x180002ccc`

## import_xrefs

- `msvcrt!free` at `0x180002ce0`
- `msvcrt!free` at `0x180002ce0`

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
0x180002ccc  push    rbx
0x180002cce  sub     rsp, 20h
0x180002cd2  mov     rbx, rcx
0x180002cd5  mov     rcx, [rcx]
0x180002cd8  jmp     short loc_180002CE9
0x180002cda  mov     rax, [rcx]
0x180002cdd  mov     [rbx], rax
0x180002ce0  call    cs:__imp_free
0x180002ce6  mov     rcx, [rbx]; Block
0x180002ce9  test    rcx, rcx
0x180002cec  jnz     short loc_180002CDA
0x180002cee  add     rsp, 20h
0x180002cf2  pop     rbx
0x180002cf3  retn
```
