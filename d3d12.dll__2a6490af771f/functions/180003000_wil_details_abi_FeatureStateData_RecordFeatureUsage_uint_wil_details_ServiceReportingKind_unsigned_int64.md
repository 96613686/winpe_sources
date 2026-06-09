# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180003000`
- end: `0x1800030a2`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180002d2c`

## callees

- `0x180003000`
- `0x1800030a8`
- `0x18000387c`
- `0x18000a1e4`
- `0x18000d780`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003049`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003049`

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
  else if ( a3 >= 0xC8 && (a3 >= 0x200 || (int)a3 < 256) )
  {
    return 0;
  }
  else
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
}

```

## disassembly

```asm
0x180003000  push    rbx
0x180003002  push    rbp
0x180003003  push    rsi
0x180003004  push    rdi
0x180003005  sub     rsp, 38h
0x180003009  mov     rbp, r9
0x18000300c  mov     ebx, r8d
0x18000300f  mov     esi, edx
0x180003011  mov     rdi, rcx
0x180003014  cmp     r8d, 0FEh
0x18000301b  jnz     short loc_18000302D
0x18000301d  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180003022  mov     al, 1
0x180003024  add     rsp, 38h
0x180003028  pop     rdi
0x180003029  pop     rsi
0x18000302a  pop     rbp
0x18000302b  pop     rbx
0x18000302c  retn
0x18000302d  cmp     ebx, 0C8h
0x180003033  jb      short loc_180003049
0x180003035  cmp     ebx, 200h
0x18000303b  jb      short loc_180003041
0x18000303d  xor     al, al
0x18000303f  jmp     short loc_180003024
0x180003041  cmp     ebx, 100h
0x180003047  jl      short loc_18000303D
0x180003049  call    cs:__imp_AcquireSRWLockExclusive
0x18000304f  mov     [rsp+58h+var_38], rdi
0x180003054  cmp     ebx, 7
0x180003057  ja      short loc_180003063
0x180003059  mov     eax, 0CCh
0x18000305e  bt      eax, ebx
0x180003061  jb      short loc_180003083
0x180003063  lea     eax, [rbx-100h]
0x180003069  cmp     eax, 7Fh
0x18000306c  jbe     short loc_180003083
0x18000306e  mov     r9d, ebp
0x180003071  lea     rcx, [rdi+48h]
0x180003075  mov     r8d, esi
0x180003078  mov     edx, ebx
0x18000307a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000307f  mov     bl, al
0x180003081  jmp     short loc_180003094
0x180003083  mov     r8d, esi
0x180003086  lea     rcx, [rdi+8]
0x18000308a  mov     edx, ebx
0x18000308c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180003091  mov     bl, [rdi+40h]
0x180003094  lea     rcx, [rsp+58h+var_38]
0x180003099  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000309e  mov     al, bl
0x1800030a0  jmp     short loc_180003024
```
