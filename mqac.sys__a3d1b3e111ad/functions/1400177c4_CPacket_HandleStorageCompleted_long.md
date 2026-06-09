# CPacket::HandleStorageCompleted(long)

- ea: `0x1400177c4`
- end: `0x14001787c`
- name: `?HandleStorageCompleted@CPacket@@QEAAXJ@Z`
- size: `184`
- prototype: `void __fastcall(CPacket *__hidden this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140020ebc`
- `0x140020f9c`

## callees

- `0x140001010`
- `0x140014c48`
- `0x1400177c4`
- `0x1400183c4`
- `0x140018ff4`
- `0x14001fc94`

## pseudocode

```c
void __fastcall CPacket::HandleStorageCompleted(CTransaction **this, int a2)
{
  CTransaction *v4; // rcx
  int v5; // eax
  unsigned int v6; // eax
  int v7; // eax
  bool v8; // zf

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 49, WPP_521cf5ef77973c292796e113f00b944d_Traceguids, this, a2);
  }
  v4 = this[5];
  if ( a2 < 0 )
  {
    if ( !v4 )
    {
      CPacket::PacketRundown((CPacket *)this, a2);
      return;
    }
    v5 = *((_DWORD *)this + 13);
    if ( (v5 & 0x1000000) == 0 )
      goto LABEL_10;
    v6 = v5 & 0xFDFFFFFF;
LABEL_9:
    *((_DWORD *)this + 13) = v6;
LABEL_10:
    CTransaction::PacketStoreCompleted(v4, a2);
    return;
  }
  v7 = *((_DWORD *)this + 13);
  if ( v4 )
  {
    v6 = v7 | 0x1000000;
    goto LABEL_9;
  }
  if ( (v7 & 0x1000000) == 0 )
  {
    v8 = this[4] == 0;
    *((_DWORD *)this + 13) = v7 | 0x1000000;
    if ( !v8 )
      CPacket::SendArrivalAcknowledgment((CPacket *)this);
  }
  CPacket::CompleteWriter((CPacket *)this, a2);
}

```

## disassembly

```asm
0x1400177c4  mov     [rsp+arg_0], rbx
0x1400177c9  push    rdi
0x1400177ca  sub     rsp, 30h
0x1400177ce  mov     edi, edx
0x1400177d0  mov     rbx, rcx
0x1400177d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400177da  lea     rax, WPP_GLOBAL_Control
0x1400177e1  cmp     rcx, rax
0x1400177e4  jz      short loc_140017809
0x1400177e6  mov     eax, [rcx+6Ch]
0x1400177e9  test    al, 4
0x1400177eb  jz      short loc_140017809
0x1400177ed  mov     rcx, [rcx+58h]
0x1400177f1  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x1400177f8  mov     edx, 31h ; '1'
0x1400177fd  mov     [rsp+38h+var_18], edi
0x140017801  mov     r9, rbx
0x140017804  call    WPP_SF_qD
0x140017809  mov     rcx, [rbx+28h]; this
0x14001780d  test    edi, edi
0x14001780f  jns     short loc_14001783B
0x140017811  test    rcx, rcx
0x140017814  jnz     short loc_140017822
0x140017816  mov     edx, edi; int
0x140017818  mov     rcx, rbx; this
0x14001781b  call    ?PacketRundown@CPacket@@QEAAXJ@Z; CPacket::PacketRundown(long)
0x140017820  jmp     short loc_140017870
0x140017822  mov     eax, [rbx+34h]
0x140017825  bt      eax, 18h
0x140017829  jnb     short loc_140017832
0x14001782b  btr     eax, 19h
0x14001782f  mov     [rbx+34h], eax
0x140017832  mov     edx, edi; int
0x140017834  call    ?PacketStoreCompleted@CTransaction@@QEAAXJ@Z; CTransaction::PacketStoreCompleted(long)
0x140017839  jmp     short loc_140017870
0x14001783b  mov     eax, [rbx+34h]
0x14001783e  test    rcx, rcx
0x140017841  jz      short loc_140017849
0x140017843  bts     eax, 18h
0x140017847  jmp     short loc_14001782F
0x140017849  mov     edx, 1000000h
0x14001784e  test    edx, eax
0x140017850  jnz     short loc_140017866
0x140017852  or      eax, edx
0x140017854  cmp     qword ptr [rbx+20h], 0
0x140017859  mov     [rbx+34h], eax
0x14001785c  jz      short loc_140017866
0x14001785e  mov     rcx, rbx; this
0x140017861  call    ?SendArrivalAcknowledgment@CPacket@@QEAAXXZ; CPacket::SendArrivalAcknowledgment(void)
0x140017866  mov     edx, edi; int
0x140017868  mov     rcx, rbx; this
0x14001786b  call    ?CompleteWriter@CPacket@@QEAAXJ@Z; CPacket::CompleteWriter(long)
0x140017870  mov     rbx, [rsp+38h+arg_0]
0x140017875  add     rsp, 30h
0x140017879  pop     rdi
0x14001787a  retn
```
