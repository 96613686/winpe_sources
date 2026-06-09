# DeleteDriverVersionIni(_INIVERSION *,_INIENVIRONMENT *,_INISPOOLER *)

- ea: `0x18006cde0`
- end: `0x18006cf21`
- name: `?DeleteDriverVersionIni@@YAHPEAU_INIVERSION@@PEAU_INIENVIRONMENT@@PEAU_INISPOOLER@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(struct _INIVERSION *, struct _INIENVIRONMENT *, struct _INISPOOLER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18006ca34`

## callees

- `0x180054638`
- `0x18006cde0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006ceb6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18006ceb6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006ce4f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006ce4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cefc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cefc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ce77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ce9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ce77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ce9e`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006ce16`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006ce16`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18006cf05`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18006cf05`

## string_xrefs

- `0x18006cec9`: `Failed to delete key %p for %ws, error %d`
- `0x18006ced4`: `DeleteDriverVersionIni`

## pseudocode

```c
__int64 __fastcall DeleteDriverVersionIni(LPCWSTR *a1, LPCWSTR *a2, LPCWSTR *a3)
{
  unsigned int v6; // edi
  HANDLE v7; // r14
  LSTATUS v8; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY v12; // [rsp+A0h] [rbp+40h] BYREF
  HKEY v13; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  v13 = 0;
  v12 = 0;
  v6 = 0;
  v7 = RevertToPrinterSelf();
  if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3[14], 0, 0, 0, 0x20006u, 0, &hKey, 0) )
  {
    if ( !RegOpenKeyExW(hKey, a2[3], 0, 0x20006u, &v13) )
    {
      if ( !RegOpenKeyExW(v13, L"Drivers", 0, 0x20006u, &v12) )
      {
        v8 = RegDeleteKeyExW(v12, a1[2], 0, 0);
        if ( v8 )
        {
          dwOptions[0] = v8;
          LocalSpoolerTelemetry::WriteDbgTraceWarning(
            "DeleteDriverVersionIni",
            L"Failed to delete key %p for %ws, error %d",
            v12,
            a1[2],
            *(_QWORD *)dwOptions);
        }
        else
        {
          v6 = 1;
        }
        RegCloseKey(v12);
      }
      RegCloseKey(v13);
    }
    RegCloseKey(hKey);
  }
  ImpersonatePrinterClient(v7);
  return v6;
}

```

## disassembly

```asm
0x18006cde0  mov     [rsp-28h+arg_0], rbx
0x18006cde5  push    rbp
0x18006cde6  push    rsi
0x18006cde7  push    rdi
0x18006cde8  push    r14
0x18006cdea  push    r15
0x18006cdec  mov     rbp, rsp
0x18006cdef  sub     rsp, 60h
0x18006cdf3  mov     rbx, r8
0x18006cdf6  mov     [rbp+hKey], 0
0x18006cdfe  mov     r15, rdx
0x18006ce01  mov     [rbp+arg_18], 0
0x18006ce09  mov     rsi, rcx
0x18006ce0c  mov     [rbp+arg_10], 0
0x18006ce14  xor     edi, edi
0x18006ce16  call    cs:__imp_RevertToPrinterSelf
0x18006ce1c  mov     rdx, [rbx+70h]; lpSubKey
0x18006ce20  xor     r9d, r9d; lpClass
0x18006ce23  mov     [rsp+60h+lpdwDisposition], rdi; lpdwDisposition
0x18006ce28  mov     r14, rax
0x18006ce2b  lea     rax, [rbp+hKey]
0x18006ce2f  xor     r8d, r8d; Reserved
0x18006ce32  mov     [rsp+60h+phkResult], rax; phkResult
0x18006ce37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006ce3e  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18006ce43  mov     [rsp+60h+samDesired], 20006h; samDesired
0x18006ce4b  mov     [rsp+60h+dwOptions], edi; dwOptions
0x18006ce4f  call    cs:__imp_RegCreateKeyExW
0x18006ce55  test    eax, eax
0x18006ce57  jnz     loc_18006CF02
0x18006ce5d  mov     rdx, [r15+18h]; lpSubKey
0x18006ce61  lea     rax, [rbp+arg_18]
0x18006ce65  mov     rcx, [rbp+hKey]; hKey
0x18006ce69  mov     r9d, 20006h; samDesired
0x18006ce6f  xor     r8d, r8d; ulOptions
0x18006ce72  mov     qword ptr [rsp+60h+dwOptions], rax; phkResult
0x18006ce77  call    cs:__imp_RegOpenKeyExW
0x18006ce7d  test    eax, eax
0x18006ce7f  jnz     short loc_18006CEF8
0x18006ce81  mov     rcx, [rbp+arg_18]; hKey
0x18006ce85  lea     rax, [rbp+arg_10]
0x18006ce89  mov     r9d, 20006h; samDesired
0x18006ce8f  mov     qword ptr [rsp+60h+dwOptions], rax; phkResult
0x18006ce94  xor     r8d, r8d; ulOptions
0x18006ce97  lea     rdx, szDriversKey; "Drivers"
0x18006ce9e  call    cs:__imp_RegOpenKeyExW
0x18006cea4  test    eax, eax
0x18006cea6  jnz     short loc_18006CEEE
0x18006cea8  mov     rdx, [rsi+10h]; lpSubKey
0x18006ceac  xor     r9d, r9d; Reserved
0x18006ceaf  mov     rcx, [rbp+arg_10]; hKey
0x18006ceb3  xor     r8d, r8d; samDesired
0x18006ceb6  call    cs:__imp_RegDeleteKeyExW
0x18006cebc  test    eax, eax
0x18006cebe  jnz     short loc_18006CEC5
0x18006cec0  lea     edi, [rax+1]
0x18006cec3  jmp     short loc_18006CEE4
0x18006cec5  mov     r9, [rsi+10h]
0x18006cec9  lea     rdx, aFailedToDelete; "Failed to delete key %p for %ws, error "...
0x18006ced0  mov     r8, [rbp+arg_10]
0x18006ced4  lea     rcx, aDeletedriverve; "DeleteDriverVersionIni"
0x18006cedb  mov     [rsp+60h+dwOptions], eax
0x18006cedf  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18006cee4  mov     rcx, [rbp+arg_10]; hKey
0x18006cee8  call    cs:__imp_RegCloseKey
0x18006ceee  mov     rcx, [rbp+arg_18]; hKey
0x18006cef2  call    cs:__imp_RegCloseKey
0x18006cef8  mov     rcx, [rbp+hKey]; hKey
0x18006cefc  call    cs:__imp_RegCloseKey
0x18006cf02  mov     rcx, r14; hToken
0x18006cf05  call    cs:__imp_ImpersonatePrinterClient
0x18006cf0b  mov     rbx, [rsp+60h+arg_0]
0x18006cf13  mov     eax, edi
0x18006cf15  add     rsp, 60h
0x18006cf19  pop     r15
0x18006cf1b  pop     r14
0x18006cf1d  pop     rdi
0x18006cf1e  pop     rsi
0x18006cf1f  pop     rbp
0x18006cf20  retn
```
