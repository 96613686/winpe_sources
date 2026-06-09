# GetCurrentProcessCpuCount(void)

- ea: `0x180079350`
- end: `0x180079534`
- name: `?GetCurrentProcessCpuCount@@YAHXZ`
- size: `484`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f7ac`
- `0x180023ea8`
- `0x1800245f8`

## callees

- `0x180078a98`
- `0x180079260`
- `0x180079350`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1800793fc`
- `KERNEL32!GetCurrentProcess` at `0x1800793fc`
- `KERNEL32!QueryInformationJobObject` at `0x18007948b`
- `KERNEL32!QueryInformationJobObject` at `0x18007948b`
- `KERNEL32!GetProcessAffinityMask` at `0x18007940d`
- `KERNEL32!GetProcessAffinityMask` at `0x18007940d`
- `KERNEL32!SwitchToThread` at `0x1800793cb`
- `KERNEL32!SwitchToThread` at `0x1800794e5`
- `KERNEL32!SwitchToThread` at `0x1800793cb`
- `KERNEL32!SwitchToThread` at `0x1800794e5`

## pseudocode

```c
__int64 __fastcall GetCurrentProcessCpuCount(__int64 a1, bool a2)
{
  __int64 result; // rax
  bool v3; // dl
  unsigned int ConfigValue; // ebx
  bool v5; // dl
  HANDLE CurrentProcess; // rax
  ULONG_PTR v7; // rcx
  ULONG_PTR v8; // rcx
  int v9; // edi
  DWORD dwNumberOfProcessors; // ecx
  bool v11; // [rsp+30h] [rbp-28h] BYREF
  ULONG_PTR ProcessAffinityMask; // [rsp+38h] [rbp-20h] BYREF
  char JobObjectInformation; // [rsp+40h] [rbp-18h] BYREF
  int JobObjectInformation_4; // [rsp+44h] [rbp-14h]
  ULONG_PTR SystemAffinityMask[2]; // [rsp+48h] [rbp-10h] BYREF
  bool v16; // [rsp+80h] [rbp+28h] BYREF
  bool v17; // [rsp+88h] [rbp+30h] BYREF
  bool v18; // [rsp+90h] [rbp+38h] BYREF
  bool v19; // [rsp+98h] [rbp+40h] BYREF

  result = (unsigned int)dword_180163E78;
  if ( !dword_180163E78 )
  {
    if ( CLRConfig::GetConfigValue(
           (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_RunningInContainer,
           a2,
           &v16) )
    {
      ConfigValue = CLRConfig::GetConfigValue(
                      (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_ProcessorCount,
                      v3,
                      &v17);
      if ( ConfigValue - 1 <= 0xFFFE )
        goto LABEL_37;
    }
    if ( CPUGroupInfo::m_initialization != -1 )
    {
      if ( _InterlockedCompareExchange(&CPUGroupInfo::m_initialization, 1, 0) )
      {
        while ( CPUGroupInfo::m_initialization != -1 )
          SwitchToThread();
      }
      else
      {
        CPUGroupInfo::InitCPUGroupInfo();
        CPUGroupInfo::m_initialization = -1;
      }
    }
    if ( CLRConfig::GetConfigValue(
           (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_RunningInContainer,
           v3,
           &v18)
      && CPUGroupInfo::m_enableGCCPUGroups )
    {
      ConfigValue = CPUGroupInfo::m_nProcessors;
      goto LABEL_21;
    }
    CurrentProcess = GetCurrentProcess();
    if ( GetProcessAffinityMask(CurrentProcess, &ProcessAffinityMask, SystemAffinityMask) )
    {
      v7 = ProcessAffinityMask;
      if ( ProcessAffinityMask == 1 )
      {
        if ( !CLRConfig::GetConfigValue(
                (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_RunningInContainer,
                v5,
                &v19) )
          goto LABEL_15;
        v7 = ProcessAffinityMask;
      }
      v8 = SystemAffinityMask[0] & v7;
      ConfigValue = 0;
      ProcessAffinityMask = v8;
      if ( !v8 )
        goto LABEL_20;
      do
      {
        ++ConfigValue;
        v8 &= v8 - 1;
      }
      while ( v8 );
      ProcessAffinityMask = 0;
      if ( !ConfigValue )
LABEL_20:
        ConfigValue = 64;
LABEL_21:
      if ( CLRConfig::GetConfigValue(
             (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_RunningInContainer,
             v5,
             &v11)
        && QueryInformationJobObject(0, MaxJobObjectInfoClass|JobObjectBasicProcessIdList, &JobObjectInformation, 8u, 0) )
      {
        if ( (JobObjectInformation & 5) == 5 )
        {
          v9 = JobObjectInformation_4;
          goto LABEL_27;
        }
        if ( (JobObjectInformation & 0x11) == 0x11 )
        {
          v9 = HIWORD(JobObjectInformation_4);
LABEL_27:
          if ( (unsigned int)(v9 - 1) <= 0x270E )
          {
            if ( CPUGroupInfo::m_initialization != -1 )
            {
              if ( _InterlockedCompareExchange(&CPUGroupInfo::m_initialization, 1, 0) )
              {
                while ( CPUGroupInfo::m_initialization != -1 )
                  SwitchToThread();
              }
              else
              {
                CPUGroupInfo::InitCPUGroupInfo();
                CPUGroupInfo::m_initialization = -1;
              }
            }
            dwNumberOfProcessors = CPUGroupInfo::m_nProcessors;
            if ( !CPUGroupInfo::m_enableGCCPUGroups )
              dwNumberOfProcessors = g_SystemInfo.dwNumberOfProcessors;
            if ( (v9 * dwNumberOfProcessors + 9999) / 0x2710 < ConfigValue )
              ConfigValue = (v9 * dwNumberOfProcessors + 9999) / 0x2710;
          }
        }
      }
LABEL_37:
      dword_180163E78 = ConfigValue;
      return ConfigValue;
    }
LABEL_15:
    ConfigValue = 1;
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x180079350  push    rbp
0x180079352  push    rbx
0x180079353  push    rdi
0x180079354  push    r15
0x180079356  mov     rbp, rsp
0x180079359  sub     rsp, 58h
0x18007935d  mov     eax, cs:dword_180163E78
0x180079363  test    eax, eax
0x180079365  jnz     loc_18007952A
0x18007936b  lea     rdi, ?EXTERNAL_RunningInContainer@CLRConfig@@2UConfigDWORDInfo@1@B; CLRConfig::ConfigDWORDInfo const CLRConfig::EXTERNAL_RunningInContainer
0x180079372  mov     rcx, rdi; struct CLRConfig::ConfigDWORDInfo *
0x180079375  lea     r8, [rbp+arg_0]; bool *
0x180079379  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18007937e  test    eax, eax
0x180079380  jz      short loc_1800793A1
0x180079382  lea     r8, [rbp+arg_8]; bool *
0x180079386  lea     rcx, ?EXTERNAL_ProcessorCount@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18007938d  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180079392  mov     ebx, eax
0x180079394  dec     eax
0x180079396  cmp     eax, 0FFFEh
0x18007939b  jbe     loc_180079522
0x1800793a1  cmp     cs:?m_initialization@CPUGroupInfo@@0JA, 0FFFFFFFFh; long CPUGroupInfo::m_initialization
0x1800793a8  mov     r15d, 1
0x1800793ae  jz      short loc_1800793DA
0x1800793b0  xor     eax, eax
0x1800793b2  lock cmpxchg cs:?m_initialization@CPUGroupInfo@@0JA, r15d; long CPUGroupInfo::m_initialization
0x1800793bb  jnz     short loc_1800793D1
0x1800793bd  call    ?InitCPUGroupInfo@CPUGroupInfo@@CAXXZ; CPUGroupInfo::InitCPUGroupInfo(void)
0x1800793c2  or      cs:?m_initialization@CPUGroupInfo@@0JA, 0FFFFFFFFh; long CPUGroupInfo::m_initialization
0x1800793c9  jmp     short loc_1800793DA
0x1800793cb  call    cs:__imp_SwitchToThread
0x1800793d1  cmp     cs:?m_initialization@CPUGroupInfo@@0JA, 0FFFFFFFFh; long CPUGroupInfo::m_initialization
0x1800793d8  jnz     short loc_1800793CB
0x1800793da  lea     r8, [rbp+arg_10]; bool *
0x1800793de  mov     rcx, rdi; struct CLRConfig::ConfigDWORDInfo *
0x1800793e1  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x1800793e6  test    eax, eax
0x1800793e8  jz      short loc_1800793FC
0x1800793ea  cmp     cs:?m_enableGCCPUGroups@CPUGroupInfo@@0HA, 0; int CPUGroupInfo::m_enableGCCPUGroups
0x1800793f1  jz      short loc_1800793FC
0x1800793f3  movzx   ebx, cs:?m_nProcessors@CPUGroupInfo@@0GA; ushort CPUGroupInfo::m_nProcessors
0x1800793fa  jmp     short loc_180079461
0x1800793fc  call    cs:__imp_GetCurrentProcess
0x180079402  mov     rcx, rax; hProcess
0x180079405  lea     r8, [rbp+SystemAffinityMask]; lpSystemAffinityMask
0x180079409  lea     rdx, [rbp+ProcessAffinityMask]; lpProcessAffinityMask
0x18007940d  call    cs:__imp_GetProcessAffinityMask
0x180079413  test    eax, eax
0x180079415  jz      short loc_180079430
0x180079417  mov     rcx, [rbp+ProcessAffinityMask]
0x18007941b  cmp     rcx, r15
0x18007941e  jnz     short loc_180079439
0x180079420  lea     r8, [rbp+arg_18]; bool *
0x180079424  mov     rcx, rdi; struct CLRConfig::ConfigDWORDInfo *
0x180079427  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18007942c  test    eax, eax
0x18007942e  jnz     short loc_180079435
0x180079430  mov     ebx, r15d
0x180079433  jmp     short loc_180079461
0x180079435  mov     rcx, [rbp+ProcessAffinityMask]
0x180079439  and     rcx, [rbp+SystemAffinityMask]
0x18007943d  mov     ebx, 0
0x180079442  mov     [rbp+ProcessAffinityMask], rcx
0x180079446  jz      short loc_18007945C
0x180079448  lea     rax, [rcx-1]
0x18007944c  add     ebx, r15d
0x18007944f  and     rcx, rax
0x180079452  jnz     short loc_180079448
0x180079454  mov     [rbp+ProcessAffinityMask], rcx
0x180079458  test    ebx, ebx
0x18007945a  jnz     short loc_180079461
0x18007945c  mov     ebx, 40h ; '@'
0x180079461  lea     r8, [rbp+var_28]; bool *
0x180079465  mov     rcx, rdi; struct CLRConfig::ConfigDWORDInfo *
0x180079468  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18007946d  test    eax, eax
0x18007946f  jz      loc_180079522
0x180079475  and     [rsp+58h+var_38], 0
0x18007947b  lea     r8, [rbp+JobObjectInformation]; lpJobObjectInformation
0x18007947f  mov     r9d, 8; cbJobObjectInformationLength
0x180079485  xor     ecx, ecx; hJob
0x180079487  lea     edx, [r9+7]; JobObjectInformationClass
0x18007948b  call    cs:__imp_QueryInformationJobObject
0x180079491  test    eax, eax
0x180079493  jz      loc_180079522
0x180079499  mov     rax, [rbp+JobObjectInformation]
0x18007949d  mov     ecx, eax
0x18007949f  and     ecx, 5
0x1800794a2  cmp     cl, 5
0x1800794a5  jnz     short loc_1800794AC
0x1800794a7  mov     edi, dword ptr [rbp+JobObjectInformation+4]
0x1800794aa  jmp     short loc_1800794B7
0x1800794ac  and     eax, 11h
0x1800794af  cmp     al, 11h
0x1800794b1  jnz     short loc_180079522
0x1800794b3  movzx   edi, word ptr [rbp+JobObjectInformation+6]
0x1800794b7  lea     eax, [rdi-1]
0x1800794ba  cmp     eax, 270Eh
0x1800794bf  ja      short loc_180079522
0x1800794c1  cmp     cs:?m_initialization@CPUGroupInfo@@0JA, 0FFFFFFFFh; long CPUGroupInfo::m_initialization
0x1800794c8  jz      short loc_1800794F4
0x1800794ca  xor     eax, eax
0x1800794cc  lock cmpxchg cs:?m_initialization@CPUGroupInfo@@0JA, r15d; long CPUGroupInfo::m_initialization
0x1800794d5  jnz     short loc_1800794EB
0x1800794d7  call    ?InitCPUGroupInfo@CPUGroupInfo@@CAXXZ; CPUGroupInfo::InitCPUGroupInfo(void)
0x1800794dc  or      cs:?m_initialization@CPUGroupInfo@@0JA, 0FFFFFFFFh; long CPUGroupInfo::m_initialization
0x1800794e3  jmp     short loc_1800794F4
0x1800794e5  call    cs:__imp_SwitchToThread
0x1800794eb  cmp     cs:?m_initialization@CPUGroupInfo@@0JA, 0FFFFFFFFh; long CPUGroupInfo::m_initialization
0x1800794f2  jnz     short loc_1800794E5
0x1800794f4  cmp     cs:?m_enableGCCPUGroups@CPUGroupInfo@@0HA, 0; int CPUGroupInfo::m_enableGCCPUGroups
0x1800794fb  movzx   ecx, cs:?m_nProcessors@CPUGroupInfo@@0GA; ushort CPUGroupInfo::m_nProcessors
0x180079502  jnz     short loc_18007950A
0x180079504  mov     ecx, cs:?g_SystemInfo@@3U_SYSTEM_INFO@@A.dwNumberOfProcessors; _SYSTEM_INFO g_SystemInfo ...
0x18007950a  imul    ecx, edi
0x18007950d  mov     eax, 0D1B71759h
0x180079512  add     ecx, 270Fh
0x180079518  mul     ecx
0x18007951a  shr     edx, 0Dh
0x18007951d  cmp     edx, ebx
0x18007951f  cmovb   ebx, edx
0x180079522  mov     cs:dword_180163E78, ebx
0x180079528  mov     eax, ebx
0x18007952a  add     rsp, 58h
0x18007952e  pop     r15
0x180079530  pop     rdi
0x180079531  pop     rbx
0x180079532  pop     rbp
0x180079533  retn
```
