# KdComConnection::ReadPacketContents(ulong,int,void *,ulong,ulong *)

- ea: `0x180433bc0`
- end: `0x180434281`
- name: `?ReadPacketContents@KdComConnection@@UEAAJKHPEAXKPEAK@Z`
- size: `1729`
- prototype: `__int64 __fastcall(KdComConnection *__hidden this, unsigned int, int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800db578`
- `0x1801ce6a0`
- `0x180433bc0`
- `0x180434bd4`
- `0x180437ec0`
- `0x180437f40`
- `0x1804387fc`
- `0x1804f4010`

## string_xrefs

- `0x180434218`: `READ: Data packet header Type error (short read).\n`
- `0x180433c3f`: `Attempting to get initial breakpoint.\n`
- `0x180434258`: `READ: Too many leader loops (%d), request resync\n`
- `0x18043417f`: `READ: Data packet header ByteCount error (short read).\n`
- `0x1804341b5`: `READ: Data packet header ByteCount error (short read).\n`
- `0x1804341cb`: `READ: Received INVALID packet type.\n`
- `0x180433f60`: `READ: Too many unmatched packets (%d), request resync\n`
- `0x180433d9c`: `READ: Received unmatched packet id = 0x%lx (expected 0x%lx), Type = %s, accum %d\n`
- `0x180434147`: `READ: Data packet header Id error (short read).\n`
- `0x180433fe7`: `READ: Received RESEND packet\n`
- `0x180433f86`: `READ: Received KD_RESET packet`
- `0x180433de1`: `READ: Received correct ACK packet.\n`
- `0x18043401d`: `READ: Received Data packet with unmatched ID = 0x%lx (expected 0x%lx), acking\n`
- `0x180433e50`: `READ: Received VALID data packet 0x%lxwhile waiting for ACK.\n`
- `0x18043410f`: `READ: Data packet header checksum error (short read).\n`
- `0x180434004`: `READ: Received Control packet with UNKNOWN type\n`
- `0x18043408e`: `READ: Checksum error.\n`
- `0x1804340a9`: `READ: Packet trailing byte timeout.\n`
- `0x1804340c4`: `READ: Data packet error (short read).\n`
- `0x1804340df`: `READ: Received INVALID packet Id.\n`
- `0x18043404f`: `READ: Got Sync Id, reset PacketId.\n`
- `0x180433f48`: `READ: Unexpected Packet Id (Acked).\n`
- `0x180433ef6`: `READ: Received Type %s data packet with id = 0x%lx successfully.\n`

## pseudocode

```c
__int64 __fastcall KdComConnection::ReadPacketContents(
        KdComConnection *this,
        unsigned int a2,
        int a3,
        char *a4,
        unsigned int a5,
        unsigned int *a6)
{
  int v7; // r14d
  unsigned int v8; // r13d
  __int64 result; // rax
  unsigned int v11; // r12d
  unsigned int PacketLeader; // ebp
  int v13; // edx
  int v14; // ebp
  unsigned __int16 *v15; // r15
  unsigned int *v16; // r14
  __int16 v17; // ax
  __int64 v18; // rax
  unsigned int v19; // edx
  KdConnection *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // ebp
  unsigned int v23; // r9d
  unsigned int v24; // eax
  int v25; // ebp
  unsigned int v26; // eax
  unsigned int v27; // ecx
  __int64 v28; // [rsp+28h] [rbp-40h]
  unsigned int v29; // [rsp+78h] [rbp+10h]
  int v30; // [rsp+80h] [rbp+18h]
  char v31; // [rsp+88h] [rbp+20h] BYREF

  v30 = a3;
  v29 = a2;
  v31 = 0;
  v7 = a3;
  v8 = a2;
  if ( a5 < (unsigned __int64)(unsigned int)KdTransportMaxPacketSize + 16 )
    return 2147942487LL;
  v11 = 0;
  while ( 2 )
  {
    if ( ++v11 > 0x64 )
    {
      LnkOut(0x80000000, L"READ: Too many leader loops (%d), request resync\n", v11);
      return 2147614738LL;
    }
    PacketLeader = KdComConnection::ReadPacketLeader((KdComConnection *)((char *)this - 16), a2, (unsigned int *)a4);
    if ( v7 )
    {
      LnkOut(0x80000000, L"Attempting to get initial breakpoint.\n");
      KdConnection::WriteBreakInPacket((KdComConnection *)((char *)this - 16));
      v30 = 0;
    }
    if ( PacketLeader )
      return PacketLeader;
    do
    {
      v13 = (*(__int64 (__fastcall **)(KdComConnection *, char *, __int64))(*(_QWORD *)this + 72LL))(this, &v31, 1);
      if ( v13 )
      {
        result = 2147614723LL;
        if ( v13 == -2147024891 )
          return 2147614741LL;
        return result;
      }
    }
    while ( v31 == 48 || v31 == 105 );
    a4[4] = v31;
    v14 = (*(__int64 (__fastcall **)(KdComConnection *, char *, __int64))(*(_QWORD *)this + 72LL))(this, a4 + 5, 1);
    if ( v14 )
    {
      if ( *(_DWORD *)a4 == 808464432 )
      {
        KdConnection::WriteControlPacket((KdComConnection *)((char *)this - 16), 3u, 5u, 0);
        LnkOut(0x80000000, L"READ: Data packet header Type error (short read).\n");
      }
      v26 = -2147352572;
      goto LABEL_70;
    }
    if ( *((_WORD *)a4 + 2) >= 0xCu )
    {
      LnkOut(0x80000000, L"READ: Received INVALID packet type.\n");
      if ( *(_DWORD *)a4 == 808464432 )
        KdConnection::WriteControlPacket((KdComConnection *)((char *)this - 16), 3u, 5u, 0);
      return 2147614725LL;
    }
    LnkOut(0x80000000, L"      PacketType=0x%x, ", *((unsigned __int16 *)a4 + 2));
    v15 = (unsigned __int16 *)(a4 + 6);
    v14 = (*(__int64 (__fastcall **)(KdComConnection *, char *, _QWORD))(*(_QWORD *)this + 72LL))(
            this,
            a4 + 6,
            (unsigned int)(v14 + 2));
    if ( v14 )
    {
      if ( *(_DWORD *)a4 == 808464432 )
      {
        KdConnection::WriteControlPacket((KdComConnection *)((char *)this - 16), 3u, 5u, 0);
        LnkOut(0x80000000, L"READ: Data packet header ByteCount error (short read).\n");
      }
      v26 = -2147352570;
      goto LABEL_70;
    }
    if ( *v15 > (unsigned int)KdTransportMaxPacketSize )
    {
      if ( *(_DWORD *)a4 == 808464432 )
      {
        KdConnection::WriteControlPacket((KdComConnection *)((char *)this - 16), 3u, 5u, 0);
        LnkOut(0x80000000, L"READ: Data packet header ByteCount error (short read).\n");
      }
      return 2147614727LL;
    }
    LnkOut(0x80000000, L"Bytes=0x%x, ");
    v16 = (unsigned int *)(a4 + 8);
    v14 = (*(__int64 (__fastcall **)(KdComConnection *, char *, _QWORD))(*(_QWORD *)this + 72LL))(
            this,
            a4 + 8,
            (unsigned int)(v14 + 4));
    if ( v14 )
    {
      if ( *(_DWORD *)a4 == 808464432 )
      {
        KdConnection::WriteControlPacket((KdComConnection *)((char *)this - 16), 3u, 5u, 0);
        LnkOut(0x80000000, L"READ: Data packet header Id error (short read).\n");
      }
      v26 = -2147352568;
      goto LABEL_70;
    }
    LnkOut(0x80000000, L"PacketId=0x%x,\n", *v16);
    if ( *(_DWORD *)a4 != 1768515945 )
    {
      v14 = (*(__int64 (__fastcall **)(KdComConnection *, char *, __int64))(*(_QWORD *)this + 72LL))(this, a4 + 12, 4);
      if ( v14 )
      {
        KdConnection::WriteControlPacket((KdComConnection *)((char *)this - 16), 3u, 5u, 0);
        LnkOut(0x80000000, L"READ: Data packet header checksum error (short read).\n");
        v26 = -2147352565;
      }
      else
      {
        if ( v8 == 4 )
        {
          if ( *v16 != *((_DWORD *)this + 42) && (*v16 & 0x800) == 0 )
          {
            LnkOut(0x80000000, L"READ: Received Data packet with unmatched ID = 0x%lx (expected 0x%lx), acking\n", *v16);
            KdConnection::WriteControlPacket((KdComConnection *)((char *)this - 16), 3u, 4u, *v16);
            return 2147614729LL;
          }
          *((_DWORD *)this + 43) ^= 1u;
          LnkOut(0x80000000, L"READ: Received VALID data packet 0x%lxwhile waiting for ACK.\n", *v16);
        }
        *((_DWORD *)this + 16) = 0;
        if ( (*v16 & 0xFFFFF7FF) + 2139095040 > 1 )
        {
          LnkOut(0x80000000, L"READ: Received INVALID packet Id.\n");
          return 2147614730LL;
        }
        v14 = (*(__int64 (__fastcall **)(KdComConnection *, char *, _QWORD))(*(_QWORD *)this + 72LL))(
                this,
                a4 + 16,
                *v15);
        if ( v14 )
        {
          LnkOut(0x80000000, L"READ: Data packet error (short read).\n");
          v26 = -2147352562;
        }
        else
        {
          v14 = (*(__int64 (__fastcall **)(KdComConnection *, char *, __int64))(*(_QWORD *)this + 72LL))(this, &v31, 1);
          if ( !v14 && v31 == -86 )
          {
            if ( KdConnection::ComputeChecksum(v20, (unsigned __int8 *)a4 + 16, *v15) != *((_DWORD *)a4 + 3) )
            {
              LnkOut(0x80000000, L"READ: Checksum error.\n");
              return 2147614732LL;
            }
            v21 = PacketTypeToPacketName(*((unsigned __int16 *)a4 + 2));
            LnkOut(0x80000000, L"READ: Received Type %s data packet with id = 0x%lx successfully.\n", v21, *v16);
            v22 = *v16;
            v23 = *v16 & 0xFFFFF7FF;
            *v16 = v23;
            KdConnection::WriteControlPacket((KdComConnection *)((char *)this - 16), 0, 4u, v23);
            v24 = *((_DWORD *)this + 42);
            v25 = v22 & 0x800;
            if ( *v16 == v24 )
            {
              if ( !v25 )
              {
LABEL_49:
                *((_DWORD *)this + 42) = v24 ^ 1;
                *a6 = *v15 + 16;
                return 0;
              }
            }
            else if ( !v25 )
            {
              LnkOut(0x80000000, L"READ: Unexpected Packet Id (Acked).\n");
              v8 = v29;
              goto LABEL_20;
            }
            LnkOut(0x80000000, L"READ: Got Sync Id, reset PacketId.\n");
            v24 = *v16;
            *((_DWORD *)this + 43) = -2139095040;
            goto LABEL_49;
          }
          LnkOut(0x80000000, L"READ: Packet trailing byte timeout.\n");
          v26 = -2147352561;
        }
      }
LABEL_70:
      v27 = -2147352555;
      if ( v14 != -2147024891 )
        return v26;
      return v27;
    }
    v17 = *((_WORD *)a4 + 2);
    if ( v17 != 4 )
    {
      if ( v17 == 6 )
      {
        *((_DWORD *)this + 43) = -2139095040;
        *((_DWORD *)this + 42) = -2139095040;
        LnkOut(0x80000000, L"READ: Received KD_RESET packet");
        if ( *((_DWORD *)this + 13) )
        {
          LnkOut(0x80000000, L"\n");
        }
        else
        {
          KdConnection::WriteControlPacket((KdComConnection *)((char *)this - 16), 3u, 6u, 0);
          LnkOut(0x80000000, L", send KD_RESET ACK packet\n");
        }
        result = 2147614736LL;
      }
      else
      {
        if ( v17 != 5 )
        {
          LnkOut(0x80000000, L"READ: Received Control packet with UNKNOWN type\n");
          return 2147614733LL;
        }
        LnkOut(0x80000000, L"READ: Received RESEND packet\n");
        result = 2147614737LL;
      }
LABEL_44:
      *((_DWORD *)this + 16) = 0;
      return result;
    }
    a2 = *((_DWORD *)this + 43);
    if ( *v16 == a2 )
    {
      if ( v8 != 4 )
        goto LABEL_20;
      *((_DWORD *)this + 43) = a2 ^ 1;
      LnkOut(0x80000000, L"READ: Received correct ACK packet.\n");
      *a6 = 16;
      result = 131074;
      goto LABEL_44;
    }
    v18 = PacketTypeToPacketName(4);
    LODWORD(v28) = *((_DWORD *)this + 16);
    LnkOut(
      0x80000000,
      L"READ: Received unmatched packet id = 0x%lx (expected 0x%lx), Type = %s, accum %d\n",
      *v16,
      v19,
      v18,
      v28);
    if ( ++*((_DWORD *)this + 16) <= *((_DWORD *)this + 15) )
    {
LABEL_20:
      v7 = v30;
      continue;
    }
    break;
  }
  LnkOut(0x80000000, L"READ: Too many unmatched packets (%d), request resync\n");
  *((_DWORD *)this + 16) = 0;
  return 2147614738LL;
}

```

## disassembly

```asm
0x180433bc0  mov     rax, rsp
0x180433bc3  mov     [rax+8], rbx
0x180433bc7  mov     [rax+18h], r8d
0x180433bcb  mov     [rax+10h], edx
0x180433bce  push    rbp
0x180433bcf  push    rsi
0x180433bd0  push    rdi
0x180433bd1  push    r12
0x180433bd3  push    r13
0x180433bd5  push    r14
0x180433bd7  push    r15
0x180433bd9  sub     rsp, 30h
0x180433bdd  mov     r10d, cs:KdTransportMaxPacketSize
0x180433be4  mov     rdi, r9
0x180433be7  mov     byte ptr [rax+20h], 0
0x180433beb  add     r10, 10h
0x180433bef  mov     eax, [rsp+68h+arg_20]
0x180433bf6  mov     r14d, r8d
0x180433bf9  mov     r13d, edx
0x180433bfc  mov     rbx, rcx
0x180433bff  cmp     rax, r10
0x180433c02  jnb     short loc_180433C0E
0x180433c04  mov     eax, 80070057h
0x180433c09  jmp     loc_18043426B
0x180433c0e  xor     r12d, r12d
0x180433c11  mov     ebp, 80000000h
0x180433c16  inc     r12d
0x180433c19  cmp     r12d, 64h ; 'd'
0x180433c1d  ja      loc_180434255
0x180433c23  lea     rsi, [rbx-10h]
0x180433c27  mov     r8, rdi; unsigned int *
0x180433c2a  mov     rcx, rsi; this
0x180433c2d  call    ?ReadPacketLeader@KdComConnection@@QEAAJKPEAK@Z; KdComConnection::ReadPacketLeader(ulong,ulong *)
0x180433c32  test    r14d, r14d
0x180433c35  mov     ebp, eax
0x180433c37  mov     r14d, 80000000h
0x180433c3d  jz      short loc_180433C61
0x180433c3f  lea     rdx, aAttemptingToGe; "Attempting to get initial breakpoint.\n"
0x180433c46  mov     ecx, r14d; unsigned int
0x180433c49  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433c4e  mov     rcx, rsi; this
0x180433c51  call    ?WriteBreakInPacket@KdConnection@@QEAAJXZ; KdConnection::WriteBreakInPacket(void)
0x180433c56  mov     [rsp+68h+arg_10], 0
0x180433c61  test    ebp, ebp
0x180433c63  jnz     loc_180434251
0x180433c69  mov     rax, [rbx]
0x180433c6c  lea     rdx, [rsp+68h+arg_18]
0x180433c74  mov     r8d, 1
0x180433c7a  mov     rcx, rbx
0x180433c7d  mov     rax, [rax+48h]
0x180433c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180433c86  mov     edx, eax
0x180433c88  test    eax, eax
0x180433c8a  jnz     loc_18043423E
0x180433c90  mov     al, [rsp+68h+arg_18]
0x180433c97  cmp     al, 30h ; '0'
0x180433c99  jz      short loc_180433C69
0x180433c9b  cmp     al, 69h ; 'i'
0x180433c9d  jz      short loc_180433C69
0x180433c9f  mov     [rdi+4], al
0x180433ca2  lea     rdx, [rdi+5]
0x180433ca6  mov     rax, [rbx]
0x180433ca9  mov     r8d, 1
0x180433caf  mov     rcx, rbx
0x180433cb2  mov     rax, [rax+48h]
0x180433cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180433cbb  mov     ebp, eax
0x180433cbd  test    eax, eax
0x180433cbf  jnz     loc_1804341FB
0x180433cc5  cmp     word ptr [rdi+4], 0Ch
0x180433cca  mov     ecx, r14d; unsigned int
0x180433ccd  jnb     loc_1804341CB
0x180433cd3  movzx   r8d, word ptr [rdi+4]
0x180433cd8  lea     rdx, aPackettype0xX; "      PacketType=0x%x, "
0x180433cdf  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433ce4  mov     rax, [rbx]
0x180433ce7  lea     r15, [rdi+6]
0x180433ceb  lea     r8d, [rbp+2]
0x180433cef  mov     rdx, r15
0x180433cf2  mov     rcx, rbx
0x180433cf5  mov     rax, [rax+48h]
0x180433cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180433cfe  mov     ebp, eax
0x180433d00  test    eax, eax
0x180433d02  jnz     loc_180434198
0x180433d08  movzx   r8d, word ptr [r15]
0x180433d0c  cmp     r8d, cs:KdTransportMaxPacketSize
0x180433d13  ja      loc_180434162
0x180433d19  lea     rdx, aBytes0xX; "Bytes=0x%x, "
0x180433d20  mov     ecx, r14d; unsigned int
0x180433d23  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433d28  mov     rax, [rbx]
0x180433d2b  lea     r14, [rdi+8]
0x180433d2f  lea     r8d, [rbp+4]
0x180433d33  mov     rdx, r14
0x180433d36  mov     rcx, rbx
0x180433d39  mov     rax, [rax+48h]
0x180433d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180433d42  mov     ebp, eax
0x180433d44  test    eax, eax
0x180433d46  jnz     loc_18043412A
0x180433d4c  mov     r8d, [r14]
0x180433d4f  lea     rdx, aPacketid0xX; "PacketId=0x%x,\n"
0x180433d56  mov     ebp, 80000000h
0x180433d5b  mov     ecx, ebp; unsigned int
0x180433d5d  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433d62  cmp     dword ptr [rdi], 69696969h
0x180433d68  jnz     loc_180433E05
0x180433d6e  movzx   eax, word ptr [rdi+4]
0x180433d72  mov     ecx, 4
0x180433d77  cmp     ax, cx
0x180433d7a  jnz     loc_180433F7A
0x180433d80  mov     edx, [rbx+0ACh]
0x180433d86  cmp     [r14], edx
0x180433d89  jz      short loc_180433DD1
0x180433d8b  movzx   ecx, ax
0x180433d8e  call    PacketTypeToPacketName
0x180433d93  mov     ecx, [rbx+40h]
0x180433d96  mov     r9d, edx
0x180433d99  mov     r8d, [r14]
0x180433d9c  lea     rdx, aReadReceivedUn; "READ: Received unmatched packet id = 0x"...
0x180433da3  mov     dword ptr [rsp+68h+var_40], ecx
0x180433da7  mov     ecx, ebp; unsigned int
0x180433da9  mov     [rsp+68h+var_48], rax
0x180433dae  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433db3  inc     dword ptr [rbx+40h]
0x180433db6  mov     r8d, [rbx+40h]
0x180433dba  cmp     r8d, [rbx+3Ch]
0x180433dbe  ja      loc_180433F60
0x180433dc4  mov     r14d, [rsp+68h+arg_10]
0x180433dcc  jmp     loc_180433C16
0x180433dd1  cmp     r13d, ecx
0x180433dd4  jnz     short loc_180433DC4
0x180433dd6  xor     edx, 1
0x180433dd9  mov     ecx, ebp; unsigned int
0x180433ddb  mov     [rbx+0ACh], edx
0x180433de1  lea     rdx, aReadReceivedCo_0; "READ: Received correct ACK packet.\n"
0x180433de8  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433ded  mov     rax, [rsp+68h+arg_28]
0x180433df5  mov     dword ptr [rax], 10h
0x180433dfb  mov     eax, 20002h
0x180433e00  jmp     loc_180433FF8
0x180433e05  mov     rax, [rbx]
0x180433e08  lea     rdx, [rdi+0Ch]
0x180433e0c  mov     r8d, 4
0x180433e12  mov     rcx, rbx
0x180433e15  mov     rax, [rax+48h]
0x180433e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180433e1e  mov     ebp, eax
0x180433e20  test    eax, eax
0x180433e22  jnz     loc_1804340FA
0x180433e28  lea     ebp, [rax+4]
0x180433e2b  cmp     r13d, ebp
0x180433e2e  jnz     short loc_180433E64
0x180433e30  mov     r9d, [rbx+0A8h]
0x180433e37  cmp     [r14], r9d
0x180433e3a  jz      short loc_180433E49
0x180433e3c  test    dword ptr [r14], 800h
0x180433e43  jz      loc_18043401A
0x180433e49  xor     dword ptr [rbx+0ACh], 1
0x180433e50  lea     rdx, aReadReceivedVa; "READ: Received VALID data packet 0x%lxw"...
0x180433e57  mov     r8d, [r14]
0x180433e5a  mov     ecx, 80000000h; unsigned int
0x180433e5f  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433e64  mov     dword ptr [rbx+40h], 0
0x180433e6b  mov     eax, [r14]
0x180433e6e  btr     eax, 0Bh
0x180433e72  add     eax, 7F800000h
0x180433e77  cmp     eax, 1
0x180433e7a  ja      loc_1804340DF
0x180433e80  mov     rax, [rbx]
0x180433e83  lea     rdx, [rdi+10h]
0x180433e87  movzx   r8d, word ptr [r15]
0x180433e8b  mov     rcx, rbx
0x180433e8e  mov     rax, [rax+48h]
0x180433e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180433e97  mov     ebp, eax
0x180433e99  test    eax, eax
0x180433e9b  jnz     loc_1804340C4
0x180433ea1  mov     rax, [rbx]
0x180433ea4  lea     r8d, [rbp+1]
0x180433ea8  lea     rdx, [rsp+68h+arg_18]
0x180433eb0  mov     rcx, rbx
0x180433eb3  mov     rax, [rax+48h]
0x180433eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180433ebc  mov     ebp, eax
0x180433ebe  test    eax, eax
0x180433ec0  jnz     loc_1804340A9
0x180433ec6  cmp     [rsp+68h+arg_18], 0AAh
0x180433ece  jnz     loc_1804340A9
0x180433ed4  movzx   r8d, word ptr [r15]; unsigned int
0x180433ed8  lea     rdx, [rdi+10h]; unsigned __int8 *
0x180433edc  call    ?ComputeChecksum@KdConnection@@QEAAKPEAEK@Z; KdConnection::ComputeChecksum(uchar *,ulong)
0x180433ee1  cmp     eax, [rdi+0Ch]
0x180433ee4  jnz     loc_18043408E
0x180433eea  movzx   ecx, word ptr [rdi+4]
0x180433eee  call    PacketTypeToPacketName
0x180433ef3  mov     r9d, [r14]
0x180433ef6  lea     rdx, aReadReceivedTy; "READ: Received Type %s data packet with"...
0x180433efd  mov     r8, rax
0x180433f00  mov     ecx, 80000000h; unsigned int
0x180433f05  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433f0a  mov     ebp, [r14]
0x180433f0d  xor     edx, edx; unsigned int
0x180433f0f  mov     r9d, ebp
0x180433f12  mov     rcx, rsi; this
0x180433f15  btr     r9d, 0Bh; unsigned int
0x180433f1a  mov     [r14], r9d
0x180433f1d  lea     r8d, [rdx+4]; unsigned __int16
0x180433f21  call    ?WriteControlPacket@KdConnection@@QEAAJKGK@Z; KdConnection::WriteControlPacket(ulong,ushort,ulong)
0x180433f26  mov     eax, [rbx+0A8h]
0x180433f2c  and     ebp, 800h
0x180433f32  cmp     [r14], eax
0x180433f35  jz      loc_18043404B
0x180433f3b  test    ebp, ebp
0x180433f3d  jnz     loc_18043404F
0x180433f43  mov     ebp, 80000000h
0x180433f48  lea     rdx, aReadUnexpected_0; "READ: Unexpected Packet Id (Acked).\n"
0x180433f4f  mov     ecx, ebp; unsigned int
0x180433f51  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433f56  mov     r13d, [rsp+68h+arg_8]
0x180433f5b  jmp     loc_180433DC4
0x180433f60  lea     rdx, aReadTooManyUnm; "READ: Too many unmatched packets (%d), "...
0x180433f67  mov     ecx, ebp; unsigned int
0x180433f69  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433f6e  mov     dword ptr [rbx+40h], 0
0x180433f75  jmp     loc_180434266
0x180433f7a  mov     edi, 6
0x180433f7f  mov     ecx, ebp; unsigned int
0x180433f81  cmp     ax, di
0x180433f84  jnz     short loc_180433FDB
0x180433f86  lea     rdx, aReadReceivedKd_0; "READ: Received KD_RESET packet"
0x180433f8d  mov     dword ptr [rbx+0ACh], 80800000h
0x180433f97  mov     dword ptr [rbx+0A8h], 80800000h
0x180433fa1  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433fa6  cmp     dword ptr [rbx+34h], 0
0x180433faa  jnz     short loc_180433FC6
0x180433fac  mov     r8d, edi; unsigned __int16
0x180433faf  lea     edx, [rdi-3]; unsigned int
0x180433fb2  xor     r9d, r9d; unsigned int
0x180433fb5  mov     rcx, rsi; this
0x180433fb8  call    ?WriteControlPacket@KdConnection@@QEAAJKGK@Z; KdConnection::WriteControlPacket(ulong,ushort,ulong)
0x180433fbd  lea     rdx, aSendKdResetAck; ", send KD_RESET ACK packet\n"
0x180433fc4  jmp     short loc_180433FCD
0x180433fc6  lea     rdx, asc_1805BAA38; "\n"
0x180433fcd  mov     ecx, ebp; unsigned int
0x180433fcf  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433fd4  mov     eax, 80020010h
0x180433fd9  jmp     short loc_180433FF8
0x180433fdb  mov     r8d, 5
0x180433fe1  cmp     ax, r8w
0x180433fe5  jnz     short loc_180434004
0x180433fe7  lea     rdx, aReadReceivedRe; "READ: Received RESEND packet\n"
0x180433fee  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433ff3  mov     eax, 80020011h
0x180433ff8  mov     dword ptr [rbx+40h], 0
0x180433fff  jmp     loc_18043426B
0x180434004  lea     rdx, aReadReceivedCo; "READ: Received Control packet with UNKN"...
0x18043400b  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180434010  mov     eax, 8002000Dh
0x180434015  jmp     loc_18043426B
0x18043401a  mov     r8d, [r14]
0x18043401d  lea     rdx, aReadReceivedDa_0; "READ: Received Data packet with unmatch"...
0x180434024  mov     ecx, 80000000h; unsigned int
0x180434029  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x18043402e  mov     r9d, [r14]; unsigned int
0x180434031  mov     r8d, ebp; unsigned __int16
0x180434034  mov     edx, 3; unsigned int
0x180434039  mov     rcx, rsi; this
0x18043403c  call    ?WriteControlPacket@KdConnection@@QEAAJKGK@Z; KdConnection::WriteControlPacket(ulong,ushort,ulong)
0x180434041  mov     eax, 80020009h
0x180434046  jmp     loc_18043426B
0x18043404b  test    ebp, ebp
0x18043404d  jz      short loc_18043406D
0x18043404f  lea     rdx, aReadGotSyncIdR; "READ: Got Sync Id, reset PacketId.\n"
0x180434056  mov     ecx, 80000000h; unsigned int
0x18043405b  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180434060  mov     eax, [r14]
0x180434063  mov     dword ptr [rbx+0ACh], 80800000h
0x18043406d  xor     eax, 1
0x180434070  mov     [rbx+0A8h], eax
0x180434076  mov     rax, [rsp+68h+arg_28]
0x18043407e  movzx   ecx, word ptr [r15]
0x180434082  add     ecx, 10h
0x180434085  mov     [rax], ecx
0x180434087  xor     eax, eax
0x180434089  jmp     loc_18043426B
0x18043408e  lea     rdx, aReadChecksumEr; "READ: Checksum error.\n"
0x180434095  mov     ecx, 80000000h; unsigned int
0x18043409a  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x18043409f  mov     eax, 8002000Ch
0x1804340a4  jmp     loc_18043426B
0x1804340a9  lea     rdx, aReadPacketTrai; "READ: Packet trailing byte timeout.\n"
0x1804340b0  mov     ecx, 80000000h; unsigned int
0x1804340b5  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804340ba  mov     eax, 8002000Fh
0x1804340bf  jmp     loc_18043422C
0x1804340c4  lea     rdx, aReadDataPacket_0; "READ: Data packet error (short read).\n"
0x1804340cb  mov     ecx, 80000000h; unsigned int
0x1804340d0  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
  ... truncated ...
```
