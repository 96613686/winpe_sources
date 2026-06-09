# DeactivateRoute

- ea: `0x140027a50`
- end: `0x140027d91`
- name: `DeactivateRoute`
- size: `833`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400035f0`
- `0x140003870`
- `0x140005494`
- `0x1400084d8`
- `0x14000899c`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000a5f4`
- `0x14000a68c`
- `0x14000b818`
- `0x140027a50`
- `0x14002c16c`
- `0x14002c200`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140027cdd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140027cdd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027c63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027cb7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027d6b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027c63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027cb7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027d6b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027bcc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027c8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027cec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027bcc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027c8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027cec`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140027c7b`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140027c7b`

## pseudocode

```c
__int64 __fastcall DeactivateRoute(__int64 *a1, unsigned int a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  _DWORD *v7; // rbx
  int v8; // esi
  int v9; // eax
  __int64 v10; // rcx
  char *v11; // rbx
  KSPIN_LOCK *v12; // rbp
  char *i; // rdi
  int v14; // eax
  volatile __int32 **v15; // r15
  volatile __int32 *v16; // r14
  __int64 v17; // rax
  PVOID Entry; // [rsp+60h] [rbp+8h] BYREF

  Entry = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  v7 = a5;
  *a5 = 0;
  if ( a2 < 0x10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a2, 16);
    }
    *v7 = 16;
    return (unsigned int)-1073741820;
  }
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v9 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v9 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline();
  v10 = *a1;
  if ( v9 )
  {
    v8 = ValidateBundle(v10, 0, &Entry);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          101,
          WPP_5659416b879e33cc7e241cd80588418e_Traceguids,
          *a1,
          *((unsigned __int16 *)a1 + 4));
      }
      goto LABEL_26;
    }
LABEL_27:
    v11 = (char *)Entry;
    v12 = (KSPIN_LOCK *)((char *)Entry + 1768);
    v11[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 221);
    for ( i = (char *)*((_QWORD *)v11 + 35); i != v11 + 280; i = *(char **)i )
    {
      if ( *((_WORD *)i + 106) == *((_WORD *)a1 + 4) )
      {
        if ( *((_DWORD *)i + 5) != 1 )
        {
          v14 = ~*((_DWORD *)i + 27);
          *((_DWORD *)i + 5) = 1;
          *((_DWORD *)v11 + 78) &= v14;
          FlushProtocolPacketQueue(i);
          v15 = (volatile __int32 **)(i + 72);
          while ( 1 )
          {
            v16 = *v15;
            if ( *v15 == (volatile __int32 *)v15 )
              break;
            if ( *((volatile __int32 ***)v16 + 1) != v15
              || (v17 = *(_QWORD *)v16, *(volatile __int32 **)(*(_QWORD *)v16 + 8LL) != v16) )
            {
              __fastfail(3u);
            }
            *v15 = (volatile __int32 *)v17;
            *(_QWORD *)(v17 + 8) = v15;
            if ( *((_DWORD *)v16 + 5) == 1 )
            {
              _InterlockedExchange(v16 + 5, 2);
              KeReleaseSpinLock(v12, v11[1776]);
              NdisCmDispatchIncomingCloseCall(0, *((NDIS_HANDLE *)v16 + 5), 0, 0);
              v11[1776] = KeAcquireSpinLockRaiseToDpc(v12);
            }
          }
          DereferenceRefCount(i + 24);
          KeReleaseSpinLock(v12, v11[1776]);
          KeWaitForSingleObject(i + 304, UserRequest, 0, 0, 0);
          v11[1776] = KeAcquireSpinLockRaiseToDpc(v12);
          DoLineDownToProtocol(i);
          NdisWanFreeProtocolCB((PVOID *)i);
        }
        goto LABEL_45;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        103,
        WPP_5659416b879e33cc7e241cd80588418e_Traceguids,
        *((unsigned __int16 *)a1 + 4));
    }
    v8 = 606;
    goto LABEL_45;
  }
  v8 = 0;
  if ( (unsigned __int8)IsBundleValid(v10, 0, &Entry) )
    goto LABEL_27;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      102,
      WPP_5659416b879e33cc7e241cd80588418e_Traceguids,
      *a1,
      *((unsigned __int16 *)a1 + 4));
  }
  v8 = 601;
LABEL_26:
  v11 = (char *)Entry;
LABEL_45:
  if ( v11 )
  {
    if ( (*((_DWORD *)v11 + 6))-- == 1 )
      DoDerefBundleCBWork(v11);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v11 + 221, v11[1776]);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140027a50  mov     [rsp+arg_10], rbx
0x140027a55  mov     [rsp+arg_18], rbp
0x140027a5a  push    rsi
0x140027a5b  push    rdi
0x140027a5c  push    r13
0x140027a5e  push    r14
0x140027a60  push    r15
0x140027a62  sub     rsp, 30h
0x140027a66  mov     edi, edx
0x140027a68  mov     [rsp+58h+Entry], 0
0x140027a71  mov     r14, rcx
0x140027a74  mov     rcx, cs:WPP_GLOBAL_Control
0x140027a7b  lea     r13, WPP_GLOBAL_Control
0x140027a82  lea     rbp, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140027a89  mov     r15b, 20h ; ' '
0x140027a8c  cmp     rcx, r13
0x140027a8f  jz      short loc_140027AB0
0x140027a91  mov     eax, [rcx+2Ch]
0x140027a94  test    r15b, al
0x140027a97  jz      short loc_140027AB0
0x140027a99  cmp     byte ptr [rcx+29h], 5
0x140027a9d  jb      short loc_140027AB0
0x140027a9f  mov     rcx, [rcx+18h]
0x140027aa3  mov     edx, 63h ; 'c'
0x140027aa8  mov     r8, rbp
0x140027aab  call    WPP_SF_
0x140027ab0  mov     rbx, [rsp+58h+arg_20]
0x140027ab8  mov     esi, 10h
0x140027abd  mov     dword ptr [rbx], 0
0x140027ac3  cmp     edi, esi
0x140027ac5  jnb     short loc_140027B03
0x140027ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x140027ace  cmp     rcx, r13
0x140027ad1  jz      short loc_140027AF7
0x140027ad3  mov     eax, [rcx+2Ch]
0x140027ad6  test    r15b, al
0x140027ad9  jz      short loc_140027AF7
0x140027adb  cmp     byte ptr [rcx+29h], 3
0x140027adf  jb      short loc_140027AF7
0x140027ae1  mov     rcx, [rcx+18h]
0x140027ae5  lea     edx, [rsi+54h]
0x140027ae8  mov     r9d, edi
0x140027aeb  mov     dword ptr [rsp+58h+Timeout], esi
0x140027aef  mov     r8, rbp
0x140027af2  call    WPP_SF_dd
0x140027af7  mov     [rbx], esi
0x140027af9  mov     esi, 0C0000004h
0x140027afe  jmp     loc_140027D77
0x140027b03  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x140027b09  test    sil, al
0x140027b0c  jz      short loc_140027B13
0x140027b0e  and     eax, 1
0x140027b11  jmp     short loc_140027B18
0x140027b13  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x140027b18  mov     rcx, [r14]
0x140027b1b  lea     r8, [rsp+58h+Entry]
0x140027b20  xor     edx, edx
0x140027b22  test    eax, eax
0x140027b24  jnz     short loc_140027B71
0x140027b26  xor     esi, esi
0x140027b28  call    IsBundleValid
0x140027b2d  test    al, al
0x140027b2f  jnz     loc_140027BBD
0x140027b35  mov     rcx, cs:WPP_GLOBAL_Control
0x140027b3c  cmp     rcx, r13
0x140027b3f  jz      short loc_140027B6A
0x140027b41  mov     eax, [rcx+2Ch]
0x140027b44  test    r15b, al
0x140027b47  jz      short loc_140027B6A
0x140027b49  cmp     byte ptr [rcx+29h], 3
0x140027b4d  jb      short loc_140027B6A
0x140027b4f  movzx   eax, word ptr [r14+8]
0x140027b54  lea     edx, [rsi+66h]
0x140027b57  mov     r9, [r14]
0x140027b5a  mov     r8, rbp
0x140027b5d  mov     rcx, [rcx+18h]
0x140027b61  mov     dword ptr [rsp+58h+Timeout], eax
0x140027b65  call    WPP_SF_qD
0x140027b6a  mov     esi, 259h
0x140027b6f  jmp     short loc_140027BB3
0x140027b71  call    ValidateBundle
0x140027b76  mov     esi, eax
0x140027b78  test    eax, eax
0x140027b7a  jns     short loc_140027BBD
0x140027b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140027b83  cmp     rcx, r13
0x140027b86  jz      short loc_140027BB3
0x140027b88  mov     edx, [rcx+2Ch]
0x140027b8b  test    r15b, dl
0x140027b8e  jz      short loc_140027BB3
0x140027b90  cmp     byte ptr [rcx+29h], 3
0x140027b94  jb      short loc_140027BB3
0x140027b96  movzx   eax, word ptr [r14+8]
0x140027b9b  mov     edx, 65h ; 'e'
0x140027ba0  mov     r9, [r14]
0x140027ba3  mov     r8, rbp
0x140027ba6  mov     rcx, [rcx+18h]
0x140027baa  mov     dword ptr [rsp+58h+Timeout], eax
0x140027bae  call    WPP_SF_qD
0x140027bb3  mov     rbx, [rsp+58h+Entry]
0x140027bb8  jmp     loc_140027D49
0x140027bbd  mov     rbx, [rsp+58h+Entry]
0x140027bc2  lea     rbp, [rbx+6E8h]
0x140027bc9  mov     rcx, rbp; SpinLock
0x140027bcc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140027bd3  nop     dword ptr [rax+rax+00h]
0x140027bd8  lea     rcx, [rbx+118h]
0x140027bdf  mov     [rbx+6F0h], al
0x140027be5  mov     rdi, [rcx]
0x140027be8  cmp     rdi, rcx
0x140027beb  jz      loc_140027D10
0x140027bf1  movzx   eax, word ptr [r14+8]
0x140027bf6  cmp     [rdi+0D4h], ax
0x140027bfd  jz      short loc_140027C04
0x140027bff  mov     rdi, [rdi]
0x140027c02  jmp     short loc_140027BE8
0x140027c04  cmp     dword ptr [rdi+14h], 1
0x140027c08  jz      loc_140027D49
0x140027c0e  mov     eax, [rdi+6Ch]
0x140027c11  mov     rcx, rdi
0x140027c14  not     eax
0x140027c16  mov     dword ptr [rdi+14h], 1
0x140027c1d  and     [rbx+138h], eax
0x140027c23  call    FlushProtocolPacketQueue
0x140027c28  lea     r15, [rdi+48h]
0x140027c2c  mov     r14, [r15]
0x140027c2f  cmp     r14, r15
0x140027c32  jz      short loc_140027CA5
0x140027c34  cmp     [r14+8], r15
0x140027c38  jnz     short loc_140027C9E
0x140027c3a  mov     rax, [r14]
0x140027c3d  cmp     [rax+8], r14
0x140027c41  jnz     short loc_140027C9E
0x140027c43  mov     [r15], rax
0x140027c46  mov     [rax+8], r15
0x140027c4a  cmp     dword ptr [r14+14h], 1
0x140027c4f  jnz     short loc_140027C2C
0x140027c51  mov     eax, 2
0x140027c56  mov     rcx, rbp; SpinLock
0x140027c59  xchg    eax, [r14+14h]
0x140027c5d  mov     dl, [rbx+6F0h]; NewIrql
0x140027c63  call    cs:__imp_KeReleaseSpinLock
0x140027c6a  nop     dword ptr [rax+rax+00h]
0x140027c6f  mov     rdx, [r14+28h]; NdisVcHandle
0x140027c73  xor     r9d, r9d; Size
0x140027c76  xor     r8d, r8d; Buffer
0x140027c79  xor     ecx, ecx; CloseStatus
0x140027c7b  call    cs:__imp_NdisCmDispatchIncomingCloseCall
0x140027c82  nop     dword ptr [rax+rax+00h]
0x140027c87  mov     rcx, rbp; SpinLock
0x140027c8a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140027c91  nop     dword ptr [rax+rax+00h]
0x140027c96  mov     [rbx+6F0h], al
0x140027c9c  jmp     short loc_140027C2C
0x140027c9e  mov     ecx, 3
0x140027ca3  int     29h; Win8: RtlFailFast(ecx)
0x140027ca5  lea     rcx, [rdi+18h]
0x140027ca9  call    DereferenceRefCount
0x140027cae  mov     dl, [rbx+6F0h]; NewIrql
0x140027cb4  mov     rcx, rbp; SpinLock
0x140027cb7  call    cs:__imp_KeReleaseSpinLock
0x140027cbe  nop     dword ptr [rax+rax+00h]
0x140027cc3  xor     r9d, r9d; Alertable
0x140027cc6  mov     [rsp+58h+Timeout], 0; Timeout
0x140027ccf  lea     rcx, [rdi+130h]; Object
0x140027cd6  xor     r8d, r8d; WaitMode
0x140027cd9  lea     edx, [r9+6]; WaitReason
0x140027cdd  call    cs:__imp_KeWaitForSingleObject
0x140027ce4  nop     dword ptr [rax+rax+00h]
0x140027ce9  mov     rcx, rbp; SpinLock
0x140027cec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140027cf3  nop     dword ptr [rax+rax+00h]
0x140027cf8  mov     rcx, rdi
0x140027cfb  mov     [rbx+6F0h], al
0x140027d01  call    DoLineDownToProtocol
0x140027d06  mov     rcx, rdi; Entry
0x140027d09  call    NdisWanFreeProtocolCB
0x140027d0e  jmp     short loc_140027D49
0x140027d10  mov     rcx, cs:WPP_GLOBAL_Control
0x140027d17  cmp     rcx, r13
0x140027d1a  jz      short loc_140027D44
0x140027d1c  mov     eax, [rcx+2Ch]
0x140027d1f  test    r15b, al
0x140027d22  jz      short loc_140027D44
0x140027d24  cmp     byte ptr [rcx+29h], 3
0x140027d28  jb      short loc_140027D44
0x140027d2a  movzx   r9d, word ptr [r14+8]
0x140027d2f  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140027d36  mov     rcx, [rcx+18h]
0x140027d3a  mov     edx, 67h ; 'g'
0x140027d3f  call    WPP_SF_d
0x140027d44  mov     esi, 25Eh
0x140027d49  test    rbx, rbx
0x140027d4c  jz      short loc_140027D77
0x140027d4e  add     dword ptr [rbx+18h], 0FFFFFFFFh
0x140027d52  jnz     short loc_140027D5E
0x140027d54  mov     rcx, rbx; Entry
0x140027d57  call    DoDerefBundleCBWork
0x140027d5c  jmp     short loc_140027D77
0x140027d5e  mov     dl, [rbx+6F0h]; NewIrql
0x140027d64  lea     rcx, [rbx+6E8h]; SpinLock
0x140027d6b  call    cs:__imp_KeReleaseSpinLock
0x140027d72  nop     dword ptr [rax+rax+00h]
0x140027d77  mov     rbx, [rsp+58h+arg_10]
0x140027d7c  mov     eax, esi
0x140027d7e  mov     rbp, [rsp+58h+arg_18]
0x140027d83  add     rsp, 30h
0x140027d87  pop     r15
0x140027d89  pop     r14
0x140027d8b  pop     r13
0x140027d8d  pop     rdi
0x140027d8e  pop     rsi
0x140027d8f  retn
```
