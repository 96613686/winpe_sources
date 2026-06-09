# UlCopyRequestToIrp

- ea: `0x1c00b0480`
- end: `0x1c00b08ed`
- name: `UlCopyRequestToIrp`
- size: `1133`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c00097a0`
- `0x1c00a4250`
- `0x1c00aebe0`

## callees

- `0x1c0009240`
- `0x1c0010ce8`
- `0x1c001604c`
- `0x1c001a4b0`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c008f4f0`
- `0x1c008f680`
- `0x1c0099f54`
- `0x1c00b0480`
- `0x1c00b0900`
- `0x1c00b29fc`
- `0x1c0133964`
- `0x1c013a0b4`
- `0x1c013a124`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x1c00e5a4f`
- `ntoskrnl!IoGetRequestorProcess` at `0x1c00e5a4f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00b089d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00e5cc0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00b089d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00e5cc0`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1c00b0516`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1c00b0516`
- `ntoskrnl!PsGetProcessId` at `0x1c00e5a5e`
- `ntoskrnl!PsGetProcessId` at `0x1c00e5a5e`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b0573`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b065c`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b0691`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b06c2`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5b3b`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5b72`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5bbc`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5c19`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5c59`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5ce2`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b0573`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b065c`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b0691`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b06c2`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5b3b`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5b72`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5bbc`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5c19`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5c59`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e5ce2`
- `ntoskrnl!IofCompleteRequest` at `0x1c00b08c8`
- `ntoskrnl!IofCompleteRequest` at `0x1c00b08c8`

## pseudocode

```c
void __fastcall UlCopyRequestToIrp(__int64 a1, PIRP Irp, __int64 a3, struct _LIST_ENTRY *a4, char a5)
{
  int v9; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  int Status; // r14d
  __int64 v12; // rdx
  int v13; // ecx
  __int64 v14; // rax
  unsigned int v15; // esi
  _QWORD *v16; // r14
  int v17; // eax
  unsigned int v18; // r14d
  unsigned int v19; // r14d
  unsigned int v20; // esi
  unsigned int v21; // eax
  unsigned int v22; // esi
  unsigned __int8 v23; // bl
  PMDL v24; // rcx
  PVOID v25; // r9
  __int64 v26; // rcx
  __int64 v27; // rax
  const wchar_t *v28; // rcx
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 **Blink; // rax
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rbp
  struct _KPROCESS *RequestorProcess; // rax
  HANDLE ProcessId; // rax
  __int64 v33; // r9
  unsigned int v34; // esi
  BOOLEAN v35; // al
  __int64 v36; // rdx
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rdx
  unsigned int UserChannelBindInfoSize; // eax
  unsigned int v41; // esi
  BOOLEAN v42; // al
  __int64 v43; // rdx
  __int64 v44; // rcx
  int UserTokenBindingInfoSize; // esi
  unsigned int v46; // eax
  unsigned int v47; // eax
  PMDL MdlAddress; // rcx
  _QWORD *MappedSystemVa; // rbx
  size_t v50; // r8
  size_t v51; // r8
  ULONG Length; // r8d
  char v53; // [rsp+70h] [rbp-98h]
  int v54; // [rsp+74h] [rbp-94h] BYREF
  int v55; // [rsp+78h] [rbp-90h]
  __int128 v56; // [rsp+80h] [rbp-88h] BYREF
  __int128 v57; // [rsp+90h] [rbp-78h]
  __int128 v58; // [rsp+A0h] [rbp-68h]
  int *v59; // [rsp+B0h] [rbp-58h]

  v53 = 0;
  v9 = *(_DWORD *)(*(_QWORD *)(a3 + 8) + 276LL);
  v55 = v9;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x200000) != 0 )
  {
    RequestorProcess = IoGetRequestorProcess(Irp);
    ProcessId = PsGetProcessId(RequestorProcess);
    WPP_SF_q(11, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, ProcessId);
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( *(_DWORD *)(a3 + 40) != 1 )
    goto LABEL_11;
  Status = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
  {
    if ( a1 )
      v33 = *(_QWORD *)(a1 + 64);
    else
      v33 = 0;
    WPP_SF_qq(253, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, v33);
  }
  if ( !*(_BYTE *)(a1 + 1834) )
  {
    Status = PsChargeProcessPoolQuota(
               *(PEPROCESS *)(*(_QWORD *)(a1 + 1728) + 72LL),
               (POOL_TYPE)512,
               *(unsigned int *)(a1 + 1628));
    if ( Status >= 0 )
      *(_BYTE *)(a1 + 1834) = 1;
  }
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_D(254, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  if ( Status >= 0 )
  {
LABEL_11:
    v54 = 0;
    v56 = 0;
    v59 = 0;
    v57 = 0;
    v58 = 0;
    if ( IoIs32bitProcess(Irp) )
    {
      LOBYTE(v12) = 1;
      v13 = 12 * *(unsigned __int16 *)(a1 + 1964) + 536;
    }
    else
    {
      LOBYTE(v12) = 0;
      v13 = 24 * *(unsigned __int16 *)(a1 + 1964) + 928;
    }
    v14 = *(_QWORD *)(a1 + 24);
    v15 = v13 + *(_DWORD *)(a1 + 1960);
    if ( !*(_BYTE *)(v14 + 369) )
      goto LABEL_20;
    BYTE8(v56) = v12;
    v59 = &v54;
    v16 = (_QWORD *)(v14 + 384);
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
      WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, v14 + 384, 35, &v56, 0, 0, 0);
    Status = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD, _QWORD, _QWORD))(v16[1] + 120LL))(
               *v16,
               35,
               &v56,
               0,
               0,
               0);
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
      WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
    if ( Status >= 0 )
    {
      v15 = v54 + ((v15 + 7) & 0xFFFFFFF8);
LABEL_20:
      v17 = *(_DWORD *)(a1 + 2248);
      if ( (v17 & 1) != 0 && (v17 & 2) == 0 )
      {
        v34 = (v15 + 7) & 0xFFFFFFF8;
        v35 = IoIs32bitProcess(Irp);
        v37 = a1 + 2248;
        if ( v35 )
        {
          LOBYTE(v36) = 1;
          v38 = UlGetUserAuthInfoSize(v37, v36) + 12;
        }
        else
        {
          v38 = UlGetUserAuthInfoSize(v37, 0) + 16;
        }
        v15 = v38 + v34;
      }
      v18 = v15;
      if ( (unsigned __int8)UlChannelBindRequestInfoPresent(a1, v12) )
      {
        if ( IoIs32bitProcess(Irp) )
        {
          LOBYTE(v39) = 1;
          UserChannelBindInfoSize = UlGetUserChannelBindInfoSize(a1, v39);
          v41 = (v15 + 15) & 0xFFFFFFFC;
        }
        else
        {
          v41 = UlGetUserChannelBindInfoSize(a1, 0);
          UserChannelBindInfoSize = (v18 + 23) & 0xFFFFFFF8;
        }
        v15 = UserChannelBindInfoSize + v41;
      }
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 369LL) )
      {
        if ( IoIs32bitProcess(Irp) )
          v15 = ((v15 + 15) & 0xFFFFFFFC) + 28;
        else
          v15 = ((v15 + 7) & 0xFFFFFFF8) + 44;
      }
      v19 = v15;
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 24) + 768LL) )
      {
        v42 = IoIs32bitProcess(Irp);
        v44 = *(_QWORD *)(a1 + 24) + 768LL;
        if ( v42 )
        {
          LOBYTE(v43) = 1;
          UserTokenBindingInfoSize = UlGetUserTokenBindingInfoSize(v44, v43);
          v46 = (v19 + 15) & 0xFFFFFFFC;
        }
        else
        {
          UserTokenBindingInfoSize = UlGetUserTokenBindingInfoSize(v44, 0);
          v46 = (v19 + 23) & 0xFFFFFFF8;
        }
        v15 = v46 + UserTokenBindingInfoSize;
      }
      if ( IoIs32bitProcess(Irp) )
        v20 = (v15 + 275) & 0xFFFFFFFC;
      else
        v20 = (v15 + 287) & 0xFFFFFFF8;
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 370LL) )
      {
        if ( IoIs32bitProcess(Irp) )
          v21 = (v20 + 83) & 0xFFFFFFFC;
        else
          v21 = (v20 + 95) & 0xFFFFFFF8;
        v22 = v21 + 136;
      }
      else if ( IoIs32bitProcess(Irp) )
      {
        v22 = ((v20 + 71) & 0xFFFFFFFC) + 192;
      }
      else
      {
        v22 = ((v20 + 63) & 0xFFFFFFF8) + 208;
      }
      if ( (_WORD)v9 != 1 || HIWORD(v55) )
      {
        v23 = 0;
      }
      else
      {
        v23 = 1;
        v53 = 1;
      }
      if ( v22 > CurrentStackLocation->Parameters.Read.Length )
      {
        if ( IoIs32bitProcess(Irp) )
        {
          v47 = 8 * (v23 ^ 1) + 464;
        }
        else
        {
          v47 = 864;
          if ( v23 )
            v47 = 848;
        }
        if ( CurrentStackLocation->Parameters.Read.Length >= v47 )
        {
          MdlAddress = Irp->MdlAddress;
          if ( (MdlAddress->MdlFlags & 5) != 0 )
            MappedSystemVa = MdlAddress->MappedSystemVa;
          else
            MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000000u);
          if ( MappedSystemVa )
          {
            if ( IoIs32bitProcess(Irp) )
            {
              v50 = 464;
              if ( !v53 )
                v50 = 472;
              memset(MappedSystemVa, 0, v50);
              MappedSystemVa[2] = *(_QWORD *)(a1 + 56);
              MappedSystemVa[1] = *(_QWORD *)(a1 + 32);
              MappedSystemVa[56] = *(_QWORD *)(a1 + 40);
            }
            else
            {
              v51 = 848;
              if ( !v53 )
                v51 = 864;
              memset(MappedSystemVa, 0, v51);
              MappedSystemVa[2] = *(_QWORD *)(a1 + 56);
              MappedSystemVa[1] = *(_QWORD *)(a1 + 32);
              MappedSystemVa[104] = *(_QWORD *)(a1 + 40);
            }
            Status = -2147483643;
            Irp->IoStatus.Information = v22;
          }
          else
          {
            Status = -1073741670;
          }
        }
        else
        {
          Status = -1073741789;
        }
      }
      else
      {
        v24 = Irp->MdlAddress;
        if ( (v24->MdlFlags & 5) != 0 )
          v25 = v24->MappedSystemVa;
        else
          v25 = MmMapLockedPagesSpecifyCache(v24, 0, MmCached, 0, 0, 0x40000000u);
        if ( v25 )
        {
          UlpCopyRequestToBuffer(
            a1,
            Irp,
            LODWORD(Irp->MdlAddress->StartVa) + Irp->MdlAddress->ByteOffset,
            CurrentStackLocation->Parameters.Read.Length,
            (int)Irp->AssociatedIrp.MasterIrp->MdlAddress,
            a5,
            (__int64)&Irp->IoStatus);
          Status = Irp->IoStatus.Status;
        }
        else
        {
          Status = -1073741670;
        }
      }
    }
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x4000) != 0 )
  {
    if ( CurrentStackLocation )
      Length = CurrentStackLocation->Parameters.Read.Length;
    else
      LOBYTE(Length) = 0;
    WPP_SF_dqiqZLSiqdP(
      *(_QWORD *)(a3 + 8) + 152,
      *(_QWORD *)(a3 + 8),
      Status,
      a1,
      *(_QWORD *)(a1 + 56),
      *(_QWORD *)(a3 + 8),
      *(_QWORD *)(a3 + 8) + 152LL,
      *(_DWORD *)(a1 + 1392),
      *(_QWORD *)(a1 + 2016),
      *(_QWORD *)(a1 + 32),
      (char)Irp,
      Length,
      Irp->IoStatus.Information);
  }
  Irp->IoStatus.Status = Status;
  if ( (int)(Status + 0x80000000) < 0 || Status == -2147483643 )
  {
    v26 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 960LL);
    if ( *(_BYTE *)(v26 + 1568) )
    {
      v56 = (unsigned __int64)(a1 + 72);
      v27 = *(_QWORD *)(a3 + 8);
      *(_QWORD *)&v57 = v26;
      *(_DWORD *)((char *)&v57 + 9) = 0;
      *(_WORD *)((char *)&v57 + 13) = 0;
      v28 = *(const wchar_t **)(v27 + 160);
      HIBYTE(v57) = 0;
      if ( !v28 )
        v28 = L"<<unnamed>>";
      BYTE8(v57) = 0;
      McTemplateK0pxqzzq_UlEtwWriteEventWrapper(
        (_DWORD)v28,
        0x80000000,
        (unsigned int)&v56,
        a1,
        *(_QWORD *)(a1 + 56),
        *(_DWORD *)(a1 + 1392),
        (__int64)v28,
        *(_QWORD *)(a1 + 2016),
        Status);
    }
    if ( Status == -2147483643 )
      UlStartRequestQueueTimer(a1);
  }
  else
  {
    UlCloseConnection(*(_QWORD *)(a1 + 24));
  }
  if ( a4 )
  {
    Blink = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 **)a4->Blink;
    p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&Irp->Tail.Overlay.ListEntry;
    if ( *Blink != (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)a4 )
      __fastfail(3u);
    p_ListEntry->ListEntry.Flink = a4;
    p_ListEntry->ListEntry.Blink = (struct _LIST_ENTRY *)Blink;
    *Blink = p_ListEntry;
    a4->Blink = &p_ListEntry->ListEntry;
  }
  else
  {
    IofCompleteRequest(Irp, 0);
  }
}

```

## disassembly

```asm
0x1c00b0480  push    rbx
0x1c00b0482  push    rbp
0x1c00b0483  push    rsi
0x1c00b0484  push    rdi
0x1c00b0485  push    r12
0x1c00b0487  push    r13
0x1c00b0489  push    r14
0x1c00b048b  push    r15
0x1c00b048d  sub     rsp, 0C8h
0x1c00b0494  mov     rax, cs:__security_cookie
0x1c00b049b  xor     rax, rsp
0x1c00b049e  mov     [rsp+108h+var_50], rax
0x1c00b04a6  mov     rax, [r8+8]
0x1c00b04aa  mov     r15, r9
0x1c00b04ad  mov     r13, r8
0x1c00b04b0  mov     [rsp+108h+var_98], 0
0x1c00b04b5  mov     rbp, rdx
0x1c00b04b8  mov     rdi, rcx
0x1c00b04bb  mov     ebx, [rax+114h]
0x1c00b04c1  mov     [rsp+108h+var_90], ebx
0x1c00b04c5  test    dword ptr cs:WPP_MAIN_CB.Queue, 200000h
0x1c00b04cf  jnz     loc_1C00E5A4C
0x1c00b04d5  mov     r12, [rbp+0B8h]
0x1c00b04dc  xor     esi, esi
0x1c00b04de  cmp     dword ptr [r13+28h], 1
0x1c00b04e3  jnz     short loc_1C00B0547
0x1c00b04e5  mov     r14d, esi
0x1c00b04e8  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00b04ee  test    al, al
0x1c00b04f0  js      loc_1C00E5A84
0x1c00b04f6  cmp     [rdi+72Ah], sil
0x1c00b04fd  jnz     short loc_1C00B0530
0x1c00b04ff  mov     rcx, [rdi+6C0h]
0x1c00b0506  mov     edx, 200h; PoolType
0x1c00b050b  mov     r8d, [rdi+65Ch]; Amount
0x1c00b0512  mov     rcx, [rcx+48h]; Process
0x1c00b0516  call    cs:__imp_PsChargeProcessPoolQuota
0x1c00b051d  nop     dword ptr [rax+rax+00h]
0x1c00b0522  mov     r14d, eax
0x1c00b0525  test    eax, eax
0x1c00b0527  js      short loc_1C00B0530
0x1c00b0529  mov     byte ptr [rdi+72Ah], 1
0x1c00b0530  mov     ecx, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00b0536  test    cl, cl
0x1c00b0538  js      loc_1C00E5AAC
0x1c00b053e  test    r14d, r14d
0x1c00b0541  js      loc_1C00B0760
0x1c00b0547  xorps   xmm0, xmm0
0x1c00b054a  mov     [rsp+108h+var_94], esi
0x1c00b054e  xor     eax, eax
0x1c00b0550  mov     rcx, rbp; Irp
0x1c00b0553  movups  [rsp+108h+var_88], xmm0
0x1c00b055b  mov     [rsp+108h+var_58], rax
0x1c00b0563  movups  [rsp+108h+var_78], xmm0
0x1c00b056b  movups  [rsp+108h+var_68], xmm0
0x1c00b0573  call    cs:__imp_IoIs32bitProcess
0x1c00b057a  nop     dword ptr [rax+rax+00h]
0x1c00b057f  movzx   ecx, word ptr [rdi+7ACh]
0x1c00b0586  test    al, al
0x1c00b0588  lea     eax, [rcx+rcx*2]
0x1c00b058b  jnz     loc_1C00E5AC6
0x1c00b0591  xor     dl, dl
0x1c00b0593  lea     ecx, ds:3A0h[rax*8]
0x1c00b059a  mov     rax, [rdi+18h]
0x1c00b059e  mov     esi, [rdi+7A8h]
0x1c00b05a4  add     esi, ecx
0x1c00b05a6  cmp     byte ptr [rax+171h], 0
0x1c00b05ad  jz      short loc_1C00B062B
0x1c00b05af  lea     rcx, [rsp+108h+var_94]
0x1c00b05b4  mov     byte ptr [rsp+108h+var_88+8], dl
0x1c00b05bb  mov     [rsp+108h+var_58], rcx
0x1c00b05c3  lea     r14, [rax+180h]
0x1c00b05ca  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00b05d4  jnz     loc_1C00E5AD4
0x1c00b05da  mov     rax, [r14+8]
0x1c00b05de  lea     r8, [rsp+108h+var_88]
0x1c00b05e6  xor     ecx, ecx
0x1c00b05e8  xor     r9d, r9d
0x1c00b05eb  mov     qword ptr [rsp+108h+Priority], rcx
0x1c00b05f0  mov     qword ptr [rsp+108h+BugCheckOnFailure], rcx
0x1c00b05f5  mov     rax, [rax+78h]
0x1c00b05f9  lea     edx, [rcx+23h]
0x1c00b05fc  mov     rcx, [r14]
0x1c00b05ff  call    cs:__guard_dispatch_icall_fptr
0x1c00b0605  mov     r14d, eax
0x1c00b0608  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00b0612  jnz     loc_1C00E5B10
0x1c00b0618  test    r14d, r14d
0x1c00b061b  js      loc_1C00E5D6A
0x1c00b0621  add     esi, 7
0x1c00b0624  and     esi, 0FFFFFFF8h
0x1c00b0627  add     esi, [rsp+108h+var_94]
0x1c00b062b  mov     eax, [rdi+8C8h]
0x1c00b0631  test    al, 1
0x1c00b0633  jnz     loc_1C00E5B2A
0x1c00b0639  mov     rcx, rdi
0x1c00b063c  mov     r14d, esi
0x1c00b063f  call    UlChannelBindRequestInfoPresent
0x1c00b0644  test    al, al
0x1c00b0646  jnz     loc_1C00E5B6F
0x1c00b064c  mov     rax, [rdi+18h]
0x1c00b0650  cmp     byte ptr [rax+171h], 0
0x1c00b0657  jz      short loc_1C00B0679
0x1c00b0659  mov     rcx, rbp; Irp
0x1c00b065c  call    cs:__imp_IoIs32bitProcess
0x1c00b0663  nop     dword ptr [rax+rax+00h]
0x1c00b0668  test    al, al
0x1c00b066a  jnz     loc_1C00E5BAB
0x1c00b0670  add     esi, 7
0x1c00b0673  and     esi, 0FFFFFFF8h
0x1c00b0676  add     esi, 2Ch ; ','
0x1c00b0679  mov     rax, [rdi+18h]
0x1c00b067d  mov     r14d, esi
0x1c00b0680  cmp     qword ptr [rax+300h], 0
0x1c00b0688  jnz     loc_1C00E5BB9
0x1c00b068e  mov     rcx, rbp; Irp
0x1c00b0691  call    cs:__imp_IoIs32bitProcess
0x1c00b0698  nop     dword ptr [rax+rax+00h]
0x1c00b069d  test    al, al
0x1c00b069f  jnz     loc_1C00E5C00
0x1c00b06a5  add     esi, 11Fh
0x1c00b06ab  and     esi, 0FFFFFFF8h
0x1c00b06ae  mov     rax, [rdi+18h]
0x1c00b06b2  mov     rcx, rbp; Irp
0x1c00b06b5  cmp     byte ptr [rax+172h], 0
0x1c00b06bc  jz      loc_1C00E5C19
0x1c00b06c2  call    cs:__imp_IoIs32bitProcess
0x1c00b06c9  nop     dword ptr [rax+rax+00h]
0x1c00b06ce  test    al, al
0x1c00b06d0  jnz     loc_1C00E5C0E
0x1c00b06d6  lea     eax, [rsi+5Fh]
0x1c00b06d9  and     eax, 0FFFFFFF8h
0x1c00b06dc  lea     esi, [rax+88h]
0x1c00b06e2  cmp     bx, 1
0x1c00b06e6  jz      loc_1C00B08D6
0x1c00b06ec  xor     bl, bl
0x1c00b06ee  cmp     esi, [r12+8]
0x1c00b06f3  ja      loc_1C00E5C56
0x1c00b06f9  mov     rcx, [rbp+8]; MemoryDescriptorList
0x1c00b06fd  xor     esi, esi
0x1c00b06ff  test    byte ptr [rcx+0Ah], 5
0x1c00b0703  jz      loc_1C00B0888
0x1c00b0709  mov     r9, [rcx+18h]
0x1c00b070d  test    r9, r9
0x1c00b0710  jz      loc_1C00E5C4B
0x1c00b0716  mov     rax, [rbp+8]
0x1c00b071a  lea     rbx, [rbp+30h]
0x1c00b071e  mov     rcx, [rbp+18h]
0x1c00b0722  mov     r8, r13
0x1c00b0725  mov     [rsp+108h+var_C8], rbx; __int64
0x1c00b072a  mov     edx, [rax+2Ch]
0x1c00b072d  add     rdx, [rax+20h]
0x1c00b0731  movzx   eax, [rsp+108h+arg_20]
0x1c00b0739  mov     [rsp+108h+var_D0], al; char
0x1c00b073d  mov     eax, [rcx+8]
0x1c00b0740  mov     rcx, rdi; int
0x1c00b0743  mov     [rsp+108h+var_D8], eax; int
0x1c00b0747  mov     eax, [r12+8]
0x1c00b074c  mov     [rsp+108h+Priority], eax; int
0x1c00b0750  mov     qword ptr [rsp+108h+BugCheckOnFailure], rdx; int
0x1c00b0755  mov     rdx, rbp; Irp
0x1c00b0758  call    UlpCopyRequestToBuffer
0x1c00b075d  mov     r14d, [rbx]
0x1c00b0760  test    dword ptr cs:WPP_MAIN_CB.Queue, 4000h
0x1c00b076a  jnz     loc_1C00E5D71
0x1c00b0770  mov     edx, 80000000h
0x1c00b0775  mov     [rbp+30h], r14d
0x1c00b0779  lea     eax, [r14+rdx]
0x1c00b077d  test    edx, eax
0x1c00b077f  jz      loc_1C00B08B1
0x1c00b0785  mov     rax, [rdi+18h]
0x1c00b0789  mov     rcx, [rax+3C0h]
0x1c00b0790  cmp     byte ptr [rcx+620h], 0
0x1c00b0797  jz      loc_1C00B082A
0x1c00b079d  mov     dword ptr [rsp+108h+var_C8], r14d
0x1c00b07a2  lea     rax, [rdi+48h]
0x1c00b07a6  mov     qword ptr [rsp+108h+var_88], rax
0x1c00b07ae  lea     r8, [rsp+108h+var_88]
0x1c00b07b6  mov     rax, [r13+8]
0x1c00b07ba  mov     r9, rdi
0x1c00b07bd  mov     qword ptr [rsp+108h+var_78], rcx
0x1c00b07c5  mov     dword ptr [rsp+108h+var_78+9], esi
0x1c00b07cc  mov     word ptr [rsp+108h+var_78+0Dh], si
0x1c00b07d4  mov     rcx, [rax+0A0h]
0x1c00b07db  lea     rax, aUnnamed; "<<unnamed>>"
0x1c00b07e2  test    rcx, rcx
0x1c00b07e5  mov     byte ptr [rsp+108h+var_78+0Fh], 0
0x1c00b07ed  mov     qword ptr [rsp+108h+var_88+8], rsi
0x1c00b07f5  cmovz   rcx, rax
0x1c00b07f9  mov     byte ptr [rsp+108h+var_78+8], 0
0x1c00b0801  mov     rax, [rdi+7E0h]
0x1c00b0808  mov     qword ptr [rsp+108h+var_D0], rax
0x1c00b080d  mov     eax, [rdi+570h]
0x1c00b0813  mov     qword ptr [rsp+108h+var_D8], rcx
0x1c00b0818  mov     [rsp+108h+Priority], eax
0x1c00b081c  mov     rax, [rdi+38h]
0x1c00b0820  mov     qword ptr [rsp+108h+BugCheckOnFailure], rax
0x1c00b0825  call    McTemplateK0pxqzzq_UlEtwWriteEventWrapper
0x1c00b082a  cmp     r14d, 80000005h
0x1c00b0831  jz      loc_1C00E5DF2
0x1c00b0837  test    r15, r15
0x1c00b083a  jz      loc_1C00B08C3
0x1c00b0840  mov     rax, [r15+8]
0x1c00b0844  add     rbp, 0A8h
0x1c00b084b  cmp     [rax], r15
0x1c00b084e  jnz     loc_1C00E5E00
0x1c00b0854  mov     [rbp+0], r15
0x1c00b0858  mov     [rbp+8], rax
0x1c00b085c  mov     [rax], rbp
0x1c00b085f  mov     [r15+8], rbp
0x1c00b0863  mov     rcx, [rsp+108h+var_50]
0x1c00b086b  xor     rcx, rsp; StackCookie
0x1c00b086e  call    __security_check_cookie
0x1c00b0873  add     rsp, 0C8h
0x1c00b087a  pop     r15
0x1c00b087c  pop     r14
0x1c00b087e  pop     r13
0x1c00b0880  pop     r12
0x1c00b0882  pop     rdi
0x1c00b0883  pop     rsi
0x1c00b0884  pop     rbp
0x1c00b0885  pop     rbx
0x1c00b0886  retn
0x1c00b0888  xor     r9d, r9d; RequestedAddress
0x1c00b088b  mov     [rsp+108h+Priority], 40000000h; Priority
0x1c00b0893  xor     edx, edx; AccessMode
0x1c00b0895  mov     [rsp+108h+BugCheckOnFailure], esi; BugCheckOnFailure
0x1c00b0899  lea     r8d, [r9+1]; CacheType
0x1c00b089d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1c00b08a4  nop     dword ptr [rax+rax+00h]
0x1c00b08a9  mov     r9, rax
0x1c00b08ac  jmp     loc_1C00B070D
0x1c00b08b1  cmp     r14d, 80000005h
0x1c00b08b8  jz      loc_1C00B0785
0x1c00b08be  jmp     loc_1C00E5DE1
0x1c00b08c3  xor     edx, edx; PriorityBoost
0x1c00b08c5  mov     rcx, rbp; Irp
0x1c00b08c8  call    cs:__imp_IofCompleteRequest
0x1c00b08cf  nop     dword ptr [rax+rax+00h]
0x1c00b08d4  jmp     short loc_1C00B0863
0x1c00b08d6  cmp     word ptr [rsp+108h+var_90+2], 0
0x1c00b08dc  jnz     loc_1C00B06EC
0x1c00b08e2  mov     bl, 1
0x1c00b08e4  mov     [rsp+108h+var_98], bl
0x1c00b08e8  jmp     loc_1C00B06EE
0x1c00e5a4c  mov     rcx, rbp; Irp
0x1c00e5a4f  call    cs:__imp_IoGetRequestorProcess
0x1c00e5a56  nop     dword ptr [rax+rax+00h]
0x1c00e5a5b  mov     rcx, rax; Process
0x1c00e5a5e  call    cs:__imp_PsGetProcessId
0x1c00e5a65  nop     dword ptr [rax+rax+00h]
0x1c00e5a6a  mov     ecx, 0Bh
0x1c00e5a6f  lea     rdx, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids
0x1c00e5a76  mov     r8, rax
0x1c00e5a79  call    WPP_SF_q
0x1c00e5a7e  nop
0x1c00e5a7f  jmp     loc_1C00B04D5
0x1c00e5a84  test    rdi, rdi
0x1c00e5a87  jz      short loc_1C00E5A8F
0x1c00e5a89  mov     r9, [rdi+40h]
0x1c00e5a8d  jmp     short loc_1C00E5A92
0x1c00e5a8f  mov     r9, rsi
0x1c00e5a92  mov     ecx, 0FDh
0x1c00e5a97  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00e5a9e  mov     r8, rdi
0x1c00e5aa1  call    WPP_SF_qq
0x1c00e5aa6  nop
0x1c00e5aa7  jmp     loc_1C00B04F6
0x1c00e5aac  mov     ecx, 0FEh
0x1c00e5ab1  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00e5ab8  mov     r8d, r14d
0x1c00e5abb  call    WPP_SF_D
0x1c00e5ac0  nop
0x1c00e5ac1  jmp     loc_1C00B053E
0x1c00e5ac6  mov     dl, 1
0x1c00e5ac8  lea     ecx, ds:218h[rax*4]
0x1c00e5acf  jmp     loc_1C00B059A
0x1c00e5ad4  xor     eax, eax
0x1c00e5ad6  lea     rdx, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids
0x1c00e5add  mov     qword ptr [rsp+108h+var_D0], rax
0x1c00e5ae2  mov     ecx, 0Ah
0x1c00e5ae7  mov     qword ptr [rsp+108h+var_D8], rax
0x1c00e5aec  mov     r8, r14
0x1c00e5aef  mov     qword ptr [rsp+108h+Priority], rax
0x1c00e5af4  lea     rax, [rsp+108h+var_88]
0x1c00e5afc  mov     qword ptr [rsp+108h+BugCheckOnFailure], rax
0x1c00e5b01  lea     r9d, [rcx+19h]
0x1c00e5b05  call    WPP_SF_qLqqqq
0x1c00e5b0a  nop
0x1c00e5b0b  jmp     loc_1C00B05DA
0x1c00e5b10  mov     ecx, 0Bh
0x1c00e5b15  lea     rdx, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids
0x1c00e5b1c  mov     r8d, r14d
0x1c00e5b1f  call    WPP_SF_D
0x1c00e5b24  nop
0x1c00e5b25  jmp     loc_1C00B0618
0x1c00e5b2a  test    al, 2
0x1c00e5b2c  jnz     loc_1C00B0639
0x1c00e5b32  add     esi, 7
0x1c00e5b35  mov     rcx, rbp; Irp
  ... truncated ...
```
