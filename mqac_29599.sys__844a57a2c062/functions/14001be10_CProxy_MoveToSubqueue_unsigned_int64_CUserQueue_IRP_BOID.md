# CProxy::MoveToSubqueue(unsigned __int64,CUserQueue *,_IRP *,BOID *)

- ea: `0x14001be10`
- end: `0x14001bff3`
- name: `?MoveToSubqueue@CProxy@@UEAAJ_KPEAVCUserQueue@@PEAU_IRP@@PEAUBOID@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(CProxy *__hidden this, unsigned __int64, struct CUserQueue *, struct _IRP *, struct BOID *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140001c04`
- `0x140001c34`
- `0x140019f04`
- `0x14001bcb0`
- `0x14001be10`
- `0x14001c3f8`
- `0x140024bf0`

## pseudocode

```c
int __fastcall CProxy::MoveToSubqueue(
        CProxy *this,
        unsigned __int64 a2,
        struct CUserQueue *a3,
        struct _IRP *a4,
        struct BOID *a5)
{
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ecx
  unsigned int v15; // edx
  int v16; // ecx
  int v17; // ebx

  if ( !a3 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return -1073741816;
    }
    v10 = 20;
LABEL_13:
    WPP_SF_(v9->Queue.ListEntry.Blink, v10, &WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids);
    return -1073741816;
  }
  if ( a3 == this )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return -1073741816;
    }
    v10 = 21;
    goto LABEL_13;
  }
  if ( !(*(__int64 (__fastcall **)(struct CUserQueue *))(*(_QWORD *)a3 + 112LL))(a3) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return -1073741816;
    }
    v10 = 22;
    goto LABEL_13;
  }
  v12 = *((_BYTE *)this + 89) & 0xF;
  if ( (_DWORD)v12 == 5 || (v13 = *((_BYTE *)a3 + 89) & 0xF, (_DWORD)v13 == 5) )
  {
    a4->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = 0;
    a4->Tail.Overlay.DriverContext[2] = 0;
    a4->Tail.Overlay.DriverContext[3] = 0;
    v14 = *(_DWORD *)(&a4->Tail.CompletionKey + 3) & 0xFF0000FB;
    v15 = ++g_IrpTag;
    v16 = (g_IrpTag << 8) | v14;
    a4->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)this;
    *((_DWORD *)&a4->Tail.CompletionKey + 6) = v16 & 0xFFFFFFD4 | 3;
    v17 = CProxy::IssueRemoteMoveMessage(this, v15, a3, a2, a5);
    if ( v17 >= 0 )
    {
      return CQueueBase::HoldRequest(
               this,
               a4,
               0xFFFFFFFF,
               (void (*)(struct _DEVICE_OBJECT *, struct _IRP *))ACCancelRemoteQueueOperation,
               0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->Queue.ListEntry.Blink,
          24,
          &WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids,
          (unsigned int)v17);
      }
      return v17;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        v12,
        v13,
        *((unsigned __int8 *)this + 88),
        v12,
        *((unsigned __int8 *)a3 + 88),
        *((_BYTE *)a3 + 89) & 0xF);
    }
    return -1072824288;
  }
}

```

## disassembly

```asm
0x14001be10  push    rbx
0x14001be12  push    rbp
0x14001be13  push    rsi
0x14001be14  push    rdi
0x14001be15  sub     rsp, 48h
0x14001be19  mov     rsi, r9
0x14001be1c  mov     rbx, r8
0x14001be1f  mov     rbp, rdx
0x14001be22  mov     rdi, rcx
0x14001be25  test    r8, r8
0x14001be28  jnz     short loc_14001BE4A
0x14001be2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be31  lea     rax, WPP_GLOBAL_Control
0x14001be38  cmp     rcx, rax
0x14001be3b  jz      short loc_14001BEB3
0x14001be3d  mov     eax, [rcx+6Ch]
0x14001be40  test    al, 1
0x14001be42  jz      short loc_14001BEB3
0x14001be44  lea     edx, [r8+14h]
0x14001be48  jmp     short loc_14001BEA3
0x14001be4a  cmp     rbx, rdi
0x14001be4d  jnz     short loc_14001BE70
0x14001be4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be56  lea     rax, WPP_GLOBAL_Control
0x14001be5d  cmp     rcx, rax
0x14001be60  jz      short loc_14001BEB3
0x14001be62  mov     eax, [rcx+6Ch]
0x14001be65  test    al, 1
0x14001be67  jz      short loc_14001BEB3
0x14001be69  mov     edx, 15h
0x14001be6e  jmp     short loc_14001BEA3
0x14001be70  mov     rax, [r8]
0x14001be73  mov     rcx, rbx
0x14001be76  mov     rax, [rax+70h]
0x14001be7a  call    _guard_dispatch_icall
0x14001be7f  test    rax, rax
0x14001be82  jnz     short loc_14001BEBD
0x14001be84  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be8b  lea     rax, WPP_GLOBAL_Control
0x14001be92  cmp     rcx, rax
0x14001be95  jz      short loc_14001BEB3
0x14001be97  mov     eax, [rcx+6Ch]
0x14001be9a  test    al, 1
0x14001be9c  jz      short loc_14001BEB3
0x14001be9e  mov     edx, 16h
0x14001bea3  mov     rcx, [rcx+58h]
0x14001bea7  lea     r8, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids
0x14001beae  call    WPP_SF_
0x14001beb3  mov     eax, 0C0000008h
0x14001beb8  jmp     loc_14001BFE9
0x14001bebd  movzx   edx, byte ptr [rdi+59h]
0x14001bec1  and     edx, 0Fh
0x14001bec4  cmp     edx, 5
0x14001bec7  jz      short loc_14001BF1B
0x14001bec9  movzx   r8d, byte ptr [rbx+59h]
0x14001bece  and     r8d, 0Fh
0x14001bed2  cmp     r8d, 5
0x14001bed6  jz      short loc_14001BF1B
0x14001bed8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bedf  lea     rax, WPP_GLOBAL_Control
0x14001bee6  cmp     rcx, rax
0x14001bee9  jz      short loc_14001BF11
0x14001beeb  mov     eax, [rcx+6Ch]
0x14001beee  test    al, 1
0x14001bef0  jz      short loc_14001BF11
0x14001bef2  movzx   eax, byte ptr [rbx+58h]
0x14001bef6  movzx   r9d, byte ptr [rdi+58h]
0x14001befb  mov     rcx, [rcx+58h]
0x14001beff  mov     [rsp+68h+var_38], r8d
0x14001bf04  mov     [rsp+68h+var_40], eax
0x14001bf08  mov     dword ptr [rsp+68h+var_48], edx
0x14001bf0c  call    WPP_SF_DDDD
0x14001bf11  mov     eax, 0C00E0020h
0x14001bf16  jmp     loc_14001BFE9
0x14001bf1b  mov     qword ptr [rsi+80h], 0
0x14001bf26  mov     r9, rbp; unsigned __int64
0x14001bf29  mov     qword ptr [rsi+88h], 0
0x14001bf34  mov     r8, rbx; struct CUserQueue *
0x14001bf37  mov     qword ptr [rsi+90h], 0
0x14001bf42  movzx   eax, cs:?g_IrpTag@@3GA; ushort g_IrpTag
0x14001bf49  mov     ecx, [rsi+90h]
0x14001bf4f  inc     ax
0x14001bf52  and     ecx, 0FF0000FBh
0x14001bf58  movzx   edx, ax; unsigned int
0x14001bf5b  mov     cs:?g_IrpTag@@3GA, ax; ushort g_IrpTag
0x14001bf62  mov     eax, edx
0x14001bf64  shl     eax, 8
0x14001bf67  or      ecx, eax
0x14001bf69  mov     [rsi+78h], rdi
0x14001bf6d  mov     rax, [rsp+68h+arg_20]
0x14001bf75  and     ecx, 0FFFFFFD7h
0x14001bf78  or      ecx, 3
0x14001bf7b  mov     [rsp+68h+var_48], rax; struct BOID *
0x14001bf80  mov     [rsi+90h], ecx
0x14001bf86  mov     rcx, rdi; this
0x14001bf89  call    ?IssueRemoteMoveMessage@CProxy@@QEBAJKPEAVCUserQueue@@_KPEAUBOID@@@Z; CProxy::IssueRemoteMoveMessage(ulong,CUserQueue *,unsigned __int64,BOID *)
0x14001bf8e  mov     ebx, eax
0x14001bf90  test    eax, eax
0x14001bf92  jns     short loc_14001BFCB
0x14001bf94  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf9b  lea     rax, WPP_GLOBAL_Control
0x14001bfa2  cmp     rcx, rax
0x14001bfa5  jz      short loc_14001BFC7
0x14001bfa7  mov     edx, [rcx+6Ch]
0x14001bfaa  test    dl, 1
0x14001bfad  jz      short loc_14001BFC7
0x14001bfaf  mov     rcx, [rcx+58h]
0x14001bfb3  lea     r8, WPP_c5d1d6c3d61c3e5c96519d971c1f293d_Traceguids
0x14001bfba  mov     edx, 18h
0x14001bfbf  mov     r9d, ebx
0x14001bfc2  call    WPP_SF_d
0x14001bfc7  mov     eax, ebx
0x14001bfc9  jmp     short loc_14001BFE9
0x14001bfcb  lea     r9, ACCancelRemoteQueueOperation; void (*)(struct _DEVICE_OBJECT *, struct _IRP *)
0x14001bfd2  mov     dword ptr [rsp+68h+var_48], 0; int
0x14001bfda  or      r8d, 0FFFFFFFFh; unsigned int
0x14001bfde  mov     rdx, rsi; struct _IRP *
0x14001bfe1  mov     rcx, rdi; this
0x14001bfe4  call    ?HoldRequest@CQueueBase@@IEAAJPEAU_IRP@@KP6AXPEAU_DEVICE_OBJECT@@0@ZH@Z; CQueueBase::HoldRequest(_IRP *,ulong,void (*)(_DEVICE_OBJECT *,_IRP *),int)
0x14001bfe9  add     rsp, 48h
0x14001bfed  pop     rdi
0x14001bfee  pop     rsi
0x14001bfef  pop     rbp
0x14001bff0  pop     rbx
0x14001bff1  retn
```
