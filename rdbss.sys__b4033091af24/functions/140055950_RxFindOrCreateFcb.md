# RxFindOrCreateFcb

- ea: `0x140055950`
- end: `0x140055fb9`
- name: `RxFindOrCreateFcb`
- size: `1641`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, __int64, IRP *, PFCB *, char)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x140054ca0`

## callees

- `0x140008030`
- `0x140008190`
- `0x140009b80`
- `0x14000d7c0`
- `0x14000ea70`
- `0x140014e40`
- `0x140016e70`
- `0x1400188e4`
- `0x14001bea8`
- `0x140055950`
- `0x140055fc0`
- `0x140057660`
- `0x140058540`
- `0x14005cae0`
- `0x14006a4c0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140055cc2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140055cc2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140055ded`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007ca45`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140055ded`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007ca45`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055ae5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055c0b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055e4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055f2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007ca30`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055ae5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055c0b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055e4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055f2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007ca30`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140055a66`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140055a66`

## pseudocode

```c
__int64 __fastcall RxFindOrCreateFcb(PRX_CONTEXT RxContext, __int64 a2, IRP *a3, PFCB *a4, char a5)
{
  NTSTATUS ParentFcb; // r12d
  PFCB NetFcb; // rbx
  PSZ v9; // rdi
  PSZ v10; // rdx
  char v11; // r14
  bool v12; // r15
  UNICODE_STRING **v13; // r8
  UNICODE_STRING *p_FileName; // r13
  int v15; // eax
  struct _ERESOURCE *v16; // rcx
  PFCB v17; // rax
  UNICODE_STRING *v18; // r9
  int v19; // ecx
  struct _V_NET_ROOT *v20; // r8
  ULONG v21; // r8d
  const CHAR *v22; // r9
  struct _RX_CONTEXT *v23; // rcx
  __int64 v24; // rdi
  char v25; // al
  ULONG v27; // r8d
  const CHAR *v28; // r9
  ULONG v29; // r8d
  const CHAR *v30; // r9
  __int64 v31; // r8
  ULONG v32; // r8d
  const CHAR *v33; // r9
  const CHAR *FileName; // [rsp+20h] [rbp-D8h]
  ULONG FileNamea; // [rsp+20h] [rbp-D8h]
  ULONG SerialNumber; // [rsp+28h] [rbp-D0h]
  int v37; // [rsp+54h] [rbp-A4h]
  int v38; // [rsp+68h] [rbp-90h]
  CHAR *v39; // [rsp+70h] [rbp-88h]
  RX_FCBTRACKER_CALLINFO *v40; // [rsp+78h] [rbp-80h]
  __int64 v41; // [rsp+88h] [rbp-70h]
  PSZ v43; // [rsp+B0h] [rbp-48h]

  ParentFcb = 0;
  v41 = *(_QWORD *)(a2 + 184);
  NetFcb = 0;
  v9 = RxContext->TrackerHistory[0].FileName;
  v39 = v9;
  v10 = v9;
  v43 = v9;
  v11 = 0;
  v38 = *((_DWORD *)&RxContext->9 + 35) & 0x200000;
  v12 = (RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.LockNV & 0x20000) != 0 || dbgForceNewFcb;
  v13 = (UNICODE_STRING **)&RxContext->TrackerHistory[1];
  v40 = &RxContext->TrackerHistory[1];
  p_FileName = (UNICODE_STRING *)&RxContext->TrackerHistory[7].FileName;
  if ( !*(_QWORD *)&RxContext->TrackerHistory[1].AcquireRelease )
    p_FileName = (UNICODE_STRING *)a3;
  v15 = 0;
  v37 = 0;
  while ( 1 )
  {
    if ( !v12 )
    {
      if ( !v11 )
      {
        v16 = (struct _ERESOURCE *)(v10 + 344);
        if ( v15 )
          ExAcquireResourceExclusiveLite(v16, 1u);
        else
          ExAcquireResourceSharedLite(v16, 1u);
        v11 = 1;
      }
      v17 = RxFcbTableLookupFcb((PRX_FCB_TABLE)(v9 + 296), p_FileName);
      NetFcb = v17;
      if ( a5 )
      {
        if ( !v17 && !v37 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_Z(
              WPP_GLOBAL_Control->AttachedDevice,
              21,
              WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
              p_FileName);
          }
          ExReleaseResourceLite((PERESOURCE)(v9 + 344));
          v11 = 0;
          v37 = 1;
          goto LABEL_44;
        }
      }
      else if ( !v17 )
      {
        ParentFcb = -1073741275;
        goto LABEL_48;
      }
      v13 = (UNICODE_STRING **)v40;
    }
    if ( !NetFcb )
    {
      v18 = *v13;
      v19 = ((*(_BYTE *)(v41 + 2) & 2) != 0 ? 4 : 0) | 0x20000;
      if ( (BYTE2(RxContext->TrackerHistory[4].FileName) & 0x10) == 0 )
        v19 = (*(_BYTE *)(v41 + 2) & 2) != 0 ? 4 : 0;
      v20 = (struct _V_NET_ROOT *)&RxContext->TrackerHistory[7].FileName;
      if ( !v18 )
        v20 = 0;
      SerialNumber = v19;
      LOWORD(FileName) = RxContext->Create.Password.Length;
      NetFcb = RxCreateNetFcb((PRX_CONTEXT)v9, a3, v20, v18);
      if ( !NetFcb )
        break;
    }
    if ( !v12 )
    {
      if ( ((__int64)NetFcb->FcbTableEntry.HashLinks.Blink & 2) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, NetFcb);
        }
        if ( !v37 )
        {
          ExReleaseResourceLite((PERESOURCE)(v9 + 344));
          ExAcquireResourceExclusiveLite((PERESOURCE)(v9 + 344), 1u);
          v37 = 1;
          v9 = v39;
        }
        _RxAcquireFcb(NetFcb, 0, 1u, 0, FileName, SerialNumber);
        LOBYTE(v31) = 1;
        RxAcquirePagingIoResource(0, NetFcb, v31);
        RxOrphanThisFcb(NetFcb);
        RxReleasePagingIoResource(0, NetFcb);
LABEL_62:
        if ( !RxpDereferenceAndFinalizeNetFcb(NetFcb, 0, 0, 0) )
        {
          v23 = 0;
LABEL_64:
          _RxReleaseFcb(v23, (PMRX_FCB)&NetFcb->Header, v21, v22, (ULONG)FileName);
        }
LABEL_65:
        NetFcb = 0;
        goto LABEL_45;
      }
      if ( !*(_QWORD *)&NetFcb->UpperFinalizationDone && (unsigned __int8)RxpFcbShouldHaveParent(NetFcb) )
      {
        if ( v37 != 1 )
        {
          ExReleaseResourceLite((PERESOURCE)(v9 + 344));
          v37 = 1;
          v11 = 0;
          _RxAcquireFcb(NetFcb, 0, 1u, 0, FileName, SerialNumber);
          goto LABEL_62;
        }
        ParentFcb = RxpFindOrCreateParentFcb(NetFcb);
        if ( ParentFcb < 0 )
          goto LABEL_48;
      }
    }
    if ( v11 )
    {
      ExReleaseResourceLite((PERESOURCE)(v9 + 344));
      v11 = 0;
    }
    ParentFcb = _RxAcquireFcb(NetFcb, RxContext, 1u, 0, FileName, SerialNumber);
    if ( ParentFcb < 0 )
      goto LABEL_48;
    if ( LOWORD(NetFcb->InternalFobx) != p_FileName->Length
      || !RtlEqualUnicodeString((PCUNICODE_STRING)&NetFcb->InternalFobx, p_FileName, v9[472]) )
    {
      goto LABEL_38;
    }
    if ( v38 )
    {
      if ( (HIBYTE(NetFcb->ShareAccess.Writers) & 0x3C) == 0xC )
        goto LABEL_38;
    }
    else if ( (HIBYTE(NetFcb->ShareAccess.Writers) & 0x3C) == 8 )
    {
      goto LABEL_38;
    }
    if ( *((char *)&NetFcb->1 + 156) < 0 )
    {
LABEL_38:
      if ( !RxpDereferenceAndFinalizeNetFcb(NetFcb, RxContext, 0, 0) )
      {
        v23 = RxContext;
        goto LABEL_64;
      }
      goto LABEL_65;
    }
    v24 = *(_QWORD *)&NetFcb->UpperFinalizationDone;
    if ( v24 && (*(_DWORD *)(v24 + 156) & 0x80u) != 0 )
    {
      *(_QWORD *)&NetFcb->UpperFinalizationDone = 0;
      if ( !RxpDereferenceAndFinalizeNetFcb(NetFcb, 0, 0, 0) )
        _RxReleaseFcb(0, (PMRX_FCB)&NetFcb->Header, v27, v28, (ULONG)FileName);
      NetFcb = 0;
      _RxAcquireFcb((PFCB)v24, 0, 1u, 0, FileName, SerialNumber);
      if ( !RxpDereferenceAndFinalizeNetFcb((PFCB)v24, 0, 0, 0) )
        _RxReleaseFcb(0, (PMRX_FCB)v24, v32, v33, (ULONG)FileName);
      v37 = 1;
    }
    v9 = v39;
LABEL_44:
    if ( NetFcb )
      goto LABEL_48;
LABEL_45:
    v15 = v37;
    v13 = (UNICODE_STRING **)v40;
    v10 = v43;
  }
  ParentFcb = -1073741670;
LABEL_48:
  if ( v11 )
    ExReleaseResourceLite((PERESOURCE)(v9 + 344));
  v25 = BYTE5(RxContext->TrackerHistory[4].FileName);
  if ( ParentFcb < 0 )
  {
    BYTE5(RxContext->TrackerHistory[4].FileName) = v25 & 0xFE;
    if ( NetFcb )
    {
      _RxAcquireFcb(NetFcb, 0, 1u, 0, FileName, SerialNumber);
      if ( !RxpDereferenceAndFinalizeNetFcb(NetFcb, 0, 0, 0) )
        _RxReleaseFcb(0, (PMRX_FCB)&NetFcb->Header, v29, v30, FileNamea);
      LODWORD(NetFcb) = 0;
    }
    RxContext->pFcb = 0;
  }
  else
  {
    RxContext->pFcb = (PMRX_FCB)&NetFcb->Header;
    BYTE5(RxContext->TrackerHistory[4].FileName) = v25 | 1;
    _InterlockedIncrement((volatile signed __int32 *)&NetFcb->FileLock.LastReturnedLockInfo);
    if ( a4 )
      *a4 = NetFcb;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDZ(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      (unsigned int)WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
      (_DWORD)NetFcb,
      ParentFcb,
      (__int64)p_FileName);
  }
  return (unsigned int)ParentFcb;
}

```

## disassembly

```asm
0x140055950  mov     [rsp+arg_18], r9
0x140055955  mov     [rsp+Irp], r8
0x14005595a  mov     [rsp+arg_0], rcx
0x14005595f  push    rbx
0x140055960  push    rsi
0x140055961  push    rdi
0x140055962  push    r12
0x140055964  push    r13
0x140055966  push    r14
0x140055968  push    r15
0x14005596a  sub     rsp, 0C0h
0x140055971  mov     r10, r8
0x140055974  mov     rsi, rcx
0x140055977  mov     [rsp+0F8h+var_60], rcx
0x14005597f  xor     r9d, r9d
0x140055982  mov     r12d, r9d
0x140055985  mov     rax, [rdx+0B8h]
0x14005598c  mov     [rsp+0F8h+var_70], rax
0x140055994  mov     [rsp+0F8h+var_58], rax
0x14005599c  mov     ebx, r9d
0x14005599f  mov     [rsp+0F8h+var_98], rbx
0x1400559a4  mov     rdi, [rcx+288h]
0x1400559ab  mov     [rsp+0F8h+var_88], rdi
0x1400559b0  mov     [rsp+0F8h+var_50], rdi
0x1400559b8  mov     rdx, rdi
0x1400559bb  mov     [rsp+0F8h+var_48], rdx
0x1400559c3  xor     r14b, r14b
0x1400559c6  mov     [rsp+0F8h+arg_8], r14b
0x1400559ce  mov     eax, [rcx+21Ch]
0x1400559d4  and     eax, 200000h
0x1400559d9  mov     [rsp+0F8h+var_90], eax
0x1400559dd  mov     [rsp+0F8h+var_74], eax
0x1400559e4  setnz   [rsp+0F8h+var_A0]
0x1400559e9  mov     rax, [rcx+50h]
0x1400559ed  test    dword ptr [rax+150h], 20000h
0x1400559f7  jnz     loc_140055E3F
0x1400559fd  movzx   eax, cs:dbgForceNewFcb
0x140055a04  test    al, al
0x140055a06  jnz     loc_140055E3F
0x140055a0c  xor     r15b, r15b
0x140055a0f  mov     [rsp+0F8h+var_A7], r15b
0x140055a14  movzx   r11d, r15b
0x140055a18  mov     [rsp+0F8h+var_A8], r15b
0x140055a1d  lea     r8, [rcx+298h]
0x140055a24  mov     [rsp+0F8h+var_80], r8
0x140055a29  cmp     [r8], rbx
0x140055a2c  lea     r13, [rcx+330h]
0x140055a33  jnz     short loc_140055A38
0x140055a35  mov     r13, r10
0x140055a38  mov     [rsp+0F8h+var_68], r13
0x140055a40  mov     eax, r9d
0x140055a43  mov     [rsp+0F8h+var_A4], eax
0x140055a47  test    r15b, r15b
0x140055a4a  jnz     loc_140055B14
0x140055a50  test    r14b, r14b
0x140055a53  jnz     short loc_140055A82
0x140055a55  lea     rcx, [rdx+158h]; Resource
0x140055a5c  mov     dl, 1; Wait
0x140055a5e  test    eax, eax
0x140055a60  jnz     loc_140055DED
0x140055a66  call    cs:__imp_ExAcquireResourceSharedLite
0x140055a6d  nop     dword ptr [rax+rax+00h]
0x140055a72  mov     r14b, 1
0x140055a75  mov     [rsp+0F8h+arg_8], r14b
0x140055a7d  mov     r8, [rsp+0F8h+var_80]
0x140055a82  cmp     qword ptr [r8], 0
0x140055a86  setnz   r8b
0x140055a8a  lea     rcx, [rdi+128h]; FcbTable
0x140055a91  movzx   r9d, [rsp+0F8h+var_A0]
0x140055a97  mov     rdx, r13; Path
0x140055a9a  call    RxFcbTableLookupFcb
0x140055a9f  mov     rbx, rax
0x140055aa2  mov     [rsp+0F8h+var_98], rax
0x140055aa7  cmp     [rsp+0F8h+arg_20], 0
0x140055aaf  jz      loc_140055D6D
0x140055ab5  test    rax, rax
0x140055ab8  jnz     short loc_140055B09
0x140055aba  cmp     [rsp+0F8h+var_A4], eax
0x140055abe  jnz     short loc_140055B09
0x140055ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x140055ac7  lea     rax, WPP_GLOBAL_Control
0x140055ace  cmp     rcx, rax
0x140055ad1  jz      short loc_140055ADE
0x140055ad3  mov     eax, [rcx+2Ch]
0x140055ad6  test    al, 8
0x140055ad8  jnz     loc_140055EB3
0x140055ade  lea     rcx, [rdi+158h]; Resource
0x140055ae5  call    cs:__imp_ExReleaseResourceLite
0x140055aec  nop     dword ptr [rax+rax+00h]
0x140055af1  xor     r14b, r14b
0x140055af4  mov     [rsp+0F8h+arg_8], r14b
0x140055afc  mov     [rsp+0F8h+var_A4], 1
0x140055b04  jmp     loc_140055D46
0x140055b09  movzx   r11d, [rsp+0F8h+var_A8]
0x140055b0f  mov     r8, [rsp+0F8h+var_80]
0x140055b14  test    rbx, rbx
0x140055b17  jnz     loc_140055BB9
0x140055b1d  mov     rax, [rsp+0F8h+var_70]
0x140055b25  movzx   ecx, byte ptr [rax+2]
0x140055b29  and     cl, 2
0x140055b2c  movzx   eax, cl
0x140055b2f  neg     al
0x140055b31  sbb     edx, edx
0x140055b33  and     edx, 4
0x140055b36  mov     r9, [r8]; Name
0x140055b39  xor     r11b, 1
0x140055b3d  mov     r10d, 40h ; '@'
0x140055b43  test    cl, cl
0x140055b45  mov     eax, 100h
0x140055b4a  cmovz   r10d, eax
0x140055b4e  mov     ecx, edx
0x140055b50  bts     ecx, 11h
0x140055b54  test    byte ptr [rsi+2EAh], 10h
0x140055b5b  cmovz   ecx, edx
0x140055b5e  mov     r8, [rsp+0F8h+var_60]
0x140055b66  add     r8, 330h
0x140055b6d  test    r9, r9
0x140055b70  mov     rax, rbx
0x140055b73  cmovz   r8, rbx; VNetRoot
0x140055b77  mov     [rsp+0F8h+var_B8], r11b
0x140055b7c  mov     [rsp+0F8h+var_C0], 0EC20h
0x140055b83  mov     [rsp+0F8h+var_C8], r10
0x140055b88  mov     [rsp+0F8h+SerialNumber], ecx; SerialNumber
0x140055b8c  movzx   eax, word ptr [rsi+248h]
0x140055b93  mov     word ptr [rsp+0F8h+FileName], ax; FileName
0x140055b98  mov     rdx, [rsp+0F8h+Irp]; Irp
0x140055ba0  mov     rcx, rdi; RxContext
0x140055ba3  call    RxCreateNetFcb
0x140055ba8  mov     rbx, rax
0x140055bab  mov     [rsp+0F8h+var_98], rax
0x140055bb0  test    rax, rax
0x140055bb3  jz      loc_140055EA8
0x140055bb9  test    r15b, r15b
0x140055bbc  jnz     short loc_140055BFF
0x140055bbe  test    byte ptr [rbx+100h], 2
0x140055bc5  jnz     loc_140055EDA
0x140055bcb  cmp     qword ptr [rbx+120h], 0
0x140055bd3  jnz     short loc_140055BFF
0x140055bd5  mov     rcx, rbx
0x140055bd8  call    RxpFcbShouldHaveParent
0x140055bdd  test    al, al
0x140055bdf  jz      short loc_140055BFF
0x140055be1  cmp     [rsp+0F8h+var_A4], 1
0x140055be6  jnz     loc_140055E47
0x140055bec  mov     rcx, rbx; Instance
0x140055bef  call    RxpFindOrCreateParentFcb
0x140055bf4  mov     r12d, eax
0x140055bf7  test    eax, eax
0x140055bf9  js      loc_140055D7C
0x140055bff  test    r14b, r14b
0x140055c02  jz      short loc_140055C22
0x140055c04  lea     rcx, [rdi+158h]; Resource
0x140055c0b  call    cs:__imp_ExReleaseResourceLite
0x140055c12  nop     dword ptr [rax+rax+00h]
0x140055c17  xor     r14b, r14b
0x140055c1a  mov     [rsp+0F8h+arg_8], r14b
0x140055c22  xor     r9d, r9d; LineNumber
0x140055c25  mov     r8d, 1; Mode
0x140055c2b  mov     rdx, rsi; RxContext
0x140055c2e  mov     rcx, rbx; Fcb
0x140055c31  call    __RxAcquireFcb
0x140055c36  mov     r12d, eax
0x140055c39  mov     [rsp+0F8h+var_78], eax
0x140055c40  jmp     short loc_140055C9D
0x140055c42  mov     rsi, [rsp+0F8h+arg_0]
0x140055c4a  mov     r12d, [rsi+0B0h]
0x140055c51  mov     [rsp+0F8h+var_78], r12d
0x140055c59  mov     rax, [rsp+0F8h+var_58]
0x140055c61  mov     [rsp+0F8h+var_70], rax
0x140055c69  mov     rbx, [rsp+0F8h+var_98]
0x140055c6e  mov     rdi, [rsp+0F8h+var_50]
0x140055c76  mov     [rsp+0F8h+var_88], rdi
0x140055c7b  movzx   r14d, [rsp+0F8h+arg_8]
0x140055c84  movzx   r15d, [rsp+0F8h+var_A7]
0x140055c8a  mov     r13, [rsp+0F8h+var_68]
0x140055c92  mov     eax, [rsp+0F8h+var_74]
0x140055c99  mov     [rsp+0F8h+var_90], eax
0x140055c9d  test    r12d, r12d
0x140055ca0  js      loc_140055D7C
0x140055ca6  lea     rcx, [rbx+150h]; String1
0x140055cad  movzx   eax, word ptr [r13+0]
0x140055cb2  cmp     [rcx], ax
0x140055cb5  jnz     short loc_140055CE7
0x140055cb7  movzx   r8d, byte ptr [rdi+1D8h]; CaseInSensitive
0x140055cbf  mov     rdx, r13; String2
0x140055cc2  call    cs:__imp_RtlEqualUnicodeString
0x140055cc9  nop     dword ptr [rax+rax+00h]
0x140055cce  test    al, al
0x140055cd0  jz      short loc_140055CE7
0x140055cd2  mov     ecx, [rsp+0F8h+var_90]
0x140055cd6  test    ecx, ecx
0x140055cd8  jnz     short loc_140055D08
0x140055cda  movzx   eax, byte ptr [rbx+163h]
0x140055ce1  and     al, 3Ch
0x140055ce3  cmp     al, 8
0x140055ce5  jnz     short loc_140055D19
0x140055ce7  xor     r9d, r9d; ForceFinalize
0x140055cea  xor     r8d, r8d; RecursiveFinalize
0x140055ced  mov     rdx, rsi; RxContext
0x140055cf0  mov     rcx, rbx; ThisFcb
0x140055cf3  call    RxpDereferenceAndFinalizeNetFcb
0x140055cf8  test    al, al
0x140055cfa  jnz     loc_140055E9C
0x140055d00  mov     rcx, rsi
0x140055d03  jmp     loc_140055E94
0x140055d08  movzx   eax, byte ptr [rbx+163h]
0x140055d0f  and     al, 3Ch
0x140055d11  cmp     al, 0Ch
0x140055d13  jz      short loc_140055CE7
0x140055d15  test    ecx, ecx
0x140055d17  jz      short loc_140055CDA
0x140055d19  xor     cl, cl
0x140055d1b  test    byte ptr [rbx+9Ch], 80h
0x140055d22  movzx   eax, cl
0x140055d25  mov     ecx, 1
0x140055d2a  cmovnz  eax, ecx
0x140055d2d  test    al, al
0x140055d2f  jnz     short loc_140055CE7
0x140055d31  mov     rdi, [rbx+120h]
0x140055d38  test    rdi, rdi
0x140055d3b  jnz     loc_140055DFE
0x140055d41  mov     rdi, [rsp+0F8h+var_88]
0x140055d46  test    rbx, rbx
0x140055d49  jnz     short loc_140055D7C
0x140055d4b  test    r12d, r12d
0x140055d4e  mov     eax, [rsp+0F8h+var_A4]
0x140055d52  mov     r8, [rsp+0F8h+var_80]
0x140055d57  mov     rdx, [rsp+0F8h+var_48]
0x140055d5f  movzx   r11d, [rsp+0F8h+var_A8]
0x140055d65  jns     loc_140055A47
0x140055d6b  jmp     short loc_140055D7C
0x140055d6d  test    rax, rax
0x140055d70  jnz     loc_140055B09
0x140055d76  mov     r12d, 0C0000225h
0x140055d7c  test    r14b, r14b
0x140055d7f  jnz     loc_140055F24
0x140055d85  movzx   eax, byte ptr [rsi+2EDh]
0x140055d8c  test    r12d, r12d
0x140055d8f  js      loc_140055F3C
0x140055d95  mov     [rsi+38h], rbx
0x140055d99  or      al, 1
0x140055d9b  mov     [rsi+2EDh], al
0x140055da1  lock inc dword ptr [rbx+1E0h]
0x140055da8  mov     rax, [rsp+0F8h+arg_18]
0x140055db0  test    rax, rax
0x140055db3  jz      short loc_140055DB8
0x140055db5  mov     [rax], rbx
0x140055db8  mov     rcx, cs:WPP_GLOBAL_Control
0x140055dbf  lea     rax, WPP_GLOBAL_Control
0x140055dc6  cmp     rcx, rax
0x140055dc9  jz      short loc_140055DD6
0x140055dcb  mov     eax, [rcx+2Ch]
0x140055dce  test    al, 8
0x140055dd0  jnz     loc_140055F88
0x140055dd6  mov     eax, r12d
0x140055dd9  add     rsp, 0C0h
0x140055de0  pop     r15
0x140055de2  pop     r14
0x140055de4  pop     r13
0x140055de6  pop     r12
0x140055de8  pop     rdi
0x140055de9  pop     rsi
0x140055dea  pop     rbx
0x140055deb  retn
0x140055ded  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140055df4  nop     dword ptr [rax+rax+00h]
0x140055df9  jmp     loc_140055A72
0x140055dfe  mov     eax, [rdi+9Ch]
0x140055e04  test    al, al
0x140055e06  jns     loc_140055D41
0x140055e0c  mov     qword ptr [rbx+120h], 0
0x140055e17  xor     r9d, r9d; ForceFinalize
0x140055e1a  xor     r8d, r8d; RecursiveFinalize
0x140055e1d  xor     edx, edx; RxContext
0x140055e1f  mov     rcx, rbx; ThisFcb
0x140055e22  call    RxpDereferenceAndFinalizeNetFcb
0x140055e27  test    al, al
0x140055e29  jnz     loc_14007CA96
0x140055e2f  mov     rdx, rbx; MrxFcb
0x140055e32  xor     ecx, ecx; RxContext
0x140055e34  call    __RxReleaseFcb
0x140055e39  nop
0x140055e3a  jmp     loc_14007CA96
0x140055e3f  mov     r15b, 1
0x140055e42  jmp     loc_140055A0F
0x140055e47  lea     rcx, [rdi+158h]; Resource
0x140055e4e  call    cs:__imp_ExReleaseResourceLite
0x140055e55  nop     dword ptr [rax+rax+00h]
0x140055e5a  mov     eax, 1
0x140055e5f  mov     [rsp+0F8h+var_A4], eax
0x140055e63  xor     r14b, r14b
0x140055e66  mov     [rsp+0F8h+arg_8], r14b
0x140055e6e  xor     r9d, r9d; LineNumber
0x140055e71  mov     r8d, eax; Mode
0x140055e74  xor     edx, edx; RxContext
0x140055e76  mov     rcx, rbx; Fcb
0x140055e79  call    __RxAcquireFcb
0x140055e7e  xor     r9d, r9d; ForceFinalize
0x140055e81  xor     r8d, r8d; RecursiveFinalize
0x140055e84  xor     edx, edx; RxContext
  ... truncated ...
```
