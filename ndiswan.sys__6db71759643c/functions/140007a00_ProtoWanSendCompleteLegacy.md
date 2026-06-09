# ProtoWanSendCompleteLegacy

- ea: `0x140007a00`
- end: `0x140007be0`
- name: `ProtoWanSendCompleteLegacy`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010150`

## callees

- `0x140003060`
- `0x14000550c`
- `0x140007a00`
- `0x1400084d8`
- `0x1400087f0`
- `0x14000a290`
- `0x14000a648`
- `0x140030940`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140007b36`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140007b36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007b92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007b92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b4c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b6b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b4c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b6b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140007b21`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140007b21`

## pseudocode

```c
void __fastcall ProtoWanSendCompleteLegacy(__int64 a1, struct _SLIST_ENTRY *a2, NDIS_STATUS a3)
{
  __int64 Next; // rbp
  __int64 v6; // rbx
  int v7; // eax
  __int64 v8; // rcx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  KIRQL v12; // al
  bool v13; // zf
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v14 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_714410adb39534c9cec6a41078899c0f_Traceguids, a2);
  }
  Next = (__int64)a2[3].Next;
  v6 = *(_QWORD *)(Next + 40);
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v7 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v7 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline();
  v8 = *(_QWORD *)(v6 + 40);
  if ( v7 )
  {
    a3 = ValidateLink(v8, 0, &v14);
    if ( a3 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v10 = 24;
LABEL_14:
        WPP_SF_q(v9->AttachedDevice, v10, WPP_714410adb39534c9cec6a41078899c0f_Traceguids, v6);
        return;
      }
      return;
    }
LABEL_20:
    v11 = *(_QWORD *)(v6 + 72);
    if ( *(_DWORD *)(v11 + 188) )
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v11 + 336), a2);
    else
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v11 + 320), a2);
    *(_BYTE *)(v6 + 744) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 736));
    CompleteSendDesc(Next, a3);
    v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 736));
    v13 = (*(_DWORD *)(v6 + 28))-- == 1;
    *(_BYTE *)(v6 + 744) = v12;
    if ( v13 )
      DoDerefLinkCBWork((PVOID)v6);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 736), v12);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_714410adb39534c9cec6a41078899c0f_Traceguids);
    }
    return;
  }
  if ( (unsigned __int8)IsLinkValid(v8, 0, &v14) )
    goto LABEL_20;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    v10 = 25;
    goto LABEL_14;
  }
}

```

## disassembly

```asm
0x140007a00  mov     [rsp+arg_0], rbx
0x140007a05  mov     [rsp+arg_10], rbp
0x140007a0a  push    rsi
0x140007a0b  push    rdi
0x140007a0c  push    r14
0x140007a0e  sub     rsp, 20h
0x140007a12  mov     esi, r8d
0x140007a15  mov     [rsp+38h+arg_8], 0
0x140007a1e  mov     rdi, rdx
0x140007a21  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a28  lea     r14, WPP_GLOBAL_Control
0x140007a2f  cmp     rcx, r14
0x140007a32  jz      short loc_140007A59
0x140007a34  mov     eax, [rcx+2Ch]
0x140007a37  test    al, 8
0x140007a39  jz      short loc_140007A59
0x140007a3b  cmp     byte ptr [rcx+29h], 5
0x140007a3f  jb      short loc_140007A59
0x140007a41  mov     rcx, [rcx+18h]
0x140007a45  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x140007a4c  mov     edx, 17h
0x140007a51  mov     r9, rdi
0x140007a54  call    WPP_SF_q
0x140007a59  mov     rbp, [rdi+30h]
0x140007a5d  mov     rbx, [rbp+28h]
0x140007a61  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x140007a67  test    al, 10h
0x140007a69  jz      short loc_140007A70
0x140007a6b  and     eax, 1
0x140007a6e  jmp     short loc_140007A75
0x140007a70  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x140007a75  mov     rcx, [rbx+28h]
0x140007a79  lea     r8, [rsp+38h+arg_8]
0x140007a7e  xor     edx, edx
0x140007a80  test    eax, eax
0x140007a82  jz      short loc_140007AD3
0x140007a84  call    ValidateLink
0x140007a89  mov     esi, eax
0x140007a8b  test    eax, eax
0x140007a8d  jns     short loc_140007B0A
0x140007a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a96  cmp     rcx, r14
0x140007a99  jz      loc_140007BCC
0x140007a9f  test    dword ptr [rcx+2Ch], 8000h
0x140007aa6  jz      loc_140007BCC
0x140007aac  cmp     byte ptr [rcx+29h], 3
0x140007ab0  jb      loc_140007BCC
0x140007ab6  mov     edx, 18h
0x140007abb  mov     rcx, [rcx+18h]
0x140007abf  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x140007ac6  mov     r9, rbx
0x140007ac9  call    WPP_SF_q
0x140007ace  jmp     loc_140007BCC
0x140007ad3  call    IsLinkValid
0x140007ad8  test    al, al
0x140007ada  jnz     short loc_140007B0A
0x140007adc  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ae3  cmp     rcx, r14
0x140007ae6  jz      loc_140007BCC
0x140007aec  test    dword ptr [rcx+2Ch], 8000h
0x140007af3  jz      loc_140007BCC
0x140007af9  cmp     byte ptr [rcx+29h], 3
0x140007afd  jb      loc_140007BCC
0x140007b03  mov     edx, 19h
0x140007b08  jmp     short loc_140007ABB
0x140007b0a  mov     rcx, [rbx+48h]
0x140007b0e  mov     rdx, rdi; ListEntry
0x140007b11  cmp     dword ptr [rcx+0BCh], 0
0x140007b18  jnz     short loc_140007B2F
0x140007b1a  add     rcx, 140h; Lookaside
0x140007b21  call    cs:__imp_ExFreeToNPagedLookasideList
0x140007b28  nop     dword ptr [rax+rax+00h]
0x140007b2d  jmp     short loc_140007B42
0x140007b2f  add     rcx, 150h; ListHead
0x140007b36  call    cs:__imp_ExpInterlockedPushEntrySList
0x140007b3d  nop     dword ptr [rax+rax+00h]
0x140007b42  lea     rdi, [rbx+2E0h]
0x140007b49  mov     rcx, rdi; SpinLock
0x140007b4c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007b53  nop     dword ptr [rax+rax+00h]
0x140007b58  mov     edx, esi
0x140007b5a  mov     rcx, rbp
0x140007b5d  mov     [rbx+2E8h], al
0x140007b63  call    CompleteSendDesc
0x140007b68  mov     rcx, rdi; SpinLock
0x140007b6b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007b72  nop     dword ptr [rax+rax+00h]
0x140007b77  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x140007b7b  mov     [rbx+2E8h], al
0x140007b81  jnz     short loc_140007B8D
0x140007b83  mov     rcx, rbx; Entry
0x140007b86  call    DoDerefLinkCBWork
0x140007b8b  jmp     short loc_140007B9E
0x140007b8d  mov     dl, al; NewIrql
0x140007b8f  mov     rcx, rdi; SpinLock
0x140007b92  call    cs:__imp_KeReleaseSpinLock
0x140007b99  nop     dword ptr [rax+rax+00h]
0x140007b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ba5  cmp     rcx, r14
0x140007ba8  jz      short loc_140007BCC
0x140007baa  mov     eax, [rcx+2Ch]
0x140007bad  test    al, 8
0x140007baf  jz      short loc_140007BCC
0x140007bb1  cmp     byte ptr [rcx+29h], 5
0x140007bb5  jb      short loc_140007BCC
0x140007bb7  mov     rcx, [rcx+18h]
0x140007bbb  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x140007bc2  mov     edx, 1Ah
0x140007bc7  call    WPP_SF_
0x140007bcc  mov     rbx, [rsp+38h+arg_0]
0x140007bd1  mov     rbp, [rsp+38h+arg_10]
0x140007bd6  add     rsp, 20h
0x140007bda  pop     r14
0x140007bdc  pop     rdi
0x140007bdd  pop     rsi
0x140007bde  retn
```
