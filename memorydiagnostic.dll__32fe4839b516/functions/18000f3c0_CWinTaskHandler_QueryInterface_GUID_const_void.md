# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f3c0`
- end: `0x18000f424`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000f3c0`
- `0x180024010`

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
0x18000f3c0  sub     rsp, 28h
0x18000f3c4  test    r8, r8
0x18000f3c7  jnz     short loc_18000F3D0
0x18000f3c9  mov     eax, 80070057h
0x18000f3ce  jmp     short loc_18000F41E
0x18000f3d0  mov     rax, [rdx]
0x18000f3d3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18000f3da  jnz     short loc_18000F3E9
0x18000f3dc  mov     rax, [rdx+8]
0x18000f3e0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x18000f3e7  jz      short loc_18000F402
0x18000f3e9  mov     rax, [rdx]
0x18000f3ec  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000f3f3  jnz     short loc_18000F415
0x18000f3f5  mov     rax, [rdx+8]
0x18000f3f9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000f400  jnz     short loc_18000F415
0x18000f402  mov     [r8], rcx
0x18000f405  mov     rax, [rcx]
0x18000f408  mov     rax, [rax+8]
0x18000f40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f411  xor     eax, eax
0x18000f413  jmp     short loc_18000F41E
0x18000f415  and     qword ptr [r8], 0
0x18000f419  mov     eax, 80004002h
0x18000f41e  add     rsp, 28h
0x18000f422  retn
```
