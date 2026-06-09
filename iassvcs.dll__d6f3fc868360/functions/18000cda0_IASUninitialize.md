# IASUninitialize

- ea: `0x18000cda0`
- end: `0x18000ce82`
- name: `IASUninitialize`
- size: `226`
- prototype: `void()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000cd50`
- `0x18000cda0`
- `0x180017698`
- `0x180019010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000cdf4`
- `KERNEL32!CloseHandle` at `0x18000ce0c`
- `KERNEL32!CloseHandle` at `0x18000ce24`
- `KERNEL32!CloseHandle` at `0x18000cdf4`
- `KERNEL32!CloseHandle` at `0x18000ce0c`
- `KERNEL32!CloseHandle` at `0x18000ce24`
- `KERNEL32!WaitForSingleObject` at `0x18000cdd2`
- `KERNEL32!WaitForSingleObject` at `0x18000cde7`
- `KERNEL32!WaitForSingleObject` at `0x18000cdd2`
- `KERNEL32!WaitForSingleObject` at `0x18000cde7`
- `KERNEL32!EnterCriticalSection` at `0x18000cdab`
- `KERNEL32!EnterCriticalSection` at `0x18000cdab`
- `KERNEL32!LeaveCriticalSection` at `0x18000ce7b`
- `OLEAUT32!__imp_VariantClear` at `0x18000ce60`
- `OLEAUT32!__imp_VariantClear` at `0x18000ce60`
- `WS2_32!__imp_WSACleanup` at `0x18000ce35`
- `WS2_32!__imp_WSACleanup` at `0x18000ce35`

## pseudocode

```c
void IASUninitialize()
{
  Dispatcher *v0; // rcx
  HANDLE v1; // rcx

  EnterCriticalSection(&theGlobalLock);
  if ( !--refCount )
  {
    IASShutdown();
    Dispatcher::shutdown(v0);
    WaitForSingleObject(hHandle, 0xFFFFFFFF);
    v1 = hObject;
    if ( hObject )
    {
      WaitForSingleObject(hObject, 0xFFFFFFFF);
      v1 = hObject;
    }
    CloseHandle(v1);
    hObject = 0;
    CloseHandle(hHandle);
    hHandle = 0;
    CloseHandle(CompletionPort);
    CompletionPort = 0;
    WSACleanup();
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pAuditChannel + 16LL))(pAuditChannel);
    pAuditChannel = 0;
    VariantClear(&theDictionaryStorage);
    shutdownInProgress = 0;
  }
  LeaveCriticalSection(&theGlobalLock);
}

```

## disassembly

```asm
0x18000cda0  sub     rsp, 28h
0x18000cda4  lea     rcx, ?theGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000cdab  call    cs:__imp_EnterCriticalSection
0x18000cdb1  sub     cs:?refCount@@3JA, 1; long refCount
0x18000cdb8  jnz     loc_18000CE70
0x18000cdbe  call    IASShutdown
0x18000cdc3  call    ?shutdown@Dispatcher@@QEAAXXZ; Dispatcher::shutdown(void)
0x18000cdc8  mov     rcx, cs:hHandle; hHandle
0x18000cdcf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000cdd2  call    cs:__imp_WaitForSingleObject
0x18000cdd8  mov     rcx, cs:hObject; hHandle
0x18000cddf  test    rcx, rcx
0x18000cde2  jz      short loc_18000CDF4
0x18000cde4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000cde7  call    cs:__imp_WaitForSingleObject
0x18000cded  mov     rcx, cs:hObject; hObject
0x18000cdf4  call    cs:__imp_CloseHandle
0x18000cdfa  mov     rcx, cs:hHandle; hObject
0x18000ce01  mov     cs:hObject, 0
0x18000ce0c  call    cs:__imp_CloseHandle
0x18000ce12  mov     rcx, cs:CompletionPort; hObject
0x18000ce19  mov     cs:hHandle, 0
0x18000ce24  call    cs:__imp_CloseHandle
0x18000ce2a  mov     cs:CompletionPort, 0
0x18000ce35  call    cs:__imp_WSACleanup
0x18000ce3b  mov     rcx, cs:?pAuditChannel@@3PEAUIAuditSink@@EA; IAuditSink * pAuditChannel
0x18000ce42  mov     rax, [rcx]
0x18000ce45  mov     rax, [rax+10h]
0x18000ce49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce4e  lea     rcx, ?theDictionaryStorage@@3UtagVARIANT@@A; pvarg
0x18000ce55  mov     cs:?pAuditChannel@@3PEAUIAuditSink@@EA, 0; IAuditSink * pAuditChannel
0x18000ce60  call    cs:__imp_VariantClear
0x18000ce66  mov     cs:?shutdownInProgress@@3HA, 0; int shutdownInProgress
0x18000ce70  lea     rcx, ?theGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION theGlobalLock
0x18000ce77  add     rsp, 28h
0x18000ce7b  jmp     cs:__imp_LeaveCriticalSection
```
