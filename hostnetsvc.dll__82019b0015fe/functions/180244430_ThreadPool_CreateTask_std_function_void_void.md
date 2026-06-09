# ThreadPool::CreateTask(std::function<void (void)>)

- ea: `0x180244430`
- end: `0x180244560`
- name: `?CreateTask@ThreadPool@@QEAAXV?$function@$$A6AXXZ@std@@@Z`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010e8bc`
- `0x1801f5050`
- `0x180257d58`

## callees

- `0x18005f59c`
- `0x180061240`
- `0x18007e864`
- `0x1800cfdc4`
- `0x1802443e8`
- `0x180244430`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802444ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802444ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180244498`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180244498`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1802444a9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1802444a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1802444b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1802444b2`

## string_xrefs

- `0x180244519`: `Unable to create thread pool task`
- `0x18024453c`: `Unable to create thread pool task. Thread pool not initialized`
- `0x180244525`: `onecore\vm\dv\net\hns\service\common\helperlib\src\threadpool.cpp`
- `0x18024454e`: `onecore\vm\dv\net\hns\service\common\helperlib\src\threadpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ThreadPool::CreateTask(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rdi
  __int64 (__fastcall ***v5)(_QWORD, _QWORD *); // rcx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // rcx
  signed int LastError; // ebx
  unsigned int v11; // eax
  const char *v12; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !*(_QWORD *)(a1 + 8) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\threadpool.cpp",
      (const char *)0x10DD,
      (unsigned int)"Unable to create thread pool task. Thread pool not initialized",
      v12);
  v4 = operator new(0x40u);
  v4[7] = 0;
  v5 = *(__int64 (__fastcall ****)(_QWORD, _QWORD *))(a2 + 56);
  if ( v5 )
    v4[7] = (**v5)(v5, v4);
  ThreadpoolWork = CreateThreadpoolWork(ThreadPool::DefaultWorkCallback, v4, (PTP_CALLBACK_ENVIRON)(a1 + 16));
  v7 = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    LastError = GetLastError();
    std::function<void (void)>::`scalar deleting destructor'(v4);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = wil::verify_hresult<long>((unsigned int)LastError);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\threadpool.cpp",
      (const char *)v11,
      (int)"Unable to create thread pool task",
      v12);
  }
  SubmitThreadpoolWork(ThreadpoolWork);
  CloseThreadpoolWork(v7);
  v9 = *(_QWORD *)(a2 + 56);
  if ( v9 )
  {
    LOBYTE(v8) = v9 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, v8);
    *(_QWORD *)(a2 + 56) = 0;
  }
}

```

## disassembly

```asm
0x180244430  mov     [rsp+arg_10], rbx
0x180244435  mov     [rsp+arg_18], rsi
0x18024443a  mov     [rsp+arg_8], rdx
0x18024443f  push    rdi
0x180244440  sub     rsp, 30h
0x180244444  mov     rbx, rdx
0x180244447  mov     rsi, rcx
0x18024444a  cmp     qword ptr [rcx+8], 0
0x18024444f  jz      loc_180244537
0x180244455  mov     ecx, 40h ; '@'; Size
0x18024445a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18024445f  mov     rdi, rax
0x180244462  mov     [rsp+38h+arg_0], rax
0x180244467  mov     qword ptr [rax+38h], 0
0x18024446f  mov     rcx, [rbx+38h]
0x180244473  test    rcx, rcx
0x180244476  jz      short loc_18024448A
0x180244478  mov     rdx, [rcx]
0x18024447b  mov     rax, [rdx]
0x18024447e  mov     rdx, rdi
0x180244481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180244486  mov     [rdi+38h], rax
0x18024448a  lea     r8, [rsi+10h]; pcbe
0x18024448e  mov     rdx, rdi; pv
0x180244491  lea     rcx, ?DefaultWorkCallback@ThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180244498  call    cs:__imp_CreateThreadpoolWork
0x18024449e  mov     rsi, rax
0x1802444a1  test    rax, rax
0x1802444a4  jz      short loc_1802444EC
0x1802444a6  mov     rcx, rax; pwk
0x1802444a9  call    cs:__imp_SubmitThreadpoolWork
0x1802444af  mov     rcx, rsi; pwk
0x1802444b2  call    cs:__imp_CloseThreadpoolWork
0x1802444b8  nop
0x1802444b9  mov     rcx, [rbx+38h]
0x1802444bd  test    rcx, rcx
0x1802444c0  jz      short loc_1802444DC
0x1802444c2  mov     rax, [rcx]
0x1802444c5  cmp     rcx, rbx
0x1802444c8  setnz   dl
0x1802444cb  mov     rax, [rax+20h]
0x1802444cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802444d4  mov     qword ptr [rbx+38h], 0
0x1802444dc  mov     rbx, [rsp+38h+arg_10]
0x1802444e1  mov     rsi, [rsp+38h+arg_18]
0x1802444e6  add     rsp, 30h
0x1802444ea  pop     rdi
0x1802444eb  retn
0x1802444ec  call    cs:__imp_GetLastError
0x1802444f2  nop
0x1802444f3  mov     ebx, eax
0x1802444f5  mov     rcx, rdi; void *
0x1802444f8  call    ??_G?$function@$$A6AXXZ@std@@QEAAPEAXI@Z; std::function<void (void)>::`scalar deleting destructor'(uint)
0x1802444fd  test    ebx, ebx
0x1802444ff  jle     short loc_18024450A
0x180244501  movzx   ebx, bx
0x180244504  or      ebx, 80070000h
0x18024450a  mov     ecx, ebx
0x18024450c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180244511  mov     r9d, eax; char *
0x180244514  mov     rcx, [rsp+38h]; this
0x180244519  lea     rax, aUnableToCreate_0; "Unable to create thread pool task"
0x180244520  mov     qword ptr [rsp+38h+var_18], rax; int
0x180244525  lea     r8, aOnecoreVmDvNet_199; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x18024452c  mov     edx, 70h ; 'p'; void *
0x180244531  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180244537  mov     rcx, [rsp+38h]; this
0x18024453c  lea     rax, aUnableToCreate_3; "Unable to create thread pool task. Thre"...
0x180244543  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x180244548  mov     r9d, 10DDh; char *
0x18024454e  lea     r8, aOnecoreVmDvNet_199; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180244555  mov     edx, 63h ; 'c'; void *
0x18024455a  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
