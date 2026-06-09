# ACAckingCompleted

- ea: `0x14000a2b8`
- end: `0x14000a39f`
- name: `ACAckingCompleted`
- size: `231`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000a3b0`
- `0x14001adac`

## callees

- `0x140003d84`
- `0x140009adc`
- `0x14000a1d4`
- `0x14000a2b8`
- `0x140012754`

## pseudocode

```c
__int64 __fastcall ACAckingCompleted(struct _DEVICE_OBJECT *a1, struct CPacket *a2)
{
  CQEntry *v3; // rbx

  v3 = CPacketHandleToCPacket(a1, a2);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 132, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v3);
    }
    CQEntry::ReleaseBuffer(v3);
    CBaseObject::Release(v3);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 131, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a2);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000a2b8  mov     [rsp+arg_0], rbx
0x14000a2bd  mov     [rsp+arg_8], rdx
0x14000a2c2  push    rdi
0x14000a2c3  sub     rsp, 20h
0x14000a2c7  mov     rdi, rdx
0x14000a2ca  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAU_DEVICE_OBJECT@@PEAV1@@Z; CPacketHandleToCPacket(_DEVICE_OBJECT *,CPacket *)
0x14000a2cf  mov     rbx, rax
0x14000a2d2  test    rax, rax
0x14000a2d5  jnz     short loc_14000A313
0x14000a2d7  lea     rax, WPP_GLOBAL_Control
0x14000a2de  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a2e5  cmp     rcx, rax
0x14000a2e8  jz      short loc_14000A309
0x14000a2ea  mov     eax, [rcx+6Ch]
0x14000a2ed  test    al, 1
0x14000a2ef  jz      short loc_14000A309
0x14000a2f1  mov     edx, 83h
0x14000a2f6  mov     r9, rdi
0x14000a2f9  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000a300  mov     rcx, [rcx+58h]
0x14000a304  call    WPP_SF_q
0x14000a309  mov     eax, 0C000000Dh
0x14000a30e  jmp     loc_14000A393
0x14000a313  lea     rax, WPP_GLOBAL_Control
0x14000a31a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a321  cmp     rcx, rax
0x14000a324  jz      short loc_14000A345
0x14000a326  mov     eax, [rcx+6Ch]
0x14000a329  test    al, 4
0x14000a32b  jz      short loc_14000A345
0x14000a32d  mov     edx, 84h
0x14000a332  mov     r9, rbx
0x14000a335  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000a33c  mov     rcx, [rcx+58h]
0x14000a340  call    WPP_SF_q
0x14000a345  mov     rcx, rbx; this
0x14000a348  call    ?ReleaseBuffer@CQEntry@@QEBAXXZ; CQEntry::ReleaseBuffer(void)
0x14000a34d  mov     rcx, rbx; this
0x14000a350  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14000a355  nop
0x14000a356  xor     eax, eax
0x14000a358  jmp     short loc_14000A393
0x14000a35a  mov     ebx, eax
0x14000a35c  lea     rax, WPP_GLOBAL_Control
0x14000a363  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a36a  cmp     rcx, rax
0x14000a36d  jz      short loc_14000A391
0x14000a36f  mov     edx, [rcx+6Ch]
0x14000a372  test    dl, 1
0x14000a375  jz      short loc_14000A391
0x14000a377  mov     edx, 85h
0x14000a37c  mov     r9, [rsp+28h+arg_8]
0x14000a381  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000a388  mov     rcx, [rcx+58h]
0x14000a38c  call    WPP_SF_q
0x14000a391  mov     eax, ebx
0x14000a393  mov     rbx, [rsp+28h+arg_0]
0x14000a398  add     rsp, 20h
0x14000a39c  pop     rdi
0x14000a39d  retn
```
