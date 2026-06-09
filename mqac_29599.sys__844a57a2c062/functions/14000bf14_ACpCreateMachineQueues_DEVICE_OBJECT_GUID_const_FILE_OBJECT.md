# ACpCreateMachineQueues(_DEVICE_OBJECT *,_GUID const *,_FILE_OBJECT *)

- ea: `0x14000bf14`
- end: `0x14000c0fa`
- name: `?ACpCreateMachineQueues@@YAPEAVCQueue@@PEAU_DEVICE_OBJECT@@PEBU_GUID@@PEAU_FILE_OBJECT@@@Z`
- size: `486`
- prototype: `struct CQueue *__fastcall(struct _DEVICE_OBJECT *, const struct _GUID *, struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000bb00`

## callees

- `0x140001128`
- `0x140001c04`
- `0x14000baa0`
- `0x14000bf14`
- `0x14001c530`
- `0x14001cc6c`

## pseudocode

```c
struct CQueue *__fastcall ACpCreateMachineQueues(
        struct _DEVICE_OBJECT *a1,
        const struct _GUID *a2,
        struct _FILE_OBJECT *a3)
{
  _QWORD *DeviceExtension; // rdi
  struct _GUID v7; // xmm0
  CQueue *v8; // rax
  CQueue *v9; // rbx
  _DWORD *FsContext2; // rax
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rbx
  _WORD v16[36]; // [rsp+60h] [rbp-48h] BYREF

  DeviceExtension = a1->DeviceExtension;
  memset(v16, 0, 32);
  v7 = *a2;
  v16[0] = 516;
  *(struct _GUID *)&v16[4] = v7;
  v8 = (CQueue *)operator new(0x180u, 0x40u, 0x5141514Du, LowPoolPriority);
  if ( v8 )
    v9 = CQueue::CQueue(v8, a1, a3, 2u, 5u, 0, a2, (const struct QUEUE_FORMAT *)v16, 0, 0, 0, 0);
  else
    v9 = 0;
  FsContext2 = a3->FsContext2;
  a3->FsContext = v9;
  FsContext2[5] |= 1u;
  *((_DWORD *)a3->FsContext2 + 5) |= 4u;
  *((_DWORD *)a3->FsContext2 + 5) &= ~2u;
  if ( !v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return 0;
    }
    v12 = 10;
    goto LABEL_12;
  }
  *((_DWORD *)v9 + 14) &= ~2u;
  *((_DWORD *)v9 + 42) |= 0x2Cu;
  DeviceExtension[119] = v9;
  CQueue::CreateJournalQueue(v9);
  v13 = *((_QWORD *)v9 + 19);
  if ( !v13 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return 0;
    }
    v12 = 11;
LABEL_12:
    WPP_SF_(v11->Queue.ListEntry.Blink, v12, &WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids);
    return 0;
  }
  *(_DWORD *)(v13 + 56) &= ~2u;
  *(_DWORD *)(v13 + 168) |= 0x2Cu;
  DeviceExtension[118] = v13;
  CQueue::CreateJournalQueue((CQueue *)v13);
  v14 = *(_QWORD *)(v13 + 152);
  if ( !v14 )
    return 0;
  *(_DWORD *)(v14 + 56) |= 2u;
  *(_DWORD *)(v14 + 168) |= 0x2Cu;
  *(_BYTE *)(v14 + 89) = *(_BYTE *)(v14 + 89) & 0xF0 | 3;
  DeviceExtension[120] = v14;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      12,
      &WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids,
      DeviceExtension[119],
      DeviceExtension[118],
      v14);
  }
  return (struct CQueue *)v14;
}

```

## disassembly

```asm
0x14000bf14  mov     rax, rsp
0x14000bf17  push    rbx
0x14000bf18  push    rbp
0x14000bf19  push    rsi
0x14000bf1a  push    rdi
0x14000bf1b  sub     rsp, 88h
0x14000bf22  mov     rdi, [rcx+40h]
0x14000bf26  xorps   xmm0, xmm0
0x14000bf29  movups  xmmword ptr [rax-48h], xmm0
0x14000bf2d  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000bf30  mov     rsi, r8
0x14000bf33  movups  xmmword ptr [rax-38h], xmm0
0x14000bf37  mov     rbx, rdx
0x14000bf3a  mov     rbp, rcx
0x14000bf3d  movups  xmm0, xmmword ptr [rdx]
0x14000bf40  lea     edx, [r9+40h]; unsigned __int64
0x14000bf44  mov     word ptr [rax-48h], 204h
0x14000bf4a  mov     ecx, 180h; unsigned __int64
0x14000bf4f  mov     r8d, 5141514Dh; unsigned int
0x14000bf55  movdqu  xmmword ptr [rax-40h], xmm0
0x14000bf5a  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000bf5f  test    rax, rax
0x14000bf62  jz      short loc_14000BFBF
0x14000bf64  mov     [rsp+0A8h+var_50], 0; struct CSenderStream *
0x14000bf6d  lea     rcx, [rsp+0A8h+var_48]
0x14000bf72  mov     [rsp+0A8h+var_58], 0; unsigned int
0x14000bf7a  mov     r9d, 2; unsigned int
0x14000bf80  mov     [rsp+0A8h+var_60], 0; __int64
0x14000bf89  mov     r8, rsi; struct _FILE_OBJECT *
0x14000bf8c  mov     [rsp+0A8h+var_68], 0; struct QueueCounters *
0x14000bf95  mov     rdx, rbp; struct _DEVICE_OBJECT *
0x14000bf98  mov     [rsp+0A8h+var_70], rcx; struct QUEUE_FORMAT *
0x14000bf9d  mov     rcx, rax; this
0x14000bfa0  mov     [rsp+0A8h+var_78], rbx; struct _GUID *
0x14000bfa5  mov     [rsp+0A8h+var_80], 0; int
0x14000bfad  mov     [rsp+0A8h+var_88], 5; unsigned int
0x14000bfb5  call    ??0CQueue@@QEAA@PEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@KKHPEBU_GUID@@PEBUQUEUE_FORMAT@@PEAUQueueCounters@@_JKPEBVCSenderStream@@@Z; CQueue::CQueue(_DEVICE_OBJECT *,_FILE_OBJECT *,ulong,ulong,int,_GUID const *,QUEUE_FORMAT const *,QueueCounters *,__int64,ulong,CSenderStream const *)
0x14000bfba  mov     rbx, rax
0x14000bfbd  jmp     short loc_14000BFC1
0x14000bfbf  xor     ebx, ebx
0x14000bfc1  mov     rax, [rsi+20h]
0x14000bfc5  mov     [rsi+18h], rbx
0x14000bfc9  or      dword ptr [rax+14h], 1
0x14000bfcd  mov     rax, [rsi+20h]
0x14000bfd1  or      dword ptr [rax+14h], 4
0x14000bfd5  mov     rax, [rsi+20h]
0x14000bfd9  mov     esi, 0FFFFFFFDh
0x14000bfde  and     [rax+14h], esi
0x14000bfe1  test    rbx, rbx
0x14000bfe4  jnz     short loc_14000C009
0x14000bfe6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bfed  lea     rax, WPP_GLOBAL_Control
0x14000bff4  cmp     rcx, rax
0x14000bff7  jz      loc_14000C082
0x14000bffd  mov     eax, [rcx+6Ch]
0x14000c000  test    al, 1
0x14000c002  jz      short loc_14000C082
0x14000c004  lea     edx, [rbx+0Ah]
0x14000c007  jmp     short loc_14000C04B
0x14000c009  and     [rbx+38h], esi
0x14000c00c  mov     rcx, rbx; this
0x14000c00f  or      dword ptr [rbx+0A8h], 2Ch
0x14000c016  mov     [rdi+3B8h], rbx
0x14000c01d  call    ?CreateJournalQueue@CQueue@@QEAAXXZ; CQueue::CreateJournalQueue(void)
0x14000c022  mov     rbx, [rbx+98h]
0x14000c029  test    rbx, rbx
0x14000c02c  jnz     short loc_14000C05D
0x14000c02e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c035  lea     rax, WPP_GLOBAL_Control
0x14000c03c  cmp     rcx, rax
0x14000c03f  jz      short loc_14000C082
0x14000c041  mov     eax, [rcx+6Ch]
0x14000c044  test    al, 1
0x14000c046  jz      short loc_14000C082
0x14000c048  lea     edx, [rbx+0Bh]
0x14000c04b  mov     rcx, [rcx+58h]
0x14000c04f  lea     r8, WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids
0x14000c056  call    WPP_SF_
0x14000c05b  jmp     short loc_14000C082
0x14000c05d  and     [rbx+38h], esi
0x14000c060  mov     rcx, rbx; this
0x14000c063  or      dword ptr [rbx+0A8h], 2Ch
0x14000c06a  mov     [rdi+3B0h], rbx
0x14000c071  call    ?CreateJournalQueue@CQueue@@QEAAXXZ; CQueue::CreateJournalQueue(void)
0x14000c076  mov     rbx, [rbx+98h]
0x14000c07d  test    rbx, rbx
0x14000c080  jnz     short loc_14000C086
0x14000c082  xor     eax, eax
0x14000c084  jmp     short loc_14000C0ED
0x14000c086  or      dword ptr [rbx+38h], 2
0x14000c08a  or      dword ptr [rbx+0A8h], 2Ch
0x14000c091  mov     al, [rbx+59h]
0x14000c094  and     al, 0F3h
0x14000c096  or      al, 3
0x14000c098  mov     [rbx+59h], al
0x14000c09b  mov     [rdi+3C0h], rbx
0x14000c0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c0a9  lea     rax, WPP_GLOBAL_Control
0x14000c0b0  cmp     rcx, rax
0x14000c0b3  jz      short loc_14000C0EA
0x14000c0b5  mov     edx, [rcx+6Ch]
0x14000c0b8  test    dl, 4
0x14000c0bb  jz      short loc_14000C0EA
0x14000c0bd  mov     r8, [rdi+3B0h]
0x14000c0c4  mov     edx, 0Ch
0x14000c0c9  mov     r9, [rdi+3B8h]
0x14000c0d0  mov     rcx, [rcx+58h]
0x14000c0d4  mov     qword ptr [rsp+0A8h+var_80], rbx
0x14000c0d9  mov     qword ptr [rsp+0A8h+var_88], r8
0x14000c0de  lea     r8, WPP_9ecb2faca1bb356d97935309a38b2833_Traceguids
0x14000c0e5  call    WPP_SF_qqq
0x14000c0ea  mov     rax, rbx
0x14000c0ed  add     rsp, 88h
0x14000c0f4  pop     rdi
0x14000c0f5  pop     rsi
0x14000c0f6  pop     rbp
0x14000c0f7  pop     rbx
0x14000c0f8  retn
```
