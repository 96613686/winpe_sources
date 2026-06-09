# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008224`
- end: `0x1800082c6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800034f4`

## callees

- `0x180003620`
- `0x180008224`
- `0x180008304`
- `0x180008338`
- `0x180008370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000825d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000825d`

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
0x180008224  push    rbx
0x180008226  push    rbp
0x180008227  push    rsi
0x180008228  push    rdi
0x180008229  sub     rsp, 38h
0x18000822d  mov     rbp, r9
0x180008230  mov     ebx, r8d
0x180008233  mov     esi, edx
0x180008235  mov     rdi, rcx
0x180008238  cmp     r8d, 0FEh
0x18000823f  jz      short loc_1800082B6
0x180008241  cmp     ebx, 0C8h
0x180008247  jb      short loc_18000825D
0x180008249  cmp     ebx, 100h
0x18000824f  jl      short loc_180008259
0x180008251  cmp     ebx, 200h
0x180008257  jb      short loc_18000825D
0x180008259  xor     al, al
0x18000825b  jmp     short loc_1800082BD
0x18000825d  call    cs:__imp_AcquireSRWLockExclusive
0x180008263  mov     [rsp+58h+var_38], rdi
0x180008268  cmp     ebx, 7
0x18000826b  ja      short loc_180008277
0x18000826d  mov     eax, 0CCh
0x180008272  bt      eax, ebx
0x180008275  jb      short loc_180008297
0x180008277  lea     eax, [rbx-100h]
0x18000827d  cmp     eax, 7Fh
0x180008280  jbe     short loc_180008297
0x180008282  mov     r9d, ebp
0x180008285  lea     rcx, [rdi+48h]
0x180008289  mov     r8d, esi
0x18000828c  mov     edx, ebx
0x18000828e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180008293  mov     bl, al
0x180008295  jmp     short loc_1800082A8
0x180008297  mov     r8d, esi
0x18000829a  lea     rcx, [rdi+8]
0x18000829e  mov     edx, ebx
0x1800082a0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800082a5  mov     bl, [rdi+40h]
0x1800082a8  lea     rcx, [rsp+58h+var_38]
0x1800082ad  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800082b2  mov     al, bl
0x1800082b4  jmp     short loc_1800082BD
0x1800082b6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800082bb  mov     al, 1
0x1800082bd  add     rsp, 38h
0x1800082c1  pop     rdi
0x1800082c2  pop     rsi
0x1800082c3  pop     rbp
0x1800082c4  pop     rbx
0x1800082c5  retn
```
