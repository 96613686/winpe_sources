# Container::Manager::Hcs::Details::ComputeSystemImpl::~ComputeSystemImpl(void)

- ea: `0x18017ebdc`
- end: `0x18017ee05`
- name: `??1ComputeSystemImpl@Details@Hcs@Manager@Container@@QEAA@XZ`
- size: `553`
- prototype: `void __fastcall(Container::Manager::Hcs::Details::ComputeSystemImpl *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18011e8f0`
- `0x18012309c`

## callees

- `0x180004fc4`
- `0x1800051b0`
- `0x18003de70`
- `0x1800471dc`
- `0x180053ea0`
- `0x180175a2c`
- `0x180175aa8`
- `0x180175dc8`
- `0x18017ebdc`
- `0x18017ee0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017ec23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017ec23`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017ecce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017ecce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ed10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ed10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017ed2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017ed2f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017ed21`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017ede6`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017ed21`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017ede6`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017ec82`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017ec82`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Hcs::Details::ComputeSystemImpl::~ComputeSystemImpl(RTL_SRWLOCK *this)
{
  _QWORD *v2; // rax
  RTL_SRWLOCK *v3; // r14
  _QWORD *v4; // rbx
  _QWORD *v5; // rsi
  void *v6; // r12
  _QWORD *v7; // r13
  utl::_RefCountBase *v8; // rcx
  HCS_OPERATION v9; // rcx
  _QWORD *v10; // rdx
  __int64 v11; // rbx
  HCS_SYSTEM v12; // rsi
  DWORD LastError; // ebx
  utl::_RefCountBase *v14; // rcx
  utl::_RefCountBase *v15; // rcx
  RTL_SRWLOCK *v16; // rcx
  utl::_RefCountBase *v17; // rcx
  HCS_SYSTEM v18; // rcx
  _QWORD *Ptr; // [rsp+20h] [rbp-18h] BYREF
  PVOID v20; // [rsp+28h] [rbp-10h]
  char v21; // [rsp+88h] [rbp+50h] BYREF

  v20 = 0;
  v2 = operator new(0x40u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  Ptr = v2;
  AcquireSRWLockExclusive(this + 4);
  v3 = this + 34;
  if ( &Ptr != (_QWORD **)&this[34] )
  {
    v4 = Ptr;
    v5 = (_QWORD *)Ptr[1];
    while ( !*((_BYTE *)v5 + 25) )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>,void *>>>(
        &Ptr,
        &Ptr,
        v5[2]);
      v6 = v5;
      v7 = v5;
      v5 = (_QWORD *)*v5;
      v8 = (utl::_RefCountBase *)v7[7];
      if ( v8 )
        utl::_RefCountBase::_DecStrong(v8);
      v9 = (HCS_OPERATION)v7[5];
      if ( v9 )
        HcsCloseOperation(v9);
      operator delete(v6, (const struct std::nothrow_t *)0x40);
    }
    v4[1] = v4;
    *v4 = v4;
    v4[2] = v4;
    v10 = Ptr;
    Ptr = v3->Ptr;
    v3->Ptr = v10;
    v20 = this[35].Ptr;
    this[35].Ptr = 0;
  }
  if ( this != (RTL_SRWLOCK *)-32LL )
    ReleaseSRWLockExclusive(this + 4);
  while ( v20 )
  {
    v11 = *Ptr;
    Csl::CompletionEvent<void>::CompleteInternal(*(_QWORD *)(*Ptr + 48LL), 2147943623LL);
    std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>>>,0>(
      &Ptr,
      &v21,
      v11);
  }
  v12 = (HCS_SYSTEM)this[3].Ptr;
  if ( v12 )
  {
    LastError = GetLastError();
    HcsCloseComputeSystem(v12);
    SetLastError(LastError);
  }
  this[3].Ptr = 0;
  std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::~_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>(&Ptr);
  std::wstring::~wstring(&this[117]);
  std::wstring::~wstring(&this[113]);
  v14 = (utl::_RefCountBase *)this[112].Ptr;
  if ( v14 )
    utl::_RefCountBase::_DecStrong(v14);
  v15 = (utl::_RefCountBase *)this[110].Ptr;
  if ( v15 )
    utl::_RefCountBase::_DecStrong(v15);
  std::wstring::~wstring(&this[105]);
  Schema::Responses::System::CrashReport::~CrashReport((Schema::Responses::System::CrashReport *)&this[37]);
  std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::~_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>(&this[34]);
  if ( LOBYTE(this[31].Ptr) )
  {
    v16 = (RTL_SRWLOCK *)this[24].Ptr;
    if ( v16 != &this[26] )
      operator delete(v16, (const struct std::nothrow_t *)&std::nothrow);
  }
  v17 = (utl::_RefCountBase *)this[8].Ptr;
  if ( v17 )
    utl::_RefCountBase::_DecStrong(v17);
  v18 = (HCS_SYSTEM)this[3].Ptr;
  if ( v18 )
    HcsCloseComputeSystem(v18);
}

```

## disassembly

```asm
0x18017ebdc  push    rbp
0x18017ebde  push    rbx
0x18017ebdf  push    rsi
0x18017ebe0  push    rdi
0x18017ebe1  push    r12
0x18017ebe3  push    r13
0x18017ebe5  push    r14
0x18017ebe7  push    r15
0x18017ebe9  mov     rbp, rsp
0x18017ebec  sub     rsp, 38h
0x18017ebf0  mov     rdi, rcx
0x18017ebf3  xor     r13d, r13d
0x18017ebf6  mov     [rbp+var_18], r13
0x18017ebfa  mov     [rbp+var_10], r13
0x18017ebfe  lea     ecx, [r13+40h]; Size
0x18017ec02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18017ec07  mov     [rax], rax
0x18017ec0a  mov     [rax+8], rax
0x18017ec0e  mov     [rax+10h], rax
0x18017ec12  mov     word ptr [rax+18h], 101h
0x18017ec18  mov     [rbp+var_18], rax
0x18017ec1c  lea     r15, [rdi+20h]
0x18017ec20  mov     rcx, r15; SRWLock
0x18017ec23  call    cs:__imp_AcquireSRWLockExclusive
0x18017ec2a  nop     dword ptr [rax+rax+00h]
0x18017ec2f  lea     r14, [rdi+110h]
0x18017ec36  lea     rax, [rbp+var_18]
0x18017ec3a  cmp     rax, r14
0x18017ec3d  jz      loc_18017ECC6
0x18017ec43  mov     rbx, [rbp+var_18]
0x18017ec47  mov     rsi, [rbx+8]
0x18017ec4b  jmp     short loc_18017EC9B
0x18017ec4d  mov     r8, [rsi+10h]
0x18017ec51  lea     rdx, [rbp+var_18]
0x18017ec55  lea     rcx, [rbp+var_18]
0x18017ec59  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEAUHCS_OPERATION__@@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHCS_OPERATION__@@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAUHCS_OPERATION__@@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEAUHCS_OPERATION__@@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>,void *>>>(std::allocator<std::_Tree_node<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>,void *>> &,std::_Tree_node<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>,void *> *)
0x18017ec5e  mov     r12, rsi
0x18017ec61  mov     r13, rsi
0x18017ec64  mov     rsi, [rsi]
0x18017ec67  mov     rcx, [r13+38h]; this
0x18017ec6b  test    rcx, rcx
0x18017ec6e  jz      short loc_18017EC76
0x18017ec70  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017ec75  nop
0x18017ec76  mov     rcx, [r13+28h]; operation
0x18017ec7a  xor     r13d, r13d
0x18017ec7d  test    rcx, rcx
0x18017ec80  jz      short loc_18017EC8E
0x18017ec82  call    cs:__imp_HcsCloseOperation
0x18017ec89  nop     dword ptr [rax+rax+00h]
0x18017ec8e  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18017ec93  mov     rcx, r12; void *
0x18017ec96  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18017ec9b  cmp     [rsi+19h], r13b
0x18017ec9f  jz      short loc_18017EC4D
0x18017eca1  mov     [rbx+8], rbx
0x18017eca5  mov     [rbx], rbx
0x18017eca8  mov     [rbx+10h], rbx
0x18017ecac  mov     rdx, [rbp+var_18]
0x18017ecb0  mov     rax, [r14]
0x18017ecb3  mov     [rbp+var_18], rax
0x18017ecb7  mov     [r14], rdx
0x18017ecba  mov     rax, [r14+8]
0x18017ecbe  mov     [rbp+var_10], rax
0x18017ecc2  mov     [r14+8], r13
0x18017ecc6  test    r15, r15
0x18017ecc9  jz      short loc_18017ECDA
0x18017eccb  mov     rcx, r15; SRWLock
0x18017ecce  call    cs:__imp_ReleaseSRWLockExclusive
0x18017ecd5  nop     dword ptr [rax+rax+00h]
0x18017ecda  cmp     [rbp+var_10], r13
0x18017ecde  jz      short loc_18017ED07
0x18017ece0  mov     rbx, [rbp+var_18]
0x18017ece4  mov     rbx, [rbx]
0x18017ece7  mov     edx, 800704C7h
0x18017ecec  mov     rcx, [rbx+30h]
0x18017ecf0  call    ?CompleteInternal@?$CompletionEvent@X@Csl@@AEAAXJ@Z; Csl::CompletionEvent<void>::CompleteInternal(long)
0x18017ecf5  mov     r8, rbx
0x18017ecf8  lea     rdx, [rbp+arg_8]
0x18017ecfc  lea     rcx, [rbp+var_18]
0x18017ed00  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@PEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@U?$less@PEAUHCS_OPERATION__@@@std@@V?$allocator@U?$pair@QEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@@std@@@9@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>>>)
0x18017ed05  jmp     short loc_18017ECDA
0x18017ed07  mov     rsi, [rdi+18h]
0x18017ed0b  test    rsi, rsi
0x18017ed0e  jz      short loc_18017ED3B
0x18017ed10  call    cs:__imp_GetLastError
0x18017ed17  nop     dword ptr [rax+rax+00h]
0x18017ed1c  mov     ebx, eax
0x18017ed1e  mov     rcx, rsi; computeSystem
0x18017ed21  call    cs:__imp_HcsCloseComputeSystem
0x18017ed28  nop     dword ptr [rax+rax+00h]
0x18017ed2d  mov     ecx, ebx; dwErrCode
0x18017ed2f  call    cs:__imp_SetLastError
0x18017ed36  nop     dword ptr [rax+rax+00h]
0x18017ed3b  mov     [rdi+18h], r13
0x18017ed3f  lea     rcx, [rbp+var_18]
0x18017ed43  call    ??1?$_Tree@V?$_Tmap_traits@PEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@U?$less@PEAUHCS_OPERATION__@@@std@@V?$allocator@U?$pair@QEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@@std@@@9@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::~_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>(void)
0x18017ed48  lea     rcx, [rdi+3A8h]; void *
0x18017ed4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017ed54  lea     rcx, [rdi+388h]; void *
0x18017ed5b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017ed60  nop
0x18017ed61  mov     rcx, [rdi+380h]; this
0x18017ed68  test    rcx, rcx
0x18017ed6b  jz      short loc_18017ED73
0x18017ed6d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017ed72  nop
0x18017ed73  mov     rcx, [rdi+370h]; this
0x18017ed7a  test    rcx, rcx
0x18017ed7d  jz      short loc_18017ED85
0x18017ed7f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017ed84  nop
0x18017ed85  lea     rcx, [rdi+348h]; void *
0x18017ed8c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017ed91  lea     rcx, [rdi+128h]; this
0x18017ed98  call    ??1CrashReport@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReport::~CrashReport(void)
0x18017ed9d  mov     rcx, r14
0x18017eda0  call    ??1?$_Tree@V?$_Tmap_traits@PEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@U?$less@PEAUHCS_OPERATION__@@@std@@V?$allocator@U?$pair@QEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@@std@@@9@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::~_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>(void)
0x18017eda5  cmp     [rdi+0F8h], r13b
0x18017edac  jz      short loc_18017EDCE
0x18017edae  mov     rcx, [rdi+0C0h]; void *
0x18017edb5  lea     rax, [rdi+0D0h]
0x18017edbc  cmp     rcx, rax
0x18017edbf  jz      short loc_18017EDCE
0x18017edc1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18017edc8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18017edcd  nop
0x18017edce  mov     rcx, [rdi+40h]; this
0x18017edd2  test    rcx, rcx
0x18017edd5  jz      short loc_18017EDDD
0x18017edd7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017eddc  nop
0x18017eddd  mov     rcx, [rdi+18h]; computeSystem
0x18017ede1  test    rcx, rcx
0x18017ede4  jz      short loc_18017EDF3
0x18017ede6  call    cs:__imp_HcsCloseComputeSystem
0x18017eded  nop     dword ptr [rax+rax+00h]
0x18017edf2  nop
0x18017edf3  add     rsp, 38h
0x18017edf7  pop     r15
0x18017edf9  pop     r14
0x18017edfb  pop     r13
0x18017edfd  pop     r12
0x18017edff  pop     rdi
0x18017ee00  pop     rsi
0x18017ee01  pop     rbx
0x18017ee02  pop     rbp
0x18017ee03  retn
```
