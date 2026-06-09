# ProtoPnPEventLegacy

- ea: `0x14000fb30`
- end: `0x14000fd76`
- name: `ProtoPnPEventLegacy`
- size: `582`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000ed9c`
- `0x14000fb30`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000fd04`
- `ntoskrnl!IofCompleteRequest` at `0x14000fd04`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fc17`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fce4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fd2e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fc17`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fce4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fd2e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fbd6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fca7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fd13`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fbd6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fca7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fd13`

## pseudocode

```c
__int64 __fastcall ProtoPnPEventLegacy(__int64 a1, __int64 a2)
{
  unsigned int v4; // esi
  int v5; // ebx
  int v6; // ebx
  KIRQL v7; // al
  PIRP v8; // rdi
  int v9; // ebx
  int v10; // ebx
  KIRQL v11; // al

  if ( !a1 )
    return 0;
  v4 = 0;
  if ( !*(_DWORD *)a2 )
  {
    v9 = **(_DWORD **)(a2 + 8);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qsd(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        (unsigned int)WPP_714410adb39534c9cec6a41078899c0f_Traceguids,
        a1,
        (__int64)"SetPower",
        v9);
    }
    v10 = v9 - 2;
    if ( v10 && (unsigned int)(v10 - 1) > 1 )
      goto LABEL_26;
    v4 = -1073741637;
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 48), 0, 0) )
      goto LABEL_26;
    v11 = KeAcquireSpinLockRaiseToDpc(&NdisWanCB);
    v8 = Irp;
    byte_14001E288 = v11;
    if ( !Irp || !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
      goto LABEL_25;
    goto LABEL_24;
  }
  if ( *(_DWORD *)a2 != 1 )
    goto LABEL_26;
  v5 = **(_DWORD **)(a2 + 8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qsd(
      WPP_GLOBAL_Control->AttachedDevice,
      41,
      (unsigned int)WPP_714410adb39534c9cec6a41078899c0f_Traceguids,
      a1,
      (__int64)"QueryPower",
      v5);
  }
  v6 = v5 - 2;
  if ( v6 )
  {
    if ( (unsigned int)(v6 - 1) > 1 )
      goto LABEL_26;
  }
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 48), 0, 0) )
    goto LABEL_26;
  v7 = KeAcquireSpinLockRaiseToDpc(&NdisWanCB);
  v8 = Irp;
  byte_14001E288 = v7;
  if ( Irp && _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
  {
LABEL_24:
    Irp = 0;
    KeReleaseSpinLock(&NdisWanCB, byte_14001E288);
    v8->IoStatus.Status = 0;
    v8->IoStatus.Information = 0;
    IofCompleteRequest(v8, 2);
    byte_14001E288 = KeAcquireSpinLockRaiseToDpc(&NdisWanCB);
  }
LABEL_25:
  KeReleaseSpinLock(&NdisWanCB, byte_14001E288);
LABEL_26:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_714410adb39534c9cec6a41078899c0f_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x14000fb30  push    rbx
0x14000fb32  push    rsi
0x14000fb33  push    rdi
0x14000fb34  push    r12
0x14000fb36  sub     rsp, 38h
0x14000fb3a  mov     rdi, rcx
0x14000fb3d  test    rcx, rcx
0x14000fb40  jnz     short loc_14000FB49
0x14000fb42  xor     eax, eax
0x14000fb44  jmp     loc_14000FD6B
0x14000fb49  mov     ecx, [rdx]
0x14000fb4b  lea     r12, WPP_GLOBAL_Control
0x14000fb52  xor     esi, esi
0x14000fb54  test    ecx, ecx
0x14000fb56  jz      loc_14000FC2F
0x14000fb5c  cmp     ecx, 1
0x14000fb5f  jnz     loc_14000FD3A
0x14000fb65  mov     rax, [rdx+8]
0x14000fb69  mov     ebx, [rax]
0x14000fb6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb72  cmp     rcx, r12
0x14000fb75  jz      short loc_14000FBAA
0x14000fb77  mov     eax, [rcx+2Ch]
0x14000fb7a  test    al, 4
0x14000fb7c  jz      short loc_14000FBAA
0x14000fb7e  cmp     byte ptr [rcx+29h], 5
0x14000fb82  jb      short loc_14000FBAA
0x14000fb84  mov     rcx, [rcx+18h]
0x14000fb88  lea     rax, aQuerypower; "QueryPower"
0x14000fb8f  lea     edx, [rsi+29h]
0x14000fb92  mov     [rsp+58h+var_30], ebx
0x14000fb96  mov     r9, rdi
0x14000fb99  mov     [rsp+58h+var_38], rax
0x14000fb9e  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000fba5  call    WPP_SF_qsd
0x14000fbaa  sub     ebx, 2
0x14000fbad  jz      short loc_14000FBBD
0x14000fbaf  sub     ebx, 1
0x14000fbb2  jz      short loc_14000FBBD
0x14000fbb4  cmp     ebx, 1
0x14000fbb7  jnz     loc_14000FD3A
0x14000fbbd  xor     ecx, ecx
0x14000fbbf  xor     eax, eax
0x14000fbc1  lock cmpxchg [rdi+30h], ecx
0x14000fbc6  jz      loc_14000FD3A
0x14000fbcc  lea     rbx, NdisWanCB
0x14000fbd3  mov     rcx, rbx; SpinLock
0x14000fbd6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fbdd  nop     dword ptr [rax+rax+00h]
0x14000fbe2  mov     rdi, cs:Irp
0x14000fbe9  mov     cs:byte_14001E288, al
0x14000fbef  test    rdi, rdi
0x14000fbf2  jz      loc_14000FD25
0x14000fbf8  xor     eax, eax
0x14000fbfa  xchg    rax, [rdi+68h]
0x14000fbfe  test    rax, rax
0x14000fc01  jz      loc_14000FD25
0x14000fc07  mov     dl, cs:byte_14001E288; NewIrql
0x14000fc0d  mov     rcx, rbx; SpinLock
0x14000fc10  mov     cs:Irp, rsi
0x14000fc17  call    cs:__imp_KeReleaseSpinLock
0x14000fc1e  nop     dword ptr [rax+rax+00h]
0x14000fc23  mov     [rdi+30h], esi
0x14000fc26  mov     [rdi+38h], rsi
0x14000fc2a  jmp     loc_14000FCFF
0x14000fc2f  mov     rax, [rdx+8]
0x14000fc33  mov     ebx, [rax]
0x14000fc35  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc3c  cmp     rcx, r12
0x14000fc3f  jz      short loc_14000FC76
0x14000fc41  mov     eax, [rcx+2Ch]
0x14000fc44  test    al, 4
0x14000fc46  jz      short loc_14000FC76
0x14000fc48  cmp     byte ptr [rcx+29h], 5
0x14000fc4c  jb      short loc_14000FC76
0x14000fc4e  mov     rcx, [rcx+18h]
0x14000fc52  lea     rax, aSetpower; "SetPower"
0x14000fc59  mov     edx, 28h ; '('
0x14000fc5e  mov     [rsp+58h+var_30], ebx
0x14000fc62  mov     r9, rdi
0x14000fc65  mov     [rsp+58h+var_38], rax
0x14000fc6a  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000fc71  call    WPP_SF_qsd
0x14000fc76  sub     ebx, 2
0x14000fc79  jz      short loc_14000FC89
0x14000fc7b  sub     ebx, 1
0x14000fc7e  jz      short loc_14000FC89
0x14000fc80  cmp     ebx, 1
0x14000fc83  jnz     loc_14000FD3A
0x14000fc89  xor     ecx, ecx
0x14000fc8b  mov     esi, 0C00000BBh
0x14000fc90  xor     eax, eax
0x14000fc92  lock cmpxchg [rdi+30h], ecx
0x14000fc97  jz      loc_14000FD3A
0x14000fc9d  lea     rbx, NdisWanCB
0x14000fca4  mov     rcx, rbx; SpinLock
0x14000fca7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fcae  nop     dword ptr [rax+rax+00h]
0x14000fcb3  mov     rdi, cs:Irp
0x14000fcba  mov     cs:byte_14001E288, al
0x14000fcc0  test    rdi, rdi
0x14000fcc3  jz      short loc_14000FD25
0x14000fcc5  xor     eax, eax
0x14000fcc7  xchg    rax, [rdi+68h]
0x14000fccb  test    rax, rax
0x14000fcce  jz      short loc_14000FD25
0x14000fcd0  mov     dl, cs:byte_14001E288; NewIrql
0x14000fcd6  mov     rcx, rbx; SpinLock
0x14000fcd9  mov     cs:Irp, 0
0x14000fce4  call    cs:__imp_KeReleaseSpinLock
0x14000fceb  nop     dword ptr [rax+rax+00h]
0x14000fcf0  mov     dword ptr [rdi+30h], 0
0x14000fcf7  mov     qword ptr [rdi+38h], 0
0x14000fcff  mov     dl, 2; PriorityBoost
0x14000fd01  mov     rcx, rdi; Irp
0x14000fd04  call    cs:__imp_IofCompleteRequest
0x14000fd0b  nop     dword ptr [rax+rax+00h]
0x14000fd10  mov     rcx, rbx; SpinLock
0x14000fd13  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fd1a  nop     dword ptr [rax+rax+00h]
0x14000fd1f  mov     cs:byte_14001E288, al
0x14000fd25  mov     dl, cs:byte_14001E288; NewIrql
0x14000fd2b  mov     rcx, rbx; SpinLock
0x14000fd2e  call    cs:__imp_KeReleaseSpinLock
0x14000fd35  nop     dword ptr [rax+rax+00h]
0x14000fd3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd41  cmp     rcx, r12
0x14000fd44  jz      short loc_14000FD69
0x14000fd46  mov     edx, [rcx+2Ch]
0x14000fd49  test    dl, 4
0x14000fd4c  jz      short loc_14000FD69
0x14000fd4e  cmp     byte ptr [rcx+29h], 5
0x14000fd52  jb      short loc_14000FD69
0x14000fd54  mov     rcx, [rcx+18h]
0x14000fd58  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000fd5f  mov     edx, 2Ah ; '*'
0x14000fd64  call    WPP_SF_
0x14000fd69  mov     eax, esi
0x14000fd6b  add     rsp, 38h
0x14000fd6f  pop     r12
0x14000fd71  pop     rdi
0x14000fd72  pop     rsi
0x14000fd73  pop     rbx
0x14000fd74  retn
```
