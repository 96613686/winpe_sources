# ComputeService::Client::NotificationCallbacks::RemoveNotificationContext(void *)

- ea: `0x18002dd9c`
- end: `0x18002df63`
- name: `?RemoveNotificationContext@NotificationCallbacks@Client@ComputeService@@AEAA_NPEAX@Z`
- size: `455`
- prototype: `bool __fastcall(ComputeService::Client::NotificationCallbacks *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e058`

## callees

- `0x180006bf8`
- `0x18001587c`
- `0x180017b2c`
- `0x180018828`
- `0x180027b38`
- `0x18002d618`
- `0x18002dd9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002de97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002dec7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002de97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002dec7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ddc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dea9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ddc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dea9`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002ded1`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002ded1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002deff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002deff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002df0e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002df0e`

## string_xrefs

- `0x18002df50`: `onecore\vm\compute\dll\lib\core\notificationcallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ComputeService::Client::NotificationCallbacks::RemoveNotificationContext(
        RTL_SRWLOCK *this,
        unsigned __int64 a2)
{
  char v4; // r15
  __int64 v5; // rdi
  RTL_SRWLOCK *v6; // r12
  _QWORD *Ptr; // rdx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  __int64 **v10; // rcx
  _QWORD *v11; // rdx
  __int64 i; // rcx
  __int64 *j; // rcx
  __int64 v14; // rax
  void *v15; // r14
  void *v16; // rsi
  int v17; // r14d
  int v18; // eax
  wil *v19; // rcx
  unsigned int v21; // eax
  const char *v22; // [rsp+28h] [rbp-70h]
  int v23; // [rsp+20h] [rbp-78h]
  __int64 v24; // [rsp+38h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = 0;
  v5 = 0;
  v24 = 0;
  v6 = this + 5;
  AcquireSRWLockExclusive(this + 5);
  Ptr = this[3].Ptr;
  v8 = (_QWORD *)Ptr[1];
  v9 = Ptr;
  while ( !*((_BYTE *)v8 + 25) )
  {
    if ( v8[4] >= a2 )
    {
      v9 = v8;
      v8 = (_QWORD *)*v8;
    }
    else
    {
      v8 = (_QWORD *)v8[2];
    }
  }
  if ( !*((_BYTE *)v9 + 25) && a2 >= v9[4] && v9 != Ptr )
  {
    v5 = v9[5];
    v9[5] = 0;
    v24 = v5;
    v10 = (__int64 **)v9[2];
    v11 = v9;
    if ( *((_BYTE *)v10 + 25) )
    {
      for ( i = v9[1]; !*(_BYTE *)(i + 25) && v9 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v9 = (_QWORD *)i;
    }
    else
    {
      for ( j = *v10; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        ;
    }
    v14 = std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Extract(&this[3], v11);
    v15 = (void *)v14;
    v16 = *(void **)(v14 + 40);
    if ( v16 )
    {
      ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(*(ComputeService::Client::NotificationCallbacks::NotificationContext **)(v14 + 40));
      operator delete(v16, 0x68u);
    }
    operator delete(v15, 0x30u);
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  if ( v5 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(v5 + 72));
    v17 = *(_DWORD *)(v5 + 64);
    v4 = 1;
    *(_BYTE *)(v5 + 68) = 1;
    if ( v5 != -72 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v5 + 72));
    WakeAllConditionVariable((PCONDITION_VARIABLE)(v5 + 80));
    try
    {
      v18 = ComputeService::Client::InvokeRpcFunction<long (*)(void *),void * &>(this[1].Ptr, v5);
      v19 = retaddr;
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x125,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
          (const char *)(unsigned int)v18,
          v23);
    }
    catch ( ... )
    {
      v21 = wil::ResultFromCaughtException(v19);
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
        (const char *)v21,
        (int)"Unregister notification failed",
        v22);
      v4 = 1;
      v5 = v24;
    }
    if ( v17 == GetCurrentThreadId() )
    {
      SubmitThreadpoolWork(*(PTP_WORK *)(v5 + 88));
      v5 = 0;
    }
    else
    {
      ComputeService::Client::NotificationCallbacks::CleanupNotificationContext((PTP_WAIT *)v5);
    }
  }
  if ( v5 )
  {
    ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext((ComputeService::Client::NotificationCallbacks::NotificationContext *)v5);
    operator delete((void *)v5, 0x68u);
  }
  return v4;
}

```

## disassembly

```asm
0x18002dd9c  push    rsi
0x18002dd9e  push    rdi
0x18002dd9f  push    r12
0x18002dda1  push    r13
0x18002dda3  push    r14
0x18002dda5  push    r15
0x18002dda7  sub     rsp, 68h
0x18002ddab  mov     rsi, rdx
0x18002ddae  mov     r13, rcx
0x18002ddb1  xor     r15b, r15b
0x18002ddb4  xor     edi, edi
0x18002ddb6  mov     [rsp+98h+var_60], rdi
0x18002ddbb  lea     r12, [rcx+28h]
0x18002ddbf  mov     rcx, r12; SRWLock
0x18002ddc2  call    cs:__imp_AcquireSRWLockExclusive
0x18002ddc8  mov     rdx, [r13+18h]
0x18002ddcc  mov     rcx, [rdx+8]
0x18002ddd0  mov     rax, rdx
0x18002ddd3  jmp     short loc_18002DDE7
0x18002ddd5  cmp     [rcx+20h], rsi
0x18002ddd9  jnb     short loc_18002DDE1
0x18002dddb  mov     rcx, [rcx+10h]
0x18002dddf  jmp     short loc_18002DDE7
0x18002dde1  mov     rax, rcx
0x18002dde4  mov     rcx, [rcx]
0x18002dde7  cmp     byte ptr [rcx+19h], 0
0x18002ddeb  jz      short loc_18002DDD5
0x18002dded  cmp     byte ptr [rax+19h], 0
0x18002ddf1  jnz     loc_18002DE8F
0x18002ddf7  cmp     rsi, [rax+20h]
0x18002ddfb  jb      loc_18002DE8F
0x18002de01  cmp     rax, rdx
0x18002de04  jz      loc_18002DE8F
0x18002de0a  mov     rdi, [rax+28h]
0x18002de0e  mov     qword ptr [rax+28h], 0
0x18002de16  mov     [rsp+98h+var_60], rdi
0x18002de1b  mov     rcx, [rax+10h]
0x18002de1f  mov     rdx, rax
0x18002de22  cmp     byte ptr [rcx+19h], 0
0x18002de26  jz      short loc_18002DE43
0x18002de28  mov     rcx, [rax+8]
0x18002de2c  jmp     short loc_18002DE3B
0x18002de2e  cmp     rax, [rcx+10h]
0x18002de32  jnz     short loc_18002DE58
0x18002de34  mov     rax, rcx
0x18002de37  mov     rcx, [rcx+8]
0x18002de3b  cmp     byte ptr [rcx+19h], 0
0x18002de3f  jz      short loc_18002DE2E
0x18002de41  jmp     short loc_18002DE58
0x18002de43  mov     rcx, [rcx]
0x18002de46  cmp     byte ptr [rcx+19h], 0
0x18002de4a  jnz     short loc_18002DE58
0x18002de4c  mov     rax, [rcx]
0x18002de4f  mov     rcx, rax
0x18002de52  cmp     byte ptr [rax+19h], 0
0x18002de56  jz      short loc_18002DE4C
0x18002de58  lea     rcx, [r13+18h]
0x18002de5c  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18002de61  mov     r14, rax
0x18002de64  mov     rsi, [rax+28h]
0x18002de68  test    rsi, rsi
0x18002de6b  jz      short loc_18002DE82
0x18002de6d  mov     rcx, rsi; this
0x18002de70  call    ??1NotificationContext@NotificationCallbacks@Client@ComputeService@@QEAA@XZ; ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x18002de75  mov     edx, 68h ; 'h'; unsigned __int64
0x18002de7a  mov     rcx, rsi; void *
0x18002de7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002de82  mov     edx, 30h ; '0'; unsigned __int64
0x18002de87  mov     rcx, r14; void *
0x18002de8a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002de8f  test    r12, r12
0x18002de92  jz      short loc_18002DE9D
0x18002de94  mov     rcx, r12; SRWLock
0x18002de97  call    cs:__imp_ReleaseSRWLockExclusive
0x18002de9d  test    rdi, rdi
0x18002dea0  jz      short loc_18002DF21
0x18002dea2  lea     rsi, [rdi+48h]
0x18002dea6  mov     rcx, rsi; SRWLock
0x18002dea9  call    cs:__imp_AcquireSRWLockExclusive
0x18002deaf  mov     r14d, [rdi+40h]
0x18002deb3  mov     [rsp+98h+var_68], r14d
0x18002deb8  mov     r15b, 1
0x18002debb  mov     [rdi+44h], r15b
0x18002debf  test    rsi, rsi
0x18002dec2  jz      short loc_18002DECD
0x18002dec4  mov     rcx, rsi; SRWLock
0x18002dec7  call    cs:__imp_ReleaseSRWLockExclusive
0x18002decd  lea     rcx, [rdi+50h]; ConditionVariable
0x18002ded1  call    cs:__imp_WakeAllConditionVariable
0x18002ded7  nop
0x18002ded8  mov     rdx, rdi
0x18002dedb  mov     rcx, [r13+8]
0x18002dedf  call    ??$InvokeRpcFunction@P6AJPEAX@ZAEAPEAX@Client@ComputeService@@YA?A_TP6AJPEAX@ZAEAPEAX@Z
0x18002dee4  mov     rcx, [rsp+98h]; this
0x18002deec  test    eax, eax
0x18002deee  js      short loc_18002DF4D
0x18002def0  jmp     short loc_18002DEFF
0x18002def2  mov     r15b, 1
0x18002def5  mov     rdi, [rsp+98h+var_60]
0x18002defa  mov     r14d, [rsp+98h+var_68]
0x18002deff  call    cs:__imp_GetCurrentThreadId
0x18002df05  cmp     r14d, eax
0x18002df08  jnz     short loc_18002DF18
0x18002df0a  mov     rcx, [rdi+58h]; pwk
0x18002df0e  call    cs:__imp_SubmitThreadpoolWork
0x18002df14  xor     edi, edi
0x18002df16  jmp     short loc_18002DF21
0x18002df18  mov     rcx, rdi; struct ComputeService::Client::NotificationCallbacks::NotificationContext *
0x18002df1b  call    ?CleanupNotificationContext@NotificationCallbacks@Client@ComputeService@@CAXPEAUNotificationContext@123@@Z; ComputeService::Client::NotificationCallbacks::CleanupNotificationContext(ComputeService::Client::NotificationCallbacks::NotificationContext *)
0x18002df20  nop
0x18002df21  test    rdi, rdi
0x18002df24  jz      short loc_18002DF3B
0x18002df26  mov     rcx, rdi; this
0x18002df29  call    ??1NotificationContext@NotificationCallbacks@Client@ComputeService@@QEAA@XZ; ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x18002df2e  mov     edx, 68h ; 'h'; unsigned __int64
0x18002df33  mov     rcx, rdi; void *
0x18002df36  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002df3b  mov     al, r15b
0x18002df3e  add     rsp, 68h
0x18002df42  pop     r15
0x18002df44  pop     r14
0x18002df46  pop     r13
0x18002df48  pop     r12
0x18002df4a  pop     rdi
0x18002df4b  pop     rsi
0x18002df4c  retn
0x18002df4d  mov     r9d, eax; char *
0x18002df50  lea     r8, aOnecoreVmCompu_16; "onecore\\vm\\compute\\dll\\lib\\core\\n"...
0x18002df57  mov     edx, 125h; void *
0x18002df5c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
