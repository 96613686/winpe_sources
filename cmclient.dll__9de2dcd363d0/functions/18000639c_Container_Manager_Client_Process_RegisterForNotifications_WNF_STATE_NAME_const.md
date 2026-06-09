# Container::Manager::Client::Process::RegisterForNotifications(_WNF_STATE_NAME const &)

- ea: `0x18000639c`
- end: `0x18000650c`
- name: `?RegisterForNotifications@Process@Client@Manager@Container@@QEAAJAEBU_WNF_STATE_NAME@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(Container::Manager::Client::Process *__hidden this, const struct _WNF_STATE_NAME *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1800079d0`
- `0x180008a90`

## callees

- `0x180001574`
- `0x180001944`
- `0x180003c74`
- `0x180005788`
- `0x18000639c`
- `0x1800066e4`
- `0x180006708`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000641f`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000641f`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180006462`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180006462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006414`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006427`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006427`

## string_xrefs

- `0x180006495`: `onecore\base\gendrv\silos\clem\client\dll\CmClientHandles.h`
- `0x1800064e2`: `onecore\base\gendrv\silos\clem\client\dll\CmClientHandles.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Client::Process::RegisterForNotifications(
        Container::Manager::Client::Process *this,
        struct _WNF_STATE_NAME *a2)
{
  __int64 *v4; // rax
  __int64 v5; // r8
  __int64 *v6; // rsi
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // r15
  DWORD LastError; // edi
  int v13; // eax
  void *v14; // rbx
  int v16; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v4;
  if ( !v4 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\CmClientHandles.h",
      (const char *)0x8007000ELL,
      v16);
    return v8;
  }
  v4[1] = 0;
  v4[2] = 0;
  *v4 = 0;
  v7 = Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::Initialize(v4, a2, v5, (__int64)this);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 611;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\CmClientHandles.h",
      (const char *)(unsigned int)v7,
      v16);
    Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(v6);
    operator delete(v6, (const struct std::nothrow_t *)0x18);
    return v8;
  }
  v10 = *v6;
  v11 = v6[1];
  if ( v11 )
  {
    LastError = GetLastError();
    RtlUnsubscribeWnfStateChangeNotification(v11);
    SetLastError(LastError);
  }
  v6[1] = 0;
  v13 = RtlSubscribeWnfStateChangeNotification(
          v6 + 1,
          v10,
          0,
          Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::OnWnfStateChange);
  if ( v13 < 0 )
  {
    v7 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x202,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
           (const char *)(unsigned int)v13,
           (int)v6);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 613;
      goto LABEL_9;
    }
  }
  v14 = (void *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = v6;
  if ( v14 )
  {
    Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(v14);
    operator delete(v14, (const struct std::nothrow_t *)0x18);
  }
  return 0;
}

```

## disassembly

```asm
0x18000639c  push    rbx
0x18000639e  push    rbp
0x18000639f  push    rsi
0x1800063a0  push    rdi
0x1800063a1  push    r13
0x1800063a3  push    r14
0x1800063a5  push    r15
0x1800063a7  sub     rsp, 40h
0x1800063ab  mov     rbx, rdx
0x1800063ae  mov     rbp, rcx
0x1800063b1  mov     r13d, 18h
0x1800063b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800063be  mov     ecx, r13d; unsigned __int64
0x1800063c1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800063c6  mov     rsi, rax
0x1800063c9  test    rax, rax
0x1800063cc  jz      loc_1800064DD
0x1800063d2  mov     qword ptr [rax+8], 0
0x1800063da  mov     r9, rbp
0x1800063dd  mov     qword ptr [rax+10h], 0
0x1800063e5  mov     rdx, rbx
0x1800063e8  xor     eax, eax
0x1800063ea  mov     rcx, rsi
0x1800063ed  mov     [rsi], rax
0x1800063f0  call    ?Initialize@?$OutOfProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAAJAEBU_WNF_STATE_NAME@@P6AXPEAU_CMS_PROCESS_NOTIFICATION@@PEAX@Z2@Z; Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::Initialize(_WNF_STATE_NAME const &,void (*)(_CMS_PROCESS_NOTIFICATION *,void *),void *)
0x1800063f5  mov     ebx, eax
0x1800063f7  test    eax, eax
0x1800063f9  jns     short loc_180006405
0x1800063fb  mov     edx, 263h
0x180006400  jmp     loc_180006490
0x180006405  mov     rbx, [rsi]
0x180006408  lea     r14, [rsi+8]
0x18000640c  mov     r15, [r14]
0x18000640f  test    r15, r15
0x180006412  jz      short loc_18000642D
0x180006414  call    cs:__imp_GetLastError
0x18000641a  mov     rcx, r15
0x18000641d  mov     edi, eax
0x18000641f  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180006425  mov     ecx, edi; dwErrCode
0x180006427  call    cs:__imp_SetLastError
0x18000642d  mov     [rsp+78h+var_40], 0
0x180006435  lea     r9, ?OnWnfStateChange@?$OutOfProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::OnWnfStateChange(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18000643c  mov     [rsp+78h+var_48], 0
0x180006444  xor     r8d, r8d
0x180006447  mov     [rsp+78h+var_50], 0
0x180006450  mov     rdx, rbx
0x180006453  mov     rcx, r14
0x180006456  mov     qword ptr [rsp+78h+var_58], rsi; int
0x18000645b  mov     qword ptr [r14], 0
0x180006462  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180006468  test    eax, eax
0x18000646a  jns     short loc_1800064B9
0x18000646c  mov     rcx, [rsp+78h]; this
0x180006471  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180006478  mov     r9d, eax; char *
0x18000647b  mov     edx, 202h; void *
0x180006480  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006485  mov     ebx, eax
0x180006487  test    eax, eax
0x180006489  jns     short loc_1800064B9
0x18000648b  mov     edx, 265h; void *
0x180006490  mov     rcx, [rsp+78h]; this
0x180006495  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000649c  mov     r9d, eax; char *
0x18000649f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064a4  mov     rcx, rsi
0x1800064a7  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(void)
0x1800064ac  mov     rdx, r13; struct std::nothrow_t *
0x1800064af  mov     rcx, rsi; void *
0x1800064b2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800064b7  jmp     short loc_1800064FB
0x1800064b9  mov     rbx, [rbp+20h]
0x1800064bd  mov     [rbp+20h], rsi
0x1800064c1  test    rbx, rbx
0x1800064c4  jz      short loc_1800064D9
0x1800064c6  mov     rcx, rbx
0x1800064c9  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(void)
0x1800064ce  mov     rdx, r13; struct std::nothrow_t *
0x1800064d1  mov     rcx, rbx; void *
0x1800064d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800064d9  xor     eax, eax
0x1800064db  jmp     short loc_1800064FD
0x1800064dd  mov     rcx, [rsp+78h]; this
0x1800064e2  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800064e9  mov     ebx, 8007000Eh
0x1800064ee  mov     edx, 25Fh; void *
0x1800064f3  mov     r9d, ebx; char *
0x1800064f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064fb  mov     eax, ebx
0x1800064fd  add     rsp, 40h
0x180006501  pop     r15
0x180006503  pop     r14
0x180006505  pop     r13
0x180006507  pop     rdi
0x180006508  pop     rsi
0x180006509  pop     rbp
0x18000650a  pop     rbx
0x18000650b  retn
```
