# ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(IDomNode *)

- ea: `0x180024028`
- end: `0x180024052`
- name: `??0?$CComPtrBase@UIDomNode@@@ATL@@IEAA@PEAUIDomNode@@@Z`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180023c20`
- `0x180023fcc`
- `0x180024260`
- `0x18002559c`
- `0x180025be0`
- `0x18002842c`
- `0x180029240`
- `0x18002d810`

## callees

- `0x180024028`
- `0x180030010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(_QWORD *a1, __int64 a2)
{
  *a1 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  return a1;
}

```

## disassembly

```asm
0x180024028  push    rbx
0x18002402a  sub     rsp, 20h
0x18002402e  mov     rbx, rcx
0x180024031  mov     [rcx], rdx
0x180024034  test    rdx, rdx
0x180024037  jz      short loc_180024048
0x180024039  mov     rax, [rdx]
0x18002403c  mov     rcx, rdx
0x18002403f  mov     rax, [rax+8]
0x180024043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024048  mov     rax, rbx
0x18002404b  add     rsp, 20h
0x18002404f  pop     rbx
0x180024050  retn
```
