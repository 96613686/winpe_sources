# KerbUpdateSpnCacheEntry(_KERB_INTERNAL_NAME *,_KERB_PRIMARY_CREDENTIAL *,ulong,_UNICODE_STRING *)

- ea: `0x18005e9a0`
- end: `0x18005ebaa`
- name: `?KerbUpdateSpnCacheEntry@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_KERB_PRIMARY_CREDENTIAL@@KPEAU_UNICODE_STRING@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(struct _KERB_INTERNAL_NAME *, struct _KERB_PRIMARY_CREDENTIAL *, unsigned int, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18003eb80`
- `0x1800566a8`

## callees

- `0x180009184`
- `0x180029b0c`
- `0x18002c31c`
- `0x18002d020`
- `0x18005e9a0`
- `0x18006ba20`
- `0x18008a304`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005e9c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005e9c7`
- `ntdll!RtlReleaseResource` at `0x18005ea33`
- `ntdll!RtlReleaseResource` at `0x18005ea5d`
- `ntdll!RtlReleaseResource` at `0x18005ea90`
- `ntdll!RtlReleaseResource` at `0x18005eb73`
- `ntdll!RtlReleaseResource` at `0x18005ea33`
- `ntdll!RtlReleaseResource` at `0x18005ea5d`
- `ntdll!RtlReleaseResource` at `0x18005ea90`
- `ntdll!RtlReleaseResource` at `0x18005eb73`
- `ntdll!RtlAcquireResourceShared` at `0x18005ea00`
- `ntdll!RtlAcquireResourceShared` at `0x18005ea00`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005ea68`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005ea68`

## string_xrefs

- `0x18005eb7d`: `KerbUpdateSpnCacheEntry: SPN cache is not enabled.\n`
- `0x18005eaf6`: `KerbUpdateSpnCacheEntry`
- `0x18005eb5f`: `KerbUpdateSpnCacheEntry`
- `0x18005eb8a`: `KerbUpdateSpnCacheEntry`
- `0x18005ea48`: `KerbUpdateSpnCacheEntry: Fake update, doing nothing.\n`
- `0x18005ea96`: `KerbUpdateSpnCacheEntry: Race condition in update, doing nothing.\n`
- `0x18005eae4`: ` and account realm %wZ with update flags 0x%X\n`
- `0x18005eb4e`: `KerbUpdateSpnCacheEntry: Failed to create new SPN cache entry 0x%08X\n`

## pseudocode

```c
__int64 __fastcall KerbUpdateSpnCacheEntry(
        struct _KERB_INTERNAL_NAME *a1,
        struct _KERB_PRIMARY_CREDENTIAL *a2,
        unsigned int a3,
        struct _UNICODE_STRING *a4)
{
  _KerberosSystemRole *v8; // rcx
  struct _KERB_SPN_CACHE_ENTRY *SpnCacheEntry; // rax
  struct _KERB_SPN_CACHE_ENTRY *v10; // rbx
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v14; // [rsp+28h] [rbp-50h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-48h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( _KerberosSystemRole::IsEnterpriseKdc(v8) || !KerbGlobalSpnCacheTimeout.QuadPart || !KerberosSpnCacheInitialized )
  {
    KerbTracerT::Log(19, "KerbUpdateSpnCacheEntry", 573, "KerbUpdateSpnCacheEntry: SPN cache is not enabled.\n");
    return 0;
  }
  RtlAcquireResourceShared(&stru_180144E88, 1u);
  SpnCacheEntry = KerbFindSpnCacheEntry(a1, a2);
  v10 = SpnCacheEntry;
  if ( SpnCacheEntry
    && KerbGlobalSpnCacheTimeout.QuadPart + *((_QWORD *)SpnCacheEntry + 13) > *(_QWORD *)&SystemTimeAsFileTime
    && *((_DWORD *)SpnCacheEntry + 28) == a3 )
  {
    RtlReleaseResource(&stru_180144E88);
    _KERB_TABLE::Dereference((_KERB_TABLE *)&KerbSpnCache, v10);
    KerbTracerT::Log(19, "KerbUpdateSpnCacheEntry", 595, "KerbUpdateSpnCacheEntry: Fake update, doing nothing.\n");
    return 0;
  }
  RtlReleaseResource(&stru_180144E88);
  RtlAcquireResourceExclusive(&stru_180144E88, 1u);
  if ( v10 )
  {
    if ( !*((_QWORD *)v10 + 3) )
    {
      _KERB_TABLE::Dereference((_KERB_TABLE *)&KerbSpnCache, v10);
      RtlReleaseResource(&stru_180144E88);
      KerbTracerT::Log(
        19,
        "KerbUpdateSpnCacheEntry",
        627,
        "KerbUpdateSpnCacheEntry: Race condition in update, doing nothing.\n");
      return 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6638f291fd6038c5282b026baf0d567a_Traceguids, a1);
    v14 = a3;
    KerbTracerT::Log(
      19,
      "KerbUpdateSpnCacheEntry",
      633,
      " and account realm %wZ with update flags 0x%X\n",
      (char *)a2 + 16,
      v14);
    _KERB_TABLE::Remove((_KERB_TABLE *)&KerbSpnCache, a1, v10);
    _KERB_TABLE::Dereference((_KERB_TABLE *)&KerbSpnCache, v10);
    _KERB_TABLE::Dereference((_KERB_TABLE *)&KerbSpnCache, v10);
  }
  v11 = KerbCreateSpnCacheEntry(a1, a2, a3, a4);
  v12 = v11;
  if ( v11 < 0 )
    KerbTracerT::Log(
      1,
      "KerbUpdateSpnCacheEntry",
      644,
      "KerbUpdateSpnCacheEntry: Failed to create new SPN cache entry 0x%08X\n",
      v11);
  RtlReleaseResource(&stru_180144E88);
  return v12;
}

```

## disassembly

```asm
0x18005e9a0  push    rbx
0x18005e9a2  push    rbp
0x18005e9a3  push    rsi
0x18005e9a4  push    rdi
0x18005e9a5  push    r12
0x18005e9a7  push    r14
0x18005e9a9  sub     rsp, 48h
0x18005e9ad  mov     rdi, rcx
0x18005e9b0  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18005e9b9  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005e9be  mov     r14, r9
0x18005e9c1  mov     esi, r8d
0x18005e9c4  mov     rbp, rdx
0x18005e9c7  call    cs:__imp_GetSystemTimeAsFileTime
0x18005e9cd  call    ?IsEnterpriseKdc@_KerberosSystemRole@@QEAA_NXZ; _KerberosSystemRole::IsEnterpriseKdc(void)
0x18005e9d2  test    al, al
0x18005e9d4  jnz     loc_18005EB7D
0x18005e9da  cmp     cs:?KerbGlobalSpnCacheTimeout@@3T_LARGE_INTEGER@@A, 0; _LARGE_INTEGER KerbGlobalSpnCacheTimeout
0x18005e9e2  jz      loc_18005EB7D
0x18005e9e8  cmp     cs:?KerberosSpnCacheInitialized@@3EA, al; uchar KerberosSpnCacheInitialized
0x18005e9ee  jz      loc_18005EB7D
0x18005e9f4  lea     r12, stru_180144E88
0x18005e9fb  mov     dl, 1; Wait
0x18005e9fd  mov     rcx, r12; Resource
0x18005ea00  call    cs:__imp_RtlAcquireResourceShared
0x18005ea06  mov     rdx, rbp; struct _KERB_PRIMARY_CREDENTIAL *
0x18005ea09  mov     rcx, rdi; struct _KERB_INTERNAL_NAME *
0x18005ea0c  call    ?KerbFindSpnCacheEntry@@YAPEAU_KERB_SPN_CACHE_ENTRY@@PEAU_KERB_INTERNAL_NAME@@PEAU_KERB_PRIMARY_CREDENTIAL@@@Z; KerbFindSpnCacheEntry(_KERB_INTERNAL_NAME *,_KERB_PRIMARY_CREDENTIAL *)
0x18005ea11  mov     rbx, rax
0x18005ea14  test    rax, rax
0x18005ea17  jz      short loc_18005EA5A
0x18005ea19  mov     r8, [rax+68h]
0x18005ea1d  add     r8, cs:?KerbGlobalSpnCacheTimeout@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalSpnCacheTimeout
0x18005ea24  cmp     r8, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x18005ea29  jle     short loc_18005EA5A
0x18005ea2b  cmp     [rax+70h], esi
0x18005ea2e  jnz     short loc_18005EA5A
0x18005ea30  mov     rcx, r12; Resource
0x18005ea33  call    cs:__imp_RtlReleaseResource
0x18005ea39  mov     rdx, rbx; struct _KERB_TABLE_ENTRY *
0x18005ea3c  lea     rcx, ?KerbSpnCache@@3U_KERB_TABLE@@A; this
0x18005ea43  call    ?Dereference@_KERB_TABLE@@QEAAEPEAU_KERB_TABLE_ENTRY@@@Z; _KERB_TABLE::Dereference(_KERB_TABLE_ENTRY *)
0x18005ea48  lea     r9, aKerbupdatespnc_0; "KerbUpdateSpnCacheEntry: Fake update, d"...
0x18005ea4f  mov     r8d, 253h
0x18005ea55  jmp     loc_18005EB8A
0x18005ea5a  mov     rcx, r12; Resource
0x18005ea5d  call    cs:__imp_RtlReleaseResource
0x18005ea63  mov     dl, 1; Wait
0x18005ea65  mov     rcx, r12; Resource
0x18005ea68  call    cs:__imp_RtlAcquireResourceExclusive
0x18005ea6e  test    rbx, rbx
0x18005ea71  jz      loc_18005EB37
0x18005ea77  cmp     qword ptr [rbx+18h], 0
0x18005ea7c  jnz     short loc_18005EAA8
0x18005ea7e  mov     rdx, rbx; struct _KERB_TABLE_ENTRY *
0x18005ea81  lea     rcx, ?KerbSpnCache@@3U_KERB_TABLE@@A; this
0x18005ea88  call    ?Dereference@_KERB_TABLE@@QEAAEPEAU_KERB_TABLE_ENTRY@@@Z; _KERB_TABLE::Dereference(_KERB_TABLE_ENTRY *)
0x18005ea8d  mov     rcx, r12; Resource
0x18005ea90  call    cs:__imp_RtlReleaseResource
0x18005ea96  lea     r9, aKerbupdatespnc_3; "KerbUpdateSpnCacheEntry: Race condition"...
0x18005ea9d  mov     r8d, 273h
0x18005eaa3  jmp     loc_18005EB8A
0x18005eaa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eaaf  lea     rax, WPP_GLOBAL_Control
0x18005eab6  cmp     rcx, rax
0x18005eab9  jz      short loc_18005EADC
0x18005eabb  test    dword ptr [rcx+1Ch], 40000h
0x18005eac2  jz      short loc_18005EADC
0x18005eac4  mov     rcx, [rcx+10h]
0x18005eac8  lea     r8, WPP_6638f291fd6038c5282b026baf0d567a_Traceguids
0x18005eacf  mov     edx, 0Dh
0x18005ead4  mov     r9, rdi
0x18005ead7  call    WPP_SF__KERB_NAME_
0x18005eadc  lea     rax, [rbp+10h]
0x18005eae0  mov     [rsp+78h+var_50], esi
0x18005eae4  lea     r9, aAndAccountReal_0; " and account realm %wZ with update flag"...
0x18005eaeb  mov     [rsp+78h+var_58], rax
0x18005eaf0  mov     r8d, 279h
0x18005eaf6  lea     rdx, aKerbupdatespnc_1; "KerbUpdateSpnCacheEntry"
0x18005eafd  mov     ecx, 13h
0x18005eb02  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005eb07  mov     r8, rbx; struct _KERB_TABLE_ENTRY *
0x18005eb0a  lea     rcx, ?KerbSpnCache@@3U_KERB_TABLE@@A; this
0x18005eb11  mov     rdx, rdi; void *
0x18005eb14  call    ?Remove@_KERB_TABLE@@QEAAXPEAXPEAU_KERB_TABLE_ENTRY@@@Z; _KERB_TABLE::Remove(void *,_KERB_TABLE_ENTRY *)
0x18005eb19  mov     rdx, rbx; struct _KERB_TABLE_ENTRY *
0x18005eb1c  lea     rcx, ?KerbSpnCache@@3U_KERB_TABLE@@A; this
0x18005eb23  call    ?Dereference@_KERB_TABLE@@QEAAEPEAU_KERB_TABLE_ENTRY@@@Z; _KERB_TABLE::Dereference(_KERB_TABLE_ENTRY *)
0x18005eb28  mov     rdx, rbx; struct _KERB_TABLE_ENTRY *
0x18005eb2b  lea     rcx, ?KerbSpnCache@@3U_KERB_TABLE@@A; this
0x18005eb32  call    ?Dereference@_KERB_TABLE@@QEAAEPEAU_KERB_TABLE_ENTRY@@@Z; _KERB_TABLE::Dereference(_KERB_TABLE_ENTRY *)
0x18005eb37  mov     r9, r14; struct _UNICODE_STRING *
0x18005eb3a  mov     r8d, esi; unsigned int
0x18005eb3d  mov     rdx, rbp; struct _KERB_PRIMARY_CREDENTIAL *
0x18005eb40  mov     rcx, rdi; struct _KERB_INTERNAL_NAME *
0x18005eb43  call    ?KerbCreateSpnCacheEntry@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_KERB_PRIMARY_CREDENTIAL@@KPEAU_UNICODE_STRING@@@Z; KerbCreateSpnCacheEntry(_KERB_INTERNAL_NAME *,_KERB_PRIMARY_CREDENTIAL *,ulong,_UNICODE_STRING *)
0x18005eb48  mov     ebx, eax
0x18005eb4a  test    eax, eax
0x18005eb4c  jns     short loc_18005EB70
0x18005eb4e  lea     r9, aKerbupdatespnc_2; "KerbUpdateSpnCacheEntry: Failed to crea"...
0x18005eb55  mov     dword ptr [rsp+78h+var_58], eax
0x18005eb59  mov     r8d, 284h
0x18005eb5f  lea     rdx, aKerbupdatespnc_1; "KerbUpdateSpnCacheEntry"
0x18005eb66  mov     ecx, 1
0x18005eb6b  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005eb70  mov     rcx, r12; Resource
0x18005eb73  call    cs:__imp_RtlReleaseResource
0x18005eb79  mov     eax, ebx
0x18005eb7b  jmp     short loc_18005EB9D
0x18005eb7d  lea     r9, aKerbupdatespnc; "KerbUpdateSpnCacheEntry: SPN cache is n"...
0x18005eb84  mov     r8d, 23Dh
0x18005eb8a  lea     rdx, aKerbupdatespnc_1; "KerbUpdateSpnCacheEntry"
0x18005eb91  mov     ecx, 13h
0x18005eb96  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005eb9b  xor     eax, eax
0x18005eb9d  add     rsp, 48h
0x18005eba1  pop     r14
0x18005eba3  pop     r12
0x18005eba5  pop     rdi
0x18005eba6  pop     rsi
0x18005eba7  pop     rbp
0x18005eba8  pop     rbx
0x18005eba9  retn
```
