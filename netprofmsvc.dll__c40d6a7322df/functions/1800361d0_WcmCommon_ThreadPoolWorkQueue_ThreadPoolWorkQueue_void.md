# WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(void)

- ea: `0x1800361d0`
- end: `0x1800365af`
- name: `??1ThreadPoolWorkQueue@WcmCommon@@QEAA@XZ`
- size: `991`
- prototype: `void __fastcall(WcmCommon::ThreadPoolWorkQueue *__hidden this)`
- caller_count: `39`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800584a0`
- `0x18006fea0`
- `0x1800702ac`
- `0x180080ca0`
- `0x180080d94`
- `0x180080e74`
- `0x18008118c`
- `0x180081924`
- `0x1800823d4`
- `0x1800847bc`
- `0x1800989b4`
- `0x180098c48`
- `0x18009af38`
- `0x1800beb78`
- `0x1800cd8cc`
- `0x1800d1534`
- `0x1800fc35c`
- `0x1800fd304`
- `0x180124810`
- `0x180124930`
- `0x18012bae8`
- `0x18012c40c`
- `0x18013bf64`
- `0x18013c321`
- `0x18013c424`
- `0x18013c43d`
- `0x18013ea72`
- `0x18013ea84`
- `0x18013ed58`
- `0x18013ed6a`
- `0x18013f051`
- `0x18013f06a`
- `0x18013f968`
- `0x18013fc79`
- `0x18013ff04`
- `0x180140008`
- `0x180144c83`
- `0x180145c17`
- `0x180145c30`

## callees

- `0x18000e998`
- `0x180032c90`
- `0x1800361d0`
- `0x1800368f0`
- `0x18006f460`
- `0x18006f500`
- `0x180097168`
- `0x1800971c8`
- `0x1800bae24`
- `0x1800bae94`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800361f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800361f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036274`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800363b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036274`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800363b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800363a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003628e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800363f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003628e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800363f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003627c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800362af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036409`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003627c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800362af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036409`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800362a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180036599`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800362a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180036599`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003629e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180036590`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003629e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180036590`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180036401`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800365a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180036401`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800365a4`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(WcmCommon::ThreadPoolWorkQueue *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  void **v3; // r14
  __int64 v4; // rsi
  __int64 v5; // rbp
  __int64 v6; // rcx
  DWORD LastError; // esi
  struct _TP_WORK *v8; // rbp
  DWORD v9; // esi
  struct _TP_POOL *v10; // rbp
  __int64 v11; // rcx
  void *v12; // rcx
  __int64 v13; // rcx
  void *v14; // rcx
  __int64 v15; // rcx
  void *v16; // rcx
  struct _TP_WORK *v17; // rsi
  struct _TP_POOL *v18; // rcx
  __int64 v19; // rcx
  DWORD v20; // esi
  bool v21; // zf
  __int64 v22; // rsi
  __int64 v23; // r15
  _BYTE *v24; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v3 = (void **)((char *)this + 152);
  *((_BYTE *)this + 272) = 1;
  if ( *((_QWORD *)this + 16) )
  {
    if ( *(_DWORD *)this == 1 )
    {
      v4 = *((_QWORD *)this + 27);
      v5 = v4 + *((_QWORD *)this + 28);
      while ( v4 != v5 )
      {
        v19 = **(_QWORD **)(*((_QWORD *)this + 25) + 8 * (v4 & (*((_QWORD *)this + 26) - 1LL)));
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        ++v4;
      }
      while ( 1 )
      {
        v6 = *((_QWORD *)this + 28);
        if ( !v6 )
          break;
        std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(*(_QWORD *)(*((_QWORD *)this + 25) + 8 * ((*((_QWORD *)this + 26) - 1LL) & (v6 - 1 + *((_QWORD *)this + 27)))));
        v21 = (*((_QWORD *)this + 28))-- == 1;
        if ( v21 )
          *((_QWORD *)this + 27) = 0;
      }
      if ( *((_QWORD *)this + 25) )
        std::deque<unsigned long>::_Reset_map((char *)this + 192);
      std::deque<std::function<void (void)>>::_Tidy((char *)this + 152);
    }
    else
    {
      v22 = *((_QWORD *)this + 32);
      v23 = v22 + *((_QWORD *)this + 33);
      while ( v22 != v23 )
      {
        v24 = *(_BYTE **)(*((_QWORD *)this + 30) + 8 * (v22 & (*((_QWORD *)this + 31) - 1LL)));
        if ( v24 && v24[64] == 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 16LL))(*(_QWORD *)v24);
        ++v22;
      }
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Tidy((char *)this + 232);
    }
    if ( v1 )
    {
      LastError = GetLastError();
      LeaveCriticalSection(v1);
      SetLastError(LastError);
    }
    v8 = (struct _TP_WORK *)*((_QWORD *)this + 16);
    if ( v8 )
    {
      v9 = GetLastError();
      WaitForThreadpoolWorkCallbacks(v8, 1);
      CloseThreadpoolWork(v8);
      SetLastError(v9);
    }
    *((_QWORD *)this + 16) = 0;
    v10 = (struct _TP_POOL *)*((_QWORD *)this + 15);
    if ( v10 )
    {
      v20 = GetLastError();
      CloseThreadpool(v10);
      SetLastError(v20);
    }
    *((_QWORD *)this + 15) = 0;
    *((_OWORD *)this + 3) = 0;
    *((_OWORD *)this + 4) = 0;
    *((_OWORD *)this + 5) = 0;
    *((_OWORD *)this + 6) = 0;
    *((_QWORD *)this + 14) = 0;
    _InterlockedExchange64((volatile __int64 *)this + 17, 0);
  }
  else if ( v1 )
  {
    LeaveCriticalSection(v1);
  }
  while ( 1 )
  {
    v11 = *((_QWORD *)this + 33);
    if ( !v11 )
      break;
    std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(*(_QWORD *)(*((_QWORD *)this + 30) + 8 * ((*((_QWORD *)this + 31) - 1LL) & (v11 - 1 + *((_QWORD *)this + 32)))));
    v21 = (*((_QWORD *)this + 33))-- == 1;
    if ( v21 )
      *((_QWORD *)this + 32) = 0;
  }
  if ( *((_QWORD *)this + 30) )
    std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Reset_map((char *)this + 232);
  v12 = (void *)*((_QWORD *)this + 29);
  *((_QWORD *)this + 29) = 0;
  std::_Deallocate<16>(v12, 0x10u);
  while ( 1 )
  {
    v13 = *((_QWORD *)this + 28);
    if ( !v13 )
      break;
    std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(*(_QWORD *)(*((_QWORD *)this + 25) + 8 * ((*((_QWORD *)this + 26) - 1LL) & (v13 - 1 + *((_QWORD *)this + 27)))));
    v21 = (*((_QWORD *)this + 28))-- == 1;
    if ( v21 )
      *((_QWORD *)this + 27) = 0;
  }
  if ( *((_QWORD *)this + 25) )
    std::deque<unsigned long>::_Reset_map((char *)this + 192);
  v14 = (void *)*((_QWORD *)this + 24);
  *((_QWORD *)this + 24) = 0;
  std::_Deallocate<16>(v14, 0x10u);
  while ( 1 )
  {
    v15 = *((_QWORD *)this + 23);
    if ( !v15 )
      break;
    std::function<void (void)>::`scalar deleting destructor'(*(void **)(*((_QWORD *)this + 20)
                                                                      + 8
                                                                      * ((*((_QWORD *)this + 21) - 1LL)
                                                                       & (v15 - 1 + *((_QWORD *)this + 22)))));
    v21 = (*((_QWORD *)this + 23))-- == 1;
    if ( v21 )
      *((_QWORD *)this + 22) = 0;
  }
  if ( *((_QWORD *)this + 20) )
    std::deque<std::function<void (void)>>::_Reset_map((char *)this + 152);
  v16 = *v3;
  *v3 = 0;
  std::_Deallocate<16>(v16, 0x10u);
  v17 = (struct _TP_WORK *)*((_QWORD *)this + 16);
  if ( v17 )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 16), 1);
    CloseThreadpoolWork(v17);
  }
  v18 = (struct _TP_POOL *)*((_QWORD *)this + 15);
  if ( v18 )
    CloseThreadpool(v18);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x1800361d0  push    rbx
0x1800361d2  sub     rsp, 50h
0x1800361d6  mov     [rsp+58h+arg_10], rsi
0x1800361db  lea     rbx, [rcx+8]
0x1800361df  mov     [rsp+58h+var_10], rdi
0x1800361e4  mov     rdi, rcx
0x1800361e7  mov     rcx, rbx; lpCriticalSection
0x1800361ea  mov     [rsp+58h+var_18], r12
0x1800361ef  mov     [rsp+58h+var_20], r14
0x1800361f4  call    cs:__imp_EnterCriticalSection
0x1800361fa  xor     r12d, r12d
0x1800361fd  lea     r14, [rdi+98h]
0x180036204  mov     byte ptr [r14+78h], 1
0x180036209  cmp     [rdi+80h], r12
0x180036210  jz      loc_1800363AB
0x180036216  cmp     dword ptr [rdi], 1
0x180036219  mov     [rsp+58h+arg_8], rbp
0x18003621e  jnz     loc_180036456
0x180036224  mov     rsi, [rdi+0D8h]
0x18003622b  mov     rbp, [rdi+0E0h]
0x180036232  add     rbp, rsi
0x180036235  cmp     rsi, rbp
0x180036238  jnz     loc_1800363C2
0x18003623e  lea     rsi, [rdi+0C0h]
0x180036245  mov     rcx, [rsi+20h]
0x180036249  test    rcx, rcx
0x18003624c  jnz     loc_180036414
0x180036252  cmp     [rsi+8], r12
0x180036256  jnz     loc_180036449
0x18003625c  mov     rcx, r14
0x18003625f  call    ?_Tidy@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAXXZ; std::deque<std::function<void (void)>>::_Tidy(void)
0x180036264  test    rbx, rbx
0x180036267  jz      short loc_180036282
0x180036269  call    cs:__imp_GetLastError
0x18003626f  mov     rcx, rbx; lpCriticalSection
0x180036272  mov     esi, eax
0x180036274  call    cs:__imp_LeaveCriticalSection
0x18003627a  mov     ecx, esi; dwErrCode
0x18003627c  call    cs:__imp_SetLastError
0x180036282  mov     rbp, [rdi+80h]
0x180036289  test    rbp, rbp
0x18003628c  jz      short loc_1800362B5
0x18003628e  call    cs:__imp_GetLastError
0x180036294  mov     edx, 1; fCancelPendingCallbacks
0x180036299  mov     rcx, rbp; pwk
0x18003629c  mov     esi, eax
0x18003629e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800362a4  mov     rcx, rbp; pwk
0x1800362a7  call    cs:__imp_CloseThreadpoolWork
0x1800362ad  mov     ecx, esi; dwErrCode
0x1800362af  call    cs:__imp_SetLastError
0x1800362b5  mov     [rdi+80h], r12
0x1800362bc  mov     rbp, [rdi+78h]
0x1800362c0  test    rbp, rbp
0x1800362c3  jnz     loc_1800363F6
0x1800362c9  mov     rbp, [rsp+58h+arg_8]
0x1800362ce  xorps   xmm0, xmm0
0x1800362d1  mov     [rdi+78h], r12
0x1800362d5  xor     eax, eax
0x1800362d7  movups  xmmword ptr [rdi+30h], xmm0
0x1800362db  movups  xmmword ptr [rdi+40h], xmm0
0x1800362df  movups  xmmword ptr [rdi+50h], xmm0
0x1800362e3  movups  xmmword ptr [rdi+60h], xmm0
0x1800362e7  mov     [rdi+70h], rax
0x1800362eb  xchg    rax, [rdi+88h]
0x1800362f2  mov     rcx, [r14+70h]
0x1800362f6  test    rcx, rcx
0x1800362f9  jnz     loc_1800364BE
0x1800362ff  cmp     [r14+58h], r12
0x180036303  jnz     loc_1800364F3
0x180036309  mov     rcx, [r14+50h]
0x18003630d  mov     edx, 10h
0x180036312  mov     [r14+50h], r12
0x180036316  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003631b  mov     rcx, [r14+48h]
0x18003631f  test    rcx, rcx
0x180036322  jnz     loc_180036501
0x180036328  cmp     [r14+30h], r12
0x18003632c  jnz     loc_180036536
0x180036332  mov     rcx, [r14+28h]
0x180036336  mov     edx, 10h
0x18003633b  mov     [r14+28h], r12
0x18003633f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180036344  mov     rcx, [r14+20h]
0x180036348  test    rcx, rcx
0x18003634b  jnz     loc_180036544
0x180036351  cmp     [r14+8], r12
0x180036355  jnz     loc_18003657B
0x18003635b  mov     rcx, [r14]
0x18003635e  mov     edx, 10h
0x180036363  mov     [r14], r12
0x180036366  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003636b  mov     rsi, [rdi+80h]
0x180036372  mov     r14, [rsp+58h+var_20]
0x180036377  mov     r12, [rsp+58h+var_18]
0x18003637c  test    rsi, rsi
0x18003637f  jnz     loc_180036588
0x180036385  mov     rcx, [rdi+78h]; ptpp
0x180036389  mov     rdi, [rsp+58h+var_10]
0x18003638e  mov     rsi, [rsp+58h+arg_10]
0x180036393  test    rcx, rcx
0x180036396  jnz     loc_1800365A4
0x18003639c  mov     rcx, rbx
0x18003639f  add     rsp, 50h
0x1800363a3  pop     rbx
0x1800363a4  jmp     cs:__imp_DeleteCriticalSection
0x1800363ab  test    rbx, rbx
0x1800363ae  jz      loc_1800362F2
0x1800363b4  mov     rcx, rbx; lpCriticalSection
0x1800363b7  call    cs:__imp_LeaveCriticalSection
0x1800363bd  jmp     loc_1800362F2
0x1800363c2  mov     rcx, [rdi+0D0h]
0x1800363c9  mov     rax, [rdi+0C8h]
0x1800363d0  dec     rcx
0x1800363d3  and     rcx, rsi
0x1800363d6  mov     rcx, [rax+rcx*8]
0x1800363da  mov     rcx, [rcx]
0x1800363dd  test    rcx, rcx
0x1800363e0  jz      short loc_1800363EE
0x1800363e2  mov     rax, [rcx]
0x1800363e5  mov     rax, [rax+10h]
0x1800363e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363ee  inc     rsi
0x1800363f1  jmp     loc_180036235
0x1800363f6  call    cs:__imp_GetLastError
0x1800363fc  mov     rcx, rbp; ptpp
0x1800363ff  mov     esi, eax
0x180036401  call    cs:__imp_CloseThreadpool
0x180036407  mov     ecx, esi; dwErrCode
0x180036409  call    cs:__imp_SetLastError
0x18003640f  jmp     loc_1800362C9
0x180036414  mov     rdx, [rsi+18h]
0x180036418  dec     rcx
0x18003641b  mov     rax, [rsi+10h]
0x18003641f  add     rdx, rcx
0x180036422  mov     rcx, [rsi+8]
0x180036426  dec     rax
0x180036429  and     rdx, rax
0x18003642c  mov     rcx, [rcx+rdx*8]
0x180036430  call    ??_G?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAAPEAXI@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(uint)
0x180036435  sub     qword ptr [rsi+20h], 1
0x18003643a  jnz     loc_180036245
0x180036440  mov     [rsi+18h], r12
0x180036444  jmp     loc_180036245
0x180036449  mov     rcx, rsi
0x18003644c  call    ?_Reset_map@?$deque@KV?$allocator@K@std@@@std@@AEAAXXZ; std::deque<ulong>::_Reset_map(void)
0x180036451  jmp     loc_18003625C
0x180036456  mov     rsi, [rdi+100h]
0x18003645d  mov     [rsp+58h+var_28], r15
0x180036462  mov     r15, [rdi+108h]
0x180036469  add     r15, rsi
0x18003646c  cmp     rsi, r15
0x18003646f  jz      short loc_1800364A8
0x180036471  mov     rcx, [rdi+0F8h]
0x180036478  mov     rax, [rdi+0F0h]
0x18003647f  dec     rcx
0x180036482  and     rcx, rsi
0x180036485  mov     rcx, [rax+rcx*8]
0x180036489  test    rcx, rcx
0x18003648c  jz      short loc_1800364A3
0x18003648e  cmp     byte ptr [rcx+40h], 1
0x180036492  jnz     short loc_1800364A3
0x180036494  mov     rcx, [rcx]
0x180036497  mov     rax, [rcx]
0x18003649a  mov     rax, [rax+10h]
0x18003649e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364a3  inc     rsi
0x1800364a6  jmp     short loc_18003646C
0x1800364a8  lea     rcx, [rdi+0E8h]
0x1800364af  call    ?_Tidy@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAXXZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Tidy(void)
0x1800364b4  mov     r15, [rsp+58h+var_28]
0x1800364b9  jmp     loc_180036264
0x1800364be  mov     rdx, [r14+68h]
0x1800364c2  dec     rcx
0x1800364c5  mov     rax, [r14+60h]
0x1800364c9  add     rdx, rcx
0x1800364cc  mov     rcx, [r14+58h]
0x1800364d0  dec     rax
0x1800364d3  and     rdx, rax
0x1800364d6  mov     rcx, [rcx+rdx*8]
0x1800364da  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x1800364df  sub     qword ptr [r14+70h], 1
0x1800364e4  jnz     loc_1800362F2
0x1800364ea  mov     [r14+68h], r12
0x1800364ee  jmp     loc_1800362F2
0x1800364f3  lea     rcx, [r14+50h]
0x1800364f7  call    ?_Reset_map@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAXXZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Reset_map(void)
0x1800364fc  jmp     loc_180036309
0x180036501  mov     rdx, [r14+40h]
0x180036505  dec     rcx
0x180036508  mov     rax, [r14+38h]
0x18003650c  add     rdx, rcx
0x18003650f  mov     rcx, [r14+30h]
0x180036513  dec     rax
0x180036516  and     rdx, rax
0x180036519  mov     rcx, [rcx+rdx*8]
0x18003651d  call    ??_G?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAAPEAXI@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(uint)
0x180036522  sub     qword ptr [r14+48h], 1
0x180036527  jnz     loc_18003631B
0x18003652d  mov     [r14+40h], r12
0x180036531  jmp     loc_18003631B
0x180036536  lea     rcx, [r14+28h]
0x18003653a  call    ?_Reset_map@?$deque@KV?$allocator@K@std@@@std@@AEAAXXZ; std::deque<ulong>::_Reset_map(void)
0x18003653f  jmp     loc_180036332
0x180036544  mov     r8, [r14+18h]
0x180036548  dec     rcx
0x18003654b  mov     rax, [r14+10h]
0x18003654f  add     r8, rcx
0x180036552  mov     rcx, [r14+8]
0x180036556  dec     rax
0x180036559  and     r8, rax
0x18003655c  xor     edx, edx
0x18003655e  mov     rcx, [rcx+r8*8]; Block
0x180036562  call    ??_G?$function@$$A6AXXZ@std@@QEAAPEAXI@Z; std::function<void (void)>::`scalar deleting destructor'(uint)
0x180036567  sub     qword ptr [r14+20h], 1
0x18003656c  jnz     loc_180036344
0x180036572  mov     [r14+18h], r12
0x180036576  jmp     loc_180036344
0x18003657b  mov     rcx, r14
0x18003657e  call    ?_Reset_map@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAXXZ; std::deque<std::function<void (void)>>::_Reset_map(void)
0x180036583  jmp     loc_18003635B
0x180036588  mov     edx, 1; fCancelPendingCallbacks
0x18003658d  mov     rcx, rsi; pwk
0x180036590  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180036596  mov     rcx, rsi; pwk
0x180036599  call    cs:__imp_CloseThreadpoolWork
0x18003659f  jmp     loc_180036385
0x1800365a4  call    cs:__imp_CloseThreadpool
0x1800365aa  jmp     loc_18003639C
```
