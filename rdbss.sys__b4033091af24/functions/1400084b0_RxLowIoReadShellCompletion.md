# RxLowIoReadShellCompletion

- ea: `0x1400084b0`
- end: `0x1400088fd`
- name: `RxLowIoReadShellCompletion`
- size: `1101`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1400084b0`
- `0x140016e20`
- `0x140016e70`
- `0x140016fc0`
- `0x1400178e8`
- `0x14001810c`
- `0x14001d5e8`
- `0x14001e3b0`
- `0x14001e478`
- `0x140065690`
- `0x140071ee0`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400088b0`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400088b0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008543`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008563`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008543`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008563`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400085ba`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140008615`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400085ba`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140008615`

## pseudocode

```c
__int64 __fastcall RxLowIoReadShellCompletion(PRX_CONTEXT RxContext)
{
  int v1; // edi
  PIRP CurrentIrp; // r13
  char v4; // si
  PMRX_FCB pFcb; // r14
  NTSTATUS StoredStatus; // r12d
  ULONG Flags; // ebp
  PFILE_OBJECT FileObject; // r15
  ULONG_PTR InformationToReturn; // rax
  int v10; // ebp
  int v11; // edi
  KIRQL CurrentIrql; // al
  char v13; // cl
  ERESOURCE_THREAD *v14; // r15
  ERESOURCE_THREAD v15; // rbp
  ERESOURCE_THREAD v16; // r15
  int v17; // ebp
  struct _ERESOURCE *Resource; // rcx
  PDEVICE_OBJECT v19; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rbp
  __int64 v23; // rbp
  PIRP v24; // [rsp+20h] [rbp-48h]
  NTSTATUS v25; // [rsp+28h] [rbp-40h]
  PMRX_FOBX pFobx; // [rsp+70h] [rbp+8h]

  v1 = *((_DWORD *)&RxContext->9 + 28);
  CurrentIrp = RxContext->CurrentIrp;
  v4 = v1 & 1;
  pFcb = RxContext->pFcb;
  StoredStatus = RxContext->StoredStatus;
  pFobx = RxContext->pFobx;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v25 = RxContext->StoredStatus;
    v24 = RxContext->CurrentIrp;
    WPP_SF_qqDD(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids, RxContext);
  }
  if ( !CurrentIrp )
  {
LABEL_7:
    v11 = v1 & 2;
    CurrentIrql = KeGetCurrentIrql();
    v13 = *((_BYTE *)&RxContext->9 + 177);
    v14 = (ERESOURCE_THREAD *)((char *)&RxContext->9 + 184);
    if ( CurrentIrql >= 2u )
    {
      v22 = (_QWORD *)((char *)&RxContext->9 + 152);
      if ( v13 )
        RxReleasePagingIoResourceForThreadAtDpc(RxContext, pFcb, *v22, *v14, v24, v25);
      if ( !*((_BYTE *)&RxContext->9 + 176) )
        goto LABEL_18;
      v16 = *v14;
      v23 = *v22;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          43,
          WPP_16f2bee2656c381c8186d78b34bda825_Traceguids,
          RxContext,
          pFcb,
          v16);
      }
      LOBYTE(RxContext->Flags) = 0;
      Resource = (struct _ERESOURCE *)(v23 + 32);
    }
    else
    {
      if ( v13 )
      {
        v15 = *v14;
        BYTE1(RxContext->Flags) = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v15);
        }
        ExReleaseResourceForThreadLite(pFcb->Header.PagingIoResource, v15);
      }
      if ( !*((_BYTE *)&RxContext->9 + 176) )
        goto LABEL_18;
      v16 = *v14;
      v17 = *(_DWORD *)(*(_QWORD *)&pFcb[1].OpenCount + 296LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_16f2bee2656c381c8186d78b34bda825_Traceguids,
          RxContext,
          pFcb,
          v16);
      }
      if ( v17
        && ExIsResourceAcquiredExclusiveLite(pFcb->Header.Resource)
        && (unsigned __int8)RxIsSafeToProcessBufferingStateChange(RxContext, pFcb) )
      {
        RxProcessFcbChangeBufferingStateRequestInternal(pFcb);
      }
      LOBYTE(RxContext->Flags) = 0;
      Resource = pFcb->Header.Resource;
    }
    ExReleaseResourceForThreadLite(Resource, v16);
LABEL_18:
    if ( v11 )
      RxResumeBlockedOperations_Serially(RxContext, (PLIST_ENTRY)&pFobx[3]);
    if ( v4 )
    {
      if ( CurrentIrp->IoStatus.Information )
      {
        *(_DWORD *)&pFobx[2].UnicodeQueryTemplate.Length = 0;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return (unsigned int)StoredStatus;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_qqqL(
            WPP_GLOBAL_Control->AttachedDevice,
            41,
            WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids,
            RxContext,
            pFobx,
            &pFobx[2].Flags,
            pFobx[2].OffsetOfNextEaToReturn);
      }
      else
      {
        if ( LODWORD(pFobx[2].AssociatedFileObject) == 1 )
        {
          RxInitiateOrContinueThrottling((PTHROTTLING_STATE)&pFobx[2].Flags);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqqL(
              WPP_GLOBAL_Control->AttachedDevice,
              40,
              WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids,
              RxContext,
              pFobx,
              &pFobx[2].Flags,
              pFobx[2].OffsetOfNextEaToReturn);
          }
        }
        if ( LODWORD(pFobx[2].pSrvOpen) == 1 && !StoredStatus )
          StoredStatus = -1073741607;
      }
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      return (unsigned int)StoredStatus;
    }
    v21 = 42;
LABEL_70:
    WPP_SF_d(v19->AttachedDevice, v21, WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids, (unsigned int)StoredStatus);
    return (unsigned int)StoredStatus;
  }
  Flags = CurrentIrp->Flags;
  FileObject = CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject;
  InformationToReturn = RxContext->InformationToReturn;
  CurrentIrp->IoStatus.Information = InformationToReturn;
  v10 = Flags & 2;
  if ( v10 && StoredStatus >= 0 && !InformationToReturn )
    StoredStatus = -1073741807;
  if ( (*((_BYTE *)&RxContext->9 + 122) & 1) != 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      return (unsigned int)StoredStatus;
    }
    v21 = 39;
    goto LABEL_70;
  }
  if ( !KeGetCurrentIrql() )
  {
    if ( StoredStatus < 0 )
      goto LABEL_7;
    goto LABEL_34;
  }
  if ( StoredStatus >= 0 )
  {
LABEL_34:
    if ( !v10 && !v4 )
      FileObject->Flags |= 0x80000u;
    goto LABEL_7;
  }
  return 3225485315LL;
}

```

## disassembly

```asm
0x1400084b0  mov     [rsp+arg_18], rbx
0x1400084b5  push    rsi
0x1400084b6  push    rdi
0x1400084b7  push    r12
0x1400084b9  push    r13
0x1400084bb  push    r14
0x1400084bd  sub     rsp, 40h
0x1400084c1  mov     edi, [rcx+200h]
0x1400084c7  mov     rbx, rcx
0x1400084ca  mov     rax, [rcx+40h]
0x1400084ce  movzx   esi, dil
0x1400084d2  mov     r13, [rcx+28h]
0x1400084d6  and     sil, 1
0x1400084da  mov     r14, [rcx+38h]
0x1400084de  mov     r12d, [rcx+0B0h]
0x1400084e5  mov     [rsp+68h+arg_0], rax
0x1400084ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400084f1  lea     rdx, WPP_GLOBAL_Control
0x1400084f8  cmp     rcx, rdx
0x1400084fb  jnz     loc_14000867F
0x140008501  mov     [rsp+68h+arg_8], rbp
0x140008506  mov     [rsp+68h+arg_10], r15
0x14000850e  test    r13, r13
0x140008511  jz      short loc_140008560
0x140008513  mov     rax, [r13+0B8h]
0x14000851a  mov     ebp, [r13+10h]
0x14000851e  mov     r15, [rax+30h]
0x140008522  mov     rax, [rbx+0B8h]
0x140008529  mov     [r13+38h], rax
0x14000852d  and     ebp, 2
0x140008530  jnz     loc_1400087B7
0x140008536  test    byte ptr [rbx+20Ah], 1
0x14000853d  jnz     loc_1400086CC
0x140008543  call    cs:__imp_KeGetCurrentIrql
0x14000854a  nop     dword ptr [rax+rax+00h]
0x14000854f  test    al, al
0x140008551  jnz     loc_140008717
0x140008557  test    r12d, r12d
0x14000855a  jns     loc_140008720
0x140008560  and     edi, 2
0x140008563  call    cs:__imp_KeGetCurrentIrql
0x14000856a  nop     dword ptr [rax+rax+00h]
0x14000856f  movzx   ecx, byte ptr [rbx+241h]
0x140008576  lea     r15, [rbx+248h]
0x14000857d  cmp     al, 2
0x14000857f  jnb     loc_1400087D1
0x140008585  test    cl, cl
0x140008587  jz      short loc_1400085C6
0x140008589  mov     rbp, [r15]
0x14000858c  mov     byte ptr [rbx+0A9h], 0
0x140008593  mov     rcx, cs:WPP_GLOBAL_Control
0x14000859a  lea     rax, WPP_GLOBAL_Control
0x1400085a1  cmp     rcx, rax
0x1400085a4  jz      short loc_1400085B3
0x1400085a6  test    dword ptr [rcx+2Ch], 100h
0x1400085ad  jnz     loc_140008854
0x1400085b3  mov     rcx, [r14+10h]; Resource
0x1400085b7  mov     rdx, rbp; ResourceThreadId
0x1400085ba  call    cs:__imp_ExReleaseResourceForThreadLite
0x1400085c1  nop     dword ptr [rax+rax+00h]
0x1400085c6  cmp     byte ptr [rbx+240h], 0
0x1400085cd  jz      short loc_140008621
0x1400085cf  mov     rax, [r14+130h]
0x1400085d6  mov     r15, [r15]
0x1400085d9  mov     ebp, [rax+128h]
0x1400085df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400085e6  lea     rax, WPP_GLOBAL_Control
0x1400085ed  cmp     rcx, rax
0x1400085f0  jz      short loc_1400085FF
0x1400085f2  test    dword ptr [rcx+2Ch], 100h
0x1400085f9  jnz     loc_14000887B
0x1400085ff  test    ebp, ebp
0x140008601  jnz     loc_1400088AC
0x140008607  mov     byte ptr [rbx+0A8h], 0
0x14000860e  mov     rcx, [r14+8]; Resource
0x140008612  mov     rdx, r15; ResourceThreadId
0x140008615  call    cs:__imp_ExReleaseResourceForThreadLite
0x14000861c  nop     dword ptr [rax+rax+00h]
0x140008621  mov     rbp, [rsp+68h+arg_0]
0x140008626  test    edi, edi
0x140008628  jz      short loc_140008639
0x14000862a  lea     rdx, [rbp+0D8h]; BlockingIoQ
0x140008631  mov     rcx, rbx; RxContext
0x140008634  call    RxResumeBlockedOperations_Serially
0x140008639  test    sil, sil
0x14000863c  jnz     loc_14000873E
0x140008642  lea     rsi, WPP_GLOBAL_Control
0x140008649  mov     rcx, cs:WPP_GLOBAL_Control
0x140008650  cmp     rcx, rsi
0x140008653  jnz     loc_1400086F8
0x140008659  mov     eax, r12d
0x14000865c  mov     r15, [rsp+68h+arg_10]
0x140008664  mov     rbp, [rsp+68h+arg_8]
0x140008669  mov     rbx, [rsp+68h+arg_18]
0x140008671  add     rsp, 40h
0x140008675  pop     r14
0x140008677  pop     r13
0x140008679  pop     r12
0x14000867b  pop     rdi
0x14000867c  pop     rsi
0x14000867d  retn
0x14000867f  mov     eax, [rcx+2Ch]
0x140008682  test    al, 10h
0x140008684  jz      loc_140008501
0x14000868a  cmp     byte ptr [rcx+29h], 4
0x14000868e  jb      loc_140008501
0x140008694  mov     eax, [rbx+0B8h]
0x14000869a  lea     r8, WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids
0x1400086a1  mov     rcx, [rcx+18h]
0x1400086a5  mov     edx, 26h ; '&'
0x1400086aa  mov     [rsp+68h+var_38], eax
0x1400086ae  mov     r9, rbx
0x1400086b1  mov     dword ptr [rsp+68h+var_40], r12d
0x1400086b6  mov     [rsp+68h+var_48], r13
0x1400086bb  call    WPP_SF_qqDD
0x1400086c0  lea     rdx, WPP_GLOBAL_Control
0x1400086c7  jmp     loc_140008501
0x1400086cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086d3  cmp     rcx, rdx
0x1400086d6  jz      short loc_140008659
0x1400086d8  mov     edx, [rcx+2Ch]
0x1400086db  test    dl, 10h
0x1400086de  jz      loc_140008659
0x1400086e4  cmp     byte ptr [rcx+29h], 4
0x1400086e8  jb      loc_140008659
0x1400086ee  mov     edx, 27h ; '''
0x1400086f3  jmp     loc_1400271EE
0x1400086f8  mov     eax, [rcx+2Ch]
0x1400086fb  test    al, 10h
0x1400086fd  jz      loc_140008659
0x140008703  cmp     byte ptr [rcx+29h], 4
0x140008707  jb      loc_140008659
0x14000870d  mov     edx, 2Ah ; '*'
0x140008712  jmp     loc_1400271EE
0x140008717  test    r12d, r12d
0x14000871a  js      loc_14000884A
0x140008720  test    ebp, ebp
0x140008722  jnz     loc_140008560
0x140008728  test    sil, sil
0x14000872b  jnz     loc_140008560
0x140008731  or      dword ptr [r15+50h], 80000h
0x140008739  jmp     loc_140008560
0x14000873e  cmp     qword ptr [r13+38h], 0
0x140008743  jz      loc_140027160
0x140008749  mov     dword ptr [rbp+0C0h], 0
0x140008753  mov     rcx, cs:WPP_GLOBAL_Control
0x14000875a  lea     rax, WPP_GLOBAL_Control
0x140008761  cmp     rcx, rax
0x140008764  jz      loc_140008659
0x14000876a  mov     eax, [rcx+2Ch]
0x14000876d  test    al, 10h
0x14000876f  jz      loc_140008642
0x140008775  cmp     byte ptr [rcx+29h], 2
0x140008779  jb      loc_140008642
0x14000877f  mov     eax, [rbp+0D0h]
0x140008785  lea     r8, [rbp+0B8h]
0x14000878c  mov     rcx, [rcx+18h]
0x140008790  mov     edx, 29h ; ')'
0x140008795  mov     [rsp+68h+var_38], eax
0x140008799  mov     r9, rbx
0x14000879c  mov     [rsp+68h+var_40], r8
0x1400087a1  lea     r8, WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids
0x1400087a8  mov     [rsp+68h+var_48], rbp
0x1400087ad  call    WPP_SF_qqqL
0x1400087b2  jmp     loc_140008642
0x1400087b7  test    r12d, r12d
0x1400087ba  js      loc_140008536
0x1400087c0  test    rax, rax
0x1400087c3  mov     ecx, 0C0000011h
0x1400087c8  cmovz   r12d, ecx
0x1400087cc  jmp     loc_140008536
0x1400087d1  lea     rbp, [rbx+228h]
0x1400087d8  test    cl, cl
0x1400087da  jnz     loc_1400088E6
0x1400087e0  cmp     byte ptr [rbx+240h], 0
0x1400087e7  jz      loc_140008621
0x1400087ed  mov     r15, [r15]
0x1400087f0  mov     rbp, [rbp+0]
0x1400087f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087fb  lea     rax, WPP_GLOBAL_Control
0x140008802  cmp     rcx, rax
0x140008805  jnz     short loc_140008817
0x140008807  mov     byte ptr [rbx+0A8h], 0
0x14000880e  lea     rcx, [rbp+20h]
0x140008812  jmp     loc_140008612
0x140008817  test    dword ptr [rcx+2Ch], 100h
0x14000881e  jz      short loc_140008807
0x140008820  cmp     byte ptr [rcx+29h], 4
0x140008824  jb      short loc_140008807
0x140008826  mov     rcx, [rcx+18h]
0x14000882a  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140008831  mov     edx, 2Bh ; '+'
0x140008836  mov     [rsp+68h+var_40], r15
0x14000883b  mov     r9, rbx
0x14000883e  mov     [rsp+68h+var_48], r14
0x140008843  call    WPP_SF_qqq
0x140008848  jmp     short loc_140008807
0x14000884a  mov     eax, 0C0410003h
0x14000884f  jmp     loc_14000865C
0x140008854  cmp     byte ptr [rcx+29h], 4
0x140008858  jb      loc_1400085B3
0x14000885e  mov     rcx, [rcx+18h]
0x140008862  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140008869  mov     edx, 15h
0x14000886e  mov     r9, rbp
0x140008871  call    WPP_SF_q
0x140008876  jmp     loc_1400085B3
0x14000887b  cmp     byte ptr [rcx+29h], 4
0x14000887f  jb      loc_1400085FF
0x140008885  mov     rcx, [rcx+18h]
0x140008889  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140008890  mov     edx, 0Eh
0x140008895  mov     [rsp+68h+var_40], r15
0x14000889a  mov     r9, rbx
0x14000889d  mov     [rsp+68h+var_48], r14
0x1400088a2  call    WPP_SF_qqq
0x1400088a7  jmp     loc_1400085FF
0x1400088ac  mov     rcx, [r14+8]; Resource
0x1400088b0  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400088b7  nop     dword ptr [rax+rax+00h]
0x1400088bc  test    al, al
0x1400088be  jz      loc_140008607
0x1400088c4  mov     rdx, r14
0x1400088c7  mov     rcx, rbx
0x1400088ca  call    RxIsSafeToProcessBufferingStateChange
0x1400088cf  test    al, al
0x1400088d1  jz      loc_140008607
0x1400088d7  xor     edx, edx
0x1400088d9  mov     rcx, r14; Instance
0x1400088dc  call    RxProcessFcbChangeBufferingStateRequestInternal
0x1400088e1  jmp     loc_140008607
0x1400088e6  mov     r9, [r15]
0x1400088e9  mov     rdx, r14
0x1400088ec  mov     r8, [rbp+0]
0x1400088f0  mov     rcx, rbx
0x1400088f3  call    RxReleasePagingIoResourceForThreadAtDpc
0x1400088f8  jmp     loc_1400087E0
0x140027160  cmp     dword ptr [rbp+0A0h], 1
0x140027167  jnz     short loc_1400271C6
0x140027169  lea     rdi, [rbp+0B8h]
0x140027170  mov     rcx, rdi; pBP
0x140027173  call    RxInitiateOrContinueThrottling
0x140027178  mov     rcx, cs:WPP_GLOBAL_Control
0x14002717f  lea     rsi, WPP_GLOBAL_Control
0x140027186  cmp     rcx, rsi
0x140027189  jz      short loc_1400271CD
0x14002718b  mov     eax, [rcx+2Ch]
0x14002718e  test    al, 10h
0x140027190  jz      short loc_1400271CD
0x140027192  cmp     byte ptr [rcx+29h], 2
0x140027196  jb      short loc_1400271CD
0x140027198  mov     eax, [rbp+0D0h]
0x14002719e  lea     r8, WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids
0x1400271a5  mov     rcx, [rcx+18h]
0x1400271a9  mov     edx, 28h ; '('
0x1400271ae  mov     [rsp+68h+var_38], eax
0x1400271b2  mov     r9, rbx
0x1400271b5  mov     [rsp+68h+var_40], rdi
0x1400271ba  mov     [rsp+68h+var_48], rbp
0x1400271bf  call    WPP_SF_qqqL
0x1400271c4  jmp     short loc_1400271CD
0x1400271c6  lea     rsi, WPP_GLOBAL_Control
0x1400271cd  cmp     dword ptr [rbp+98h], 1
0x1400271d4  jnz     loc_140008649
0x1400271da  test    r12d, r12d
0x1400271dd  jnz     loc_140008649
0x1400271e3  mov     r12d, 0C00000D9h
0x1400271e9  jmp     loc_140008649
0x1400271ee  mov     rcx, [rcx+18h]
0x1400271f2  lea     r8, WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids
0x1400271f9  mov     r9d, r12d
0x1400271fc  call    WPP_SF_d
0x140027201  nop
0x140027202  jmp     loc_140008659
```
