# CQueue::CreatePacket(_IRP *,CTransaction *,int,CACSendParameters const *,ACSendParametersPointerContents const *)

- ea: `0x14001cd90`
- end: `0x14001cf76`
- name: `?CreatePacket@CQueue@@EEAAJPEAU_IRP@@PEAVCTransaction@@HPEBVCACSendParameters@@PEBUACSendParametersPointerContents@@@Z`
- size: `486`
- prototype: `__int64 __usercall@<rax>(CQueue *__hidden this@<rcx>, struct _IRP *@<rdx>, struct CTransaction *@<r8>, int@<r9d>, const struct CACSendParameters *, const struct ACSendParametersPointerContents *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140001cb0`
- `0x140001df4`
- `0x140002094`
- `0x140012754`
- `0x140017b04`
- `0x1400194ec`
- `0x14001cd90`
- `0x14001d9e4`
- `0x140024bb0`
- `0x140024bf0`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14001ce10`
- `ntoskrnl!IoGetCurrentProcess` at `0x14001ce10`
- `ntoskrnl!EtwActivityIdControl` at `0x14001cebb`
- `ntoskrnl!EtwActivityIdControl` at `0x14001cebb`

## pseudocode

```c
__int64 __fastcall CQueue::CreatePacket(
        CQueue *this,
        struct _IRP *a2,
        struct CTransaction *a3,
        int a4,
        const struct CACSendParameters *a5,
        const struct ACSendParametersPointerContents *a6)
{
  __int64 v9; // rax
  __int64 v10; // rbx
  int v11; // r15d
  struct _KPROCESS *v12; // rbx
  int v13; // ebp
  bool v14; // di
  bool v15; // bp
  struct _DEVICE_OBJECT *v16; // rcx
  __int64 result; // rax
  CBaseObject *v18; // rbx
  struct CPacketBuffer *v19; // r15
  int PacketRequest; // edi
  CBaseObject *v21; // [rsp+60h] [rbp-68h] BYREF
  struct ACSendParametersPointerContents *v22; // [rsp+68h] [rbp-60h]
  struct CTransaction *v23; // [rsp+70h] [rbp-58h]
  GUID ActivityId; // [rsp+78h] [rbp-50h] BYREF

  v22 = a6;
  v9 = *((_QWORD *)this + 8);
  v23 = a3;
  v10 = *(_QWORD *)(v9 + 64);
  *((_DWORD *)&a2->Tail.CompletionKey + 6) &= ~0x80u;
  v11 = *((_DWORD *)a5 + 144);
  v12 = *(struct _KPROCESS **)(v10 + 80);
  v13 = *((_DWORD *)a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext2 + 5) & 2;
  v14 = v13 != 0;
  if ( IoGetCurrentProcess() == v12 )
  {
    v14 = v13 || (v11 & 1) != 0;
    v15 = 1;
  }
  else
  {
    v15 = 0;
  }
  v16 = (struct _DEVICE_OBJECT *)*((_QWORD *)this + 8);
  v21 = 0;
  result = CPacket::SyncCreate(v16, a2, v23, this, 1u, (CQueue *)((char *)this + 88), a4, a5, v22, this, v14, &v21);
  if ( (int)result >= 0 )
  {
    v18 = v21;
    v19 = CQEntry::Buffer(v21);
    ActivityId = 0;
    EtwActivityIdControl(1u, &ActivityId);
    E2ETraceMessageSend(v18, &ActivityId);
    if ( (*(unsigned int (__fastcall **)(CQueue *))(*(_QWORD *)this + 32LL))(this) )
      E2ETraceMessageInQueue(v18);
    if ( CQueue::NeedAsyncCreatePacket(this, v19, v14, v15) )
    {
      PacketRequest = CPacket::IssueCreatePacketRequest(v18, v14);
      if ( PacketRequest >= 0 )
      {
        return 259;
      }
      else
      {
        a2->IoStatus.Information = 0;
        *((_QWORD *)v18 + 4) = 0;
        *((_QWORD *)v18 + 5) = 0;
        CBaseObject::Release(v18);
        CBaseObject::Release(v18);
        return (unsigned int)PacketRequest;
      }
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001cd90  mov     [rsp+arg_10], rbx
0x14001cd95  push    rbp
0x14001cd96  push    rsi
0x14001cd97  push    rdi
0x14001cd98  push    r12
0x14001cd9a  push    r13
0x14001cd9c  push    r14
0x14001cd9e  push    r15
0x14001cda0  sub     rsp, 90h
0x14001cda7  mov     rax, cs:__security_cookie
0x14001cdae  xor     rax, rsp
0x14001cdb1  mov     [rsp+0C8h+var_40], rax
0x14001cdb9  mov     rax, [rsp+0C8h+arg_28]
0x14001cdc1  mov     rsi, rcx
0x14001cdc4  mov     r13, [rsp+0C8h+arg_20]
0x14001cdcc  mov     r12d, r9d
0x14001cdcf  mov     [rsp+0C8h+var_60], rax
0x14001cdd4  mov     r14, rdx
0x14001cdd7  mov     rax, [rcx+40h]
0x14001cddb  mov     [rsp+0C8h+var_58], r8
0x14001cde0  mov     rbx, [rax+40h]
0x14001cde4  btr     dword ptr [rdx+90h], 7
0x14001cdec  mov     rax, [rdx+0B8h]
0x14001cdf3  mov     r15d, [r13+240h]
0x14001cdfa  mov     rbx, [rbx+50h]
0x14001cdfe  mov     rcx, [rax+30h]
0x14001ce02  mov     rax, [rcx+20h]
0x14001ce06  mov     ebp, [rax+14h]
0x14001ce09  and     ebp, 2
0x14001ce0c  setnz   dil
0x14001ce10  call    cs:__imp_IoGetCurrentProcess
0x14001ce17  nop     dword ptr [rax+rax+00h]
0x14001ce1c  cmp     rax, rbx
0x14001ce1f  jnz     short loc_14001CE38
0x14001ce21  test    ebp, ebp
0x14001ce23  jnz     short loc_14001CE30
0x14001ce25  test    r15b, 1
0x14001ce29  jnz     short loc_14001CE30
0x14001ce2b  xor     dil, dil
0x14001ce2e  jmp     short loc_14001CE33
0x14001ce30  mov     dil, 1
0x14001ce33  mov     bpl, 1
0x14001ce36  jmp     short loc_14001CE3B
0x14001ce38  xor     bpl, bpl
0x14001ce3b  mov     r8, [rsp+0C8h+var_58]; struct CTransaction *
0x14001ce40  lea     rcx, [rsp+0C8h+var_68]
0x14001ce45  mov     [rsp+0C8h+var_70], rcx; struct CPacket **
0x14001ce4a  lea     rax, [rsi+58h]
0x14001ce4e  mov     rcx, [rsp+0C8h+var_60]
0x14001ce53  mov     r9, rsi; struct CQueue *
0x14001ce56  mov     [rsp+0C8h+var_78], dil; bool
0x14001ce5b  mov     rdx, r14; struct _IRP *
0x14001ce5e  mov     [rsp+0C8h+var_80], rsi; struct CQueue *
0x14001ce63  mov     [rsp+0C8h+var_88], rcx; struct ACSendParametersPointerContents *
0x14001ce68  mov     rcx, [rsi+40h]; struct _DEVICE_OBJECT *
0x14001ce6c  mov     [rsp+0C8h+var_90], r13; struct CACSendParameters *
0x14001ce71  mov     [rsp+0C8h+var_98], r12d; int
0x14001ce76  mov     [rsp+0C8h+var_A0], rax; struct QUEUE_FORMAT *
0x14001ce7b  mov     [rsp+0C8h+var_A8], 1; unsigned int
0x14001ce83  mov     [rsp+0C8h+var_68], 0
0x14001ce8c  call    ?SyncCreate@CPacket@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAVCTransaction@@PEAVCQueue@@KQEBUQUEUE_FORMAT@@HPEBVCACSendParameters@@PEBUACSendParametersPointerContents@@3_NPEAPEAV1@@Z; CPacket::SyncCreate(_DEVICE_OBJECT *,_IRP *,CTransaction *,CQueue *,ulong,QUEUE_FORMAT const * const,int,CACSendParameters const *,ACSendParametersPointerContents const *,CQueue *,bool,CPacket * *)
0x14001ce91  test    eax, eax
0x14001ce93  js      loc_14001CF4A
0x14001ce99  mov     rbx, [rsp+0C8h+var_68]
0x14001ce9e  mov     rcx, rbx; this
0x14001cea1  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001cea6  xorps   xmm0, xmm0
0x14001cea9  lea     rdx, [rsp+0C8h+ActivityId]; ActivityId
0x14001ceae  mov     ecx, 1; ControlCode
0x14001ceb3  mov     r15, rax
0x14001ceb6  movups  xmmword ptr [rsp+0C8h+ActivityId.Data1], xmm0
0x14001cebb  call    cs:__imp_EtwActivityIdControl
0x14001cec2  nop     dword ptr [rax+rax+00h]
0x14001cec7  lea     rdx, [rsp+0C8h+ActivityId]; RelatedActivityId
0x14001cecc  mov     rcx, rbx; struct CPacket *
0x14001cecf  call    ?E2ETraceMessageSend@@YAXPEAVCPacket@@PEAU_GUID@@@Z; E2ETraceMessageSend(CPacket *,_GUID *)
0x14001ced4  mov     rcx, [rsi]
0x14001ced7  mov     rax, [rcx+20h]
0x14001cedb  mov     rcx, rsi
0x14001cede  call    _guard_dispatch_icall
0x14001cee3  test    eax, eax
0x14001cee5  jz      short loc_14001CEEF
0x14001cee7  mov     rcx, rbx; struct CPacket *
0x14001ceea  call    ?E2ETraceMessageInQueue@@YAXPEAVCPacket@@@Z; E2ETraceMessageInQueue(CPacket *)
0x14001ceef  mov     r9b, bpl; bool
0x14001cef2  mov     r8b, dil; bool
0x14001cef5  mov     rdx, r15; struct CPacketBuffer *
0x14001cef8  mov     rcx, rsi; this
0x14001cefb  call    ?NeedAsyncCreatePacket@CQueue@@QEBA_NPEAVCPacketBuffer@@_N1@Z; CQueue::NeedAsyncCreatePacket(CPacketBuffer *,bool,bool)
0x14001cf00  test    al, al
0x14001cf02  jnz     short loc_14001CF08
0x14001cf04  xor     eax, eax
0x14001cf06  jmp     short loc_14001CF4A
0x14001cf08  mov     dl, dil; bool
0x14001cf0b  mov     rcx, rbx; this
0x14001cf0e  call    ?IssueCreatePacketRequest@CPacket@@QEAAJ_N@Z; CPacket::IssueCreatePacketRequest(bool)
0x14001cf13  mov     edi, eax
0x14001cf15  test    eax, eax
0x14001cf17  jns     short loc_14001CF45
0x14001cf19  mov     qword ptr [r14+38h], 0
0x14001cf21  mov     rcx, rbx; this
0x14001cf24  mov     qword ptr [rbx+20h], 0
0x14001cf2c  mov     qword ptr [rbx+28h], 0
0x14001cf34  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001cf39  mov     rcx, rbx; this
0x14001cf3c  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001cf41  mov     eax, edi
0x14001cf43  jmp     short loc_14001CF4A
0x14001cf45  mov     eax, 103h
0x14001cf4a  mov     rcx, [rsp+0C8h+var_40]
0x14001cf52  xor     rcx, rsp; StackCookie
0x14001cf55  call    __security_check_cookie
0x14001cf5a  mov     rbx, [rsp+0C8h+arg_10]
0x14001cf62  add     rsp, 90h
0x14001cf69  pop     r15
0x14001cf6b  pop     r14
0x14001cf6d  pop     r13
0x14001cf6f  pop     r12
0x14001cf71  pop     rdi
0x14001cf72  pop     rsi
0x14001cf73  pop     rbp
0x14001cf74  retn
```
