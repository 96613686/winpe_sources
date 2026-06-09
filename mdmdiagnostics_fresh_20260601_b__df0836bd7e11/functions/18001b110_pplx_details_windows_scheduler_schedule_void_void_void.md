# pplx::details::windows_scheduler::schedule(void (*)(void *),void *)

- ea: `0x18001b110`
- end: `0x18001b1b5`
- name: `?schedule@windows_scheduler@details@pplx@@UEAAXP6AXPEAX@Z0@Z`
- size: `165`
- prototype: `void __fastcall(pplx::details::windows_scheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180019024`
- `0x180019508`
- `0x180019ff4`
- `0x18001afc0`
- `0x18001b110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b191`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b154`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b154`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b165`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b165`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001b17d`

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
0x18001b110  mov     [rsp+arg_0], rbx
0x18001b115  mov     [rsp+arg_8], rsi
0x18001b11a  push    rdi
0x18001b11b  sub     rsp, 50h
0x18001b11f  mov     ecx, 10h; Size
0x18001b124  mov     rdi, r8
0x18001b127  mov     rsi, rdx
0x18001b12a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b12f  mov     [rsp+58h+arg_18], rax
0x18001b134  mov     rbx, rax
0x18001b137  test    rax, rax
0x18001b13a  jz      short loc_18001B145
0x18001b13c  mov     [rax], rsi
0x18001b13f  mov     [rax+8], rdi
0x18001b143  jmp     short loc_18001B147
0x18001b145  xor     ebx, ebx
0x18001b147  xor     r8d, r8d; pcbe
0x18001b14a  lea     rcx, ?DefaultWorkCallback@_Scheduler_Param@details@pplx@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001b151  mov     rdx, rbx; pv
0x18001b154  call    cs:__imp_CreateThreadpoolWork
0x18001b15a  mov     rdi, rax
0x18001b15d  test    rax, rax
0x18001b160  jz      short loc_18001B184
0x18001b162  mov     rcx, rax; pwk
0x18001b165  call    cs:__imp_SubmitThreadpoolWork
0x18001b16b  mov     rcx, rdi
0x18001b16e  mov     rbx, [rsp+58h+arg_0]
0x18001b173  mov     rsi, [rsp+58h+arg_8]
0x18001b178  add     rsp, 50h
0x18001b17c  pop     rdi
0x18001b17d  jmp     cs:__imp_CloseThreadpoolWork
0x18001b184  mov     edx, 10h
0x18001b189  mov     rcx, rbx; Block
0x18001b18c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b191  call    cs:__imp_GetLastError
0x18001b197  mov     edx, eax
0x18001b199  lea     rcx, [rsp+58h+pExceptionObject]
0x18001b19e  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18001b1a3  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18001b1aa  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001b1af  call    _CxxThrowException_0
```
