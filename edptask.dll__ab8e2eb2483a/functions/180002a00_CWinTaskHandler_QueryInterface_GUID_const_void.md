# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180002a00`
- end: `0x180002a66`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002a00`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::QueryInterface(CWinTaskHandler *this, const struct _GUID *a2, void **a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITaskHandler.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ITaskHandler.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180002a00  sub     rsp, 28h
0x180002a04  test    r8, r8
0x180002a07  jnz     short loc_180002A10
0x180002a09  mov     eax, 80070057h
0x180002a0e  jmp     short loc_180002A61
0x180002a10  mov     rax, [rdx]
0x180002a13  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x180002a1a  jnz     short loc_180002A29
0x180002a1c  mov     rax, [rdx+8]
0x180002a20  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180002a27  jz      short loc_180002A42
0x180002a29  mov     rax, [rdx]
0x180002a2c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180002a33  jnz     short loc_180002A55
0x180002a35  mov     rax, [rdx+8]
0x180002a39  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180002a40  jnz     short loc_180002A55
0x180002a42  mov     [r8], rcx
0x180002a45  mov     rax, [rcx]
0x180002a48  mov     rax, [rax+8]
0x180002a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a51  xor     eax, eax
0x180002a53  jmp     short loc_180002A61
0x180002a55  mov     qword ptr [r8], 0
0x180002a5c  mov     eax, 80004002h
0x180002a61  add     rsp, 28h
0x180002a65  retn
```
