# KerbInitHostToRealmTable(void)

- ea: `0x1800941c8`
- end: `0x1800943a4`
- name: `?KerbInitHostToRealmTable@@YAJXZ`
- size: `476`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b445c`

## callees

- `0x18008b70c`
- `0x1800941c8`
- `0x1800d505c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009434e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009434e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800942cc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800942cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800942d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094391`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800942d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094391`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094249`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094286`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094249`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094286`
- `ntdll!RtlInitializeResource` at `0x180094217`
- `ntdll!RtlInitializeResource` at `0x180094217`
- `ntdll!RtlDeleteResource` at `0x180094381`
- `ntdll!RtlDeleteResource` at `0x180094381`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180094209`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180094209`

## string_xrefs

- `0x1800942e7`: `Failed to create HotToRealm key: 0x%x\n`
- `0x180094310`: `Failed to open HostToRealm key: 0x%x\n`
- `0x180094358`: `Failed to create HostToRealm watcher: 0x%x\n`

## pseudocode

```c
__int64 KerbInitHostToRealmTable(void)
{
  LSTATUS v0; // eax
  LSTATUS v1; // edi
  unsigned int v2; // edi
  PVOID TableContext; // [rsp+20h] [rbp-38h]
  PVOID TableContexta; // [rsp+20h] [rbp-38h]
  PVOID TableContextb; // [rsp+20h] [rbp-38h]
  HKEY phkResult; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  phkResult = 0;
  hKey = 0;
  RtlInitializeGenericTableAvl(
    &HostToRealmTable,
    KerbTableStringComparisonRoutine,
    (PRTL_AVL_ALLOCATE_ROUTINE)AuthenAllocate,
    (PRTL_AVL_FREE_ROUTINE)AuthenFree,
    0);
  RtlInitializeResource(&HostToRealmLock);
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Lsa\\Kerberos\\HostToRealm",
         0,
         0x20019u,
         &phkResult);
  if ( !v0 )
    goto LABEL_9;
  if ( v0 != 2 )
  {
    LODWORD(TableContext) = v0;
    KerbTracerT::Log(2, "KerbInitHostToRealmTable", 764, "Failed to open HostToRealm key: 0x%x\n", TableContext);
    goto LABEL_7;
  }
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa\\Kerberos", 0, 4u, &hKey);
  if ( !v1 )
  {
    v1 = RegCreateKeyExW(hKey, L"HostToRealm", 0, 0, 0, 0x20019u, 0, &phkResult, 0);
    RegCloseKey(hKey);
  }
  if ( v1 )
  {
    LODWORD(TableContexta) = v1;
    KerbTracerT::Log(2, "KerbInitHostToRealmTable", 757, "Failed to create HotToRealm key: 0x%x\n", TableContexta);
  }
  else
  {
LABEL_9:
    v2 = 0;
    qword_180146728 = SspRegistry::RegistryWatcher::CreateCommon(
                        phkResult,
                        (unsigned int (*)(void *))KerbRefreshHostToRealmTable,
                        1,
                        0,
                        0,
                        0);
    if ( qword_180146728 )
      goto LABEL_14;
    LODWORD(TableContextb) = GetLastError();
    KerbTracerT::Log(2, "KerbInitHostToRealmTable", 774, "Failed to create HostToRealm watcher: 0x%x\n", TableContextb);
  }
LABEL_7:
  v2 = -1073741823;
  if ( &HostToRealmLock )
    RtlDeleteResource(&HostToRealmLock);
LABEL_14:
  if ( phkResult )
    RegCloseKey(phkResult);
  return v2;
}

```

## disassembly

```asm
0x1800941c8  mov     [rsp+arg_10], rsi
0x1800941cd  push    rdi
0x1800941ce  sub     rsp, 50h
0x1800941d2  mov     [rsp+58h+phkResult], 0
0x1800941db  mov     [rsp+58h+hKey], 0
0x1800941e4  mov     [rsp+58h+TableContext], 0; TableContext
0x1800941ed  lea     r9, ?AuthenFree@@YAXPEAU_RTL_GENERIC_TABLE@@PEAX@Z; FreeRoutine
0x1800941f4  lea     r8, ?AuthenAllocate@@YAPEAXPEAU_RTL_GENERIC_TABLE@@K@Z; AllocateRoutine
0x1800941fb  lea     rdx, ?KerbTableStringComparisonRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180094202  lea     rcx, ?HostToRealmTable@@3U_RTL_AVL_TABLE@@A; Table
0x180094209  call    cs:__imp_RtlInitializeGenericTableAvl
0x18009420f  nop
0x180094210  lea     rcx, ?HostToRealmLock@@3U_RTL_RESOURCE@@A; Resource
0x180094217  call    cs:__imp_RtlInitializeResource
0x18009421d  nop
0x18009421e  lea     rsi, ?HostToRealmLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE HostToRealmLock
0x180094225  lea     rax, [rsp+58h+phkResult]
0x18009422a  mov     [rsp+58h+TableContext], rax; phkResult
0x18009422f  mov     r9d, 20019h; samDesired
0x180094235  xor     r8d, r8d; ulOptions
0x180094238  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Control\\Lsa"...
0x18009423f  mov     rdi, 0FFFFFFFF80000002h
0x180094246  mov     rcx, rdi; hKey
0x180094249  call    cs:__imp_RegOpenKeyExW
0x18009424f  test    eax, eax
0x180094251  jz      loc_18009431F
0x180094257  cmp     eax, 2
0x18009425a  jnz     loc_18009430C
0x180094260  mov     [rsp+58h+hKey], 0
0x180094269  lea     rax, [rsp+58h+hKey]
0x18009426e  mov     [rsp+58h+TableContext], rax; phkResult
0x180094273  mov     r9d, 4; samDesired
0x180094279  xor     r8d, r8d; ulOptions
0x18009427c  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Lsa"...
0x180094283  mov     rcx, rdi; hKey
0x180094286  call    cs:__imp_RegOpenKeyExW
0x18009428c  mov     edi, eax
0x18009428e  test    eax, eax
0x180094290  jnz     short loc_1800942DF
0x180094292  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18009429b  lea     rax, [rsp+58h+phkResult]
0x1800942a0  mov     [rsp+58h+var_20], rax; phkResult
0x1800942a5  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800942ae  mov     [rsp+58h+samDesired], 20019h; samDesired
0x1800942b6  mov     dword ptr [rsp+58h+TableContext], edi; dwOptions
0x1800942ba  xor     r9d, r9d; lpClass
0x1800942bd  xor     r8d, r8d; Reserved
0x1800942c0  lea     rdx, aHosttorealm; "HostToRealm"
0x1800942c7  mov     rcx, [rsp+58h+hKey]; hKey
0x1800942cc  call    cs:__imp_RegCreateKeyExW
0x1800942d2  mov     edi, eax
0x1800942d4  mov     rcx, [rsp+58h+hKey]; hKey
0x1800942d9  call    cs:__imp_RegCloseKey
0x1800942df  test    edi, edi
0x1800942e1  jz      short loc_18009431F
0x1800942e3  mov     dword ptr [rsp+58h+TableContext], edi
0x1800942e7  lea     r9, aFailedToCreate_11; "Failed to create HotToRealm key: 0x%x\n"
0x1800942ee  mov     r8d, 2F5h
0x1800942f4  lea     rdx, aKerbinithostto; "KerbInitHostToRealmTable"
0x1800942fb  mov     ecx, 2
0x180094300  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180094305  mov     edi, 0C0000001h
0x18009430a  jmp     short loc_180094375
0x18009430c  mov     dword ptr [rsp+58h+TableContext], eax
0x180094310  lea     r9, aFailedToOpenHo; "Failed to open HostToRealm key: 0x%x\n"
0x180094317  mov     r8d, 2FCh
0x18009431d  jmp     short loc_1800942F4
0x18009431f  xor     edi, edi
0x180094321  mov     byte ptr [rsp+58h+samDesired], dil; bool
0x180094326  mov     byte ptr [rsp+58h+TableContext], dil; bool
0x18009432b  xor     r9d, r9d; void *
0x18009432e  mov     r8b, 1; bool
0x180094331  lea     rdx, ?KerbRefreshHostToRealmTable@@YAKPEAX@Z; unsigned int (*)(void *)
0x180094338  mov     rcx, [rsp+58h+phkResult]; hSourceHandle
0x18009433d  call    ?CreateCommon@RegistryWatcher@SspRegistry@@CAPEAV12@PEAUHKEY__@@P6AKPEAX@Z_N133@Z; SspRegistry::RegistryWatcher::CreateCommon(HKEY__ *,ulong (*)(void *),bool,void *,bool,bool)
0x180094342  mov     cs:qword_180146728, rax
0x180094349  test    rax, rax
0x18009434c  jnz     short loc_180094371
0x18009434e  call    cs:__imp_GetLastError
0x180094354  mov     dword ptr [rsp+58h+TableContext], eax
0x180094358  lea     r9, aFailedToCreate_40; "Failed to create HostToRealm watcher: 0"...
0x18009435f  mov     r8d, 306h
0x180094365  jmp     short loc_1800942F4
0x180094367  mov     edi, 0C000009Ah
0x18009436c  mov     rsi, [rsp+58h+hKey]
0x180094371  test    edi, edi
0x180094373  jns     short loc_180094387
0x180094375  test    rsi, rsi
0x180094378  jz      short loc_180094387
0x18009437a  lea     rcx, ?HostToRealmLock@@3U_RTL_RESOURCE@@A; Resource
0x180094381  call    cs:__imp_RtlDeleteResource
0x180094387  mov     rcx, [rsp+58h+phkResult]; hKey
0x18009438c  test    rcx, rcx
0x18009438f  jz      short loc_180094397
0x180094391  call    cs:__imp_RegCloseKey
0x180094397  mov     eax, edi
0x180094399  mov     rsi, [rsp+58h+arg_10]
0x18009439e  add     rsp, 50h
0x1800943a2  pop     rdi
0x1800943a3  retn
```
