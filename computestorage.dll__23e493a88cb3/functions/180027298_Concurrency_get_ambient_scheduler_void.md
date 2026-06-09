# Concurrency::get_ambient_scheduler(void)

- ea: `0x180027298`
- end: `0x18002737c`
- name: `?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ`
- size: `228`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180021d60`
- `0x180026c14`

## callees

- `0x180002690`
- `0x180002b54`
- `0x180003838`
- `0x180003990`
- `0x1800039f8`
- `0x180027298`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800272c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800272c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002731d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002731d`

## pseudocode

```c
__int64 Concurrency::get_ambient_scheduler()
{
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(
          &`Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_Flag,
          0,
          &fPending,
          0) )
    __fastfail(5u);
  if ( fPending )
  {
    if ( __TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL) )
    {
      Init_thread_header(&__TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA);
      if ( __TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA == -1 )
      {
        atexit(`Concurrency::details::_GetStaticAmbientSchedulerStorage'::`2'::`dynamic atexit destructor for '_S_scheduler'');
        Init_thread_footer(&__TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA);
      }
    }
    `Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_S_scheduler_address = (__int64)&`Concurrency::details::_GetStaticAmbientSchedulerStorage'::`2'::_S_scheduler;
    if ( !InitOnceComplete(&`Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_Flag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  return `Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_S_scheduler_address;
}

```

## disassembly

```asm
0x180027298  sub     rsp, 48h
0x18002729c  mov     rax, cs:__security_cookie
0x1800272a3  xor     rax, rsp
0x1800272a6  mov     [rsp+48h+var_10], rax
0x1800272ab  xor     r9d, r9d; lpContext
0x1800272ae  mov     [rsp+48h+fPending], 0
0x1800272b6  lea     r8, [rsp+48h+fPending]; fPending
0x1800272bb  xor     edx, edx; dwFlags
0x1800272bd  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x1800272c4  call    cs:__imp___std_init_once_begin_initialize
0x1800272cb  nop     dword ptr [rax+rax+00h]
0x1800272d0  test    eax, eax
0x1800272d2  jnz     short loc_1800272D9
0x1800272d4  lea     ecx, [rax+5]
0x1800272d7  int     29h; Win8: RtlFailFast(ecx)
0x1800272d9  cmp     [rsp+48h+fPending], 0
0x1800272de  jz      short loc_18002732D
0x1800272e0  mov     ecx, cs:_tls_index
0x1800272e6  mov     rax, gs:58h
0x1800272ef  mov     edx, 10h
0x1800272f4  mov     rax, [rax+rcx*8]
0x1800272f8  mov     eax, [rdx+rax]
0x1800272fb  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, eax
0x180027301  jg      short loc_18002734D
0x180027303  lea     rax, ?_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4V45@A; std::shared_ptr<Concurrency::scheduler_interface> `Concurrency::details::_GetStaticAmbientSchedulerStorage(void)'::`2'::_S_scheduler
0x18002730a  xor     r8d, r8d; lpContext
0x18002730d  xor     edx, edx; dwFlags
0x18002730f  mov     cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA, rax; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x180027316  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x18002731d  call    cs:__imp_InitOnceComplete
0x180027324  nop     dword ptr [rax+rax+00h]
0x180027329  test    eax, eax
0x18002732b  jz      short loc_180027347
0x18002732d  mov     rax, cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x180027334  mov     rcx, [rsp+48h+var_10]
0x180027339  xor     rcx, rsp; StackCookie
0x18002733c  call    __security_check_cookie
0x180027341  add     rsp, 48h
0x180027345  retn
0x180027347  call    __std_init_once_link_alternate_names_and_abort
0x18002734d  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x180027354  call    _Init_thread_header
0x180027359  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, 0FFFFFFFFh
0x180027360  jnz     short loc_180027303
0x180027362  lea     rcx, ??__F_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@YAXXZ; void (__cdecl *)()
0x180027369  call    atexit
0x18002736e  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x180027375  call    _Init_thread_footer
0x18002737a  jmp     short loc_180027303
```
