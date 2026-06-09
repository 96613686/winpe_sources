# CompleteSendDesc

- ea: `0x140030940`
- end: `0x140030e5f`
- name: `CompleteSendDesc`
- size: `1311`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140002e40`
- `0x140007a00`
- `0x140010150`
- `0x1400305b0`
- `0x140030940`

## callees

- `0x140005494`
- `0x14000a2c0`
- `0x14000a744`
- `0x14000ed38`
- `0x140016230`
- `0x14002e898`
- `0x140030940`
- `0x140030e70`
- `0x140032300`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140030e4e`
- `ntoskrnl!KeSetEvent` at `0x140030e4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400309b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030a76`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030bc1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030bf2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030c2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030c88`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400309b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030a76`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030bc1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030bf2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030c2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030c88`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030a3e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030b4a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030bd0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030caf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030e20`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030a3e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030b4a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030bd0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030caf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030e20`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140030da0`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140030da0`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140030a97`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140030a97`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140030ad3`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140030ad3`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140030b2d`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140030b2d`
- `NDIS!NdisFreeNetBufferListContext` at `0x140030af2`
- `NDIS!NdisFreeNetBufferListContext` at `0x140030af2`
- `NDIS!NdisFreeNetBufferList` at `0x140030d83`
- `NDIS!NdisFreeNetBufferList` at `0x140030d83`

## pseudocode

```c
void __fastcall CompleteSendDesc(__int64 a1, NDIS_STATUS a2)
{
  unsigned int v2; // r13d
  __int64 v3; // rsi
  __int64 v5; // r14
  __int64 v6; // r15
  int v7; // ebp
  __int64 v8; // rdi
  __int64 v9; // r12
  struct _NET_BUFFER_LIST *v10; // rbx
  __int64 v11; // r13
  char *v12; // r15
  ULONG v13; // edx
  int v14; // eax
  KIRQL v15; // al
  bool v16; // zf
  __int64 v17; // rbx
  __int64 v18; // [rsp+30h] [rbp-58h]
  __int16 v19; // [rsp+90h] [rbp+8h]
  int v21; // [rsp+A0h] [rbp+18h]
  __int64 v22; // [rsp+A8h] [rbp+20h]

  v2 = a2;
  v3 = *(_QWORD *)(a1 + 40);
  v5 = *(_QWORD *)(a1 + 48);
  v6 = *(_QWORD *)(a1 + 112);
  v7 = *(_DWORD *)(a1 + 28);
  v21 = *(_DWORD *)(a1 + 32);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids, a1, v6, a2);
  }
  if ( (v7 & 4) != 0 )
  {
    v8 = *(_QWORD *)(a1 + 56);
  }
  else
  {
    --*(_DWORD *)(v3 + 28);
    v8 = *(_QWORD *)(v3 + 80);
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 736), *(_BYTE *)(v3 + 744));
  }
  if ( v6 )
  {
    v9 = *(unsigned __int16 *)(*(_QWORD *)(v6 + 16) + 10LL) + *(_QWORD *)(v6 + 16) + 16LL;
    NdisWanFreeSendDesc(a1, &WPP_GLOBAL_Control);
  }
  else
  {
    v9 = 0;
    v10 = *(struct _NET_BUFFER_LIST **)(a1 + 80);
    v11 = *(_QWORD *)(v5 + 64);
    v18 = *(_QWORD *)(v5 + 56);
    v12 = (char *)v10->Context + v10->Context->Offset;
    v22 = *((_QWORD *)v12 + 11);
    v19 = *(_WORD *)(v5 + 214);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids, v5, v10);
    }
    _InterlockedDecrement((volatile signed __int32 *)(v5 + 104));
    if ( *(_WORD *)(v5 + 212) == 0xAB00 )
    {
      NdisFreeNetBufferList(v10);
      v2 = a2;
    }
    else
    {
      *(_BYTE *)(v11 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 1768));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 24), 0xFFFFFFFF) == 1 )
        (*(void (**)(void))(v5 + 32))();
      KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 1768), *(_BYTE *)(v11 + 1776));
      if ( (*((_DWORD *)v12 + 11) & 0x20) != 0 )
        NdisAdvanceNetBufferListDataStart(v10, *((_DWORD *)v12 + 30), 0, 0);
      if ( (*((_DWORD *)v12 + 11) & 0x10) != 0 )
      {
        v13 = 12;
        if ( v19 != 171 )
          v13 = 14;
        NdisRetreatNetBufferListDataStart(v10, v13, 0, 0, 0);
      }
      v10->SourceHandle = (NDIS_HANDLE)*((_QWORD *)v12 + 17);
      NdisFreeNetBufferListContext(v10, 0x80u);
      v2 = a2;
      v10->Status = a2;
      if ( v22 )
      {
        NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(v22 + 40), v10, 0);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 24), 0xFFFFFFFF) == 1 )
          DoDerefCmVcCBWork(v22);
      }
      else
      {
        NdisMSendNetBufferListsComplete(*(NDIS_HANDLE *)(v18 + 40), v10, 0);
      }
      _InterlockedIncrement(&glSendCompleteCount);
    }
  }
  *(_BYTE *)(v8 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 1768));
  if ( (v7 & 2) != 0 )
  {
    if ( *(_DWORD *)(v3 + 212) == *(_DWORD *)(v3 + 208) )
    {
      v16 = *(_BYTE *)(v3 + 200) == 0;
      *(_BYTE *)(v3 + 201) = 1;
      if ( !v16 )
        ++*(_DWORD *)(v8 + 156);
    }
    --*(_DWORD *)(v3 + 212);
  }
  if ( (v7 & 1) != 0 )
    _InterlockedDecrement((volatile signed __int32 *)(48LL * v21 + v5 + 152));
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        67,
        WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids,
        *(unsigned int *)(v9 + 24));
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 24), 0xFFFFFFFF) == 1 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 1768), *(_BYTE *)(v8 + 1776));
      if ( (*(_DWORD *)(v9 + 28) & 4) == 0 )
      {
        v17 = *(_QWORD *)(v9 + 40);
        *(_BYTE *)(v17 + 744) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v17 + 736));
      }
      CompleteSendDesc(v9, v2);
      *(_BYTE *)(v8 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 1768));
    }
  }
  v14 = *(_DWORD *)(v8 + 16);
  if ( (v7 & 8) != 0 )
  {
    --*(_DWORD *)(v8 + 168);
    if ( (v14 & 0x20) != 0 && !*(_DWORD *)(v8 + 168) )
      KeSetEvent((PRKEVENT)(v8 + 176), 1, 0);
    if ( (*(_DWORD *)(v8 + 16) & 0x80000) != 0 )
      KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 1768), *(_BYTE *)(v8 + 1776));
    else
      SendPacketOnBundle((PVOID)v8);
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 1768));
    v16 = (*(_DWORD *)(v8 + 24))-- == 1;
    *(_BYTE *)(v8 + 1776) = v15;
    if ( v16 )
      DoDerefBundleCBWork((PVOID)v8);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 1768), v15);
  }
  else if ( (v14 & 0x80000) != 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 1768), *(_BYTE *)(v8 + 1776));
  }
  else
  {
    SendPacketOnBundle((PVOID)v8);
  }
}

```

## disassembly

```asm
0x140030940  mov     [rsp+arg_8], edx
0x140030944  push    rbx
0x140030945  push    rbp
0x140030946  push    rsi
0x140030947  push    rdi
0x140030948  push    r12
0x14003094a  push    r13
0x14003094c  push    r14
0x14003094e  push    r15
0x140030950  sub     rsp, 48h
0x140030954  mov     eax, [rcx+20h]
0x140030957  mov     r13d, edx
0x14003095a  mov     rsi, [rcx+28h]
0x14003095e  mov     rbx, rcx
0x140030961  mov     r14, [rcx+30h]
0x140030965  mov     r15, [rcx+70h]
0x140030969  mov     ebp, [rcx+1Ch]
0x14003096c  mov     [rsp+88h+arg_10], eax
0x140030973  mov     rcx, cs:WPP_GLOBAL_Control
0x14003097a  lea     rdx, WPP_GLOBAL_Control
0x140030981  cmp     rcx, rdx
0x140030984  jz      short loc_140030991
0x140030986  mov     eax, [rcx+2Ch]
0x140030989  test    al, 8
0x14003098b  jnz     loc_140030D1C
0x140030991  test    bpl, 4
0x140030995  jnz     loc_140030C42
0x14003099b  dec     dword ptr [rsi+1Ch]
0x14003099e  lea     rcx, [rsi+2E0h]; SpinLock
0x1400309a5  movzx   edx, byte ptr [rsi+2E8h]; NewIrql
0x1400309ac  mov     rdi, [rsi+50h]
0x1400309b0  call    cs:__imp_KeReleaseSpinLock
0x1400309b7  nop     dword ptr [rax+rax+00h]
0x1400309bc  lea     rdx, WPP_GLOBAL_Control
0x1400309c3  test    r15, r15
0x1400309c6  jnz     loc_140030CC6
0x1400309cc  mov     rax, [r14+38h]
0x1400309d0  xor     r12d, r12d
0x1400309d3  mov     rbx, [rbx+50h]
0x1400309d7  mov     r13, [r14+40h]
0x1400309db  mov     [rsp+88h+var_58], rax
0x1400309e0  mov     rcx, [rbx+10h]
0x1400309e4  movzx   r15d, word ptr [rcx+0Ah]
0x1400309e9  add     r15, rcx
0x1400309ec  mov     rax, [r15+58h]
0x1400309f0  mov     [rsp+88h+arg_18], rax
0x1400309f8  movzx   eax, word ptr [r14+0D6h]
0x140030a00  mov     [rsp+88h+arg_0], ax
0x140030a08  mov     rcx, cs:WPP_GLOBAL_Control
0x140030a0f  cmp     rcx, rdx
0x140030a12  jz      short loc_140030A1F
0x140030a14  mov     eax, [rcx+2Ch]
0x140030a17  test    al, 8
0x140030a19  jnz     loc_140030D54
0x140030a1f  lock dec dword ptr [r14+68h]
0x140030a24  mov     eax, 0AB00h
0x140030a29  cmp     [r14+0D4h], ax
0x140030a31  jz      loc_140030D80
0x140030a37  lea     rcx, [r13+6E8h]; SpinLock
0x140030a3e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030a45  nop     dword ptr [rax+rax+00h]
0x140030a4a  mov     [r13+6F0h], al
0x140030a51  lea     rcx, [r14+18h]
0x140030a55  mov     eax, 0FFFFFFFFh
0x140030a5a  lock xadd [rcx], eax
0x140030a5e  cmp     eax, 1
0x140030a61  jz      loc_140030D0E
0x140030a67  movzx   edx, byte ptr [r13+6F0h]; NewIrql
0x140030a6f  lea     rcx, [r13+6E8h]; SpinLock
0x140030a76  call    cs:__imp_KeReleaseSpinLock
0x140030a7d  nop     dword ptr [rax+rax+00h]
0x140030a82  mov     eax, [r15+2Ch]
0x140030a86  test    al, 20h
0x140030a88  jz      short loc_140030AA3
0x140030a8a  mov     edx, [r15+78h]; DataOffsetDelta
0x140030a8e  xor     r9d, r9d; FreeMdlMdlHandler
0x140030a91  xor     r8d, r8d; FreeMdl
0x140030a94  mov     rcx, rbx; NetBufferList
0x140030a97  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x140030a9e  nop     dword ptr [rax+rax+00h]
0x140030aa3  mov     eax, [r15+2Ch]
0x140030aa7  test    al, 10h
0x140030aa9  jz      short loc_140030ADF
0x140030aab  mov     ecx, 0ABh
0x140030ab0  mov     [rsp+88h+FreeMdlHandler], r12; FreeMdlHandler
0x140030ab5  cmp     [rsp+88h+arg_0], cx
0x140030abd  mov     edx, 0Ch
0x140030ac2  mov     eax, 0Eh
0x140030ac7  mov     rcx, rbx; NetBufferList
0x140030aca  cmovnz  edx, eax; DataOffsetDelta
0x140030acd  xor     r9d, r9d; AllocateMdlHandler
0x140030ad0  xor     r8d, r8d; DataBackFill
0x140030ad3  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x140030ada  nop     dword ptr [rax+rax+00h]
0x140030adf  mov     rax, [r15+88h]
0x140030ae6  mov     edx, 80h; ContextSize
0x140030aeb  mov     rcx, rbx; NetBufferList
0x140030aee  mov     [rbx+78h], rax
0x140030af2  call    cs:__imp_NdisFreeNetBufferListContext
0x140030af9  nop     dword ptr [rax+rax+00h]
0x140030afe  mov     r15, [rsp+88h+arg_18]
0x140030b06  xor     r8d, r8d; SendCompleteFlags
0x140030b09  mov     r13d, [rsp+88h+arg_8]
0x140030b11  mov     rdx, rbx; NetBufferLists
0x140030b14  mov     [rbx+8Ch], r13d
0x140030b1b  test    r15, r15
0x140030b1e  jnz     loc_140030D9C
0x140030b24  mov     rcx, [rsp+88h+var_58]
0x140030b29  mov     rcx, [rcx+28h]; MiniportAdapterHandle
0x140030b2d  call    cs:__imp_NdisMSendNetBufferListsComplete
0x140030b34  nop     dword ptr [rax+rax+00h]
0x140030b39  lock inc cs:glSendCompleteCount
0x140030b40  lea     r15, [rdi+6E8h]
0x140030b47  mov     rcx, r15; SpinLock
0x140030b4a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030b51  nop     dword ptr [rax+rax+00h]
0x140030b56  mov     [rdi+6F0h], al
0x140030b5c  test    bpl, 2
0x140030b60  jz      short loc_140030B7A
0x140030b62  mov     eax, [rsi+0D0h]
0x140030b68  cmp     [rsi+0D4h], eax
0x140030b6e  jz      loc_140030CE2
0x140030b74  dec     dword ptr [rsi+0D4h]
0x140030b7a  test    bpl, 1
0x140030b7e  jnz     loc_140030DCD
0x140030b84  test    r12, r12
0x140030b87  jnz     loc_140030C4B
0x140030b8d  mov     eax, [rdi+10h]
0x140030b90  test    bpl, 8
0x140030b94  jz      short loc_140030C10
0x140030b96  dec     dword ptr [rdi+0A8h]
0x140030b9c  mov     ecx, [rdi+0A8h]
0x140030ba2  test    al, 20h
0x140030ba4  jnz     loc_140030E37
0x140030baa  test    dword ptr [rdi+10h], 80000h
0x140030bb1  jz      loc_140030C38
0x140030bb7  movzx   edx, byte ptr [rdi+6F0h]; NewIrql
0x140030bbe  mov     rcx, r15; SpinLock
0x140030bc1  call    cs:__imp_KeReleaseSpinLock
0x140030bc8  nop     dword ptr [rax+rax+00h]
0x140030bcd  mov     rcx, r15; SpinLock
0x140030bd0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030bd7  nop     dword ptr [rax+rax+00h]
0x140030bdc  add     dword ptr [rdi+18h], 0FFFFFFFFh
0x140030be0  mov     [rdi+6F0h], al
0x140030be6  jz      loc_140030D01
0x140030bec  movzx   edx, al; NewIrql
0x140030bef  mov     rcx, r15; SpinLock
0x140030bf2  call    cs:__imp_KeReleaseSpinLock
0x140030bf9  nop     dword ptr [rax+rax+00h]
0x140030bfe  add     rsp, 48h
0x140030c02  pop     r15
0x140030c04  pop     r14
0x140030c06  pop     r13
0x140030c08  pop     r12
0x140030c0a  pop     rdi
0x140030c0b  pop     rsi
0x140030c0c  pop     rbp
0x140030c0d  pop     rbx
0x140030c0e  retn
0x140030c10  bt      eax, 13h
0x140030c14  jb      short loc_140030C20
0x140030c16  mov     rcx, rdi; Entry
0x140030c19  call    SendPacketOnBundle
0x140030c1e  jmp     short loc_140030BFE
0x140030c20  movzx   edx, byte ptr [rdi+6F0h]; NewIrql
0x140030c27  mov     rcx, r15; SpinLock
0x140030c2a  call    cs:__imp_KeReleaseSpinLock
0x140030c31  nop     dword ptr [rax+rax+00h]
0x140030c36  jmp     short loc_140030BFE
0x140030c38  mov     rcx, rdi; Entry
0x140030c3b  call    SendPacketOnBundle
0x140030c40  jmp     short loc_140030BCD
0x140030c42  mov     rdi, [rbx+38h]
0x140030c46  jmp     loc_1400309C3
0x140030c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140030c52  lea     rax, WPP_GLOBAL_Control
0x140030c59  cmp     rcx, rax
0x140030c5c  jz      short loc_140030C69
0x140030c5e  mov     eax, [rcx+2Ch]
0x140030c61  test    al, 8
0x140030c63  jnz     loc_140030DEB
0x140030c69  mov     eax, 0FFFFFFFFh
0x140030c6e  lock xadd [r12+18h], eax
0x140030c75  cmp     eax, 1
0x140030c78  jnz     loc_140030B8D
0x140030c7e  movzx   edx, byte ptr [rdi+6F0h]; NewIrql
0x140030c85  mov     rcx, r15; SpinLock
0x140030c88  call    cs:__imp_KeReleaseSpinLock
0x140030c8f  nop     dword ptr [rax+rax+00h]
0x140030c94  mov     eax, [r12+1Ch]
0x140030c99  test    al, 4
0x140030c9b  jz      loc_140030E14
0x140030ca1  mov     edx, r13d
0x140030ca4  mov     rcx, r12
0x140030ca7  call    CompleteSendDesc
0x140030cac  mov     rcx, r15; SpinLock
0x140030caf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030cb6  nop     dword ptr [rax+rax+00h]
0x140030cbb  mov     [rdi+6F0h], al
0x140030cc1  jmp     loc_140030B8D
0x140030cc6  mov     rcx, [r15+10h]
0x140030cca  movzx   eax, word ptr [rcx+0Ah]
0x140030cce  lea     r12, [rcx+10h]
0x140030cd2  add     r12, rax
0x140030cd5  mov     rcx, rbx
0x140030cd8  call    NdisWanFreeSendDesc
0x140030cdd  jmp     loc_140030B40
0x140030ce2  cmp     byte ptr [rsi+0C8h], 0
0x140030ce9  mov     byte ptr [rsi+0C9h], 1
0x140030cf0  jz      loc_140030B74
0x140030cf6  inc     dword ptr [rdi+9Ch]
0x140030cfc  jmp     loc_140030B74
0x140030d01  mov     rcx, rdi; Entry
0x140030d04  call    DoDerefBundleCBWork
0x140030d09  jmp     loc_140030BFE
0x140030d0e  mov     rax, [rcx+8]
0x140030d12  call    _guard_dispatch_icall
0x140030d17  jmp     loc_140030A67
0x140030d1c  cmp     byte ptr [rcx+29h], 5
0x140030d20  jb      loc_140030991
0x140030d26  mov     rcx, [rcx+18h]
0x140030d2a  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140030d31  mov     edx, 42h ; 'B'
0x140030d36  mov     [rsp+88h+var_60], r13d
0x140030d3b  mov     r9, rbx
0x140030d3e  mov     [rsp+88h+FreeMdlHandler], r15
0x140030d43  call    WPP_SF_qqD
0x140030d48  lea     rdx, WPP_GLOBAL_Control
0x140030d4f  jmp     loc_140030991
0x140030d54  cmp     byte ptr [rcx+29h], 5
0x140030d58  jb      loc_140030A1F
0x140030d5e  mov     rcx, [rcx+18h]
0x140030d62  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x140030d69  mov     edx, 33h ; '3'
0x140030d6e  mov     [rsp+88h+FreeMdlHandler], rbx
0x140030d73  mov     r9, r14
0x140030d76  call    WPP_SF_qq
0x140030d7b  jmp     loc_140030A1F
0x140030d80  mov     rcx, rbx; NetBufferList
0x140030d83  call    cs:__imp_NdisFreeNetBufferList
0x140030d8a  nop     dword ptr [rax+rax+00h]
0x140030d8f  mov     r13d, [rsp+88h+arg_8]
0x140030d97  jmp     loc_140030B40
0x140030d9c  mov     rcx, [r15+28h]; NdisVcHandle
0x140030da0  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x140030da7  nop     dword ptr [rax+rax+00h]
0x140030dac  mov     eax, 0FFFFFFFFh
0x140030db1  lock xadd [r15+18h], eax
0x140030db7  cmp     eax, 1
0x140030dba  jnz     loc_140030B39
0x140030dc0  mov     rcx, r15
0x140030dc3  call    DoDerefCmVcCBWork
0x140030dc8  jmp     loc_140030B39
0x140030dcd  movsxd  rax, [rsp+88h+arg_10]
0x140030dd5  lea     rcx, [rax+rax*2]
0x140030dd9  shl     rcx, 4
0x140030ddd  lock dec dword ptr [rcx+r14+98h]
0x140030de6  jmp     loc_140030B84
0x140030deb  cmp     byte ptr [rcx+29h], 5
0x140030def  jb      loc_140030C69
0x140030df5  mov     r9d, [r12+18h]
0x140030dfa  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140030e01  mov     rcx, [rcx+18h]
0x140030e05  mov     edx, 43h ; 'C'
0x140030e0a  call    WPP_SF_d
0x140030e0f  jmp     loc_140030C69
0x140030e14  mov     rbx, [r12+28h]
0x140030e19  lea     rcx, [rbx+2E0h]; SpinLock
0x140030e20  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030e27  nop     dword ptr [rax+rax+00h]
0x140030e2c  mov     [rbx+2E8h], al
0x140030e32  jmp     loc_140030CA1
0x140030e37  test    ecx, ecx
0x140030e39  jnz     loc_140030BAA
0x140030e3f  lea     rcx, [rdi+0B0h]; Event
0x140030e46  xor     r8d, r8d; Wait
0x140030e49  mov     edx, 1; Increment
0x140030e4e  call    cs:__imp_KeSetEvent
0x140030e55  nop     dword ptr [rax+rax+00h]
0x140030e5a  jmp     loc_140030BAA
```
