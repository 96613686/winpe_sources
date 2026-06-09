# ndisIfUpdateInterfaceOnAddDevice(_NDIS_IF_BLOCK *,_NDIS_MINIPORT_BLOCK *)

- ea: `0x140009070`
- end: `0x140009258`
- name: `?ndisIfUpdateInterfaceOnAddDevice@@YAHPEAU_NDIS_IF_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(struct _NDIS_IF_BLOCK *, struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140185810`

## callees

- `0x140008fa0`
- `0x140009070`
- `0x14000a8e0`
- `0x14000dd10`
- `0x1400100f0`
- `0x140014ca0`
- `0x140017220`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x14013e950`
- `0x14016a100`
- `0x14016a150`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140009102`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009102`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000911d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000911d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009172`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400eca3f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009172`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400eca3f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000914a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000914a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400ec9bb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400ec9bb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ec9fc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ec9fc`

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
0x140009070  mov     r11, rsp
0x140009073  push    rdi
0x140009074  push    r14
0x140009076  sub     rsp, 88h
0x14000907d  mov     [r11+8], rbx
0x140009081  xor     eax, eax
0x140009083  mov     [r11+18h], rsi
0x140009087  mov     r14, rdx
0x14000908a  mov     [r11-28h], r15
0x14000908e  mov     rdi, rcx
0x140009091  mov     [r11-58h], rax
0x140009095  mov     [r11-50h], rax
0x140009099  lea     rax, WPP_RECORDER_INITIALIZED
0x1400090a0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400090a7  lea     rcx, WPP_3d61bbabecaa38aa84130e7e4a2da4d6_Traceguids
0x1400090ae  jz      short loc_1400090DA
0x1400090b0  mov     [r11-68h], rdx
0x1400090b4  mov     r9d, 0Eh; int
0x1400090ba  mov     [r11-70h], rdi
0x1400090be  mov     r8d, 16h; int
0x1400090c4  mov     [r11-78h], rcx
0x1400090c8  mov     dl, 4; int
0x1400090ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400090d1  mov     rcx, [rcx+40h]; int
0x1400090d5  call    WPP_RECORDER_SF_qq
0x1400090da  cmp     word ptr [rdi+8], 0
0x1400090df  lea     rbx, [rdi+8]
0x1400090e3  mov     [rsp+98h+var_18], r12
0x1400090eb  lea     r12, [rbx+2]
0x1400090ef  mov     [rsp+98h+var_20], r13
0x1400090f4  jz      loc_1400091D8
0x1400090fa  mov     rdx, r12; SourceString
0x1400090fd  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140009102  call    cs:__imp_RtlInitUnicodeString
0x140009109  nop     dword ptr [rax+rax+00h]
0x14000910e  mov     rdx, [r14+0F10h]; String2
0x140009115  lea     rcx, [rsp+98h+DestinationString]; String1
0x14000911a  mov     r8b, 1; CaseInSensitive
0x14000911d  call    cs:__imp_RtlCompareUnicodeString
0x140009124  nop     dword ptr [rax+rax+00h]
0x140009129  test    eax, eax
0x14000912b  setnz   r13b
0x14000912f  mov     dl, 2
0x140009131  mov     [rsp+98h+arg_8], rbp
0x140009139  mov     cl, 1Eh
0x14000913b  call    NdisAllocateRefCount
0x140009140  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140009147  mov     rsi, rax
0x14000914a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009151  nop     dword ptr [rax+rax+00h]
0x140009156  cmp     byte ptr [rdi+573h], 0
0x14000915d  movzx   r15d, al
0x140009161  jz      short loc_1400091E0
0x140009163  movzx   edx, al; NewIrql
0x140009166  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14000916d  mov     ebp, 0C0000001h
0x140009172  call    cs:__imp_KeReleaseSpinLock
0x140009179  nop     dword ptr [rax+rax+00h]
0x14000917e  mov     dl, 0FFh
0x140009180  mov     rcx, rsi; BugCheckParameter3
0x140009183  call    NdisDereferenceWithTag
0x140009188  mov     rcx, rsi; BugCheckParameter3
0x14000918b  call    NdisFreeRefCount
0x140009190  mov     r15, [rsp+98h+var_28]
0x140009195  lea     rax, WPP_RECORDER_INITIALIZED
0x14000919c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400091a3  mov     r13, [rsp+98h+var_20]
0x1400091a8  mov     r12, [rsp+98h+var_18]
0x1400091b0  mov     rsi, [rsp+98h+arg_10]
0x1400091b8  mov     rbx, [rsp+98h+arg_0]
0x1400091c0  jnz     short loc_14000921B
0x1400091c2  mov     eax, ebp
0x1400091c4  mov     rbp, [rsp+98h+arg_8]
0x1400091cc  add     rsp, 88h
0x1400091d3  pop     r14
0x1400091d5  pop     rdi
0x1400091d6  retn
0x1400091d8  mov     r13b, 1
0x1400091db  jmp     loc_14000912F
0x1400091e0  xor     ebp, ebp
0x1400091e2  test    r13b, r13b
0x1400091e5  jz      loc_1400EC97A
0x1400091eb  xor     edx, edx; Val
0x1400091ed  mov     r8d, 204h; Size
0x1400091f3  mov     rcx, rbx; void *
0x1400091f6  call    memset
0x1400091fb  mov     rax, [r14+0F10h]
0x140009202  movzx   ecx, word ptr [rax]
0x140009205  mov     eax, 200h
0x14000920a  cmp     cx, ax
0x14000920d  jbe     loc_1400EC958
0x140009213  mov     [rbx], ax
0x140009216  jmp     loc_1400EC963
0x14000921b  mov     rcx, cs:WPP_GLOBAL_Control
0x140009222  lea     rax, WPP_3d61bbabecaa38aa84130e7e4a2da4d6_Traceguids
0x140009229  mov     dword ptr [rsp+98h+var_60], ebp; char
0x14000922d  mov     r9d, 0Fh; int
0x140009233  mov     qword ptr [rsp+98h+var_68], r14; char
0x140009238  mov     r8d, 16h; int
0x14000923e  mov     qword ptr [rsp+98h+var_70], rdi; char
0x140009243  mov     dl, 4; int
0x140009245  mov     rcx, [rcx+40h]; int
0x140009249  mov     [rsp+98h+var_78], rax; struct _GUID *
0x14000924e  call    WPP_RECORDER_SF_qqL
0x140009253  jmp     loc_1400091C2
0x1400ec958  mov     [rbx], cx
0x1400ec95b  test    cx, cx
0x1400ec95e  jz      short loc_1400EC97A
0x1400ec960  movzx   eax, cx
0x1400ec963  mov     rdx, [r14+0F10h]
0x1400ec96a  mov     rcx, r12; void *
0x1400ec96d  movzx   r8d, ax; Size
0x1400ec971  mov     rdx, [rdx+8]; Src
0x1400ec975  call    memmove
0x1400ec97a  mov     eax, [r14+0FDCh]
0x1400ec981  lea     r12, [rdi+4A8h]
0x1400ec988  mov     rcx, [rdi+598h]
0x1400ec98f  mov     dl, 0Ch
0x1400ec991  mov     [r12], eax
0x1400ec995  mov     qword ptr [rdi+458h], 2
0x1400ec9a0  call    NdisReferenceWithTag
0x1400ec9a5  inc     dword ptr [rdi+518h]
0x1400ec9ab  lea     rcx, SpinLock; SpinLock
0x1400ec9b2  xor     eax, eax
0x1400ec9b4  mov     [rdi+5ACh], ax
0x1400ec9bb  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400ec9c2  nop     dword ptr [rax+rax+00h]
0x1400ec9c7  mov     byte ptr [rdi+573h], 1
0x1400ec9ce  lea     rcx, SpinLock; SpinLock
0x1400ec9d5  mov     dword ptr [rdi+574h], 1
0x1400ec9df  mov     [rdi+580h], r14
0x1400ec9e6  mov     [rdi+5A0h], rsi
0x1400ec9ed  mov     [r14+0FC8h], rdi
0x1400ec9f4  mov     byte ptr [r14+0FC0h], 1
0x1400ec9fc  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400eca03  nop     dword ptr [rax+rax+00h]
0x1400eca08  mov     eax, [rdi+4]
0x1400eca0b  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400eca12  mov     [r14+0FD8h], eax
0x1400eca19  movzx   edx, r15b; NewIrql
0x1400eca1d  mov     rax, [rdi+520h]
0x1400eca24  mov     [r14+0FB8h], rax
0x1400eca2b  mov     eax, [rdi+458h]
0x1400eca31  mov     [r14+0FE0h], eax
0x1400eca38  mov     [r14+0FE4h], ebp
0x1400eca3f  call    cs:__imp_KeReleaseSpinLock
0x1400eca46  nop     dword ptr [rax+rax+00h]
0x1400eca4b  test    r13b, r13b
0x1400eca4e  jz      short loc_1400ECA9D
0x1400eca50  mov     r9, rbx; unsigned __int8 *
0x1400eca53  lea     rcx, [rdi+520h]; unsigned __int8 *
0x1400eca5a  mov     edx, 204h; unsigned int
0x1400eca5f  mov     r8d, 208h; unsigned int
0x1400eca65  call    ?ndisIfUpdatePersistedInterfaceInfo@@YAHPEAEKK0@Z; ndisIfUpdatePersistedInterfaceInfo(uchar *,ulong,ulong,uchar *)
0x1400eca6a  mov     r9d, 1
0x1400eca70  mov     [rsp+98h+var_48], 2
0x1400eca79  lea     r8, [rsp+98h+var_48]
0x1400eca7e  mov     [rsp+98h+var_40], rbx
0x1400eca83  xor     edx, edx
0x1400eca85  mov     [rsp+98h+var_38], 204h
0x1400eca8d  mov     rcx, rdi
0x1400eca90  mov     [rsp+98h+var_34], 4
0x1400eca98  call    ?ndisNsiNotifyClientInterfaceChange@@YAXPEAU_NDIS_IF_BLOCK@@W4_NSI_NOTIFICATION@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NDIS_NSI_OBJECT_INDEX@@@Z; ndisNsiNotifyClientInterfaceChange(_NDIS_IF_BLOCK *,_NSI_NOTIFICATION,_NSI_SINGLE_PARAM_DESC *,_NDIS_NSI_OBJECT_INDEX)
0x1400eca9d  xor     r9d, r9d
0x1400ecaa0  mov     [rsp+98h+var_48], rbp
0x1400ecaa5  lea     r8, [rsp+98h+var_48]
0x1400ecaaa  mov     [rsp+98h+var_40], r12
0x1400ecaaf  xor     edx, edx
0x1400ecab1  mov     [rsp+98h+var_38], 4
0x1400ecab9  mov     rcx, rdi
0x1400ecabc  mov     [rsp+98h+var_34], 10h
0x1400ecac4  call    ?ndisNsiNotifyClientInterfaceChange@@YAXPEAU_NDIS_IF_BLOCK@@W4_NSI_NOTIFICATION@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NDIS_NSI_OBJECT_INDEX@@@Z; ndisNsiNotifyClientInterfaceChange(_NDIS_IF_BLOCK *,_NSI_NOTIFICATION,_NSI_SINGLE_PARAM_DESC *,_NDIS_NSI_OBJECT_INDEX)
0x1400ecac9  mov     rcx, r14; struct _NDIS_MINIPORT_BLOCK *
0x1400ecacc  call    ?ndisNsiSyncMiniportOperStatusNotification@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisNsiSyncMiniportOperStatusNotification(_NDIS_MINIPORT_BLOCK *)
0x1400ecad1  nop
0x1400ecad2  jmp     loc_140009190
```
