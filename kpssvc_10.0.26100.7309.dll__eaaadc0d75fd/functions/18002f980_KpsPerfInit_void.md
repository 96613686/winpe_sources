# KpsPerfInit(void)

- ea: `0x18002f980`
- end: `0x18002fd28`
- name: `?KpsPerfInit@@YAKXZ`
- size: `936`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002cf60`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x18002f980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002faf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002faf8`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18002fb50`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18002fba1`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18002fbf2`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18002fc38`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18002fb50`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18002fba1`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18002fbf2`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18002fc38`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x18002fa6a`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x18002fa6a`
- `ADVAPI32!PerfDeleteInstance` at `0x18002fc82`
- `ADVAPI32!PerfDeleteInstance` at `0x18002fc82`
- `ADVAPI32!PerfCreateInstance` at `0x18002fae0`
- `ADVAPI32!PerfCreateInstance` at `0x18002fae0`
- `ADVAPI32!PerfStartProviderEx` at `0x18002fa44`
- `ADVAPI32!PerfStartProviderEx` at `0x18002fa44`
- `ADVAPI32!PerfStopProvider` at `0x18002fa88`
- `ADVAPI32!PerfStopProvider` at `0x18002fc9a`
- `ADVAPI32!PerfStopProvider` at `0x18002fa88`
- `ADVAPI32!PerfStopProvider` at `0x18002fc9a`
- `ntdll!RtlInitializeCriticalSection` at `0x18002f9c7`
- `ntdll!RtlInitializeCriticalSection` at `0x18002f9c7`
- `ntdll!RtlDeleteCriticalSection` at `0x18002fcb5`
- `ntdll!RtlDeleteCriticalSection` at `0x18002fcb5`

## pseudocode

```c
__int64 KpsPerfInit(void)
{
  unsigned int v0; // eax
  ULONG started; // ebx
  _QWORD *v2; // rcx
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax
  DWORD LastError; // eax
  ULONG v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  _PROVIDER_CONTEXT ProviderContext; // [rsp+20h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids);
  v0 = RtlInitializeCriticalSection(&stru_18003ADA8);
  started = v0;
  if ( v0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return started;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_42:
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
        WPP_SF_D(v2[2], 21, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids, started);
      return started;
    }
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids, v0);
LABEL_41:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_42;
  }
  memset(&ProviderContext.Reserved, 0, 36);
  ProviderContext.ContextSize = 40;
  started = PerfStartProviderEx(&KpsSvcPerfProviderGuid, &ProviderContext, &KpsSvcPerfProvider);
  if ( started )
    goto LABEL_12;
  started = PerfSetCounterSetInfo(KpsSvcPerfProvider, &KpsSvcPerfCountersInfo, 0xA8u);
  if ( started )
  {
    if ( !KpsSvcPerfProvider )
    {
LABEL_13:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids, started);
LABEL_40:
      RtlDeleteCriticalSection(&stru_18003ADA8);
      goto LABEL_41;
    }
    PerfStopProvider(KpsSvcPerfProvider);
LABEL_12:
    KpsSvcPerfProvider = 0;
    goto LABEL_13;
  }
  Instance = PerfCreateInstance(KpsSvcPerfProvider, &KpsSvcPerfCountersGuid, L"Default", 0);
  InstanceBlock = Instance;
  if ( !Instance )
  {
    LastError = GetLastError();
    started = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids, LastError);
    goto LABEL_38;
  }
  v5 = PerfSetCounterRefValue(KpsSvcPerfProvider, Instance, 1u, &dword_18003ADD8);
  started = v5;
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v7 = 16;
LABEL_36:
    WPP_SF_D(v6[2], v7, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids, v5);
LABEL_37:
    PerfDeleteInstance(KpsSvcPerfProvider, InstanceBlock);
LABEL_38:
    if ( KpsSvcPerfProvider )
    {
      PerfStopProvider(KpsSvcPerfProvider);
      KpsSvcPerfProvider = 0;
    }
    goto LABEL_40;
  }
  v5 = PerfSetCounterRefValue(KpsSvcPerfProvider, InstanceBlock, 2u, &dword_18003ADDC);
  started = v5;
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v7 = 17;
    goto LABEL_36;
  }
  v5 = PerfSetCounterRefValue(KpsSvcPerfProvider, InstanceBlock, 3u, &dword_18003ADE0);
  started = v5;
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v7 = 18;
    goto LABEL_36;
  }
  v5 = PerfSetCounterRefValue(KpsSvcPerfProvider, InstanceBlock, 4u, &dword_18003ADE4);
  started = v5;
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v7 = 19;
    goto LABEL_36;
  }
  KpsPerfData = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18002f980  mov     [rsp+arg_0], rbx
0x18002f985  mov     [rsp+arg_8], rbp
0x18002f98a  push    rsi
0x18002f98b  sub     rsp, 50h
0x18002f98f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f996  lea     rsi, WPP_GLOBAL_Control
0x18002f99d  lea     rbp, WPP_d7d92ff6f8843d103aaec7ed415865b2_Traceguids
0x18002f9a4  cmp     rcx, rsi
0x18002f9a7  jz      short loc_18002F9C0
0x18002f9a9  test    byte ptr [rcx+1Ch], 20h
0x18002f9ad  jz      short loc_18002F9C0
0x18002f9af  mov     rcx, [rcx+10h]
0x18002f9b3  mov     edx, 0Ch
0x18002f9b8  mov     r8, rbp
0x18002f9bb  call    WPP_SF_
0x18002f9c0  lea     rcx, stru_18003ADA8; CriticalSection
0x18002f9c7  call    cs:__imp_RtlInitializeCriticalSection
0x18002f9ce  nop     dword ptr [rax+rax+00h]
0x18002f9d3  mov     ebx, eax
0x18002f9d5  test    eax, eax
0x18002f9d7  jz      short loc_18002FA0C
0x18002f9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9e0  cmp     rcx, rsi
0x18002f9e3  jz      loc_18002FCE7
0x18002f9e9  test    byte ptr [rcx+1Ch], 1
0x18002f9ed  jz      loc_18002FCC8
0x18002f9f3  mov     rcx, [rcx+10h]
0x18002f9f7  mov     edx, 0Dh
0x18002f9fc  mov     r9d, eax
0x18002f9ff  mov     r8, rbp
0x18002fa02  call    WPP_SF_D
0x18002fa07  jmp     loc_18002FCC1
0x18002fa0c  and     [rsp+58h+ProviderContext.Reserved], 0
0x18002fa11  lea     r8, KpsSvcPerfProvider; Provider
0x18002fa18  and     [rsp+58h+ProviderContext.ControlCallback], 0
0x18002fa1e  lea     rdx, [rsp+58h+ProviderContext]; ProviderContext
0x18002fa23  and     [rsp+58h+ProviderContext.MemAllocRoutine], 0
0x18002fa29  lea     rcx, KpsSvcPerfProviderGuid; ProviderGuid
0x18002fa30  and     [rsp+58h+ProviderContext.MemFreeRoutine], 0
0x18002fa36  and     [rsp+58h+ProviderContext.pMemContext], 0
0x18002fa3c  mov     [rsp+58h+ProviderContext.ContextSize], 28h ; '('
0x18002fa44  call    cs:__imp_PerfStartProviderEx
0x18002fa4b  nop     dword ptr [rax+rax+00h]
0x18002fa50  mov     ebx, eax
0x18002fa52  test    eax, eax
0x18002fa54  jnz     short loc_18002FA94
0x18002fa56  mov     rcx, cs:KpsSvcPerfProvider; ProviderHandle
0x18002fa5d  lea     rdx, KpsSvcPerfCountersInfo; Template
0x18002fa64  mov     r8d, 0A8h; TemplateSize
0x18002fa6a  call    cs:__imp_PerfSetCounterSetInfo
0x18002fa71  nop     dword ptr [rax+rax+00h]
0x18002fa76  mov     rcx, cs:KpsSvcPerfProvider; ProviderHandle
0x18002fa7d  mov     ebx, eax
0x18002fa7f  test    eax, eax
0x18002fa81  jz      short loc_18002FACF
0x18002fa83  test    rcx, rcx
0x18002fa86  jz      short loc_18002FA9C
0x18002fa88  call    cs:__imp_PerfStopProvider
0x18002fa8f  nop     dword ptr [rax+rax+00h]
0x18002fa94  and     cs:KpsSvcPerfProvider, 0
0x18002fa9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002faa3  cmp     rcx, rsi
0x18002faa6  jz      loc_18002FCAE
0x18002faac  test    byte ptr [rcx+1Ch], 1
0x18002fab0  jz      loc_18002FCAE
0x18002fab6  mov     rcx, [rcx+10h]
0x18002faba  mov     edx, 0Eh
0x18002fabf  mov     r9d, ebx
0x18002fac2  mov     r8, rbp
0x18002fac5  call    WPP_SF_D
0x18002faca  jmp     loc_18002FCAE
0x18002facf  xor     r9d, r9d; Id
0x18002fad2  lea     r8, Name; "Default"
0x18002fad9  lea     rdx, KpsSvcPerfCountersGuid; CounterSetGuid
0x18002fae0  call    cs:__imp_PerfCreateInstance
0x18002fae7  nop     dword ptr [rax+rax+00h]
0x18002faec  mov     cs:InstanceBlock, rax
0x18002faf3  test    rax, rax
0x18002faf6  jnz     short loc_18002FB39
0x18002faf8  call    cs:__imp_GetLastError
0x18002faff  nop     dword ptr [rax+rax+00h]
0x18002fb04  mov     ebx, eax
0x18002fb06  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb0d  cmp     rcx, rsi
0x18002fb10  jz      loc_18002FC8E
0x18002fb16  test    byte ptr [rcx+1Ch], 1
0x18002fb1a  jz      loc_18002FC8E
0x18002fb20  mov     rcx, [rcx+10h]
0x18002fb24  mov     edx, 0Fh
0x18002fb29  mov     r9d, eax
0x18002fb2c  mov     r8, rbp
0x18002fb2f  call    WPP_SF_D
0x18002fb34  jmp     loc_18002FC8E
0x18002fb39  mov     rcx, cs:KpsSvcPerfProvider; Provider
0x18002fb40  lea     r9, dword_18003ADD8; Address
0x18002fb47  mov     r8d, 1; CounterId
0x18002fb4d  mov     rdx, rax; Instance
0x18002fb50  call    cs:__imp_PerfSetCounterRefValue
0x18002fb57  nop     dword ptr [rax+rax+00h]
0x18002fb5c  mov     ebx, eax
0x18002fb5e  test    eax, eax
0x18002fb60  jz      short loc_18002FB86
0x18002fb62  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb69  cmp     rcx, rsi
0x18002fb6c  jz      loc_18002FC74
0x18002fb72  test    byte ptr [rcx+1Ch], 1
0x18002fb76  jz      loc_18002FC74
0x18002fb7c  mov     edx, 10h
0x18002fb81  jmp     loc_18002FC65
0x18002fb86  mov     rdx, cs:InstanceBlock; Instance
0x18002fb8d  lea     r9, dword_18003ADDC; Address
0x18002fb94  mov     rcx, cs:KpsSvcPerfProvider; Provider
0x18002fb9b  mov     r8d, 2; CounterId
0x18002fba1  call    cs:__imp_PerfSetCounterRefValue
0x18002fba8  nop     dword ptr [rax+rax+00h]
0x18002fbad  mov     ebx, eax
0x18002fbaf  test    eax, eax
0x18002fbb1  jz      short loc_18002FBD7
0x18002fbb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbba  cmp     rcx, rsi
0x18002fbbd  jz      loc_18002FC74
0x18002fbc3  test    byte ptr [rcx+1Ch], 1
0x18002fbc7  jz      loc_18002FC74
0x18002fbcd  mov     edx, 11h
0x18002fbd2  jmp     loc_18002FC65
0x18002fbd7  mov     rdx, cs:InstanceBlock; Instance
0x18002fbde  lea     r9, dword_18003ADE0; Address
0x18002fbe5  mov     rcx, cs:KpsSvcPerfProvider; Provider
0x18002fbec  mov     r8d, 3; CounterId
0x18002fbf2  call    cs:__imp_PerfSetCounterRefValue
0x18002fbf9  nop     dword ptr [rax+rax+00h]
0x18002fbfe  mov     ebx, eax
0x18002fc00  test    eax, eax
0x18002fc02  jz      short loc_18002FC1D
0x18002fc04  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc0b  cmp     rcx, rsi
0x18002fc0e  jz      short loc_18002FC74
0x18002fc10  test    byte ptr [rcx+1Ch], 1
0x18002fc14  jz      short loc_18002FC74
0x18002fc16  mov     edx, 12h
0x18002fc1b  jmp     short loc_18002FC65
0x18002fc1d  mov     rdx, cs:InstanceBlock; Instance
0x18002fc24  lea     r9, dword_18003ADE4; Address
0x18002fc2b  mov     rcx, cs:KpsSvcPerfProvider; Provider
0x18002fc32  mov     r8d, 4; CounterId
0x18002fc38  call    cs:__imp_PerfSetCounterRefValue
0x18002fc3f  nop     dword ptr [rax+rax+00h]
0x18002fc44  mov     ebx, eax
0x18002fc46  test    eax, eax
0x18002fc48  jz      loc_18002FCEB
0x18002fc4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc55  cmp     rcx, rsi
0x18002fc58  jz      short loc_18002FC74
0x18002fc5a  test    byte ptr [rcx+1Ch], 1
0x18002fc5e  jz      short loc_18002FC74
0x18002fc60  mov     edx, 13h
0x18002fc65  mov     rcx, [rcx+10h]
0x18002fc69  mov     r9d, eax
0x18002fc6c  mov     r8, rbp
0x18002fc6f  call    WPP_SF_D
0x18002fc74  mov     rdx, cs:InstanceBlock; InstanceBlock
0x18002fc7b  mov     rcx, cs:KpsSvcPerfProvider; Provider
0x18002fc82  call    cs:__imp_PerfDeleteInstance
0x18002fc89  nop     dword ptr [rax+rax+00h]
0x18002fc8e  mov     rcx, cs:KpsSvcPerfProvider; ProviderHandle
0x18002fc95  test    rcx, rcx
0x18002fc98  jz      short loc_18002FCAE
0x18002fc9a  call    cs:__imp_PerfStopProvider
0x18002fca1  nop     dword ptr [rax+rax+00h]
0x18002fca6  and     cs:KpsSvcPerfProvider, 0
0x18002fcae  lea     rcx, stru_18003ADA8; CriticalSection
0x18002fcb5  call    cs:__imp_RtlDeleteCriticalSection
0x18002fcbc  nop     dword ptr [rax+rax+00h]
0x18002fcc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fcc8  cmp     rcx, rsi
0x18002fccb  jz      short loc_18002FCE7
0x18002fccd  test    byte ptr [rcx+1Ch], 20h
0x18002fcd1  jz      short loc_18002FCE7
0x18002fcd3  mov     rcx, [rcx+10h]
0x18002fcd7  mov     edx, 15h
0x18002fcdc  mov     r9d, ebx
0x18002fcdf  mov     r8, rbp
0x18002fce2  call    WPP_SF_D
0x18002fce7  mov     eax, ebx
0x18002fce9  jmp     short loc_18002FD17
0x18002fceb  mov     cs:?KpsPerfData@@3U_KPS_PERF_DATA@@A, 1; _KPS_PERF_DATA KpsPerfData
0x18002fcf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fcf9  cmp     rcx, rsi
0x18002fcfc  jz      short loc_18002FD15
0x18002fcfe  test    byte ptr [rcx+1Ch], 20h
0x18002fd02  jz      short loc_18002FD15
0x18002fd04  mov     rcx, [rcx+10h]
0x18002fd08  mov     edx, 14h
0x18002fd0d  mov     r8, rbp
0x18002fd10  call    WPP_SF_
0x18002fd15  xor     eax, eax
0x18002fd17  mov     rbx, [rsp+58h+arg_0]
0x18002fd1c  mov     rbp, [rsp+58h+arg_8]
0x18002fd21  add     rsp, 50h
0x18002fd25  pop     rsi
0x18002fd26  retn
```
