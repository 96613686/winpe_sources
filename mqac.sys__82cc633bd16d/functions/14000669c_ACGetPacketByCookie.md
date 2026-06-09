# ACGetPacketByCookie

- ea: `0x14000669c`
- end: `0x140006801`
- name: `ACGetPacketByCookie`
- size: `357`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, volatile void *Address)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001c04`
- `0x140003d84`
- `0x14000669c`
- `0x140009a04`
- `0x140009adc`
- `0x14000ef4c`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400066ec`
- `ntoskrnl!ProbeForWrite` at `0x1400066ec`

## pseudocode

```c
__int64 __fastcall ACGetPacketByCookie(struct _DEVICE_OBJECT *a1, struct CBaseHeader **Address)
{
  struct CPacket *v4; // rsi
  struct CPacket *v5; // rbx
  struct CBaseHeader *v7; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 147, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
  }
  ProbeForWrite(Address, 0x10u, 1u);
  v4 = Address[1];
  v5 = CPacketHandleToCPacket(a1, v4);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 149, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v5);
    }
    v7 = AC2QM(v5);
    if ( v7 )
    {
      *Address = v7;
      CQEntry::AddRefBuffer(v5);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 150, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v5);
      }
      return 3221225626LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 148, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v4);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000669c  mov     [rsp+arg_8], rdx
0x1400066a1  push    rbx
0x1400066a2  push    rsi
0x1400066a3  push    rdi
0x1400066a4  push    r14
0x1400066a6  sub     rsp, 28h
0x1400066aa  mov     rdi, rdx
0x1400066ad  mov     rbx, rcx
0x1400066b0  lea     r14, WPP_GLOBAL_Control
0x1400066b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066be  cmp     rcx, r14
0x1400066c1  jz      short loc_1400066E0
0x1400066c3  mov     eax, [rcx+6Ch]
0x1400066c6  test    al, 4
0x1400066c8  jz      short loc_1400066E0
0x1400066ca  mov     edx, 93h
0x1400066cf  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400066d6  mov     rcx, [rcx+58h]
0x1400066da  call    WPP_SF_
0x1400066df  nop
0x1400066e0  mov     edx, 10h; Length
0x1400066e5  lea     r8d, [rdx-0Fh]; Alignment
0x1400066e9  mov     rcx, rdi; Address
0x1400066ec  call    cs:__imp_ProbeForWrite
0x1400066f3  nop     dword ptr [rax+rax+00h]
0x1400066f8  mov     rsi, [rdi+8]
0x1400066fc  mov     rdx, rsi; struct CPacket *
0x1400066ff  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x140006702  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAU_DEVICE_OBJECT@@PEAV1@@Z; CPacketHandleToCPacket(_DEVICE_OBJECT *,CPacket *)
0x140006707  mov     rbx, rax
0x14000670a  test    rax, rax
0x14000670d  jnz     short loc_140006744
0x14000670f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006716  cmp     rcx, r14
0x140006719  jz      short loc_14000673A
0x14000671b  mov     eax, [rcx+6Ch]
0x14000671e  test    al, 1
0x140006720  jz      short loc_14000673A
0x140006722  mov     edx, 94h
0x140006727  mov     r9, rsi
0x14000672a  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006731  mov     rcx, [rcx+58h]
0x140006735  call    WPP_SF_q
0x14000673a  mov     eax, 0C000000Dh
0x14000673f  jmp     loc_1400067F6
0x140006744  mov     rcx, cs:WPP_GLOBAL_Control
0x14000674b  cmp     rcx, r14
0x14000674e  jz      short loc_14000676F
0x140006750  mov     eax, [rcx+6Ch]
0x140006753  test    al, 4
0x140006755  jz      short loc_14000676F
0x140006757  mov     edx, 95h
0x14000675c  mov     r9, rbx
0x14000675f  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006766  mov     rcx, [rcx+58h]
0x14000676a  call    WPP_SF_q
0x14000676f  mov     rcx, rbx; struct CPacket *
0x140006772  call    ?AC2QM@@YAPEAUCBaseHeader@@PEAVCPacket@@@Z; AC2QM(CPacket *)
0x140006777  test    rax, rax
0x14000677a  jnz     short loc_1400067AE
0x14000677c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006783  cmp     rcx, r14
0x140006786  jz      short loc_1400067A7
0x140006788  mov     eax, [rcx+6Ch]
0x14000678b  test    al, 1
0x14000678d  jz      short loc_1400067A7
0x14000678f  mov     edx, 96h
0x140006794  mov     r9, rbx
0x140006797  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000679e  mov     rcx, [rcx+58h]
0x1400067a2  call    WPP_SF_q
0x1400067a7  mov     eax, 0C000009Ah
0x1400067ac  jmp     short loc_1400067F6
0x1400067ae  mov     [rdi], rax
0x1400067b1  mov     rcx, rbx; this
0x1400067b4  call    ?AddRefBuffer@CQEntry@@QEBAXXZ; CQEntry::AddRefBuffer(void)
0x1400067b9  xor     eax, eax
0x1400067bb  jmp     short loc_1400067F6
0x1400067bd  mov     ebx, eax
0x1400067bf  lea     rax, WPP_GLOBAL_Control
0x1400067c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400067cd  cmp     rcx, rax
0x1400067d0  jz      short loc_1400067F4
0x1400067d2  mov     edx, [rcx+6Ch]
0x1400067d5  test    dl, 1
0x1400067d8  jz      short loc_1400067F4
0x1400067da  mov     edx, 97h
0x1400067df  mov     r9, [rsp+48h+arg_8]
0x1400067e4  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400067eb  mov     rcx, [rcx+58h]
0x1400067ef  call    WPP_SF_q
0x1400067f4  mov     eax, ebx
0x1400067f6  add     rsp, 28h
0x1400067fa  pop     r14
0x1400067fc  pop     rdi
0x1400067fd  pop     rsi
0x1400067fe  pop     rbx
0x1400067ff  retn
```
