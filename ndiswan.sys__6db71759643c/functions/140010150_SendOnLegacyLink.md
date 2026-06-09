# SendOnLegacyLink

- ea: `0x140010150`
- end: `0x140010435`
- name: `SendOnLegacyLink`
- size: `741`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140007a00`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000a744`
- `0x14000f174`
- `0x140010150`
- `0x140016230`
- `0x140016400`
- `0x14002e20c`
- `0x140030940`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140010349`
- `ntoskrnl!KfRaiseIrql` at `0x140010349`
- `ntoskrnl!KeLowerIrql` at `0x140010377`
- `ntoskrnl!KeLowerIrql` at `0x140010377`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400101d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400102b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400102eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010387`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400101d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400102b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400102eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010387`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400101eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400102ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400103e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400101eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400102ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400103e3`
- `NDIS!NdisGetDataBuffer` at `0x140010328`
- `NDIS!NdisGetDataBuffer` at `0x140010328`

## pseudocode

```c
__int64 __fastcall SendOnLegacyLink(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // r13
  _DWORD *v4; // rsi
  struct _NET_BUFFER *v5; // r12
  _QWORD *WanPacket; // rax
  _QWORD *v7; // r15
  KSPIN_LOCK *v8; // rbp
  size_t DataLength; // r14
  KIRQL *v10; // rsi
  KSPIN_LOCK *v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  KIRQL v14; // al
  bool v15; // zf
  KSPIN_LOCK *v16; // rcx
  PVOID DataBuffer; // rax
  KIRQL v18; // bl
  unsigned int v19; // edi

  v1 = *(_QWORD *)(a1 + 40);
  v3 = *(_QWORD *)(a1 + 80);
  v4 = *(_DWORD **)(v1 + 80);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_714410adb39534c9cec6a41078899c0f_Traceguids, v1, v3);
  }
  v5 = *(struct _NET_BUFFER **)(v3 + 8);
  WanPacket = NdisWanAllocateWanPacket(v1);
  v7 = WanPacket;
  if ( WanPacket )
  {
    WanPacket[6] = a1;
    *(_DWORD *)(a1 + 28) |= 2u;
    if ( *(_DWORD *)(v1 + 208) == ++*(_DWORD *)(v1 + 212) )
    {
      *(_BYTE *)(v1 + 201) = 0;
      --v4[39];
    }
    DataLength = v5->DataLength;
    v8 = (KSPIN_LOCK *)(v4 + 442);
    ++*(_DWORD *)(v1 + 588);
    v11 = (KSPIN_LOCK *)(v4 + 442);
    ++v4[405];
    v12 = DataLength + ((unsigned __int64)*(unsigned int *)(v1 + 696) << 32) + *(unsigned int *)(v1 + 580);
    *(_DWORD *)(v1 + 580) += DataLength;
    *(_DWORD *)(v1 + 696) = HIDWORD(v12);
    v13 = DataLength + ((unsigned __int64)(unsigned int)v4[432] << 32) + (unsigned int)v4[403];
    v4[403] += DataLength;
    v4[432] = HIDWORD(v13);
    v10 = (KIRQL *)(v4 + 444);
    KeReleaseSpinLock(v11, *v10);
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 736));
    v15 = *(_DWORD *)(v1 + 20) == 2;
    v16 = (KSPIN_LOCK *)(v1 + 736);
    *(_BYTE *)(v1 + 744) = v14;
    if ( v15 )
    {
      KeReleaseSpinLock(v16, v14);
      if ( gbSniffLink && qword_14001E2D8 )
        IndicatePromiscuousSendNBL(v1, v3);
      DataBuffer = NdisGetDataBuffer(v5, DataLength, 0, 1u, 0);
      memmove((void *)v7[2], DataBuffer, DataLength);
      *((_DWORD *)v7 + 6) = DataLength;
      v18 = KfRaiseIrql(2u);
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(*(_QWORD *)(*(_QWORD *)(v1 + 72) + 56LL) + 96LL))(
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 72) + 56LL) + 8LL),
              *(_QWORD *)(v1 + 56),
              v7);
      KeLowerIrql(v18);
    }
    else
    {
      v19 = 0;
      KeReleaseSpinLock(v16, v14);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_714410adb39534c9cec6a41078899c0f_Traceguids, v19);
    }
    if ( v19 != 259 )
      ProtoWanSendCompleteLegacy(0, (struct _SLIST_ENTRY *)v7, 0);
  }
  else
  {
    v8 = (KSPIN_LOCK *)(v4 + 442);
    LODWORD(DataLength) = -1;
    v10 = (KIRQL *)(v4 + 444);
    KeReleaseSpinLock(v8, *v10);
    *(_BYTE *)(v1 + 744) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 736));
    CompleteSendDesc(a1, -1073741670);
  }
  *v10 = KeAcquireSpinLockRaiseToDpc(v8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_714410adb39534c9cec6a41078899c0f_Traceguids);
  }
  return (unsigned int)DataLength;
}

```

## disassembly

```asm
0x140010150  push    rbx
0x140010152  push    rbp
0x140010153  push    rsi
0x140010154  push    rdi
0x140010155  push    r12
0x140010157  push    r13
0x140010159  push    r14
0x14001015b  push    r15
0x14001015d  sub     rsp, 38h
0x140010161  mov     rdi, [rcx+28h]
0x140010165  mov     rbx, rcx
0x140010168  mov     r13, [rcx+50h]
0x14001016c  mov     rsi, [rdi+50h]
0x140010170  mov     rcx, cs:WPP_GLOBAL_Control
0x140010177  lea     rax, WPP_GLOBAL_Control
0x14001017e  cmp     rcx, rax
0x140010181  jz      short loc_1400101AD
0x140010183  mov     eax, [rcx+2Ch]
0x140010186  test    al, 8
0x140010188  jz      short loc_1400101AD
0x14001018a  cmp     byte ptr [rcx+29h], 5
0x14001018e  jb      short loc_1400101AD
0x140010190  mov     rcx, [rcx+18h]
0x140010194  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14001019b  mov     edx, 2Fh ; '/'
0x1400101a0  mov     qword ptr [rsp+78h+AlignOffset], r13
0x1400101a5  mov     r9, rdi
0x1400101a8  call    WPP_SF_qq
0x1400101ad  mov     r12, [r13+8]
0x1400101b1  mov     rcx, rdi
0x1400101b4  call    NdisWanAllocateWanPacket
0x1400101b9  mov     r15, rax
0x1400101bc  test    rax, rax
0x1400101bf  jnz     short loc_140010216
0x1400101c1  lea     rbp, [rsi+6E8h]
0x1400101c8  or      r14d, 0FFFFFFFFh
0x1400101cc  add     rsi, 6F0h
0x1400101d3  mov     rcx, rbp; SpinLock
0x1400101d6  mov     dl, [rsi]; NewIrql
0x1400101d8  call    cs:__imp_KeReleaseSpinLock
0x1400101df  nop     dword ptr [rax+rax+00h]
0x1400101e4  lea     rcx, [rdi+2E0h]; SpinLock
0x1400101eb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400101f2  nop     dword ptr [rax+rax+00h]
0x1400101f7  mov     edx, 0C000009Ah
0x1400101fc  mov     rcx, rbx
0x1400101ff  mov     [rdi+2E8h], al
0x140010205  call    CompleteSendDesc
0x14001020a  lea     rbx, WPP_GLOBAL_Control
0x140010211  jmp     loc_1400103E0
0x140010216  mov     [rax+30h], rbx
0x14001021a  or      dword ptr [rbx+1Ch], 2
0x14001021e  inc     dword ptr [rdi+0D4h]
0x140010224  mov     eax, [rdi+0D4h]
0x14001022a  cmp     [rdi+0D0h], eax
0x140010230  jnz     short loc_140010244
0x140010232  or      r14d, 0FFFFFFFFh
0x140010236  mov     byte ptr [rdi+0C9h], 0
0x14001023d  add     [rsi+9Ch], r14d
0x140010244  mov     r14d, [r12+18h]
0x140010249  lea     rbp, [rsi+6E8h]
0x140010250  inc     dword ptr [rdi+24Ch]
0x140010256  mov     rcx, rbp; SpinLock
0x140010259  inc     dword ptr [rsi+654h]
0x14001025f  mov     eax, [rdi+2B8h]
0x140010265  mov     edx, [rdi+244h]
0x14001026b  shl     rax, 20h
0x14001026f  add     rax, r14
0x140010272  add     rdx, rax
0x140010275  mov     [rdi+244h], edx
0x14001027b  shr     rdx, 20h
0x14001027f  mov     [rdi+2B8h], edx
0x140010285  mov     eax, [rsi+6C0h]
0x14001028b  mov     edx, [rsi+64Ch]
0x140010291  shl     rax, 20h
0x140010295  add     rax, r14
0x140010298  add     rdx, rax
0x14001029b  mov     [rsi+64Ch], edx
0x1400102a1  shr     rdx, 20h
0x1400102a5  mov     [rsi+6C0h], edx
0x1400102ab  add     rsi, 6F0h
0x1400102b2  mov     dl, [rsi]; NewIrql
0x1400102b4  call    cs:__imp_KeReleaseSpinLock
0x1400102bb  nop     dword ptr [rax+rax+00h]
0x1400102c0  lea     rbx, [rdi+2E0h]
0x1400102c7  mov     rcx, rbx; SpinLock
0x1400102ca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400102d1  nop     dword ptr [rax+rax+00h]
0x1400102d6  cmp     dword ptr [rdi+14h], 2
0x1400102da  mov     rcx, rbx; SpinLock
0x1400102dd  mov     [rdi+2E8h], al
0x1400102e3  mov     dl, al; NewIrql
0x1400102e5  jnz     loc_140010385
0x1400102eb  call    cs:__imp_KeReleaseSpinLock
0x1400102f2  nop     dword ptr [rax+rax+00h]
0x1400102f7  xor     ebx, ebx
0x1400102f9  cmp     cs:gbSniffLink, bl
0x1400102ff  jz      short loc_140010315
0x140010301  cmp     cs:qword_14001E2D8, rbx
0x140010308  jz      short loc_140010315
0x14001030a  mov     rdx, r13
0x14001030d  mov     rcx, rdi
0x140010310  call    IndicatePromiscuousSendNBL
0x140010315  mov     r9d, 1; AlignMultiple
0x14001031b  mov     [rsp+78h+AlignOffset], ebx; AlignOffset
0x14001031f  xor     r8d, r8d; Storage
0x140010322  mov     edx, r14d; BytesNeeded
0x140010325  mov     rcx, r12; NetBuffer
0x140010328  call    cs:__imp_NdisGetDataBuffer
0x14001032f  nop     dword ptr [rax+rax+00h]
0x140010334  mov     rcx, [r15+10h]; void *
0x140010338  mov     r8, r14; Size
0x14001033b  mov     rdx, rax; Src
0x14001033e  call    memmove
0x140010343  mov     cl, 2; NewIrql
0x140010345  mov     [r15+18h], r14d
0x140010349  call    cs:__imp_KfRaiseIrql
0x140010350  nop     dword ptr [rax+rax+00h]
0x140010355  mov     rcx, [rdi+48h]
0x140010359  mov     r8, r15
0x14001035c  mov     rdx, [rdi+38h]
0x140010360  mov     bl, al
0x140010362  mov     rcx, [rcx+38h]
0x140010366  mov     rax, [rcx+60h]
0x14001036a  mov     rcx, [rcx+8]
0x14001036e  call    _guard_dispatch_icall
0x140010373  mov     cl, bl; NewIrql
0x140010375  mov     edi, eax
0x140010377  call    cs:__imp_KeLowerIrql
0x14001037e  nop     dword ptr [rax+rax+00h]
0x140010383  jmp     short loc_140010393
0x140010385  xor     edi, edi
0x140010387  call    cs:__imp_KeReleaseSpinLock
0x14001038e  nop     dword ptr [rax+rax+00h]
0x140010393  mov     rcx, cs:WPP_GLOBAL_Control
0x14001039a  lea     rbx, WPP_GLOBAL_Control
0x1400103a1  cmp     rcx, rbx
0x1400103a4  jz      short loc_1400103CB
0x1400103a6  mov     eax, [rcx+2Ch]
0x1400103a9  test    al, 8
0x1400103ab  jz      short loc_1400103CB
0x1400103ad  cmp     byte ptr [rcx+29h], 5
0x1400103b1  jb      short loc_1400103CB
0x1400103b3  mov     rcx, [rcx+18h]
0x1400103b7  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x1400103be  mov     edx, 30h ; '0'
0x1400103c3  mov     r9d, edi
0x1400103c6  call    WPP_SF_d
0x1400103cb  cmp     edi, 103h
0x1400103d1  jz      short loc_1400103E0
0x1400103d3  xor     r8d, r8d
0x1400103d6  mov     rdx, r15
0x1400103d9  xor     ecx, ecx
0x1400103db  call    ProtoWanSendCompleteLegacy
0x1400103e0  mov     rcx, rbp; SpinLock
0x1400103e3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400103ea  nop     dword ptr [rax+rax+00h]
0x1400103ef  mov     [rsi], al
0x1400103f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103f8  cmp     rcx, rbx
0x1400103fb  jz      short loc_140010420
0x1400103fd  mov     edx, [rcx+2Ch]
0x140010400  test    dl, 8
0x140010403  jz      short loc_140010420
0x140010405  cmp     byte ptr [rcx+29h], 5
0x140010409  jb      short loc_140010420
0x14001040b  mov     rcx, [rcx+18h]
0x14001040f  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x140010416  mov     edx, 31h ; '1'
0x14001041b  call    WPP_SF_
0x140010420  mov     eax, r14d
0x140010423  add     rsp, 38h
0x140010427  pop     r15
0x140010429  pop     r14
0x14001042b  pop     r13
0x14001042d  pop     r12
0x14001042f  pop     rdi
0x140010430  pop     rsi
0x140010431  pop     rbp
0x140010432  pop     rbx
0x140010433  retn
```
