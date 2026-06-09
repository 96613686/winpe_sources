# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180021584`
- end: `0x180021626`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180011abc`

## callees

- `0x180011c60`
- `0x180021584`
- `0x180021680`
- `0x1800216b4`
- `0x1800216ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800215bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800215bd`

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
0x180021584  push    rbx
0x180021586  push    rbp
0x180021587  push    rsi
0x180021588  push    rdi
0x180021589  sub     rsp, 38h
0x18002158d  mov     rbp, r9
0x180021590  mov     ebx, r8d
0x180021593  mov     esi, edx
0x180021595  mov     rdi, rcx
0x180021598  cmp     r8d, 0FEh
0x18002159f  jz      short loc_180021616
0x1800215a1  cmp     ebx, 0C8h
0x1800215a7  jb      short loc_1800215BD
0x1800215a9  cmp     ebx, 100h
0x1800215af  jl      short loc_1800215B9
0x1800215b1  cmp     ebx, 200h
0x1800215b7  jb      short loc_1800215BD
0x1800215b9  xor     al, al
0x1800215bb  jmp     short loc_18002161D
0x1800215bd  call    cs:__imp_AcquireSRWLockExclusive
0x1800215c3  mov     [rsp+58h+var_38], rdi
0x1800215c8  cmp     ebx, 7
0x1800215cb  ja      short loc_1800215D7
0x1800215cd  mov     eax, 0CCh
0x1800215d2  bt      eax, ebx
0x1800215d5  jb      short loc_1800215F7
0x1800215d7  lea     eax, [rbx-100h]
0x1800215dd  cmp     eax, 7Fh
0x1800215e0  jbe     short loc_1800215F7
0x1800215e2  mov     r9d, ebp
0x1800215e5  lea     rcx, [rdi+48h]
0x1800215e9  mov     r8d, esi
0x1800215ec  mov     edx, ebx
0x1800215ee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800215f3  mov     bl, al
0x1800215f5  jmp     short loc_180021608
0x1800215f7  mov     r8d, esi
0x1800215fa  lea     rcx, [rdi+8]
0x1800215fe  mov     edx, ebx
0x180021600  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180021605  mov     bl, [rdi+40h]
0x180021608  lea     rcx, [rsp+58h+var_38]
0x18002160d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180021612  mov     al, bl
0x180021614  jmp     short loc_18002161D
0x180021616  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002161b  mov     al, 1
0x18002161d  add     rsp, 38h
0x180021621  pop     rdi
0x180021622  pop     rsi
0x180021623  pop     rbp
0x180021624  pop     rbx
0x180021625  retn
```
