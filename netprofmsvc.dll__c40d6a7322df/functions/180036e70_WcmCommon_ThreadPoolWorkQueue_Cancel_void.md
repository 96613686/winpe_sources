# WcmCommon::ThreadPoolWorkQueue::Cancel(void)

- ea: `0x180036e70`
- end: `0x1800370f8`
- name: `?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ`
- size: `648`
- prototype: `void __fastcall(WcmCommon::ThreadPoolWorkQueue *__hidden this)`
- caller_count: `19`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800584a0`
- `0x18006fea0`
- `0x180070274`
- `0x1800702ac`
- `0x180080ca0`
- `0x180080d94`
- `0x180080e74`
- `0x18008118c`
- `0x180081924`
- `0x1800823d4`
- `0x1800989b4`
- `0x180098c48`
- `0x18009af38`
- `0x1800d1534`
- `0x1800fd304`
- `0x180124810`
- `0x180124930`
- `0x18012bae8`
- `0x18012c40c`

## callees

- `0x18000e998`
- `0x1800368f0`
- `0x180036e70`
- `0x18006f460`
- `0x180097168`
- `0x1800bae24`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036e81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036e81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036f22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036fb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036f22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036fb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036fec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036f2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036f5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036fff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036f2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036f5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036fff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180036f55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180036f55`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180036f4c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180036f4c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180036ff7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180036ff7`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::Cancel(WcmCommon::ThreadPoolWorkQueue *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  bool v3; // zf
  __int64 v4; // rdi
  __int64 v5; // rbp
  __int64 v6; // rcx
  __int64 v7; // rcx
  DWORD LastError; // edi
  struct _TP_WORK *v9; // rsi
  DWORD v10; // edi
  struct _TP_POOL *v11; // rsi
  __int64 v12; // rcx
  DWORD v13; // edi
  __int64 v14; // rdi
  __int64 v15; // r14
  _BYTE *v16; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v3 = *((_QWORD *)this + 16) == 0;
  *((_BYTE *)this + 272) = 1;
  if ( v3 )
  {
    if ( v1 )
      LeaveCriticalSection(v1);
  }
  else
  {
    if ( *(_DWORD *)this == 1 )
    {
      v4 = *((_QWORD *)this + 27);
      v5 = v4 + *((_QWORD *)this + 28);
      while ( v4 != v5 )
      {
        v12 = **(_QWORD **)(*((_QWORD *)this + 25) + 8 * (v4 & (*((_QWORD *)this + 26) - 1LL)));
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        ++v4;
      }
      while ( 1 )
      {
        v6 = *((_QWORD *)this + 28);
        if ( !v6 )
          break;
        std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(*(_QWORD *)(*((_QWORD *)this + 25) + 8 * ((*((_QWORD *)this + 26) - 1LL) & (v6 - 1 + *((_QWORD *)this + 27)))));
        v3 = (*((_QWORD *)this + 28))-- == 1;
        if ( v3 )
          *((_QWORD *)this + 27) = 0;
      }
      if ( *((_QWORD *)this + 25) )
        std::deque<unsigned long>::_Reset_map((char *)this + 192);
      while ( 1 )
      {
        v7 = *((_QWORD *)this + 23);
        if ( !v7 )
          break;
        std::function<void (void)>::`scalar deleting destructor'(*(void **)(*((_QWORD *)this + 20)
                                                                          + 8
                                                                          * ((*((_QWORD *)this + 21) - 1LL)
                                                                           & (v7 - 1 + *((_QWORD *)this + 22)))));
        v3 = (*((_QWORD *)this + 23))-- == 1;
        if ( v3 )
          *((_QWORD *)this + 22) = 0;
      }
      if ( *((_QWORD *)this + 20) )
        std::deque<std::function<void (void)>>::_Reset_map((char *)this + 152);
    }
    else
    {
      v14 = *((_QWORD *)this + 32);
      v15 = v14 + *((_QWORD *)this + 33);
      while ( v14 != v15 )
      {
        v16 = *(_BYTE **)(*((_QWORD *)this + 30) + 8 * (v14 & (*((_QWORD *)this + 31) - 1LL)));
        if ( v16 && v16[64] == 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 16LL))(*(_QWORD *)v16);
        ++v14;
      }
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Tidy((char *)this + 232);
    }
    if ( v1 )
    {
      LastError = GetLastError();
      LeaveCriticalSection(v1);
      SetLastError(LastError);
    }
    v9 = (struct _TP_WORK *)*((_QWORD *)this + 16);
    if ( v9 )
    {
      v10 = GetLastError();
      WaitForThreadpoolWorkCallbacks(v9, 1);
      CloseThreadpoolWork(v9);
      SetLastError(v10);
    }
    *((_QWORD *)this + 16) = 0;
    v11 = (struct _TP_POOL *)*((_QWORD *)this + 15);
    if ( v11 )
    {
      v13 = GetLastError();
      CloseThreadpool(v11);
      SetLastError(v13);
    }
    *((_QWORD *)this + 15) = 0;
    *((_OWORD *)this + 3) = 0;
    *((_OWORD *)this + 4) = 0;
    *((_OWORD *)this + 5) = 0;
    *((_OWORD *)this + 6) = 0;
    *((_QWORD *)this + 14) = 0;
    _InterlockedExchange64((volatile __int64 *)this + 17, 0);
  }
}

```

## disassembly

```asm
0x180036e70  push    rbx
0x180036e72  push    rsi
0x180036e73  sub     rsp, 38h
0x180036e77  lea     rsi, [rcx+8]
0x180036e7b  mov     rbx, rcx
0x180036e7e  mov     rcx, rsi; lpCriticalSection
0x180036e81  call    cs:__imp_EnterCriticalSection
0x180036e87  cmp     qword ptr [rbx+80h], 0
0x180036e8f  mov     byte ptr [rbx+110h], 1
0x180036e96  jz      loc_180036FA8
0x180036e9c  mov     [rsp+48h+var_18], r15
0x180036ea1  xor     r15d, r15d
0x180036ea4  cmp     dword ptr [rbx], 1
0x180036ea7  mov     [rsp+48h+arg_8], rbp
0x180036eac  mov     [rsp+48h+arg_10], rdi
0x180036eb1  jnz     loc_180037090
0x180036eb7  mov     rdi, [rbx+0D8h]
0x180036ebe  mov     rbp, [rbx+0E0h]
0x180036ec5  add     rbp, rdi
0x180036ec8  cmp     rdi, rbp
0x180036ecb  jnz     loc_180036FB8
0x180036ed1  lea     rdi, [rbx+0C0h]
0x180036ed8  mov     rcx, [rdi+20h]
0x180036edc  test    rcx, rcx
0x180036edf  jnz     loc_18003700A
0x180036ee5  cmp     [rdi+8], r15
0x180036ee9  jnz     loc_18003703F
0x180036eef  lea     rdi, [rbx+98h]
0x180036ef6  mov     rcx, [rdi+20h]
0x180036efa  test    rcx, rcx
0x180036efd  jnz     loc_18003704C
0x180036f03  cmp     [rdi+8], r15
0x180036f07  jnz     loc_180037083
0x180036f0d  mov     rbp, [rsp+48h+arg_8]
0x180036f12  test    rsi, rsi
0x180036f15  jz      short loc_180036F30
0x180036f17  call    cs:__imp_GetLastError
0x180036f1d  mov     rcx, rsi; lpCriticalSection
0x180036f20  mov     edi, eax
0x180036f22  call    cs:__imp_LeaveCriticalSection
0x180036f28  mov     ecx, edi; dwErrCode
0x180036f2a  call    cs:__imp_SetLastError
0x180036f30  mov     rsi, [rbx+80h]
0x180036f37  test    rsi, rsi
0x180036f3a  jz      short loc_180036F63
0x180036f3c  call    cs:__imp_GetLastError
0x180036f42  mov     edx, 1; fCancelPendingCallbacks
0x180036f47  mov     rcx, rsi; pwk
0x180036f4a  mov     edi, eax
0x180036f4c  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180036f52  mov     rcx, rsi; pwk
0x180036f55  call    cs:__imp_CloseThreadpoolWork
0x180036f5b  mov     ecx, edi; dwErrCode
0x180036f5d  call    cs:__imp_SetLastError
0x180036f63  mov     [rbx+80h], r15
0x180036f6a  mov     rsi, [rbx+78h]
0x180036f6e  test    rsi, rsi
0x180036f71  jnz     short loc_180036FEC
0x180036f73  mov     rdi, [rsp+48h+arg_10]
0x180036f78  xorps   xmm0, xmm0
0x180036f7b  mov     [rbx+78h], r15
0x180036f7f  xor     eax, eax
0x180036f81  mov     r15, [rsp+48h+var_18]
0x180036f86  movups  xmmword ptr [rbx+30h], xmm0
0x180036f8a  movups  xmmword ptr [rbx+40h], xmm0
0x180036f8e  movups  xmmword ptr [rbx+50h], xmm0
0x180036f92  movups  xmmword ptr [rbx+60h], xmm0
0x180036f96  mov     [rbx+70h], rax
0x180036f9a  xchg    rax, [rbx+88h]
0x180036fa1  add     rsp, 38h
0x180036fa5  pop     rsi
0x180036fa6  pop     rbx
0x180036fa7  retn
0x180036fa8  test    rsi, rsi
0x180036fab  jz      short loc_180036FA1
0x180036fad  mov     rcx, rsi; lpCriticalSection
0x180036fb0  call    cs:__imp_LeaveCriticalSection
0x180036fb6  jmp     short loc_180036FA1
0x180036fb8  mov     rcx, [rbx+0D0h]
0x180036fbf  mov     rax, [rbx+0C8h]
0x180036fc6  dec     rcx
0x180036fc9  and     rcx, rdi
0x180036fcc  mov     rcx, [rax+rcx*8]
0x180036fd0  mov     rcx, [rcx]
0x180036fd3  test    rcx, rcx
0x180036fd6  jz      short loc_180036FE4
0x180036fd8  mov     rax, [rcx]
0x180036fdb  mov     rax, [rax+10h]
0x180036fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fe4  inc     rdi
0x180036fe7  jmp     loc_180036EC8
0x180036fec  call    cs:__imp_GetLastError
0x180036ff2  mov     rcx, rsi; ptpp
0x180036ff5  mov     edi, eax
0x180036ff7  call    cs:__imp_CloseThreadpool
0x180036ffd  mov     ecx, edi; dwErrCode
0x180036fff  call    cs:__imp_SetLastError
0x180037005  jmp     loc_180036F73
0x18003700a  mov     rdx, [rdi+18h]
0x18003700e  dec     rcx
0x180037011  mov     rax, [rdi+10h]
0x180037015  add     rdx, rcx
0x180037018  mov     rcx, [rdi+8]
0x18003701c  dec     rax
0x18003701f  and     rdx, rax
0x180037022  mov     rcx, [rcx+rdx*8]
0x180037026  call    ??_G?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAAPEAXI@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(uint)
0x18003702b  sub     qword ptr [rdi+20h], 1
0x180037030  jnz     loc_180036ED8
0x180037036  mov     [rdi+18h], r15
0x18003703a  jmp     loc_180036ED8
0x18003703f  mov     rcx, rdi
0x180037042  call    ?_Reset_map@?$deque@KV?$allocator@K@std@@@std@@AEAAXXZ; std::deque<ulong>::_Reset_map(void)
0x180037047  jmp     loc_180036EEF
0x18003704c  mov     r8, [rdi+18h]
0x180037050  dec     rcx
0x180037053  mov     rax, [rdi+10h]
0x180037057  add     r8, rcx
0x18003705a  mov     rcx, [rdi+8]
0x18003705e  dec     rax
0x180037061  and     r8, rax
0x180037064  xor     edx, edx
0x180037066  mov     rcx, [rcx+r8*8]; Block
0x18003706a  call    ??_G?$function@$$A6AXXZ@std@@QEAAPEAXI@Z; std::function<void (void)>::`scalar deleting destructor'(uint)
0x18003706f  sub     qword ptr [rdi+20h], 1
0x180037074  jnz     loc_180036EF6
0x18003707a  mov     [rdi+18h], r15
0x18003707e  jmp     loc_180036EF6
0x180037083  mov     rcx, rdi
0x180037086  call    ?_Reset_map@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAXXZ; std::deque<std::function<void (void)>>::_Reset_map(void)
0x18003708b  jmp     loc_180036F0D
0x180037090  mov     rdi, [rbx+100h]
0x180037097  mov     [rsp+48h+arg_18], r14
0x18003709c  mov     r14, [rbx+108h]
0x1800370a3  add     r14, rdi
0x1800370a6  cmp     rdi, r14
0x1800370a9  jz      short loc_1800370E2
0x1800370ab  mov     rcx, [rbx+0F8h]
0x1800370b2  mov     rax, [rbx+0F0h]
0x1800370b9  dec     rcx
0x1800370bc  and     rcx, rdi
0x1800370bf  mov     rcx, [rax+rcx*8]
0x1800370c3  test    rcx, rcx
0x1800370c6  jz      short loc_1800370DD
0x1800370c8  cmp     byte ptr [rcx+40h], 1
0x1800370cc  jnz     short loc_1800370DD
0x1800370ce  mov     rcx, [rcx]
0x1800370d1  mov     rax, [rcx]
0x1800370d4  mov     rax, [rax+10h]
0x1800370d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370dd  inc     rdi
0x1800370e0  jmp     short loc_1800370A6
0x1800370e2  lea     rcx, [rbx+0E8h]
0x1800370e9  call    ?_Tidy@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAXXZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Tidy(void)
0x1800370ee  mov     r14, [rsp+48h+arg_18]
0x1800370f3  jmp     loc_180036F0D
```
