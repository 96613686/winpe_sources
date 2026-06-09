# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180014bc4`
- end: `0x180014c66`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000ab80`

## callees

- `0x18000acac`
- `0x180014bc4`
- `0x180014cc0`
- `0x180014cf4`
- `0x180014d2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014bfd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014bfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180014bc4  push    rbx
0x180014bc6  push    rbp
0x180014bc7  push    rsi
0x180014bc8  push    rdi
0x180014bc9  sub     rsp, 38h
0x180014bcd  mov     rbp, r9
0x180014bd0  mov     ebx, r8d
0x180014bd3  mov     esi, edx
0x180014bd5  mov     rdi, rcx
0x180014bd8  cmp     r8d, 0FEh
0x180014bdf  jz      short loc_180014C56
0x180014be1  cmp     ebx, 0C8h
0x180014be7  jb      short loc_180014BFD
0x180014be9  cmp     ebx, 100h
0x180014bef  jl      short loc_180014BF9
0x180014bf1  cmp     ebx, 200h
0x180014bf7  jb      short loc_180014BFD
0x180014bf9  xor     al, al
0x180014bfb  jmp     short loc_180014C5D
0x180014bfd  call    cs:__imp_AcquireSRWLockExclusive
0x180014c03  mov     [rsp+58h+var_38], rdi
0x180014c08  cmp     ebx, 7
0x180014c0b  ja      short loc_180014C17
0x180014c0d  mov     eax, 0CCh
0x180014c12  bt      eax, ebx
0x180014c15  jb      short loc_180014C37
0x180014c17  lea     eax, [rbx-100h]
0x180014c1d  cmp     eax, 7Fh
0x180014c20  jbe     short loc_180014C37
0x180014c22  mov     r9d, ebp
0x180014c25  lea     rcx, [rdi+48h]
0x180014c29  mov     r8d, esi
0x180014c2c  mov     edx, ebx
0x180014c2e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180014c33  mov     bl, al
0x180014c35  jmp     short loc_180014C48
0x180014c37  mov     r8d, esi
0x180014c3a  mov     edx, ebx
0x180014c3c  lea     rcx, [rdi+8]
0x180014c40  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180014c45  mov     bl, [rdi+40h]
0x180014c48  lea     rcx, [rsp+58h+var_38]
0x180014c4d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014c52  mov     al, bl
0x180014c54  jmp     short loc_180014C5D
0x180014c56  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180014c5b  mov     al, 1
0x180014c5d  add     rsp, 38h
0x180014c61  pop     rdi
0x180014c62  pop     rsi
0x180014c63  pop     rbp
0x180014c64  pop     rbx
0x180014c65  retn
```
