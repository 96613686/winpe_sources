# CPacket::IssueCreatePacketRequest(bool)

- ea: `0x140017b04`
- end: `0x140017b87`
- name: `?IssueCreatePacketRequest@CPacket@@QEAAJ_N@Z`
- size: `131`
- prototype: `__int64 __fastcall(CPacket *__hidden this, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000dc20`
- `0x14001cd90`

## callees

- `0x140009b90`
- `0x1400126fc`
- `0x140012754`
- `0x140017b04`
- `0x14001b114`

## pseudocode

```c
__int64 __fastcall CPacket::IssueCreatePacketRequest(CPacket *this, char a2)
{
  struct _DEVICE_OBJECT *v3; // rcx
  char *DeviceExtension; // rbx
  int v6; // ebx
  char v8[16]; // [rsp+20h] [rbp-F8h] BYREF
  int v9; // [rsp+30h] [rbp-E8h]
  __int64 v10; // [rsp+38h] [rbp-E0h]
  unsigned __int64 CPacketHandle; // [rsp+40h] [rbp-D8h]
  char v12; // [rsp+48h] [rbp-D0h]

  v9 = 2;
  v3 = (struct _DEVICE_OBJECT *)*((_QWORD *)this + 13);
  v10 = 0;
  DeviceExtension = (char *)v3->DeviceExtension;
  CPacketHandle = GenerateCPacketHandle(v3, this);
  v12 = a2;
  CBaseObject::AddRef(this);
  v6 = CQMInterface::ProcessRequest((CQMInterface *)(DeviceExtension + 72), (const struct CACRequest *)v8);
  if ( v6 >= 0 )
    return 0;
  CBaseObject::Release(this);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140017b04  mov     [rsp+arg_0], rbx
0x140017b09  mov     [rsp+arg_8], rsi
0x140017b0e  push    rdi
0x140017b0f  sub     rsp, 110h
0x140017b16  mov     rsi, rcx
0x140017b19  mov     [rsp+118h+var_E8], 2
0x140017b21  mov     rcx, [rcx+68h]; struct _DEVICE_OBJECT *
0x140017b25  mov     dil, dl
0x140017b28  mov     rdx, rsi; struct CPacket *
0x140017b2b  mov     [rsp+118h+var_E0], 0
0x140017b34  mov     rbx, [rcx+40h]
0x140017b38  call    ?GenerateCPacketHandle@@YA_KPEAU_DEVICE_OBJECT@@PEAVCPacket@@@Z; GenerateCPacketHandle(_DEVICE_OBJECT *,CPacket *)
0x140017b3d  mov     rcx, rsi; this
0x140017b40  mov     [rsp+118h+var_D8], rax
0x140017b45  mov     [rsp+118h+var_D0], dil
0x140017b4a  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x140017b4f  lea     rcx, [rbx+48h]; this
0x140017b53  lea     rdx, [rsp+118h+var_F8]; struct CACRequest *
0x140017b58  call    ?ProcessRequest@CQMInterface@@QEAAJAEBVCACRequest@@@Z; CQMInterface::ProcessRequest(CACRequest const &)
0x140017b5d  mov     ebx, eax
0x140017b5f  test    eax, eax
0x140017b61  jns     short loc_140017B6F
0x140017b63  mov     rcx, rsi; this
0x140017b66  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140017b6b  mov     eax, ebx
0x140017b6d  jmp     short loc_140017B71
0x140017b6f  xor     eax, eax
0x140017b71  lea     r11, [rsp+118h+var_8]
0x140017b79  mov     rbx, [r11+10h]
0x140017b7d  mov     rsi, [r11+18h]
0x140017b81  mov     rsp, r11
0x140017b84  pop     rdi
0x140017b85  retn
```
