# KerbRefreshHostToRealmTable(void *)

- ea: `0x180094410`
- end: `0x1800946ae`
- name: `?KerbRefreshHostToRealmTable@@YAKPEAX@Z`
- size: `670`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007e200`

## callees

- `0x180070680`
- `0x18007108c`
- `0x18008b70c`
- `0x180093acc`
- `0x180093e38`
- `0x1800943ac`
- `0x180094410`
- `0x180094704`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800945bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094652`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094662`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800945bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094652`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094662`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800944ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094543`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094573`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800944ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094543`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094573`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800945f4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800945f4`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180094483`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180094483`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18009467f`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18009467f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180094672`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180094672`
- `ntdll!RtlReleaseResource` at `0x180094632`
- `ntdll!RtlReleaseResource` at `0x180094632`
- `ntdll!RtlAcquireResourceExclusive` at `0x18009451c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18009451c`

## pseudocode

```c
PVOID __fastcall KerbRefreshHostToRealmTable(void *a1)
{
  LSTATUS v1; // eax
  DWORD v2; // ebx
  DWORD i; // edx
  LSTATUS v4; // eax
  PVOID result; // rax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v7; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  struct _RTL_AVL_TABLE Table; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[512]; // [rsp+D0h] [rbp-30h] BYREF

  cchName = 512;
  hKey = 0;
  v7 = 0;
  phkResult = 0;
  memset_0(&Table, 0, sizeof(Table));
  RtlInitializeGenericTableAvl(
    &Table,
    KerbTableStringComparisonRoutine,
    (PRTL_AVL_ALLOCATE_ROUTINE)AuthenAllocate,
    (PRTL_AVL_FREE_ROUTINE)AuthenFree,
    0);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kerberos\\domain_realm",
         0,
         0x20019u,
         &phkResult);
  if ( v1 )
  {
    if ( v1 == 2 )
    {
      KerbPurgeHostToRealmTable();
      RtlAcquireResourceExclusive(&HostToRealmLock, 1u);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Control\\Lsa\\Kerberos\\HostToRealm",
              0,
              0x20019u,
              &hKey) )
      {
        v2 = 0;
        for ( i = 0; ; i = v2 )
        {
          cchName = 512;
          v4 = RegEnumKeyExW(hKey, i, SubKey, &cchName, 0, 0, 0, 0);
          if ( v4 )
            break;
          if ( RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &v7) )
            goto LABEL_17;
          if ( !KerbAddHostToRealmMapping(v7, SubKey) )
            KerbTracerT::Log(1, "KerbRefreshHostToRealmTable", 982, "KerbAddHostToRealmMapping failed!\n");
          if ( v7 )
          {
            RegCloseKey(v7);
            v7 = 0;
          }
          ++v2;
        }
        if ( v4 != 259 )
          KerbTracerT::Log(1, "KerbRefreshHostToRealmTable", 958, "RegEnumKeyExW failed - %x\n", v4);
      }
LABEL_17:
      RtlReleaseResource(&HostToRealmLock);
    }
    else
    {
      KerbTracerT::Log(
        1,
        "KerbRefreshHostToRealmTable",
        912,
        "KerbRefreshHostToRealmTable failed to query value %ws, %d\n",
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kerberos\\domain_realm",
        v1);
    }
  }
  else if ( !KerbBuildHostToRealmTableFromPolicy(phkResult, &Table) )
  {
    KerbUpdateRealmTable(&Table);
  }
  if ( v7 )
    RegCloseKey(v7);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  while ( 1 )
  {
    result = RtlEnumerateGenericTableAvl(&Table, 1u);
    if ( !result )
      break;
    RtlDeleteElementGenericTableAvl(&Table, result);
  }
  return result;
}

```

## disassembly

```asm
0x180094410  mov     [rsp-8+arg_0], rbx
0x180094415  mov     [rsp-8+arg_8], rdi
0x18009441a  push    rbp
0x18009441b  lea     rbp, [rsp-3E0h]
0x180094423  sub     rsp, 4E0h
0x18009442a  mov     rax, cs:__security_cookie
0x180094431  xor     rax, rsp
0x180094434  mov     [rbp+3E0h+var_10], rax
0x18009443b  xor     edi, edi
0x18009443d  mov     [rsp+4E0h+cchName], 200h
0x180094445  xor     edx, edx; Val
0x180094447  mov     [rsp+4E0h+hKey], rdi
0x18009444c  lea     rcx, [rsp+4E0h+Table]; void *
0x180094451  mov     [rsp+4E0h+var_498], rdi
0x180094456  mov     [rsp+4E0h+phkResult], rdi
0x18009445b  lea     r8d, [rdi+68h]; Size
0x18009445f  call    memset_0
0x180094464  lea     r9, ?AuthenFree@@YAXPEAU_RTL_GENERIC_TABLE@@PEAX@Z; FreeRoutine
0x18009446b  mov     [rsp+4E0h+TableContext], rdi; TableContext
0x180094470  lea     r8, ?AuthenAllocate@@YAPEAXPEAU_RTL_GENERIC_TABLE@@K@Z; AllocateRoutine
0x180094477  lea     rdx, ?KerbTableStringComparisonRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18009447e  lea     rcx, [rsp+4E0h+Table]; Table
0x180094483  call    cs:__imp_RtlInitializeGenericTableAvl
0x180094489  lea     rax, [rsp+4E0h+phkResult]
0x18009448e  mov     r9d, 20019h; samDesired
0x180094494  lea     rbx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009449b  mov     [rsp+4E0h+TableContext], rax; phkResult
0x1800944a0  mov     rdx, rbx; lpSubKey
0x1800944a3  xor     r8d, r8d; ulOptions
0x1800944a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800944ad  call    cs:__imp_RegOpenKeyExW
0x1800944b3  test    eax, eax
0x1800944b5  jnz     short loc_1800944DD
0x1800944b7  mov     rcx, [rsp+4E0h+phkResult]; hKey
0x1800944bc  lea     rdx, [rsp+4E0h+Table]; struct _RTL_AVL_TABLE *
0x1800944c1  call    ?KerbBuildHostToRealmTableFromPolicy@@YAKPEAUHKEY__@@PEAU_RTL_AVL_TABLE@@@Z; KerbBuildHostToRealmTableFromPolicy(HKEY__ *,_RTL_AVL_TABLE *)
0x1800944c6  test    eax, eax
0x1800944c8  jnz     loc_180094638
0x1800944ce  lea     rcx, [rsp+4E0h+Table]; Table
0x1800944d3  call    ?KerbUpdateRealmTable@@YAXPEAU_RTL_AVL_TABLE@@@Z; KerbUpdateRealmTable(_RTL_AVL_TABLE *)
0x1800944d8  jmp     loc_180094638
0x1800944dd  cmp     eax, 2
0x1800944e0  jz      short loc_18009450E
0x1800944e2  mov     dword ptr [rsp+4E0h+lpClass], eax
0x1800944e6  lea     r9, aKerbrefreshhos_0; "KerbRefreshHostToRealmTable failed to q"...
0x1800944ed  mov     r8d, 390h
0x1800944f3  mov     [rsp+4E0h+TableContext], rbx
0x1800944f8  lea     rdx, aKerbrefreshhos; "KerbRefreshHostToRealmTable"
0x1800944ff  mov     ecx, 1
0x180094504  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180094509  jmp     loc_180094638
0x18009450e  call    ?KerbPurgeHostToRealmTable@@YAXXZ; KerbPurgeHostToRealmTable(void)
0x180094513  mov     dl, 1; Wait
0x180094515  lea     rcx, ?HostToRealmLock@@3U_RTL_RESOURCE@@A; Resource
0x18009451c  call    cs:__imp_RtlAcquireResourceExclusive
0x180094522  lea     rax, [rsp+4E0h+hKey]
0x180094527  mov     r9d, 20019h; samDesired
0x18009452d  xor     r8d, r8d; ulOptions
0x180094530  mov     [rsp+4E0h+TableContext], rax; phkResult
0x180094535  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Control\\Lsa"...
0x18009453c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180094543  call    cs:__imp_RegOpenKeyExW
0x180094549  test    eax, eax
0x18009454b  jnz     loc_18009462B
0x180094551  mov     ebx, edi
0x180094553  xor     edx, edx
0x180094555  jmp     short loc_1800945CA
0x180094557  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18009455c  lea     rax, [rsp+4E0h+var_498]
0x180094561  mov     r9d, 20019h; samDesired
0x180094567  mov     [rsp+4E0h+TableContext], rax; phkResult
0x18009456c  xor     r8d, r8d; ulOptions
0x18009456f  lea     rdx, [rbp+3E0h+SubKey]; lpSubKey
0x180094573  call    cs:__imp_RegOpenKeyExW
0x180094579  test    eax, eax
0x18009457b  jnz     loc_18009462B
0x180094581  mov     rcx, [rsp+4E0h+var_498]; hKey
0x180094586  lea     rdx, [rbp+3E0h+SubKey]; unsigned __int16 *
0x18009458a  call    ?KerbAddHostToRealmMapping@@YAEPEAUHKEY__@@PEAG@Z; KerbAddHostToRealmMapping(HKEY__ *,ushort *)
0x18009458f  test    al, al
0x180094591  jnz     short loc_1800945B1
0x180094593  lea     r9, aKerbaddhosttor_0; "KerbAddHostToRealmMapping failed!\n"
0x18009459a  mov     r8d, 3D6h
0x1800945a0  lea     rdx, aKerbrefreshhos; "KerbRefreshHostToRealmTable"
0x1800945a7  mov     ecx, 1
0x1800945ac  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800945b1  mov     rcx, [rsp+4E0h+var_498]; hKey
0x1800945b6  test    rcx, rcx
0x1800945b9  jz      short loc_1800945C6
0x1800945bb  call    cs:__imp_RegCloseKey
0x1800945c1  mov     [rsp+4E0h+var_498], rdi
0x1800945c6  inc     ebx
0x1800945c8  mov     edx, ebx; dwIndex
0x1800945ca  mov     rcx, [rsp+4E0h+hKey]; hKey
0x1800945cf  lea     r9, [rsp+4E0h+cchName]; lpcchName
0x1800945d4  mov     [rsp+4E0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800945d9  lea     r8, [rbp+3E0h+SubKey]; lpName
0x1800945dd  mov     [rsp+4E0h+lpcchClass], rdi; lpcchClass
0x1800945e2  mov     [rsp+4E0h+lpClass], rdi; lpClass
0x1800945e7  mov     [rsp+4E0h+TableContext], rdi; lpReserved
0x1800945ec  mov     [rsp+4E0h+cchName], 200h
0x1800945f4  call    cs:__imp_RegEnumKeyExW
0x1800945fa  test    eax, eax
0x1800945fc  jz      loc_180094557
0x180094602  cmp     eax, 103h
0x180094607  jz      short loc_18009462B
0x180094609  lea     r9, aRegenumkeyexwF; "RegEnumKeyExW failed - %x\n"
0x180094610  mov     dword ptr [rsp+4E0h+TableContext], eax
0x180094614  mov     r8d, 3BEh
0x18009461a  lea     rdx, aKerbrefreshhos; "KerbRefreshHostToRealmTable"
0x180094621  mov     ecx, 1
0x180094626  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009462b  lea     rcx, ?HostToRealmLock@@3U_RTL_RESOURCE@@A; Resource
0x180094632  call    cs:__imp_RtlReleaseResource
0x180094638  mov     rcx, [rsp+4E0h+var_498]; hKey
0x18009463d  test    rcx, rcx
0x180094640  jz      short loc_180094648
0x180094642  call    cs:__imp_RegCloseKey
0x180094648  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18009464d  test    rcx, rcx
0x180094650  jz      short loc_180094658
0x180094652  call    cs:__imp_RegCloseKey
0x180094658  mov     rcx, [rsp+4E0h+phkResult]; hKey
0x18009465d  test    rcx, rcx
0x180094660  jz      short loc_180094678
0x180094662  call    cs:__imp_RegCloseKey
0x180094668  jmp     short loc_180094678
0x18009466a  mov     rdx, rax; Buffer
0x18009466d  lea     rcx, [rsp+4E0h+Table]; Table
0x180094672  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180094678  mov     dl, 1; Restart
0x18009467a  lea     rcx, [rsp+4E0h+Table]; Table
0x18009467f  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180094685  test    rax, rax
0x180094688  jnz     short loc_18009466A
0x18009468a  mov     rcx, [rbp+3E0h+var_10]
0x180094691  xor     rcx, rsp; StackCookie
0x180094694  call    __security_check_cookie
0x180094699  lea     r11, [rsp+4E0h+var_s0]
0x1800946a1  mov     rbx, [r11+10h]
0x1800946a5  mov     rdi, [r11+18h]
0x1800946a9  mov     rsp, r11
0x1800946ac  pop     rbp
0x1800946ad  retn
```
