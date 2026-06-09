# DrSession::PrivateSendToClient(void *,ulong,ISessionPacketSender *,long (*)(void *,_IO_STATUS_BLOCK *),int,int,void *)

- ea: `0x140024cf0`
- end: `0x140024ff9`
- name: `?PrivateSendToClient@DrSession@@AEAAJPEAXKPEAVISessionPacketSender@@P6AJ0PEAU_IO_STATUS_BLOCK@@@ZHH0@Z`
- size: `777`
- prototype: `__int64 __usercall@<rax>(DrSession *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, struct ISessionPacketSender *@<r9>, int (*)(void *, struct _IO_STATUS_BLOCK *), int, int, void *)`
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001ac10`
- `0x14001cc44`
- `0x14001d560`
- `0x14001d610`
- `0x14001d698`
- `0x14001d710`
- `0x140027fe0`

## callees

- `0x140001660`
- `0x140001890`
- `0x14000324c`
- `0x140006560`
- `0x140024cf0`
- `0x140025000`
- `0x140025228`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140024d89`
- `ntoskrnl!ExAllocatePool2` at `0x140024d89`
- `ntoskrnl!KeInitializeEvent` at `0x140024ec4`
- `ntoskrnl!KeInitializeEvent` at `0x140024ec4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140024d15`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140024d15`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024fe4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024fe4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140024d2a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140024d2a`

## pseudocode

```c
__int64 __fastcall DrSession::PrivateSendToClient(
        DrSession *this,
        void *a2,
        unsigned int a3,
        struct ISessionPacketSender *a4,
        int (*a5)(void *, struct _IO_STATUS_BLOCK *),
        int a6,
        int a7,
        void *a8)
{
  VirtualChannel *v12; // rbp
  __int64 Pool2; // rax
  _QWORD *v14; // rbx
  unsigned int v15; // ebx
  RefCount *v17; // rcx
  void *v18; // rcx
  _QWORD v19[2]; // [rsp+50h] [rbp-58h] BYREF
  _BYTE Event[32]; // [rsp+60h] [rbp-48h] BYREF

  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 480), 1u);
  v12 = (VirtualChannel *)*((_QWORD *)this + 5);
  if ( v12 )
  {
    RefCount::AddRef(*((RefCount **)this + 5));
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 58) + 32LL))((char *)this + 464);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x34u,
        (__int64)WPP_5c887063686c325024567ba4647d07cf_Traceguids);
    Pool2 = ExAllocatePool2(256, 56, 1917088324);
    v14 = (_QWORD *)Pool2;
    if ( Pool2 )
    {
      *(_QWORD *)(Pool2 + 16) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x35u,
          (__int64)WPP_5c887063686c325024567ba4647d07cf_Traceguids);
      v17 = (RefCount *)v14[2];
      if ( v17 )
        RefCount::Release(v17);
      v14[2] = this;
      RefCount::AddRef(this);
      v18 = a2;
      if ( !a6 )
        v18 = 0;
      v14[3] = v18;
      v14[6] = a5;
      v14[4] = a8;
      v14[5] = a4;
      if ( a6 )
      {
        v15 = VirtualChannel::SubmitIo(
                v12,
                (int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *))DrSession::SendCompletionRoutine,
                v14,
                a2,
                a3,
                4u,
                a6,
                1,
                a7);
      }
      else
      {
        v19[1] = v14;
        v19[0] = DrSession::SendCompletionRoutine;
        memset(Event, 0, sizeof(Event));
        KeInitializeEvent((PRKEVENT)Event, NotificationEvent, 0);
        v15 = VirtualChannel::Io(
                v12,
                (int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *))_ChannelWriteCompletionRoutine,
                v19,
                a2,
                a3,
                4u,
                1,
                a7,
                0);
        if ( v15 == 259 )
        {
          KeWaitForSingleObject(Event, Executive, 0, 0, 0);
          v15 = *(_DWORD *)&Event[24];
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x36u,
          (__int64)WPP_5c887063686c325024567ba4647d07cf_Traceguids);
      v15 = -1073741670;
    }
    RefCount::Release(v12);
    return v15;
  }
  else
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 58) + 32LL))((char *)this + 464);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x37u,
        (__int64)WPP_5c887063686c325024567ba4647d07cf_Traceguids);
    return 3221225629LL;
  }
}

```

## disassembly

```asm
0x140024cf0  mov     [rsp+arg_8], rbx
0x140024cf5  mov     [rsp+arg_10], rbp
0x140024cfa  push    rsi
0x140024cfb  push    rdi
0x140024cfc  push    r12
0x140024cfe  push    r14
0x140024d00  push    r15
0x140024d02  sub     rsp, 80h
0x140024d09  mov     r15, r9
0x140024d0c  mov     r12d, r8d
0x140024d0f  mov     r14, rdx
0x140024d12  mov     rsi, rcx
0x140024d15  call    cs:__imp_KeEnterCriticalRegion
0x140024d1c  nop     dword ptr [rax+rax+00h]
0x140024d21  lea     rcx, [rsi+1E0h]; Resource
0x140024d28  mov     dl, 1; Wait
0x140024d2a  call    cs:__imp_ExAcquireResourceSharedLite
0x140024d31  nop     dword ptr [rax+rax+00h]
0x140024d36  mov     rbp, [rsi+28h]
0x140024d3a  test    rbp, rbp
0x140024d3d  jz      loc_140024DD2
0x140024d43  mov     rcx, rbp; this
0x140024d46  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140024d4b  mov     rax, [rsi+1D0h]
0x140024d52  lea     rcx, [rsi+1D0h]
0x140024d59  mov     rax, [rax+20h]
0x140024d5d  call    _guard_dispatch_icall
0x140024d62  mov     rcx, cs:WPP_GLOBAL_Control
0x140024d69  lea     rdi, WPP_GLOBAL_Control
0x140024d70  cmp     rcx, rdi
0x140024d73  jnz     loc_140024F54
0x140024d79  mov     edx, 38h ; '8'
0x140024d7e  mov     ecx, 100h
0x140024d83  mov     r8d, 72447244h
0x140024d89  call    cs:__imp_ExAllocatePool2
0x140024d90  nop     dword ptr [rax+rax+00h]
0x140024d95  mov     rbx, rax
0x140024d98  test    rax, rax
0x140024d9b  jnz     loc_140024E22
0x140024da1  mov     rcx, cs:WPP_GLOBAL_Control
0x140024da8  cmp     rcx, rdi
0x140024dab  jz      short loc_140024DC8
0x140024dad  cmp     byte ptr [rcx+29h], 2
0x140024db1  jb      short loc_140024DC8
0x140024db3  mov     rcx, [rcx+18h]
0x140024db7  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140024dbe  mov     edx, 36h ; '6'
0x140024dc3  call    WPP_SF_
0x140024dc8  mov     ebx, 0C000009Ah
0x140024dcd  jmp     loc_140024F21
0x140024dd2  mov     rax, [rsi+1D0h]
0x140024dd9  lea     rcx, [rsi+1D0h]
0x140024de0  mov     rax, [rax+20h]
0x140024de4  call    _guard_dispatch_icall
0x140024de9  mov     rcx, cs:WPP_GLOBAL_Control
0x140024df0  lea     rdi, WPP_GLOBAL_Control
0x140024df7  cmp     rcx, rdi
0x140024dfa  jnz     loc_140024F30
0x140024e00  mov     eax, 0C000009Dh
0x140024e05  lea     r11, [rsp+0A8h+var_28]
0x140024e0d  mov     rbx, [r11+38h]
0x140024e11  mov     rbp, [r11+40h]
0x140024e15  mov     rsp, r11
0x140024e18  pop     r15
0x140024e1a  pop     r14
0x140024e1c  pop     r12
0x140024e1e  pop     rdi
0x140024e1f  pop     rsi
0x140024e20  retn
0x140024e22  mov     [rsp+0A8h+arg_0], r13
0x140024e2a  xor     r13d, r13d
0x140024e2d  mov     [rax+10h], r13
0x140024e31  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e38  cmp     rcx, rdi
0x140024e3b  jz      short loc_140024E47
0x140024e3d  cmp     byte ptr [rcx+29h], 5
0x140024e41  jnb     loc_140024F78
0x140024e47  mov     rcx, [rbx+10h]; this
0x140024e4b  test    rcx, rcx
0x140024e4e  jz      short loc_140024E55
0x140024e50  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140024e55  mov     rcx, rsi; this
0x140024e58  mov     [rbx+10h], rsi
0x140024e5c  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140024e61  mov     rax, [rsp+0A8h+arg_20]
0x140024e69  mov     rcx, r14
0x140024e6c  mov     edx, [rsp+0A8h+arg_28]
0x140024e73  test    edx, edx
0x140024e75  cmovz   rcx, r13
0x140024e79  mov     [rbx+18h], rcx
0x140024e7d  mov     [rbx+30h], rax
0x140024e81  mov     rax, [rsp+0A8h+arg_38]
0x140024e89  mov     [rbx+20h], rax
0x140024e8d  mov     [rbx+28h], r15
0x140024e91  jnz     loc_140024F92
0x140024e97  xorps   xmm0, xmm0
0x140024e9a  mov     [rsp+0A8h+var_50], rbx
0x140024e9f  xorps   xmm1, xmm1
0x140024ea2  lea     rax, ?SendCompletionRoutine@DrSession@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; DrSession::SendCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140024ea9  xor     r8d, r8d; State
0x140024eac  mov     [rsp+0A8h+var_58], rax
0x140024eb1  xor     edx, edx; Type
0x140024eb3  lea     rcx, [rsp+0A8h+Event]; Event
0x140024eb8  movdqu  xmmword ptr [rsp+0A8h+Event], xmm0
0x140024ebe  movdqu  xmmword ptr [rsp+0A8h+Event+10h], xmm1
0x140024ec4  call    cs:__imp_KeInitializeEvent
0x140024ecb  nop     dword ptr [rax+rax+00h]
0x140024ed0  mov     eax, [rsp+0A8h+arg_30]
0x140024ed7  lea     r8, [rsp+0A8h+var_58]; void *
0x140024edc  mov     [rsp+0A8h+var_68], r13d; int
0x140024ee1  lea     rdx, ?_ChannelWriteCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)
0x140024ee8  mov     [rsp+0A8h+var_70], eax; int
0x140024eec  mov     r9, r14; void *
0x140024eef  mov     [rsp+0A8h+var_78], 1; int
0x140024ef7  mov     rcx, rbp; this
0x140024efa  mov     [rsp+0A8h+var_80], 4; unsigned int
0x140024f02  mov     dword ptr [rsp+0A8h+Timeout], r12d; unsigned int
0x140024f07  call    ?Io@VirtualChannel@@AEAAJP6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z22KKHHH@Z; VirtualChannel::Io(long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *,void *,ulong,ulong,int,int,int)
0x140024f0c  mov     ebx, eax
0x140024f0e  cmp     eax, 103h
0x140024f13  jz      loc_140024FD2
0x140024f19  mov     r13, [rsp+0A8h+arg_0]
0x140024f21  mov     rcx, rbp; this
0x140024f24  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140024f29  mov     eax, ebx
0x140024f2b  jmp     loc_140024E05
0x140024f30  cmp     byte ptr [rcx+29h], 4
0x140024f34  jb      loc_140024E00
0x140024f3a  mov     rcx, [rcx+18h]
0x140024f3e  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140024f45  mov     edx, 37h ; '7'
0x140024f4a  call    WPP_SF_
0x140024f4f  jmp     loc_140024E00
0x140024f54  cmp     byte ptr [rcx+29h], 5
0x140024f58  jb      loc_140024D79
0x140024f5e  mov     rcx, [rcx+18h]
0x140024f62  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140024f69  mov     edx, 34h ; '4'
0x140024f6e  call    WPP_SF_
0x140024f73  jmp     loc_140024D79
0x140024f78  mov     rcx, [rcx+18h]
0x140024f7c  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140024f83  mov     edx, 35h ; '5'
0x140024f88  call    WPP_SF_
0x140024f8d  jmp     loc_140024E47
0x140024f92  mov     eax, [rsp+0A8h+arg_30]
0x140024f99  mov     r9, r14; void *
0x140024f9c  mov     [rsp+0A8h+var_68], eax; int
0x140024fa0  mov     r8, rbx; void *
0x140024fa3  mov     [rsp+0A8h+var_70], 1; int
0x140024fab  mov     rcx, rbp; this
0x140024fae  mov     [rsp+0A8h+var_78], edx; int
0x140024fb2  lea     rdx, ?SendCompletionRoutine@DrSession@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)
0x140024fb9  mov     [rsp+0A8h+var_80], 4; unsigned int
0x140024fc1  mov     dword ptr [rsp+0A8h+Timeout], r12d; unsigned int
0x140024fc6  call    ?SubmitIo@VirtualChannel@@AEAAJP6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z22KKHHH@Z; VirtualChannel::SubmitIo(long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *,void *,ulong,ulong,int,int,int)
0x140024fcb  mov     ebx, eax
0x140024fcd  jmp     loc_140024F19
0x140024fd2  xor     r9d, r9d; Alertable
0x140024fd5  mov     [rsp+0A8h+Timeout], r13; Timeout
0x140024fda  xor     r8d, r8d; WaitMode
0x140024fdd  lea     rcx, [rsp+0A8h+Event]; Object
0x140024fe2  xor     edx, edx; WaitReason
0x140024fe4  call    cs:__imp_KeWaitForSingleObject
0x140024feb  nop     dword ptr [rax+rax+00h]
0x140024ff0  mov     ebx, dword ptr [rsp+0A8h+Event+18h]
0x140024ff4  jmp     loc_140024F19
```
