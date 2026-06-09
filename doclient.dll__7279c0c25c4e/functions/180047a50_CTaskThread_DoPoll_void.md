# CTaskThread::_DoPoll(void)

- ea: `0x180047a50`
- end: `0x180047cd8`
- name: `?_DoPoll@CTaskThread@@AEAAXXZ`
- size: `648`
- prototype: `void __fastcall(CTaskThread *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180048150`

## callees

- `0x18000cdd0`
- `0x1800199b4`
- `0x180019c5c`
- `0x18001e6dc`
- `0x18001eeac`
- `0x180047a50`
- `0x180047e28`
- `0x1800a1ea4`
- `0x1800f8134`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047c44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047c44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047ae8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047bcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047c9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047ae8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047bcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180047c9e`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180047c36`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180047c36`

## string_xrefs

- `0x180047afb`: `CTaskThread::_DoPoll`
- `0x180047aee`: `Core thread exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CTaskThread::_DoPoll(
        CTaskThread *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  CTaskThread *v8; // r12
  CTaskThread *v9; // rbx
  CTaskThread *v10; // r14
  char *v11; // rsi
  int v12; // eax
  char v13; // r13
  int v14; // eax
  __int64 v15; // rbx
  __int64 *v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rcx
  bool v20; // zf
  RTL_CONDITION_VARIABLE *v21; // rcx
  int v22; // ebx
  int v23; // eax
  int v24; // [rsp+20h] [rbp-88h]
  __int64 v25; // [rsp+30h] [rbp-78h]
  __int128 v27; // [rsp+40h] [rbp-68h] BYREF
  __int64 v28; // [rsp+50h] [rbp-58h]
  __int64 v29; // [rsp+58h] [rbp-50h] BYREF
  CTaskThread *v30; // [rsp+60h] [rbp-48h]
  CTaskThread *v31; // [rsp+70h] [rbp-38h]
  char v32[8]; // [rsp+78h] [rbp-30h] BYREF
  __int64 *v33; // [rsp+80h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v8 = this;
  v9 = this;
  v10 = this;
  v30 = this;
  v31 = this;
  while ( 1 )
  {
    v11 = (char *)v9 + 16;
    v27 = (unsigned __int64)v9 + 16;
    if ( (unsigned int)mtx_do_lock((char *)v9 + 16) )
      std::_Throw_Cpp_error(5);
    v12 = *((_DWORD *)v10 + 23);
    if ( v12 == 0x7FFFFFFF )
    {
      *((_DWORD *)v10 + 23) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v13 = 1;
    BYTE8(v27) = 1;
    if ( !*((_BYTE *)v9 + 184) )
      break;
    v15 = 0;
    v28 = 0;
    if ( *((_QWORD *)v8 + 1) )
    {
      v16 = **(__int64 ***)v8;
      v29 = v16[4];
      v25 = v29;
      v17 = *(_QWORD *)std::chrono::steady_clock::now(v32);
      v18 = v25;
      if ( v25 == v17 || (v19 = 0, v25 < v17) )
      {
        v15 = v16[5];
        v16[5] = 0;
        v28 = v15;
        std::_Tree<std::_Tmap_traits<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>,std::unique_ptr<CTaskQueue::Task>,std::less<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>>,std::allocator<std::pair<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const,std::unique_ptr<CTaskQueue::Task>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const,std::unique_ptr<CTaskQueue::Task>>>>>,0>(
          (__int64)this,
          &v33,
          v16);
        v19 = v15;
        v18 = v25;
      }
    }
    else
    {
      v29 = 0x7FFFFFFFFFFFFFFFLL;
      v19 = 0;
      v18 = 0x7FFFFFFFFFFFFFFFLL;
    }
    if ( v19 )
    {
      if ( !v11 )
        std::_Throw_system_error(1);
      v20 = (*((_DWORD *)v11 + 19))-- == 1;
      if ( v20 )
      {
        *((_DWORD *)v11 + 18) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)v11 + 2);
      }
      try
      {
        v13 = 0;
        BYTE8(v27) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      }
      catch ( std::bad_alloc )
      {
        LogResult(1u, "CTaskThread::_DoPoll", 0x47u, -2147024882, "Caught std::bad_alloc");
        if ( CGlobalObjects::_pPlatformHost )
        {
          v23 = (**(__int64 (__fastcall ***)(struct IDOPlatformHost *))CGlobalObjects::_pPlatformHost)(CGlobalObjects::_pPlatformHost);
          v22 = v23;
          if ( v23 >= 0 )
            v22 = 0;
          else
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x69,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\GlobalObjects.cpp",
              (const char *)(unsigned int)v23,
              v24);
        }
        else
        {
          v22 = -2147023728;
        }
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x48,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TaskThread.cpp",
            (const char *)(unsigned int)v22,
            v24);
        v13 = BYTE8(v27);
        v11 = (char *)v27;
        v15 = v28;
        v10 = v30;
        v8 = v30;
      }
    }
    else
    {
      v21 = (RTL_CONDITION_VARIABLE *)((char *)v31 + 96);
      if ( v18 == 0x7FFFFFFFFFFFFFFFLL )
      {
        *((_DWORD *)v11 + 18) = -1;
        --*((_DWORD *)v11 + 19);
        if ( !SleepConditionVariableSRW(v21 + 1, (PSRWLOCK)v11 + 2, 0xFFFFFFFF, 0) )
          abort();
        *((_DWORD *)v11 + 18) = GetCurrentThreadId();
        ++*((_DWORD *)v11 + 19);
      }
      else
      {
        std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
          v21,
          (__int64 *)&v27,
          &v29);
      }
    }
    if ( v15 )
      (**(void (__fastcall ***)(__int64, __int64))v15)(v15, 1);
    v9 = this;
    if ( v13 )
    {
      v20 = (*((_DWORD *)v11 + 19))-- == 1;
      if ( v20 )
      {
        *((_DWORD *)v11 + 18) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)v11 + 2);
      }
    }
  }
  v14 = v12 - 1;
  *((_DWORD *)v9 + 23) = v14;
  if ( !v14 )
  {
    *((_DWORD *)v10 + 22) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)v10 + 4);
  }
  LogMessage(4u, "CTaskThread::_DoPoll", 0x55u, "Core thread exit", a5, a6, a7, a8);
}

```

## disassembly

```asm
0x180047a50  mov     [rsp+arg_8], rbx
0x180047a55  mov     [rsp+arg_10], rsi
0x180047a5a  mov     [rsp+arg_18], rdi
0x180047a5f  push    r12
0x180047a61  push    r13
0x180047a63  push    r14
0x180047a65  sub     rsp, 90h
0x180047a6c  mov     r12, rcx
0x180047a6f  mov     rbx, rcx
0x180047a72  mov     [rsp+0A8h+var_70], rcx
0x180047a77  mov     r14, rcx
0x180047a7a  mov     [rsp+0A8h+var_48], rcx
0x180047a7f  mov     [rsp+0A8h+var_38], rcx
0x180047a84  mov     rdi, 7FFFFFFFFFFFFFFFh
0x180047a8e  xorps   xmm0, xmm0
0x180047a91  movups  [rsp+0A8h+var_68], xmm0
0x180047a96  lea     rsi, [rbx+10h]
0x180047a9a  mov     qword ptr [rsp+0A8h+var_68], rsi
0x180047a9f  mov     byte ptr [rsp+0A8h+var_68+8], 0
0x180047aa4  mov     rcx, rsi
0x180047aa7  call    mtx_do_lock
0x180047aac  test    eax, eax
0x180047aae  jnz     loc_180047CA9
0x180047ab4  mov     eax, [r14+5Ch]
0x180047ab8  cmp     eax, 7FFFFFFFh
0x180047abd  jz      loc_180047CB4
0x180047ac3  mov     r13b, 1
0x180047ac6  mov     byte ptr [rsp+0A8h+var_68+8], r13b
0x180047acb  cmp     byte ptr [rbx+0B8h], 0
0x180047ad2  jnz     short loc_180047B28
0x180047ad4  sub     eax, 1
0x180047ad7  mov     [rsi+4Ch], eax
0x180047ada  jnz     short loc_180047AEE
0x180047adc  mov     dword ptr [r14+58h], 0FFFFFFFFh
0x180047ae4  lea     rcx, [r14+20h]; SRWLock
0x180047ae8  call    cs:__imp_ReleaseSRWLockExclusive
0x180047aee  lea     r9, aCoreThreadExit; "Core thread exit"
0x180047af5  mov     r8d, 55h ; 'U'; unsigned int
0x180047afb  lea     rdx, aCtaskthreadDop; "CTaskThread::_DoPoll"
0x180047b02  lea     ecx, [r8-51h]; unsigned __int8
0x180047b06  lea     r11, [rsp+0A8h+var_18]
0x180047b0e  mov     rbx, [r11+28h]
0x180047b12  mov     rsi, [r11+30h]
0x180047b16  mov     rdi, [r11+38h]
0x180047b1a  mov     rsp, r11
0x180047b1d  pop     r14
0x180047b1f  pop     r13
0x180047b21  pop     r12
0x180047b23  jmp     ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180047b28  xor     ebx, ebx
0x180047b2a  mov     [rsp+0A8h+var_58], rbx
0x180047b2f  cmp     [r12+8], rbx
0x180047b34  jz      short loc_180047BA3
0x180047b36  mov     rdi, [r12]
0x180047b3a  mov     rdi, [rdi]
0x180047b3d  mov     rax, [rdi+20h]
0x180047b41  mov     [rsp+0A8h+var_78], rax
0x180047b46  mov     [rsp+0A8h+var_50], rax
0x180047b4b  lea     rcx, [rsp+0A8h+var_30]
0x180047b50  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180047b55  mov     rdx, [rax]
0x180047b58  mov     rax, [rsp+0A8h+var_78]
0x180047b5d  cmp     rax, rdx
0x180047b60  jz      short loc_180047B69
0x180047b62  xor     ecx, ecx
0x180047b64  cmp     rax, rdx
0x180047b67  jge     short loc_180047B97
0x180047b69  mov     rbx, [rdi+28h]
0x180047b6d  mov     qword ptr [rdi+28h], 0
0x180047b75  mov     [rsp+0A8h+var_58], rbx
0x180047b7a  mov     r8, rdi
0x180047b7d  lea     rdx, [rsp+0A8h+var_28]
0x180047b85  mov     rcx, [rsp+0A8h+var_70]
0x180047b8a  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@V?$unique_ptr@VTask@CTaskQueue@@U?$default_delete@VTask@CTaskQueue@@@std@@@3@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@V?$unique_ptr@VTask@CTaskQueue@@U?$default_delete@VTask@CTaskQueue@@@std@@@3@U?$less@V?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@@3@V?$allocator@U?$pair@$$CBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@V?$unique_ptr@VTask@CTaskQueue@@U?$default_delete@VTask@CTaskQueue@@@std@@@3@@std@@@3@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@V?$unique_ptr@VTask@CTaskQueue@@U?$default_delete@VTask@CTaskQueue@@@std@@@3@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>,std::unique_ptr<CTaskQueue::Task>,std::less<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>>,std::allocator<std::pair<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const,std::unique_ptr<CTaskQueue::Task>>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const,std::unique_ptr<CTaskQueue::Task>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const,std::unique_ptr<CTaskQueue::Task>>>>>)
0x180047b8f  mov     rcx, rbx
0x180047b92  mov     rax, [rsp+0A8h+var_78]
0x180047b97  mov     rdi, 7FFFFFFFFFFFFFFFh
0x180047ba1  jmp     short loc_180047BAD
0x180047ba3  mov     [rsp+0A8h+var_50], rdi
0x180047ba8  xor     ecx, ecx
0x180047baa  mov     rax, rdi
0x180047bad  test    rcx, rcx
0x180047bb0  jz      short loc_180047C0F
0x180047bb2  test    rsi, rsi
0x180047bb5  jz      loc_180047CC7
0x180047bbb  sub     dword ptr [rsi+4Ch], 1
0x180047bbf  jnz     short loc_180047BD2
0x180047bc1  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x180047bc8  lea     rcx, [rsi+10h]; SRWLock
0x180047bcc  call    cs:__imp_ReleaseSRWLockExclusive
0x180047bd2  xor     r13b, r13b
0x180047bd5  mov     byte ptr [rsp+0A8h+var_68+8], r13b
0x180047bda  mov     rax, [rbx]
0x180047bdd  mov     rcx, rbx
0x180047be0  mov     rax, [rax+8]
0x180047be4  call    _guard_dispatch_icall
0x180047be9  nop
0x180047bea  jmp     short loc_180047C62
0x180047bec  mov     rdi, 7FFFFFFFFFFFFFFFh
0x180047bf6  mov     r13b, byte ptr [rsp+0A8h+var_68+8]
0x180047bfb  mov     rsi, qword ptr [rsp+0A8h+var_68]
0x180047c00  mov     rbx, [rsp+0A8h+var_58]
0x180047c05  mov     r14, [rsp+0A8h+var_48]
0x180047c0a  mov     r12, r14
0x180047c0d  jmp     short loc_180047C62
0x180047c0f  mov     rcx, [rsp+0A8h+var_38]
0x180047c14  add     rcx, 60h ; '`'
0x180047c18  cmp     rax, rdi
0x180047c1b  jnz     short loc_180047C52
0x180047c1d  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x180047c24  dec     dword ptr [rsi+4Ch]
0x180047c27  lea     rdx, [rsi+10h]; SRWLock
0x180047c2b  add     rcx, 8; ConditionVariable
0x180047c2f  xor     r9d, r9d; Flags
0x180047c32  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180047c36  call    cs:__imp_SleepConditionVariableSRW
0x180047c3c  test    eax, eax
0x180047c3e  jz      loc_180047CD2
0x180047c44  call    cs:__imp_GetCurrentThreadId
0x180047c4a  mov     [rsi+48h], eax
0x180047c4d  inc     dword ptr [rsi+4Ch]
0x180047c50  jmp     short loc_180047C62
0x180047c52  lea     r8, [rsp+0A8h+var_50]
0x180047c57  lea     rdx, [rsp+0A8h+var_68]
0x180047c5c  call    ??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x180047c61  nop
0x180047c62  test    rbx, rbx
0x180047c65  jz      short loc_180047C7B
0x180047c67  mov     rax, [rbx]
0x180047c6a  mov     edx, 1
0x180047c6f  mov     rcx, rbx
0x180047c72  mov     rax, [rax]
0x180047c75  call    _guard_dispatch_icall
0x180047c7a  nop
0x180047c7b  test    r13b, r13b
0x180047c7e  mov     rbx, [rsp+0A8h+var_70]
0x180047c83  jz      loc_180047A8E
0x180047c89  sub     dword ptr [rsi+4Ch], 1
0x180047c8d  jnz     loc_180047A8E
0x180047c93  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x180047c9a  lea     rcx, [rsi+10h]; SRWLock
0x180047c9e  call    cs:__imp_ReleaseSRWLockExclusive
0x180047ca4  jmp     loc_180047A8E
0x180047ca9  mov     ecx, 5; int
0x180047cae  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180047cb4  mov     dword ptr [r14+5Ch], 7FFFFFFEh
0x180047cbc  mov     ecx, 6; int
0x180047cc1  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180047cc7  mov     ecx, 1
0x180047ccc  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x180047cd2  call    abort
```
