# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x18000ea60`
- end: `0x18000eac6`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000ea60`
- `0x180023010`

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
0x18000ea60  sub     rsp, 28h
0x18000ea64  test    r8, r8
0x18000ea67  jnz     short loc_18000EA70
0x18000ea69  mov     eax, 80070057h
0x18000ea6e  jmp     short loc_18000EAC1
0x18000ea70  mov     rax, [rdx]
0x18000ea73  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18000ea7a  jnz     short loc_18000EA89
0x18000ea7c  mov     rax, [rdx+8]
0x18000ea80  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x18000ea87  jz      short loc_18000EAA2
0x18000ea89  mov     rax, [rdx]
0x18000ea8c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000ea93  jnz     short loc_18000EAB5
0x18000ea95  mov     rax, [rdx+8]
0x18000ea99  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000eaa0  jnz     short loc_18000EAB5
0x18000eaa2  mov     [r8], rcx
0x18000eaa5  mov     rax, [rcx]
0x18000eaa8  mov     rax, [rax+8]
0x18000eaac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eab1  xor     eax, eax
0x18000eab3  jmp     short loc_18000EAC1
0x18000eab5  mov     qword ptr [r8], 0
0x18000eabc  mov     eax, 80004002h
0x18000eac1  add     rsp, 28h
0x18000eac5  retn
```
