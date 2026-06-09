# ACpStorageCompletedSuccess(_DEVICE_OBJECT *,ulong,CPacket * *)

- ea: `0x140021080`
- end: `0x14002113d`
- name: `?ACpStorageCompletedSuccess@@YAJPEAU_DEVICE_OBJECT@@KPEAPEAVCPacket@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, unsigned int, struct CPacket **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140020ebc`

## callees

- `0x140003d84`
- `0x140009a54`
- `0x14000ffdc`
- `0x140012d34`
- `0x140012d8c`
- `0x14001961c`
- `0x140021080`

## pseudocode

```c
__int64 __fastcall ACpStorageCompletedSuccess(struct _DEVICE_OBJECT *a1, unsigned int a2, struct CPacket **a3)
{
  struct CDeviceExt *DeviceExtension; // r14
  struct _KPROCESS *v6; // rcx
  __int64 v8; // rbx
  struct _KPROCESS *i; // rbp
  struct CPacket *v10; // rax
  __int64 v11; // rdx
  unsigned int *QmAccessibleBufferNoMapping; // rax
  CPacket *v13; // r8

  DeviceExtension = (struct CDeviceExt *)a1->DeviceExtension;
  v6 = (struct _KPROCESS *)*((_QWORD *)DeviceExtension + 10);
  if ( !v6 )
    return 3222143018LL;
  v8 = 0;
  for ( i = ACAttachProcess(v6); (unsigned int)v8 < a2; v8 = (unsigned int)(v8 + 1) )
  {
    v10 = CPacketHandleToCPacket(DeviceExtension, a3[v8]);
    if ( v10 )
    {
      v11 = *((unsigned int *)v10 + 4);
      if ( (_DWORD)v11 != -1 )
      {
        QmAccessibleBufferNoMapping = (unsigned int *)CMMFAllocator::GetQmAccessibleBufferNoMapping(
                                                        *((_QWORD *)v10 + 3),
                                                        v11,
                                                        v10);
        if ( QmAccessibleBufferNoMapping )
          CPacket::UpdateBitmap(v13, *QmAccessibleBufferNoMapping);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 14, WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids, a3[v8]);
    }
  }
  ACDetachProcess(i);
  return 0;
}

```

## disassembly

```asm
0x140021080  push    rbx
0x140021082  push    rbp
0x140021083  push    rsi
0x140021084  push    rdi
0x140021085  push    r14
0x140021087  push    r15
0x140021089  sub     rsp, 28h
0x14002108d  mov     r14, [rcx+40h]
0x140021091  mov     r15, r8
0x140021094  mov     edi, edx
0x140021096  mov     rcx, [r14+50h]; Process
0x14002109a  test    rcx, rcx
0x14002109d  jnz     short loc_1400210A9
0x14002109f  mov     eax, 0C00E002Ah
0x1400210a4  jmp     loc_14002112F
0x1400210a9  call    ?ACAttachProcess@@YAPEAU_EPROCESS@@PEAU1@@Z; ACAttachProcess(_EPROCESS *)
0x1400210ae  xor     ebx, ebx
0x1400210b0  mov     rbp, rax
0x1400210b3  test    edi, edi
0x1400210b5  jz      short loc_140021125
0x1400210b7  mov     rdx, [r15+rbx*8]; void *
0x1400210bb  mov     rcx, r14; struct CDeviceExt *
0x1400210be  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAUCDeviceExt@@PEAX@Z; CPacketHandleToCPacket(CDeviceExt *,void *)
0x1400210c3  mov     r8, rax
0x1400210c6  test    rax, rax
0x1400210c9  jnz     short loc_1400210FF
0x1400210cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400210d2  lea     rax, WPP_GLOBAL_Control
0x1400210d9  cmp     rcx, rax
0x1400210dc  jz      short loc_14002111F
0x1400210de  mov     eax, [rcx+6Ch]
0x1400210e1  test    al, 1
0x1400210e3  jz      short loc_14002111F
0x1400210e5  mov     r9, [r15+rbx*8]
0x1400210e9  lea     edx, [r8+0Eh]
0x1400210ed  mov     rcx, [rcx+58h]
0x1400210f1  lea     r8, WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids
0x1400210f8  call    WPP_SF_q
0x1400210fd  jmp     short loc_14002111F
0x1400210ff  mov     edx, [rax+10h]
0x140021102  cmp     edx, 0FFFFFFFFh
0x140021105  jz      short loc_14002111F
0x140021107  mov     rcx, [rax+18h]
0x14002110b  call    ?GetQmAccessibleBufferNoMapping@CMMFAllocator@@QEBAPEAVCAccessibleBlock@@VCAllocatorBlockOffset@@@Z; CMMFAllocator::GetQmAccessibleBufferNoMapping(CAllocatorBlockOffset)
0x140021110  test    rax, rax
0x140021113  jz      short loc_14002111F
0x140021115  mov     edx, [rax]; unsigned int
0x140021117  mov     rcx, r8; this
0x14002111a  call    ?UpdateBitmap@CPacket@@QEAAXK@Z; CPacket::UpdateBitmap(ulong)
0x14002111f  inc     ebx
0x140021121  cmp     ebx, edi
0x140021123  jb      short loc_1400210B7
0x140021125  mov     rcx, rbp; Process
0x140021128  call    ?ACDetachProcess@@YAXPEAU_EPROCESS@@@Z; ACDetachProcess(_EPROCESS *)
0x14002112d  xor     eax, eax
0x14002112f  add     rsp, 28h
0x140021133  pop     r15
0x140021135  pop     r14
0x140021137  pop     rdi
0x140021138  pop     rsi
0x140021139  pop     rbp
0x14002113a  pop     rbx
0x14002113b  retn
```
