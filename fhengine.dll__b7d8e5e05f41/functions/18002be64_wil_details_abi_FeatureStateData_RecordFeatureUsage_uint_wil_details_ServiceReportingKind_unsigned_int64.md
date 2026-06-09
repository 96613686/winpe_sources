# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18002be64`
- end: `0x18002bf06`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18002bf0c`

## callees

- `0x180027a6c`
- `0x18002be64`
- `0x18002c020`
- `0x18002c054`
- `0x18002c08c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18002be9d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002be9d`

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
0x18002be64  push    rbx
0x18002be66  push    rbp
0x18002be67  push    rsi
0x18002be68  push    rdi
0x18002be69  sub     rsp, 38h
0x18002be6d  mov     rbp, r9
0x18002be70  mov     ebx, r8d
0x18002be73  mov     esi, edx
0x18002be75  mov     rdi, rcx
0x18002be78  cmp     r8d, 0FEh
0x18002be7f  jz      short loc_18002BEF6
0x18002be81  cmp     ebx, 0C8h
0x18002be87  jb      short loc_18002BE9D
0x18002be89  cmp     ebx, 100h
0x18002be8f  jl      short loc_18002BE99
0x18002be91  cmp     ebx, 200h
0x18002be97  jb      short loc_18002BE9D
0x18002be99  xor     al, al
0x18002be9b  jmp     short loc_18002BEFD
0x18002be9d  call    cs:__imp_AcquireSRWLockExclusive
0x18002bea3  mov     [rsp+58h+var_38], rdi
0x18002bea8  cmp     ebx, 7
0x18002beab  ja      short loc_18002BEB7
0x18002bead  mov     eax, 0CCh
0x18002beb2  bt      eax, ebx
0x18002beb5  jb      short loc_18002BED7
0x18002beb7  lea     eax, [rbx-100h]
0x18002bebd  cmp     eax, 7Fh
0x18002bec0  jbe     short loc_18002BED7
0x18002bec2  mov     r9d, ebp
0x18002bec5  lea     rcx, [rdi+48h]
0x18002bec9  mov     r8d, esi
0x18002becc  mov     edx, ebx
0x18002bece  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002bed3  mov     bl, al
0x18002bed5  jmp     short loc_18002BEE8
0x18002bed7  mov     r8d, esi
0x18002beda  lea     rcx, [rdi+8]
0x18002bede  mov     edx, ebx
0x18002bee0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002bee5  mov     bl, [rdi+40h]
0x18002bee8  lea     rcx, [rsp+58h+var_38]
0x18002beed  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002bef2  mov     al, bl
0x18002bef4  jmp     short loc_18002BEFD
0x18002bef6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002befb  mov     al, 1
0x18002befd  add     rsp, 38h
0x18002bf01  pop     rdi
0x18002bf02  pop     rsi
0x18002bf03  pop     rbp
0x18002bf04  pop     rbx
0x18002bf05  retn
```
