# CPacket::IssueDeleteStorage(void)

- ea: `0x140017b90`
- end: `0x140017c9c`
- name: `?IssueDeleteStorage@CPacket@@AEAAJXZ`
- size: `268`
- prototype: `__int64 __fastcall(CPacket *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x140015654`

## callees

- `0x140001cb0`
- `0x140009b90`
- `0x1400126fc`
- `0x140012754`
- `0x140012d34`
- `0x140012d8c`
- `0x140017b90`
- `0x1400195f4`
- `0x14001961c`
- `0x14001b114`

## pseudocode

```c
__int64 __fastcall CPacket::IssueDeleteStorage(CPacket *this)
{
  __int64 v2; // rbp
  struct _KPROCESS *v3; // r14
  struct CPacketBuffer *v4; // rax
  struct CPacketBuffer *v5; // rsi
  int v6; // ebx
  struct _DEVICE_OBJECT *v7; // rcx
  CPacket *v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // r8d
  unsigned int v11; // edx
  _BYTE v13[16]; // [rsp+20h] [rbp-118h] BYREF
  int v14; // [rsp+30h] [rbp-108h]
  __int64 v15; // [rsp+38h] [rbp-100h]
  unsigned __int64 CPacketHandle; // [rsp+40h] [rbp-F8h]
  __int64 v17; // [rsp+48h] [rbp-F0h]
  unsigned int v18; // [rsp+50h] [rbp-E8h]
  int v19; // [rsp+54h] [rbp-E4h]

  v2 = *(_QWORD *)(*((_QWORD *)this + 13) + 64LL);
  v3 = ACAttachProcess(*(PRKPROCESS *)(v2 + 80));
  v4 = CQEntry::Buffer(this);
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 4) &= 0xFFE001FF;
    *((_BYTE *)v4 + 37) = 0;
    v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)this + 13);
    v14 = 1;
    v15 = 0;
    CPacketHandle = GenerateCPacketHandle(v7, this);
    v9 = *((_QWORD *)this + 3);
    v10 = 0;
    v18 = 0;
    v17 = v9;
    v19 = *((_DWORD *)this + 4);
    if ( *((_DWORD *)v5 + 11) <= 0x4000u )
      v10 = *((_DWORD *)v5 + 11);
    v18 = v10;
    CPacket::Touch(v8, (struct CPacketBuffer *)((char *)v5 + 36), v10);
    CBaseObject::AddRef(this);
    v6 = CQMInterface::ProcessRequest((CQMInterface *)(v2 + 72), (const struct CACRequest *)v13);
    if ( v6 >= 0 )
    {
      v11 = *(_DWORD *)v5;
      ++*(_DWORD *)(*((_QWORD *)this + 3) + 144LL);
      *((_DWORD *)this + 13) |= 0x2000000u;
      CPacket::UpdateBitmap(this, v11);
    }
    else
    {
      *((_DWORD *)v5 + 4) = *((_DWORD *)v5 + 4) & 0xFFE001FF | 0x157800;
      *((_BYTE *)v5 + 37) = 124;
      CBaseObject::Release(this);
    }
  }
  else
  {
    v6 = -1073741670;
  }
  ACDetachProcess(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140017b90  push    rbx
0x140017b92  push    rbp
0x140017b93  push    rsi
0x140017b94  push    rdi
0x140017b95  push    r14
0x140017b97  sub     rsp, 110h
0x140017b9e  mov     rax, [rcx+68h]
0x140017ba2  mov     rdi, rcx
0x140017ba5  mov     rbp, [rax+40h]
0x140017ba9  mov     rcx, [rbp+50h]; Process
0x140017bad  call    ?ACAttachProcess@@YAPEAU_EPROCESS@@PEAU1@@Z; ACAttachProcess(_EPROCESS *)
0x140017bb2  mov     rcx, rdi; this
0x140017bb5  mov     r14, rax
0x140017bb8  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x140017bbd  mov     rsi, rax
0x140017bc0  test    rax, rax
0x140017bc3  jnz     short loc_140017BCF
0x140017bc5  mov     ebx, 0C000009Ah
0x140017bca  jmp     loc_140017C83
0x140017bcf  and     dword ptr [rax+10h], 0FFE001FFh
0x140017bd6  mov     rdx, rdi; struct CPacket *
0x140017bd9  mov     byte ptr [rax+25h], 0
0x140017bdd  mov     rcx, [rdi+68h]; struct _DEVICE_OBJECT *
0x140017be1  mov     [rsp+138h+var_108], 1
0x140017be9  mov     [rsp+138h+var_100], 0
0x140017bf2  call    ?GenerateCPacketHandle@@YA_KPEAU_DEVICE_OBJECT@@PEAVCPacket@@@Z; GenerateCPacketHandle(_DEVICE_OBJECT *,CPacket *)
0x140017bf7  mov     [rsp+138h+var_F8], rax
0x140017bfc  lea     rdx, [rsi+24h]; struct CBaseHeader *
0x140017c00  mov     rax, [rdi+18h]
0x140017c04  xor     r8d, r8d
0x140017c07  mov     [rsp+138h+var_E8], r8d
0x140017c0c  mov     [rsp+138h+var_F0], rax
0x140017c11  mov     eax, [rdi+10h]
0x140017c14  mov     [rsp+138h+var_E4], eax
0x140017c18  mov     eax, [rsi+2Ch]
0x140017c1b  cmp     eax, 4000h
0x140017c20  cmovbe  r8d, eax; unsigned int
0x140017c24  mov     [rsp+138h+var_E8], r8d
0x140017c29  call    ?Touch@CPacket@@QEAAXPEAUCBaseHeader@@K@Z; CPacket::Touch(CBaseHeader *,ulong)
0x140017c2e  mov     rcx, rdi; this
0x140017c31  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x140017c36  lea     rdx, [rsp+138h+var_118]; struct CACRequest *
0x140017c3b  lea     rcx, [rbp+48h]; this
0x140017c3f  call    ?ProcessRequest@CQMInterface@@QEAAJAEBVCACRequest@@@Z; CQMInterface::ProcessRequest(CACRequest const &)
0x140017c44  mov     ebx, eax
0x140017c46  test    eax, eax
0x140017c48  jns     short loc_140017C6A
0x140017c4a  mov     ecx, [rsi+10h]
0x140017c4d  and     ecx, 0FFF579FFh
0x140017c53  or      ecx, 157800h
0x140017c59  mov     [rsi+10h], ecx
0x140017c5c  mov     rcx, rdi; this
0x140017c5f  mov     byte ptr [rsi+25h], 7Ch ; '|'
0x140017c63  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140017c68  jmp     short loc_140017C83
0x140017c6a  mov     edx, [rsi]; unsigned int
0x140017c6c  mov     rcx, rdi; this
0x140017c6f  mov     rax, [rdi+18h]
0x140017c73  inc     dword ptr [rax+90h]
0x140017c79  bts     dword ptr [rdi+34h], 19h
0x140017c7e  call    ?UpdateBitmap@CPacket@@QEAAXK@Z; CPacket::UpdateBitmap(ulong)
0x140017c83  mov     rcx, r14; Process
0x140017c86  call    ?ACDetachProcess@@YAXPEAU_EPROCESS@@@Z; ACDetachProcess(_EPROCESS *)
0x140017c8b  mov     eax, ebx
0x140017c8d  add     rsp, 110h
0x140017c94  pop     r14
0x140017c96  pop     rdi
0x140017c97  pop     rsi
0x140017c98  pop     rbp
0x140017c99  pop     rbx
0x140017c9a  retn
```
