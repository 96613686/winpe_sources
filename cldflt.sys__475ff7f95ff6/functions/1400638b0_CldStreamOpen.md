# CldStreamOpen

- ea: `0x1400638b0`
- end: `0x140063d83`
- name: `CldStreamOpen`
- size: `1235`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x14003fcb0`
- `0x140040090`
- `0x140063200`
- `0x140082ba0`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000d868`
- `0x140010c34`
- `0x14001123c`
- `0x14001e600`
- `0x1400638b0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140063ad8`
- `ntoskrnl!KeInitializeEvent` at `0x140063ad8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140063a72`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140063a72`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140063bf0`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140063bf0`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140063b36`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140063b36`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140063a28`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140063a28`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140063c0c`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140063c0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063b99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063b99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063d38`
- `ntoskrnl!ExAllocatePool2` at `0x14006393d`
- `ntoskrnl!ExAllocatePool2` at `0x140063ab6`
- `ntoskrnl!ExAllocatePool2` at `0x14006393d`
- `ntoskrnl!ExAllocatePool2` at `0x140063ab6`
- `FLTMGR!FltReleasePushLockEx` at `0x1400638f3`
- `FLTMGR!FltReleasePushLockEx` at `0x140063a93`
- `FLTMGR!FltReleasePushLockEx` at `0x140063bbb`
- `FLTMGR!FltReleasePushLockEx` at `0x140063c1d`
- `FLTMGR!FltReleasePushLockEx` at `0x1400638f3`
- `FLTMGR!FltReleasePushLockEx` at `0x140063a93`
- `FLTMGR!FltReleasePushLockEx` at `0x140063bbb`
- `FLTMGR!FltReleasePushLockEx` at `0x140063c1d`
- `FLTMGR!FltInitializePushLock` at `0x140063977`
- `FLTMGR!FltInitializePushLock` at `0x1400639a2`
- `FLTMGR!FltInitializePushLock` at `0x140063a82`
- `FLTMGR!FltInitializePushLock` at `0x140063977`
- `FLTMGR!FltInitializePushLock` at `0x1400639a2`
- `FLTMGR!FltInitializePushLock` at `0x140063a82`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400638d7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400639fa`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400638d7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400639fa`

## pseudocode

```c
__int64 __fastcall CldStreamOpen(_QWORD *a1)
{
  __int64 v2; // rsi
  __int64 v3; // r15
  unsigned int v4; // r14d
  unsigned __int64 *Pool2; // rax
  unsigned __int64 *v7; // r12
  unsigned __int64 *v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // r13
  char *inserted; // rax
  char *v13; // rdi
  BASE_MCB *v14; // rsi
  struct _KEVENT *v15; // rax
  __int64 v16; // r8
  void *v17; // rcx
  unsigned int v18; // edi
  _QWORD Buffer[12]; // [rsp+30h] [rbp-98h] BYREF
  unsigned __int8 NewElement; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+10h] BYREF
  PRTL_AVL_TABLE Table; // [rsp+E0h] [rbp+18h]

  v2 = a1[2];
  v3 = *(_QWORD *)(*(_QWORD *)(*a1 + 16LL) + 32LL);
  FltAcquirePushLockExclusiveEx(a1 + 3, 0);
  if ( a1[4] )
  {
    v4 = 0;
    goto LABEL_3;
  }
  if ( *(_QWORD *)(v2 + 32) )
  {
    Pool2 = (unsigned __int64 *)ExAllocatePool2(256, 120, 1953721411);
    v7 = Pool2;
    if ( Pool2 )
    {
      *Pool2 = (unsigned __int64)a1;
      v8 = Pool2 + 4;
      v4 = 0;
      Pool2[1] = 0;
      v9 = Pool2 + 2;
      v9[1] = v9;
      *v9 = v9;
      FltInitializePushLock(v8);
      if ( (*(_DWORD *)(*(_QWORD *)*v7 + 28LL) & 2) == 0 )
      {
        v7[10] = (unsigned __int64)(v7 + 9);
        v7[9] = (unsigned __int64)(v7 + 9);
        FltInitializePushLock(v7 + 11);
        v7[13] = (unsigned __int64)(v7 + 12);
        v7[12] = (unsigned __int64)(v7 + 12);
      }
      v10 = *(_QWORD *)(v2 + 32);
      v21 = *(_QWORD *)(*a1 + 40LL);
      memset(&Buffer[2], 0, 0x48u);
      v11 = v10 + 104;
      NewElement = 0;
      Buffer[0] = v21;
      Buffer[1] = v7;
      FltAcquirePushLockExclusiveEx(v10 + 104, 0);
      Table = (PRTL_AVL_TABLE)(v10 + 112);
      inserted = (char *)RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(v10 + 112), Buffer, 0x58u, &NewElement);
      v13 = inserted;
      if ( inserted )
      {
        v14 = (BASE_MCB *)(inserted + 32);
        if ( NewElement )
        {
          v14->MaximumPairCount = 0;
          if ( (*(_DWORD *)(*(_QWORD *)*v7 + 28LL) & 2) != 0 )
          {
            *(_OWORD *)(inserted + 40) = 0;
LABEL_12:
            ExInitializeRundownProtection((PEX_RUNDOWN_REF)v13 + 2);
            FltInitializePushLock((PULONG_PTR)v13 + 3);
            FltReleasePushLockEx(v11, 0);
            HsmDbgBreakOnStatus(0);
            v15 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1752331075);
            v7[8] = (unsigned __int64)v15;
            if ( v15 )
            {
              KeInitializeEvent(v15, NotificationEvent, 1u);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_qqq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  35,
                  WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids,
                  v7,
                  *(_QWORD *)(*(_QWORD *)*v7 + 40LL),
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)*v7 + 16LL) + 32LL));
              }
              a1[4] = v7;
              goto LABEL_3;
            }
            v4 = -1073741670;
            HsmDbgBreakOnStatus(3221225626LL);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qqi(WPP_GLOBAL_Control->AttachedDevice, 34, v16, v7, a1, v3);
            }
            goto LABEL_22;
          }
          if ( FsRtlInitializeBaseMcbEx(v14, PagedPool, 0) )
          {
            *(_OWORD *)(v13 + 56) = 0;
            *(_OWORD *)(v13 + 72) = 0;
            goto LABEL_12;
          }
          v18 = -1073741670;
        }
        else
        {
          v18 = -1073741595;
        }
        HsmDbgBreakOnStatus(v18);
        if ( (*(_DWORD *)(*(_QWORD *)*v7 + 28LL) & 2) == 0 )
          FsRtlUninitializeBaseMcb(v14);
        RtlDeleteElementGenericTableAvl(Table, &v21);
        FltReleasePushLockEx(v11, 0);
        v4 = v18;
        HsmDbgBreakOnStatus(v18);
      }
      else
      {
        HsmDbgBreakOnStatus(3221225626LL);
        FltReleasePushLockEx(v10 + 104, 0);
        HsmDbgBreakOnStatus(3221225626LL);
        v4 = -1073741670;
      }
LABEL_22:
      v17 = (void *)v7[8];
      if ( v17 )
        ExFreePoolWithTag(v17, 0x68727343u);
      ExFreePoolWithTag(v7, 0x74736C43u);
      goto LABEL_3;
    }
    v4 = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qi(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids, a1, v3);
    }
  }
  else
  {
    v4 = -1073688831;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids,
        a1,
        v3,
        -1073688831);
    }
  }
LABEL_3:
  FltReleasePushLockEx(a1 + 3, 0);
  return v4;
}

```

## disassembly

```asm
0x1400638b0  push    rbx
0x1400638b2  push    rbp
0x1400638b3  push    rsi
0x1400638b4  push    r14
0x1400638b6  push    r15
0x1400638b8  sub     rsp, 0A0h
0x1400638bf  mov     rax, [rcx]
0x1400638c2  mov     rbx, rcx
0x1400638c5  mov     rsi, [rcx+10h]
0x1400638c9  xor     edx, edx
0x1400638cb  mov     rcx, [rax+10h]
0x1400638cf  mov     r15, [rcx+20h]
0x1400638d3  lea     rcx, [rbx+18h]
0x1400638d7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400638de  nop     dword ptr [rax+rax+00h]
0x1400638e3  cmp     qword ptr [rbx+20h], 0
0x1400638e8  jz      short loc_140063912
0x1400638ea  xor     r14d, r14d
0x1400638ed  xor     edx, edx
0x1400638ef  lea     rcx, [rbx+18h]
0x1400638f3  call    cs:__imp_FltReleasePushLockEx
0x1400638fa  nop     dword ptr [rax+rax+00h]
0x1400638ff  mov     eax, r14d
0x140063902  add     rsp, 0A0h
0x140063909  pop     r15
0x14006390b  pop     r14
0x14006390d  pop     rsi
0x14006390e  pop     rbp
0x14006390f  pop     rbx
0x140063910  retn
0x140063912  cmp     qword ptr [rsi+20h], 0
0x140063917  jz      loc_140063C38
0x14006391d  mov     [rsp+0C8h+arg_18], rdi
0x140063925  mov     edx, 78h ; 'x'
0x14006392a  mov     ecx, 100h
0x14006392f  mov     [rsp+0C8h+var_30], r12
0x140063937  mov     r8d, 74736C43h
0x14006393d  call    cs:__imp_ExAllocatePool2
0x140063944  nop     dword ptr [rax+rax+00h]
0x140063949  mov     r12, rax
0x14006394c  test    rax, rax
0x14006394f  jz      loc_140063C93
0x140063955  mov     [rax], rbx
0x140063958  lea     rcx, [r12+20h]; PushLock
0x14006395d  xor     r14d, r14d
0x140063960  mov     [rsp+0C8h+var_38], r13
0x140063968  mov     [rax+8], r14
0x14006396c  add     rax, 10h
0x140063970  mov     [rax+8], rax
0x140063974  mov     [rax], rax
0x140063977  call    cs:__imp_FltInitializePushLock
0x14006397e  nop     dword ptr [rax+rax+00h]
0x140063983  mov     rax, [r12]
0x140063987  mov     rcx, [rax]
0x14006398a  mov     eax, [rcx+1Ch]
0x14006398d  test    al, 2
0x14006398f  jnz     short loc_1400639BA
0x140063991  lea     rax, [r12+48h]
0x140063996  lea     rcx, [r12+58h]; PushLock
0x14006399b  mov     [rax+8], rax
0x14006399f  mov     [rax], rax
0x1400639a2  call    cs:__imp_FltInitializePushLock
0x1400639a9  nop     dword ptr [rax+rax+00h]
0x1400639ae  lea     rax, [r12+60h]
0x1400639b3  mov     [rax+8], rax
0x1400639b7  mov     [rax], rax
0x1400639ba  mov     rax, [rbx]
0x1400639bd  lea     rcx, [rsp+0C8h+var_88]; void *
0x1400639c2  mov     rsi, [rsi+20h]
0x1400639c6  xor     edx, edx; Val
0x1400639c8  mov     r8d, 48h ; 'H'; Size
0x1400639ce  mov     rdi, [rax+28h]
0x1400639d2  mov     [rsp+0C8h+arg_8], rdi
0x1400639da  call    memset
0x1400639df  lea     r13, [rsi+68h]
0x1400639e3  mov     [rsp+0C8h+NewElement], r14b
0x1400639eb  mov     rcx, r13
0x1400639ee  mov     [rsp+0C8h+Buffer], rdi
0x1400639f3  xor     edx, edx
0x1400639f5  mov     [rsp+0C8h+var_90], r12
0x1400639fa  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140063a01  nop     dword ptr [rax+rax+00h]
0x140063a06  lea     rax, [rsi+70h]
0x140063a0a  mov     r8d, 58h ; 'X'; BufferSize
0x140063a10  mov     rcx, rax; Table
0x140063a13  mov     [rsp+0C8h+Table], rax
0x140063a1b  lea     r9, [rsp+0C8h+NewElement]; NewElement
0x140063a23  lea     rdx, [rsp+0C8h+Buffer]; Buffer
0x140063a28  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140063a2f  nop     dword ptr [rax+rax+00h]
0x140063a34  mov     rdi, rax
0x140063a37  test    rax, rax
0x140063a3a  jz      loc_140063BAA
0x140063a40  lea     rsi, [rax+20h]
0x140063a44  cmp     [rsp+0C8h+NewElement], r14b
0x140063a4c  jz      loc_140063CF2
0x140063a52  mov     [rsi], r14d
0x140063a55  mov     rax, [r12]
0x140063a59  mov     rcx, [rax]
0x140063a5c  mov     eax, [rcx+1Ch]
0x140063a5f  test    al, 2
0x140063a61  jz      loc_140063B2B
0x140063a67  xorps   xmm0, xmm0
0x140063a6a  movups  xmmword ptr [rdi+28h], xmm0
0x140063a6e  lea     rcx, [rdi+10h]; RunRef
0x140063a72  call    cs:__imp_ExInitializeRundownProtection
0x140063a79  nop     dword ptr [rax+rax+00h]
0x140063a7e  lea     rcx, [rdi+18h]; PushLock
0x140063a82  call    cs:__imp_FltInitializePushLock
0x140063a89  nop     dword ptr [rax+rax+00h]
0x140063a8e  xor     edx, edx
0x140063a90  mov     rcx, r13
0x140063a93  call    cs:__imp_FltReleasePushLockEx
0x140063a9a  nop     dword ptr [rax+rax+00h]
0x140063a9f  xor     ecx, ecx
0x140063aa1  call    HsmDbgBreakOnStatus
0x140063aa6  mov     edx, 18h
0x140063aab  mov     ecx, 40h ; '@'
0x140063ab0  mov     r8d, 68727343h
0x140063ab6  call    cs:__imp_ExAllocatePool2
0x140063abd  nop     dword ptr [rax+rax+00h]
0x140063ac2  mov     [r12+40h], rax
0x140063ac7  test    rax, rax
0x140063aca  jz      loc_140063B5D
0x140063ad0  mov     r8b, 1; State
0x140063ad3  xor     edx, edx; Type
0x140063ad5  mov     rcx, rax; Event
0x140063ad8  call    cs:__imp_KeInitializeEvent
0x140063adf  nop     dword ptr [rax+rax+00h]
0x140063ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x140063aeb  lea     rax, WPP_GLOBAL_Control
0x140063af2  cmp     rcx, rax
0x140063af5  jz      short loc_140063B0A
0x140063af7  test    dword ptr [rcx+2Ch], 100h
0x140063afe  jz      short loc_140063B0A
0x140063b00  cmp     byte ptr [rcx+29h], 5
0x140063b04  jnb     loc_140063D49
0x140063b0a  mov     [rbx+20h], r12
0x140063b0e  mov     r13, [rsp+0C8h+var_38]
0x140063b16  mov     rdi, [rsp+0C8h+arg_18]
0x140063b1e  mov     r12, [rsp+0C8h+var_30]
0x140063b26  jmp     loc_1400638ED
0x140063b2b  xor     r8d, r8d; Flags
0x140063b2e  mov     edx, 1; PoolType
0x140063b33  mov     rcx, rsi; Mcb
0x140063b36  call    cs:__imp_FsRtlInitializeBaseMcbEx
0x140063b3d  nop     dword ptr [rax+rax+00h]
0x140063b42  test    al, al
0x140063b44  jz      loc_140063BD3
0x140063b4a  xorps   xmm0, xmm0
0x140063b4d  xorps   xmm1, xmm1
0x140063b50  movups  xmmword ptr [rdi+38h], xmm0
0x140063b54  movups  xmmword ptr [rdi+48h], xmm1
0x140063b58  jmp     loc_140063A6E
0x140063b5d  mov     edi, 0C000009Ah
0x140063b62  mov     ecx, edi
0x140063b64  mov     r14d, edi
0x140063b67  call    HsmDbgBreakOnStatus
0x140063b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140063b73  lea     rax, WPP_GLOBAL_Control
0x140063b7a  cmp     rcx, rax
0x140063b7d  jnz     loc_140063CFC
0x140063b83  mov     rcx, [r12+40h]; P
0x140063b88  test    rcx, rcx
0x140063b8b  jnz     loc_140063D33
0x140063b91  mov     edx, 74736C43h; Tag
0x140063b96  mov     rcx, r12; P
0x140063b99  call    cs:__imp_ExFreePoolWithTag
0x140063ba0  nop     dword ptr [rax+rax+00h]
0x140063ba5  jmp     loc_140063B0E
0x140063baa  mov     edi, 0C000009Ah
0x140063baf  mov     ecx, edi
0x140063bb1  call    HsmDbgBreakOnStatus
0x140063bb6  xor     edx, edx
0x140063bb8  mov     rcx, r13
0x140063bbb  call    cs:__imp_FltReleasePushLockEx
0x140063bc2  nop     dword ptr [rax+rax+00h]
0x140063bc7  mov     ecx, edi
0x140063bc9  call    HsmDbgBreakOnStatus
0x140063bce  mov     r14d, edi
0x140063bd1  jmp     short loc_140063B83
0x140063bd3  mov     edi, 0C000009Ah
0x140063bd8  mov     ecx, edi
0x140063bda  call    HsmDbgBreakOnStatus
0x140063bdf  mov     rax, [r12]
0x140063be3  mov     rdx, [rax]
0x140063be6  mov     eax, [rdx+1Ch]
0x140063be9  test    al, 2
0x140063beb  jnz     short loc_140063BFC
0x140063bed  mov     rcx, rsi; Mcb
0x140063bf0  call    cs:__imp_FsRtlUninitializeBaseMcb
0x140063bf7  nop     dword ptr [rax+rax+00h]
0x140063bfc  mov     rcx, [rsp+0C8h+Table]; Table
0x140063c04  lea     rdx, [rsp+0C8h+arg_8]; Buffer
0x140063c0c  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140063c13  nop     dword ptr [rax+rax+00h]
0x140063c18  xor     edx, edx
0x140063c1a  mov     rcx, r13
0x140063c1d  call    cs:__imp_FltReleasePushLockEx
0x140063c24  nop     dword ptr [rax+rax+00h]
0x140063c29  mov     ecx, edi
0x140063c2b  mov     r14d, edi
0x140063c2e  call    HsmDbgBreakOnStatus
0x140063c33  jmp     loc_140063B83
0x140063c38  mov     r14d, 0C000CF01h
0x140063c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140063c45  lea     rax, WPP_GLOBAL_Control
0x140063c4c  cmp     rcx, rax
0x140063c4f  jz      loc_1400638ED
0x140063c55  test    dword ptr [rcx+2Ch], 100h
0x140063c5c  jz      loc_1400638ED
0x140063c62  cmp     byte ptr [rcx+29h], 2
0x140063c66  jb      loc_1400638ED
0x140063c6c  mov     rcx, [rcx+18h]
0x140063c70  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140063c77  mov     edx, 20h ; ' '
0x140063c7c  mov     dword ptr [rsp+0C8h+var_A0], r14d
0x140063c81  mov     r9, rbx
0x140063c84  mov     [rsp+0C8h+var_A8], r15
0x140063c89  call    WPP_SF_qqd
0x140063c8e  jmp     loc_1400638ED
0x140063c93  mov     edi, 0C000009Ah
0x140063c98  mov     ecx, edi
0x140063c9a  mov     r14d, edi
0x140063c9d  call    HsmDbgBreakOnStatus
0x140063ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x140063ca9  lea     rax, WPP_GLOBAL_Control
0x140063cb0  cmp     rcx, rax
0x140063cb3  jz      loc_140063B16
0x140063cb9  test    dword ptr [rcx+2Ch], 100h
0x140063cc0  jz      loc_140063B16
0x140063cc6  cmp     byte ptr [rcx+29h], 2
0x140063cca  jb      loc_140063B16
0x140063cd0  mov     rcx, [rcx+18h]
0x140063cd4  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140063cdb  mov     edx, 21h ; '!'
0x140063ce0  mov     [rsp+0C8h+var_A8], r15
0x140063ce5  mov     r9, rbx
0x140063ce8  call    WPP_SF_qi
0x140063ced  jmp     loc_140063B16
0x140063cf2  mov     edi, 0C00000E5h
0x140063cf7  jmp     loc_140063BD8
0x140063cfc  test    dword ptr [rcx+2Ch], 100h
0x140063d03  jz      loc_140063B83
0x140063d09  cmp     byte ptr [rcx+29h], 2
0x140063d0d  jb      loc_140063B83
0x140063d13  mov     rcx, [rcx+18h]
0x140063d17  mov     edx, 22h ; '"'
0x140063d1c  mov     [rsp+0C8h+var_A0], r15
0x140063d21  mov     r9, r12
0x140063d24  mov     [rsp+0C8h+var_A8], rbx
0x140063d29  call    WPP_SF_qqi
0x140063d2e  jmp     loc_140063B83
0x140063d33  mov     edx, 68727343h; Tag
0x140063d38  call    cs:__imp_ExFreePoolWithTag
0x140063d3f  nop     dword ptr [rax+rax+00h]
0x140063d44  jmp     loc_140063B91
0x140063d49  mov     rax, [r12]
0x140063d4d  mov     edx, 23h ; '#'
0x140063d52  mov     rcx, [rcx+18h]
0x140063d56  mov     r9, r12
0x140063d59  mov     r8, [rax]
0x140063d5c  mov     rax, [r8+10h]
0x140063d60  mov     rax, [rax+20h]
0x140063d64  mov     [rsp+0C8h+var_A0], rax
0x140063d69  mov     rax, [r8+28h]
0x140063d6d  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140063d74  mov     [rsp+0C8h+var_A8], rax
0x140063d79  call    WPP_SF_qqq
0x140063d7e  jmp     loc_140063B0A
```
