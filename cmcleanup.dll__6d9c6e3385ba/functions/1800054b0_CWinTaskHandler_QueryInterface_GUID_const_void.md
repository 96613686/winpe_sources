# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x1800054b0`
- end: `0x180005516`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800054b0`
- `0x180009010`

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
0x1800054b0  sub     rsp, 28h
0x1800054b4  test    r8, r8
0x1800054b7  jnz     short loc_1800054C0
0x1800054b9  mov     eax, 80070057h
0x1800054be  jmp     short loc_180005511
0x1800054c0  mov     rax, [rdx]
0x1800054c3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x1800054ca  jnz     short loc_1800054D9
0x1800054cc  mov     rax, [rdx+8]
0x1800054d0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x1800054d7  jz      short loc_1800054F2
0x1800054d9  mov     rax, [rdx]
0x1800054dc  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800054e3  jnz     short loc_180005505
0x1800054e5  mov     rax, [rdx+8]
0x1800054e9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800054f0  jnz     short loc_180005505
0x1800054f2  mov     [r8], rcx
0x1800054f5  mov     rax, [rcx]
0x1800054f8  mov     rax, [rax+8]
0x1800054fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005501  xor     eax, eax
0x180005503  jmp     short loc_180005511
0x180005505  mov     qword ptr [r8], 0
0x18000550c  mov     eax, 80004002h
0x180005511  add     rsp, 28h
0x180005515  retn
```
