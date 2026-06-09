# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x1800022a0`
- end: `0x180002306`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800022a0`
- `0x180003010`

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
0x1800022a0  sub     rsp, 28h
0x1800022a4  test    r8, r8
0x1800022a7  jnz     short loc_1800022B0
0x1800022a9  mov     eax, 80070057h
0x1800022ae  jmp     short loc_180002301
0x1800022b0  mov     rax, [rdx]
0x1800022b3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x1800022ba  jnz     short loc_1800022C9
0x1800022bc  mov     rax, [rdx+8]
0x1800022c0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x1800022c7  jz      short loc_1800022E2
0x1800022c9  mov     rax, [rdx]
0x1800022cc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800022d3  jnz     short loc_1800022F5
0x1800022d5  mov     rax, [rdx+8]
0x1800022d9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800022e0  jnz     short loc_1800022F5
0x1800022e2  mov     [r8], rcx
0x1800022e5  mov     rax, [rcx]
0x1800022e8  mov     rax, [rax+8]
0x1800022ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022f1  xor     eax, eax
0x1800022f3  jmp     short loc_180002301
0x1800022f5  mov     qword ptr [r8], 0
0x1800022fc  mov     eax, 80004002h
0x180002301  add     rsp, 28h
0x180002305  retn
```
