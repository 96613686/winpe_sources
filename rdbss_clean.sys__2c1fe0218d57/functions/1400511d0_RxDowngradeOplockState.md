# RxDowngradeOplockState

- ea: `0x1400511d0`
- end: `0x140051a24`
- name: `RxDowngradeOplockState`
- size: `2132`
- prototype: ``
- caller_count: `4`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x140001b70`
- `0x140008910`
- `0x140023cf0`
- `0x140065690`

## callees

- `0x140003410`
- `0x1400037e0`
- `0x140008030`
- `0x140008190`
- `0x140012030`
- `0x140014d10`
- `0x140016e20`
- `0x140016e70`
- `0x140017220`
- `0x140017370`
- `0x140017420`
- `0x140017a38`
- `0x140023f04`
- `0x140023f98`
- `0x140024048`
- `0x140025d00`
- `0x1400511d0`
- `0x14005b620`
- `0x14006d6e0`

## import_xrefs

- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14005158e`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14005158e`
- `ntoskrnl!MmIsFileSectionActive` at `0x140051694`
- `ntoskrnl!MmIsFileSectionActive` at `0x140051694`
- `ntoskrnl!FsRtlCheckUpperOplock` at `0x140051373`
- `ntoskrnl!FsRtlCheckUpperOplock` at `0x140051373`
- `ntoskrnl!FsRtlGetNextFileLock` at `0x14005174d`
- `ntoskrnl!FsRtlGetNextFileLock` at `0x14005174d`

## pseudocode

```c
__int64 __fastcall RxDowngradeOplockState(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r11
  ULONG_PTR v4; // rbx
  __int64 v5; // r13
  char v6; // cl
  unsigned int v7; // r10d
  int v8; // edi
  __int64 (__fastcall *v9)(ULONG_PTR, __int64, _QWORD, unsigned int *); // rax
  int v10; // eax
  char v11; // r12
  __int64 v12; // rdi
  unsigned int v13; // eax
  __int64 v14; // rdx
  int v16; // edi
  NTSTATUS v17; // r9d
  char v18; // r12
  __int64 v19; // rcx
  PDEVICE_OBJECT v20; // rcx
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  int v24; // eax
  __int64 v25; // rdx
  _QWORD *v26; // rdi
  _QWORD *v27; // rdx
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rcx
  PRX_CONTEXT RxContext; // rax
  struct _RX_CONTEXT *v32; // rsi
  char v33; // cl
  char v34; // dl
  __int64 v35; // r13
  __int64 (__fastcall *v36)(struct _RX_CONTEXT *); // rax
  UCHAR IrpMajorCode; // [rsp+20h] [rbp-B8h]
  PVOID Context; // [rsp+28h] [rbp-B0h]
  int v39; // [rsp+60h] [rbp-78h]
  unsigned int v40; // [rsp+64h] [rbp-74h]
  char v41; // [rsp+68h] [rbp-70h]
  int v42; // [rsp+6Ch] [rbp-6Ch] BYREF
  char v43; // [rsp+70h] [rbp-68h]
  unsigned int v44; // [rsp+74h] [rbp-64h]
  _QWORD *v45; // [rsp+78h] [rbp-60h]
  ULONG_PTR v46; // [rsp+80h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+88h] [rbp-50h] BYREF
  char v49; // [rsp+E8h] [rbp+10h]
  char v50; // [rsp+F0h] [rbp+18h]
  unsigned int v51; // [rsp+F8h] [rbp+20h] BYREF

  v49 = a2;
  v3 = a1;
  v51 = 0;
  v4 = *(_QWORD *)(a1 + 40);
  v46 = v4;
  v5 = *(_QWORD *)(a1 + 32);
  v6 = 0;
  v41 = 0;
  v7 = *(_DWORD *)(v3 + 16);
  v8 = v7 & 0x1000000;
  v42 = v7 & 0x1000000;
  v39 = *(_DWORD *)(v4 + 164);
  v9 = *(__int64 (__fastcall **)(ULONG_PTR, __int64, _QWORD, unsigned int *))(*(_QWORD *)(v4 + 392) + 296LL);
  if ( v9 )
  {
    v10 = v9(v4, v5, *(_QWORD *)(v3 + 80), &v51);
    v3 = a1;
    v7 = *(_DWORD *)(a1 + 16);
    v6 = 0;
  }
  else
  {
    v10 = -1073741822;
  }
  if ( v10 == -1073741597 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    if ( v10 == -1073741528 )
      v6 = 1;
    v41 = v6;
  }
  v40 = v7 >> 31;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    Context = (PVOID)v5;
    IrpMajorCode = v4;
    WPP_SF_qqqDDddd(WPP_GLOBAL_Control->AttachedDevice, v5 == 0, v8 != 0, v3);
  }
  if ( v5 || v8 )
  {
    v12 = a1;
  }
  else
  {
    *(_DWORD *)(v4 + 156) |= 0x100000u;
    v12 = a1;
    *(_DWORD *)(a1 + 16) |= 0x1000000u;
    v13 = (v51 >> 4) & 2;
    if ( (v51 & 2) != 0 )
      v13 |= 4u;
    v14 = v13 | 1;
    if ( (v51 & 1) == 0 )
      v14 = v13;
    LODWORD(Context) = 0;
    IrpMajorCode = 0;
    if ( (unsigned int)FsRtlCheckUpperOplock(v4 + 88, v14, a1, RxUpperOplockBreakComplete) == 259 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, &WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, 259);
      }
      return 259;
    }
  }
  v50 = 0;
  *(_DWORD *)(v4 + 156) &= ~0x100000u;
  *(_DWORD *)(v12 + 16) &= ~0x1000000u;
  v44 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    Context = (PVOID)v5;
    IrpMajorCode = v4;
    WPP_SF_qqqDDd(WPP_GLOBAL_Control->AttachedDevice, a2, a3, v12);
  }
  if ( v11 || v41 || (v39 & 2) != 0 && (v51 & 2) == 0 )
  {
    LOBYTE(a2) = 1;
    v16 = RxFlushFcbInSystemCacheEx(v4, a2, 0);
    if ( v16 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 41, &WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, v4);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        IrpMajorCode = v16;
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 40, &WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, v4);
      }
      RxCcLogError((PDEVICE_OBJECT)v4, (PUNICODE_STRING)(unsigned int)v16, a3, v17, IrpMajorCode, Context);
    }
  }
  if ( v11 )
  {
    v18 = 0;
  }
  else
  {
    v18 = 0;
    if ( !v41 && ((v39 & 1) == 0 || (v51 & 1) != 0) )
      goto LABEL_59;
  }
  IoStatus = 0;
  LOBYTE(a3) = 1;
  RxAcquirePagingIoResource(0, v4, a3);
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(v19, &CcPurgeRequest, 0, v4);
  CcCoherencyFlushAndPurgeCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v4 + 304) + 8LL), 0, 0xFFFFFFFF, &IoStatus, 0);
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 42, &WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, v4);
  }
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    McTemplateK0p_EtwWriteTransfer(v20, &CcPurgeCompletion, 0, v4);
  RxReleasePagingIoResource(0, v4);
LABEL_59:
  if ( ((v39 & 0x10) != 0 || (v39 & 0x20) != 0) && (v51 & 0x10) == 0 && (v51 & 0x20) == 0 )
  {
    RxPurgeConflictingSrvOpensEx(v4, 0, 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, &WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, v4);
    }
  }
  if ( v42 )
  {
    if ( *(_DWORD *)(v4 + 184)
      || *(_DWORD *)(v4 + 192) != 1
      || (v42 = 0, MmIsFileSectionActive(*(_QWORD *)(v4 + 304) + 8LL, 7, &v42), v42) )
    {
      v21 = WPP_GLOBAL_Control;
      v18 = v40;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_81;
      }
      v23 = (unsigned __int8)v40;
      v22 = 45;
    }
    else
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_81;
      }
      v22 = 44;
      v23 = 0;
    }
    WPP_SF_dq(v21->AttachedDevice, v22, &WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, v23, v4);
  }
  else
  {
    v18 = v40;
  }
LABEL_81:
  v24 = *(_DWORD *)(v4 + 164) & v51;
  v51 = v24;
  if ( (v39 & 4) != 0 && (v24 & 4) == 0 && FsRtlGetNextFileLock((PFILE_LOCK)(v4 + 536), 1u) )
  {
    RxDisableLocalBuffering((PFCB)v4);
    if ( !*(_BYTE *)(v4 + 640) )
    {
      v50 = 1;
      v43 = 1;
      *(_BYTE *)(v4 + 640) = 1;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 46, &WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, v4);
    }
  }
  if ( v5 && !v51 )
    *(_DWORD *)(v5 + 72) |= 0x40u;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    if ( v5 )
      v25 = *(unsigned int *)(v5 + 92);
    else
      v25 = 0;
    WPP_SF_qqqdDDd(WPP_GLOBAL_Control->AttachedDevice, v25, a3, a1, v4, v5, v25, v39, v51, v5 == 0);
  }
  if ( !v5 || *(int *)(v5 + 92) > 0 )
  {
    v26 = 0;
    v45 = 0;
    if ( v5 )
    {
      v27 = (_QWORD *)(v5 + 184);
      v28 = (_QWORD *)(v5 + 184);
      while ( 1 )
      {
        v28 = (_QWORD *)*v28;
        if ( v28 == v27 )
          break;
        v26 = v28 - 14;
        if ( *((_WORD *)v28 - 56) != 0xEBAA )
          goto LABEL_107;
      }
      v26 = 0;
LABEL_107:
      v45 = v26;
      while ( v26 )
      {
        v29 = v26 + 14;
        while ( 1 )
        {
          v29 = (_QWORD *)*v29;
          if ( v29 == v27 )
            break;
          v30 = v29 - 14;
          if ( *((_WORD *)v29 - 56) != 0xEBAA )
            goto LABEL_113;
        }
        v30 = 0;
LABEL_113:
        if ( (v26[9] & 2) == 0 )
        {
          if ( *(_WORD *)v26 != 0xEBAA )
            goto LABEL_118;
          break;
        }
        v26 = v30;
        v45 = v30;
      }
      __int2c();
    }
LABEL_118:
    RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(v4 + 400), 2u);
    v32 = RxContext;
    if ( RxContext )
    {
      RxContext->pFcb = (PMRX_FCB)v4;
      RxContext->pFobx = (PMRX_FOBX)v26;
      RxContext->pRelevantSrvOpen = (PMRX_SRV_OPEN)v5;
      LODWORD(RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory.pNotificationBuffer) = v39;
      HIDWORD(RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory.pNotificationBuffer) = v51;
      RxContext->Create.NtCreateParameters.DfsContext = *(PVOID *)(a1 + 80);
      v33 = v18 | *(_BYTE *)(&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 1) & 0xFE;
      *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 24) = v33;
      v34 = v33 ^ (v33 ^ (2 * v50)) & 2;
      *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 24) = v34;
      v35 = -v5;
      v34 &= ~4u;
      *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 24) = v34 | (v35 == 0 ? 4 : 0);
      *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 24) = v34 & 0xF7
                                                                                | (v35 == 0 ? 4 : 0)
                                                                                | (8 * v41);
      *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 24) = v34 & 0xE7
                                                                                | (v35 == 0 ? 4 : 0)
                                                                                | (8 * v41) & 0xEF
                                                                                | (v49 != 0 ? 0x10 : 0);
      v36 = *(__int64 (__fastcall **)(struct _RX_CONTEXT *))(*(_QWORD *)(v4 + 392) + 408LL);
      if ( v36 )
        v44 = v36(v32);
      else
        v44 = -1073741822;
      RxDereferenceAndDeleteRxContext_Real(v32);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        48,
        (unsigned int)&WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids,
        v4,
        v4 + 360);
    }
  }
  *(_DWORD *)(v4 + 164) = v51;
  return v44;
}

```

## disassembly

```asm
0x1400511d0  mov     rax, rsp
0x1400511d3  mov     [rax+10h], dl
0x1400511d6  mov     [rax+8], rcx
0x1400511da  push    rbx
0x1400511db  push    rsi
0x1400511dc  push    rdi
0x1400511dd  push    r12
0x1400511df  push    r13
0x1400511e1  push    r15
0x1400511e3  sub     rsp, 0A8h
0x1400511ea  mov     r11, rcx
0x1400511ed  xor     r9d, r9d
0x1400511f0  mov     [rax+20h], r9d
0x1400511f4  mov     rbx, [rcx+28h]
0x1400511f8  mov     [rsp+0D8h+var_58], rbx
0x140051200  mov     r13, [rcx+20h]
0x140051204  xor     cl, cl
0x140051206  mov     [rsp+0D8h+var_70], ecx
0x14005120a  mov     r10d, [r11+10h]
0x14005120e  mov     edi, r10d
0x140051211  and     edi, 1000000h
0x140051217  mov     [rsp+0D8h+var_6C], edi
0x14005121b  mov     eax, [rbx+0A4h]
0x140051221  mov     [rsp+0D8h+var_78], eax
0x140051225  mov     rax, [rbx+188h]
0x14005122c  mov     rax, [rax+128h]
0x140051233  test    rax, rax
0x140051236  jnz     short loc_14005123F
0x140051238  mov     eax, 0C0000002h
0x14005123d  jmp     short loc_14005126E
0x14005123f  lea     r9, [rsp+0D8h+arg_18]
0x140051247  mov     r8, [r11+50h]
0x14005124b  mov     rdx, r13
0x14005124e  mov     rcx, rbx
0x140051251  call    _guard_dispatch_icall
0x140051256  mov     r11, [rsp+0D8h+arg_0]
0x14005125e  mov     r10d, [r11+10h]
0x140051262  mov     r9d, [rsp+0D8h+arg_18]
0x14005126a  mov     ecx, [rsp+0D8h+var_70]
0x14005126e  mov     r15d, 1
0x140051274  cmp     eax, 0C00000E3h
0x140051279  jnz     short loc_140051280
0x14005127b  mov     r12b, r15b
0x14005127e  jmp     short loc_140051293
0x140051280  xor     r12b, r12b
0x140051283  movzx   ecx, cl
0x140051286  cmp     eax, 0C0000128h
0x14005128b  cmovz   ecx, r15d
0x14005128f  mov     [rsp+0D8h+var_70], ecx
0x140051293  shr     r10d, 1Fh
0x140051297  mov     [rsp+0D8h+var_74], r10d
0x14005129c  lea     rax, WPP_GLOBAL_Control
0x1400512a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400512aa  mov     esi, 40h ; '@'
0x1400512af  cmp     rcx, rax
0x1400512b2  jz      short loc_140051307
0x1400512b4  mov     eax, [rcx+2Ch]
0x1400512b7  test    sil, al
0x1400512ba  jz      short loc_140051307
0x1400512bc  cmp     byte ptr [rcx+29h], 2
0x1400512c0  jb      short loc_140051307
0x1400512c2  xor     r8d, r8d
0x1400512c5  test    edi, edi
0x1400512c7  setnz   r8b
0x1400512cb  xor     edx, edx
0x1400512cd  test    r13, r13
0x1400512d0  setz    dl
0x1400512d3  movzx   eax, r10b
0x1400512d7  mov     [rsp+0D8h+var_88], r8d
0x1400512dc  mov     [rsp+0D8h+var_90], edx
0x1400512e0  mov     [rsp+0D8h+var_98], eax
0x1400512e4  mov     [rsp+0D8h+var_A0], r9d
0x1400512e9  mov     eax, [rsp+0D8h+var_78]
0x1400512ed  mov     [rsp+0D8h+var_A8], eax
0x1400512f1  mov     [rsp+0D8h+Context], r13
0x1400512f6  mov     qword ptr [rsp+0D8h+IrpMajorCode], rbx
0x1400512fb  mov     r9, r11
0x1400512fe  mov     rcx, [rcx+18h]
0x140051302  call    WPP_SF_qqqDDddd
0x140051307  test    r13, r13
0x14005130a  jnz     loc_1400513D9
0x140051310  test    edi, edi
0x140051312  jnz     loc_1400513D9
0x140051318  bts     dword ptr [rbx+9Ch], 14h
0x140051320  mov     rdi, [rsp+0D8h+arg_0]
0x140051328  bts     dword ptr [rdi+10h], 18h
0x14005132d  mov     ecx, [rsp+0D8h+arg_18]
0x140051334  mov     eax, ecx
0x140051336  shr     eax, 4
0x140051339  and     eax, 2
0x14005133c  test    cl, 2
0x14005133f  jz      short loc_140051344
0x140051341  or      eax, 4
0x140051344  mov     edx, eax
0x140051346  or      edx, r15d
0x140051349  test    byte ptr [rsp+0D8h+arg_18], r15b
0x140051351  cmovz   edx, eax
0x140051354  lea     rcx, [rbx+58h]
0x140051358  mov     dword ptr [rsp+0D8h+Context], 0
0x140051360  mov     qword ptr [rsp+0D8h+IrpMajorCode], 0
0x140051369  lea     r9, RxUpperOplockBreakComplete
0x140051370  mov     r8, rdi
0x140051373  call    cs:__imp_FsRtlCheckUpperOplock
0x14005137a  nop     dword ptr [rax+rax+00h]
0x14005137f  cmp     eax, 103h
0x140051384  jnz     short loc_1400513E1
0x140051386  mov     rcx, cs:WPP_GLOBAL_Control
0x14005138d  lea     rax, WPP_GLOBAL_Control
0x140051394  cmp     rcx, rax
0x140051397  jz      short loc_1400513C2
0x140051399  mov     edx, [rcx+2Ch]
0x14005139c  test    sil, dl
0x14005139f  jz      short loc_1400513C2
0x1400513a1  cmp     byte ptr [rcx+29h], 2
0x1400513a5  jb      short loc_1400513C2
0x1400513a7  mov     edx, 26h ; '&'
0x1400513ac  mov     r9d, 103h
0x1400513b2  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x1400513b9  mov     rcx, [rcx+18h]
0x1400513bd  call    WPP_SF_d
0x1400513c2  mov     eax, 103h
0x1400513c7  add     rsp, 0A8h
0x1400513ce  pop     r15
0x1400513d0  pop     r13
0x1400513d2  pop     r12
0x1400513d4  pop     rdi
0x1400513d5  pop     rsi
0x1400513d6  pop     rbx
0x1400513d7  retn
0x1400513d9  mov     rdi, [rsp+0D8h+arg_0]
0x1400513e1  mov     [rsp+0D8h+arg_10], 0
0x1400513e9  btr     dword ptr [rbx+9Ch], 14h
0x1400513f1  btr     dword ptr [rdi+10h], 18h
0x1400513f6  mov     [rsp+0D8h+var_64], 0
0x1400513fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140051405  lea     rax, WPP_GLOBAL_Control
0x14005140c  cmp     rcx, rax
0x14005140f  jz      short loc_140051450
0x140051411  mov     eax, [rcx+2Ch]
0x140051414  test    sil, al
0x140051417  jz      short loc_140051450
0x140051419  cmp     byte ptr [rcx+29h], 2
0x14005141d  jb      short loc_140051450
0x14005141f  movzx   eax, r12b
0x140051423  mov     [rsp+0D8h+var_98], eax
0x140051427  mov     eax, [rsp+0D8h+arg_18]
0x14005142e  mov     [rsp+0D8h+var_A0], eax
0x140051432  mov     eax, [rsp+0D8h+var_78]
0x140051436  mov     [rsp+0D8h+var_A8], eax
0x14005143a  mov     [rsp+0D8h+Context], r13; Context
0x14005143f  mov     qword ptr [rsp+0D8h+IrpMajorCode], rbx
0x140051444  mov     r9, rdi
0x140051447  mov     rcx, [rcx+18h]
0x14005144b  call    WPP_SF_qqqDDd
0x140051450  test    r12b, r12b
0x140051453  jnz     short loc_140051475
0x140051455  cmp     byte ptr [rsp+0D8h+var_70], r12b
0x14005145a  jnz     short loc_140051475
0x14005145c  test    byte ptr [rsp+0D8h+var_78], 2
0x140051461  jz      loc_14005150E
0x140051467  test    byte ptr [rsp+0D8h+arg_18], 2
0x14005146f  jnz     loc_14005150E
0x140051475  xor     r9d, r9d
0x140051478  xor     r8d, r8d
0x14005147b  mov     dl, r15b
0x14005147e  mov     rcx, rbx
0x140051481  call    RxFlushFcbInSystemCacheEx
0x140051486  mov     edi, eax
0x140051488  test    eax, eax
0x14005148a  jns     short loc_1400514D5
0x14005148c  mov     rcx, cs:WPP_GLOBAL_Control
0x140051493  lea     rax, WPP_GLOBAL_Control
0x14005149a  cmp     rcx, rax
0x14005149d  jz      short loc_1400514C9
0x14005149f  mov     edx, [rcx+2Ch]
0x1400514a2  test    r15b, dl
0x1400514a5  jz      short loc_1400514C9
0x1400514a7  cmp     [rcx+29h], r15b
0x1400514ab  jb      short loc_1400514C9
0x1400514ad  mov     edx, 28h ; '('
0x1400514b2  mov     dword ptr [rsp+0D8h+IrpMajorCode], edi; IrpMajorCode
0x1400514b6  mov     r9, rbx
0x1400514b9  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x1400514c0  mov     rcx, [rcx+18h]
0x1400514c4  call    WPP_SF_qD
0x1400514c9  mov     edx, edi; FileName
0x1400514cb  mov     rcx, rbx; DeviceObject
0x1400514ce  call    RxCcLogError
0x1400514d3  jmp     short loc_14005150E
0x1400514d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400514dc  lea     rax, WPP_GLOBAL_Control
0x1400514e3  cmp     rcx, rax
0x1400514e6  jz      short loc_14005150E
0x1400514e8  mov     eax, [rcx+2Ch]
0x1400514eb  test    sil, al
0x1400514ee  jz      short loc_14005150E
0x1400514f0  cmp     byte ptr [rcx+29h], 2
0x1400514f4  jb      short loc_14005150E
0x1400514f6  mov     edx, 29h ; ')'
0x1400514fb  mov     r9, rbx
0x1400514fe  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x140051505  mov     rcx, [rcx+18h]
0x140051509  call    WPP_SF_q
0x14005150e  mov     edi, [rsp+0D8h+var_78]
0x140051512  test    r12b, r12b
0x140051515  jnz     short loc_140051539
0x140051517  xor     r12d, r12d
0x14005151a  cmp     byte ptr [rsp+0D8h+var_70], r12b
0x14005151f  jnz     short loc_14005153C
0x140051521  test    r15b, dil
0x140051524  jz      loc_1400515F9
0x14005152a  test    byte ptr [rsp+0D8h+arg_18], r15b
0x140051532  jz      short loc_14005153C
0x140051534  jmp     loc_1400515F9
0x140051539  xor     r12d, r12d
0x14005153c  xorps   xmm0, xmm0
0x14005153f  movups  xmmword ptr [rsp+0D8h+IoStatus], xmm0
0x140051547  mov     r8b, r15b
0x14005154a  mov     rdx, rbx
0x14005154d  xor     ecx, ecx
0x14005154f  call    RxAcquirePagingIoResource
0x140051554  mov     eax, dword ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4
0x14005155a  test    al, 8
0x14005155c  jz      short loc_140051570
0x14005155e  mov     r9, rbx
0x140051561  xor     r8d, r8d
0x140051564  lea     rdx, CcPurgeRequest
0x14005156b  call    McTemplateK0p_EtwWriteTransfer
0x140051570  mov     rcx, [rbx+130h]
0x140051577  add     rcx, 8; SectionObjectPointer
0x14005157b  mov     dword ptr [rsp+0D8h+IrpMajorCode], r12d; Flags
0x140051580  lea     r9, [rsp+0D8h+IoStatus]; IoStatus
0x140051588  or      r8d, 0FFFFFFFFh; Length
0x14005158c  xor     edx, edx; FileOffset
0x14005158e  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x140051595  nop     dword ptr [rax+rax+00h]
0x14005159a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400515a1  lea     rax, WPP_GLOBAL_Control
0x1400515a8  cmp     rcx, rax
0x1400515ab  jz      short loc_1400515D3
0x1400515ad  mov     eax, [rcx+2Ch]
0x1400515b0  test    sil, al
0x1400515b3  jz      short loc_1400515D3
0x1400515b5  cmp     byte ptr [rcx+29h], 2
0x1400515b9  jb      short loc_1400515D3
0x1400515bb  mov     edx, 2Ah ; '*'
0x1400515c0  mov     r9, rbx
0x1400515c3  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x1400515ca  mov     rcx, [rcx+18h]
0x1400515ce  call    WPP_SF_q
0x1400515d3  mov     eax, dword ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4
0x1400515d9  test    al, 8
0x1400515db  jz      short loc_1400515EF
0x1400515dd  mov     r9, rbx
0x1400515e0  xor     r8d, r8d
0x1400515e3  lea     rdx, CcPurgeCompletion
0x1400515ea  call    McTemplateK0p_EtwWriteTransfer
0x1400515ef  mov     rdx, rbx
0x1400515f2  xor     ecx, ecx
0x1400515f4  call    RxReleasePagingIoResource
0x1400515f9  test    dil, 10h
0x1400515fd  jnz     short loc_140051605
0x1400515ff  test    dil, 20h
0x140051603  jz      short loc_14005165D
0x140051605  mov     eax, [rsp+0D8h+arg_18]
0x14005160c  test    al, 10h
0x14005160e  jnz     short loc_14005165D
0x140051610  test    al, 20h
0x140051612  jnz     short loc_14005165D
0x140051614  xor     r9d, r9d
0x140051617  xor     r8d, r8d
0x14005161a  xor     edx, edx
0x14005161c  mov     rcx, rbx; BugCheckParameter2
0x14005161f  call    RxPurgeConflictingSrvOpensEx
0x140051624  mov     rcx, cs:WPP_GLOBAL_Control
0x14005162b  lea     rax, WPP_GLOBAL_Control
0x140051632  cmp     rcx, rax
0x140051635  jz      short loc_14005165D
0x140051637  mov     eax, [rcx+2Ch]
0x14005163a  test    sil, al
0x14005163d  jz      short loc_14005165D
0x14005163f  cmp     byte ptr [rcx+29h], 2
0x140051643  jb      short loc_14005165D
0x140051645  mov     edx, 2Bh ; '+'
0x14005164a  mov     r9, rbx
0x14005164d  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x140051654  mov     rcx, [rcx+18h]
0x140051658  call    WPP_SF_q
0x14005165d  cmp     [rsp+0D8h+var_6C], r12d
0x140051662  jz      loc_140051718
0x140051668  cmp     [rbx+0B8h], r12d
0x14005166f  jnz     short loc_1400516E7
0x140051671  cmp     [rbx+0C0h], r15d
0x140051678  jnz     short loc_1400516E7
0x14005167a  mov     [rsp+0D8h+var_6C], r12d
0x14005167f  mov     rcx, [rbx+130h]
0x140051686  add     rcx, 8
0x14005168a  lea     r8, [rsp+0D8h+var_6C]
0x14005168f  mov     edx, 7
0x140051694  call    cs:__imp_MmIsFileSectionActive
  ... truncated ...
```
