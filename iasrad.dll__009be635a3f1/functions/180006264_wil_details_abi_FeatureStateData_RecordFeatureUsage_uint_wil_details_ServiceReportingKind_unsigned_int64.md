# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006264`
- end: `0x180006306`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000630c`

## callees

- `0x180003338`
- `0x180006264`
- `0x180006420`
- `0x180006454`
- `0x18000648c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000629d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000629d`

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
0x180006264  push    rbx
0x180006266  push    rbp
0x180006267  push    rsi
0x180006268  push    rdi
0x180006269  sub     rsp, 38h
0x18000626d  mov     rbp, r9
0x180006270  mov     ebx, r8d
0x180006273  mov     esi, edx
0x180006275  mov     rdi, rcx
0x180006278  cmp     r8d, 0FEh
0x18000627f  jz      short loc_1800062F6
0x180006281  cmp     ebx, 0C8h
0x180006287  jb      short loc_18000629D
0x180006289  cmp     ebx, 100h
0x18000628f  jl      short loc_180006299
0x180006291  cmp     ebx, 200h
0x180006297  jb      short loc_18000629D
0x180006299  xor     al, al
0x18000629b  jmp     short loc_1800062FD
0x18000629d  call    cs:__imp_AcquireSRWLockExclusive
0x1800062a3  mov     [rsp+58h+var_38], rdi
0x1800062a8  cmp     ebx, 7
0x1800062ab  ja      short loc_1800062B7
0x1800062ad  mov     eax, 0CCh
0x1800062b2  bt      eax, ebx
0x1800062b5  jb      short loc_1800062D7
0x1800062b7  lea     eax, [rbx-100h]
0x1800062bd  cmp     eax, 7Fh
0x1800062c0  jbe     short loc_1800062D7
0x1800062c2  mov     r9d, ebp
0x1800062c5  lea     rcx, [rdi+48h]
0x1800062c9  mov     r8d, esi
0x1800062cc  mov     edx, ebx
0x1800062ce  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800062d3  mov     bl, al
0x1800062d5  jmp     short loc_1800062E8
0x1800062d7  mov     r8d, esi
0x1800062da  lea     rcx, [rdi+8]
0x1800062de  mov     edx, ebx
0x1800062e0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800062e5  mov     bl, [rdi+40h]
0x1800062e8  lea     rcx, [rsp+58h+var_38]
0x1800062ed  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800062f2  mov     al, bl
0x1800062f4  jmp     short loc_1800062FD
0x1800062f6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800062fb  mov     al, 1
0x1800062fd  add     rsp, 38h
0x180006301  pop     rdi
0x180006302  pop     rsi
0x180006303  pop     rbp
0x180006304  pop     rbx
0x180006305  retn
```
