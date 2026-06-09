# CldStreamOpen

- ea: `0x140063790`
- end: `0x140063c63`
- name: `CldStreamOpen`
- size: `1235`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x14003fc70`
- `0x140040090`
- `0x1400630e0`
- `0x1400829e0`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000d868`
- `0x140010bb4`
- `0x1400111bc`
- `0x14001e580`
- `0x140063790`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400639b8`
- `ntoskrnl!KeInitializeEvent` at `0x1400639b8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140063952`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140063952`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140063ad0`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140063ad0`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140063a16`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140063a16`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140063908`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140063908`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140063aec`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140063aec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063c18`
- `ntoskrnl!ExAllocatePool2` at `0x14006381d`
- `ntoskrnl!ExAllocatePool2` at `0x140063996`
- `ntoskrnl!ExAllocatePool2` at `0x14006381d`
- `ntoskrnl!ExAllocatePool2` at `0x140063996`
- `FLTMGR!FltReleasePushLockEx` at `0x1400637d3`
- `FLTMGR!FltReleasePushLockEx` at `0x140063973`
- `FLTMGR!FltReleasePushLockEx` at `0x140063a9b`
- `FLTMGR!FltReleasePushLockEx` at `0x140063afd`
- `FLTMGR!FltReleasePushLockEx` at `0x1400637d3`
- `FLTMGR!FltReleasePushLockEx` at `0x140063973`
- `FLTMGR!FltReleasePushLockEx` at `0x140063a9b`
- `FLTMGR!FltReleasePushLockEx` at `0x140063afd`
- `FLTMGR!FltInitializePushLock` at `0x140063857`
- `FLTMGR!FltInitializePushLock` at `0x140063882`
- `FLTMGR!FltInitializePushLock` at `0x140063962`
- `FLTMGR!FltInitializePushLock` at `0x140063857`
- `FLTMGR!FltInitializePushLock` at `0x140063882`
- `FLTMGR!FltInitializePushLock` at `0x140063962`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400637b7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400638da`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400637b7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400638da`

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
  __int64 Buffer; // [rsp+30h] [rbp-98h] BYREF
  unsigned __int64 *v20; // [rsp+38h] [rbp-90h]
  _BYTE v21[72]; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int8 NewElement; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v23; // [rsp+D8h] [rbp+10h] BYREF
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
      v23 = *(_QWORD *)(*a1 + 40LL);
      memset(v21, 0, sizeof(v21));
      v11 = v10 + 104;
      NewElement = 0;
      Buffer = v23;
      v20 = v7;
      FltAcquirePushLockExclusiveEx(v10 + 104, 0);
      Table = (PRTL_AVL_TABLE)(v10 + 112);
      inserted = (char *)RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(v10 + 112), &Buffer, 0x58u, &NewElement);
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
              WPP_SF_qqi(WPP_GLOBAL_Control->AttachedDevice, 34, v16, v7, a1, v3, Buffer, v20);
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
        RtlDeleteElementGenericTableAvl(Table, &v23);
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
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids, a1, v3);
    }
  }
LABEL_3:
  FltReleasePushLockEx(a1 + 3, 0);
  return v4;
}

```

## disassembly

```asm
0x140063790  push    rbx
0x140063792  push    rbp
0x140063793  push    rsi
0x140063794  push    r14
0x140063796  push    r15
0x140063798  sub     rsp, 0A0h
0x14006379f  mov     rax, [rcx]
0x1400637a2  mov     rbx, rcx
0x1400637a5  mov     rsi, [rcx+10h]
0x1400637a9  xor     edx, edx
0x1400637ab  mov     rcx, [rax+10h]
0x1400637af  mov     r15, [rcx+20h]
0x1400637b3  lea     rcx, [rbx+18h]
0x1400637b7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400637be  nop     dword ptr [rax+rax+00h]
0x1400637c3  cmp     qword ptr [rbx+20h], 0
0x1400637c8  jz      short loc_1400637F2
0x1400637ca  xor     r14d, r14d
0x1400637cd  xor     edx, edx
0x1400637cf  lea     rcx, [rbx+18h]
0x1400637d3  call    cs:__imp_FltReleasePushLockEx
0x1400637da  nop     dword ptr [rax+rax+00h]
0x1400637df  mov     eax, r14d
0x1400637e2  add     rsp, 0A0h
0x1400637e9  pop     r15
0x1400637eb  pop     r14
0x1400637ed  pop     rsi
0x1400637ee  pop     rbp
0x1400637ef  pop     rbx
0x1400637f0  retn
0x1400637f2  cmp     qword ptr [rsi+20h], 0
0x1400637f7  jz      loc_140063B18
0x1400637fd  mov     [rsp+0C8h+arg_18], rdi
0x140063805  mov     edx, 78h ; 'x'
0x14006380a  mov     ecx, 100h
0x14006380f  mov     [rsp+0C8h+var_30], r12
0x140063817  mov     r8d, 74736C43h
0x14006381d  call    cs:__imp_ExAllocatePool2
0x140063824  nop     dword ptr [rax+rax+00h]
0x140063829  mov     r12, rax
0x14006382c  test    rax, rax
0x14006382f  jz      loc_140063B73
0x140063835  mov     [rax], rbx
0x140063838  lea     rcx, [r12+20h]; PushLock
0x14006383d  xor     r14d, r14d
0x140063840  mov     [rsp+0C8h+var_38], r13
0x140063848  mov     [rax+8], r14
0x14006384c  add     rax, 10h
0x140063850  mov     [rax+8], rax
0x140063854  mov     [rax], rax
0x140063857  call    cs:__imp_FltInitializePushLock
0x14006385e  nop     dword ptr [rax+rax+00h]
0x140063863  mov     rax, [r12]
0x140063867  mov     rcx, [rax]
0x14006386a  mov     eax, [rcx+1Ch]
0x14006386d  test    al, 2
0x14006386f  jnz     short loc_14006389A
0x140063871  lea     rax, [r12+48h]
0x140063876  lea     rcx, [r12+58h]; PushLock
0x14006387b  mov     [rax+8], rax
0x14006387f  mov     [rax], rax
0x140063882  call    cs:__imp_FltInitializePushLock
0x140063889  nop     dword ptr [rax+rax+00h]
0x14006388e  lea     rax, [r12+60h]
0x140063893  mov     [rax+8], rax
0x140063897  mov     [rax], rax
0x14006389a  mov     rax, [rbx]
0x14006389d  lea     rcx, [rsp+0C8h+var_88]; void *
0x1400638a2  mov     rsi, [rsi+20h]
0x1400638a6  xor     edx, edx; Val
0x1400638a8  mov     r8d, 48h ; 'H'; Size
0x1400638ae  mov     rdi, [rax+28h]
0x1400638b2  mov     [rsp+0C8h+arg_8], rdi
0x1400638ba  call    memset
0x1400638bf  lea     r13, [rsi+68h]
0x1400638c3  mov     [rsp+0C8h+NewElement], r14b
0x1400638cb  mov     rcx, r13
0x1400638ce  mov     [rsp+0C8h+Buffer], rdi
0x1400638d3  xor     edx, edx
0x1400638d5  mov     [rsp+0C8h+var_90], r12
0x1400638da  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400638e1  nop     dword ptr [rax+rax+00h]
0x1400638e6  lea     rax, [rsi+70h]
0x1400638ea  mov     r8d, 58h ; 'X'; BufferSize
0x1400638f0  mov     rcx, rax; Table
0x1400638f3  mov     [rsp+0C8h+Table], rax
0x1400638fb  lea     r9, [rsp+0C8h+NewElement]; NewElement
0x140063903  lea     rdx, [rsp+0C8h+Buffer]; Buffer
0x140063908  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14006390f  nop     dword ptr [rax+rax+00h]
0x140063914  mov     rdi, rax
0x140063917  test    rax, rax
0x14006391a  jz      loc_140063A8A
0x140063920  lea     rsi, [rax+20h]
0x140063924  cmp     [rsp+0C8h+NewElement], r14b
0x14006392c  jz      loc_140063BD2
0x140063932  mov     [rsi], r14d
0x140063935  mov     rax, [r12]
0x140063939  mov     rcx, [rax]
0x14006393c  mov     eax, [rcx+1Ch]
0x14006393f  test    al, 2
0x140063941  jz      loc_140063A0B
0x140063947  xorps   xmm0, xmm0
0x14006394a  movups  xmmword ptr [rdi+28h], xmm0
0x14006394e  lea     rcx, [rdi+10h]; RunRef
0x140063952  call    cs:__imp_ExInitializeRundownProtection
0x140063959  nop     dword ptr [rax+rax+00h]
0x14006395e  lea     rcx, [rdi+18h]; PushLock
0x140063962  call    cs:__imp_FltInitializePushLock
0x140063969  nop     dword ptr [rax+rax+00h]
0x14006396e  xor     edx, edx
0x140063970  mov     rcx, r13
0x140063973  call    cs:__imp_FltReleasePushLockEx
0x14006397a  nop     dword ptr [rax+rax+00h]
0x14006397f  xor     ecx, ecx
0x140063981  call    HsmDbgBreakOnStatus
0x140063986  mov     edx, 18h
0x14006398b  mov     ecx, 40h ; '@'
0x140063990  mov     r8d, 68727343h
0x140063996  call    cs:__imp_ExAllocatePool2
0x14006399d  nop     dword ptr [rax+rax+00h]
0x1400639a2  mov     [r12+40h], rax
0x1400639a7  test    rax, rax
0x1400639aa  jz      loc_140063A3D
0x1400639b0  mov     r8b, 1; State
0x1400639b3  xor     edx, edx; Type
0x1400639b5  mov     rcx, rax; Event
0x1400639b8  call    cs:__imp_KeInitializeEvent
0x1400639bf  nop     dword ptr [rax+rax+00h]
0x1400639c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400639cb  lea     rax, WPP_GLOBAL_Control
0x1400639d2  cmp     rcx, rax
0x1400639d5  jz      short loc_1400639EA
0x1400639d7  test    dword ptr [rcx+2Ch], 100h
0x1400639de  jz      short loc_1400639EA
0x1400639e0  cmp     byte ptr [rcx+29h], 5
0x1400639e4  jnb     loc_140063C29
0x1400639ea  mov     [rbx+20h], r12
0x1400639ee  mov     r13, [rsp+0C8h+var_38]
0x1400639f6  mov     rdi, [rsp+0C8h+arg_18]
0x1400639fe  mov     r12, [rsp+0C8h+var_30]
0x140063a06  jmp     loc_1400637CD
0x140063a0b  xor     r8d, r8d; Flags
0x140063a0e  mov     edx, 1; PoolType
0x140063a13  mov     rcx, rsi; Mcb
0x140063a16  call    cs:__imp_FsRtlInitializeBaseMcbEx
0x140063a1d  nop     dword ptr [rax+rax+00h]
0x140063a22  test    al, al
0x140063a24  jz      loc_140063AB3
0x140063a2a  xorps   xmm0, xmm0
0x140063a2d  xorps   xmm1, xmm1
0x140063a30  movups  xmmword ptr [rdi+38h], xmm0
0x140063a34  movups  xmmword ptr [rdi+48h], xmm1
0x140063a38  jmp     loc_14006394E
0x140063a3d  mov     edi, 0C000009Ah
0x140063a42  mov     ecx, edi
0x140063a44  mov     r14d, edi
0x140063a47  call    HsmDbgBreakOnStatus
0x140063a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140063a53  lea     rax, WPP_GLOBAL_Control
0x140063a5a  cmp     rcx, rax
0x140063a5d  jnz     loc_140063BDC
0x140063a63  mov     rcx, [r12+40h]; P
0x140063a68  test    rcx, rcx
0x140063a6b  jnz     loc_140063C13
0x140063a71  mov     edx, 74736C43h; Tag
0x140063a76  mov     rcx, r12; P
0x140063a79  call    cs:__imp_ExFreePoolWithTag
0x140063a80  nop     dword ptr [rax+rax+00h]
0x140063a85  jmp     loc_1400639EE
0x140063a8a  mov     edi, 0C000009Ah
0x140063a8f  mov     ecx, edi
0x140063a91  call    HsmDbgBreakOnStatus
0x140063a96  xor     edx, edx
0x140063a98  mov     rcx, r13
0x140063a9b  call    cs:__imp_FltReleasePushLockEx
0x140063aa2  nop     dword ptr [rax+rax+00h]
0x140063aa7  mov     ecx, edi
0x140063aa9  call    HsmDbgBreakOnStatus
0x140063aae  mov     r14d, edi
0x140063ab1  jmp     short loc_140063A63
0x140063ab3  mov     edi, 0C000009Ah
0x140063ab8  mov     ecx, edi
0x140063aba  call    HsmDbgBreakOnStatus
0x140063abf  mov     rax, [r12]
0x140063ac3  mov     rdx, [rax]
0x140063ac6  mov     eax, [rdx+1Ch]
0x140063ac9  test    al, 2
0x140063acb  jnz     short loc_140063ADC
0x140063acd  mov     rcx, rsi; Mcb
0x140063ad0  call    cs:__imp_FsRtlUninitializeBaseMcb
0x140063ad7  nop     dword ptr [rax+rax+00h]
0x140063adc  mov     rcx, [rsp+0C8h+Table]; Table
0x140063ae4  lea     rdx, [rsp+0C8h+arg_8]; Buffer
0x140063aec  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140063af3  nop     dword ptr [rax+rax+00h]
0x140063af8  xor     edx, edx
0x140063afa  mov     rcx, r13
0x140063afd  call    cs:__imp_FltReleasePushLockEx
0x140063b04  nop     dword ptr [rax+rax+00h]
0x140063b09  mov     ecx, edi
0x140063b0b  mov     r14d, edi
0x140063b0e  call    HsmDbgBreakOnStatus
0x140063b13  jmp     loc_140063A63
0x140063b18  mov     r14d, 0C000CF01h
0x140063b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140063b25  lea     rax, WPP_GLOBAL_Control
0x140063b2c  cmp     rcx, rax
0x140063b2f  jz      loc_1400637CD
0x140063b35  test    dword ptr [rcx+2Ch], 100h
0x140063b3c  jz      loc_1400637CD
0x140063b42  cmp     byte ptr [rcx+29h], 2
0x140063b46  jb      loc_1400637CD
0x140063b4c  mov     rcx, [rcx+18h]
0x140063b50  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140063b57  mov     edx, 20h ; ' '
0x140063b5c  mov     dword ptr [rsp+0C8h+var_A0], r14d
0x140063b61  mov     r9, rbx
0x140063b64  mov     [rsp+0C8h+var_A8], r15
0x140063b69  call    WPP_SF_qqd
0x140063b6e  jmp     loc_1400637CD
0x140063b73  mov     edi, 0C000009Ah
0x140063b78  mov     ecx, edi
0x140063b7a  mov     r14d, edi
0x140063b7d  call    HsmDbgBreakOnStatus
0x140063b82  mov     rcx, cs:WPP_GLOBAL_Control
0x140063b89  lea     rax, WPP_GLOBAL_Control
0x140063b90  cmp     rcx, rax
0x140063b93  jz      loc_1400639F6
0x140063b99  test    dword ptr [rcx+2Ch], 100h
0x140063ba0  jz      loc_1400639F6
0x140063ba6  cmp     byte ptr [rcx+29h], 2
0x140063baa  jb      loc_1400639F6
0x140063bb0  mov     rcx, [rcx+18h]
0x140063bb4  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140063bbb  mov     edx, 21h ; '!'
0x140063bc0  mov     [rsp+0C8h+var_A8], r15
0x140063bc5  mov     r9, rbx
0x140063bc8  call    WPP_SF_qi
0x140063bcd  jmp     loc_1400639F6
0x140063bd2  mov     edi, 0C00000E5h
0x140063bd7  jmp     loc_140063AB8
0x140063bdc  test    dword ptr [rcx+2Ch], 100h
0x140063be3  jz      loc_140063A63
0x140063be9  cmp     byte ptr [rcx+29h], 2
0x140063bed  jb      loc_140063A63
0x140063bf3  mov     rcx, [rcx+18h]
0x140063bf7  mov     edx, 22h ; '"'
0x140063bfc  mov     [rsp+0C8h+var_A0], r15
0x140063c01  mov     r9, r12
0x140063c04  mov     [rsp+0C8h+var_A8], rbx
0x140063c09  call    WPP_SF_qqi
0x140063c0e  jmp     loc_140063A63
0x140063c13  mov     edx, 68727343h; Tag
0x140063c18  call    cs:__imp_ExFreePoolWithTag
0x140063c1f  nop     dword ptr [rax+rax+00h]
0x140063c24  jmp     loc_140063A71
0x140063c29  mov     rax, [r12]
0x140063c2d  mov     edx, 23h ; '#'
0x140063c32  mov     rcx, [rcx+18h]
0x140063c36  mov     r9, r12
0x140063c39  mov     r8, [rax]
0x140063c3c  mov     rax, [r8+10h]
0x140063c40  mov     rax, [rax+20h]
0x140063c44  mov     [rsp+0C8h+var_A0], rax
0x140063c49  mov     rax, [r8+28h]
0x140063c4d  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140063c54  mov     [rsp+0C8h+var_A8], rax
0x140063c59  call    WPP_SF_qqq
0x140063c5e  jmp     loc_1400639EA
```
