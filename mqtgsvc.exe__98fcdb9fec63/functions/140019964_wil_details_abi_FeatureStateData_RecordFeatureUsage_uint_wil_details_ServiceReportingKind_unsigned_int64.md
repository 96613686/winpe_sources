# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140019964`
- end: `0x140019a06`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x140019a0c`

## callees

- `0x140017254`
- `0x140019964`
- `0x140019b10`
- `0x140019b44`
- `0x140019b7c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14001999d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001999d`

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
0x140019964  push    rbx
0x140019966  push    rbp
0x140019967  push    rsi
0x140019968  push    rdi
0x140019969  sub     rsp, 38h
0x14001996d  mov     rbp, r9
0x140019970  mov     ebx, r8d
0x140019973  mov     esi, edx
0x140019975  mov     rdi, rcx
0x140019978  cmp     r8d, 0FEh
0x14001997f  jz      short loc_1400199F6
0x140019981  cmp     ebx, 0C8h
0x140019987  jb      short loc_14001999D
0x140019989  cmp     ebx, 100h
0x14001998f  jl      short loc_140019999
0x140019991  cmp     ebx, 200h
0x140019997  jb      short loc_14001999D
0x140019999  xor     al, al
0x14001999b  jmp     short loc_1400199FD
0x14001999d  call    cs:__imp_AcquireSRWLockExclusive
0x1400199a3  mov     [rsp+58h+var_38], rdi
0x1400199a8  cmp     ebx, 7
0x1400199ab  ja      short loc_1400199B7
0x1400199ad  mov     eax, 0CCh
0x1400199b2  bt      eax, ebx
0x1400199b5  jb      short loc_1400199D7
0x1400199b7  lea     eax, [rbx-100h]
0x1400199bd  cmp     eax, 7Fh
0x1400199c0  jbe     short loc_1400199D7
0x1400199c2  mov     r9d, ebp
0x1400199c5  lea     rcx, [rdi+48h]
0x1400199c9  mov     r8d, esi
0x1400199cc  mov     edx, ebx
0x1400199ce  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400199d3  mov     bl, al
0x1400199d5  jmp     short loc_1400199E8
0x1400199d7  mov     r8d, esi
0x1400199da  mov     edx, ebx
0x1400199dc  lea     rcx, [rdi+8]
0x1400199e0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400199e5  mov     bl, [rdi+40h]
0x1400199e8  lea     rcx, [rsp+58h+var_38]
0x1400199ed  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400199f2  mov     al, bl
0x1400199f4  jmp     short loc_1400199FD
0x1400199f6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400199fb  mov     al, 1
0x1400199fd  add     rsp, 38h
0x140019a01  pop     rdi
0x140019a02  pop     rsi
0x140019a03  pop     rbp
0x140019a04  pop     rbx
0x140019a05  retn
```
