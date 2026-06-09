# Sm::IsClustered(wchar_t *)

- ea: `0x180167750`
- end: `0x180167a3f`
- name: `?IsClustered@Sm@@SAHPEA_W@Z`
- size: `751`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801684e0`

## callees

- `0x1800013e0`
- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180156400`
- `0x180167750`
- `0x1801a65e1`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x180167834`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x180167834`
- `ADVAPI32!RegOpenKeyExW` at `0x1801678ac`
- `ADVAPI32!RegOpenKeyExW` at `0x1801678ac`
- `ADVAPI32!RegCloseKey` at `0x1801678bb`
- `ADVAPI32!RegCloseKey` at `0x1801678bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BOOL8 __fastcall Sm::IsClustered(wchar_t *String2, __int64 a2, __int64 a3, __int64 a4)
{
  BOOL v5; // ebx
  __int64 v6; // rcx
  struct localeinfo_struct *v7; // rax
  __int64 v8; // rcx
  struct __crt_locale_pointers *v9; // rax
  int v10; // eax
  struct __crt_locale_pointers *v11; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v17[5]; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+A0h] [rbp-60h]
  WCHAR SubKey; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v20[772]; // [rsp+B2h] [rbp-4Eh] BYREF
  __int16 v21; // [rsp+3B6h] [rbp+2B6h]
  _BYTE v22[512]; // [rsp+3C0h] [rbp+2C0h] BYREF

  v16 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266A70[0] )
    bidScopeEnterW(&v16, off_180266A70[0], String2, a4);
  v5 = 0;
  if ( qword_1802539E0 )
  {
    v14 = 255;
    memset(v17, 0, sizeof(v17));
    v18 = 0;
    if ( (*((unsigned int (__fastcall **)(wchar_t *, _QWORD, _OWORD *))qword_1802539E0 + 1))(String2, 0, v17) )
      v5 = (*((__int64 (__fastcall **)(_OWORD *, const wchar_t *, const wchar_t *, _BYTE *, int *))qword_1802539E0 + 2))(
             v17,
             L"Cluster",
             L"ClusterName",
             v22,
             &v14) != 0;
  }
  else
  {
    v15 = -1;
    if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266A68[0] )
      bidScopeEnterW(&v15, off_180266A68[0], String2, a4);
    SubKey = 0;
    memset_0(v20, 0, 0x306u);
    v21 = 0;
    v7 = (struct localeinfo_struct *)ImplBidTouch(v6);
    if ( _wcsicmp_l(L"MSSQLSERVER", String2, v7) )
    {
      v11 = (struct __crt_locale_pointers *)ImplBidTouch(v8);
      v10 = StringCchPrintf_lW(&SubKey, 0x184u, L"SOFTWARE\\Microsoft\\Microsoft SQL Server\\%s\\Cluster", v11, String2);
    }
    else
    {
      v9 = (struct __crt_locale_pointers *)ImplBidTouch(v8);
      v10 = StringCchPrintf_lW(&SubKey, 0x184u, L"SOFTWARE\\Microsoft\\MSSQLServer\\Cluster", v9);
    }
    if ( v10 < 0 || (hKey = 0, RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 1u, &hKey)) )
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264900[0] )
        bidTraceW(off_1802615B8[0], 376832, off_180264900[0], 0);
      _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v15);
    }
    else
    {
      RegCloseKey(hKey);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802648F8[0] )
        bidTraceW(off_1802615B0[0], 370688, off_1802648F8[0], 1);
      _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v15);
      v5 = 1;
    }
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264908[0] )
    bidTraceW(off_1802615C0[0], 431104, off_180264908[0], v5);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v16);
  return v5;
}

```

## disassembly

```asm
0x180167750  mov     [rsp-8+arg_8], rbx
0x180167755  mov     [rsp-8+arg_10], rdi
0x18016775a  push    rbp
0x18016775b  lea     rbp, [rsp-4D0h]
0x180167763  sub     rsp, 5D0h
0x18016776a  mov     rax, cs:__security_cookie
0x180167771  xor     rax, rsp
0x180167774  mov     [rbp+4D0h+var_10], rax
0x18016777b  mov     rdi, rcx
0x18016777e  mov     [rsp+5D0h+var_588], 0FFFFFFFFFFFFFFFFh
0x180167787  mov     eax, cs:_bidGblFlags
0x18016778d  and     eax, 20004h
0x180167792  cmp     eax, 20004h
0x180167797  jnz     short loc_1801677B9
0x180167799  mov     rax, cs:off_180266A70; "<Sm::IsClustered|API|SNI> szInstance: "...
0x1801677a0  test    rax, rax
0x1801677a3  jz      short loc_1801677B9
0x1801677a5  mov     r8, rcx
0x1801677a8  mov     rdx, cs:off_180266A70; "<Sm::IsClustered|API|SNI> szInstance: "...
0x1801677af  lea     rcx, [rsp+5D0h+var_588]
0x1801677b4  call    _bidScopeEnterW
0x1801677b9  xor     ebx, ebx
0x1801677bb  mov     rax, cs:qword_1802539E0
0x1801677c2  test    rax, rax
0x1801677c5  jnz     loc_180167956
0x1801677cb  mov     [rsp+5D0h+var_590], 0FFFFFFFFFFFFFFFFh
0x1801677d4  mov     eax, cs:_bidGblFlags
0x1801677da  and     eax, 20004h
0x1801677df  cmp     eax, 20004h
0x1801677e4  jnz     short loc_180167806
0x1801677e6  mov     rax, cs:off_180266A68; "<Sm::IsShilohClustered|API|SNI> szInsta"...
0x1801677ed  test    rax, rax
0x1801677f0  jz      short loc_180167806
0x1801677f2  mov     r8, rdi
0x1801677f5  mov     rdx, cs:off_180266A68; "<Sm::IsShilohClustered|API|SNI> szInsta"...
0x1801677fc  lea     rcx, [rsp+5D0h+var_590]
0x180167801  call    _bidScopeEnterW
0x180167806  mov     [rbp+4D0h+SubKey], bx
0x18016780a  xor     edx, edx; Val
0x18016780c  mov     r8d, 306h; Size
0x180167812  lea     rcx, [rbp+4D0h+var_51E]; void *
0x180167816  call    memset_0
0x18016781b  mov     [rbp+4D0h+var_21A], bx
0x180167822  call    ImplBidTouch
0x180167827  mov     r8, rax; Locale
0x18016782a  mov     rdx, rdi; String2
0x18016782d  lea     rcx, aMssqlserver; "MSSQLSERVER"
0x180167834  call    cs:__imp__wcsicmp_l
0x18016783a  test    eax, eax
0x18016783c  jnz     short loc_18016785D
0x18016783e  call    ImplBidTouch
0x180167843  mov     r9, rax; struct __crt_locale_pointers *
0x180167846  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\MSSQLServer\\Clust"...
0x18016784d  mov     edx, 184h; unsigned __int64
0x180167852  lea     rcx, [rbp+4D0h+SubKey]; Buffer
0x180167856  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x18016785b  jmp     short loc_18016787F
0x18016785d  call    ImplBidTouch
0x180167862  mov     r9, rax; struct __crt_locale_pointers *
0x180167865  mov     [rsp+5D0h+phkResult], rdi
0x18016786a  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Microsoft SQL Serv"...
0x180167871  mov     edx, 184h; unsigned __int64
0x180167876  lea     rcx, [rbp+4D0h+SubKey]; Buffer
0x18016787a  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x18016787f  test    eax, eax
0x180167881  js      loc_18016790D
0x180167887  mov     [rsp+5D0h+hKey], rbx
0x18016788c  lea     rax, [rsp+5D0h+hKey]
0x180167891  mov     [rsp+5D0h+phkResult], rax; phkResult
0x180167896  mov     edi, 1
0x18016789b  mov     r9d, edi; samDesired
0x18016789e  xor     r8d, r8d; ulOptions
0x1801678a1  lea     rdx, [rbp+4D0h+SubKey]; lpSubKey
0x1801678a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801678ac  call    cs:__imp_RegOpenKeyExW
0x1801678b2  test    eax, eax
0x1801678b4  jnz     short loc_18016790D
0x1801678b6  mov     rcx, [rsp+5D0h+hKey]; hKey
0x1801678bb  call    cs:__imp_RegCloseKey
0x1801678c1  mov     eax, cs:_bidGblFlags
0x1801678c7  and     eax, 20002h
0x1801678cc  cmp     eax, 20002h
0x1801678d1  jnz     short loc_1801678FB
0x1801678d3  mov     rax, cs:off_1802648F8; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x1801678da  test    rax, rax
0x1801678dd  jz      short loc_1801678FB
0x1801678df  mov     r9d, edi
0x1801678e2  mov     r8, cs:off_1802648F8; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x1801678e9  mov     edx, 5A800h
0x1801678ee  mov     rcx, cs:off_1802615B0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801678f5  call    _bidTraceW
0x1801678fa  nop
0x1801678fb  lea     rcx, [rsp+5D0h+var_590]; this
0x180167900  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180167905  nop
0x180167906  mov     ebx, edi
0x180167908  jmp     loc_1801679D4
0x18016790d  mov     eax, cs:_bidGblFlags
0x180167913  and     eax, 20002h
0x180167918  cmp     eax, 20002h
0x18016791d  jnz     short loc_180167947
0x18016791f  mov     rax, cs:off_180264900; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x180167926  test    rax, rax
0x180167929  jz      short loc_180167947
0x18016792b  xor     r9d, r9d
0x18016792e  mov     r8, cs:off_180264900; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x180167935  mov     edx, 5C000h
0x18016793a  mov     rcx, cs:off_1802615B8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167941  call    _bidTraceW
0x180167946  nop
0x180167947  lea     rcx, [rsp+5D0h+var_590]; this
0x18016794c  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180167951  nop
0x180167952  mov     edi, ebx
0x180167954  jmp     short loc_1801679D4
0x180167956  mov     [rsp+5D0h+var_598], 0FFh
0x18016795e  xorps   xmm0, xmm0
0x180167961  xor     ecx, ecx
0x180167963  movups  [rsp+5D0h+var_580], xmm0
0x180167968  movups  [rsp+5D0h+var_570], xmm0
0x18016796d  movups  [rsp+5D0h+var_560], xmm0
0x180167972  movups  [rbp+4D0h+var_550], xmm0
0x180167976  movups  [rbp+4D0h+var_540], xmm0
0x18016797a  mov     [rbp+4D0h+var_530], ecx
0x18016797d  lea     r8, [rsp+5D0h+var_580]
0x180167982  xor     edx, edx
0x180167984  mov     rcx, rdi
0x180167987  mov     rax, [rax+8]
0x18016798b  call    cs:__guard_dispatch_icall_fptr
0x180167991  test    eax, eax
0x180167993  jz      short loc_1801679D4
0x180167995  mov     rax, cs:qword_1802539E0
0x18016799c  lea     rcx, [rsp+5D0h+var_598]
0x1801679a1  mov     [rsp+5D0h+phkResult], rcx
0x1801679a6  lea     r9, [rbp+4D0h+var_210]
0x1801679ad  lea     r8, aClustername; "ClusterName"
0x1801679b4  lea     rdx, aCluster; "Cluster"
0x1801679bb  lea     rcx, [rsp+5D0h+var_580]
0x1801679c0  mov     rax, [rax+10h]
0x1801679c4  call    cs:__guard_dispatch_icall_fptr
0x1801679ca  mov     edi, 1
0x1801679cf  test    eax, eax
0x1801679d1  cmovnz  ebx, edi
0x1801679d4  mov     eax, cs:_bidGblFlags
0x1801679da  and     eax, 20002h
0x1801679df  cmp     eax, 20002h
0x1801679e4  jnz     short loc_180167A0E
0x1801679e6  mov     rax, cs:off_180264908; "<Sm::IsClustered|RET|SNI> %d{BOOL}\n"
0x1801679ed  test    rax, rax
0x1801679f0  jz      short loc_180167A0E
0x1801679f2  mov     r9d, ebx
0x1801679f5  mov     r8, cs:off_180264908; "<Sm::IsClustered|RET|SNI> %d{BOOL}\n"
0x1801679fc  mov     edx, 69400h
0x180167a01  mov     rcx, cs:off_1802615C0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180167a08  call    _bidTraceW
0x180167a0d  nop
0x180167a0e  lea     rcx, [rsp+5D0h+var_588]; this
0x180167a13  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180167a18  nop
0x180167a19  mov     eax, ebx
0x180167a1b  mov     rcx, [rbp+4D0h+var_10]
0x180167a22  xor     rcx, rsp; StackCookie
0x180167a25  call    __security_check_cookie
0x180167a2a  lea     r11, [rsp+5D0h+var_s0]
0x180167a32  mov     rbx, [r11+18h]
0x180167a36  mov     rdi, [r11+20h]
0x180167a3a  mov     rsp, r11
0x180167a3d  pop     rbp
0x180167a3e  retn
```
