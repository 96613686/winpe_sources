# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180011454`
- end: `0x1800114f6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800114fc`

## callees

- `0x1800070ac`
- `0x180011454`
- `0x1800115c4`
- `0x1800115f8`
- `0x180011630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001148d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001148d`

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
0x180011454  push    rbx
0x180011456  push    rbp
0x180011457  push    rsi
0x180011458  push    rdi
0x180011459  sub     rsp, 38h
0x18001145d  mov     rbp, r9
0x180011460  mov     ebx, r8d
0x180011463  mov     esi, edx
0x180011465  mov     rdi, rcx
0x180011468  cmp     r8d, 0FEh
0x18001146f  jz      short loc_1800114E6
0x180011471  cmp     ebx, 0C8h
0x180011477  jb      short loc_18001148D
0x180011479  cmp     ebx, 100h
0x18001147f  jl      short loc_180011489
0x180011481  cmp     ebx, 200h
0x180011487  jb      short loc_18001148D
0x180011489  xor     al, al
0x18001148b  jmp     short loc_1800114ED
0x18001148d  call    cs:__imp_AcquireSRWLockExclusive
0x180011493  mov     [rsp+58h+var_38], rdi
0x180011498  cmp     ebx, 7
0x18001149b  ja      short loc_1800114A7
0x18001149d  mov     eax, 0CCh
0x1800114a2  bt      eax, ebx
0x1800114a5  jb      short loc_1800114C7
0x1800114a7  lea     eax, [rbx-100h]
0x1800114ad  cmp     eax, 7Fh
0x1800114b0  jbe     short loc_1800114C7
0x1800114b2  mov     r9d, ebp
0x1800114b5  lea     rcx, [rdi+48h]
0x1800114b9  mov     r8d, esi
0x1800114bc  mov     edx, ebx
0x1800114be  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800114c3  mov     bl, al
0x1800114c5  jmp     short loc_1800114D8
0x1800114c7  mov     r8d, esi
0x1800114ca  lea     rcx, [rdi+8]
0x1800114ce  mov     edx, ebx
0x1800114d0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800114d5  mov     bl, [rdi+40h]
0x1800114d8  lea     rcx, [rsp+58h+var_38]
0x1800114dd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800114e2  mov     al, bl
0x1800114e4  jmp     short loc_1800114ED
0x1800114e6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800114eb  mov     al, 1
0x1800114ed  add     rsp, 38h
0x1800114f1  pop     rdi
0x1800114f2  pop     rsi
0x1800114f3  pop     rbp
0x1800114f4  pop     rbx
0x1800114f5  retn
```
