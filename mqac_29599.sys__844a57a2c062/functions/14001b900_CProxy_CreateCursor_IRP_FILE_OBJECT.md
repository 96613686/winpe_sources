# CProxy::CreateCursor(_IRP *,_FILE_OBJECT *)

- ea: `0x14001b900`
- end: `0x14001b9cf`
- name: `?CreateCursor@CProxy@@UEAAJPEAU_IRP@@PEAU_FILE_OBJECT@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(CProxy *__hidden this, struct _IRP *, struct _FILE_OBJECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140019f04`
- `0x14001b114`
- `0x14001b900`

## pseudocode

```c
int __fastcall CProxy::CreateCursor(struct _LIST_ENTRY *this, struct _IRP *a2, struct _FILE_OBJECT *a3)
{
  unsigned __int16 v5; // ax
  unsigned int v6; // edx
  int result; // eax
  _BYTE v8[16]; // [rsp+30h] [rbp-F8h] BYREF
  int v9; // [rsp+40h] [rbp-E8h]
  struct _LIST_ENTRY *Blink; // [rsp+48h] [rbp-E0h]
  int v11; // [rsp+50h] [rbp-D8h]

  a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = 0;
  a2->Tail.Overlay.DriverContext[2] = 0;
  a2->Tail.Overlay.DriverContext[3] = 0;
  v5 = g_IrpTag;
  a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = this;
  g_IrpTag = v5 + 1;
  v6 = *(_DWORD *)(&a2->Tail.CompletionKey + 3) & 0xFF0000FB | ((unsigned __int16)(v5 + 1) << 8);
  v9 = 7;
  v11 = (unsigned __int16)(v5 + 1);
  *((_DWORD *)&a2->Tail.CompletionKey + 6) = v6 & 0xFFFFFFD4 | 3;
  Blink = this[9].Blink;
  result = CQMInterface::ProcessRequest((CQMInterface *)&this[4].Flink[4].Flink[4].Blink, (const struct CACRequest *)v8);
  if ( result >= 0 )
    return CQueueBase::HoldRequest(
             (CQueueBase *)this,
             a2,
             0xFFFFFFFF,
             (void (*)(struct _DEVICE_OBJECT *, struct _IRP *))ACCancelRemoteQueueOperation,
             0);
  return result;
}

```

## disassembly

```asm
0x14001b900  mov     [rsp+arg_0], rbx
0x14001b905  push    rdi
0x14001b906  sub     rsp, 120h
0x14001b90d  mov     qword ptr [rdx+80h], 0
0x14001b918  mov     rbx, rdx
0x14001b91b  mov     qword ptr [rdx+88h], 0
0x14001b926  mov     rdi, rcx
0x14001b929  mov     qword ptr [rdx+90h], 0
0x14001b934  movzx   eax, cs:?g_IrpTag@@3GA; ushort g_IrpTag
0x14001b93b  mov     [rdx+78h], rcx
0x14001b93f  inc     ax
0x14001b942  movzx   r8d, ax
0x14001b946  mov     cs:?g_IrpTag@@3GA, ax; ushort g_IrpTag
0x14001b94d  mov     edx, r8d
0x14001b950  mov     eax, [rbx+90h]
0x14001b956  shl     edx, 8
0x14001b959  and     eax, 0FF0000FBh
0x14001b95e  or      edx, eax
0x14001b960  mov     [rsp+128h+var_E8], 7
0x14001b968  and     edx, 0FFFFFFD7h
0x14001b96b  mov     [rsp+128h+var_D8], r8d
0x14001b970  or      edx, 3
0x14001b973  mov     [rbx+90h], edx
0x14001b979  lea     rdx, [rsp+128h+var_F8]; struct CACRequest *
0x14001b97e  mov     rax, [rcx+98h]
0x14001b985  mov     [rsp+128h+var_E0], rax
0x14001b98a  mov     rax, [rcx+40h]
0x14001b98e  mov     rcx, [rax+40h]
0x14001b992  add     rcx, 48h ; 'H'; this
0x14001b996  call    ?ProcessRequest@CQMInterface@@QEAAJAEBVCACRequest@@@Z; CQMInterface::ProcessRequest(CACRequest const &)
0x14001b99b  test    eax, eax
0x14001b99d  js      short loc_14001B9BD
0x14001b99f  lea     r9, ACCancelRemoteQueueOperation; void (*)(struct _DEVICE_OBJECT *, struct _IRP *)
0x14001b9a6  mov     [rsp+128h+var_108], 0; int
0x14001b9ae  or      r8d, 0FFFFFFFFh; unsigned int
0x14001b9b2  mov     rdx, rbx; struct _IRP *
0x14001b9b5  mov     rcx, rdi; this
0x14001b9b8  call    ?HoldRequest@CQueueBase@@IEAAJPEAU_IRP@@KP6AXPEAU_DEVICE_OBJECT@@0@ZH@Z; CQueueBase::HoldRequest(_IRP *,ulong,void (*)(_DEVICE_OBJECT *,_IRP *),int)
0x14001b9bd  mov     rbx, [rsp+128h+arg_0]
0x14001b9c5  add     rsp, 120h
0x14001b9cc  pop     rdi
0x14001b9cd  retn
```
