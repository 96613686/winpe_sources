# ActionFveExternalDataDeleteEntries

- ea: `0x1400551f4`
- end: `0x140055816`
- name: `ActionFveExternalDataDeleteEntries`
- size: `1570`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008b6ec`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x14000ba48`
- `0x14001530c`
- `0x140022bf0`
- `0x140023040`
- `0x1400551f4`
- `0x140066554`
- `0x140066e1c`
- `0x1400675c4`
- `0x1400678d8`
- `0x140067ae0`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140055549`
- `ntoskrnl!ProbeForWrite` at `0x140055549`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14005546c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14005546c`
- `ntoskrnl!KeStackAttachProcess` at `0x14005552b`
- `ntoskrnl!KeStackAttachProcess` at `0x14005552b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005549c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005549c`
- `ntoskrnl!ExAllocatePool2` at `0x14005536d`
- `ntoskrnl!ExAllocatePool2` at `0x14005536d`

## pseudocode

```c
__int64 __fastcall ActionFveExternalDataDeleteEntries(__int64 a1, __int64 a2, unsigned __int16 *a3)
{
  _BYTE *v6; // r12
  int v7; // ebx
  char v8; // r15
  int v9; // r8d
  _BYTE *Pool2; // rax
  __int64 v11; // r8
  int active; // eax
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  _BYTE *v16; // rcx
  int v18; // eax
  int v19; // eax
  char v20; // [rsp+32h] [rbp-136h]
  USHORT v21[2]; // [rsp+34h] [rbp-134h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-130h] BYREF
  int v23; // [rsp+3Ch] [rbp-12Ch]
  void *v24; // [rsp+40h] [rbp-128h]
  __int64 v25; // [rsp+48h] [rbp-120h]
  PRKPROCESS PROCESS; // [rsp+50h] [rbp-118h]
  _BYTE v27[144]; // [rsp+60h] [rbp-108h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+F0h] [rbp-78h] BYREF

  v25 = a2;
  memset(&ApcState, 0, sizeof(ApcState));
  memset(v27, 0, sizeof(v27));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 170, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids);
  }
  v6 = 0;
  v21[0] = 0;
  v20 = 0;
  v22 = 0x8000;
  if ( *a3 < 0x38u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 171, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids, *a3);
    }
LABEL_10:
    v7 = -1073741811;
LABEL_11:
    v8 = 0;
    goto LABEL_36;
  }
  v9 = *((_DWORD *)a3 + 1);
  if ( v9 != 30 || a3[1] != 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 172, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids, a3[1], v9);
    }
    goto LABEL_10;
  }
  PROCESS = *(PRKPROCESS *)(a2 + 120);
  if ( *(_BYTE *)(a2 + 64) )
  {
    v7 = FveCheckAdminAccess(a1, a2, 2);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          173,
          WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
          (unsigned int)v7);
      }
      goto LABEL_11;
    }
  }
  Pool2 = (_BYTE *)ExAllocatePool2(64, 0x8000, 809850438);
  v6 = Pool2;
  v24 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 174, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids, 0x8000);
    }
    v7 = -1073741670;
    goto LABEL_11;
  }
  memset(Pool2, 0, 0x8000u);
  LOBYTE(v11) = 1;
  FvepAcquireDevFveLock(a1, v27, v11);
  if ( (*(_DWORD *)(a1 + 852) & 0x200) != 0 )
    active = FveCopyActiveDatasetToBufferEDrv(a1, v6, 0x8000, &v22, 0);
  else
    active = FveCopyActiveDatasetToBuffer(a1, v6, 0x8000, &v22, 0);
  v23 = active;
  v7 = active;
  if ( active < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_35;
    }
    v14 = 176;
LABEL_34:
    WPP_SF_d(v13->AttachedDevice, v14, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids, (unsigned int)v7);
LABEL_35:
    v8 = 1;
    goto LABEL_36;
  }
  if ( !*(_BYTE *)(v25 + 64) )
  {
    v7 = FveDataSetExternalDataDeleteEntries((__int64)v6, (__int64)(a3 + 4), v21);
    if ( v7 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_35;
      }
      v14 = 180;
      goto LABEL_34;
    }
    if ( (*(_DWORD *)(a1 + 852) & 0x200) != 0 )
      v19 = FveApplyDataSetUpdateAndCommitEDrv(a1, v6, v22);
    else
      v19 = FveApplyDataSetUpdateAndCommit(a1);
    v7 = v19;
    if ( v19 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_35;
      }
      v14 = 181;
      goto LABEL_34;
    }
    **((_WORD **)a3 + 6) = v21[0];
LABEL_80:
    v7 = FveEnforceMountAndNotify(a1);
    if ( v7 >= 0 )
      goto LABEL_35;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_35;
    }
    v14 = 182;
    goto LABEL_34;
  }
  KeStackAttachProcess(PROCESS, &ApcState);
  v20 = 1;
  ProbeForWrite(*((volatile void **)a3 + 6), 2u, 4u);
  v7 = FveDataSetExternalDataDeleteEntries((__int64)v6, (__int64)(a3 + 4), v21);
  v23 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        177,
        WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
        (unsigned int)v7);
    }
    v8 = 1;
    goto LABEL_36;
  }
  if ( (*(_DWORD *)(a1 + 852) & 0x200) != 0 )
    v18 = FveApplyDataSetUpdateAndCommitEDrv(a1, v6, v22);
  else
    v18 = FveApplyDataSetUpdateAndCommit(a1);
  v23 = v18;
  v7 = v18;
  if ( v18 >= 0 )
  {
    **((_WORD **)a3 + 6) = v21[0];
    goto LABEL_80;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      178,
      WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
      (unsigned int)v18);
  }
  v8 = 1;
LABEL_36:
  if ( v20 )
    KeUnstackDetachProcess(&ApcState);
  if ( v6 )
  {
    v15 = v22;
    v16 = v6;
    if ( v22 )
    {
      do
      {
        *v16++ = 0;
        --v15;
      }
      while ( v15 );
    }
    ExFreePoolWithTag(v6, 0x30455646u);
  }
  if ( v8 )
    FvepReleaseDevFveLock(v27);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 183, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400551f4  mov     r11, rsp
0x1400551f7  push    rbx
0x1400551f8  push    rsi
0x1400551f9  push    rdi
0x1400551fa  push    r12
0x1400551fc  push    r13
0x1400551fe  push    r14
0x140055200  push    r15
0x140055202  sub     rsp, 130h
0x140055209  mov     rax, cs:__security_cookie
0x140055210  xor     rax, rsp
0x140055213  mov     [rsp+168h+var_48], rax
0x14005521b  mov     r13, r8
0x14005521e  mov     rbx, rdx
0x140055221  mov     [rsp+168h+var_120], rdx
0x140055226  mov     r15, rcx
0x140055229  xorps   xmm0, xmm0
0x14005522c  movups  xmmword ptr [r11-78h], xmm0
0x140055231  movups  xmmword ptr [r11-68h], xmm0
0x140055236  movups  xmmword ptr [r11-58h], xmm0
0x14005523b  xor     edx, edx; Val
0x14005523d  mov     r8d, 90h; Size
0x140055243  lea     rcx, [rsp+168h+var_108]; void *
0x140055248  call    memset
0x14005524d  lea     r14, WPP_GLOBAL_Control
0x140055254  mov     rcx, cs:WPP_GLOBAL_Control
0x14005525b  mov     edi, 1
0x140055260  cmp     rcx, r14
0x140055263  jz      short loc_140055288
0x140055265  mov     eax, [rcx+2Ch]
0x140055268  test    dil, al
0x14005526b  jz      short loc_140055288
0x14005526d  cmp     byte ptr [rcx+29h], 5
0x140055271  jb      short loc_140055288
0x140055273  mov     edx, 0AAh
0x140055278  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x14005527f  mov     rcx, [rcx+18h]
0x140055283  call    WPP_SF_
0x140055288  xor     esi, esi
0x14005528a  mov     r12d, esi
0x14005528d  mov     [rsp+168h+var_134], si
0x140055292  mov     [rsp+168h+var_136], sil
0x140055297  mov     [rsp+168h+var_130], 8000h
0x14005529f  movzx   edx, word ptr [r13+0]
0x1400552a4  cmp     edx, 38h ; '8'
0x1400552a7  jnb     short loc_1400552E8
0x1400552a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400552b0  cmp     rcx, r14
0x1400552b3  jz      short loc_1400552DB
0x1400552b5  mov     eax, [rcx+2Ch]
0x1400552b8  test    dil, al
0x1400552bb  jz      short loc_1400552DB
0x1400552bd  cmp     byte ptr [rcx+29h], 2
0x1400552c1  jb      short loc_1400552DB
0x1400552c3  mov     r9d, edx
0x1400552c6  mov     edx, 0ABh
0x1400552cb  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x1400552d2  mov     rcx, [rcx+18h]
0x1400552d6  call    WPP_SF_d
0x1400552db  mov     ebx, 0C000000Dh
0x1400552e0  mov     r15b, sil
0x1400552e3  jmp     loc_14005545D
0x1400552e8  mov     r8d, [r13+4]
0x1400552ec  cmp     r8d, 1Eh
0x1400552f0  jnz     loc_1400557CC
0x1400552f6  cmp     [r13+2], di
0x1400552fb  jnz     loc_1400557CC
0x140055301  mov     rax, [rbx+78h]
0x140055305  mov     [rsp+168h+PROCESS], rax
0x14005530a  cmp     [rbx+40h], sil
0x14005530e  jz      short loc_14005535B
0x140055310  mov     r8d, 2
0x140055316  mov     rdx, rbx
0x140055319  mov     rcx, r15
0x14005531c  call    FveCheckAdminAccess
0x140055321  mov     ebx, eax
0x140055323  test    eax, eax
0x140055325  jns     short loc_14005535B
0x140055327  mov     rcx, cs:WPP_GLOBAL_Control
0x14005532e  cmp     rcx, r14
0x140055331  jz      short loc_1400552E0
0x140055333  mov     eax, [rcx+2Ch]
0x140055336  test    dil, al
0x140055339  jz      short loc_1400552E0
0x14005533b  cmp     byte ptr [rcx+29h], 2
0x14005533f  jb      short loc_1400552E0
0x140055341  mov     edx, 0ADh
0x140055346  mov     r9d, ebx
0x140055349  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055350  mov     rcx, [rcx+18h]
0x140055354  call    WPP_SF_d
0x140055359  jmp     short loc_1400552E0
0x14005535b  mov     ebx, 8000h
0x140055360  mov     r8d, 30455646h
0x140055366  mov     edx, ebx
0x140055368  mov     ecx, 40h ; '@'
0x14005536d  call    cs:__imp_ExAllocatePool2
0x140055374  nop     dword ptr [rax+rax+00h]
0x140055379  mov     r12, rax
0x14005537c  mov     [rsp+168h+var_128], rax
0x140055381  test    rax, rax
0x140055384  jnz     short loc_1400553C4
0x140055386  mov     r10, cs:WPP_GLOBAL_Control
0x14005538d  cmp     r10, r14
0x140055390  jz      short loc_1400553BA
0x140055392  mov     ecx, [r10+2Ch]
0x140055396  test    dil, cl
0x140055399  jz      short loc_1400553BA
0x14005539b  cmp     byte ptr [r10+29h], 2
0x1400553a0  jb      short loc_1400553BA
0x1400553a2  mov     edx, 0AEh
0x1400553a7  mov     r9d, ebx
0x1400553aa  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x1400553b1  mov     rcx, [r10+18h]
0x1400553b5  call    WPP_SF_d
0x1400553ba  mov     ebx, 0C000009Ah
0x1400553bf  jmp     loc_1400552E0
0x1400553c4  mov     r8, rbx; Size
0x1400553c7  xor     edx, edx; Val
0x1400553c9  mov     rcx, r12; void *
0x1400553cc  call    memset
0x1400553d1  mov     r8b, dil
0x1400553d4  lea     rdx, [rsp+168h+var_108]
0x1400553d9  mov     rcx, r15
0x1400553dc  call    FvepAcquireDevFveLock
0x1400553e1  mov     al, dil
0x1400553e4  mov     [rsp+168h+var_138], al
0x1400553e8  mov     [rsp+168h+var_137], al
0x1400553ec  mov     byte ptr [rsp+168h+var_148], sil
0x1400553f1  lea     r9, [rsp+168h+var_130]
0x1400553f6  mov     r8d, ebx
0x1400553f9  mov     rdx, r12
0x1400553fc  mov     rcx, r15
0x1400553ff  test    dword ptr [r15+354h], 200h
0x14005540a  jz      short loc_140055413
0x14005540c  call    FveCopyActiveDatasetToBufferEDrv
0x140055411  jmp     short loc_140055418
0x140055413  call    FveCopyActiveDatasetToBuffer
0x140055418  mov     [rsp+168h+var_12C], eax
0x14005541c  mov     ebx, eax
0x14005541e  test    ebx, ebx
0x140055420  jns     loc_14005550F
0x140055426  mov     rcx, cs:WPP_GLOBAL_Control
0x14005542d  cmp     rcx, r14
0x140055430  jz      short loc_140055458
0x140055432  mov     eax, [rcx+2Ch]
0x140055435  test    dil, al
0x140055438  jz      short loc_140055458
0x14005543a  cmp     byte ptr [rcx+29h], 2
0x14005543e  jb      short loc_140055458
0x140055440  mov     edx, 0B0h
0x140055445  mov     r9d, ebx
0x140055448  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x14005544f  mov     rcx, [rcx+18h]
0x140055453  call    WPP_SF_d
0x140055458  mov     r15b, [rsp+168h+var_138]
0x14005545d  cmp     [rsp+168h+var_136], sil
0x140055462  jz      short loc_140055478
0x140055464  lea     rcx, [rsp+168h+ApcState]; ApcState
0x14005546c  call    cs:__imp_KeUnstackDetachProcess
0x140055473  nop     dword ptr [rax+rax+00h]
0x140055478  test    r12, r12
0x14005547b  jz      short loc_1400554A8
0x14005547d  mov     eax, [rsp+168h+var_130]
0x140055481  mov     rcx, r12
0x140055484  test    rax, rax
0x140055487  jz      short loc_140055494
0x140055489  mov     [rcx], sil
0x14005548c  add     rcx, rdi
0x14005548f  sub     rax, rdi
0x140055492  jnz     short loc_140055489
0x140055494  mov     edx, 30455646h; Tag
0x140055499  mov     rcx, r12; P
0x14005549c  call    cs:__imp_ExFreePoolWithTag
0x1400554a3  nop     dword ptr [rax+rax+00h]
0x1400554a8  test    r15b, r15b
0x1400554ab  jz      short loc_1400554B7
0x1400554ad  lea     rcx, [rsp+168h+var_108]
0x1400554b2  call    FvepReleaseDevFveLock
0x1400554b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400554be  cmp     rcx, r14
0x1400554c1  jz      short loc_1400554E9
0x1400554c3  mov     eax, [rcx+2Ch]
0x1400554c6  test    dil, al
0x1400554c9  jz      short loc_1400554E9
0x1400554cb  cmp     byte ptr [rcx+29h], 5
0x1400554cf  jb      short loc_1400554E9
0x1400554d1  mov     edx, 0B7h
0x1400554d6  mov     r9d, ebx
0x1400554d9  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x1400554e0  mov     rcx, [rcx+18h]
0x1400554e4  call    WPP_SF_d
0x1400554e9  mov     eax, ebx
0x1400554eb  mov     rcx, [rsp+168h+var_48]
0x1400554f3  xor     rcx, rsp; StackCookie
0x1400554f6  call    __security_check_cookie
0x1400554fb  add     rsp, 130h
0x140055502  pop     r15
0x140055504  pop     r14
0x140055506  pop     r13
0x140055508  pop     r12
0x14005550a  pop     rdi
0x14005550b  pop     rsi
0x14005550c  pop     rbx
0x14005550d  retn
0x14005550f  mov     rax, [rsp+168h+var_120]
0x140055514  cmp     [rax+40h], sil
0x140055518  jz      loc_140055682
0x14005551e  lea     rdx, [rsp+168h+ApcState]; ApcState
0x140055526  mov     rcx, [rsp+168h+PROCESS]; PROCESS
0x14005552b  call    cs:__imp_KeStackAttachProcess
0x140055532  nop     dword ptr [rax+rax+00h]
0x140055537  mov     [rsp+168h+var_136], dil
0x14005553c  mov     edx, 2; Length
0x140055541  lea     r8d, [rdx+2]; Alignment
0x140055545  mov     rcx, [r13+30h]; Address
0x140055549  call    cs:__imp_ProbeForWrite
0x140055550  nop     dword ptr [rax+rax+00h]
0x140055555  lea     rdx, [r13+8]
0x140055559  lea     r8, [rsp+168h+var_134]
0x14005555e  mov     rcx, r12
0x140055561  call    FveDataSetExternalDataDeleteEntries
0x140055566  mov     ebx, eax
0x140055568  mov     [rsp+168h+var_12C], eax
0x14005556c  test    eax, eax
0x14005556e  jns     short loc_1400555AC
0x140055570  mov     rcx, cs:WPP_GLOBAL_Control
0x140055577  cmp     rcx, r14
0x14005557a  jz      short loc_1400555A2
0x14005557c  mov     eax, [rcx+2Ch]
0x14005557f  test    dil, al
0x140055582  jz      short loc_1400555A2
0x140055584  cmp     byte ptr [rcx+29h], 2
0x140055588  jb      short loc_1400555A2
0x14005558a  mov     edx, 0B1h
0x14005558f  mov     r9d, ebx
0x140055592  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055599  mov     rcx, [rcx+18h]
0x14005559d  call    WPP_SF_d
0x1400555a2  mov     r15b, [rsp+168h+var_138]
0x1400555a7  jmp     loc_14005545D
0x1400555ac  mov     r8d, [rsp+168h+var_130]
0x1400555b1  mov     rdx, r12
0x1400555b4  mov     rcx, r15
0x1400555b7  test    dword ptr [r15+354h], 200h
0x1400555c2  jz      short loc_1400555CB
0x1400555c4  call    FveApplyDataSetUpdateAndCommitEDrv
0x1400555c9  jmp     short loc_1400555D0
0x1400555cb  call    FveApplyDataSetUpdateAndCommit
0x1400555d0  mov     [rsp+168h+var_12C], eax
0x1400555d4  mov     ebx, eax
0x1400555d6  test    eax, eax
0x1400555d8  jns     short loc_140055616
0x1400555da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400555e1  cmp     rcx, r14
0x1400555e4  jz      short loc_14005560C
0x1400555e6  mov     eax, [rcx+2Ch]
0x1400555e9  test    dil, al
0x1400555ec  jz      short loc_14005560C
0x1400555ee  cmp     byte ptr [rcx+29h], 2
0x1400555f2  jb      short loc_14005560C
0x1400555f4  mov     edx, 0B2h
0x1400555f9  mov     r9d, ebx
0x1400555fc  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055603  mov     rcx, [rcx+18h]
0x140055607  call    WPP_SF_d
0x14005560c  mov     r15b, [rsp+168h+var_138]
0x140055611  jmp     loc_14005545D
0x140055616  mov     rcx, [r13+30h]
0x14005561a  movzx   eax, [rsp+168h+var_134]
0x14005561f  mov     [rcx], ax
0x140055622  jmp     loc_14005572F
0x140055627  mov     ebx, eax
0x140055629  mov     [rsp+168h+var_12C], eax
0x14005562d  lea     rax, WPP_GLOBAL_Control
0x140055634  mov     rcx, cs:WPP_GLOBAL_Control
0x14005563b  cmp     rcx, rax
0x14005563e  jz      short loc_140055665
0x140055640  mov     eax, [rcx+2Ch]
0x140055643  test    al, 1
0x140055645  jz      short loc_140055665
0x140055647  cmp     byte ptr [rcx+29h], 2
0x14005564b  jb      short loc_140055665
0x14005564d  mov     edx, 0B3h
0x140055652  mov     r9d, ebx
0x140055655  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x14005565c  mov     rcx, [rcx+18h]
0x140055660  call    WPP_SF_d
0x140055665  lea     r14, WPP_GLOBAL_Control
0x14005566c  mov     edi, 1
0x140055671  xor     esi, esi
0x140055673  mov     r12, [rsp+168h+var_128]
0x140055678  mov     r15b, [rsp+168h+var_137]
0x14005567d  jmp     loc_14005545D
0x140055682  lea     rdx, [r13+8]
0x140055686  lea     r8, [rsp+168h+var_134]
0x14005568b  mov     rcx, r12
0x14005568e  call    FveDataSetExternalDataDeleteEntries
0x140055693  mov     ebx, eax
0x140055695  test    eax, eax
  ... truncated ...
```
