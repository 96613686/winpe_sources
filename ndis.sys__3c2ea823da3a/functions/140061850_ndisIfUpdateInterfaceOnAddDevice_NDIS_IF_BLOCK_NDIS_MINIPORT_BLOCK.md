# ndisIfUpdateInterfaceOnAddDevice(_NDIS_IF_BLOCK *,_NDIS_MINIPORT_BLOCK *)

- ea: `0x140061850`
- end: `0x140061a38`
- name: `?ndisIfUpdateInterfaceOnAddDevice@@YAHPEAU_NDIS_IF_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(struct _NDIS_IF_BLOCK *, struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14017f260`

## callees

- `0x140016840`
- `0x140019c70`
- `0x14001c050`
- `0x140020b40`
- `0x1400230c0`
- `0x140061850`
- `0x140061a40`
- `0x1400e62c0`
- `0x1400e65c0`
- `0x140137950`
- `0x140163170`
- `0x1401631c0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400618e2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400618e2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400618fd`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400618fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140061952`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ed3d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140061952`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ed3d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006192a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006192a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ed392`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ed392`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400ed351`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400ed351`

## pseudocode

```c
__int64 __fastcall ndisIfUpdateInterfaceOnAddDevice(struct _NDIS_IF_BLOCK *a1, struct _NDIS_MINIPORT_BLOCK *a2)
{
  struct _NDIS_MINIPORT_BLOCK *v2; // r14
  const struct _GUID *v4; // rcx
  _IF_COUNTED_STRING_LH *p_ifDescr; // rbx
  bool v6; // r13
  __int64 RefCount; // rsi
  KIRQL v8; // al
  __int64 v9; // rdx
  KIRQL v10; // r15
  unsigned int v11; // ebp
  int v12; // edx
  unsigned __int16 Length; // cx
  unsigned __int16 v15; // ax
  NDIS_REFCOUNT_HANDLE__ *RefCountTracker; // rcx
  char v17; // [rsp+30h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF
  __int64 v19; // [rsp+50h] [rbp-48h] BYREF
  void *p_ifAdminStatus; // [rsp+58h] [rbp-40h]
  int v21; // [rsp+60h] [rbp-38h]
  int v22; // [rsp+64h] [rbp-34h]

  v2 = a2;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v4 = &WPP_3d61bbabecaa38aa84130e7e4a2da4d6_Traceguids;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v17 = (char)a2;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      22,
      14,
      (struct _GUID *)&WPP_3d61bbabecaa38aa84130e7e4a2da4d6_Traceguids,
      (char)a1,
      v17);
  }
  p_ifDescr = &a1->ifDescr;
  if ( a1->ifDescr.Length )
  {
    RtlInitUnicodeString(&DestinationString, a1->ifDescr.String);
    v6 = RtlCompareUnicodeString(&DestinationString, v2->pAdapterInstanceName, 1u) != 0;
  }
  else
  {
    v6 = 1;
  }
  LOBYTE(a2) = 2;
  LOBYTE(v4) = 30;
  RefCount = NdisAllocateRefCount(v4, a2);
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
  v10 = v8;
  if ( a1->MiniportAvailable )
  {
    v11 = -1073741823;
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v8);
    NdisDereferenceWithTag(RefCount);
    NdisFreeRefCount(RefCount);
    goto LABEL_7;
  }
  v11 = 0;
  if ( v6 )
  {
    memset(&a1->ifDescr, 0, sizeof(a1->ifDescr));
    Length = v2->pAdapterInstanceName->Length;
    v15 = 512;
    if ( Length > 0x200u )
    {
      p_ifDescr->Length = 512;
LABEL_16:
      memmove(a1->ifDescr.String, v2->pAdapterInstanceName->Buffer, v15);
      goto LABEL_17;
    }
    p_ifDescr->Length = Length;
    if ( Length )
    {
      v15 = Length;
      goto LABEL_16;
    }
  }
LABEL_17:
  RefCountTracker = a1->RefCountTracker;
  LOBYTE(v9) = 12;
  a1->ifAdminStatus = v2->AdminStatus;
  *(_QWORD *)&a1->ifOperStatus = 2;
  NdisReferenceWithTag(RefCountTracker, v9);
  ++a1->Ref;
  a1->LastMiniportFatalErrorReason = NdisMEvent_Unknown;
  KeAcquireSpinLockAtDpcLevel(&SpinLock);
  a1->MiniportAvailable = 1;
  a1->MiniportLinkReference = 1;
  a1->Miniport = v2;
  a1->MpRefCountTracker = (NDIS_REFCOUNT_HANDLE__ *)RefCount;
  v2->IfBlock = a1;
  v2->IfBlockAvailable = 1;
  KeReleaseSpinLockFromDpcLevel(&SpinLock);
  v2->IfIndex = a1->ifIndex;
  v2->NetLuid.Value = a1->NetLuid.Value;
  v2->OperStatus = a1->ifOperStatus;
  v2->OperStatusFlags = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v10);
  if ( v6 )
  {
    ndisIfUpdatePersistedInterfaceInfo((unsigned __int8 *)&a1->NetLuid, 0x204u, 0x208u, (unsigned __int8 *)&a1->ifDescr);
    v19 = 2;
    p_ifAdminStatus = &a1->ifDescr;
    v21 = 516;
    v22 = 4;
    ndisNsiNotifyClientInterfaceChange(a1, 0, &v19, 1);
  }
  v19 = 0;
  p_ifAdminStatus = &a1->ifAdminStatus;
  v21 = 4;
  v22 = 16;
  ndisNsiNotifyClientInterfaceChange(a1, 0, &v19, 0);
  ndisNsiSyncMiniportOperStatusNotification(v2);
LABEL_7:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 4;
    WPP_RECORDER_SF_qqL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v12,
      22,
      15,
      (struct _GUID *)&WPP_3d61bbabecaa38aa84130e7e4a2da4d6_Traceguids,
      (char)a1,
      (char)v2,
      v11);
  }
  return v11;
}

```

## disassembly

```asm
0x140061850  mov     r11, rsp
0x140061853  push    rdi
0x140061854  push    r14
0x140061856  sub     rsp, 88h
0x14006185d  mov     [r11+8], rbx
0x140061861  xor     eax, eax
0x140061863  mov     [r11+18h], rsi
0x140061867  mov     r14, rdx
0x14006186a  mov     [r11-28h], r15
0x14006186e  mov     rdi, rcx
0x140061871  mov     [r11-58h], rax
0x140061875  mov     [r11-50h], rax
0x140061879  lea     rax, WPP_RECORDER_INITIALIZED
0x140061880  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140061887  lea     rcx, WPP_3d61bbabecaa38aa84130e7e4a2da4d6_Traceguids
0x14006188e  jz      short loc_1400618BA
0x140061890  mov     [r11-68h], rdx
0x140061894  mov     r9d, 0Eh; int
0x14006189a  mov     [r11-70h], rdi
0x14006189e  mov     r8d, 16h; int
0x1400618a4  mov     [r11-78h], rcx
0x1400618a8  mov     dl, 4; int
0x1400618aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400618b1  mov     rcx, [rcx+40h]; int
0x1400618b5  call    WPP_RECORDER_SF_qq
0x1400618ba  cmp     word ptr [rdi+8], 0
0x1400618bf  lea     rbx, [rdi+8]
0x1400618c3  mov     [rsp+98h+var_18], r12
0x1400618cb  lea     r12, [rbx+2]
0x1400618cf  mov     [rsp+98h+var_20], r13
0x1400618d4  jz      loc_1400619B8
0x1400618da  mov     rdx, r12; SourceString
0x1400618dd  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1400618e2  call    cs:__imp_RtlInitUnicodeString
0x1400618e9  nop     dword ptr [rax+rax+00h]
0x1400618ee  mov     rdx, [r14+0F10h]; String2
0x1400618f5  lea     rcx, [rsp+98h+DestinationString]; String1
0x1400618fa  mov     r8b, 1; CaseInSensitive
0x1400618fd  call    cs:__imp_RtlCompareUnicodeString
0x140061904  nop     dword ptr [rax+rax+00h]
0x140061909  test    eax, eax
0x14006190b  setnz   r13b
0x14006190f  mov     dl, 2
0x140061911  mov     [rsp+98h+arg_8], rbp
0x140061919  mov     cl, 1Eh
0x14006191b  call    NdisAllocateRefCount
0x140061920  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140061927  mov     rsi, rax
0x14006192a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140061931  nop     dword ptr [rax+rax+00h]
0x140061936  cmp     byte ptr [rdi+573h], 0
0x14006193d  movzx   r15d, al
0x140061941  jz      short loc_1400619C0
0x140061943  movzx   edx, al; NewIrql
0x140061946  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14006194d  mov     ebp, 0C0000001h
0x140061952  call    cs:__imp_KeReleaseSpinLock
0x140061959  nop     dword ptr [rax+rax+00h]
0x14006195e  mov     dl, 0FFh
0x140061960  mov     rcx, rsi; BugCheckParameter3
0x140061963  call    NdisDereferenceWithTag
0x140061968  mov     rcx, rsi; BugCheckParameter3
0x14006196b  call    NdisFreeRefCount
0x140061970  mov     r15, [rsp+98h+var_28]
0x140061975  lea     rax, WPP_RECORDER_INITIALIZED
0x14006197c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140061983  mov     r13, [rsp+98h+var_20]
0x140061988  mov     r12, [rsp+98h+var_18]
0x140061990  mov     rsi, [rsp+98h+arg_10]
0x140061998  mov     rbx, [rsp+98h+arg_0]
0x1400619a0  jnz     short loc_1400619FB
0x1400619a2  mov     eax, ebp
0x1400619a4  mov     rbp, [rsp+98h+arg_8]
0x1400619ac  add     rsp, 88h
0x1400619b3  pop     r14
0x1400619b5  pop     rdi
0x1400619b6  retn
0x1400619b8  mov     r13b, 1
0x1400619bb  jmp     loc_14006190F
0x1400619c0  xor     ebp, ebp
0x1400619c2  test    r13b, r13b
0x1400619c5  jz      loc_1400ED310
0x1400619cb  xor     edx, edx; Val
0x1400619cd  mov     r8d, 204h; Size
0x1400619d3  mov     rcx, rbx; void *
0x1400619d6  call    memset
0x1400619db  mov     rax, [r14+0F10h]
0x1400619e2  movzx   ecx, word ptr [rax]
0x1400619e5  mov     eax, 200h
0x1400619ea  cmp     cx, ax
0x1400619ed  jbe     loc_1400ED2EE
0x1400619f3  mov     [rbx], ax
0x1400619f6  jmp     loc_1400ED2F9
0x1400619fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140061a02  lea     rax, WPP_3d61bbabecaa38aa84130e7e4a2da4d6_Traceguids
0x140061a09  mov     dword ptr [rsp+98h+var_60], ebp; char
0x140061a0d  mov     r9d, 0Fh; int
0x140061a13  mov     qword ptr [rsp+98h+var_68], r14; char
0x140061a18  mov     r8d, 16h; int
0x140061a1e  mov     qword ptr [rsp+98h+var_70], rdi; char
0x140061a23  mov     dl, 4; int
0x140061a25  mov     rcx, [rcx+40h]; int
0x140061a29  mov     [rsp+98h+var_78], rax; struct _GUID *
0x140061a2e  call    WPP_RECORDER_SF_qqL
0x140061a33  jmp     loc_1400619A2
0x1400ed2ee  mov     [rbx], cx
0x1400ed2f1  test    cx, cx
0x1400ed2f4  jz      short loc_1400ED310
0x1400ed2f6  movzx   eax, cx
0x1400ed2f9  mov     rdx, [r14+0F10h]
0x1400ed300  mov     rcx, r12; void *
0x1400ed303  movzx   r8d, ax; Size
0x1400ed307  mov     rdx, [rdx+8]; Src
0x1400ed30b  call    memmove
0x1400ed310  mov     eax, [r14+0FDCh]
0x1400ed317  lea     r12, [rdi+4A8h]
0x1400ed31e  mov     rcx, [rdi+598h]
0x1400ed325  mov     dl, 0Ch
0x1400ed327  mov     [r12], eax
0x1400ed32b  mov     qword ptr [rdi+458h], 2
0x1400ed336  call    NdisReferenceWithTag
0x1400ed33b  inc     dword ptr [rdi+518h]
0x1400ed341  lea     rcx, SpinLock; SpinLock
0x1400ed348  xor     eax, eax
0x1400ed34a  mov     [rdi+5ACh], ax
0x1400ed351  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400ed358  nop     dword ptr [rax+rax+00h]
0x1400ed35d  mov     byte ptr [rdi+573h], 1
0x1400ed364  lea     rcx, SpinLock; SpinLock
0x1400ed36b  mov     dword ptr [rdi+574h], 1
0x1400ed375  mov     [rdi+580h], r14
0x1400ed37c  mov     [rdi+5A0h], rsi
0x1400ed383  mov     [r14+0FC8h], rdi
0x1400ed38a  mov     byte ptr [r14+0FC0h], 1
0x1400ed392  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400ed399  nop     dword ptr [rax+rax+00h]
0x1400ed39e  mov     eax, [rdi+4]
0x1400ed3a1  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400ed3a8  mov     [r14+0FD8h], eax
0x1400ed3af  movzx   edx, r15b; NewIrql
0x1400ed3b3  mov     rax, [rdi+520h]
0x1400ed3ba  mov     [r14+0FB8h], rax
0x1400ed3c1  mov     eax, [rdi+458h]
0x1400ed3c7  mov     [r14+0FE0h], eax
0x1400ed3ce  mov     [r14+0FE4h], ebp
0x1400ed3d5  call    cs:__imp_KeReleaseSpinLock
0x1400ed3dc  nop     dword ptr [rax+rax+00h]
0x1400ed3e1  test    r13b, r13b
0x1400ed3e4  jz      short loc_1400ED433
0x1400ed3e6  mov     r9, rbx; unsigned __int8 *
0x1400ed3e9  lea     rcx, [rdi+520h]; unsigned __int8 *
0x1400ed3f0  mov     edx, 204h; unsigned int
0x1400ed3f5  mov     r8d, 208h; unsigned int
0x1400ed3fb  call    ?ndisIfUpdatePersistedInterfaceInfo@@YAHPEAEKK0@Z; ndisIfUpdatePersistedInterfaceInfo(uchar *,ulong,ulong,uchar *)
0x1400ed400  mov     r9d, 1
0x1400ed406  mov     [rsp+98h+var_48], 2
0x1400ed40f  lea     r8, [rsp+98h+var_48]
0x1400ed414  mov     [rsp+98h+var_40], rbx
0x1400ed419  xor     edx, edx
0x1400ed41b  mov     [rsp+98h+var_38], 204h
0x1400ed423  mov     rcx, rdi
0x1400ed426  mov     [rsp+98h+var_34], 4
0x1400ed42e  call    ?ndisNsiNotifyClientInterfaceChange@@YAXPEAU_NDIS_IF_BLOCK@@W4_NSI_NOTIFICATION@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NDIS_NSI_OBJECT_INDEX@@@Z; ndisNsiNotifyClientInterfaceChange(_NDIS_IF_BLOCK *,_NSI_NOTIFICATION,_NSI_SINGLE_PARAM_DESC *,_NDIS_NSI_OBJECT_INDEX)
0x1400ed433  xor     r9d, r9d
0x1400ed436  mov     [rsp+98h+var_48], rbp
0x1400ed43b  lea     r8, [rsp+98h+var_48]
0x1400ed440  mov     [rsp+98h+var_40], r12
0x1400ed445  xor     edx, edx
0x1400ed447  mov     [rsp+98h+var_38], 4
0x1400ed44f  mov     rcx, rdi
0x1400ed452  mov     [rsp+98h+var_34], 10h
0x1400ed45a  call    ?ndisNsiNotifyClientInterfaceChange@@YAXPEAU_NDIS_IF_BLOCK@@W4_NSI_NOTIFICATION@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NDIS_NSI_OBJECT_INDEX@@@Z; ndisNsiNotifyClientInterfaceChange(_NDIS_IF_BLOCK *,_NSI_NOTIFICATION,_NSI_SINGLE_PARAM_DESC *,_NDIS_NSI_OBJECT_INDEX)
0x1400ed45f  mov     rcx, r14; struct _NDIS_MINIPORT_BLOCK *
0x1400ed462  call    ?ndisNsiSyncMiniportOperStatusNotification@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisNsiSyncMiniportOperStatusNotification(_NDIS_MINIPORT_BLOCK *)
0x1400ed467  nop
0x1400ed468  jmp     loc_140061970
```
