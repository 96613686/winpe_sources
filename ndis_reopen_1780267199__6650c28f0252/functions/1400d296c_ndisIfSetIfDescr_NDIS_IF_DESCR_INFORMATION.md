# ndisIfSetIfDescr(_NDIS_IF_DESCR_INFORMATION *)

- ea: `0x1400d296c`
- end: `0x1400d2c09`
- name: `?ndisIfSetIfDescr@@YAHPEAU_NDIS_IF_DESCR_INFORMATION@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(struct _NDIS_IF_DESCR_INFORMATION *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401811f0`

## callees

- `0x1400110b0`
- `0x1400114b0`
- `0x140017220`
- `0x140019f00`
- `0x140043c30`
- `0x1400d296c`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x14013e950`
- `0x14016a150`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400d2a67`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d2a7b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d2a67`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d2a7b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400d2a92`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400d2a92`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d2a4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d2b17`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d2ba3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d2a4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d2b17`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d2ba3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d2a03`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d2aae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d2b86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d2a03`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d2aae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d2b86`

## pseudocode

```c
__int64 __fastcall ndisIfSetIfDescr(const WCHAR *a1)
{
  unsigned int updated; // r14d
  unsigned __int64 v3; // rbx
  KIRQL v4; // r12
  struct _NDIS_IF_BLOCK *InterfaceByNetLuid; // rax
  __int64 v6; // rdx
  struct _NDIS_IF_BLOCK *v7; // rdi
  _IF_COUNTED_STRING_LH *p_ifDescr; // r15
  bool v9; // bl
  unsigned __int16 v10; // ax
  KIRQL v11; // bl
  UNICODE_STRING String2; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v15[2]; // [rsp+60h] [rbp-9h] BYREF
  int v16; // [rsp+70h] [rbp+7h]
  int v17; // [rsp+74h] [rbp+Bh]

  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      22,
      14,
      (struct _GUID *)&WPP_ec7904e244ab3ff37c3c2f5002e64fc8_Traceguids,
      (char)a1);
  if ( a1 )
  {
    v3 = (*(_DWORD *)a1 & 0xFFFFFF | ((unsigned __int64)a1[2] << 24)) << 24;
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
    InterfaceByNetLuid = ndisIfFindInterfaceByNetLuid((union _NET_LUID_LH)v3);
    v7 = InterfaceByNetLuid;
    p_ifDescr = &InterfaceByNetLuid->ifDescr;
    if ( InterfaceByNetLuid )
    {
      LOBYTE(v6) = 13;
      updated = 0;
      NdisReferenceWithTag(InterfaceByNetLuid->RefCountTracker, v6);
      ++v7->Ref;
      KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v4);
      if ( p_ifDescr->Length )
      {
        RtlInitUnicodeString(&DestinationString, p_ifDescr->String);
        RtlInitUnicodeString(&String2, a1 + 5);
        v9 = RtlCompareUnicodeString(&DestinationString, &String2, 1u) != 0;
      }
      else
      {
        v9 = 1;
      }
      v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
      if ( v9 )
      {
        memset(p_ifDescr, 0, sizeof(_IF_COUNTED_STRING_LH));
        v10 = 512;
        if ( a1[4] <= 0x200u )
          v10 = a1[4];
        p_ifDescr->Length = v10;
        if ( a1[4] )
          memmove(p_ifDescr->String, a1 + 5, v10);
      }
    }
    else
    {
      v9 = 0;
      updated = -1073741772;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v4);
    if ( !updated && v9 )
    {
      if ( v7->bNdisIsProvider )
        updated = ndisIfUpdatePersistedInterfaceInfo(
                    (unsigned __int8 *)&v7->NetLuid,
                    0x204u,
                    0x208u,
                    (unsigned __int8 *)p_ifDescr);
      v15[0] = 2;
      v15[1] = p_ifDescr;
      v16 = 516;
      v17 = 4;
      ndisNsiNotifyClientInterfaceChange(v7, 0, v15, 1);
    }
    if ( v7 )
    {
      v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
      IFBLOCK_DECREMENT_REF(v7, IFREF_SETDESCR);
      KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v11);
    }
  }
  else
  {
    updated = -1073741811;
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      22,
      15,
      (struct _GUID *)&WPP_ec7904e244ab3ff37c3c2f5002e64fc8_Traceguids,
      (char)a1,
      updated);
  return updated;
}

```

## disassembly

```asm
0x1400d296c  push    rbp
0x1400d296e  push    rbx
0x1400d296f  push    rsi
0x1400d2970  push    rdi
0x1400d2971  push    r12
0x1400d2973  push    r13
0x1400d2975  push    r14
0x1400d2977  push    r15
0x1400d2979  lea     rbp, [rsp-1Fh]
0x1400d297e  sub     rsp, 88h
0x1400d2985  xor     r13d, r13d
0x1400d2988  mov     rsi, rcx
0x1400d298b  mov     qword ptr [rbp+57h+DestinationString.Length], r13
0x1400d298f  mov     [rbp+57h+DestinationString.Buffer], r13
0x1400d2993  mov     qword ptr [rbp+57h+String2.Length], r13
0x1400d2997  mov     [rbp+57h+String2.Buffer], r13
0x1400d299b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d29a2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d29a9  lea     rbx, WPP_ec7904e244ab3ff37c3c2f5002e64fc8_Traceguids
0x1400d29b0  jz      short loc_1400D29D6
0x1400d29b2  mov     qword ptr [rsp+0C0h+var_98], rcx; char
0x1400d29b7  lea     r9d, [r13+0Eh]; int
0x1400d29bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d29c2  lea     r8d, [r13+16h]; int
0x1400d29c6  mov     dl, 4; int
0x1400d29c8  mov     [rsp+0C0h+var_A0], rbx; struct _GUID *
0x1400d29cd  mov     rcx, [rcx+40h]; int
0x1400d29d1  call    WPP_RECORDER_SF_q
0x1400d29d6  test    rsi, rsi
0x1400d29d9  jnz     short loc_1400D29E6
0x1400d29db  mov     r14d, 0C000000Dh
0x1400d29e1  jmp     loc_1400D2BB6
0x1400d29e6  mov     eax, [rsi]
0x1400d29e8  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400d29ef  movzx   ebx, word ptr [rsi+4]
0x1400d29f3  and     eax, 0FFFFFFh
0x1400d29f8  shl     rbx, 18h
0x1400d29fc  or      rbx, rax
0x1400d29ff  shl     rbx, 18h
0x1400d2a03  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d2a0a  nop     dword ptr [rax+rax+00h]
0x1400d2a0f  mov     rcx, rbx; union _NET_LUID_LH
0x1400d2a12  mov     r12b, al
0x1400d2a15  call    ?ndisIfFindInterfaceByNetLuid@@YAPEAU_NDIS_IF_BLOCK@@T_NET_LUID_LH@@@Z; ndisIfFindInterfaceByNetLuid(_NET_LUID_LH)
0x1400d2a1a  mov     rdi, rax
0x1400d2a1d  lea     r15, [rax+8]
0x1400d2a21  test    rax, rax
0x1400d2a24  jz      loc_1400D2B01
0x1400d2a2a  mov     rcx, [rax+598h]
0x1400d2a31  mov     dl, 0Dh
0x1400d2a33  mov     r14d, r13d
0x1400d2a36  call    NdisReferenceWithTag
0x1400d2a3b  inc     dword ptr [rdi+518h]
0x1400d2a41  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400d2a48  mov     dl, r12b; NewIrql
0x1400d2a4b  call    cs:__imp_KeReleaseSpinLock
0x1400d2a52  nop     dword ptr [rax+rax+00h]
0x1400d2a57  xor     ebx, ebx
0x1400d2a59  cmp     [r15], bx
0x1400d2a5d  jz      short loc_1400D2AA5
0x1400d2a5f  lea     rdx, [r15+2]; SourceString
0x1400d2a63  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400d2a67  call    cs:__imp_RtlInitUnicodeString
0x1400d2a6e  nop     dword ptr [rax+rax+00h]
0x1400d2a73  lea     rdx, [rsi+0Ah]; SourceString
0x1400d2a77  lea     rcx, [rbp+57h+String2]; DestinationString
0x1400d2a7b  call    cs:__imp_RtlInitUnicodeString
0x1400d2a82  nop     dword ptr [rax+rax+00h]
0x1400d2a87  mov     r8b, 1; CaseInSensitive
0x1400d2a8a  lea     rdx, [rbp+57h+String2]; String2
0x1400d2a8e  lea     rcx, [rbp+57h+DestinationString]; String1
0x1400d2a92  call    cs:__imp_RtlCompareUnicodeString
0x1400d2a99  nop     dword ptr [rax+rax+00h]
0x1400d2a9e  test    eax, eax
0x1400d2aa0  setnz   bl
0x1400d2aa3  jmp     short loc_1400D2AA7
0x1400d2aa5  mov     bl, 1
0x1400d2aa7  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400d2aae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d2ab5  nop     dword ptr [rax+rax+00h]
0x1400d2aba  mov     r12b, al
0x1400d2abd  test    bl, bl
0x1400d2abf  jz      short loc_1400D2B0A
0x1400d2ac1  xor     edx, edx; Val
0x1400d2ac3  mov     r8d, 204h; Size
0x1400d2ac9  mov     rcx, r15; void *
0x1400d2acc  call    memset
0x1400d2ad1  movzx   ecx, word ptr [rsi+8]
0x1400d2ad5  mov     eax, 200h
0x1400d2ada  cmp     cx, ax
0x1400d2add  ja      short loc_1400D2AE2
0x1400d2adf  movzx   eax, cx
0x1400d2ae2  xor     ecx, ecx
0x1400d2ae4  mov     [r15], ax
0x1400d2ae8  cmp     [rsi+8], cx
0x1400d2aec  jz      short loc_1400D2B0A
0x1400d2aee  movzx   r8d, ax; Size
0x1400d2af2  lea     rdx, [rsi+0Ah]; Src
0x1400d2af6  lea     rcx, [r15+2]; void *
0x1400d2afa  call    memmove
0x1400d2aff  jmp     short loc_1400D2B0A
0x1400d2b01  mov     bl, r13b
0x1400d2b04  mov     r14d, 0C0000034h
0x1400d2b0a  mov     dl, r12b; NewIrql
0x1400d2b0d  lea     r12, WPP_MAIN_CB.Reserved
0x1400d2b14  mov     rcx, r12; SpinLock
0x1400d2b17  call    cs:__imp_KeReleaseSpinLock
0x1400d2b1e  nop     dword ptr [rax+rax+00h]
0x1400d2b23  test    r14d, r14d
0x1400d2b26  jnz     short loc_1400D2B7E
0x1400d2b28  test    bl, bl
0x1400d2b2a  jz      short loc_1400D2B7E
0x1400d2b2c  cmp     [rdi+571h], r13b
0x1400d2b33  jz      short loc_1400D2B50
0x1400d2b35  mov     edx, 204h; unsigned int
0x1400d2b3a  lea     rcx, [rdi+520h]; unsigned __int8 *
0x1400d2b41  mov     r9, r15; unsigned __int8 *
0x1400d2b44  lea     r8d, [rdx+4]; unsigned int
0x1400d2b48  call    ?ndisIfUpdatePersistedInterfaceInfo@@YAHPEAEKK0@Z; ndisIfUpdatePersistedInterfaceInfo(uchar *,ulong,ulong,uchar *)
0x1400d2b4d  mov     r14d, eax
0x1400d2b50  mov     r9d, 1
0x1400d2b56  mov     [rbp+57h+var_60], 2
0x1400d2b5e  lea     r8, [rbp+57h+var_60]
0x1400d2b62  mov     [rbp+57h+var_58], r15
0x1400d2b66  xor     edx, edx
0x1400d2b68  mov     [rbp+57h+var_50], 204h
0x1400d2b6f  mov     rcx, rdi
0x1400d2b72  mov     [rbp+57h+var_4C], 4
0x1400d2b79  call    ?ndisNsiNotifyClientInterfaceChange@@YAXPEAU_NDIS_IF_BLOCK@@W4_NSI_NOTIFICATION@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NDIS_NSI_OBJECT_INDEX@@@Z; ndisNsiNotifyClientInterfaceChange(_NDIS_IF_BLOCK *,_NSI_NOTIFICATION,_NSI_SINGLE_PARAM_DESC *,_NDIS_NSI_OBJECT_INDEX)
0x1400d2b7e  test    rdi, rdi
0x1400d2b81  jz      short loc_1400D2BAF
0x1400d2b83  mov     rcx, r12; SpinLock
0x1400d2b86  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d2b8d  nop     dword ptr [rax+rax+00h]
0x1400d2b92  mov     dl, 0Dh; enum _NDIS_IF_REFTAG
0x1400d2b94  mov     rcx, rdi; P
0x1400d2b97  mov     bl, al
0x1400d2b99  call    ?IFBLOCK_DECREMENT_REF@@YAXPEAU_NDIS_IF_BLOCK@@W4_NDIS_IF_REFTAG@@@Z; IFBLOCK_DECREMENT_REF(_NDIS_IF_BLOCK *,_NDIS_IF_REFTAG)
0x1400d2b9e  mov     dl, bl; NewIrql
0x1400d2ba0  mov     rcx, r12; SpinLock
0x1400d2ba3  call    cs:__imp_KeReleaseSpinLock
0x1400d2baa  nop     dword ptr [rax+rax+00h]
0x1400d2baf  lea     rbx, WPP_ec7904e244ab3ff37c3c2f5002e64fc8_Traceguids
0x1400d2bb6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d2bbd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d2bc4  jz      short loc_1400D2BF1
0x1400d2bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2bcd  mov     r9d, 0Fh; int
0x1400d2bd3  mov     dword ptr [rsp+0C0h+var_90], r14d; char
0x1400d2bd8  mov     dl, 4; int
0x1400d2bda  mov     qword ptr [rsp+0C0h+var_98], rsi; char
0x1400d2bdf  mov     [rsp+0C0h+var_A0], rbx; struct _GUID *
0x1400d2be4  mov     rcx, [rcx+40h]; int
0x1400d2be8  lea     r8d, [r9+7]; int
0x1400d2bec  call    WPP_RECORDER_SF_qL
0x1400d2bf1  mov     eax, r14d
0x1400d2bf4  add     rsp, 88h
0x1400d2bfb  pop     r15
0x1400d2bfd  pop     r14
0x1400d2bff  pop     r13
0x1400d2c01  pop     r12
0x1400d2c03  pop     rdi
0x1400d2c04  pop     rsi
0x1400d2c05  pop     rbx
0x1400d2c06  pop     rbp
0x1400d2c07  retn
```
