# CCreatePacket::GetCreatePacketRequest(CPacket *)

- ea: `0x1400121e8`
- end: `0x140012360`
- name: `?GetCreatePacketRequest@CCreatePacket@@QEAAPEAU_IRP@@PEAVCPacket@@@Z`
- size: `376`
- prototype: `struct _IRP *__fastcall(CCreatePacket *__hidden this, struct CPacket *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140017694`

## callees

- `0x140001c04`
- `0x140003d84`
- `0x1400121e8`
- `0x1400126bc`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012339`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012339`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140012209`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140012209`

## pseudocode

```c
struct _IRP *__fastcall CCreatePacket::GetCreatePacketRequest(CCreatePacket **this, struct CPacket *a2)
{
  PDEVICE_OBJECT v4; // rcx
  CCreatePacket *i; // rsi
  char *v6; // rbx
  struct _DEVICE_OBJECT **v7; // r14
  struct _DEVICE_OBJECT *j; // rdi
  struct _DEVICE_OBJECT *v9; // rax
  struct _DEVICE_OBJECT *v10; // r9
  __int64 v11; // rcx
  KIRQL Irql; // [rsp+50h] [rbp+8h] BYREF

  IoAcquireCancelSpinLock(&Irql);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 11, WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids, a2);
  }
  for ( i = *this; ; i = *(CCreatePacket **)i )
  {
    v6 = 0;
    if ( this != (CCreatePacket **)i )
      v6 = (char *)i - 168;
    if ( !v6 )
      break;
    if ( (*((_DWORD *)v6 + 36) & 0x80) != 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 12, WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids);
      }
      v7 = (struct _DEVICE_OBJECT **)*((_QWORD *)v6 + 7);
      for ( j = *v7; ; j = *(struct _DEVICE_OBJECT **)&j->Type )
      {
        v9 = 0;
        if ( v7 != (struct _DEVICE_OBJECT **)j )
          v9 = j;
        if ( !v9 )
          break;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
        {
          v10 = j;
          if ( v7 == (struct _DEVICE_OBJECT **)j )
            v10 = 0;
          WPP_SF_q(
            WPP_GLOBAL_Control->Queue.ListEntry.Blink,
            13,
            WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids,
            v10->NextDevice);
        }
        v4 = j;
        if ( v7 == (struct _DEVICE_OBJECT **)j )
          v4 = 0;
        if ( (struct CPacket *)v4->NextDevice == a2 )
        {
          _InterlockedExchange64((volatile __int64 *)v6 + 13, 0);
          v11 = *((_QWORD *)v6 + 7);
          --*(_DWORD *)(v11 + 20);
          XList<_IRP,168>::remove(v11, v6);
          *(_BYTE *)(*((_QWORD *)v6 + 7) + 24LL) = 0;
          goto LABEL_29;
        }
      }
    }
    else if ( *((struct CPacket **)v6 + 7) == a2 )
    {
      _InterlockedExchange64((volatile __int64 *)v6 + 13, 0);
      XList<_IRP,168>::remove(v4, v6);
      break;
    }
  }
LABEL_29:
  IoReleaseCancelSpinLock(Irql);
  return (struct _IRP *)v6;
}

```

## disassembly

```asm
0x1400121e8  mov     [rsp+arg_8], rbx
0x1400121ed  mov     [rsp+arg_10], rbp
0x1400121f2  push    rsi
0x1400121f3  push    rdi
0x1400121f4  push    r13
0x1400121f6  push    r14
0x1400121f8  push    r15
0x1400121fa  sub     rsp, 20h
0x1400121fe  mov     r15, rcx
0x140012201  mov     rbp, rdx
0x140012204  lea     rcx, [rsp+48h+Irql]; Irql
0x140012209  call    cs:__imp_IoAcquireCancelSpinLock
0x140012210  nop     dword ptr [rax+rax+00h]
0x140012215  mov     rcx, cs:WPP_GLOBAL_Control
0x14001221c  lea     r13, WPP_GLOBAL_Control
0x140012223  cmp     rcx, r13
0x140012226  jz      short loc_140012247
0x140012228  mov     eax, [rcx+6Ch]
0x14001222b  test    al, 4
0x14001222d  jz      short loc_140012247
0x14001222f  mov     rcx, [rcx+58h]
0x140012233  lea     r8, WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids
0x14001223a  mov     edx, 0Bh
0x14001223f  mov     r9, rbp
0x140012242  call    WPP_SF_q
0x140012247  mov     rsi, [r15]
0x14001224a  xor     ebx, ebx
0x14001224c  lea     rax, [rsi-0A8h]
0x140012253  cmp     r15, rsi
0x140012256  cmovnz  rbx, rax
0x14001225a  test    rbx, rbx
0x14001225d  jz      loc_140012335
0x140012263  mov     eax, [rbx+90h]
0x140012269  shr     eax, 7
0x14001226c  test    al, 1
0x14001226e  jnz     short loc_14001227F
0x140012270  cmp     [rbx+38h], rbp
0x140012274  jz      loc_140012309
0x14001227a  mov     rsi, [rsi]
0x14001227d  jmp     short loc_14001224A
0x14001227f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012286  cmp     rcx, r13
0x140012289  jz      short loc_1400122A7
0x14001228b  mov     eax, [rcx+6Ch]
0x14001228e  test    al, 4
0x140012290  jz      short loc_1400122A7
0x140012292  mov     rcx, [rcx+58h]
0x140012296  lea     r8, WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids
0x14001229d  mov     edx, 0Ch
0x1400122a2  call    WPP_SF_
0x1400122a7  mov     r14, [rbx+38h]
0x1400122ab  mov     rdi, [r14]
0x1400122ae  xor     eax, eax
0x1400122b0  cmp     r14, rdi
0x1400122b3  cmovnz  rax, rdi
0x1400122b7  test    rax, rax
0x1400122ba  jz      short loc_14001227A
0x1400122bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122c3  cmp     rcx, r13
0x1400122c6  jz      short loc_1400122F2
0x1400122c8  mov     eax, [rcx+6Ch]
0x1400122cb  test    al, 4
0x1400122cd  jz      short loc_1400122F2
0x1400122cf  mov     rcx, [rcx+58h]
0x1400122d3  lea     r8, WPP_f72b4ea4c5c535374694b3572d3977a7_Traceguids
0x1400122da  xor     eax, eax
0x1400122dc  mov     r9, rdi
0x1400122df  cmp     r14, rdi
0x1400122e2  cmovz   r9, rax
0x1400122e6  lea     edx, [rax+0Dh]
0x1400122e9  mov     r9, [r9+10h]
0x1400122ed  call    WPP_SF_q
0x1400122f2  xor     eax, eax
0x1400122f4  mov     rcx, rdi
0x1400122f7  cmp     r14, rdi
0x1400122fa  cmovz   rcx, rax
0x1400122fe  cmp     [rcx+10h], rbp
0x140012302  jz      short loc_140012319
0x140012304  mov     rdi, [rdi]
0x140012307  jmp     short loc_1400122AE
0x140012309  xor     eax, eax
0x14001230b  mov     rdx, rbx
0x14001230e  xchg    rax, [rbx+68h]
0x140012312  call    ?remove@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z; XList<_IRP,168>::remove(_IRP *)
0x140012317  jmp     short loc_140012335
0x140012319  xchg    rax, [rbx+68h]
0x14001231d  mov     rcx, [rbx+38h]
0x140012321  mov     rdx, rbx
0x140012324  dec     dword ptr [rcx+14h]
0x140012327  call    ?remove@?$XList@U_IRP@@$0KI@@@QEAAXPEAU_IRP@@@Z; XList<_IRP,168>::remove(_IRP *)
0x14001232c  mov     r8, [rbx+38h]
0x140012330  mov     byte ptr [r8+18h], 0
0x140012335  mov     cl, [rsp+48h+Irql]; Irql
0x140012339  call    cs:__imp_IoReleaseCancelSpinLock
0x140012340  nop     dword ptr [rax+rax+00h]
0x140012345  mov     rbp, [rsp+48h+arg_10]
0x14001234a  mov     rax, rbx
0x14001234d  mov     rbx, [rsp+48h+arg_8]
0x140012352  add     rsp, 20h
0x140012356  pop     r15
0x140012358  pop     r14
0x14001235a  pop     r13
0x14001235c  pop     rdi
0x14001235d  pop     rsi
0x14001235e  retn
```
