# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800084c4`
- end: `0x18000856d`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000321c`

## callees

- `0x18000336c`
- `0x1800084c4`
- `0x1800085ac`
- `0x180008600`
- `0x180008658`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008500`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008500`

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
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-28h] BYREF

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
0x1800084c4  mov     [rsp+arg_18], rbx
0x1800084c9  push    rbp
0x1800084ca  push    rsi
0x1800084cb  push    rdi
0x1800084cc  sub     rsp, 30h
0x1800084d0  mov     rbp, r9
0x1800084d3  mov     ebx, r8d
0x1800084d6  mov     esi, edx
0x1800084d8  mov     rdi, rcx
0x1800084db  cmp     r8d, 0FEh
0x1800084e2  jz      short loc_180008559
0x1800084e4  cmp     ebx, 0C8h
0x1800084ea  jb      short loc_180008500
0x1800084ec  cmp     ebx, 100h
0x1800084f2  jl      short loc_1800084FC
0x1800084f4  cmp     ebx, 200h
0x1800084fa  jb      short loc_180008500
0x1800084fc  xor     al, al
0x1800084fe  jmp     short loc_180008560
0x180008500  call    cs:__imp_AcquireSRWLockExclusive
0x180008506  mov     [rsp+48h+var_28], rdi
0x18000850b  cmp     ebx, 7
0x18000850e  ja      short loc_18000851A
0x180008510  mov     eax, 0CCh
0x180008515  bt      eax, ebx
0x180008518  jb      short loc_18000853A
0x18000851a  lea     eax, [rbx-100h]
0x180008520  cmp     eax, 7Fh
0x180008523  jbe     short loc_18000853A
0x180008525  mov     r9d, ebp
0x180008528  lea     rcx, [rdi+48h]
0x18000852c  mov     r8d, esi
0x18000852f  mov     edx, ebx
0x180008531  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180008536  mov     bl, al
0x180008538  jmp     short loc_18000854B
0x18000853a  mov     r8d, esi
0x18000853d  lea     rcx, [rdi+8]
0x180008541  mov     edx, ebx
0x180008543  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180008548  mov     bl, [rdi+40h]
0x18000854b  lea     rcx, [rsp+48h+var_28]
0x180008550  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008555  mov     al, bl
0x180008557  jmp     short loc_180008560
0x180008559  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000855e  mov     al, 1
0x180008560  mov     rbx, [rsp+48h+arg_18]
0x180008565  add     rsp, 30h
0x180008569  pop     rdi
0x18000856a  pop     rsi
0x18000856b  pop     rbp
0x18000856c  retn
```
