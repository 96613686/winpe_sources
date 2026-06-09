# Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::Initialize(_WNF_STATE_NAME const &,void (*)(_CMS_ACTIVITY_NOTIFICATION *,void *),void *)

- ea: `0x180005540`
- end: `0x180005781`
- name: `?Initialize@?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAAJAEBU_WNF_STATE_NAME@@P6AXPEAU_CMS_ACTIVITY_NOTIFICATION@@PEAX@Z2@Z`
- size: `577`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180009270`
- `0x1800095a0`

## callees

- `0x180001574`
- `0x180001944`
- `0x180003ae4`
- `0x180005540`
- `0x1800066c4`
- `0x1800066e4`
- `0x180006f7c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000567c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800056ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000571a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000567c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800056ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000571a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000559e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000559e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005671`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005684`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005684`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::Initialize(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  struct _TP_WORK **v8; // rax
  struct _TP_WORK **v9; // rsi
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v11; // r9
  unsigned int v12; // edi
  _QWORD *v13; // rax
  utl::_RefCountBase *v14; // r15
  struct _TP_WORK *v15; // r14
  struct _TP_WORK *v16; // rbp
  DWORD LastError; // edi
  utl::_RefCountBase *v18; // rcx
  void *v19; // rbx
  int v21; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v8 = (struct _TP_WORK **)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
      (const char *)0x8007000ELL,
      v21);
    return v12;
  }
  *v8 = 0;
  v8[1] = 0;
  v8[2] = 0;
  ThreadpoolWork = CreateThreadpoolWork(
                     Csl::InProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::NotificationDeliveryThread,
                     v8,
                     0);
  if ( ThreadpoolWork )
  {
    v13 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
    v14 = (utl::_RefCountBase *)v13;
    if ( v13 )
    {
      *((_DWORD *)v13 + 2) = 1;
      *((_DWORD *)v13 + 3) = 1;
      *v13 = &utl::_RefCountVtable<utl::_RefCountStored<Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::NotificationDeliveryThreadState,utl::allocator<int>,0>,0>::`vftable';
      v15 = (struct _TP_WORK *)(v13 + 2);
      v13[2] = 0;
      v13[3] = 0;
      v13[4] = 0;
      v13[5] = 0;
      v13[6] = 0;
      v13[7] = 0;
      v13[10] = 0;
      v13[11] = 0;
      v13[12] = 0;
      v13[13] = 0;
      v13[14] = 0;
      *((_BYTE *)v13 + 120) = 0;
      *((_DWORD *)v13 + 31) = -1;
      *((_WORD *)v13 + 64) = 0;
      if ( v13 != (_QWORD *)-16LL )
      {
        *(_QWORD *)v15 = a3;
        v13[3] = a4;
        if ( v9 != (struct _TP_WORK **)&v21 )
        {
          v16 = *v9;
          if ( *v9 )
          {
            LastError = GetLastError();
            CloseThreadpoolWork(v16);
            SetLastError(LastError);
          }
          *v9 = ThreadpoolWork;
          ThreadpoolWork = 0;
        }
        v9[1] = v15;
        v18 = v9[2];
        v9[2] = v14;
        if ( v18 )
          utl::_RefCountBase::_DecStrong(v18);
        if ( ThreadpoolWork )
          CloseThreadpoolWork(ThreadpoolWork);
        goto LABEL_15;
      }
    }
    else
    {
      v14 = 0;
    }
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
      (const char *)0x8007000ELL,
      v21);
    if ( v14 )
      utl::_RefCountBase::_DecStrong(v14);
    CloseThreadpoolWork(ThreadpoolWork);
    goto LABEL_22;
  }
  v12 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x88,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
          v11);
  if ( (v12 & 0x80000000) != 0 )
  {
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
      (const char *)v12,
      v21);
    Csl::InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>::~InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>(v9);
    operator delete(v9, (const struct std::nothrow_t *)0x18);
    return v12;
  }
LABEL_15:
  *a1 = *a2;
  v19 = (void *)a1[2];
  a1[2] = v9;
  if ( v19 )
  {
    Csl::InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>::~InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>(v19);
    operator delete(v19, (const struct std::nothrow_t *)0x18);
  }
  return 0;
}

```

## disassembly

```asm
0x180005540  push    rbx
0x180005542  push    rbp
0x180005543  push    rsi
0x180005544  push    rdi
0x180005545  push    r12
0x180005547  push    r13
0x180005549  push    r14
0x18000554b  push    r15
0x18000554d  sub     rsp, 38h
0x180005551  mov     rdi, r9
0x180005554  mov     rbp, r8
0x180005557  mov     r13, rdx
0x18000555a  mov     r12, rcx
0x18000555d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005564  mov     ecx, 18h; unsigned __int64
0x180005569  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000556e  mov     rsi, rax
0x180005571  test    rax, rax
0x180005574  jz      loc_180005750
0x18000557a  mov     qword ptr [rax], 0
0x180005581  mov     qword ptr [rax+8], 0
0x180005589  mov     qword ptr [rax+10h], 0
0x180005591  xor     r8d, r8d; pcbe
0x180005594  mov     rdx, rax; pv
0x180005597  lea     rcx, ?NotificationDeliveryThread@?$InProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000559e  call    cs:__imp_CreateThreadpoolWork
0x1800055a4  mov     rbx, rax
0x1800055a7  test    rax, rax
0x1800055aa  jnz     short loc_1800055D1
0x1800055ac  mov     rcx, [rsp+78h]; this
0x1800055b1  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800055b8  mov     edx, 88h; void *
0x1800055bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800055c2  mov     edi, eax
0x1800055c4  test    eax, eax
0x1800055c6  jns     loc_1800056B4
0x1800055cc  jmp     loc_180005720
0x1800055d1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800055d8  mov     ecx, 88h; unsigned __int64
0x1800055dd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800055e2  mov     r15, rax
0x1800055e5  test    rax, rax
0x1800055e8  jz      loc_1800056E7
0x1800055ee  mov     eax, 1
0x1800055f3  mov     [r15+8], eax
0x1800055f7  mov     [r15+0Ch], eax
0x1800055fb  lea     rax, ??_7?$_RefCountVtable@V?$_RefCountStored@UNotificationDeliveryThreadState@?$InProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountStored<Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::NotificationDeliveryThreadState,utl::allocator<int>,0>,0>::`vftable'
0x180005602  mov     [r15], rax
0x180005605  lea     r14, [r15+10h]
0x180005609  mov     qword ptr [r14], 0
0x180005610  mov     qword ptr [r14+8], 0
0x180005618  xor     eax, eax
0x18000561a  mov     [r14+10h], rax
0x18000561e  mov     [r14+18h], rax
0x180005622  mov     [r14+20h], rax
0x180005626  mov     [r14+28h], rax
0x18000562a  mov     [r14+40h], rax
0x18000562e  mov     [r14+48h], rax
0x180005632  mov     [r14+50h], rax
0x180005636  mov     [r14+58h], rax
0x18000563a  mov     [r14+60h], rax
0x18000563e  mov     [r14+68h], al
0x180005642  mov     dword ptr [r14+6Ch], 0FFFFFFFFh
0x18000564a  mov     [r14+70h], ax
0x18000564f  test    r14, r14
0x180005652  jz      loc_1800056EA
0x180005658  mov     [r14], rbp
0x18000565b  mov     [r14+8], rdi
0x18000565f  lea     rax, [rsp+78h+var_58]
0x180005664  cmp     rsi, rax
0x180005667  jz      short loc_18000568F
0x180005669  mov     rbp, [rsi]
0x18000566c  test    rbp, rbp
0x18000566f  jz      short loc_18000568A
0x180005671  call    cs:__imp_GetLastError
0x180005677  mov     edi, eax
0x180005679  mov     rcx, rbp; pwk
0x18000567c  call    cs:__imp_CloseThreadpoolWork
0x180005682  mov     ecx, edi; dwErrCode
0x180005684  call    cs:__imp_SetLastError
0x18000568a  mov     [rsi], rbx
0x18000568d  xor     ebx, ebx
0x18000568f  mov     [rsi+8], r14
0x180005693  mov     rcx, [rsi+10h]; this
0x180005697  mov     [rsi+10h], r15
0x18000569b  test    rcx, rcx
0x18000569e  jz      short loc_1800056A6
0x1800056a0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800056a5  nop
0x1800056a6  test    rbx, rbx
0x1800056a9  jz      short loc_1800056B4
0x1800056ab  mov     rcx, rbx; pwk
0x1800056ae  call    cs:__imp_CloseThreadpoolWork
0x1800056b4  mov     rax, [r13+0]
0x1800056b8  mov     [r12], rax
0x1800056bc  mov     rbx, [r12+10h]
0x1800056c1  mov     [r12+10h], rsi
0x1800056c6  test    rbx, rbx
0x1800056c9  jz      short loc_1800056E0
0x1800056cb  mov     rcx, rbx
0x1800056ce  call    ??1?$InProcNotificationSubscriber@U_CMS_CONTAINER_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>::~InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>(void)
0x1800056d3  mov     edx, 18h; struct std::nothrow_t *
0x1800056d8  mov     rcx, rbx; void *
0x1800056db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800056e0  xor     eax, eax
0x1800056e2  jmp     loc_180005770
0x1800056e7  xor     r15d, r15d
0x1800056ea  mov     rcx, [rsp+78h]; this
0x1800056ef  mov     edi, 8007000Eh
0x1800056f4  mov     r9d, edi; char *
0x1800056f7  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800056fe  mov     edx, 8Eh; void *
0x180005703  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005708  nop
0x180005709  test    r15, r15
0x18000570c  jz      short loc_180005717
0x18000570e  mov     rcx, r15; this
0x180005711  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180005716  nop
0x180005717  mov     rcx, rbx; pwk
0x18000571a  call    cs:__imp_CloseThreadpoolWork
0x180005720  mov     rcx, [rsp+78h]; this
0x180005725  mov     r9d, edi; char *
0x180005728  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000572f  mov     edx, 1DAh; void *
0x180005734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005739  mov     rcx, rsi
0x18000573c  call    ??1?$InProcNotificationSubscriber@U_CMS_CONTAINER_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>::~InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>(void)
0x180005741  mov     edx, 18h; struct std::nothrow_t *
0x180005746  mov     rcx, rsi; void *
0x180005749  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000574e  jmp     short loc_18000576E
0x180005750  mov     rcx, [rsp+78h]; this
0x180005755  mov     edi, 8007000Eh
0x18000575a  mov     r9d, edi; char *
0x18000575d  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180005764  mov     edx, 1D9h; void *
0x180005769  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000576e  mov     eax, edi
0x180005770  add     rsp, 38h
0x180005774  pop     r15
0x180005776  pop     r14
0x180005778  pop     r13
0x18000577a  pop     r12
0x18000577c  pop     rdi
0x18000577d  pop     rsi
0x18000577e  pop     rbp
0x18000577f  pop     rbx
0x180005780  retn
```
