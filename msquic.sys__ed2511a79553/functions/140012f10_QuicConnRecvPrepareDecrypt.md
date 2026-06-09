# QuicConnRecvPrepareDecrypt

- ea: `0x140012f10`
- end: `0x1400131ed`
- name: `QuicConnRecvPrepareDecrypt`
- size: `733`
- prototype: `char __fastcall(__int64, __int64, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140012c80`

## callees

- `0x140012f10`
- `0x140026a88`
- `0x14003c8e0`
- `0x14003ec10`
- `0x1400465f4`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001312d`
- `ntoskrnl!_snprintf_s` at `0x14001317c`
- `ntoskrnl!_snprintf_s` at `0x14001312d`
- `ntoskrnl!_snprintf_s` at `0x14001317c`

## string_xrefs

- `0x140013164`: `Possible peer initiated key update [packet %llu]`

## pseudocode

```c
char __fastcall QuicConnRecvPrepareDecrypt(__int64 a1, __int64 a2, char *a3)
{
  _BYTE *v5; // rdx
  char v7; // cl
  char v8; // cl
  unsigned __int8 v9; // r10
  unsigned __int8 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rdx
  unsigned __int16 v13; // si
  unsigned int v14; // r8d
  __int64 v15; // r10
  unsigned __int8 v16; // dl
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r11
  unsigned __int16 v20; // ax
  int v21; // ecx
  unsigned __int16 v22; // si
  int v23; // ecx
  unsigned __int64 v24; // r10
  __int64 v25; // r9
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // r9
  unsigned __int64 v28; // rax
  char v29; // cl
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // rcx
  _QWORD v34[2]; // [rsp+30h] [rbp-A8h]
  char DstBuf[128]; // [rsp+40h] [rbp-98h] BYREF

  v5 = *(_BYTE **)(a2 + 56);
  v7 = *a3;
  if ( (*(_BYTE *)(a2 + 92) & 4) != 0 )
    v8 = v7 & 0x1F;
  else
    v8 = v7 & 0xF;
  v9 = 0;
  *v5 ^= v8;
  v10 = (**(_BYTE **)(a2 + 56) & 3) + 1;
  if ( (**(_BYTE **)(a2 + 56) & 3) == 0xFF )
  {
    v13 = *(_WORD *)(a2 + 82);
    v14 = 0;
    v19 = 0;
  }
  else
  {
    do
    {
      v11 = v9++;
      v12 = (unsigned int)v11 + *(unsigned __int16 *)(a2 + 82);
      *(_BYTE *)(v12 + *(_QWORD *)(a2 + 56)) ^= a3[v11 + 1];
    }
    while ( v9 < v10 );
    v13 = *(_WORD *)(a2 + 82);
    v14 = 0;
    v34[0] = 0;
    v15 = *(_QWORD *)(a2 + 56) + v13;
    v16 = 0;
    do
    {
      v17 = v16;
      v18 = v15 - v16++;
      *((_BYTE *)v34 + v17) = *(_BYTE *)(v18 + v10 - 1);
    }
    while ( v16 < v10 );
    v19 = v34[0];
  }
  *(_WORD *)(a2 + 82) = v13 + v10;
  v20 = *(_WORD *)(a2 + 84) - v10;
  v21 = *(_DWORD *)(a2 + 88);
  *(_WORD *)(a2 + 84) = v20;
  v22 = v20;
  if ( v21 )
  {
    v23 = v21 - 1;
    if ( !v23 || (v14 = 1, v23 != 1) )
      v14 = 2;
  }
  v24 = *(_QWORD *)(*(_QWORD *)(a1 + 8LL * v14 + 2760) + 8LL);
  v25 = -1LL << (8 * v10);
  v26 = v19 | v24 & v25;
  v27 = -v25;
  if ( v26 >= v24 )
  {
    if ( v27 - (v26 - v24) <= v26 - v24 && v26 >= v27 )
      v26 -= v27;
  }
  else
  {
    v28 = v26 + v27;
    if ( v27 - (v24 - v26) >= v24 - v26 )
      v28 = v26;
    v26 = v28;
  }
  v29 = *(_BYTE *)(a2 + 92);
  *(_QWORD *)(a2 + 40) = v26;
  *(_BYTE *)(a2 + 92) = v29 | 0x20;
  if ( v26 > 0x3FFFFFFFFFFFFFFFLL )
  {
    QuicPacketLogDrop(a1, a2, "Packet number too big");
    return 0;
  }
  if ( (v29 & 0x40) != 0 && v22 < 0x10u )
  {
    QuicPacketLogDrop(a1, a2, "Payload length less than encryption tag");
    return 0;
  }
  v31 = *(_QWORD *)(a1 + 2776);
  if ( (v29 & 4) != 0 && v14 == 2 && ((*(_BYTE *)(v31 + 424) ^ (**(_BYTE **)(a2 + 56) >> 2)) & 1) != 0 )
  {
    if ( v26 >= *(_QWORD *)(v31 + 408) )
    {
      if ( (byte_14005C48C & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Possible peer initiated key update [packet %llu]", v26);
        McTemplateU0ps_EtwWriteTransfer(v33, QuicConnLogVerbose, a1, DstBuf);
      }
      if ( (int)QuicCryptoGenerateNewKeys(a1) < 0 )
      {
        QuicPacketLogDrop(a1, a2, "Generate new packet keys");
        return 0;
      }
      *(_DWORD *)(a2 + 88) = 5;
    }
    else
    {
      if ( (byte_14005C48C & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Using old key to decrypt");
        McTemplateU0ps_EtwWriteTransfer(v32, QuicConnLogVerbose, a1, DstBuf);
      }
      *(_DWORD *)(a2 + 88) = 4;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140012f10  mov     [rsp+arg_10], rbx
0x140012f15  mov     [rsp+arg_18], rsi
0x140012f1a  push    rdi
0x140012f1b  sub     rsp, 0D0h
0x140012f22  mov     rax, cs:__security_cookie
0x140012f29  xor     rax, rsp
0x140012f2c  mov     [rsp+0D8h+var_18], rax
0x140012f34  mov     rbx, rdx
0x140012f37  mov     rdi, rcx
0x140012f3a  mov     rdx, [rdx+38h]
0x140012f3e  mov     r11, r8
0x140012f41  movzx   ecx, byte ptr [r8]
0x140012f45  test    byte ptr [rbx+5Ch], 4
0x140012f49  movzx   r8d, byte ptr [rdx]
0x140012f4d  jz      short loc_140012F54
0x140012f4f  and     cl, 1Fh
0x140012f52  jmp     short loc_140012F57
0x140012f54  and     cl, 0Fh
0x140012f57  xor     cl, r8b
0x140012f5a  mov     r10b, 0
0x140012f5d  mov     [rdx], cl
0x140012f5f  mov     rax, [rbx+38h]
0x140012f63  movzx   r9d, byte ptr [rax]
0x140012f67  and     r9b, 3
0x140012f6b  add     r9b, 1
0x140012f6f  jz      short loc_140012FD1
0x140012f71  movzx   edx, word ptr [rbx+52h]
0x140012f75  mov     rax, [rbx+38h]
0x140012f79  movzx   r8d, r10b
0x140012f7d  inc     r10b
0x140012f80  add     edx, r8d
0x140012f83  movzx   ecx, byte ptr [r8+r11+1]
0x140012f89  xor     [rdx+rax], cl
0x140012f8c  cmp     r10b, r9b
0x140012f8f  jb      short loc_140012F71
0x140012f91  movzx   esi, word ptr [rbx+52h]
0x140012f95  xor     r8d, r8d
0x140012f98  mov     r10d, esi
0x140012f9b  mov     [rsp+0D8h+var_A8], r8
0x140012fa0  add     r10, [rbx+38h]
0x140012fa4  xor     dl, dl
0x140012fa6  movzx   r11d, r9b
0x140012faa  nop     word ptr [rax+rax+00h]
0x140012fb0  movzx   ecx, dl
0x140012fb3  mov     rax, r10
0x140012fb6  sub     rax, rcx
0x140012fb9  inc     dl
0x140012fbb  movzx   eax, byte ptr [rax+r11-1]
0x140012fc1  mov     byte ptr [rsp+rcx+0D8h+var_A8], al
0x140012fc5  cmp     dl, r9b
0x140012fc8  jb      short loc_140012FB0
0x140012fca  mov     r11, [rsp+0D8h+var_A8]
0x140012fcf  jmp     short loc_140012FDB
0x140012fd1  movzx   esi, word ptr [rbx+52h]
0x140012fd5  xor     r8d, r8d
0x140012fd8  mov     r11d, r8d
0x140012fdb  movzx   ecx, r9b
0x140012fdf  lea     eax, [rsi+rcx]
0x140012fe2  mov     [rbx+52h], ax
0x140012fe6  movzx   eax, word ptr [rbx+54h]
0x140012fea  sub     ax, cx
0x140012fed  mov     ecx, [rbx+58h]
0x140012ff0  mov     [rbx+54h], ax
0x140012ff4  movzx   esi, ax
0x140012ff7  test    ecx, ecx
0x140012ff9  jz      short loc_140013011
0x140012ffb  sub     ecx, 1
0x140012ffe  jz      short loc_14001300B
0x140013000  mov     r8d, 1
0x140013006  cmp     ecx, 1
0x140013009  jz      short loc_140013011
0x14001300b  mov     r8d, 2
0x140013011  mov     eax, r8d
0x140013014  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14001301b  mov     rcx, [rdi+rax*8+0AC8h]
0x140013023  mov     r10, [rcx+8]
0x140013027  movzx   ecx, r9b
0x14001302b  shl     ecx, 3
0x14001302e  shl     rdx, cl
0x140013031  mov     r9, rdx
0x140013034  and     rdx, r10
0x140013037  or      rdx, r11
0x14001303a  neg     r9
0x14001303d  cmp     rdx, r10
0x140013040  jnb     short loc_14001305B
0x140013042  sub     r10, rdx
0x140013045  lea     rax, [rdx+r9]
0x140013049  mov     rcx, r9
0x14001304c  sub     rcx, r10
0x14001304f  cmp     rcx, r10
0x140013052  cmovnb  rax, rdx
0x140013056  mov     rdx, rax
0x140013059  jmp     short loc_140013074
0x14001305b  mov     rcx, rdx
0x14001305e  mov     rax, r9
0x140013061  sub     rcx, r10
0x140013064  sub     rax, rcx
0x140013067  cmp     rax, rcx
0x14001306a  ja      short loc_140013074
0x14001306c  cmp     rdx, r9
0x14001306f  jb      short loc_140013074
0x140013071  sub     rdx, r9
0x140013074  movzx   ecx, byte ptr [rbx+5Ch]
0x140013078  movzx   eax, cl
0x14001307b  mov     [rbx+28h], rdx
0x14001307f  or      al, 20h
0x140013081  mov     [rbx+5Ch], al
0x140013084  mov     rax, 3FFFFFFFFFFFFFFFh
0x14001308e  cmp     rdx, rax
0x140013091  jbe     short loc_1400130AC
0x140013093  lea     r8, aPacketNumberTo; "Packet number too big"
0x14001309a  mov     rdx, rbx
0x14001309d  mov     rcx, rdi
0x1400130a0  call    QuicPacketLogDrop
0x1400130a5  xor     al, al
0x1400130a7  jmp     loc_1400131C7
0x1400130ac  test    cl, 40h
0x1400130af  jz      short loc_1400130D0
0x1400130b1  cmp     si, 10h
0x1400130b5  jnb     short loc_1400130D0
0x1400130b7  lea     r8, aPayloadLengthL; "Payload length less than encryption tag"
0x1400130be  mov     rdx, rbx
0x1400130c1  mov     rcx, rdi
0x1400130c4  call    QuicPacketLogDrop
0x1400130c9  xor     al, al
0x1400130cb  jmp     loc_1400131C7
0x1400130d0  mov     r9, [rdi+0AD8h]
0x1400130d7  test    cl, 4
0x1400130da  jz      loc_1400131C5
0x1400130e0  cmp     r8d, 2
0x1400130e4  jnz     loc_1400131C5
0x1400130ea  mov     rax, [rbx+38h]
0x1400130ee  movzx   ecx, byte ptr [rax]
0x1400130f1  shr     cl, 2
0x1400130f4  xor     cl, [r9+1A8h]
0x1400130fb  test    cl, 1
0x1400130fe  jz      loc_1400131C5
0x140013104  cmp     rdx, [r9+198h]
0x14001310b  jnb     short loc_140013156
0x14001310d  test    cs:byte_14005C48C, 1
0x140013114  jz      short loc_14001314D
0x140013116  lea     edx, [r8+7Eh]; SizeInBytes
0x14001311a  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140013121  lea     r9, aUsingOldKeyToD; "Using old key to decrypt"
0x140013128  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x14001312d  call    cs:__imp__snprintf_s
0x140013134  nop     dword ptr [rax+rax+00h]
0x140013139  lea     r9, [rsp+0D8h+DstBuf]
0x14001313e  mov     r8, rdi
0x140013141  lea     rdx, QuicConnLogVerbose
0x140013148  call    McTemplateU0ps_EtwWriteTransfer
0x14001314d  mov     dword ptr [rbx+58h], 4
0x140013154  jmp     short loc_1400131C5
0x140013156  test    cs:byte_14005C48C, 1
0x14001315d  jz      short loc_14001319C
0x14001315f  mov     [rsp+0D8h+var_B8], rdx
0x140013164  lea     r9, aPossiblePeerIn; "Possible peer initiated key update [pac"...
0x14001316b  mov     edx, 80h; SizeInBytes
0x140013170  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x140013175  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001317c  call    cs:__imp__snprintf_s
0x140013183  nop     dword ptr [rax+rax+00h]
0x140013188  lea     r9, [rsp+0D8h+DstBuf]
0x14001318d  mov     r8, rdi
0x140013190  lea     rdx, QuicConnLogVerbose
0x140013197  call    McTemplateU0ps_EtwWriteTransfer
0x14001319c  mov     rcx, rdi
0x14001319f  call    QuicCryptoGenerateNewKeys
0x1400131a4  test    eax, eax
0x1400131a6  jns     short loc_1400131BE
0x1400131a8  lea     r8, aGenerateNewPac; "Generate new packet keys"
0x1400131af  mov     rdx, rbx
0x1400131b2  mov     rcx, rdi
0x1400131b5  call    QuicPacketLogDrop
0x1400131ba  xor     al, al
0x1400131bc  jmp     short loc_1400131C7
0x1400131be  mov     dword ptr [rbx+58h], 5
0x1400131c5  mov     al, 1
0x1400131c7  mov     rcx, [rsp+0D8h+var_18]
0x1400131cf  xor     rcx, rsp; StackCookie
0x1400131d2  call    __security_check_cookie
0x1400131d7  lea     r11, [rsp+0D8h+var_8]
0x1400131df  mov     rbx, [r11+20h]
0x1400131e3  mov     rsi, [r11+28h]
0x1400131e7  mov     rsp, r11
0x1400131ea  pop     rdi
0x1400131eb  retn
```
