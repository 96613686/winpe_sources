# CFilterMapper2::UnregisterFilter(_GUID)

- ea: `0x180068510`
- end: `0x1800686a4`
- name: `?UnregisterFilter@CFilterMapper2@@EEAAJU_GUID@@@Z`
- size: `404`
- prototype: `int(CFilterMapper2 *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004924`
- `0x1800388a0`
- `0x180058e08`
- `0x18005992c`
- `0x180065b20`
- `0x180068510`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180068673`
- `KERNEL32!LeaveCriticalSection` at `0x180068673`
- `KERNEL32!EnterCriticalSection` at `0x18006856f`
- `KERNEL32!EnterCriticalSection` at `0x18006856f`
- `ADVAPI32!RegDeleteValueW` at `0x180068634`
- `ADVAPI32!RegDeleteValueW` at `0x180068634`
- `ADVAPI32!RegOpenKeyExW` at `0x180068618`
- `ADVAPI32!RegOpenKeyExW` at `0x180068618`
- `ADVAPI32!RegCloseKey` at `0x180068645`
- `ADVAPI32!RegCloseKey` at `0x180068645`
- `ole32!StringFromGUID2` at `0x18006854c`
- `ole32!StringFromGUID2` at `0x18006854c`

## string_xrefs

- `0x1800685d9`: `CLSID`

## pseudocode

```c
__int64 __fastcall CFilterMapper2::UnregisterFilter(CFilterMapper2 *this, struct _GUID *a2)
{
  char *v4; // rdi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  CFilterMapper2 *v6; // rcx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  StringFromGUID2(a2, sz, 39);
  v4 = (char *)this - 8;
  v5 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 40) & -(__int64)(this != (CFilterMapper2 *)8));
  EnterCriticalSection(v5);
  CFilterMapper2::BreakCacheIfNotBuildingCache(v6);
  (*(void (__fastcall **)(char *, _QWORD, _QWORD, struct _GUID *))(*(_QWORD *)v4 + 32LL))(v4, 0, 0, a2);
  StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls", L"Filter", sz);
  EliminateSubKey(0xFFFFFFFF80000000uLL, SubKey);
  StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls", L"CLSID", sz);
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2000000u, &hKey) )
  {
    RegDeleteValueW(hKey, L"Merit");
    RegCloseKey(hKey);
  }
  StringCchCatW(SubKey, 0x104u, L"\\Pins");
  EliminateSubKey(0xFFFFFFFF80000000uLL, SubKey);
  LeaveCriticalSection(v5);
  return 0;
}

```

## disassembly

```asm
0x180068510  mov     [rsp-8+arg_10], rbx
0x180068515  push    rbp
0x180068516  push    rsi
0x180068517  push    rdi
0x180068518  lea     rbp, [rsp-1B0h]
0x180068520  sub     rsp, 2B0h
0x180068527  mov     rax, cs:__security_cookie
0x18006852e  xor     rax, rsp
0x180068531  mov     [rbp+1C0h+var_20], rax
0x180068538  mov     rsi, rdx
0x18006853b  mov     rbx, rcx
0x18006853e  mov     rcx, rsi; rguid
0x180068541  lea     rdx, [rsp+2C0h+sz]; lpsz
0x180068546  mov     r8d, 27h ; '''; cchMax
0x18006854c  call    cs:__imp_StringFromGUID2
0x180068553  nop     dword ptr [rax+rax+00h]
0x180068558  lea     rdi, [rbx-8]
0x18006855c  lea     rdx, [rbx+28h]
0x180068560  mov     rax, rdi
0x180068563  neg     rax
0x180068566  sbb     rbx, rbx
0x180068569  and     rbx, rdx
0x18006856c  mov     rcx, rbx; lpCriticalSection
0x18006856f  call    cs:__imp_EnterCriticalSection
0x180068576  nop     dword ptr [rax+rax+00h]
0x18006857b  call    ?BreakCacheIfNotBuildingCache@CFilterMapper2@@AEAAXXZ; CFilterMapper2::BreakCacheIfNotBuildingCache(void)
0x180068580  mov     rax, [rdi]
0x180068583  mov     r9, rsi
0x180068586  xor     r8d, r8d
0x180068589  xor     edx, edx
0x18006858b  mov     rcx, rdi
0x18006858e  mov     rax, [rax+20h]
0x180068592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068597  lea     rax, [rsp+2C0h+sz]
0x18006859c  mov     edi, 104h
0x1800685a1  mov     edx, edi; unsigned __int64
0x1800685a3  mov     [rsp+2C0h+phkResult], rax
0x1800685a8  lea     r9, aFilter; "Filter"
0x1800685af  lea     r8, aLsLs_0; "%ls\\%ls"
0x1800685b6  lea     rcx, [rbp+1C0h+SubKey]; Buffer
0x1800685ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800685bf  mov     rsi, 0FFFFFFFF80000000h
0x1800685c6  lea     rdx, [rbp+1C0h+SubKey]
0x1800685ca  mov     rcx, rsi
0x1800685cd  call    EliminateSubKey
0x1800685d2  lea     rax, [rsp+2C0h+sz]
0x1800685d7  mov     edx, edi; unsigned __int64
0x1800685d9  lea     r9, aClsid_0; "CLSID"
0x1800685e0  mov     [rsp+2C0h+phkResult], rax
0x1800685e5  lea     r8, aLsLs_0; "%ls\\%ls"
0x1800685ec  lea     rcx, [rbp+1C0h+SubKey]; Buffer
0x1800685f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800685f5  lea     rax, [rsp+2C0h+hKey]
0x1800685fa  mov     [rsp+2C0h+hKey], 0
0x180068603  mov     r9d, 2000000h; samDesired
0x180068609  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18006860e  xor     r8d, r8d; ulOptions
0x180068611  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x180068615  mov     rcx, rsi; hKey
0x180068618  call    cs:__imp_RegOpenKeyExW
0x18006861f  nop     dword ptr [rax+rax+00h]
0x180068624  test    eax, eax
0x180068626  jnz     short loc_180068651
0x180068628  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18006862d  lea     rdx, aMerit; "Merit"
0x180068634  call    cs:__imp_RegDeleteValueW
0x18006863b  nop     dword ptr [rax+rax+00h]
0x180068640  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180068645  call    cs:__imp_RegCloseKey
0x18006864c  nop     dword ptr [rax+rax+00h]
0x180068651  lea     r8, aPins; "\\Pins"
0x180068658  mov     rdx, rdi; unsigned __int64
0x18006865b  lea     rcx, [rbp+1C0h+SubKey]; unsigned __int16 *
0x18006865f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180068664  lea     rdx, [rbp+1C0h+SubKey]
0x180068668  mov     rcx, rsi
0x18006866b  call    EliminateSubKey
0x180068670  mov     rcx, rbx; lpCriticalSection
0x180068673  call    cs:__imp_LeaveCriticalSection
0x18006867a  nop     dword ptr [rax+rax+00h]
0x18006867f  xor     eax, eax
0x180068681  mov     rcx, [rbp+1C0h+var_20]
0x180068688  xor     rcx, rsp; StackCookie
0x18006868b  call    __security_check_cookie
0x180068690  mov     rbx, [rsp+2C0h+arg_10]
0x180068698  add     rsp, 2B0h
0x18006869f  pop     rdi
0x1800686a0  pop     rsi
0x1800686a1  pop     rbp
0x1800686a2  retn
```
