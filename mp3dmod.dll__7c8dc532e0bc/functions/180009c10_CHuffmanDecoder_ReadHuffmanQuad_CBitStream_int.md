# CHuffmanDecoder::ReadHuffmanQuad(CBitStream &,int *)

- ea: `0x180009c10`
- end: `0x18000a09f`
- name: `?ReadHuffmanQuad@CHuffmanDecoder@@AEAA_NAEAVCBitStream@@PEAH@Z`
- size: `1167`
- prototype: `bool __fastcall(CHuffmanDecoder *__hidden this, struct CBitStream *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004230`

## callees

- `0x180009c10`

## pseudocode

```c
bool __fastcall CHuffmanDecoder::ReadHuffmanQuad(CHuffmanDecoder *this, struct CBitStream *a2, int *a3)
{
  __int64 v3; // r13
  int v4; // edi
  int v5; // r12d
  __int64 v6; // r15
  int v8; // esi
  __int64 v9; // rax
  unsigned __int16 v10; // r10
  unsigned int v11; // ecx
  int v12; // ebx
  unsigned __int64 v13; // r10
  unsigned int v14; // ecx
  unsigned int v15; // eax
  int v16; // ecx
  unsigned int v18; // r10d
  int v19; // edi
  unsigned int v20; // esi
  int v21; // ebx
  int v22; // r10d
  int v23; // esi
  bool result; // al
  int v25; // r12d
  __int64 v26; // r13
  unsigned int v27; // r15d
  unsigned int v28; // ecx
  unsigned __int16 v29; // r13
  int v30; // eax
  int v31; // eax
  int v32; // r13d
  __int64 v33; // r9
  unsigned int v34; // r15d
  unsigned __int16 v35; // r12
  unsigned int v36; // ecx
  int v37; // eax
  int v38; // eax
  int v39; // r13d
  __int64 v40; // r9
  unsigned int v41; // r15d
  unsigned __int16 v42; // r12
  unsigned int v43; // ecx
  int v44; // eax
  int v45; // eax
  int v46; // r13d
  __int64 v47; // r9
  unsigned int v48; // r15d
  unsigned __int16 v49; // r12
  unsigned int v50; // ecx
  int v51; // eax
  int v52; // eax
  __int64 v53; // r8
  __int64 v54; // r8
  __int64 v55; // r8
  __int64 v56; // r8
  int v57; // [rsp+38h] [rbp+8h]
  __int64 v58; // [rsp+48h] [rbp+18h]
  __int64 v59; // [rsp+48h] [rbp+18h]
  __int64 v60; // [rsp+48h] [rbp+18h]
  __int64 v61; // [rsp+48h] [rbp+18h]

  v3 = 0;
  v4 = *((_DWORD *)a2 + 6);
  v5 = *((_DWORD *)a2 + 5) - 1;
  v6 = *((_QWORD *)a2 + 6);
  v57 = *((_DWORD *)a2 + 8);
  v8 = v57;
  while ( 1 )
  {
    v9 = (*((int *)a2 + 9) >> 3) & 0xFFFFFFFE;
    v10 = (*(unsigned __int8 *)((unsigned int)(v9 + 1) + v6) | (unsigned __int16)(*(unsigned __int8 *)(v9 + v6) << 8)) << (*((_BYTE *)a2 + 36) & 0xF);
    v11 = 16 - (*((_DWORD *)a2 + 9) & 0xF);
    if ( v11 < 2 )
      v10 |= (unsigned __int16)(*(unsigned __int8 *)(((*((_DWORD *)a2 + 4) - 1)
                                                    & (((*((int *)a2 + 9) >> 3) & 0xFFFFFFFE) + 2))
                                                   + 1
                                                   + v6)
                              | (*(unsigned __int8 *)(((*((_DWORD *)a2 + 4) - 1)
                                                     & (((*((int *)a2 + 9) >> 3) & 0xFFFFFFFE) + 2))
                                                    + v6) << 8)) >> v11;
    v12 = v5 & (*((_DWORD *)a2 + 9) + 2);
    *((_DWORD *)a2 + 9) = v12;
    v8 += 2;
    *((_DWORD *)a2 + 8) = v8;
    v4 -= 2;
    *((_DWORD *)a2 + 6) = v4;
    v13 = 4 * (((unsigned __int64)v10 >> 14) + 4 * v3);
    v14 = *(_DWORD *)(v13 + *((_QWORD *)&CHuffmanTable::ht + 2 * *(unsigned int *)(*((_QWORD *)this + 5) + 8LL) + 1));
    v15 = v14 >> 8;
    if ( (v14 & 0xFF00) != 0 )
      break;
    v3 = (unsigned __int8)v14;
  }
  v16 = BYTE1(v14) - v8 + v57;
  *((_DWORD *)a2 + 6) = v4 - v16;
  *((_DWORD *)a2 + 8) = (unsigned __int8)v15 + v57;
  *((_DWORD *)a2 + 9) = v5 & (v16 + v12);
  v18 = (unsigned __int8)*(_DWORD *)(*((_QWORD *)&CHuffmanTable::ht
                                     + 2 * *(unsigned int *)(*((_QWORD *)this + 5) + 8LL)
                                     + 1)
                                   + v13);
  *((_DWORD *)this + 8) = v18;
  v19 = (v18 >> 2) & 1;
  v20 = v18 >> 3;
  v21 = (v18 >> 1) & 1;
  v22 = v18 & 1;
  v23 = v20 & 1;
  if ( v23 )
  {
    v46 = *((_DWORD *)a2 + 9);
    v47 = *((_QWORD *)a2 + 6);
    v48 = *((_DWORD *)this + 14);
    v61 = (v46 >> 3) & 0xFFFFFFFE;
    v49 = (*(unsigned __int8 *)((unsigned int)(v61 + 1) + v47) | (unsigned __int16)(*(unsigned __int8 *)(v61 + v47) << 8)) << (*((_BYTE *)a2 + 36) & 0xF);
    v50 = 16 - (v46 & 0xF);
    if ( v48 > v50 )
    {
      v56 = ((_DWORD)v61 + 2) & (unsigned int)(*((_DWORD *)a2 + 4) - 1);
      v49 |= (unsigned __int16)(*(unsigned __int8 *)((unsigned int)(v56 + 1) + *((_QWORD *)a2 + 6))
                              | (*(unsigned __int8 *)(v56 + v47) << 8)) >> v50;
    }
    v51 = *((_DWORD *)a2 + 5);
    *((_DWORD *)a2 + 8) += v48;
    *((_DWORD *)a2 + 6) -= v48;
    *((_DWORD *)a2 + 9) = (v51 - 1) & (v48 + v46);
    v52 = v49 >> (16 - v48);
    *((_DWORD *)this + 15) = v52;
    if ( v52 == 1 )
      v23 = -v23;
  }
  if ( v19 )
  {
    v39 = *((_DWORD *)a2 + 9);
    v40 = *((_QWORD *)a2 + 6);
    v41 = *((_DWORD *)this + 14);
    v60 = (v39 >> 3) & 0xFFFFFFFE;
    v42 = (*(unsigned __int8 *)((unsigned int)(v60 + 1) + v40) | (unsigned __int16)(*(unsigned __int8 *)(v60 + v40) << 8)) << (*((_BYTE *)a2 + 36) & 0xF);
    v43 = 16 - (v39 & 0xF);
    if ( v41 > v43 )
    {
      v55 = ((_DWORD)v60 + 2) & (unsigned int)(*((_DWORD *)a2 + 4) - 1);
      v42 |= (unsigned __int16)(*(unsigned __int8 *)((unsigned int)(v55 + 1) + *((_QWORD *)a2 + 6))
                              | (*(unsigned __int8 *)(v55 + v40) << 8)) >> v43;
    }
    v44 = *((_DWORD *)a2 + 5);
    *((_DWORD *)a2 + 8) += v41;
    *((_DWORD *)a2 + 6) -= v41;
    *((_DWORD *)a2 + 9) = (v44 - 1) & (v41 + v39);
    v45 = v42 >> (16 - v41);
    *((_DWORD *)this + 15) = v45;
    if ( v45 == 1 )
      v19 = -v19;
  }
  if ( v21 )
  {
    v32 = *((_DWORD *)a2 + 9);
    v33 = *((_QWORD *)a2 + 6);
    v34 = *((_DWORD *)this + 14);
    v59 = (v32 >> 3) & 0xFFFFFFFE;
    v35 = (*(unsigned __int8 *)((unsigned int)(v59 + 1) + v33) | (unsigned __int16)(*(unsigned __int8 *)(v59 + v33) << 8)) << (*((_BYTE *)a2 + 36) & 0xF);
    v36 = 16 - (v32 & 0xF);
    if ( v34 > v36 )
    {
      v54 = ((_DWORD)v59 + 2) & (unsigned int)(*((_DWORD *)a2 + 4) - 1);
      v35 |= (unsigned __int16)(*(unsigned __int8 *)((unsigned int)(v54 + 1) + *((_QWORD *)a2 + 6))
                              | (*(unsigned __int8 *)(v54 + v33) << 8)) >> v36;
    }
    v37 = *((_DWORD *)a2 + 5);
    *((_DWORD *)a2 + 8) += v34;
    *((_DWORD *)a2 + 6) -= v34;
    *((_DWORD *)a2 + 9) = (v37 - 1) & (v34 + v32);
    v38 = v35 >> (16 - v34);
    *((_DWORD *)this + 15) = v38;
    if ( v38 == 1 )
      v21 = -v21;
  }
  if ( v22 )
  {
    v25 = *((_DWORD *)a2 + 9);
    v26 = *((_QWORD *)a2 + 6);
    v27 = *((_DWORD *)this + 14);
    v58 = (v25 >> 3) & 0xFFFFFFFE;
    v28 = 16 - (v25 & 0xF);
    if ( v27 > v28 )
    {
      v53 = ((_DWORD)v58 + 2) & (unsigned int)(*((_DWORD *)a2 + 4) - 1);
      v29 = ((*(unsigned __int8 *)((unsigned int)(v58 + 1) + v26)
            | (unsigned __int16)(*(unsigned __int8 *)(v58 + v26) << 8)) << (*((_BYTE *)a2 + 36) & 0xF))
          | ((unsigned __int16)(*(unsigned __int8 *)((unsigned int)(v53 + 1) + *((_QWORD *)a2 + 6))
                              | (*(unsigned __int8 *)(v53 + v26) << 8)) >> v28);
    }
    else
    {
      v29 = (*(unsigned __int8 *)((unsigned int)(v58 + 1) + v26)
           | (unsigned __int16)(*(unsigned __int8 *)(v58 + v26) << 8)) << (*((_BYTE *)a2 + 36) & 0xF);
    }
    v30 = *((_DWORD *)a2 + 5);
    *((_DWORD *)a2 + 8) += v27;
    *((_DWORD *)a2 + 6) -= v27;
    *((_DWORD *)a2 + 9) = (v30 - 1) & (v27 + v25);
    v31 = v29 >> (16 - v27);
    *((_DWORD *)this + 15) = v31;
    if ( v31 == 1 )
      v22 = -v22;
  }
  result = 1;
  a3[2] = v21;
  *a3 = v23;
  a3[1] = v19;
  a3[3] = v22;
  return result;
}

```

## disassembly

```asm
0x180009c10  mov     [rsp+arg_8], rbx
0x180009c15  mov     [rsp+arg_18], rbp
0x180009c1a  mov     [rsp+arg_10], r8
0x180009c1f  push    rsi
0x180009c20  push    rdi
0x180009c21  push    r12
0x180009c23  push    r13
0x180009c25  push    r14
0x180009c27  push    r15
0x180009c29  mov     eax, [rdx+20h]
0x180009c2c  lea     r11, ?ht@CHuffmanTable@@0QBUhuffmantab@1@B; CHuffmanTable::huffmantab const near * const CHuffmanTable::ht
0x180009c33  mov     r12d, [rdx+14h]
0x180009c37  xor     r13d, r13d
0x180009c3a  mov     edi, [rdx+18h]
0x180009c3d  dec     r12d
0x180009c40  mov     r15, [rdx+30h]
0x180009c44  mov     r14, rcx
0x180009c47  mov     [rsp+30h+arg_0], eax
0x180009c4b  mov     esi, eax
0x180009c4d  mov     ebp, 10h
0x180009c52  mov     ebx, [rdx+24h]
0x180009c55  mov     eax, ebx
0x180009c57  sar     eax, 3
0x180009c5a  mov     r8d, ebx
0x180009c5d  and     eax, 0FFFFFFFEh
0x180009c60  and     r8d, 0Fh
0x180009c64  mov     r9d, eax
0x180009c67  mov     ecx, r8d
0x180009c6a  movzx   r10d, byte ptr [rax+r15]
0x180009c6f  inc     eax
0x180009c71  shl     r10w, 8
0x180009c76  movzx   eax, byte ptr [rax+r15]
0x180009c7b  or      r10w, ax
0x180009c7f  shl     r10w, cl
0x180009c83  mov     ecx, ebp
0x180009c85  sub     ecx, r8d
0x180009c88  cmp     ecx, 2
0x180009c8b  jb      loc_180009D81
0x180009c91  add     ebx, 2
0x180009c94  movzx   ecx, r10w
0x180009c98  shr     rcx, 0Eh
0x180009c9c  and     ebx, r12d
0x180009c9f  mov     [rdx+24h], ebx
0x180009ca2  add     esi, 2
0x180009ca5  mov     [rdx+20h], esi
0x180009ca8  add     edi, 0FFFFFFFEh
0x180009cab  mov     [rdx+18h], edi
0x180009cae  mov     rax, [r14+28h]
0x180009cb2  lea     rcx, [rcx+r13*4]
0x180009cb6  lea     r10, ds:0[rcx*4]
0x180009cbe  mov     eax, [rax+8]
0x180009cc1  add     rax, rax
0x180009cc4  mov     rax, [r11+rax*8+8]
0x180009cc9  mov     ecx, [r10+rax]
0x180009ccd  mov     eax, ecx
0x180009ccf  shr     eax, 8
0x180009cd2  test    ecx, 0FF00h
0x180009cd8  jnz     short loc_180009CE3
0x180009cda  movzx   r13d, cl
0x180009cde  jmp     loc_180009C52
0x180009ce3  mov     ecx, [rsp+30h+arg_0]
0x180009ce7  movzx   eax, al
0x180009cea  sub     eax, esi
0x180009cec  add     ecx, eax
0x180009cee  sub     edi, ecx
0x180009cf0  mov     [rdx+18h], edi
0x180009cf3  lea     eax, [rcx+rsi]
0x180009cf6  mov     [rdx+20h], eax
0x180009cf9  lea     eax, [rcx+rbx]
0x180009cfc  and     eax, r12d
0x180009cff  mov     [rdx+24h], eax
0x180009d02  mov     rax, [r14+28h]
0x180009d06  mov     eax, [rax+8]
0x180009d09  add     rax, rax
0x180009d0c  mov     rax, [r11+rax*8+8]
0x180009d11  mov     r11, [rsp+30h+arg_10]
0x180009d16  mov     r10d, [rax+r10]
0x180009d1a  movzx   r10d, r10b
0x180009d1e  mov     edi, r10d
0x180009d21  mov     [r14+20h], r10d
0x180009d25  mov     ebx, r10d
0x180009d28  shr     edi, 2
0x180009d2b  shr     ebx, 1
0x180009d2d  mov     esi, r10d
0x180009d30  and     edi, 1
0x180009d33  shr     esi, 3
0x180009d36  and     ebx, 1
0x180009d39  and     r10d, 1
0x180009d3d  and     esi, 1
0x180009d40  jnz     loc_180009F3B
0x180009d46  test    edi, edi
0x180009d48  jnz     loc_180009EBB
0x180009d4e  test    ebx, ebx
0x180009d50  jnz     loc_180009E3B
0x180009d56  test    r10d, r10d
0x180009d59  jnz     short loc_180009DB2
0x180009d5b  mov     rbp, [rsp+30h+arg_18]
0x180009d60  mov     al, 1
0x180009d62  mov     [r11+8], ebx
0x180009d66  mov     rbx, [rsp+30h+arg_8]
0x180009d6b  mov     [r11], esi
0x180009d6e  mov     [r11+4], edi
0x180009d72  mov     [r11+0Ch], r10d
0x180009d76  pop     r15
0x180009d78  pop     r14
0x180009d7a  pop     r13
0x180009d7c  pop     r12
0x180009d7e  pop     rdi
0x180009d7f  pop     rsi
0x180009d80  retn
0x180009d81  mov     eax, [rdx+10h]
0x180009d84  lea     r8d, [r9+2]
0x180009d88  dec     eax
0x180009d8a  and     r8d, eax
0x180009d8d  mov     eax, r8d
0x180009d90  movzx   r9d, byte ptr [r8+r15]
0x180009d95  shl     r9w, 8
0x180009d9a  inc     eax
0x180009d9c  movzx   eax, byte ptr [rax+r15]
0x180009da1  or      r9w, ax
0x180009da5  shr     r9w, cl
0x180009da9  or      r10w, r9w
0x180009dad  jmp     loc_180009C91
0x180009db2  mov     r12d, [rdx+24h]
0x180009db6  mov     eax, r12d
0x180009db9  mov     r13, [rdx+30h]
0x180009dbd  mov     r8d, r12d
0x180009dc0  mov     r15d, [r14+38h]
0x180009dc4  and     r8d, 0Fh
0x180009dc8  sar     eax, 3
0x180009dcb  mov     ecx, r8d
0x180009dce  and     eax, 0FFFFFFFEh
0x180009dd1  mov     [rsp+30h+arg_10], rax
0x180009dd6  movzx   r9d, byte ptr [rax+r13]
0x180009ddb  shl     r9w, 8
0x180009de0  inc     eax
0x180009de2  movzx   eax, byte ptr [rax+r13]
0x180009de7  or      r9w, ax
0x180009deb  shl     r9w, cl
0x180009def  mov     ecx, ebp
0x180009df1  sub     ecx, r8d
0x180009df4  cmp     r15d, ecx
0x180009df7  ja      loc_180009FBB
0x180009dfd  movzx   r13d, r9w
0x180009e01  mov     eax, [rdx+14h]
0x180009e04  lea     r8d, [r15+r12]
0x180009e08  add     [rdx+20h], r15d
0x180009e0c  dec     eax
0x180009e0e  sub     [rdx+18h], r15d
0x180009e12  and     r8d, eax
0x180009e15  sub     ebp, r15d
0x180009e18  movzx   eax, r13w
0x180009e1c  movzx   ecx, bpl
0x180009e20  mov     [rdx+24h], r8d
0x180009e24  shr     eax, cl
0x180009e26  mov     [r14+3Ch], eax
0x180009e2a  cmp     eax, 1
0x180009e2d  jnz     loc_180009D5B
0x180009e33  neg     r10d
0x180009e36  jmp     loc_180009D5B
0x180009e3b  mov     r13d, [rdx+24h]
0x180009e3f  mov     eax, r13d
0x180009e42  mov     r9, [rdx+30h]
0x180009e46  mov     r8d, r13d
0x180009e49  mov     r15d, [r14+38h]
0x180009e4d  and     r8d, 0Fh
0x180009e51  sar     eax, 3
0x180009e54  mov     ecx, r8d
0x180009e57  and     eax, 0FFFFFFFEh
0x180009e5a  mov     [rsp+30h+arg_10], rax
0x180009e5f  movzx   r12d, byte ptr [rax+r9]
0x180009e64  shl     r12w, 8
0x180009e69  inc     eax
0x180009e6b  movzx   eax, byte ptr [rax+r9]
0x180009e70  or      r12w, ax
0x180009e74  shl     r12w, cl
0x180009e78  mov     ecx, ebp
0x180009e7a  sub     ecx, r8d
0x180009e7d  cmp     r15d, ecx
0x180009e80  ja      loc_180009FF4
0x180009e86  mov     eax, [rdx+14h]
0x180009e89  lea     ecx, [r15+r13]
0x180009e8d  add     [rdx+20h], r15d
0x180009e91  dec     eax
0x180009e93  sub     [rdx+18h], r15d
0x180009e97  and     ecx, eax
0x180009e99  mov     [rdx+24h], ecx
0x180009e9c  mov     ecx, ebp
0x180009e9e  sub     ecx, r15d
0x180009ea1  movzx   eax, r12w
0x180009ea5  shr     eax, cl
0x180009ea7  mov     [r14+3Ch], eax
0x180009eab  cmp     eax, 1
0x180009eae  jnz     loc_180009D56
0x180009eb4  neg     ebx
0x180009eb6  jmp     loc_180009D56
0x180009ebb  mov     r13d, [rdx+24h]
0x180009ebf  mov     eax, r13d
0x180009ec2  mov     r9, [rdx+30h]
0x180009ec6  mov     r8d, r13d
0x180009ec9  mov     r15d, [r14+38h]
0x180009ecd  and     r8d, 0Fh
0x180009ed1  sar     eax, 3
0x180009ed4  mov     ecx, r8d
0x180009ed7  and     eax, 0FFFFFFFEh
0x180009eda  mov     [rsp+30h+arg_10], rax
0x180009edf  movzx   r12d, byte ptr [rax+r9]
0x180009ee4  shl     r12w, 8
0x180009ee9  inc     eax
0x180009eeb  movzx   eax, byte ptr [rax+r9]
0x180009ef0  or      r12w, ax
0x180009ef4  shl     r12w, cl
0x180009ef8  mov     ecx, ebp
0x180009efa  sub     ecx, r8d
0x180009efd  cmp     r15d, ecx
0x180009f00  ja      loc_18000A02D
0x180009f06  mov     eax, [rdx+14h]
0x180009f09  lea     ecx, [r15+r13]
0x180009f0d  add     [rdx+20h], r15d
0x180009f11  dec     eax
0x180009f13  sub     [rdx+18h], r15d
0x180009f17  and     ecx, eax
0x180009f19  mov     [rdx+24h], ecx
0x180009f1c  mov     ecx, ebp
0x180009f1e  sub     ecx, r15d
0x180009f21  movzx   eax, r12w
0x180009f25  shr     eax, cl
0x180009f27  mov     [r14+3Ch], eax
0x180009f2b  cmp     eax, 1
0x180009f2e  jnz     loc_180009D4E
0x180009f34  neg     edi
0x180009f36  jmp     loc_180009D4E
0x180009f3b  mov     r13d, [rdx+24h]
0x180009f3f  mov     eax, r13d
0x180009f42  mov     r9, [rdx+30h]
0x180009f46  mov     r8d, r13d
0x180009f49  mov     r15d, [r14+38h]
0x180009f4d  and     r8d, 0Fh
0x180009f51  sar     eax, 3
0x180009f54  mov     ecx, r8d
0x180009f57  and     eax, 0FFFFFFFEh
0x180009f5a  mov     [rsp+30h+arg_10], rax
0x180009f5f  movzx   r12d, byte ptr [rax+r9]
0x180009f64  shl     r12w, 8
0x180009f69  inc     eax
0x180009f6b  movzx   eax, byte ptr [rax+r9]
0x180009f70  or      r12w, ax
0x180009f74  shl     r12w, cl
0x180009f78  mov     ecx, ebp
0x180009f7a  sub     ecx, r8d
0x180009f7d  cmp     r15d, ecx
0x180009f80  ja      loc_18000A066
0x180009f86  mov     eax, [rdx+14h]
0x180009f89  lea     ecx, [r15+r13]
0x180009f8d  add     [rdx+20h], r15d
0x180009f91  dec     eax
0x180009f93  sub     [rdx+18h], r15d
0x180009f97  and     ecx, eax
0x180009f99  mov     [rdx+24h], ecx
0x180009f9c  mov     ecx, ebp
0x180009f9e  sub     ecx, r15d
0x180009fa1  movzx   eax, r12w
0x180009fa5  shr     eax, cl
0x180009fa7  mov     [r14+3Ch], eax
0x180009fab  cmp     eax, 1
0x180009fae  jnz     loc_180009D46
0x180009fb4  neg     esi
0x180009fb6  jmp     loc_180009D46
0x180009fbb  mov     r8d, [rdx+10h]
0x180009fbf  mov     rax, [rsp+30h+arg_10]
0x180009fc4  dec     r8d
0x180009fc7  add     eax, 2
0x180009fca  and     r8d, eax
0x180009fcd  mov     rax, [rdx+30h]
0x180009fd1  movzx   r13d, byte ptr [r8+r13]
0x180009fd6  inc     r8d
0x180009fd9  shl     r13w, 8
0x180009fde  movzx   eax, byte ptr [r8+rax]
0x180009fe3  or      r13w, ax
0x180009fe7  shr     r13w, cl
0x180009feb  or      r13w, r9w
0x180009fef  jmp     loc_180009E01
0x180009ff4  mov     r8d, [rdx+10h]
0x180009ff8  mov     rax, [rsp+30h+arg_10]
0x180009ffd  dec     r8d
0x18000a000  add     eax, 2
0x18000a003  and     r8d, eax
0x18000a006  mov     rax, [rdx+30h]
0x18000a00a  movzx   r9d, byte ptr [r8+r9]
0x18000a00f  inc     r8d
0x18000a012  shl     r9w, 8
0x18000a017  movzx   eax, byte ptr [r8+rax]
0x18000a01c  or      r9w, ax
0x18000a020  shr     r9w, cl
0x18000a024  or      r12w, r9w
0x18000a028  jmp     loc_180009E86
0x18000a02d  mov     r8d, [rdx+10h]
0x18000a031  mov     rax, [rsp+30h+arg_10]
0x18000a036  dec     r8d
0x18000a039  add     eax, 2
  ... truncated ...
```
