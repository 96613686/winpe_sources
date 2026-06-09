# WcmCommon::ThreadPoolWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800329f0`
- end: `0x180032c80`
- name: `?WorkCallback@ThreadPoolWorkQueue@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `656`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000c160`
- `0x18000e998`
- `0x1800329f0`
- `0x180032c90`
- `0x180032ce4`
- `0x180032d90`
- `0x180032df0`
- `0x180037140`
- `0x1800a88a0`
- `0x1800a9744`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032a25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032a25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032abe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032bbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032abe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032bbc`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180032aaa`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180032aaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032aa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180032aa1`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::WorkCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        char *a2,
        struct _TP_WORK *a3)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  bool v5; // zf
  HANDLE CurrentThread; // rax
  __int64 v7; // rbx
  void **pExceptionObject; // [rsp+28h] [rbp-41h] BYREF
  __int128 v9; // [rsp+30h] [rbp-39h]
  _OWORD v10[3]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v11; // [rsp+78h] [rbp+Fh]
  char v12; // [rsp+80h] [rbp+17h]

  v11 = 0;
  v12 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)(a2 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  if ( *(_DWORD *)a2 == 1 )
  {
    if ( *((_QWORD *)a2 + 28) )
    {
      v7 = *(_QWORD *)(*((_QWORD *)a2 + 25) + 8 * (*((_QWORD *)a2 + 27) & (*((_QWORD *)a2 + 26) - 1LL)));
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Reset(v10);
      v10[0] = 0;
      v10[0] = *(_OWORD *)v7;
      *(_QWORD *)v7 = 0;
      *(_QWORD *)(v7 + 8) = 0;
      v12 = 1;
      std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(*(_QWORD *)(*((_QWORD *)a2 + 25) + 8 * (*((_QWORD *)a2 + 27) & (*((_QWORD *)a2 + 26) - 1LL))));
      v5 = (*((_QWORD *)a2 + 28))-- == 1;
      if ( v5 )
        *((_QWORD *)a2 + 27) = 0;
      else
        ++*((_QWORD *)a2 + 27);
      goto LABEL_5;
    }
    if ( *((_QWORD *)a2 + 23) )
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::emplace<std::function<void (void)>,std::function<void (void)>,0,0>(
        v10,
        *(_QWORD *)(*((_QWORD *)a2 + 20) + 8 * (*((_QWORD *)a2 + 22) & (*((_QWORD *)a2 + 21) - 1LL))));
      std::_Func_class<void,>::~_Func_class<void,>(*(_QWORD *)(*((_QWORD *)a2 + 20)
                                                             + 8 * (*((_QWORD *)a2 + 22) & (*((_QWORD *)a2 + 21) - 1LL))));
      v5 = (*((_QWORD *)a2 + 23))-- == 1;
      if ( v5 )
        *((_QWORD *)a2 + 22) = 0;
      else
        ++*((_QWORD *)a2 + 22);
      goto LABEL_5;
    }
  }
  else if ( *((_QWORD *)a2 + 33) )
  {
    std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::swap(
      v10,
      *(_QWORD *)(*((_QWORD *)a2 + 30) + 8 * (*((_QWORD *)a2 + 32) & (*((_QWORD *)a2 + 31) - 1LL))));
    std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(*(_QWORD *)(*((_QWORD *)a2 + 30) + 8 * (*((_QWORD *)a2 + 32) & (*((_QWORD *)a2 + 31) - 1LL))));
    v5 = (*((_QWORD *)a2 + 33))-- == 1;
    if ( v5 )
      *((_QWORD *)a2 + 32) = 0;
    else
      ++*((_QWORD *)a2 + 32);
LABEL_5:
    CurrentThread = GetCurrentThread();
    _InterlockedExchange((volatile __int32 *)a2 + 36, GetThreadId(CurrentThread));
    if ( v4 )
      LeaveCriticalSection(v4);
    if ( v12 == 1 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v10[0] + 8LL))(*(_QWORD *)&v10[0]);
    }
    else
    {
      if ( v12 )
      {
        v9 = 0;
        pExceptionObject = &std::bad_variant_access::`vftable';
        throw (std::bad_variant_access *)&pExceptionObject;
      }
      std::_Func_class<void,>::operator()(v10);
    }
    _InterlockedDecrement64((volatile signed __int64 *)a2 + 17);
    _InterlockedExchange((volatile __int32 *)a2 + 36, 0);
    goto LABEL_10;
  }
  if ( v4 )
    LeaveCriticalSection(v4);
LABEL_10:
  std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v10);
}

```

## disassembly

```asm
0x1800329f0  push    rbp
0x1800329f2  push    rbx
0x1800329f3  push    rsi
0x1800329f4  push    rdi
0x1800329f5  lea     rbp, [rsp-3Fh]
0x1800329fa  sub     rsp, 0A8h
0x180032a01  mov     rax, cs:__security_cookie
0x180032a08  xor     rax, rsp
0x180032a0b  mov     [rbp+57h+var_30], rax
0x180032a0f  mov     rdi, rdx
0x180032a12  mov     [rbp+57h+var_48], 0
0x180032a1a  mov     [rbp+57h+var_40], 0
0x180032a1e  lea     rsi, [rdx+8]
0x180032a22  mov     rcx, rsi; lpCriticalSection
0x180032a25  call    cs:__imp_EnterCriticalSection
0x180032a2b  cmp     dword ptr [rdi], 1
0x180032a2e  jz      loc_180032B2C
0x180032a34  cmp     qword ptr [rdi+108h], 0
0x180032a3c  jz      loc_180032BB0
0x180032a42  mov     rax, [rdi+0F8h]
0x180032a49  dec     rax
0x180032a4c  and     rax, [rdi+100h]
0x180032a53  mov     rdx, [rdi+0F0h]
0x180032a5a  mov     rdx, [rdx+rax*8]
0x180032a5e  lea     rcx, [rbp+57h+var_80]
0x180032a62  call    ?swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV12@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::swap(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &)
0x180032a67  mov     rax, [rdi+0F8h]
0x180032a6e  dec     rax
0x180032a71  and     rax, [rdi+100h]
0x180032a78  mov     rcx, [rdi+0F0h]
0x180032a7f  mov     rcx, [rcx+rax*8]
0x180032a83  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x180032a88  sub     qword ptr [rdi+108h], 1
0x180032a90  jnz     loc_180032B20
0x180032a96  mov     qword ptr [rdi+100h], 0
0x180032aa1  call    cs:__imp_GetCurrentThread
0x180032aa7  mov     rcx, rax; Thread
0x180032aaa  call    cs:__imp_GetThreadId
0x180032ab0  xchg    eax, [rdi+90h]
0x180032ab6  test    rsi, rsi
0x180032ab9  jz      short loc_180032AC4
0x180032abb  mov     rcx, rsi; lpCriticalSection
0x180032abe  call    cs:__imp_LeaveCriticalSection
0x180032ac4  mov     al, [rbp+57h+var_40]
0x180032ac7  cmp     al, 1
0x180032ac9  jnz     short loc_180032B0D
0x180032acb  mov     rcx, qword ptr [rbp+57h+var_80]
0x180032acf  mov     rax, [rcx]
0x180032ad2  mov     rax, [rax+8]
0x180032ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032adb  lock dec qword ptr [rdi+88h]
0x180032ae3  xor     eax, eax
0x180032ae5  xchg    eax, [rdi+90h]
0x180032aeb  lea     rcx, [rbp+57h+var_80]
0x180032aef  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x180032af4  nop
0x180032af5  mov     rcx, [rbp+57h+var_30]
0x180032af9  xor     rcx, rsp; StackCookie
0x180032afc  call    __security_check_cookie
0x180032b01  add     rsp, 0A8h
0x180032b08  pop     rdi
0x180032b09  pop     rsi
0x180032b0a  pop     rbx
0x180032b0b  pop     rbp
0x180032b0c  retn
0x180032b0d  test    al, al
0x180032b0f  jnz     loc_180032C5D
0x180032b15  lea     rcx, [rbp+57h+var_80]
0x180032b19  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180032b1e  jmp     short loc_180032ADB
0x180032b20  inc     qword ptr [rdi+100h]
0x180032b27  jmp     loc_180032AA1
0x180032b2c  cmp     qword ptr [rdi+0E0h], 0
0x180032b34  jnz     loc_180032BC7
0x180032b3a  cmp     qword ptr [rdi+0B8h], 0
0x180032b42  jz      short loc_180032BB0
0x180032b44  mov     rax, [rdi+0A8h]
0x180032b4b  dec     rax
0x180032b4e  and     rax, [rdi+0B0h]
0x180032b55  mov     rdx, [rdi+0A0h]
0x180032b5c  mov     rdx, [rdx+rax*8]
0x180032b60  lea     rcx, [rbp+57h+var_80]
0x180032b64  call    ??$emplace@V?$function@$$A6AXXZ@std@@V12@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::emplace<std::function<void (void)>,std::function<void (void)>,0,0>(std::function<void (void)> &&)
0x180032b69  mov     rax, [rdi+0A8h]
0x180032b70  dec     rax
0x180032b73  and     rax, [rdi+0B0h]
0x180032b7a  mov     rcx, [rdi+0A0h]
0x180032b81  mov     rcx, [rcx+rax*8]
0x180032b85  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180032b8a  sub     qword ptr [rdi+0B8h], 1
0x180032b92  jnz     short loc_180032BA4
0x180032b94  mov     qword ptr [rdi+0B0h], 0
0x180032b9f  jmp     loc_180032AA1
0x180032ba4  inc     qword ptr [rdi+0B0h]
0x180032bab  jmp     loc_180032AA1
0x180032bb0  test    rsi, rsi
0x180032bb3  jz      loc_180032AEB
0x180032bb9  mov     rcx, rsi; lpCriticalSection
0x180032bbc  call    cs:__imp_LeaveCriticalSection
0x180032bc2  jmp     loc_180032AEB
0x180032bc7  mov     rcx, [rdi+0D0h]
0x180032bce  dec     rcx
0x180032bd1  and     rcx, [rdi+0D8h]
0x180032bd8  mov     rax, [rdi+0C8h]
0x180032bdf  mov     rbx, [rax+rcx*8]
0x180032be3  lea     rcx, [rbp+57h+var_80]
0x180032be7  call    ?_Reset@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Reset(void)
0x180032bec  xorps   xmm0, xmm0
0x180032bef  movdqa  [rbp+57h+var_80], xmm0
0x180032bf4  mov     rax, [rbx]
0x180032bf7  mov     qword ptr [rbp+57h+var_80], rax
0x180032bfb  mov     rax, [rbx+8]
0x180032bff  mov     qword ptr [rbp+57h+var_80+8], rax
0x180032c03  mov     qword ptr [rbx], 0
0x180032c0a  mov     qword ptr [rbx+8], 0
0x180032c12  mov     [rbp+57h+var_40], 1
0x180032c16  mov     rax, [rdi+0D0h]
0x180032c1d  dec     rax
0x180032c20  and     rax, [rdi+0D8h]
0x180032c27  mov     rcx, [rdi+0C8h]
0x180032c2e  mov     rcx, [rcx+rax*8]
0x180032c32  call    ??_G?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAAPEAXI@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(uint)
0x180032c37  sub     qword ptr [rdi+0E0h], 1
0x180032c3f  jnz     short loc_180032C51
0x180032c41  mov     qword ptr [rdi+0D8h], 0
0x180032c4c  jmp     loc_180032AA1
0x180032c51  inc     qword ptr [rdi+0D8h]
0x180032c58  jmp     loc_180032AA1
0x180032c5d  xorps   xmm0, xmm0
0x180032c60  movups  [rbp+57h+var_90], xmm0
0x180032c64  lea     rax, ??_7bad_variant_access@std@@6B@; const std::bad_variant_access::`vftable'
0x180032c6b  mov     [rbp+57h+pExceptionObject], rax
0x180032c6f  lea     rdx, _TI2?AVbad_variant_access@std@@; pThrowInfo
0x180032c76  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180032c7a  call    _CxxThrowException_0
```
