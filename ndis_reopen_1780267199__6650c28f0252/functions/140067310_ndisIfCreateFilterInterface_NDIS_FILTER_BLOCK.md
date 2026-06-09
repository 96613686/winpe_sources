# ndisIfCreateFilterInterface(_NDIS_FILTER_BLOCK *)

- ea: `0x140067310`
- end: `0x14006751c`
- name: `?ndisIfCreateFilterInterface@@YAHPEAU_NDIS_FILTER_BLOCK@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(struct _NDIS_FILTER_BLOCK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140186f10`

## callees

- `0x1400110b0`
- `0x1400114b0`
- `0x140067310`
- `0x14016c030`
- `0x14016c2a0`
- `0x14016c700`
- `0x14016cef0`

## import_xrefs

- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140067382`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140067382`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006742b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006742b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140067407`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140067407`
- `ntoskrnl!ExUuidCreate` at `0x1400673b0`
- `ntoskrnl!ExUuidCreate` at `0x1400674d0`
- `ntoskrnl!ExUuidCreate` at `0x1400673b0`
- `ntoskrnl!ExUuidCreate` at `0x1400674d0`

## pseudocode

```c
__int64 __fastcall ndisIfCreateFilterInterface(struct _NDIS_FILTER_BLOCK *a1)
{
  _NDIS_MINIPORT_BLOCK *Miniport; // rsi
  __int64 ifType; // rbp
  int v4; // edx
  unsigned int v5; // edi
  KIRQL v6; // al
  struct _NDIS_IF_NETWORK_BLOCK *Network; // rdi
  int v8; // eax
  unsigned int v10; // [rsp+80h] [rbp+8h] BYREF
  union _NET_LUID_LH v11; // [rsp+88h] [rbp+10h] BYREF

  Miniport = a1->Miniport;
  v10 = 0;
  v11.Value = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      22,
      16,
      (struct _GUID *)&WPP_0533647bba4931a92b3f74f2e1f8f42b_Traceguids,
      (char)a1);
  ifType = Miniport->IfBlock->ifType;
  v5 = ndisIfAllocateAndVerifyNetLuidIndex(Miniport->IfBlock->ifType, &v10, 1u, 0);
  if ( !v5 )
  {
    if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
    {
      if ( ExUuidCreate(&a1->InterfaceGuid) < 0 )
      {
        v5 = -1073741823;
        goto LABEL_10;
      }
    }
    else if ( (unsigned int)ndisIfGetFilterIfInfoFromRegistry((char)a1, (unsigned __int8)a1 - 104) )
    {
      if ( ExUuidCreate(&a1->InterfaceGuid) < 0 )
      {
        v5 = -1073741823;
        goto LABEL_10;
      }
      ndisIfSetFilterIfInfoInRegistry((char)a1);
    }
    v11.Value = ((ifType << 24) | v10 & 0xFFFFFF) << 24;
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
    Network = Miniport->IfBlock->Network;
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v6);
    v8 = ndisIfCreateInterface(Network, 0, 0, &v11, 0, 0, a1, NdisIfBlockSourceAutomaticLwFilter);
    v5 = 0;
    if ( v8 < 0 )
      v5 = -1073741823;
  }
LABEL_10:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v4,
      22,
      17,
      (struct _GUID *)&WPP_0533647bba4931a92b3f74f2e1f8f42b_Traceguids,
      (char)a1,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x140067310  mov     rax, rsp
0x140067313  mov     [rax+18h], rbx
0x140067317  mov     [rax+20h], rbp
0x14006731b  push    rsi
0x14006731c  push    rdi
0x14006731d  push    r12
0x14006731f  push    r14
0x140067321  push    r15
0x140067323  sub     rsp, 50h
0x140067327  mov     rsi, [rcx+20h]
0x14006732b  xor     r14d, r14d
0x14006732e  mov     [rax+8], r14d
0x140067332  mov     rbx, rcx
0x140067335  mov     [rax+10h], r14
0x140067339  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140067340  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140067347  lea     r12, WPP_0533647bba4931a92b3f74f2e1f8f42b_Traceguids
0x14006734e  jnz     loc_14006749C
0x140067354  mov     rax, [rsi+0FC8h]
0x14006735b  lea     rdx, [rsp+78h+arg_0]; unsigned int *
0x140067363  xor     r9d, r9d; unsigned __int8
0x140067366  mov     r8b, 1; unsigned __int8
0x140067369  movzx   ebp, word ptr [rax+20Ch]
0x140067370  movzx   ecx, bp; unsigned __int16
0x140067373  call    ?ndisIfAllocateAndVerifyNetLuidIndex@@YAHGPEAIEE@Z; ndisIfAllocateAndVerifyNetLuidIndex(ushort,uint *,uchar,uchar)
0x140067378  mov     edi, eax
0x14006737a  test    eax, eax
0x14006737c  jnz     loc_140067470
0x140067382  call    cs:__imp_RtlIsStateSeparationEnabled
0x140067389  nop     dword ptr [rax+rax+00h]
0x14006738e  test    al, al
0x140067390  jnz     loc_1400674C9
0x140067396  lea     rdx, [rbx+298h]; char
0x14006739d  mov     rcx, rbx; char
0x1400673a0  call    ndisIfGetFilterIfInfoFromRegistry
0x1400673a5  test    eax, eax
0x1400673a7  jz      short loc_1400673DD
0x1400673a9  lea     rcx, [rbx+298h]; Uuid
0x1400673b0  call    cs:__imp_ExUuidCreate
0x1400673b7  nop     dword ptr [rax+rax+00h]
0x1400673bc  test    eax, eax
0x1400673be  js      loc_140067495
0x1400673c4  movups  xmm0, xmmword ptr [rbx+298h]
0x1400673cb  lea     rdx, [rsp+78h+var_38]
0x1400673d0  mov     rcx, rbx; char
0x1400673d3  movaps  [rsp+78h+var_38], xmm0
0x1400673d8  call    ndisIfSetFilterIfInfoInRegistry
0x1400673dd  mov     ecx, [rsp+78h+arg_0]
0x1400673e4  mov     rax, rbp
0x1400673e7  and     ecx, 0FFFFFFh
0x1400673ed  shl     rax, 18h
0x1400673f1  or      rcx, rax
0x1400673f4  shl     rcx, 18h
0x1400673f8  mov     qword ptr [rsp+78h+arg_8], rcx
0x140067400  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140067407  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006740e  nop     dword ptr [rax+rax+00h]
0x140067413  mov     rdx, [rsi+0FC8h]
0x14006741a  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140067421  mov     rdi, [rdx+558h]
0x140067428  movzx   edx, al; NewIrql
0x14006742b  call    cs:__imp_KeReleaseSpinLock
0x140067432  nop     dword ptr [rax+rax+00h]
0x140067437  mov     [rsp+78h+var_40], 2; enum NdisIfBlockSource
0x14006743f  lea     r9, [rsp+78h+arg_8]; union _NET_LUID_LH *
0x140067447  mov     [rsp+78h+var_48], rbx; struct _NDIS_FILTER_BLOCK *
0x14006744c  xor     r8d, r8d; struct _NDIS_NSI_COMPARTMENT_RW *
0x14006744f  mov     [rsp+78h+var_50], r14; struct NdisNetworkInterfacePersistedState *
0x140067454  xor     edx, edx; unsigned __int8
0x140067456  mov     rcx, rdi; struct _NDIS_IF_NETWORK_BLOCK *
0x140067459  mov     [rsp+78h+var_58], r14; struct _GUID *
0x14006745e  call    ?ndisIfCreateInterface@@YAJPEAU_NDIS_IF_NETWORK_BLOCK@@EPEAU_NDIS_NSI_COMPARTMENT_RW@@PEBT_NET_LUID_LH@@PEBU_GUID@@PEBUNdisNetworkInterfacePersistedState@@PEAU_NDIS_FILTER_BLOCK@@W4NdisIfBlockSource@@@Z; ndisIfCreateInterface(_NDIS_IF_NETWORK_BLOCK *,uchar,_NDIS_NSI_COMPARTMENT_RW *,_NET_LUID_LH const *,_GUID const *,NdisNetworkInterfacePersistedState const *,_NDIS_FILTER_BLOCK *,NdisIfBlockSource)
0x140067463  test    eax, eax
0x140067465  mov     ecx, 0C0000001h
0x14006746a  mov     edi, r14d
0x14006746d  cmovs   edi, ecx
0x140067470  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140067477  jnz     short loc_1400674EB
0x140067479  lea     r11, [rsp+78h+var_28]
0x14006747e  mov     eax, edi
0x140067480  mov     rbx, [r11+40h]
0x140067484  mov     rbp, [r11+48h]
0x140067488  mov     rsp, r11
0x14006748b  pop     r15
0x14006748d  pop     r14
0x14006748f  pop     r12
0x140067491  pop     rdi
0x140067492  pop     rsi
0x140067493  retn
0x140067495  mov     edi, 0C0000001h
0x14006749a  jmp     short loc_140067470
0x14006749c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400674a3  mov     r9d, 10h; int
0x1400674a9  mov     [rsp+78h+var_50], rbx; char
0x1400674ae  mov     r8d, 16h; int
0x1400674b4  mov     dl, 4; int
0x1400674b6  mov     [rsp+78h+var_58], r12; struct _GUID *
0x1400674bb  mov     rcx, [rcx+40h]; int
0x1400674bf  call    WPP_RECORDER_SF_q
0x1400674c4  jmp     loc_140067354
0x1400674c9  lea     rcx, [rbx+298h]; Uuid
0x1400674d0  call    cs:__imp_ExUuidCreate
0x1400674d7  nop     dword ptr [rax+rax+00h]
0x1400674dc  test    eax, eax
0x1400674de  jns     loc_1400673DD
0x1400674e4  mov     edi, 0C0000001h
0x1400674e9  jmp     short loc_140067470
0x1400674eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400674f2  mov     r9d, 11h; int
0x1400674f8  mov     dword ptr [rsp+78h+var_48], edi; char
0x1400674fc  mov     r8d, 16h; int
0x140067502  mov     [rsp+78h+var_50], rbx; char
0x140067507  mov     dl, 4; int
0x140067509  mov     [rsp+78h+var_58], r12; struct _GUID *
0x14006750e  mov     rcx, [rcx+40h]; int
0x140067512  call    WPP_RECORDER_SF_qL
0x140067517  jmp     loc_140067479
```
