# ACGetRestoredPacket

- ea: `0x140006a74`
- end: `0x140006be7`
- name: `ACGetRestoredPacket`
- size: `371`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001c04`
- `0x140001cb0`
- `0x140003d84`
- `0x140006a74`
- `0x140009af8`
- `0x14000a274`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140006ad1`
- `ntoskrnl!ProbeForWrite` at `0x140006ad1`

## pseudocode

```c
__int64 __fastcall ACGetRestoredPacket(__int64 a1, _QWORD *a2)
{
  struct CDeviceExt *v4; // rsi
  _QWORD *v5; // rcx
  CQEntry *v6; // rbx
  struct CPacketBuffer *v7; // rax
  _QWORD *v9; // r8

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 143, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
  }
  v4 = *(struct CDeviceExt **)(a1 + 64);
  ProbeForWrite(a2, 0x10u, 1u);
  a2[1] = 0;
  v5 = (_QWORD *)*((_QWORD *)v4 + 114);
  v6 = 0;
  if ( v5 != (_QWORD *)((char *)v4 + 912) )
    v6 = (CQEntry *)(v5 - 9);
  if ( v6 )
  {
    v7 = CQEntry::Buffer(v6);
    if ( (((unsigned __int64)v7 + 4) & -(__int64)(v7 != 0)) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 144, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v6);
      }
      return 3221225626LL;
    }
    XList<CPacket,72>::gethead((char *)v4 + 912);
    *a2 = *v9;
    a2[1] = GenerateCPacketHandle(v4, v6);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 145, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v6);
  }
  return 0;
}

```

## disassembly

```asm
0x140006a74  mov     [rsp+arg_0], rbx
0x140006a79  mov     [rsp+arg_10], rsi
0x140006a7e  mov     [rsp+arg_8], rdx
0x140006a83  push    rdi
0x140006a84  push    r14
0x140006a86  push    r15
0x140006a88  sub     rsp, 20h
0x140006a8c  mov     rdi, rdx
0x140006a8f  mov     rbx, rcx
0x140006a92  lea     r15, WPP_GLOBAL_Control
0x140006a99  mov     rcx, cs:WPP_GLOBAL_Control
0x140006aa0  cmp     rcx, r15
0x140006aa3  jz      short loc_140006AC1
0x140006aa5  mov     eax, [rcx+6Ch]
0x140006aa8  test    al, 4
0x140006aaa  jz      short loc_140006AC1
0x140006aac  mov     edx, 8Fh
0x140006ab1  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006ab8  mov     rcx, [rcx+58h]
0x140006abc  call    WPP_SF_
0x140006ac1  mov     rsi, [rbx+40h]
0x140006ac5  mov     edx, 10h; Length
0x140006aca  lea     r8d, [rdx-0Fh]; Alignment
0x140006ace  mov     rcx, rdi; Address
0x140006ad1  call    cs:__imp_ProbeForWrite
0x140006ad8  nop     dword ptr [rax+rax+00h]
0x140006add  mov     qword ptr [rdi+8], 0
0x140006ae5  lea     r14, [rsi+390h]
0x140006aec  mov     rcx, [r14]
0x140006aef  lea     rax, [rcx-48h]
0x140006af3  xor     ebx, ebx
0x140006af5  cmp     rcx, r14
0x140006af8  cmovnz  rbx, rax
0x140006afc  test    rbx, rbx
0x140006aff  jz      short loc_140006B6A
0x140006b01  mov     rcx, rbx; this
0x140006b04  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x140006b09  lea     rcx, [rax+4]
0x140006b0d  neg     rax
0x140006b10  sbb     r8, r8
0x140006b13  and     r8, rcx
0x140006b16  jnz     short loc_140006B4D
0x140006b18  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b1f  cmp     rcx, r15
0x140006b22  jz      short loc_140006B43
0x140006b24  mov     eax, [rcx+6Ch]
0x140006b27  test    al, 1
0x140006b29  jz      short loc_140006B43
0x140006b2b  mov     edx, 90h
0x140006b30  mov     r9, rbx
0x140006b33  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006b3a  mov     rcx, [rcx+58h]
0x140006b3e  call    WPP_SF_q
0x140006b43  mov     eax, 0C000009Ah
0x140006b48  jmp     loc_140006BD2
0x140006b4d  mov     rcx, r14
0x140006b50  call    ?gethead@?$XList@VCPacket@@$0EI@@@QEAAPEAVCPacket@@XZ; XList<CPacket,72>::gethead(void)
0x140006b55  mov     r8, [r8]
0x140006b58  mov     [rdi], r8
0x140006b5b  mov     rdx, rbx; struct CPacket *
0x140006b5e  mov     rcx, rsi; struct CDeviceExt *
0x140006b61  call    ?GenerateCPacketHandle@@YA_KPEAUCDeviceExt@@PEAVCPacket@@@Z; GenerateCPacketHandle(CDeviceExt *,CPacket *)
0x140006b66  mov     [rdi+8], rax
0x140006b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b71  cmp     rcx, r15
0x140006b74  jz      short loc_140006B95
0x140006b76  mov     eax, [rcx+6Ch]
0x140006b79  test    al, 4
0x140006b7b  jz      short loc_140006B95
0x140006b7d  mov     edx, 91h
0x140006b82  mov     r9, rbx
0x140006b85  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006b8c  mov     rcx, [rcx+58h]
0x140006b90  call    WPP_SF_q
0x140006b95  xor     eax, eax
0x140006b97  jmp     short loc_140006BD2
0x140006b99  mov     ebx, eax
0x140006b9b  lea     rax, WPP_GLOBAL_Control
0x140006ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ba9  cmp     rcx, rax
0x140006bac  jz      short loc_140006BD0
0x140006bae  mov     edx, [rcx+6Ch]
0x140006bb1  test    dl, 1
0x140006bb4  jz      short loc_140006BD0
0x140006bb6  mov     edx, 92h
0x140006bbb  mov     r9, [rsp+38h+arg_8]
0x140006bc0  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006bc7  mov     rcx, [rcx+58h]
0x140006bcb  call    WPP_SF_q
0x140006bd0  mov     eax, ebx
0x140006bd2  mov     rbx, [rsp+38h+arg_0]
0x140006bd7  mov     rsi, [rsp+38h+arg_10]
0x140006bdc  add     rsp, 20h
0x140006be0  pop     r15
0x140006be2  pop     r14
0x140006be4  pop     rdi
0x140006be5  retn
```
