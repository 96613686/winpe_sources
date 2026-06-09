# AddToMessageLog

- ea: `0x18000f51c`
- end: `0x18000f603`
- name: `AddToMessageLog`
- size: `231`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009bf0`
- `0x18000b324`

## callees

- `0x18000c798`
- `0x18000e2f0`
- `0x18000f51c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f535`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x18000f5da`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x18000f5da`
- `ntdll!EtwEventUnregister` at `0x18000f5e5`
- `ntdll!EtwEventUnregister` at `0x18000f5e5`
- `ntdll!EtwEventRegister` at `0x18000f598`
- `ntdll!EtwEventRegister` at `0x18000f598`

## string_xrefs

- `0x18000f583`: `SetServiceStatus`

## pseudocode

```c
__int64 AddToMessageLog()
{
  __int64 result; // rax
  DWORD LastError; // [rsp+20h] [rbp-468h]
  __int64 v2; // [rsp+50h] [rbp-438h] BYREF
  __int128 v3; // [rsp+58h] [rbp-430h]
  unsigned __int16 v4[512]; // [rsp+70h] [rbp-418h] BYREF

  v2 = 0;
  LastError = GetLastError();
  v3 = 0;
  result = StringCchPrintfW(v4, 0x200u, L"%s error: %lu", L"CryptSvc", LastError);
  if ( (int)result >= 0 )
  {
    *(_QWORD *)&v3 = v4;
    *((_QWORD *)&v3 + 1) = L"SetServiceStatus";
    result = EtwEventRegister(CAPI2_PROVIDER, 0, 0, &v2);
    if ( !(_DWORD)result )
    {
      EvtIntReportEventAndSourceAsync(v2, L"Microsoft-Windows-CAPI2", 1);
      return EtwEventUnregister(v2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f51c  sub     rsp, 488h
0x18000f523  mov     rax, cs:__security_cookie
0x18000f52a  xor     rax, rsp
0x18000f52d  mov     [rsp+488h+var_18], rax
0x18000f535  call    cs:__imp_GetLastError
0x18000f53b  xorps   xmm0, xmm0
0x18000f53e  mov     [rsp+488h+var_438], 0
0x18000f547  lea     r9, ServiceName; "CryptSvc"
0x18000f54e  mov     [rsp+488h+var_468], eax
0x18000f552  lea     r8, aSErrorLu; "%s error: %lu"
0x18000f559  mov     edx, 200h; unsigned __int64
0x18000f55e  lea     rcx, [rsp+488h+var_418]; unsigned __int16 *
0x18000f563  movups  [rsp+488h+var_430], xmm0
0x18000f568  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f56d  test    eax, eax
0x18000f56f  js      short loc_18000F5EB
0x18000f571  lea     rax, [rsp+488h+var_418]
0x18000f576  xor     r8d, r8d
0x18000f579  mov     qword ptr [rsp+488h+var_430], rax
0x18000f57e  lea     r9, [rsp+488h+var_438]
0x18000f583  lea     rax, aSetservicestat_0; "SetServiceStatus"
0x18000f58a  xor     edx, edx
0x18000f58c  lea     rcx, CAPI2_PROVIDER
0x18000f593  mov     qword ptr [rsp+488h+var_430+8], rax
0x18000f598  call    cs:__imp_EtwEventRegister
0x18000f59e  test    eax, eax
0x18000f5a0  jnz     short loc_18000F5EB
0x18000f5a2  mov     rcx, [rsp+488h+var_438]
0x18000f5a7  lea     r8d, [rax+1]
0x18000f5ab  xor     r9d, r9d
0x18000f5ae  lea     rax, [rsp+488h+var_430]
0x18000f5b3  mov     [rsp+488h+var_440], r9
0x18000f5b8  lea     rdx, aMicrosoftWindo; "Microsoft-Windows-CAPI2"
0x18000f5bf  mov     [rsp+488h+var_448], rax
0x18000f5c4  mov     [rsp+488h+var_450], r9d
0x18000f5c9  mov     [rsp+488h+var_458], 2
0x18000f5d0  mov     [rsp+488h+var_460], r9
0x18000f5d5  mov     [rsp+488h+var_468], r9d
0x18000f5da  call    cs:__imp_EvtIntReportEventAndSourceAsync
0x18000f5e0  mov     rcx, [rsp+488h+var_438]
0x18000f5e5  call    cs:__imp_EtwEventUnregister
0x18000f5eb  mov     rcx, [rsp+488h+var_18]
0x18000f5f3  xor     rcx, rsp; StackCookie
0x18000f5f6  call    __security_check_cookie
0x18000f5fb  add     rsp, 488h
0x18000f602  retn
```
