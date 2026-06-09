# pplx::details::windows_scheduler::schedule(void (*)(void *),void *)

- ea: `0x18001b1f0`
- end: `0x18001b295`
- name: `?schedule@windows_scheduler@details@pplx@@UEAAXP6AXPEAX@Z0@Z`
- size: `165`
- prototype: `void __fastcall(pplx::details::windows_scheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1800190a4`
- `0x180019588`
- `0x18001a084`
- `0x18001b0a0`
- `0x18001b1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b271`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b234`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b234`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b245`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b245`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001b25d`

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
    operator delete(v6);
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
0x18001b1f0  mov     [rsp+arg_0], rbx
0x18001b1f5  mov     [rsp+arg_8], rsi
0x18001b1fa  push    rdi
0x18001b1fb  sub     rsp, 50h
0x18001b1ff  mov     ecx, 10h; Size
0x18001b204  mov     rdi, r8
0x18001b207  mov     rsi, rdx
0x18001b20a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b20f  mov     [rsp+58h+arg_18], rax
0x18001b214  mov     rbx, rax
0x18001b217  test    rax, rax
0x18001b21a  jz      short loc_18001B225
0x18001b21c  mov     [rax], rsi
0x18001b21f  mov     [rax+8], rdi
0x18001b223  jmp     short loc_18001B227
0x18001b225  xor     ebx, ebx
0x18001b227  xor     r8d, r8d; pcbe
0x18001b22a  lea     rcx, ?DefaultWorkCallback@_Scheduler_Param@details@pplx@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001b231  mov     rdx, rbx; pv
0x18001b234  call    cs:__imp_CreateThreadpoolWork
0x18001b23a  mov     rdi, rax
0x18001b23d  test    rax, rax
0x18001b240  jz      short loc_18001B264
0x18001b242  mov     rcx, rax; pwk
0x18001b245  call    cs:__imp_SubmitThreadpoolWork
0x18001b24b  mov     rcx, rdi
0x18001b24e  mov     rbx, [rsp+58h+arg_0]
0x18001b253  mov     rsi, [rsp+58h+arg_8]
0x18001b258  add     rsp, 50h
0x18001b25c  pop     rdi
0x18001b25d  jmp     cs:__imp_CloseThreadpoolWork
0x18001b264  mov     edx, 10h
0x18001b269  mov     rcx, rbx; Block
0x18001b26c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b271  call    cs:__imp_GetLastError
0x18001b277  mov     edx, eax
0x18001b279  lea     rcx, [rsp+58h+pExceptionObject]
0x18001b27e  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18001b283  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18001b28a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001b28f  call    _CxxThrowException_0
```
