# ndisIfSetIfDescr(_NDIS_IF_DESCR_INFORMATION *)

- ea: `0x1400cd7bc`
- end: `0x1400cda59`
- name: `?ndisIfSetIfDescr@@YAHPEAU_NDIS_IF_DESCR_INFORMATION@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(struct _NDIS_IF_DESCR_INFORMATION *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14017b220`

## callees

- `0x14001cf50`
- `0x14001d350`
- `0x1400230c0`
- `0x140025da0`
- `0x1400412b0`
- `0x1400cd7bc`
- `0x1400e62c0`
- `0x1400e65c0`
- `0x140137950`
- `0x1401631c0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400cd8b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400cd8cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400cd8b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400cd8cb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400cd8e2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400cd8e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cd89b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cd967`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cd9f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cd89b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cd967`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cd9f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cd853`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cd8fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cd9d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cd853`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cd8fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cd9d6`

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
0x1400cd7bc  push    rbp
0x1400cd7be  push    rbx
0x1400cd7bf  push    rsi
0x1400cd7c0  push    rdi
0x1400cd7c1  push    r12
0x1400cd7c3  push    r13
0x1400cd7c5  push    r14
0x1400cd7c7  push    r15
0x1400cd7c9  lea     rbp, [rsp-1Fh]
0x1400cd7ce  sub     rsp, 88h
0x1400cd7d5  xor     r13d, r13d
0x1400cd7d8  mov     rsi, rcx
0x1400cd7db  mov     qword ptr [rbp+57h+DestinationString.Length], r13
0x1400cd7df  mov     [rbp+57h+DestinationString.Buffer], r13
0x1400cd7e3  mov     qword ptr [rbp+57h+String2.Length], r13
0x1400cd7e7  mov     [rbp+57h+String2.Buffer], r13
0x1400cd7eb  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400cd7f2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cd7f9  lea     rbx, WPP_ec7904e244ab3ff37c3c2f5002e64fc8_Traceguids
0x1400cd800  jz      short loc_1400CD826
0x1400cd802  mov     qword ptr [rsp+0C0h+var_98], rcx; char
0x1400cd807  lea     r9d, [r13+0Eh]; int
0x1400cd80b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd812  lea     r8d, [r13+16h]; int
0x1400cd816  mov     dl, 4; int
0x1400cd818  mov     [rsp+0C0h+var_A0], rbx; struct _GUID *
0x1400cd81d  mov     rcx, [rcx+40h]; int
0x1400cd821  call    WPP_RECORDER_SF_q
0x1400cd826  test    rsi, rsi
0x1400cd829  jnz     short loc_1400CD836
0x1400cd82b  mov     r14d, 0C000000Dh
0x1400cd831  jmp     loc_1400CDA06
0x1400cd836  mov     eax, [rsi]
0x1400cd838  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400cd83f  movzx   ebx, word ptr [rsi+4]
0x1400cd843  and     eax, 0FFFFFFh
0x1400cd848  shl     rbx, 18h
0x1400cd84c  or      rbx, rax
0x1400cd84f  shl     rbx, 18h
0x1400cd853  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400cd85a  nop     dword ptr [rax+rax+00h]
0x1400cd85f  mov     rcx, rbx; union _NET_LUID_LH
0x1400cd862  mov     r12b, al
0x1400cd865  call    ?ndisIfFindInterfaceByNetLuid@@YAPEAU_NDIS_IF_BLOCK@@T_NET_LUID_LH@@@Z; ndisIfFindInterfaceByNetLuid(_NET_LUID_LH)
0x1400cd86a  mov     rdi, rax
0x1400cd86d  lea     r15, [rax+8]
0x1400cd871  test    rax, rax
0x1400cd874  jz      loc_1400CD951
0x1400cd87a  mov     rcx, [rax+598h]
0x1400cd881  mov     dl, 0Dh
0x1400cd883  mov     r14d, r13d
0x1400cd886  call    NdisReferenceWithTag
0x1400cd88b  inc     dword ptr [rdi+518h]
0x1400cd891  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400cd898  mov     dl, r12b; NewIrql
0x1400cd89b  call    cs:__imp_KeReleaseSpinLock
0x1400cd8a2  nop     dword ptr [rax+rax+00h]
0x1400cd8a7  xor     ebx, ebx
0x1400cd8a9  cmp     [r15], bx
0x1400cd8ad  jz      short loc_1400CD8F5
0x1400cd8af  lea     rdx, [r15+2]; SourceString
0x1400cd8b3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400cd8b7  call    cs:__imp_RtlInitUnicodeString
0x1400cd8be  nop     dword ptr [rax+rax+00h]
0x1400cd8c3  lea     rdx, [rsi+0Ah]; SourceString
0x1400cd8c7  lea     rcx, [rbp+57h+String2]; DestinationString
0x1400cd8cb  call    cs:__imp_RtlInitUnicodeString
0x1400cd8d2  nop     dword ptr [rax+rax+00h]
0x1400cd8d7  mov     r8b, 1; CaseInSensitive
0x1400cd8da  lea     rdx, [rbp+57h+String2]; String2
0x1400cd8de  lea     rcx, [rbp+57h+DestinationString]; String1
0x1400cd8e2  call    cs:__imp_RtlCompareUnicodeString
0x1400cd8e9  nop     dword ptr [rax+rax+00h]
0x1400cd8ee  test    eax, eax
0x1400cd8f0  setnz   bl
0x1400cd8f3  jmp     short loc_1400CD8F7
0x1400cd8f5  mov     bl, 1
0x1400cd8f7  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400cd8fe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400cd905  nop     dword ptr [rax+rax+00h]
0x1400cd90a  mov     r12b, al
0x1400cd90d  test    bl, bl
0x1400cd90f  jz      short loc_1400CD95A
0x1400cd911  xor     edx, edx; Val
0x1400cd913  mov     r8d, 204h; Size
0x1400cd919  mov     rcx, r15; void *
0x1400cd91c  call    memset
0x1400cd921  movzx   ecx, word ptr [rsi+8]
0x1400cd925  mov     eax, 200h
0x1400cd92a  cmp     cx, ax
0x1400cd92d  ja      short loc_1400CD932
0x1400cd92f  movzx   eax, cx
0x1400cd932  xor     ecx, ecx
0x1400cd934  mov     [r15], ax
0x1400cd938  cmp     [rsi+8], cx
0x1400cd93c  jz      short loc_1400CD95A
0x1400cd93e  movzx   r8d, ax; Size
0x1400cd942  lea     rdx, [rsi+0Ah]; Src
0x1400cd946  lea     rcx, [r15+2]; void *
0x1400cd94a  call    memmove
0x1400cd94f  jmp     short loc_1400CD95A
0x1400cd951  mov     bl, r13b
0x1400cd954  mov     r14d, 0C0000034h
0x1400cd95a  mov     dl, r12b; NewIrql
0x1400cd95d  lea     r12, WPP_MAIN_CB.Reserved
0x1400cd964  mov     rcx, r12; SpinLock
0x1400cd967  call    cs:__imp_KeReleaseSpinLock
0x1400cd96e  nop     dword ptr [rax+rax+00h]
0x1400cd973  test    r14d, r14d
0x1400cd976  jnz     short loc_1400CD9CE
0x1400cd978  test    bl, bl
0x1400cd97a  jz      short loc_1400CD9CE
0x1400cd97c  cmp     [rdi+571h], r13b
0x1400cd983  jz      short loc_1400CD9A0
0x1400cd985  mov     edx, 204h; unsigned int
0x1400cd98a  lea     rcx, [rdi+520h]; unsigned __int8 *
0x1400cd991  mov     r9, r15; unsigned __int8 *
0x1400cd994  lea     r8d, [rdx+4]; unsigned int
0x1400cd998  call    ?ndisIfUpdatePersistedInterfaceInfo@@YAHPEAEKK0@Z; ndisIfUpdatePersistedInterfaceInfo(uchar *,ulong,ulong,uchar *)
0x1400cd99d  mov     r14d, eax
0x1400cd9a0  mov     r9d, 1
0x1400cd9a6  mov     [rbp+57h+var_60], 2
0x1400cd9ae  lea     r8, [rbp+57h+var_60]
0x1400cd9b2  mov     [rbp+57h+var_58], r15
0x1400cd9b6  xor     edx, edx
0x1400cd9b8  mov     [rbp+57h+var_50], 204h
0x1400cd9bf  mov     rcx, rdi
0x1400cd9c2  mov     [rbp+57h+var_4C], 4
0x1400cd9c9  call    ?ndisNsiNotifyClientInterfaceChange@@YAXPEAU_NDIS_IF_BLOCK@@W4_NSI_NOTIFICATION@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NDIS_NSI_OBJECT_INDEX@@@Z; ndisNsiNotifyClientInterfaceChange(_NDIS_IF_BLOCK *,_NSI_NOTIFICATION,_NSI_SINGLE_PARAM_DESC *,_NDIS_NSI_OBJECT_INDEX)
0x1400cd9ce  test    rdi, rdi
0x1400cd9d1  jz      short loc_1400CD9FF
0x1400cd9d3  mov     rcx, r12; SpinLock
0x1400cd9d6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400cd9dd  nop     dword ptr [rax+rax+00h]
0x1400cd9e2  mov     dl, 0Dh; enum _NDIS_IF_REFTAG
0x1400cd9e4  mov     rcx, rdi; P
0x1400cd9e7  mov     bl, al
0x1400cd9e9  call    ?IFBLOCK_DECREMENT_REF@@YAXPEAU_NDIS_IF_BLOCK@@W4_NDIS_IF_REFTAG@@@Z; IFBLOCK_DECREMENT_REF(_NDIS_IF_BLOCK *,_NDIS_IF_REFTAG)
0x1400cd9ee  mov     dl, bl; NewIrql
0x1400cd9f0  mov     rcx, r12; SpinLock
0x1400cd9f3  call    cs:__imp_KeReleaseSpinLock
0x1400cd9fa  nop     dword ptr [rax+rax+00h]
0x1400cd9ff  lea     rbx, WPP_ec7904e244ab3ff37c3c2f5002e64fc8_Traceguids
0x1400cda06  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400cda0d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cda14  jz      short loc_1400CDA41
0x1400cda16  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cda1d  mov     r9d, 0Fh; int
0x1400cda23  mov     dword ptr [rsp+0C0h+var_90], r14d; char
0x1400cda28  mov     dl, 4; int
0x1400cda2a  mov     qword ptr [rsp+0C0h+var_98], rsi; char
0x1400cda2f  mov     [rsp+0C0h+var_A0], rbx; struct _GUID *
0x1400cda34  mov     rcx, [rcx+40h]; int
0x1400cda38  lea     r8d, [r9+7]; int
0x1400cda3c  call    WPP_RECORDER_SF_qL
0x1400cda41  mov     eax, r14d
0x1400cda44  add     rsp, 88h
0x1400cda4b  pop     r15
0x1400cda4d  pop     r14
0x1400cda4f  pop     r13
0x1400cda51  pop     r12
0x1400cda53  pop     rdi
0x1400cda54  pop     rsi
0x1400cda55  pop     rbx
0x1400cda56  pop     rbp
0x1400cda57  retn
```
