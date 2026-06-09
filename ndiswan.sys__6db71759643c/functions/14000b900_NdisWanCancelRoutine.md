# NdisWanCancelRoutine

- ea: `0x14000b900`
- end: `0x14000baec`
- name: `NdisWanCancelRoutine`
- size: `492`
- prototype: `void __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000a648`
- `0x14000b900`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000bac8`
- `ntoskrnl!IofCompleteRequest` at `0x14000bac8`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000b94d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000b94d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b9ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b9ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000baa8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b9ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b9ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000baa8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b960`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b9c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ba0a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b960`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b9c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ba0a`

## pseudocode

```c
void __fastcall NdisWanCancelRoutine(__int64 a1, IRP *a2)
{
  KIRQL v3; // al
  char v4; // di
  __int64 v5; // rsi
  KIRQL v6; // al
  PKSPIN_LOCK v7; // rcx
  KIRQL v8; // al
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 *v11; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a2);
  }
  IoReleaseCancelSpinLock(a2->CancelIrql);
  v3 = KeAcquireSpinLockRaiseToDpc(&NdisWanCB);
  byte_14001E288 = v3;
  if ( a2 == Irp )
  {
    Irp = 0;
LABEL_9:
    v4 = 1;
    goto LABEL_10;
  }
  v4 = 0;
  if ( a2 == qword_14001E2E0 )
  {
    qword_14001E2E0 = 0;
    goto LABEL_9;
  }
LABEL_10:
  KeReleaseSpinLock(&NdisWanCB, v3);
  v5 = 0;
  if ( !v4 )
  {
    v6 = KeAcquireSpinLockRaiseToDpc(ProtocolInfoTable);
    v7 = ProtocolInfoTable;
    *((_BYTE *)ProtocolInfoTable + 8) = v6;
    if ( a2 == (IRP *)v7[4] )
    {
      v7[4] = 0;
      v4 = 1;
    }
    KeReleaseSpinLock(v7, v6);
    if ( !v4 )
    {
      v8 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      v9 = (__int64 *)qword_14001E308;
      byte_14001E3D8 = v8;
      while ( 1 )
      {
        v5 = 0;
        if ( v9 == &qword_14001E308 )
          break;
        if ( v9 - 21 == (__int64 *)a2 )
        {
          --IoRecvList;
          v10 = *v9;
          if ( *(__int64 **)(*v9 + 8) != v9 || (v11 = (__int64 *)v9[1], (__int64 *)*v11 != v9) )
            __fastfail(3u);
          *v11 = v10;
          *(_QWORD *)(v10 + 8) = v11;
          LOWORD(a2->AssociatedIrp.MasterIrp->Flags) = -21582;
          dword_14001E320 = 0;
          v5 = 32;
          qword_14001E318 = (__int64)a2;
          dword_14001E328 = 32;
          dword_14001E324 = *(_DWORD *)a2->AssociatedIrp.MasterIrp;
          break;
        }
        v9 = (__int64 *)*v9;
      }
      KeReleaseSpinLock(&SpinLock, byte_14001E3D8);
    }
  }
  a2->Cancel = 1;
  a2->IoStatus.Status = -1073741536;
  a2->IoStatus.Information = v5;
  IofCompleteRequest(a2, 2);
}

```

## disassembly

```asm
0x14000b900  mov     [rsp+arg_0], rbx
0x14000b905  mov     [rsp+arg_8], rsi
0x14000b90a  push    rdi
0x14000b90b  sub     rsp, 20h
0x14000b90f  mov     rbx, rdx
0x14000b912  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b919  lea     rax, WPP_GLOBAL_Control
0x14000b920  cmp     rcx, rax
0x14000b923  jz      short loc_14000B94A
0x14000b925  mov     eax, [rcx+2Ch]
0x14000b928  test    al, 20h
0x14000b92a  jz      short loc_14000B94A
0x14000b92c  cmp     byte ptr [rcx+29h], 5
0x14000b930  jb      short loc_14000B94A
0x14000b932  mov     rcx, [rcx+18h]
0x14000b936  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14000b93d  mov     edx, 10h
0x14000b942  mov     r9, rbx
0x14000b945  call    WPP_SF_q
0x14000b94a  mov     cl, [rbx+45h]; Irql
0x14000b94d  call    cs:__imp_IoReleaseCancelSpinLock
0x14000b954  nop     dword ptr [rax+rax+00h]
0x14000b959  lea     rcx, NdisWanCB; SpinLock
0x14000b960  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b967  nop     dword ptr [rax+rax+00h]
0x14000b96c  cmp     rbx, cs:Irp
0x14000b973  mov     cs:byte_14001E288, al
0x14000b979  jnz     short loc_14000B988
0x14000b97b  mov     cs:Irp, 0
0x14000b986  jmp     short loc_14000B99F
0x14000b988  xor     dil, dil
0x14000b98b  cmp     rbx, cs:qword_14001E2E0
0x14000b992  jnz     short loc_14000B9A2
0x14000b994  mov     cs:qword_14001E2E0, 0
0x14000b99f  mov     dil, 1
0x14000b9a2  mov     dl, al; NewIrql
0x14000b9a4  lea     rcx, NdisWanCB; SpinLock
0x14000b9ab  call    cs:__imp_KeReleaseSpinLock
0x14000b9b2  nop     dword ptr [rax+rax+00h]
0x14000b9b7  xor     esi, esi
0x14000b9b9  test    dil, dil
0x14000b9bc  jnz     loc_14000BAB4
0x14000b9c2  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x14000b9c9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b9d0  nop     dword ptr [rax+rax+00h]
0x14000b9d5  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x14000b9dc  mov     [rcx+8], al
0x14000b9df  cmp     rbx, [rcx+20h]
0x14000b9e3  jnz     short loc_14000B9EC
0x14000b9e5  mov     [rcx+20h], rsi
0x14000b9e9  mov     dil, 1
0x14000b9ec  mov     dl, al; NewIrql
0x14000b9ee  call    cs:__imp_KeReleaseSpinLock
0x14000b9f5  nop     dword ptr [rax+rax+00h]
0x14000b9fa  test    dil, dil
0x14000b9fd  jnz     loc_14000BAB4
0x14000ba03  lea     rcx, SpinLock; SpinLock
0x14000ba0a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ba11  nop     dword ptr [rax+rax+00h]
0x14000ba16  mov     rcx, cs:qword_14001E308
0x14000ba1d  mov     cs:byte_14001E3D8, al
0x14000ba23  xor     esi, esi
0x14000ba25  lea     rax, qword_14001E308
0x14000ba2c  cmp     rcx, rax
0x14000ba2f  jz      short loc_14000BA9B
0x14000ba31  lea     rax, [rcx-0A8h]
0x14000ba38  cmp     rax, rbx
0x14000ba3b  jz      short loc_14000BA42
0x14000ba3d  mov     rcx, [rcx]
0x14000ba40  jmp     short loc_14000BA23
0x14000ba42  dec     cs:IoRecvList
0x14000ba48  mov     rax, [rcx]
0x14000ba4b  cmp     [rax+8], rcx
0x14000ba4f  jnz     loc_14000BAE5
0x14000ba55  mov     rdx, [rcx+8]
0x14000ba59  cmp     [rdx], rcx
0x14000ba5c  jnz     loc_14000BAE5
0x14000ba62  mov     [rdx], rax
0x14000ba65  mov     [rax+8], rdx
0x14000ba69  mov     rax, [rbx+18h]
0x14000ba6d  mov     word ptr [rax+10h], 0ABB2h
0x14000ba73  mov     cs:dword_14001E320, esi
0x14000ba79  mov     esi, 20h ; ' '
0x14000ba7e  mov     cs:qword_14001E318, rbx
0x14000ba85  mov     cs:dword_14001E328, 20h ; ' '
0x14000ba8f  mov     rax, [rbx+18h]
0x14000ba93  mov     ecx, [rax]
0x14000ba95  mov     cs:dword_14001E324, ecx
0x14000ba9b  mov     dl, cs:byte_14001E3D8; NewIrql
0x14000baa1  lea     rcx, SpinLock; SpinLock
0x14000baa8  call    cs:__imp_KeReleaseSpinLock
0x14000baaf  nop     dword ptr [rax+rax+00h]
0x14000bab4  mov     dl, 2; PriorityBoost
0x14000bab6  mov     byte ptr [rbx+44h], 1
0x14000baba  mov     rcx, rbx; Irp
0x14000babd  mov     dword ptr [rbx+30h], 0C0000120h
0x14000bac4  mov     [rbx+38h], rsi
0x14000bac8  call    cs:__imp_IofCompleteRequest
0x14000bacf  nop     dword ptr [rax+rax+00h]
0x14000bad4  mov     rbx, [rsp+28h+arg_0]
0x14000bad9  mov     rsi, [rsp+28h+arg_8]
0x14000bade  add     rsp, 20h
0x14000bae2  pop     rdi
0x14000bae3  retn
0x14000bae5  mov     ecx, 3
0x14000baea  int     29h; Win8: RtlFailFast(ecx)
```
