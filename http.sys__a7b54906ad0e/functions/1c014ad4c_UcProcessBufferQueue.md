# UcProcessBufferQueue

- ea: `0x1c014ad4c`
- end: `0x1c014b70e`
- name: `UcProcessBufferQueue`
- size: `2498`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1c0053950`
- `0x1c0054628`

## callees

- `0x1c00060d4`
- `0x1c001b640`
- `0x1c0052cc8`
- `0x1c00555d4`
- `0x1c0056c58`
- `0x1c008f21c`
- `0x1c008f3ec`
- `0x1c008f570`
- `0x1c008f680`
- `0x1c008f76c`
- `0x1c00903a4`
- `0x1c0090454`
- `0x1c00905f0`
- `0x1c0093c3c`
- `0x1c009a0f4`
- `0x1c009a180`
- `0x1c014ad4c`
- `0x1c014c6f0`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x1c014b034`
- `ntoskrnl!IoGetRequestorProcess` at `0x1c014b034`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c014b086`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c014b086`
- `ntoskrnl!IofCompleteRequest` at `0x1c014afae`
- `ntoskrnl!IofCompleteRequest` at `0x1c014b66a`
- `ntoskrnl!IofCompleteRequest` at `0x1c014afae`
- `ntoskrnl!IofCompleteRequest` at `0x1c014b66a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c014b043`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c014b043`

## pseudocode

```c
__int64 __fastcall UcProcessBufferQueue(__int64 a1)
{
  __int64 v1; // rdi
  PIRP v2; // r14
  unsigned int v3; // r13d
  _QWORD *v4; // rdx
  _QWORD *v5; // rbx
  __int64 v6; // r9
  unsigned int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rbx
  struct _KPROCESS *RequestorProcess; // rbx
  char *MappedSystemVa; // rcx
  PMDL MdlAddress; // rcx
  __int64 v15; // r9
  __int64 v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // edx
  unsigned int v19; // ebx
  _QWORD *v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rbx
  int v24; // eax
  __int64 v25; // r11
  __int64 v26; // rax
  unsigned int v27; // edx
  unsigned int v28; // edx
  unsigned int v29; // ebx
  __int64 v30; // r9
  __int64 v31; // r10
  unsigned int v32; // edx
  unsigned int v33; // edx
  unsigned int v34; // ebx
  __int64 result; // rax
  __int64 v36; // [rsp+60h] [rbp-88h]
  bool v37; // [rsp+68h] [rbp-80h]
  _QWORD *v38; // [rsp+70h] [rbp-78h]
  _QWORD *v39; // [rsp+78h] [rbp-70h]
  __int64 v40; // [rsp+78h] [rbp-70h]
  PIRP Irp; // [rsp+80h] [rbp-68h] BYREF
  void *v42; // [rsp+88h] [rbp-60h]
  __int64 v43; // [rsp+90h] [rbp-58h]
  __int64 v44; // [rsp+98h] [rbp-50h]
  __int64 v45; // [rsp+A0h] [rbp-48h]
  int v47; // [rsp+F8h] [rbp+10h]
  unsigned int Size; // [rsp+100h] [rbp+18h]
  unsigned int v49; // [rsp+108h] [rbp+20h] BYREF

  v45 = *(_QWORD *)(a1 + 584);
  v1 = v45;
  v2 = 0;
  Irp = 0;
  v3 = 0;
  v36 = 0;
  v49 = 0;
  v43 = *(_QWORD *)(*(_QWORD *)(v45 + 24) + 464LL);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000000) != 0 )
    WPP_SF_qqD(40, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, a1, 0, 0);
  v37 = (*(_DWORD *)(v45 + 1496) & 0x20) != 0;
  v42 = 0;
  v47 = -v37;
  while ( 1 )
  {
    do
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v4 = (_QWORD *)(v1 + 1464);
          v38 = (_QWORD *)(v1 + 1464);
          if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
          {
            WPP_SF_qLIIq(
              41,
              WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids,
              v1,
              *(unsigned int *)(v1 + 480),
              *v4,
              *(_QWORD *)(v1 + 1448),
              *(_QWORD *)(v1 + 1520));
            v4 = (_QWORD *)(v1 + 1464);
          }
          else
          {
            v38 = (_QWORD *)(v1 + 1464);
          }
          v5 = (_QWORD *)(v1 + 1448);
          v39 = (_QWORD *)(v1 + 1448);
          if ( *(_DWORD *)(v1 + 480) == 10 && *v4 == *v5 )
          {
            if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
              WPP_SF_q(42, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1);
            v3 += *(_DWORD *)(v1 + 1472);
            LODWORD(v36) = v3;
            *(_DWORD *)(v1 + 1472) = 0;
            Size = 0;
          }
          else
          {
            v6 = *(_QWORD *)(v1 + 1520);
            if ( !v6 || *(_QWORD *)(v1 + 1464) == *v5 )
            {
              if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
                WPP_SF_qqqI(
                  43,
                  WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids,
                  v1,
                  v6,
                  *(_QWORD *)(v1 + 1464),
                  *(_QWORD *)(v1 + 1448));
              goto LABEL_113;
            }
            v7 = *(_DWORD *)(v6 + 112) - *(_DWORD *)(v1 + 1528) + v6 + 136;
            Size = v7;
            if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
            {
              WPP_SF_qD(44, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, v7);
              v7 = Size;
            }
            v39 = (_QWORD *)(v1 + 1448);
            if ( !v7 )
            {
              v8 = *(_QWORD *)(*(_QWORD *)(v1 + 1520) + 32LL);
              v9 = v8 - 32;
              if ( v8 == *(_QWORD *)(v1 + 32) + 552LL )
                v9 = 0;
              if ( !v9 )
                goto LABEL_113;
              v39 = (_QWORD *)(v1 + 1448);
              if ( !*(_DWORD *)(v9 + 120) )
                goto LABEL_113;
            }
          }
          v10 = v47;
          if ( !v47 )
          {
            if ( v37 )
              goto LABEL_113;
            if ( v2 )
            {
              if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
                WPP_SF_qqD(45, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, v2, v2->IoStatus.Status);
              v11 = a1;
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
                UcFreeRequest((PSLIST_ENTRY)a1);
              IofCompleteRequest(Irp, 0);
              Irp = 0;
            }
            else
            {
              v11 = a1;
            }
            HIDWORD(v36) = UcDequeueRequestIrp(v11, 3, &Irp);
            v2 = Irp;
            if ( v36 < 0 )
              goto LABEL_114;
            if ( !Irp )
              goto LABEL_119;
            if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
              WPP_SF_qq(46, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, Irp);
            v47 = v2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length - LODWORD(v2->IoStatus.Information);
            RequestorProcess = IoGetRequestorProcess(v2);
            if ( RequestorProcess == IoGetCurrentProcess() )
            {
              MappedSystemVa = (char *)v2->MdlAddress->StartVa + v2->MdlAddress->ByteOffset;
            }
            else
            {
              MdlAddress = v2->MdlAddress;
              if ( (MdlAddress->MdlFlags & 5) != 0 )
                MappedSystemVa = (char *)MdlAddress->MappedSystemVa;
              else
                MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000000u);
            }
            if ( !MappedSystemVa )
            {
              v2->IoStatus.Status = -1073741670;
              v2->IoStatus.Information = 0;
              goto LABEL_113;
            }
            v42 = &MappedSystemVa[v2->IoStatus.Information];
            v2->IoStatus.Status = 0;
            v10 = v47;
          }
          if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
          {
            v15 = *(_QWORD *)(v1 + 1520);
            if ( v15 )
              v16 = *(_QWORD *)(v15 + 128);
            else
              v16 = -1;
            WPP_SF_qqq(47, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, v15, v16);
          }
          v17 = v10;
          v18 = Size;
          if ( Size <= v10 )
            v17 = Size;
          v19 = v17;
          if ( (unsigned __int64)v17 > *(_QWORD *)(v1 + 1456) )
            v19 = *(_DWORD *)(v1 + 1456);
          if ( v19 )
          {
            if ( !v37 )
            {
              v44 = v19;
              memmove(v42, *(const void **)(v1 + 1528), v19);
              if ( v2 )
                v2->IoStatus.Information += v44;
              if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
              {
                WPP_SF_qD(48, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, v19);
                if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
                  WPP_SF_(49, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids);
              }
              v18 = Size;
            }
            *(_QWORD *)(v1 + 1528) += v19;
            v18 -= v19;
            Size = v18;
            *(_QWORD *)(v1 + 1456) -= v19;
            v20 = v38;
            *v38 += v19;
            v42 = (char *)v42 + v19;
            v47 -= v19;
            v3 += v19;
            LODWORD(v36) = v3;
          }
          else
          {
            if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
            {
              WPP_SF_q(50, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1);
              v18 = Size;
            }
            v20 = v38;
          }
          if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
            WPP_SF_qLIIIIL(
              51,
              WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids,
              v1,
              *(unsigned int *)(v1 + 480),
              *v20,
              *v39,
              *(_QWORD *)(v1 + 1456),
              *(_QWORD *)(v1 + 1440),
              v18);
          if ( *(_DWORD *)(v1 + 480) != 10 || *v38 != *v39 )
            break;
          if ( !v37 && v2 && !v2->IoStatus.Information )
            v2->IoStatus.Status = -1073741807;
          v3 += *(_DWORD *)(v1 + 1472);
          LODWORD(v36) = v3;
          *(_DWORD *)(v1 + 1472) = 0;
          v47 = 0;
          if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
            WPP_SF_qq(52, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, v2);
        }
        if ( Size )
          break;
        if ( *v38 == *v39 )
        {
          if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) == 0 )
            goto LABEL_113;
          v21 = 53;
          goto LABEL_77;
        }
        v22 = *(_QWORD *)(*(_QWORD *)(v1 + 1520) + 32LL);
        v23 = v22 - 32;
        if ( v22 == *(_QWORD *)(v1 + 32) + 552LL )
          v23 = 0;
        if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
        {
          if ( v23 )
            v24 = *(_DWORD *)(v23 + 120);
          else
            v24 = 0;
          WPP_SF_qqD(54, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, v23, v24);
        }
        if ( v23 && *(_DWORD *)(v23 + 120) )
        {
          v25 = *(_QWORD *)(v1 + 1520);
          v40 = v25;
          *(_QWORD *)(v1 + 1520) = v23;
          *(_QWORD *)(v1 + 1528) = v23 + 136;
          v26 = *(unsigned int *)(v23 + 112);
          if ( !*(_QWORD *)(v1 + 1456) )
          {
            v27 = *(_DWORD *)(v1 + 1496);
            if ( (v27 & 8) != 0 )
            {
              v28 = ParseChunkLength(v43, (v27 >> 4) & 1, (int)v23 + 136, v26, (__int64)&v49, v1 + 1456, 0);
              HIDWORD(v36) = v28;
            }
            else
            {
              *(_QWORD *)(v1 + 1456) = v26;
              v28 = HIDWORD(v36);
            }
            v29 = v49;
            if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
              WPP_SF_qlLq(55, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, v28, v49, *(_QWORD *)(v1 + 1456));
            *(_QWORD *)(v1 + 1528) += v29;
            v3 += v29;
            LODWORD(v36) = v3;
            v25 = v40;
          }
          if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
          {
            v30 = *(_QWORD *)(v1 + 1520);
            if ( v30 )
              v31 = *(_QWORD *)(v30 + 128);
            else
              LOBYTE(v31) = -1;
            WPP_SF_qqIqIqqIqI(
              56,
              (unsigned int)WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids,
              v1,
              v25,
              *(_QWORD *)(v25 + 128),
              v30,
              v31,
              *(_QWORD *)(v1 + 24),
              *(_QWORD *)(*(_QWORD *)(v1 + 32) + 568LL),
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 32) + 568LL) + 128LL),
              *(_QWORD *)(v1 + 1512),
              *(_QWORD *)(*(_QWORD *)(v1 + 1512) + 128LL),
              v36);
          }
          if ( v40 != *(_QWORD *)(v1 + 1512) )
            UcReleaseResponseBuffer(v43);
        }
      }
    }
    while ( *(_QWORD *)(v1 + 1456) );
    if ( *v38 >= *v39 )
      break;
    v32 = *(_DWORD *)(v1 + 1496);
    if ( (v32 & 8) != 0 )
    {
      v33 = ParseChunkLength(v43, (v32 >> 4) & 1, *(_QWORD *)(v1 + 1528), Size, (__int64)&v49, v1 + 1456, 0);
      HIDWORD(v36) = v33;
    }
    else
    {
      *(_QWORD *)(v1 + 1456) = Size;
      v33 = HIDWORD(v36);
    }
    v34 = v49;
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
      WPP_SF_qlLq(57, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, v33, v49, *(_QWORD *)(v1 + 1456));
    *(_QWORD *)(v1 + 1528) += v34;
    v3 += v34;
    LODWORD(v36) = v3;
  }
  if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
  {
    v21 = 58;
LABEL_77:
    WPP_SF_q(v21, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1);
  }
LABEL_113:
  v11 = a1;
LABEL_114:
  if ( v2 )
  {
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
      WPP_SF_qqD(59, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, v2, v2->IoStatus.Status);
    IofCompleteRequest(v2, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 20), 0xFFFFFFFF) == 1 )
      UcFreeRequest((PSLIST_ENTRY)v11);
    goto LABEL_121;
  }
LABEL_119:
  if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
    WPP_SF_q(60, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1);
LABEL_121:
  result = HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink);
  if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x80) != 0 )
    result = WPP_SF_qqD(61, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids, v1, *(_QWORD *)(v1 + 24), v3);
  if ( v3 )
    result = UcConsumeBytesFromConnection(*(_QWORD *)(v1 + 24), *(_QWORD *)(v1 + 32), v3);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000000) != 0 )
    return WPP_SF_(62, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1c014ad4c  mov     rax, rsp
0x1c014ad4f  mov     [rax+18h], r8d
0x1c014ad53  mov     [rax+10h], rdx
0x1c014ad57  mov     [rax+8], rcx
0x1c014ad5b  push    rbx
0x1c014ad5c  push    rsi
0x1c014ad5d  push    rdi
0x1c014ad5e  push    r12
0x1c014ad60  push    r13
0x1c014ad62  push    r14
0x1c014ad64  push    r15
0x1c014ad66  sub     rsp, 0B0h
0x1c014ad6d  mov     r8, rcx
0x1c014ad70  xor     esi, esi
0x1c014ad72  mov     [rsp+0E8h+var_84], esi
0x1c014ad76  mov     rdi, [rcx+248h]
0x1c014ad7d  mov     [rsp+0E8h+var_48], rdi
0x1c014ad85  mov     r14d, esi
0x1c014ad88  mov     [rax-68h], rsi
0x1c014ad8c  mov     r13d, esi
0x1c014ad8f  mov     [rsp+0E8h+var_88], esi
0x1c014ad93  mov     [rax+20h], esi
0x1c014ad96  mov     rax, [rdi+18h]
0x1c014ad9a  mov     rax, [rax+1D0h]
0x1c014ada1  mov     [rsp+0E8h+var_58], rax
0x1c014ada9  lea     r15, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids
0x1c014adb0  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000000h
0x1c014adba  jz      short loc_1C014ADCE
0x1c014adbc  lea     ecx, [rsi+28h]
0x1c014adbf  mov     [rsp+0E8h+BugCheckOnFailure], esi
0x1c014adc3  xor     r9d, r9d
0x1c014adc6  mov     rdx, r15
0x1c014adc9  call    WPP_SF_qqD
0x1c014adce  mov     eax, [rdi+5D8h]
0x1c014add4  shr     eax, 5
0x1c014add7  and     al, 1
0x1c014add9  mov     dword ptr [rsp+0E8h+var_80], eax
0x1c014addd  mov     [rsp+0E8h+var_60], rsi
0x1c014ade5  neg     al
0x1c014ade7  sbb     ecx, ecx
0x1c014ade9  mov     [rsp+0E8h+arg_8], ecx
0x1c014adf0  mov     r12b, 80h
0x1c014adf3  lea     rdx, [rdi+5B8h]
0x1c014adfa  mov     [rsp+0E8h+var_78], rdx
0x1c014adff  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c014ae05  test    r12b, al
0x1c014ae08  jz      short loc_1C014AE48
0x1c014ae0a  mov     ecx, 29h ; ')'
0x1c014ae0f  mov     rax, [rdi+5F0h]
0x1c014ae16  mov     [rsp+0E8h+var_B8], rax
0x1c014ae1b  mov     rax, [rdi+5A8h]
0x1c014ae22  mov     qword ptr [rsp+0E8h+Priority], rax
0x1c014ae27  mov     rax, [rdx]
0x1c014ae2a  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax
0x1c014ae2f  mov     r9d, [rdi+1E0h]
0x1c014ae36  mov     r8, rdi
0x1c014ae39  mov     rdx, r15
0x1c014ae3c  call    WPP_SF_qLIIq
0x1c014ae41  mov     rdx, [rsp+0E8h+var_78]
0x1c014ae46  jmp     short loc_1C014AE4D
0x1c014ae48  mov     [rsp+0E8h+var_78], rdx
0x1c014ae4d  lea     rbx, [rdi+5A8h]
0x1c014ae54  mov     [rsp+0E8h+var_70], rbx
0x1c014ae59  cmp     dword ptr [rdi+1E0h], 0Ah
0x1c014ae60  jnz     short loc_1C014AEA3
0x1c014ae62  mov     rax, [rbx]
0x1c014ae65  cmp     [rdx], rax
0x1c014ae68  jnz     short loc_1C014AEA3
0x1c014ae6a  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c014ae70  test    r12b, al
0x1c014ae73  jz      short loc_1C014AE85
0x1c014ae75  mov     ecx, 2Ah ; '*'
0x1c014ae7a  mov     r8, rdi
0x1c014ae7d  mov     rdx, r15
0x1c014ae80  call    WPP_SF_q
0x1c014ae85  add     r13d, [rdi+5C0h]
0x1c014ae8c  mov     [rsp+0E8h+var_88], r13d
0x1c014ae91  mov     [rdi+5C0h], esi
0x1c014ae97  mov     dword ptr [rsp+0E8h+Size], esi
0x1c014ae9e  jmp     loc_1C014AF44
0x1c014aea3  mov     r9, [rdi+5F0h]
0x1c014aeaa  test    r9, r9
0x1c014aead  jz      loc_1C014B5FF
0x1c014aeb3  mov     rax, [rbx]
0x1c014aeb6  cmp     [rdi+5B8h], rax
0x1c014aebd  jz      loc_1C014B5FF
0x1c014aec3  mov     ecx, [r9+70h]
0x1c014aec7  sub     ecx, [rdi+5F8h]
0x1c014aecd  mov     edx, r9d
0x1c014aed0  add     edx, 88h
0x1c014aed6  add     edx, ecx
0x1c014aed8  mov     dword ptr [rsp+0E8h+Size], edx
0x1c014aedf  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c014aee5  test    r12b, al
0x1c014aee8  jz      short loc_1C014AF04
0x1c014aeea  mov     ecx, 2Ch ; ','
0x1c014aeef  mov     r9d, edx
0x1c014aef2  mov     r8, rdi
0x1c014aef5  mov     rdx, r15
0x1c014aef8  call    WPP_SF_qD
0x1c014aefd  mov     edx, dword ptr [rsp+0E8h+Size]
0x1c014af04  mov     [rsp+0E8h+var_70], rbx
0x1c014af09  test    edx, edx
0x1c014af0b  jnz     short loc_1C014AF44
0x1c014af0d  mov     rax, [rdi+5F0h]
0x1c014af14  mov     rcx, [rax+20h]
0x1c014af18  mov     rax, [rdi+20h]
0x1c014af1c  add     rax, 228h
0x1c014af22  lea     rdx, [rcx-20h]
0x1c014af26  cmp     rcx, rax
0x1c014af29  cmovz   rdx, rsi
0x1c014af2d  test    rdx, rdx
0x1c014af30  jz      loc_1C014B632
0x1c014af36  mov     [rsp+0E8h+var_70], rbx
0x1c014af3b  cmp     [rdx+78h], esi
0x1c014af3e  jz      loc_1C014B632
0x1c014af44  mov     ebx, [rsp+0E8h+arg_8]
0x1c014af4b  test    ebx, ebx
0x1c014af4d  jnz     loc_1C014B0C2
0x1c014af53  cmp     [rsp+0E8h+var_80], sil
0x1c014af58  jnz     loc_1C014B632
0x1c014af5e  test    r14, r14
0x1c014af61  jz      short loc_1C014AFC4
0x1c014af63  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c014af69  test    r12b, al
0x1c014af6c  jz      short loc_1C014AF87
0x1c014af6e  lea     ecx, [rbx+2Dh]
0x1c014af71  mov     eax, [r14+30h]
0x1c014af75  mov     [rsp+0E8h+BugCheckOnFailure], eax
0x1c014af79  mov     r9, r14
0x1c014af7c  mov     r8, rdi
0x1c014af7f  mov     rdx, r15
0x1c014af82  call    WPP_SF_qqD
0x1c014af87  or      eax, 0FFFFFFFFh
0x1c014af8a  mov     rbx, [rsp+0E8h+ListEntry]
0x1c014af92  lock xadd [rbx+14h], eax
0x1c014af97  cmp     eax, 1
0x1c014af9a  jnz     short loc_1C014AFA4
0x1c014af9c  mov     rcx, rbx; ListEntry
0x1c014af9f  call    UcFreeRequest
0x1c014afa4  xor     edx, edx; PriorityBoost
0x1c014afa6  mov     rcx, [rsp+0E8h+Irp]; Irp
0x1c014afae  call    cs:__imp_IofCompleteRequest
0x1c014afb5  nop     dword ptr [rax+rax+00h]
0x1c014afba  mov     [rsp+0E8h+Irp], rsi
0x1c014afc2  jmp     short loc_1C014AFCC
0x1c014afc4  mov     rbx, [rsp+0E8h+ListEntry]
0x1c014afcc  lea     r8, [rsp+0E8h+Irp]
0x1c014afd4  mov     edx, 3
0x1c014afd9  mov     rcx, rbx
0x1c014afdc  call    UcDequeueRequestIrp
0x1c014afe1  mov     [rsp+0E8h+var_84], eax
0x1c014afe5  mov     r14, [rsp+0E8h+Irp]
0x1c014afed  test    eax, eax
0x1c014afef  js      loc_1C014B63A
0x1c014aff5  test    r14, r14
0x1c014aff8  jz      loc_1C014B68D
0x1c014affe  mov     ecx, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c014b004  test    r12b, cl
0x1c014b007  jz      short loc_1C014B01C
0x1c014b009  mov     ecx, 2Eh ; '.'
0x1c014b00e  mov     r9, r14
0x1c014b011  mov     r8, rdi
0x1c014b014  mov     rdx, r15
0x1c014b017  call    WPP_SF_qq
0x1c014b01c  mov     rcx, [r14+0B8h]
0x1c014b023  mov     ecx, [rcx+8]
0x1c014b026  sub     ecx, [r14+38h]
0x1c014b02a  mov     [rsp+0E8h+arg_8], ecx
0x1c014b031  mov     rcx, r14; Irp
0x1c014b034  call    cs:__imp_IoGetRequestorProcess
0x1c014b03b  nop     dword ptr [rax+rax+00h]
0x1c014b040  mov     rbx, rax
0x1c014b043  call    cs:__imp_IoGetCurrentProcess
0x1c014b04a  nop     dword ptr [rax+rax+00h]
0x1c014b04f  cmp     rbx, rax
0x1c014b052  jnz     short loc_1C014B061
0x1c014b054  mov     rax, [r14+8]
0x1c014b058  mov     ecx, [rax+2Ch]
0x1c014b05b  add     rcx, [rax+20h]
0x1c014b05f  jmp     short loc_1C014B095
0x1c014b061  mov     rcx, [r14+8]; MemoryDescriptorList
0x1c014b065  test    byte ptr [rcx+0Ah], 5
0x1c014b069  jz      short loc_1C014B071
0x1c014b06b  mov     rcx, [rcx+18h]
0x1c014b06f  jmp     short loc_1C014B095
0x1c014b071  mov     [rsp+0E8h+Priority], 40000000h; Priority
0x1c014b079  mov     [rsp+0E8h+BugCheckOnFailure], esi; BugCheckOnFailure
0x1c014b07d  xor     r9d, r9d; RequestedAddress
0x1c014b080  xor     edx, edx; AccessMode
0x1c014b082  lea     r8d, [r9+1]; CacheType
0x1c014b086  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1c014b08d  nop     dword ptr [rax+rax+00h]
0x1c014b092  mov     rcx, rax
0x1c014b095  test    rcx, rcx
0x1c014b098  jnz     short loc_1C014B0AB
0x1c014b09a  mov     dword ptr [r14+30h], 0C000009Ah
0x1c014b0a2  mov     [r14+38h], rsi
0x1c014b0a6  jmp     loc_1C014B632
0x1c014b0ab  add     rcx, [r14+38h]
0x1c014b0af  mov     [rsp+0E8h+var_60], rcx
0x1c014b0b7  mov     [r14+30h], esi
0x1c014b0bb  mov     ebx, [rsp+0E8h+arg_8]
0x1c014b0c2  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c014b0c8  test    r12b, al
0x1c014b0cb  jz      short loc_1C014B0FB
0x1c014b0cd  mov     r9, [rdi+5F0h]
0x1c014b0d4  test    r9, r9
0x1c014b0d7  jnz     short loc_1C014B0DF
0x1c014b0d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1c014b0dd  jmp     short loc_1C014B0E6
0x1c014b0df  mov     rax, [r9+80h]
0x1c014b0e6  mov     ecx, 2Fh ; '/'
0x1c014b0eb  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax
0x1c014b0f0  mov     r8, rdi
0x1c014b0f3  mov     rdx, r15
0x1c014b0f6  call    WPP_SF_qqq
0x1c014b0fb  mov     eax, ebx
0x1c014b0fd  mov     edx, dword ptr [rsp+0E8h+Size]
0x1c014b104  cmp     edx, ebx
0x1c014b106  cmovbe  eax, edx
0x1c014b109  mov     ebx, eax
0x1c014b10b  cmp     rbx, [rdi+5B0h]
0x1c014b112  jbe     short loc_1C014B11A
0x1c014b114  mov     ebx, [rdi+5B0h]
0x1c014b11a  test    ebx, ebx
0x1c014b11c  jz      loc_1C014B233
0x1c014b122  cmp     [rsp+0E8h+var_80], sil
0x1c014b127  jnz     loc_1C014B1F9
0x1c014b12d  mov     eax, ebx
0x1c014b12f  mov     [rsp+0E8h+var_50], rax
0x1c014b137  mov     r8d, ebx; Size
0x1c014b13a  mov     rdx, [rdi+5F8h]; Src
0x1c014b141  mov     rcx, [rsp+0E8h+var_60]; void *
0x1c014b149  call    memmove
0x1c014b14e  nop
0x1c014b14f  test    r14, r14
0x1c014b152  jz      short loc_1C014B160
0x1c014b154  mov     rax, [rsp+0E8h+var_50]
0x1c014b15c  add     [r14+38h], rax
0x1c014b160  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c014b166  test    r12b, al
0x1c014b169  jz      loc_1C014B1F2
0x1c014b16f  mov     ecx, 30h ; '0'
0x1c014b174  mov     r9d, ebx
0x1c014b177  mov     r8, rdi
0x1c014b17a  mov     rdx, r15
0x1c014b17d  call    WPP_SF_qD
0x1c014b182  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c014b188  test    r12b, al
0x1c014b18b  jz      short loc_1C014B1F2
0x1c014b18d  mov     ecx, 31h ; '1'
0x1c014b192  mov     rdx, r15
0x1c014b195  call    WPP_SF_
0x1c014b19a  jmp     short loc_1C014B1F2
0x1c014b19c  mov     r14, [rsp+0E8h+Irp]
0x1c014b1a4  test    r14, r14
0x1c014b1a7  jz      short loc_1C014B1CE
0x1c014b1a9  and     qword ptr [r14+38h], 0
0x1c014b1ae  mov     ecx, eax
0x1c014b1b0  and     ecx, 0C0000000h
0x1c014b1b6  cmp     ecx, 80000000h
0x1c014b1bc  jnz     short loc_1C014B1CA
0x1c014b1be  cmp     eax, 80000005h
0x1c014b1c3  jz      short loc_1C014B1CA
0x1c014b1c5  mov     eax, 0C000000Dh
0x1c014b1ca  mov     [r14+30h], eax
0x1c014b1ce  lea     r15, WPP_5a12e4e4b13231907ee69b8a2e018474_Traceguids
0x1c014b1d5  mov     r12b, 80h
0x1c014b1d8  mov     rdi, [rsp+0E8h+var_48]
0x1c014b1e0  mov     r13d, [rsp+0E8h+var_88]
0x1c014b1e5  mov     rbx, [rsp+0E8h+ListEntry]
0x1c014b1ed  jmp     loc_1C014B63A
0x1c014b1f2  mov     edx, dword ptr [rsp+0E8h+Size]
0x1c014b1f9  mov     eax, ebx
0x1c014b1fb  add     [rdi+5F8h], rax
0x1c014b202  sub     edx, ebx
0x1c014b204  mov     dword ptr [rsp+0E8h+Size], edx
0x1c014b20b  sub     [rdi+5B0h], rax
0x1c014b212  mov     r8, [rsp+0E8h+var_78]
0x1c014b217  add     [r8], rax
0x1c014b21a  add     [rsp+0E8h+var_60], rax
0x1c014b222  sub     [rsp+0E8h+arg_8], ebx
0x1c014b229  add     r13d, ebx
0x1c014b22c  mov     [rsp+0E8h+var_88], r13d
0x1c014b231  jmp     short loc_1C014B25A
0x1c014b233  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c014b239  test    r12b, al
0x1c014b23c  jz      short loc_1C014B255
0x1c014b23e  mov     ecx, 32h ; '2'
0x1c014b243  mov     r8, rdi
0x1c014b246  mov     rdx, r15
0x1c014b249  call    WPP_SF_q
0x1c014b24e  mov     edx, dword ptr [rsp+0E8h+Size]
0x1c014b255  mov     r8, [rsp+0E8h+var_78]
0x1c014b25a  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c014b260  mov     rbx, [rsp+0E8h+var_70]
0x1c014b265  test    r12b, al
0x1c014b268  jz      short loc_1C014B2AD
0x1c014b26a  mov     ecx, 33h ; '3'
  ... truncated ...
```
