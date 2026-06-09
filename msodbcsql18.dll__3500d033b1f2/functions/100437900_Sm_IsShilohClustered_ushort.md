# Sm::IsShilohClustered(ushort *)

- ea: `0x100437900`
- end: `0x100437abc`
- name: `?IsShilohClustered@Sm@@SAHPEAG@Z`
- size: `444`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1004377bc`

## callees

- `0x1004134a0`
- `0x1004165dc`
- `0x100437900`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100548140`
- `0x100548210`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x100437a04`
- `ADVAPI32!RegOpenKeyExW` at `0x100437a04`
- `ADVAPI32!RegCloseKey` at `0x100437a13`
- `ADVAPI32!RegCloseKey` at `0x100437a13`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100437992`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100437992`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Sm::IsShilohClustered(wchar_t *String2)
{
  __int64 v2; // rcx
  struct localeinfo_struct *v3; // rax
  __int64 v4; // rcx
  struct __crt_locale_pointers *v5; // rax
  int v6; // eax
  struct __crt_locale_pointers *v7; // rax
  __int64 v9; // [rsp+30h] [rbp-348h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-340h] BYREF
  WCHAR SubKey[392]; // [rsp+50h] [rbp-328h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v9 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7DA0[0] )
    bidScopeEnterW(&v9, off_1005E7DA0[0], String2);
  memset_0(SubKey, 0, 0x308u);
  SubKey[387] = 0;
  v3 = (struct localeinfo_struct *)ImplBidTouch(v2);
  if ( _wcsicmp_l(L"MSSQLSERVER", String2, v3) )
  {
    v7 = (struct __crt_locale_pointers *)ImplBidTouch(v4);
    v6 = StringCchPrintf_lW(SubKey, 0x184u, L"SOFTWARE\\Microsoft\\Microsoft SQL Server\\%s\\Cluster", v7, String2);
  }
  else
  {
    v5 = (struct __crt_locale_pointers *)ImplBidTouch(v4);
    v6 = StringCchPrintf_lW(SubKey, 0x184u, L"SOFTWARE\\Microsoft\\MSSQLServer\\Cluster", v5);
  }
  if ( v6 < 0 || RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, hKey) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5B10[0] )
      bidTraceW(0, 377856, off_1005E5B10[0], 0);
    _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v9);
    return 0;
  }
  else
  {
    RegCloseKey(hKey[0]);
    if ( (bidGblFlags & 0x20002) == 0x20002 )
    {
      if ( off_1005E5B08[0] )
        bidTraceW(0, 371712, off_1005E5B08[0], 1);
    }
    _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v9);
    return 1;
  }
}

```

## disassembly

```asm
0x100437900  mov     rax, rsp
0x100437903  push    rdi
0x100437904  sub     rsp, 370h
0x10043790b  mov     [rsp+378h+var_338], 0FFFFFFFFFFFFFFFEh
0x100437914  mov     [rax+10h], rbx
0x100437918  mov     rax, cs:__security_cookie
0x10043791f  xor     rax, rsp
0x100437922  mov     [rsp+378h+var_18], rax
0x10043792a  mov     rbx, rcx
0x10043792d  or      [rsp+378h+var_348], 0FFFFFFFFFFFFFFFFh
0x100437933  mov     eax, cs:_bidGblFlags
0x100437939  mov     ecx, 20004h
0x10043793e  and     eax, ecx
0x100437940  xor     edi, edi
0x100437942  cmp     eax, ecx
0x100437944  jnz     short loc_100437966
0x100437946  mov     rax, cs:off_1005E7DA0; "<Sm::IsShilohClustered|API|SNI> szInsta"...
0x10043794d  test    rax, rax
0x100437950  jz      short loc_100437966
0x100437952  mov     r8, rbx
0x100437955  mov     rdx, cs:off_1005E7DA0; "<Sm::IsShilohClustered|API|SNI> szInsta"...
0x10043795c  lea     rcx, [rsp+378h+var_348]
0x100437961  call    _bidScopeEnterW
0x100437966  xor     edx, edx; Val
0x100437968  mov     r8d, 308h; Size
0x10043796e  lea     rcx, [rsp+378h+SubKey]; void *
0x100437973  call    memset_0
0x100437978  mov     [rsp+378h+var_22], di
0x100437980  call    ImplBidTouch
0x100437985  mov     r8, rax; Locale
0x100437988  mov     rdx, rbx; String2
0x10043798b  lea     rcx, aMssqlserver_0; "MSSQLSERVER"
0x100437992  call    cs:__imp__wcsicmp_l
0x100437998  test    eax, eax
0x10043799a  jnz     short loc_1004379BC
0x10043799c  call    ImplBidTouch
0x1004379a1  mov     r9, rax; struct __crt_locale_pointers *
0x1004379a4  lea     r8, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\MSSQLServer\\Clust"...
0x1004379ab  mov     edx, 184h; unsigned __int64
0x1004379b0  lea     rcx, [rsp+378h+SubKey]; unsigned __int16 *
0x1004379b5  call    ?StringCchPrintf_lW@@YAJPEAG_KPEBGPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(ushort *,unsigned __int64,ushort const *,__crt_locale_pointers *,...)
0x1004379ba  jmp     short loc_1004379DF
0x1004379bc  call    ImplBidTouch
0x1004379c1  mov     r9, rax; struct __crt_locale_pointers *
0x1004379c4  mov     [rsp+378h+phkResult], rbx
0x1004379c9  lea     r8, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Microsoft SQL Serv"...
0x1004379d0  mov     edx, 184h; unsigned __int64
0x1004379d5  lea     rcx, [rsp+378h+SubKey]; unsigned __int16 *
0x1004379da  call    ?StringCchPrintf_lW@@YAJPEAG_KPEBGPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(ushort *,unsigned __int64,ushort const *,__crt_locale_pointers *,...)
0x1004379df  test    eax, eax
0x1004379e1  js      short loc_100437A5B
0x1004379e3  lea     rax, [rsp+378h+hKey]
0x1004379e8  mov     [rsp+378h+phkResult], rax; phkResult
0x1004379ed  mov     ebx, 1
0x1004379f2  mov     r9d, ebx; samDesired
0x1004379f5  xor     r8d, r8d; ulOptions
0x1004379f8  lea     rdx, [rsp+378h+SubKey]; lpSubKey
0x1004379fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x100437a04  call    cs:__imp_RegOpenKeyExW
0x100437a0a  test    eax, eax
0x100437a0c  jnz     short loc_100437A5B
0x100437a0e  mov     rcx, [rsp+378h+hKey]; hKey
0x100437a13  call    cs:__imp_RegCloseKey
0x100437a19  mov     eax, cs:_bidGblFlags
0x100437a1f  mov     ecx, 20002h
0x100437a24  and     eax, ecx
0x100437a26  cmp     eax, ecx
0x100437a28  jnz     short loc_100437A4D
0x100437a2a  mov     rcx, cs:off_1005E5B08; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x100437a31  test    rcx, rcx
0x100437a34  jz      short loc_100437A4D
0x100437a36  mov     r9d, ebx
0x100437a39  mov     r8, cs:off_1005E5B08; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x100437a40  mov     edx, 5AC00h
0x100437a45  xor     ecx, ecx
0x100437a47  call    _bidTraceW
0x100437a4c  nop
0x100437a4d  lea     rcx, [rsp+378h+var_348]; this
0x100437a52  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100437a57  mov     eax, ebx
0x100437a59  jmp     short loc_100437A9B
0x100437a5b  mov     eax, cs:_bidGblFlags
0x100437a61  mov     ecx, 20002h
0x100437a66  and     eax, ecx
0x100437a68  cmp     eax, ecx
0x100437a6a  jnz     short loc_100437A8F
0x100437a6c  mov     rax, cs:off_1005E5B10; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x100437a73  test    rax, rax
0x100437a76  jz      short loc_100437A8F
0x100437a78  xor     r9d, r9d
0x100437a7b  mov     r8, cs:off_1005E5B10; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x100437a82  mov     edx, 5C400h
0x100437a87  xor     ecx, ecx
0x100437a89  call    _bidTraceW
0x100437a8e  nop
0x100437a8f  lea     rcx, [rsp+378h+var_348]; this
0x100437a94  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100437a99  xor     eax, eax
0x100437a9b  mov     rcx, [rsp+378h+var_18]
0x100437aa3  xor     rcx, rsp; StackCookie
0x100437aa6  call    __security_check_cookie
0x100437aab  mov     rbx, [rsp+378h+arg_8]
0x100437ab3  add     rsp, 370h
0x100437aba  pop     rdi
0x100437abb  retn
```
