# CreateKeyIsoPerfCounterInstance

- ea: `0x18000a3c8`
- end: `0x18000a47b`
- name: `CreateKeyIsoPerfCounterInstance`
- size: `179`
- prototype: `PPERF_COUNTERSET_INSTANCE __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a268`

## callees

- `0x180003cf0`
- `0x18000a3c8`
- `0x18000d10c`
- `0x180018950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a446`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18000a438`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18000a438`

## string_xrefs

- `0x18000a459`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\perfcounters.c`

## pseudocode

```c
PPERF_COUNTERSET_INSTANCE __fastcall CreateKeyIsoPerfCounterInstance(unsigned int a1)
{
  PPERF_COUNTERSET_INSTANCE Instance; // rbx
  __int64 v2; // r9
  const char *v3; // rdx
  __int64 LastError; // rcx
  wchar_t Buffer[12]; // [rsp+20h] [rbp-28h] BYREF

  Instance = 0;
  if ( dword_180025A30 )
  {
    if ( swprintf_s(Buffer, 0xBu, L"%u", a1) < 1 )
    {
      v2 = 83;
      v3 = "ERROR_INVALID_DATA";
      LastError = 13;
LABEL_6:
      DebugTraceError(LastError, v3, "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\perfcounters.c", v2);
      return Instance;
    }
    Instance = PerfCreateInstance(
                 KeyIsoPerfCounterProvider,
                 &KeyIsoClientPerfCountersGuid,
                 Buffer,
                 _InterlockedIncrement(&dword_180025A34));
    if ( !Instance )
    {
      LastError = GetLastError();
      v2 = 96;
      v3 = "GetLastError()";
      goto LABEL_6;
    }
  }
  return Instance;
}

```

## disassembly

```asm
0x18000a3c8  push    rbx
0x18000a3ca  sub     rsp, 40h
0x18000a3ce  mov     rax, cs:__security_cookie
0x18000a3d5  xor     rax, rsp
0x18000a3d8  mov     [rsp+48h+var_10], rax
0x18000a3dd  xor     ebx, ebx
0x18000a3df  cmp     cs:dword_180025A30, ebx
0x18000a3e5  jz      short loc_18000A465
0x18000a3e7  mov     r9d, ecx
0x18000a3ea  lea     r8, aU; "%u"
0x18000a3f1  lea     rcx, [rsp+48h+Buffer]; Buffer
0x18000a3f6  lea     edx, [rbx+0Bh]; BufferCount
0x18000a3f9  call    swprintf_s
0x18000a3fe  cmp     eax, 1
0x18000a401  jge     short loc_18000A413
0x18000a403  lea     r9d, [rbx+53h]
0x18000a407  lea     rdx, aErrorInvalidDa; "ERROR_INVALID_DATA"
0x18000a40e  lea     ecx, [rbx+0Dh]
0x18000a411  jmp     short loc_18000A459
0x18000a413  mov     r9d, 1
0x18000a419  lock xadd cs:dword_180025A34, r9d
0x18000a422  mov     rcx, cs:KeyIsoPerfCounterProvider; ProviderHandle
0x18000a429  lea     r8, [rsp+48h+Buffer]; Name
0x18000a42e  inc     r9d; Id
0x18000a431  lea     rdx, KeyIsoClientPerfCountersGuid; CounterSetGuid
0x18000a438  call    cs:__imp_PerfCreateInstance
0x18000a43e  mov     rbx, rax
0x18000a441  test    rax, rax
0x18000a444  jnz     short loc_18000A465
0x18000a446  call    cs:__imp_GetLastError
0x18000a44c  mov     ecx, eax
0x18000a44e  lea     r9d, [rbx+60h]
0x18000a452  lea     rdx, aGetlasterror; "GetLastError()"
0x18000a459  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a460  call    DebugTraceError
0x18000a465  mov     rax, rbx
0x18000a468  mov     rcx, [rsp+48h+var_10]
0x18000a46d  xor     rcx, rsp; StackCookie
0x18000a470  call    __security_check_cookie
0x18000a475  add     rsp, 40h
0x18000a479  pop     rbx
0x18000a47a  retn
```
