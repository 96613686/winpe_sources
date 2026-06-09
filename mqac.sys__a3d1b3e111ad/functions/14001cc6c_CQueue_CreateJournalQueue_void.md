# CQueue::CreateJournalQueue(void)

- ea: `0x14001cc6c`
- end: `0x14001cd7e`
- name: `?CreateJournalQueue@CQueue@@QEAAXXZ`
- size: `274`
- prototype: `void __fastcall(CQueue *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000bf14`
- `0x14001c530`

## callees

- `0x140001128`
- `0x140001c04`
- `0x14001c530`
- `0x14001cc6c`
- `0x140024fc0`

## pseudocode

```c
void __fastcall CQueue::CreateJournalQueue(CQueue *this)
{
  struct QueueCounters *v2; // rdi
  CQueue *v3; // rax
  CQueue *v4; // rax
  struct _FILE_OBJECT v5; // [rsp+60h] [rbp-E8h] BYREF

  memset(&v5, 0, sizeof(v5));
  v2 = (struct QueueCounters *)((*((_QWORD *)this + 29) + 16LL) & -(__int64)(*((_QWORD *)this + 29) != 0));
  v3 = (CQueue *)operator new(0x180u, 0x40u, 0x4341514Du, LowPoolPriority);
  if ( v3
    && (v4 = CQueue::CQueue(
               v3,
               *((struct _DEVICE_OBJECT **)this + 8),
               &v5,
               2u,
               5u,
               0,
               (const struct _GUID *)((char *)this + 200),
               (CQueue *)((char *)this + 88),
               v2,
               0,
               0,
               0)) != 0 )
  {
    *((_BYTE *)v4 + 89) &= 0xF0u;
    *((_BYTE *)v4 + 89) |= 1u;
    *((_DWORD *)v4 + 42) |= 4u;
    *((_DWORD *)v4 + 42) |= 0x20u;
    *((_QWORD *)this + 19) = v4;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids);
  }
}

```

## disassembly

```asm
0x14001cc6c  mov     [rsp+arg_0], rbx
0x14001cc71  push    rdi
0x14001cc72  sub     rsp, 140h
0x14001cc79  mov     rbx, rcx
0x14001cc7c  xor     edx, edx; Val
0x14001cc7e  lea     rcx, [rsp+148h+var_E8]; void *
0x14001cc83  mov     r8d, 0D8h; Size
0x14001cc89  call    memset
0x14001cc8e  mov     rax, [rbx+0E8h]
0x14001cc95  mov     ecx, 180h; unsigned __int64
0x14001cc9a  mov     r8d, 4341514Dh; unsigned int
0x14001cca0  lea     rdx, [rax+10h]
0x14001cca4  neg     rax
0x14001cca7  sbb     rdi, rdi
0x14001ccaa  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14001ccad  and     rdi, rdx
0x14001ccb0  lea     edx, [r9+40h]; unsigned __int64
0x14001ccb4  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14001ccb9  test    rax, rax
0x14001ccbc  jz      short loc_14001CD3D
0x14001ccbe  mov     [rsp+148h+var_F0], 0; struct CSenderStream *
0x14001ccc7  lea     rcx, [rbx+58h]
0x14001cccb  mov     [rsp+148h+var_F8], 0; unsigned int
0x14001ccd3  lea     rdx, [rbx+0C8h]
0x14001ccda  mov     [rsp+148h+var_100], 0; __int64
0x14001cce3  lea     r8, [rsp+148h+var_E8]; struct _FILE_OBJECT *
0x14001cce8  mov     [rsp+148h+var_108], rdi; struct QueueCounters *
0x14001cced  mov     r9d, 2; unsigned int
0x14001ccf3  mov     [rsp+148h+var_110], rcx; struct QUEUE_FORMAT *
0x14001ccf8  mov     rcx, rax; this
0x14001ccfb  mov     [rsp+148h+var_118], rdx; struct _GUID *
0x14001cd00  mov     rdx, [rbx+40h]; struct _DEVICE_OBJECT *
0x14001cd04  mov     [rsp+148h+var_120], 0; int
0x14001cd0c  mov     [rsp+148h+var_128], 5; unsigned int
0x14001cd14  call    ??0CQueue@@QEAA@PEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@KKHPEBU_GUID@@PEBUQUEUE_FORMAT@@PEAUQueueCounters@@_JKPEBVCSenderStream@@@Z; CQueue::CQueue(_DEVICE_OBJECT *,_FILE_OBJECT *,ulong,ulong,int,_GUID const *,QUEUE_FORMAT const *,QueueCounters *,__int64,ulong,CSenderStream const *)
0x14001cd19  test    rax, rax
0x14001cd1c  jz      short loc_14001CD3D
0x14001cd1e  and     byte ptr [rax+59h], 0F0h
0x14001cd22  or      byte ptr [rax+59h], 1
0x14001cd26  or      dword ptr [rax+0A8h], 4
0x14001cd2d  or      dword ptr [rax+0A8h], 20h
0x14001cd34  mov     [rbx+98h], rax
0x14001cd3b  jmp     short loc_14001CD6C
0x14001cd3d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd44  lea     rax, WPP_GLOBAL_Control
0x14001cd4b  cmp     rcx, rax
0x14001cd4e  jz      short loc_14001CD6C
0x14001cd50  mov     eax, [rcx+6Ch]
0x14001cd53  test    al, 1
0x14001cd55  jz      short loc_14001CD6C
0x14001cd57  mov     rcx, [rcx+58h]
0x14001cd5b  lea     r8, WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids
0x14001cd62  mov     edx, 0Ah
0x14001cd67  call    WPP_SF_
0x14001cd6c  mov     rbx, [rsp+148h+arg_0]
0x14001cd74  add     rsp, 140h
0x14001cd7b  pop     rdi
0x14001cd7c  retn
```
