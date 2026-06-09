# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180002310`
- end: `0x180002376`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002310`
- `0x180004010`

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
0x180002310  sub     rsp, 28h
0x180002314  test    r8, r8
0x180002317  jnz     short loc_180002320
0x180002319  mov     eax, 80070057h
0x18000231e  jmp     short loc_180002371
0x180002320  mov     rax, [rdx]
0x180002323  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18000232a  jnz     short loc_180002339
0x18000232c  mov     rax, [rdx+8]
0x180002330  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180002337  jz      short loc_180002352
0x180002339  mov     rax, [rdx]
0x18000233c  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180002343  jnz     short loc_180002365
0x180002345  mov     rax, [rdx+8]
0x180002349  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180002350  jnz     short loc_180002365
0x180002352  mov     [r8], rcx
0x180002355  mov     rax, [rcx]
0x180002358  mov     rax, [rax+8]
0x18000235c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002361  xor     eax, eax
0x180002363  jmp     short loc_180002371
0x180002365  mov     qword ptr [r8], 0
0x18000236c  mov     eax, 80004002h
0x180002371  add     rsp, 28h
0x180002375  retn
```
