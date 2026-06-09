# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a45c`
- end: `0x18000a4fe`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000a504`

## callees

- `0x180007984`
- `0x18000a45c`
- `0x18000a700`
- `0x18000a734`
- `0x18000a76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a495`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a495`

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
0x18000a45c  push    rbx
0x18000a45e  push    rbp
0x18000a45f  push    rsi
0x18000a460  push    rdi
0x18000a461  sub     rsp, 38h
0x18000a465  mov     rbp, r9
0x18000a468  mov     ebx, r8d
0x18000a46b  mov     esi, edx
0x18000a46d  mov     rdi, rcx
0x18000a470  cmp     r8d, 0FEh
0x18000a477  jz      short loc_18000A4EE
0x18000a479  cmp     ebx, 0C8h
0x18000a47f  jb      short loc_18000A495
0x18000a481  cmp     ebx, 100h
0x18000a487  jl      short loc_18000A491
0x18000a489  cmp     ebx, 200h
0x18000a48f  jb      short loc_18000A495
0x18000a491  xor     al, al
0x18000a493  jmp     short loc_18000A4F5
0x18000a495  call    cs:__imp_AcquireSRWLockExclusive
0x18000a49b  mov     [rsp+58h+var_38], rdi
0x18000a4a0  cmp     ebx, 7
0x18000a4a3  ja      short loc_18000A4AF
0x18000a4a5  mov     eax, 0CCh
0x18000a4aa  bt      eax, ebx
0x18000a4ad  jb      short loc_18000A4CF
0x18000a4af  lea     eax, [rbx-100h]
0x18000a4b5  cmp     eax, 7Fh
0x18000a4b8  jbe     short loc_18000A4CF
0x18000a4ba  mov     r9d, ebp
0x18000a4bd  lea     rcx, [rdi+48h]
0x18000a4c1  mov     r8d, esi
0x18000a4c4  mov     edx, ebx
0x18000a4c6  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a4cb  mov     bl, al
0x18000a4cd  jmp     short loc_18000A4E0
0x18000a4cf  mov     r8d, esi
0x18000a4d2  lea     rcx, [rdi+8]
0x18000a4d6  mov     edx, ebx
0x18000a4d8  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a4dd  mov     bl, [rdi+40h]
0x18000a4e0  lea     rcx, [rsp+58h+var_38]
0x18000a4e5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a4ea  mov     al, bl
0x18000a4ec  jmp     short loc_18000A4F5
0x18000a4ee  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a4f3  mov     al, 1
0x18000a4f5  add     rsp, 38h
0x18000a4f9  pop     rdi
0x18000a4fa  pop     rsi
0x18000a4fb  pop     rbp
0x18000a4fc  pop     rbx
0x18000a4fd  retn
```
