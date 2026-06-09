# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001b174`
- end: `0x18001b21d`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180012118`

## callees

- `0x180012260`
- `0x18001b174`
- `0x18001b264`
- `0x18001b29c`
- `0x18001b2d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b1ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b1ad`

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
0x18001b174  push    rbx
0x18001b176  push    rbp
0x18001b177  push    rsi
0x18001b178  push    rdi
0x18001b179  sub     rsp, 38h
0x18001b17d  mov     rbp, r9
0x18001b180  mov     ebx, r8d
0x18001b183  mov     esi, edx
0x18001b185  mov     rdi, rcx
0x18001b188  cmp     r8d, 0FEh
0x18001b18f  jz      short loc_18001B20C
0x18001b191  cmp     ebx, 0C8h
0x18001b197  jb      short loc_18001B1AD
0x18001b199  cmp     ebx, 100h
0x18001b19f  jl      short loc_18001B1A9
0x18001b1a1  cmp     ebx, 200h
0x18001b1a7  jb      short loc_18001B1AD
0x18001b1a9  xor     al, al
0x18001b1ab  jmp     short loc_18001B213
0x18001b1ad  call    cs:__imp_AcquireSRWLockExclusive
0x18001b1b4  nop     dword ptr [rax+rax+00h]
0x18001b1b9  mov     [rsp+58h+var_38], rdi
0x18001b1be  cmp     ebx, 7
0x18001b1c1  ja      short loc_18001B1CD
0x18001b1c3  mov     eax, 0CCh
0x18001b1c8  bt      eax, ebx
0x18001b1cb  jb      short loc_18001B1ED
0x18001b1cd  lea     eax, [rbx-100h]
0x18001b1d3  cmp     eax, 7Fh
0x18001b1d6  jbe     short loc_18001B1ED
0x18001b1d8  mov     r9d, ebp
0x18001b1db  lea     rcx, [rdi+48h]
0x18001b1df  mov     r8d, esi
0x18001b1e2  mov     edx, ebx
0x18001b1e4  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001b1e9  mov     bl, al
0x18001b1eb  jmp     short loc_18001B1FE
0x18001b1ed  mov     r8d, esi
0x18001b1f0  lea     rcx, [rdi+8]
0x18001b1f4  mov     edx, ebx
0x18001b1f6  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001b1fb  mov     bl, [rdi+40h]
0x18001b1fe  lea     rcx, [rsp+58h+var_38]
0x18001b203  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001b208  mov     al, bl
0x18001b20a  jmp     short loc_18001B213
0x18001b20c  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001b211  mov     al, 1
0x18001b213  add     rsp, 38h
0x18001b217  pop     rdi
0x18001b218  pop     rsi
0x18001b219  pop     rbp
0x18001b21a  pop     rbx
0x18001b21b  retn
```
