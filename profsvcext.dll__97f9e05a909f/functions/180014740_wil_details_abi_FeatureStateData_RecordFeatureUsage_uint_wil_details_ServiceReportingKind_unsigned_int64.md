# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180014740`
- end: `0x1800147e2`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800147e8`

## callees

- `0x180011514`
- `0x180014740`
- `0x1800148c0`
- `0x1800148f4`
- `0x18001492c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014779`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014779`

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
0x180014740  push    rbx
0x180014742  push    rbp
0x180014743  push    rsi
0x180014744  push    rdi
0x180014745  sub     rsp, 38h
0x180014749  mov     rbp, r9
0x18001474c  mov     ebx, r8d
0x18001474f  mov     esi, edx
0x180014751  mov     rdi, rcx
0x180014754  cmp     r8d, 0FEh
0x18001475b  jz      short loc_1800147D2
0x18001475d  cmp     ebx, 0C8h
0x180014763  jb      short loc_180014779
0x180014765  cmp     ebx, 100h
0x18001476b  jl      short loc_180014775
0x18001476d  cmp     ebx, 200h
0x180014773  jb      short loc_180014779
0x180014775  xor     al, al
0x180014777  jmp     short loc_1800147D9
0x180014779  call    cs:__imp_AcquireSRWLockExclusive
0x18001477f  mov     [rsp+58h+var_38], rdi
0x180014784  cmp     ebx, 7
0x180014787  ja      short loc_180014793
0x180014789  mov     eax, 0CCh
0x18001478e  bt      eax, ebx
0x180014791  jb      short loc_1800147B3
0x180014793  lea     eax, [rbx-100h]
0x180014799  cmp     eax, 7Fh
0x18001479c  jbe     short loc_1800147B3
0x18001479e  mov     r9d, ebp
0x1800147a1  lea     rcx, [rdi+48h]
0x1800147a5  mov     r8d, esi
0x1800147a8  mov     edx, ebx
0x1800147aa  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800147af  mov     bl, al
0x1800147b1  jmp     short loc_1800147C4
0x1800147b3  mov     r8d, esi
0x1800147b6  lea     rcx, [rdi+8]
0x1800147ba  mov     edx, ebx
0x1800147bc  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800147c1  mov     bl, [rdi+40h]
0x1800147c4  lea     rcx, [rsp+58h+var_38]
0x1800147c9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800147ce  mov     al, bl
0x1800147d0  jmp     short loc_1800147D9
0x1800147d2  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800147d7  mov     al, 1
0x1800147d9  add     rsp, 38h
0x1800147dd  pop     rdi
0x1800147de  pop     rsi
0x1800147df  pop     rbp
0x1800147e0  pop     rbx
0x1800147e1  retn
```
