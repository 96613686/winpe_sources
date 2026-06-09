# KsecInsertValidAddress

- ea: `0x1800021bc`
- end: `0x1800025e3`
- name: `KsecInsertValidAddress`
- size: `1063`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int)`
- caller_count: `9`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002070`
- `0x180002140`
- `0x180004c74`
- `0x18000c93c`
- `0x18001f610`
- `0x18001f9e4`
- `0x180020b14`
- `0x180027738`
- `0x180027a18`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x1800021bc`
- `0x180007ba8`
- `0x180007bd8`
- `0x18000c7a0`
- `0x18000df18`
- `0x18000e0b0`
- `0x1800101a8`
- `0x180010980`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18000240c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000240c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180002424`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180002424`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000257d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800025c1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000257d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800025c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180002589`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800025cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180002589`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800025cd`
- `ntoskrnl!PsGetCurrentProcess` at `0x180002239`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800023dc`
- `ntoskrnl!PsGetCurrentProcess` at `0x180002239`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800023dc`
- `ntoskrnl!PsIsProtectedProcess` at `0x180002256`
- `ntoskrnl!PsIsProtectedProcess` at `0x180002256`
- `ntoskrnl!MmIsUserAddress` at `0x180002296`
- `ntoskrnl!MmIsUserAddress` at `0x180002296`
- `ntoskrnl!MmUserProbeAddress` at `0x180002206`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x180002305`
- `ntoskrnl!ZwQueryVirtualMemory` at `0x180002305`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800024a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800024a5`
- `ntoskrnl!ExAllocatePool2` at `0x180002467`
- `ntoskrnl!ExAllocatePool2` at `0x180002467`

## pseudocode

```c
__int64 __fastcall KsecInsertValidAddress(unsigned __int8 *a1, int a2, unsigned int a3, int a4)
{
  unsigned __int64 v5; // r12
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  struct _KSECDDLSASTATE *v11; // rbx
  NTSTATUS inserted; // edi
  char v13; // di
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  PVOID CurrentProcess; // rax
  int v20; // r14d
  unsigned __int8 *v21; // r13
  struct _EPROCESS *v22; // rax
  __int64 v23; // r8
  int v24; // r14d
  __int64 v25; // r14
  void *Pool2; // rax
  void *v27; // r12
  int v28; // r15d
  unsigned int v29; // eax
  struct _KSECDDLSASTATE *v30; // [rsp+40h] [rbp-40h] BYREF
  __int128 MemoryInformation; // [rsp+48h] [rbp-38h] BYREF
  __int128 v32; // [rsp+58h] [rbp-28h]
  __int128 v33; // [rsp+68h] [rbp-18h]
  char v34; // [rsp+C0h] [rbp+40h]

  LODWORD(v5) = a2;
  if ( !a1 )
    return 0;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v30);
  v11 = v30;
  if ( !v30 )
  {
    inserted = -1073741058;
LABEL_7:
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v30);
    return (unsigned int)inserted;
  }
  v13 = 0;
  v34 = 0;
  if ( (unsigned __int64)a1 <= MmUserProbeAddress )
  {
    if ( (a3 & 0x20) == 0 )
    {
LABEL_6:
      inserted = -1073741800;
      goto LABEL_7;
    }
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    CurrentProcess = (PVOID)PsGetCurrentProcess(v16, v15, v17, v18);
    if ( CurrentProcess != WPP_MAIN_CB.DeviceExtension )
    {
      if ( CurrentProcess == *(PVOID *)v11 || !(unsigned int)PsIsProtectedProcess(CurrentProcess) )
      {
        inserted = 0;
        goto LABEL_7;
      }
      v34 = 1;
      v20 = a3 & 1;
      goto LABEL_14;
    }
  }
  v20 = a3 & 1;
  if ( (a3 & 1) != 0 )
  {
LABEL_14:
    MemoryInformation = 0;
    v32 = 0;
    v33 = 0;
    if ( !(unsigned __int8)MmIsUserAddress(a1) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 26, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids);
      goto LABEL_6;
    }
    inserted = ZwQueryVirtualMemory(
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 a1,
                 MemoryBasicVlmInformation,
                 &MemoryInformation,
                 0x30u,
                 0);
    if ( inserted < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 3), 27, v9, a1, inserted);
      goto LABEL_7;
    }
    v10 = HIDWORD(MemoryInformation);
    if ( HIDWORD(MemoryInformation) != 0x20000 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          28,
          WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids,
          HIDWORD(MemoryInformation));
      inserted = -1073741503;
      goto LABEL_7;
    }
    if ( v20 )
    {
      v5 = v32 + MemoryInformation - (_QWORD)a1;
      if ( v5 > 0xFFFFFFFF )
      {
        inserted = -1073741675;
        goto LABEL_7;
      }
    }
    v13 = v34;
  }
  v21 = &a1[(unsigned int)v5];
  if ( v21 < a1 )
  {
    inserted = -1073741811;
    goto LABEL_7;
  }
  if ( v13 )
  {
    v22 = (struct _EPROCESS *)PsGetCurrentProcess(v8, v7, v9, v10);
    inserted = KsecInsertValidVm(v11, 0, v22, a1, v5, 1u);
    goto LABEL_7;
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx((char *)v11 + 568, 0);
  v24 = *((_DWORD *)v11 + 136);
  if ( *((_DWORD *)v11 + 137) == v24 )
  {
    v25 = (unsigned int)(v24 + 512);
    if ( (unsigned int)v25 >= 0xAAAAAAA
      || (Pool2 = (void *)ExAllocatePool2(256, 24 * v25, 1667593035), (v27 = Pool2) == 0) )
    {
      ExReleasePushLockExclusiveEx((char *)v11 + 568, 0);
      KeLeaveCriticalRegion();
      inserted = -1073741670;
      goto LABEL_7;
    }
    memmove(Pool2, *((const void **)v11 + 67), 24LL * *((unsigned int *)v11 + 137));
    ExFreePoolWithTag(*((PVOID *)v11 + 67), 0);
    *((_QWORD *)v11 + 67) = v27;
    *((_DWORD *)v11 + 136) = v25;
  }
  v28 = (a3 >> 1) & 1;
  *(_QWORD *)(*((_QWORD *)v11 + 67) + 24LL * *((unsigned int *)v11 + 137)) = a1;
  *(_QWORD *)(*((_QWORD *)v11 + 67) + 24LL * *((unsigned int *)v11 + 137) + 8) = v21;
  *(_DWORD *)(*((_QWORD *)v11 + 67) + 24LL * *((unsigned int *)v11 + 137) + 16) = v28;
  *(_DWORD *)(*((_QWORD *)v11 + 67) + 24LL * (unsigned int)(*((_DWORD *)v11 + 137))++ + 20) = a4;
  v29 = *((_DWORD *)v11 + 137);
  if ( v29 > *((_DWORD *)v11 + 138) )
    *((_DWORD *)v11 + 138) = v29;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0 )
    WPP_SF_qqLL(*((_QWORD *)WPP_GLOBAL_Control + 3), 29, v23, a1, v21, v28, *((_DWORD *)v11 + 137));
  ExReleasePushLockExclusiveEx((char *)v11 + 568, 0);
  KeLeaveCriticalRegion();
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v30);
  return 0;
}

```

## disassembly

```asm
0x1800021bc  mov     [rsp-38h+arg_8], rbx
0x1800021c1  mov     [rsp-38h+arg_18], r9d
0x1800021c6  push    rbp
0x1800021c7  push    rsi
0x1800021c8  push    rdi
0x1800021c9  push    r12
0x1800021cb  push    r13
0x1800021cd  push    r14
0x1800021cf  push    r15
0x1800021d1  mov     rbp, rsp
0x1800021d4  sub     rsp, 80h
0x1800021db  mov     r15d, r8d
0x1800021de  mov     r12d, edx
0x1800021e1  mov     rsi, rcx
0x1800021e4  test    rcx, rcx
0x1800021e7  jz      loc_18000259E
0x1800021ed  lea     rcx, [rbp+var_40]; this
0x1800021f1  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800021f6  mov     rbx, [rbp+var_40]
0x1800021fa  test    rbx, rbx
0x1800021fd  jnz     short loc_180002206
0x1800021ff  mov     edi, 0C00002FEh
0x180002204  jmp     short loc_180002224
0x180002206  mov     rax, cs:MmUserProbeAddress
0x18000220d  xor     dil, dil
0x180002210  mov     [rbp+arg_0], dil
0x180002214  cmp     rsi, [rax]
0x180002217  ja      short loc_180002277
0x180002219  test    r15b, 20h
0x18000221d  jnz     short loc_180002234
0x18000221f  mov     edi, 0C0000018h
0x180002224  lea     rcx, [rbp+var_40]; this
0x180002228  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000222d  mov     eax, edi
0x18000222f  jmp     loc_1800025A0
0x180002234  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x180002239  call    cs:__imp_PsGetCurrentProcess
0x180002240  nop     dword ptr [rax+rax+00h]
0x180002245  cmp     rax, cs:WPP_MAIN_CB.DeviceExtension
0x18000224c  jz      short loc_180002277
0x18000224e  cmp     rax, [rbx]
0x180002251  jz      short loc_180002273
0x180002253  mov     rcx, rax
0x180002256  call    cs:__imp_PsIsProtectedProcess
0x18000225d  nop     dword ptr [rax+rax+00h]
0x180002262  test    eax, eax
0x180002264  jz      short loc_180002273
0x180002266  mov     r14d, r15d
0x180002269  mov     [rbp+arg_0], 1
0x18000226d  and     r14d, 1
0x180002271  jmp     short loc_180002284
0x180002273  xor     edi, edi
0x180002275  jmp     short loc_180002224
0x180002277  mov     r14d, r15d
0x18000227a  and     r14d, 1
0x18000227e  jz      loc_1800023C2
0x180002284  xorps   xmm0, xmm0
0x180002287  mov     rcx, rsi
0x18000228a  movups  [rbp+MemoryInformation], xmm0
0x18000228e  movups  [rbp+var_28], xmm0
0x180002292  movups  [rbp+var_18], xmm0
0x180002296  call    cs:__imp_MmIsUserAddress
0x18000229d  nop     dword ptr [rax+rax+00h]
0x1800022a2  test    al, al
0x1800022a4  jnz     short loc_1800022E2
0x1800022a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022ad  lea     rax, WPP_GLOBAL_Control
0x1800022b4  cmp     rcx, rax
0x1800022b7  jz      loc_18000221F
0x1800022bd  mov     eax, [rcx+2Ch]
0x1800022c0  test    al, 1
0x1800022c2  jz      loc_18000221F
0x1800022c8  mov     rcx, [rcx+18h]
0x1800022cc  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x1800022d3  mov     edx, 1Ah
0x1800022d8  call    WPP_SF_
0x1800022dd  jmp     loc_18000221F
0x1800022e2  mov     [rsp+80h+ReturnLength], 0; ReturnLength
0x1800022eb  lea     r9, [rbp+MemoryInformation]; MemoryInformation
0x1800022ef  mov     r8d, 3; MemoryInformationClass
0x1800022f5  mov     [rsp+80h+MemoryInformationLength], 30h ; '0'; MemoryInformationLength
0x1800022fe  mov     rdx, rsi; BaseAddress
0x180002301  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180002305  call    cs:__imp_ZwQueryVirtualMemory
0x18000230c  nop     dword ptr [rax+rax+00h]
0x180002311  mov     edi, eax
0x180002313  test    eax, eax
0x180002315  jns     short loc_180002354
0x180002317  mov     rcx, cs:WPP_GLOBAL_Control
0x18000231e  lea     rax, WPP_GLOBAL_Control
0x180002325  cmp     rcx, rax
0x180002328  jz      loc_180002224
0x18000232e  mov     edx, [rcx+2Ch]
0x180002331  test    dl, 1
0x180002334  jz      loc_180002224
0x18000233a  mov     rcx, [rcx+18h]
0x18000233e  mov     edx, 1Bh
0x180002343  mov     r9, rsi
0x180002346  mov     dword ptr [rsp+80h+MemoryInformationLength], edi
0x18000234a  call    WPP_SF_qL
0x18000234f  jmp     loc_180002224
0x180002354  mov     r9d, dword ptr [rbp+MemoryInformation+0Ch]
0x180002358  cmp     r9d, 20000h
0x18000235f  jz      short loc_18000239A
0x180002361  mov     rcx, cs:WPP_GLOBAL_Control
0x180002368  lea     rax, WPP_GLOBAL_Control
0x18000236f  cmp     rcx, rax
0x180002372  jz      short loc_180002390
0x180002374  mov     eax, [rcx+2Ch]
0x180002377  test    al, 1
0x180002379  jz      short loc_180002390
0x18000237b  mov     rcx, [rcx+18h]
0x18000237f  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x180002386  mov     edx, 1Ch
0x18000238b  call    WPP_SF_D
0x180002390  mov     edi, 0C0000141h
0x180002395  jmp     loc_180002224
0x18000239a  test    r14d, r14d
0x18000239d  jz      short loc_1800023BE
0x18000239f  mov     r12, qword ptr [rbp+MemoryInformation]
0x1800023a3  mov     eax, 0FFFFFFFFh
0x1800023a8  sub     r12, rsi
0x1800023ab  add     r12, qword ptr [rbp+var_28]
0x1800023af  cmp     r12, rax
0x1800023b2  jbe     short loc_1800023BE
0x1800023b4  mov     edi, 0C0000095h
0x1800023b9  jmp     loc_180002224
0x1800023be  mov     dil, [rbp+arg_0]
0x1800023c2  mov     r13d, r12d
0x1800023c5  add     r13, rsi
0x1800023c8  cmp     r13, rsi
0x1800023cb  jnb     short loc_1800023D7
0x1800023cd  mov     edi, 0C000000Dh
0x1800023d2  jmp     loc_180002224
0x1800023d7  test    dil, dil
0x1800023da  jz      short loc_18000240C
0x1800023dc  call    cs:__imp_PsGetCurrentProcess
0x1800023e3  nop     dword ptr [rax+rax+00h]
0x1800023e8  mov     dword ptr [rsp+80h+ReturnLength], 1; unsigned int
0x1800023f0  mov     r9, rsi; unsigned __int8 *
0x1800023f3  mov     r8, rax; struct _EPROCESS *
0x1800023f6  mov     dword ptr [rsp+80h+MemoryInformationLength], r12d; unsigned int
0x1800023fb  xor     edx, edx; void *
0x1800023fd  mov     rcx, rbx; struct _KSECDDLSASTATE *
0x180002400  call    ?KsecInsertValidVm@@YAJPEAU_KSECDDLSASTATE@@PEAXPEAU_EPROCESS@@PEAEKK@Z; KsecInsertValidVm(_KSECDDLSASTATE *,void *,_EPROCESS *,uchar *,ulong,ulong)
0x180002405  mov     edi, eax
0x180002407  jmp     loc_180002224
0x18000240c  call    cs:__imp_KeEnterCriticalRegion
0x180002413  nop     dword ptr [rax+rax+00h]
0x180002418  lea     rdi, [rbx+238h]
0x18000241f  xor     edx, edx
0x180002421  mov     rcx, rdi
0x180002424  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x18000242b  nop     dword ptr [rax+rax+00h]
0x180002430  mov     r14d, [rbx+220h]
0x180002437  cmp     [rbx+224h], r14d
0x18000243e  jnz     short loc_1800024BF
0x180002440  add     r14d, 200h
0x180002447  cmp     r14d, 0AAAAAAAh
0x18000244e  jnb     loc_1800025BC
0x180002454  lea     rdx, [r14+r14*2]
0x180002458  mov     ecx, 100h
0x18000245d  shl     rdx, 3
0x180002461  mov     r8d, 6365734Bh
0x180002467  call    cs:__imp_ExAllocatePool2
0x18000246e  nop     dword ptr [rax+rax+00h]
0x180002473  mov     r12, rax
0x180002476  test    rax, rax
0x180002479  jz      loc_1800025BC
0x18000247f  mov     ecx, [rbx+224h]
0x180002485  mov     rdx, [rbx+218h]; Src
0x18000248c  lea     r8, [rcx+rcx*2]
0x180002490  mov     rcx, rax; void *
0x180002493  shl     r8, 3; Size
0x180002497  call    memmove
0x18000249c  mov     rcx, [rbx+218h]; P
0x1800024a3  xor     edx, edx; Tag
0x1800024a5  call    cs:__imp_ExFreePoolWithTag
0x1800024ac  nop     dword ptr [rax+rax+00h]
0x1800024b1  mov     [rbx+218h], r12
0x1800024b8  mov     [rbx+220h], r14d
0x1800024bf  mov     eax, [rbx+224h]
0x1800024c5  mov     edx, [rbp+arg_18]
0x1800024c8  shr     r15d, 1
0x1800024cb  and     r15d, 1
0x1800024cf  lea     rcx, [rax+rax*2]
0x1800024d3  mov     rax, [rbx+218h]
0x1800024da  mov     [rax+rcx*8], rsi
0x1800024de  mov     eax, [rbx+224h]
0x1800024e4  lea     rcx, [rax+rax*2]
0x1800024e8  mov     rax, [rbx+218h]
0x1800024ef  mov     [rax+rcx*8+8], r13
0x1800024f4  mov     eax, [rbx+224h]
0x1800024fa  lea     rcx, [rax+rax*2]
0x1800024fe  mov     rax, [rbx+218h]
0x180002505  mov     [rax+rcx*8+10h], r15d
0x18000250a  mov     eax, [rbx+224h]
0x180002510  lea     rcx, [rax+rax*2]
0x180002514  mov     rax, [rbx+218h]
0x18000251b  mov     [rax+rcx*8+14h], edx
0x18000251f  inc     dword ptr [rbx+224h]
0x180002525  mov     eax, [rbx+224h]
0x18000252b  cmp     eax, [rbx+228h]
0x180002531  jbe     short loc_180002539
0x180002533  mov     [rbx+228h], eax
0x180002539  mov     rcx, cs:WPP_GLOBAL_Control
0x180002540  lea     rax, WPP_GLOBAL_Control
0x180002547  cmp     rcx, rax
0x18000254a  jz      short loc_180002578
0x18000254c  mov     eax, [rcx+2Ch]
0x18000254f  test    al, 10h
0x180002551  jz      short loc_180002578
0x180002553  mov     eax, [rbx+224h]
0x180002559  mov     edx, 1Dh
0x18000255e  mov     rcx, [rcx+18h]
0x180002562  mov     r9, rsi
0x180002565  mov     [rsp+80h+var_50], eax
0x180002569  mov     dword ptr [rsp+80h+ReturnLength], r15d
0x18000256e  mov     [rsp+80h+MemoryInformationLength], r13
0x180002573  call    WPP_SF_qqLL
0x180002578  xor     edx, edx
0x18000257a  mov     rcx, rdi
0x18000257d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180002584  nop     dword ptr [rax+rax+00h]
0x180002589  call    cs:__imp_KeLeaveCriticalRegion
0x180002590  nop     dword ptr [rax+rax+00h]
0x180002595  lea     rcx, [rbp+var_40]; this
0x180002599  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000259e  xor     eax, eax
0x1800025a0  mov     rbx, [rsp+80h+arg_8]
0x1800025a8  add     rsp, 80h
0x1800025af  pop     r15
0x1800025b1  pop     r14
0x1800025b3  pop     r13
0x1800025b5  pop     r12
0x1800025b7  pop     rdi
0x1800025b8  pop     rsi
0x1800025b9  pop     rbp
0x1800025ba  retn
0x1800025bc  xor     edx, edx
0x1800025be  mov     rcx, rdi
0x1800025c1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800025c8  nop     dword ptr [rax+rax+00h]
0x1800025cd  call    cs:__imp_KeLeaveCriticalRegion
0x1800025d4  nop     dword ptr [rax+rax+00h]
0x1800025d9  mov     edi, 0C000009Ah
0x1800025de  jmp     loc_180002224
```
