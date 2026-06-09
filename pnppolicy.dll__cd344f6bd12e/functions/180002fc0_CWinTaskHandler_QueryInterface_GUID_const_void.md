# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180002fc0`
- end: `0x180003026`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002fc0`
- `0x18000b010`

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
0x180002fc0  sub     rsp, 28h
0x180002fc4  test    r8, r8
0x180002fc7  jnz     short loc_180002FD0
0x180002fc9  mov     eax, 80070057h
0x180002fce  jmp     short loc_180003021
0x180002fd0  mov     rax, [rdx]
0x180002fd3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x180002fda  jnz     short loc_180002FE9
0x180002fdc  mov     rax, [rdx+8]
0x180002fe0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180002fe7  jz      short loc_180003002
0x180002fe9  mov     rax, [rdx]
0x180002fec  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180002ff3  jnz     short loc_180003015
0x180002ff5  mov     rax, [rdx+8]
0x180002ff9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180003000  jnz     short loc_180003015
0x180003002  mov     [r8], rcx
0x180003005  mov     rax, [rcx]
0x180003008  mov     rax, [rax+8]
0x18000300c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003011  xor     eax, eax
0x180003013  jmp     short loc_180003021
0x180003015  mov     qword ptr [r8], 0
0x18000301c  mov     eax, 80004002h
0x180003021  add     rsp, 28h
0x180003025  retn
```
