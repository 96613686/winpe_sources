# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180006854`
- end: `0x180006912`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `190`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000321c`
- `0x180006ad8`
- `0x180009588`

## callees

- `0x1800032ec`
- `0x18000336c`
- `0x18000338c`
- `0x180006498`
- `0x180006854`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800068d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800068d0`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  __int64 v2; // rsi
  __int64 Ptr; // rcx
  bool v4; // zf
  RTL_SRWLOCK *v6; // [rsp+20h] [rbp-18h] BYREF
  _BYTE v7[16]; // [rsp+28h] [rbp-10h] BYREF

  if ( !this[3].Ptr )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v7);
    if ( this[3].Ptr )
    {
      v2 = 0;
    }
    else
    {
      if ( !this[2].Ptr )
      {
        Ptr = (__int64)this[1].Ptr;
        v6 = 0;
        if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
                    Ptr,
                    (void **)&v6) >= 0
          && !this[2].Ptr )
        {
          this[2].Ptr = v6;
        }
      }
      v2 = ((__int64)this[2].Ptr + 32) & -(__int64)(this[2].Ptr != 0);
    }
    AcquireSRWLockExclusive(this + 4);
    v4 = this[3].Ptr == 0;
    v6 = this + 4;
    if ( v4 )
      this[3].Ptr = (PVOID)v2;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v7);
  }
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x180006854  mov     [rsp+arg_8], rbx
0x180006859  mov     [rsp+arg_10], rsi
0x18000685e  push    rdi
0x18000685f  sub     rsp, 30h
0x180006863  cmp     qword ptr [rcx+18h], 0
0x180006868  mov     rdi, rcx
0x18000686b  jnz     loc_1800068FA
0x180006871  lea     rcx, [rsp+38h+var_10]; this
0x180006876  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000687b  cmp     qword ptr [rdi+18h], 0
0x180006880  jz      short loc_180006886
0x180006882  xor     esi, esi
0x180006884  jmp     short loc_1800068C9
0x180006886  cmp     qword ptr [rdi+10h], 0
0x18000688b  jnz     short loc_1800068B8
0x18000688d  mov     rcx, [rdi+8]
0x180006891  lea     rdx, [rsp+38h+var_18]
0x180006896  mov     [rsp+38h+var_18], 0
0x18000689f  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800068a4  test    eax, eax
0x1800068a6  js      short loc_1800068B8
0x1800068a8  cmp     qword ptr [rdi+10h], 0
0x1800068ad  jnz     short loc_1800068B8
0x1800068af  mov     rax, [rsp+38h+var_18]
0x1800068b4  mov     [rdi+10h], rax
0x1800068b8  mov     rax, [rdi+10h]
0x1800068bc  lea     rcx, [rax+20h]
0x1800068c0  neg     rax
0x1800068c3  sbb     rsi, rsi
0x1800068c6  and     rsi, rcx
0x1800068c9  lea     rbx, [rdi+20h]
0x1800068cd  mov     rcx, rbx; SRWLock
0x1800068d0  call    cs:__imp_AcquireSRWLockExclusive
0x1800068d6  cmp     qword ptr [rdi+18h], 0
0x1800068db  mov     [rsp+38h+var_18], rbx
0x1800068e0  jnz     short loc_1800068E6
0x1800068e2  mov     [rdi+18h], rsi
0x1800068e6  lea     rcx, [rsp+38h+var_18]
0x1800068eb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800068f0  lea     rcx, [rsp+38h+var_10]; this
0x1800068f5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800068fa  cmp     qword ptr [rdi+18h], 0
0x1800068ff  mov     rbx, [rsp+38h+arg_8]
0x180006904  mov     rsi, [rsp+38h+arg_10]
0x180006909  setnz   al
0x18000690c  add     rsp, 30h
0x180006910  pop     rdi
0x180006911  retn
```
