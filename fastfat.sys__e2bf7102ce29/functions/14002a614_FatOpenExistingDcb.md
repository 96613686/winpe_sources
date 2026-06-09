# FatOpenExistingDcb

- ea: `0x14002a614`
- end: `0x14002aadf`
- name: `FatOpenExistingDcb`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400268c0`

## callees

- `0x140002ed8`
- `0x1400201f4`
- `0x1400267dc`
- `0x14002a614`
- `0x1400319bc`
- `0x1400364fc`
- `0x14003db44`
- `0x1400465f4`
- `0x1400475e8`
- `0x14004814c`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14002a69e`
- `ntoskrnl!KeClearEvent` at `0x14002a69e`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14002a70e`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14002a70e`
- `ntoskrnl!IoRemoveShareAccess` at `0x14005c66f`
- `ntoskrnl!IoRemoveShareAccess` at `0x14005c66f`
- `ntoskrnl!FsRtlCheckOplock` at `0x14002a8c9`
- `ntoskrnl!FsRtlCheckOplock` at `0x14002a8c9`
- `ntoskrnl!IoSetShareAccess` at `0x14002a952`
- `ntoskrnl!IoSetShareAccess` at `0x14002a952`
- `ntoskrnl!FsRtlOplockBreakH2` at `0x14002a872`
- `ntoskrnl!FsRtlOplockBreakH2` at `0x14002a872`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14002a902`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14002a902`
- `ntoskrnl!IoUpdateShareAccess` at `0x14002a935`
- `ntoskrnl!IoUpdateShareAccess` at `0x14002a935`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002aabc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c687`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002aabc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c687`
- `ntoskrnl!CcUnpinData` at `0x14002a787`
- `ntoskrnl!CcUnpinData` at `0x14002aaa3`
- `ntoskrnl!CcUnpinData` at `0x14005c629`
- `ntoskrnl!CcUnpinData` at `0x14002a787`
- `ntoskrnl!CcUnpinData` at `0x14002aaa3`
- `ntoskrnl!CcUnpinData` at `0x14005c629`
- `ntoskrnl!ExRaiseStatus` at `0x14002a6b3`
- `ntoskrnl!ExRaiseStatus` at `0x14002aa75`
- `ntoskrnl!ExRaiseStatus` at `0x14002a6b3`
- `ntoskrnl!ExRaiseStatus` at `0x14002aa75`

## pseudocode

```c
__int64 __fastcall FatOpenExistingDcb(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        ACCESS_MASK *a7,
        unsigned __int16 a8,
        int a9,
        char a10,
        char a11,
        char a12,
        char a13,
        _BYTE *a14)
{
  NTSTATUS v17; // eax
  __int64 v18; // rdx
  PVOID v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  NTSTATUS v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  _DWORD *v28; // rsi
  NTSTATUS Callback; // eax
  PVOID Bcb; // [rsp+68h] [rbp-50h] BYREF
  __int64 Ccb; // [rsp+70h] [rbp-48h]
  __int64 v33; // [rsp+78h] [rbp-40h] BYREF

  *(_OWORD *)a1 = 0;
  Bcb = 0;
  v33 = 0;
  Ccb = 0;
  FatAcquireExclusiveFcb(a2, a6);
  if ( (*(_DWORD *)(a5 + 200) & 0x400000) != 0 && (*(_DWORD *)(a6 + 192) & 0x100000) != 0 )
  {
    *(_DWORD *)(a2 + 68) |= 0x80000u;
    KeClearEvent(&Event);
    *(_DWORD *)(a2 + 72) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  *a14 = 0;
  if ( *(_WORD *)a6 == 1284 && a11 )
  {
    *(_DWORD *)a1 = -1073741535;
    goto LABEL_51;
  }
  v17 = FsRtlCheckOplockEx((POPLOCK)(a6 + 88), *(PIRP *)(a2 + 40), 2u, 0, 0, 0);
  *(_DWORD *)a1 = v17;
  if ( v17 )
    goto LABEL_51;
  if ( a10 )
  {
    if ( *(_WORD *)a6 != 1284 && *(_BYTE *)(a5 + 376) != 32 )
    {
      FatGetDirentFromFcbOrDcb(a2, a6, 0, (unsigned int)&v33, (__int64)&Bcb);
      FatGetNeedEaCount(a2, a5);
      v19 = Bcb;
      if ( Bcb )
      {
        CcUnpinData(Bcb);
        Bcb = 0;
      }
    }
  }
  if ( ((a9 - 1) & 0xFFFFFFFD) != 0 )
  {
    *(_DWORD *)a1 = -1073741771;
    goto LABEL_51;
  }
  LOBYTE(v18) = *(_BYTE *)(a6 + 546);
  if ( !(unsigned __int8)FatCheckFileAccess(v19, v18, a7) )
  {
    *(_DWORD *)a1 = -1073741790;
    goto LABEL_51;
  }
  if ( !*(_DWORD *)(a6 + 232) || (v21 = FatCheckShareAccess(v20, a4, a6, a7, a8), *(_DWORD *)a1 = v21, v21 >= 0) )
  {
    if ( *(_DWORD *)(a6 + 228) )
      *(_DWORD *)a1 = FsRtlCheckOplock(
                        (POPLOCK)(a6 + 88),
                        *(PIRP *)(a2 + 40),
                        (PVOID)a2,
                        FatOplockComplete,
                        FatPrePostIrp);
    v23 = *(_DWORD *)a1;
    if ( *(_DWORD *)a1 == 259 )
      goto LABEL_24;
    if ( a12 )
    {
      if ( v23 )
        goto LABEL_34;
      v23 = FsRtlOplockFsctrl((POPLOCK)(a6 + 88), *(PIRP *)(a2 + 40), *(_DWORD *)(a6 + 228) + 1);
      *(_DWORD *)a1 = v23;
    }
    if ( !v23 )
    {
LABEL_35:
      if ( *(_DWORD *)(a6 + 232) )
        IoUpdateShareAccess((PFILE_OBJECT)a4, (PSHARE_ACCESS)(a6 + 200));
      else
        IoSetShareAccess(*a7, a8, (PFILE_OBJECT)a4, (PSHARE_ACCESS)(a6 + 200));
      Ccb = FatCreateCcb(v25, v24);
      FatSetFileObject(a4, v26, a6, Ccb);
      ++*(_DWORD *)(a6 + 228);
      ++*(_DWORD *)(a6 + 232);
      ++*(_DWORD *)(a5 + 272);
      if ( !*(_WORD *)(a4 + 75) )
        ++*(_DWORD *)(a5 + 276);
      v27 = *(_QWORD *)(a4 + 32);
      if ( a11 )
        *(_DWORD *)(v27 + 4) |= 0x400u;
      if ( a13 )
        *(_DWORD *)(v27 + 4) |= 0x800u;
      v28 = (_DWORD *)(a6 + 192);
      if ( (*(_DWORD *)(a5 + 200) & 0x400000) != 0 && (*v28 & 0x60000) != 0 )
      {
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL) + 20LL) |= *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL)
                                                                                + 16LL);
        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL) + 20LL) & 0x27) != 0 )
        {
          *(_DWORD *)(a2 + 136) = 131080;
          Callback = EfsFileCreateCallback(
                       a6,
                       *(_QWORD *)(a6 + 176),
                       a3,
                       *(_DWORD *)(a2 + 136),
                       (*(_DWORD *)(a5 + 200) >> 14) & 1,
                       a2,
                       a5 - 416);
          if ( Callback < 0 )
          {
            *(_DWORD *)a1 = Callback;
            *(_DWORD *)(a2 + 72) = Callback;
            ExRaiseStatus(Callback);
          }
          *(_DWORD *)(a2 + 68) |= 0x8000u;
        }
      }
      *v28 &= ~0x800u;
      *(_DWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 1;
      goto LABEL_51;
    }
LABEL_34:
    if ( v23 != 264 )
      goto LABEL_51;
    goto LABEL_35;
  }
  if ( v21 == -1073741757 && (*(_DWORD *)(a3 + 16) & 0x100) == 0 )
  {
    v22 = FsRtlOplockBreakH2(a6 + 88, *(_QWORD *)(a2 + 40), 128, a2, FatOplockComplete, FatPrePostIrp, a7);
    if ( v22 == 259 )
    {
      *(_DWORD *)a1 = 259;
LABEL_24:
      *a14 = 1;
      goto LABEL_51;
    }
    if ( v22 < 0 )
      *(_DWORD *)a1 = v22;
  }
LABEL_51:
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  ExReleaseResourceLite(*(PERESOURCE *)(a6 + 8));
  return a1;
}

```

## disassembly

```asm
0x14002a614  mov     rax, rsp
0x14002a617  mov     [rax+20h], r9
0x14002a61b  mov     [rax+18h], r8
0x14002a61f  push    rbx
0x14002a620  push    rsi
0x14002a621  push    rdi
0x14002a622  push    r12
0x14002a624  push    r13
0x14002a626  push    r14
0x14002a628  push    r15
0x14002a62a  sub     rsp, 80h
0x14002a631  mov     rsi, r9
0x14002a634  mov     r14, rdx
0x14002a637  mov     rdi, rcx
0x14002a63a  mov     rbx, [rsp+0B8h+arg_28]
0x14002a642  xorps   xmm0, xmm0
0x14002a645  movups  xmmword ptr [rcx], xmm0
0x14002a648  mov     qword ptr [rax-50h], 0
0x14002a650  mov     qword ptr [rax-40h], 0
0x14002a658  mov     byte ptr [rax-58h], 0
0x14002a65c  mov     qword ptr [rax-48h], 0
0x14002a664  mov     rdx, rbx
0x14002a667  mov     rcx, r14
0x14002a66a  call    FatAcquireExclusiveFcb
0x14002a66f  nop
0x14002a670  mov     r15, [rsp+0B8h+arg_20]
0x14002a678  mov     eax, [r15+0C8h]
0x14002a67f  bt      eax, 16h
0x14002a683  jnb     short loc_14002A6BF
0x14002a685  test    dword ptr [rbx+0C0h], 100000h
0x14002a68f  jz      short loc_14002A6BF
0x14002a691  bts     dword ptr [r14+44h], 13h
0x14002a697  lea     rcx, Event; Event
0x14002a69e  call    cs:__imp_KeClearEvent
0x14002a6a5  nop     dword ptr [rax+rax+00h]
0x14002a6aa  mov     ecx, 0C00000D8h; Status
0x14002a6af  mov     [r14+48h], ecx
0x14002a6b3  call    cs:__imp_ExRaiseStatus
0x14002a6bf  mov     r12, [rsp+0B8h+arg_68]
0x14002a6c7  mov     byte ptr [r12], 0
0x14002a6cc  mov     r13d, 504h
0x14002a6d2  cmp     [rbx], r13w
0x14002a6d6  jnz     short loc_14002A6ED
0x14002a6d8  cmp     [rsp+0B8h+arg_50], 0
0x14002a6e0  jz      short loc_14002A6ED
0x14002a6e2  mov     dword ptr [rdi], 0C0000121h
0x14002a6e8  jmp     loc_14002AA99
0x14002a6ed  lea     rcx, [rbx+58h]; Oplock
0x14002a6f1  mov     [rsp+0B8h+PostIrpRoutine], 0; PostIrpRoutine
0x14002a6fa  mov     [rsp+0B8h+CompletionRoutine], 0; CompletionRoutine
0x14002a703  xor     r9d, r9d; Context
0x14002a706  lea     r8d, [r9+2]; Flags
0x14002a70a  mov     rdx, [r14+28h]; Irp
0x14002a70e  call    cs:__imp_FsRtlCheckOplockEx
0x14002a715  nop     dword ptr [rax+rax+00h]
0x14002a71a  mov     [rdi], eax
0x14002a71c  test    eax, eax
0x14002a71e  jnz     loc_14002AA99
0x14002a724  cmp     [rsp+0B8h+arg_48], al
0x14002a72b  jz      loc_14002A7B1
0x14002a731  cmp     [rbx], r13w
0x14002a735  jz      short loc_14002A7B1
0x14002a737  cmp     byte ptr [r15+178h], 20h ; ' '
0x14002a73f  jz      short loc_14002A7B1
0x14002a741  mov     [rsp+0B8h+arg_0], eax
0x14002a748  lea     rax, [rsp+0B8h+Bcb]
0x14002a74d  mov     [rsp+0B8h+CompletionRoutine], rax
0x14002a752  lea     r9, [rsp+0B8h+var_40]
0x14002a757  xor     r8d, r8d
0x14002a75a  mov     rdx, rbx
0x14002a75d  mov     rcx, r14
0x14002a760  call    FatGetDirentFromFcbOrDcb
0x14002a765  lea     r9, [rsp+0B8h+arg_0]
0x14002a76d  mov     r8, [rsp+0B8h+var_40]
0x14002a772  mov     rdx, r15; int
0x14002a775  mov     rcx, r14; int
0x14002a778  call    FatGetNeedEaCount
0x14002a77d  mov     rcx, [rsp+0B8h+Bcb]; Bcb
0x14002a782  test    rcx, rcx
0x14002a785  jz      short loc_14002A79C
0x14002a787  call    cs:__imp_CcUnpinData
0x14002a78e  nop     dword ptr [rax+rax+00h]
0x14002a793  mov     [rsp+0B8h+Bcb], 0
0x14002a79c  cmp     [rsp+0B8h+arg_0], 0
0x14002a7a4  jz      short loc_14002A7B1
0x14002a7a6  mov     dword ptr [rdi], 0C0000022h
0x14002a7ac  jmp     loc_14002AA99
0x14002a7b1  mov     eax, [rsp+0B8h+arg_40]
0x14002a7b8  dec     eax
0x14002a7ba  test    eax, 0FFFFFFFDh
0x14002a7bf  jz      short loc_14002A7CC
0x14002a7c1  mov     dword ptr [rdi], 0C0000035h
0x14002a7c7  jmp     loc_14002AA99
0x14002a7cc  mov     r13, [rsp+0B8h+arg_30]
0x14002a7d4  mov     r8, r13
0x14002a7d7  mov     dl, [rbx+222h]
0x14002a7dd  call    FatCheckFileAccess
0x14002a7e2  test    al, al
0x14002a7e4  jz      short loc_14002A7A6
0x14002a7e6  cmp     dword ptr [rbx+0E8h], 0
0x14002a7ed  jbe     loc_14002A8A2
0x14002a7f3  movzx   eax, [rsp+0B8h+arg_38]
0x14002a7fb  mov     dword ptr [rsp+0B8h+CompletionRoutine], eax
0x14002a7ff  mov     r9, r13
0x14002a802  mov     r8, rbx
0x14002a805  mov     rdx, rsi
0x14002a808  call    FatCheckShareAccess
0x14002a80d  mov     [rdi], eax
0x14002a80f  test    eax, eax
0x14002a811  jns     loc_14002A8A2
0x14002a817  cmp     eax, 0C0000043h
0x14002a81c  jnz     loc_14002AA99
0x14002a822  mov     rax, [rsp+0B8h+arg_10]
0x14002a82a  test    dword ptr [rax+10h], 100h
0x14002a831  jnz     loc_14002AA99
0x14002a837  lea     rax, [rsp+0B8h+arg_38]
0x14002a83f  mov     [rsp+0B8h+var_80], rax
0x14002a844  mov     [rsp+0B8h+var_88], r13
0x14002a849  lea     rax, FatPrePostIrp
0x14002a850  mov     [rsp+0B8h+PostIrpRoutine], rax
0x14002a855  lea     r9, FatOplockComplete
0x14002a85c  mov     [rsp+0B8h+CompletionRoutine], r9
0x14002a861  mov     r9, r14
0x14002a864  mov     r8d, 80h
0x14002a86a  mov     rdx, [r14+28h]
0x14002a86e  lea     rcx, [rbx+58h]
0x14002a872  call    cs:__imp_FsRtlOplockBreakH2
0x14002a879  nop     dword ptr [rax+rax+00h]
0x14002a87e  mov     ecx, 103h
0x14002a883  cmp     eax, ecx
0x14002a885  jnz     short loc_14002A893
0x14002a887  mov     [rdi], ecx
0x14002a889  mov     byte ptr [r12], 1
0x14002a88e  jmp     loc_14002AA99
0x14002a893  test    eax, eax
0x14002a895  jns     loc_14002AA99
0x14002a89b  mov     [rdi], eax
0x14002a89d  jmp     loc_14002AA99
0x14002a8a2  cmp     dword ptr [rbx+0E4h], 0
0x14002a8a9  jz      short loc_14002A8D7
0x14002a8ab  lea     rax, FatPrePostIrp
0x14002a8b2  mov     [rsp+0B8h+CompletionRoutine], rax; PostIrpRoutine
0x14002a8b7  lea     r9, FatOplockComplete; CompletionRoutine
0x14002a8be  mov     r8, r14; Context
0x14002a8c1  mov     rdx, [r14+28h]; Irp
0x14002a8c5  lea     rcx, [rbx+58h]; Oplock
0x14002a8c9  call    cs:__imp_FsRtlCheckOplock
0x14002a8d0  nop     dword ptr [rax+rax+00h]
0x14002a8d5  mov     [rdi], eax
0x14002a8d7  mov     eax, [rdi]
0x14002a8d9  mov     ecx, 103h
0x14002a8de  cmp     eax, ecx
0x14002a8e0  jz      short loc_14002A889
0x14002a8e2  cmp     [rsp+0B8h+arg_58], 0
0x14002a8ea  jz      short loc_14002A910
0x14002a8ec  test    eax, eax
0x14002a8ee  jnz     short loc_14002A914
0x14002a8f0  mov     r8d, [rbx+0E4h]
0x14002a8f7  inc     r8d; OpenCount
0x14002a8fa  mov     rdx, [r14+28h]; Irp
0x14002a8fe  lea     rcx, [rbx+58h]; Oplock
0x14002a902  call    cs:__imp_FsRtlOplockFsctrl
0x14002a909  nop     dword ptr [rax+rax+00h]
0x14002a90e  mov     [rdi], eax
0x14002a910  test    eax, eax
0x14002a912  jz      short loc_14002A91F
0x14002a914  cmp     eax, 108h
0x14002a919  jnz     loc_14002AA99
0x14002a91f  lea     r9, [rbx+0C8h]; ShareAccess
0x14002a926  cmp     dword ptr [rbx+0E8h], 0
0x14002a92d  jbe     short loc_14002A943
0x14002a92f  mov     rdx, r9; ShareAccess
0x14002a932  mov     rcx, rsi; FileObject
0x14002a935  call    cs:__imp_IoUpdateShareAccess
0x14002a93c  nop     dword ptr [rax+rax+00h]
0x14002a941  jmp     short loc_14002A95E
0x14002a943  movzx   edx, [rsp+0B8h+arg_38]; DesiredShareAccess
0x14002a94b  mov     r8, rsi; FileObject
0x14002a94e  mov     ecx, [r13+0]; DesiredAccess
0x14002a952  call    cs:__imp_IoSetShareAccess
0x14002a959  nop     dword ptr [rax+rax+00h]
0x14002a95e  mov     [rsp+0B8h+var_58], 1
0x14002a963  call    FatCreateCcb
0x14002a968  mov     [rsp+0B8h+var_48], rax
0x14002a96d  mov     r9, rax
0x14002a970  mov     r8, rbx
0x14002a973  mov     rcx, rsi
0x14002a976  call    FatSetFileObject
0x14002a97b  inc     dword ptr [rbx+0E4h]
0x14002a981  inc     dword ptr [rbx+0E8h]
0x14002a987  inc     dword ptr [r15+110h]
0x14002a98e  mov     al, [rsi+4Ch]
0x14002a991  or      al, [rsi+4Bh]
0x14002a994  jnz     short loc_14002A99D
0x14002a996  inc     dword ptr [r15+114h]
0x14002a99d  mov     rax, [rsi+20h]
0x14002a9a1  cmp     [rsp+0B8h+arg_50], 0
0x14002a9a9  jz      short loc_14002A9B0
0x14002a9ab  bts     dword ptr [rax+4], 0Ah
0x14002a9b0  cmp     [rsp+0B8h+arg_60], 0
0x14002a9b8  jz      short loc_14002A9BF
0x14002a9ba  bts     dword ptr [rax+4], 0Bh
0x14002a9bf  mov     eax, [r15+0C8h]
0x14002a9c6  lea     rsi, [rbx+0C0h]
0x14002a9cd  bt      eax, 16h
0x14002a9d1  jnb     loc_14002AA87
0x14002a9d7  test    dword ptr [rsi], 60000h
0x14002a9dd  jz      loc_14002AA87
0x14002a9e3  mov     r10, [rsp+0B8h+arg_10]
0x14002a9eb  mov     rax, [r10+8]
0x14002a9ef  mov     rcx, [rax+8]
0x14002a9f3  mov     eax, [rcx+10h]
0x14002a9f6  or      [rcx+14h], eax
0x14002a9f9  mov     rax, [r10+8]
0x14002a9fd  mov     rcx, [rax+8]
0x14002aa01  mov     eax, [rcx+14h]
0x14002aa04  test    al, 27h
0x14002aa06  jz      short loc_14002AA87
0x14002aa08  mov     dword ptr [r14+88h], 20008h
0x14002aa13  mov     r8d, [r15+0C8h]
0x14002aa1a  lea     rax, [r14+80h]
0x14002aa21  lea     rcx, [rbx+90h]
0x14002aa28  lea     rdx, [r15-1A0h]
0x14002aa2f  shr     r8d, 0Eh
0x14002aa33  and     r8d, 1
0x14002aa37  mov     [rsp+0B8h+var_70], rax
0x14002aa3c  mov     [rsp+0B8h+var_78], rcx
0x14002aa41  mov     [rsp+0B8h+var_88], rdx
0x14002aa46  mov     [rsp+0B8h+PostIrpRoutine], r14
0x14002aa4b  mov     dword ptr [rsp+0B8h+CompletionRoutine], r8d
0x14002aa50  mov     r9d, [r14+88h]
0x14002aa57  mov     r8, r10
0x14002aa5a  mov     rdx, [rbx+0B0h]
0x14002aa61  mov     rcx, rbx
0x14002aa64  call    EfsFileCreateCallback
0x14002aa69  test    eax, eax
0x14002aa6b  jns     short loc_14002AA81
0x14002aa6d  mov     [rdi], eax
0x14002aa6f  mov     [r14+48h], eax
0x14002aa73  mov     ecx, eax; Status
0x14002aa75  call    cs:__imp_ExRaiseStatus
0x14002aa81  bts     dword ptr [r14+44h], 0Fh
0x14002aa87  btr     dword ptr [rsi], 0Bh
0x14002aa8b  mov     dword ptr [rdi], 0
0x14002aa91  mov     qword ptr [rdi+8], 1
0x14002aa99  mov     rcx, [rsp+0B8h+Bcb]; Bcb
0x14002aa9e  test    rcx, rcx
0x14002aaa1  jz      short loc_14002AAB8
0x14002aaa3  call    cs:__imp_CcUnpinData
0x14002aaaa  nop     dword ptr [rax+rax+00h]
0x14002aaaf  mov     [rsp+0B8h+Bcb], 0
0x14002aab8  mov     rcx, [rbx+8]; Resource
0x14002aabc  call    cs:__imp_ExReleaseResourceLite
0x14002aac3  nop     dword ptr [rax+rax+00h]
0x14002aac8  mov     rax, rdi
0x14002aacb  add     rsp, 80h
0x14002aad2  pop     r15
0x14002aad4  pop     r14
0x14002aad6  pop     r13
0x14002aad8  pop     r12
0x14002aada  pop     rdi
0x14002aadb  pop     rsi
0x14002aadc  pop     rbx
0x14002aadd  retn
0x14005c613  push    rbx
0x14005c615  push    rbp
0x14005c616  sub     rsp, 68h
0x14005c61a  mov     rbp, rdx
0x14005c61d  movzx   ebx, cl
0x14005c620  mov     rcx, [rbp+68h]; Bcb
0x14005c624  test    rcx, rcx
0x14005c627  jz      short loc_14005C63D
0x14005c629  call    cs:__imp_CcUnpinData
0x14005c630  nop     dword ptr [rax+rax+00h]
0x14005c635  mov     qword ptr [rbp+68h], 0
0x14005c63d  mov     eax, ebx
0x14005c63f  test    bl, bl
0x14005c641  jz      short loc_14005C67C
0x14005c643  cmp     qword ptr [rbp+70h], 0
0x14005c648  jz      short loc_14005C654
0x14005c64a  lea     rdx, [rbp+70h]
0x14005c64e  call    FatDeleteCcb
0x14005c653  nop
0x14005c654  cmp     byte ptr [rbp+60h], 0
0x14005c658  jz      short loc_14005C67C
0x14005c65a  mov     rdx, [rbp+0E8h]
0x14005c661  add     rdx, 0C8h; ShareAccess
0x14005c668  mov     rcx, [rbp+0D8h]; FileObject
0x14005c66f  call    cs:__imp_IoRemoveShareAccess
0x14005c676  nop     dword ptr [rax+rax+00h]
0x14005c67b  nop
0x14005c67c  mov     rcx, [rbp+0E8h]
0x14005c683  mov     rcx, [rcx+8]; Resource
0x14005c687  call    cs:__imp_ExReleaseResourceLite
0x14005c68e  nop     dword ptr [rax+rax+00h]
0x14005c693  nop
0x14005c694  add     rsp, 68h
0x14005c698  pop     rbp
0x14005c699  pop     rbx
0x14005c69a  retn
  ... truncated ...
```
