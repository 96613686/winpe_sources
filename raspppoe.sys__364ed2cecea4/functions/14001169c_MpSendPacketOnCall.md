# MpSendPacketOnCall

- ea: `0x14001169c`
- end: `0x1400119e3`
- name: `MpSendPacketOnCall`
- size: `839`
- prototype: `__int64 __fastcall(__int64, PNET_BUFFER_LIST OriginalNetBufferList)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010130`

## callees

- `0x14000110c`
- `0x1400024dc`
- `0x140002794`
- `0x1400028cc`
- `0x140005098`
- `0x140006b80`
- `0x14001169c`
- `0x140013510`
- `0x140015bb0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140011751`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011763`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001183f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011851`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400118bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400118ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001192a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011751`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011763`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400117ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001183f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011851`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400118bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400118ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001192a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011702`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011733`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011702`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011733`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400119a6`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400119a6`

## pseudocode

```c
void __fastcall MpSendPacketOnCall(__int64 a1, PNET_BUFFER_LIST OriginalNetBufferList)
{
  NDIS_STATUS v4; // ebx
  __int64 v5; // rsi
  __int64 v6; // rdx
  KIRQL v7; // al
  bool v8; // zf
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rbx
  UCHAR *v13; // r15
  UCHAR *v14; // [rsp+80h] [rbp+8h] BYREF

  v14 = 0;
  v4 = -1073741823;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  v5 = *(_QWORD *)(a1 + 96);
  LOBYTE(v6) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 8));
  *(_BYTE *)(v5 + 16) = v6;
  if ( (*(_DWORD *)(v5 + 84) & 3) == 1 )
  {
    ReferenceTapiProv(v5, v6);
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
    v8 = *(_QWORD *)(a1 + 728) == 0;
    *(_BYTE *)(a1 + 64) = v7;
    if ( v8 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v7);
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 8), *(_BYTE *)(v5 + 16));
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v10 = 81;
LABEL_11:
        WPP_SF_q(v9->AttachedDevice, v10, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids, a1);
      }
    }
    else if ( *(_DWORD *)(a1 + 72) == 8 )
    {
      v4 = PacketInitializePAYLOADToSendEx(
             &v14,
             a1 + 715,
             (int *)(a1 + 709),
             *(_WORD *)(a1 + 722),
             OriginalNetBufferList,
             (void *)a1);
      if ( v4 )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
        KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 8), *(_BYTE *)(v5 + 16));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
        }
      }
      else
      {
        v12 = *(_QWORD *)(a1 + 728);
        LOBYTE(v11) = 1;
        ReferenceBinding(v12, v11);
        v13 = v14;
        _InterlockedIncrement((volatile signed __int32 *)v14);
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
        KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 8), *(_BYTE *)(v5 + 16));
        PrSend(v12, v13);
        v4 = 259;
        _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.DeviceExtension);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1 )
          (*((void (__fastcall **)(UCHAR *))v13 + 1))(v13);
      }
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v7);
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 8), *(_BYTE *)(v5 + 16));
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v10 = 82;
        goto LABEL_11;
      }
    }
    DereferenceTapiProv(v5);
    if ( v4 == 259 )
      return;
    goto LABEL_30;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 8), v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
LABEL_30:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
    }
  }
  OriginalNetBufferList->Status = v4;
  NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 168), OriginalNetBufferList, 0);
  _InterlockedIncrement((_DWORD *)&WPP_MAIN_CB.DeviceExtension + 1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 40), 0xFFFFFFFF) == 1 )
    (*(void (**)(void))(a1 + 48))();
}

```

## disassembly

```asm
0x14001169c  mov     rax, rsp
0x14001169f  push    rbx
0x1400116a0  push    rbp
0x1400116a1  push    rsi
0x1400116a2  push    rdi
0x1400116a3  push    r12
0x1400116a5  push    r13
0x1400116a7  push    r14
0x1400116a9  push    r15
0x1400116ab  sub     rsp, 38h
0x1400116af  mov     r13, rdx
0x1400116b2  mov     qword ptr [rax+8], 0
0x1400116ba  mov     rdi, rcx
0x1400116bd  mov     ebx, 0C0000001h
0x1400116c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116c9  lea     r15, WPP_GLOBAL_Control
0x1400116d0  cmp     rcx, r15
0x1400116d3  jz      short loc_1400116F7
0x1400116d5  mov     eax, [rcx+2Ch]
0x1400116d8  test    al, 1
0x1400116da  jz      short loc_1400116F7
0x1400116dc  cmp     byte ptr [rcx+29h], 2
0x1400116e0  jb      short loc_1400116F7
0x1400116e2  mov     rcx, [rcx+18h]
0x1400116e6  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x1400116ed  mov     edx, 4Fh ; 'O'
0x1400116f2  call    WPP_SF_
0x1400116f7  mov     rsi, [rdi+60h]
0x1400116fb  lea     rbp, [rsi+8]
0x1400116ff  mov     rcx, rbp; SpinLock
0x140011702  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011709  nop     dword ptr [rax+rax+00h]
0x14001170e  mov     dl, al; NewIrql
0x140011710  mov     [rsi+10h], al
0x140011713  mov     eax, [rsi+54h]
0x140011716  or      r12d, 0FFFFFFFFh
0x14001171a  and     al, 3
0x14001171c  cmp     al, 1
0x14001171e  jnz     loc_140011927
0x140011724  mov     rcx, rsi
0x140011727  call    ReferenceTapiProv
0x14001172c  lea     r14, [rdi+38h]
0x140011730  mov     rcx, r14; SpinLock
0x140011733  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001173a  nop     dword ptr [rax+rax+00h]
0x14001173f  cmp     qword ptr [rdi+2D8h], 0
0x140011747  mov     [rdi+40h], al
0x14001174a  jnz     short loc_1400117B1
0x14001174c  mov     dl, al; NewIrql
0x14001174e  mov     rcx, r14; SpinLock
0x140011751  call    cs:__imp_KeReleaseSpinLock
0x140011758  nop     dword ptr [rax+rax+00h]
0x14001175d  mov     dl, [rsi+10h]; NewIrql
0x140011760  mov     rcx, rbp; SpinLock
0x140011763  call    cs:__imp_KeReleaseSpinLock
0x14001176a  nop     dword ptr [rax+rax+00h]
0x14001176f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011776  cmp     rcx, r15
0x140011779  jz      loc_140011911
0x14001177f  mov     eax, [rcx+2Ch]
0x140011782  test    al, 2
0x140011784  jz      loc_140011911
0x14001178a  cmp     byte ptr [rcx+29h], 1
0x14001178e  jb      loc_140011911
0x140011794  lea     edx, [r12+52h]
0x140011799  mov     rcx, [rcx+18h]
0x14001179d  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x1400117a4  mov     r9, rdi
0x1400117a7  call    WPP_SF_q
0x1400117ac  jmp     loc_140011911
0x1400117b1  cmp     dword ptr [rdi+48h], 8
0x1400117b5  jz      short loc_140011806
0x1400117b7  mov     dl, al; NewIrql
0x1400117b9  mov     rcx, r14; SpinLock
0x1400117bc  call    cs:__imp_KeReleaseSpinLock
0x1400117c3  nop     dword ptr [rax+rax+00h]
0x1400117c8  mov     dl, [rsi+10h]; NewIrql
0x1400117cb  mov     rcx, rbp; SpinLock
0x1400117ce  call    cs:__imp_KeReleaseSpinLock
0x1400117d5  nop     dword ptr [rax+rax+00h]
0x1400117da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400117e1  cmp     rcx, r15
0x1400117e4  jz      loc_140011911
0x1400117ea  mov     eax, [rcx+2Ch]
0x1400117ed  test    al, 2
0x1400117ef  jz      loc_140011911
0x1400117f5  cmp     byte ptr [rcx+29h], 1
0x1400117f9  jb      loc_140011911
0x1400117ff  mov     edx, 52h ; 'R'
0x140011804  jmp     short loc_140011799
0x140011806  movzx   r9d, word ptr [rdi+2D2h]; int
0x14001180e  lea     r8, [rdi+2C5h]; int
0x140011815  lea     rdx, [rdi+2CBh]; int
0x14001181c  mov     [rsp+78h+var_50], rdi; __int64
0x140011821  lea     rcx, [rsp+78h+arg_0]; int
0x140011829  mov     [rsp+78h+OriginalNetBufferList], r13; OriginalNetBufferList
0x14001182e  call    PacketInitializePAYLOADToSendEx
0x140011833  mov     ebx, eax
0x140011835  test    eax, eax
0x140011837  jz      short loc_140011899
0x140011839  mov     dl, [rdi+40h]; NewIrql
0x14001183c  mov     rcx, r14; SpinLock
0x14001183f  call    cs:__imp_KeReleaseSpinLock
0x140011846  nop     dword ptr [rax+rax+00h]
0x14001184b  mov     dl, [rsi+10h]; NewIrql
0x14001184e  mov     rcx, rbp; SpinLock
0x140011851  call    cs:__imp_KeReleaseSpinLock
0x140011858  nop     dword ptr [rax+rax+00h]
0x14001185d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011864  cmp     rcx, r15
0x140011867  jz      loc_140011911
0x14001186d  mov     eax, [rcx+2Ch]
0x140011870  test    al, 2
0x140011872  jz      loc_140011911
0x140011878  cmp     byte ptr [rcx+29h], 1
0x14001187c  jb      loc_140011911
0x140011882  mov     rcx, [rcx+18h]
0x140011886  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x14001188d  mov     edx, 53h ; 'S'
0x140011892  call    WPP_SF_
0x140011897  jmp     short loc_140011911
0x140011899  mov     rbx, [rdi+2D8h]
0x1400118a0  mov     dl, 1
0x1400118a2  mov     rcx, rbx
0x1400118a5  call    ReferenceBinding
0x1400118aa  mov     r15, [rsp+78h+arg_0]
0x1400118b2  lock inc dword ptr [r15]
0x1400118b6  mov     dl, [rdi+40h]; NewIrql
0x1400118b9  mov     rcx, r14; SpinLock
0x1400118bc  call    cs:__imp_KeReleaseSpinLock
0x1400118c3  nop     dword ptr [rax+rax+00h]
0x1400118c8  mov     dl, [rsi+10h]; NewIrql
0x1400118cb  mov     rcx, rbp; SpinLock
0x1400118ce  call    cs:__imp_KeReleaseSpinLock
0x1400118d5  nop     dword ptr [rax+rax+00h]
0x1400118da  mov     rdx, r15
0x1400118dd  mov     rcx, rbx
0x1400118e0  call    PrSend
0x1400118e5  mov     ebx, 103h
0x1400118ea  lock inc dword ptr cs:WPP_MAIN_CB.DeviceExtension
0x1400118f1  mov     eax, r12d
0x1400118f4  lock xadd [r15], eax
0x1400118f9  cmp     eax, 1
0x1400118fc  jnz     short loc_14001190A
0x1400118fe  mov     rax, [r15+8]
0x140011902  mov     rcx, r15
0x140011905  call    _guard_dispatch_icall
0x14001190a  lea     r15, WPP_GLOBAL_Control
0x140011911  mov     rcx, rsi
0x140011914  call    DereferenceTapiProv
0x140011919  cmp     ebx, 103h
0x14001191f  jz      loc_1400119D1
0x140011925  jmp     short loc_140011964
0x140011927  mov     rcx, rbp; SpinLock
0x14001192a  call    cs:__imp_KeReleaseSpinLock
0x140011931  nop     dword ptr [rax+rax+00h]
0x140011936  mov     rcx, cs:WPP_GLOBAL_Control
0x14001193d  cmp     rcx, r15
0x140011940  jz      short loc_140011992
0x140011942  mov     eax, [rcx+2Ch]
0x140011945  test    al, 2
0x140011947  jz      short loc_140011964
0x140011949  cmp     byte ptr [rcx+29h], 1
0x14001194d  jb      short loc_140011964
0x14001194f  mov     rcx, [rcx+18h]
0x140011953  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x14001195a  mov     edx, 50h ; 'P'
0x14001195f  call    WPP_SF_
0x140011964  mov     rcx, cs:WPP_GLOBAL_Control
0x14001196b  cmp     rcx, r15
0x14001196e  jz      short loc_140011992
0x140011970  mov     eax, [rcx+2Ch]
0x140011973  test    al, 2
0x140011975  jz      short loc_140011992
0x140011977  cmp     byte ptr [rcx+29h], 1
0x14001197b  jb      short loc_140011992
0x14001197d  mov     rcx, [rcx+18h]
0x140011981  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x140011988  mov     edx, 54h ; 'T'
0x14001198d  call    WPP_SF_
0x140011992  mov     [r13+8Ch], ebx
0x140011999  xor     r8d, r8d; SendCompleteFlags
0x14001199c  mov     rcx, [rdi+0A8h]; NdisVcHandle
0x1400119a3  mov     rdx, r13; NetBufferLists
0x1400119a6  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x1400119ad  nop     dword ptr [rax+rax+00h]
0x1400119b2  lock inc dword ptr cs:WPP_MAIN_CB.DeviceExtension+4
0x1400119b9  lea     rcx, [rdi+28h]
0x1400119bd  lock xadd [rcx], r12d
0x1400119c2  cmp     r12d, 1
0x1400119c6  jnz     short loc_1400119D1
0x1400119c8  mov     rax, [rcx+8]
0x1400119cc  call    _guard_dispatch_icall
0x1400119d1  add     rsp, 38h
0x1400119d5  pop     r15
0x1400119d7  pop     r14
0x1400119d9  pop     r13
0x1400119db  pop     r12
0x1400119dd  pop     rdi
0x1400119de  pop     rsi
0x1400119df  pop     rbp
0x1400119e0  pop     rbx
0x1400119e1  retn
```
