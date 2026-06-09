# RxLowIoWriteShellCompletion

- ea: `0x14000b350`
- end: `0x14000b7d5`
- name: `RxLowIoWriteShellCompletion`
- size: `1157`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x14000b350`
- `0x140011440`
- `0x140016e20`
- `0x140016fc0`
- `0x140017a8c`
- `0x14001810c`
- `0x14001dd20`
- `0x14001e3b0`
- `0x14001e478`
- `0x140065690`
- `0x140071ee0`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000b784`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000b784`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b3db`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b442`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b3db`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b442`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000b4bc`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000b691`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000b4bc`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000b691`

## pseudocode

```c
__int64 __fastcall RxLowIoWriteShellCompletion(PRX_CONTEXT RxContext, __int64 a2, __int64 a3)
{
  int v3; // r15d
  PMRX_FOBX pFobx; // r12
  PIRP CurrentIrp; // rsi
  char v7; // r14
  PMRX_FCB pFcb; // r13
  unsigned int StoredStatus; // edi
  int v10; // ebp
  PIRP v11; // r9
  ULONG v12; // r8d
  wchar_t *Buffer; // r10
  ULONG v14; // edx
  PMRX_FCB v15; // r11
  PFILE_OBJECT FileObject; // rcx
  int v17; // r15d
  KIRQL CurrentIrql; // al
  char v19; // cl
  ERESOURCE_THREAD *v20; // rbp
  ERESOURCE_THREAD v21; // r12
  int v22; // ebp
  PDEVICE_OBJECT v23; // rcx
  __int64 v25; // rdx
  ERESOURCE_THREAD v26; // rbp
  char *v27; // r10
  LARGE_INTEGER FileSize; // r8
  LARGE_INTEGER v29; // [rsp+20h] [rbp-48h]
  char *v30; // [rsp+28h] [rbp-40h]
  struct _MRX_FOBX_ *v31; // [rsp+70h] [rbp+8h]
  __int64 v32; // [rsp+70h] [rbp+8h]

  v3 = *((_DWORD *)&RxContext->9 + 28);
  pFobx = RxContext->pFobx;
  CurrentIrp = RxContext->CurrentIrp;
  v7 = v3 & 1;
  pFcb = RxContext->pFcb;
  StoredStatus = RxContext->StoredStatus;
  v31 = pFobx;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqLL(
      WPP_GLOBAL_Control->AttachedDevice,
      &WPP_GLOBAL_Control,
      a3,
      RxContext,
      CurrentIrp,
      StoredStatus,
      RxContext->IoStatusBlock.Information);
  }
  if ( !CurrentIrp )
    goto LABEL_13;
  v10 = CurrentIrp->Flags & 2;
  CurrentIrp->IoStatus.Information = RxContext->InformationToReturn;
  if ( StoredStatus && v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      LODWORD(v30) = StoredStatus;
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        57,
        &WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids,
        pFcb,
        *(_QWORD *)&pFcb->UncleanCount,
        v30);
    }
    if ( dbgBreakOnPagingWriteError
      && (StoredStatus == dbgPagingWriteStatus || !dbgPagingWriteStatus)
      && StoredStatus != -1073741740 )
    {
      __debugbreak();
    }
    ++LODWORD(pFcb[2].SrvOpenList.Flink);
    _InterlockedIncrement(&LDWCount);
    WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink = (struct _LIST_ENTRY *)MEMORY[0xFFFFF78000000014];
  }
  if ( (*((_BYTE *)&RxContext->9 + 122) & 1) != 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      return StoredStatus;
    }
    v25 = 58;
    goto LABEL_73;
  }
  if ( !KeGetCurrentIrql() )
  {
    if ( (StoredStatus & 0x80000000) != 0 )
    {
LABEL_13:
      v17 = v3 & 2;
      CurrentIrql = KeGetCurrentIrql();
      v19 = *((_BYTE *)&RxContext->9 + 177);
      v20 = (ERESOURCE_THREAD *)((char *)&RxContext->9 + 184);
      if ( CurrentIrql >= 2u )
      {
        if ( v19 )
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))RxReleasePagingIoResourceForThreadAtDpc)(
            RxContext,
            pFcb,
            *((_QWORD *)&RxContext->9 + 19),
            *v20,
            (LARGE_INTEGER)v29.QuadPart,
            v30);
        if ( *((_BYTE *)&RxContext->9 + 176) )
        {
          v26 = *v20;
          v32 = *((_QWORD *)&RxContext->9 + 19);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 43, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids);
          }
          LOBYTE(RxContext->Flags) = 0;
          ExReleaseResourceForThreadLite((PERESOURCE)(v32 + 32), v26);
        }
      }
      else
      {
        if ( v19 )
          RxReleasePagingIoResourceForThread(RxContext, pFcb, *v20);
        if ( *((_BYTE *)&RxContext->9 + 176) )
        {
          v21 = *v20;
          v22 = *(_DWORD *)(*(_QWORD *)&pFcb[1].OpenCount + 296LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids);
          }
          if ( v22
            && ExIsResourceAcquiredExclusiveLite(pFcb->Header.Resource)
            && (unsigned __int8)RxIsSafeToProcessBufferingStateChange(RxContext, pFcb) )
          {
            RxProcessFcbChangeBufferingStateRequestInternal(pFcb);
          }
          LOBYTE(RxContext->Flags) = 0;
          ExReleaseResourceForThreadLite(pFcb->Header.Resource, v21);
          pFobx = v31;
        }
      }
      if ( v17 )
        RxResumeBlockedOperations_Serially(RxContext, (PLIST_ENTRY)&pFobx[3].AssociatedFileObject);
      if ( v7 && CurrentIrp->IoStatus.Information )
      {
        *(_DWORD *)&pFobx[2].UnicodeQueryTemplate.Length = 0;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return StoredStatus;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_qqqL(
            WPP_GLOBAL_Control->AttachedDevice,
            59,
            &WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids,
            RxContext,
            pFobx,
            &pFobx[2].Flags,
            pFobx[2].OffsetOfNextEaToReturn);
      }
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        return StoredStatus;
      }
      v25 = 60;
LABEL_73:
      WPP_SF_d(v23->AttachedDevice, v25, &WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids, StoredStatus);
      return StoredStatus;
    }
LABEL_7:
    if ( !v7 )
    {
      v11 = RxContext->CurrentIrp;
      v12 = RxContext->Create.PipeCompletionMode & 4;
      Buffer = RxContext->Create.TransportName.Buffer;
      v14 = RxContext->Create.PipeCompletionMode & 2;
      v15 = RxContext->pFcb;
      FileObject = v11->Tail.Overlay.CurrentStackLocation->FileObject;
      if ( !v10 )
        FileObject->Flags |= 0x1000u;
      if ( v14 )
        FileObject->Flags |= 0x2000u;
      if ( v12 )
      {
        v27 = (char *)Buffer + v11->IoStatus.Information;
        FileSize = v15->Header.FileSize;
        if ( FileSize.QuadPart >= (__int64)v27 )
          FileSize.QuadPart = (LONGLONG)v27;
        v15->Header.ValidDataLength = FileSize;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v30 = v27;
          v29 = FileSize;
          WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids);
        }
      }
    }
    goto LABEL_13;
  }
  if ( (StoredStatus & 0x80000000) == 0 )
    goto LABEL_7;
  return 3225485315LL;
}

```

## disassembly

```asm
0x14000b350  mov     [rsp+arg_10], rbx
0x14000b355  mov     [rsp+arg_18], rsi
0x14000b35a  push    rdi
0x14000b35b  push    r12
0x14000b35d  push    r13
0x14000b35f  push    r14
0x14000b361  push    r15
0x14000b363  sub     rsp, 40h
0x14000b367  mov     r15d, [rcx+200h]
0x14000b36e  mov     rbx, rcx
0x14000b371  mov     r12, [rcx+40h]
0x14000b375  movzx   r14d, r15b
0x14000b379  mov     rsi, [rcx+28h]
0x14000b37d  and     r14b, 1
0x14000b381  mov     r13, [rcx+38h]
0x14000b385  mov     edi, [rcx+0B0h]
0x14000b38b  mov     [rsp+68h+arg_0], r12
0x14000b390  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b397  lea     rdx, WPP_GLOBAL_Control
0x14000b39e  cmp     rcx, rdx
0x14000b3a1  jnz     loc_14000B553
0x14000b3a7  mov     [rsp+68h+arg_8], rbp
0x14000b3ac  test    rsi, rsi
0x14000b3af  jz      loc_14000B43E
0x14000b3b5  mov     ebp, [rsi+10h]
0x14000b3b8  mov     rax, [rbx+0B8h]
0x14000b3bf  and     ebp, 2
0x14000b3c2  mov     [rsi+38h], rax
0x14000b3c6  test    edi, edi
0x14000b3c8  jnz     loc_140027574
0x14000b3ce  test    byte ptr [rbx+20Ah], 1
0x14000b3d5  jnz     loc_14000B524
0x14000b3db  call    cs:__imp_KeGetCurrentIrql
0x14000b3e2  nop     dword ptr [rax+rax+00h]
0x14000b3e7  test    al, al
0x14000b3e9  jnz     loc_14000B593
0x14000b3ef  test    edi, edi
0x14000b3f1  js      short loc_14000B43E
0x14000b3f3  test    r14b, r14b
0x14000b3f6  jnz     short loc_14000B43E
0x14000b3f8  mov     edx, [rbx+218h]
0x14000b3fe  mov     r8d, edx
0x14000b401  mov     r9, [rbx+28h]
0x14000b405  and     r8d, 4
0x14000b409  mov     r10, [rbx+230h]
0x14000b410  and     edx, 2
0x14000b413  mov     r11, [rbx+38h]
0x14000b417  mov     rax, [r9+0B8h]
0x14000b41e  mov     rcx, [rax+30h]
0x14000b422  test    ebp, ebp
0x14000b424  jnz     short loc_14000B42D
0x14000b426  or      dword ptr [rcx+50h], 1000h
0x14000b42d  test    edx, edx
0x14000b42f  jnz     loc_14000B547
0x14000b435  test    r8d, r8d
0x14000b438  jnz     loc_14000B6D5
0x14000b43e  and     r15d, 2
0x14000b442  call    cs:__imp_KeGetCurrentIrql
0x14000b449  nop     dword ptr [rax+rax+00h]
0x14000b44e  movzx   ecx, byte ptr [rbx+241h]
0x14000b455  lea     rbp, [rbx+248h]
0x14000b45c  cmp     al, 2
0x14000b45e  jnb     loc_14000B643
0x14000b464  test    cl, cl
0x14000b466  jnz     loc_14000B73B
0x14000b46c  cmp     byte ptr [rbx+240h], 0
0x14000b473  jz      short loc_14000B4CD
0x14000b475  mov     rax, [r13+130h]
0x14000b47c  mov     r12, [rbp+0]
0x14000b480  mov     ebp, [rax+128h]
0x14000b486  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b48d  lea     rax, WPP_GLOBAL_Control
0x14000b494  cmp     rcx, rax
0x14000b497  jz      short loc_14000B4A6
0x14000b499  test    dword ptr [rcx+2Ch], 100h
0x14000b4a0  jnz     loc_14000B74F
0x14000b4a6  test    ebp, ebp
0x14000b4a8  jnz     loc_14000B780
0x14000b4ae  mov     byte ptr [rbx+0A8h], 0
0x14000b4b5  mov     rdx, r12; ResourceThreadId
0x14000b4b8  mov     rcx, [r13+8]; Resource
0x14000b4bc  call    cs:__imp_ExReleaseResourceForThreadLite
0x14000b4c3  nop     dword ptr [rax+rax+00h]
0x14000b4c8  mov     r12, [rsp+68h+arg_0]
0x14000b4cd  test    r15d, r15d
0x14000b4d0  jz      short loc_14000B4E2
0x14000b4d2  lea     rdx, [r12+0E8h]; BlockingIoQ
0x14000b4da  mov     rcx, rbx; RxContext
0x14000b4dd  call    RxResumeBlockedOperations_Serially
0x14000b4e2  test    r14b, r14b
0x14000b4e5  jnz     loc_14000B5C5
0x14000b4eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4f2  lea     rax, WPP_GLOBAL_Control
0x14000b4f9  cmp     rcx, rax
0x14000b4fc  jnz     loc_14000B5A5
0x14000b502  mov     eax, edi
0x14000b504  mov     rbp, [rsp+68h+arg_8]
0x14000b509  lea     r11, [rsp+68h+var_28]
0x14000b50e  mov     rbx, [r11+40h]
0x14000b512  mov     rsi, [r11+48h]
0x14000b516  mov     rsp, r11
0x14000b519  pop     r15
0x14000b51b  pop     r14
0x14000b51d  pop     r13
0x14000b51f  pop     r12
0x14000b521  pop     rdi
0x14000b522  retn
0x14000b524  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b52b  cmp     rcx, rdx
0x14000b52e  jz      short loc_14000B502
0x14000b530  mov     eax, [rcx+2Ch]
0x14000b533  test    al, 10h
0x14000b535  jz      short loc_14000B502
0x14000b537  cmp     byte ptr [rcx+29h], 4
0x14000b53b  jb      short loc_14000B502
0x14000b53d  mov     edx, 3Ah ; ':'
0x14000b542  jmp     loc_140027610
0x14000b547  or      dword ptr [rcx+50h], 2000h
0x14000b54e  jmp     loc_14000B435
0x14000b553  mov     eax, [rcx+2Ch]
0x14000b556  test    al, 10h
0x14000b558  jz      loc_14000B3A7
0x14000b55e  cmp     byte ptr [rcx+29h], 2
0x14000b562  jb      loc_14000B3A7
0x14000b568  mov     eax, [rbx+0B8h]
0x14000b56e  mov     r9, rbx
0x14000b571  mov     rcx, [rcx+18h]
0x14000b575  mov     [rsp+68h+var_38], eax
0x14000b579  mov     dword ptr [rsp+68h+var_40], edi
0x14000b57d  mov     [rsp+68h+var_48], rsi
0x14000b582  call    WPP_SF_qqLL
0x14000b587  lea     rdx, WPP_GLOBAL_Control
0x14000b58e  jmp     loc_14000B3A7
0x14000b593  test    edi, edi
0x14000b595  jns     loc_14000B3F3
0x14000b59b  mov     eax, 0C0410003h
0x14000b5a0  jmp     loc_14000B504
0x14000b5a5  mov     edx, [rcx+2Ch]
0x14000b5a8  test    dl, 10h
0x14000b5ab  jz      loc_14000B502
0x14000b5b1  cmp     byte ptr [rcx+29h], 4
0x14000b5b5  jb      loc_14000B502
0x14000b5bb  mov     edx, 3Ch ; '<'
0x14000b5c0  jmp     loc_140027610
0x14000b5c5  cmp     qword ptr [rsi+38h], 0
0x14000b5ca  jz      loc_14000B4EB
0x14000b5d0  mov     dword ptr [r12+0C0h], 0
0x14000b5dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b5e3  lea     rax, WPP_GLOBAL_Control
0x14000b5ea  cmp     rcx, rax
0x14000b5ed  jz      loc_14000B502
0x14000b5f3  mov     eax, [rcx+2Ch]
0x14000b5f6  test    al, 10h
0x14000b5f8  jz      loc_14000B4EB
0x14000b5fe  cmp     byte ptr [rcx+29h], 2
0x14000b602  jb      loc_14000B4EB
0x14000b608  mov     eax, [r12+0D0h]
0x14000b610  lea     r8, [r12+0B8h]
0x14000b618  mov     rcx, [rcx+18h]
0x14000b61c  mov     edx, 3Bh ; ';'
0x14000b621  mov     [rsp+68h+var_38], eax
0x14000b625  mov     r9, rbx
0x14000b628  mov     [rsp+68h+var_40], r8
0x14000b62d  lea     r8, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids
0x14000b634  mov     [rsp+68h+var_48], r12
0x14000b639  call    WPP_SF_qqqL
0x14000b63e  jmp     loc_14000B4EB
0x14000b643  test    cl, cl
0x14000b645  jnz     loc_14000B7BA
0x14000b64b  cmp     byte ptr [rbx+240h], 0
0x14000b652  lea     rax, [rbx+228h]
0x14000b659  jz      loc_14000B4CD
0x14000b65f  mov     rcx, [rax]
0x14000b662  mov     rbp, [rbp+0]
0x14000b666  mov     [rsp+68h+arg_0], rcx
0x14000b66b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b672  lea     rax, WPP_GLOBAL_Control
0x14000b679  cmp     rcx, rax
0x14000b67c  jnz     short loc_14000B6A2
0x14000b67e  mov     rcx, [rsp+68h+arg_0]
0x14000b683  mov     rdx, rbp; ResourceThreadId
0x14000b686  add     rcx, 20h ; ' '; Resource
0x14000b68a  mov     byte ptr [rbx+0A8h], 0
0x14000b691  call    cs:__imp_ExReleaseResourceForThreadLite
0x14000b698  nop     dword ptr [rax+rax+00h]
0x14000b69d  jmp     loc_14000B4CD
0x14000b6a2  test    dword ptr [rcx+2Ch], 100h
0x14000b6a9  jz      short loc_14000B67E
0x14000b6ab  cmp     byte ptr [rcx+29h], 4
0x14000b6af  jb      short loc_14000B67E
0x14000b6b1  mov     rcx, [rcx+18h]
0x14000b6b5  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14000b6bc  mov     edx, 2Bh ; '+'
0x14000b6c1  mov     [rsp+68h+var_40], rbp
0x14000b6c6  mov     r9, rbx
0x14000b6c9  mov     [rsp+68h+var_48], r13
0x14000b6ce  call    WPP_SF_qqq
0x14000b6d3  jmp     short loc_14000B67E
0x14000b6d5  add     r10, [r9+38h]
0x14000b6d9  mov     r9, [r11+20h]
0x14000b6dd  cmp     r9, r10
0x14000b6e0  lea     rax, WPP_GLOBAL_Control
0x14000b6e7  mov     r8, r9
0x14000b6ea  cmovge  r8, r10
0x14000b6ee  mov     [r11+28h], r8
0x14000b6f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6f9  cmp     rcx, rax
0x14000b6fc  jz      loc_14000B43E
0x14000b702  mov     eax, [rcx+2Ch]
0x14000b705  test    al, 10h
0x14000b707  jz      loc_14000B43E
0x14000b70d  cmp     byte ptr [rcx+29h], 2
0x14000b711  jb      loc_14000B43E
0x14000b717  mov     rcx, [rcx+18h]
0x14000b71b  mov     edx, 0Eh
0x14000b720  mov     [rsp+68h+var_40], r10
0x14000b725  mov     [rsp+68h+var_48], r8
0x14000b72a  lea     r8, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids
0x14000b731  call    WPP_SF_qqq
0x14000b736  jmp     loc_14000B43E
0x14000b73b  mov     r8, [rbp+0]
0x14000b73f  mov     rdx, r13
0x14000b742  mov     rcx, rbx
0x14000b745  call    RxReleasePagingIoResourceForThread
0x14000b74a  jmp     loc_14000B46C
0x14000b74f  cmp     byte ptr [rcx+29h], 4
0x14000b753  jb      loc_14000B4A6
0x14000b759  mov     rcx, [rcx+18h]
0x14000b75d  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14000b764  mov     edx, 0Eh
0x14000b769  mov     [rsp+68h+var_40], r12
0x14000b76e  mov     r9, rbx
0x14000b771  mov     [rsp+68h+var_48], r13
0x14000b776  call    WPP_SF_qqq
0x14000b77b  jmp     loc_14000B4A6
0x14000b780  mov     rcx, [r13+8]; Resource
0x14000b784  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14000b78b  nop     dword ptr [rax+rax+00h]
0x14000b790  test    al, al
0x14000b792  jz      loc_14000B4AE
0x14000b798  mov     rdx, r13
0x14000b79b  mov     rcx, rbx
0x14000b79e  call    RxIsSafeToProcessBufferingStateChange
0x14000b7a3  test    al, al
0x14000b7a5  jz      loc_14000B4AE
0x14000b7ab  xor     edx, edx
0x14000b7ad  mov     rcx, r13; Instance
0x14000b7b0  call    RxProcessFcbChangeBufferingStateRequestInternal
0x14000b7b5  jmp     loc_14000B4AE
0x14000b7ba  mov     r9, [rbp+0]
0x14000b7be  mov     rdx, r13
0x14000b7c1  mov     r8, [rbx+228h]
0x14000b7c8  mov     rcx, rbx
0x14000b7cb  call    RxReleasePagingIoResourceForThreadAtDpc
0x14000b7d0  jmp     loc_14000B64B
0x140027574  test    ebp, ebp
0x140027576  jz      loc_14000B3CE
0x14002757c  mov     rcx, cs:WPP_GLOBAL_Control
0x140027583  cmp     rcx, rdx
0x140027586  jz      short loc_1400275C1
0x140027588  mov     eax, [rcx+2Ch]
0x14002758b  test    al, 10h
0x14002758d  jz      short loc_1400275C1
0x14002758f  cmp     byte ptr [rcx+29h], 2
0x140027593  jb      short loc_1400275C1
0x140027595  mov     rax, [r13+78h]
0x140027599  lea     r8, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids
0x1400275a0  mov     rcx, [rcx+18h]
0x1400275a4  mov     edx, 39h ; '9'
0x1400275a9  mov     dword ptr [rsp+68h+var_40], edi
0x1400275ad  mov     r9, r13
0x1400275b0  mov     [rsp+68h+var_48], rax
0x1400275b5  call    WPP_SF_qqD
0x1400275ba  lea     rdx, WPP_GLOBAL_Control
0x1400275c1  movzx   eax, cs:dbgBreakOnPagingWriteError
0x1400275c8  test    al, al
0x1400275ca  jz      short loc_1400275E9
0x1400275cc  mov     eax, cs:dbgPagingWriteStatus
0x1400275d2  cmp     edi, eax
0x1400275d4  jz      short loc_1400275E0
0x1400275d6  mov     eax, cs:dbgPagingWriteStatus
0x1400275dc  test    eax, eax
0x1400275de  jnz     short loc_1400275E9
0x1400275e0  cmp     edi, 0C0000054h
0x1400275e6  jz      short loc_1400275E9
0x1400275e8  int     3; Trap to Debugger
0x1400275e9  inc     dword ptr [r13+1F8h]
0x1400275f0  lock inc cs:LDWCount
0x1400275f7  mov     rax, 0FFFFF78000000014h
0x140027601  mov     rax, [rax]
0x140027604  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, rax
0x14002760b  jmp     loc_14000B3CE
0x140027610  mov     rcx, [rcx+18h]
0x140027614  lea     r8, WPP_40322347dcd53e0bf93cb1041cae84c9_Traceguids
0x14002761b  mov     r9d, edi
0x14002761e  call    WPP_SF_d
0x140027623  nop
0x140027624  jmp     loc_14000B502
```
