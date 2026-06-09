# ProtoUnbindAdapterEx

- ea: `0x140005a80`
- end: `0x140005dca`
- name: `ProtoUnbindAdapterEx`
- size: `842`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140005a80`
- `0x140005dd0`
- `0x140006080`
- `0x14000a290`
- `0x14000a648`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140005d32`
- `ntoskrnl!IofCompleteRequest` at `0x140005d32`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005cde`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005cde`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005d1a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005d87`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005d1a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005d87`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005c60`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005c60`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005af9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005b5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005bfd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005c2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005c40`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005af9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005b5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005bfd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005c2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005c40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005ab4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005b40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c0d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c8b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005ab4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005b40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c0d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c8b`
- `NDIS!NdisWaitEvent` at `0x140005b2d`
- `NDIS!NdisWaitEvent` at `0x140005b2d`
- `NDIS!NdisSetEvent` at `0x140005b1c`
- `NDIS!NdisSetEvent` at `0x140005b1c`

## pseudocode

```c
__int64 __fastcall ProtoUnbindAdapterEx(__int64 a1, __int64 a2)
{
  KIRQL v4; // al
  KIRQL v5; // dl
  KIRQL v6; // al
  KSPIN_LOCK **v8; // rsi
  KSPIN_LOCK *v9; // rdi
  KSPIN_LOCK *v10; // rax
  KSPIN_LOCK **v11; // rcx
  KIRQL v12; // al
  bool v13; // zf
  PIRP v14; // rdi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids, a2);
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 504));
  *(_DWORD *)(a2 + 20) |= 0x20u;
  while ( 1 )
  {
    *(_BYTE *)(a2 + 512) = v4;
    if ( !*(_DWORD *)(a2 + 448) )
      break;
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 504), v4);
    KeWaitForSingleObject((PVOID)(a2 + 456), Executive, 0, 1u, 0);
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 504));
  }
  if ( *(_DWORD *)(a2 + 48) )
  {
    KeAcquireSpinLockAtDpcLevel(&NdisWanCB);
    v14 = qword_14001E2E0;
    if ( qword_14001E2E0
      && !qword_14001E2E0->Cancel
      && _InterlockedExchange64((volatile __int64 *)&qword_14001E2E0->CancelRoutine, 0) )
    {
      qword_14001E2E0 = 0;
      KeReleaseSpinLockFromDpcLevel(&NdisWanCB);
      v14->IoStatus.Status = 0;
      v14->IoStatus.Information = 0;
      IofCompleteRequest(v14, 2);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
      }
    }
    else
    {
      KeReleaseSpinLockFromDpcLevel(&NdisWanCB);
    }
  }
  if ( (*(_DWORD *)(a2 + 20) & 1) == 0 )
  {
    v8 = (KSPIN_LOCK **)(a2 + 224);
    while ( 1 )
    {
      v9 = *v8;
      if ( *v8 == (KSPIN_LOCK *)v8 )
        break;
      if ( (KSPIN_LOCK **)v9[1] != v8
        || (v10 = (KSPIN_LOCK *)*v9, *(KSPIN_LOCK **)(*v9 + 8) != v9)
        || (*v8 = v10, v10[1] = (KSPIN_LOCK)v8, v11 = *(KSPIN_LOCK ***)(a2 + 248), *v11 != (KSPIN_LOCK *)(a2 + 240)) )
      {
        __fastfail(3u);
      }
      v9[1] = (KSPIN_LOCK)v11;
      *v9 = a2 + 240;
      *v11 = v9;
      *(_QWORD *)(a2 + 248) = v9;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 504), *(_BYTE *)(a2 + 512));
      v12 = KeAcquireSpinLockRaiseToDpc(v9 + 11);
      *((_DWORD *)v9 + 6) |= 0x200u;
      v13 = (*((_DWORD *)v9 + 5))-- == 1;
      *((_BYTE *)v9 + 96) = v12;
      if ( v13 )
        DoDerefClAfSapCBWork(v9);
      else
        KeReleaseSpinLock(v9 + 11, v12);
      *(_BYTE *)(a2 + 512) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 504));
    }
  }
  v5 = *(_BYTE *)(a2 + 512);
  *(_QWORD *)(a2 + 112) = a1;
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 504), v5);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 16), 0xFFFFFFFF) == 1 )
    NdisSetEvent((PNDIS_EVENT)(a2 + 552));
  NdisWaitEvent((PNDIS_EVENT)(a2 + 552), 0);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 504));
  *(_DWORD *)(a2 + 20) &= ~0x20u;
  *(_BYTE *)(a2 + 512) = v6;
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 504), v6);
  ProtoCloseWanAdapter((PVOID)a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  return 259;
}

```

## disassembly

```asm
0x140005a80  push    rbx
0x140005a82  push    rbp
0x140005a83  push    rsi
0x140005a84  push    rdi
0x140005a85  push    r14
0x140005a87  push    r15
0x140005a89  sub     rsp, 38h
0x140005a8d  mov     rbx, rdx
0x140005a90  mov     r15, rcx
0x140005a93  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a9a  lea     r14, WPP_GLOBAL_Control
0x140005aa1  cmp     rcx, r14
0x140005aa4  jnz     loc_140005CA2
0x140005aaa  lea     rbp, [rbx+1F8h]
0x140005ab1  mov     rcx, rbp; SpinLock
0x140005ab4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005abb  nop     dword ptr [rax+rax+00h]
0x140005ac0  or      dword ptr [rbx+14h], 20h
0x140005ac4  xor     esi, esi
0x140005ac6  mov     [rbx+200h], al
0x140005acc  cmp     [rbx+1C0h], esi
0x140005ad2  jnz     loc_140005C3B
0x140005ad8  cmp     [rbx+30h], esi
0x140005adb  jnz     loc_140005CD4
0x140005ae1  mov     eax, [rbx+14h]
0x140005ae4  test    al, 1
0x140005ae6  jz      loc_140005B99
0x140005aec  mov     dl, [rbx+200h]; NewIrql
0x140005af2  mov     rcx, rbp; SpinLock
0x140005af5  mov     [rbx+70h], r15
0x140005af9  call    cs:__imp_KeReleaseSpinLock
0x140005b00  nop     dword ptr [rax+rax+00h]
0x140005b05  or      eax, 0FFFFFFFFh
0x140005b08  lock xadd [rbx+10h], eax
0x140005b0d  lea     rdi, [rbx+228h]
0x140005b14  cmp     eax, 1
0x140005b17  jnz     short loc_140005B28
0x140005b19  mov     rcx, rdi; Event
0x140005b1c  call    cs:__imp_NdisSetEvent
0x140005b23  nop     dword ptr [rax+rax+00h]
0x140005b28  xor     edx, edx; MsToWait
0x140005b2a  mov     rcx, rdi; Event
0x140005b2d  call    cs:__imp_NdisWaitEvent
0x140005b34  nop     dword ptr [rax+rax+00h]
0x140005b39  lea     rcx, [rbx+1F8h]; SpinLock
0x140005b40  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005b47  nop     dword ptr [rax+rax+00h]
0x140005b4c  and     dword ptr [rbx+14h], 0FFFFFFDFh
0x140005b50  mov     rcx, rbp; SpinLock
0x140005b53  mov     dl, al; NewIrql
0x140005b55  mov     [rbx+200h], al
0x140005b5b  call    cs:__imp_KeReleaseSpinLock
0x140005b62  nop     dword ptr [rax+rax+00h]
0x140005b67  mov     rcx, rbx; P
0x140005b6a  call    ProtoCloseWanAdapter
0x140005b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b76  cmp     rcx, r14
0x140005b79  jz      short loc_140005B86
0x140005b7b  mov     eax, [rcx+2Ch]
0x140005b7e  test    al, 4
0x140005b80  jnz     loc_140005DA6
0x140005b86  mov     eax, 103h
0x140005b8b  add     rsp, 38h
0x140005b8f  pop     r15
0x140005b91  pop     r14
0x140005b93  pop     rdi
0x140005b94  pop     rsi
0x140005b95  pop     rbp
0x140005b96  pop     rbx
0x140005b97  retn
0x140005b99  lea     rsi, [rbx+0E0h]
0x140005ba0  mov     rdi, [rsi]
0x140005ba3  cmp     rdi, rsi
0x140005ba6  jnz     short loc_140005BB4
0x140005ba8  lea     r14, WPP_GLOBAL_Control
0x140005baf  jmp     loc_140005AEC
0x140005bb4  cmp     [rdi+8], rsi
0x140005bb8  jnz     loc_140005D9F
0x140005bbe  mov     rax, [rdi]
0x140005bc1  cmp     [rax+8], rdi
0x140005bc5  jnz     loc_140005D9F
0x140005bcb  mov     [rsi], rax
0x140005bce  mov     [rax+8], rsi
0x140005bd2  lea     rax, [rbx+0F0h]
0x140005bd9  mov     rcx, [rax+8]
0x140005bdd  cmp     [rcx], rax
0x140005be0  jnz     loc_140005D9F
0x140005be6  mov     [rdi+8], rcx
0x140005bea  mov     [rdi], rax
0x140005bed  mov     [rcx], rdi
0x140005bf0  mov     rcx, rbp; SpinLock
0x140005bf3  mov     [rax+8], rdi
0x140005bf7  mov     dl, [rbx+200h]; NewIrql
0x140005bfd  call    cs:__imp_KeReleaseSpinLock
0x140005c04  nop     dword ptr [rax+rax+00h]
0x140005c09  lea     rcx, [rdi+58h]; SpinLock
0x140005c0d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005c14  nop     dword ptr [rax+rax+00h]
0x140005c19  bts     dword ptr [rdi+18h], 9
0x140005c1e  add     dword ptr [rdi+14h], 0FFFFFFFFh
0x140005c22  mov     [rdi+60h], al
0x140005c25  jz      short loc_140005C80
0x140005c27  mov     dl, al; NewIrql
0x140005c29  lea     rcx, [rdi+58h]; SpinLock
0x140005c2d  call    cs:__imp_KeReleaseSpinLock
0x140005c34  nop     dword ptr [rax+rax+00h]
0x140005c39  jmp     short loc_140005C88
0x140005c3b  mov     dl, al; NewIrql
0x140005c3d  mov     rcx, rbp; SpinLock
0x140005c40  call    cs:__imp_KeReleaseSpinLock
0x140005c47  nop     dword ptr [rax+rax+00h]
0x140005c4c  mov     r9b, 1; Alertable
0x140005c4f  mov     [rsp+68h+Timeout], rsi; Timeout
0x140005c54  xor     r8d, r8d; WaitMode
0x140005c57  lea     rcx, [rbx+1C8h]; Object
0x140005c5e  xor     edx, edx; WaitReason
0x140005c60  call    cs:__imp_KeWaitForSingleObject
0x140005c67  nop     dword ptr [rax+rax+00h]
0x140005c6c  mov     rcx, rbp; SpinLock
0x140005c6f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005c76  nop     dword ptr [rax+rax+00h]
0x140005c7b  jmp     loc_140005AC6
0x140005c80  mov     rcx, rdi
0x140005c83  call    DoDerefClAfSapCBWork
0x140005c88  mov     rcx, rbp; SpinLock
0x140005c8b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005c92  nop     dword ptr [rax+rax+00h]
0x140005c97  mov     [rbx+200h], al
0x140005c9d  jmp     loc_140005BA0
0x140005ca2  mov     eax, [rcx+2Ch]
0x140005ca5  test    al, 4
0x140005ca7  jz      loc_140005AAA
0x140005cad  cmp     byte ptr [rcx+29h], 5
0x140005cb1  jb      loc_140005AAA
0x140005cb7  mov     rcx, [rcx+18h]
0x140005cbb  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140005cc2  mov     edx, 1Eh
0x140005cc7  mov     r9, rbx
0x140005cca  call    WPP_SF_q
0x140005ccf  jmp     loc_140005AAA
0x140005cd4  lea     r14, NdisWanCB
0x140005cdb  mov     rcx, r14; SpinLock
0x140005cde  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140005ce5  nop     dword ptr [rax+rax+00h]
0x140005cea  mov     rdi, cs:qword_14001E2E0
0x140005cf1  test    rdi, rdi
0x140005cf4  jz      loc_140005D84
0x140005cfa  cmp     [rdi+44h], sil
0x140005cfe  jnz     loc_140005D84
0x140005d04  mov     rax, rsi
0x140005d07  xchg    rax, [rdi+68h]
0x140005d0b  test    rax, rax
0x140005d0e  jz      short loc_140005D84
0x140005d10  mov     rcx, r14; SpinLock
0x140005d13  mov     cs:qword_14001E2E0, rsi
0x140005d1a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005d21  nop     dword ptr [rax+rax+00h]
0x140005d26  mov     dl, 2; PriorityBoost
0x140005d28  mov     [rdi+30h], esi
0x140005d2b  mov     rcx, rdi; Irp
0x140005d2e  mov     [rdi+38h], rsi
0x140005d32  call    cs:__imp_IofCompleteRequest
0x140005d39  nop     dword ptr [rax+rax+00h]
0x140005d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d45  lea     r14, WPP_GLOBAL_Control
0x140005d4c  cmp     rcx, r14
0x140005d4f  jz      loc_140005AE1
0x140005d55  mov     eax, [rcx+2Ch]
0x140005d58  test    al, 4
0x140005d5a  jz      loc_140005AE1
0x140005d60  cmp     byte ptr [rcx+29h], 5
0x140005d64  jb      loc_140005AE1
0x140005d6a  mov     rcx, [rcx+18h]
0x140005d6e  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140005d75  mov     edx, 1Fh
0x140005d7a  call    WPP_SF_
0x140005d7f  jmp     loc_140005AE1
0x140005d84  mov     rcx, r14; SpinLock
0x140005d87  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005d8e  nop     dword ptr [rax+rax+00h]
0x140005d93  lea     r14, WPP_GLOBAL_Control
0x140005d9a  jmp     loc_140005AE1
0x140005d9f  mov     ecx, 3
0x140005da4  int     29h; Win8: RtlFailFast(ecx)
0x140005da6  cmp     byte ptr [rcx+29h], 5
0x140005daa  jb      loc_140005B86
0x140005db0  mov     rcx, [rcx+18h]
0x140005db4  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140005dbb  mov     edx, 20h ; ' '
0x140005dc0  call    WPP_SF_
0x140005dc5  jmp     loc_140005B86
```
