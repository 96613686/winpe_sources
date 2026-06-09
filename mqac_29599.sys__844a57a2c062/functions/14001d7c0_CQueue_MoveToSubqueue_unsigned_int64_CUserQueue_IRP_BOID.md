# CQueue::MoveToSubqueue(unsigned __int64,CUserQueue *,_IRP *,BOID *)

- ea: `0x14001d7c0`
- end: `0x14001d9dd`
- name: `?MoveToSubqueue@CQueue@@UEAAJ_KPEAVCUserQueue@@PEAU_IRP@@PEAUBOID@@@Z`
- size: `541`
- prototype: `__int64 __fastcall(CQueue *__hidden this, unsigned __int64, struct CUserQueue *, struct _IRP *, struct BOID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140001c04`
- `0x140001c34`
- `0x140003d84`
- `0x140018150`
- `0x14001821c`
- `0x14001d7c0`
- `0x14001da60`
- `0x140024bf0`

## pseudocode

```c
__int64 __fastcall CQueue::MoveToSubqueue(
        CQueue *this,
        unsigned __int64 a2,
        struct CUserQueue *a3,
        struct _IRP *a4,
        struct BOID *a5)
{
  __int64 (__fastcall *v9)(CQueue *); // rdi
  __int64 v10; // rbx
  struct CPacket *v12; // rax
  CPacket *v13; // r9
  int v14; // eax
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx

  if ( !a3 || a3 == this )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return 3221225485LL;
    }
    v16 = 17;
    goto LABEL_32;
  }
  if ( !(*(__int64 (__fastcall **)(CQueue *))(*(_QWORD *)this + 104LL))(this)
    || (v9 = *(__int64 (__fastcall **)(CQueue *))(*(_QWORD *)this + 104LL),
        v10 = (*(__int64 (__fastcall **)(struct CUserQueue *))(*(_QWORD *)a3 + 104LL))(a3),
        v9(this) != v10) )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return 3221225485LL;
    }
    v16 = 18;
LABEL_32:
    WPP_SF_(v15->Queue.ListEntry.Blink, v16, &WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids);
    return 3221225485LL;
  }
  if ( !a5 || (*((_DWORD *)this + 14) & 2) != 0 )
  {
    v12 = CQueue::PeekCurrentPacketByLookupId(this, a2, 1);
    v13 = v12;
    if ( v12 )
    {
      a4->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
      a4->Tail.Overlay.DriverContext[3] = 0;
      *((_DWORD *)&a4->Tail.CompletionKey + 6) = *(_DWORD *)(&a4->Tail.CompletionKey + 3) & 0xFFFFFFF8 | 2;
      a4->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = &a4->Tail.Overlay.DeviceQueueEntry.DeviceListEntry;
      a4->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = &a4->Tail.Overlay.DeviceQueueEntry.DeviceListEntry;
      *((_DWORD *)&a4->Tail.CompletionKey + 6) |= 0x28u;
      a4->Tail.Overlay.DriverContext[2] = 0;
      v14 = *((_DWORD *)v12 + 13);
      if ( (v14 & 0x20000) != 0 || v14 < 0 || (v14 & 0x40000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->Queue.ListEntry.Blink,
            50,
            &WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
            *((_QWORD *)v13 + 7));
        }
        return 3222143132LL;
      }
      else if ( a5 )
      {
        return CPacket::MoveToSubqueueInXact(v13, a3, a5);
      }
      else
      {
        return CPacket::MoveToSubqueueNoXact(v13, a3, a4);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 20, &WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids, a2);
      }
      return 3222143112LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        19,
        &WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids,
        3222143056LL);
    }
    return 3222143056LL;
  }
}

```

## disassembly

```asm
0x14001d7c0  push    rbx
0x14001d7c2  push    rbp
0x14001d7c3  push    rsi
0x14001d7c4  push    rdi
0x14001d7c5  push    r14
0x14001d7c7  push    r15
0x14001d7c9  sub     rsp, 28h
0x14001d7cd  mov     rbp, r9
0x14001d7d0  mov     r14, r8
0x14001d7d3  mov     r15, rdx
0x14001d7d6  mov     rsi, rcx
0x14001d7d9  test    r8, r8
0x14001d7dc  jz      loc_14001D99B
0x14001d7e2  cmp     r8, rcx
0x14001d7e5  jz      loc_14001D99B
0x14001d7eb  mov     rax, [rcx]
0x14001d7ee  mov     rax, [rax+68h]
0x14001d7f2  call    _guard_dispatch_icall
0x14001d7f7  test    rax, rax
0x14001d7fa  jz      loc_14001D97A
0x14001d800  mov     rcx, [rsi]
0x14001d803  mov     rax, [r14]
0x14001d806  mov     rdi, [rcx+68h]
0x14001d80a  mov     rcx, r14
0x14001d80d  mov     rax, [rax+68h]
0x14001d811  call    _guard_dispatch_icall
0x14001d816  mov     rbx, rax
0x14001d819  mov     rcx, rsi
0x14001d81c  mov     rax, rdi
0x14001d81f  call    _guard_dispatch_icall
0x14001d824  cmp     rax, rbx
0x14001d827  jnz     loc_14001D97A
0x14001d82d  mov     rbx, [rsp+58h+arg_20]
0x14001d835  test    rbx, rbx
0x14001d838  jz      short loc_14001D880
0x14001d83a  mov     eax, [rsi+38h]
0x14001d83d  test    al, 2
0x14001d83f  jnz     short loc_14001D880
0x14001d841  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d848  lea     rax, WPP_GLOBAL_Control
0x14001d84f  mov     ebx, 0C00E0050h
0x14001d854  cmp     rcx, rax
0x14001d857  jz      short loc_14001D879
0x14001d859  mov     edx, [rcx+6Ch]
0x14001d85c  test    dl, 1
0x14001d85f  jz      short loc_14001D879
0x14001d861  mov     rcx, [rcx+58h]
0x14001d865  lea     r8, WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids
0x14001d86c  mov     edx, 13h
0x14001d871  mov     r9d, ebx
0x14001d874  call    WPP_SF_d
0x14001d879  mov     eax, ebx
0x14001d87b  jmp     loc_14001D9CF
0x14001d880  mov     r8b, 1; bool
0x14001d883  mov     rdx, r15; unsigned __int64
0x14001d886  mov     rcx, rsi; this
0x14001d889  call    ?PeekCurrentPacketByLookupId@CQueue@@AEBAPEAVCPacket@@_K_N@Z; CQueue::PeekCurrentPacketByLookupId(unsigned __int64,bool)
0x14001d88e  mov     r9, rax
0x14001d891  test    rax, rax
0x14001d894  jnz     short loc_14001D8D1
0x14001d896  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d89d  lea     rax, WPP_GLOBAL_Control
0x14001d8a4  cmp     rcx, rax
0x14001d8a7  jz      short loc_14001D8C7
0x14001d8a9  mov     eax, [rcx+6Ch]
0x14001d8ac  test    al, 1
0x14001d8ae  jz      short loc_14001D8C7
0x14001d8b0  mov     rcx, [rcx+58h]
0x14001d8b4  lea     edx, [r9+14h]
0x14001d8b8  mov     r9, r15
0x14001d8bb  lea     r8, WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids
0x14001d8c2  call    WPP_SF_q
0x14001d8c7  mov     eax, 0C00E0088h
0x14001d8cc  jmp     loc_14001D9CF
0x14001d8d1  mov     qword ptr [rbp+78h], 0
0x14001d8d9  lea     rcx, [rbp+78h]
0x14001d8dd  mov     qword ptr [rbp+90h], 0
0x14001d8e8  mov     eax, [rcx+18h]
0x14001d8eb  and     eax, 0FFFFFFFAh
0x14001d8ee  or      eax, 2
0x14001d8f1  mov     [rcx+18h], eax
0x14001d8f4  mov     [rcx+8], rcx
0x14001d8f8  mov     [rcx], rcx
0x14001d8fb  or      dword ptr [rcx+18h], 28h
0x14001d8ff  mov     qword ptr [rcx+10h], 0
0x14001d907  mov     eax, [r9+34h]
0x14001d90b  bt      eax, 11h
0x14001d90f  jb      short loc_14001D940
0x14001d911  test    eax, eax
0x14001d913  js      short loc_14001D940
0x14001d915  bt      eax, 12h
0x14001d919  jb      short loc_14001D940
0x14001d91b  mov     rdx, r14; struct CQueue *
0x14001d91e  mov     rcx, r9; this
0x14001d921  test    rbx, rbx
0x14001d924  jz      short loc_14001D933
0x14001d926  mov     r8, rbx; struct BOID *
0x14001d929  call    ?MoveToSubqueueInXact@CPacket@@AEAAJPEAVCQueue@@PEAUBOID@@@Z; CPacket::MoveToSubqueueInXact(CQueue *,BOID *)
0x14001d92e  jmp     loc_14001D9CF
0x14001d933  mov     r8, rbp; struct _IRP *
0x14001d936  call    ?MoveToSubqueueNoXact@CPacket@@AEAAJPEAVCQueue@@PEAU_IRP@@@Z; CPacket::MoveToSubqueueNoXact(CQueue *,_IRP *)
0x14001d93b  jmp     loc_14001D9CF
0x14001d940  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d947  lea     rax, WPP_GLOBAL_Control
0x14001d94e  cmp     rcx, rax
0x14001d951  jz      short loc_14001D973
0x14001d953  mov     eax, [rcx+6Ch]
0x14001d956  test    al, 1
0x14001d958  jz      short loc_14001D973
0x14001d95a  mov     r9, [r9+38h]
0x14001d95e  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x14001d965  mov     rcx, [rcx+58h]
0x14001d969  mov     edx, 32h ; '2'
0x14001d96e  call    WPP_SF_q
0x14001d973  mov     eax, 0C00E009Ch
0x14001d978  jmp     short loc_14001D9CF
0x14001d97a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d981  lea     rax, WPP_GLOBAL_Control
0x14001d988  cmp     rcx, rax
0x14001d98b  jz      short loc_14001D9CA
0x14001d98d  mov     eax, [rcx+6Ch]
0x14001d990  test    al, 1
0x14001d992  jz      short loc_14001D9CA
0x14001d994  mov     edx, 12h
0x14001d999  jmp     short loc_14001D9BA
0x14001d99b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d9a2  lea     rax, WPP_GLOBAL_Control
0x14001d9a9  cmp     rcx, rax
0x14001d9ac  jz      short loc_14001D9CA
0x14001d9ae  mov     eax, [rcx+6Ch]
0x14001d9b1  test    al, 1
0x14001d9b3  jz      short loc_14001D9CA
0x14001d9b5  mov     edx, 11h
0x14001d9ba  mov     rcx, [rcx+58h]
0x14001d9be  lea     r8, WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids
0x14001d9c5  call    WPP_SF_
0x14001d9ca  mov     eax, 0C000000Dh
0x14001d9cf  add     rsp, 28h
0x14001d9d3  pop     r15
0x14001d9d5  pop     r14
0x14001d9d7  pop     rdi
0x14001d9d8  pop     rsi
0x14001d9d9  pop     rbp
0x14001d9da  pop     rbx
0x14001d9db  retn
```
