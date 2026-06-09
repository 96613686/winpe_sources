# SrvRundownMemoryBuffer

- ea: `0x18000a1dc`
- end: `0x18000a262`
- name: `SrvRundownMemoryBuffer`
- size: `134`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800099d8`
- `0x18000eb40`

## callees

- `0x180003cf0`
- `0x180005510`
- `0x180006280`
- `0x18000a1dc`
- `0x18000a6cc`
- `0x18000a8e8`
- `0x180019010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000a24a`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a24a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a241`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a241`

## string_xrefs

- `0x18000a229`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
__int64 __fastcall SrvRundownMemoryBuffer(PRTL_CRITICAL_SECTION CriticalSection)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdi
  int v3; // eax

  DebugInfo = CriticalSection[1].DebugInfo;
  (*(void (__fastcall **)(_QWORD))&DebugInfo[2].Flags)(*(_QWORD *)&CriticalSection[1].LockCount);
  if ( (unsigned int)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline() )
    DecrementKeyIsoPerfCounter(*(PPERF_COUNTERSET_INSTANCE *)&DebugInfo[7].EntryCount, 4u);
  v3 = SrvDereferenceProvider(DebugInfo);
  if ( v3 < 0 )
    DebugTraceError(
      (unsigned int)v3,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
      170);
  RtlLeaveCriticalSection(CriticalSection);
  RtlDeleteCriticalSection(CriticalSection);
  return MSCryptFree(CriticalSection);
}

```

## disassembly

```asm
0x18000a1dc  mov     [rsp+arg_0], rbx
0x18000a1e1  push    rdi
0x18000a1e2  sub     rsp, 20h
0x18000a1e6  mov     rdi, [rcx+28h]
0x18000a1ea  mov     rbx, rcx
0x18000a1ed  mov     rcx, [rcx+30h]
0x18000a1f1  mov     rax, [rdi+88h]
0x18000a1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1fd  call    Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline
0x18000a202  test    eax, eax
0x18000a204  jz      short loc_18000A217
0x18000a206  mov     rcx, [rdi+170h]; Instance
0x18000a20d  mov     edx, 4; CounterId
0x18000a212  call    DecrementKeyIsoPerfCounter
0x18000a217  mov     rcx, rdi
0x18000a21a  call    SrvDereferenceProvider
0x18000a21f  test    eax, eax
0x18000a221  jns     short loc_18000A23E
0x18000a223  mov     r9d, 0AAh
0x18000a229  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a230  lea     rdx, aStatus; "Status"
0x18000a237  mov     ecx, eax
0x18000a239  call    DebugTraceError
0x18000a23e  mov     rcx, rbx; CriticalSection
0x18000a241  call    cs:__imp_RtlLeaveCriticalSection
0x18000a247  mov     rcx, rbx; CriticalSection
0x18000a24a  call    cs:__imp_RtlDeleteCriticalSection
0x18000a250  mov     rcx, rbx
0x18000a253  mov     rbx, [rsp+28h+arg_0]
0x18000a258  add     rsp, 20h
0x18000a25c  pop     rdi
0x18000a25d  jmp     MSCryptFree
```
