# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140008db4`
- end: `0x140008e8e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x14000aaa0`

## callees

- `0x14000380c`
- `0x1400050dc`
- `0x140005f94`
- `0x1400089e8`
- `0x140008db4`
- `0x140008e94`
- `0x140008fac`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140008e0f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140008e55`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140008e0f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140008e55`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  _BYTE *v8; // rsi
  char v9; // bl
  wil *v10; // rcx
  _BYTE *v11; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
  {
    v8 = (_BYTE *)*((_QWORD *)a1 + 3);
    if ( a3 == 254 )
    {
      wil::details_abi::FeatureStateData::RecordUsage(*((wil::details_abi::FeatureStateData **)a1 + 3));
LABEL_10:
      if ( !wil::ProcessShutdownInProgress(v10) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
        v11 = a1 + 32;
        wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>((_QWORD *)a1 + 6, a1 + 65, a1);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      }
      return;
    }
    if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
    {
      AcquireSRWLockExclusive(*((PSRWLOCK *)a1 + 3));
      v11 = v8;
      v9 = wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(v8, a2, a3, a4);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      if ( v9 )
        goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x140008db4  mov     [rsp+arg_8], rbx
0x140008db9  mov     [rsp+arg_10], rbp
0x140008dbe  push    rsi
0x140008dbf  push    rdi
0x140008dc0  push    r14
0x140008dc2  sub     rsp, 20h
0x140008dc6  mov     rbp, r9
0x140008dc9  mov     ebx, r8d
0x140008dcc  mov     r14d, edx
0x140008dcf  mov     rdi, rcx
0x140008dd2  cmp     byte ptr [rcx], 0
0x140008dd5  jz      loc_140008E7B
0x140008ddb  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140008de0  test    al, al
0x140008de2  jz      loc_140008E7B
0x140008de8  mov     rsi, [rdi+18h]
0x140008dec  cmp     ebx, 0FEh
0x140008df2  jz      short loc_140008E3D
0x140008df4  cmp     ebx, 0C8h
0x140008dfa  jb      short loc_140008E0C
0x140008dfc  cmp     ebx, 100h
0x140008e02  jl      short loc_140008E7B
0x140008e04  cmp     ebx, 200h
0x140008e0a  jnb     short loc_140008E7B
0x140008e0c  mov     rcx, rsi; SRWLock
0x140008e0f  call    cs:__imp_AcquireSRWLockExclusive
0x140008e15  mov     [rsp+38h+arg_0], rsi
0x140008e1a  mov     r9, rbp
0x140008e1d  mov     r8d, ebx
0x140008e20  mov     edx, r14d
0x140008e23  mov     rcx, rsi
0x140008e26  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140008e2b  mov     bl, al
0x140008e2d  lea     rcx, [rsp+38h+arg_0]
0x140008e32  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140008e37  test    bl, bl
0x140008e39  jz      short loc_140008E7B
0x140008e3b  jmp     short loc_140008E45
0x140008e3d  mov     rcx, rsi; this
0x140008e40  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140008e45  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140008e4a  test    al, al
0x140008e4c  jnz     short loc_140008E7B
0x140008e4e  lea     rbx, [rdi+20h]
0x140008e52  mov     rcx, rbx; SRWLock
0x140008e55  call    cs:__imp_AcquireSRWLockExclusive
0x140008e5b  mov     [rsp+38h+arg_0], rbx
0x140008e60  lea     rdx, [rdi+41h]
0x140008e64  lea     rcx, [rdi+30h]
0x140008e68  mov     r8, rdi
0x140008e6b  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x140008e70  lea     rcx, [rsp+38h+arg_0]
0x140008e75  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140008e7a  nop
0x140008e7b  mov     rbx, [rsp+38h+arg_8]
0x140008e80  mov     rbp, [rsp+38h+arg_10]
0x140008e85  add     rsp, 20h
0x140008e89  pop     r14
0x140008e8b  pop     rdi
0x140008e8c  pop     rsi
0x140008e8d  retn
```
