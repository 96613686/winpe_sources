# DeleteDriverIni(_INIDRIVER *,_INIVERSION *,_INIENVIRONMENT *,_INISPOOLER *)

- ea: `0x18006cbf8`
- end: `0x18006cdd9`
- name: `?DeleteDriverIni@@YAHPEAU_INIDRIVER@@PEAU_INIVERSION@@PEAU_INIENVIRONMENT@@PEAU_INISPOOLER@@@Z`
- size: `481`
- prototype: `int(struct _INIDRIVER *, struct _INIVERSION *, struct _INIENVIRONMENT *, struct _INISPOOLER *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800685e4`
- `0x1800be85c`

## callees

- `0x180045010`
- `0x180054638`
- `0x18006cbf8`
- `0x18009ef20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cdbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cdbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cd91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cc98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ccc5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ccef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cc98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ccc5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ccef`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006cc34`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006cc34`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18006cdb1`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18006cdb1`

## string_xrefs

- `0x18006cd12`: `Error:RegDeleteKey failed with %d`
- `0x18006cd36`: `Error:RegOpenKeyEx <version> failed with %d`
- `0x18006cd19`: `DeleteDriverIni`
- `0x18006cd3d`: `DeleteDriverIni`
- `0x18006cd5f`: `DeleteDriverIni`
- `0x18006cd81`: `DeleteDriverIni`
- `0x18006cda2`: `DeleteDriverIni`
- `0x18006cd7a`: `Error:RegOpenKeyEx <Environment> failed with %d`
- `0x18006cd58`: `Error:RegOpenKeyEx <Drivers> failed with %d`
- `0x18006cd9b`: `Error:RegCreateKeyEx <Environments> failed with %d`

## pseudocode

```c
__int64 __fastcall DeleteDriverIni(const unsigned __int16 **a1, LPCWSTR *a2, LPCWSTR *a3, struct _INISPOOLER *a4)
{
  HANDLE v8; // r14
  unsigned int v9; // eax
  DWORD v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  DWORD v13; // eax
  HKEY v16; // [rsp+40h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  HKEY v19; // [rsp+B8h] [rbp+50h] BYREF

  hKey = 0;
  phkResult = 0;
  v16 = 0;
  v19 = 0;
  v8 = RevertToPrinterSelf();
  if ( (unsigned int)SplRegCreateKey(
                       HKEY_LOCAL_MACHINE,
                       *((const unsigned __int16 **)a4 + 14),
                       0,
                       0x20006u,
                       0,
                       (void **)&hKey,
                       0) )
  {
    v10 = 0;
    LocalSpoolerTelemetry::WriteDbgTraceWarning(
      "DeleteDriverIni",
      L"Error:RegCreateKeyEx <Environments> failed with %d",
      0);
  }
  else
  {
    v9 = RegOpenKeyExW(hKey, a3[3], 0, 0x20006u, &phkResult);
    v10 = v9;
    if ( v9 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "DeleteDriverIni",
        L"Error:RegOpenKeyEx <Environment> failed with %d",
        v9);
    }
    else
    {
      v11 = RegOpenKeyExW(phkResult, L"Drivers", 0, 0x20006u, &v16);
      v10 = v11;
      if ( v11 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "DeleteDriverIni",
          L"Error:RegOpenKeyEx <Drivers> failed with %d",
          v11);
      }
      else
      {
        v12 = RegOpenKeyExW(v16, a2[2], 0, 0x20006u, &v19);
        v10 = v12;
        if ( v12 )
        {
          LocalSpoolerTelemetry::WriteDbgTraceWarning(
            "DeleteDriverIni",
            L"Error:RegOpenKeyEx <version> failed with %d",
            v12);
        }
        else
        {
          v13 = SplRegDeleteKey(v19, a1[3], a4);
          if ( v13 )
          {
            v10 = v13;
            LocalSpoolerTelemetry::WriteDbgTraceWarning("DeleteDriverIni", L"Error:RegDeleteKey failed with %d", v13);
          }
          RegCloseKey(v19);
        }
        RegCloseKey(v16);
      }
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  ImpersonatePrinterClient(v8);
  if ( !v10 )
    return 1;
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x18006cbf8  push    rbp
0x18006cbfa  push    rbx
0x18006cbfb  push    rsi
0x18006cbfc  push    rdi
0x18006cbfd  push    r14
0x18006cbff  push    r15
0x18006cc01  mov     rbp, rsp
0x18006cc04  sub     rsp, 68h
0x18006cc08  mov     rdi, r9
0x18006cc0b  mov     [rbp+hKey], 0
0x18006cc13  mov     rbx, r8
0x18006cc16  mov     [rbp+var_20], 0
0x18006cc1e  mov     r15, rdx
0x18006cc21  mov     [rbp+var_28], 0
0x18006cc29  mov     rsi, rcx
0x18006cc2c  mov     [rbp+arg_18], 0
0x18006cc34  call    cs:__imp_RevertToPrinterSelf
0x18006cc3a  mov     rdx, [rdi+70h]; unsigned __int16 *
0x18006cc3e  mov     r9d, 20006h; unsigned int
0x18006cc44  mov     [rsp+68h+var_30], rdi; struct _INISPOOLER *
0x18006cc49  mov     r14, rax
0x18006cc4c  lea     rax, [rbp+hKey]
0x18006cc50  mov     [rsp+68h+var_38], 0; unsigned int *
0x18006cc59  mov     [rsp+68h+var_40], rax; void **
0x18006cc5e  xor     r8d, r8d; unsigned int
0x18006cc61  mov     rcx, 0FFFFFFFF80000002h; void *
0x18006cc68  mov     [rsp+68h+phkResult], 0; struct _SECURITY_ATTRIBUTES *
0x18006cc71  call    ?SplRegCreateKey@@YAJPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAXPEAKPEAU_INISPOOLER@@@Z; SplRegCreateKey(void *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,void * *,ulong *,_INISPOOLER *)
0x18006cc76  xor     r8d, r8d; ulOptions
0x18006cc79  test    eax, eax
0x18006cc7b  jnz     loc_18006CD99
0x18006cc81  mov     rdx, [rbx+18h]; lpSubKey
0x18006cc85  lea     rax, [rbp+var_20]
0x18006cc89  mov     rcx, [rbp+hKey]; hKey
0x18006cc8d  mov     r9d, 20006h; samDesired
0x18006cc93  mov     [rsp+68h+phkResult], rax; phkResult
0x18006cc98  call    cs:__imp_RegOpenKeyExW
0x18006cc9e  mov     ebx, eax
0x18006cca0  test    eax, eax
0x18006cca2  jnz     loc_18006CD77
0x18006cca8  mov     rcx, [rbp+var_20]; hKey
0x18006ccac  lea     rax, [rbp+var_28]
0x18006ccb0  mov     r9d, 20006h; samDesired
0x18006ccb6  mov     [rsp+68h+phkResult], rax; phkResult
0x18006ccbb  xor     r8d, r8d; ulOptions
0x18006ccbe  lea     rdx, szDriversKey; "Drivers"
0x18006ccc5  call    cs:__imp_RegOpenKeyExW
0x18006cccb  mov     ebx, eax
0x18006cccd  test    eax, eax
0x18006cccf  jnz     loc_18006CD55
0x18006ccd5  mov     rdx, [r15+10h]; lpSubKey
0x18006ccd9  lea     rax, [rbp+arg_18]
0x18006ccdd  mov     rcx, [rbp+var_28]; hKey
0x18006cce1  mov     r9d, 20006h; samDesired
0x18006cce7  xor     r8d, r8d; ulOptions
0x18006ccea  mov     [rsp+68h+phkResult], rax; phkResult
0x18006ccef  call    cs:__imp_RegOpenKeyExW
0x18006ccf5  mov     ebx, eax
0x18006ccf7  test    eax, eax
0x18006ccf9  jnz     short loc_18006CD33
0x18006ccfb  mov     rdx, [rsi+18h]; unsigned __int16 *
0x18006ccff  mov     r8, rdi; struct _INISPOOLER *
0x18006cd02  mov     rcx, [rbp+arg_18]; void *
0x18006cd06  call    ?SplRegDeleteKey@@YAJPEAXPEBGPEAU_INISPOOLER@@@Z; SplRegDeleteKey(void *,ushort const *,_INISPOOLER *)
0x18006cd0b  test    eax, eax
0x18006cd0d  jz      short loc_18006CD27
0x18006cd0f  mov     r8d, eax
0x18006cd12  lea     rdx, aErrorRegdelete; "Error:RegDeleteKey failed with %d"
0x18006cd19  lea     rcx, aDeletedriverin; "DeleteDriverIni"
0x18006cd20  mov     ebx, eax
0x18006cd22  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18006cd27  mov     rcx, [rbp+arg_18]; hKey
0x18006cd2b  call    cs:__imp_RegCloseKey
0x18006cd31  jmp     short loc_18006CD49
0x18006cd33  mov     r8d, eax
0x18006cd36  lea     rdx, aErrorRegopenke; "Error:RegOpenKeyEx <version> failed wit"...
0x18006cd3d  lea     rcx, aDeletedriverin; "DeleteDriverIni"
0x18006cd44  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18006cd49  mov     rcx, [rbp+var_28]; hKey
0x18006cd4d  call    cs:__imp_RegCloseKey
0x18006cd53  jmp     short loc_18006CD6B
0x18006cd55  mov     r8d, eax
0x18006cd58  lea     rdx, aErrorRegopenke_0; "Error:RegOpenKeyEx <Drivers> failed wit"...
0x18006cd5f  lea     rcx, aDeletedriverin; "DeleteDriverIni"
0x18006cd66  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18006cd6b  mov     rcx, [rbp+var_20]; hKey
0x18006cd6f  call    cs:__imp_RegCloseKey
0x18006cd75  jmp     short loc_18006CD8D
0x18006cd77  mov     r8d, eax
0x18006cd7a  lea     rdx, aErrorRegopenke_1; "Error:RegOpenKeyEx <Environment> failed"...
0x18006cd81  lea     rcx, aDeletedriverin; "DeleteDriverIni"
0x18006cd88  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18006cd8d  mov     rcx, [rbp+hKey]; hKey
0x18006cd91  call    cs:__imp_RegCloseKey
0x18006cd97  jmp     short loc_18006CDAE
0x18006cd99  xor     ebx, ebx
0x18006cd9b  lea     rdx, aErrorRegcreate; "Error:RegCreateKeyEx <Environments> fai"...
0x18006cda2  lea     rcx, aDeletedriverin; "DeleteDriverIni"
0x18006cda9  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18006cdae  mov     rcx, r14; hToken
0x18006cdb1  call    cs:__imp_ImpersonatePrinterClient
0x18006cdb7  test    ebx, ebx
0x18006cdb9  jz      short loc_18006CDC7
0x18006cdbb  mov     ecx, ebx; dwErrCode
0x18006cdbd  call    cs:__imp_SetLastError
0x18006cdc3  xor     eax, eax
0x18006cdc5  jmp     short loc_18006CDCC
0x18006cdc7  mov     eax, 1
0x18006cdcc  add     rsp, 68h
0x18006cdd0  pop     r15
0x18006cdd2  pop     r14
0x18006cdd4  pop     rdi
0x18006cdd5  pop     rsi
0x18006cdd6  pop     rbx
0x18006cdd7  pop     rbp
0x18006cdd8  retn
```
