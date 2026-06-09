# ATL::CComPtrBase<IDomNode>::Release(void)

- ea: `0x180023b0c`
- end: `0x180023b35`
- name: `?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800229fc`
- `0x180023010`
- `0x1800234b8`
- `0x1800237f8`
- `0x1800253a0`
- `0x180026480`
- `0x180026854`
- `0x180027230`
- `0x180027550`
- `0x180028a50`
- `0x180029098`
- `0x180029240`

## callees

- `0x180023b0c`
- `0x180030010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtrBase<IDomNode>::Release(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180023b0c  sub     rsp, 28h
0x180023b10  mov     rax, rcx
0x180023b13  mov     rcx, [rcx]
0x180023b16  test    rcx, rcx
0x180023b19  jz      short loc_180023B2F
0x180023b1b  mov     qword ptr [rax], 0
0x180023b22  mov     rax, [rcx]
0x180023b25  mov     rax, [rax+10h]
0x180023b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b2e  nop
0x180023b2f  add     rsp, 28h
0x180023b33  retn
```
