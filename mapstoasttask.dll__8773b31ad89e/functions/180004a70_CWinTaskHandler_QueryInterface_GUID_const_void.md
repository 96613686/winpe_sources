# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180004a70`
- end: `0x180004ad6`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004a70`
- `0x18000a010`

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
0x180004a70  sub     rsp, 28h
0x180004a74  test    r8, r8
0x180004a77  jnz     short loc_180004A80
0x180004a79  mov     eax, 80070057h
0x180004a7e  jmp     short loc_180004AD1
0x180004a80  mov     rax, [rdx]
0x180004a83  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x180004a8a  jnz     short loc_180004A99
0x180004a8c  mov     rax, [rdx+8]
0x180004a90  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180004a97  jz      short loc_180004AB2
0x180004a99  mov     rax, [rdx]
0x180004a9c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180004aa3  jnz     short loc_180004AC5
0x180004aa5  mov     rax, [rdx+8]
0x180004aa9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180004ab0  jnz     short loc_180004AC5
0x180004ab2  mov     [r8], rcx
0x180004ab5  mov     rax, [rcx]
0x180004ab8  mov     rax, [rax+8]
0x180004abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ac1  xor     eax, eax
0x180004ac3  jmp     short loc_180004AD1
0x180004ac5  mov     qword ptr [r8], 0
0x180004acc  mov     eax, 80004002h
0x180004ad1  add     rsp, 28h
0x180004ad5  retn
```
