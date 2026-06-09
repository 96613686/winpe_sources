# CPacket::HandleCreatePacketCompleted(long,ushort)

- ea: `0x140017694`
- end: `0x1400177bd`
- name: `?HandleCreatePacketCompleted@CPacket@@QEAAXJG@Z`
- size: `297`
- prototype: `void __fastcall(CPacket *__hidden this, int, unsigned __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001206c`

## callees

- `0x14000b7bc`
- `0x140011dc4`
- `0x1400121e8`
- `0x140012450`
- `0x140017694`
- `0x14001979c`
- `0x140024bf0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400177a7`
- `ntoskrnl!IofCompleteRequest` at `0x1400177a7`

## pseudocode

```c
void __fastcall CPacket::HandleCreatePacketCompleted(CPacket *this, int a2, unsigned __int16 a3)
{
  __int64 v6; // rdi
  struct _IRP *PacketRequest; // rax
  struct _IRP *v8; // rbx
  struct CPacket *Packet; // rax
  struct CPacket *v10; // rcx
  int v11; // edx
  ULONG_PTR Information; // rax
  int v13; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      48,
      WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
      this,
      a2,
      a3);
  }
  if ( a3 )
  {
    *((_WORD *)this + 26) = a3 | *((_WORD *)this + 26) & 0x1000;
    *((_DWORD *)this + 13) |= 0x20000u;
  }
  v6 = *(_QWORD *)(*((_QWORD *)this + 13) + 64LL);
  PacketRequest = CCreatePacket::GetCreatePacketRequest((CCreatePacket *)(v6 + 416), this);
  v8 = PacketRequest;
  if ( PacketRequest )
  {
    Packet = CIrp2Pkt::SafePeekFirstPacket(PacketRequest);
    v10 = Packet;
    if ( a2 < 0 )
    {
      (*(void (__fastcall **)(_QWORD, struct _IRP *))(**((_QWORD **)Packet + 4) + 160LL))(*((_QWORD *)Packet + 4), v8);
      v11 = a2;
LABEL_15:
      irp_safe_set_final_status(v8, v11);
      v8->IoStatus.Information = 0;
      IofCompleteRequest(v8, 2);
      return;
    }
    if ( (*(_DWORD *)(&v8->Tail.CompletionKey + 3) & 0x80) != 0 )
    {
      Information = v8->IoStatus.Information;
      if ( Information )
      {
        if ( *(_DWORD *)(Information + 20) )
        {
          CCreatePacket::HoldCreatePacketRequest((CCreatePacket *)(v6 + 416), v8);
          return;
        }
      }
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, struct _IRP *))(**((_QWORD **)v10 + 4) + 152LL))(*((_QWORD *)v10 + 4), v8);
    if ( v13 != 259 )
    {
      v11 = v13;
      goto LABEL_15;
    }
  }
}

```

## disassembly

```asm
0x140017694  push    rbx
0x140017696  push    rbp
0x140017697  push    rsi
0x140017698  push    rdi
0x140017699  sub     rsp, 38h
0x14001769d  movzx   edi, r8w
0x1400176a1  mov     esi, edx
0x1400176a3  mov     rbx, rcx
0x1400176a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400176ad  lea     rax, WPP_GLOBAL_Control
0x1400176b4  cmp     rcx, rax
0x1400176b7  jz      short loc_1400176E0
0x1400176b9  mov     eax, [rcx+6Ch]
0x1400176bc  test    al, 4
0x1400176be  jz      short loc_1400176E0
0x1400176c0  mov     rcx, [rcx+58h]
0x1400176c4  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x1400176cb  mov     edx, 30h ; '0'
0x1400176d0  mov     [rsp+58h+var_30], edi
0x1400176d4  mov     r9, rbx
0x1400176d7  mov     [rsp+58h+var_38], esi
0x1400176db  call    WPP_SF_qDD
0x1400176e0  xor     ebp, ebp
0x1400176e2  test    di, di
0x1400176e5  jz      short loc_1400176FF
0x1400176e7  movzx   eax, word ptr [rbx+34h]
0x1400176eb  mov     ecx, 1000h
0x1400176f0  and     ax, cx
0x1400176f3  or      ax, di
0x1400176f6  mov     [rbx+34h], ax
0x1400176fa  bts     dword ptr [rbx+34h], 11h
0x1400176ff  mov     rax, [rbx+68h]
0x140017703  mov     rdx, rbx; struct CPacket *
0x140017706  mov     rdi, [rax+40h]
0x14001770a  lea     rcx, [rdi+1A0h]; this
0x140017711  call    ?GetCreatePacketRequest@CCreatePacket@@QEAAPEAU_IRP@@PEAVCPacket@@@Z; CCreatePacket::GetCreatePacketRequest(CPacket *)
0x140017716  mov     rbx, rax
0x140017719  test    rax, rax
0x14001771c  jz      loc_1400177B3
0x140017722  mov     rcx, rax; struct _IRP *
0x140017725  call    ?SafePeekFirstPacket@CIrp2Pkt@@SAPEAVCPacket@@PEAU_IRP@@@Z; CIrp2Pkt::SafePeekFirstPacket(_IRP *)
0x14001772a  mov     rcx, rax
0x14001772d  test    esi, esi
0x14001772f  jns     short loc_14001774B
0x140017731  mov     rcx, [rax+20h]
0x140017735  mov     rdx, [rcx]
0x140017738  mov     rax, [rdx+0A0h]
0x14001773f  mov     rdx, rbx
0x140017742  call    _guard_dispatch_icall
0x140017747  mov     edx, esi
0x140017749  jmp     short loc_140017796
0x14001774b  mov     eax, [rbx+90h]
0x140017751  shr     eax, 7
0x140017754  test    al, 1
0x140017756  jz      short loc_140017777
0x140017758  mov     rax, [rbx+38h]
0x14001775c  test    rax, rax
0x14001775f  jz      short loc_140017777
0x140017761  cmp     [rax+14h], ebp
0x140017764  jz      short loc_140017777
0x140017766  mov     rdx, rbx; struct _IRP *
0x140017769  lea     rcx, [rdi+1A0h]; this
0x140017770  call    ?HoldCreatePacketRequest@CCreatePacket@@QEAAXPEAU_IRP@@@Z; CCreatePacket::HoldCreatePacketRequest(_IRP *)
0x140017775  jmp     short loc_1400177B3
0x140017777  mov     rcx, [rcx+20h]
0x14001777b  mov     rdx, rbx
0x14001777e  mov     rax, [rcx]
0x140017781  mov     rax, [rax+98h]
0x140017788  call    _guard_dispatch_icall
0x14001778d  cmp     eax, 103h
0x140017792  jz      short loc_1400177B3
0x140017794  mov     edx, eax; int
0x140017796  mov     rcx, rbx; struct _IRP *
0x140017799  call    ?irp_safe_set_final_status@@YAXPEAU_IRP@@J@Z; irp_safe_set_final_status(_IRP *,long)
0x14001779e  mov     dl, 2; PriorityBoost
0x1400177a0  mov     [rbx+38h], rbp
0x1400177a4  mov     rcx, rbx; Irp
0x1400177a7  call    cs:__imp_IofCompleteRequest
0x1400177ae  nop     dword ptr [rax+rax+00h]
0x1400177b3  add     rsp, 38h
0x1400177b7  pop     rdi
0x1400177b8  pop     rsi
0x1400177b9  pop     rbp
0x1400177ba  pop     rbx
0x1400177bb  retn
```
