# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180014bc0`
- end: `0x180014c62`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000eff0`

## callees

- `0x18000f11c`
- `0x180014bc0`
- `0x180014c80`
- `0x180014cb4`
- `0x180014cec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014bf9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014bf9`

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
0x180014bc0  push    rbx
0x180014bc2  push    rbp
0x180014bc3  push    rsi
0x180014bc4  push    rdi
0x180014bc5  sub     rsp, 38h
0x180014bc9  mov     rbp, r9
0x180014bcc  mov     ebx, r8d
0x180014bcf  mov     esi, edx
0x180014bd1  mov     rdi, rcx
0x180014bd4  cmp     r8d, 0FEh
0x180014bdb  jz      short loc_180014C52
0x180014bdd  cmp     ebx, 0C8h
0x180014be3  jb      short loc_180014BF9
0x180014be5  cmp     ebx, 100h
0x180014beb  jl      short loc_180014BF5
0x180014bed  cmp     ebx, 200h
0x180014bf3  jb      short loc_180014BF9
0x180014bf5  xor     al, al
0x180014bf7  jmp     short loc_180014C59
0x180014bf9  call    cs:__imp_AcquireSRWLockExclusive
0x180014bff  mov     [rsp+58h+var_38], rdi
0x180014c04  cmp     ebx, 7
0x180014c07  ja      short loc_180014C13
0x180014c09  mov     eax, 0CCh
0x180014c0e  bt      eax, ebx
0x180014c11  jb      short loc_180014C33
0x180014c13  lea     eax, [rbx-100h]
0x180014c19  cmp     eax, 7Fh
0x180014c1c  jbe     short loc_180014C33
0x180014c1e  mov     r9d, ebp
0x180014c21  lea     rcx, [rdi+48h]
0x180014c25  mov     r8d, esi
0x180014c28  mov     edx, ebx
0x180014c2a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180014c2f  mov     bl, al
0x180014c31  jmp     short loc_180014C44
0x180014c33  mov     r8d, esi
0x180014c36  lea     rcx, [rdi+8]
0x180014c3a  mov     edx, ebx
0x180014c3c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180014c41  mov     bl, [rdi+40h]
0x180014c44  lea     rcx, [rsp+58h+var_38]
0x180014c49  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014c4e  mov     al, bl
0x180014c50  jmp     short loc_180014C59
0x180014c52  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180014c57  mov     al, 1
0x180014c59  add     rsp, 38h
0x180014c5d  pop     rdi
0x180014c5e  pop     rsi
0x180014c5f  pop     rbp
0x180014c60  pop     rbx
0x180014c61  retn
```
