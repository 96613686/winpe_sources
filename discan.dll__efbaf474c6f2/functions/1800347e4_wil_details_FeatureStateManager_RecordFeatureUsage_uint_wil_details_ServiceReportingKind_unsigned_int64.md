# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800347e4`
- end: `0x1800348bd`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `217`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180035df0`

## callees

- `0x1800137d4`
- `0x180031530`
- `0x180032b08`
- `0x1800344dc`
- `0x1800347e4`
- `0x1800348c4`
- `0x1800349c4`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18003483f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180034885`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003483f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180034885`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  RTL_SRWLOCK *v8; // rsi
  char v9; // bl
  wil *v10; // rcx
  RTL_SRWLOCK *v11; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
  {
    v8 = (RTL_SRWLOCK *)*((_QWORD *)a1 + 3);
    if ( a3 == 254 )
    {
      wil::details_abi::FeatureStateData::RecordUsage(*((wil::details_abi::FeatureStateData **)a1 + 3));
LABEL_10:
      if ( !wil::ProcessShutdownInProgress(v10) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
        v11 = (RTL_SRWLOCK *)(a1 + 32);
        wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>((_QWORD *)a1 + 6, a1 + 65, a1);
        CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v11);
      }
      return;
    }
    if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
    {
      AcquireSRWLockExclusive(*((PSRWLOCK *)a1 + 3));
      v11 = v8;
      v9 = wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(v8, a2, a3, a4);
      CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v11);
      if ( v9 )
        goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x1800347e4  mov     [rsp+arg_8], rbx
0x1800347e9  mov     [rsp+arg_10], rbp
0x1800347ee  push    rsi
0x1800347ef  push    rdi
0x1800347f0  push    r14
0x1800347f2  sub     rsp, 20h
0x1800347f6  cmp     byte ptr [rcx], 0
0x1800347f9  mov     rbp, r9
0x1800347fc  mov     ebx, r8d
0x1800347ff  mov     r14d, edx
0x180034802  mov     rdi, rcx
0x180034805  jz      loc_1800348AA
0x18003480b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180034810  test    al, al
0x180034812  jz      loc_1800348AA
0x180034818  mov     rsi, [rdi+18h]
0x18003481c  cmp     ebx, 0FEh
0x180034822  jz      short loc_18003486D
0x180034824  cmp     ebx, 0C8h
0x18003482a  jb      short loc_18003483C
0x18003482c  cmp     ebx, 100h
0x180034832  jl      short loc_1800348AA
0x180034834  cmp     ebx, 200h
0x18003483a  jnb     short loc_1800348AA
0x18003483c  mov     rcx, rsi; SRWLock
0x18003483f  call    cs:__imp_AcquireSRWLockExclusive
0x180034845  mov     r9, rbp
0x180034848  mov     [rsp+38h+arg_0], rsi
0x18003484d  mov     r8d, ebx
0x180034850  mov     edx, r14d
0x180034853  mov     rcx, rsi
0x180034856  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18003485b  lea     rcx, [rsp+38h+arg_0]; this
0x180034860  mov     bl, al
0x180034862  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180034867  test    bl, bl
0x180034869  jz      short loc_1800348AA
0x18003486b  jmp     short loc_180034875
0x18003486d  mov     rcx, rsi; this
0x180034870  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180034875  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003487a  test    al, al
0x18003487c  jnz     short loc_1800348AA
0x18003487e  lea     rbx, [rdi+20h]
0x180034882  mov     rcx, rbx; SRWLock
0x180034885  call    cs:__imp_AcquireSRWLockExclusive
0x18003488b  lea     rdx, [rdi+41h]
0x18003488f  mov     [rsp+38h+arg_0], rbx
0x180034894  lea     rcx, [rdi+30h]
0x180034898  mov     r8, rdi
0x18003489b  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x1800348a0  lea     rcx, [rsp+38h+arg_0]; this
0x1800348a5  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x1800348aa  mov     rbx, [rsp+38h+arg_8]
0x1800348af  mov     rbp, [rsp+38h+arg_10]
0x1800348b4  add     rsp, 20h
0x1800348b8  pop     r14
0x1800348ba  pop     rdi
0x1800348bb  pop     rsi
0x1800348bc  retn
```
