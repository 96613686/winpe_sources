# PlaliInitializeNewQuery(HKEY__ *,HKEY__ * &,ushort const *,ushort const *)

- ea: `0x180131208`
- end: `0x180131562`
- name: `?PlaliInitializeNewQuery@@YAJPEAUHKEY__@@AEAPEAU1@PEBG2@Z`
- size: `858`
- prototype: `__int64 __fastcall(HKEY hKey, PHKEY phkResult, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012ec18`

## callees

- `0x180015f98`
- `0x18012f320`
- `0x180130fb0`
- `0x180131208`
- `0x18013161c`
- `0x180133278`
- `0x1801333bc`
- `0x1801333f0`
- `0x18013aee0`

## import_xrefs

- `msvcrt!_wgetenv` at `0x1801314e5`
- `msvcrt!_wgetenv` at `0x1801314e5`
- `ntdll!RtlFreeUnicodeString` at `0x1801312f1`
- `ntdll!RtlFreeUnicodeString` at `0x1801312f1`
- `ntdll!RtlStringFromGUID` at `0x1801312ae`
- `ntdll!RtlStringFromGUID` at `0x1801312ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013133f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013133f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801312e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180131325`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801312e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180131325`
- `RPCRT4!UuidCreate` at `0x180131289`
- `RPCRT4!UuidCreate` at `0x180131289`

## string_xrefs

- `0x1801314bb`: `Comment`
- `0x18013141d`: `Create New File`

## pseudocode

```c
__int64 __fastcall PlaliInitializeNewQuery(
        HKEY hKey,
        PHKEY phkResult,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int Version; // edi
  RPC_STATUS v9; // eax
  LSTATUS v11; // edi
  unsigned int v12; // eax
  HKEY v13; // rcx
  HKEY v14; // rcx
  HKEY v15; // rcx
  HKEY v16; // rcx
  int v17; // eax
  HKEY v18; // rcx
  HKEY v19; // rcx
  HKEY v20; // rcx
  HKEY v21; // rcx
  HKEY v22; // rcx
  HKEY v23; // rcx
  HKEY v24; // rcx
  wchar_t *v25; // rax
  unsigned __int64 v26; // rcx
  const unsigned __int16 *p_Uuid; // r9
  unsigned int v28; // [rsp+50h] [rbp-39h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-35h] BYREF
  _UNICODE_STRING GuidString; // [rsp+58h] [rbp-31h] BYREF
  __int128 v31; // [rsp+68h] [rbp-21h] BYREF
  UUID Uuid; // [rsp+78h] [rbp-11h] BYREF

  dwDisposition = 0;
  v28 = 0;
  v31 = 0;
  GuidString = 0;
  Version = PlaliGetVersion(a3, (struct _PLALI_VERSION_ *)&GuidString);
  if ( Version )
    return Version;
  if ( LODWORD(GuidString.Buffer) <= 0x893 )
  {
    v11 = RegCreateKeyExW(hKey, a4, 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
  }
  else
  {
    Uuid = 0;
    GuidString = 0;
    v9 = UuidCreate(&Uuid);
    if ( v9 && v9 != 1824 )
      return PlaliErrorToPdhStatus(v9);
    v9 = RtlStringFromGUID(&Uuid, &GuidString);
    if ( v9 )
      return PlaliErrorToPdhStatus(v9);
    v11 = RegCreateKeyExW(hKey, GuidString.Buffer, 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
    RtlFreeUnicodeString(&GuidString);
  }
  v12 = PlaliErrorToPdhStatus(v11);
  Version = v12;
  if ( dwDisposition == 2 )
  {
    RegCloseKey(*phkResult);
    *phkResult = 0;
    return (unsigned int)-1073738770;
  }
  else
  {
    if ( v12 )
      return Version;
    PlaliWriteRegistryStringValue(*phkResult, L"Collection Name", 1u, a4, 0);
    v13 = *phkResult;
    v28 = 0;
    Version = PlaliWriteRegistryDwordValue(v13, L"Current State", &v28);
    if ( Version )
      return Version;
    v14 = *phkResult;
    v28 = -1;
    PlaliWriteRegistryDwordValue(v14, L"Log Type", &v28);
    PlaliWriteRegistryStringValue(*phkResult, L"Log File Base Name", 1u, a4, 0);
    v15 = *phkResult;
    *(_QWORD *)&v31 = 65537;
    *((_QWORD *)&v31 + 1) = 0x7FFFFFFFFFFFFFFFLL;
    PlaliWriteRegistryPlaTime(v15, L"Start", (struct _PLALI_TIME_INFO *)&v31);
    v16 = *phkResult;
    WORD1(v31) = 2;
    *((_QWORD *)&v31 + 1) = 0;
    v17 = PlaliWriteRegistryPlaTime(v16, L"Stop", (struct _PLALI_TIME_INFO *)&v31);
    v18 = *phkResult;
    v31 = 0;
    Version = v17;
    PlaliWriteRegistryPlaTime(v18, L"Create New File", (struct _PLALI_TIME_INFO *)&v31);
    v19 = *phkResult;
    v28 = 0;
    PlaliWriteRegistryDwordValue(v19, L"Restart", &v28);
    v20 = *phkResult;
    v28 = 0;
    PlaliWriteRegistryDwordValue(v20, L"Current State", &v28);
    v21 = *phkResult;
    v28 = -1;
    PlaliWriteRegistryDwordValue(v21, L"Log File Max Size", &v28);
    v22 = *phkResult;
    v28 = 1;
    PlaliWriteRegistryDwordValue(v22, L"Log File Serial Number", &v28);
    v23 = *phkResult;
    v28 = 1;
    PlaliWriteRegistryDwordValue(v23, L"Log File Auto Format", &v28);
    v24 = *phkResult;
    v28 = 0;
    PlaliWriteRegistryDwordValue(v24, L"ExecuteOnly", &v28);
    PlaliWriteRegistryStringValue(*phkResult, L"Comment", 1u, 0, 0);
    if ( (unsigned int)PlaliIsStringEmpty(a3) )
    {
      v25 = _wgetenv(L"SystemDrive");
      if ( !v25 )
        return Version;
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
      if ( v26 >= 5 )
        return Version;
      StringCchPrintfW((unsigned __int16 *)&Uuid, 0x10u, L"%s\\PerfLogs", v25);
      p_Uuid = (const unsigned __int16 *)&Uuid;
    }
    else
    {
      p_Uuid = L"%SystemDrive%\\PerfLogs";
    }
    PlaliWriteRegistryStringValue(*phkResult, L"Log File Folder", 1u, p_Uuid, 0);
  }
  return Version;
}

```

## disassembly

```asm
0x180131208  push    rbp
0x18013120a  push    rbx
0x18013120b  push    rsi
0x18013120c  push    rdi
0x18013120d  push    r12
0x18013120f  push    r13
0x180131211  push    r14
0x180131213  push    r15
0x180131215  lea     rbp, [rsp-1Fh]
0x18013121a  sub     rsp, 0A8h
0x180131221  mov     rax, cs:__security_cookie
0x180131228  xor     rax, rsp
0x18013122b  mov     [rbp+57h+var_48], rax
0x18013122f  mov     rbx, rdx
0x180131232  mov     rsi, rcx
0x180131235  xor     r12d, r12d
0x180131238  lea     rdx, [rbp+57h+GuidString]; struct _PLALI_VERSION_ *
0x18013123c  xorps   xmm0, xmm0
0x18013123f  mov     [rbp+57h+dwDisposition], r12d
0x180131243  xorps   xmm1, xmm1
0x180131246  mov     [rbp+57h+var_90], r12d
0x18013124a  mov     rcx, r8; lpMachineName
0x18013124d  mov     r14, r9
0x180131250  movups  [rbp+57h+var_78], xmm0
0x180131254  mov     r15, r8
0x180131257  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm1
0x18013125b  call    ?PlaliGetVersion@@YAJPEBGPEAU_PLALI_VERSION_@@@Z; PlaliGetVersion(ushort const *,_PLALI_VERSION_ *)
0x180131260  mov     edi, eax
0x180131262  test    eax, eax
0x180131264  jnz     loc_180131540
0x18013126a  cmp     dword ptr [rbp+57h+GuidString.Buffer], 893h
0x180131271  jbe     loc_1801312F9
0x180131277  xorps   xmm0, xmm0
0x18013127a  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18013127e  xorps   xmm1, xmm1
0x180131281  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180131285  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm1
0x180131289  call    cs:__imp_UuidCreate
0x18013128f  test    eax, eax
0x180131291  jz      short loc_1801312A6
0x180131293  cmp     eax, 720h
0x180131298  jz      short loc_1801312A6
0x18013129a  mov     ecx, eax; unsigned int
0x18013129c  call    ?PlaliErrorToPdhStatus@@YAJK@Z; PlaliErrorToPdhStatus(ulong)
0x1801312a1  jmp     loc_180131542
0x1801312a6  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1801312aa  lea     rcx, [rbp+57h+Uuid]; Guid
0x1801312ae  call    cs:__imp_RtlStringFromGUID
0x1801312b4  test    eax, eax
0x1801312b6  jnz     short loc_18013129A
0x1801312b8  mov     rdx, [rbp+57h+GuidString.Buffer]; lpSubKey
0x1801312bc  lea     rax, [rbp+57h+dwDisposition]
0x1801312c0  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x1801312c5  xor     r9d, r9d; lpClass
0x1801312c8  mov     [rsp+0E0h+phkResult], rbx; phkResult
0x1801312cd  xor     r8d, r8d; Reserved
0x1801312d0  mov     [rsp+0E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1801312d5  mov     rcx, rsi; hKey
0x1801312d8  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x1801312e0  mov     [rsp+0E0h+dwOptions], r12d; dwOptions
0x1801312e5  call    cs:__imp_RegCreateKeyExW
0x1801312eb  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x1801312ef  mov     edi, eax
0x1801312f1  call    cs:__imp_RtlFreeUnicodeString
0x1801312f7  jmp     short loc_18013132D
0x1801312f9  lea     rax, [rbp+57h+dwDisposition]
0x1801312fd  xor     r9d, r9d; lpClass
0x180131300  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x180131305  xor     r8d, r8d; Reserved
0x180131308  mov     [rsp+0E0h+phkResult], rbx; phkResult
0x18013130d  mov     rdx, r14; lpSubKey
0x180131310  mov     [rsp+0E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180131315  mov     rcx, rsi; hKey
0x180131318  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x180131320  mov     [rsp+0E0h+dwOptions], r12d; dwOptions
0x180131325  call    cs:__imp_RegCreateKeyExW
0x18013132b  mov     edi, eax
0x18013132d  mov     ecx, edi; unsigned int
0x18013132f  call    ?PlaliErrorToPdhStatus@@YAJK@Z; PlaliErrorToPdhStatus(ulong)
0x180131334  cmp     [rbp+57h+dwDisposition], 2
0x180131338  mov     edi, eax
0x18013133a  jnz     short loc_180131352
0x18013133c  mov     rcx, [rbx]; hKey
0x18013133f  call    cs:__imp_RegCloseKey
0x180131345  mov     [rbx], r12
0x180131348  mov     edi, 0C0000BEEh
0x18013134d  jmp     loc_180131540
0x180131352  test    eax, eax
0x180131354  jnz     loc_180131540
0x18013135a  mov     rcx, [rbx]; HKEY
0x18013135d  lea     r13d, [rax+1]
0x180131361  mov     r8d, r13d; unsigned int
0x180131364  mov     [rsp+0E0h+dwOptions], r12d; unsigned int
0x180131369  mov     r9, r14; unsigned __int16 *
0x18013136c  lea     rdx, aCollectionName; "Collection Name"
0x180131373  call    ?PlaliWriteRegistryStringValue@@YAJPEAUHKEY__@@PEBGK1K@Z; PlaliWriteRegistryStringValue(HKEY__ *,ushort const *,ulong,ushort const *,ulong)
0x180131378  mov     rcx, [rbx]; HKEY
0x18013137b  lea     r8, [rbp+57h+var_90]; unsigned int *
0x18013137f  lea     rdx, aCurrentState; "Current State"
0x180131386  mov     [rbp+57h+var_90], r12d
0x18013138a  call    ?PlaliWriteRegistryDwordValue@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaliWriteRegistryDwordValue(HKEY__ *,ushort const *,ulong *)
0x18013138f  mov     edi, eax
0x180131391  test    eax, eax
0x180131393  jnz     loc_180131540
0x180131399  mov     rcx, [rbx]; HKEY
0x18013139c  lea     r8, [rbp+57h+var_90]; unsigned int *
0x1801313a0  or      esi, 0FFFFFFFFh
0x1801313a3  lea     rdx, aLogType; "Log Type"
0x1801313aa  mov     [rbp+57h+var_90], esi
0x1801313ad  call    ?PlaliWriteRegistryDwordValue@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaliWriteRegistryDwordValue(HKEY__ *,ushort const *,ulong *)
0x1801313b2  mov     rcx, [rbx]; HKEY
0x1801313b5  lea     rdx, aLogFileBaseNam; "Log File Base Name"
0x1801313bc  mov     r9, r14; unsigned __int16 *
0x1801313bf  mov     [rsp+0E0h+dwOptions], r12d; unsigned int
0x1801313c4  mov     r8d, r13d; unsigned int
0x1801313c7  call    ?PlaliWriteRegistryStringValue@@YAJPEAUHKEY__@@PEBGK1K@Z; PlaliWriteRegistryStringValue(HKEY__ *,ushort const *,ulong,ushort const *,ulong)
0x1801313cc  mov     rcx, [rbx]; HKEY
0x1801313cf  lea     r8, [rbp+57h+var_78]; struct _PLALI_TIME_INFO *
0x1801313d3  mov     rax, 7FFFFFFFFFFFFFFFh
0x1801313dd  mov     qword ptr [rbp+57h+var_78], 10001h
0x1801313e5  lea     rdx, aStart; "Start"
0x1801313ec  mov     qword ptr [rbp+57h+var_78+8], rax
0x1801313f0  call    ?PlaliWriteRegistryPlaTime@@YAJPEAUHKEY__@@PEBGPEAU_PLALI_TIME_INFO@@@Z; PlaliWriteRegistryPlaTime(HKEY__ *,ushort const *,_PLALI_TIME_INFO *)
0x1801313f5  mov     rcx, [rbx]; HKEY
0x1801313f8  lea     eax, [rdi+2]
0x1801313fb  lea     r8, [rbp+57h+var_78]; struct _PLALI_TIME_INFO *
0x1801313ff  mov     word ptr [rbp+57h+var_78+2], ax
0x180131403  lea     rdx, aStop; "Stop"
0x18013140a  mov     qword ptr [rbp+57h+var_78+8], r12
0x18013140e  call    ?PlaliWriteRegistryPlaTime@@YAJPEAUHKEY__@@PEBGPEAU_PLALI_TIME_INFO@@@Z; PlaliWriteRegistryPlaTime(HKEY__ *,ushort const *,_PLALI_TIME_INFO *)
0x180131413  mov     rcx, [rbx]; HKEY
0x180131416  lea     r8, [rbp+57h+var_78]; struct _PLALI_TIME_INFO *
0x18013141a  xorps   xmm0, xmm0
0x18013141d  lea     rdx, aCreateNewFile; "Create New File"
0x180131424  movups  [rbp+57h+var_78], xmm0
0x180131428  mov     edi, eax
0x18013142a  call    ?PlaliWriteRegistryPlaTime@@YAJPEAUHKEY__@@PEBGPEAU_PLALI_TIME_INFO@@@Z; PlaliWriteRegistryPlaTime(HKEY__ *,ushort const *,_PLALI_TIME_INFO *)
0x18013142f  mov     rcx, [rbx]; HKEY
0x180131432  lea     r8, [rbp+57h+var_90]; unsigned int *
0x180131436  lea     rdx, aRestart; "Restart"
0x18013143d  mov     [rbp+57h+var_90], r12d
0x180131441  call    ?PlaliWriteRegistryDwordValue@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaliWriteRegistryDwordValue(HKEY__ *,ushort const *,ulong *)
0x180131446  mov     rcx, [rbx]; HKEY
0x180131449  lea     r8, [rbp+57h+var_90]; unsigned int *
0x18013144d  lea     rdx, aCurrentState; "Current State"
0x180131454  mov     [rbp+57h+var_90], r12d
0x180131458  call    ?PlaliWriteRegistryDwordValue@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaliWriteRegistryDwordValue(HKEY__ *,ushort const *,ulong *)
0x18013145d  mov     rcx, [rbx]; HKEY
0x180131460  lea     r8, [rbp+57h+var_90]; unsigned int *
0x180131464  lea     rdx, aLogFileMaxSize; "Log File Max Size"
0x18013146b  mov     [rbp+57h+var_90], esi
0x18013146e  call    ?PlaliWriteRegistryDwordValue@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaliWriteRegistryDwordValue(HKEY__ *,ushort const *,ulong *)
0x180131473  mov     rcx, [rbx]; HKEY
0x180131476  lea     r8, [rbp+57h+var_90]; unsigned int *
0x18013147a  lea     rdx, aLogFileSerialN; "Log File Serial Number"
0x180131481  mov     [rbp+57h+var_90], r13d
0x180131485  call    ?PlaliWriteRegistryDwordValue@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaliWriteRegistryDwordValue(HKEY__ *,ushort const *,ulong *)
0x18013148a  mov     rcx, [rbx]; HKEY
0x18013148d  lea     r8, [rbp+57h+var_90]; unsigned int *
0x180131491  lea     rdx, aLogFileAutoFor; "Log File Auto Format"
0x180131498  mov     [rbp+57h+var_90], r13d
0x18013149c  call    ?PlaliWriteRegistryDwordValue@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaliWriteRegistryDwordValue(HKEY__ *,ushort const *,ulong *)
0x1801314a1  mov     rcx, [rbx]; HKEY
0x1801314a4  lea     r8, [rbp+57h+var_90]; unsigned int *
0x1801314a8  lea     rdx, aExecuteonly; "ExecuteOnly"
0x1801314af  mov     [rbp+57h+var_90], r12d
0x1801314b3  call    ?PlaliWriteRegistryDwordValue@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaliWriteRegistryDwordValue(HKEY__ *,ushort const *,ulong *)
0x1801314b8  mov     rcx, [rbx]; HKEY
0x1801314bb  lea     rdx, aComment; "Comment"
0x1801314c2  xor     r9d, r9d; unsigned __int16 *
0x1801314c5  mov     [rsp+0E0h+dwOptions], r12d; unsigned int
0x1801314ca  mov     r8d, r13d; unsigned int
0x1801314cd  call    ?PlaliWriteRegistryStringValue@@YAJPEAUHKEY__@@PEBGK1K@Z; PlaliWriteRegistryStringValue(HKEY__ *,ushort const *,ulong,ushort const *,ulong)
0x1801314d2  mov     rcx, r15; unsigned __int16 *
0x1801314d5  call    ?PlaliIsStringEmpty@@YAHPEBG@Z; PlaliIsStringEmpty(ushort const *)
0x1801314da  test    eax, eax
0x1801314dc  jz      short loc_180131522
0x1801314de  lea     rcx, aSystemdrive; "SystemDrive"
0x1801314e5  call    cs:__imp__wgetenv
0x1801314eb  test    rax, rax
0x1801314ee  jz      short loc_180131540
0x1801314f0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801314f4  inc     rcx
0x1801314f7  cmp     [rax+rcx*2], r12w
0x1801314fc  jnz     short loc_1801314F4
0x1801314fe  cmp     rcx, 5
0x180131502  jnb     short loc_180131540
0x180131504  mov     r9, rax
0x180131507  lea     r8, aSPerflogs; "%s\\PerfLogs"
0x18013150e  mov     edx, 10h; unsigned __int64
0x180131513  lea     rcx, [rbp+57h+Uuid]; unsigned __int16 *
0x180131517  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18013151c  lea     r9, [rbp+57h+Uuid]
0x180131520  jmp     short loc_180131529
0x180131522  lea     r9, aSystemdrivePer_0; "%SystemDrive%\\PerfLogs"
0x180131529  mov     rcx, [rbx]; HKEY
0x18013152c  lea     rdx, aLogFileFolder; "Log File Folder"
0x180131533  mov     r8d, r13d; unsigned int
0x180131536  mov     [rsp+0E0h+dwOptions], r12d; unsigned int
0x18013153b  call    ?PlaliWriteRegistryStringValue@@YAJPEAUHKEY__@@PEBGK1K@Z; PlaliWriteRegistryStringValue(HKEY__ *,ushort const *,ulong,ushort const *,ulong)
0x180131540  mov     eax, edi
0x180131542  mov     rcx, [rbp+57h+var_48]
0x180131546  xor     rcx, rsp; StackCookie
0x180131549  call    __security_check_cookie
0x18013154e  add     rsp, 0A8h
0x180131555  pop     r15
0x180131557  pop     r14
0x180131559  pop     r13
0x18013155b  pop     r12
0x18013155d  pop     rdi
0x18013155e  pop     rsi
0x18013155f  pop     rbx
0x180131560  pop     rbp
0x180131561  retn
```
