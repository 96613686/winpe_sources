# ATL::CComQIPtr<ISimpleTableController,&_GUID const IID_ISimpleTableController>::CComQIPtr<ISimpleTableController,&_GUID const IID_ISimpleTableController>(IUnknown *)

- ea: `0x180002b50`
- end: `0x180002b89`
- name: `??0?$CComQIPtr@UISimpleTableController@@$1?IID_ISimpleTableController@@3U_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003370`
- `0x1800147c0`

## callees

- `0x180002b50`
- `0x180030010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComQIPtr<ISimpleTableController,&_GUID const IID_ISimpleTableController>::CComQIPtr<ISimpleTableController,&_GUID const IID_ISimpleTableController>(
        _QWORD *a1,
        void (__fastcall ***a2)(_QWORD, GUID *, _QWORD *))
{
  *a1 = 0;
  if ( a2 )
    (**a2)(a2, &IID_ISimpleTableController, a1);
  return a1;
}

```

## disassembly

```asm
0x180002b50  push    rbx
0x180002b52  sub     rsp, 20h
0x180002b56  mov     qword ptr [rcx], 0
0x180002b5d  mov     r9, rdx
0x180002b60  mov     rbx, rcx
0x180002b63  test    rdx, rdx
0x180002b66  jz      short loc_180002B80
0x180002b68  mov     rax, [rdx]
0x180002b6b  mov     r8, rcx
0x180002b6e  lea     rdx, IID_ISimpleTableController
0x180002b75  mov     rcx, r9
0x180002b78  mov     rax, [rax]
0x180002b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b80  mov     rax, rbx
0x180002b83  add     rsp, 20h
0x180002b87  pop     rbx
0x180002b88  retn
```
