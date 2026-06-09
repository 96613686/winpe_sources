# CMFTSimpleDataHandler::~CMFTSimpleDataHandler(void)

- ea: `0x180008e10`
- end: `0x180008e50`
- name: `??1CMFTSimpleDataHandler@@UEAA@XZ`
- size: `64`
- prototype: `void __fastcall(CMFTSimpleDataHandler *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800020e0`
- `0x180004818`
- `0x180008f00`

## callees

- `0x180008e10`
- `0x18001e010`

## pseudocode

```c
void __fastcall CMFTSimpleDataHandler::~CMFTSimpleDataHandler(CMFTSimpleDataHandler *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CMFTSimpleDataHandler::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 2) = 0;
  }
  *(_QWORD *)this = &CMFTDataHandler::`vftable';
}

```

## disassembly

```asm
0x180008e10  push    rbx
0x180008e12  sub     rsp, 20h
0x180008e16  lea     rax, ??_7CMFTSimpleDataHandler@@6B@; const CMFTSimpleDataHandler::`vftable'
0x180008e1d  mov     rbx, rcx
0x180008e20  mov     [rcx], rax
0x180008e23  mov     rcx, [rcx+10h]
0x180008e27  test    rcx, rcx
0x180008e2a  jz      short loc_180008E40
0x180008e2c  mov     rax, [rcx]
0x180008e2f  mov     rax, [rax+10h]
0x180008e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e38  mov     qword ptr [rbx+10h], 0
0x180008e40  lea     rax, ??_7CMFTDataHandler@@6B@; const CMFTDataHandler::`vftable'
0x180008e47  mov     [rbx], rax
0x180008e4a  add     rsp, 20h
0x180008e4e  pop     rbx
0x180008e4f  retn
```
