# InternalDeleteForm

- ea: `0x180094d9c`
- end: `0x18009502e`
- name: `InternalDeleteForm`
- size: `658`
- prototype: `__int64 __fastcall(struct _INISPOOLER *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180094128`
- `0x180094174`

## callees

- `0x1800051f0`
- `0x180008520`
- `0x180008560`
- `0x180008cb8`
- `0x180009630`
- `0x18000d988`
- `0x180022990`
- `0x180035ae4`
- `0x18003ea2c`
- `0x180074f20`
- `0x1800945a4`
- `0x180094d9c`
- `0x180099584`
- `0x18009ef20`
- `0x1800ab0fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094de2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094e80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094ebb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094fef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094de2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094e80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094ebb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094fef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094f6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094f88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094f6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094f88`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180094f0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180094f0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094ef7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094f46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094ef7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180094f46`
- `SPOOLSS!RevertToPrinterSelf` at `0x180094ecd`
- `SPOOLSS!RevertToPrinterSelf` at `0x180094ecd`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180094fde`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180094fde`

## string_xrefs

- `0x180094dc9`: `InternalDeleteForm`
- `0x180094e95`: `InternalDeleteForm`
- `0x180095002`: `InternalDeleteForm`
- `0x180094ff8`: `DeleteForm operation for form '%ws' failed.  Error %d`

## pseudocode

```c
_BOOL8 __fastcall InternalDeleteForm(struct _INISPOOLER *a1, unsigned __int16 *a2)
{
  int v4; // edi
  __int64 IniKey; // rax
  __int64 v6; // rbp
  __int64 v7; // rcx
  HANDLE v9; // r14
  __int64 v10; // rcx
  unsigned int v11; // edi
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF

  hKey = 0;
  if ( !a1 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError("InternalDeleteForm", L"pInispooler is NULL.");
    return 0;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    LocalSpoolerTelemetry::WriteDbgTraceError("InternalDeleteForm", L"pFormName must be specified.");
    return 0;
  }
  v4 = 0;
  if ( !(unsigned int)ValidateObjectAccess(0, 1, 0, 0, (__int64)a1, 1) )
  {
    if ( (unsigned int)RemoteOrGuestOrAppContainerUser() || !(unsigned int)ValidateFormAccess(a1, 0) )
    {
      SetLastError(5u);
      return 0;
    }
    v4 = 1;
  }
  EnterSplSem(0);
  InitializeForms(a1);
  IniKey = FindIniKey(*((_QWORD *)a1 + 9), a2, 0);
  v6 = IniKey;
  if ( !IniKey )
  {
LABEL_13:
    SetLastError(IniKey != 0 ? 87 : 1902);
    LeaveSplSem(v7);
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalDeleteForm",
      L"Form '%ws' does not exist or is a built-in form.",
      a2);
    return 0;
  }
  if ( *(_DWORD *)(IniKey + 60) == 1 )
  {
    if ( (*((_DWORD *)a1 + 42) & 0x1000000) != 0 )
      goto LABEL_13;
  }
  else if ( !*(_DWORD *)(IniKey + 60) )
  {
    goto LABEL_18;
  }
  if ( v4 )
    goto LABEL_13;
LABEL_18:
  v9 = RevertToPrinterSelf();
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)a1 + 20), 0, 0x20006u, &hKey);
  if ( !v11 )
  {
    v11 = RegDeleteValueW(hKey, a2);
    if ( !v11 )
    {
      if ( *(_QWORD *)(v6 + 88) )
      {
        phkResult = 0;
        v11 = RegOpenKeyExW(hKey, a2, 0, 0x20006u, &phkResult);
        if ( !v11 )
        {
          v11 = SplRegDeleteKey(phkResult, L"LanguagePairs", a1);
          RegCloseKey(phkResult);
        }
      }
      SplRegDeleteKey(hKey, a2, a1);
    }
    RegCloseKey(hKey);
    if ( !v11 )
    {
      DeleteIniForm(v6, a1);
      if ( (*((_DWORD *)a1 + 42) & 0x4000000) == 0 )
      {
        SetPrinterChange(0, 0, 0, 0x40000, (__int64)a1);
        BroadcastChangeForms(a1);
        RunForEachSpooler(0, DsUpdateAllDriverKeys);
      }
    }
  }
  if ( v9 )
    ImpersonatePrinterClient(v9);
  LeaveSplSem(v10);
  if ( v11 )
  {
    SetLastError(v11);
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "InternalDeleteForm",
      L"DeleteForm operation for form '%ws' failed.  Error %d",
      a2,
      v11);
  }
  SplLogEvent(&MSG_FORM_DELETED, v11, a2, 0);
  return v11 == 0;
}

```

## disassembly

```asm
0x180094d9c  mov     [rsp+arg_8], rbx
0x180094da1  mov     [rsp+arg_18], rbp
0x180094da6  push    rsi
0x180094da7  push    rdi
0x180094da8  push    r14
0x180094daa  sub     rsp, 30h
0x180094dae  mov     [rsp+48h+hKey], 0
0x180094db7  mov     rsi, rdx
0x180094dba  mov     rbx, rcx
0x180094dbd  test    rcx, rcx
0x180094dc0  jnz     short loc_180094DDA
0x180094dc2  lea     rdx, aPinispoolerIsN; "pInispooler is NULL."
0x180094dc9  lea     rcx, aInternaldelete; "InternalDeleteForm"
0x180094dd0  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180094dd5  jmp     loc_180094EA1
0x180094dda  test    rsi, rsi
0x180094ddd  jnz     short loc_180094DF1
0x180094ddf  lea     ecx, [rsi+57h]; dwErrCode
0x180094de2  call    cs:__imp_SetLastError
0x180094de8  lea     rdx, aPformnameMustB; "pFormName must be specified."
0x180094def  jmp     short loc_180094DC9
0x180094df1  xor     edi, edi
0x180094df3  xor     r9d, r9d
0x180094df6  xor     r8d, r8d
0x180094df9  xor     ecx, ecx
0x180094dfb  lea     r14d, [rdi+1]
0x180094dff  mov     [rsp+48h+var_20], r14d
0x180094e04  mov     edx, r14d
0x180094e07  mov     [rsp+48h+phkResult], rbx
0x180094e0c  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x180094e11  test    eax, eax
0x180094e13  jnz     short loc_180094E37
0x180094e15  call    ?RemoteOrGuestOrAppContainerUser@@YAHXZ; RemoteOrGuestOrAppContainerUser(void)
0x180094e1a  test    eax, eax
0x180094e1c  jnz     loc_180094EB6
0x180094e22  xor     edx, edx
0x180094e24  mov     rcx, rbx
0x180094e27  call    ValidateFormAccess
0x180094e2c  test    eax, eax
0x180094e2e  jz      loc_180094EB6
0x180094e34  mov     edi, r14d
0x180094e37  xor     ecx, ecx
0x180094e39  call    EnterSplSem
0x180094e3e  mov     rcx, rbx; struct _INISPOOLER *
0x180094e41  call    InitializeForms
0x180094e46  mov     rcx, [rbx+48h]
0x180094e4a  xor     r8d, r8d
0x180094e4d  mov     rdx, rsi
0x180094e50  call    FindIniKey
0x180094e55  mov     rbp, rax
0x180094e58  test    rax, rax
0x180094e5b  jz      short loc_180094E6F
0x180094e5d  cmp     [rax+3Ch], r14d
0x180094e61  jnz     short loc_180094EC3
0x180094e63  test    dword ptr [rbx+0A8h], 1000000h
0x180094e6d  jz      short loc_180094EC9
0x180094e6f  neg     rbp
0x180094e72  sbb     ecx, ecx
0x180094e74  and     ecx, 0FFFFF8E9h
0x180094e7a  add     ecx, 76Eh; dwErrCode
0x180094e80  call    cs:__imp_SetLastError
0x180094e86  call    LeaveSplSem
0x180094e8b  mov     r8, rsi
0x180094e8e  lea     rdx, aFormWsDoesNotE; "Form '%ws' does not exist or is a built"...
0x180094e95  lea     rcx, aInternaldelete; "InternalDeleteForm"
0x180094e9c  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180094ea1  xor     eax, eax
0x180094ea3  mov     rbx, [rsp+48h+arg_8]
0x180094ea8  mov     rbp, [rsp+48h+arg_18]
0x180094ead  add     rsp, 30h
0x180094eb1  pop     r14
0x180094eb3  pop     rdi
0x180094eb4  pop     rsi
0x180094eb5  retn
0x180094eb6  mov     ecx, 5; dwErrCode
0x180094ebb  call    cs:__imp_SetLastError
0x180094ec1  jmp     short loc_180094EA1
0x180094ec3  cmp     dword ptr [rax+3Ch], 0
0x180094ec7  jz      short loc_180094ECD
0x180094ec9  test    edi, edi
0x180094ecb  jnz     short loc_180094E6F
0x180094ecd  call    cs:__imp_RevertToPrinterSelf
0x180094ed3  mov     rdx, [rbx+0A0h]; lpSubKey
0x180094eda  mov     r9d, 20006h; samDesired
0x180094ee0  mov     r14, rax
0x180094ee3  xor     r8d, r8d; ulOptions
0x180094ee6  lea     rax, [rsp+48h+hKey]
0x180094eeb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180094ef2  mov     [rsp+48h+phkResult], rax; phkResult
0x180094ef7  call    cs:__imp_RegOpenKeyExW
0x180094efd  mov     edi, eax
0x180094eff  test    eax, eax
0x180094f01  jnz     loc_180094FD6
0x180094f07  mov     rcx, [rsp+48h+hKey]; hKey
0x180094f0c  mov     rdx, rsi; lpValueName
0x180094f0f  call    cs:__imp_RegDeleteValueW
0x180094f15  mov     edi, eax
0x180094f17  test    eax, eax
0x180094f19  jnz     short loc_180094F83
0x180094f1b  cmp     qword ptr [rbp+58h], 0
0x180094f20  jz      short loc_180094F73
0x180094f22  mov     rcx, [rsp+48h+hKey]; hKey
0x180094f27  lea     rax, [rsp+48h+arg_10]
0x180094f2c  mov     r9d, 20006h; samDesired
0x180094f32  mov     [rsp+48h+phkResult], rax; phkResult
0x180094f37  xor     r8d, r8d; ulOptions
0x180094f3a  mov     [rsp+48h+arg_10], 0
0x180094f43  mov     rdx, rsi; lpSubKey
0x180094f46  call    cs:__imp_RegOpenKeyExW
0x180094f4c  mov     edi, eax
0x180094f4e  test    eax, eax
0x180094f50  jnz     short loc_180094F73
0x180094f52  mov     rcx, [rsp+48h+arg_10]; void *
0x180094f57  lea     rdx, ipszRegstryLanguagePairs; "LanguagePairs"
0x180094f5e  mov     r8, rbx; struct _INISPOOLER *
0x180094f61  call    ?SplRegDeleteKey@@YAJPEAXPEBGPEAU_INISPOOLER@@@Z; SplRegDeleteKey(void *,ushort const *,_INISPOOLER *)
0x180094f66  mov     rcx, [rsp+48h+arg_10]; hKey
0x180094f6b  mov     edi, eax
0x180094f6d  call    cs:__imp_RegCloseKey
0x180094f73  mov     rcx, [rsp+48h+hKey]; void *
0x180094f78  mov     r8, rbx; struct _INISPOOLER *
0x180094f7b  mov     rdx, rsi; unsigned __int16 *
0x180094f7e  call    ?SplRegDeleteKey@@YAJPEAXPEBGPEAU_INISPOOLER@@@Z; SplRegDeleteKey(void *,ushort const *,_INISPOOLER *)
0x180094f83  mov     rcx, [rsp+48h+hKey]; hKey
0x180094f88  call    cs:__imp_RegCloseKey
0x180094f8e  test    edi, edi
0x180094f90  jnz     short loc_180094FD6
0x180094f92  mov     rdx, rbx
0x180094f95  mov     rcx, rbp
0x180094f98  call    DeleteIniForm
0x180094f9d  test    dword ptr [rbx+0A8h], 4000000h
0x180094fa7  jnz     short loc_180094FD6
0x180094fa9  mov     r9d, 40000h
0x180094faf  mov     [rsp+48h+phkResult], rbx
0x180094fb4  xor     r8d, r8d
0x180094fb7  xor     edx, edx
0x180094fb9  xor     ecx, ecx
0x180094fbb  call    SetPrinterChange
0x180094fc0  mov     rcx, rbx; struct _INISPOOLER *
0x180094fc3  call    ?BroadcastChangeForms@@YAXPEAU_INISPOOLER@@@Z; BroadcastChangeForms(_INISPOOLER *)
0x180094fc8  lea     rdx, DsUpdateAllDriverKeys
0x180094fcf  xor     ecx, ecx
0x180094fd1  call    RunForEachSpooler
0x180094fd6  test    r14, r14
0x180094fd9  jz      short loc_180094FE4
0x180094fdb  mov     rcx, r14; hToken
0x180094fde  call    cs:__imp_ImpersonatePrinterClient
0x180094fe4  call    LeaveSplSem
0x180094fe9  test    edi, edi
0x180094feb  jz      short loc_18009500E
0x180094fed  mov     ecx, edi; dwErrCode
0x180094fef  call    cs:__imp_SetLastError
0x180094ff5  mov     r9d, edi
0x180094ff8  lea     rdx, aDeleteformOper; "DeleteForm operation for form '%ws' fai"...
0x180094fff  mov     r8, rsi
0x180095002  lea     rcx, aInternaldelete; "InternalDeleteForm"
0x180095009  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009500e  xor     r9d, r9d
0x180095011  lea     rcx, MSG_FORM_DELETED; struct _EVENT_DESCRIPTOR *
0x180095018  mov     r8, rsi; unsigned __int16 *
0x18009501b  mov     edx, edi; unsigned int
0x18009501d  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x180095022  xor     eax, eax
0x180095024  test    edi, edi
0x180095026  setz    al
0x180095029  jmp     loc_180094EA3
```
