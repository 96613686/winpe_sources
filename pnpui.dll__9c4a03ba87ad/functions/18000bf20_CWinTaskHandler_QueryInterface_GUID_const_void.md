# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x18000bf20`
- end: `0x18000bf86`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000bf20`
- `0x18000e010`

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
0x18000bf20  sub     rsp, 28h
0x18000bf24  test    r8, r8
0x18000bf27  jnz     short loc_18000BF30
0x18000bf29  mov     eax, 80070057h
0x18000bf2e  jmp     short loc_18000BF81
0x18000bf30  mov     rax, [rdx]
0x18000bf33  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18000bf3a  jnz     short loc_18000BF49
0x18000bf3c  mov     rax, [rdx+8]
0x18000bf40  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x18000bf47  jz      short loc_18000BF62
0x18000bf49  mov     rax, [rdx]
0x18000bf4c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000bf53  jnz     short loc_18000BF75
0x18000bf55  mov     rax, [rdx+8]
0x18000bf59  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000bf60  jnz     short loc_18000BF75
0x18000bf62  mov     [r8], rcx
0x18000bf65  mov     rax, [rcx]
0x18000bf68  mov     rax, [rax+8]
0x18000bf6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf71  xor     eax, eax
0x18000bf73  jmp     short loc_18000BF81
0x18000bf75  mov     qword ptr [r8], 0
0x18000bf7c  mov     eax, 80004002h
0x18000bf81  add     rsp, 28h
0x18000bf85  retn
```
