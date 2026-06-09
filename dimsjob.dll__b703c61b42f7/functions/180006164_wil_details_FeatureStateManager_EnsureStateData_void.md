# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x180006164`
- end: `0x180006222`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `190`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800034f4`
- `0x1800063b4`
- `0x180009118`

## callees

- `0x1800035bc`
- `0x180003620`
- `0x180003640`
- `0x180005e10`
- `0x180006164`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800061e0`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  __int64 v2; // rsi
  __int64 Ptr; // rcx
  bool v4; // zf
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF
  char v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !this[3].Ptr )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
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
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
  }
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x180006164  mov     [rsp+arg_10], rbx
0x180006169  mov     [rsp+arg_18], rsi
0x18000616e  push    rdi
0x18000616f  sub     rsp, 20h
0x180006173  cmp     qword ptr [rcx+18h], 0
0x180006178  mov     rdi, rcx
0x18000617b  jnz     loc_18000620A
0x180006181  lea     rcx, [rsp+28h+arg_8]; this
0x180006186  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000618b  cmp     qword ptr [rdi+18h], 0
0x180006190  jz      short loc_180006196
0x180006192  xor     esi, esi
0x180006194  jmp     short loc_1800061D9
0x180006196  cmp     qword ptr [rdi+10h], 0
0x18000619b  jnz     short loc_1800061C8
0x18000619d  mov     rcx, [rdi+8]
0x1800061a1  lea     rdx, [rsp+28h+arg_0]
0x1800061a6  mov     [rsp+28h+arg_0], 0
0x1800061af  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1800061b4  test    eax, eax
0x1800061b6  js      short loc_1800061C8
0x1800061b8  cmp     qword ptr [rdi+10h], 0
0x1800061bd  jnz     short loc_1800061C8
0x1800061bf  mov     rax, [rsp+28h+arg_0]
0x1800061c4  mov     [rdi+10h], rax
0x1800061c8  mov     rax, [rdi+10h]
0x1800061cc  lea     rcx, [rax+20h]
0x1800061d0  neg     rax
0x1800061d3  sbb     rsi, rsi
0x1800061d6  and     rsi, rcx
0x1800061d9  lea     rbx, [rdi+20h]
0x1800061dd  mov     rcx, rbx; SRWLock
0x1800061e0  call    cs:__imp_AcquireSRWLockExclusive
0x1800061e6  cmp     qword ptr [rdi+18h], 0
0x1800061eb  mov     [rsp+28h+arg_0], rbx
0x1800061f0  jnz     short loc_1800061F6
0x1800061f2  mov     [rdi+18h], rsi
0x1800061f6  lea     rcx, [rsp+28h+arg_0]
0x1800061fb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180006200  lea     rcx, [rsp+28h+arg_8]; this
0x180006205  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000620a  cmp     qword ptr [rdi+18h], 0
0x18000620f  mov     rbx, [rsp+28h+arg_10]
0x180006214  mov     rsi, [rsp+28h+arg_18]
0x180006219  setnz   al
0x18000621c  add     rsp, 20h
0x180006220  pop     rdi
0x180006221  retn
```
