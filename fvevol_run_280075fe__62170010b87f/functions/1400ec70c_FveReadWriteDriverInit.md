# FveReadWriteDriverInit

- ea: `0x1400ec70c`
- end: `0x1400ecd02`
- name: `FveReadWriteDriverInit`
- size: `1526`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x1400eb6e0`

## callees

- `0x140005edc`
- `0x1400063a8`
- `0x140006670`
- `0x14000a574`
- `0x14000b3ac`
- `0x14000b62c`
- `0x14000f724`
- `0x14000f820`
- `0x14000f8a4`
- `0x14001ac5c`
- `0x140021a00`
- `0x140072e68`
- `0x140073118`
- `0x140082540`
- `0x140091688`
- `0x1400ec70c`
- `0x1400ecd08`
- `0x1400ed800`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400eccc1`
- `ntoskrnl!KeReleaseMutex` at `0x1400eccc1`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x1400eca9e`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x1400eca9e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400eca65`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400ecb83`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400ecbde`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400eca65`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400ecb83`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400ecbde`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ecc0b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ecc42`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ecc91`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ecc0b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ecc42`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ecc91`
- `ntoskrnl!MmSizeOfMdl` at `0x1400eca8d`
- `ntoskrnl!MmSizeOfMdl` at `0x1400eca8d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ec751`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ec751`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ecc23`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ecc5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ecca9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ecc23`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ecc5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ecca9`
- `ntoskrnl!ExAllocatePool2` at `0x1400eca1e`
- `ntoskrnl!ExAllocatePool2` at `0x1400ecb44`
- `ntoskrnl!ExAllocatePool2` at `0x1400ecb9d`
- `ntoskrnl!ExAllocatePool2` at `0x1400eca1e`
- `ntoskrnl!ExAllocatePool2` at `0x1400ecb44`
- `ntoskrnl!ExAllocatePool2` at `0x1400ecb9d`

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

  v1 = (struct _KMUTANT *)(a1 + 9608);
  pbInput = 0;
  LODWORD(pulResult) = 0;
  v3 = 0;
  v4 = 0;
  KeWaitForSingleObject((PVOID)(a1 + 9608), Executive, 0, 0, 0);
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
        FveCryptoThrottleInit(*(unsigned int *)(a1 + 4LL * *(unsigned int *)(a1 + 884) + 1372), a1 + 2488);
        FveCryptoThrottleInit(*(unsigned int *)(a1 + 4LL * *(unsigned int *)(a1 + 884) + 1384), a1 + 5744);
        *(_QWORD *)(a1 + 9000) = 0;
        *(_QWORD *)(a1 + 9008) = 0;
        *(_QWORD *)(a1 + 9016) = 0;
        *(_QWORD *)(a1 + 9024) = 0;
        Pool2 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 809850438);
        *(_QWORD *)(a1 + 9000) = Pool2;
        if ( !Pool2 )
        {
LABEL_21:
          ChatConfig = -1073741670;
LABEL_33:
          v18 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9000);
          if ( v18 )
          {
            ExDeleteNPagedLookasideList(v18);
            ExFreePoolWithTag(*(PVOID *)(a1 + 9000), 0x30455646u);
            *(_QWORD *)(a1 + 9000) = 0;
          }
          v19 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9008);
          if ( v19 )
          {
            ExDeleteNPagedLookasideList(v19);
            ExFreePoolWithTag(*(PVOID *)(a1 + 9008), 0x30455646u);
            *(_QWORD *)(a1 + 9008) = 0;
          }
          v20 = *(void **)(a1 + 9016);
          if ( v20 )
          {
            PplDestroyLookasideList(v20);
            *(_QWORD *)(a1 + 9016) = 0;
          }
          v21 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 9024);
          if ( v21 )
          {
            ExDeleteNPagedLookasideList(v21);
            ExFreePoolWithTag(*(PVOID *)(a1 + 9024), 0x656E6F4Eu);
            *(_QWORD *)(a1 + 9024) = 0;
          }
          goto LABEL_41;
        }
        ExInitializeNPagedLookasideList(Pool2, 0, 0, 0x200u, 0x1728u, 0x78455646u, 0);
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
          *(_QWORD *)(a1 + 9016) = LookasideList;
          if ( !LookasideList )
            goto LABEL_21;
        }
        else
        {
          v16 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 809850438);
          *(_QWORD *)(a1 + 9008) = v16;
          if ( !v16 )
            goto LABEL_21;
          ExInitializeNPagedLookasideList(v16, 0, 0, 0x200u, v10, 0x70455646u, 0);
        }
        v17 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 809850438);
        *(_QWORD *)(a1 + 9024) = v17;
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
0x1400ec70c  mov     rax, rsp
0x1400ec70f  mov     [rax+18h], rbx
0x1400ec713  mov     [rax+20h], rbp
0x1400ec717  push    rsi
0x1400ec718  push    rdi
0x1400ec719  push    r13
0x1400ec71b  push    r14
0x1400ec71d  push    r15
0x1400ec71f  sub     rsp, 80h
0x1400ec726  xor     r13d, r13d
0x1400ec729  lea     r15, [rcx+2588h]
0x1400ec730  mov     rdi, rcx
0x1400ec733  mov     [rax+10h], r13
0x1400ec737  mov     rcx, r15; Object
0x1400ec73a  mov     [rax+8], r13d
0x1400ec73e  xor     r9d, r9d; Alertable
0x1400ec741  mov     [rsp+0A8h+Timeout], r13; Timeout
0x1400ec746  xor     r8d, r8d; WaitMode
0x1400ec749  xor     edx, edx; WaitReason
0x1400ec74b  mov     ebp, r13d
0x1400ec74e  mov     r14d, r13d
0x1400ec751  call    cs:__imp_KeWaitForSingleObject
0x1400ec758  nop     dword ptr [rax+rax+00h]
0x1400ec75d  mov     rcx, rdi
0x1400ec760  call    FveConfigRegisterEventCallbacks
0x1400ec765  xor     r8d, r8d
0x1400ec768  xor     edx, edx
0x1400ec76a  mov     rcx, rdi
0x1400ec76d  call    FveLoadChatConfig
0x1400ec772  mov     esi, eax
0x1400ec774  cmp     [rdi+658h], r13
0x1400ec77b  jnz     short loc_1400EC794
0x1400ec77d  test    esi, esi
0x1400ec77f  mov     eax, 0C0000001h
0x1400ec784  cmovs   esi, eax
0x1400ec787  test    esi, esi
0x1400ec789  jns     loc_1400ECCBC
0x1400ec78f  jmp     loc_1400ECBFF
0x1400ec794  xor     r9d, r9d
0x1400ec797  xor     r8d, r8d
0x1400ec79a  xor     edx, edx
0x1400ec79c  mov     rcx, rdi
0x1400ec79f  call    FveLoadCryptoThrottleConfig
0x1400ec7a4  xor     r9d, r9d
0x1400ec7a7  mov     [rsp+0A8h+Timeout], r13
0x1400ec7ac  xor     r8d, r8d
0x1400ec7af  xor     edx, edx
0x1400ec7b1  mov     rcx, rdi
0x1400ec7b4  call    FveLoadIoCryptoConfig
0x1400ec7b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ec7c0  lea     rsi, WPP_GLOBAL_Control
0x1400ec7c7  cmp     rcx, rsi
0x1400ec7ca  jz      loc_1400EC949
0x1400ec7d0  mov     eax, [rcx+2Ch]
0x1400ec7d3  mov     bl, 4
0x1400ec7d5  test    al, al
0x1400ec7d7  jns     loc_1400EC88B
0x1400ec7dd  cmp     [rcx+29h], bl
0x1400ec7e0  jb      loc_1400EC88B
0x1400ec7e6  mov     r9d, [rdi+374h]
0x1400ec7ed  mov     edx, 34h ; '4'
0x1400ec7f2  mov     rcx, [rcx+18h]
0x1400ec7f6  mov     eax, [rdi+r9*4+444h]
0x1400ec7fe  mov     [rsp+0A8h+var_30], eax
0x1400ec802  mov     eax, [rdi+r9*4+438h]
0x1400ec80a  mov     [rsp+0A8h+var_38], eax
0x1400ec80e  mov     eax, [rdi+r9*4+42Ch]
0x1400ec816  mov     [rsp+0A8h+var_40], eax
0x1400ec81a  mov     eax, [rdi+r9*4+420h]
0x1400ec822  mov     [rsp+0A8h+var_48], eax
0x1400ec826  mov     eax, [rdi+r9*4+414h]
0x1400ec82e  mov     [rsp+0A8h+var_50], eax
0x1400ec832  mov     eax, [rdi+r9*4+408h]
0x1400ec83a  mov     [rsp+0A8h+var_58], eax
0x1400ec83e  mov     eax, [rdi+r9*4+3FCh]
0x1400ec846  mov     [rsp+0A8h+var_60], eax
0x1400ec84a  mov     eax, [rdi+r9*4+3E4h]
0x1400ec852  mov     [rsp+0A8h+var_68], eax
0x1400ec856  mov     eax, [rdi+r9*4+3D8h]
0x1400ec85e  mov     [rsp+0A8h+var_70], eax
0x1400ec862  mov     eax, [rdi+r9*4+3C0h]
0x1400ec86a  mov     dword ptr [rsp+0A8h+Depth], eax
0x1400ec86e  mov     eax, [rdi+r9*4+3B4h]
0x1400ec876  mov     [rsp+0A8h+Tag], eax
0x1400ec87a  mov     eax, [rdi+r9*4+3A8h]
0x1400ec882  mov     dword ptr [rsp+0A8h+Timeout], eax
0x1400ec886  call    WPP_SF_LDDDDDDDDDDDD
0x1400ec88b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ec892  cmp     rcx, rsi
0x1400ec895  jz      loc_1400EC949
0x1400ec89b  mov     eax, [rcx+2Ch]
0x1400ec89e  test    al, al
0x1400ec8a0  jns     short loc_1400EC8EC
0x1400ec8a2  cmp     [rcx+29h], bl
0x1400ec8a5  jb      short loc_1400EC8EC
0x1400ec8a7  mov     r9d, [rdi+374h]
0x1400ec8ae  mov     edx, 35h ; '5'
0x1400ec8b3  mov     rcx, [rcx+18h]
0x1400ec8b7  mov     eax, [rdi+r9*4+3F0h]
0x1400ec8bf  mov     [rsp+0A8h+var_70], eax
0x1400ec8c3  mov     eax, [rdi+r9*4+3CCh]
0x1400ec8cb  mov     dword ptr [rsp+0A8h+Depth], eax
0x1400ec8cf  mov     eax, [rdi+r9*4+45Ch]
0x1400ec8d7  mov     [rsp+0A8h+Tag], eax
0x1400ec8db  mov     eax, [rdi+r9*4+450h]
0x1400ec8e3  mov     dword ptr [rsp+0A8h+Timeout], eax
0x1400ec8e7  call    WPP_SF_LDDDD
0x1400ec8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ec8f3  cmp     rcx, rsi
0x1400ec8f6  jz      short loc_1400EC949
0x1400ec8f8  mov     eax, [rcx+2Ch]
0x1400ec8fb  test    al, al
0x1400ec8fd  jns     short loc_1400EC949
0x1400ec8ff  cmp     [rcx+29h], bl
0x1400ec902  jb      short loc_1400EC949
0x1400ec904  mov     r9d, [rdi+374h]
0x1400ec90b  mov     edx, 36h ; '6'
0x1400ec910  mov     rcx, [rcx+18h]
0x1400ec914  mov     eax, [rdi+r9*4+574h]
0x1400ec91c  mov     [rsp+0A8h+var_70], eax
0x1400ec920  mov     eax, [rdi+r9*4+550h]
0x1400ec928  mov     dword ptr [rsp+0A8h+Depth], eax
0x1400ec92c  mov     eax, [rdi+r9*4+568h]
0x1400ec934  mov     [rsp+0A8h+Tag], eax
0x1400ec938  mov     eax, [rdi+r9*4+55Ch]
0x1400ec940  mov     dword ptr [rsp+0A8h+Timeout], eax
0x1400ec944  call    WPP_SF_LDDDD
0x1400ec949  mov     rcx, [rdi+660h]; Size
0x1400ec950  lea     r8, [rsp+0A8h+pbInput]
0x1400ec958  mov     edx, 2
0x1400ec95d  call    FveLibAllocWithTagZero
0x1400ec962  mov     esi, eax
0x1400ec964  test    eax, eax
0x1400ec966  js      loc_1400ECBF7
0x1400ec96c  mov     rcx, [rdi+660h]; ullOperand
0x1400ec973  lea     rdx, [rsp+0A8h+pulResult]; pulResult
0x1400ec97b  call    RtlULongLongToULong
0x1400ec980  mov     esi, eax
0x1400ec982  test    eax, eax
0x1400ec984  js      loc_1400ECBEF
0x1400ec98a  mov     r8d, dword ptr [rsp+0A8h+pulResult]; Size
0x1400ec992  mov     rdx, [rdi+658h]; Src
0x1400ec999  mov     rcx, [rsp+0A8h+pbInput]; void *
0x1400ec9a1  call    memmove
0x1400ec9a6  mov     edx, dword ptr [rsp+0A8h+pulResult]; cbInput
0x1400ec9ad  mov     rcx, [rsp+0A8h+pbInput]; pbInput
0x1400ec9b5  call    FveChatConfig
0x1400ec9ba  mov     rcx, rdi
0x1400ec9bd  call    FveReadWriteSubrequestTransitionsInit
0x1400ec9c2  mov     ecx, [rdi+374h]
0x1400ec9c8  lea     rdx, [rdi+9B8h]
0x1400ec9cf  mov     ecx, [rdi+rcx*4+55Ch]
0x1400ec9d6  call    FveCryptoThrottleInit
0x1400ec9db  mov     ecx, [rdi+374h]
0x1400ec9e1  lea     rdx, [rdi+1670h]
0x1400ec9e8  mov     ecx, [rdi+rcx*4+568h]
0x1400ec9ef  call    FveCryptoThrottleInit
0x1400ec9f4  mov     edx, 80h
0x1400ec9f9  mov     [rdi+2328h], r13
0x1400eca00  mov     r8d, 30455646h
0x1400eca06  mov     [rdi+2330h], r13
0x1400eca0d  mov     [rdi+2338h], r13
0x1400eca14  mov     [rdi+2340h], r13
0x1400eca1b  lea     ecx, [rdx-40h]
0x1400eca1e  call    cs:__imp_ExAllocatePool2
0x1400eca25  nop     dword ptr [rax+rax+00h]
0x1400eca2a  mov     [rdi+2328h], rax
0x1400eca31  mov     rcx, rax; Lookaside
0x1400eca34  test    rax, rax
0x1400eca37  jnz     short loc_1400ECA43
0x1400eca39  mov     esi, 0C000009Ah
0x1400eca3e  jmp     loc_1400ECBFF
0x1400eca43  mov     [rsp+0A8h+Depth], r13w; Depth
0x1400eca49  mov     r9d, 200h; Flags
0x1400eca4f  mov     [rsp+0A8h+Tag], 78455646h; Tag
0x1400eca57  xor     r8d, r8d; Free
0x1400eca5a  xor     edx, edx; Allocate
0x1400eca5c  mov     [rsp+0A8h+Timeout], 1728h; int
0x1400eca65  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400eca6c  nop     dword ptr [rax+rax+00h]
0x1400eca71  mov     eax, [rdi+374h]
0x1400eca77  xor     ecx, ecx; Base
0x1400eca79  mov     ebx, [rdi+rax*4+3A8h]
0x1400eca80  mov     eax, [rdi+374h]
0x1400eca86  mov     edx, [rdi+rax*4+3A8h]; Length
0x1400eca8d  call    cs:__imp_MmSizeOfMdl
0x1400eca94  nop     dword ptr [rax+rax+00h]
0x1400eca99  add     ebx, 40h ; '@'
0x1400eca9c  add     ebx, eax
0x1400eca9e  call    cs:__imp_MmIsThisAnNtAsSystem
0x1400ecaa5  nop     dword ptr [rax+rax+00h]
0x1400ecaaa  test    al, al
0x1400ecaac  jz      loc_1400ECB36
0x1400ecab2  mov     ecx, cs:Feature_BitLocker_PerProc_Buffer__private_featureState
0x1400ecab8  mov     [rsp+0A8h+pulResult], r13
0x1400ecac0  mov     dword ptr [rsp+0A8h+pulResult], ecx
0x1400ecac7  test    cl, 10h
0x1400ecaca  jnz     short loc_1400ECB19
0x1400ecacc  mov     rax, [rsp+0A8h+pulResult]
0x1400ecad4  or      ecx, 1
0x1400ecad7  mov     [rsp+0A8h+pulResult], rax
0x1400ecadf  mov     r8d, 3
0x1400ecae5  mov     dword ptr [rsp+0A8h+pulResult], ecx
0x1400ecaec  lea     rcx, Feature_BitLocker_PerProc_Buffer__private_descriptor
0x1400ecaf3  mov     rdx, [rsp+0A8h+pulResult]
0x1400ecafb  call    wil_details_FeatureReporting_ReportUsageToService
0x1400ecb00  mov     rcx, [rsp+0A8h+pulResult]
0x1400ecb08  lea     r8, Feature_BitLocker_PerProc_Buffer__private_descriptor
0x1400ecb0f  mov     edx, 3
0x1400ecb14  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400ecb19  mov     eax, ebx
0x1400ecb1b  mov     qword ptr [rsp+0A8h+Tag], rax; SIZE_T
0x1400ecb20  call    PplCreateLookasideList
0x1400ecb25  mov     [rdi+2338h], rax
0x1400ecb2c  test    rax, rax
0x1400ecb2f  jnz     short loc_1400ECB8F
0x1400ecb31  jmp     loc_1400ECA39
0x1400ecb36  mov     edx, 80h
0x1400ecb3b  mov     r8d, 30455646h
0x1400ecb41  lea     ecx, [rdx-40h]
0x1400ecb44  call    cs:__imp_ExAllocatePool2
0x1400ecb4b  nop     dword ptr [rax+rax+00h]
0x1400ecb50  mov     [rdi+2330h], rax
0x1400ecb57  mov     rcx, rax; Lookaside
0x1400ecb5a  test    rax, rax
0x1400ecb5d  jz      loc_1400ECA39
0x1400ecb63  mov     edx, ebx
0x1400ecb65  mov     r9d, 200h; Flags
0x1400ecb6b  mov     [rsp+0A8h+Depth], r13w; Depth
0x1400ecb71  xor     r8d, r8d; Free
0x1400ecb74  mov     [rsp+0A8h+Tag], 70455646h; Tag
0x1400ecb7c  mov     [rsp+0A8h+Timeout], rdx; Size
0x1400ecb81  xor     edx, edx; Allocate
0x1400ecb83  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400ecb8a  nop     dword ptr [rax+rax+00h]
0x1400ecb8f  mov     edx, 80h
0x1400ecb94  mov     r8d, 30455646h
0x1400ecb9a  lea     ecx, [rdx-40h]
0x1400ecb9d  call    cs:__imp_ExAllocatePool2
0x1400ecba4  nop     dword ptr [rax+rax+00h]
0x1400ecba9  mov     [rdi+2340h], rax
0x1400ecbb0  mov     rcx, rax; Lookaside
0x1400ecbb3  test    rax, rax
0x1400ecbb6  jz      loc_1400ECA39
0x1400ecbbc  mov     [rsp+0A8h+Depth], r13w; Depth
0x1400ecbc2  mov     r9d, 200h; Flags
0x1400ecbc8  mov     [rsp+0A8h+Tag], 656E6F4Eh; Tag
0x1400ecbd0  xor     r8d, r8d; Free
0x1400ecbd3  xor     edx, edx; Allocate
0x1400ecbd5  mov     [rsp+0A8h+Timeout], 10h; Size
0x1400ecbde  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400ecbe5  nop     dword ptr [rax+rax+00h]
0x1400ecbea  jmp     loc_1400ECCBC
0x1400ecbef  mov     r14d, dword ptr [rsp+0A8h+pulResult]
0x1400ecbf7  mov     rbp, [rsp+0A8h+pbInput]
0x1400ecbff  mov     rcx, [rdi+2328h]; Lookaside
0x1400ecc06  test    rcx, rcx
0x1400ecc09  jz      short loc_1400ECC36
0x1400ecc0b  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400ecc12  nop     dword ptr [rax+rax+00h]
0x1400ecc17  mov     rcx, [rdi+2328h]; P
0x1400ecc1e  mov     edx, 30455646h; Tag
0x1400ecc23  call    cs:__imp_ExFreePoolWithTag
0x1400ecc2a  nop     dword ptr [rax+rax+00h]
0x1400ecc2f  mov     [rdi+2328h], r13
0x1400ecc36  mov     rcx, [rdi+2330h]; Lookaside
0x1400ecc3d  test    rcx, rcx
0x1400ecc40  jz      short loc_1400ECC6D
0x1400ecc42  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400ecc49  nop     dword ptr [rax+rax+00h]
0x1400ecc4e  mov     rcx, [rdi+2330h]; P
0x1400ecc55  mov     edx, 30455646h; Tag
0x1400ecc5a  call    cs:__imp_ExFreePoolWithTag
0x1400ecc61  nop     dword ptr [rax+rax+00h]
0x1400ecc66  mov     [rdi+2330h], r13
0x1400ecc6d  mov     rcx, [rdi+2338h]; P
0x1400ecc74  test    rcx, rcx
0x1400ecc77  jz      short loc_1400ECC85
0x1400ecc79  call    PplDestroyLookasideList
0x1400ecc7e  mov     [rdi+2338h], r13
0x1400ecc85  mov     rcx, [rdi+2340h]; Lookaside
0x1400ecc8c  test    rcx, rcx
0x1400ecc8f  jz      short loc_1400ECCBC
0x1400ecc91  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400ecc98  nop     dword ptr [rax+rax+00h]
0x1400ecc9d  mov     rcx, [rdi+2340h]; P
0x1400ecca4  mov     edx, 656E6F4Eh; Tag
0x1400ecca9  call    cs:__imp_ExFreePoolWithTag
0x1400eccb0  nop     dword ptr [rax+rax+00h]
0x1400eccb5  mov     [rdi+2340h], r13
0x1400eccbc  xor     edx, edx; Wait
0x1400eccbe  mov     rcx, r15; Mutex
0x1400eccc1  call    cs:__imp_KeReleaseMutex
0x1400eccc8  nop     dword ptr [rax+rax+00h]
0x1400ecccd  test    rbp, rbp
0x1400eccd0  jz      short loc_1400ECCE3
0x1400eccd2  mov     edx, r14d
0x1400eccd5  mov     r8d, 2
0x1400eccdb  mov     rcx, rbp
0x1400eccde  call    FveLibFreeWithTag
  ... truncated ...
```
