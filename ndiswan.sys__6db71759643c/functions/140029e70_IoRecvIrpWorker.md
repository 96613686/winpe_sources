# IoRecvIrpWorker

- ea: `0x140029e70`
- end: `0x14002a0db`
- name: `IoRecvIrpWorker`
- size: `619`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140005750`
- `0x14000a648`
- `0x140016400`
- `0x140029e70`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002a068`
- `ntoskrnl!IofCompleteRequest` at `0x14002a068`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140029ec7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140029ec7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140029edd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140029ff8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140029edd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140029ff8`
- `ntoskrnl!KeSetTimer` at `0x140029f14`
- `ntoskrnl!KeSetTimer` at `0x140029f14`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029f2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a011`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029f2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002a011`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029e84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a0bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029e84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a0bd`

## pseudocode

```c
void __fastcall IoRecvIrpWorker(struct _KDPC *Dpc, PVOID DeferredContext, PVOID SystemArgument1, PVOID SystemArgument2)
{
  __int64 *v4; // rsi
  __int64 v5; // rbp
  IRP *v6; // r14
  __int64 v7; // rax
  __int64 **v8; // rcx
  __int64 v9; // rcx
  struct _IRP *MasterIrp; // rdi
  int v11; // ebx

  byte_14001E3D8 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  byte_14001E3C8 = 0;
  if ( IoRecvList )
  {
    v4 = (__int64 *)qword_14001E338;
    if ( (__int64 *)qword_14001E338 != &qword_14001E338 )
    {
      do
      {
        v5 = v4[3];
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v5 + 736));
        if ( *(_QWORD *)(v5 + 48) )
        {
          v6 = (IRP *)(qword_14001E308 - 168);
          if ( _InterlockedExchange64((volatile __int64 *)(qword_14001E308 - 64), 0) )
          {
            v7 = *v4;
            if ( *(__int64 **)(*v4 + 8) != v4
              || (v8 = (__int64 **)v4[1], *v8 != v4)
              || (*v8 = (__int64 *)v7,
                  *(_QWORD *)(v7 + 8) = v8,
                  --dword_14001E32C,
                  --*(_DWORD *)(v5 + 96),
                  *(__int64 **)(qword_14001E308 + 8) != &qword_14001E308)
              || (v9 = *(_QWORD *)qword_14001E308, *(_QWORD *)(*(_QWORD *)qword_14001E308 + 8LL) != qword_14001E308) )
            {
              __fastfail(3u);
            }
            qword_14001E308 = *(_QWORD *)qword_14001E308;
            *(_QWORD *)(v9 + 8) = &qword_14001E308;
            --IoRecvList;
            MasterIrp = v6->AssociatedIrp.MasterIrp;
            v11 = v6->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length - 32;
            if ( *((_DWORD *)v4 + 18) <= v11 )
              v11 = *((_DWORD *)v4 + 18);
            MasterIrp->MdlAddress = *(PMDL *)(v5 + 48);
            *((_WORD *)&MasterIrp->Flags + 3) = 0;
            MasterIrp->Flags = 961456;
            *((_WORD *)&MasterIrp->Flags + 2) = v11;
            KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v5 + 736));
            KeReleaseSpinLock(&SpinLock, byte_14001E3D8);
            memmove(&MasterIrp->AssociatedIrp, (const void *)v4[8], v11);
            v6->IoStatus.Status = 0;
            v6->IoStatus.Information = v11 + 31LL;
            dword_14001E324 = *(_DWORD *)&MasterIrp->Type;
            qword_14001E318 = (__int64)v6;
            dword_14001E320 = 0;
            dword_14001E328 = v6->IoStatus.Information;
            IofCompleteRequest(v6, 2);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, v4);
            }
            NdisWanFreeRecvDesc((__int64)v4);
            byte_14001E3D8 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
          }
          goto LABEL_7;
        }
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v5 + 736));
        v4 = (__int64 *)*v4;
      }
      while ( v4 != &qword_14001E338 );
      if ( byte_14001E3C8 )
        goto LABEL_7;
    }
    byte_14001E3C8 = 1;
    KeSetTimer(&Timer, (LARGE_INTEGER)15LL, &::Dpc);
  }
LABEL_7:
  KeReleaseSpinLock(&SpinLock, byte_14001E3D8);
}

```

## disassembly

```asm
0x140029e70  push    rbx
0x140029e72  push    rbp
0x140029e73  push    rsi
0x140029e74  push    rdi
0x140029e75  push    r14
0x140029e77  push    r15
0x140029e79  sub     rsp, 28h
0x140029e7d  lea     rcx, SpinLock; SpinLock
0x140029e84  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140029e8b  nop     dword ptr [rax+rax+00h]
0x140029e90  cmp     cs:IoRecvList, 0
0x140029e97  mov     cs:byte_14001E3D8, al
0x140029e9d  mov     cs:byte_14001E3C8, 0
0x140029ea4  jz      short loc_140029F20
0x140029ea6  mov     rsi, cs:qword_14001E338
0x140029ead  lea     rbx, qword_14001E338
0x140029eb4  cmp     rsi, rbx
0x140029eb7  jz      short loc_140029EFA
0x140029eb9  mov     rbp, [rsi+18h]
0x140029ebd  lea     r15, [rbp+2E0h]
0x140029ec4  mov     rcx, r15; SpinLock
0x140029ec7  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140029ece  nop     dword ptr [rax+rax+00h]
0x140029ed3  cmp     qword ptr [rbp+30h], 0
0x140029ed8  jnz     short loc_140029F47
0x140029eda  mov     rcx, r15; SpinLock
0x140029edd  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140029ee4  nop     dword ptr [rax+rax+00h]
0x140029ee9  mov     rsi, [rsi]
0x140029eec  cmp     rsi, rbx
0x140029eef  jnz     short loc_140029EB9
0x140029ef1  cmp     cs:byte_14001E3C8, 0
0x140029ef8  jnz     short loc_140029F20
0x140029efa  lea     r8, Dpc; Dpc
0x140029f01  mov     cs:byte_14001E3C8, 1
0x140029f08  mov     edx, 0Fh; DueTime
0x140029f0d  lea     rcx, Timer; Timer
0x140029f14  call    cs:__imp_KeSetTimer
0x140029f1b  nop     dword ptr [rax+rax+00h]
0x140029f20  mov     dl, cs:byte_14001E3D8; NewIrql
0x140029f26  lea     rcx, SpinLock; SpinLock
0x140029f2d  call    cs:__imp_KeReleaseSpinLock
0x140029f34  nop     dword ptr [rax+rax+00h]
0x140029f39  add     rsp, 28h
0x140029f3d  pop     r15
0x140029f3f  pop     r14
0x140029f41  pop     rdi
0x140029f42  pop     rsi
0x140029f43  pop     rbp
0x140029f44  pop     rbx
0x140029f45  retn
0x140029f47  mov     r14, cs:qword_14001E308
0x140029f4e  xor     eax, eax
0x140029f50  xchg    rax, [r14-40h]
0x140029f54  add     r14, 0FFFFFFFFFFFFFF58h
0x140029f5b  test    rax, rax
0x140029f5e  jz      short loc_140029F20
0x140029f60  mov     rax, [rsi]
0x140029f63  cmp     [rax+8], rsi
0x140029f67  jnz     loc_14002A0D4
0x140029f6d  mov     rcx, [rsi+8]
0x140029f71  cmp     [rcx], rsi
0x140029f74  jnz     loc_14002A0D4
0x140029f7a  mov     [rcx], rax
0x140029f7d  lea     r8, qword_14001E308
0x140029f84  mov     [rax+8], rcx
0x140029f88  or      edx, 0FFFFFFFFh
0x140029f8b  add     cs:dword_14001E32C, edx
0x140029f91  add     [rbp+60h], edx
0x140029f94  mov     rax, cs:qword_14001E308
0x140029f9b  cmp     [rax+8], r8
0x140029f9f  jnz     loc_14002A0D4
0x140029fa5  mov     rcx, [rax]
0x140029fa8  cmp     [rcx+8], rax
0x140029fac  jnz     loc_14002A0D4
0x140029fb2  mov     cs:qword_14001E308, rcx
0x140029fb9  mov     [rcx+8], r8
0x140029fbd  mov     rcx, r15; SpinLock
0x140029fc0  add     cs:IoRecvList, edx
0x140029fc6  mov     rax, [r14+0B8h]
0x140029fcd  mov     rdi, [r14+18h]
0x140029fd1  mov     ebx, [rax+8]
0x140029fd4  mov     eax, [rsi+48h]
0x140029fd7  add     ebx, 0FFFFFFE0h
0x140029fda  cmp     eax, ebx
0x140029fdc  cmovle  ebx, eax
0x140029fdf  mov     rax, [rbp+30h]
0x140029fe3  mov     [rdi+8], rax
0x140029fe7  xor     eax, eax
0x140029fe9  mov     [rdi+16h], ax
0x140029fed  mov     dword ptr [rdi+10h], 0EABB0h
0x140029ff4  mov     [rdi+14h], bx
0x140029ff8  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140029fff  nop     dword ptr [rax+rax+00h]
0x14002a004  mov     dl, cs:byte_14001E3D8; NewIrql
0x14002a00a  lea     rcx, SpinLock; SpinLock
0x14002a011  call    cs:__imp_KeReleaseSpinLock
0x14002a018  nop     dword ptr [rax+rax+00h]
0x14002a01d  mov     rdx, [rsi+40h]; Src
0x14002a021  lea     rcx, [rdi+18h]; void *
0x14002a025  movsxd  rbx, ebx
0x14002a028  mov     r8, rbx; Size
0x14002a02b  call    memmove
0x14002a030  mov     dword ptr [r14+30h], 0
0x14002a038  lea     rax, [rbx+1Fh]
0x14002a03c  mov     [r14+38h], rax
0x14002a040  mov     dl, 2; PriorityBoost
0x14002a042  mov     eax, [rdi]
0x14002a044  mov     rcx, r14; Irp
0x14002a047  mov     cs:dword_14001E324, eax
0x14002a04d  mov     cs:qword_14001E318, r14
0x14002a054  mov     cs:dword_14001E320, 0
0x14002a05e  mov     eax, [r14+38h]
0x14002a062  mov     cs:dword_14001E328, eax
0x14002a068  call    cs:__imp_IofCompleteRequest
0x14002a06f  nop     dword ptr [rax+rax+00h]
0x14002a074  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a07b  lea     rax, WPP_GLOBAL_Control
0x14002a082  cmp     rcx, rax
0x14002a085  jz      short loc_14002A0AE
0x14002a087  test    dword ptr [rcx+2Ch], 8000h
0x14002a08e  jz      short loc_14002A0AE
0x14002a090  cmp     byte ptr [rcx+29h], 5
0x14002a094  jb      short loc_14002A0AE
0x14002a096  mov     rcx, [rcx+18h]
0x14002a09a  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002a0a1  mov     edx, 35h ; '5'
0x14002a0a6  mov     r9, rsi
0x14002a0a9  call    WPP_SF_q
0x14002a0ae  mov     rcx, rsi
0x14002a0b1  call    NdisWanFreeRecvDesc
0x14002a0b6  lea     rcx, SpinLock; SpinLock
0x14002a0bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a0c4  nop     dword ptr [rax+rax+00h]
0x14002a0c9  mov     cs:byte_14001E3D8, al
0x14002a0cf  jmp     loc_140029F20
0x14002a0d4  mov     ecx, 3
0x14002a0d9  int     29h; Win8: RtlFailFast(ecx)
```
