# pplx::details::windows_scheduler::schedule(void (*)(void *),void *)

- ea: `0x180014310`
- end: `0x1800143b5`
- name: `?schedule@windows_scheduler@details@pplx@@UEAAXP6AXPEAX@Z0@Z`
- size: `165`
- prototype: `void __fastcall(pplx::details::windows_scheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000e430`
- `0x18000e46c`
- `0x18000ec30`
- `0x18000f910`
- `0x180014310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014391`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180014365`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180014365`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180014354`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180014354`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001437d`

## pseudocode

```c
void __fastcall pplx::details::windows_scheduler::schedule(
        pplx::details::windows_scheduler *this,
        void (*a2)(void *),
        void *a3)
{
  _QWORD *v5; // rax
  void *v6; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v8; // rdi
  DWORD LastError; // eax
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  v5 = operator new(0x10u);
  v6 = v5;
  if ( v5 )
  {
    *v5 = a2;
    v5[1] = a3;
  }
  else
  {
    v6 = 0;
  }
  ThreadpoolWork = CreateThreadpoolWork(pplx::details::_Scheduler_Param::DefaultWorkCallback, v6, 0);
  v8 = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    operator delete(v6, (const struct std::nothrow_t *)0x10);
    LastError = GetLastError();
    utility::details::create_system_error(pExceptionObject, LastError);
    throw (std::system_error *)pExceptionObject;
  }
  SubmitThreadpoolWork(ThreadpoolWork);
  CloseThreadpoolWork(v8);
}

```

## disassembly

```asm
0x180014310  mov     [rsp+arg_0], rbx
0x180014315  mov     [rsp+arg_8], rsi
0x18001431a  push    rdi
0x18001431b  sub     rsp, 50h
0x18001431f  mov     ecx, 10h; Size
0x180014324  mov     rdi, r8
0x180014327  mov     rsi, rdx
0x18001432a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001432f  mov     [rsp+58h+arg_18], rax
0x180014334  mov     rbx, rax
0x180014337  test    rax, rax
0x18001433a  jz      short loc_180014345
0x18001433c  mov     [rax], rsi
0x18001433f  mov     [rax+8], rdi
0x180014343  jmp     short loc_180014347
0x180014345  xor     ebx, ebx
0x180014347  xor     r8d, r8d; pcbe
0x18001434a  lea     rcx, ?DefaultWorkCallback@_Scheduler_Param@details@pplx@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180014351  mov     rdx, rbx; pv
0x180014354  call    cs:__imp_CreateThreadpoolWork
0x18001435a  mov     rdi, rax
0x18001435d  test    rax, rax
0x180014360  jz      short loc_180014384
0x180014362  mov     rcx, rax; pwk
0x180014365  call    cs:__imp_SubmitThreadpoolWork
0x18001436b  mov     rcx, rdi
0x18001436e  mov     rbx, [rsp+58h+arg_0]
0x180014373  mov     rsi, [rsp+58h+arg_8]
0x180014378  add     rsp, 50h
0x18001437c  pop     rdi
0x18001437d  jmp     cs:__imp_CloseThreadpoolWork
0x180014384  mov     edx, 10h; struct std::nothrow_t *
0x180014389  mov     rcx, rbx; void *
0x18001438c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014391  call    cs:__imp_GetLastError
0x180014397  mov     edx, eax
0x180014399  lea     rcx, [rsp+58h+pExceptionObject]
0x18001439e  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x1800143a3  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x1800143aa  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800143af  call    _CxxThrowException_0
```
