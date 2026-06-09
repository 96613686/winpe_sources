# LsaDbpLookupNamesInTrustedDomains(ulong,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,long *)

- ea: `0x18001d228`
- end: `0x18001d32b`
- name: `?LsaDbpLookupNamesInTrustedDomains@@YAJKKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAJ@Z`
- size: `259`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001c670`

## callees

- `0x18001b214`
- `0x18001b2d4`
- `0x18001b8dc`
- `0x18001d228`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001d2b9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001d2e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001d2b9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001d2e3`
- `LSASRV!LsaLookupPerfCounterAddLargeAmount` at `0x18001d2fa`
- `LSASRV!LsaLookupPerfCounterAddLargeAmount` at `0x18001d2fa`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001d2af`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001d308`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001d2af`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001d308`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupNamesInTrustedDomains(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        int *a11)
{
  int v11; // eax
  HLOCAL v12; // rdi
  unsigned int v13; // ebx
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-21h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-19h]
  LARGE_INTEGER v17; // [rsp+78h] [rbp-11h] BYREF

  hMem = 0;
  PerformanceCount.QuadPart = 0;
  v17.QuadPart = 0;
  *a11 = 0;
  v11 = LsaDbpLookupNamesBuildWorkList(a1, a2, a3);
  v12 = hMem;
  v13 = v11;
  if ( v11 >= 0 )
  {
    LsaLookupPerfCounterAddAmount(0x13u, *((_DWORD *)hMem + 14));
    if ( !QueryPerformanceCounter(&PerformanceCount) )
      PerformanceCount.QuadPart = 0;
    v13 = LsaDbpLookupProcessWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST *)v12, a11);
    if ( PerformanceCount.QuadPart && QueryPerformanceCounter(&v17) )
    {
      LsaLookupPerfCounterAddLargeAmount(0x14u, v17.QuadPart - PerformanceCount.QuadPart);
      LsaLookupPerfCounterAddAmount(0x15u, *((_DWORD *)v12 + 14));
    }
  }
  else if ( v11 == -1073741709 )
  {
    v13 = 0;
  }
  if ( v12 )
    return (unsigned int)LsaDbpLookupDeleteWorkList(v12);
  return v13;
}

```

## disassembly

```asm
0x18001d228  mov     r11, rsp
0x18001d22b  push    rbp
0x18001d22c  push    rbx
0x18001d22d  push    rsi
0x18001d22e  push    rdi
0x18001d22f  lea     rbp, [r11-27h]
0x18001d233  sub     rsp, 88h
0x18001d23a  mov     rsi, [rbp+1Fh+arg_50]
0x18001d23e  lea     rax, [rbp+1Fh+hMem]
0x18001d242  mov     [r11-58h], rax
0x18001d246  mov     rax, [rbp+1Fh+arg_48]
0x18001d24a  mov     [r11-60h], rax
0x18001d24e  mov     rax, [rbp+1Fh+arg_40]
0x18001d252  mov     [r11-68h], rax
0x18001d256  mov     rax, [rbp+1Fh+arg_30]
0x18001d25a  mov     [r11-78h], rax
0x18001d25e  mov     rax, [rbp+1Fh+arg_28]
0x18001d262  mov     [r11-80h], rax
0x18001d266  mov     rax, [rbp+1Fh+arg_20]
0x18001d26a  mov     [rsp+20h], rax
0x18001d26f  mov     [rbp+1Fh+hMem], 0
0x18001d277  mov     qword ptr [rbp+1Fh+PerformanceCount], 0
0x18001d27f  mov     qword ptr [rbp+1Fh+var_30], 0
0x18001d287  mov     dword ptr [rsi], 0
0x18001d28d  call    ?LsaDbpLookupNamesBuildWorkList@@YAJKKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupNamesBuildWorkList(ulong,ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,_LSAP_DB_LOOKUP_WORK_LIST * *)
0x18001d292  mov     rdi, [rbp+1Fh+hMem]
0x18001d296  mov     ebx, eax
0x18001d298  test    eax, eax
0x18001d29a  jns     short loc_18001D2A7
0x18001d29c  cmp     eax, 0C0000073h
0x18001d2a1  jnz     short loc_18001D30E
0x18001d2a3  xor     ebx, ebx
0x18001d2a5  jmp     short loc_18001D30E
0x18001d2a7  mov     edx, [rdi+38h]
0x18001d2aa  mov     ecx, 13h
0x18001d2af  call    cs:__imp_?LsaLookupPerfCounterAddAmount@@YAXKK@Z; LsaLookupPerfCounterAddAmount(ulong,ulong)
0x18001d2b5  lea     rcx, [rbp+1Fh+PerformanceCount]; lpPerformanceCount
0x18001d2b9  call    cs:__imp_QueryPerformanceCounter
0x18001d2bf  test    eax, eax
0x18001d2c1  jnz     short loc_18001D2CB
0x18001d2c3  mov     qword ptr [rbp+1Fh+PerformanceCount], 0
0x18001d2cb  mov     rdx, rsi; int *
0x18001d2ce  mov     rcx, rdi; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001d2d1  call    ?LsaDbpLookupProcessWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAJ@Z; LsaDbpLookupProcessWorkList(_LSAP_DB_LOOKUP_WORK_LIST *,long *)
0x18001d2d6  cmp     qword ptr [rbp+1Fh+PerformanceCount], 0
0x18001d2db  mov     ebx, eax
0x18001d2dd  jz      short loc_18001D30E
0x18001d2df  lea     rcx, [rbp+1Fh+var_30]; lpPerformanceCount
0x18001d2e3  call    cs:__imp_QueryPerformanceCounter
0x18001d2e9  test    eax, eax
0x18001d2eb  jz      short loc_18001D30E
0x18001d2ed  mov     rdx, qword ptr [rbp+1Fh+var_30]
0x18001d2f1  mov     ecx, 14h
0x18001d2f6  sub     rdx, qword ptr [rbp+1Fh+PerformanceCount]
0x18001d2fa  call    cs:__imp_?LsaLookupPerfCounterAddLargeAmount@@YAXK_K@Z; LsaLookupPerfCounterAddLargeAmount(ulong,unsigned __int64)
0x18001d300  mov     edx, [rdi+38h]
0x18001d303  mov     ecx, 15h
0x18001d308  call    cs:__imp_?LsaLookupPerfCounterAddAmount@@YAXKK@Z; LsaLookupPerfCounterAddAmount(ulong,ulong)
0x18001d30e  test    rdi, rdi
0x18001d311  jz      short loc_18001D31D
0x18001d313  mov     rcx, rdi; hMem
0x18001d316  call    ?LsaDbpLookupDeleteWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupDeleteWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x18001d31b  mov     ebx, eax
0x18001d31d  mov     eax, ebx
0x18001d31f  add     rsp, 88h
0x18001d326  pop     rdi
0x18001d327  pop     rsi
0x18001d328  pop     rbx
0x18001d329  pop     rbp
0x18001d32a  retn
```
