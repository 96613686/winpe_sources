# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800295bc`
- end: `0x18002965e`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001f688`

## callees

- `0x18001f7b4`
- `0x1800295bc`
- `0x180029680`
- `0x1800296b4`
- `0x1800296ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800295f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800295f5`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        wil::details_abi::FeatureStateData *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  int v9; // eax
  char v10; // bl
  wil::details_abi::FeatureStateData *v11; // [rsp+20h] [rbp-38h] BYREF

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    v11 = a1;
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        (char *)a1 + 8,
        a3,
        a2);
      v10 = *((_BYTE *)a1 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              (char *)a1 + 72,
              a3,
              a2,
              a4,
              v11);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
    return v10;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x1800295bc  push    rbx
0x1800295be  push    rbp
0x1800295bf  push    rsi
0x1800295c0  push    rdi
0x1800295c1  sub     rsp, 38h
0x1800295c5  mov     rbp, r9
0x1800295c8  mov     ebx, r8d
0x1800295cb  mov     esi, edx
0x1800295cd  mov     rdi, rcx
0x1800295d0  cmp     r8d, 0FEh
0x1800295d7  jz      short loc_18002964E
0x1800295d9  cmp     ebx, 0C8h
0x1800295df  jb      short loc_1800295F5
0x1800295e1  cmp     ebx, 100h
0x1800295e7  jl      short loc_1800295F1
0x1800295e9  cmp     ebx, 200h
0x1800295ef  jb      short loc_1800295F5
0x1800295f1  xor     al, al
0x1800295f3  jmp     short loc_180029655
0x1800295f5  call    cs:__imp_AcquireSRWLockExclusive
0x1800295fb  mov     [rsp+58h+var_38], rdi
0x180029600  cmp     ebx, 7
0x180029603  ja      short loc_18002960F
0x180029605  mov     eax, 0CCh
0x18002960a  bt      eax, ebx
0x18002960d  jb      short loc_18002962F
0x18002960f  lea     eax, [rbx-100h]
0x180029615  cmp     eax, 7Fh
0x180029618  jbe     short loc_18002962F
0x18002961a  mov     r9d, ebp
0x18002961d  lea     rcx, [rdi+48h]
0x180029621  mov     r8d, esi
0x180029624  mov     edx, ebx
0x180029626  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002962b  mov     bl, al
0x18002962d  jmp     short loc_180029640
0x18002962f  mov     r8d, esi
0x180029632  lea     rcx, [rdi+8]
0x180029636  mov     edx, ebx
0x180029638  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002963d  mov     bl, [rdi+40h]
0x180029640  lea     rcx, [rsp+58h+var_38]
0x180029645  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002964a  mov     al, bl
0x18002964c  jmp     short loc_180029655
0x18002964e  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180029653  mov     al, 1
0x180029655  add     rsp, 38h
0x180029659  pop     rdi
0x18002965a  pop     rsi
0x18002965b  pop     rbp
0x18002965c  pop     rbx
0x18002965d  retn
```
