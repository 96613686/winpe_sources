# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x1800056e0`
- end: `0x180005746`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800056e0`
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
0x1800056e0  sub     rsp, 28h
0x1800056e4  test    r8, r8
0x1800056e7  jnz     short loc_1800056F0
0x1800056e9  mov     eax, 80070057h
0x1800056ee  jmp     short loc_180005741
0x1800056f0  mov     rax, [rdx]
0x1800056f3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x1800056fa  jnz     short loc_180005709
0x1800056fc  mov     rax, [rdx+8]
0x180005700  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180005707  jz      short loc_180005722
0x180005709  mov     rax, [rdx]
0x18000570c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180005713  jnz     short loc_180005735
0x180005715  mov     rax, [rdx+8]
0x180005719  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180005720  jnz     short loc_180005735
0x180005722  mov     [r8], rcx
0x180005725  mov     rax, [rcx]
0x180005728  mov     rax, [rax+8]
0x18000572c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005731  xor     eax, eax
0x180005733  jmp     short loc_180005741
0x180005735  mov     qword ptr [r8], 0
0x18000573c  mov     eax, 80004002h
0x180005741  add     rsp, 28h
0x180005745  retn
```
