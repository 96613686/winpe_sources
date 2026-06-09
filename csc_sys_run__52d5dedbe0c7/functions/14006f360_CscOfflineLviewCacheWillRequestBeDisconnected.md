# CscOfflineLviewCacheWillRequestBeDisconnected

- ea: `0x14006f360`
- end: `0x14006fd79`
- name: `CscOfflineLviewCacheWillRequestBeDisconnected`
- size: `2585`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation`

## callers

- `0x140008610`

## callees

- `0x14000a634`
- `0x14000f8b0`
- `0x1400135d4`
- `0x1400151b0`
- `0x1400169d4`
- `0x1400179f8`
- `0x14001ac1c`
- `0x14001c214`
- `0x14001c660`
- `0x14001d5c4`
- `0x14001d854`
- `0x1400222d0`
- `0x14002f010`
- `0x140047f44`
- `0x140049434`
- `0x140053278`
- `0x14006f270`
- `0x14006f360`
- `0x14006fd80`
- `0x14006ff60`
- `0x1400706b0`
- `0x1400709b0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14006f409`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14006f498`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14006f8c1`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14006f409`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14006f498`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14006f8c1`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14006f5d2`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14006f5d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f429`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f460`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f4d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f8fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f429`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f460`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f4d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006f8fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006fa5f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006fc43`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006fa5f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006fc43`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14006f989`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14006f989`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14006fcf7`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14006fcf7`

## pseudocode

```c
__int64 __fastcall CscOfflineLviewCacheWillRequestBeDisconnected(
        PIRP Irp,
        const UNICODE_STRING *a2,
        char *a3,
        __int64 *a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  char *v5; // r12
  struct _IRP *MasterIrp; // r8
  ULONG EaLength; // ecx
  __int64 v9; // rbx
  unsigned int v10; // esi
  ULONG Options; // eax
  struct _ERESOURCE *v12; // rdi
  struct _LIST_ENTRY *Flink; // r14
  char v14; // di
  int v15; // r14d
  char v16; // r14
  int v17; // edx
  bool v18; // zf
  const UNICODE_STRING *v19; // r14
  char v20; // si
  BOOLEAN v21; // r13
  int v22; // eax
  int v23; // esi
  __int64 *v24; // rax
  __int16 v26; // dx
  unsigned __int64 Length; // rax
  unsigned __int64 v28; // rcx
  __int64 v29; // rdx
  int v30; // edx
  bool v31; // di
  char v32; // cl
  __int16 v33; // r8
  __int64 v34; // rdx
  char v35; // al
  int v36; // edi
  char v37; // al
  __int64 v38; // r9
  char v39; // al
  char v40; // r9
  __int64 v41; // r9
  int v42; // [rsp+28h] [rbp-D8h]
  char v43; // [rsp+40h] [rbp-C0h] BYREF
  char v44; // [rsp+41h] [rbp-BFh]
  char v45; // [rsp+42h] [rbp-BEh] BYREF
  char v46; // [rsp+43h] [rbp-BDh]
  char v47; // [rsp+44h] [rbp-BCh]
  int v48; // [rsp+48h] [rbp-B8h] BYREF
  int InformationEntry; // [rsp+4Ch] [rbp-B4h]
  __int64 v50; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v51[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v52; // [rsp+68h] [rbp-98h]
  PCUNICODE_STRING String2; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  struct _IRP *v55; // [rsp+80h] [rbp-80h]
  __int64 *v56; // [rsp+90h] [rbp-70h]
  __int128 v57; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v58[5]; // [rsp+B0h] [rbp-50h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v52 = a3;
  v5 = a3;
  v56 = a4;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  EaLength = CurrentStackLocation->Parameters.Create.EaLength;
  v9 = 0;
  memset(v58, 0, sizeof(v58));
  String2 = a2;
  v10 = 0;
  InformationEntry = 0;
  v54 = 0;
  v55 = MasterIrp;
  Options = CurrentStackLocation->Parameters.Create.Options;
  v48 = EaLength;
  v45 = 0;
  v50 = 0;
  if ( (Options & 0x80u) != 0 && EaLength && (unsigned __int8)CscCredentialEaPresent(MasterIrp, EaLength) )
  {
    v14 = 0;
    v15 = 1692;
    goto LABEL_25;
  }
  v12 = (struct _ERESOURCE *)(CscDevExtn + 384);
  v47 = 1;
  ExAcquireResourceSharedLite((PERESOURCE)(CscDevExtn + 384), 1u);
  Flink = v12[1].SystemResourcesList.Flink;
  if ( Flink == (struct _LIST_ENTRY *)&v12[1] )
    goto LABEL_3;
  do
  {
    if ( LOWORD(Flink[10].Flink) > String2->Length )
      break;
    if ( RtlPrefixUnicodeString((PCUNICODE_STRING)&Flink[10], String2, 1u) )
    {
      v26 = (__int16)Flink[10].Flink;
      if ( String2->Length == v26 || String2->Buffer[(unsigned __int64)LOWORD(Flink[10].Flink) >> 1] == 92 )
      {
        v9 = (__int64)&Flink[-1];
        if ( v26 == String2->Length )
          break;
      }
    }
    Flink = Flink->Flink;
  }
  while ( Flink != (struct _LIST_ENTRY *)&v12[1] );
  v5 = v52;
  if ( !v9 )
  {
LABEL_3:
    ExReleaseResourceLite(v12);
    v14 = 0;
    v51[0] = v9;
    v15 = 1703;
    goto LABEL_23;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v9 + 4));
  ExReleaseResourceLite(v12);
  v46 = 0;
  while ( 2 )
  {
    v51[0] = v9;
    v44 = 0;
    v16 = 0;
    while ( 1 )
    {
      ExAcquireResourceSharedLite((PERESOURCE)(v9 + 40), 1u);
      v17 = *(unsigned __int8 *)(v9 + 12);
      if ( (_BYTE)v17 == 2 )
      {
        v16 = 1;
      }
      else if ( (_BYTE)v17 == 1 )
      {
        v43 = 1;
        goto LABEL_11;
      }
      v43 = 0;
LABEL_11:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_qZDDc(WPP_GLOBAL_Control->AttachedDevice, v17, v9 + 176, v9, v9 + 176, v17, *(_DWORD *)(v9 + 8), 63);
      ExReleaseResourceLite((PERESOURCE)(v9 + 40));
      if ( !v43 )
        break;
      KeWaitForSingleObject((PVOID)(v9 + 144), Executive, 0, 0, 0);
    }
    v5 = v52;
    v18 = v16 == 0;
    v19 = String2;
    v20 = 0;
    if ( !v18 )
    {
      v14 = 0;
      v20 = 1;
      v21 = 0;
      v15 = 1717;
      goto LABEL_17;
    }
    Length = String2->Length;
    v28 = *(unsigned __int16 *)(v9 + 176) + 2LL;
    v44 = 0;
    if ( Length <= v28 )
      goto LABEL_50;
    v44 = 0;
    if ( v46 )
      goto LABEL_50;
    InformationEntry = CscStoreQueryInformationEntryEx(*(_QWORD *)(v9 + 32), 1, (__int64)v58, 0, 0, 0, 0);
    if ( InformationEntry < 0 )
    {
      v14 = 0;
      v15 = 1741;
      v21 = 0;
      goto LABEL_17;
    }
    v44 = 1;
    if ( (BYTE4(v58[0]) & 1) == 0 || (BYTE4(v58[0]) & 0x10) == 0 )
      goto LABEL_50;
    v57 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_ZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        (unsigned int)WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids,
        v9 + 176,
        (__int64)v19);
    if ( (int)CscStoreFindLastLinkEntry(&v50, v29, v19, &v57) < 0 || !v50 || *(_QWORD *)(v9 + 32) == v50 )
    {
LABEL_50:
      v30 = v48;
      v31 = 0;
      if ( !v48 )
        goto LABEL_55;
      v48 = 0;
      v43 = 0;
      CscProcessCscEa((_DWORD)v55, v30, 0, 0, (__int64)&v43, 0, (__int64)&v48);
      v32 = v43;
      v33 = v48;
      if ( v43 )
        v31 = (v48 & 0xE000) != 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        v38 = 78;
        v39 = 89;
        if ( v43 )
          v38 = 89;
        if ( !v31 )
          v39 = 78;
        LOBYTE(v42) = v39;
        WPP_SF_cDc(
          WPP_GLOBAL_Control->AttachedDevice,
          40,
          WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids,
          v38,
          v48,
          v42);
        v32 = v43;
        v33 = v48;
      }
      if ( v32 && (v33 & 0x200) != 0 )
      {
        if ( !(unsigned __int8)CscOfflineLviewCachepIsCscOwned(v19) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids);
          }
          v14 = 0;
          v15 = 1874;
          v21 = 0;
          goto LABEL_17;
        }
      }
      else
      {
LABEL_55:
        if ( (int)CscStoreAccessCheck(
                    *(_QWORD *)(v9 + 32),
                    v30,
                    (unsigned int)*(_QWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 8) + 32,
                    0,
                    128) < 0 )
        {
          v14 = 0;
          v15 = 1859;
          v21 = 0;
          goto LABEL_17;
        }
      }
      if ( v31 )
      {
        LOBYTE(v34) = 1;
        v35 = CscOfflineLviewCachepSetIgnoreEntry(v9, v34, &v45);
        v21 = v45;
        v20 = v35;
LABEL_58:
        if ( v20 )
        {
          v14 = 0;
          v15 = 1899;
        }
        else if ( v44
               || (InformationEntry = CscStoreQueryInformationEntryEx(*(_QWORD *)(v9 + 32), 0, (__int64)v58, 0, 0, 0, 0),
                   InformationEntry >= 0) )
        {
          v48 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_ZZ(
              WPP_GLOBAL_Control->AttachedDevice,
              42,
              (unsigned int)WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids,
              (_DWORD)v19,
              v9 + 176);
          }
          v21 = 0;
          v47 = 0;
          v14 = 1;
          if ( (BYTE4(v58[0]) & 0xC) != 0 || (v58[0] & 0x120000) != 0 )
            CscEcpSetType(Irp, 1);
          v15 = v48;
        }
        else
        {
          v14 = 0;
          v15 = 1910;
        }
        goto LABEL_17;
      }
      v21 = 0;
      while ( 1 )
      {
        ExAcquireResourceSharedLite((PERESOURCE)(v9 + 40), 1u);
        v37 = *(_BYTE *)(v9 + 12);
        if ( v37 == 2 )
        {
          v20 = 1;
        }
        else
        {
          if ( v37 == 1 )
          {
            v43 = 1;
            goto LABEL_74;
          }
          v21 = ExAcquireRundownProtection((PEX_RUNDOWN_REF)(v9 + 168));
        }
        v43 = 0;
LABEL_74:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          v40 = 78;
          if ( v21 )
            v40 = 89;
          WPP_SF_qZDDc(
            WPP_GLOBAL_Control->AttachedDevice,
            *(unsigned __int8 *)(v9 + 12),
            v9 + 176,
            v9,
            v9 + 176,
            *(_BYTE *)(v9 + 12),
            *(_DWORD *)(v9 + 8),
            v40);
        }
        ExReleaseResourceLite((PERESOURCE)(v9 + 40));
        if ( !v43 )
        {
          v5 = v52;
          LODWORD(v19) = (_DWORD)String2;
          goto LABEL_58;
        }
        KeWaitForSingleObject((PVOID)(v9 + 144), Executive, 0, 0, 0);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_ZZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        38,
        (unsigned int)WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids,
        (unsigned int)&v57,
        v9 + 176,
        (__int64)v19);
    v36 = CscOfflineLviewCacheAddEntryEx((PERESOURCE)(CscDevExtn + 384), (__int64)&v54);
    CscStoreDereferenceEntry(&v50);
    if ( v36 >= 0 )
    {
      v46 = 1;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 4), 0xFFFFFFFF) == 1 )
        CscOfflineLviewCachepDeleteListEntry(v51);
      v9 = v54;
      continue;
    }
    break;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_ZZ(
      WPP_GLOBAL_Control->AttachedDevice,
      39,
      (unsigned int)WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids,
      v9 + 176,
      (__int64)v19);
  v14 = 0;
  v15 = 1796;
  v21 = 0;
LABEL_17:
  if ( v50 )
    CscStoreDereferenceEntry(&v50);
  if ( v21 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v9 + 168));
  if ( v20 )
  {
    v45 = 1;
    v22 = CscSetEcp(Irp, (LPCGUID)qword_140032580, &v45);
    v23 = v22;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_f74abd63425539499d784964bfbadaaa_Traceguids, Irp, v22);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_DqD(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_f74abd63425539499d784964bfbadaaa_Traceguids, 2, Irp, v23);
    }
  }
LABEL_23:
  if ( v9 && v47 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 4), 0xFFFFFFFF) == 1 )
      CscOfflineLviewCachepDeleteListEntry(v51);
    v9 = 0;
  }
  v10 = InformationEntry;
LABEL_25:
  v24 = v56;
  *v5 = v14;
  *v24 = v9;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    v41 = 89;
    if ( !v14 )
      v41 = 78;
    WPP_SF_cDD(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids, v41, v10, v15);
  }
  return v10;
}

```

## disassembly

```asm
0x14006f360  push    rbp
0x14006f362  push    rbx
0x14006f363  push    rsi
0x14006f364  push    rdi
0x14006f365  push    r12
0x14006f367  push    r13
0x14006f369  push    r14
0x14006f36b  push    r15
0x14006f36d  lea     rbp, [rsp-18h]
0x14006f372  sub     rsp, 118h
0x14006f379  mov     rax, cs:__security_cookie
0x14006f380  xor     rax, rsp
0x14006f383  mov     [rbp+50h+var_50], rax
0x14006f387  mov     r13, [rcx+0B8h]
0x14006f38e  xor     r14d, r14d
0x14006f391  xorps   xmm0, xmm0
0x14006f394  mov     [rsp+150h+var_E8], r8
0x14006f399  mov     r12, r8
0x14006f39c  mov     [rbp+50h+var_C0], r9
0x14006f3a0  mov     r8, [rcx+18h]
0x14006f3a4  mov     r15, rcx
0x14006f3a7  mov     ecx, [r13+20h]
0x14006f3ab  mov     ebx, r14d
0x14006f3ae  movups  [rbp+50h+var_A0], xmm0
0x14006f3b2  mov     [rsp+150h+String2], rdx
0x14006f3b7  mov     esi, r14d
0x14006f3ba  movups  [rbp+50h+var_90], xmm0
0x14006f3be  mov     [rsp+150h+var_104], r14d
0x14006f3c3  movups  [rbp+50h+var_80], xmm0
0x14006f3c7  mov     [rsp+150h+var_D8], r14
0x14006f3cc  movups  [rbp+50h+var_70], xmm0
0x14006f3d0  mov     [rbp+50h+var_D0], r8
0x14006f3d4  movups  [rbp+50h+var_60], xmm0
0x14006f3d8  mov     eax, [r13+10h]
0x14006f3dc  mov     [rsp+150h+var_108], ecx
0x14006f3e0  mov     [rsp+150h+var_10E], bl
0x14006f3e4  mov     [rsp+150h+var_100], r14
0x14006f3e9  test    al, al
0x14006f3eb  js      loc_14006F622
0x14006f3f1  mov     rdi, cs:CscDevExtn
0x14006f3f8  mov     dl, 1; Wait
0x14006f3fa  add     rdi, 180h
0x14006f401  mov     [rsp+150h+var_10C], 1
0x14006f406  mov     rcx, rdi; Resource
0x14006f409  call    cs:__imp_ExAcquireResourceSharedLite
0x14006f410  nop     dword ptr [rax+rax+00h]
0x14006f415  mov     r14, [rdi+68h]
0x14006f419  lea     rsi, [rdi+68h]
0x14006f41d  cmp     r14, rsi
0x14006f420  jnz     loc_14006F5B2
0x14006f426  mov     rcx, rdi; Resource
0x14006f429  call    cs:__imp_ExReleaseResourceLite
0x14006f430  nop     dword ptr [rax+rax+00h]
0x14006f435  xor     dil, dil
0x14006f438  mov     [rsp+150h+var_F8], rbx
0x14006f43d  mov     r14d, 6A7h
0x14006f443  lea     r13, WPP_GLOBAL_Control
0x14006f44a  jmp     loc_14006F560
0x14006f44f  mov     r12, [rsp+150h+var_E8]
0x14006f454  test    rbx, rbx
0x14006f457  jz      short loc_14006F426
0x14006f459  lock inc dword ptr [rbx+4]
0x14006f45d  mov     rcx, rdi; Resource
0x14006f460  call    cs:__imp_ExReleaseResourceLite
0x14006f467  nop     dword ptr [rax+rax+00h]
0x14006f46c  mov     [rsp+150h+var_10D], 0
0x14006f471  mov     rdi, rbx
0x14006f474  mov     [rsp+150h+var_F8], rbx
0x14006f479  nop     dword ptr [rax+00000000h]
0x14006f480  mov     [rsp+150h+var_10F], 0
0x14006f485  lea     rsi, WPP_GLOBAL_Control
0x14006f48c  movzx   r14d, [rsp+150h+var_10F]
0x14006f492  mov     dl, 1; Wait
0x14006f494  lea     rcx, [rdi+28h]; Resource
0x14006f498  call    cs:__imp_ExAcquireResourceSharedLite
0x14006f49f  nop     dword ptr [rax+rax+00h]
0x14006f4a4  movzx   edx, byte ptr [rdi+0Ch]
0x14006f4a8  cmp     dl, 2
0x14006f4ab  jnz     loc_14006F6C4
0x14006f4b1  mov     r14b, 1
0x14006f4b4  mov     [rsp+150h+var_110], 0
0x14006f4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f4c0  cmp     rcx, rsi
0x14006f4c3  jz      short loc_14006F4D0
0x14006f4c5  mov     eax, [rcx+2Ch]
0x14006f4c8  test    al, 20h
0x14006f4ca  jnz     loc_14006FA1A
0x14006f4d0  lea     rcx, [rdi+28h]; Resource
0x14006f4d4  call    cs:__imp_ExReleaseResourceLite
0x14006f4db  nop     dword ptr [rax+rax+00h]
0x14006f4e0  cmp     [rsp+150h+var_110], 0
0x14006f4e5  jnz     loc_14006FA47
0x14006f4eb  mov     r12, [rsp+150h+var_E8]
0x14006f4f0  test    r14b, r14b
0x14006f4f3  mov     r14, [rsp+150h+String2]
0x14006f4f8  mov     sil, 0
0x14006f4fb  jz      loc_14006F651
0x14006f501  xor     dil, dil
0x14006f504  mov     sil, 1
0x14006f507  xor     r13b, r13b
0x14006f50a  mov     r14d, 6B5h
0x14006f510  cmp     [rsp+150h+var_100], 0
0x14006f516  jnz     loc_14006FCE1
0x14006f51c  test    r13b, r13b
0x14006f51f  jnz     loc_14006FCF0
0x14006f525  test    sil, sil
0x14006f528  jz      loc_14006F443
0x14006f52e  mov     rdx, cs:EcpType; EcpType
0x14006f535  lea     r8, [rsp+150h+var_10E]
0x14006f53a  mov     rcx, r15; Irp
0x14006f53d  mov     [rsp+150h+var_10E], 1
0x14006f542  call    CscSetEcp
0x14006f547  mov     esi, eax
0x14006f549  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f550  lea     r13, WPP_GLOBAL_Control
0x14006f557  cmp     rcx, r13
0x14006f55a  jnz     loc_14006FD08
0x14006f560  test    rbx, rbx
0x14006f563  jnz     loc_14006F6D6
0x14006f569  mov     esi, [rsp+150h+var_104]
0x14006f56d  mov     rax, [rbp+50h+var_C0]
0x14006f571  mov     [r12], dil
0x14006f575  mov     [rax], rbx
0x14006f578  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f57f  cmp     rcx, r13
0x14006f582  jz      short loc_14006F58F
0x14006f584  mov     eax, [rcx+2Ch]
0x14006f587  test    al, 20h
0x14006f589  jnz     loc_14006FD44
0x14006f58f  mov     eax, esi
0x14006f591  mov     rcx, [rbp+50h+var_50]
0x14006f595  xor     rcx, rsp; StackCookie
0x14006f598  call    __security_check_cookie
0x14006f59d  add     rsp, 118h
0x14006f5a4  pop     r15
0x14006f5a6  pop     r14
0x14006f5a8  pop     r13
0x14006f5aa  pop     r12
0x14006f5ac  pop     rdi
0x14006f5ad  pop     rsi
0x14006f5ae  pop     rbx
0x14006f5af  pop     rbp
0x14006f5b0  retn
0x14006f5b2  mov     r12, [rsp+150h+String2]
0x14006f5b7  movzx   eax, word ptr [r12]
0x14006f5bc  lea     rcx, [r14+0A0h]; String1
0x14006f5c3  cmp     [rcx], ax
0x14006f5c6  ja      loc_14006F44F
0x14006f5cc  mov     r8b, 1; CaseInSensitive
0x14006f5cf  mov     rdx, r12; String2
0x14006f5d2  call    cs:__imp_RtlPrefixUnicodeString
0x14006f5d9  nop     dword ptr [rax+rax+00h]
0x14006f5de  test    al, al
0x14006f5e0  jnz     short loc_14006F5EF
0x14006f5e2  mov     r14, [r14]
0x14006f5e5  cmp     r14, rsi
0x14006f5e8  jnz     short loc_14006F5B7
0x14006f5ea  jmp     loc_14006F44F
0x14006f5ef  movzx   edx, word ptr [r14+0A0h]
0x14006f5f7  movzx   r8d, word ptr [r12]
0x14006f5fc  cmp     r8w, dx
0x14006f600  jz      short loc_14006F613
0x14006f602  mov     rax, [r12+8]
0x14006f607  mov     ecx, edx
0x14006f609  shr     rcx, 1
0x14006f60c  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x14006f611  jnz     short loc_14006F5E2
0x14006f613  lea     rbx, [r14-10h]
0x14006f617  cmp     dx, r8w
0x14006f61b  jnz     short loc_14006F5E2
0x14006f61d  jmp     loc_14006F44F
0x14006f622  test    ecx, ecx
0x14006f624  jz      loc_14006F3F1
0x14006f62a  mov     edx, ecx
0x14006f62c  mov     rcx, r8
0x14006f62f  call    CscCredentialEaPresent
0x14006f634  test    al, al
0x14006f636  jz      loc_14006F3F1
0x14006f63c  xor     dil, dil
0x14006f63f  lea     r13, WPP_GLOBAL_Control
0x14006f646  mov     r14d, 69Ch
0x14006f64c  jmp     loc_14006F56D
0x14006f651  movzx   ecx, word ptr [rbx+0B0h]
0x14006f658  movzx   eax, word ptr [r14]
0x14006f65c  add     rcx, 2
0x14006f660  mov     [rsp+150h+var_10F], sil
0x14006f665  cmp     rax, rcx
0x14006f668  jbe     loc_14006F70B
0x14006f66e  mov     [rsp+150h+var_10F], sil
0x14006f673  cmp     [rsp+150h+var_10D], sil
0x14006f678  jnz     loc_14006F70B
0x14006f67e  mov     rcx, [rbx+20h]
0x14006f682  lea     r8, [rbp+50h+var_A0]
0x14006f686  mov     [rsp+150h+var_120], 0
0x14006f68f  xor     r9d, r9d
0x14006f692  mov     [rsp+150h+var_128], 0
0x14006f69b  mov     dl, 1
0x14006f69d  mov     [rsp+150h+Timeout], 0
0x14006f6a6  call    CscStoreQueryInformationEntryEx
0x14006f6ab  mov     [rsp+150h+var_104], eax
0x14006f6af  test    eax, eax
0x14006f6b1  jns     short loc_14006F6FB
0x14006f6b3  xor     dil, dil
0x14006f6b6  mov     r14d, 6CDh
0x14006f6bc  xor     r13b, r13b
0x14006f6bf  jmp     loc_14006F510
0x14006f6c4  cmp     dl, 1
0x14006f6c7  jnz     loc_14006F4B4
0x14006f6cd  mov     [rsp+150h+var_110], dl
0x14006f6d1  jmp     loc_14006F4B9
0x14006f6d6  cmp     [rsp+150h+var_10C], 0
0x14006f6db  jz      loc_14006F569
0x14006f6e1  mov     eax, 0FFFFFFFFh
0x14006f6e6  lock xadd [rbx+4], eax
0x14006f6eb  cmp     eax, 1
0x14006f6ee  jz      loc_14006FD35
0x14006f6f4  xor     ebx, ebx
0x14006f6f6  jmp     loc_14006F569
0x14006f6fb  mov     eax, dword ptr [rbp+50h+var_A0+4]
0x14006f6fe  mov     [rsp+150h+var_10F], 1
0x14006f703  test    al, 1
0x14006f705  jnz     loc_14006F7E0
0x14006f70b  mov     edx, [rsp+150h+var_108]
0x14006f70f  xor     dil, dil
0x14006f712  test    edx, edx
0x14006f714  jz      short loc_14006F780
0x14006f716  mov     rcx, [rbp+50h+var_D0]
0x14006f71a  lea     rax, [rsp+150h+var_108]
0x14006f71f  mov     [rsp+150h+var_120], rax
0x14006f724  xor     r9d, r9d
0x14006f727  lea     rax, [rsp+150h+var_110]
0x14006f72c  mov     [rsp+150h+var_128], 0
0x14006f735  xor     r8d, r8d
0x14006f738  mov     [rsp+150h+Timeout], rax
0x14006f73d  mov     [rsp+150h+var_108], 0
0x14006f745  mov     [rsp+150h+var_110], sil
0x14006f74a  call    CscProcessCscEa
0x14006f74f  movzx   ecx, [rsp+150h+var_110]
0x14006f754  mov     r8d, [rsp+150h+var_108]
0x14006f759  test    cl, cl
0x14006f75b  jnz     loc_14006FB36
0x14006f761  mov     r10, cs:WPP_GLOBAL_Control
0x14006f768  lea     rax, WPP_GLOBAL_Control
0x14006f76f  cmp     r10, rax
0x14006f772  jnz     loc_14006FB4B
0x14006f778  test    cl, cl
0x14006f77a  jnz     loc_14006FB9D
0x14006f780  mov     rax, [r13+8]
0x14006f784  xor     r9d, r9d
0x14006f787  mov     rcx, [rbx+20h]
0x14006f78b  mov     dword ptr [rsp+150h+Timeout], 80h
0x14006f793  mov     r8, [rax+8]
0x14006f797  add     r8, 20h ; ' '
0x14006f79b  call    CscStoreAccessCheck
0x14006f7a0  test    eax, eax
0x14006f7a2  js      loc_14006FBD2
0x14006f7a8  test    dil, dil
0x14006f7ab  jz      loc_14006F8AB
0x14006f7b1  lea     r8, [rsp+150h+var_10E]
0x14006f7b6  mov     dl, 1
0x14006f7b8  mov     rcx, rbx
0x14006f7bb  call    CscOfflineLviewCachepSetIgnoreEntry
0x14006f7c0  movzx   r13d, [rsp+150h+var_10E]
0x14006f7c6  movzx   esi, al
0x14006f7c9  test    sil, sil
0x14006f7cc  jz      loc_14006F924
0x14006f7d2  xor     dil, dil
0x14006f7d5  mov     r14d, 76Bh
0x14006f7db  jmp     loc_14006F510
0x14006f7e0  test    al, 10h
0x14006f7e2  jz      loc_14006F70B
0x14006f7e8  xorps   xmm0, xmm0
0x14006f7eb  movups  [rbp+50h+var_B8], xmm0
0x14006f7ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f7f6  lea     rax, WPP_GLOBAL_Control
0x14006f7fd  cmp     rcx, rax
0x14006f800  jnz     loc_14006FA70
0x14006f806  lea     r9, [rbp+50h+var_B8]
0x14006f80a  mov     r8, r14
0x14006f80d  lea     rcx, [rsp+150h+var_100]
0x14006f812  call    CscStoreFindLastLinkEntry
0x14006f817  test    eax, eax
0x14006f819  js      loc_14006F70B
0x14006f81f  mov     rdi, [rsp+150h+var_100]
0x14006f824  test    rdi, rdi
0x14006f827  jz      loc_14006F70B
0x14006f82d  cmp     [rbx+20h], rdi
0x14006f831  jz      loc_14006F70B
0x14006f837  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f83e  lea     rax, WPP_GLOBAL_Control
0x14006f845  cmp     rcx, rax
0x14006f848  jnz     loc_14006FAA1
0x14006f84e  mov     rcx, cs:CscDevExtn
0x14006f855  lea     rax, [rsp+150h+var_D8]
0x14006f85a  add     rcx, 180h; Resource
0x14006f861  mov     [rsp+150h+Timeout], rax; __int64
0x14006f866  mov     r9b, 1
0x14006f869  lea     rdx, [rbp+50h+var_B8]
0x14006f86d  mov     r8, rdi
0x14006f870  call    CscOfflineLviewCacheAddEntryEx
  ... truncated ...
```
