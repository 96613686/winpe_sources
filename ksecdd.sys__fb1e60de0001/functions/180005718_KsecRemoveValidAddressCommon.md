# KsecRemoveValidAddressCommon

- ea: `0x180005718`
- end: `0x180005b51`
- name: `KsecRemoveValidAddressCommon`
- size: `1081`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004c74`
- `0x180007a0c`
- `0x18000ba98`
- `0x18000c93c`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180005718`
- `0x180005b58`
- `0x18000ded4`
- `0x18000e0b0`
- `0x180010a00`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800057f0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005914`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800057f0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180005914`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180005929`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180005929`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000589f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18000589f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800058ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005908`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800058ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005908`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180005810`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180005810`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800058fc`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180005b16`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1800058fc`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180005b16`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x1800058df`
- `ntoskrnl!ExTryConvertPushLockSharedToExclusiveEx` at `0x1800058df`
- `ntoskrnl!PsGetCurrentProcess` at `0x180005772`
- `ntoskrnl!PsGetCurrentProcess` at `0x180005772`
- `ntoskrnl!PsIsProtectedProcess` at `0x180005792`
- `ntoskrnl!PsIsProtectedProcess` at `0x180005792`
- `ntoskrnl!MmUserProbeAddress` at `0x18000575c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180005aee`
- `ntoskrnl!ExFreePoolWithTag` at `0x180005aee`
- `ntoskrnl!ExAllocatePool2` at `0x180005ab0`
- `ntoskrnl!ExAllocatePool2` at `0x180005ab0`
- `ntoskrnl!ZwClose` at `0x1800057b5`
- `ntoskrnl!ZwClose` at `0x1800057b5`

## pseudocode

```c
_BOOL8 __fastcall KsecRemoveValidAddressCommon(unsigned __int8 *a1, unsigned int a2)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rbx
  struct _EPROCESS *CurrentProcess; // rax
  struct _EPROCESS *v11; // rdi
  void *v12; // rax
  BOOL v13; // edi
  unsigned int i; // r12d
  unsigned int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // r15
  __int64 v18; // r14
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int v21; // r15d
  __int64 v22; // rax
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // xmm1_8
  unsigned int v27; // ecx
  __int64 v28; // rbp
  void *Pool2; // rsi
  int v30; // [rsp+80h] [rbp+8h]
  __int64 v31; // [rsp+90h] [rbp+18h]
  __int64 v32; // [rsp+98h] [rbp+20h] BYREF

  if ( !a1 )
    return 1;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v32);
  v9 = v32;
  if ( !v32 )
    goto LABEL_56;
  if ( (unsigned __int64)a1 <= MmUserProbeAddress )
  {
    if ( (a2 & 0x20) != 0 )
    {
      CurrentProcess = (struct _EPROCESS *)PsGetCurrentProcess(v6, v5, v7, v8);
      v11 = CurrentProcess;
      if ( CurrentProcess != WPP_MAIN_CB.DeviceExtension )
      {
        if ( CurrentProcess != *(struct _EPROCESS **)v9 && (unsigned int)PsIsProtectedProcess(CurrentProcess) )
        {
          v12 = (void *)KsecRemoveValidVm(v11, a1);
          if ( v12 )
            ZwClose(v12);
        }
        v13 = 1;
        goto LABEL_57;
      }
      goto LABEL_12;
    }
LABEL_56:
    v13 = 0;
    goto LABEL_57;
  }
LABEL_12:
  if ( !*(_DWORD *)(v9 + 548) )
  {
    v13 = ((a2 >> 3) & 1) == 0;
    goto LABEL_57;
  }
  v30 = 0;
  KeEnterCriticalRegion();
  v31 = v9 + 568;
  ExAcquirePushLockSharedEx(v9 + 568, 0);
  v13 = 1;
  for ( i = 1; i <= 2; ++i )
  {
    v15 = *(_DWORD *)(v9 + 548);
    if ( !v15 )
    {
LABEL_19:
      if ( (a2 & 8) == 0 )
      {
LABEL_25:
        v21 = v30;
        goto LABEL_26;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      {
LABEL_24:
        v13 = 0;
        goto LABEL_25;
      }
      v20 = 30;
LABEL_23:
      WPP_SF_q(v19[3], v20, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids, a1);
      goto LABEL_24;
    }
    v16 = *(_QWORD *)(v9 + 536);
    v17 = 0;
    while ( 1 )
    {
      v18 = 3 * v17;
      if ( a1 == *(unsigned __int8 **)(v16 + 24 * v17) )
        break;
      v17 = (unsigned int)(v17 + 1);
      if ( (unsigned int)v17 >= v15 )
        goto LABEL_19;
    }
    if ( (a2 & 0x10) != 0 && *(_DWORD *)(v16 + 24 * v17 + 16) )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
        goto LABEL_24;
      v20 = 31;
      goto LABEL_23;
    }
    if ( i == 1 )
    {
      if ( (unsigned __int8)ExTryConvertPushLockSharedToExclusiveEx(v9 + 568, 0) )
        goto LABEL_46;
      ExReleasePushLockSharedEx(v9 + 568, 0);
      KeLeaveCriticalRegion();
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v9 + 568, 0);
      v30 = 1;
      if ( (unsigned int)v17 < *(_DWORD *)(v9 + 548) )
      {
        v22 = *(_QWORD *)(v9 + 536);
        if ( a1 == *(unsigned __int8 **)(v22 + 24 * v17) )
        {
          if ( (a2 & 0x10) != 0 && *(_DWORD *)(v22 + 24 * v17 + 16) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            {
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 32, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids, a1);
            }
            v13 = 0;
            goto LABEL_27;
          }
LABEL_46:
          v21 = 1;
          goto LABEL_47;
        }
      }
    }
  }
  v21 = v30;
LABEL_47:
  ++*(_DWORD *)(v9 + 556);
  v23 = *(_DWORD *)(v9 + 548);
  if ( v23 > 1 )
  {
    v24 = *(_QWORD *)(v9 + 536);
    v25 = 3LL * (v23 - 1);
    v26 = *(_QWORD *)(v24 + 8 * v25 + 16);
    *(_OWORD *)(v24 + 8 * v18) = *(_OWORD *)(v24 + 8 * v25);
    *(_QWORD *)(v24 + 8 * v18 + 16) = v26;
  }
  --*(_DWORD *)(v9 + 548);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0 )
    WPP_SF_qqLL(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      33,
      *(unsigned int *)(v9 + 548),
      *(_QWORD *)(*(_QWORD *)(v9 + 536) + 8 * v18),
      *(_QWORD *)(*(_QWORD *)(v9 + 536) + 8 * v18 + 8),
      *(_DWORD *)(*(_QWORD *)(v9 + 536) + 8 * v18 + 16),
      *(_DWORD *)(v9 + 548));
  v27 = *(_DWORD *)(v9 + 544);
  if ( *(_DWORD *)(v9 + 548) + 1024 < v27 )
  {
    v28 = v27 - 512;
    Pool2 = (void *)ExAllocatePool2(256, 24 * v28, 1667593035);
    if ( Pool2 )
    {
      memmove(Pool2, *(const void **)(v9 + 536), 24LL * *(unsigned int *)(v9 + 548));
      ExFreePoolWithTag(*(PVOID *)(v9 + 536), 0);
      *(_QWORD *)(v9 + 536) = Pool2;
      *(_DWORD *)(v9 + 544) = v28;
    }
  }
LABEL_26:
  if ( v21 )
  {
LABEL_27:
    ExReleasePushLockExclusiveEx(v31, 0);
    goto LABEL_28;
  }
  ExReleasePushLockSharedEx(v31, 0);
LABEL_28:
  KeLeaveCriticalRegion();
LABEL_57:
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v32);
  return v13;
}

```

## disassembly

```asm
0x180005718  mov     [rsp+arg_8], rbx
0x18000571d  push    rbp
0x18000571e  push    rsi
0x18000571f  push    rdi
0x180005720  push    r12
0x180005722  push    r13
0x180005724  push    r14
0x180005726  push    r15
0x180005728  sub     rsp, 40h
0x18000572c  mov     esi, edx
0x18000572e  mov     rbp, rcx
0x180005731  test    rcx, rcx
0x180005734  jnz     short loc_18000573E
0x180005736  lea     eax, [rcx+1]
0x180005739  jmp     loc_180005B38
0x18000573e  lea     rcx, [rsp+78h+arg_18]; this
0x180005746  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x18000574b  mov     rbx, [rsp+78h+arg_18]
0x180005753  test    rbx, rbx
0x180005756  jz      loc_180005B27
0x18000575c  mov     rax, cs:MmUserProbeAddress
0x180005763  cmp     rbp, [rax]
0x180005766  ja      short loc_1800057CB
0x180005768  test    sil, 20h
0x18000576c  jz      loc_180005B27
0x180005772  call    cs:__imp_PsGetCurrentProcess
0x180005779  nop     dword ptr [rax+rax+00h]
0x18000577e  cmp     rax, cs:WPP_MAIN_CB.DeviceExtension
0x180005785  mov     rdi, rax
0x180005788  jz      short loc_1800057CB
0x18000578a  cmp     rax, [rbx]
0x18000578d  jz      short loc_1800057C1
0x18000578f  mov     rcx, rax
0x180005792  call    cs:__imp_PsIsProtectedProcess
0x180005799  nop     dword ptr [rax+rax+00h]
0x18000579e  test    eax, eax
0x1800057a0  jz      short loc_1800057C1
0x1800057a2  mov     rdx, rbp; unsigned __int8 *
0x1800057a5  mov     rcx, rdi; struct _EPROCESS *
0x1800057a8  call    KsecRemoveValidVm
0x1800057ad  test    rax, rax
0x1800057b0  jz      short loc_1800057C1
0x1800057b2  mov     rcx, rax; Handle
0x1800057b5  call    cs:__imp_ZwClose
0x1800057bc  nop     dword ptr [rax+rax+00h]
0x1800057c1  mov     edi, 1
0x1800057c6  jmp     loc_180005B29
0x1800057cb  cmp     dword ptr [rbx+224h], 0
0x1800057d2  jnz     short loc_1800057E5
0x1800057d4  shr     esi, 3
0x1800057d7  mov     edi, 1
0x1800057dc  not     esi
0x1800057de  and     edi, esi
0x1800057e0  jmp     loc_180005B29
0x1800057e5  xor     r15d, r15d
0x1800057e8  mov     [rsp+78h+arg_0], r15d
0x1800057f0  call    cs:__imp_KeEnterCriticalRegion
0x1800057f7  nop     dword ptr [rax+rax+00h]
0x1800057fc  lea     r13, [rbx+238h]
0x180005803  xor     edx, edx
0x180005805  mov     rcx, r13
0x180005808  mov     [rsp+78h+arg_10], r13
0x180005810  call    cs:__imp_ExAcquirePushLockSharedEx
0x180005817  nop     dword ptr [rax+rax+00h]
0x18000581c  lea     edi, [r15+1]
0x180005820  mov     r12d, edi
0x180005823  mov     ecx, [rbx+224h]
0x180005829  test    ecx, ecx
0x18000582b  jz      short loc_180005849
0x18000582d  mov     rdx, [rbx+218h]
0x180005834  xor     r15d, r15d
0x180005837  lea     r14, [r15+r15*2]
0x18000583b  cmp     rbp, [rdx+r14*8]
0x18000583f  jz      short loc_1800058BC
0x180005841  add     r15d, edi
0x180005844  cmp     r15d, ecx
0x180005847  jb      short loc_180005837
0x180005849  test    sil, 8
0x18000584d  jz      short loc_180005884
0x18000584f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005856  lea     rax, WPP_GLOBAL_Control
0x18000585d  cmp     rcx, rax
0x180005860  jz      short loc_180005882
0x180005862  mov     eax, [rcx+2Ch]
0x180005865  test    dil, al
0x180005868  jz      short loc_180005882
0x18000586a  mov     edx, 1Eh
0x18000586f  mov     rcx, [rcx+18h]
0x180005873  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000587a  mov     r9, rbp
0x18000587d  call    WPP_SF_q
0x180005882  xor     edi, edi
0x180005884  mov     r15d, [rsp+78h+arg_0]
0x18000588c  test    r15d, r15d
0x18000588f  jz      loc_180005B0C
0x180005895  mov     rcx, [rsp+78h+arg_10]
0x18000589d  xor     edx, edx
0x18000589f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800058a6  nop     dword ptr [rax+rax+00h]
0x1800058ab  call    cs:__imp_KeLeaveCriticalRegion
0x1800058b2  nop     dword ptr [rax+rax+00h]
0x1800058b7  jmp     loc_180005B29
0x1800058bc  mov     r13d, esi
0x1800058bf  and     r13d, 10h
0x1800058c3  jz      short loc_1800058D1
0x1800058c5  cmp     dword ptr [rdx+r14*8+10h], 0
0x1800058cb  jnz     loc_180005969
0x1800058d1  cmp     r12d, edi
0x1800058d4  jnz     short loc_180005952
0x1800058d6  xor     edx, edx
0x1800058d8  lea     rcx, [rbx+238h]
0x1800058df  call    cs:__imp_ExTryConvertPushLockSharedToExclusiveEx
0x1800058e6  nop     dword ptr [rax+rax+00h]
0x1800058eb  test    al, al
0x1800058ed  jnz     loc_1800059DD
0x1800058f3  xor     edx, edx
0x1800058f5  lea     rcx, [rbx+238h]
0x1800058fc  call    cs:__imp_ExReleasePushLockSharedEx
0x180005903  nop     dword ptr [rax+rax+00h]
0x180005908  call    cs:__imp_KeLeaveCriticalRegion
0x18000590f  nop     dword ptr [rax+rax+00h]
0x180005914  call    cs:__imp_KeEnterCriticalRegion
0x18000591b  nop     dword ptr [rax+rax+00h]
0x180005920  xor     edx, edx
0x180005922  lea     rcx, [rbx+238h]
0x180005929  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x180005930  nop     dword ptr [rax+rax+00h]
0x180005935  mov     [rsp+78h+arg_0], edi
0x18000593c  cmp     r15d, [rbx+224h]
0x180005943  jnb     short loc_180005952
0x180005945  mov     rax, [rbx+218h]
0x18000594c  cmp     rbp, [rax+r14*8]
0x180005950  jz      short loc_180005996
0x180005952  add     r12d, edi
0x180005955  cmp     r12d, 2
0x180005959  jbe     loc_180005823
0x18000595f  mov     r15d, [rsp+78h+arg_0]
0x180005967  jmp     short loc_1800059E0
0x180005969  mov     rcx, cs:WPP_GLOBAL_Control
0x180005970  lea     rax, WPP_GLOBAL_Control
0x180005977  cmp     rcx, rax
0x18000597a  jz      loc_180005882
0x180005980  mov     eax, [rcx+2Ch]
0x180005983  test    dil, al
0x180005986  jz      loc_180005882
0x18000598c  mov     edx, 1Fh
0x180005991  jmp     loc_18000586F
0x180005996  test    r13d, r13d
0x180005999  jz      short loc_1800059DD
0x18000599b  cmp     dword ptr [rax+r14*8+10h], 0
0x1800059a1  jz      short loc_1800059DD
0x1800059a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059aa  lea     rax, WPP_GLOBAL_Control
0x1800059b1  cmp     rcx, rax
0x1800059b4  jz      short loc_1800059D6
0x1800059b6  mov     eax, [rcx+2Ch]
0x1800059b9  test    dil, al
0x1800059bc  jz      short loc_1800059D6
0x1800059be  mov     rcx, [rcx+18h]
0x1800059c2  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x1800059c9  mov     edx, 20h ; ' '
0x1800059ce  mov     r9, rbp
0x1800059d1  call    WPP_SF_q
0x1800059d6  xor     edi, edi
0x1800059d8  jmp     loc_180005895
0x1800059dd  mov     r15d, edi
0x1800059e0  add     [rbx+22Ch], edi
0x1800059e6  cmp     r12d, 2
0x1800059ea  jnz     short loc_1800059F2
0x1800059ec  add     [rbx+230h], edi
0x1800059f2  mov     eax, [rbx+224h]
0x1800059f8  cmp     eax, edi
0x1800059fa  jbe     short loc_180005A1F
0x1800059fc  mov     rdx, [rbx+218h]
0x180005a03  dec     eax
0x180005a05  lea     rax, [rax+rax*2]
0x180005a09  movups  xmm0, xmmword ptr [rdx+rax*8]
0x180005a0d  movsd   xmm1, qword ptr [rdx+rax*8+10h]
0x180005a13  movups  xmmword ptr [rdx+r14*8], xmm0
0x180005a18  movsd   qword ptr [rdx+r14*8+10h], xmm1
0x180005a1f  dec     dword ptr [rbx+224h]
0x180005a25  mov     r8d, [rbx+224h]
0x180005a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a33  lea     rax, WPP_GLOBAL_Control
0x180005a3a  cmp     rcx, rax
0x180005a3d  jz      short loc_180005A77
0x180005a3f  mov     eax, [rcx+2Ch]
0x180005a42  test    al, 10h
0x180005a44  jz      short loc_180005A77
0x180005a46  mov     r9, [rbx+218h]
0x180005a4d  mov     edx, 21h ; '!'
0x180005a52  mov     rcx, [rcx+18h]
0x180005a56  mov     [rsp+78h+var_48], r8d
0x180005a5b  mov     eax, [r9+r14*8+10h]
0x180005a60  mov     [rsp+78h+var_50], eax
0x180005a64  mov     rax, [r9+r14*8+8]
0x180005a69  mov     r9, [r9+r14*8]
0x180005a6d  mov     [rsp+78h+var_58], rax
0x180005a72  call    WPP_SF_qqLL
0x180005a77  mov     eax, [rbx+224h]
0x180005a7d  mov     ecx, [rbx+220h]
0x180005a83  add     eax, 400h
0x180005a88  cmp     eax, ecx
0x180005a8a  jnb     loc_18000588C
0x180005a90  lea     ebp, [rcx-200h]
0x180005a96  mov     r8d, 6365734Bh
0x180005a9c  lea     rdx, ds:0[rbp*2]
0x180005aa4  mov     ecx, 100h
0x180005aa9  add     rdx, rbp
0x180005aac  shl     rdx, 3
0x180005ab0  call    cs:__imp_ExAllocatePool2
0x180005ab7  nop     dword ptr [rax+rax+00h]
0x180005abc  mov     rsi, rax
0x180005abf  test    rax, rax
0x180005ac2  jz      loc_18000588C
0x180005ac8  mov     eax, [rbx+224h]
0x180005ace  mov     rcx, rsi; void *
0x180005ad1  mov     rdx, [rbx+218h]; Src
0x180005ad8  lea     r8, [rax+rax*2]
0x180005adc  shl     r8, 3; Size
0x180005ae0  call    memmove
0x180005ae5  mov     rcx, [rbx+218h]; P
0x180005aec  xor     edx, edx; Tag
0x180005aee  call    cs:__imp_ExFreePoolWithTag
0x180005af5  nop     dword ptr [rax+rax+00h]
0x180005afa  mov     [rbx+218h], rsi
0x180005b01  mov     [rbx+220h], ebp
0x180005b07  jmp     loc_18000588C
0x180005b0c  mov     rcx, [rsp+78h+arg_10]
0x180005b14  xor     edx, edx
0x180005b16  call    cs:__imp_ExReleasePushLockSharedEx
0x180005b1d  nop     dword ptr [rax+rax+00h]
0x180005b22  jmp     loc_1800058AB
0x180005b27  xor     edi, edi
0x180005b29  lea     rcx, [rsp+78h+arg_18]; this
0x180005b31  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180005b36  mov     eax, edi
0x180005b38  mov     rbx, [rsp+78h+arg_8]
0x180005b40  add     rsp, 40h
0x180005b44  pop     r15
0x180005b46  pop     r14
0x180005b48  pop     r13
0x180005b4a  pop     r12
0x180005b4c  pop     rdi
0x180005b4d  pop     rsi
0x180005b4e  pop     rbp
0x180005b4f  retn
```
