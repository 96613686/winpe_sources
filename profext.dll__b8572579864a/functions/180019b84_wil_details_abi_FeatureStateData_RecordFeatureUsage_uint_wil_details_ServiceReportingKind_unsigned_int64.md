# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180019b84`
- end: `0x180019c2d`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180019c34`

## callees

- `0x180013750`
- `0x180019b84`
- `0x180019d20`
- `0x180019d58`
- `0x180019d90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019bbd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019bbd`

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
0x180019b84  push    rbx
0x180019b86  push    rbp
0x180019b87  push    rsi
0x180019b88  push    rdi
0x180019b89  sub     rsp, 38h
0x180019b8d  mov     rbp, r9
0x180019b90  mov     ebx, r8d
0x180019b93  mov     esi, edx
0x180019b95  mov     rdi, rcx
0x180019b98  cmp     r8d, 0FEh
0x180019b9f  jz      short loc_180019C1C
0x180019ba1  cmp     ebx, 0C8h
0x180019ba7  jb      short loc_180019BBD
0x180019ba9  cmp     ebx, 100h
0x180019baf  jl      short loc_180019BB9
0x180019bb1  cmp     ebx, 200h
0x180019bb7  jb      short loc_180019BBD
0x180019bb9  xor     al, al
0x180019bbb  jmp     short loc_180019C23
0x180019bbd  call    cs:__imp_AcquireSRWLockExclusive
0x180019bc4  nop     dword ptr [rax+rax+00h]
0x180019bc9  mov     [rsp+58h+var_38], rdi
0x180019bce  cmp     ebx, 7
0x180019bd1  ja      short loc_180019BDD
0x180019bd3  mov     eax, 0CCh
0x180019bd8  bt      eax, ebx
0x180019bdb  jb      short loc_180019BFD
0x180019bdd  lea     eax, [rbx-100h]
0x180019be3  cmp     eax, 7Fh
0x180019be6  jbe     short loc_180019BFD
0x180019be8  mov     r9d, ebp
0x180019beb  lea     rcx, [rdi+48h]
0x180019bef  mov     r8d, esi
0x180019bf2  mov     edx, ebx
0x180019bf4  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180019bf9  mov     bl, al
0x180019bfb  jmp     short loc_180019C0E
0x180019bfd  mov     r8d, esi
0x180019c00  lea     rcx, [rdi+8]
0x180019c04  mov     edx, ebx
0x180019c06  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180019c0b  mov     bl, [rdi+40h]
0x180019c0e  lea     rcx, [rsp+58h+var_38]
0x180019c13  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180019c18  mov     al, bl
0x180019c1a  jmp     short loc_180019C23
0x180019c1c  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180019c21  mov     al, 1
0x180019c23  add     rsp, 38h
0x180019c27  pop     rdi
0x180019c28  pop     rsi
0x180019c29  pop     rbp
0x180019c2a  pop     rbx
0x180019c2b  retn
```
