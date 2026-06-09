# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a894`
- end: `0x18000a936`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000a93c`

## callees

- `0x18000474c`
- `0x18000a894`
- `0x18000aa50`
- `0x18000aa84`
- `0x18000aabc`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a8cd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000a8cd`

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
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-38h] BYREF

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    v11 = (RTL_SRWLOCK *)a1;
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
0x18000a894  push    rbx
0x18000a896  push    rbp
0x18000a897  push    rsi
0x18000a898  push    rdi
0x18000a899  sub     rsp, 38h
0x18000a89d  mov     rbp, r9
0x18000a8a0  mov     ebx, r8d
0x18000a8a3  mov     esi, edx
0x18000a8a5  mov     rdi, rcx
0x18000a8a8  cmp     r8d, 0FEh
0x18000a8af  jz      short loc_18000A926
0x18000a8b1  cmp     ebx, 0C8h
0x18000a8b7  jb      short loc_18000A8CD
0x18000a8b9  cmp     ebx, 100h
0x18000a8bf  jl      short loc_18000A8C9
0x18000a8c1  cmp     ebx, 200h
0x18000a8c7  jb      short loc_18000A8CD
0x18000a8c9  xor     al, al
0x18000a8cb  jmp     short loc_18000A92D
0x18000a8cd  call    cs:__imp_AcquireSRWLockExclusive
0x18000a8d3  mov     [rsp+58h+var_38], rdi
0x18000a8d8  cmp     ebx, 7
0x18000a8db  ja      short loc_18000A8E7
0x18000a8dd  mov     eax, 0CCh
0x18000a8e2  bt      eax, ebx
0x18000a8e5  jb      short loc_18000A907
0x18000a8e7  lea     eax, [rbx-100h]
0x18000a8ed  cmp     eax, 7Fh
0x18000a8f0  jbe     short loc_18000A907
0x18000a8f2  mov     r9d, ebp
0x18000a8f5  lea     rcx, [rdi+48h]
0x18000a8f9  mov     r8d, esi
0x18000a8fc  mov     edx, ebx
0x18000a8fe  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a903  mov     bl, al
0x18000a905  jmp     short loc_18000A918
0x18000a907  mov     r8d, esi
0x18000a90a  lea     rcx, [rdi+8]
0x18000a90e  mov     edx, ebx
0x18000a910  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a915  mov     bl, [rdi+40h]
0x18000a918  lea     rcx, [rsp+58h+var_38]
0x18000a91d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a922  mov     al, bl
0x18000a924  jmp     short loc_18000A92D
0x18000a926  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a92b  mov     al, 1
0x18000a92d  add     rsp, 38h
0x18000a931  pop     rdi
0x18000a932  pop     rsi
0x18000a933  pop     rbp
0x18000a934  pop     rbx
0x18000a935  retn
```
