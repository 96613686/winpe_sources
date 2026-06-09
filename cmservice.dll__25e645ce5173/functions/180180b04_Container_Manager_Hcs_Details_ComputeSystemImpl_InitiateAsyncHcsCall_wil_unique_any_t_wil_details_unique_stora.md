# Container::Manager::Hcs::Details::ComputeSystemImpl::InitiateAsyncHcsCall(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &,Container::Manager::Hcs::Details::ComputeSystemImpl::AsyncHcsCall,std::optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>)

- ea: `0x180180b04`
- end: `0x180180e57`
- name: `?InitiateAsyncHcsCall@ComputeSystemImpl@Details@Hcs@Manager@Container@@AEAA?AV?$AsyncOperation@X@Csl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4AsyncHcsCall@12345@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z`
- size: `851`
- prototype: `__int64 __fastcall(int, int, int, int, PCWSTR options)`
- caller_count: `7`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180123ce8`
- `0x18012475c`
- `0x180124c00`
- `0x180124df0`
- `0x180124ed8`
- `0x180181ea0`
- `0x180181f40`

## callees

- `0x180004fc4`
- `0x18003dbf8`
- `0x18003de70`
- `0x18003f7d8`
- `0x1800471dc`
- `0x1800491e8`
- `0x180050510`
- `0x180053ea0`
- `0x180173480`
- `0x18017fb80`
- `0x180180b04`
- `0x180182118`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180180cec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180180cec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180bb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180d20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180d48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180bb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180d20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180d0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180180bc5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180180d2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180180bc5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180180d2e`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsTerminateComputeSystem` at `0x180180c1d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsTerminateComputeSystem` at `0x180180c1d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsStartComputeSystem` at `0x180180cd7`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsStartComputeSystem` at `0x180180cd7`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsShutDownComputeSystem` at `0x180180c38`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsShutDownComputeSystem` at `0x180180c38`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSaveComputeSystem` at `0x180180c83`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSaveComputeSystem` at `0x180180c83`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsResumeComputeSystem` at `0x180180c9b`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsResumeComputeSystem` at `0x180180c9b`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180180e04`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180180e04`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsPauseComputeSystem` at `0x180180cbf`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsPauseComputeSystem` at `0x180180cbf`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCrashComputeSystem` at `0x180180c5f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCrashComputeSystem` at `0x180180c5f`

## string_xrefs

- `0x180180e3f`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Container::Manager::Hcs::Details::ComputeSystemImpl::InitiateAsyncHcsCall(
        __int64 a1,
        _QWORD *a2,
        char *a3,
        int a4,
        WCHAR *options)
{
  __int64 v9; // rax
  HCS_OPERATION v10; // r12
  HCS_OPERATION v11; // rbx
  RTL_SRWLOCK *v12; // rdi
  DWORD LastError; // ebx
  int v14; // edi
  HRESULT started; // eax
  WCHAR *v16; // r8
  const WCHAR *v17; // r8
  const WCHAR *v18; // r8
  DWORD v19; // ebx
  HCS_OPERATION v20; // rbx
  utl::_RefCountBase *v21; // rcx
  utl::_RefCountBase *v22; // r15
  char v24; // [rsp+28h] [rbp-48h] BYREF
  HCS_OPERATION v25; // [rsp+30h] [rbp-40h]
  utl::_RefCountBase *v26; // [rsp+38h] [rbp-38h]
  utl::_RefCountBase *v27; // [rsp+40h] [rbp-30h]
  HCS_OPERATION operation; // [rsp+48h] [rbp-28h] BYREF
  utl::_RefCountBase *v29[2]; // [rsp+50h] [rbp-20h]
  char v30; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  RTL_SRWLOCK *SRWLock; // [rsp+B0h] [rbp+40h]

  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v9 = Container::Manager::Hcs::Details::ComputeSystemImpl::CreateOperationsForAsyncCall(a1, &operation);
  v10 = *(HCS_OPERATION *)(v9 + 24);
  Csl::AsyncOperation<void>::operator=(a2, v9);
  Csl::AsyncOperation<void>::Cleanup(&operation);
  if ( v29[1] )
    utl::_RefCountBase::_DecStrong(v29[1]);
  v11 = operation;
  operation = 0;
  if ( v11 )
  {
    Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v11);
    operator delete(v11, (const struct std::nothrow_t *)0x30);
  }
  v12 = *(RTL_SRWLOCK **)a3;
  if ( *(_QWORD *)a3 )
  {
    LastError = GetLastError();
    ReleaseSRWLockExclusive(v12);
    SetLastError(LastError);
  }
  *(_QWORD *)a3 = 0;
  if ( a4 )
  {
    switch ( a4 )
    {
      case 1:
        if ( *((_QWORD *)options + 3) <= 7u )
          v18 = options;
        else
          v18 = *(const WCHAR **)options;
        started = HcsPauseComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, v18);
        break;
      case 2:
        started = HcsResumeComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, 0);
        break;
      case 3:
        if ( *((_QWORD *)options + 3) <= 7u )
          v17 = options;
        else
          v17 = *(const WCHAR **)options;
        started = HcsSaveComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, v17);
        break;
      case 4:
        if ( *((_QWORD *)options + 3) <= 7u )
          v16 = options;
        else
          v16 = *(WCHAR **)options;
        started = HcsCrashComputeSystem(*(_QWORD *)(a1 + 24), v10, v16);
        break;
      case 5:
        started = HcsShutDownComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, 0);
        break;
      case 6:
        started = HcsTerminateComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, 0);
        break;
      default:
        v14 = -2147418113;
        goto LABEL_32;
    }
  }
  else
  {
    started = HcsStartComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, 0);
  }
  v14 = started;
LABEL_32:
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
  if ( a3 == &v24 )
  {
    if ( a1 != -32 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
  }
  else
  {
    SRWLock = *(RTL_SRWLOCK **)a3;
    if ( *(_QWORD *)a3 )
    {
      v19 = GetLastError();
      ReleaseSRWLockExclusive(SRWLock);
      SetLastError(v19);
    }
    *(_QWORD *)a3 = a1 + 32;
  }
  if ( v14 < 0 )
  {
    Container::Manager::Hcs::Details::ComputeSystemImpl::TryRemoveContextForOperation(a1, &operation, v10);
    if ( !v30 )
      std::_Throw_bad_optional_access();
    v20 = operation;
    v25 = operation;
    operation = 0;
    v21 = v29[0];
    v26 = v29[0];
    v22 = v29[1];
    v27 = v29[1];
    *(_OWORD *)v29 = 0;
    if ( a4 == 6 )
    {
      if ( v14 == -2143878896 )
      {
        v14 = 0;
        Csl::CompletionEvent<void>::CompleteInternal(v21, 0);
      }
    }
    else if ( *(_DWORD *)(a1 + 44) )
    {
      v14 = -2143878905;
    }
    else if ( v14 == -2143878896 && a4 != 5 )
    {
      v14 = -2143878906;
    }
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
        (const char *)(unsigned int)v14,
        3);
    if ( v22 )
      utl::_RefCountBase::_DecStrong(v22);
    if ( v20 )
      HcsCloseOperation(v20);
  }
  if ( *((_BYTE *)options + 32) )
    std::wstring::~wstring(options);
  return a2;
}

```

## disassembly

```asm
0x180180b04  mov     [rsp-38h+arg_10], rbx
0x180180b09  mov     [rsp-38h+arg_18], r9d
0x180180b0e  mov     [rsp-38h+arg_8], rdx
0x180180b13  push    rbp
0x180180b14  push    rsi
0x180180b15  push    rdi
0x180180b16  push    r12
0x180180b18  push    r13
0x180180b1a  push    r14
0x180180b1c  push    r15
0x180180b1e  mov     rbp, rsp
0x180180b21  sub     rsp, 70h
0x180180b25  mov     esi, r9d
0x180180b28  mov     r13, r8
0x180180b2b  mov     rbx, rdx
0x180180b2e  mov     r14, rcx
0x180180b31  xor     r15d, r15d
0x180180b34  mov     [rbp+var_50], r15d
0x180180b38  mov     [rdx], r15
0x180180b3b  mov     [rdx+8], r15
0x180180b3f  mov     [rdx+10h], r15
0x180180b43  mov     [rbp+var_50], 1
0x180180b4a  lea     rdx, [rbp+operation]
0x180180b4e  call    ?CreateOperationsForAsyncCall@ComputeSystemImpl@Details@Hcs@Manager@Container@@AEAA?AV?$tuple@PEAUHCS_OPERATION__@@V?$AsyncOperation@X@Csl@@@std@@XZ; Container::Manager::Hcs::Details::ComputeSystemImpl::CreateOperationsForAsyncCall(void)
0x180180b53  mov     r12, [rax+18h]
0x180180b57  mov     rdx, rax
0x180180b5a  mov     rcx, rbx
0x180180b5d  call    ??4?$AsyncOperation@X@Csl@@QEAAAEAV01@$$QEAV01@@Z; Csl::AsyncOperation<void>::operator=(Csl::AsyncOperation<void> &&)
0x180180b62  lea     rcx, [rbp+operation]
0x180180b66  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x180180b6b  nop
0x180180b6c  mov     rcx, [rbp+var_20+8]; this
0x180180b70  test    rcx, rcx
0x180180b73  jz      short loc_180180B7B
0x180180b75  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180180b7a  nop
0x180180b7b  mov     rbx, [rbp+operation]
0x180180b7f  mov     [rbp+operation], r15
0x180180b83  test    rbx, rbx
0x180180b86  jz      short loc_180180B9D
0x180180b88  mov     rcx, rbx
0x180180b8b  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x180180b90  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180180b95  mov     rcx, rbx; void *
0x180180b98  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180180b9d  mov     rdi, [r13+0]
0x180180ba1  test    rdi, rdi
0x180180ba4  jz      short loc_180180BD1
0x180180ba6  call    cs:__imp_GetLastError
0x180180bad  nop     dword ptr [rax+rax+00h]
0x180180bb2  mov     ebx, eax
0x180180bb4  mov     rcx, rdi; SRWLock
0x180180bb7  call    cs:__imp_ReleaseSRWLockExclusive
0x180180bbe  nop     dword ptr [rax+rax+00h]
0x180180bc3  mov     ecx, ebx; dwErrCode
0x180180bc5  call    cs:__imp_SetLastError
0x180180bcc  nop     dword ptr [rax+rax+00h]
0x180180bd1  mov     [r13+0], r15
0x180180bd5  mov     ecx, esi
0x180180bd7  mov     rsi, [rbp+options]
0x180180bdb  test    ecx, ecx
0x180180bdd  jz      loc_180180CCD
0x180180be3  sub     ecx, 1
0x180180be6  jz      loc_180180CA9
0x180180bec  sub     ecx, 1
0x180180bef  jz      loc_180180C91
0x180180bf5  sub     ecx, 1
0x180180bf8  jz      short loc_180180C6D
0x180180bfa  sub     ecx, 1
0x180180bfd  jz      short loc_180180C49
0x180180bff  sub     ecx, 1
0x180180c02  jz      short loc_180180C2E
0x180180c04  cmp     ecx, 1
0x180180c07  jz      short loc_180180C13
0x180180c09  mov     edi, 8000FFFFh
0x180180c0e  jmp     loc_180180CE5
0x180180c13  xor     r8d, r8d; options
0x180180c16  mov     rdx, r12; operation
0x180180c19  mov     rcx, [r14+18h]; computeSystem
0x180180c1d  call    cs:__imp_HcsTerminateComputeSystem
0x180180c24  nop     dword ptr [rax+rax+00h]
0x180180c29  jmp     loc_180180CE3
0x180180c2e  xor     r8d, r8d; options
0x180180c31  mov     rdx, r12; operation
0x180180c34  mov     rcx, [r14+18h]; computeSystem
0x180180c38  call    cs:__imp_HcsShutDownComputeSystem
0x180180c3f  nop     dword ptr [rax+rax+00h]
0x180180c44  jmp     loc_180180CE3
0x180180c49  cmp     qword ptr [rsi+18h], 7
0x180180c4e  jbe     short loc_180180C55
0x180180c50  mov     r8, [rsi]
0x180180c53  jmp     short loc_180180C58
0x180180c55  mov     r8, rsi
0x180180c58  mov     rdx, r12
0x180180c5b  mov     rcx, [r14+18h]
0x180180c5f  call    cs:__imp_HcsCrashComputeSystem
0x180180c66  nop     dword ptr [rax+rax+00h]
0x180180c6b  jmp     short loc_180180CE3
0x180180c6d  cmp     qword ptr [rsi+18h], 7
0x180180c72  jbe     short loc_180180C79
0x180180c74  mov     r8, [rsi]
0x180180c77  jmp     short loc_180180C7C
0x180180c79  mov     r8, rsi; options
0x180180c7c  mov     rdx, r12; operation
0x180180c7f  mov     rcx, [r14+18h]; computeSystem
0x180180c83  call    cs:__imp_HcsSaveComputeSystem
0x180180c8a  nop     dword ptr [rax+rax+00h]
0x180180c8f  jmp     short loc_180180CE3
0x180180c91  xor     r8d, r8d; options
0x180180c94  mov     rdx, r12; operation
0x180180c97  mov     rcx, [r14+18h]; computeSystem
0x180180c9b  call    cs:__imp_HcsResumeComputeSystem
0x180180ca2  nop     dword ptr [rax+rax+00h]
0x180180ca7  jmp     short loc_180180CE3
0x180180ca9  cmp     qword ptr [rsi+18h], 7
0x180180cae  jbe     short loc_180180CB5
0x180180cb0  mov     r8, [rsi]
0x180180cb3  jmp     short loc_180180CB8
0x180180cb5  mov     r8, rsi; options
0x180180cb8  mov     rdx, r12; operation
0x180180cbb  mov     rcx, [r14+18h]; computeSystem
0x180180cbf  call    cs:__imp_HcsPauseComputeSystem
0x180180cc6  nop     dword ptr [rax+rax+00h]
0x180180ccb  jmp     short loc_180180CE3
0x180180ccd  xor     r8d, r8d; options
0x180180cd0  mov     rdx, r12; operation
0x180180cd3  mov     rcx, [r14+18h]; computeSystem
0x180180cd7  call    cs:__imp_HcsStartComputeSystem
0x180180cde  nop     dword ptr [rax+rax+00h]
0x180180ce3  mov     edi, eax
0x180180ce5  lea     r15, [r14+20h]
0x180180ce9  mov     rcx, r15; SRWLock
0x180180cec  call    cs:__imp_AcquireSRWLockExclusive
0x180180cf3  nop     dword ptr [rax+rax+00h]
0x180180cf8  lea     rax, [rbp+var_48]
0x180180cfc  cmp     r13, rax
0x180180cff  jz      short loc_180180D40
0x180180d01  mov     rax, [r13+0]
0x180180d05  mov     [rbp+SRWLock], rax
0x180180d09  test    rax, rax
0x180180d0c  jz      short loc_180180D3A
0x180180d0e  call    cs:__imp_GetLastError
0x180180d15  nop     dword ptr [rax+rax+00h]
0x180180d1a  mov     ebx, eax
0x180180d1c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180180d20  call    cs:__imp_ReleaseSRWLockExclusive
0x180180d27  nop     dword ptr [rax+rax+00h]
0x180180d2c  mov     ecx, ebx; dwErrCode
0x180180d2e  call    cs:__imp_SetLastError
0x180180d35  nop     dword ptr [rax+rax+00h]
0x180180d3a  mov     [r13+0], r15
0x180180d3e  jmp     short loc_180180D54
0x180180d40  test    r15, r15
0x180180d43  jz      short loc_180180D54
0x180180d45  mov     rcx, r15; SRWLock
0x180180d48  call    cs:__imp_ReleaseSRWLockExclusive
0x180180d4f  nop     dword ptr [rax+rax+00h]
0x180180d54  test    edi, edi
0x180180d56  jns     loc_180180E11
0x180180d5c  mov     r8, r12
0x180180d5f  lea     rdx, [rbp+operation]
0x180180d63  mov     rcx, r14
0x180180d66  call    ?TryRemoveContextForOperation@ComputeSystemImpl@Details@Hcs@Manager@Container@@AEAA?AV?$optional@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@PEAUHCS_OPERATION__@@@Z; Container::Manager::Hcs::Details::ComputeSystemImpl::TryRemoveContextForOperation(HCS_OPERATION__ *)
0x180180d6b  nop
0x180180d6c  cmp     [rbp+var_10], 0
0x180180d70  jz      loc_180180E51
0x180180d76  mov     rbx, [rbp+operation]
0x180180d7a  mov     [rbp+var_40], rbx
0x180180d7e  mov     [rbp+operation], 0
0x180180d86  mov     rcx, [rbp+var_20]
0x180180d8a  mov     [rbp+var_38], rcx
0x180180d8e  mov     r15, [rbp+var_20+8]
0x180180d92  mov     [rbp+var_30], r15
0x180180d96  xorps   xmm0, xmm0
0x180180d99  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180180d9e  mov     [rbp+var_50], 3
0x180180da5  mov     eax, [rbp+arg_18]
0x180180da8  cmp     eax, 6
0x180180dab  jnz     short loc_180180DC0
0x180180dad  cmp     edi, 80370110h
0x180180db3  jnz     short loc_180180DDF
0x180180db5  xor     edi, edi
0x180180db7  xor     edx, edx
0x180180db9  call    ?CompleteInternal@?$CompletionEvent@X@Csl@@AEAAXJ@Z; Csl::CompletionEvent<void>::CompleteInternal(long)
0x180180dbe  jmp     short loc_180180DDF
0x180180dc0  cmp     dword ptr [r14+2Ch], 0
0x180180dc5  jbe     short loc_180180DCE
0x180180dc7  mov     edi, 80370107h
0x180180dcc  jmp     short loc_180180DDF
0x180180dce  cmp     edi, 80370110h
0x180180dd4  jnz     short loc_180180DDF
0x180180dd6  lea     ecx, [rdi-0Ah]
0x180180dd9  cmp     eax, 5
0x180180ddc  cmovnz  edi, ecx
0x180180ddf  mov     rcx, [rbp+38h]; this
0x180180de3  test    edi, edi
0x180180de5  js      short loc_180180E3C
0x180180de7  mov     [rbp+var_50], 1
0x180180dee  test    r15, r15
0x180180df1  jz      short loc_180180DFC
0x180180df3  mov     rcx, r15; this
0x180180df6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180180dfb  nop
0x180180dfc  test    rbx, rbx
0x180180dff  jz      short loc_180180E11
0x180180e01  mov     rcx, rbx; operation
0x180180e04  call    cs:__imp_HcsCloseOperation
0x180180e0b  nop     dword ptr [rax+rax+00h]
0x180180e10  nop
0x180180e11  cmp     byte ptr [rsi+20h], 0
0x180180e15  jz      short loc_180180E1F
0x180180e17  mov     rcx, rsi; void *
0x180180e1a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180180e1f  mov     rax, [rbp+arg_8]
0x180180e23  mov     rbx, [rsp+70h+arg_10]
0x180180e2b  add     rsp, 70h
0x180180e2f  pop     r15
0x180180e31  pop     r14
0x180180e33  pop     r13
0x180180e35  pop     r12
0x180180e37  pop     rdi
0x180180e38  pop     rsi
0x180180e39  pop     rbp
0x180180e3a  retn
0x180180e3c  mov     r9d, edi; char *
0x180180e3f  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180180e46  mov     edx, 58Fh; void *
0x180180e4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180180e51  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
```
