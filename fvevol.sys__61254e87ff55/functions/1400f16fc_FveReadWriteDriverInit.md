# FveReadWriteDriverInit

- ea: `0x1400f16fc`
- end: `0x1400f1cf2`
- name: `FveReadWriteDriverInit`
- size: `1526`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x1400f06e0`

## callees

- `0x140005eec`
- `0x1400063b8`
- `0x140006730`
- `0x14000a634`
- `0x14000b50c`
- `0x14000b78c`
- `0x14000fa9c`
- `0x14000fb98`
- `0x14000fc1c`
- `0x14001b66c`
- `0x140022d40`
- `0x140074e98`
- `0x140075148`
- `0x1400845e0`
- `0x140093738`
- `0x1400f16fc`
- `0x1400f1cf8`
- `0x1400f286c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400f1cb1`
- `ntoskrnl!KeReleaseMutex` at `0x1400f1cb1`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x1400f1a8e`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x1400f1a8e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400f1a55`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400f1b73`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400f1bce`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400f1a55`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400f1b73`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400f1bce`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400f1bfb`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400f1c32`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400f1c81`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400f1bfb`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400f1c32`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400f1c81`
- `ntoskrnl!MmSizeOfMdl` at `0x1400f1a7d`
- `ntoskrnl!MmSizeOfMdl` at `0x1400f1a7d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f1741`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f1741`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1c13`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1c4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1c99`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1c13`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1c4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f1c99`
- `ntoskrnl!ExAllocatePool2` at `0x1400f1a0e`
- `ntoskrnl!ExAllocatePool2` at `0x1400f1b34`
- `ntoskrnl!ExAllocatePool2` at `0x1400f1b8d`
- `ntoskrnl!ExAllocatePool2` at `0x1400f1a0e`
- `ntoskrnl!ExAllocatePool2` at `0x1400f1b34`
- `ntoskrnl!ExAllocatePool2` at `0x1400f1b8d`

## pseudocode

```c
__int64 __fastcall FveReadWriteDriverInit(__int64 a1)
{
  struct _KMUTANT *v1; // r15
  PUCHAR v3; // rbp
  unsigned int v4; // r14d
  NTSTATUS ChatConfig; // esi
  int v6; // r8d
  __int64 v7; // r9
  struct _NPAGED_LOOKASIDE_LIST *Pool2; // rax
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  __int64 LookasideList; // rax
  struct _NPAGED_LOOKASIDE_LIST *v16; // rax
  struct _NPAGED_LOOKASIDE_LIST *v17; // rax
  struct _NPAGED_LOOKASIDE_LIST *v18; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v19; // rcx
  void *v20; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v21; // rcx
  int Timeout; // [rsp+20h] [rbp-88h]
  __int64 pulResult; // [rsp+B0h] [rbp+8h] BYREF
  PUCHAR pbInput; // [rsp+B8h] [rbp+10h]

  v1 = (struct _KMUTANT *)(a1 + 9856);
  pbInput = 0;
  LODWORD(pulResult) = 0;
  v3 = 0;
  v4 = 0;
  KeWaitForSingleObject((PVOID)(a1 + 9856), Executive, 0, 0, 0);
  FveConfigRegisterEventCallbacks(a1);
  ChatConfig = FveLoadChatConfig(a1, 0, 0);
  if ( *(_QWORD *)(a1 + 1624) )
  {
    FveLoadCryptoThrottleConfig(a1, 0, 0, 0);
    FveLoadIoCryptoConfig(a1, 0, 0, 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v7 = *(unsigned int *)(a1 + 884);
        WPP_SF_LDDDDDDDDDDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          52,
          v6,
          v7,
          *(_DWORD *)(a1 + 4 * v7 + 936),
          *(_DWORD *)(a1 + 4 * v7 + 948),
          *(_DWORD *)(a1 + 4 * v7 + 960),
          *(_DWORD *)(a1 + 4 * v7 + 984),
          *(_DWORD *)(a1 + 4 * v7 + 996),
          *(_DWORD *)(a1 + 4 * v7 + 1020),
          *(_DWORD *)(a1 + 4 * v7 + 1032),
          *(_DWORD *)(a1 + 4 * v7 + 1044),
          *(_DWORD *)(a1 + 4 * v7 + 1056),
          *(_DWORD *)(a1 + 4 * v7 + 1068),
          *(_DWORD *)(a1 + 4 * v7 + 1080),
          *(_DWORD *)(a1 + 4 * v7 + 1092));
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_LDDDD(WPP_GLOBAL_Control->AttachedDevice, 53);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_LDDDD(WPP_GLOBAL_Control->AttachedDevice, 54);
        }
      }
    }
    ChatConfig = FveLibAllocWithTagZero(*(_QWORD *)(a1 + 1632));
    if ( ChatConfig >= 0 )
    {
      ChatConfig = RtlULongLongToULong(*(_QWORD *)(a1 + 1632), (ULONG *)&pulResult);
      if ( ChatConfig >= 0 )
      {
        memmove(pbInput, *(const void **)(a1 + 1624), (unsigned int)pulResult);
        FveChatConfig(pbInput, pulResult);
        FveReadWriteSubrequestTransitionsInit(a1);
        FveCryptoThrottleInit(*(unsigned int *)(a1 + 4LL * *(unsigned int *)(a1 + 884) + 1372), a1 + 2736);
        FveCryptoThrottleInit(*(unsigned int *)(a1 + 4LL * *(unsigned int *)(a1 + 884) + 1384), a1 + 5992);
        *(_QWORD *)(a1 + 9248) = 0;
        *(_QWORD *)(a1 + 9256) = 0;
        *(_QWORD *)(a1 + 9264) = 0;
        *(_QWORD *)(a1 + 9272) = 0;
        Pool2 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 809850438);
        *(_QWORD *)(a1 + 9248) = Pool2;
        if ( !Pool2 )
        {
LABEL_21:
          ChatConfig = -1073741670;
LABEL_33:
          v18 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9248);
          if ( v18 )
          {
            ExDeleteNPagedLookasideList(v18);
            ExFreePoolWithTag(*(PVOID *)(a1 + 9248), 0x30455646u);
            *(_QWORD *)(a1 + 9248) = 0;
          }
          v19 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9256);
          if ( v19 )
          {
            ExDeleteNPagedLookasideList(v19);
            ExFreePoolWithTag(*(PVOID *)(a1 + 9256), 0x30455646u);
            *(_QWORD *)(a1 + 9256) = 0;
          }
          v20 = *(void **)(a1 + 9264);
          if ( v20 )
          {
            PplDestroyLookasideList(v20);
            *(_QWORD *)(a1 + 9264) = 0;
          }
          v21 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9272);
          if ( v21 )
          {
            ExDeleteNPagedLookasideList(v21);
            ExFreePoolWithTag(*(PVOID *)(a1 + 9272), 0x656E6F4Eu);
            *(_QWORD *)(a1 + 9272) = 0;
          }
          goto LABEL_41;
        }
        ExInitializeNPagedLookasideList(Pool2, 0, 0, 0x200u, 0x1938u, 0x78455646u, 0);
        v9 = *(_DWORD *)(a1 + 4LL * *(unsigned int *)(a1 + 884) + 936);
        v10 = MmSizeOfMdl(0, v9) + v9 + 64;
        if ( MmIsThisAnNtAsSystem() )
        {
          v14 = Feature_BitLocker_PerProc_Buffer__private_featureState;
          pulResult = (unsigned int)Feature_BitLocker_PerProc_Buffer__private_featureState;
          if ( (Feature_BitLocker_PerProc_Buffer__private_featureState & 0x10) == 0 )
          {
            LODWORD(pulResult) = Feature_BitLocker_PerProc_Buffer__private_featureState | 1;
            wil_details_FeatureReporting_ReportUsageToService(
              Feature_BitLocker_PerProc_Buffer__private_descriptor,
              pulResult,
              3);
            wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
              pulResult,
              3,
              Feature_BitLocker_PerProc_Buffer__private_descriptor);
          }
          LookasideList = PplCreateLookasideList(v14, v11, v12, v13, Timeout, v10);
          *(_QWORD *)(a1 + 9264) = LookasideList;
          if ( !LookasideList )
            goto LABEL_21;
        }
        else
        {
          v16 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 809850438);
          *(_QWORD *)(a1 + 9256) = v16;
          if ( !v16 )
            goto LABEL_21;
          ExInitializeNPagedLookasideList(v16, 0, 0, 0x200u, v10, 0x70455646u, 0);
        }
        v17 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 809850438);
        *(_QWORD *)(a1 + 9272) = v17;
        if ( v17 )
        {
          ExInitializeNPagedLookasideList(v17, 0, 0, 0x200u, 0x10u, 0x656E6F4Eu, 0);
          goto LABEL_41;
        }
        goto LABEL_21;
      }
      v4 = pulResult;
    }
    v3 = pbInput;
    goto LABEL_33;
  }
  if ( ChatConfig < 0 )
    ChatConfig = -1073741823;
  if ( ChatConfig < 0 )
    goto LABEL_33;
LABEL_41:
  KeReleaseMutex(v1, 0);
  if ( v3 )
    FveLibFreeWithTag(v3, v4, 2);
  return (unsigned int)ChatConfig;
}

```

## disassembly

```asm
0x1400f16fc  mov     rax, rsp
0x1400f16ff  mov     [rax+18h], rbx
0x1400f1703  mov     [rax+20h], rbp
0x1400f1707  push    rsi
0x1400f1708  push    rdi
0x1400f1709  push    r13
0x1400f170b  push    r14
0x1400f170d  push    r15
0x1400f170f  sub     rsp, 80h
0x1400f1716  xor     r13d, r13d
0x1400f1719  lea     r15, [rcx+2680h]
0x1400f1720  mov     rdi, rcx
0x1400f1723  mov     [rax+10h], r13
0x1400f1727  mov     rcx, r15; Object
0x1400f172a  mov     [rax+8], r13d
0x1400f172e  xor     r9d, r9d; Alertable
0x1400f1731  mov     [rsp+0A8h+Timeout], r13; Timeout
0x1400f1736  xor     r8d, r8d; WaitMode
0x1400f1739  xor     edx, edx; WaitReason
0x1400f173b  mov     ebp, r13d
0x1400f173e  mov     r14d, r13d
0x1400f1741  call    cs:__imp_KeWaitForSingleObject
0x1400f1748  nop     dword ptr [rax+rax+00h]
0x1400f174d  mov     rcx, rdi
0x1400f1750  call    FveConfigRegisterEventCallbacks
0x1400f1755  xor     r8d, r8d
0x1400f1758  xor     edx, edx
0x1400f175a  mov     rcx, rdi
0x1400f175d  call    FveLoadChatConfig
0x1400f1762  mov     esi, eax
0x1400f1764  cmp     [rdi+658h], r13
0x1400f176b  jnz     short loc_1400F1784
0x1400f176d  test    esi, esi
0x1400f176f  mov     eax, 0C0000001h
0x1400f1774  cmovs   esi, eax
0x1400f1777  test    esi, esi
0x1400f1779  jns     loc_1400F1CAC
0x1400f177f  jmp     loc_1400F1BEF
0x1400f1784  xor     r9d, r9d
0x1400f1787  xor     r8d, r8d
0x1400f178a  xor     edx, edx
0x1400f178c  mov     rcx, rdi
0x1400f178f  call    FveLoadCryptoThrottleConfig
0x1400f1794  xor     r9d, r9d
0x1400f1797  mov     [rsp+0A8h+Timeout], r13
0x1400f179c  xor     r8d, r8d
0x1400f179f  xor     edx, edx
0x1400f17a1  mov     rcx, rdi
0x1400f17a4  call    FveLoadIoCryptoConfig
0x1400f17a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f17b0  lea     rsi, WPP_GLOBAL_Control
0x1400f17b7  cmp     rcx, rsi
0x1400f17ba  jz      loc_1400F1939
0x1400f17c0  mov     eax, [rcx+2Ch]
0x1400f17c3  mov     bl, 4
0x1400f17c5  test    al, al
0x1400f17c7  jns     loc_1400F187B
0x1400f17cd  cmp     [rcx+29h], bl
0x1400f17d0  jb      loc_1400F187B
0x1400f17d6  mov     r9d, [rdi+374h]
0x1400f17dd  mov     edx, 34h ; '4'
0x1400f17e2  mov     rcx, [rcx+18h]
0x1400f17e6  mov     eax, [rdi+r9*4+444h]
0x1400f17ee  mov     [rsp+0A8h+var_30], eax
0x1400f17f2  mov     eax, [rdi+r9*4+438h]
0x1400f17fa  mov     [rsp+0A8h+var_38], eax
0x1400f17fe  mov     eax, [rdi+r9*4+42Ch]
0x1400f1806  mov     [rsp+0A8h+var_40], eax
0x1400f180a  mov     eax, [rdi+r9*4+420h]
0x1400f1812  mov     [rsp+0A8h+var_48], eax
0x1400f1816  mov     eax, [rdi+r9*4+414h]
0x1400f181e  mov     [rsp+0A8h+var_50], eax
0x1400f1822  mov     eax, [rdi+r9*4+408h]
0x1400f182a  mov     [rsp+0A8h+var_58], eax
0x1400f182e  mov     eax, [rdi+r9*4+3FCh]
0x1400f1836  mov     [rsp+0A8h+var_60], eax
0x1400f183a  mov     eax, [rdi+r9*4+3E4h]
0x1400f1842  mov     [rsp+0A8h+var_68], eax
0x1400f1846  mov     eax, [rdi+r9*4+3D8h]
0x1400f184e  mov     [rsp+0A8h+var_70], eax
0x1400f1852  mov     eax, [rdi+r9*4+3C0h]
0x1400f185a  mov     dword ptr [rsp+0A8h+Depth], eax
0x1400f185e  mov     eax, [rdi+r9*4+3B4h]
0x1400f1866  mov     [rsp+0A8h+Tag], eax
0x1400f186a  mov     eax, [rdi+r9*4+3A8h]
0x1400f1872  mov     dword ptr [rsp+0A8h+Timeout], eax
0x1400f1876  call    WPP_SF_LDDDDDDDDDDDD
0x1400f187b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f1882  cmp     rcx, rsi
0x1400f1885  jz      loc_1400F1939
0x1400f188b  mov     eax, [rcx+2Ch]
0x1400f188e  test    al, al
0x1400f1890  jns     short loc_1400F18DC
0x1400f1892  cmp     [rcx+29h], bl
0x1400f1895  jb      short loc_1400F18DC
0x1400f1897  mov     r9d, [rdi+374h]
0x1400f189e  mov     edx, 35h ; '5'
0x1400f18a3  mov     rcx, [rcx+18h]
0x1400f18a7  mov     eax, [rdi+r9*4+3F0h]
0x1400f18af  mov     [rsp+0A8h+var_70], eax
0x1400f18b3  mov     eax, [rdi+r9*4+3CCh]
0x1400f18bb  mov     dword ptr [rsp+0A8h+Depth], eax
0x1400f18bf  mov     eax, [rdi+r9*4+45Ch]
0x1400f18c7  mov     [rsp+0A8h+Tag], eax
0x1400f18cb  mov     eax, [rdi+r9*4+450h]
0x1400f18d3  mov     dword ptr [rsp+0A8h+Timeout], eax
0x1400f18d7  call    WPP_SF_LDDDD
0x1400f18dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f18e3  cmp     rcx, rsi
0x1400f18e6  jz      short loc_1400F1939
0x1400f18e8  mov     eax, [rcx+2Ch]
0x1400f18eb  test    al, al
0x1400f18ed  jns     short loc_1400F1939
0x1400f18ef  cmp     [rcx+29h], bl
0x1400f18f2  jb      short loc_1400F1939
0x1400f18f4  mov     r9d, [rdi+374h]
0x1400f18fb  mov     edx, 36h ; '6'
0x1400f1900  mov     rcx, [rcx+18h]
0x1400f1904  mov     eax, [rdi+r9*4+574h]
0x1400f190c  mov     [rsp+0A8h+var_70], eax
0x1400f1910  mov     eax, [rdi+r9*4+550h]
0x1400f1918  mov     dword ptr [rsp+0A8h+Depth], eax
0x1400f191c  mov     eax, [rdi+r9*4+568h]
0x1400f1924  mov     [rsp+0A8h+Tag], eax
0x1400f1928  mov     eax, [rdi+r9*4+55Ch]
0x1400f1930  mov     dword ptr [rsp+0A8h+Timeout], eax
0x1400f1934  call    WPP_SF_LDDDD
0x1400f1939  mov     rcx, [rdi+660h]; Size
0x1400f1940  lea     r8, [rsp+0A8h+pbInput]
0x1400f1948  mov     edx, 2
0x1400f194d  call    FveLibAllocWithTagZero
0x1400f1952  mov     esi, eax
0x1400f1954  test    eax, eax
0x1400f1956  js      loc_1400F1BE7
0x1400f195c  mov     rcx, [rdi+660h]; ullOperand
0x1400f1963  lea     rdx, [rsp+0A8h+pulResult]; pulResult
0x1400f196b  call    RtlULongLongToULong
0x1400f1970  mov     esi, eax
0x1400f1972  test    eax, eax
0x1400f1974  js      loc_1400F1BDF
0x1400f197a  mov     r8d, dword ptr [rsp+0A8h+pulResult]; Size
0x1400f1982  mov     rdx, [rdi+658h]; Src
0x1400f1989  mov     rcx, [rsp+0A8h+pbInput]; void *
0x1400f1991  call    memmove
0x1400f1996  mov     edx, dword ptr [rsp+0A8h+pulResult]; cbInput
0x1400f199d  mov     rcx, [rsp+0A8h+pbInput]; pbInput
0x1400f19a5  call    FveChatConfig
0x1400f19aa  mov     rcx, rdi
0x1400f19ad  call    FveReadWriteSubrequestTransitionsInit
0x1400f19b2  mov     ecx, [rdi+374h]
0x1400f19b8  lea     rdx, [rdi+0AB0h]
0x1400f19bf  mov     ecx, [rdi+rcx*4+55Ch]
0x1400f19c6  call    FveCryptoThrottleInit
0x1400f19cb  mov     ecx, [rdi+374h]
0x1400f19d1  lea     rdx, [rdi+1768h]
0x1400f19d8  mov     ecx, [rdi+rcx*4+568h]
0x1400f19df  call    FveCryptoThrottleInit
0x1400f19e4  mov     edx, 80h
0x1400f19e9  mov     [rdi+2420h], r13
0x1400f19f0  mov     r8d, 30455646h
0x1400f19f6  mov     [rdi+2428h], r13
0x1400f19fd  mov     [rdi+2430h], r13
0x1400f1a04  mov     [rdi+2438h], r13
0x1400f1a0b  lea     ecx, [rdx-40h]
0x1400f1a0e  call    cs:__imp_ExAllocatePool2
0x1400f1a15  nop     dword ptr [rax+rax+00h]
0x1400f1a1a  mov     [rdi+2420h], rax
0x1400f1a21  mov     rcx, rax; Lookaside
0x1400f1a24  test    rax, rax
0x1400f1a27  jnz     short loc_1400F1A33
0x1400f1a29  mov     esi, 0C000009Ah
0x1400f1a2e  jmp     loc_1400F1BEF
0x1400f1a33  mov     [rsp+0A8h+Depth], r13w; Depth
0x1400f1a39  mov     r9d, 200h; Flags
0x1400f1a3f  mov     [rsp+0A8h+Tag], 78455646h; Tag
0x1400f1a47  xor     r8d, r8d; Free
0x1400f1a4a  xor     edx, edx; Allocate
0x1400f1a4c  mov     [rsp+0A8h+Timeout], 1938h; int
0x1400f1a55  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400f1a5c  nop     dword ptr [rax+rax+00h]
0x1400f1a61  mov     eax, [rdi+374h]
0x1400f1a67  xor     ecx, ecx; Base
0x1400f1a69  mov     ebx, [rdi+rax*4+3A8h]
0x1400f1a70  mov     eax, [rdi+374h]
0x1400f1a76  mov     edx, [rdi+rax*4+3A8h]; Length
0x1400f1a7d  call    cs:__imp_MmSizeOfMdl
0x1400f1a84  nop     dword ptr [rax+rax+00h]
0x1400f1a89  add     ebx, 40h ; '@'
0x1400f1a8c  add     ebx, eax
0x1400f1a8e  call    cs:__imp_MmIsThisAnNtAsSystem
0x1400f1a95  nop     dword ptr [rax+rax+00h]
0x1400f1a9a  test    al, al
0x1400f1a9c  jz      loc_1400F1B26
0x1400f1aa2  mov     ecx, cs:Feature_BitLocker_PerProc_Buffer__private_featureState
0x1400f1aa8  mov     [rsp+0A8h+pulResult], r13
0x1400f1ab0  mov     dword ptr [rsp+0A8h+pulResult], ecx
0x1400f1ab7  test    cl, 10h
0x1400f1aba  jnz     short loc_1400F1B09
0x1400f1abc  mov     rax, [rsp+0A8h+pulResult]
0x1400f1ac4  or      ecx, 1
0x1400f1ac7  mov     [rsp+0A8h+pulResult], rax
0x1400f1acf  mov     r8d, 3
0x1400f1ad5  mov     dword ptr [rsp+0A8h+pulResult], ecx
0x1400f1adc  lea     rcx, Feature_BitLocker_PerProc_Buffer__private_descriptor
0x1400f1ae3  mov     rdx, [rsp+0A8h+pulResult]
0x1400f1aeb  call    wil_details_FeatureReporting_ReportUsageToService
0x1400f1af0  mov     rcx, [rsp+0A8h+pulResult]
0x1400f1af8  lea     r8, Feature_BitLocker_PerProc_Buffer__private_descriptor
0x1400f1aff  mov     edx, 3
0x1400f1b04  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400f1b09  mov     eax, ebx
0x1400f1b0b  mov     qword ptr [rsp+0A8h+Tag], rax; SIZE_T
0x1400f1b10  call    PplCreateLookasideList
0x1400f1b15  mov     [rdi+2430h], rax
0x1400f1b1c  test    rax, rax
0x1400f1b1f  jnz     short loc_1400F1B7F
0x1400f1b21  jmp     loc_1400F1A29
0x1400f1b26  mov     edx, 80h
0x1400f1b2b  mov     r8d, 30455646h
0x1400f1b31  lea     ecx, [rdx-40h]
0x1400f1b34  call    cs:__imp_ExAllocatePool2
0x1400f1b3b  nop     dword ptr [rax+rax+00h]
0x1400f1b40  mov     [rdi+2428h], rax
0x1400f1b47  mov     rcx, rax; Lookaside
0x1400f1b4a  test    rax, rax
0x1400f1b4d  jz      loc_1400F1A29
0x1400f1b53  mov     edx, ebx
0x1400f1b55  mov     r9d, 200h; Flags
0x1400f1b5b  mov     [rsp+0A8h+Depth], r13w; Depth
0x1400f1b61  xor     r8d, r8d; Free
0x1400f1b64  mov     [rsp+0A8h+Tag], 70455646h; Tag
0x1400f1b6c  mov     [rsp+0A8h+Timeout], rdx; Size
0x1400f1b71  xor     edx, edx; Allocate
0x1400f1b73  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400f1b7a  nop     dword ptr [rax+rax+00h]
0x1400f1b7f  mov     edx, 80h
0x1400f1b84  mov     r8d, 30455646h
0x1400f1b8a  lea     ecx, [rdx-40h]
0x1400f1b8d  call    cs:__imp_ExAllocatePool2
0x1400f1b94  nop     dword ptr [rax+rax+00h]
0x1400f1b99  mov     [rdi+2438h], rax
0x1400f1ba0  mov     rcx, rax; Lookaside
0x1400f1ba3  test    rax, rax
0x1400f1ba6  jz      loc_1400F1A29
0x1400f1bac  mov     [rsp+0A8h+Depth], r13w; Depth
0x1400f1bb2  mov     r9d, 200h; Flags
0x1400f1bb8  mov     [rsp+0A8h+Tag], 656E6F4Eh; Tag
0x1400f1bc0  xor     r8d, r8d; Free
0x1400f1bc3  xor     edx, edx; Allocate
0x1400f1bc5  mov     [rsp+0A8h+Timeout], 10h; Size
0x1400f1bce  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400f1bd5  nop     dword ptr [rax+rax+00h]
0x1400f1bda  jmp     loc_1400F1CAC
0x1400f1bdf  mov     r14d, dword ptr [rsp+0A8h+pulResult]
0x1400f1be7  mov     rbp, [rsp+0A8h+pbInput]
0x1400f1bef  mov     rcx, [rdi+2420h]; Lookaside
0x1400f1bf6  test    rcx, rcx
0x1400f1bf9  jz      short loc_1400F1C26
0x1400f1bfb  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400f1c02  nop     dword ptr [rax+rax+00h]
0x1400f1c07  mov     rcx, [rdi+2420h]; P
0x1400f1c0e  mov     edx, 30455646h; Tag
0x1400f1c13  call    cs:__imp_ExFreePoolWithTag
0x1400f1c1a  nop     dword ptr [rax+rax+00h]
0x1400f1c1f  mov     [rdi+2420h], r13
0x1400f1c26  mov     rcx, [rdi+2428h]; Lookaside
0x1400f1c2d  test    rcx, rcx
0x1400f1c30  jz      short loc_1400F1C5D
0x1400f1c32  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400f1c39  nop     dword ptr [rax+rax+00h]
0x1400f1c3e  mov     rcx, [rdi+2428h]; P
0x1400f1c45  mov     edx, 30455646h; Tag
0x1400f1c4a  call    cs:__imp_ExFreePoolWithTag
0x1400f1c51  nop     dword ptr [rax+rax+00h]
0x1400f1c56  mov     [rdi+2428h], r13
0x1400f1c5d  mov     rcx, [rdi+2430h]; P
0x1400f1c64  test    rcx, rcx
0x1400f1c67  jz      short loc_1400F1C75
0x1400f1c69  call    PplDestroyLookasideList
0x1400f1c6e  mov     [rdi+2430h], r13
0x1400f1c75  mov     rcx, [rdi+2438h]; Lookaside
0x1400f1c7c  test    rcx, rcx
0x1400f1c7f  jz      short loc_1400F1CAC
0x1400f1c81  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400f1c88  nop     dword ptr [rax+rax+00h]
0x1400f1c8d  mov     rcx, [rdi+2438h]; P
0x1400f1c94  mov     edx, 656E6F4Eh; Tag
0x1400f1c99  call    cs:__imp_ExFreePoolWithTag
0x1400f1ca0  nop     dword ptr [rax+rax+00h]
0x1400f1ca5  mov     [rdi+2438h], r13
0x1400f1cac  xor     edx, edx; Wait
0x1400f1cae  mov     rcx, r15; Mutex
0x1400f1cb1  call    cs:__imp_KeReleaseMutex
0x1400f1cb8  nop     dword ptr [rax+rax+00h]
0x1400f1cbd  test    rbp, rbp
0x1400f1cc0  jz      short loc_1400F1CD3
0x1400f1cc2  mov     edx, r14d
0x1400f1cc5  mov     r8d, 2
0x1400f1ccb  mov     rcx, rbp
0x1400f1cce  call    FveLibFreeWithTag
  ... truncated ...
```
