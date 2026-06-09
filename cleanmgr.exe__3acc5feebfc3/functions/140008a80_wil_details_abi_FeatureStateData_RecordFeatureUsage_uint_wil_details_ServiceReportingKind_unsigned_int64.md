# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140008a80`
- end: `0x140008b22`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x140008b28`

## callees

- `0x140006e08`
- `0x140008a80`
- `0x140008c00`
- `0x140008c34`
- `0x140008c6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008ab9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008ab9`

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
0x140008a80  push    rbx
0x140008a82  push    rbp
0x140008a83  push    rsi
0x140008a84  push    rdi
0x140008a85  sub     rsp, 38h
0x140008a89  mov     rbp, r9
0x140008a8c  mov     ebx, r8d
0x140008a8f  mov     esi, edx
0x140008a91  mov     rdi, rcx
0x140008a94  cmp     r8d, 0FEh
0x140008a9b  jz      short loc_140008B12
0x140008a9d  cmp     ebx, 0C8h
0x140008aa3  jb      short loc_140008AB9
0x140008aa5  cmp     ebx, 100h
0x140008aab  jl      short loc_140008AB5
0x140008aad  cmp     ebx, 200h
0x140008ab3  jb      short loc_140008AB9
0x140008ab5  xor     al, al
0x140008ab7  jmp     short loc_140008B19
0x140008ab9  call    cs:__imp_AcquireSRWLockExclusive
0x140008abf  mov     [rsp+58h+var_38], rdi
0x140008ac4  cmp     ebx, 7
0x140008ac7  ja      short loc_140008AD3
0x140008ac9  mov     eax, 0CCh
0x140008ace  bt      eax, ebx
0x140008ad1  jb      short loc_140008AF3
0x140008ad3  lea     eax, [rbx-100h]
0x140008ad9  cmp     eax, 7Fh
0x140008adc  jbe     short loc_140008AF3
0x140008ade  mov     r9d, ebp
0x140008ae1  lea     rcx, [rdi+48h]
0x140008ae5  mov     r8d, esi
0x140008ae8  mov     edx, ebx
0x140008aea  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140008aef  mov     bl, al
0x140008af1  jmp     short loc_140008B04
0x140008af3  mov     r8d, esi
0x140008af6  lea     rcx, [rdi+8]
0x140008afa  mov     edx, ebx
0x140008afc  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140008b01  mov     bl, [rdi+40h]
0x140008b04  lea     rcx, [rsp+58h+var_38]
0x140008b09  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140008b0e  mov     al, bl
0x140008b10  jmp     short loc_140008B19
0x140008b12  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140008b17  mov     al, 1
0x140008b19  add     rsp, 38h
0x140008b1d  pop     rdi
0x140008b1e  pop     rsi
0x140008b1f  pop     rbp
0x140008b20  pop     rbx
0x140008b21  retn
```
