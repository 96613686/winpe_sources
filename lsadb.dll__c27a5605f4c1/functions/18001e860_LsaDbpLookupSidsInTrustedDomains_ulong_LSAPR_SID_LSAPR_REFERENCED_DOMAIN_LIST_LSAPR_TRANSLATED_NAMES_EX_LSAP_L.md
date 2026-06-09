# LsaDbpLookupSidsInTrustedDomains(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,long *)

- ea: `0x18001e860`
- end: `0x18001e95f`
- name: `?LsaDbpLookupSidsInTrustedDomains@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAJ@Z`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001db90`

## callees

- `0x18001b214`
- `0x18001b8dc`
- `0x18001b94c`
- `0x18001e860`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e8e4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e911`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e8e4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e911`
- `LSASRV!LsaLookupPerfCounterAddLargeAmount` at `0x18001e92a`
- `LSASRV!LsaLookupPerfCounterAddLargeAmount` at `0x18001e92a`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001e8d9`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001e938`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001e8d9`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001e938`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupSidsInTrustedDomains(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int *a8)
{
  int v8; // eax
  HLOCAL v9; // rdi
  unsigned int v10; // ebx
  unsigned __int8 v12; // [rsp+20h] [rbp-48h]
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-20h] BYREF
  LARGE_INTEGER v15; // [rsp+50h] [rbp-18h] BYREF

  hMem = 0;
  PerformanceCount.QuadPart = 0;
  v15.QuadPart = 0;
  *a8 = 0;
  v8 = LsaDbpLookupSidsBuildWorkList(a1, a2, a3, a4, v12, a6, a7, &hMem);
  v9 = hMem;
  v10 = v8;
  if ( v8 >= 0 )
  {
    LsaLookupPerfCounterAddAmount(0x28u, *((_DWORD *)hMem + 14));
    if ( !QueryPerformanceCounter(&PerformanceCount) )
      PerformanceCount.QuadPart = 0;
    v10 = LsaDbpLookupProcessWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST *)v9, a8);
    if ( PerformanceCount.QuadPart && QueryPerformanceCounter(&v15) )
    {
      LsaLookupPerfCounterAddLargeAmount(0x29u, v15.QuadPart - PerformanceCount.QuadPart);
      LsaLookupPerfCounterAddAmount(0x2Au, *((_DWORD *)v9 + 14));
    }
  }
  else if ( v8 == -1073741709 )
  {
    v10 = 0;
  }
  if ( v9 )
    return (unsigned int)LsaDbpLookupDeleteWorkList(v9);
  return v10;
}

```

## disassembly

```asm
0x18001e860  mov     r11, rsp
0x18001e863  mov     [r11+8], rbx
0x18001e867  mov     [r11+10h], rsi
0x18001e86b  push    rdi
0x18001e86c  sub     rsp, 60h
0x18001e870  mov     rsi, [rsp+68h+arg_38]
0x18001e878  lea     rax, [r11-20h]
0x18001e87c  mov     [r11-30h], rax
0x18001e880  mov     rax, [rsp+68h+arg_30]
0x18001e888  mov     [r11-38h], rax
0x18001e88c  mov     rax, [rsp+68h+arg_28]
0x18001e894  mov     [r11-40h], rax
0x18001e898  mov     qword ptr [r11-20h], 0
0x18001e8a0  mov     qword ptr [r11-28h], 0
0x18001e8a8  mov     qword ptr [r11-18h], 0
0x18001e8b0  mov     dword ptr [rsi], 0
0x18001e8b6  call    ?LsaDbpLookupSidsBuildWorkList@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupSidsBuildWorkList(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,_LSAP_DB_LOOKUP_WORK_LIST * *)
0x18001e8bb  mov     rdi, [rsp+68h+hMem]
0x18001e8c0  mov     ebx, eax
0x18001e8c2  test    eax, eax
0x18001e8c4  jns     short loc_18001E8D1
0x18001e8c6  cmp     eax, 0C0000073h
0x18001e8cb  jnz     short loc_18001E93E
0x18001e8cd  xor     ebx, ebx
0x18001e8cf  jmp     short loc_18001E93E
0x18001e8d1  mov     edx, [rdi+38h]
0x18001e8d4  mov     ecx, 28h ; '('
0x18001e8d9  call    cs:__imp_?LsaLookupPerfCounterAddAmount@@YAXKK@Z; LsaLookupPerfCounterAddAmount(ulong,ulong)
0x18001e8df  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x18001e8e4  call    cs:__imp_QueryPerformanceCounter
0x18001e8ea  test    eax, eax
0x18001e8ec  jnz     short loc_18001E8F7
0x18001e8ee  mov     qword ptr [rsp+68h+PerformanceCount], 0
0x18001e8f7  mov     rdx, rsi; int *
0x18001e8fa  mov     rcx, rdi; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001e8fd  call    ?LsaDbpLookupProcessWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAJ@Z; LsaDbpLookupProcessWorkList(_LSAP_DB_LOOKUP_WORK_LIST *,long *)
0x18001e902  cmp     qword ptr [rsp+68h+PerformanceCount], 0
0x18001e908  mov     ebx, eax
0x18001e90a  jz      short loc_18001E93E
0x18001e90c  lea     rcx, [rsp+68h+var_18]; lpPerformanceCount
0x18001e911  call    cs:__imp_QueryPerformanceCounter
0x18001e917  test    eax, eax
0x18001e919  jz      short loc_18001E93E
0x18001e91b  mov     rdx, qword ptr [rsp+68h+var_18]
0x18001e920  mov     ecx, 29h ; ')'
0x18001e925  sub     rdx, qword ptr [rsp+68h+PerformanceCount]
0x18001e92a  call    cs:__imp_?LsaLookupPerfCounterAddLargeAmount@@YAXK_K@Z; LsaLookupPerfCounterAddLargeAmount(ulong,unsigned __int64)
0x18001e930  mov     edx, [rdi+38h]
0x18001e933  mov     ecx, 2Ah ; '*'
0x18001e938  call    cs:__imp_?LsaLookupPerfCounterAddAmount@@YAXKK@Z; LsaLookupPerfCounterAddAmount(ulong,ulong)
0x18001e93e  test    rdi, rdi
0x18001e941  jz      short loc_18001E94D
0x18001e943  mov     rcx, rdi; hMem
0x18001e946  call    ?LsaDbpLookupDeleteWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupDeleteWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x18001e94b  mov     ebx, eax
0x18001e94d  mov     rsi, [rsp+68h+arg_8]
0x18001e952  mov     eax, ebx
0x18001e954  mov     rbx, [rsp+68h+arg_0]
0x18001e959  add     rsp, 60h
0x18001e95d  pop     rdi
0x18001e95e  retn
```
