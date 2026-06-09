# Hns::Client::Notifications::NotificationCallbacks::RemoveNotificationContext(void *)

- ea: `0x18000aaa0`
- end: `0x18000ac7f`
- name: `?RemoveNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@AEAA_NPEAX@Z`
- size: `479`
- prototype: `bool __fastcall(Hns::Client::Notifications::NotificationCallbacks *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ad58`

## callees

- `0x1800019d0`
- `0x1800020dc`
- `0x180004240`
- `0x180007904`
- `0x18000a208`
- `0x18000aaa0`
- `0x18000ae34`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ac23`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000ac23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aaca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000abb8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aaca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000abb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aba2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000abd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aba2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000abd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac14`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000abe3`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000abe3`

## string_xrefs

- `0x18000ac6c`: `onecore\vm\dv\net\hns\computenetwork\src\notificationcallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Hns::Client::Notifications::NotificationCallbacks::RemoveNotificationContext(
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
  const char *v22; // [rsp+28h] [rbp-50h]
  int v23; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v25; // [rsp+90h] [rbp+18h]

  v4 = 0;
  v5 = 0;
  v25 = 0;
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
    v25 = v5;
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
    v14 = std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Extract(
            &this[3],
            v11);
    v15 = (void *)v14;
    v16 = *(void **)(v14 + 40);
    if ( v16 )
    {
      Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(*(Hns::Client::Notifications::NotificationCallbacks::NotificationContext **)(v14 + 40));
      operator delete(v16, 0x60u);
    }
    operator delete(v15, 0x30u);
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  if ( v5 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(v5 + 64));
    v17 = *(_DWORD *)(v5 + 56);
    v4 = 1;
    *(_BYTE *)(v5 + 60) = 1;
    if ( v5 != -64 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v5 + 64));
    WakeAllConditionVariable((PCONDITION_VARIABLE)(v5 + 72));
    try
    {
      v18 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void * *),void * *>(this[1].Ptr, v5);
      v19 = retaddr;
      if ( v18 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
          (const char *)(unsigned int)v18,
          v23);
    }
    catch ( ... )
    {
      v21 = wil::ResultFromCaughtException(v19);
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\notificationcallbacks.cpp",
        (const char *)v21,
        (int)"Unregister notification failed",
        v22);
      v4 = 1;
      v5 = v25;
    }
    if ( v17 == GetCurrentThreadId() )
    {
      SubmitThreadpoolWork(*(PTP_WORK *)(v5 + 80));
      v5 = 0;
    }
    else
    {
      Hns::Client::Notifications::NotificationCallbacks::CleanupNotificationContext((PTP_WAIT *)v5);
    }
  }
  if ( v5 )
  {
    Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext((Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)v5);
    operator delete((void *)v5, 0x60u);
  }
  return v4;
}

```

## disassembly

```asm
0x18000aaa0  mov     rax, rsp
0x18000aaa3  mov     [rax+10h], rsi
0x18000aaa7  push    rdi
0x18000aaa8  push    r12
0x18000aaaa  push    r13
0x18000aaac  push    r14
0x18000aaae  push    r15
0x18000aab0  sub     rsp, 50h
0x18000aab4  mov     rsi, rdx
0x18000aab7  mov     r13, rcx
0x18000aaba  xor     r15b, r15b
0x18000aabd  xor     edi, edi
0x18000aabf  mov     [rax+18h], rdi
0x18000aac3  lea     r12, [rcx+28h]
0x18000aac7  mov     rcx, r12; SRWLock
0x18000aaca  call    cs:__imp_AcquireSRWLockExclusive
0x18000aad0  mov     rdx, [r13+18h]
0x18000aad4  mov     rcx, [rdx+8]
0x18000aad8  mov     rax, rdx
0x18000aadb  jmp     short loc_18000AAEF
0x18000aadd  cmp     [rcx+20h], rsi
0x18000aae1  jnb     short loc_18000AAE9
0x18000aae3  mov     rcx, [rcx+10h]
0x18000aae7  jmp     short loc_18000AAEF
0x18000aae9  mov     rax, rcx
0x18000aaec  mov     rcx, [rcx]
0x18000aaef  cmp     byte ptr [rcx+19h], 0
0x18000aaf3  jz      short loc_18000AADD
0x18000aaf5  cmp     byte ptr [rax+19h], 0
0x18000aaf9  jnz     loc_18000AB9A
0x18000aaff  cmp     rsi, [rax+20h]
0x18000ab03  jb      loc_18000AB9A
0x18000ab09  cmp     rax, rdx
0x18000ab0c  jz      loc_18000AB9A
0x18000ab12  mov     rdi, [rax+28h]
0x18000ab16  mov     qword ptr [rax+28h], 0
0x18000ab1e  mov     [rsp+78h+arg_10], rdi
0x18000ab26  mov     rcx, [rax+10h]
0x18000ab2a  mov     rdx, rax
0x18000ab2d  cmp     byte ptr [rcx+19h], 0
0x18000ab31  jz      short loc_18000AB4E
0x18000ab33  mov     rcx, [rax+8]
0x18000ab37  jmp     short loc_18000AB46
0x18000ab39  cmp     rax, [rcx+10h]
0x18000ab3d  jnz     short loc_18000AB63
0x18000ab3f  mov     rax, rcx
0x18000ab42  mov     rcx, [rcx+8]
0x18000ab46  cmp     byte ptr [rcx+19h], 0
0x18000ab4a  jz      short loc_18000AB39
0x18000ab4c  jmp     short loc_18000AB63
0x18000ab4e  mov     rcx, [rcx]
0x18000ab51  cmp     byte ptr [rcx+19h], 0
0x18000ab55  jnz     short loc_18000AB63
0x18000ab57  mov     rax, [rcx]
0x18000ab5a  mov     rcx, rax
0x18000ab5d  cmp     byte ptr [rax+19h], 0
0x18000ab61  jz      short loc_18000AB57
0x18000ab63  lea     rcx, [r13+18h]
0x18000ab67  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAXV?$unique_ptr@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@U?$default_delete@UNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void * const,std::unique_ptr<Hns::Client::Notifications::NotificationCallbacks::NotificationContext>>>>,std::_Iterator_base0>)
0x18000ab6c  mov     r14, rax
0x18000ab6f  mov     rsi, [rax+28h]
0x18000ab73  test    rsi, rsi
0x18000ab76  jz      short loc_18000AB8D
0x18000ab78  mov     rcx, rsi; this
0x18000ab7b  call    ??1NotificationContext@NotificationCallbacks@Notifications@Client@Hns@@QEAA@XZ; Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x18000ab80  mov     edx, 60h ; '`'; unsigned __int64
0x18000ab85  mov     rcx, rsi; void *
0x18000ab88  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ab8d  mov     edx, 30h ; '0'; unsigned __int64
0x18000ab92  mov     rcx, r14; void *
0x18000ab95  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ab9a  test    r12, r12
0x18000ab9d  jz      short loc_18000ABA8
0x18000ab9f  mov     rcx, r12; SRWLock
0x18000aba2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000aba8  test    rdi, rdi
0x18000abab  jz      loc_18000AC36
0x18000abb1  lea     rsi, [rdi+40h]
0x18000abb5  mov     rcx, rsi; SRWLock
0x18000abb8  call    cs:__imp_AcquireSRWLockExclusive
0x18000abbe  mov     r14d, [rdi+38h]
0x18000abc2  mov     [rsp+78h+arg_0], r14d
0x18000abca  mov     r15b, 1
0x18000abcd  mov     [rdi+3Ch], r15b
0x18000abd1  test    rsi, rsi
0x18000abd4  jz      short loc_18000ABDF
0x18000abd6  mov     rcx, rsi; SRWLock
0x18000abd9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000abdf  lea     rcx, [rdi+48h]; ConditionVariable
0x18000abe3  call    cs:__imp_WakeAllConditionVariable
0x18000abe9  nop
0x18000abea  mov     rdx, rdi
0x18000abed  mov     rcx, [r13+8]
0x18000abf1  call    ??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z
0x18000abf6  mov     rcx, [rsp+78h]; this
0x18000abfb  test    eax, eax
0x18000abfd  js      short loc_18000AC69
0x18000abff  jmp     short loc_18000AC14
0x18000ac01  mov     r15b, 1
0x18000ac04  mov     rdi, [rsp+78h+arg_10]
0x18000ac0c  mov     r14d, [rsp+78h+arg_0]
0x18000ac14  call    cs:__imp_GetCurrentThreadId
0x18000ac1a  cmp     r14d, eax
0x18000ac1d  jnz     short loc_18000AC2D
0x18000ac1f  mov     rcx, [rdi+50h]; pwk
0x18000ac23  call    cs:__imp_SubmitThreadpoolWork
0x18000ac29  xor     edi, edi
0x18000ac2b  jmp     short loc_18000AC36
0x18000ac2d  mov     rcx, rdi; struct Hns::Client::Notifications::NotificationCallbacks::NotificationContext *
0x18000ac30  call    ?CleanupNotificationContext@NotificationCallbacks@Notifications@Client@Hns@@CAXPEAUNotificationContext@1234@@Z; Hns::Client::Notifications::NotificationCallbacks::CleanupNotificationContext(Hns::Client::Notifications::NotificationCallbacks::NotificationContext *)
0x18000ac35  nop
0x18000ac36  test    rdi, rdi
0x18000ac39  jz      short loc_18000AC50
0x18000ac3b  mov     rcx, rdi; this
0x18000ac3e  call    ??1NotificationContext@NotificationCallbacks@Notifications@Client@Hns@@QEAA@XZ; Hns::Client::Notifications::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x18000ac43  mov     edx, 60h ; '`'; unsigned __int64
0x18000ac48  mov     rcx, rdi; void *
0x18000ac4b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ac50  mov     al, r15b
0x18000ac53  mov     rsi, [rsp+78h+arg_8]
0x18000ac5b  add     rsp, 50h
0x18000ac5f  pop     r15
0x18000ac61  pop     r14
0x18000ac63  pop     r13
0x18000ac65  pop     r12
0x18000ac67  pop     rdi
0x18000ac68  retn
0x18000ac69  mov     r9d, eax; char *
0x18000ac6c  lea     r8, aOnecoreVmDvNet_1; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x18000ac73  mov     edx, 0B5h; void *
0x18000ac78  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
