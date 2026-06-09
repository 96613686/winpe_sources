# CPUGroupInfo::InitCPUGroupInfoAPI(void)

- ea: `0x180078ff0`
- end: `0x1800790aa`
- name: `?InitCPUGroupInfoAPI@CPUGroupInfo@@CAHXZ`
- size: `186`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180079260`

## callees

- `0x180078ff0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180078ffd`
- `KERNEL32!GetModuleHandleW` at `0x180078ffd`
- `KERNEL32!GetProcAddress` at `0x180079019`
- `KERNEL32!GetProcAddress` at `0x180079035`
- `KERNEL32!GetProcAddress` at `0x180079051`
- `KERNEL32!GetProcAddress` at `0x18007906d`
- `KERNEL32!GetProcAddress` at `0x180079089`
- `KERNEL32!GetProcAddress` at `0x180079019`
- `KERNEL32!GetProcAddress` at `0x180079035`
- `KERNEL32!GetProcAddress` at `0x180079051`
- `KERNEL32!GetProcAddress` at `0x18007906d`
- `KERNEL32!GetProcAddress` at `0x180079089`

## string_xrefs

- `0x18007902b`: `SetThreadGroupAffinity`
- `0x180079047`: `GetThreadGroupAffinity`

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
0x180078ff0  push    rbx
0x180078ff2  sub     rsp, 20h
0x180078ff6  lea     rcx, aKernel32; "kernel32"
0x180078ffd  call    cs:__imp_GetModuleHandleW
0x180079003  mov     rbx, rax
0x180079006  test    rax, rax
0x180079009  jz      loc_1800790A2
0x18007900f  lea     rdx, aGetlogicalproc; "GetLogicalProcessorInformationEx"
0x180079016  mov     rcx, rax; hModule
0x180079019  call    cs:__imp_GetProcAddress
0x18007901f  mov     cs:?m_pGetLogicalProcessorInformationEx@CPUGroupInfo@@0P6AHKPEAU_SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX@@PEAK@ZEA, rax; int (*CPUGroupInfo::m_pGetLogicalProcessorInformationEx)(ulong,_SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *,ulong *)
0x180079026  test    rax, rax
0x180079029  jz      short loc_1800790A2
0x18007902b  lea     rdx, aSetthreadgroup; "SetThreadGroupAffinity"
0x180079032  mov     rcx, rbx; hModule
0x180079035  call    cs:__imp_GetProcAddress
0x18007903b  mov     cs:?m_pSetThreadGroupAffinity@CPUGroupInfo@@0P6AHPEAXPEAU_GROUP_AFFINITY@@1@ZEA, rax; int (*CPUGroupInfo::m_pSetThreadGroupAffinity)(void *,_GROUP_AFFINITY *,_GROUP_AFFINITY *)
0x180079042  test    rax, rax
0x180079045  jz      short loc_1800790A2
0x180079047  lea     rdx, aGetthreadgroup; "GetThreadGroupAffinity"
0x18007904e  mov     rcx, rbx; hModule
0x180079051  call    cs:__imp_GetProcAddress
0x180079057  mov     cs:?m_pGetThreadGroupAffinity@CPUGroupInfo@@0P6AHPEAXPEAU_GROUP_AFFINITY@@@ZEA, rax; int (*CPUGroupInfo::m_pGetThreadGroupAffinity)(void *,_GROUP_AFFINITY *)
0x18007905e  test    rax, rax
0x180079061  jz      short loc_1800790A2
0x180079063  lea     rdx, aGetcurrentproc; "GetCurrentProcessorNumberEx"
0x18007906a  mov     rcx, rbx; hModule
0x18007906d  call    cs:__imp_GetProcAddress
0x180079073  mov     cs:?m_pGetCurrentProcessorNumberEx@CPUGroupInfo@@0P6AXPEAU_PROCESSOR_NUMBER@@@ZEA, rax; void (*CPUGroupInfo::m_pGetCurrentProcessorNumberEx)(_PROCESSOR_NUMBER *)
0x18007907a  test    rax, rax
0x18007907d  jz      short loc_1800790A2
0x18007907f  lea     rdx, aGetsystemtimes; "GetSystemTimes"
0x180079086  mov     rcx, rbx; hModule
0x180079089  call    cs:__imp_GetProcAddress
0x18007908f  mov     cs:?m_pGetSystemTimes@CPUGroupInfo@@0P6AHPEAU_FILETIME@@00@ZEA, rax; int (*CPUGroupInfo::m_pGetSystemTimes)(_FILETIME *,_FILETIME *,_FILETIME *)
0x180079096  test    rax, rax
0x180079099  jz      short loc_1800790A2
0x18007909b  mov     eax, 1
0x1800790a0  jmp     short loc_1800790A4
0x1800790a2  xor     eax, eax
0x1800790a4  add     rsp, 20h
0x1800790a8  pop     rbx
0x1800790a9  retn
```
