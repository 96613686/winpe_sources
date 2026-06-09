# azure::storage::core::timer_handler::stop_timer(void)

- ea: `0x180077660`
- end: `0x18007778d`
- name: `?stop_timer@timer_handler@core@storage@azure@@QEAAXXZ`
- size: `301`
- prototype: `void __fastcall(azure::storage::core::timer_handler *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180076920`
- `0x180076e90`

## callees

- `0x180055ae0`
- `0x180077660`
- `0x1800a9f05`
- `0x1800a9f11`
- `0x1800a9f1d`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800776d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800776d0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800776c1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800776e5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800776c1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800776e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall azure::storage::core::timer_handler::stop_timer(azure::storage::core::timer_handler *this)
{
  char *v2; // rbx
  HANDLE *v3; // rdi
  volatile signed __int32 *v4; // rdi

  v2 = (char *)this + 80;
  if ( Mtx_lock_0((azure::storage::core::timer_handler *)((char *)this + 80)) )
  {
    std::_Throw_Cpp_error(5);
    JUMPOUT(0x18007778CLL);
  }
  if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v2 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  if ( *((_BYTE *)this + 176) )
  {
    v3 = (HANDLE *)*((_QWORD *)this + 20);
    if ( v3 )
    {
      if ( !DeleteTimerQueueTimer(0, *v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      {
        while ( GetLastError() != 997 && !DeleteTimerQueueTimer(0, *v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
          ;
      }
      if ( !*(_BYTE *)(*((_QWORD *)this + 8) + 112LL) && !*(_BYTE *)(*((_QWORD *)this + 8) + 113LL) )
        pplx::task_completion_event<unsigned __int64>::_CancelInternal();
      *((_QWORD *)this + 20) = 0;
      v4 = (volatile signed __int32 *)*((_QWORD *)this + 21);
      *((_QWORD *)this + 21) = 0;
      if ( v4 )
      {
        if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
          if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
        }
      }
    }
  }
  Mtx_unlock_0((_Mtx_t)v2);
}

```

## disassembly

```asm
0x180077660  push    rbx
0x180077662  push    rbp
0x180077663  push    rsi
0x180077664  push    rdi
0x180077665  sub     rsp, 28h
0x180077669  mov     rsi, rcx
0x18007766c  lea     rbx, [rcx+50h]
0x180077670  mov     [rsp+48h+arg_0], rbx
0x180077675  mov     rcx, rbx; _Mtx_t
0x180077678  call    _Mtx_lock_0
0x18007767d  test    eax, eax
0x18007767f  jnz     loc_180077782
0x180077685  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18007768c  jz      loc_180077770
0x180077692  movzx   eax, byte ptr [rsi+0B0h]
0x180077699  nop
0x18007769a  test    al, al
0x18007769c  jz      loc_180077760
0x1800776a2  mov     rdi, [rsi+0A0h]
0x1800776a9  test    rdi, rdi
0x1800776ac  jz      loc_180077760
0x1800776b2  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800776b9  mov     r8, rbp; CompletionEvent
0x1800776bc  mov     rdx, [rdi]; Timer
0x1800776bf  xor     ecx, ecx; TimerQueue
0x1800776c1  call    cs:__imp_DeleteTimerQueueTimer
0x1800776c7  test    eax, eax
0x1800776c9  jnz     short loc_1800776EF
0x1800776cb  nop     dword ptr [rax+rax+00h]
0x1800776d0  call    cs:__imp_GetLastError
0x1800776d6  cmp     eax, 3E5h
0x1800776db  jz      short loc_1800776EF
0x1800776dd  mov     r8, rbp; CompletionEvent
0x1800776e0  mov     rdx, [rdi]; Timer
0x1800776e3  xor     ecx, ecx; TimerQueue
0x1800776e5  call    cs:__imp_DeleteTimerQueueTimer
0x1800776eb  test    eax, eax
0x1800776ed  jz      short loc_1800776D0
0x1800776ef  lea     rcx, [rsi+40h]
0x1800776f3  mov     rax, [rcx]
0x1800776f6  movzx   edx, byte ptr [rax+70h]
0x1800776fa  nop
0x1800776fb  test    dl, dl
0x1800776fd  jnz     short loc_180077710
0x1800776ff  mov     rax, [rcx]
0x180077702  movzx   edx, byte ptr [rax+71h]
0x180077706  nop
0x180077707  test    dl, dl
0x180077709  jnz     short loc_180077710
0x18007770b  call    ?_CancelInternal@?$task_completion_event@_K@pplx@@AEBA_NXZ; pplx::task_completion_event<unsigned __int64>::_CancelInternal(void)
0x180077710  xor     eax, eax
0x180077712  mov     [rsi+0A0h], rax
0x180077719  mov     rdi, [rsi+0A8h]
0x180077720  mov     [rsi+0A8h], rax
0x180077727  test    rdi, rdi
0x18007772a  jz      short loc_180077760
0x18007772c  mov     eax, ebp
0x18007772e  lock xadd [rdi+8], eax
0x180077733  cmp     eax, 1
0x180077736  jnz     short loc_180077760
0x180077738  mov     rax, [rdi]
0x18007773b  mov     rcx, rdi
0x18007773e  mov     rax, [rax]
0x180077741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077746  lock xadd [rdi+0Ch], ebp
0x18007774b  cmp     ebp, 1
0x18007774e  jnz     short loc_180077760
0x180077750  mov     rax, [rdi]
0x180077753  mov     rcx, rdi
0x180077756  mov     rax, [rax+8]
0x18007775a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007775f  nop
0x180077760  mov     rcx, rbx; _Mtx_t
0x180077763  add     rsp, 28h
0x180077767  pop     rdi
0x180077768  pop     rsi
0x180077769  pop     rbp
0x18007776a  pop     rbx
0x18007776b  jmp     _Mtx_unlock_0
0x180077770  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180077777  mov     ecx, 6; int
0x18007777c  call    ?_Throw_Cpp_error@std@@YAXH@Z_0; std::_Throw_Cpp_error(int)
0x180077781  int     3; Trap to Debugger
0x180077782  mov     ecx, 5; int
0x180077787  call    ?_Throw_Cpp_error@std@@YAXH@Z_0; std::_Throw_Cpp_error(int)
```
