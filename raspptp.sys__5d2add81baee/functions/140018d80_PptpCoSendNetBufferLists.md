# PptpCoSendNetBufferLists

- ea: `0x140018d80`
- end: `0x140019070`
- name: `PptpCoSendNetBufferLists`
- size: `752`
- prototype: `__int64 __fastcall(PVOID WorkItemContext, PNET_BUFFER_LIST NetBufferLists)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400020b0`
- `0x140003e38`
- `0x140007710`
- `0x140018d80`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140018dd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018e0f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018e85`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018f05`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018fa4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018fbc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018dd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018e0f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018e85`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018f05`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018fa4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018fbc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018d9d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018ded`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018e4a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018ea3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018d9d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018ded`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018e4a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018ea3`
- `NDIS!NdisQueueIoWorkItem` at `0x140018eeb`
- `NDIS!NdisQueueIoWorkItem` at `0x140018eeb`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x14001905f`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x14001905f`

## pseudocode

```c
void __fastcall PptpCoSendNetBufferLists(char *WorkItemContext, PNET_BUFFER_LIST NetBufferLists)
{
  __int64 v2; // rsi
  unsigned int v5; // ebp
  __int64 v6; // rdi
  KIRQL v7; // al
  bool v8; // zf
  KSPIN_LOCK *v9; // rcx
  PNET_BUFFER_LIST v10; // rbp
  PNET_BUFFER_LIST i; // r15
  SLIST_HEADER *FirstNetBuffer; // rax
  int j; // r12d
  KIRQL v14; // al
  KIRQL v15; // al
  char v16; // r12
  PNET_BUFFER_LIST k; // rax
  SLIST_HEADER *Alignment; // rcx
  unsigned int v19; // edx

  v2 = *((_QWORD *)WorkItemContext + 7);
  *(_BYTE *)(v2 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 8));
  v5 = MiniportCheckAdapterState(v2);
  if ( v5 )
  {
    v16 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_03516810ed2635a74cea1971954143d2_Traceguids, v5);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 8), *(_BYTE *)(v2 + 16));
    v6 = v2 + 192;
  }
  else
  {
    v6 = v2 + 192;
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 192));
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 8), *(_BYTE *)(v2 + 16));
    if ( *((_DWORD *)WorkItemContext + 12) == 1129337936 )
    {
      v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WorkItemContext + 12);
      v8 = *((_DWORD *)WorkItemContext + 28) == 9;
      v9 = (KSPIN_LOCK *)(WorkItemContext + 96);
      WorkItemContext[104] = v7;
      if ( v8 )
      {
        v10 = 0;
        KeReleaseSpinLock(v9, v7);
        for ( i = NetBufferLists; i; i = (PNET_BUFFER_LIST)i->Link.Alignment )
        {
          FirstNetBuffer = (SLIST_HEADER *)i->FirstNetBuffer;
          for ( j = 0; FirstNetBuffer; ++j )
            FirstNetBuffer = (SLIST_HEADER *)FirstNetBuffer->Alignment;
          LODWORD(i->MiniportReserved[0]) = j;
          LODWORD(i->Scratch) = 0;
          v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WorkItemContext + 12);
          *((_DWORD *)WorkItemContext + 47) += j;
          WorkItemContext[104] = v14;
          _InterlockedIncrement((volatile signed __int32 *)WorkItemContext + 8);
          if ( i != *((PNET_BUFFER_LIST *)WorkItemContext + 60) )
          {
            _InterlockedIncrement((volatile signed __int32 *)&i->Scratch);
            _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)WorkItemContext + 7) + 192LL));
          }
          KeReleaseSpinLock((PKSPIN_LOCK)WorkItemContext + 12, WorkItemContext[104]);
          v10 = i;
        }
        v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WorkItemContext + 17);
        v8 = *((_QWORD *)WorkItemContext + 15) == 0;
        WorkItemContext[144] = v15;
        if ( v8 )
          *((_QWORD *)WorkItemContext + 15) = NetBufferLists;
        else
          **((_QWORD **)WorkItemContext + 16) = NetBufferLists;
        v8 = WorkItemContext[195] == 0;
        *((_QWORD *)WorkItemContext + 16) = v10;
        if ( v8 )
        {
          WorkItemContext[195] = 1;
          _InterlockedIncrement((volatile signed __int32 *)WorkItemContext);
          NdisQueueIoWorkItem(
            *((NDIS_HANDLE *)WorkItemContext + 75),
            (NDIS_IO_WORKITEM_ROUTINE)CallProcessNBLs,
            WorkItemContext);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)WorkItemContext + 17, WorkItemContext[144]);
LABEL_18:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(__int64))(v6 + 8))(v6);
        return;
      }
      KeReleaseSpinLock(v9, v7);
    }
    v5 = -1073741823;
    v16 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_03516810ed2635a74cea1971954143d2_Traceguids, 3221225473LL);
    }
  }
  if ( v5 != 259 )
  {
    for ( k = NetBufferLists; k; k = (PNET_BUFFER_LIST)k->Link.Alignment )
    {
      Alignment = (SLIST_HEADER *)k->FirstNetBuffer;
      v19 = 0;
      for ( k->Status = v5; Alignment; ++v19 )
        Alignment = (SLIST_HEADER *)Alignment->Alignment;
      _InterlockedAdd((volatile signed __int32 *)WorkItemContext + 169, v19);
      _InterlockedAdd(&dword_14000B428, v19);
    }
    NdisMCoSendNetBufferListsComplete(*((NDIS_HANDLE *)WorkItemContext + 28), NetBufferLists, 0);
  }
  if ( v16 )
    goto LABEL_18;
}

```

## disassembly

```asm
0x140018d80  push    rbx
0x140018d82  push    rbp
0x140018d83  push    rsi
0x140018d84  push    rdi
0x140018d85  push    r12
0x140018d87  push    r14
0x140018d89  push    r15
0x140018d8b  sub     rsp, 20h
0x140018d8f  mov     rsi, [rcx+38h]
0x140018d93  mov     rbx, rcx
0x140018d96  mov     r14, rdx
0x140018d99  lea     rcx, [rsi+8]; SpinLock
0x140018d9d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018da4  nop     dword ptr [rax+rax+00h]
0x140018da9  mov     rcx, rsi
0x140018dac  mov     [rsi+10h], al
0x140018daf  call    MiniportCheckAdapterState
0x140018db4  mov     ebp, eax
0x140018db6  test    eax, eax
0x140018db8  jnz     loc_140018F60
0x140018dbe  lea     rdi, [rsi+0C0h]
0x140018dc5  lock inc dword ptr [rdi]
0x140018dc8  movzx   edx, byte ptr [rsi+10h]; NewIrql
0x140018dcc  lea     rcx, [rsi+8]; SpinLock
0x140018dd0  call    cs:__imp_KeReleaseSpinLock
0x140018dd7  nop     dword ptr [rax+rax+00h]
0x140018ddc  cmp     dword ptr [rbx+30h], 43505450h
0x140018de3  jnz     loc_140018FC8
0x140018de9  lea     rcx, [rbx+60h]; SpinLock
0x140018ded  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018df4  nop     dword ptr [rax+rax+00h]
0x140018df9  cmp     dword ptr [rbx+70h], 9
0x140018dfd  lea     rcx, [rbx+60h]; SpinLock
0x140018e01  mov     [rbx+68h], al
0x140018e04  movzx   edx, al; NewIrql
0x140018e07  jnz     loc_140018FBC
0x140018e0d  xor     ebp, ebp
0x140018e0f  call    cs:__imp_KeReleaseSpinLock
0x140018e16  nop     dword ptr [rax+rax+00h]
0x140018e1b  mov     r15, r14
0x140018e1e  test    r14, r14
0x140018e21  jz      short loc_140018E9C
0x140018e23  mov     rax, [r15+8]
0x140018e27  xor     r12d, r12d
0x140018e2a  test    rax, rax
0x140018e2d  jz      short loc_140018E3A
0x140018e2f  mov     rax, [rax]
0x140018e32  inc     r12d
0x140018e35  test    rax, rax
0x140018e38  jnz     short loc_140018E2F
0x140018e3a  lea     rcx, [rbx+60h]; SpinLock
0x140018e3e  mov     [r15+60h], r12d
0x140018e42  mov     dword ptr [r15+70h], 0
0x140018e4a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018e51  nop     dword ptr [rax+rax+00h]
0x140018e56  add     [rbx+0BCh], r12d
0x140018e5d  mov     [rbx+68h], al
0x140018e60  lock inc dword ptr [rbx+20h]
0x140018e64  cmp     r15, [rbx+1E0h]
0x140018e6b  jz      short loc_140018E7D
0x140018e6d  lock inc dword ptr [r15+70h]
0x140018e72  mov     rax, [rbx+38h]
0x140018e76  lock inc dword ptr [rax+0C0h]
0x140018e7d  movzx   edx, byte ptr [rbx+68h]; NewIrql
0x140018e81  lea     rcx, [rbx+60h]; SpinLock
0x140018e85  call    cs:__imp_KeReleaseSpinLock
0x140018e8c  nop     dword ptr [rax+rax+00h]
0x140018e91  mov     rbp, r15
0x140018e94  mov     r15, [r15]
0x140018e97  test    r15, r15
0x140018e9a  jnz     short loc_140018E23
0x140018e9c  lea     rcx, [rbx+88h]; SpinLock
0x140018ea3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018eaa  nop     dword ptr [rax+rax+00h]
0x140018eaf  cmp     qword ptr [rbx+78h], 0
0x140018eb4  mov     [rbx+90h], al
0x140018eba  jnz     short loc_140018F13
0x140018ebc  mov     [rbx+78h], r14
0x140018ec0  cmp     byte ptr [rbx+0C3h], 0
0x140018ec7  mov     [rbx+80h], rbp
0x140018ece  jnz     short loc_140018EF7
0x140018ed0  mov     byte ptr [rbx+0C3h], 1
0x140018ed7  lock inc dword ptr [rbx]
0x140018eda  mov     rcx, [rbx+258h]; NdisIoWorkItemHandle
0x140018ee1  lea     rdx, CallProcessNBLs; Routine
0x140018ee8  mov     r8, rbx; WorkItemContext
0x140018eeb  call    cs:__imp_NdisQueueIoWorkItem
0x140018ef2  nop     dword ptr [rax+rax+00h]
0x140018ef7  movzx   edx, byte ptr [rbx+90h]; NewIrql
0x140018efe  lea     rcx, [rbx+88h]; SpinLock
0x140018f05  call    cs:__imp_KeReleaseSpinLock
0x140018f0c  nop     dword ptr [rax+rax+00h]
0x140018f11  jmp     short loc_140018F34
0x140018f13  mov     rax, [rbx+80h]
0x140018f1a  mov     [rax], r14
0x140018f1d  jmp     short loc_140018EC0
0x140018f1f  test    ebp, ebp
0x140018f21  jz      short loc_140018F2F
0x140018f23  cmp     ebp, 103h
0x140018f29  jnz     loc_140019019
0x140018f2f  test    r12b, r12b
0x140018f32  jz      short loc_140018F42
0x140018f34  mov     eax, 0FFFFFFFFh
0x140018f39  lock xadd [rdi], eax
0x140018f3d  cmp     eax, 1
0x140018f40  jz      short loc_140018F52
0x140018f42  add     rsp, 20h
0x140018f46  pop     r15
0x140018f48  pop     r14
0x140018f4a  pop     r12
0x140018f4c  pop     rdi
0x140018f4d  pop     rsi
0x140018f4e  pop     rbp
0x140018f4f  pop     rbx
0x140018f50  retn
0x140018f52  mov     rax, [rdi+8]
0x140018f56  mov     rcx, rdi
0x140018f59  call    _guard_dispatch_icall
0x140018f5e  jmp     short loc_140018F42
0x140018f60  xor     r12b, r12b
0x140018f63  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f6a  lea     rax, WPP_GLOBAL_Control
0x140018f71  cmp     rcx, rax
0x140018f74  jz      short loc_140018F9C
0x140018f76  mov     edx, [rcx+2Ch]
0x140018f79  test    dl, 20h
0x140018f7c  jz      short loc_140018F9C
0x140018f7e  cmp     byte ptr [rcx+29h], 1
0x140018f82  jb      short loc_140018F9C
0x140018f84  mov     rcx, [rcx+18h]
0x140018f88  lea     r8, WPP_03516810ed2635a74cea1971954143d2_Traceguids
0x140018f8f  mov     edx, 18h
0x140018f94  mov     r9d, ebp
0x140018f97  call    WPP_SF_d
0x140018f9c  movzx   edx, byte ptr [rsi+10h]; NewIrql
0x140018fa0  lea     rcx, [rsi+8]; SpinLock
0x140018fa4  call    cs:__imp_KeReleaseSpinLock
0x140018fab  nop     dword ptr [rax+rax+00h]
0x140018fb0  lea     rdi, [rsi+0C0h]
0x140018fb7  jmp     loc_140018F23
0x140018fbc  call    cs:__imp_KeReleaseSpinLock
0x140018fc3  nop     dword ptr [rax+rax+00h]
0x140018fc8  mov     ebp, 0C0000001h
0x140018fcd  mov     r12b, 1
0x140018fd0  mov     r9d, ebp
0x140018fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140018fda  lea     rax, WPP_GLOBAL_Control
0x140018fe1  cmp     rcx, rax
0x140018fe4  jz      loc_140018F1F
0x140018fea  mov     eax, [rcx+2Ch]
0x140018fed  test    al, 20h
0x140018fef  jz      loc_140018F1F
0x140018ff5  cmp     [rcx+29h], r12b
0x140018ff9  jb      loc_140018F1F
0x140018fff  mov     rcx, [rcx+18h]
0x140019003  lea     r8, WPP_03516810ed2635a74cea1971954143d2_Traceguids
0x14001900a  mov     edx, 19h
0x14001900f  call    WPP_SF_d
0x140019014  jmp     loc_140018F1F
0x140019019  mov     rax, r14
0x14001901c  test    r14, r14
0x14001901f  jz      short loc_140019052
0x140019021  mov     rcx, [rax+8]
0x140019025  xor     edx, edx
0x140019027  mov     [rax+8Ch], ebp
0x14001902d  test    rcx, rcx
0x140019030  jz      short loc_14001903C
0x140019032  mov     rcx, [rcx]
0x140019035  inc     edx
0x140019037  test    rcx, rcx
0x14001903a  jnz     short loc_140019032
0x14001903c  lock add [rbx+2A4h], edx
0x140019043  lock add cs:dword_14000B428, edx
0x14001904a  mov     rax, [rax]
0x14001904d  test    rax, rax
0x140019050  jnz     short loc_140019021
0x140019052  mov     rcx, [rbx+0E0h]; NdisVcHandle
0x140019059  xor     r8d, r8d; SendCompleteFlags
0x14001905c  mov     rdx, r14; NetBufferLists
0x14001905f  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x140019066  nop     dword ptr [rax+rax+00h]
0x14001906b  jmp     loc_140018F2F
```
