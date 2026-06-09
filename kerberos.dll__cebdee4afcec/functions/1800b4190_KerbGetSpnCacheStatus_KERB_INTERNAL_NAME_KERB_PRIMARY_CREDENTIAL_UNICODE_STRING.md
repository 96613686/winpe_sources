# KerbGetSpnCacheStatus(_KERB_INTERNAL_NAME *,_KERB_PRIMARY_CREDENTIAL *,_UNICODE_STRING *)

- ea: `0x1800b4190`
- end: `0x1800b4453`
- name: `?KerbGetSpnCacheStatus@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_KERB_PRIMARY_CREDENTIAL@@PEAU_UNICODE_STRING@@@Z`
- size: `707`
- prototype: `__int64 __fastcall(struct _KERB_INTERNAL_NAME *, struct _KERB_PRIMARY_CREDENTIAL *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003eb80`
- `0x1800566a8`

## callees

- `0x18000b300`
- `0x180029b0c`
- `0x18002c31c`
- `0x18002d020`
- `0x18006ba20`
- `0x18008a304`
- `0x18008b70c`
- `0x1800b4190`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b41b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b4227`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b41b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b4227`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800b4239`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800b4239`
- `ntdll!RtlReleaseResource` at `0x1800b4264`
- `ntdll!RtlReleaseResource` at `0x1800b430d`
- `ntdll!RtlReleaseResource` at `0x1800b4264`
- `ntdll!RtlReleaseResource` at `0x1800b430d`
- `ntdll!RtlAcquireResourceShared` at `0x1800b4249`
- `ntdll!RtlAcquireResourceShared` at `0x1800b4249`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800b42ee`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800b42ee`

## string_xrefs

- `0x1800b41c2`: `KerbGetSpnCacheStatus spn cache disabled\n`
- `0x1800b42d3`: `KerbGetSpnCacheStatus`
- `0x1800b437c`: `KerbGetSpnCacheStatus`
- `0x1800b43e4`: `KerbGetSpnCacheStatus`
- `0x1800b4439`: `KerbGetSpnCacheStatus`
- `0x1800b4427`: `KerbUpdateSpnCacheEntry: SPN cache is not enabled.\n`
- `0x1800b4416`: `Found an SPN cache entry with neither positive nor negative flags set.\n`

## pseudocode

```c
__int64 __fastcall KerbGetSpnCacheStatus(
        struct _KERB_INTERNAL_NAME *a1,
        struct _KERB_PRIMARY_CREDENTIAL *a2,
        struct _UNICODE_STRING *a3)
{
  _KerberosSystemRole *v6; // rcx
  const char *v7; // r9
  __int64 v8; // r8
  struct _KERB_SPN_CACHE_ENTRY *SpnCacheEntry; // rdi
  unsigned int v10; // ebx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( (KerbInfoLevel & 0x10000000) != 0 )
  {
    v7 = "KerbGetSpnCacheStatus spn cache disabled\n";
    v8 = 361;
LABEL_28:
    KerbTracerT::Log(19, "KerbGetSpnCacheStatus", v8, v7);
    return 3221226098LL;
  }
  if ( _KerberosSystemRole::IsEnterpriseKdc(v6) || !KerbGlobalSpnCacheTimeout.QuadPart || !KerberosSpnCacheInitialized )
  {
    v7 = "KerbUpdateSpnCacheEntry: SPN cache is not enabled.\n";
    v8 = 367;
    goto LABEL_28;
  }
  if ( KerbGlobalSpnCacheTimeout.QuadPart + *(_QWORD *)&KerbLastSpnCacheAgeTime < *(_QWORD *)&SystemTimeAsFileTime
    && !_InterlockedCompareExchange(&KerbSpnCacheAgeInProgress, 1, 0) )
  {
    GetSystemTimeAsFileTime(&KerbLastSpnCacheAgeTime);
    QueueUserWorkItem(KerbAgeSpnCache, 0, 0);
  }
  RtlAcquireResourceShared(&stru_180144E88, 1u);
  SpnCacheEntry = KerbFindSpnCacheEntry(a1, a2);
  RtlReleaseResource(&stru_180144E88);
  if ( !SpnCacheEntry )
    return 3221226098LL;
  if ( *((_QWORD *)SpnCacheEntry + 13) + KerbGlobalSpnCacheTimeout.QuadPart < *(_QWORD *)&SystemTimeAsFileTime )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6638f291fd6038c5282b026baf0d567a_Traceguids, a1);
    KerbTracerT::Log(19, "KerbGetSpnCacheStatus", 395, " and account realm %wZ\n", (char *)SpnCacheEntry + 72);
    RtlAcquireResourceExclusive(&stru_180144E88, 1u);
    _KERB_TABLE::Remove((_KERB_TABLE *)&KerbSpnCache, a1, SpnCacheEntry);
    RtlReleaseResource(&stru_180144E88);
    _KERB_TABLE::Dereference((_KERB_TABLE *)&KerbSpnCache, SpnCacheEntry);
    v10 = -1073741198;
LABEL_25:
    _KERB_TABLE::Dereference((_KERB_TABLE *)&KerbSpnCache, SpnCacheEntry);
    return v10;
  }
  if ( (*((_BYTE *)SpnCacheEntry + 112) & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6638f291fd6038c5282b026baf0d567a_Traceguids, a1);
    KerbTracerT::Log(19, "KerbGetSpnCacheStatus", 421, " and account realm %wZ\n", (char *)SpnCacheEntry + 72);
    v10 = -1073741429;
    goto LABEL_25;
  }
  if ( (*((_BYTE *)SpnCacheEntry + 112) & 2) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_6638f291fd6038c5282b026baf0d567a_Traceguids, a1);
    KerbTracerT::Log(19, "KerbGetSpnCacheStatus", 432, " and account realm %wZ\n", (char *)SpnCacheEntry + 72);
    v10 = KerbDuplicateStringEx(a3, (const struct _UNICODE_STRING *)((char *)SpnCacheEntry + 88));
    goto LABEL_25;
  }
  KerbTracerT::Log(
    1,
    "KerbGetSpnCacheStatus",
    448,
    "Found an SPN cache entry with neither positive nor negative flags set.\n");
  return 3221226098LL;
}

```

## disassembly

```asm
0x1800b4190  push    rbx
0x1800b4192  push    rbp
0x1800b4193  push    rsi
0x1800b4194  push    rdi
0x1800b4195  sub     rsp, 38h
0x1800b4199  mov     rbx, rcx
0x1800b419c  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800b41a5  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800b41aa  mov     rsi, r8
0x1800b41ad  mov     rdi, rdx
0x1800b41b0  call    cs:__imp_GetSystemTimeAsFileTime
0x1800b41b6  test    cs:?KerbInfoLevel@@3KA, 10000000h; ulong KerbInfoLevel
0x1800b41c0  jz      short loc_1800B41D4
0x1800b41c2  lea     r9, aKerbgetspncach_2; "KerbGetSpnCacheStatus spn cache disable"...
0x1800b41c9  mov     r8d, 169h
0x1800b41cf  jmp     loc_1800B4434
0x1800b41d4  call    ?IsEnterpriseKdc@_KerberosSystemRole@@QEAA_NXZ; _KerberosSystemRole::IsEnterpriseKdc(void)
0x1800b41d9  test    al, al
0x1800b41db  jnz     loc_1800B4427
0x1800b41e1  mov     rax, cs:?KerbGlobalSpnCacheTimeout@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalSpnCacheTimeout
0x1800b41e8  test    rax, rax
0x1800b41eb  jz      loc_1800B4427
0x1800b41f1  cmp     cs:?KerberosSpnCacheInitialized@@3EA, 0; uchar KerberosSpnCacheInitialized
0x1800b41f8  jz      loc_1800B4427
0x1800b41fe  mov     rdx, qword ptr cs:?KerbLastSpnCacheAgeTime@@3T_LARGE_INTEGER@@A.dwLowDateTime; _LARGE_INTEGER KerbLastSpnCacheAgeTime ...
0x1800b4205  mov     ebp, 1
0x1800b420a  add     rdx, rax
0x1800b420d  cmp     rdx, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x1800b4212  jge     short loc_1800B423F
0x1800b4214  xor     eax, eax
0x1800b4216  lock cmpxchg cs:?KerbSpnCacheAgeInProgress@@3JA, ebp; long KerbSpnCacheAgeInProgress
0x1800b421e  jnz     short loc_1800B423F
0x1800b4220  lea     rcx, ?KerbLastSpnCacheAgeTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x1800b4227  call    cs:__imp_GetSystemTimeAsFileTime
0x1800b422d  xor     r8d, r8d; Flags
0x1800b4230  lea     rcx, ?KerbAgeSpnCache@@YAKPEAX@Z; Function
0x1800b4237  xor     edx, edx; Context
0x1800b4239  call    cs:__imp_QueueUserWorkItem
0x1800b423f  mov     dl, bpl; Wait
0x1800b4242  lea     rcx, stru_180144E88; Resource
0x1800b4249  call    cs:__imp_RtlAcquireResourceShared
0x1800b424f  mov     rdx, rdi; struct _KERB_PRIMARY_CREDENTIAL *
0x1800b4252  mov     rcx, rbx; struct _KERB_INTERNAL_NAME *
0x1800b4255  call    ?KerbFindSpnCacheEntry@@YAPEAU_KERB_SPN_CACHE_ENTRY@@PEAU_KERB_INTERNAL_NAME@@PEAU_KERB_PRIMARY_CREDENTIAL@@@Z; KerbFindSpnCacheEntry(_KERB_INTERNAL_NAME *,_KERB_PRIMARY_CREDENTIAL *)
0x1800b425a  lea     rcx, stru_180144E88; Resource
0x1800b4261  mov     rdi, rax
0x1800b4264  call    cs:__imp_RtlReleaseResource
0x1800b426a  test    rdi, rdi
0x1800b426d  jz      loc_1800B4445
0x1800b4273  mov     r8, cs:?KerbGlobalSpnCacheTimeout@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalSpnCacheTimeout
0x1800b427a  add     r8, [rdi+68h]
0x1800b427e  cmp     r8, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x1800b4283  jge     loc_1800B432C
0x1800b4289  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4290  lea     rax, WPP_GLOBAL_Control
0x1800b4297  cmp     rcx, rax
0x1800b429a  jz      short loc_1800B42BD
0x1800b429c  test    dword ptr [rcx+1Ch], 40000h
0x1800b42a3  jz      short loc_1800B42BD
0x1800b42a5  mov     rcx, [rcx+10h]
0x1800b42a9  lea     r8, WPP_6638f291fd6038c5282b026baf0d567a_Traceguids
0x1800b42b0  mov     edx, 0Ah
0x1800b42b5  mov     r9, rbx
0x1800b42b8  call    WPP_SF__KERB_NAME_
0x1800b42bd  lea     rax, [rdi+48h]
0x1800b42c1  mov     r8d, 18Bh
0x1800b42c7  lea     r9, aAndAccountReal; " and account realm %wZ\n"
0x1800b42ce  mov     [rsp+58h+var_38], rax
0x1800b42d3  lea     rdx, aKerbgetspncach_1; "KerbGetSpnCacheStatus"
0x1800b42da  mov     ecx, 13h
0x1800b42df  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b42e4  mov     dl, bpl; Wait
0x1800b42e7  lea     rcx, stru_180144E88; Resource
0x1800b42ee  call    cs:__imp_RtlAcquireResourceExclusive
0x1800b42f4  mov     r8, rdi; struct _KERB_TABLE_ENTRY *
0x1800b42f7  lea     rcx, ?KerbSpnCache@@3U_KERB_TABLE@@A; this
0x1800b42fe  mov     rdx, rbx; void *
0x1800b4301  call    ?Remove@_KERB_TABLE@@QEAAXPEAXPEAU_KERB_TABLE_ENTRY@@@Z; _KERB_TABLE::Remove(void *,_KERB_TABLE_ENTRY *)
0x1800b4306  lea     rcx, stru_180144E88; Resource
0x1800b430d  call    cs:__imp_RtlReleaseResource
0x1800b4313  mov     rdx, rdi; struct _KERB_TABLE_ENTRY *
0x1800b4316  lea     rcx, ?KerbSpnCache@@3U_KERB_TABLE@@A; this
0x1800b431d  call    ?Dereference@_KERB_TABLE@@QEAAEPEAU_KERB_TABLE_ENTRY@@@Z; _KERB_TABLE::Dereference(_KERB_TABLE_ENTRY *)
0x1800b4322  mov     ebx, 0C0000272h
0x1800b4327  jmp     loc_1800B4403
0x1800b432c  test    [rdi+70h], bpl
0x1800b4330  jz      short loc_1800B4394
0x1800b4332  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4339  lea     rax, WPP_GLOBAL_Control
0x1800b4340  cmp     rcx, rax
0x1800b4343  jz      short loc_1800B4366
0x1800b4345  test    dword ptr [rcx+1Ch], 40000h
0x1800b434c  jz      short loc_1800B4366
0x1800b434e  mov     rcx, [rcx+10h]
0x1800b4352  lea     r8, WPP_6638f291fd6038c5282b026baf0d567a_Traceguids
0x1800b4359  mov     edx, 0Bh
0x1800b435e  mov     r9, rbx
0x1800b4361  call    WPP_SF__KERB_NAME_
0x1800b4366  lea     rax, [rdi+48h]
0x1800b436a  mov     r8d, 1A5h
0x1800b4370  lea     r9, aAndAccountReal; " and account realm %wZ\n"
0x1800b4377  mov     [rsp+58h+var_38], rax
0x1800b437c  lea     rdx, aKerbgetspncach_1; "KerbGetSpnCacheStatus"
0x1800b4383  mov     ecx, 13h
0x1800b4388  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b438d  mov     ebx, 0C000018Bh
0x1800b4392  jmp     short loc_1800B4403
0x1800b4394  test    byte ptr [rdi+70h], 2
0x1800b4398  jz      short loc_1800B4416
0x1800b439a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b43a1  lea     rax, WPP_GLOBAL_Control
0x1800b43a8  cmp     rcx, rax
0x1800b43ab  jz      short loc_1800B43CE
0x1800b43ad  test    dword ptr [rcx+1Ch], 40000h
0x1800b43b4  jz      short loc_1800B43CE
0x1800b43b6  mov     rcx, [rcx+10h]
0x1800b43ba  lea     r8, WPP_6638f291fd6038c5282b026baf0d567a_Traceguids
0x1800b43c1  mov     edx, 0Ch
0x1800b43c6  mov     r9, rbx
0x1800b43c9  call    WPP_SF__KERB_NAME_
0x1800b43ce  lea     rax, [rdi+48h]
0x1800b43d2  mov     r8d, 1B0h
0x1800b43d8  lea     r9, aAndAccountReal; " and account realm %wZ\n"
0x1800b43df  mov     [rsp+58h+var_38], rax
0x1800b43e4  lea     rdx, aKerbgetspncach_1; "KerbGetSpnCacheStatus"
0x1800b43eb  mov     ecx, 13h
0x1800b43f0  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b43f5  lea     rdx, [rdi+58h]; struct _UNICODE_STRING *
0x1800b43f9  mov     rcx, rsi; struct _UNICODE_STRING *
0x1800b43fc  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800b4401  mov     ebx, eax
0x1800b4403  mov     rdx, rdi; struct _KERB_TABLE_ENTRY *
0x1800b4406  lea     rcx, ?KerbSpnCache@@3U_KERB_TABLE@@A; this
0x1800b440d  call    ?Dereference@_KERB_TABLE@@QEAAEPEAU_KERB_TABLE_ENTRY@@@Z; _KERB_TABLE::Dereference(_KERB_TABLE_ENTRY *)
0x1800b4412  mov     eax, ebx
0x1800b4414  jmp     short loc_1800B444A
0x1800b4416  lea     r9, aFoundAnSpnCach; "Found an SPN cache entry with neither p"...
0x1800b441d  mov     r8d, 1C0h
0x1800b4423  mov     ecx, ebp
0x1800b4425  jmp     short loc_1800B4439
0x1800b4427  lea     r9, aKerbupdatespnc; "KerbUpdateSpnCacheEntry: SPN cache is n"...
0x1800b442e  mov     r8d, 16Fh
0x1800b4434  mov     ecx, 13h
0x1800b4439  lea     rdx, aKerbgetspncach_1; "KerbGetSpnCacheStatus"
0x1800b4440  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b4445  mov     eax, 0C0000272h
0x1800b444a  add     rsp, 38h
0x1800b444e  pop     rdi
0x1800b444f  pop     rsi
0x1800b4450  pop     rbp
0x1800b4451  pop     rbx
0x1800b4452  retn
```
