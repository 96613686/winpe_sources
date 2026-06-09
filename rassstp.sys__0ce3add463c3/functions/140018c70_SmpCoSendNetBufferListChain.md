# SmpCoSendNetBufferListChain

- ea: `0x140018c70`
- end: `0x14001902b`
- name: `SmpCoSendNetBufferListChain`
- size: `955`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140002c08`
- `0x140002f88`
- `0x140003010`
- `0x140005ef0`
- `0x140018c70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018c8d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018d85`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018c8d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018d85`
- `ntoskrnl!IofCompleteRequest` at `0x140018e1f`
- `ntoskrnl!IofCompleteRequest` at `0x140018e1f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018cd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018dfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018ec6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018eef`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018cd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018dfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018ec6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018eef`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140018f95`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140018f95`
- `fwpkclnt!DPSendNetBufferList0` at `0x140018cfb`
- `fwpkclnt!DPSendNetBufferList0` at `0x140018cfb`

## pseudocode

```c
void __fastcall SmpCoSendNetBufferListChain(__int64 a1, struct _NET_BUFFER_LIST *Alignment)
{
  KIRQL v4; // al
  void (**v5)(void); // rcx
  struct _NET_BUFFER_LIST *v6; // rcx
  PVOID *MiniportReserved; // r14
  KIRQL v8; // r13
  bool v9; // zf
  __int64 v10; // rbp
  __int64 v11; // r8
  struct _NET_BUFFER_LIST *i; // rax

  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 25);
  if ( *((_DWORD *)SstpGlobals + 40) == 2 && *(_BYTE *)(a1 + 507) )
  {
    _InterlockedIncrement((volatile signed __int32 *)SstpGlobals + 36);
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 25, v4);
    if ( *(_BYTE *)(a1 + 21132) )
    {
      DPSendNetBufferList0(*(_QWORD *)(a1 + 21136), Alignment);
    }
    else
    {
      while ( Alignment )
      {
        v6 = Alignment;
        Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
        MiniportReserved = v6->MiniportReserved;
        v6->Link.Alignment = 0;
        v6->MiniportReserved[0] = 0;
        LOBYTE(v6->MiniportReserved[1]) = 0;
        v6->Scratch = v6->FirstNetBuffer;
        _InterlockedIncrement((volatile signed __int32 *)SstpGlobals + 36);
        v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
        if ( *(_QWORD *)(a1 + 96) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF__guid_(
              WPP_GLOBAL_Control->AttachedDevice,
              77,
              WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
              a1 + 484);
          }
          if ( *((_BYTE *)MiniportReserved + 8) )
          {
            *MiniportReserved = *(PVOID *)(a1 + 96);
            *(_QWORD *)(a1 + 96) = MiniportReserved;
          }
          else
          {
            **(_QWORD **)(a1 + 104) = MiniportReserved;
            *(_QWORD *)(a1 + 104) = MiniportReserved;
          }
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v8);
        }
        else
        {
          v9 = *(_QWORD *)(a1 + 80) == 0;
          *(_QWORD *)(a1 + 96) = MiniportReserved;
          if ( v9 )
          {
            v10 = 0;
            *(_BYTE *)(a1 + 88) = 1;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF__guid_(
                WPP_GLOBAL_Control->AttachedDevice,
                76,
                WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
                a1 + 484);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF__guid_(
                WPP_GLOBAL_Control->AttachedDevice,
                75,
                WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
                a1 + 484);
            }
            v10 = *(_QWORD *)(a1 + 80);
            *(_QWORD *)(a1 + 80) = 0;
            if ( _InterlockedExchange64((volatile __int64 *)(v10 + 104), 0) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(__int64))(a1 + 8))(a1);
            }
            else
            {
              *(_BYTE *)(a1 + 88) = 1;
              v10 = 0;
            }
          }
          *(_QWORD *)(a1 + 104) = MiniportReserved;
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v8);
          if ( v10 )
          {
            *(_DWORD *)(v10 + 48) = 0;
            *(_QWORD *)(v10 + 56) = 0;
            IofCompleteRequest((PIRP)v10, 2);
          }
        }
      }
    }
    v5 = (void (**)(void))((char *)SstpGlobals + 144);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)SstpGlobals + 36, 0xFFFFFFFF) == 1 )
      v5[1]();
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 25, v4);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          *((unsigned int *)SstpGlobals + 40),
          v11,
          *(unsigned __int8 *)(a1 + 507),
          *((_DWORD *)SstpGlobals + 40));
      }
    }
    for ( i = Alignment; i; i = (struct _NET_BUFFER_LIST *)i->Link.Alignment )
      i->Status = -1073741823;
    NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 40), Alignment, 0);
  }
}

```

## disassembly

```asm
0x140018c70  push    rsi
0x140018c72  push    rdi
0x140018c73  push    r12
0x140018c75  sub     rsp, 40h
0x140018c79  mov     rdi, rcx
0x140018c7c  mov     rsi, rdx
0x140018c7f  mov     rcx, cs:SstpGlobals
0x140018c86  add     rcx, 0C8h; SpinLock
0x140018c8d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018c94  nop     dword ptr [rax+rax+00h]
0x140018c99  mov     rcx, cs:SstpGlobals
0x140018ca0  cmp     dword ptr [rcx+0A0h], 2
0x140018ca7  jnz     loc_140018EE5
0x140018cad  cmp     byte ptr [rdi+1FBh], 0
0x140018cb4  jz      loc_140018EE5
0x140018cba  mov     [rsp+58h+arg_0], rbx
0x140018cbf  lock inc dword ptr [rcx+90h]
0x140018cc6  mov     rcx, cs:SstpGlobals
0x140018ccd  movzx   edx, al; NewIrql
0x140018cd0  add     rcx, 0C8h; SpinLock
0x140018cd7  call    cs:__imp_KeReleaseSpinLock
0x140018cde  nop     dword ptr [rax+rax+00h]
0x140018ce3  cmp     byte ptr [rdi+528Ch], 0
0x140018cea  mov     ebx, 0FFFFFFFFh
0x140018cef  jz      short loc_140018D31
0x140018cf1  mov     rcx, [rdi+5290h]
0x140018cf8  mov     rdx, rsi
0x140018cfb  call    cs:__imp_DPSendNetBufferList0
0x140018d02  nop     dword ptr [rax+rax+00h]
0x140018d07  mov     rcx, cs:SstpGlobals
0x140018d0e  add     rcx, 90h
0x140018d15  lock xadd [rcx], ebx
0x140018d19  cmp     ebx, 1
0x140018d1c  mov     rbx, [rsp+58h+arg_0]
0x140018d21  jz      loc_14001901D
0x140018d27  add     rsp, 40h
0x140018d2b  pop     r12
0x140018d2d  pop     rdi
0x140018d2e  pop     rsi
0x140018d2f  retn
0x140018d31  test    rsi, rsi
0x140018d34  jz      short loc_140018D07
0x140018d36  mov     [rsp+58h+arg_10], r13
0x140018d3b  lea     r12, WPP_GLOBAL_Control
0x140018d42  mov     [rsp+58h+var_20], r14
0x140018d47  xor     r13d, r13d
0x140018d4a  mov     [rsp+58h+var_28], r15
0x140018d4f  mov     [rsp+58h+arg_8], rbp
0x140018d54  mov     rcx, rsi
0x140018d57  mov     rax, rsi
0x140018d5a  mov     rsi, [rsi]
0x140018d5d  lea     r14, [rcx+60h]
0x140018d61  mov     [rcx], r13
0x140018d64  mov     [r14], r13
0x140018d67  mov     byte ptr [rcx+68h], 0
0x140018d6b  mov     rax, [rcx+8]
0x140018d6f  mov     [rcx+70h], rax
0x140018d73  mov     rax, cs:SstpGlobals
0x140018d7a  lock inc dword ptr [rax+90h]
0x140018d81  lea     rcx, [rdi+20h]; SpinLock
0x140018d85  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018d8c  nop     dword ptr [rax+rax+00h]
0x140018d91  cmp     qword ptr [rdi+60h], 0
0x140018d96  movzx   r13d, al
0x140018d9a  jnz     loc_140018E8F
0x140018da0  cmp     qword ptr [rdi+50h], 0
0x140018da5  mov     [rdi+60h], r14
0x140018da9  jz      loc_140018E4D
0x140018daf  mov     rcx, cs:WPP_GLOBAL_Control
0x140018db6  cmp     rcx, r12
0x140018db9  jz      short loc_140018DC8
0x140018dbb  test    dword ptr [rcx+2Ch], 100h
0x140018dc2  jnz     loc_140018FA6
0x140018dc8  mov     rbp, [rdi+50h]
0x140018dcc  xor     eax, eax
0x140018dce  mov     qword ptr [rdi+50h], 0
0x140018dd6  xchg    rax, [rbp+68h]
0x140018dda  test    rax, rax
0x140018ddd  jz      loc_140018EDA
0x140018de3  mov     eax, ebx
0x140018de5  lock xadd [rdi], eax
0x140018de9  cmp     eax, 1
0x140018dec  jz      loc_140018FD1
0x140018df2  movzx   edx, r13b; NewIrql
0x140018df6  mov     [rdi+68h], r14
0x140018dfa  lea     rcx, [rdi+20h]; SpinLock
0x140018dfe  call    cs:__imp_KeReleaseSpinLock
0x140018e05  nop     dword ptr [rax+rax+00h]
0x140018e0a  xor     r13d, r13d
0x140018e0d  test    rbp, rbp
0x140018e10  jz      short loc_140018E2B
0x140018e12  mov     dl, 2; PriorityBoost
0x140018e14  mov     [rbp+30h], r13d
0x140018e18  mov     rcx, rbp; Irp
0x140018e1b  mov     [rbp+38h], r13
0x140018e1f  call    cs:__imp_IofCompleteRequest
0x140018e26  nop     dword ptr [rax+rax+00h]
0x140018e2b  test    rsi, rsi
0x140018e2e  jnz     loc_140018D54
0x140018e34  mov     r15, [rsp+58h+var_28]
0x140018e39  mov     r14, [rsp+58h+var_20]
0x140018e3e  mov     r13, [rsp+58h+arg_10]
0x140018e43  mov     rbp, [rsp+58h+arg_8]
0x140018e48  jmp     loc_140018D07
0x140018e4d  xor     ebp, ebp
0x140018e4f  mov     byte ptr [rdi+58h], 1
0x140018e53  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e5a  cmp     rcx, r12
0x140018e5d  jz      short loc_140018DF2
0x140018e5f  test    dword ptr [rcx+2Ch], 100h
0x140018e66  jz      short loc_140018DF2
0x140018e68  cmp     byte ptr [rcx+29h], 4
0x140018e6c  jb      short loc_140018DF2
0x140018e6e  mov     rcx, [rcx+18h]
0x140018e72  lea     r9, [rdi+1E4h]
0x140018e79  mov     edx, 4Ch ; 'L'
0x140018e7e  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140018e85  call    WPP_SF__guid_
0x140018e8a  jmp     loc_140018DF2
0x140018e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e96  cmp     rcx, r12
0x140018e99  jz      short loc_140018EA8
0x140018e9b  test    dword ptr [rcx+2Ch], 100h
0x140018ea2  jnz     loc_140018FE2
0x140018ea8  cmp     byte ptr [r14+8], 0
0x140018ead  lea     rcx, [rdi+20h]; SpinLock
0x140018eb1  movzx   edx, r13b; NewIrql
0x140018eb5  jnz     loc_14001900D
0x140018ebb  mov     rax, [rdi+68h]
0x140018ebf  mov     [rax], r14
0x140018ec2  mov     [rdi+68h], r14
0x140018ec6  call    cs:__imp_KeReleaseSpinLock
0x140018ecd  nop     dword ptr [rax+rax+00h]
0x140018ed2  xor     r13d, r13d
0x140018ed5  jmp     loc_140018E2B
0x140018eda  mov     byte ptr [rdi+58h], 1
0x140018ede  xor     ebp, ebp
0x140018ee0  jmp     loc_140018DF2
0x140018ee5  movzx   edx, al; NewIrql
0x140018ee8  add     rcx, 0C8h; SpinLock
0x140018eef  call    cs:__imp_KeReleaseSpinLock
0x140018ef6  nop     dword ptr [rax+rax+00h]
0x140018efb  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f02  lea     r12, WPP_GLOBAL_Control
0x140018f09  cmp     rcx, r12
0x140018f0c  jz      short loc_140018F71
0x140018f0e  mov     eax, [rcx+2Ch]
0x140018f11  test    al, 1
0x140018f13  jz      short loc_140018F36
0x140018f15  cmp     byte ptr [rcx+29h], 2
0x140018f19  jb      short loc_140018F36
0x140018f1b  mov     rcx, [rcx+18h]
0x140018f1f  lea     r8, WPP_bd95722c768d3598be23ac079e3ae056_Traceguids
0x140018f26  mov     edx, 22h ; '"'
0x140018f2b  mov     r9d, 0C0000001h
0x140018f31  call    WPP_SF_d
0x140018f36  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f3d  cmp     rcx, r12
0x140018f40  jz      short loc_140018F71
0x140018f42  mov     eax, [rcx+2Ch]
0x140018f45  test    al, 1
0x140018f47  jz      short loc_140018F71
0x140018f49  cmp     byte ptr [rcx+29h], 2
0x140018f4d  jb      short loc_140018F71
0x140018f4f  mov     rax, cs:SstpGlobals
0x140018f56  movzx   r9d, byte ptr [rdi+1FBh]
0x140018f5e  mov     rcx, [rcx+18h]
0x140018f62  mov     edx, [rax+0A0h]
0x140018f68  mov     [rsp+58h+var_38], edx
0x140018f6c  call    WPP_SF_dd
0x140018f71  mov     rax, rsi
0x140018f74  test    rsi, rsi
0x140018f77  jz      short loc_140018F8B
0x140018f79  mov     dword ptr [rax+8Ch], 0C0000001h
0x140018f83  mov     rax, [rax]
0x140018f86  test    rax, rax
0x140018f89  jnz     short loc_140018F79
0x140018f8b  mov     rcx, [rdi+28h]; NdisVcHandle
0x140018f8f  xor     r8d, r8d; SendCompleteFlags
0x140018f92  mov     rdx, rsi; NetBufferLists
0x140018f95  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x140018f9c  nop     dword ptr [rax+rax+00h]
0x140018fa1  jmp     loc_140018D27
0x140018fa6  cmp     byte ptr [rcx+29h], 4
0x140018faa  jb      loc_140018DC8
0x140018fb0  mov     rcx, [rcx+18h]
0x140018fb4  lea     r9, [rdi+1E4h]
0x140018fbb  mov     edx, 4Bh ; 'K'
0x140018fc0  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140018fc7  call    WPP_SF__guid_
0x140018fcc  jmp     loc_140018DC8
0x140018fd1  mov     rax, [rdi+8]
0x140018fd5  mov     rcx, rdi
0x140018fd8  call    _guard_dispatch_icall
0x140018fdd  jmp     loc_140018DF2
0x140018fe2  cmp     byte ptr [rcx+29h], 4
0x140018fe6  jb      loc_140018EA8
0x140018fec  mov     rcx, [rcx+18h]
0x140018ff0  lea     r9, [rdi+1E4h]
0x140018ff7  mov     edx, 4Dh ; 'M'
0x140018ffc  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140019003  call    WPP_SF__guid_
0x140019008  jmp     loc_140018EA8
0x14001900d  mov     rax, [rdi+60h]
0x140019011  mov     [r14], rax
0x140019014  mov     [rdi+60h], r14
0x140019018  jmp     loc_140018EC6
0x14001901d  mov     rax, [rcx+8]
0x140019021  call    _guard_dispatch_icall
0x140019026  jmp     loc_140018D27
```
