# ScmCmIncomingCallComplete

- ea: `0x140013eb0`
- end: `0x1400140bb`
- name: `ScmCmIncomingCallComplete`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140010fd4`

## callees

- `0x1400018b0`
- `0x140002030`
- `0x140002bd8`
- `0x140002fc4`
- `0x140006240`
- `0x140013eb0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013f36`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013fca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014024`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013f36`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013fca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014024`
- `ntoskrnl!IofCompleteRequest` at `0x140014074`
- `ntoskrnl!IofCompleteRequest` at `0x140014074`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f80`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001403c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f80`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001403c`
- `NDIS!NdisCmDispatchCallConnected` at `0x14001404c`
- `NDIS!NdisCmDispatchCallConnected` at `0x14001404c`

## pseudocode

```c
void __fastcall ScmCmIncomingCallComplete(int a1, __int64 a2)
{
  KIRQL v4; // al
  int v5; // r14d
  __int64 v6; // rdi
  __int64 v7; // r8
  _DWORD *v8; // rbx
  KIRQL v9; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_D(
        WPP_GLOBAL_Control->AttachedDevice,
        42,
        WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids,
        a2 + 484,
        a1);
    }
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  *(_DWORD *)(a2 + 21088) &= ~0x100u;
  v5 = -1073741247;
  v6 = *(_QWORD *)(a2 + 56);
  if ( !*(_BYTE *)(a2 + 21092) )
    v5 = a1;
  *(_QWORD *)(a2 + 56) = 0;
  if ( v6 )
    v6 &= -(__int64)(_InterlockedExchange64((volatile __int64 *)(v6 + 104), 0) != 0);
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), v4);
  if ( !v5 && v6 )
    goto LABEL_20;
  if ( !v6
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  }
  LOBYTE(v7) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  InitiateSstpContextCleanup(a2, 4, v7);
  if ( v6 )
  {
LABEL_20:
    v8 = *(_DWORD **)(v6 + 24);
    memset(v8, 0, 0x78u);
    v8[8] = v5;
    *v8 = *(_DWORD *)(a2 + 116);
    v8[9] = *(_DWORD *)(a2 + 112);
    *((_OWORD *)v8 + 6) = *(_OWORD *)(a2 + 484);
    if ( !v5 )
    {
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
      *(_DWORD *)(a2 + 21088) |= 0x40u;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), v9);
      NdisCmDispatchCallConnected(*(NDIS_HANDLE *)(a2 + 40));
    }
    *(_QWORD *)(v6 + 56) = 120;
    *(_DWORD *)(v6 + 48) = 0;
    DereferenceRefCount(a2);
    IofCompleteRequest((PIRP)v6, 2);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
}

```

## disassembly

```asm
0x140013eb0  push    rbx
0x140013eb2  push    rbp
0x140013eb3  push    rsi
0x140013eb4  push    rdi
0x140013eb5  push    r13
0x140013eb7  push    r14
0x140013eb9  sub     rsp, 38h
0x140013ebd  mov     rsi, rdx
0x140013ec0  mov     ebx, ecx
0x140013ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ec9  lea     r13, WPP_GLOBAL_Control
0x140013ed0  cmp     rcx, r13
0x140013ed3  jz      short loc_140013F2F
0x140013ed5  mov     eax, [rcx+2Ch]
0x140013ed8  and     eax, 81h
0x140013edd  cmp     al, 81h
0x140013edf  jnz     short loc_140013EF6
0x140013ee1  mov     rcx, [rcx+18h]
0x140013ee5  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140013eec  mov     edx, 29h ; ')'
0x140013ef1  call    WPP_SF_
0x140013ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x140013efd  cmp     rcx, r13
0x140013f00  jz      short loc_140013F2F
0x140013f02  mov     eax, [rcx+2Ch]
0x140013f05  test    al, 1
0x140013f07  jz      short loc_140013F2F
0x140013f09  cmp     byte ptr [rcx+29h], 3
0x140013f0d  jb      short loc_140013F2F
0x140013f0f  mov     rcx, [rcx+18h]
0x140013f13  lea     r9, [rsi+1E4h]
0x140013f1a  mov     edx, 2Ah ; '*'
0x140013f1f  mov     [rsp+68h+var_48], ebx
0x140013f23  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140013f2a  call    WPP_SF__guid_D
0x140013f2f  lea     rbp, [rsi+20h]
0x140013f33  mov     rcx, rbp; SpinLock
0x140013f36  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013f3d  nop     dword ptr [rax+rax+00h]
0x140013f42  btr     dword ptr [rsi+5260h], 8
0x140013f4a  mov     r14d, 0C0000241h
0x140013f50  cmp     byte ptr [rsi+5264h], 0
0x140013f57  mov     dl, al; NewIrql
0x140013f59  mov     rdi, [rsi+38h]
0x140013f5d  cmovz   r14d, ebx
0x140013f61  mov     qword ptr [rsi+38h], 0
0x140013f69  test    rdi, rdi
0x140013f6c  jz      short loc_140013F7D
0x140013f6e  xor     eax, eax
0x140013f70  xchg    rax, [rdi+68h]
0x140013f74  neg     rax
0x140013f77  sbb     rax, rax
0x140013f7a  and     rdi, rax
0x140013f7d  mov     rcx, rbp; SpinLock
0x140013f80  call    cs:__imp_KeReleaseSpinLock
0x140013f87  nop     dword ptr [rax+rax+00h]
0x140013f8c  test    r14d, r14d
0x140013f8f  jnz     short loc_140013F96
0x140013f91  test    rdi, rdi
0x140013f94  jnz     short loc_140013FEF
0x140013f96  test    rdi, rdi
0x140013f99  jnz     short loc_140013FC7
0x140013f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013fa2  cmp     rcx, r13
0x140013fa5  jz      short loc_140013FC7
0x140013fa7  mov     eax, [rcx+2Ch]
0x140013faa  test    al, 2
0x140013fac  jz      short loc_140013FC7
0x140013fae  cmp     byte ptr [rcx+29h], 1
0x140013fb2  jb      short loc_140013FC7
0x140013fb4  mov     rcx, [rcx+18h]
0x140013fb8  lea     edx, [rdi+2Bh]
0x140013fbb  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140013fc2  call    WPP_SF_
0x140013fc7  mov     rcx, rbp; SpinLock
0x140013fca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013fd1  nop     dword ptr [rax+rax+00h]
0x140013fd6  mov     edx, 4
0x140013fdb  mov     rcx, rsi
0x140013fde  mov     r8b, al
0x140013fe1  call    InitiateSstpContextCleanup
0x140013fe6  test    rdi, rdi
0x140013fe9  jz      loc_140014080
0x140013fef  mov     rbx, [rdi+18h]
0x140013ff3  xor     edx, edx; Val
0x140013ff5  mov     rcx, rbx; void *
0x140013ff8  lea     r8d, [rdx+78h]; Size
0x140013ffc  call    memset
0x140014001  mov     [rbx+20h], r14d
0x140014005  mov     eax, [rsi+74h]
0x140014008  mov     [rbx], eax
0x14001400a  mov     eax, [rsi+70h]
0x14001400d  mov     [rbx+24h], eax
0x140014010  movups  xmm0, xmmword ptr [rsi+1E4h]
0x140014017  movdqu  xmmword ptr [rbx+60h], xmm0
0x14001401c  test    r14d, r14d
0x14001401f  jnz     short loc_140014058
0x140014021  mov     rcx, rbp; SpinLock
0x140014024  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001402b  nop     dword ptr [rax+rax+00h]
0x140014030  or      dword ptr [rsi+5260h], 40h
0x140014037  mov     rcx, rbp; SpinLock
0x14001403a  mov     dl, al; NewIrql
0x14001403c  call    cs:__imp_KeReleaseSpinLock
0x140014043  nop     dword ptr [rax+rax+00h]
0x140014048  mov     rcx, [rsi+28h]; NdisVcHandle
0x14001404c  call    cs:__imp_NdisCmDispatchCallConnected
0x140014053  nop     dword ptr [rax+rax+00h]
0x140014058  mov     rcx, rsi
0x14001405b  mov     qword ptr [rdi+38h], 78h ; 'x'
0x140014063  mov     dword ptr [rdi+30h], 0
0x14001406a  call    DereferenceRefCount
0x14001406f  mov     dl, 2; PriorityBoost
0x140014071  mov     rcx, rdi; Irp
0x140014074  call    cs:__imp_IofCompleteRequest
0x14001407b  nop     dword ptr [rax+rax+00h]
0x140014080  mov     rcx, cs:WPP_GLOBAL_Control
0x140014087  cmp     rcx, r13
0x14001408a  jz      short loc_1400140AD
0x14001408c  mov     eax, [rcx+2Ch]
0x14001408f  and     eax, 81h
0x140014094  cmp     al, 81h
0x140014096  jnz     short loc_1400140AD
0x140014098  mov     rcx, [rcx+18h]
0x14001409c  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x1400140a3  mov     edx, 2Ch ; ','
0x1400140a8  call    WPP_SF_
0x1400140ad  add     rsp, 38h
0x1400140b1  pop     r14
0x1400140b3  pop     r13
0x1400140b5  pop     rdi
0x1400140b6  pop     rsi
0x1400140b7  pop     rbp
0x1400140b8  pop     rbx
0x1400140b9  retn
```
