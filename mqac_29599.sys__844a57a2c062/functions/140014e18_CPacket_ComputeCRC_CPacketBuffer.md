# CPacket::ComputeCRC(CPacketBuffer *)

- ea: `0x140014e18`
- end: `0x140014ef1`
- name: `?ComputeCRC@CPacket@@CAKPEAVCPacketBuffer@@@Z`
- size: `217`
- prototype: `unsigned int __fastcall(struct CPacketBuffer *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400148bc`
- `0x140017ca4`

## callees

- `0x140014e18`
- `0x140019730`

## pseudocode

```c
__int64 __fastcall CPacket::ComputeCRC(struct CPacketBuffer *a1)
{
  unsigned __int64 v2; // rbp
  char *v3; // rdi
  struct CBaseHeader *v4; // rcx
  unsigned __int8 *v5; // r9
  unsigned int v6; // ebx
  char *v7; // r8
  __int64 v8; // rax
  struct CXactHeader *v9; // rdi
  struct CXactHeader *v10; // rax
  struct CXactHeader *v11; // rdx
  signed __int64 v12; // r8
  __int64 v13; // rax
  unsigned __int64 i; // r8
  __int64 v15; // rcx

  v2 = ((unsigned __int64)a1 + 4) & -(__int64)(a1 != 0);
  v3 = (char *)a1 + 40;
  v4 = (struct CBaseHeader *)(((unsigned __int64)a1 + 36) & -(__int64)(a1 != 0));
  v5 = (unsigned __int8 *)(v2 + 8);
  v6 = -1;
  v7 = &v3[-v2 - 8];
  if ( v3 != (char *)(v2 + 8) )
  {
    do
    {
      v8 = *v5++;
      v6 = dword_140027EC0[v8 ^ (unsigned __int8)v6] ^ (v6 >> 8);
      --v7;
    }
    while ( v7 );
  }
  v9 = (struct CXactHeader *)(v3 + 4);
  v10 = CPacketBuffer::XactHeaderSafe(v4);
  v11 = v10;
  if ( v10 )
  {
    v12 = (struct CXactHeader *)((char *)v10 + 16) - v9;
    if ( (struct CXactHeader *)((char *)v10 + 16) != v9 )
    {
      do
      {
        v13 = *(unsigned __int8 *)v9;
        v9 = (struct CXactHeader *)((char *)v9 + 1);
        v6 = dword_140027EC0[v13 ^ (unsigned __int8)v6] ^ (v6 >> 8);
        --v12;
      }
      while ( v12 );
    }
    v9 = (struct CXactHeader *)((char *)v11 + 36);
    if ( (*(_BYTE *)v11 & 1) == 0 )
      v9 = (struct CXactHeader *)((char *)v11 + 20);
  }
  for ( i = v2 + *((unsigned int *)a1 + 11) - (_QWORD)v9 + 32LL; i; --i )
  {
    v15 = *(unsigned __int8 *)v9;
    v9 = (struct CXactHeader *)((char *)v9 + 1);
    v6 = dword_140027EC0[v15 ^ (unsigned __int8)v6] ^ (v6 >> 8);
  }
  return v6;
}

```

## disassembly

```asm
0x140014e18  push    rbx
0x140014e1a  push    rbp
0x140014e1b  push    rsi
0x140014e1c  push    rdi
0x140014e1d  push    r14
0x140014e1f  sub     rsp, 20h
0x140014e23  lea     rdx, [rcx+4]
0x140014e27  mov     rax, rcx
0x140014e2a  neg     rax
0x140014e2d  lea     r14, dword_140027EC0
0x140014e34  mov     rsi, rcx
0x140014e37  mov     rax, rcx
0x140014e3a  sbb     rbp, rbp
0x140014e3d  and     rbp, rdx
0x140014e40  lea     rdx, [rcx+24h]
0x140014e44  neg     rax
0x140014e47  lea     rdi, [rsi+28h]
0x140014e4b  sbb     rcx, rcx
0x140014e4e  mov     r8, rdi
0x140014e51  and     rcx, rdx; struct CBaseHeader *
0x140014e54  lea     r9, [rbp+8]
0x140014e58  or      ebx, 0FFFFFFFFh
0x140014e5b  sub     r8, r9
0x140014e5e  jz      short loc_140014E7A
0x140014e60  movzx   eax, byte ptr [r9]
0x140014e64  inc     r9
0x140014e67  movzx   edx, bl
0x140014e6a  xor     rdx, rax
0x140014e6d  shr     ebx, 8
0x140014e70  xor     ebx, [r14+rdx*4]
0x140014e74  sub     r8, 1
0x140014e78  jnz     short loc_140014E60
0x140014e7a  add     rdi, 4
0x140014e7e  call    ?XactHeaderSafe@CPacketBuffer@@SAPEAUCXactHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::XactHeaderSafe(CBaseHeader *)
0x140014e83  mov     rdx, rax
0x140014e86  test    rax, rax
0x140014e89  jz      short loc_140014EBA
0x140014e8b  lea     r8, [rax+10h]
0x140014e8f  sub     r8, rdi
0x140014e92  jz      short loc_140014EAD
0x140014e94  movzx   eax, byte ptr [rdi]
0x140014e97  inc     rdi
0x140014e9a  movzx   ecx, bl
0x140014e9d  xor     rcx, rax
0x140014ea0  shr     ebx, 8
0x140014ea3  xor     ebx, [r14+rcx*4]
0x140014ea7  sub     r8, 1
0x140014eab  jnz     short loc_140014E94
0x140014ead  test    byte ptr [rdx], 1
0x140014eb0  lea     rdi, [rdx+24h]
0x140014eb4  jnz     short loc_140014EBA
0x140014eb6  lea     rdi, [rdx+14h]
0x140014eba  mov     r8d, [rsi+2Ch]
0x140014ebe  sub     r8, rdi
0x140014ec1  add     r8, 20h ; ' '
0x140014ec5  add     r8, rbp
0x140014ec8  jz      short loc_140014EE3
0x140014eca  movzx   ecx, byte ptr [rdi]
0x140014ecd  inc     rdi
0x140014ed0  movzx   edx, bl
0x140014ed3  xor     rdx, rcx
0x140014ed6  shr     ebx, 8
0x140014ed9  xor     ebx, [r14+rdx*4]
0x140014edd  sub     r8, 1
0x140014ee1  jnz     short loc_140014ECA
0x140014ee3  mov     eax, ebx
0x140014ee5  add     rsp, 20h
0x140014ee9  pop     r14
0x140014eeb  pop     rdi
0x140014eec  pop     rsi
0x140014eed  pop     rbp
0x140014eee  pop     rbx
0x140014eef  retn
```
