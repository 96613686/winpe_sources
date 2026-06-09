# CPUGroupInfo::InitCPUGroupInfoAPI(void)

- ea: `0x180035c88`
- end: `0x180035d42`
- name: `?InitCPUGroupInfoAPI@CPUGroupInfo@@CAHXZ`
- size: `186`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180035ef8`

## callees

- `0x180035c88`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180035c95`
- `KERNEL32!GetModuleHandleW` at `0x180035c95`
- `KERNEL32!GetProcAddress` at `0x180035cb1`
- `KERNEL32!GetProcAddress` at `0x180035ccd`
- `KERNEL32!GetProcAddress` at `0x180035ce9`
- `KERNEL32!GetProcAddress` at `0x180035d05`
- `KERNEL32!GetProcAddress` at `0x180035d21`
- `KERNEL32!GetProcAddress` at `0x180035cb1`
- `KERNEL32!GetProcAddress` at `0x180035ccd`
- `KERNEL32!GetProcAddress` at `0x180035ce9`
- `KERNEL32!GetProcAddress` at `0x180035d05`
- `KERNEL32!GetProcAddress` at `0x180035d21`

## string_xrefs

- `0x180035cc3`: `SetThreadGroupAffinity`
- `0x180035cdf`: `GetThreadGroupAffinity`

## pseudocode

```c
_BOOL8 CPUGroupInfo::InitCPUGroupInfoAPI(void)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rbx
  _BOOL8 result; // rax

  ModuleHandleW = GetModuleHandleW(L"kernel32");
  v1 = ModuleHandleW;
  result = 0;
  if ( ModuleHandleW )
  {
    CPUGroupInfo::m_pGetLogicalProcessorInformationEx = (int (*)(unsigned int, struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *, unsigned int *))GetProcAddress(ModuleHandleW, "GetLogicalProcessorInformationEx");
    if ( CPUGroupInfo::m_pGetLogicalProcessorInformationEx )
    {
      CPUGroupInfo::m_pSetThreadGroupAffinity = (int (*)(void *, struct _GROUP_AFFINITY *, struct _GROUP_AFFINITY *))GetProcAddress(v1, "SetThreadGroupAffinity");
      if ( CPUGroupInfo::m_pSetThreadGroupAffinity )
      {
        CPUGroupInfo::m_pGetThreadGroupAffinity = (int (*)(void *, struct _GROUP_AFFINITY *))GetProcAddress(
                                                                                               v1,
                                                                                               "GetThreadGroupAffinity");
        if ( CPUGroupInfo::m_pGetThreadGroupAffinity )
        {
          CPUGroupInfo::m_pGetCurrentProcessorNumberEx = (void (*)(struct _PROCESSOR_NUMBER *))GetProcAddress(
                                                                                                 v1,
                                                                                                 "GetCurrentProcessorNumberEx");
          if ( CPUGroupInfo::m_pGetCurrentProcessorNumberEx )
          {
            CPUGroupInfo::m_pGetSystemTimes = (int (*)(struct _FILETIME *, struct _FILETIME *, struct _FILETIME *))GetProcAddress(v1, "GetSystemTimes");
            if ( CPUGroupInfo::m_pGetSystemTimes )
              return 1;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180035c88  push    rbx
0x180035c8a  sub     rsp, 20h
0x180035c8e  lea     rcx, aKernel32; "kernel32"
0x180035c95  call    cs:__imp_GetModuleHandleW
0x180035c9b  mov     rbx, rax
0x180035c9e  test    rax, rax
0x180035ca1  jz      loc_180035D3A
0x180035ca7  lea     rdx, aGetlogicalproc; "GetLogicalProcessorInformationEx"
0x180035cae  mov     rcx, rax; hModule
0x180035cb1  call    cs:__imp_GetProcAddress
0x180035cb7  mov     cs:?m_pGetLogicalProcessorInformationEx@CPUGroupInfo@@0P6AHKPEAU_SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX@@PEAK@ZEA, rax; int (*CPUGroupInfo::m_pGetLogicalProcessorInformationEx)(ulong,_SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *,ulong *)
0x180035cbe  test    rax, rax
0x180035cc1  jz      short loc_180035D3A
0x180035cc3  lea     rdx, aSetthreadgroup; "SetThreadGroupAffinity"
0x180035cca  mov     rcx, rbx; hModule
0x180035ccd  call    cs:__imp_GetProcAddress
0x180035cd3  mov     cs:?m_pSetThreadGroupAffinity@CPUGroupInfo@@0P6AHPEAXPEAU_GROUP_AFFINITY@@1@ZEA, rax; int (*CPUGroupInfo::m_pSetThreadGroupAffinity)(void *,_GROUP_AFFINITY *,_GROUP_AFFINITY *)
0x180035cda  test    rax, rax
0x180035cdd  jz      short loc_180035D3A
0x180035cdf  lea     rdx, aGetthreadgroup; "GetThreadGroupAffinity"
0x180035ce6  mov     rcx, rbx; hModule
0x180035ce9  call    cs:__imp_GetProcAddress
0x180035cef  mov     cs:?m_pGetThreadGroupAffinity@CPUGroupInfo@@0P6AHPEAXPEAU_GROUP_AFFINITY@@@ZEA, rax; int (*CPUGroupInfo::m_pGetThreadGroupAffinity)(void *,_GROUP_AFFINITY *)
0x180035cf6  test    rax, rax
0x180035cf9  jz      short loc_180035D3A
0x180035cfb  lea     rdx, aGetcurrentproc; "GetCurrentProcessorNumberEx"
0x180035d02  mov     rcx, rbx; hModule
0x180035d05  call    cs:__imp_GetProcAddress
0x180035d0b  mov     cs:?m_pGetCurrentProcessorNumberEx@CPUGroupInfo@@0P6AXPEAU_PROCESSOR_NUMBER@@@ZEA, rax; void (*CPUGroupInfo::m_pGetCurrentProcessorNumberEx)(_PROCESSOR_NUMBER *)
0x180035d12  test    rax, rax
0x180035d15  jz      short loc_180035D3A
0x180035d17  lea     rdx, aGetsystemtimes; "GetSystemTimes"
0x180035d1e  mov     rcx, rbx; hModule
0x180035d21  call    cs:__imp_GetProcAddress
0x180035d27  mov     cs:?m_pGetSystemTimes@CPUGroupInfo@@0P6AHPEAU_FILETIME@@00@ZEA, rax; int (*CPUGroupInfo::m_pGetSystemTimes)(_FILETIME *,_FILETIME *,_FILETIME *)
0x180035d2e  test    rax, rax
0x180035d31  jz      short loc_180035D3A
0x180035d33  mov     eax, 1
0x180035d38  jmp     short loc_180035D3C
0x180035d3a  xor     eax, eax
0x180035d3c  add     rsp, 20h
0x180035d40  pop     rbx
0x180035d41  retn
```
