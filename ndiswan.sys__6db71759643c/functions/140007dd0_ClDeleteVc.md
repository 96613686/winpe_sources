# ClDeleteVc

- ea: `0x140007dd0`
- end: `0x140007fa0`
- name: `ClDeleteVc`
- size: `464`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140003060`
- `0x14000550c`
- `0x140006080`
- `0x140007dd0`
- `0x1400084d8`
- `0x1400087f0`
- `0x14000a290`
- `0x14000a648`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140007f1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f7e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007ef0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007f59`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007ef0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007f59`

## pseudocode

```c
__int64 __fastcall ClDeleteVc(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  int v5; // ebp
  KSPIN_LOCK *v7; // rbp
  KIRQL v8; // al
  KSPIN_LOCK v9; // rsi
  bool v10; // zf
  KIRQL v11; // al
  PVOID Entry; // [rsp+48h] [rbp+10h] BYREF

  Entry = 0;
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v4 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v4 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline(a1, a2, a3);
  if ( v4 )
  {
    v5 = ValidateLink(a1, 0, &Entry);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, a1);
      }
      return (unsigned int)v5;
    }
    goto LABEL_17;
  }
  if ( (unsigned __int8)IsLinkValid(a1, 0, &Entry) )
  {
LABEL_17:
    v7 = (KSPIN_LOCK *)Entry;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, Entry);
    }
    v8 = KeAcquireSpinLockRaiseToDpc(v7 + 92);
    *((_BYTE *)v7 + 744) = v8;
    v9 = v7[11];
    v10 = *((_DWORD *)v7 + 7) == 2;
    *((_DWORD *)v7 + 7) -= 2;
    if ( v10 )
      DoDerefLinkCBWork(v7);
    else
      KeReleaseSpinLock(v7 + 92, v8);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
    }
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 88));
    v10 = (*(_DWORD *)(v9 + 20))-- == 1;
    *(_BYTE *)(v9 + 96) = v11;
    if ( v10 )
      DoDerefClAfSapCBWork(v9);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 88), v11);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, a1);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x140007dd0  mov     [rsp+arg_0], rbx
0x140007dd5  mov     [rsp+arg_10], rbp
0x140007dda  push    rsi
0x140007ddb  push    rdi
0x140007ddc  push    r14
0x140007dde  sub     rsp, 20h
0x140007de2  mov     rsi, rcx
0x140007de5  mov     [rsp+38h+Entry], 0
0x140007dee  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x140007df4  test    al, 10h
0x140007df6  jz      short loc_140007DFD
0x140007df8  and     eax, 1
0x140007dfb  jmp     short loc_140007E02
0x140007dfd  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x140007e02  xor     edx, edx
0x140007e04  lea     r8, [rsp+38h+Entry]
0x140007e09  mov     rcx, rsi
0x140007e0c  test    eax, eax
0x140007e0e  jz      short loc_140007E5E
0x140007e10  call    ValidateLink
0x140007e15  mov     ebp, eax
0x140007e17  test    eax, eax
0x140007e19  jns     loc_140007EA9
0x140007e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e26  lea     rdi, WPP_GLOBAL_Control
0x140007e2d  cmp     rcx, rdi
0x140007e30  jz      short loc_140007E57
0x140007e32  bt      dword ptr [rcx+2Ch], 0Fh
0x140007e37  jnb     short loc_140007E57
0x140007e39  cmp     byte ptr [rcx+29h], 3
0x140007e3d  jb      short loc_140007E57
0x140007e3f  mov     rcx, [rcx+18h]
0x140007e43  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140007e4a  mov     edx, 0Ch
0x140007e4f  mov     r9, rsi
0x140007e52  call    WPP_SF_q
0x140007e57  mov     eax, ebp
0x140007e59  jmp     loc_140007F8C
0x140007e5e  call    IsLinkValid
0x140007e63  test    al, al
0x140007e65  jnz     short loc_140007EA9
0x140007e67  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e6e  lea     rdi, WPP_GLOBAL_Control
0x140007e75  cmp     rcx, rdi
0x140007e78  jz      short loc_140007E9F
0x140007e7a  bt      dword ptr [rcx+2Ch], 0Fh
0x140007e7f  jnb     short loc_140007E9F
0x140007e81  cmp     byte ptr [rcx+29h], 3
0x140007e85  jb      short loc_140007E9F
0x140007e87  mov     rcx, [rcx+18h]
0x140007e8b  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140007e92  mov     edx, 0Dh
0x140007e97  mov     r9, rsi
0x140007e9a  call    WPP_SF_q
0x140007e9f  mov     eax, 0C0000001h
0x140007ea4  jmp     loc_140007F8C
0x140007ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x140007eb0  lea     rdi, WPP_GLOBAL_Control
0x140007eb7  mov     rbp, [rsp+38h+Entry]
0x140007ebc  cmp     rcx, rdi
0x140007ebf  jz      short loc_140007EE6
0x140007ec1  bt      dword ptr [rcx+2Ch], 0Fh
0x140007ec6  jnb     short loc_140007EE6
0x140007ec8  cmp     byte ptr [rcx+29h], 5
0x140007ecc  jb      short loc_140007EE6
0x140007ece  mov     rcx, [rcx+18h]
0x140007ed2  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140007ed9  mov     edx, 0Eh
0x140007ede  mov     r9, rbp
0x140007ee1  call    WPP_SF_q
0x140007ee6  lea     r14, [rbp+2E0h]
0x140007eed  mov     rcx, r14; SpinLock
0x140007ef0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007ef7  nop     dword ptr [rax+rax+00h]
0x140007efc  mov     [rbp+2E8h], al
0x140007f02  mov     rsi, [rbp+58h]
0x140007f06  add     dword ptr [rbp+1Ch], 0FFFFFFFEh
0x140007f0a  jnz     short loc_140007F16
0x140007f0c  mov     rcx, rbp; Entry
0x140007f0f  call    DoDerefLinkCBWork
0x140007f14  jmp     short loc_140007F27
0x140007f16  mov     dl, al; NewIrql
0x140007f18  mov     rcx, r14; SpinLock
0x140007f1b  call    cs:__imp_KeReleaseSpinLock
0x140007f22  nop     dword ptr [rax+rax+00h]
0x140007f27  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f2e  cmp     rcx, rdi
0x140007f31  jz      short loc_140007F55
0x140007f33  bt      dword ptr [rcx+2Ch], 0Fh
0x140007f38  jnb     short loc_140007F55
0x140007f3a  cmp     byte ptr [rcx+29h], 5
0x140007f3e  jb      short loc_140007F55
0x140007f40  mov     rcx, [rcx+18h]
0x140007f44  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140007f4b  mov     edx, 0Fh
0x140007f50  call    WPP_SF_
0x140007f55  lea     rcx, [rsi+58h]; SpinLock
0x140007f59  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007f60  nop     dword ptr [rax+rax+00h]
0x140007f65  add     dword ptr [rsi+14h], 0FFFFFFFFh
0x140007f69  mov     [rsi+60h], al
0x140007f6c  jnz     short loc_140007F78
0x140007f6e  mov     rcx, rsi
0x140007f71  call    DoDerefClAfSapCBWork
0x140007f76  jmp     short loc_140007F8A
0x140007f78  mov     dl, al; NewIrql
0x140007f7a  lea     rcx, [rsi+58h]; SpinLock
0x140007f7e  call    cs:__imp_KeReleaseSpinLock
0x140007f85  nop     dword ptr [rax+rax+00h]
0x140007f8a  xor     eax, eax
0x140007f8c  mov     rbx, [rsp+38h+arg_0]
0x140007f91  mov     rbp, [rsp+38h+arg_10]
0x140007f96  add     rsp, 20h
0x140007f9a  pop     r14
0x140007f9c  pop     rdi
0x140007f9d  pop     rsi
0x140007f9e  retn
```
