# HalpMiscGetParameters

- ea: `0x140c56620`
- end: `0x140c56a05`
- name: `HalpMiscGetParameters`
- size: `997`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140b90760`

## callees

- `0x1403a5678`
- `0x14048a8c0`
- `0x14048a918`
- `0x14048a96c`
- `0x140543bb0`
- `0x140543df0`
- `0x14058ace8`
- `0x14058b53c`
- `0x1405922ac`
- `0x140592318`
- `0x140c564c4`
- `0x140c56620`

## string_xrefs

- `0x140c56820`: `FORCEMSI`
- `0x140c56808`: `MSIPOLICY=FORCEDISABLE`
- `0x140c567ed`: `CONFIGACCESSPOLICY=DISALLOWMMCONFIG`

## pseudocode

```c
__int64 __fastcall HalpMiscGetParameters(__int64 a1)
{
  __int64 result; // rax
  const char *v3; // rdi
  char *v4; // rax
  char v5; // cl
  unsigned int v6; // eax
  char *v7; // rax
  char v8; // cl
  int v9; // eax
  __int64 v10; // rcx
  char *v16; // rax
  char v17; // cl
  char v18; // [rsp+40h] [rbp+8h] BYREF

  if ( (unsigned int)HalpInterruptModel() == 1 )
    HalpMiscDiscardLowMemory = 1;
  result = HalpProcIsSmtDisabled(a1);
  HalpInterruptBlockHyperthreading = result;
  if ( a1 )
  {
    if ( (_BYTE)result && (*(_DWORD *)(*(_QWORD *)(a1 + 240) + 132LL) & 0x200) == 0 )
      HalpInterruptStartHyperthreadSiblings = 1;
    v3 = *(const char **)(a1 + 216);
    if ( !v3 )
      goto LABEL_77;
    strstr(*(const char **)(a1 + 216), "SAFEBOOT:");
    if ( strstr(v3, "ONECPU") )
      HalpInterruptProcessorCap = 1;
    if ( strstr(v3, "USEPHYSICALAPIC") )
      HalpInterruptPhysicalModeOnly = 1;
    if ( strstr(v3, "BREAK") )
      HalpMiscDebugBreakRequested = 1;
    v4 = strstr(v3, "MAXPROCSPERCLUSTER");
    if ( v4 )
    {
      while ( 1 )
      {
        v5 = *v4;
        if ( !*v4 || v5 == 32 || (unsigned __int8)(v5 - 48) <= 9u )
          break;
        ++v4;
      }
      v6 = atoi(v4);
      HalpInterruptForceClusterMode(v6);
    }
    v7 = strstr(v3, "MAXAPICCLUSTER");
    if ( v7 )
    {
      while ( 1 )
      {
        v8 = *v7;
        if ( !*v7 || v8 == 32 || (unsigned __int8)(v8 - 48) <= 9u )
          break;
        ++v7;
      }
      v9 = atoi(v7);
      if ( v9 )
        LODWORD(HalpInterruptMaxCluster) = v9;
    }
    if ( strstr(v3, "X2APICPOLICY=ENABLE") )
      HalpInterruptX2ApicPolicy = 1;
    if ( strstr(v3, "X2APICPOLICY=DISABLE") )
      HalpInterruptX2ApicPolicy = 0;
    if ( strstr(v3, "USELEGACYAPICMODE") )
      HalpInterruptX2ApicPolicy = 0;
    if ( strstr(v3, "SYSTEMWATCHDOGPOLICY=DISABLED") )
    {
      HalpTimerWatchdogDisable = 1;
    }
    else if ( strstr(v3, "SYSTEMWATCHDOGPOLICY=PHYSICALONLY") )
    {
      HalpTimerWatchdogPhysicalOnly = 1;
    }
    if ( strstr(v3, "CONFIGACCESSPOLICY=DISALLOWMMCONFIG") )
      HalpAvoidMmConfigAccessMethod = 1;
    if ( strstr(v3, "MSIPOLICY=FORCEDISABLE") )
    {
      v10 = 0;
    }
    else
    {
      if ( !strstr(v3, "FORCEMSI") )
      {
LABEL_46:
        if ( !(unsigned __int8)HalpIsHvPresent() )
          goto LABEL_52;
        HalpHvPresent = 1;
        if ( (unsigned __int8)HalpIsPartitionCpuManager() )
          HalpHvCpuManager = 1;
        if ( (unsigned __int8)HalpIsMicrosoftCompatibleHvLoaded() )
        {
          _RAX = 1073741828;
          __asm { cpuid }
          if ( (_RAX & 0x10) == 0 )
          {
LABEL_54:
            if ( HalpHvCpuManager )
            {
              v18 = 0;
              if ( (unsigned __int8)HalpGetCpuInfo(0, 0, 0, &v18) )
              {
                if ( v18 == 2 && (__readmsr(0xFEu) & 0x8000) != 0 )
                  HalpMiscDiscardLowMemory = 1;
              }
            }
            if ( strstr(v3, "FIRSTMEGABYTEPOLICY=USEALL")
              || (unsigned __int8)HalpIsMicrosoftCompatibleHvLoaded() && !HalpHvCpuManager && strstr(v3, "NOVGA") )
            {
              HalpMiscDiscardLowMemory = 0;
            }
            if ( strstr(v3, "USEPLATFORMCLOCK") )
              HalpTimerPlatformSourceForced = 1;
            if ( strstr(v3, "USEPLATFORMTICK") )
              HalpTimerPlatformClockSourceForced = 1;
            v16 = strstr(v3, "GROUPSIZE");
            if ( v16 )
            {
              while ( 1 )
              {
                v17 = *v16;
                if ( !*v16 || v17 == 32 || (unsigned __int8)(v17 - 48) <= 9u )
                  break;
                ++v16;
              }
              HalpMaximumGroupSize = atoi(v16);
              if ( (unsigned int)(HalpMaximumGroupSize - 1) > 0x3F )
                HalpMaximumGroupSize = 64;
            }
            HalpSplitLargeNumaNodes = (*(_DWORD *)(*(_QWORD *)(a1 + 240) + 132LL) & 0x20000) != 0;
            strstr(v3, "HALTPROFILINGPOLICY=BLOCKED");
            strstr(v3, "HALTPROFILINGPOLICY=RELAXED");
            strstr(v3, "HALTPROFILINGPOLICY=RESTRICTED");
LABEL_77:
            result = *(_QWORD *)(a1 + 240);
            if ( result )
            {
              result = *(unsigned int *)(result + 2648);
              if ( (result & 0x40000) != 0 )
                HalpPrebootMode = 1;
            }
            return result;
          }
        }
        else
        {
LABEL_52:
          if ( !(unsigned __int8)HalpIsXboxNanovisorPresent() )
            goto LABEL_54;
        }
        HalpHvUsedForReboot = 1;
        goto LABEL_54;
      }
      LOBYTE(v10) = 1;
    }
    HalpInterruptSetMsiOverride(v10);
    goto LABEL_46;
  }
  return result;
}

```

## disassembly

```asm
0x140c56620  mov     [rsp+arg_8], rbx
0x140c56625  mov     [rsp+arg_10], rsi
0x140c5662a  push    rdi
0x140c5662b  sub     rsp, 30h
0x140c5662f  mov     rsi, rcx
0x140c56632  call    HalpInterruptModel
0x140c56637  cmp     eax, 1
0x140c5663a  jnz     short loc_140C56642
0x140c5663c  mov     cs:HalpMiscDiscardLowMemory, al
0x140c56642  mov     rcx, rsi
0x140c56645  call    HalpProcIsSmtDisabled
0x140c5664a  mov     cs:HalpInterruptBlockHyperthreading, al
0x140c56650  test    rsi, rsi
0x140c56653  jz      loc_140C569F4
0x140c56659  test    al, al
0x140c5665b  jz      short loc_140C56677
0x140c5665d  mov     rax, [rsi+0F0h]
0x140c56664  test    dword ptr [rax+84h], 200h
0x140c5666e  jnz     short loc_140C56677
0x140c56670  mov     cs:HalpInterruptStartHyperthreadSiblings, 1
0x140c56677  mov     rdi, [rsi+0D8h]
0x140c5667e  test    rdi, rdi
0x140c56681  jz      loc_140C569D4
0x140c56687  lea     rdx, aSafeboot_1; "SAFEBOOT:"
0x140c5668e  mov     rcx, rdi; Str
0x140c56691  call    strstr
0x140c56696  lea     rdx, HalpSzOneCpu; "ONECPU"
0x140c5669d  mov     rcx, rdi; Str
0x140c566a0  call    strstr
0x140c566a5  test    rax, rax
0x140c566a8  jz      short loc_140C566B4
0x140c566aa  mov     cs:HalpInterruptProcessorCap, 1
0x140c566b4  lea     rdx, HalpSzUsePhysicalApic; "USEPHYSICALAPIC"
0x140c566bb  mov     rcx, rdi; Str
0x140c566be  call    strstr
0x140c566c3  test    rax, rax
0x140c566c6  jz      short loc_140C566CF
0x140c566c8  mov     cs:HalpInterruptPhysicalModeOnly, 1
0x140c566cf  lea     rdx, HalpSzBreak; "BREAK"
0x140c566d6  mov     rcx, rdi; Str
0x140c566d9  call    strstr
0x140c566de  test    rax, rax
0x140c566e1  jz      short loc_140C566EA
0x140c566e3  mov     cs:HalpMiscDebugBreakRequested, 1
0x140c566ea  lea     rdx, HalpSzForceClusterMode; "MAXPROCSPERCLUSTER"
0x140c566f1  mov     rcx, rdi; Str
0x140c566f4  call    strstr
0x140c566f9  test    rax, rax
0x140c566fc  jz      short loc_140C56725
0x140c566fe  jmp     short loc_140C56710
0x140c56700  cmp     cl, 20h ; ' '
0x140c56703  jz      short loc_140C56716
0x140c56705  sub     cl, 30h ; '0'
0x140c56708  cmp     cl, 9
0x140c5670b  jbe     short loc_140C56716
0x140c5670d  inc     rax
0x140c56710  mov     cl, [rax]
0x140c56712  test    cl, cl
0x140c56714  jnz     short loc_140C56700
0x140c56716  mov     rcx, rax; Str
0x140c56719  call    atoi
0x140c5671e  mov     ecx, eax
0x140c56720  call    HalpInterruptForceClusterMode
0x140c56725  lea     rdx, HalpSzMaxApicCluster; "MAXAPICCLUSTER"
0x140c5672c  mov     rcx, rdi; Str
0x140c5672f  call    strstr
0x140c56734  test    rax, rax
0x140c56737  jz      short loc_140C56764
0x140c56739  jmp     short loc_140C5674B
0x140c5673b  cmp     cl, 20h ; ' '
0x140c5673e  jz      short loc_140C56751
0x140c56740  sub     cl, 30h ; '0'
0x140c56743  cmp     cl, 9
0x140c56746  jbe     short loc_140C56751
0x140c56748  inc     rax
0x140c5674b  mov     cl, [rax]
0x140c5674d  test    cl, cl
0x140c5674f  jnz     short loc_140C5673B
0x140c56751  mov     rcx, rax; Str
0x140c56754  call    atoi
0x140c56759  cmp     eax, 1
0x140c5675c  jb      short loc_140C56764
0x140c5675e  mov     cs:HalpInterruptMaxCluster, eax
0x140c56764  lea     rdx, HalpSzEnableX2ApicPolicy; "X2APICPOLICY=ENABLE"
0x140c5676b  mov     rcx, rdi; Str
0x140c5676e  call    strstr
0x140c56773  test    rax, rax
0x140c56776  jz      short loc_140C5677F
0x140c56778  mov     cs:HalpInterruptX2ApicPolicy, 1
0x140c5677f  lea     rdx, HalpSzDisableX2ApicPolicy; "X2APICPOLICY=DISABLE"
0x140c56786  mov     rcx, rdi; Str
0x140c56789  call    strstr
0x140c5678e  test    rax, rax
0x140c56791  jz      short loc_140C5679A
0x140c56793  mov     cs:HalpInterruptX2ApicPolicy, 0
0x140c5679a  lea     rdx, HalpSzUseLegacyApicMode; "USELEGACYAPICMODE"
0x140c567a1  mov     rcx, rdi; Str
0x140c567a4  call    strstr
0x140c567a9  test    rax, rax
0x140c567ac  jz      short loc_140C567B5
0x140c567ae  mov     cs:HalpInterruptX2ApicPolicy, 0
0x140c567b5  lea     rdx, HalpSzWatchdogDisable; "SYSTEMWATCHDOGPOLICY=DISABLED"
0x140c567bc  mov     rcx, rdi; Str
0x140c567bf  call    strstr
0x140c567c4  test    rax, rax
0x140c567c7  jz      short loc_140C567D2
0x140c567c9  mov     cs:HalpTimerWatchdogDisable, 1
0x140c567d0  jmp     short loc_140C567ED
0x140c567d2  lea     rdx, HalpSzWatchdogPhysicalOnly; "SYSTEMWATCHDOGPOLICY=PHYSICALONLY"
0x140c567d9  mov     rcx, rdi; Str
0x140c567dc  call    strstr
0x140c567e1  test    rax, rax
0x140c567e4  jz      short loc_140C567ED
0x140c567e6  mov     cs:HalpTimerWatchdogPhysicalOnly, 1
0x140c567ed  lea     rdx, HalpSzDisallowMmConfig; "CONFIGACCESSPOLICY=DISALLOWMMCONFIG"
0x140c567f4  mov     rcx, rdi; Str
0x140c567f7  call    strstr
0x140c567fc  test    rax, rax
0x140c567ff  jz      short loc_140C56808
0x140c56801  mov     cs:HalpAvoidMmConfigAccessMethod, 1
0x140c56808  lea     rdx, HalpSzDisallowMsi; "MSIPOLICY=FORCEDISABLE"
0x140c5680f  mov     rcx, rdi; Str
0x140c56812  call    strstr
0x140c56817  test    rax, rax
0x140c5681a  jz      short loc_140C56820
0x140c5681c  xor     ecx, ecx
0x140c5681e  jmp     short loc_140C56836
0x140c56820  lea     rdx, HalpSzForceMSI; "FORCEMSI"
0x140c56827  mov     rcx, rdi; Str
0x140c5682a  call    strstr
0x140c5682f  test    rax, rax
0x140c56832  jz      short loc_140C5683B
0x140c56834  mov     cl, 1
0x140c56836  call    HalpInterruptSetMsiOverride
0x140c5683b  call    HalpIsHvPresent
0x140c56840  test    al, al
0x140c56842  jz      short loc_140C56876
0x140c56844  mov     cs:HalpHvPresent, 1
0x140c5684b  call    HalpIsPartitionCpuManager
0x140c56850  test    al, al
0x140c56852  jz      short loc_140C5685B
0x140c56854  mov     cs:HalpHvCpuManager, 1
0x140c5685b  call    HalpIsMicrosoftCompatibleHvLoaded
0x140c56860  test    al, al
0x140c56862  jz      short loc_140C56876
0x140c56864  xor     ecx, ecx
0x140c56866  mov     eax, 40000004h
0x140c5686b  cpuid
0x140c5686d  shr     eax, 4
0x140c56870  test    al, 1
0x140c56872  jnz     short loc_140C5687F
0x140c56874  jmp     short loc_140C56886
0x140c56876  call    HalpIsXboxNanovisorPresent
0x140c5687b  test    al, al
0x140c5687d  jz      short loc_140C56886
0x140c5687f  mov     cs:HalpHvUsedForReboot, 1
0x140c56886  cmp     cs:HalpHvCpuManager, 0
0x140c5688d  jz      short loc_140C568CC
0x140c5688f  lea     r9, [rsp+38h+arg_0]
0x140c56894  mov     [rsp+38h+arg_0], 0
0x140c56899  xor     r8d, r8d
0x140c5689c  xor     edx, edx
0x140c5689e  xor     ecx, ecx
0x140c568a0  call    HalpGetCpuInfo
0x140c568a5  test    al, al
0x140c568a7  jz      short loc_140C568CC
0x140c568a9  cmp     [rsp+38h+arg_0], 2
0x140c568ae  jnz     short loc_140C568CC
0x140c568b0  mov     ecx, 0FEh
0x140c568b5  rdmsr
0x140c568b7  shl     rdx, 20h
0x140c568bb  or      rax, rdx
0x140c568be  bt      rax, 0Fh
0x140c568c3  jnb     short loc_140C568CC
0x140c568c5  mov     cs:HalpMiscDiscardLowMemory, 1
0x140c568cc  lea     rdx, HalpSzUseLowMemory; "FIRSTMEGABYTEPOLICY=USEALL"
0x140c568d3  mov     rcx, rdi; Str
0x140c568d6  call    strstr
0x140c568db  test    rax, rax
0x140c568de  jnz     short loc_140C56906
0x140c568e0  call    HalpIsMicrosoftCompatibleHvLoaded
0x140c568e5  test    al, al
0x140c568e7  jz      short loc_140C5690D
0x140c568e9  cmp     cs:HalpHvCpuManager, 0
0x140c568f0  jnz     short loc_140C5690D
0x140c568f2  lea     rdx, HalpSzNoBiosEmulator; "NOVGA"
0x140c568f9  mov     rcx, rdi; Str
0x140c568fc  call    strstr
0x140c56901  test    rax, rax
0x140c56904  jz      short loc_140C5690D
0x140c56906  mov     cs:HalpMiscDiscardLowMemory, 0
0x140c5690d  lea     rdx, HalpSzUsePlatformClock; "USEPLATFORMCLOCK"
0x140c56914  mov     rcx, rdi; Str
0x140c56917  call    strstr
0x140c5691c  test    rax, rax
0x140c5691f  jz      short loc_140C56928
0x140c56921  mov     cs:HalpTimerPlatformSourceForced, 1
0x140c56928  lea     rdx, HalpSzUsePlatformTick; "USEPLATFORMTICK"
0x140c5692f  mov     rcx, rdi; Str
0x140c56932  call    strstr
0x140c56937  test    rax, rax
0x140c5693a  jz      short loc_140C56943
0x140c5693c  mov     cs:HalpTimerPlatformClockSourceForced, 1
0x140c56943  lea     rdx, HalpSzGroupSize; "GROUPSIZE"
0x140c5694a  mov     rcx, rdi; Str
0x140c5694d  call    strstr
0x140c56952  test    rax, rax
0x140c56955  jz      short loc_140C5698E
0x140c56957  jmp     short loc_140C56969
0x140c56959  cmp     cl, 20h ; ' '
0x140c5695c  jz      short loc_140C5696F
0x140c5695e  sub     cl, 30h ; '0'
0x140c56961  cmp     cl, 9
0x140c56964  jbe     short loc_140C5696F
0x140c56966  inc     rax
0x140c56969  mov     cl, [rax]
0x140c5696b  test    cl, cl
0x140c5696d  jnz     short loc_140C56959
0x140c5696f  mov     rcx, rax; Str
0x140c56972  call    atoi
0x140c56977  mov     cs:HalpMaximumGroupSize, eax
0x140c5697d  dec     eax
0x140c5697f  cmp     eax, 3Fh ; '?'
0x140c56982  jbe     short loc_140C5698E
0x140c56984  mov     cs:HalpMaximumGroupSize, 40h ; '@'
0x140c5698e  mov     rax, [rsi+0F0h]
0x140c56995  mov     rcx, rdi; Str
0x140c56998  mov     edx, [rax+84h]
0x140c5699e  shr     edx, 11h
0x140c569a1  and     dl, 1
0x140c569a4  mov     cs:HalpSplitLargeNumaNodes, dl
0x140c569aa  lea     rdx, HalpSzBlockedHaltProfPolicy; "HALTPROFILINGPOLICY=BLOCKED"
0x140c569b1  call    strstr
0x140c569b6  lea     rdx, HalpSzRelaxedHaltProfPolicy; "HALTPROFILINGPOLICY=RELAXED"
0x140c569bd  mov     rcx, rdi; Str
0x140c569c0  call    strstr
0x140c569c5  lea     rdx, HalpSzRestrictedHaltProfPolicy; "HALTPROFILINGPOLICY=RESTRICTED"
0x140c569cc  mov     rcx, rdi; Str
0x140c569cf  call    strstr
0x140c569d4  mov     rax, [rsi+0F0h]
0x140c569db  test    rax, rax
0x140c569de  jz      short loc_140C569F4
0x140c569e0  mov     eax, [rax+0A58h]
0x140c569e6  bt      rax, 12h
0x140c569eb  jnb     short loc_140C569F4
0x140c569ed  mov     cs:HalpPrebootMode, 1
0x140c569f4  mov     rbx, [rsp+38h+arg_8]
0x140c569f9  mov     rsi, [rsp+38h+arg_10]
0x140c569fe  add     rsp, 30h
0x140c56a02  pop     rdi
0x140c56a03  retn
```
