# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180014e14`
- end: `0x180014eb6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000d540`

## callees

- `0x18000d66c`
- `0x180014e14`
- `0x180014f10`
- `0x180014f44`
- `0x180014f7c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180014e4d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014e4d`

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
0x180014e14  push    rbx
0x180014e16  push    rbp
0x180014e17  push    rsi
0x180014e18  push    rdi
0x180014e19  sub     rsp, 38h
0x180014e1d  mov     rbp, r9
0x180014e20  mov     ebx, r8d
0x180014e23  mov     esi, edx
0x180014e25  mov     rdi, rcx
0x180014e28  cmp     r8d, 0FEh
0x180014e2f  jz      short loc_180014EA6
0x180014e31  cmp     ebx, 0C8h
0x180014e37  jb      short loc_180014E4D
0x180014e39  cmp     ebx, 100h
0x180014e3f  jl      short loc_180014E49
0x180014e41  cmp     ebx, 200h
0x180014e47  jb      short loc_180014E4D
0x180014e49  xor     al, al
0x180014e4b  jmp     short loc_180014EAD
0x180014e4d  call    cs:__imp_AcquireSRWLockExclusive
0x180014e53  mov     [rsp+58h+var_38], rdi
0x180014e58  cmp     ebx, 7
0x180014e5b  ja      short loc_180014E67
0x180014e5d  mov     eax, 0CCh
0x180014e62  bt      eax, ebx
0x180014e65  jb      short loc_180014E87
0x180014e67  lea     eax, [rbx-100h]
0x180014e6d  cmp     eax, 7Fh
0x180014e70  jbe     short loc_180014E87
0x180014e72  mov     r9d, ebp
0x180014e75  lea     rcx, [rdi+48h]
0x180014e79  mov     r8d, esi
0x180014e7c  mov     edx, ebx
0x180014e7e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180014e83  mov     bl, al
0x180014e85  jmp     short loc_180014E98
0x180014e87  mov     r8d, esi
0x180014e8a  lea     rcx, [rdi+8]
0x180014e8e  mov     edx, ebx
0x180014e90  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180014e95  mov     bl, [rdi+40h]
0x180014e98  lea     rcx, [rsp+58h+var_38]
0x180014e9d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014ea2  mov     al, bl
0x180014ea4  jmp     short loc_180014EAD
0x180014ea6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180014eab  mov     al, 1
0x180014ead  add     rsp, 38h
0x180014eb1  pop     rdi
0x180014eb2  pop     rsi
0x180014eb3  pop     rbp
0x180014eb4  pop     rbx
0x180014eb5  retn
```
