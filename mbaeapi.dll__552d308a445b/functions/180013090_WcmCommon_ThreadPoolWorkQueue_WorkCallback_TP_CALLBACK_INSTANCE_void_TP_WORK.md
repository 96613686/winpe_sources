# WcmCommon::ThreadPoolWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180013090`
- end: `0x18001334d`
- name: `?WorkCallback@ThreadPoolWorkQueue@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `701`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000c0dc`
- `0x18000c2b8`
- `0x180013090`
- `0x18001336c`
- `0x1800136b4`
- `0x18005c010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001331f`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001331f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001325e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800132f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001325e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800132f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800130b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800132db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800132db`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800132e4`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800132e4`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::WorkCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WORK Work)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rbx
  volatile signed __int32 *v7; // rbx
  bool v8; // zf
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rdx
  HANDLE CurrentThread; // rax
  void (*v15)(void); // rax
  _OWORD v16[3]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v17; // [rsp+58h] [rbp-20h]
  char v18; // [rsp+60h] [rbp-18h]

  v17 = 0;
  v18 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)(Context + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 8));
  if ( *(_DWORD *)Context == 1 )
  {
    if ( *((_QWORD *)Context + 28) )
    {
      v6 = *(_QWORD *)(*((_QWORD *)Context + 25) + 8 * (*((_QWORD *)Context + 27) & (*((_QWORD *)Context + 26) - 1LL)));
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(
        (__int64)v16,
        v5);
      v18 = -1;
      v16[0] = 0;
      v16[0] = *(_OWORD *)v6;
      *(_QWORD *)v6 = 0;
      *(_QWORD *)(v6 + 8) = 0;
      v18 = 1;
      v7 = *(volatile signed __int32 **)(*(_QWORD *)(*((_QWORD *)Context + 25)
                                                   + 8 * (*((_QWORD *)Context + 27) & (*((_QWORD *)Context + 26) - 1LL)))
                                       + 8LL);
      if ( v7 )
      {
        if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
          if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        }
      }
      v8 = (*((_QWORD *)Context + 28))-- == 1;
      if ( v8 )
        *((_QWORD *)Context + 27) = 0;
      else
        ++*((_QWORD *)Context + 27);
      goto LABEL_23;
    }
    if ( *((_QWORD *)Context + 23) )
    {
      v9 = *(_QWORD *)(*((_QWORD *)Context + 20) + 8 * (*((_QWORD *)Context + 22) & (*((_QWORD *)Context + 21) - 1LL)));
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(
        (__int64)v16,
        v5);
      v18 = -1;
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(
        (__int64)v16,
        v9);
      v11 = *(_QWORD *)(*((_QWORD *)Context + 20) + 8 * (*((_QWORD *)Context + 22) & (*((_QWORD *)Context + 21) - 1LL)));
      v12 = *(_QWORD *)(v11 + 56);
      if ( v12 )
      {
        LOBYTE(v10) = v12 != v11;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 32LL))(v12, v10);
        *(_QWORD *)(v11 + 56) = 0;
      }
      v8 = (*((_QWORD *)Context + 23))-- == 1;
      if ( v8 )
        *((_QWORD *)Context + 22) = 0;
      else
        ++*((_QWORD *)Context + 22);
      goto LABEL_23;
    }
  }
  else if ( *((_QWORD *)Context + 33) )
  {
    std::swap<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>,0>(
      (__int64)v16,
      *(_QWORD *)(*((_QWORD *)Context + 30) + 8 * (*((_QWORD *)Context + 32) & (*((_QWORD *)Context + 31) - 1LL))));
    std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(
      *(_QWORD *)(*((_QWORD *)Context + 30) + 8 * (*((_QWORD *)Context + 32) & (*((_QWORD *)Context + 31) - 1LL))),
      v13);
    v8 = (*((_QWORD *)Context + 33))-- == 1;
    if ( v8 )
      *((_QWORD *)Context + 32) = 0;
    else
      ++*((_QWORD *)Context + 32);
LABEL_23:
    CurrentThread = GetCurrentThread();
    _InterlockedExchange((volatile __int32 *)Context + 36, GetThreadId(CurrentThread));
    if ( v4 )
      LeaveCriticalSection(v4);
    if ( v18 == 1 )
    {
      v15 = *(void (**)(void))(**(_QWORD **)&v16[0] + 8LL);
    }
    else
    {
      if ( v18 )
        std::_Throw_bad_variant_access();
      if ( !v17 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      v15 = *(void (**)(void))(*(_QWORD *)v17 + 16LL);
    }
    v15();
    _InterlockedDecrement64((volatile signed __int64 *)Context + 17);
    _InterlockedExchange((volatile __int32 *)Context + 36, 0);
    goto LABEL_19;
  }
  if ( v4 )
    LeaveCriticalSection(v4);
LABEL_19:
  std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(
    (__int64)v16,
    v5);
}

```

## disassembly

```asm
0x180013090  push    rbp
0x180013092  push    rbx
0x180013093  push    rsi
0x180013094  push    rdi
0x180013095  mov     rbp, rsp
0x180013098  sub     rsp, 78h
0x18001309c  mov     rdi, rdx
0x18001309f  mov     [rbp+var_20], 0
0x1800130a7  mov     [rbp+var_18], 0
0x1800130ab  lea     rsi, [rdx+8]
0x1800130af  mov     rcx, rsi; lpCriticalSection
0x1800130b2  call    cs:__imp_EnterCriticalSection
0x1800130b8  cmp     dword ptr [rdi], 1
0x1800130bb  jnz     loc_18001324C
0x1800130c1  cmp     qword ptr [rdi+0E0h], 0
0x1800130c9  jz      loc_1800131A4
0x1800130cf  mov     rcx, [rdi+0D0h]
0x1800130d6  dec     rcx
0x1800130d9  and     rcx, [rdi+0D8h]
0x1800130e0  mov     rax, [rdi+0C8h]
0x1800130e7  mov     rbx, [rax+rcx*8]
0x1800130eb  lea     rcx, [rbp+var_58]
0x1800130ef  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x1800130f4  mov     [rbp+var_18], 0FFh
0x1800130f8  xorps   xmm0, xmm0
0x1800130fb  movdqa  [rbp+var_58], xmm0
0x180013100  mov     rax, [rbx]
0x180013103  mov     qword ptr [rbp+var_58], rax
0x180013107  mov     rax, [rbx+8]
0x18001310b  mov     qword ptr [rbp+var_58+8], rax
0x18001310f  mov     qword ptr [rbx], 0
0x180013116  mov     qword ptr [rbx+8], 0
0x18001311e  mov     [rbp+var_18], 1
0x180013122  mov     rcx, [rdi+0D0h]
0x180013129  dec     rcx
0x18001312c  and     rcx, [rdi+0D8h]
0x180013133  mov     rax, [rdi+0C8h]
0x18001313a  mov     rcx, [rax+rcx*8]
0x18001313e  mov     rbx, [rcx+8]
0x180013142  test    rbx, rbx
0x180013145  jz      short loc_18001317E
0x180013147  or      eax, 0FFFFFFFFh
0x18001314a  lock xadd [rbx+8], eax
0x18001314f  cmp     eax, 1
0x180013152  jnz     short loc_18001317E
0x180013154  mov     rax, [rbx]
0x180013157  mov     rcx, rbx
0x18001315a  mov     rax, [rax]
0x18001315d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013162  or      eax, 0FFFFFFFFh
0x180013165  lock xadd [rbx+0Ch], eax
0x18001316a  cmp     eax, 1
0x18001316d  jnz     short loc_18001317E
0x18001316f  mov     rax, [rbx]
0x180013172  mov     rcx, rbx
0x180013175  mov     rax, [rax+8]
0x180013179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001317e  sub     qword ptr [rdi+0E0h], 1
0x180013186  jnz     short loc_180013198
0x180013188  mov     qword ptr [rdi+0D8h], 0
0x180013193  jmp     loc_1800132DB
0x180013198  inc     qword ptr [rdi+0D8h]
0x18001319f  jmp     loc_1800132DB
0x1800131a4  cmp     qword ptr [rdi+0B8h], 0
0x1800131ac  jz      loc_180013256
0x1800131b2  mov     rcx, [rdi+0A8h]
0x1800131b9  dec     rcx
0x1800131bc  and     rcx, [rdi+0B0h]
0x1800131c3  mov     rax, [rdi+0A0h]
0x1800131ca  mov     rbx, [rax+rcx*8]
0x1800131ce  lea     rcx, [rbp+var_58]
0x1800131d2  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x1800131d7  mov     [rbp+var_18], 0FFh
0x1800131db  mov     rdx, rbx
0x1800131de  lea     rcx, [rbp+var_58]
0x1800131e2  call    ??$_Emplace_valueless@$0A@V?$function@$$A6AXXZ@std@@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@AEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(std::function<void (void)> &&)
0x1800131e7  mov     rcx, [rdi+0A8h]
0x1800131ee  dec     rcx
0x1800131f1  and     rcx, [rdi+0B0h]
0x1800131f8  mov     rax, [rdi+0A0h]
0x1800131ff  mov     rbx, [rax+rcx*8]
0x180013203  mov     rcx, [rbx+38h]
0x180013207  test    rcx, rcx
0x18001320a  jz      short loc_180013226
0x18001320c  mov     rax, [rcx]
0x18001320f  cmp     rcx, rbx
0x180013212  setnz   dl
0x180013215  mov     rax, [rax+20h]
0x180013219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001321e  mov     qword ptr [rbx+38h], 0
0x180013226  sub     qword ptr [rdi+0B8h], 1
0x18001322e  jnz     short loc_180013240
0x180013230  mov     qword ptr [rdi+0B0h], 0
0x18001323b  jmp     loc_1800132DB
0x180013240  inc     qword ptr [rdi+0B0h]
0x180013247  jmp     loc_1800132DB
0x18001324c  cmp     qword ptr [rdi+108h], 0
0x180013254  jnz     short loc_180013277
0x180013256  test    rsi, rsi
0x180013259  jz      short loc_180013264
0x18001325b  mov     rcx, rsi; lpCriticalSection
0x18001325e  call    cs:__imp_LeaveCriticalSection
0x180013264  lea     rcx, [rbp+var_58]
0x180013268  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x18001326d  nop
0x18001326e  add     rsp, 78h
0x180013272  pop     rdi
0x180013273  pop     rsi
0x180013274  pop     rbx
0x180013275  pop     rbp
0x180013276  retn
0x180013277  mov     rax, [rdi+0F8h]
0x18001327e  dec     rax
0x180013281  and     rax, [rdi+100h]
0x180013288  mov     rdx, [rdi+0F0h]
0x18001328f  mov     rdx, [rdx+rax*8]
0x180013293  lea     rcx, [rbp+var_58]
0x180013297  call    ??$swap@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@$0A@@std@@YAXAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@0@0@Z; std::swap<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>,0>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &,std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &)
0x18001329c  mov     rax, [rdi+0F8h]
0x1800132a3  dec     rax
0x1800132a6  and     rax, [rdi+100h]
0x1800132ad  mov     rcx, [rdi+0F0h]
0x1800132b4  mov     rcx, [rcx+rax*8]
0x1800132b8  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x1800132bd  sub     qword ptr [rdi+108h], 1
0x1800132c5  jnz     short loc_1800132D4
0x1800132c7  mov     qword ptr [rdi+100h], 0
0x1800132d2  jmp     short loc_1800132DB
0x1800132d4  inc     qword ptr [rdi+100h]
0x1800132db  call    cs:__imp_GetCurrentThread
0x1800132e1  mov     rcx, rax; Thread
0x1800132e4  call    cs:__imp_GetThreadId
0x1800132ea  xchg    eax, [rdi+90h]
0x1800132f0  test    rsi, rsi
0x1800132f3  jz      short loc_1800132FE
0x1800132f5  mov     rcx, rsi; lpCriticalSection
0x1800132f8  call    cs:__imp_LeaveCriticalSection
0x1800132fe  mov     al, [rbp+var_18]
0x180013301  cmp     al, 1
0x180013303  jnz     short loc_180013312
0x180013305  mov     rcx, qword ptr [rbp+var_58]
0x180013309  mov     rax, [rcx]
0x18001330c  mov     rax, [rax+8]
0x180013310  jmp     short loc_18001332D
0x180013312  test    al, al
0x180013314  jnz     short loc_180013347
0x180013316  mov     rcx, [rbp+var_20]
0x18001331a  test    rcx, rcx
0x18001331d  jnz     short loc_180013326
0x18001331f  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180013325  int     3; Trap to Debugger
0x180013326  mov     rax, [rcx]
0x180013329  mov     rax, [rax+10h]
0x18001332d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013332  lock dec qword ptr [rdi+88h]
0x18001333a  xor     eax, eax
0x18001333c  xchg    eax, [rdi+90h]
0x180013342  jmp     loc_180013264
0x180013347  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
```
