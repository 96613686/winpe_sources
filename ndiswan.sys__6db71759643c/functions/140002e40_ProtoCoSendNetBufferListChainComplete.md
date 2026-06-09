# ProtoCoSendNetBufferListChainComplete

- ea: `0x140002e40`
- end: `0x140003057`
- name: `ProtoCoSendNetBufferListChainComplete`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400305b0`

## callees

- `0x140002e40`
- `0x140003060`
- `0x1400035f0`
- `0x14000550c`
- `0x1400084d8`
- `0x1400087f0`
- `0x14000a290`
- `0x14000a648`
- `0x14000a744`
- `0x140030940`
- `0x140035960`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140002fb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003009`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002fb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003009`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f6e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002fe2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f6e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002fe2`

## pseudocode

```c
void __fastcall ProtoCoSendNetBufferListChainComplete(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v3; // r14
  PDEVICE_OBJECT v5; // rcx
  int v6; // eax
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rsi
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rbx
  KIRQL v13; // al
  PVOID Entry; // [rsp+68h] [rbp+20h] BYREF

  v3 = a2;
  Entry = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids, a1, a2);
  }
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v6 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v6 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline(v5, a2, a3);
  if ( v6 )
  {
    if ( (int)ValidateLink(a1, 0, &Entry) < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v8 = 39;
LABEL_14:
        WPP_SF_q(v7->AttachedDevice, v8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids, Entry);
        return;
      }
      return;
    }
LABEL_20:
    v9 = Entry;
    while ( v3 )
    {
      v10 = v3[2];
      v11 = v3;
      v3 = (_QWORD *)*v3;
      *v11 = 0;
      v12 = v10 + *(unsigned __int16 *)(v10 + 10);
      *((_BYTE *)v9 + 744) = KeAcquireSpinLockRaiseToDpc(v9 + 92);
      CompleteSendDesc(v12 + 16, 0);
      *((_BYTE *)v9 + 744) = KeAcquireSpinLockRaiseToDpc(v9 + 92);
      DerefVc(v9);
      KeReleaseSpinLock(v9 + 92, *((_BYTE *)v9 + 744));
      DereferenceRefCount(v9[9] + 32LL);
    }
    if ( v9 )
    {
      v13 = KeAcquireSpinLockRaiseToDpc(v9 + 92);
      *((_BYTE *)v9 + 744) = v13;
      if ( (*((_DWORD *)v9 + 7))-- == 1 )
        DoDerefLinkCBWork(v9);
      else
        KeReleaseSpinLock(v9 + 92, v13);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
    }
    return;
  }
  if ( (unsigned __int8)IsLinkValid(a1, 0, &Entry) )
    goto LABEL_20;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    v8 = 40;
    goto LABEL_14;
  }
}

```

## disassembly

```asm
0x140002e40  mov     r11, rsp
0x140002e43  mov     [r11+8], rbx
0x140002e47  mov     [r11+10h], rbp
0x140002e4b  push    rsi
0x140002e4c  push    rdi
0x140002e4d  push    r14
0x140002e4f  sub     rsp, 30h
0x140002e53  mov     r14, rdx
0x140002e56  mov     qword ptr [r11+20h], 0
0x140002e5e  mov     rbx, rcx
0x140002e61  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e68  lea     rbp, WPP_GLOBAL_Control
0x140002e6f  cmp     rcx, rbp
0x140002e72  jz      short loc_140002E9D
0x140002e74  mov     eax, [rcx+2Ch]
0x140002e77  test    al, 8
0x140002e79  jz      short loc_140002E9D
0x140002e7b  cmp     byte ptr [rcx+29h], 5
0x140002e7f  jb      short loc_140002E9D
0x140002e81  mov     rcx, [rcx+18h]
0x140002e85  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140002e8c  mov     edx, 26h ; '&'
0x140002e91  mov     [r11-28h], r14
0x140002e95  mov     r9, rbx
0x140002e98  call    WPP_SF_qq
0x140002e9d  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x140002ea3  test    al, 10h
0x140002ea5  jz      short loc_140002EAC
0x140002ea7  and     eax, 1
0x140002eaa  jmp     short loc_140002EB1
0x140002eac  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x140002eb1  xor     edx, edx
0x140002eb3  lea     r8, [rsp+48h+Entry]
0x140002eb8  mov     rcx, rbx
0x140002ebb  test    eax, eax
0x140002ebd  jz      short loc_140002F0E
0x140002ebf  call    ValidateLink
0x140002ec4  test    eax, eax
0x140002ec6  jns     short loc_140002F45
0x140002ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ecf  cmp     rcx, rbp
0x140002ed2  jz      loc_140003043
0x140002ed8  test    dword ptr [rcx+2Ch], 8000h
0x140002edf  jz      loc_140003043
0x140002ee5  cmp     byte ptr [rcx+29h], 3
0x140002ee9  jb      loc_140003043
0x140002eef  mov     edx, 27h ; '''
0x140002ef4  mov     r9, [rsp+48h+Entry]
0x140002ef9  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140002f00  mov     rcx, [rcx+18h]
0x140002f04  call    WPP_SF_q
0x140002f09  jmp     loc_140003043
0x140002f0e  call    IsLinkValid
0x140002f13  test    al, al
0x140002f15  jnz     short loc_140002F45
0x140002f17  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f1e  cmp     rcx, rbp
0x140002f21  jz      loc_140003043
0x140002f27  test    dword ptr [rcx+2Ch], 8000h
0x140002f2e  jz      loc_140003043
0x140002f34  cmp     byte ptr [rcx+29h], 3
0x140002f38  jb      loc_140003043
0x140002f3e  mov     edx, 28h ; '('
0x140002f43  jmp     short loc_140002EF4
0x140002f45  mov     rsi, [rsp+48h+Entry]
0x140002f4a  jmp     short loc_140002FCA
0x140002f4c  mov     rcx, [r14+10h]
0x140002f50  lea     rax, [r14]
0x140002f53  mov     r14, [r14]
0x140002f56  lea     rdi, [rsi+2E0h]
0x140002f5d  mov     qword ptr [rax], 0
0x140002f64  movzx   ebx, word ptr [rcx+0Ah]
0x140002f68  add     rbx, rcx
0x140002f6b  mov     rcx, rdi; SpinLock
0x140002f6e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002f75  nop     dword ptr [rax+rax+00h]
0x140002f7a  xor     edx, edx
0x140002f7c  lea     rcx, [rbx+10h]
0x140002f80  mov     [rsi+2E8h], al
0x140002f86  call    CompleteSendDesc
0x140002f8b  mov     rcx, rdi; SpinLock
0x140002f8e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002f95  nop     dword ptr [rax+rax+00h]
0x140002f9a  mov     rcx, rsi
0x140002f9d  mov     [rsi+2E8h], al
0x140002fa3  call    DerefVc
0x140002fa8  mov     dl, [rsi+2E8h]; NewIrql
0x140002fae  mov     rcx, rdi; SpinLock
0x140002fb1  call    cs:__imp_KeReleaseSpinLock
0x140002fb8  nop     dword ptr [rax+rax+00h]
0x140002fbd  mov     rcx, [rsi+48h]
0x140002fc1  add     rcx, 20h ; ' '
0x140002fc5  call    DereferenceRefCount
0x140002fca  test    r14, r14
0x140002fcd  jnz     loc_140002F4C
0x140002fd3  test    rsi, rsi
0x140002fd6  jz      short loc_140003015
0x140002fd8  lea     rbx, [rsi+2E0h]
0x140002fdf  mov     rcx, rbx; SpinLock
0x140002fe2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002fe9  nop     dword ptr [rax+rax+00h]
0x140002fee  mov     [rsi+2E8h], al
0x140002ff4  add     dword ptr [rsi+1Ch], 0FFFFFFFFh
0x140002ff8  jnz     short loc_140003004
0x140002ffa  mov     rcx, rsi; Entry
0x140002ffd  call    DoDerefLinkCBWork
0x140003002  jmp     short loc_140003015
0x140003004  mov     dl, al; NewIrql
0x140003006  mov     rcx, rbx; SpinLock
0x140003009  call    cs:__imp_KeReleaseSpinLock
0x140003010  nop     dword ptr [rax+rax+00h]
0x140003015  mov     rcx, cs:WPP_GLOBAL_Control
0x14000301c  cmp     rcx, rbp
0x14000301f  jz      short loc_140003043
0x140003021  mov     eax, [rcx+2Ch]
0x140003024  test    al, 8
0x140003026  jz      short loc_140003043
0x140003028  cmp     byte ptr [rcx+29h], 5
0x14000302c  jb      short loc_140003043
0x14000302e  mov     rcx, [rcx+18h]
0x140003032  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140003039  mov     edx, 29h ; ')'
0x14000303e  call    WPP_SF_
0x140003043  mov     rbx, [rsp+48h+arg_0]
0x140003048  mov     rbp, [rsp+48h+arg_8]
0x14000304d  add     rsp, 30h
0x140003051  pop     r14
0x140003053  pop     rdi
0x140003054  pop     rsi
0x140003055  retn
```
