# ClasspServicePopulateTokenTransferRequest

- ea: `0x140059cb4`
- end: `0x14005a2fa`
- name: `ClasspServicePopulateTokenTransferRequest`
- size: `1606`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140056294`

## callees

- `0x1400017c0`
- `0x140002230`
- `0x140004950`
- `0x14001fc38`
- `0x140022668`
- `0x140023c50`
- `0x140027178`
- `0x1400273c4`
- `0x140027870`
- `0x14002c85c`
- `0x140031308`
- `0x1400314e4`
- `0x140059cb4`
- `0x14005b2a8`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14005a146`
- `ntoskrnl!IoFreeIrp` at `0x14005a146`
- `ntoskrnl!IoSetActivityIdIrp` at `0x14005a12f`
- `ntoskrnl!IoSetActivityIdIrp` at `0x14005a12f`
- `ntoskrnl!ExAllocatePool2` at `0x140059daa`
- `ntoskrnl!ExAllocatePool2` at `0x140059daa`
- `ntoskrnl!IoAllocateIrp` at `0x14005a0e3`
- `ntoskrnl!IoAllocateIrp` at `0x14005a0e3`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005a106`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005a106`

## pseudocode

```c
__int64 __fastcall ClasspServicePopulateTokenTransferRequest(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  unsigned int *v4; // r13
  __int64 v5; // r8
  __int64 v6; // r14
  unsigned int v7; // ecx
  char *v8; // rdx
  __int64 v9; // rbx
  unsigned int v10; // r12d
  __int64 v11; // rax
  __int64 *Pool2; // rax
  __int64 *v13; // rsi
  unsigned int v14; // ebx
  PSLIST_ENTRY v15; // rax
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  int v18; // r8d
  bool v19; // zf
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // rbx
  int v23; // r14d
  int v24; // edx
  struct _MDL *v25; // r10
  int v26; // r9d
  __int64 v27; // rax
  char v28; // cl
  char v29; // r8
  char *v30; // r15
  __int64 v31; // rsi
  int v32; // r13d
  __int64 v33; // rdx
  unsigned int v34; // ecx
  unsigned __int16 v35; // r12
  __int16 v36; // ax
  ULONG v37; // eax
  struct _MDL *v38; // rax
  PIRP v39; // r14
  PIRP Irp; // rbx
  PSLIST_ENTRY v41; // r12
  signed __int32 v42; // eax
  signed __int32 v43; // ebx
  __int64 v44; // r14
  __int64 v45; // r8
  __int64 v46; // r12
  __int64 v48; // [rsp+20h] [rbp-99h]
  unsigned int v49; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int64 v50; // [rsp+68h] [rbp-51h] BYREF
  __int64 v51; // [rsp+70h] [rbp-49h] BYREF
  __int64 v52; // [rsp+78h] [rbp-41h]
  struct _MDL *v53; // [rsp+80h] [rbp-39h]
  PSLIST_ENTRY v54; // [rsp+88h] [rbp-31h]
  __int64 v55; // [rsp+90h] [rbp-29h]
  char *v56; // [rsp+98h] [rbp-21h]
  __int64 *v57; // [rsp+A0h] [rbp-19h]
  unsigned int *v58; // [rsp+A8h] [rbp-11h]
  __int64 v59; // [rsp+B0h] [rbp-9h]
  __int128 v60; // [rsp+B8h] [rbp-1h] BYREF
  int v61; // [rsp+120h] [rbp+67h] BYREF
  __int64 v62; // [rsp+128h] [rbp+6Fh]
  int v63; // [rsp+130h] [rbp+77h] BYREF
  ULONG v64; // [rsp+138h] [rbp+7Fh] BYREF

  v62 = a2;
  v2 = a2;
  v49 = 0;
  v50 = 0;
  v64 = 0;
  v63 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 233, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1, a2);
  }
  v4 = *(unsigned int **)(v2 + 24);
  v5 = 0;
  v6 = *(_QWORD *)(a1 + 64);
  v7 = 0;
  v59 = v6;
  v58 = v4;
  v8 = (char *)v4 + v4[5];
  v9 = v4[3];
  v10 = v4[6] >> 4;
  v56 = v8;
  v61 = 0;
  v52 = 0;
  if ( v10 )
  {
    do
    {
      v11 = v7++;
      v5 += *(_QWORD *)&v8[16 * v11 + 8];
    }
    while ( v7 < v10 );
    v52 = v5;
  }
  ClasspGetTokenOperationCommandBufferLength(a1, 16, (unsigned int)&v61, (unsigned int)&v63, (__int64)&v64);
  Pool2 = (__int64 *)ExAllocatePool2(64, (unsigned int)(v61 + 384), 1867801427);
  v57 = Pool2;
  v13 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 234, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1);
    }
    v14 = -1073741670;
    goto LABEL_67;
  }
  *Pool2 = a1;
  Pool2[1] = v2;
  v15 = DequeueFreeTransferPacket(a1);
  v54 = v15;
  if ( !v15 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_53;
    }
    v17 = 235;
LABEL_52:
    WPP_SF_q(v16->AttachedDevice, v17, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1);
LABEL_53:
    v14 = -1073741670;
    ClasspCleanupOffloadReadContext(v13);
    goto LABEL_67;
  }
  v18 = v63;
  v13[29] = (__int64)v15;
  v53 = (struct _MDL *)(v13 + 48);
  v51 = 0;
  ClasspGetTokenOperationDescriptorLimits(a1, 16, v18, (unsigned int)&v49, (__int64)&v50);
  v19 = *(unsigned int *)((char *)v4 + v9 + 4) == 0;
  v55 = v9;
  if ( v19 && (v20 = *(_QWORD *)(v6 + 1152), (v21 = *(_QWORD *)(v20 + 152)) != 0) )
  {
    v22 = v50;
    if ( v50 >= v21 )
      v22 = *(_QWORD *)(v20 + 152);
  }
  else
  {
    v22 = v50;
  }
  v23 = v49;
  if ( v49 >= 0x40 )
    v23 = 64;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDI(WPP_GLOBAL_Control->AttachedDevice, 236, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1, v23, v22);
  }
  v24 = -1;
  v25 = (struct _MDL *)(v13 + 48);
  v61 = -1;
  v26 = 0;
  v50 = (unsigned __int64)(v13 + 50);
  v27 = 0;
  v63 = 0;
  v28 = 0;
  v49 = 0;
  v29 = 1;
  v60 = 0;
  if ( v23 )
  {
    v30 = v56;
    v31 = 0;
    v32 = v50;
    while ( 1 )
    {
      if ( v27 == v22 || v28 )
      {
LABEL_44:
        v2 = v62;
        v4 = v58;
        v25 = v53;
        v51 = v31;
        v13 = v57;
        break;
      }
      if ( v29 )
      {
        v61 = v24 + 1;
        v60 = *(_OWORD *)&v30[16 * (v24 + 1)];
      }
      v51 = 0;
      ClasspConvertDataSetRangeToBlockDescr(
        a1,
        v32,
        (unsigned int)&v63,
        v23,
        (__int64)&v49,
        v22,
        (__int64)&v60,
        (__int64)&v51);
      v24 = v61;
      if ( *((_QWORD *)&v60 + 1) )
      {
        v29 = 0;
      }
      else
      {
        v29 = 1;
        if ( v61 + 1 == v10 )
        {
          v28 = 1;
          goto LABEL_42;
        }
      }
      v28 = 0;
LABEL_42:
      v31 += v51;
      v26 = v63;
      if ( v63 == v23 )
        goto LABEL_44;
      v27 = v49;
    }
  }
  v33 = v55;
  BYTE2(v25->Next) &= ~1u;
  v34 = 16 * (v26 + 1);
  v49 = v34;
  v35 = v34 - 2;
  BYTE1(v25->Next) = 16 * (v26 + 1) - 2;
  LOBYTE(v25->Next) = (unsigned __int16)(16 * (v26 + 1) - 2) >> 8;
  HIBYTE(v25->Next) = *((_BYTE *)v4 + v33 + 4);
  BYTE6(v25->Next) = *((_BYTE *)v4 + v33 + 5);
  BYTE5(v25->Next) = *((_BYTE *)v4 + v33 + 6);
  BYTE4(v25->Next) = *((_BYTE *)v4 + v33 + 7);
  v36 = 16 * (v26 + 1) - 16;
  LOWORD(v62) = 16 * (v26 + 1) - 2;
  LOWORD(v61) = v36;
  *((_BYTE *)&v25->MdlFlags + 5) = v36;
  *((_BYTE *)&v25->MdlFlags + 4) = HIBYTE(v36);
  v37 = v64;
  if ( v34 > v64 )
    v37 = 16 * (v26 + 1);
  LODWORD(v50) = v37;
  v38 = ClasspBuildDeviceMdl(v25, v37);
  v53 = v38;
  if ( !v38 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_53;
    }
    v17 = 237;
    goto LABEL_52;
  }
  v19 = ClassPnPETWEnabled == 0;
  v39 = (PIRP)(v13 + 2);
  v13[30] = (__int64)v38;
  if ( !v19 )
  {
    Irp = IoAllocateIrp(*(_BYTE *)(a1 + 76), 0);
    if ( Irp )
    {
      v41 = v54;
      if ( (int)IoGetActivityIdIrp(v2, &v54[20].Next + 1) < 0 )
        *(PSLIST_ENTRY)((char *)v41 + 328) = *(PSLIST_ENTRY)v2;
      if ( (int)IoSetActivityIdIrp(Irp, &v41[20].Next + 1) >= 0 )
      {
        v35 = v62;
        --Irp->CurrentLocation;
        v39 = Irp;
        --Irp->Tail.Overlay.CurrentStackLocation;
        v13[28] = (__int64)Irp;
      }
      else
      {
        IoFreeIrp(Irp);
        v35 = v62;
      }
    }
  }
  v39->MdlAddress = v53;
  v42 = MaxTokenOperationListIdentifier;
  v39->IoStatus.Status = 0;
  v39->IoStatus.Information = 0;
  v39->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (_LIST_ENTRY *)1;
  _InterlockedCompareExchange(&TokenOperationListIdentifier, -1, v42);
  v43 = _InterlockedIncrement(&TokenOperationListIdentifier);
  v48 = (__int64)v39;
  v44 = (__int64)v54;
  ClasspSetupPopulateTokenTransferPacket((_DWORD)v13, (_DWORD)v54, v49, (_DWORD)v13 + 384, v48, v43);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v46 = v52;
  }
  else
  {
    v45 = v35;
    v46 = v52;
    WPP_SF_qIIDDDqDD(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned __int16)v61,
      v45,
      a1,
      v51 * *(unsigned int *)(v59 + 572),
      v52,
      v63,
      v45,
      (unsigned __int16)v61,
      v44,
      v43,
      *(unsigned int *)((char *)v4 + v55 + 4));
  }
  *((_DWORD *)v13 + 62) = v50;
  *((_DWORD *)v13 + 64) = v64;
  v13[33] = v51;
  *((_DWORD *)v13 + 63) = v43;
  v13[35] = v46;
  *(_BYTE *)(*(_QWORD *)(v2 + 184) + 3LL) |= 1u;
  SubmitTransferPacket(v44);
  v14 = 259;
LABEL_67:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 239, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1, v2, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x140059cb4  mov     [rsp-8+arg_8], rdx
0x140059cb9  push    rbp
0x140059cba  push    rbx
0x140059cbb  push    rsi
0x140059cbc  push    rdi
0x140059cbd  push    r12
0x140059cbf  push    r13
0x140059cc1  push    r14
0x140059cc3  push    r15
0x140059cc5  lea     rbp, [rsp-1Fh]
0x140059cca  sub     rsp, 0D8h
0x140059cd1  xor     esi, esi
0x140059cd3  mov     r15, rdx
0x140059cd6  mov     [rbp+57h+var_B0], esi
0x140059cd9  mov     rdi, rcx
0x140059cdc  mov     [rbp+57h+var_A8], rsi
0x140059ce0  mov     [rbp+57h+arg_18], esi
0x140059ce3  mov     [rbp+57h+arg_10], esi
0x140059ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x140059ced  lea     rax, WPP_GLOBAL_Control
0x140059cf4  lea     r10d, [rsi+10h]
0x140059cf8  cmp     rcx, rax
0x140059cfb  jz      short loc_140059D2C
0x140059cfd  mov     eax, [rcx+2Ch]
0x140059d00  test    r10b, al
0x140059d03  jz      short loc_140059D2C
0x140059d05  cmp     byte ptr [rcx+29h], 5
0x140059d09  jb      short loc_140059D2C
0x140059d0b  mov     rcx, [rcx+18h]
0x140059d0f  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140059d16  mov     edx, 0E9h
0x140059d1b  mov     [rsp+110h+var_F0], r15
0x140059d20  mov     r9, rdi
0x140059d23  call    WPP_SF_qq
0x140059d28  lea     r10d, [rsi+10h]
0x140059d2c  mov     r13, [r15+18h]
0x140059d30  mov     r8, rsi
0x140059d33  mov     r14, [rdi+40h]
0x140059d37  mov     ecx, esi
0x140059d39  mov     [rbp+57h+var_60], r14
0x140059d3d  mov     [rbp+57h+var_68], r13
0x140059d41  mov     edx, [r13+14h]
0x140059d45  mov     r12d, [r13+18h]
0x140059d49  add     rdx, r13
0x140059d4c  mov     ebx, [r13+0Ch]
0x140059d50  shr     r12d, 4
0x140059d54  mov     [rbp+57h+var_78], rdx
0x140059d58  mov     [rbp+57h+arg_0], esi
0x140059d5b  mov     [rbp+57h+var_98], rsi
0x140059d5f  test    r12d, r12d
0x140059d62  jz      short loc_140059D7A
0x140059d64  mov     eax, ecx
0x140059d66  inc     ecx
0x140059d68  shl     rax, 4
0x140059d6c  add     r8, [rax+rdx+8]
0x140059d71  cmp     ecx, r12d
0x140059d74  jb      short loc_140059D64
0x140059d76  mov     [rbp+57h+var_98], r8
0x140059d7a  lea     rax, [rbp+57h+arg_18]
0x140059d7e  mov     edx, r10d
0x140059d81  lea     r9, [rbp+57h+arg_10]
0x140059d85  mov     [rsp+110h+var_F0], rax
0x140059d8a  lea     r8, [rbp+57h+arg_0]
0x140059d8e  mov     rcx, rdi
0x140059d91  call    ClasspGetTokenOperationCommandBufferLength
0x140059d96  mov     edx, [rbp+57h+arg_0]
0x140059d99  mov     ecx, 40h ; '@'
0x140059d9e  add     edx, 180h
0x140059da4  mov     r8d, 6F546353h
0x140059daa  call    cs:__imp_ExAllocatePool2
0x140059db1  nop     dword ptr [rax+rax+00h]
0x140059db6  mov     [rbp+57h+var_70], rax
0x140059dba  mov     rsi, rax
0x140059dbd  test    rax, rax
0x140059dc0  jnz     short loc_140059E04
0x140059dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140059dc9  lea     rax, WPP_GLOBAL_Control
0x140059dd0  cmp     rcx, rax
0x140059dd3  jz      short loc_140059DFA
0x140059dd5  mov     eax, [rcx+2Ch]
0x140059dd8  test    al, 10h
0x140059dda  jz      short loc_140059DFA
0x140059ddc  cmp     byte ptr [rcx+29h], 2
0x140059de0  jb      short loc_140059DFA
0x140059de2  mov     rcx, [rcx+18h]
0x140059de6  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140059ded  mov     edx, 0EAh
0x140059df2  mov     r9, rdi
0x140059df5  call    WPP_SF_q
0x140059dfa  mov     ebx, 0C000009Ah
0x140059dff  jmp     loc_14005A2A2
0x140059e04  mov     rcx, rdi
0x140059e07  mov     [rax], rdi
0x140059e0a  mov     [rax+8], r15
0x140059e0e  call    DequeueFreeTransferPacket
0x140059e13  mov     [rbp+57h+var_88], rax
0x140059e17  test    rax, rax
0x140059e1a  jnz     short loc_140059E52
0x140059e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140059e23  lea     rax, WPP_GLOBAL_Control
0x140059e2a  cmp     rcx, rax
0x140059e2d  jz      loc_14005A0B8
0x140059e33  mov     eax, [rcx+2Ch]
0x140059e36  test    al, 10h
0x140059e38  jz      loc_14005A0B8
0x140059e3e  cmp     byte ptr [rcx+29h], 2
0x140059e42  jb      loc_14005A0B8
0x140059e48  mov     edx, 0EBh
0x140059e4d  jmp     loc_14005A0A5
0x140059e52  mov     r8d, [rbp+57h+arg_10]
0x140059e56  lea     r9, [rsi+180h]
0x140059e5d  mov     [rsi+0E8h], rax
0x140059e64  mov     edx, 10h
0x140059e69  mov     [rbp+57h+var_90], r9
0x140059e6d  lea     rax, [rbp+57h+var_A8]
0x140059e71  lea     r9, [rbp+57h+var_B0]
0x140059e75  mov     [rbp+57h+var_A0], 0
0x140059e7d  mov     rcx, rdi
0x140059e80  mov     [rsp+110h+var_F0], rax
0x140059e85  call    ClasspGetTokenOperationDescriptorLimits
0x140059e8a  cmp     dword ptr [rbx+r13+4], 0
0x140059e90  mov     [rbp+57h+var_80], rbx
0x140059e94  jnz     short loc_140059EB6
0x140059e96  mov     rax, [r14+480h]
0x140059e9d  mov     rcx, [rax+98h]
0x140059ea4  test    rcx, rcx
0x140059ea7  jz      short loc_140059EB6
0x140059ea9  mov     rbx, [rbp+57h+var_A8]
0x140059ead  cmp     rbx, rcx
0x140059eb0  cmovnb  rbx, rcx
0x140059eb4  jmp     short loc_140059EBA
0x140059eb6  mov     rbx, [rbp+57h+var_A8]
0x140059eba  mov     r14d, [rbp+57h+var_B0]
0x140059ebe  mov     eax, 40h ; '@'
0x140059ec3  cmp     r14d, eax
0x140059ec6  cmovnb  r14d, eax
0x140059eca  mov     rcx, cs:WPP_GLOBAL_Control
0x140059ed1  lea     rax, WPP_GLOBAL_Control
0x140059ed8  cmp     rcx, rax
0x140059edb  jz      short loc_140059F0C
0x140059edd  mov     eax, [rcx+2Ch]
0x140059ee0  test    al, 10h
0x140059ee2  jz      short loc_140059F0C
0x140059ee4  cmp     byte ptr [rcx+29h], 4
0x140059ee8  jb      short loc_140059F0C
0x140059eea  mov     rcx, [rcx+18h]
0x140059eee  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140059ef5  mov     edx, 0ECh
0x140059efa  mov     [rsp+110h+var_E8], rbx
0x140059eff  mov     r9, rdi
0x140059f02  mov     dword ptr [rsp+110h+var_F0], r14d
0x140059f07  call    WPP_SF_qDI
0x140059f0c  or      edx, 0FFFFFFFFh
0x140059f0f  lea     r10, [rsi+180h]
0x140059f16  lea     rax, [r10+10h]
0x140059f1a  mov     [rbp+57h+arg_0], edx
0x140059f1d  xor     r9d, r9d
0x140059f20  mov     [rbp+57h+var_A8], rax
0x140059f24  xor     eax, eax
0x140059f26  mov     [rbp+57h+arg_10], r9d
0x140059f2a  xor     cl, cl
0x140059f2c  mov     [rbp+57h+var_B0], eax
0x140059f2f  xorps   xmm0, xmm0
0x140059f32  mov     r8b, 1
0x140059f35  movups  [rbp+57h+var_58], xmm0
0x140059f39  test    r14d, r14d
0x140059f3c  jz      loc_140059FF8
0x140059f42  mov     r15, [rbp+57h+var_78]
0x140059f46  mov     esi, eax
0x140059f48  mov     r13, [rbp+57h+var_A8]
0x140059f4c  cmp     rax, rbx
0x140059f4f  jz      loc_140059FE4
0x140059f55  test    cl, cl
0x140059f57  jnz     loc_140059FE4
0x140059f5d  test    r8b, r8b
0x140059f60  jz      short loc_140059F76
0x140059f62  inc     edx
0x140059f64  mov     eax, edx
0x140059f66  add     rax, rax
0x140059f69  mov     [rbp+57h+arg_0], edx
0x140059f6c  movups  xmm0, xmmword ptr [r15+rax*8]
0x140059f71  movdqu  [rbp+57h+var_58], xmm0
0x140059f76  lea     rax, [rbp+57h+var_A0]
0x140059f7a  mov     [rbp+57h+var_A0], 0
0x140059f82  mov     [rsp+110h+var_D8], rax
0x140059f87  lea     r8, [rbp+57h+arg_10]
0x140059f8b  lea     rax, [rbp+57h+var_58]
0x140059f8f  mov     r9d, r14d
0x140059f92  mov     [rsp+110h+var_E0], rax
0x140059f97  mov     rdx, r13
0x140059f9a  lea     rax, [rbp+57h+var_B0]
0x140059f9e  mov     [rsp+110h+var_E8], rbx
0x140059fa3  mov     rcx, rdi
0x140059fa6  mov     [rsp+110h+var_F0], rax
0x140059fab  call    ClasspConvertDataSetRangeToBlockDescr
0x140059fb0  cmp     qword ptr [rbp+57h+var_58+8], 0
0x140059fb5  mov     edx, [rbp+57h+arg_0]
0x140059fb8  jnz     short loc_140059FCA
0x140059fba  lea     eax, [rdx+1]
0x140059fbd  mov     r8b, 1
0x140059fc0  cmp     eax, r12d
0x140059fc3  jnz     short loc_140059FCD
0x140059fc5  mov     cl, r8b
0x140059fc8  jmp     short loc_140059FCF
0x140059fca  xor     r8b, r8b
0x140059fcd  xor     cl, cl
0x140059fcf  add     rsi, [rbp+57h+var_A0]
0x140059fd3  mov     r9d, [rbp+57h+arg_10]
0x140059fd7  cmp     r9d, r14d
0x140059fda  jz      short loc_140059FE4
0x140059fdc  mov     eax, [rbp+57h+var_B0]
0x140059fdf  jmp     loc_140059F4C
0x140059fe4  mov     r15, [rbp+57h+arg_8]
0x140059fe8  mov     r13, [rbp+57h+var_68]
0x140059fec  mov     r10, [rbp+57h+var_90]
0x140059ff0  mov     [rbp+57h+var_A0], rsi
0x140059ff4  mov     rsi, [rbp+57h+var_70]
0x140059ff8  mov     rdx, [rbp+57h+var_80]
0x140059ffc  lea     ecx, [r9+1]
0x14005a000  and     byte ptr [r10+2], 0FEh
0x14005a005  mov     ebx, 10h
0x14005a00a  shl     ecx, 4
0x14005a00d  mov     [rbp+57h+var_B0], ecx
0x14005a010  lea     r12d, [rcx-2]
0x14005a014  mov     [r10+1], r12b
0x14005a018  movzx   eax, r12w
0x14005a01c  shr     ax, 8
0x14005a020  mov     [r10], al
0x14005a023  mov     al, [rdx+r13+4]
0x14005a028  mov     [r10+7], al
0x14005a02c  mov     al, [rdx+r13+5]
0x14005a031  mov     [r10+6], al
0x14005a035  mov     al, [rdx+r13+6]
0x14005a03a  mov     [r10+5], al
0x14005a03e  mov     al, [rdx+r13+7]
0x14005a043  mov     [r10+4], al
0x14005a047  movzx   eax, cx
0x14005a04a  sub     ax, bx
0x14005a04d  mov     word ptr [rbp+57h+arg_8], r12w
0x14005a052  mov     word ptr [rbp+57h+arg_0], ax
0x14005a056  mov     [r10+0Fh], al
0x14005a05a  shr     ax, 8
0x14005a05e  mov     [r10+0Eh], al
0x14005a062  mov     eax, [rbp+57h+arg_18]
0x14005a065  cmp     ecx, eax
0x14005a067  cmova   eax, ecx
0x14005a06a  mov     rcx, r10
0x14005a06d  mov     edx, eax
0x14005a06f  mov     dword ptr [rbp+57h+var_A8], eax
0x14005a072  call    ClasspBuildDeviceMdl
0x14005a077  mov     [rbp+57h+var_90], rax
0x14005a07b  test    rax, rax
0x14005a07e  jnz     short loc_14005A0CA
0x14005a080  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a087  lea     rax, WPP_GLOBAL_Control
0x14005a08e  cmp     rcx, rax
0x14005a091  jz      short loc_14005A0B8
0x14005a093  mov     eax, [rcx+2Ch]
0x14005a096  test    bl, al
0x14005a098  jz      short loc_14005A0B8
0x14005a09a  cmp     byte ptr [rcx+29h], 2
0x14005a09e  jb      short loc_14005A0B8
0x14005a0a0  mov     edx, 0EDh
0x14005a0a5  mov     rcx, [rcx+18h]
0x14005a0a9  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005a0b0  mov     r9, rdi
0x14005a0b3  call    WPP_SF_q
0x14005a0b8  mov     rcx, rsi; P
0x14005a0bb  mov     ebx, 0C000009Ah
0x14005a0c0  call    ClasspCleanupOffloadReadContext
0x14005a0c5  jmp     loc_14005A2A2
0x14005a0ca  cmp     cs:ClassPnPETWEnabled, 0
0x14005a0d1  lea     r14, [rsi+10h]
0x14005a0d5  mov     [rsi+0F0h], rax
0x14005a0dc  jz      short loc_14005A157
0x14005a0de  mov     cl, [rdi+4Ch]; StackSize
0x14005a0e1  xor     edx, edx; ChargeQuota
0x14005a0e3  call    cs:__imp_IoAllocateIrp
0x14005a0ea  nop     dword ptr [rax+rax+00h]
0x14005a0ef  mov     rbx, rax
0x14005a0f2  test    rax, rax
0x14005a0f5  jz      short loc_14005A157
0x14005a0f7  mov     r12, [rbp+57h+var_88]
0x14005a0fb  mov     rcx, r15
0x14005a0fe  lea     rdx, [r12+148h]
0x14005a106  call    cs:__imp_IoGetActivityIdIrp
0x14005a10d  nop     dword ptr [rax+rax+00h]
0x14005a112  test    eax, eax
0x14005a114  jns     short loc_14005A124
0x14005a116  movups  xmm0, xmmword ptr [r15]
0x14005a11a  movdqu  xmmword ptr [r12+148h], xmm0
0x14005a124  lea     rdx, [r12+148h]
0x14005a12c  mov     rcx, rbx
0x14005a12f  call    cs:__imp_IoSetActivityIdIrp
0x14005a136  nop     dword ptr [rax+rax+00h]
0x14005a13b  test    eax, eax
0x14005a13d  jns     loc_14005A23A
0x14005a143  mov     rcx, rbx; Irp
0x14005a146  call    cs:__imp_IoFreeIrp
0x14005a14d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
