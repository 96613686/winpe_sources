# HalpMiscGetParameters

- ea: `0x140c51330`
- end: `0x140c51715`
- name: `HalpMiscGetParameters`
- size: `997`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140b8d710`

## callees

- `0x140242868`
- `0x1404796e0`
- `0x140479738`
- `0x14047978c`
- `0x14053c4f0`
- `0x14053c730`
- `0x140583778`
- `0x140583fcc`
- `0x14058ad3c`
- `0x14058ada8`
- `0x140c511d4`
- `0x140c51330`

## string_xrefs

- `0x140c51530`: `FORCEMSI`
- `0x140c51518`: `MSIPOLICY=FORCEDISABLE`
- `0x140c514fd`: `CONFIGACCESSPOLICY=DISALLOWMMCONFIG`

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
    BYTE2(HalpDeviceBlockUnblockPushLock.Timer.TimerListEntry.Flink) = 1;
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
      BYTE1(HalpDeviceBlockUnblockPushLock.Timer.TimerListEntry.Flink) = 1;
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
                  BYTE2(HalpDeviceBlockUnblockPushLock.Timer.TimerListEntry.Flink) = 1;
              }
            }
            if ( strstr(v3, "FIRSTMEGABYTEPOLICY=USEALL")
              || (unsigned __int8)HalpIsMicrosoftCompatibleHvLoaded() && !HalpHvCpuManager && strstr(v3, "NOVGA") )
            {
              BYTE2(HalpDeviceBlockUnblockPushLock.Timer.TimerListEntry.Flink) = 0;
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
0x140c51330  mov     [rsp+arg_8], rbx
0x140c51335  mov     [rsp+arg_10], rsi
0x140c5133a  push    rdi
0x140c5133b  sub     rsp, 30h
0x140c5133f  mov     rsi, rcx
0x140c51342  call    HalpInterruptModel
0x140c51347  cmp     eax, 1
0x140c5134a  jnz     short loc_140C51352
0x140c5134c  mov     byte ptr cs:HalpDeviceBlockUnblockPushLock.Timer.TimerListEntry.Flink+2, al
0x140c51352  mov     rcx, rsi
0x140c51355  call    HalpProcIsSmtDisabled
0x140c5135a  mov     cs:HalpInterruptBlockHyperthreading, al
0x140c51360  test    rsi, rsi
0x140c51363  jz      loc_140C51704
0x140c51369  test    al, al
0x140c5136b  jz      short loc_140C51387
0x140c5136d  mov     rax, [rsi+0F0h]
0x140c51374  test    dword ptr [rax+84h], 200h
0x140c5137e  jnz     short loc_140C51387
0x140c51380  mov     cs:HalpInterruptStartHyperthreadSiblings, 1
0x140c51387  mov     rdi, [rsi+0D8h]
0x140c5138e  test    rdi, rdi
0x140c51391  jz      loc_140C516E4
0x140c51397  lea     rdx, aSafeboot_1; "SAFEBOOT:"
0x140c5139e  mov     rcx, rdi; Str
0x140c513a1  call    strstr
0x140c513a6  lea     rdx, HalpSzOneCpu; "ONECPU"
0x140c513ad  mov     rcx, rdi; Str
0x140c513b0  call    strstr
0x140c513b5  test    rax, rax
0x140c513b8  jz      short loc_140C513C4
0x140c513ba  mov     cs:HalpInterruptProcessorCap, 1
0x140c513c4  lea     rdx, HalpSzUsePhysicalApic; "USEPHYSICALAPIC"
0x140c513cb  mov     rcx, rdi; Str
0x140c513ce  call    strstr
0x140c513d3  test    rax, rax
0x140c513d6  jz      short loc_140C513DF
0x140c513d8  mov     cs:HalpInterruptPhysicalModeOnly, 1
0x140c513df  lea     rdx, HalpSzBreak; "BREAK"
0x140c513e6  mov     rcx, rdi; Str
0x140c513e9  call    strstr
0x140c513ee  test    rax, rax
0x140c513f1  jz      short loc_140C513FA
0x140c513f3  mov     byte ptr cs:HalpDeviceBlockUnblockPushLock.Timer.TimerListEntry.Flink+1, 1
0x140c513fa  lea     rdx, HalpSzForceClusterMode; "MAXPROCSPERCLUSTER"
0x140c51401  mov     rcx, rdi; Str
0x140c51404  call    strstr
0x140c51409  test    rax, rax
0x140c5140c  jz      short loc_140C51435
0x140c5140e  jmp     short loc_140C51420
0x140c51410  cmp     cl, 20h ; ' '
0x140c51413  jz      short loc_140C51426
0x140c51415  sub     cl, 30h ; '0'
0x140c51418  cmp     cl, 9
0x140c5141b  jbe     short loc_140C51426
0x140c5141d  inc     rax
0x140c51420  mov     cl, [rax]
0x140c51422  test    cl, cl
0x140c51424  jnz     short loc_140C51410
0x140c51426  mov     rcx, rax; Str
0x140c51429  call    atoi
0x140c5142e  mov     ecx, eax
0x140c51430  call    HalpInterruptForceClusterMode
0x140c51435  lea     rdx, HalpSzMaxApicCluster; "MAXAPICCLUSTER"
0x140c5143c  mov     rcx, rdi; Str
0x140c5143f  call    strstr
0x140c51444  test    rax, rax
0x140c51447  jz      short loc_140C51474
0x140c51449  jmp     short loc_140C5145B
0x140c5144b  cmp     cl, 20h ; ' '
0x140c5144e  jz      short loc_140C51461
0x140c51450  sub     cl, 30h ; '0'
0x140c51453  cmp     cl, 9
0x140c51456  jbe     short loc_140C51461
0x140c51458  inc     rax
0x140c5145b  mov     cl, [rax]
0x140c5145d  test    cl, cl
0x140c5145f  jnz     short loc_140C5144B
0x140c51461  mov     rcx, rax; Str
0x140c51464  call    atoi
0x140c51469  cmp     eax, 1
0x140c5146c  jb      short loc_140C51474
0x140c5146e  mov     cs:HalpInterruptMaxCluster, eax
0x140c51474  lea     rdx, HalpSzEnableX2ApicPolicy; "X2APICPOLICY=ENABLE"
0x140c5147b  mov     rcx, rdi; Str
0x140c5147e  call    strstr
0x140c51483  test    rax, rax
0x140c51486  jz      short loc_140C5148F
0x140c51488  mov     cs:HalpInterruptX2ApicPolicy, 1
0x140c5148f  lea     rdx, HalpSzDisableX2ApicPolicy; "X2APICPOLICY=DISABLE"
0x140c51496  mov     rcx, rdi; Str
0x140c51499  call    strstr
0x140c5149e  test    rax, rax
0x140c514a1  jz      short loc_140C514AA
0x140c514a3  mov     cs:HalpInterruptX2ApicPolicy, 0
0x140c514aa  lea     rdx, HalpSzUseLegacyApicMode; "USELEGACYAPICMODE"
0x140c514b1  mov     rcx, rdi; Str
0x140c514b4  call    strstr
0x140c514b9  test    rax, rax
0x140c514bc  jz      short loc_140C514C5
0x140c514be  mov     cs:HalpInterruptX2ApicPolicy, 0
0x140c514c5  lea     rdx, HalpSzWatchdogDisable; "SYSTEMWATCHDOGPOLICY=DISABLED"
0x140c514cc  mov     rcx, rdi; Str
0x140c514cf  call    strstr
0x140c514d4  test    rax, rax
0x140c514d7  jz      short loc_140C514E2
0x140c514d9  mov     cs:HalpTimerWatchdogDisable, 1
0x140c514e0  jmp     short loc_140C514FD
0x140c514e2  lea     rdx, HalpSzWatchdogPhysicalOnly; "SYSTEMWATCHDOGPOLICY=PHYSICALONLY"
0x140c514e9  mov     rcx, rdi; Str
0x140c514ec  call    strstr
0x140c514f1  test    rax, rax
0x140c514f4  jz      short loc_140C514FD
0x140c514f6  mov     cs:HalpTimerWatchdogPhysicalOnly, 1
0x140c514fd  lea     rdx, HalpSzDisallowMmConfig; "CONFIGACCESSPOLICY=DISALLOWMMCONFIG"
0x140c51504  mov     rcx, rdi; Str
0x140c51507  call    strstr
0x140c5150c  test    rax, rax
0x140c5150f  jz      short loc_140C51518
0x140c51511  mov     cs:HalpAvoidMmConfigAccessMethod, 1
0x140c51518  lea     rdx, HalpSzDisallowMsi; "MSIPOLICY=FORCEDISABLE"
0x140c5151f  mov     rcx, rdi; Str
0x140c51522  call    strstr
0x140c51527  test    rax, rax
0x140c5152a  jz      short loc_140C51530
0x140c5152c  xor     ecx, ecx
0x140c5152e  jmp     short loc_140C51546
0x140c51530  lea     rdx, HalpSzForceMSI; "FORCEMSI"
0x140c51537  mov     rcx, rdi; Str
0x140c5153a  call    strstr
0x140c5153f  test    rax, rax
0x140c51542  jz      short loc_140C5154B
0x140c51544  mov     cl, 1
0x140c51546  call    HalpInterruptSetMsiOverride
0x140c5154b  call    HalpIsHvPresent
0x140c51550  test    al, al
0x140c51552  jz      short loc_140C51586
0x140c51554  mov     cs:HalpHvPresent, 1
0x140c5155b  call    HalpIsPartitionCpuManager
0x140c51560  test    al, al
0x140c51562  jz      short loc_140C5156B
0x140c51564  mov     cs:HalpHvCpuManager, 1
0x140c5156b  call    HalpIsMicrosoftCompatibleHvLoaded
0x140c51570  test    al, al
0x140c51572  jz      short loc_140C51586
0x140c51574  xor     ecx, ecx
0x140c51576  mov     eax, 40000004h
0x140c5157b  cpuid
0x140c5157d  shr     eax, 4
0x140c51580  test    al, 1
0x140c51582  jnz     short loc_140C5158F
0x140c51584  jmp     short loc_140C51596
0x140c51586  call    HalpIsXboxNanovisorPresent
0x140c5158b  test    al, al
0x140c5158d  jz      short loc_140C51596
0x140c5158f  mov     cs:HalpHvUsedForReboot, 1
0x140c51596  cmp     cs:HalpHvCpuManager, 0
0x140c5159d  jz      short loc_140C515DC
0x140c5159f  lea     r9, [rsp+38h+arg_0]
0x140c515a4  mov     [rsp+38h+arg_0], 0
0x140c515a9  xor     r8d, r8d
0x140c515ac  xor     edx, edx
0x140c515ae  xor     ecx, ecx
0x140c515b0  call    HalpGetCpuInfo
0x140c515b5  test    al, al
0x140c515b7  jz      short loc_140C515DC
0x140c515b9  cmp     [rsp+38h+arg_0], 2
0x140c515be  jnz     short loc_140C515DC
0x140c515c0  mov     ecx, 0FEh
0x140c515c5  rdmsr
0x140c515c7  shl     rdx, 20h
0x140c515cb  or      rax, rdx
0x140c515ce  bt      rax, 0Fh
0x140c515d3  jnb     short loc_140C515DC
0x140c515d5  mov     byte ptr cs:HalpDeviceBlockUnblockPushLock.Timer.TimerListEntry.Flink+2, 1
0x140c515dc  lea     rdx, HalpSzUseLowMemory; "FIRSTMEGABYTEPOLICY=USEALL"
0x140c515e3  mov     rcx, rdi; Str
0x140c515e6  call    strstr
0x140c515eb  test    rax, rax
0x140c515ee  jnz     short loc_140C51616
0x140c515f0  call    HalpIsMicrosoftCompatibleHvLoaded
0x140c515f5  test    al, al
0x140c515f7  jz      short loc_140C5161D
0x140c515f9  cmp     cs:HalpHvCpuManager, 0
0x140c51600  jnz     short loc_140C5161D
0x140c51602  lea     rdx, HalpSzNoBiosEmulator; "NOVGA"
0x140c51609  mov     rcx, rdi; Str
0x140c5160c  call    strstr
0x140c51611  test    rax, rax
0x140c51614  jz      short loc_140C5161D
0x140c51616  mov     byte ptr cs:HalpDeviceBlockUnblockPushLock.Timer.TimerListEntry.Flink+2, 0
0x140c5161d  lea     rdx, HalpSzUsePlatformClock; "USEPLATFORMCLOCK"
0x140c51624  mov     rcx, rdi; Str
0x140c51627  call    strstr
0x140c5162c  test    rax, rax
0x140c5162f  jz      short loc_140C51638
0x140c51631  mov     cs:HalpTimerPlatformSourceForced, 1
0x140c51638  lea     rdx, HalpSzUsePlatformTick; "USEPLATFORMTICK"
0x140c5163f  mov     rcx, rdi; Str
0x140c51642  call    strstr
0x140c51647  test    rax, rax
0x140c5164a  jz      short loc_140C51653
0x140c5164c  mov     cs:HalpTimerPlatformClockSourceForced, 1
0x140c51653  lea     rdx, HalpSzGroupSize; "GROUPSIZE"
0x140c5165a  mov     rcx, rdi; Str
0x140c5165d  call    strstr
0x140c51662  test    rax, rax
0x140c51665  jz      short loc_140C5169E
0x140c51667  jmp     short loc_140C51679
0x140c51669  cmp     cl, 20h ; ' '
0x140c5166c  jz      short loc_140C5167F
0x140c5166e  sub     cl, 30h ; '0'
0x140c51671  cmp     cl, 9
0x140c51674  jbe     short loc_140C5167F
0x140c51676  inc     rax
0x140c51679  mov     cl, [rax]
0x140c5167b  test    cl, cl
0x140c5167d  jnz     short loc_140C51669
0x140c5167f  mov     rcx, rax; Str
0x140c51682  call    atoi
0x140c51687  mov     cs:HalpMaximumGroupSize, eax
0x140c5168d  dec     eax
0x140c5168f  cmp     eax, 3Fh ; '?'
0x140c51692  jbe     short loc_140C5169E
0x140c51694  mov     cs:HalpMaximumGroupSize, 40h ; '@'
0x140c5169e  mov     rax, [rsi+0F0h]
0x140c516a5  mov     rcx, rdi; Str
0x140c516a8  mov     edx, [rax+84h]
0x140c516ae  shr     edx, 11h
0x140c516b1  and     dl, 1
0x140c516b4  mov     cs:HalpSplitLargeNumaNodes, dl
0x140c516ba  lea     rdx, HalpSzBlockedHaltProfPolicy; "HALTPROFILINGPOLICY=BLOCKED"
0x140c516c1  call    strstr
0x140c516c6  lea     rdx, HalpSzRelaxedHaltProfPolicy; "HALTPROFILINGPOLICY=RELAXED"
0x140c516cd  mov     rcx, rdi; Str
0x140c516d0  call    strstr
0x140c516d5  lea     rdx, HalpSzRestrictedHaltProfPolicy; "HALTPROFILINGPOLICY=RESTRICTED"
0x140c516dc  mov     rcx, rdi; Str
0x140c516df  call    strstr
0x140c516e4  mov     rax, [rsi+0F0h]
0x140c516eb  test    rax, rax
0x140c516ee  jz      short loc_140C51704
0x140c516f0  mov     eax, [rax+0A58h]
0x140c516f6  bt      rax, 12h
0x140c516fb  jnb     short loc_140C51704
0x140c516fd  mov     cs:HalpPrebootMode, 1
0x140c51704  mov     rbx, [rsp+38h+arg_8]
0x140c51709  mov     rsi, [rsp+38h+arg_10]
0x140c5170e  add     rsp, 30h
0x140c51712  pop     rdi
0x140c51713  retn
```
