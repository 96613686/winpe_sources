# CCursor::Create(CAVLTree1<CPacket,unsigned __int64,CPacket::CGetLookupId,Less<unsigned __int64>,72> const &,_FILE_OBJECT const *,_DEVICE_OBJECT *,CUserQueue *)

- ea: `0x14000c914`
- end: `0x14000ca3a`
- name: `?Create@CCursor@@SAKAEBV?$CAVLTree1@VCPacket@@_KVCGetLookupId@1@V?$Less@_K@@$0EI@@@PEBU_FILE_OBJECT@@PEAU_DEVICE_OBJECT@@PEAVCUserQueue@@@Z`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14001b9e0`
- `0x14001cbe0`

## callees

- `0x140001128`
- `0x140003d84`
- `0x14000c914`
- `0x140011268`
- `0x1400126fc`
- `0x140012754`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14000ca1e`
- `ntoskrnl!IoFreeWorkItem` at `0x14000ca1e`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000c931`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000c931`

## pseudocode

```c
unsigned int __fastcall CCursor::Create(__int64 a1, __int64 a2, struct _DEVICE_OBJECT *a3, CBaseObject *a4)
{
  char *DeviceExtension; // r15
  struct _IO_WORKITEM *WorkItem; // rdi
  char *v9; // rax
  char *v10; // rbx
  unsigned int result; // eax

  DeviceExtension = (char *)a3->DeviceExtension;
  WorkItem = IoAllocateWorkItem(a3);
  if ( WorkItem )
  {
    v9 = (char *)operator new(0x60u, 0x100u, 0x4241514Du, NormalPoolPriority);
    v10 = v9;
    if ( v9 )
    {
      *((_DWORD *)v9 + 2) = 1;
      *((_QWORD *)v9 + 3) = v9 + 16;
      *((_QWORD *)v9 + 2) = v9 + 16;
      *(_QWORD *)v9 = &CCursor::`vftable';
      *((_QWORD *)v9 + 4) = 0;
      *((_QWORD *)v9 + 5) = a1;
      *((_QWORD *)v9 + 6) = a2;
      *((_QWORD *)v9 + 7) = 0;
      *((_DWORD *)v9 + 16) = 0;
      *((_QWORD *)v9 + 9) = a4;
      *((_QWORD *)v9 + 10) = WorkItem;
      *((_DWORD *)v9 + 22) = 0;
      CBaseObject::AddRef(a4);
      result = CHTable::CreateHandle((CHTable *)(DeviceExtension + 928), v10);
      if ( result )
      {
        *((_DWORD *)v10 + 16) = result;
        return result;
      }
      *((_QWORD *)v10 + 3) = v10 + 16;
      *((_QWORD *)v10 + 2) = v10 + 16;
      CBaseObject::Release((CBaseObject *)v10);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, &WPP_12414dbceb3e33587961a24ce0efb252_Traceguids, a4);
      }
      IoFreeWorkItem(WorkItem);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000c914  push    rbx
0x14000c916  push    rbp
0x14000c917  push    rsi
0x14000c918  push    rdi
0x14000c919  push    r14
0x14000c91b  push    r15
0x14000c91d  sub     rsp, 28h
0x14000c921  mov     r15, [r8+40h]
0x14000c925  mov     r14, rcx
0x14000c928  mov     rcx, r8; DeviceObject
0x14000c92b  mov     rsi, r9
0x14000c92e  mov     rbp, rdx
0x14000c931  call    cs:__imp_IoAllocateWorkItem
0x14000c938  nop     dword ptr [rax+rax+00h]
0x14000c93d  mov     rdi, rax
0x14000c940  test    rax, rax
0x14000c943  jz      loc_14000CA2A
0x14000c949  mov     ecx, 60h ; '`'; unsigned __int64
0x14000c94e  mov     edx, 100h; unsigned __int64
0x14000c953  mov     r8d, 4241514Dh; unsigned int
0x14000c959  lea     r9d, [rcx-50h]; enum _EX_POOL_PRIORITY
0x14000c95d  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000c962  mov     rbx, rax
0x14000c965  test    rax, rax
0x14000c968  jz      short loc_14000C9E9
0x14000c96a  mov     dword ptr [rax+8], 1
0x14000c971  lea     rcx, [rax+10h]
0x14000c975  mov     [rcx+8], rcx
0x14000c979  lea     rax, ??_7CCursor@@6B@; const CCursor::`vftable'
0x14000c980  mov     [rcx], rcx
0x14000c983  mov     rcx, rsi; this
0x14000c986  mov     [rbx], rax
0x14000c989  mov     qword ptr [rbx+20h], 0
0x14000c991  mov     [rbx+28h], r14
0x14000c995  mov     [rbx+30h], rbp
0x14000c999  mov     qword ptr [rbx+38h], 0
0x14000c9a1  mov     dword ptr [rbx+40h], 0
0x14000c9a8  mov     [rbx+48h], rsi
0x14000c9ac  mov     [rbx+50h], rdi
0x14000c9b0  mov     dword ptr [rbx+58h], 0
0x14000c9b7  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x14000c9bc  lea     rcx, [r15+3A0h]; this
0x14000c9c3  mov     rdx, rbx; void *
0x14000c9c6  call    ?CreateHandle@CHTable@@QEAAKPEAX@Z; CHTable::CreateHandle(void *)
0x14000c9cb  test    eax, eax
0x14000c9cd  jnz     short loc_14000C9E4
0x14000c9cf  lea     rax, [rbx+10h]
0x14000c9d3  mov     rcx, rbx; this
0x14000c9d6  mov     [rax+8], rax
0x14000c9da  mov     [rax], rax
0x14000c9dd  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14000c9e2  jmp     short loc_14000CA2A
0x14000c9e4  mov     [rbx+40h], eax
0x14000c9e7  jmp     short loc_14000CA2C
0x14000c9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c9f0  lea     rax, WPP_GLOBAL_Control
0x14000c9f7  cmp     rcx, rax
0x14000c9fa  jz      short loc_14000CA1B
0x14000c9fc  mov     eax, [rcx+6Ch]
0x14000c9ff  test    al, 1
0x14000ca01  jz      short loc_14000CA1B
0x14000ca03  mov     rcx, [rcx+58h]
0x14000ca07  lea     r8, WPP_12414dbceb3e33587961a24ce0efb252_Traceguids
0x14000ca0e  mov     edx, 0Ah
0x14000ca13  mov     r9, rsi
0x14000ca16  call    WPP_SF_q
0x14000ca1b  mov     rcx, rdi; IoWorkItem
0x14000ca1e  call    cs:__imp_IoFreeWorkItem
0x14000ca25  nop     dword ptr [rax+rax+00h]
0x14000ca2a  xor     eax, eax
0x14000ca2c  add     rsp, 28h
0x14000ca30  pop     r15
0x14000ca32  pop     r14
0x14000ca34  pop     rdi
0x14000ca35  pop     rsi
0x14000ca36  pop     rbp
0x14000ca37  pop     rbx
0x14000ca38  retn
```
