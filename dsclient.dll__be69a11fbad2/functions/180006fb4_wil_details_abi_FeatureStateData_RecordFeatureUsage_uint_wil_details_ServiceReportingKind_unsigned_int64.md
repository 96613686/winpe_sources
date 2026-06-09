# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006fb4`
- end: `0x180007056`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000705c`

## callees

- `0x1800048f8`
- `0x180006fb4`
- `0x180007170`
- `0x1800071a4`
- `0x1800071dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006fed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006fed`

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
0x180006fb4  push    rbx
0x180006fb6  push    rbp
0x180006fb7  push    rsi
0x180006fb8  push    rdi
0x180006fb9  sub     rsp, 38h
0x180006fbd  mov     rbp, r9
0x180006fc0  mov     ebx, r8d
0x180006fc3  mov     esi, edx
0x180006fc5  mov     rdi, rcx
0x180006fc8  cmp     r8d, 0FEh
0x180006fcf  jz      short loc_180007046
0x180006fd1  cmp     ebx, 0C8h
0x180006fd7  jb      short loc_180006FED
0x180006fd9  cmp     ebx, 100h
0x180006fdf  jl      short loc_180006FE9
0x180006fe1  cmp     ebx, 200h
0x180006fe7  jb      short loc_180006FED
0x180006fe9  xor     al, al
0x180006feb  jmp     short loc_18000704D
0x180006fed  call    cs:__imp_AcquireSRWLockExclusive
0x180006ff3  mov     [rsp+58h+var_38], rdi
0x180006ff8  cmp     ebx, 7
0x180006ffb  ja      short loc_180007007
0x180006ffd  mov     eax, 0CCh
0x180007002  bt      eax, ebx
0x180007005  jb      short loc_180007027
0x180007007  lea     eax, [rbx-100h]
0x18000700d  cmp     eax, 7Fh
0x180007010  jbe     short loc_180007027
0x180007012  mov     r9d, ebp
0x180007015  lea     rcx, [rdi+48h]
0x180007019  mov     r8d, esi
0x18000701c  mov     edx, ebx
0x18000701e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007023  mov     bl, al
0x180007025  jmp     short loc_180007038
0x180007027  mov     r8d, esi
0x18000702a  lea     rcx, [rdi+8]
0x18000702e  mov     edx, ebx
0x180007030  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007035  mov     bl, [rdi+40h]
0x180007038  lea     rcx, [rsp+58h+var_38]
0x18000703d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007042  mov     al, bl
0x180007044  jmp     short loc_18000704D
0x180007046  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000704b  mov     al, 1
0x18000704d  add     rsp, 38h
0x180007051  pop     rdi
0x180007052  pop     rsi
0x180007053  pop     rbp
0x180007054  pop     rbx
0x180007055  retn
```
