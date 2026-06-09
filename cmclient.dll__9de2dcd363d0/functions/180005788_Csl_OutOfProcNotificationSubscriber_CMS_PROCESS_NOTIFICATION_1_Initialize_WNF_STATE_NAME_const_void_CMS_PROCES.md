# Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::Initialize(_WNF_STATE_NAME const &,void (*)(_CMS_PROCESS_NOTIFICATION *,void *),void *)

- ea: `0x180005788`
- end: `0x1800059be`
- name: `?Initialize@?$OutOfProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAAJAEBU_WNF_STATE_NAME@@P6AXPEAU_CMS_PROCESS_NOTIFICATION@@PEAX@Z2@Z`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000639c`

## callees

- `0x180001574`
- `0x180001944`
- `0x180003b54`
- `0x180005788`
- `0x1800066c4`
- `0x1800066e4`
- `0x180006f7c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800058b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800058ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180005957`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800058b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800058ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180005957`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800057da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800057da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::Initialize(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  struct _TP_WORK **v7; // rax
  struct _TP_WORK **v8; // rsi
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v10; // r9
  unsigned int v11; // edi
  _QWORD *v12; // rax
  utl::_RefCountBase *v13; // r15
  struct _TP_WORK *v14; // r14
  struct _TP_WORK *v15; // r12
  DWORD LastError; // edi
  utl::_RefCountBase *v17; // rcx
  void *v18; // rbx
  int v20; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v7 = (struct _TP_WORK **)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
      (const char *)0x8007000ELL,
      v20);
    return v11;
  }
  *v7 = 0;
  v7[1] = 0;
  v7[2] = 0;
  ThreadpoolWork = CreateThreadpoolWork(
                     Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::NotificationDeliveryThread,
                     v7,
                     0);
  if ( ThreadpoolWork )
  {
    v12 = operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
    v13 = (utl::_RefCountBase *)v12;
    if ( v12 )
    {
      *((_DWORD *)v12 + 2) = 1;
      *((_DWORD *)v12 + 3) = 1;
      *v12 = &utl::_RefCountVtable<utl::_RefCountStored<Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::NotificationDeliveryThreadState,utl::allocator<int>,0>,0>::`vftable';
      v14 = (struct _TP_WORK *)(v12 + 2);
      v12[2] = 0;
      v12[3] = 0;
      v12[4] = 0;
      v12[5] = 0;
      v12[6] = 0;
      v12[7] = 0;
      v12[9] = 0;
      v12[10] = 0;
      v12[11] = 0;
      v12[12] = 0;
      v12[13] = 0;
      *((_BYTE *)v12 + 112) = 0;
      *((_DWORD *)v12 + 29) = -1;
      *((_WORD *)v12 + 60) = 0;
      if ( v12 != (_QWORD *)-16LL )
      {
        *(_QWORD *)v14 = Container::Manager::Client::Process::OnNotificationReceived;
        v12[3] = a4;
        if ( v8 != (struct _TP_WORK **)&v20 )
        {
          v15 = *v8;
          if ( *v8 )
          {
            LastError = GetLastError();
            CloseThreadpoolWork(v15);
            SetLastError(LastError);
          }
          *v8 = ThreadpoolWork;
          ThreadpoolWork = 0;
        }
        v8[1] = v14;
        v17 = v8[2];
        v8[2] = v13;
        if ( v17 )
          utl::_RefCountBase::_DecStrong(v17);
        if ( ThreadpoolWork )
          CloseThreadpoolWork(ThreadpoolWork);
        goto LABEL_15;
      }
    }
    else
    {
      v13 = 0;
    }
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
      (const char *)0x8007000ELL,
      v20);
    if ( v13 )
      utl::_RefCountBase::_DecStrong(v13);
    CloseThreadpoolWork(ThreadpoolWork);
    goto LABEL_22;
  }
  v11 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x88,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
          v10);
  if ( (v11 & 0x80000000) != 0 )
  {
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
      (const char *)v11,
      v20);
    Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(v8);
    operator delete(v8, (const struct std::nothrow_t *)0x18);
    return v11;
  }
LABEL_15:
  *a1 = *a2;
  v18 = (void *)a1[2];
  a1[2] = v8;
  if ( v18 )
  {
    Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(v18);
    operator delete(v18, (const struct std::nothrow_t *)0x18);
  }
  return 0;
}

```

## disassembly

```asm
0x180005788  push    rbx
0x18000578a  push    rbp
0x18000578b  push    rsi
0x18000578c  push    rdi
0x18000578d  push    r12
0x18000578f  push    r13
0x180005791  push    r14
0x180005793  push    r15
0x180005795  sub     rsp, 38h
0x180005799  mov     rdi, r9
0x18000579c  mov     r13, rdx
0x18000579f  mov     rbp, rcx
0x1800057a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800057a9  mov     ecx, 18h; unsigned __int64
0x1800057ae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800057b3  mov     rsi, rax
0x1800057b6  xor     r12d, r12d
0x1800057b9  test    rax, rax
0x1800057bc  jz      loc_18000598D
0x1800057c2  mov     [rax], r12
0x1800057c5  mov     [rax+8], r12
0x1800057c9  mov     [rax+10h], r12
0x1800057cd  xor     r8d, r8d; pcbe
0x1800057d0  mov     rdx, rax; pv
0x1800057d3  lea     rcx, ?NotificationDeliveryThread@?$InProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800057da  call    cs:__imp_CreateThreadpoolWork
0x1800057e0  mov     rbx, rax
0x1800057e3  test    rax, rax
0x1800057e6  jnz     short loc_18000580D
0x1800057e8  mov     rcx, [rsp+78h]; this
0x1800057ed  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800057f4  mov     edx, 88h; void *
0x1800057f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800057fe  mov     edi, eax
0x180005800  test    eax, eax
0x180005802  jns     loc_1800058F3
0x180005808  jmp     loc_18000595D
0x18000580d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005814  mov     ecx, 80h; unsigned __int64
0x180005819  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000581e  mov     r15, rax
0x180005821  test    rax, rax
0x180005824  jz      loc_180005924
0x18000582a  mov     eax, 1
0x18000582f  mov     [r15+8], eax
0x180005833  mov     [r15+0Ch], eax
0x180005837  lea     rax, ??_7?$_RefCountVtable@V?$_RefCountStored@UNotificationDeliveryThreadState@?$InProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountStored<Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::NotificationDeliveryThreadState,utl::allocator<int>,0>,0>::`vftable'
0x18000583e  mov     [r15], rax
0x180005841  lea     r14, [r15+10h]
0x180005845  mov     [r14], r12
0x180005848  mov     [r14+8], r12
0x18000584c  xor     eax, eax
0x18000584e  mov     [r14+10h], rax
0x180005852  mov     [r14+18h], rax
0x180005856  mov     [r14+20h], rax
0x18000585a  mov     [r14+28h], rax
0x18000585e  mov     [r14+38h], r12
0x180005862  mov     [r14+40h], r12
0x180005866  mov     [r14+48h], r12
0x18000586a  mov     [r14+50h], r12
0x18000586e  mov     [r14+58h], r12
0x180005872  mov     [r14+60h], r12b
0x180005876  mov     dword ptr [r14+64h], 0FFFFFFFFh
0x18000587e  mov     [r14+68h], r12w
0x180005883  test    r14, r14
0x180005886  jz      loc_180005927
0x18000588c  lea     rax, ?OnNotificationReceived@Process@Client@Manager@Container@@CAXPEAU_CMS_PROCESS_NOTIFICATION@@PEAX@Z; Container::Manager::Client::Process::OnNotificationReceived(_CMS_PROCESS_NOTIFICATION *,void *)
0x180005893  mov     [r14], rax
0x180005896  mov     [r14+8], rdi
0x18000589a  lea     rax, [rsp+78h+var_58]
0x18000589f  cmp     rsi, rax
0x1800058a2  jz      short loc_1800058CE
0x1800058a4  mov     r12, [rsi]
0x1800058a7  test    r12, r12
0x1800058aa  jz      short loc_1800058C5
0x1800058ac  call    cs:__imp_GetLastError
0x1800058b2  mov     edi, eax
0x1800058b4  mov     rcx, r12; pwk
0x1800058b7  call    cs:__imp_CloseThreadpoolWork
0x1800058bd  mov     ecx, edi; dwErrCode
0x1800058bf  call    cs:__imp_SetLastError
0x1800058c5  mov     [rsi], rbx
0x1800058c8  xor     r12d, r12d
0x1800058cb  mov     ebx, r12d
0x1800058ce  mov     [rsi+8], r14
0x1800058d2  mov     rcx, [rsi+10h]; this
0x1800058d6  mov     [rsi+10h], r15
0x1800058da  test    rcx, rcx
0x1800058dd  jz      short loc_1800058E5
0x1800058df  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800058e4  nop
0x1800058e5  test    rbx, rbx
0x1800058e8  jz      short loc_1800058F3
0x1800058ea  mov     rcx, rbx; pwk
0x1800058ed  call    cs:__imp_CloseThreadpoolWork
0x1800058f3  mov     rax, [r13+0]
0x1800058f7  mov     [rbp+0], rax
0x1800058fb  mov     rbx, [rbp+10h]
0x1800058ff  mov     [rbp+10h], rsi
0x180005903  test    rbx, rbx
0x180005906  jz      short loc_18000591D
0x180005908  mov     rcx, rbx
0x18000590b  call    ??1?$InProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(void)
0x180005910  mov     edx, 18h; struct std::nothrow_t *
0x180005915  mov     rcx, rbx; void *
0x180005918  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000591d  xor     eax, eax
0x18000591f  jmp     loc_1800059AD
0x180005924  mov     r15, r12
0x180005927  mov     rcx, [rsp+78h]; this
0x18000592c  mov     edi, 8007000Eh
0x180005931  mov     r9d, edi; char *
0x180005934  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000593b  mov     edx, 8Eh; void *
0x180005940  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005945  nop
0x180005946  test    r15, r15
0x180005949  jz      short loc_180005954
0x18000594b  mov     rcx, r15; this
0x18000594e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180005953  nop
0x180005954  mov     rcx, rbx; pwk
0x180005957  call    cs:__imp_CloseThreadpoolWork
0x18000595d  mov     rcx, [rsp+78h]; this
0x180005962  mov     r9d, edi; char *
0x180005965  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000596c  mov     edx, 1DAh; void *
0x180005971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005976  mov     rcx, rsi
0x180005979  call    ??1?$InProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(void)
0x18000597e  mov     edx, 18h; struct std::nothrow_t *
0x180005983  mov     rcx, rsi; void *
0x180005986  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000598b  jmp     short loc_1800059AB
0x18000598d  mov     rcx, [rsp+78h]; this
0x180005992  mov     edi, 8007000Eh
0x180005997  mov     r9d, edi; char *
0x18000599a  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800059a1  mov     edx, 1D9h; void *
0x1800059a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800059ab  mov     eax, edi
0x1800059ad  add     rsp, 38h
0x1800059b1  pop     r15
0x1800059b3  pop     r14
0x1800059b5  pop     r13
0x1800059b7  pop     r12
0x1800059b9  pop     rdi
0x1800059ba  pop     rsi
0x1800059bb  pop     rbp
0x1800059bc  pop     rbx
0x1800059bd  retn
```
