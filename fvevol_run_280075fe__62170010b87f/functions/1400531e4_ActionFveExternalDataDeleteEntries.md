# ActionFveExternalDataDeleteEntries

- ea: `0x1400531e4`
- end: `0x140053806`
- name: `ActionFveExternalDataDeleteEntries`
- size: `1570`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008964c`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x14000b920`
- `0x140014954`
- `0x1400218c0`
- `0x140021d00`
- `0x1400531e4`
- `0x1400644c4`
- `0x140064d8c`
- `0x140065534`
- `0x140065848`
- `0x140065a50`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140053539`
- `ntoskrnl!ProbeForWrite` at `0x140053539`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14005345c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14005345c`
- `ntoskrnl!KeStackAttachProcess` at `0x14005351b`
- `ntoskrnl!KeStackAttachProcess` at `0x14005351b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005348c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005348c`
- `ntoskrnl!ExAllocatePool2` at `0x14005335d`
- `ntoskrnl!ExAllocatePool2` at `0x14005335d`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 169, WPP_db10fbeca6e03e7325aab39114461952_Traceguids);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 170, WPP_db10fbeca6e03e7325aab39114461952_Traceguids, *a3);
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
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 171, WPP_db10fbeca6e03e7325aab39114461952_Traceguids, a3[1], v9);
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
          172,
          WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 173, WPP_db10fbeca6e03e7325aab39114461952_Traceguids, 0x8000);
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
    v14 = 175;
LABEL_34:
    WPP_SF_d(v13->AttachedDevice, v14, WPP_db10fbeca6e03e7325aab39114461952_Traceguids, (unsigned int)v7);
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
      v14 = 179;
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
      v14 = 180;
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
    v14 = 181;
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
        176,
        WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
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
      177,
      WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 182, WPP_db10fbeca6e03e7325aab39114461952_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400531e4  mov     r11, rsp
0x1400531e7  push    rbx
0x1400531e8  push    rsi
0x1400531e9  push    rdi
0x1400531ea  push    r12
0x1400531ec  push    r13
0x1400531ee  push    r14
0x1400531f0  push    r15
0x1400531f2  sub     rsp, 130h
0x1400531f9  mov     rax, cs:__security_cookie
0x140053200  xor     rax, rsp
0x140053203  mov     [rsp+168h+var_48], rax
0x14005320b  mov     r13, r8
0x14005320e  mov     rbx, rdx
0x140053211  mov     [rsp+168h+var_120], rdx
0x140053216  mov     r15, rcx
0x140053219  xorps   xmm0, xmm0
0x14005321c  movups  xmmword ptr [r11-78h], xmm0
0x140053221  movups  xmmword ptr [r11-68h], xmm0
0x140053226  movups  xmmword ptr [r11-58h], xmm0
0x14005322b  xor     edx, edx; Val
0x14005322d  mov     r8d, 90h; Size
0x140053233  lea     rcx, [rsp+168h+var_108]; void *
0x140053238  call    memset
0x14005323d  lea     r14, WPP_GLOBAL_Control
0x140053244  mov     rcx, cs:WPP_GLOBAL_Control
0x14005324b  mov     edi, 1
0x140053250  cmp     rcx, r14
0x140053253  jz      short loc_140053278
0x140053255  mov     eax, [rcx+2Ch]
0x140053258  test    dil, al
0x14005325b  jz      short loc_140053278
0x14005325d  cmp     byte ptr [rcx+29h], 5
0x140053261  jb      short loc_140053278
0x140053263  mov     edx, 0A9h
0x140053268  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x14005326f  mov     rcx, [rcx+18h]
0x140053273  call    WPP_SF_
0x140053278  xor     esi, esi
0x14005327a  mov     r12d, esi
0x14005327d  mov     [rsp+168h+var_134], si
0x140053282  mov     [rsp+168h+var_136], sil
0x140053287  mov     [rsp+168h+var_130], 8000h
0x14005328f  movzx   edx, word ptr [r13+0]
0x140053294  cmp     edx, 38h ; '8'
0x140053297  jnb     short loc_1400532D8
0x140053299  mov     rcx, cs:WPP_GLOBAL_Control
0x1400532a0  cmp     rcx, r14
0x1400532a3  jz      short loc_1400532CB
0x1400532a5  mov     eax, [rcx+2Ch]
0x1400532a8  test    dil, al
0x1400532ab  jz      short loc_1400532CB
0x1400532ad  cmp     byte ptr [rcx+29h], 2
0x1400532b1  jb      short loc_1400532CB
0x1400532b3  mov     r9d, edx
0x1400532b6  mov     edx, 0AAh
0x1400532bb  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x1400532c2  mov     rcx, [rcx+18h]
0x1400532c6  call    WPP_SF_d
0x1400532cb  mov     ebx, 0C000000Dh
0x1400532d0  mov     r15b, sil
0x1400532d3  jmp     loc_14005344D
0x1400532d8  mov     r8d, [r13+4]
0x1400532dc  cmp     r8d, 1Eh
0x1400532e0  jnz     loc_1400537BC
0x1400532e6  cmp     [r13+2], di
0x1400532eb  jnz     loc_1400537BC
0x1400532f1  mov     rax, [rbx+78h]
0x1400532f5  mov     [rsp+168h+PROCESS], rax
0x1400532fa  cmp     [rbx+40h], sil
0x1400532fe  jz      short loc_14005334B
0x140053300  mov     r8d, 2
0x140053306  mov     rdx, rbx
0x140053309  mov     rcx, r15
0x14005330c  call    FveCheckAdminAccess
0x140053311  mov     ebx, eax
0x140053313  test    eax, eax
0x140053315  jns     short loc_14005334B
0x140053317  mov     rcx, cs:WPP_GLOBAL_Control
0x14005331e  cmp     rcx, r14
0x140053321  jz      short loc_1400532D0
0x140053323  mov     eax, [rcx+2Ch]
0x140053326  test    dil, al
0x140053329  jz      short loc_1400532D0
0x14005332b  cmp     byte ptr [rcx+29h], 2
0x14005332f  jb      short loc_1400532D0
0x140053331  mov     edx, 0ACh
0x140053336  mov     r9d, ebx
0x140053339  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053340  mov     rcx, [rcx+18h]
0x140053344  call    WPP_SF_d
0x140053349  jmp     short loc_1400532D0
0x14005334b  mov     ebx, 8000h
0x140053350  mov     r8d, 30455646h
0x140053356  mov     edx, ebx
0x140053358  mov     ecx, 40h ; '@'
0x14005335d  call    cs:__imp_ExAllocatePool2
0x140053364  nop     dword ptr [rax+rax+00h]
0x140053369  mov     r12, rax
0x14005336c  mov     [rsp+168h+var_128], rax
0x140053371  test    rax, rax
0x140053374  jnz     short loc_1400533B4
0x140053376  mov     r10, cs:WPP_GLOBAL_Control
0x14005337d  cmp     r10, r14
0x140053380  jz      short loc_1400533AA
0x140053382  mov     ecx, [r10+2Ch]
0x140053386  test    dil, cl
0x140053389  jz      short loc_1400533AA
0x14005338b  cmp     byte ptr [r10+29h], 2
0x140053390  jb      short loc_1400533AA
0x140053392  mov     edx, 0ADh
0x140053397  mov     r9d, ebx
0x14005339a  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x1400533a1  mov     rcx, [r10+18h]
0x1400533a5  call    WPP_SF_d
0x1400533aa  mov     ebx, 0C000009Ah
0x1400533af  jmp     loc_1400532D0
0x1400533b4  mov     r8, rbx; Size
0x1400533b7  xor     edx, edx; Val
0x1400533b9  mov     rcx, r12; void *
0x1400533bc  call    memset
0x1400533c1  mov     r8b, dil
0x1400533c4  lea     rdx, [rsp+168h+var_108]
0x1400533c9  mov     rcx, r15
0x1400533cc  call    FvepAcquireDevFveLock
0x1400533d1  mov     al, dil
0x1400533d4  mov     [rsp+168h+var_138], al
0x1400533d8  mov     [rsp+168h+var_137], al
0x1400533dc  mov     byte ptr [rsp+168h+var_148], sil
0x1400533e1  lea     r9, [rsp+168h+var_130]
0x1400533e6  mov     r8d, ebx
0x1400533e9  mov     rdx, r12
0x1400533ec  mov     rcx, r15
0x1400533ef  test    dword ptr [r15+354h], 200h
0x1400533fa  jz      short loc_140053403
0x1400533fc  call    FveCopyActiveDatasetToBufferEDrv
0x140053401  jmp     short loc_140053408
0x140053403  call    FveCopyActiveDatasetToBuffer
0x140053408  mov     [rsp+168h+var_12C], eax
0x14005340c  mov     ebx, eax
0x14005340e  test    ebx, ebx
0x140053410  jns     loc_1400534FF
0x140053416  mov     rcx, cs:WPP_GLOBAL_Control
0x14005341d  cmp     rcx, r14
0x140053420  jz      short loc_140053448
0x140053422  mov     eax, [rcx+2Ch]
0x140053425  test    dil, al
0x140053428  jz      short loc_140053448
0x14005342a  cmp     byte ptr [rcx+29h], 2
0x14005342e  jb      short loc_140053448
0x140053430  mov     edx, 0AFh
0x140053435  mov     r9d, ebx
0x140053438  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x14005343f  mov     rcx, [rcx+18h]
0x140053443  call    WPP_SF_d
0x140053448  mov     r15b, [rsp+168h+var_138]
0x14005344d  cmp     [rsp+168h+var_136], sil
0x140053452  jz      short loc_140053468
0x140053454  lea     rcx, [rsp+168h+ApcState]; ApcState
0x14005345c  call    cs:__imp_KeUnstackDetachProcess
0x140053463  nop     dword ptr [rax+rax+00h]
0x140053468  test    r12, r12
0x14005346b  jz      short loc_140053498
0x14005346d  mov     eax, [rsp+168h+var_130]
0x140053471  mov     rcx, r12
0x140053474  test    rax, rax
0x140053477  jz      short loc_140053484
0x140053479  mov     [rcx], sil
0x14005347c  add     rcx, rdi
0x14005347f  sub     rax, rdi
0x140053482  jnz     short loc_140053479
0x140053484  mov     edx, 30455646h; Tag
0x140053489  mov     rcx, r12; P
0x14005348c  call    cs:__imp_ExFreePoolWithTag
0x140053493  nop     dword ptr [rax+rax+00h]
0x140053498  test    r15b, r15b
0x14005349b  jz      short loc_1400534A7
0x14005349d  lea     rcx, [rsp+168h+var_108]
0x1400534a2  call    FvepReleaseDevFveLock
0x1400534a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400534ae  cmp     rcx, r14
0x1400534b1  jz      short loc_1400534D9
0x1400534b3  mov     eax, [rcx+2Ch]
0x1400534b6  test    dil, al
0x1400534b9  jz      short loc_1400534D9
0x1400534bb  cmp     byte ptr [rcx+29h], 5
0x1400534bf  jb      short loc_1400534D9
0x1400534c1  mov     edx, 0B6h
0x1400534c6  mov     r9d, ebx
0x1400534c9  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x1400534d0  mov     rcx, [rcx+18h]
0x1400534d4  call    WPP_SF_d
0x1400534d9  mov     eax, ebx
0x1400534db  mov     rcx, [rsp+168h+var_48]
0x1400534e3  xor     rcx, rsp; StackCookie
0x1400534e6  call    __security_check_cookie
0x1400534eb  add     rsp, 130h
0x1400534f2  pop     r15
0x1400534f4  pop     r14
0x1400534f6  pop     r13
0x1400534f8  pop     r12
0x1400534fa  pop     rdi
0x1400534fb  pop     rsi
0x1400534fc  pop     rbx
0x1400534fd  retn
0x1400534ff  mov     rax, [rsp+168h+var_120]
0x140053504  cmp     [rax+40h], sil
0x140053508  jz      loc_140053672
0x14005350e  lea     rdx, [rsp+168h+ApcState]; ApcState
0x140053516  mov     rcx, [rsp+168h+PROCESS]; PROCESS
0x14005351b  call    cs:__imp_KeStackAttachProcess
0x140053522  nop     dword ptr [rax+rax+00h]
0x140053527  mov     [rsp+168h+var_136], dil
0x14005352c  mov     edx, 2; Length
0x140053531  lea     r8d, [rdx+2]; Alignment
0x140053535  mov     rcx, [r13+30h]; Address
0x140053539  call    cs:__imp_ProbeForWrite
0x140053540  nop     dword ptr [rax+rax+00h]
0x140053545  lea     rdx, [r13+8]
0x140053549  lea     r8, [rsp+168h+var_134]
0x14005354e  mov     rcx, r12
0x140053551  call    FveDataSetExternalDataDeleteEntries
0x140053556  mov     ebx, eax
0x140053558  mov     [rsp+168h+var_12C], eax
0x14005355c  test    eax, eax
0x14005355e  jns     short loc_14005359C
0x140053560  mov     rcx, cs:WPP_GLOBAL_Control
0x140053567  cmp     rcx, r14
0x14005356a  jz      short loc_140053592
0x14005356c  mov     eax, [rcx+2Ch]
0x14005356f  test    dil, al
0x140053572  jz      short loc_140053592
0x140053574  cmp     byte ptr [rcx+29h], 2
0x140053578  jb      short loc_140053592
0x14005357a  mov     edx, 0B0h
0x14005357f  mov     r9d, ebx
0x140053582  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053589  mov     rcx, [rcx+18h]
0x14005358d  call    WPP_SF_d
0x140053592  mov     r15b, [rsp+168h+var_138]
0x140053597  jmp     loc_14005344D
0x14005359c  mov     r8d, [rsp+168h+var_130]
0x1400535a1  mov     rdx, r12
0x1400535a4  mov     rcx, r15
0x1400535a7  test    dword ptr [r15+354h], 200h
0x1400535b2  jz      short loc_1400535BB
0x1400535b4  call    FveApplyDataSetUpdateAndCommitEDrv
0x1400535b9  jmp     short loc_1400535C0
0x1400535bb  call    FveApplyDataSetUpdateAndCommit
0x1400535c0  mov     [rsp+168h+var_12C], eax
0x1400535c4  mov     ebx, eax
0x1400535c6  test    eax, eax
0x1400535c8  jns     short loc_140053606
0x1400535ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400535d1  cmp     rcx, r14
0x1400535d4  jz      short loc_1400535FC
0x1400535d6  mov     eax, [rcx+2Ch]
0x1400535d9  test    dil, al
0x1400535dc  jz      short loc_1400535FC
0x1400535de  cmp     byte ptr [rcx+29h], 2
0x1400535e2  jb      short loc_1400535FC
0x1400535e4  mov     edx, 0B1h
0x1400535e9  mov     r9d, ebx
0x1400535ec  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x1400535f3  mov     rcx, [rcx+18h]
0x1400535f7  call    WPP_SF_d
0x1400535fc  mov     r15b, [rsp+168h+var_138]
0x140053601  jmp     loc_14005344D
0x140053606  mov     rcx, [r13+30h]
0x14005360a  movzx   eax, [rsp+168h+var_134]
0x14005360f  mov     [rcx], ax
0x140053612  jmp     loc_14005371F
0x140053617  mov     ebx, eax
0x140053619  mov     [rsp+168h+var_12C], eax
0x14005361d  lea     rax, WPP_GLOBAL_Control
0x140053624  mov     rcx, cs:WPP_GLOBAL_Control
0x14005362b  cmp     rcx, rax
0x14005362e  jz      short loc_140053655
0x140053630  mov     eax, [rcx+2Ch]
0x140053633  test    al, 1
0x140053635  jz      short loc_140053655
0x140053637  cmp     byte ptr [rcx+29h], 2
0x14005363b  jb      short loc_140053655
0x14005363d  mov     edx, 0B2h
0x140053642  mov     r9d, ebx
0x140053645  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x14005364c  mov     rcx, [rcx+18h]
0x140053650  call    WPP_SF_d
0x140053655  lea     r14, WPP_GLOBAL_Control
0x14005365c  mov     edi, 1
0x140053661  xor     esi, esi
0x140053663  mov     r12, [rsp+168h+var_128]
0x140053668  mov     r15b, [rsp+168h+var_137]
0x14005366d  jmp     loc_14005344D
0x140053672  lea     rdx, [r13+8]
0x140053676  lea     r8, [rsp+168h+var_134]
0x14005367b  mov     rcx, r12
0x14005367e  call    FveDataSetExternalDataDeleteEntries
0x140053683  mov     ebx, eax
0x140053685  test    eax, eax
  ... truncated ...
```
