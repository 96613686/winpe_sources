# ACCancelSender

- ea: `0x140011f30`
- end: `0x140012063`
- name: `ACCancelSender`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140003d84`
- `0x140011dc4`
- `0x140011f30`
- `0x140024bf0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011f80`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140011f80`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011fbe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011fbe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140011fce`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140011fce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140012033`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140012033`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001203f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001203f`
- `ntoskrnl!IofCompleteRequest` at `0x140012023`
- `ntoskrnl!IofCompleteRequest` at `0x140012023`

## pseudocode

```c
void __fastcall ACCancelSender(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rax
  __int64 v4; // r8
  _QWORD *v5; // rdx
  __int64 v6; // rsi
  __int64 v7; // rdi
  struct CPacket *Packet; // rax

  v2 = (_QWORD *)(a2 + 168);
  v4 = *(_QWORD *)(a2 + 168);
  if ( *(_QWORD *)(v4 + 8) != a2 + 168 || (v5 = *(_QWORD **)(a2 + 176), (_QWORD *)*v5 != v2) )
    __fastfail(3u);
  v6 = *(_QWORD *)(a1 + 64);
  *v5 = v4;
  *(_QWORD *)(v4 + 8) = v5;
  *v2 = 0;
  v2[1] = 0;
  IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, &WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids, a2);
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v6 + 8));
  v7 = a2 + 56;
  if ( (*(_DWORD *)(a2 + 144) & 0x80) != 0 )
    *(_BYTE *)(*(_QWORD *)v7 + 24LL) = 0;
  Packet = CIrp2Pkt::SafePeekFirstPacket((struct _IRP *)a2);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)Packet + 4) + 160LL))(*((_QWORD *)Packet + 4), a2);
  *(_QWORD *)v7 = 0;
  *(_DWORD *)(a2 + 48) = -1073741536;
  IofCompleteRequest((PIRP)a2, 0);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 8));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140011f30  mov     [rsp+arg_0], rbx
0x140011f35  mov     [rsp+arg_8], rsi
0x140011f3a  push    rdi
0x140011f3b  sub     rsp, 20h
0x140011f3f  lea     rax, [rdx+0A8h]
0x140011f46  mov     rbx, rdx
0x140011f49  mov     r8, [rax]
0x140011f4c  cmp     [r8+8], rax
0x140011f50  jnz     loc_14001205C
0x140011f56  mov     rdx, [rax+8]
0x140011f5a  cmp     [rdx], rax
0x140011f5d  jnz     loc_14001205C
0x140011f63  mov     rsi, [rcx+40h]
0x140011f67  mov     [rdx], r8
0x140011f6a  mov     [r8+8], rdx
0x140011f6e  mov     qword ptr [rax], 0
0x140011f75  mov     qword ptr [rax+8], 0
0x140011f7d  mov     cl, [rbx+45h]; Irql
0x140011f80  call    cs:__imp_IoReleaseCancelSpinLock
0x140011f87  nop     dword ptr [rax+rax+00h]
0x140011f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f93  lea     rax, WPP_GLOBAL_Control
0x140011f9a  cmp     rcx, rax
0x140011f9d  jz      short loc_140011FBE
0x140011f9f  mov     eax, [rcx+6Ch]
0x140011fa2  test    al, 4
0x140011fa4  jz      short loc_140011FBE
0x140011fa6  mov     rcx, [rcx+58h]
0x140011faa  lea     r8, WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids
0x140011fb1  mov     edx, 0Ah
0x140011fb6  mov     r9, rbx
0x140011fb9  call    WPP_SF_q
0x140011fbe  call    cs:__imp_KeEnterCriticalRegion
0x140011fc5  nop     dword ptr [rax+rax+00h]
0x140011fca  lea     rcx, [rsi+8]; FastMutex
0x140011fce  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140011fd5  nop     dword ptr [rax+rax+00h]
0x140011fda  mov     eax, [rbx+90h]
0x140011fe0  lea     rdi, [rbx+38h]
0x140011fe4  shr     eax, 7
0x140011fe7  test    al, 1
0x140011fe9  jz      short loc_140011FF2
0x140011feb  mov     rax, [rdi]
0x140011fee  mov     byte ptr [rax+18h], 0
0x140011ff2  mov     rcx, rbx; struct _IRP *
0x140011ff5  call    ?SafePeekFirstPacket@CIrp2Pkt@@SAPEAVCPacket@@PEAU_IRP@@@Z; CIrp2Pkt::SafePeekFirstPacket(_IRP *)
0x140011ffa  mov     rdx, rbx
0x140011ffd  mov     rcx, [rax+20h]
0x140012001  mov     rax, [rcx]
0x140012004  mov     rax, [rax+0A0h]
0x14001200b  call    _guard_dispatch_icall
0x140012010  xor     edx, edx; PriorityBoost
0x140012012  mov     qword ptr [rdi], 0
0x140012019  mov     rcx, rbx; Irp
0x14001201c  mov     dword ptr [rbx+30h], 0C0000120h
0x140012023  call    cs:__imp_IofCompleteRequest
0x14001202a  nop     dword ptr [rax+rax+00h]
0x14001202f  lea     rcx, [rsi+8]; FastMutex
0x140012033  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001203a  nop     dword ptr [rax+rax+00h]
0x14001203f  call    cs:__imp_KeLeaveCriticalRegion
0x140012046  nop     dword ptr [rax+rax+00h]
0x14001204b  mov     rbx, [rsp+28h+arg_0]
0x140012050  mov     rsi, [rsp+28h+arg_8]
0x140012055  add     rsp, 20h
0x140012059  pop     rdi
0x14001205a  retn
0x14001205c  mov     ecx, 3
0x140012061  int     29h; Win8: RtlFailFast(ecx)
```
