# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800064e4`
- end: `0x180006586`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000658c`

## callees

- `0x18000376c`
- `0x1800064e4`
- `0x180006690`
- `0x1800066c4`
- `0x1800066fc`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000651d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000651d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800064e4  push    rbx
0x1800064e6  push    rbp
0x1800064e7  push    rsi
0x1800064e8  push    rdi
0x1800064e9  sub     rsp, 38h
0x1800064ed  mov     rbp, r9
0x1800064f0  mov     ebx, r8d
0x1800064f3  mov     esi, edx
0x1800064f5  mov     rdi, rcx
0x1800064f8  cmp     r8d, 0FEh
0x1800064ff  jz      short loc_180006576
0x180006501  cmp     ebx, 0C8h
0x180006507  jb      short loc_18000651D
0x180006509  cmp     ebx, 100h
0x18000650f  jl      short loc_180006519
0x180006511  cmp     ebx, 200h
0x180006517  jb      short loc_18000651D
0x180006519  xor     al, al
0x18000651b  jmp     short loc_18000657D
0x18000651d  call    cs:__imp_AcquireSRWLockExclusive
0x180006523  mov     [rsp+58h+var_38], rdi
0x180006528  cmp     ebx, 7
0x18000652b  ja      short loc_180006537
0x18000652d  mov     eax, 0CCh
0x180006532  bt      eax, ebx
0x180006535  jb      short loc_180006557
0x180006537  lea     eax, [rbx-100h]
0x18000653d  cmp     eax, 7Fh
0x180006540  jbe     short loc_180006557
0x180006542  mov     r9d, ebp
0x180006545  lea     rcx, [rdi+48h]
0x180006549  mov     r8d, esi
0x18000654c  mov     edx, ebx
0x18000654e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006553  mov     bl, al
0x180006555  jmp     short loc_180006568
0x180006557  mov     r8d, esi
0x18000655a  mov     edx, ebx
0x18000655c  lea     rcx, [rdi+8]
0x180006560  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006565  mov     bl, [rdi+40h]
0x180006568  lea     rcx, [rsp+58h+var_38]
0x18000656d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180006572  mov     al, bl
0x180006574  jmp     short loc_18000657D
0x180006576  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000657b  mov     al, 1
0x18000657d  add     rsp, 38h
0x180006581  pop     rdi
0x180006582  pop     rsi
0x180006583  pop     rbp
0x180006584  pop     rbx
0x180006585  retn
```
