# WcmCommon::ThreadPoolWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180024220`
- end: `0x1800244d7`
- name: `?WorkCallback@ThreadPoolWorkQueue@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `695`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x18001d590`
- `0x1800241e8`
- `0x180024220`
- `0x180024548`
- `0x180024564`
- `0x180040594`
- `0x180041694`
- `0x180042bcc`
- `0x180047240`
- `0x180047fa8`
- `0x18006d6b0`
- `0x18006d840`
- `0x18006e38c`
- `0x18006e3d0`
- `0x18006e414`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002432b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002432b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024322`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024322`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002433f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800243e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024477`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002433f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800243e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024477`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002425e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002425e`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::WorkCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        char *a2,
        struct _TP_WORK *a3)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  bool v5; // zf
  __int64 v6; // rbx
  HANDLE CurrentThread; // rax
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rcx
  void **pExceptionObject; // [rsp+20h] [rbp-39h] BYREF
  __int128 v12; // [rsp+28h] [rbp-31h]
  _OWORD v13[3]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v14; // [rsp+78h] [rbp+1Fh]
  char v15; // [rsp+80h] [rbp+27h]

  v14 = 0;
  v15 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)(a2 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  if ( *(_DWORD *)a2 == 1 )
  {
    if ( *((_QWORD *)a2 + 28) )
    {
      v6 = std::deque<std::function<void (void)>>::front(a2 + 192);
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(v13);
      v15 = -1;
      v13[0] = 0;
      v13[0] = *(_OWORD *)v6;
      *(_QWORD *)v6 = 0;
      *(_QWORD *)(v6 + 8) = 0;
      v15 = 1;
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::pop_front(a2 + 192);
    }
    else
    {
      if ( !*((_QWORD *)a2 + 23) )
      {
        if ( v4 )
          LeaveCriticalSection(v4);
        if ( v15 != -1 )
        {
          v5 = v15 == 0;
          goto LABEL_8;
        }
        return;
      }
      v8 = std::deque<std::function<void (void)>>::front(a2 + 152);
      if ( v15 != -1 )
        std::_Func_class<void,>::_Tidy(v13);
      v15 = -1;
      v14 = 0;
      std::_Func_class<void,>::_Reset_move(v13, v8);
      v15 = 0;
      std::deque<std::function<void (void)>>::pop_front(a2 + 152);
    }
  }
  else
  {
    if ( !*((_QWORD *)a2 + 33) )
    {
      if ( v4 )
        LeaveCriticalSection(v4);
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(v13);
      return;
    }
    v9 = std::deque<std::function<void (void)>>::front(a2 + 232);
    pExceptionObject = (void **)v13;
    *(_QWORD *)&v12 = v9;
    if ( v15 == -1 )
    {
      `std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::swap'::`3'::_lambda_1_::operator()<std::_Tagged<std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &,-1>>((__int64 *)&pExceptionObject);
    }
    else
    {
      *(_QWORD *)&v12 = v9;
      pExceptionObject = (void **)v13;
      *((_QWORD *)&v12 + 1) = v13;
      v10 = *(char *)(v9 + 64);
      if ( v15 )
        ____Visit_V_lambda_1___1_____RU___Tagged_AEAV__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___std___00_std___1_2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__QEAAXAEAV34__Z_QEBA_A_PU___Tagged_AEAV__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___std___00_4__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__4_____Variant_raw_visit1__00_std__SAX_K__QEAV_lambda_1___1_____RU___Tagged_AEAV__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___std___00_std___2_2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1_QEAAXAEAV41__Z_QEBA_A_PU___Tagged_AEAV__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___std___00_1__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1__Z(
          v10 + 1,
          (__int64 *)&pExceptionObject,
          (__int64 *)v9);
      else
        ____Visit_V_lambda_1___1_____RU___Tagged_AEAV__function___A6AXXZ_std___0A__std___1_2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__QEAAXAEAV34__Z_QEBA_A_PU___Tagged_AEAV__function___A6AXXZ_std___0A__4__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__4_____Variant_raw_visit1__00_std__SAX_K__QEAV_lambda_1___1_____RU___Tagged_AEAV__function___A6AXXZ_std___0A__std___2_2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1_QEAAXAEAV41__Z_QEBA_A_PU___Tagged_AEAV__function___A6AXXZ_std___0A__1__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1__Z(
          v10 + 1,
          (_BYTE **)&pExceptionObject,
          (_QWORD *)v9);
    }
    std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::pop_front(a2 + 232);
  }
  CurrentThread = GetCurrentThread();
  _InterlockedExchange((volatile __int32 *)a2 + 36, GetThreadId(CurrentThread));
  if ( v4 )
    LeaveCriticalSection(v4);
  if ( v15 == 1 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v13[0] + 8LL))(*(_QWORD *)&v13[0]);
  }
  else
  {
    if ( v15 )
    {
      v12 = 0;
      pExceptionObject = &std::bad_variant_access::`vftable';
      throw (std::bad_variant_access *)&pExceptionObject;
    }
    std::_Func_class<void,>::operator()(v13);
  }
  _InterlockedDecrement64((volatile signed __int64 *)a2 + 17);
  _InterlockedExchange((volatile __int32 *)a2 + 36, 0);
  if ( v15 != -1 )
  {
    v5 = v15 == 0;
LABEL_8:
    if ( v5 )
      std::_Func_class<void,>::_Tidy(v13);
    else
      std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(v13);
  }
}

```

## disassembly

```asm
0x180024220  mov     [rsp-8+arg_0], rbx
0x180024225  mov     [rsp-8+arg_10], rsi
0x18002422a  push    rbp
0x18002422b  push    rdi
0x18002422c  push    r14
0x18002422e  lea     rbp, [rsp-47h]
0x180024233  sub     rsp, 0A0h
0x18002423a  mov     rax, cs:__security_cookie
0x180024241  xor     rax, rsp
0x180024244  mov     [rbp+57h+var_20], rax
0x180024248  mov     rsi, rdx
0x18002424b  mov     [rbp+57h+var_38], 0
0x180024253  mov     [rbp+57h+var_30], 0
0x180024257  lea     r14, [rdx+8]
0x18002425b  mov     rcx, r14; lpCriticalSection
0x18002425e  call    cs:__imp_EnterCriticalSection
0x180024264  cmp     dword ptr [rsi], 1
0x180024267  jnz     loc_1800243F2
0x18002426d  cmp     qword ptr [rsi+0E0h], 0
0x180024275  jnz     short loc_1800242D1
0x180024277  cmp     qword ptr [rsi+0B8h], 0
0x18002427f  jnz     loc_18002438B
0x180024285  test    r14, r14
0x180024288  jnz     loc_1800243E4
0x18002428e  movsx   rax, [rbp+57h+var_30]
0x180024293  add     rax, 1
0x180024297  jz      short loc_1800242AD
0x180024299  cmp     rax, 1
0x18002429d  lea     rcx, [rbp+57h+var_70]
0x1800242a1  jnz     loc_1800244CD
0x1800242a7  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800242ac  nop
0x1800242ad  mov     rcx, [rbp+57h+var_20]
0x1800242b1  xor     rcx, rsp; StackCookie
0x1800242b4  call    __security_check_cookie
0x1800242b9  lea     r11, [rsp+0B0h+var_10]
0x1800242c1  mov     rbx, [r11+20h]
0x1800242c5  mov     rsi, [r11+30h]
0x1800242c9  mov     rsp, r11
0x1800242cc  pop     r14
0x1800242ce  pop     rdi
0x1800242cf  pop     rbp
0x1800242d0  retn
0x1800242d1  lea     rdi, [rsi+0C0h]
0x1800242d8  mov     rcx, rdi
0x1800242db  call    ?front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@2@XZ; std::deque<std::function<void (void)>>::front(void)
0x1800242e0  mov     rbx, rax
0x1800242e3  lea     rcx, [rbp+57h+var_70]
0x1800242e7  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x1800242ec  mov     [rbp+57h+var_30], 0FFh
0x1800242f0  xorps   xmm0, xmm0
0x1800242f3  movdqa  [rbp+57h+var_70], xmm0
0x1800242f8  mov     rcx, [rbx]
0x1800242fb  mov     qword ptr [rbp+57h+var_70], rcx
0x1800242ff  mov     rcx, [rbx+8]
0x180024303  mov     qword ptr [rbp+57h+var_70+8], rcx
0x180024307  mov     qword ptr [rbx], 0
0x18002430e  mov     qword ptr [rbx+8], 0
0x180024316  mov     [rbp+57h+var_30], 1
0x18002431a  mov     rcx, rdi
0x18002431d  call    ?pop_front@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAXXZ; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::pop_front(void)
0x180024322  call    cs:__imp_GetCurrentThread
0x180024328  mov     rcx, rax; Thread
0x18002432b  call    cs:__imp_GetThreadId
0x180024331  xchg    eax, [rsi+90h]
0x180024337  test    r14, r14
0x18002433a  jz      short loc_180024345
0x18002433c  mov     rcx, r14; lpCriticalSection
0x18002433f  call    cs:__imp_LeaveCriticalSection
0x180024345  mov     al, [rbp+57h+var_30]
0x180024348  cmp     al, 1
0x18002434a  jnz     loc_18002445D
0x180024350  lea     rcx, [rbp+57h+var_70]
0x180024354  mov     rcx, [rcx]
0x180024357  mov     rax, [rcx]
0x18002435a  mov     rax, [rax+8]
0x18002435e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024363  lock dec qword ptr [rsi+88h]
0x18002436b  xor     eax, eax
0x18002436d  xchg    eax, [rsi+90h]
0x180024373  movsx   rcx, [rbp+57h+var_30]
0x180024378  add     rcx, 1
0x18002437c  jz      loc_1800242AD
0x180024382  cmp     rcx, 1
0x180024386  jmp     loc_18002429D
0x18002438b  lea     rbx, [rsi+98h]
0x180024392  mov     rcx, rbx
0x180024395  call    ?front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@2@XZ; std::deque<std::function<void (void)>>::front(void)
0x18002439a  mov     rdi, rax
0x18002439d  movsx   rcx, [rbp+57h+var_30]
0x1800243a2  add     rcx, 1
0x1800243a6  jz      short loc_1800243BB
0x1800243a8  cmp     rcx, 1
0x1800243ac  lea     rcx, [rbp+57h+var_70]
0x1800243b0  jnz     loc_18002448B
0x1800243b6  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800243bb  mov     [rbp+57h+var_30], 0FFh
0x1800243bf  mov     [rbp+57h+var_38], 0
0x1800243c7  mov     rdx, rdi
0x1800243ca  lea     rcx, [rbp+57h+var_70]
0x1800243ce  call    ?_Reset_move@?$_Func_class@X$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,>::_Reset_move(std::_Func_class<void,> &&)
0x1800243d3  mov     [rbp+57h+var_30], 0
0x1800243d7  mov     rcx, rbx
0x1800243da  call    ?pop_front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAXXZ; std::deque<std::function<void (void)>>::pop_front(void)
0x1800243df  jmp     loc_180024322
0x1800243e4  mov     rcx, r14; lpCriticalSection
0x1800243e7  call    cs:__imp_LeaveCriticalSection
0x1800243ed  jmp     loc_18002428E
0x1800243f2  cmp     qword ptr [rsi+108h], 0
0x1800243fa  jz      short loc_18002446F
0x1800243fc  lea     rbx, [rsi+0E8h]
0x180024403  mov     rcx, rbx
0x180024406  call    ?front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@2@XZ; std::deque<std::function<void (void)>>::front(void)
0x18002440b  lea     rcx, [rbp+57h+var_70]
0x18002440f  mov     [rbp+57h+pExceptionObject], rcx
0x180024413  mov     qword ptr [rbp+57h+var_88], rax
0x180024417  movsx   rcx, [rbp+57h+var_30]
0x18002441c  add     rcx, 1
0x180024420  jz      short loc_18002449F
0x180024422  mov     qword ptr [rbp+57h+var_88], rax
0x180024426  mov     r8, rax
0x180024429  lea     rdx, [rbp+57h+pExceptionObject]
0x18002442d  cmp     rcx, 1
0x180024431  lea     rcx, [rbp+57h+var_70]
0x180024435  mov     [rbp+57h+pExceptionObject], rcx
0x180024439  lea     rcx, [rbp+57h+var_70]
0x18002443d  mov     qword ptr [rbp+57h+var_88+8], rcx
0x180024441  movsx   rcx, byte ptr [rax+40h]
0x180024446  jz      short loc_180024495
0x180024448  inc     rcx
0x18002444b  call    ??$_Visit@V_lambda_1_@?1???$?RU?$_Tagged@AEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@$00@std@@@1?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV34@@Z@QEBA?A_PU?$_Tagged@AEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@$00@4@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@4@@?$_Variant_raw_visit1@$00@std@@SAX_K$$QEAV_lambda_1_@?1???$?RU?$_Tagged@AEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@$00@std@@@2?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@QEAAXAEAV41@@Z@QEBA?A_PU?$_Tagged@AEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@$00@1@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z
0x180024450  mov     rcx, rbx
0x180024453  call    ?pop_front@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAXXZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::pop_front(void)
0x180024458  jmp     loc_180024322
0x18002445d  test    al, al
0x18002445f  jnz     short loc_1800244AA
0x180024461  lea     rcx, [rbp+57h+var_70]
0x180024465  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18002446a  jmp     loc_180024363
0x18002446f  test    r14, r14
0x180024472  jz      short loc_18002447D
0x180024474  mov     rcx, r14; lpCriticalSection
0x180024477  call    cs:__imp_LeaveCriticalSection
0x18002447d  lea     rcx, [rbp+57h+var_70]
0x180024481  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x180024486  jmp     loc_1800242AD
0x18002448b  call    ??_G?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAAPEAXI@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(uint)
0x180024490  jmp     loc_1800243BB
0x180024495  inc     rcx
0x180024498  call    ??$_Visit@V_lambda_1_@?1???$?RU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@std@@@1?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV34@@Z@QEBA?A_PU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@4@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@4@@?$_Variant_raw_visit1@$00@std@@SAX_K$$QEAV_lambda_1_@?1???$?RU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@std@@@2?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@QEAAXAEAV41@@Z@QEBA?A_PU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@1@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z
0x18002449d  jmp     short loc_180024450
0x18002449f  lea     rcx, [rbp+57h+pExceptionObject]
0x1800244a3  call    ??$?RU?$_Tagged@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@$0?0@std@@@_lambda_1_@?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV23@@Z@QEBA?A_PU?$_Tagged@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@$0?0@3@@Z
0x1800244a8  jmp     short loc_180024450
0x1800244aa  xorps   xmm0, xmm0
0x1800244ad  movups  [rbp+57h+var_88], xmm0
0x1800244b1  lea     rax, ??_7bad_variant_access@std@@6B@; const std::bad_variant_access::`vftable'
0x1800244b8  mov     [rbp+57h+pExceptionObject], rax
0x1800244bc  lea     rdx, _TI2?AVbad_variant_access@std@@; pThrowInfo
0x1800244c3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800244c7  call    _CxxThrowException_0
0x1800244cd  call    ??_G?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAAPEAXI@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(uint)
0x1800244d2  jmp     loc_1800242AD
```
