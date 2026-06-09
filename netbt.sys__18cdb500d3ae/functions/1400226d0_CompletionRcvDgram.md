# CompletionRcvDgram

- ea: `0x1400226d0`
- end: `0x140022cfb`
- name: `CompletionRcvDgram`
- size: `1579`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140003d04`
- `0x140004038`
- `0x140006878`
- `0x1400226d0`
- `0x140022d04`
- `0x140030f80`
- `0x140040590`
- `0x140042f5c`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140022769`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140022769`
- `ntoskrnl!IofCompleteRequest` at `0x1400229a2`
- `ntoskrnl!IofCompleteRequest` at `0x140022bfa`
- `ntoskrnl!IofCompleteRequest` at `0x1400229a2`
- `ntoskrnl!IofCompleteRequest` at `0x140022bfa`
- `ntoskrnl!IoFreeMdl` at `0x140022abd`
- `ntoskrnl!IoFreeMdl` at `0x140022abd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002279c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400227da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400229b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400229c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022c1e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022c31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002279c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400227da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400229b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400229c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022c1e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140022c31`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400228c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400228d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400229f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022a0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022bba`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022bd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022c5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022c70`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400228c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400228d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400229f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022a0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022bba`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022bd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022c5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022c70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022c0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022cb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022cca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022c0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022cb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022cca`
- `TDI!TdiCopyBufferToMdl` at `0x14002296d`
- `TDI!TdiCopyBufferToMdl` at `0x140022b52`
- `TDI!TdiCopyBufferToMdl` at `0x14002296d`
- `TDI!TdiCopyBufferToMdl` at `0x140022b52`

## pseudocode

```c
__int64 __fastcall CompletionRcvDgram(__int64 a1, __int64 a2, _QWORD *a3)
{
  void *v3; // r15
  _QWORD *v4; // rbx
  __int64 v5; // rsi
  ULONG v6; // r13d
  __int64 v7; // rcx
  PVOID v8; // r12
  KIRQL v9; // al
  _QWORD *v10; // rcx
  KIRQL v11; // dl
  _QWORD *v12; // rdi
  KIRQL v13; // si
  KSPIN_LOCK *v14; // rbx
  char v15; // cl
  KIRQL v16; // al
  __int64 v17; // rdx
  __int64 v19; // r8
  _QWORD *v20; // rax
  _QWORD *v21; // rsi
  __int64 v22; // rcx
  KIRQL v23; // al
  __int64 v24; // rdx
  KIRQL NewIrql; // [rsp+68h] [rbp-29h]
  ULONG BytesCopied; // [rsp+6Ch] [rbp-25h] BYREF
  ULONG SourceOffset; // [rsp+70h] [rbp-21h] BYREF
  PIRP Irp; // [rsp+78h] [rbp-19h] BYREF
  PKSPIN_LOCK SpinLock; // [rsp+80h] [rbp-11h]
  int v30; // [rsp+88h] [rbp-9h]
  __int64 v31; // [rsp+90h] [rbp-1h]
  _DWORD *v32; // [rsp+98h] [rbp+7h]
  _QWORD *v33; // [rsp+A0h] [rbp+Fh]
  __int64 v34; // [rsp+A8h] [rbp+17h]
  void (__fastcall *v35)(__int64, _QWORD, _DWORD *, _QWORD, _QWORD, int, ULONG, ULONG, ULONG *, PVOID, PIRP *); // [rsp+B0h] [rbp+1Fh]
  PIRP v38; // [rsp+108h] [rbp+77h]
  KIRQL v39; // [rsp+110h] [rbp+7Fh]
  unsigned int v40; // [rsp+110h] [rbp+7Fh]

  v3 = 0;
  v4 = a3;
  BytesCopied = 0;
  v5 = a2;
  SourceOffset = 0;
  if ( (BYTE2(xmmword_140038420) & 4) != 0 )
    WPP_SF_qDP(a1, 65, a3, a3, *(_DWORD *)(a2 + 48), *(_QWORD *)(a2 + 56));
  if ( !v4 )
    return 0;
  if ( *(int *)(v5 + 48) < 0 )
    v6 = 0;
  else
    v6 = *(_DWORD *)(v5 + 56);
  v7 = *(_QWORD *)(v5 + 8);
  if ( (*(_BYTE *)(v7 + 10) & 5) != 0 )
    v8 = *(PVOID *)(v7 + 24);
  else
    v8 = MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000020u);
  if ( !*((_BYTE *)v4 + 41) )
  {
    v39 = KeAcquireSpinLockRaiseToDpc(&::SpinLock);
    v31 = *(_QWORD *)(*(_QWORD *)(v4[4] + 32LL) + 560LL);
    v32 = (_DWORD *)v4[2];
    v30 = *((_DWORD *)v4 + 2);
    SpinLock = (PKSPIN_LOCK)(*v4 + 56LL);
    v9 = KeAcquireSpinLockRaiseToDpc(SpinLock);
    v10 = (_QWORD *)(*v4 + 24LL);
    NewIrql = v9;
    v11 = v9;
    v33 = v10;
    v12 = (_QWORD *)*v10;
    if ( !*((_BYTE *)v4 + 40) )
    {
      if ( v12 != v10 )
      {
        v13 = v39;
        v14 = SpinLock;
        do
        {
          Irp = 0;
          if ( *((_DWORD *)v12 + 4) == 829320259 && *(_QWORD *)(v12[4] + 560LL) == v31 )
          {
            v15 = *((_BYTE *)v12 + 272);
            v35 = (void (__fastcall *)(__int64, _QWORD, _DWORD *, _QWORD, _QWORD, int, ULONG, ULONG, ULONG *, PVOID, PIRP *))v12[27];
            v34 = v12[28];
            v40 = v15 != 0 ? 44 : 26;
            *v32 = (v15 != 0) + 1;
            if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
            {
              WPP_SF_qddds(
                *((_DWORD *)v12 + 5),
                13,
                (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
                (_DWORD)v12,
                *((_DWORD *)v12 + 5),
                *((_DWORD *)v12 + 5) + 1,
                113,
                (__int64)"minio\\netbt\\sys\\nt\\tdihndlr.c");
              v11 = NewIrql;
            }
            _InterlockedIncrement((volatile signed __int32 *)v12 + 5);
            KeReleaseSpinLock(v14, v11);
            KeReleaseSpinLock(&::SpinLock, v13);
            if ( v3 )
              NbtDereferenceClient(v3);
            v3 = v12;
            Irp = 0;
            SourceOffset = 0;
            v35(v34, v40, v32, 0, 0, v30, v6, v6, &SourceOffset, v8, &Irp);
            if ( Irp )
            {
              TdiCopyBufferToMdl(v8, SourceOffset, v6 - SourceOffset, Irp->MdlAddress, 0, &BytesCopied);
              Irp->IoStatus.Status = BytesCopied < v6 - SourceOffset ? 0x80000005 : 0;
              Irp->IoStatus.Information = BytesCopied;
              IofCompleteRequest(Irp, 2);
            }
            v13 = KeAcquireSpinLockRaiseToDpc(&::SpinLock);
            v16 = KeAcquireSpinLockRaiseToDpc(v14);
            v10 = v33;
            v11 = v16;
            NewIrql = v16;
          }
          v12 = (_QWORD *)*v12;
        }
        while ( v12 != v10 );
        v4 = a3;
        v39 = v13;
        v5 = a2;
      }
      KeReleaseSpinLock(SpinLock, v11);
      KeReleaseSpinLock(&::SpinLock, v39);
      if ( v3 )
        NbtDereferenceClient(v3);
      NbtDereferenceClient((PVOID)v4[4]);
      NbtDereferenceAddress(*v4, v17, 3915, "minio\\netbt\\sys\\nt\\tdihndlr.c");
      goto LABEL_29;
    }
    if ( v12 != v10 )
    {
      v19 = v31;
      do
      {
        while ( *(_QWORD *)(v12[4] + 560LL) != v19 )
          ;
        if ( v12 != (_QWORD *)v4[4] )
        {
          v20 = v12 + 13;
          v21 = (_QWORD *)v12[13];
          if ( v21 != v12 + 13 )
          {
            if ( (_QWORD *)v21[1] != v20 || (v22 = *v21, *(_QWORD **)(*v21 + 8LL) != v21) )
              __fastfail(3u);
            *v20 = v22;
            *(_QWORD *)(v22 + 8) = v20;
            v38 = (PIRP)v21[2];
            TdiCopyBufferToMdl(v8, 0, v6, v38->MdlAddress, 0, &BytesCopied);
            v38->IoStatus.Status = BytesCopied < v6 ? 0x80000005 : 0;
            v38->IoStatus.Information = BytesCopied;
            if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
              WPP_SF_qddds(
                *((_DWORD *)v12 + 5),
                13,
                (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
                (_DWORD)v12,
                *((_DWORD *)v12 + 5),
                *((_DWORD *)v12 + 5) + 1,
                5,
                (__int64)"minio\\netbt\\sys\\nt\\tdihndlr.c");
            _InterlockedIncrement((volatile signed __int32 *)v12 + 5);
            KeReleaseSpinLock(SpinLock, NewIrql);
            KeReleaseSpinLock(&::SpinLock, v39);
            if ( v3 )
              NbtDereferenceClient(v3);
            v3 = v12;
            IofCompleteRequest(v38, 2);
            ExFreePoolWithTag(v21, 0);
            v39 = KeAcquireSpinLockRaiseToDpc(&::SpinLock);
            v23 = KeAcquireSpinLockRaiseToDpc(SpinLock);
            v10 = v33;
            v11 = v23;
            v19 = v31;
            NewIrql = v23;
          }
        }
        v12 = (_QWORD *)*v12;
      }
      while ( v12 != v10 );
    }
    KeReleaseSpinLock(SpinLock, v11);
    KeReleaseSpinLock(&::SpinLock, v39);
    if ( v3 )
      NbtDereferenceClient(v3);
    NbtDereferenceClient((PVOID)v4[4]);
    NbtDereferenceAddress(*v4, v24, 3884, "minio\\netbt\\sys\\nt\\tdihndlr.c");
    ExFreePoolWithTag((PVOID)v4[2], 0);
    ExFreePoolWithTag(v4, 0);
    return 0;
  }
  ProxyDoDgramDist(v8, v6, (PVOID)*v4);
LABEL_29:
  if ( !*((_BYTE *)v4 + 41) )
    ExFreePoolWithTag((PVOID)v4[2], 0);
  ExFreePoolWithTag(v4, 0);
  ExFreePoolWithTag(v8, 0);
  if ( (BYTE3(xmmword_140038420) & 8) != 0 )
    WPP_SF_qq(1051, 66, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids, v5, *(_QWORD *)(v5 + 8));
  IoFreeMdl(*(PMDL *)(v5 + 8));
  NbtFreeIrp((PIRP)v5);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400226d0  mov     rax, rsp
0x1400226d3  mov     [rax+8], rbx
0x1400226d7  mov     [rax+18h], r8
0x1400226db  mov     [rax+10h], rdx
0x1400226df  push    rbp
0x1400226e0  push    rsi
0x1400226e1  push    rdi
0x1400226e2  push    r12
0x1400226e4  push    r13
0x1400226e6  push    r14
0x1400226e8  push    r15
0x1400226ea  lea     rbp, [rax-5Fh]
0x1400226ee  sub     rsp, 0B0h
0x1400226f5  xor     r15d, r15d
0x1400226f8  mov     rbx, r8
0x1400226fb  mov     [rbp+57h+BytesCopied], r15d
0x1400226ff  mov     rsi, rdx
0x140022702  mov     [rbp+57h+SourceOffset], r15d
0x140022706  test    byte ptr cs:xmmword_140038420+2, 4
0x14002270d  jz      short loc_14002272B
0x14002270f  mov     rax, [rsi+38h]
0x140022713  lea     edx, [r15+41h]
0x140022717  mov     qword ptr [rsp+0E0h+Priority], rax
0x14002271c  mov     r9, rbx
0x14002271f  mov     eax, [rsi+30h]
0x140022722  mov     [rsp+0E0h+BugCheckOnFailure], eax
0x140022726  call    WPP_SF_qDP
0x14002272b  test    rbx, rbx
0x14002272e  jz      loc_140022CD6
0x140022734  cmp     [rsi+30h], r15d
0x140022738  jl      short loc_140022740
0x14002273a  mov     r13d, [rsi+38h]
0x14002273e  jmp     short loc_140022743
0x140022740  mov     r13d, r15d
0x140022743  mov     rcx, [rsi+8]; MemoryDescriptorList
0x140022747  test    byte ptr [rcx+0Ah], 5
0x14002274b  jz      short loc_140022753
0x14002274d  mov     r12, [rcx+18h]
0x140022751  jmp     short loc_140022778
0x140022753  xor     r9d, r9d; RequestedAddress
0x140022756  mov     [rsp+0E0h+Priority], 40000020h; Priority
0x14002275e  xor     edx, edx; AccessMode
0x140022760  mov     [rsp+0E0h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x140022765  lea     r8d, [r9+1]; CacheType
0x140022769  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140022770  nop     dword ptr [rax+rax+00h]
0x140022775  mov     r12, rax
0x140022778  cmp     [rbx+29h], r15b
0x14002277c  jz      short loc_140022795
0x14002277e  mov     r9, [rbx+10h]
0x140022782  mov     edx, r13d; Size
0x140022785  mov     r8, [rbx]; P
0x140022788  mov     rcx, r12; Src
0x14002278b  call    ProxyDoDgramDist
0x140022790  jmp     loc_140022A54
0x140022795  lea     rcx, SpinLock; SpinLock
0x14002279c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400227a3  nop     dword ptr [rax+rax+00h]
0x1400227a8  mov     rcx, [rbx+20h]
0x1400227ac  mov     [rbp+57h+arg_18], al
0x1400227af  mov     rdx, [rcx+20h]
0x1400227b3  mov     rax, [rdx+230h]
0x1400227ba  mov     [rbp+57h+var_58], rax
0x1400227be  mov     rax, [rbx+10h]
0x1400227c2  mov     [rbp+57h+var_50], rax
0x1400227c6  mov     eax, [rbx+8]
0x1400227c9  mov     [rbp+57h+var_60], eax
0x1400227cc  mov     rax, [rbx]
0x1400227cf  add     rax, 38h ; '8'
0x1400227d3  mov     rcx, rax; SpinLock
0x1400227d6  mov     [rbp+57h+SpinLock], rax
0x1400227da  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400227e1  nop     dword ptr [rax+rax+00h]
0x1400227e6  mov     rcx, [rbx]
0x1400227e9  lea     r14, aMinioNetbtSysN_2; "minio\\netbt\\sys\\nt\\tdihndlr.c"
0x1400227f0  add     rcx, 18h
0x1400227f4  mov     [rbp+57h+NewIrql], al
0x1400227f7  mov     dl, al
0x1400227f9  mov     [rbp+57h+var_48], rcx
0x1400227fd  mov     rdi, [rcx]
0x140022800  cmp     [rbx+28h], r15b
0x140022804  jnz     loc_140022ADB
0x14002280a  cmp     rdi, rcx
0x14002280d  jz      loc_1400229F4
0x140022813  mov     sil, [rbp+57h+arg_18]
0x140022817  mov     rbx, [rbp+57h+SpinLock]
0x14002281b  mov     [rbp+57h+Irp], 0
0x140022823  cmp     dword ptr [rdi+10h], 316E6C43h
0x14002282a  jnz     loc_1400229DC
0x140022830  mov     rax, [rdi+20h]
0x140022834  mov     r8, [rbp+57h+var_58]
0x140022838  cmp     [rax+230h], r8
0x14002283f  jnz     loc_1400229DC
0x140022845  mov     cl, [rdi+110h]
0x14002284b  mov     rax, [rdi+0D8h]
0x140022852  mov     [rbp+57h+var_38], rax
0x140022856  mov     rax, [rdi+0E0h]
0x14002285d  mov     [rbp+57h+var_40], rax
0x140022861  mov     al, cl
0x140022863  neg     al
0x140022865  sbb     eax, eax
0x140022867  and     eax, 12h
0x14002286a  add     eax, 1Ah
0x14002286d  neg     cl
0x14002286f  mov     dword ptr [rbp+57h+arg_18], eax
0x140022872  mov     rcx, [rbp+57h+var_50]
0x140022876  sbb     eax, eax
0x140022878  neg     eax
0x14002287a  inc     eax
0x14002287c  mov     [rcx], eax
0x14002287e  test    byte ptr cs:xmmword_140038420+9, 40h
0x140022885  jz      short loc_1400228B9
0x140022887  mov     ecx, [rdi+14h]
0x14002288a  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x140022891  mov     [rsp+0E0h+var_A8], r14
0x140022896  mov     edx, 0Dh
0x14002289b  mov     dword ptr [rsp+0E0h+var_B0], 0E71h
0x1400228a3  mov     r9, rdi
0x1400228a6  lea     eax, [rcx+1]
0x1400228a9  mov     [rsp+0E0h+Priority], eax
0x1400228ad  mov     [rsp+0E0h+BugCheckOnFailure], ecx
0x1400228b1  call    WPP_SF_qddds
0x1400228b6  mov     dl, [rbp+57h+NewIrql]; NewIrql
0x1400228b9  lock inc dword ptr [rdi+14h]
0x1400228bd  mov     rcx, rbx; SpinLock
0x1400228c0  call    cs:__imp_KeReleaseSpinLock
0x1400228c7  nop     dword ptr [rax+rax+00h]
0x1400228cc  mov     dl, sil; NewIrql
0x1400228cf  lea     rcx, SpinLock; SpinLock
0x1400228d6  call    cs:__imp_KeReleaseSpinLock
0x1400228dd  nop     dword ptr [rax+rax+00h]
0x1400228e2  xor     esi, esi
0x1400228e4  test    r15, r15
0x1400228e7  jz      short loc_1400228F9
0x1400228e9  mov     r8, r14
0x1400228ec  mov     edx, 0E79h
0x1400228f1  mov     rcx, r15; P
0x1400228f4  call    NbtDereferenceClient
0x1400228f9  mov     r8, [rbp+57h+var_50]
0x1400228fd  lea     rax, [rbp+57h+Irp]
0x140022901  mov     edx, dword ptr [rbp+57h+arg_18]
0x140022904  xor     r9d, r9d
0x140022907  mov     rcx, [rbp+57h+var_40]
0x14002290b  mov     r15, rdi
0x14002290e  mov     [rsp+50h], rax
0x140022913  lea     rax, [rbp+57h+SourceOffset]
0x140022917  mov     [rsp+0E0h+var_98], r12
0x14002291c  mov     [rsp+0E0h+var_A0], rax
0x140022921  mov     eax, [rbp+57h+var_60]
0x140022924  mov     dword ptr [rsp+0E0h+var_A8], r13d
0x140022929  mov     dword ptr [rsp+0E0h+var_B0], r13d
0x14002292e  mov     [rsp+0E0h+Priority], eax
0x140022932  mov     rax, [rbp+57h+var_38]
0x140022936  mov     [rbp+57h+Irp], rsi
0x14002293a  mov     [rbp+57h+SourceOffset], esi
0x14002293d  mov     qword ptr [rsp+0E0h+BugCheckOnFailure], rsi
0x140022942  call    _guard_dispatch_icall
0x140022947  mov     r9, [rbp+57h+Irp]
0x14002294b  test    r9, r9
0x14002294e  jz      short loc_1400229AE
0x140022950  mov     edx, [rbp+57h+SourceOffset]; SourceOffset
0x140022953  lea     rax, [rbp+57h+BytesCopied]
0x140022957  mov     r9, [r9+8]; DestinationMdlChain
0x14002295b  mov     r8d, r13d
0x14002295e  mov     qword ptr [rsp+0E0h+Priority], rax; BytesCopied
0x140022963  sub     r8d, edx; SourceBytesToCopy
0x140022966  mov     rcx, r12; SourceBuffer
0x140022969  mov     [rsp+0E0h+BugCheckOnFailure], esi; DestinationOffset
0x14002296d  call    cs:__imp_TdiCopyBufferToMdl
0x140022974  nop     dword ptr [rax+rax+00h]
0x140022979  mov     eax, r13d
0x14002297c  mov     dl, 2; PriorityBoost
0x14002297e  sub     eax, [rbp+57h+SourceOffset]
0x140022981  cmp     [rbp+57h+BytesCopied], eax
0x140022984  mov     rax, [rbp+57h+Irp]
0x140022988  sbb     ecx, ecx
0x14002298a  and     ecx, 80000005h
0x140022990  mov     [rax+30h], ecx
0x140022993  mov     ecx, [rbp+57h+BytesCopied]
0x140022996  mov     rax, [rbp+57h+Irp]
0x14002299a  mov     [rax+38h], rcx
0x14002299e  mov     rcx, [rbp+57h+Irp]; Irp
0x1400229a2  call    cs:__imp_IofCompleteRequest
0x1400229a9  nop     dword ptr [rax+rax+00h]
0x1400229ae  lea     rcx, SpinLock; SpinLock
0x1400229b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400229bc  nop     dword ptr [rax+rax+00h]
0x1400229c1  mov     rcx, rbx; SpinLock
0x1400229c4  mov     sil, al
0x1400229c7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400229ce  nop     dword ptr [rax+rax+00h]
0x1400229d3  mov     rcx, [rbp+57h+var_48]
0x1400229d7  mov     dl, al; NewIrql
0x1400229d9  mov     [rbp+57h+NewIrql], al
0x1400229dc  mov     rdi, [rdi]
0x1400229df  cmp     rdi, rcx
0x1400229e2  jnz     loc_14002281B
0x1400229e8  mov     rbx, [rbp+57h+arg_10]
0x1400229ec  mov     [rbp+57h+arg_18], sil
0x1400229f0  mov     rsi, [rbp+57h+arg_8]
0x1400229f4  mov     rcx, [rbp+57h+SpinLock]; SpinLock
0x1400229f8  call    cs:__imp_KeReleaseSpinLock
0x1400229ff  nop     dword ptr [rax+rax+00h]
0x140022a04  mov     dl, [rbp+57h+arg_18]; NewIrql
0x140022a07  lea     rcx, SpinLock; SpinLock
0x140022a0e  call    cs:__imp_KeReleaseSpinLock
0x140022a15  nop     dword ptr [rax+rax+00h]
0x140022a1a  test    r15, r15
0x140022a1d  jz      short loc_140022A2F
0x140022a1f  mov     r8, r14
0x140022a22  mov     edx, 0F43h
0x140022a27  mov     rcx, r15; P
0x140022a2a  call    NbtDereferenceClient
0x140022a2f  mov     rcx, [rbx+20h]; P
0x140022a33  mov     r8, r14
0x140022a36  mov     edx, 0F4Ah
0x140022a3b  call    NbtDereferenceClient
0x140022a40  mov     rcx, [rbx]
0x140022a43  mov     r9, r14
0x140022a46  mov     r8d, 0F4Bh
0x140022a4c  call    NbtDereferenceAddress
0x140022a51  xor     r15d, r15d
0x140022a54  cmp     [rbx+29h], r15b
0x140022a58  jnz     short loc_140022A6C
0x140022a5a  mov     rcx, [rbx+10h]; P
0x140022a5e  xor     edx, edx; Tag
0x140022a60  call    cs:__imp_ExFreePoolWithTag
0x140022a67  nop     dword ptr [rax+rax+00h]
0x140022a6c  xor     edx, edx; Tag
0x140022a6e  mov     rcx, rbx; P
0x140022a71  call    cs:__imp_ExFreePoolWithTag
0x140022a78  nop     dword ptr [rax+rax+00h]
0x140022a7d  xor     edx, edx; Tag
0x140022a7f  mov     rcx, r12; P
0x140022a82  call    cs:__imp_ExFreePoolWithTag
0x140022a89  nop     dword ptr [rax+rax+00h]
0x140022a8e  test    byte ptr cs:xmmword_140038420+3, 8
0x140022a95  jz      short loc_140022AB9
0x140022a97  mov     rax, [rsi+8]
0x140022a9b  lea     r8, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids
0x140022aa2  mov     edx, 42h ; 'B'
0x140022aa7  mov     qword ptr [rsp+0E0h+BugCheckOnFailure], rax
0x140022aac  mov     ecx, 41Bh
0x140022ab1  mov     r9, rsi
0x140022ab4  call    WPP_SF_qq
0x140022ab9  mov     rcx, [rsi+8]; Mdl
0x140022abd  call    cs:__imp_IoFreeMdl
0x140022ac4  nop     dword ptr [rax+rax+00h]
0x140022ac9  mov     rcx, rsi; Irp
0x140022acc  call    NbtFreeIrp
0x140022ad1  mov     eax, 0C0000016h
0x140022ad6  jmp     loc_140022CD8
0x140022adb  cmp     rdi, rcx
0x140022ade  jz      loc_140022C56
0x140022ae4  mov     r8, [rbp+57h+var_58]
0x140022ae8  mov     rax, [rdi+20h]
0x140022aec  cmp     [rax+230h], r8
0x140022af3  jnz     short loc_140022AE8
0x140022af5  cmp     rdi, [rbx+20h]
0x140022af9  jz      loc_140022C4A
0x140022aff  lea     rax, [rdi+68h]
0x140022b03  mov     rsi, [rax]
0x140022b06  cmp     rsi, rax
0x140022b09  jz      loc_140022C4A
0x140022b0f  cmp     [rsi+8], rax
0x140022b13  jnz     loc_140022CF4
0x140022b19  mov     rcx, [rsi]
0x140022b1c  cmp     [rcx+8], rsi
0x140022b20  jnz     loc_140022CF4
0x140022b26  mov     [rax], rcx
0x140022b29  mov     r8d, r13d; SourceBytesToCopy
0x140022b2c  mov     [rcx+8], rax
0x140022b30  xor     edx, edx; SourceOffset
0x140022b32  mov     rax, [rsi+10h]
0x140022b36  lea     rcx, [rbp+57h+BytesCopied]
0x140022b3a  mov     qword ptr [rsp+0E0h+Priority], rcx; BytesCopied
0x140022b3f  mov     rcx, r12; SourceBuffer
0x140022b42  mov     [rbp+57h+arg_10], rax
0x140022b46  mov     [rsp+0E0h+BugCheckOnFailure], 0; DestinationOffset
0x140022b4e  mov     r9, [rax+8]; DestinationMdlChain
0x140022b52  call    cs:__imp_TdiCopyBufferToMdl
0x140022b59  nop     dword ptr [rax+rax+00h]
0x140022b5e  cmp     [rbp+57h+BytesCopied], r13d
0x140022b62  mov     rcx, [rbp+57h+arg_10]
0x140022b66  sbb     eax, eax
0x140022b68  and     eax, 80000005h
0x140022b6d  mov     [rcx+30h], eax
0x140022b70  mov     eax, [rbp+57h+BytesCopied]
0x140022b73  mov     [rcx+38h], rax
0x140022b77  test    byte ptr cs:xmmword_140038420+9, 40h
0x140022b7e  jz      short loc_140022BAF
0x140022b80  mov     ecx, [rdi+14h]
0x140022b83  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x140022b8a  mov     [rsp+0E0h+var_A8], r14
0x140022b8f  mov     edx, 0Dh
0x140022b94  mov     dword ptr [rsp+0E0h+var_B0], 0F05h
0x140022b9c  mov     r9, rdi
0x140022b9f  lea     eax, [rcx+1]
0x140022ba2  mov     [rsp+0E0h+Priority], eax
0x140022ba6  mov     [rsp+0E0h+BugCheckOnFailure], ecx
  ... truncated ...
```
