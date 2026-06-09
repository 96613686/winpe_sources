# ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)

- ea: `0x180001ffc`
- end: `0x180002024`
- name: `??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800161ab`
- `0x1800161bd`
- `0x1800161f3`
- `0x180016217`

## callees

- `0x180001ffc`

## import_xrefs

- `msvcrt!free` at `0x180002010`
- `msvcrt!free` at `0x180002010`

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
0x180001ffc  push    rbx
0x180001ffe  sub     rsp, 20h
0x180002002  mov     rbx, rcx
0x180002005  mov     rcx, [rcx]
0x180002008  jmp     short loc_180002019
0x18000200a  mov     rax, [rcx]
0x18000200d  mov     [rbx], rax
0x180002010  call    cs:__imp_free
0x180002016  mov     rcx, [rbx]; Block
0x180002019  test    rcx, rcx
0x18000201c  jnz     short loc_18000200A
0x18000201e  add     rsp, 20h
0x180002022  pop     rbx
0x180002023  retn
```
