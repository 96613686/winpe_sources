# std::default_delete<D3DCoreModule>::operator()(D3DCoreModule *)

- ea: `0x180005de4`
- end: `0x180005e0c`
- name: `??R?$default_delete@VD3DCoreModule@@@std@@QEBAXPEAVD3DCoreModule@@@Z`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000670c`
- `0x1800070a8`
- `0x18000ad90`
- `0x18000f574`

## callees

- `0x180005de4`
- `0x180006004`
- `0x18000b7e0`

## pseudocode

```c
void __fastcall std::default_delete<D3DCoreModule>::operator()(__int64 a1, D3DCoreModule *a2)
{
  if ( a2 )
  {
    D3DCoreModule::~D3DCoreModule(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180005de4  test    rdx, rdx
0x180005de7  jnz     short loc_180005DEA
0x180005de9  retn
0x180005dea  push    rbx
0x180005deb  sub     rsp, 20h
0x180005def  mov     rcx, rdx; this
0x180005df2  mov     rbx, rdx
0x180005df5  call    ??1D3DCoreModule@@QEAA@XZ; D3DCoreModule::~D3DCoreModule(void)
0x180005dfa  mov     edx, 0C0h
0x180005dff  mov     rcx, rbx; Block
0x180005e02  add     rsp, 20h
0x180005e06  pop     rbx
0x180005e07  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
