# MpCoSendNetBufferListChain

- ea: `0x140010130`
- end: `0x14001029c`
- name: `MpCoSendNetBufferListChain`
- size: `364`
- prototype: `__int64 __fastcall(__int64, PNET_BUFFER_LIST OriginalNetBufferList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000110c`
- `0x140006b80`
- `0x140010130`
- `0x14001169c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400101a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010212`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400101a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010212`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001018e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001018e`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400101f1`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400101f1`

## pseudocode

```c
void __fastcall MpCoSendNetBufferListChain(__int64 a1, PNET_BUFFER_LIST OriginalNetBufferList)
{
  int v4; // ecx
  KIRQL v5; // al
  bool v6; // zf
  KSPIN_LOCK *v7; // rcx
  PNET_BUFFER_LIST i; // rax
  volatile signed __int32 *v9; // rsi
  struct _NET_BUFFER_LIST *Alignment; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 64LL) == 2 )
  {
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
    v6 = *(_DWORD *)(a1 + 72) == 8;
    v7 = (KSPIN_LOCK *)(a1 + 56);
    *(_BYTE *)(a1 + 64) = v5;
    if ( v6 )
    {
      KeReleaseSpinLock(v7, v5);
      v9 = (volatile signed __int32 *)(a1 + 40);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
      if ( OriginalNetBufferList )
      {
        do
        {
          Alignment = (struct _NET_BUFFER_LIST *)OriginalNetBufferList->Link.Alignment;
          OriginalNetBufferList->Link.Alignment = 0;
          _InterlockedIncrement(v9);
          MpSendPacketOnCall(a1, OriginalNetBufferList);
          OriginalNetBufferList = Alignment;
        }
        while ( Alignment );
      }
      if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFF) == 1 )
        goto LABEL_17;
      goto LABEL_18;
    }
    KeReleaseSpinLock(v7, v5);
    v4 = -1073741823;
  }
  else
  {
    v4 = -1071448022;
  }
  if ( *(_QWORD *)(a1 + 168) )
  {
    for ( i = OriginalNetBufferList; i; i = (PNET_BUFFER_LIST)i->Link.Alignment )
      i->Status = v4;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
    NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 168), OriginalNetBufferList, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 40), 0xFFFFFFFF) == 1 )
LABEL_17:
      (*(void (__fastcall **)(__int64))(a1 + 48))(a1 + 40);
  }
LABEL_18:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
}

```

## disassembly

```asm
0x140010130  push    rbx
0x140010132  push    rbp
0x140010133  push    rsi
0x140010134  push    rdi
0x140010135  push    r14
0x140010137  sub     rsp, 20h
0x14001013b  mov     r14, rdx
0x14001013e  mov     rdi, rcx
0x140010141  mov     rcx, cs:WPP_GLOBAL_Control
0x140010148  lea     rbp, WPP_GLOBAL_Control
0x14001014f  cmp     rcx, rbp
0x140010152  jz      short loc_140010176
0x140010154  mov     eax, [rcx+2Ch]
0x140010157  test    al, 1
0x140010159  jz      short loc_140010176
0x14001015b  cmp     byte ptr [rcx+29h], 2
0x14001015f  jb      short loc_140010176
0x140010161  mov     rcx, [rcx+18h]
0x140010165  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x14001016c  mov     edx, 4Dh ; 'M'
0x140010171  call    WPP_SF_
0x140010176  mov     rax, [rdi+60h]
0x14001017a  cmp     dword ptr [rax+40h], 2
0x14001017e  jz      short loc_140010187
0x140010180  mov     ecx, 0C023002Ah
0x140010185  jmp     short loc_1400101B9
0x140010187  lea     rbx, [rdi+38h]
0x14001018b  mov     rcx, rbx; SpinLock
0x14001018e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010195  nop     dword ptr [rax+rax+00h]
0x14001019a  cmp     dword ptr [rdi+48h], 8
0x14001019e  mov     rcx, rbx; SpinLock
0x1400101a1  mov     [rdi+40h], al
0x1400101a4  mov     dl, al; NewIrql
0x1400101a6  jz      short loc_140010212
0x1400101a8  call    cs:__imp_KeReleaseSpinLock
0x1400101af  nop     dword ptr [rax+rax+00h]
0x1400101b4  mov     ecx, 0C0000001h
0x1400101b9  cmp     qword ptr [rdi+0A8h], 0
0x1400101c1  jz      loc_140010262
0x1400101c7  mov     rax, r14
0x1400101ca  test    r14, r14
0x1400101cd  jz      short loc_1400101DD
0x1400101cf  mov     [rax+8Ch], ecx
0x1400101d5  mov     rax, [rax]
0x1400101d8  test    rax, rax
0x1400101db  jnz     short loc_1400101CF
0x1400101dd  lea     rbx, [rdi+28h]
0x1400101e1  lock inc dword ptr [rbx]
0x1400101e4  mov     rcx, [rdi+0A8h]; NdisVcHandle
0x1400101eb  xor     r8d, r8d; SendCompleteFlags
0x1400101ee  mov     rdx, r14; NetBufferLists
0x1400101f1  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x1400101f8  nop     dword ptr [rax+rax+00h]
0x1400101fd  or      eax, 0FFFFFFFFh
0x140010200  lock xadd [rbx], eax
0x140010204  cmp     eax, 1
0x140010207  jnz     short loc_140010262
0x140010209  mov     rax, [rbx+8]
0x14001020d  mov     rcx, rbx
0x140010210  jmp     short loc_14001025D
0x140010212  call    cs:__imp_KeReleaseSpinLock
0x140010219  nop     dword ptr [rax+rax+00h]
0x14001021e  lea     rsi, [rdi+28h]
0x140010222  lock inc dword ptr [rsi]
0x140010225  test    r14, r14
0x140010228  jz      short loc_14001024A
0x14001022a  mov     rbx, [r14]
0x14001022d  mov     qword ptr [r14], 0
0x140010234  lock inc dword ptr [rsi]
0x140010237  mov     rdx, r14; OriginalNetBufferList
0x14001023a  mov     rcx, rdi; __int64
0x14001023d  call    MpSendPacketOnCall
0x140010242  mov     r14, rbx
0x140010245  test    rbx, rbx
0x140010248  jnz     short loc_14001022A
0x14001024a  or      eax, 0FFFFFFFFh
0x14001024d  lock xadd [rsi], eax
0x140010251  cmp     eax, 1
0x140010254  jnz     short loc_140010262
0x140010256  mov     rax, [rsi+8]
0x14001025a  mov     rcx, rsi
0x14001025d  call    _guard_dispatch_icall
0x140010262  mov     rcx, cs:WPP_GLOBAL_Control
0x140010269  cmp     rcx, rbp
0x14001026c  jz      short loc_140010290
0x14001026e  mov     eax, [rcx+2Ch]
0x140010271  test    al, 1
0x140010273  jz      short loc_140010290
0x140010275  cmp     byte ptr [rcx+29h], 2
0x140010279  jb      short loc_140010290
0x14001027b  mov     rcx, [rcx+18h]
0x14001027f  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x140010286  mov     edx, 4Eh ; 'N'
0x14001028b  call    WPP_SF_
0x140010290  add     rsp, 20h
0x140010294  pop     r14
0x140010296  pop     rdi
0x140010297  pop     rsi
0x140010298  pop     rbp
0x140010299  pop     rbx
0x14001029a  retn
```
