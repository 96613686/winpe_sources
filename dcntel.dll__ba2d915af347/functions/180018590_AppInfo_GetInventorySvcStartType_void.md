# AppInfo::GetInventorySvcStartType(void)

- ea: `0x180018590`
- end: `0x18001873f`
- name: `?GetInventorySvcStartType@AppInfo@@QEBAIXZ`
- size: `431`
- prototype: `unsigned int __fastcall(AppInfo *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180018590`
- `0x18016796c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001865f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001865f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186e8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180018640`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001868e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180018722`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001872c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180018640`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001868e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180018722`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001872c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180018600`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180018600`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800185b0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800185b0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180018655`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800186de`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180018655`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800186de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018718`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001869e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001869e`

## string_xrefs

- `0x1800185d0`: `OpenSCManager failed [%d]`
- `0x180018620`: `OpenService failed [%d]`
- `0x18001866e`: `QueryServiceConfig failed [%d]`
- `0x1800186f2`: `QueryServiceConfig failed [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppInfo::GetInventorySvcStartType(AppInfo *this)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rbx
  DWORD LastError; // eax
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD v9; // ebp
  struct _QUERY_SERVICE_CONFIGW *v10; // rax
  struct _QUERY_SERVICE_CONFIGW *v11; // rsi
  DWORD v12; // eax
  unsigned int dwServiceType; // ebp
  DWORD pcbBytesNeeded; // [rsp+78h] [rbp+10h] BYREF
  SC_HANDLE v15; // [rsp+80h] [rbp+18h]
  SC_HANDLE v16; // [rsp+88h] [rbp+20h]

  pcbBytesNeeded = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  v15 = v1;
  if ( !v1 )
  {
    LastError = GetLastError();
    AslLogCallPrintf(1, "AppInfo::GetInventorySvcStartType", 123, "OpenSCManager failed [%d]", LastError);
    return 0xFFFFFFFFLL;
  }
  v5 = OpenServiceW(v1, L"InventorySvc", 1u);
  v6 = v5;
  v16 = v5;
  if ( !v5 )
  {
    v7 = GetLastError();
    AslLogCallPrintf(1, "AppInfo::GetInventorySvcStartType", 131, "OpenService failed [%d]", v7);
LABEL_6:
    CloseServiceHandle(v2);
    return 0xFFFFFFFFLL;
  }
  if ( !QueryServiceConfigW(v5, 0, 0, &pcbBytesNeeded) )
  {
    v8 = GetLastError();
    if ( v8 != 122 )
    {
      AslLogCallPrintf(1, "AppInfo::GetInventorySvcStartType", 140, "QueryServiceConfig failed [%d]", v8);
LABEL_10:
      CloseServiceHandle(v6);
      goto LABEL_6;
    }
  }
  v9 = pcbBytesNeeded;
  v10 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0, pcbBytesNeeded);
  v11 = v10;
  if ( !v10 )
  {
    AslLogCallPrintf(1, "AppInfo::GetInventorySvcStartType", 149, "LocalAlloc failed");
    goto LABEL_10;
  }
  if ( QueryServiceConfigW(v6, v10, v9, &pcbBytesNeeded) )
  {
    dwServiceType = v11->dwServiceType;
  }
  else
  {
    v12 = GetLastError();
    AslLogCallPrintf(1, "AppInfo::GetInventorySvcStartType", 155, "QueryServiceConfig failed [%d]", v12);
    dwServiceType = -1;
  }
  LocalFree(v11);
  CloseServiceHandle(v6);
  CloseServiceHandle(v2);
  return dwServiceType;
}

```

## disassembly

```asm
0x180018590  push    rbx
0x180018592  push    rbp
0x180018593  push    rsi
0x180018594  push    rdi
0x180018595  push    r14
0x180018597  sub     rsp, 40h
0x18001859b  mov     [rsp+68h+pcbBytesNeeded], 0
0x1800185a3  mov     r14d, 1
0x1800185a9  mov     r8d, r14d; dwDesiredAccess
0x1800185ac  xor     edx, edx; lpDatabaseName
0x1800185ae  xor     ecx, ecx; lpMachineName
0x1800185b0  call    cs:__imp_OpenSCManagerW
0x1800185b6  mov     rbx, rax
0x1800185b9  mov     [rsp+68h+arg_10], rax
0x1800185c1  test    rax, rax
0x1800185c4  jnz     short loc_1800185F3
0x1800185c6  call    cs:__imp_GetLastError
0x1800185cc  mov     [rsp+68h+var_48], eax
0x1800185d0  lea     r9, aOpenscmanagerF; "OpenSCManager failed [%d]"
0x1800185d7  lea     r8d, [r14+7Ah]
0x1800185db  lea     rdx, aAppinfoGetinve; "AppInfo::GetInventorySvcStartType"
0x1800185e2  mov     ecx, r14d
0x1800185e5  call    AslLogCallPrintf
0x1800185ea  nop
0x1800185eb  or      eax, 0FFFFFFFFh
0x1800185ee  jmp     loc_180018734
0x1800185f3  mov     r8d, r14d; dwDesiredAccess
0x1800185f6  lea     rdx, ServiceName; "InventorySvc"
0x1800185fd  mov     rcx, rbx; hSCManager
0x180018600  call    cs:__imp_OpenServiceW
0x180018606  mov     rdi, rax
0x180018609  mov     [rsp+68h+arg_18], rax
0x180018611  test    rax, rax
0x180018614  jnz     short loc_180018648
0x180018616  call    cs:__imp_GetLastError
0x18001861c  mov     [rsp+68h+var_48], eax
0x180018620  lea     r9, aOpenserviceFai; "OpenService failed [%d]"
0x180018627  mov     r8d, 83h
0x18001862d  lea     rdx, aAppinfoGetinve; "AppInfo::GetInventorySvcStartType"
0x180018634  mov     ecx, r14d
0x180018637  call    AslLogCallPrintf
0x18001863c  nop
0x18001863d  mov     rcx, rbx; hSCObject
0x180018640  call    cs:__imp_CloseServiceHandle
0x180018646  jmp     short loc_1800185EB
0x180018648  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x18001864d  xor     r8d, r8d; cbBufSize
0x180018650  xor     edx, edx; lpServiceConfig
0x180018652  mov     rcx, rdi; hService
0x180018655  call    cs:__imp_QueryServiceConfigW
0x18001865b  test    eax, eax
0x18001865d  jnz     short loc_180018696
0x18001865f  call    cs:__imp_GetLastError
0x180018665  cmp     eax, 7Ah ; 'z'
0x180018668  jz      short loc_180018696
0x18001866a  mov     [rsp+68h+var_48], eax
0x18001866e  lea     r9, aQueryserviceco; "QueryServiceConfig failed [%d]"
0x180018675  mov     r8d, 8Ch
0x18001867b  lea     rdx, aAppinfoGetinve; "AppInfo::GetInventorySvcStartType"
0x180018682  mov     ecx, r14d
0x180018685  call    AslLogCallPrintf
0x18001868a  nop
0x18001868b  mov     rcx, rdi; hSCObject
0x18001868e  call    cs:__imp_CloseServiceHandle
0x180018694  jmp     short loc_18001863D
0x180018696  mov     ebp, [rsp+68h+pcbBytesNeeded]
0x18001869a  mov     edx, ebp; uBytes
0x18001869c  xor     ecx, ecx; uFlags
0x18001869e  call    cs:__imp_LocalAlloc
0x1800186a4  mov     rsi, rax
0x1800186a7  mov     [rsp+68h+var_38], rax
0x1800186ac  test    rax, rax
0x1800186af  jnz     short loc_1800186D0
0x1800186b1  lea     r9, aLocalallocFail; "LocalAlloc failed"
0x1800186b8  mov     r8d, 95h
0x1800186be  lea     rdx, aAppinfoGetinve; "AppInfo::GetInventorySvcStartType"
0x1800186c5  mov     ecx, r14d
0x1800186c8  call    AslLogCallPrintf
0x1800186cd  nop
0x1800186ce  jmp     short loc_18001868B
0x1800186d0  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x1800186d5  mov     r8d, ebp; cbBufSize
0x1800186d8  mov     rdx, rsi; lpServiceConfig
0x1800186db  mov     rcx, rdi; hService
0x1800186de  call    cs:__imp_QueryServiceConfigW
0x1800186e4  test    eax, eax
0x1800186e6  jnz     short loc_180018713
0x1800186e8  call    cs:__imp_GetLastError
0x1800186ee  mov     [rsp+68h+var_48], eax
0x1800186f2  lea     r9, aQueryserviceco; "QueryServiceConfig failed [%d]"
0x1800186f9  mov     r8d, 9Bh
0x1800186ff  lea     rdx, aAppinfoGetinve; "AppInfo::GetInventorySvcStartType"
0x180018706  mov     ecx, r14d
0x180018709  call    AslLogCallPrintf
0x18001870e  or      ebp, 0FFFFFFFFh
0x180018711  jmp     short loc_180018715
0x180018713  mov     ebp, [rsi]
0x180018715  mov     rcx, rsi; hMem
0x180018718  call    cs:__imp_LocalFree
0x18001871e  nop
0x18001871f  mov     rcx, rdi; hSCObject
0x180018722  call    cs:__imp_CloseServiceHandle
0x180018728  nop
0x180018729  mov     rcx, rbx; hSCObject
0x18001872c  call    cs:__imp_CloseServiceHandle
0x180018732  mov     eax, ebp
0x180018734  add     rsp, 40h
0x180018738  pop     r14
0x18001873a  pop     rdi
0x18001873b  pop     rsi
0x18001873c  pop     rbp
0x18001873d  pop     rbx
0x18001873e  retn
```
