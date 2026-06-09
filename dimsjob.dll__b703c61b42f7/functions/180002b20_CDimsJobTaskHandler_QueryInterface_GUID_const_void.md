# CDimsJobTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180002b20`
- end: `0x180002b9b`
- name: `?QueryInterface@CDimsJobTaskHandler@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `123`
- prototype: `__int64 __fastcall(CDimsJobTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002b20`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CDimsJobTaskHandler::QueryInterface(CDimsJobTaskHandler *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  __int64 result; // rax
  __int64 v7; // rax

  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ITaskHandler.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITaskHandler.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ITaskHandler.Data4;
  if ( !v4 )
    goto LABEL_4;
  v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( v7 )
  {
    result = 2147500034LL;
    *a3 = 0;
  }
  else
  {
LABEL_4:
    (*(void (__fastcall **)(CDimsJobTaskHandler *))(*(_QWORD *)this + 8LL))(this);
    result = 0;
    *a3 = this;
  }
  return result;
}

```

## disassembly

```asm
0x180002b20  mov     [rsp+arg_0], rbx
0x180002b25  push    rdi
0x180002b26  sub     rsp, 20h
0x180002b2a  mov     rax, [rdx]
0x180002b2d  mov     rdi, r8
0x180002b30  sub     rax, qword ptr cs:IID_ITaskHandler.Data1
0x180002b37  mov     rbx, rcx
0x180002b3a  jnz     short loc_180002B47
0x180002b3c  mov     rax, [rdx+8]
0x180002b40  sub     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180002b47  test    rax, rax
0x180002b4a  jnz     short loc_180002B68
0x180002b4c  mov     rax, [rcx]
0x180002b4f  mov     rax, [rax+8]
0x180002b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b58  xor     eax, eax
0x180002b5a  mov     [rdi], rbx
0x180002b5d  mov     rbx, [rsp+28h+arg_0]
0x180002b62  add     rsp, 20h
0x180002b66  pop     rdi
0x180002b67  retn
0x180002b68  mov     rax, [rdx]
0x180002b6b  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180002b72  jnz     short loc_180002B7F
0x180002b74  mov     rax, [rdx+8]
0x180002b78  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180002b7f  test    rax, rax
0x180002b82  jz      short loc_180002B4C
0x180002b84  mov     rbx, [rsp+28h+arg_0]
0x180002b89  mov     eax, 80004002h
0x180002b8e  mov     qword ptr [r8], 0
0x180002b95  add     rsp, 20h
0x180002b99  pop     rdi
0x180002b9a  retn
```
