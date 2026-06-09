# LmpCoSendNetBufferListChain

- ea: `0x14001be00`
- end: `0x14001c03c`
- name: `LmpCoSendNetBufferListChain`
- size: `572`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140003050`
- `0x1400031ec`
- `0x14001be00`
- `0x14001c050`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001be9a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bf76`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001be9a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001bf76`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001be74`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001be74`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x14001c02b`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x14001c02b`

## pseudocode

```c
void __fastcall LmpCoSendNetBufferListChain(__int64 a1, struct _NET_BUFFER_LIST *a2)
{
  __int64 v4; // rdi
  KIRQL v5; // al
  bool v6; // zf
  KSPIN_LOCK *v7; // rcx
  int v8; // eax
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  struct _NET_BUFFER_LIST *i; // rcx
  int v12; // [rsp+28h] [rbp-30h]
  int v13; // [rsp+30h] [rbp-28h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids);
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 24) + 184LL) == 1 )
  {
    v4 = *(_QWORD *)(a1 + 32);
    if ( v4 && (*(_DWORD *)(a1 + 60) & 0x2000000) != 0 )
    {
      if ( (*(_DWORD *)(v4 + 120) & 0x10) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids);
        }
        goto LABEL_32;
      }
      v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
      v6 = (*(_DWORD *)(a1 + 60) & 0x200) == 0;
      v7 = (KSPIN_LOCK *)(a1 + 72);
      *(_BYTE *)(a1 + 80) = v5;
      if ( !v6 )
      {
        ++*(_DWORD *)(a1 + 64);
        KeReleaseSpinLock(v7, v5);
        if ( (*(_DWORD *)(a1 + 60) & 0x40) != 0 )
          ScheduleTunnelWork(v4, a1, (__int64)SendPayloadSeq, (__int64)a2, 0, v12, v13, 0);
        else
          ScheduleTunnelWork(v4, a1, (__int64)SendPayloadUnseq, (__int64)a2, 0, v12, v13, 0);
        goto LABEL_9;
      }
      KeReleaseSpinLock(v7, v5);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_32;
      }
      v10 = 31;
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_32;
      }
      v10 = 33;
    }
    WPP_SF_q(v9->AttachedDevice, v10, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids, a1);
LABEL_32:
    v8 = -1073741823;
    goto LABEL_33;
  }
  v8 = -1071448022;
LABEL_33:
  for ( i = a2; i; i = (struct _NET_BUFFER_LIST *)i->Link.Alignment )
    i->Status = v8;
  NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 304), a2, 0);
LABEL_9:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids);
  }
}

```

## disassembly

```asm
0x14001be00  sub     rsp, 58h
0x14001be04  mov     [rsp+58h+arg_0], rbx
0x14001be09  mov     rbx, rcx
0x14001be0c  mov     [rsp+58h+arg_10], rsi
0x14001be11  mov     rsi, rdx
0x14001be14  mov     [rsp+58h+var_8], r14
0x14001be19  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be20  lea     r14, WPP_GLOBAL_Control
0x14001be27  cmp     rcx, r14
0x14001be2a  jnz     loc_14001BEFD
0x14001be30  mov     rax, [rbx+18h]
0x14001be34  mov     [rsp+58h+arg_8], rbp
0x14001be39  mov     [rsp+58h+arg_18], rdi
0x14001be3e  cmp     dword ptr [rax+0B8h], 1
0x14001be45  jnz     loc_14001BF54
0x14001be4b  mov     rdi, [rbx+20h]
0x14001be4f  test    rdi, rdi
0x14001be52  jz      loc_14001BFD2
0x14001be58  test    dword ptr [rbx+3Ch], 2000000h
0x14001be5f  jz      loc_14001BFD2
0x14001be65  mov     eax, [rdi+78h]
0x14001be68  test    al, 10h
0x14001be6a  jz      loc_14001BFA2
0x14001be70  lea     rcx, [rbx+48h]; SpinLock
0x14001be74  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001be7b  nop     dword ptr [rax+rax+00h]
0x14001be80  test    dword ptr [rbx+3Ch], 200h
0x14001be87  lea     rcx, [rbx+48h]; SpinLock
0x14001be8b  mov     [rbx+50h], al
0x14001be8e  movzx   edx, al; NewIrql
0x14001be91  jz      loc_14001BF76
0x14001be97  inc     dword ptr [rbx+40h]
0x14001be9a  call    cs:__imp_KeReleaseSpinLock
0x14001bea1  nop     dword ptr [rax+rax+00h]
0x14001bea6  mov     eax, [rbx+3Ch]
0x14001bea9  mov     r9, rsi
0x14001beac  mov     [rsp+58h+var_20], 0
0x14001beb1  mov     rdx, rbx
0x14001beb4  mov     rcx, rdi
0x14001beb7  test    al, 40h
0x14001beb9  jnz     loc_14001BF5E
0x14001bebf  xor     eax, eax
0x14001bec1  lea     r8, SendPayloadUnseq
0x14001bec8  mov     [rsp+58h+var_38], rax
0x14001becd  call    ScheduleTunnelWork
0x14001bed2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bed9  mov     rdi, [rsp+58h+arg_18]
0x14001bede  cmp     rcx, r14
0x14001bee1  mov     r14, [rsp+58h+var_8]
0x14001bee6  mov     rsi, [rsp+58h+arg_10]
0x14001beeb  mov     rbp, [rsp+58h+arg_8]
0x14001bef0  mov     rbx, [rsp+58h+arg_0]
0x14001bef5  jnz     short loc_14001BF2E
0x14001bef7  add     rsp, 58h
0x14001befb  retn
0x14001befd  test    dword ptr [rcx+2Ch], 200h
0x14001bf04  jz      loc_14001BE30
0x14001bf0a  cmp     byte ptr [rcx+29h], 4
0x14001bf0e  jb      loc_14001BE30
0x14001bf14  mov     rcx, [rcx+18h]
0x14001bf18  lea     r8, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids
0x14001bf1f  mov     edx, 1Eh
0x14001bf24  call    WPP_SF_
0x14001bf29  jmp     loc_14001BE30
0x14001bf2e  test    dword ptr [rcx+2Ch], 200h
0x14001bf35  jz      short loc_14001BEF7
0x14001bf37  cmp     byte ptr [rcx+29h], 4
0x14001bf3b  jb      short loc_14001BEF7
0x14001bf3d  mov     rcx, [rcx+18h]
0x14001bf41  lea     r8, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids
0x14001bf48  mov     edx, 22h ; '"'
0x14001bf4d  call    WPP_SF_
0x14001bf52  jmp     short loc_14001BEF7
0x14001bf54  mov     eax, 0C023002Ah
0x14001bf59  jmp     loc_14001C008
0x14001bf5e  xor     eax, eax
0x14001bf60  lea     r8, SendPayloadSeq
0x14001bf67  mov     [rsp+58h+var_38], rax
0x14001bf6c  call    ScheduleTunnelWork
0x14001bf71  jmp     loc_14001BED2
0x14001bf76  call    cs:__imp_KeReleaseSpinLock
0x14001bf7d  nop     dword ptr [rax+rax+00h]
0x14001bf82  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf89  cmp     rcx, r14
0x14001bf8c  jz      short loc_14001C003
0x14001bf8e  mov     eax, [rcx+2Ch]
0x14001bf91  test    al, 10h
0x14001bf93  jz      short loc_14001C003
0x14001bf95  cmp     byte ptr [rcx+29h], 1
0x14001bf99  jb      short loc_14001C003
0x14001bf9b  mov     edx, 1Fh
0x14001bfa0  jmp     short loc_14001BFF0
0x14001bfa2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bfa9  cmp     rcx, r14
0x14001bfac  jz      short loc_14001C003
0x14001bfae  mov     eax, [rcx+2Ch]
0x14001bfb1  test    al, 10h
0x14001bfb3  jz      short loc_14001C003
0x14001bfb5  cmp     byte ptr [rcx+29h], 1
0x14001bfb9  jb      short loc_14001C003
0x14001bfbb  mov     rcx, [rcx+18h]
0x14001bfbf  lea     r8, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids
0x14001bfc6  mov     edx, 20h ; ' '
0x14001bfcb  call    WPP_SF_
0x14001bfd0  jmp     short loc_14001C003
0x14001bfd2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bfd9  cmp     rcx, r14
0x14001bfdc  jz      short loc_14001C003
0x14001bfde  mov     eax, [rcx+2Ch]
0x14001bfe1  test    al, 10h
0x14001bfe3  jz      short loc_14001C003
0x14001bfe5  cmp     byte ptr [rcx+29h], 1
0x14001bfe9  jb      short loc_14001C003
0x14001bfeb  mov     edx, 21h ; '!'
0x14001bff0  mov     rcx, [rcx+18h]
0x14001bff4  lea     r8, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids
0x14001bffb  mov     r9, rbx
0x14001bffe  call    WPP_SF_q
0x14001c003  mov     eax, 0C0000001h
0x14001c008  mov     rcx, rsi
0x14001c00b  test    rsi, rsi
0x14001c00e  jz      short loc_14001C01E
0x14001c010  mov     [rcx+8Ch], eax
0x14001c016  mov     rcx, [rcx]
0x14001c019  test    rcx, rcx
0x14001c01c  jnz     short loc_14001C010
0x14001c01e  mov     rcx, [rbx+130h]; NdisVcHandle
0x14001c025  xor     r8d, r8d; SendCompleteFlags
0x14001c028  mov     rdx, rsi; NetBufferLists
0x14001c02b  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x14001c032  nop     dword ptr [rax+rax+00h]
0x14001c037  jmp     loc_14001BED2
```
