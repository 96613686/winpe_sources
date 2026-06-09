# SrvRundownContext

- ea: `0x18000a5c0`
- end: `0x18000a62f`
- name: `SrvRundownContext`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180006104`

## callees

- `0x180002630`
- `0x180007088`
- `0x180008dfc`
- `0x1800099d8`
- `0x18000a5c0`
- `0x18000a6cc`
- `0x18000a89c`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000a5ea`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a5f7`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a601`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a60e`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a5ea`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a5f7`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a601`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a60e`

## pseudocode

```c
void __fastcall SrvRundownContext(__int64 a1)
{
  SrvRundownKeyList();
  SrvRundownSecretList(a1);
  SrvRundownMemoryBufferList(a1);
  SrvRundownProviderList(a1);
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 168));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 40));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 232));
  if ( (unsigned int)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline() )
    FreeKeyIsoPerfCounterInstance(*(PPERF_COUNTERSET_INSTANCE *)(a1 + 296));
}

```

## disassembly

```asm
0x18000a5c0  push    rbx
0x18000a5c2  sub     rsp, 20h
0x18000a5c6  mov     rbx, rcx
0x18000a5c9  call    SrvRundownKeyList
0x18000a5ce  mov     rcx, rbx
0x18000a5d1  call    SrvRundownSecretList
0x18000a5d6  mov     rcx, rbx
0x18000a5d9  call    SrvRundownMemoryBufferList
0x18000a5de  mov     rcx, rbx
0x18000a5e1  call    SrvRundownProviderList
0x18000a5e6  lea     rcx, [rbx+68h]; CriticalSection
0x18000a5ea  call    cs:__imp_RtlDeleteCriticalSection
0x18000a5f0  lea     rcx, [rbx+0A8h]; CriticalSection
0x18000a5f7  call    cs:__imp_RtlDeleteCriticalSection
0x18000a5fd  lea     rcx, [rbx+28h]; CriticalSection
0x18000a601  call    cs:__imp_RtlDeleteCriticalSection
0x18000a607  lea     rcx, [rbx+0E8h]; CriticalSection
0x18000a60e  call    cs:__imp_RtlDeleteCriticalSection
0x18000a614  call    Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline
0x18000a619  test    eax, eax
0x18000a61b  jz      short loc_18000A629
0x18000a61d  mov     rcx, [rbx+128h]; InstanceBlock
0x18000a624  call    FreeKeyIsoPerfCounterInstance
0x18000a629  add     rsp, 20h
0x18000a62d  pop     rbx
0x18000a62e  retn
```
