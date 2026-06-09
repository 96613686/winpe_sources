# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180001bc0`
- end: `0x180001c24`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `100`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001bc0`
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
0x180001bc0  sub     rsp, 28h
0x180001bc4  test    r8, r8
0x180001bc7  jnz     short loc_180001BD0
0x180001bc9  mov     eax, 80070057h
0x180001bce  jmp     short loc_180001C1E
0x180001bd0  mov     rax, [rdx]
0x180001bd3  cmp     rax, qword ptr cs:IID_ITaskHandler.Data1
0x180001bda  jnz     short loc_180001BE9
0x180001bdc  mov     rax, [rdx+8]
0x180001be0  cmp     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180001be7  jz      short loc_180001C02
0x180001be9  mov     rax, [rdx]
0x180001bec  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180001bf3  jnz     short loc_180001C15
0x180001bf5  mov     rax, [rdx+8]
0x180001bf9  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180001c00  jnz     short loc_180001C15
0x180001c02  mov     [r8], rcx
0x180001c05  mov     rax, [rcx]
0x180001c08  mov     rax, [rax+8]
0x180001c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c11  xor     eax, eax
0x180001c13  jmp     short loc_180001C1E
0x180001c15  and     qword ptr [r8], 0
0x180001c19  mov     eax, 80004002h
0x180001c1e  add     rsp, 28h
0x180001c22  retn
```
