# IoReceivePacket

- ea: `0x140029b70`
- end: `0x140029e5b`
- name: `IoReceivePacket`
- size: `747`
- prototype: `__int64 __fastcall(PIRP Irp, __int64, __int64, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140005750`
- `0x14000a290`
- `0x14000a5f4`
- `0x14000a648`
- `0x140016400`
- `0x140029b70`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140029d9e`
- `ntoskrnl!IofCompleteRequest` at `0x140029d9e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140029c49`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140029c49`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140029c5f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140029cbc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140029c5f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140029cbc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029d8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029e3e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029d8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029e3e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029c19`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029c19`

## pseudocode

```c
__int64 __fastcall IoReceivePacket(PIRP Irp, __int64 a2, __int64 a3, unsigned int a4, _DWORD *a5)
{
  __int64 v8; // r14
  KIRQL v9; // al
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 *v12; // rcx
  struct _IRP *MasterIrp; // rbx
  int v14; // edx
  signed int v15; // edi
  char v16; // al
  __int16 v17; // dx
  _QWORD *v18; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  if ( a4 >= 0x5FC )
  {
    v8 = 0;
    v9 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v10 = qword_14001E338;
    byte_14001E3D8 = v9;
    while ( (__int64 *)v10 != &qword_14001E338 )
    {
      v8 = *(_QWORD *)(v10 + 24);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 736));
      if ( *(_QWORD *)(v8 + 48) )
        break;
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v8 + 736));
      v10 = *(_QWORD *)v10;
    }
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    if ( (__int64 *)v10 == &qword_14001E338 )
    {
      v18 = (_QWORD *)qword_14001E310;
      if ( *(__int64 **)qword_14001E310 == &qword_14001E308 )
      {
        Irp->Tail.Overlay.ListEntry.Blink = (struct _LIST_ENTRY *)qword_14001E310;
        Irp->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)&qword_14001E308;
        *v18 = &Irp->Tail.Overlay.ListEntry;
        ++IoRecvList;
        qword_14001E310 = (__int64)&Irp->Tail.Overlay.ListEntry;
        _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&NdisWanCancelRoutine);
        KeReleaseSpinLock(&SpinLock, byte_14001E3D8);
        return 259;
      }
    }
    else
    {
      v11 = *(_QWORD *)v10;
      if ( *(_QWORD *)(*(_QWORD *)v10 + 8LL) == v10 )
      {
        v12 = *(__int64 **)(v10 + 8);
        if ( *v12 == v10 )
        {
          *v12 = v11;
          *(_QWORD *)(v11 + 8) = v12;
          --dword_14001E32C;
          --*(_DWORD *)(v8 + 96);
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v8 + 736));
          MasterIrp = Irp->AssociatedIrp.MasterIrp;
          v14 = *(_DWORD *)(v10 + 72) + 14;
          v15 = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length - 31;
          MasterIrp->MdlAddress = *(PMDL *)(v8 + 48);
          MasterIrp->Flags = 961456;
          if ( v14 <= v15 )
            v15 = v14;
          *((_WORD *)&MasterIrp->Flags + 3) = 0;
          *((_WORD *)&MasterIrp->Flags + 2) = v15;
          MasterIrp->AssociatedIrp.MasterIrp = (struct _IRP *)0x5220FF5643455220LL;
          LODWORD(MasterIrp->ThreadListEntry.Flink) = -11123899;
          WORD2(MasterIrp->ThreadListEntry.Flink) = -1;
          memmove((char *)&MasterIrp->ThreadListEntry.Flink + 6, *(const void **)(v10 + 64), v15 - 14);
          v16 = *(_BYTE *)(v8 + 40);
          v17 = *(_WORD *)(v10 + 56);
          BYTE3(MasterIrp->ThreadListEntry.Flink) = v16;
          BYTE5(MasterIrp->AssociatedIrp.SystemBuffer) = v16;
          BYTE5(MasterIrp->ThreadListEntry.Flink) = v17;
          BYTE4(MasterIrp->ThreadListEntry.Flink) = HIBYTE(v17);
          Irp->IoStatus.Status = 0;
          Irp->IoStatus.Information = v15 + 31LL;
          dword_14001E324 = *(_DWORD *)&MasterIrp->Type;
          qword_14001E318 = (__int64)Irp;
          dword_14001E320 = 0;
          dword_14001E328 = Irp->IoStatus.Information;
          KeReleaseSpinLock(&SpinLock, byte_14001E3D8);
          IofCompleteRequest(Irp, 2);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, v10);
          }
          NdisWanFreeRecvDesc(v10);
          return 259;
        }
      }
    }
    __fastfail(3u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a4, 1532);
  }
  *a5 = 1532;
  return 3221225476LL;
}

```

## disassembly

```asm
0x140029b70  push    rbx
0x140029b72  push    rbp
0x140029b73  push    rsi
0x140029b74  push    rdi
0x140029b75  push    r14
0x140029b77  sub     rsp, 30h
0x140029b7b  mov     ebx, r9d
0x140029b7e  mov     rbp, rcx
0x140029b81  mov     rcx, cs:WPP_GLOBAL_Control
0x140029b88  lea     rax, WPP_GLOBAL_Control
0x140029b8f  cmp     rcx, rax
0x140029b92  jz      short loc_140029BBD
0x140029b94  mov     eax, [rcx+2Ch]
0x140029b97  test    al, 10h
0x140029b99  jz      short loc_140029BB6
0x140029b9b  cmp     byte ptr [rcx+29h], 5
0x140029b9f  jb      short loc_140029BB6
0x140029ba1  mov     rcx, [rcx+18h]
0x140029ba5  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140029bac  mov     edx, 32h ; '2'
0x140029bb1  call    WPP_SF_
0x140029bb6  lea     rax, WPP_GLOBAL_Control
0x140029bbd  mov     edi, 5FCh
0x140029bc2  cmp     ebx, edi
0x140029bc4  jnb     short loc_140029C0F
0x140029bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140029bcd  cmp     rcx, rax
0x140029bd0  jz      short loc_140029BFB
0x140029bd2  mov     eax, [rcx+2Ch]
0x140029bd5  test    al, 10h
0x140029bd7  jz      short loc_140029BFB
0x140029bd9  cmp     byte ptr [rcx+29h], 3
0x140029bdd  jb      short loc_140029BFB
0x140029bdf  mov     rcx, [rcx+18h]
0x140029be3  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140029bea  mov     edx, 33h ; '3'
0x140029bef  mov     [rsp+58h+var_38], edi
0x140029bf3  mov     r9d, ebx
0x140029bf6  call    WPP_SF_dd
0x140029bfb  mov     rax, [rsp+58h+arg_20]
0x140029c03  mov     [rax], edi
0x140029c05  mov     eax, 0C0000004h
0x140029c0a  jmp     loc_140029E4F
0x140029c0f  xor     r14d, r14d
0x140029c12  lea     rcx, SpinLock; SpinLock
0x140029c19  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140029c20  nop     dword ptr [rax+rax+00h]
0x140029c25  mov     rsi, cs:qword_14001E338
0x140029c2c  lea     rdi, qword_14001E338
0x140029c33  mov     cs:byte_14001E3D8, al
0x140029c39  jmp     short loc_140029C6E
0x140029c3b  mov     r14, [rsi+18h]
0x140029c3f  lea     rbx, [r14+2E0h]
0x140029c46  mov     rcx, rbx; SpinLock
0x140029c49  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140029c50  nop     dword ptr [rax+rax+00h]
0x140029c55  cmp     qword ptr [r14+30h], 0
0x140029c5a  jnz     short loc_140029C73
0x140029c5c  mov     rcx, rbx; SpinLock
0x140029c5f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140029c66  nop     dword ptr [rax+rax+00h]
0x140029c6b  mov     rsi, [rsi]
0x140029c6e  cmp     rsi, rdi
0x140029c71  jnz     short loc_140029C3B
0x140029c73  mov     rax, [rbp+0B8h]
0x140029c7a  or      byte ptr [rax+3], 1
0x140029c7e  cmp     rsi, rdi
0x140029c81  jz      loc_140029DEE
0x140029c87  mov     rax, [rsi]
0x140029c8a  cmp     [rax+8], rsi
0x140029c8e  jnz     loc_140029E01
0x140029c94  mov     rcx, [rsi+8]
0x140029c98  cmp     [rcx], rsi
0x140029c9b  jnz     loc_140029E01
0x140029ca1  mov     [rcx], rax
0x140029ca4  mov     [rax+8], rcx
0x140029ca8  or      eax, 0FFFFFFFFh
0x140029cab  add     cs:dword_14001E32C, eax
0x140029cb1  lea     rcx, [r14+2E0h]; SpinLock
0x140029cb8  add     [r14+60h], eax
0x140029cbc  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140029cc3  nop     dword ptr [rax+rax+00h]
0x140029cc8  mov     rax, [rbp+0B8h]
0x140029ccf  mov     edx, [rsi+48h]
0x140029cd2  mov     rbx, [rbp+18h]
0x140029cd6  add     edx, 0Eh
0x140029cd9  mov     edi, [rax+8]
0x140029cdc  mov     rax, [r14+30h]
0x140029ce0  add     edi, 0FFFFFFE1h
0x140029ce3  mov     [rbx+8], rax
0x140029ce7  lea     rcx, [rbx+26h]; void *
0x140029ceb  mov     dword ptr [rbx+10h], 0EABB0h
0x140029cf2  cmp     edx, edi
0x140029cf4  cmovle  edi, edx
0x140029cf7  xor     eax, eax
0x140029cf9  mov     [rbx+16h], ax
0x140029cfd  mov     [rbx+14h], di
0x140029d01  movsd   xmm0, cs:qword_140019838
0x140029d09  movsd   qword ptr [rbx+18h], xmm0
0x140029d0e  mov     eax, cs:dword_140019840
0x140029d14  mov     [rbx+20h], eax
0x140029d17  movzx   eax, cs:word_140019844
0x140029d1e  mov     [rbx+24h], ax
0x140029d22  lea     eax, [rdi-0Eh]
0x140029d25  mov     rdx, [rsi+40h]; Src
0x140029d29  movsxd  r8, eax; Size
0x140029d2c  call    memmove
0x140029d31  mov     al, [r14+28h]
0x140029d35  lea     rcx, SpinLock; SpinLock
0x140029d3c  movzx   edx, word ptr [rsi+38h]
0x140029d40  mov     [rbx+23h], al
0x140029d43  mov     [rbx+1Dh], al
0x140029d46  movzx   eax, dx
0x140029d49  mov     [rbx+25h], dl
0x140029d4c  shr     ax, 8
0x140029d50  mov     [rbx+24h], al
0x140029d53  mov     dword ptr [rbp+30h], 0
0x140029d5a  movsxd  rax, edi
0x140029d5d  add     rax, 1Fh
0x140029d61  mov     [rbp+38h], rax
0x140029d65  mov     eax, [rbx]
0x140029d67  mov     dl, cs:byte_14001E3D8; NewIrql
0x140029d6d  mov     cs:dword_14001E324, eax
0x140029d73  mov     cs:qword_14001E318, rbp
0x140029d7a  mov     cs:dword_14001E320, 0
0x140029d84  mov     eax, [rbp+38h]
0x140029d87  mov     cs:dword_14001E328, eax
0x140029d8d  call    cs:__imp_KeReleaseSpinLock
0x140029d94  nop     dword ptr [rax+rax+00h]
0x140029d99  mov     dl, 2; PriorityBoost
0x140029d9b  mov     rcx, rbp; Irp
0x140029d9e  call    cs:__imp_IofCompleteRequest
0x140029da5  nop     dword ptr [rax+rax+00h]
0x140029daa  mov     rcx, cs:WPP_GLOBAL_Control
0x140029db1  lea     rax, WPP_GLOBAL_Control
0x140029db8  cmp     rcx, rax
0x140029dbb  jz      short loc_140029DE4
0x140029dbd  test    dword ptr [rcx+2Ch], 8000h
0x140029dc4  jz      short loc_140029DE4
0x140029dc6  cmp     byte ptr [rcx+29h], 5
0x140029dca  jb      short loc_140029DE4
0x140029dcc  mov     rcx, [rcx+18h]
0x140029dd0  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140029dd7  mov     edx, 34h ; '4'
0x140029ddc  mov     r9, rsi
0x140029ddf  call    WPP_SF_q
0x140029de4  mov     rcx, rsi
0x140029de7  call    NdisWanFreeRecvDesc
0x140029dec  jmp     short loc_140029E4A
0x140029dee  mov     rcx, cs:qword_14001E310
0x140029df5  lea     rdx, qword_14001E308
0x140029dfc  cmp     [rcx], rdx
0x140029dff  jz      short loc_140029E08
0x140029e01  mov     ecx, 3
0x140029e06  int     29h; Win8: RtlFailFast(ecx)
0x140029e08  lea     rax, [rbp+0A8h]
0x140029e0f  mov     [rax+8], rcx
0x140029e13  mov     [rax], rdx
0x140029e16  mov     [rcx], rax
0x140029e19  lea     rcx, SpinLock; SpinLock
0x140029e20  inc     cs:IoRecvList
0x140029e26  mov     cs:qword_14001E310, rax
0x140029e2d  lea     rax, NdisWanCancelRoutine
0x140029e34  xchg    rax, [rbp+68h]
0x140029e38  mov     dl, cs:byte_14001E3D8; NewIrql
0x140029e3e  call    cs:__imp_KeReleaseSpinLock
0x140029e45  nop     dword ptr [rax+rax+00h]
0x140029e4a  mov     eax, 103h
0x140029e4f  add     rsp, 30h
0x140029e53  pop     r14
0x140029e55  pop     rdi
0x140029e56  pop     rsi
0x140029e57  pop     rbp
0x140029e58  pop     rbx
0x140029e59  retn
```
