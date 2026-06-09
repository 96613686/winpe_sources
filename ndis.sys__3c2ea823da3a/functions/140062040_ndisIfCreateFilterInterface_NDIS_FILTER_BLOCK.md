# ndisIfCreateFilterInterface(_NDIS_FILTER_BLOCK *)

- ea: `0x140062040`
- end: `0x14006224c`
- name: `?ndisIfCreateFilterInterface@@YAHPEAU_NDIS_FILTER_BLOCK@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(struct _NDIS_FILTER_BLOCK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140180960`

## callees

- `0x14001cf50`
- `0x14001d350`
- `0x140062040`
- `0x1401650a0`
- `0x140165310`
- `0x140165770`
- `0x140165f60`

## import_xrefs

- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400620b2`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400620b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006215b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006215b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140062137`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140062137`
- `ntoskrnl!ExUuidCreate` at `0x1400620e0`
- `ntoskrnl!ExUuidCreate` at `0x140062200`
- `ntoskrnl!ExUuidCreate` at `0x1400620e0`
- `ntoskrnl!ExUuidCreate` at `0x140062200`

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
0x140062040  mov     rax, rsp
0x140062043  mov     [rax+18h], rbx
0x140062047  mov     [rax+20h], rbp
0x14006204b  push    rsi
0x14006204c  push    rdi
0x14006204d  push    r12
0x14006204f  push    r14
0x140062051  push    r15
0x140062053  sub     rsp, 50h
0x140062057  mov     rsi, [rcx+20h]
0x14006205b  xor     r14d, r14d
0x14006205e  mov     [rax+8], r14d
0x140062062  mov     rbx, rcx
0x140062065  mov     [rax+10h], r14
0x140062069  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140062070  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140062077  lea     r12, WPP_0533647bba4931a92b3f74f2e1f8f42b_Traceguids
0x14006207e  jnz     loc_1400621CC
0x140062084  mov     rax, [rsi+0FC8h]
0x14006208b  lea     rdx, [rsp+78h+arg_0]; unsigned int *
0x140062093  xor     r9d, r9d; unsigned __int8
0x140062096  mov     r8b, 1; unsigned __int8
0x140062099  movzx   ebp, word ptr [rax+20Ch]
0x1400620a0  movzx   ecx, bp; unsigned __int16
0x1400620a3  call    ?ndisIfAllocateAndVerifyNetLuidIndex@@YAHGPEAIEE@Z; ndisIfAllocateAndVerifyNetLuidIndex(ushort,uint *,uchar,uchar)
0x1400620a8  mov     edi, eax
0x1400620aa  test    eax, eax
0x1400620ac  jnz     loc_1400621A0
0x1400620b2  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400620b9  nop     dword ptr [rax+rax+00h]
0x1400620be  test    al, al
0x1400620c0  jnz     loc_1400621F9
0x1400620c6  lea     rdx, [rbx+298h]; char
0x1400620cd  mov     rcx, rbx; char
0x1400620d0  call    ndisIfGetFilterIfInfoFromRegistry
0x1400620d5  test    eax, eax
0x1400620d7  jz      short loc_14006210D
0x1400620d9  lea     rcx, [rbx+298h]; Uuid
0x1400620e0  call    cs:__imp_ExUuidCreate
0x1400620e7  nop     dword ptr [rax+rax+00h]
0x1400620ec  test    eax, eax
0x1400620ee  js      loc_1400621C5
0x1400620f4  movups  xmm0, xmmword ptr [rbx+298h]
0x1400620fb  lea     rdx, [rsp+78h+var_38]
0x140062100  mov     rcx, rbx; char
0x140062103  movaps  [rsp+78h+var_38], xmm0
0x140062108  call    ndisIfSetFilterIfInfoInRegistry
0x14006210d  mov     ecx, [rsp+78h+arg_0]
0x140062114  mov     rax, rbp
0x140062117  and     ecx, 0FFFFFFh
0x14006211d  shl     rax, 18h
0x140062121  or      rcx, rax
0x140062124  shl     rcx, 18h
0x140062128  mov     qword ptr [rsp+78h+arg_8], rcx
0x140062130  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140062137  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006213e  nop     dword ptr [rax+rax+00h]
0x140062143  mov     rdx, [rsi+0FC8h]
0x14006214a  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140062151  mov     rdi, [rdx+558h]
0x140062158  movzx   edx, al; NewIrql
0x14006215b  call    cs:__imp_KeReleaseSpinLock
0x140062162  nop     dword ptr [rax+rax+00h]
0x140062167  mov     [rsp+78h+var_40], 2; enum NdisIfBlockSource
0x14006216f  lea     r9, [rsp+78h+arg_8]; union _NET_LUID_LH *
0x140062177  mov     [rsp+78h+var_48], rbx; struct _NDIS_FILTER_BLOCK *
0x14006217c  xor     r8d, r8d; struct _NDIS_NSI_COMPARTMENT_RW *
0x14006217f  mov     [rsp+78h+var_50], r14; struct NdisNetworkInterfacePersistedState *
0x140062184  xor     edx, edx; unsigned __int8
0x140062186  mov     rcx, rdi; struct _NDIS_IF_NETWORK_BLOCK *
0x140062189  mov     [rsp+78h+var_58], r14; struct _GUID *
0x14006218e  call    ?ndisIfCreateInterface@@YAJPEAU_NDIS_IF_NETWORK_BLOCK@@EPEAU_NDIS_NSI_COMPARTMENT_RW@@PEBT_NET_LUID_LH@@PEBU_GUID@@PEBUNdisNetworkInterfacePersistedState@@PEAU_NDIS_FILTER_BLOCK@@W4NdisIfBlockSource@@@Z; ndisIfCreateInterface(_NDIS_IF_NETWORK_BLOCK *,uchar,_NDIS_NSI_COMPARTMENT_RW *,_NET_LUID_LH const *,_GUID const *,NdisNetworkInterfacePersistedState const *,_NDIS_FILTER_BLOCK *,NdisIfBlockSource)
0x140062193  test    eax, eax
0x140062195  mov     ecx, 0C0000001h
0x14006219a  mov     edi, r14d
0x14006219d  cmovs   edi, ecx
0x1400621a0  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400621a7  jnz     short loc_14006221B
0x1400621a9  lea     r11, [rsp+78h+var_28]
0x1400621ae  mov     eax, edi
0x1400621b0  mov     rbx, [r11+40h]
0x1400621b4  mov     rbp, [r11+48h]
0x1400621b8  mov     rsp, r11
0x1400621bb  pop     r15
0x1400621bd  pop     r14
0x1400621bf  pop     r12
0x1400621c1  pop     rdi
0x1400621c2  pop     rsi
0x1400621c3  retn
0x1400621c5  mov     edi, 0C0000001h
0x1400621ca  jmp     short loc_1400621A0
0x1400621cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400621d3  mov     r9d, 10h; int
0x1400621d9  mov     [rsp+78h+var_50], rbx; char
0x1400621de  mov     r8d, 16h; int
0x1400621e4  mov     dl, 4; int
0x1400621e6  mov     [rsp+78h+var_58], r12; struct _GUID *
0x1400621eb  mov     rcx, [rcx+40h]; int
0x1400621ef  call    WPP_RECORDER_SF_q
0x1400621f4  jmp     loc_140062084
0x1400621f9  lea     rcx, [rbx+298h]; Uuid
0x140062200  call    cs:__imp_ExUuidCreate
0x140062207  nop     dword ptr [rax+rax+00h]
0x14006220c  test    eax, eax
0x14006220e  jns     loc_14006210D
0x140062214  mov     edi, 0C0000001h
0x140062219  jmp     short loc_1400621A0
0x14006221b  mov     rcx, cs:WPP_GLOBAL_Control
0x140062222  mov     r9d, 11h; int
0x140062228  mov     dword ptr [rsp+78h+var_48], edi; char
0x14006222c  mov     r8d, 16h; int
0x140062232  mov     [rsp+78h+var_50], rbx; char
0x140062237  mov     dl, 4; int
0x140062239  mov     [rsp+78h+var_58], r12; struct _GUID *
0x14006223e  mov     rcx, [rcx+40h]; int
0x140062242  call    WPP_RECORDER_SF_qL
0x140062247  jmp     loc_1400621A9
```
