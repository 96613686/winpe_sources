# CQueue::RelinkPacket(CPacket *)

- ea: `0x14001e4c8`
- end: `0x14001e62c`
- name: `?RelinkPacket@CQueue@@QEAAJPEAVCPacket@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(CQueue *__hidden this, struct CPacket *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140018410`

## callees

- `0x140001cb0`
- `0x140017adc`
- `0x140019730`
- `0x14001d674`
- `0x14001e4c8`
- `0x14002157c`

## pseudocode

```c
__int64 __fastcall CQueue::RelinkPacket(CQueue *this, struct CPacket *a2)
{
  CQEntry *v4; // rcx
  struct CPacketBuffer *v5; // rax
  struct CBaseHeader *v6; // rcx
  struct CXactHeader *v7; // rax
  int v8; // esi
  struct CAVLNode **v9; // r8
  struct CAVLNode *v10; // rax
  __int64 v11; // r9
  struct CAVLNode **v12; // rax
  CQEntry *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rbp
  struct CPacketBuffer *v16; // rax
  struct CBaseHeader *v17; // rcx
  struct CXactHeader *v18; // rax
  unsigned int v19; // edi
  __int64 v20; // rdx
  struct CPacketBuffer *v21; // rax
  struct CBaseHeader *v22; // rcx
  struct CXactHeader *v23; // rax
  struct CPacketBuffer *v25; // rax
  struct CBaseHeader *v26; // rcx
  struct CXactHeader *v27; // rax

  if ( !(unsigned int)CPacket::IsXactLinkable(a2) || (*((_DWORD *)this + 42) & 0x20) != 0 )
    return 0;
  v5 = CQEntry::Buffer(v4);
  v6 = (struct CBaseHeader *)(((unsigned __int64)v5 + 36) & -(__int64)(v5 != 0));
  if ( v6 )
  {
    v7 = CPacketBuffer::XactHeaderSafe(v6);
    if ( v7 )
    {
      v8 = *((_DWORD *)v7 + 4);
      if ( v8 )
      {
        v9 = (struct CAVLNode **)((char *)a2 + 72);
        do
        {
          v10 = CAVLNode::Rmost(v9[2]);
          if ( !v10 )
          {
            while ( 1 )
            {
              v12 = v9;
              v9 = (struct CAVLNode **)*v9;
              if ( !v9 )
                break;
              if ( v9[1] == (struct CAVLNode *)v12 )
                goto LABEL_11;
            }
            *(_DWORD *)(v11 + 16) = 0;
            return 0;
          }
          v9 = (struct CAVLNode **)v10;
LABEL_11:
          ;
        }
        while ( ((unsigned __int64)(v9 - 9) & -(__int64)(v9 != 0)) == 0
             || !(unsigned int)CPacket::IsXactLinkable((CPacket *)((unsigned __int64)(v9 - 9) & -(__int64)(v9 != 0))) );
        v15 = *(_QWORD *)(v14 + 4);
        v16 = CQEntry::Buffer(v13);
        v17 = (struct CBaseHeader *)(((unsigned __int64)v16 + 36) & -(__int64)(v16 != 0));
        if ( v17 )
        {
          v18 = CPacketBuffer::XactHeaderSafe(v17);
          if ( v18 )
          {
            v19 = *((_DWORD *)v18 + 3);
            if ( (unsigned int)CQueue::IsPacketAcked(this, *(_QWORD *)((char *)v18 + 4), v19) || v20 != v15 )
            {
              v21 = CQEntry::Buffer(a2);
              v22 = (struct CBaseHeader *)(((unsigned __int64)v21 + 36) & -(__int64)(v21 != 0));
              if ( v22 )
              {
                v23 = CPacketBuffer::XactHeaderSafe(v22);
                if ( v23 )
                {
                  *((_DWORD *)v23 + 4) = 0;
                  return 0;
                }
              }
            }
            else
            {
              if ( v19 == v8 )
                return 0;
              v25 = CQEntry::Buffer(a2);
              v26 = (struct CBaseHeader *)(((unsigned __int64)v25 + 36) & -(__int64)(v25 != 0));
              if ( v26 )
              {
                v27 = CPacketBuffer::XactHeaderSafe(v26);
                if ( v27 )
                {
                  *((_DWORD *)v27 + 4) = v19;
                  return 0;
                }
              }
            }
          }
        }
        return 3221225626LL;
      }
      return 0;
    }
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14001e4c8  push    rbx
0x14001e4ca  push    rbp
0x14001e4cb  push    rsi
0x14001e4cc  push    rdi
0x14001e4cd  push    r14
0x14001e4cf  sub     rsp, 20h
0x14001e4d3  mov     r14, rcx
0x14001e4d6  mov     rbx, rdx
0x14001e4d9  mov     rcx, rdx; this
0x14001e4dc  call    ?IsXactLinkable@CPacket@@QEBAHXZ; CPacket::IsXactLinkable(void)
0x14001e4e1  test    eax, eax
0x14001e4e3  jz      loc_14001E5DE
0x14001e4e9  mov     eax, [r14+0A8h]
0x14001e4f0  test    al, 20h
0x14001e4f2  jnz     loc_14001E5DE
0x14001e4f8  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001e4fd  lea     rdx, [rax+24h]
0x14001e501  neg     rax
0x14001e504  sbb     rcx, rcx
0x14001e507  and     rcx, rdx; struct CBaseHeader *
0x14001e50a  jz      loc_14001E625
0x14001e510  call    ?XactHeaderSafe@CPacketBuffer@@SAPEAUCXactHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::XactHeaderSafe(CBaseHeader *)
0x14001e515  mov     r9, rax
0x14001e518  test    rax, rax
0x14001e51b  jz      loc_14001E625
0x14001e521  mov     esi, [rax+10h]
0x14001e524  test    esi, esi
0x14001e526  jz      loc_14001E5DE
0x14001e52c  lea     r8, [rbx+48h]
0x14001e530  mov     rcx, [r8+10h]; struct CAVLNode *
0x14001e534  call    ?Rmost@CAVLNode@@SAPEAV1@PEAV1@@Z; CAVLNode::Rmost(CAVLNode *)
0x14001e539  test    rax, rax
0x14001e53c  jz      short loc_14001E543
0x14001e53e  mov     r8, rax
0x14001e541  jmp     short loc_14001E558
0x14001e543  mov     rax, r8
0x14001e546  mov     r8, [rax]
0x14001e549  test    r8, r8
0x14001e54c  jz      loc_14001E61B
0x14001e552  cmp     [r8+8], rax
0x14001e556  jnz     short loc_14001E543
0x14001e558  mov     rax, r8
0x14001e55b  lea     rcx, [r8-48h]
0x14001e55f  neg     rax
0x14001e562  sbb     r10, r10
0x14001e565  and     r10, rcx
0x14001e568  jz      short loc_14001E530
0x14001e56a  mov     rcx, r10; this
0x14001e56d  call    ?IsXactLinkable@CPacket@@QEBAHXZ; CPacket::IsXactLinkable(void)
0x14001e572  test    eax, eax
0x14001e574  jz      short loc_14001E530
0x14001e576  mov     rbp, [r9+4]
0x14001e57a  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001e57f  lea     rdx, [rax+24h]
0x14001e583  neg     rax
0x14001e586  sbb     rcx, rcx
0x14001e589  and     rcx, rdx; struct CBaseHeader *
0x14001e58c  jz      loc_14001E625
0x14001e592  call    ?XactHeaderSafe@CPacketBuffer@@SAPEAUCXactHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::XactHeaderSafe(CBaseHeader *)
0x14001e597  test    rax, rax
0x14001e59a  jz      loc_14001E625
0x14001e5a0  mov     edi, [rax+0Ch]
0x14001e5a3  mov     rcx, r14; this
0x14001e5a6  mov     rdx, [rax+4]; __int64
0x14001e5aa  mov     r8d, edi; unsigned int
0x14001e5ad  call    ?IsPacketAcked@CQueue@@AEAAH_JK@Z; CQueue::IsPacketAcked(__int64,ulong)
0x14001e5b2  test    eax, eax
0x14001e5b4  jz      short loc_14001E5EC
0x14001e5b6  mov     rcx, rbx; this
0x14001e5b9  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001e5be  lea     rdx, [rax+24h]
0x14001e5c2  neg     rax
0x14001e5c5  sbb     rcx, rcx
0x14001e5c8  and     rcx, rdx; struct CBaseHeader *
0x14001e5cb  jz      short loc_14001E625
0x14001e5cd  call    ?XactHeaderSafe@CPacketBuffer@@SAPEAUCXactHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::XactHeaderSafe(CBaseHeader *)
0x14001e5d2  test    rax, rax
0x14001e5d5  jz      short loc_14001E625
0x14001e5d7  mov     dword ptr [rax+10h], 0
0x14001e5de  xor     eax, eax
0x14001e5e0  add     rsp, 20h
0x14001e5e4  pop     r14
0x14001e5e6  pop     rdi
0x14001e5e7  pop     rsi
0x14001e5e8  pop     rbp
0x14001e5e9  pop     rbx
0x14001e5ea  retn
0x14001e5ec  cmp     rdx, rbp
0x14001e5ef  jnz     short loc_14001E5B6
0x14001e5f1  cmp     edi, esi
0x14001e5f3  jz      short loc_14001E5DE
0x14001e5f5  mov     rcx, rbx; this
0x14001e5f8  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001e5fd  lea     rdx, [rax+24h]
0x14001e601  neg     rax
0x14001e604  sbb     rcx, rcx
0x14001e607  and     rcx, rdx; struct CBaseHeader *
0x14001e60a  jz      short loc_14001E625
0x14001e60c  call    ?XactHeaderSafe@CPacketBuffer@@SAPEAUCXactHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::XactHeaderSafe(CBaseHeader *)
0x14001e611  test    rax, rax
0x14001e614  jz      short loc_14001E625
0x14001e616  mov     [rax+10h], edi
0x14001e619  jmp     short loc_14001E5DE
0x14001e61b  mov     dword ptr [r9+10h], 0
0x14001e623  jmp     short loc_14001E5DE
0x14001e625  mov     eax, 0C000009Ah
0x14001e62a  jmp     short loc_14001E5E0
```
