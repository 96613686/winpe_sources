# SrvFreeProvider

- ea: `0x180005540`
- end: `0x1800055d1`
- name: `SrvFreeProvider`
- size: `145`
- prototype: `__int64 __fastcall(char *P)`
- caller_count: `3`
- callee_count: `9`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003540`
- `0x180003880`
- `0x180005510`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180005540`
- `0x180006180`
- `0x180006a70`
- `0x180006e60`
- `0x18000a6cc`
- `0x18000a8e8`
- `0x180019010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800055b6`
- `ntdll!RtlDeleteCriticalSection` at `0x1800055b6`

## string_xrefs

- `0x18000556e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvFreeProvider(char *P)
{
  int v2; // eax
  unsigned int v3; // edi

  SrvRundownProviderNotifyEventList();
  v2 = (*((__int64 (__fastcall **)(_QWORD))P + 15))(*((_QWORD *)P + 37));
  v3 = v2;
  if ( v2 < 0 )
  {
    DebugTraceError(
      (unsigned int)v2,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
      3683);
    v3 = NormalizeNteStatus(v3);
  }
  if ( (unsigned int)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline() )
    DecrementKeyIsoPerfCounter(*((PPERF_COUNTERSET_INSTANCE *)P + 46), 1u);
  UnloadProvider(*((_QWORD *)P + 4));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(P + 304));
  SrvCryptLocalFree(P);
  return v3;
}

```

## disassembly

```asm
0x180005540  mov     [rsp+arg_0], rbx
0x180005545  push    rdi
0x180005546  sub     rsp, 20h
0x18000554a  mov     rbx, rcx
0x18000554d  call    SrvRundownProviderNotifyEventList
0x180005552  mov     rcx, [rbx+128h]
0x180005559  mov     rax, [rbx+78h]
0x18000555d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005562  mov     edi, eax
0x180005564  test    eax, eax
0x180005566  jns     short loc_18000558C
0x180005568  mov     r9d, 0E63h
0x18000556e  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005575  lea     rdx, aStatus; "Status"
0x18000557c  mov     ecx, eax
0x18000557e  call    DebugTraceError
0x180005583  mov     ecx, edi
0x180005585  call    NormalizeNteStatus
0x18000558a  mov     edi, eax
0x18000558c  call    Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline
0x180005591  test    eax, eax
0x180005593  jz      short loc_1800055A6
0x180005595  mov     rcx, [rbx+170h]; Instance
0x18000559c  mov     edx, 1; CounterId
0x1800055a1  call    DecrementKeyIsoPerfCounter
0x1800055a6  mov     rcx, [rbx+20h]
0x1800055aa  call    UnloadProvider
0x1800055af  lea     rcx, [rbx+130h]; CriticalSection
0x1800055b6  call    cs:__imp_RtlDeleteCriticalSection
0x1800055bc  mov     rcx, rbx; P
0x1800055bf  call    SrvCryptLocalFree
0x1800055c4  mov     rbx, [rsp+28h+arg_0]
0x1800055c9  mov     eax, edi
0x1800055cb  add     rsp, 20h
0x1800055cf  pop     rdi
0x1800055d0  retn
```
