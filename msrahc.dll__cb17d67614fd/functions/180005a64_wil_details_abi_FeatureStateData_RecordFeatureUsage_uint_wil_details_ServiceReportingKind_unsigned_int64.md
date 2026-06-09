# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180005a64`
- end: `0x180005b06`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180005b0c`

## callees

- `0x180003484`
- `0x180005a64`
- `0x180005c0c`
- `0x180005c40`
- `0x180005c78`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180005a9d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005a9d`

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
0x180005a64  push    rbx
0x180005a66  push    rbp
0x180005a67  push    rsi
0x180005a68  push    rdi
0x180005a69  sub     rsp, 38h
0x180005a6d  mov     rbp, r9
0x180005a70  mov     ebx, r8d
0x180005a73  mov     esi, edx
0x180005a75  mov     rdi, rcx
0x180005a78  cmp     r8d, 0FEh
0x180005a7f  jz      short loc_180005AF6
0x180005a81  cmp     ebx, 0C8h
0x180005a87  jb      short loc_180005A9D
0x180005a89  cmp     ebx, 100h
0x180005a8f  jl      short loc_180005A99
0x180005a91  cmp     ebx, 200h
0x180005a97  jb      short loc_180005A9D
0x180005a99  xor     al, al
0x180005a9b  jmp     short loc_180005AFD
0x180005a9d  call    cs:__imp_AcquireSRWLockExclusive
0x180005aa3  mov     [rsp+58h+var_38], rdi
0x180005aa8  cmp     ebx, 7
0x180005aab  ja      short loc_180005AB7
0x180005aad  mov     eax, 0CCh
0x180005ab2  bt      eax, ebx
0x180005ab5  jb      short loc_180005AD7
0x180005ab7  lea     eax, [rbx-100h]
0x180005abd  cmp     eax, 7Fh
0x180005ac0  jbe     short loc_180005AD7
0x180005ac2  mov     r9d, ebp
0x180005ac5  lea     rcx, [rdi+48h]
0x180005ac9  mov     r8d, esi
0x180005acc  mov     edx, ebx
0x180005ace  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005ad3  mov     bl, al
0x180005ad5  jmp     short loc_180005AE8
0x180005ad7  mov     r8d, esi
0x180005ada  lea     rcx, [rdi+8]
0x180005ade  mov     edx, ebx
0x180005ae0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005ae5  mov     bl, [rdi+40h]
0x180005ae8  lea     rcx, [rsp+58h+var_38]
0x180005aed  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180005af2  mov     al, bl
0x180005af4  jmp     short loc_180005AFD
0x180005af6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180005afb  mov     al, 1
0x180005afd  add     rsp, 38h
0x180005b01  pop     rdi
0x180005b02  pop     rsi
0x180005b03  pop     rbp
0x180005b04  pop     rbx
0x180005b05  retn
```
