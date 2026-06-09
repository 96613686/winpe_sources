# CHuffmanBitObj::ReadFrom(CBitStream &)

- ea: `0x180010e20`
- end: `0x180010f51`
- name: `?ReadFrom@CHuffmanBitObj@@QEAA_NAEAVCBitStream@@@Z`
- size: `305`
- prototype: `bool __fastcall(CHuffmanBitObj *__hidden this, struct CBitStream *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b870`
- `0x18000bad0`

## callees

- `0x180010e20`

## pseudocode

```c
bool __fastcall CHuffmanBitObj::ReadFrom(CHuffmanBitObj *this, struct CBitStream *a2)
{
  int v2; // r12d
  __int64 v3; // rsi
  int v4; // edi
  int v5; // r14d
  __int64 v6; // r11
  int v9; // ebp
  __int64 v10; // rax
  unsigned int v11; // ecx
  __int64 v12; // rdx
  unsigned __int16 v13; // ax
  int v14; // edx
  unsigned __int64 v15; // r8
  unsigned int v16; // ecx
  unsigned int v17; // eax
  int v18; // ecx
  bool result; // al

  v2 = *((_DWORD *)a2 + 8);
  v3 = 0;
  v4 = *((_DWORD *)a2 + 6);
  v5 = *((_DWORD *)a2 + 5) - 1;
  v6 = *((_QWORD *)a2 + 6);
  v9 = v2;
  while ( 1 )
  {
    v10 = (*((int *)a2 + 9) >> 3) & 0xFFFFFFFE;
    v11 = 16 - (*((_DWORD *)a2 + 9) & 0xF);
    if ( v11 >= 2 )
    {
      v13 = (*(unsigned __int8 *)((unsigned int)(v10 + 1) + v6) | (unsigned __int16)(*(unsigned __int8 *)(v10 + v6) << 8)) << (*((_BYTE *)a2 + 36) & 0xF);
    }
    else
    {
      v12 = (*((_DWORD *)a2 + 4) - 1) & (((*((int *)a2 + 9) >> 3) & 0xFFFFFFFE) + 2);
      v13 = ((*(unsigned __int8 *)((unsigned int)(v10 + 1) + v6)
            | (unsigned __int16)(*(unsigned __int8 *)(v10 + v6) << 8)) << (*((_BYTE *)a2 + 36) & 0xF))
          | ((unsigned __int16)(*(unsigned __int8 *)((unsigned int)(v12 + 1) + v6)
                              | (*(unsigned __int8 *)(v12 + v6) << 8)) >> v11);
    }
    v14 = v5 & (*((_DWORD *)a2 + 9) + 2);
    *((_DWORD *)a2 + 9) = v14;
    v9 += 2;
    *((_DWORD *)a2 + 8) = v9;
    v4 -= 2;
    *((_DWORD *)a2 + 6) = v4;
    v15 = 4 * (((unsigned __int64)v13 >> 14) + 4 * v3);
    v16 = *(_DWORD *)(v15 + *((_QWORD *)&CHuffmanTable::ht + 2 * *(unsigned int *)(*((_QWORD *)this + 2) + 8LL) + 1));
    v17 = v16 >> 8;
    if ( (v16 & 0xFF00) != 0 )
      break;
    v3 = (unsigned __int8)v16;
  }
  v18 = v2 + BYTE1(v16) - v9;
  *((_DWORD *)a2 + 6) = v4 - v18;
  *((_DWORD *)a2 + 8) = v2 + (unsigned __int8)v17;
  *((_DWORD *)a2 + 9) = v5 & (v18 + v14);
  result = 1;
  *((_DWORD *)this + 2) = *(unsigned __int8 *)(v15
                                             + *((_QWORD *)&CHuffmanTable::ht
                                               + 2 * *(unsigned int *)(*((_QWORD *)this + 2) + 8LL)
                                               + 1));
  return result;
}

```

## disassembly

```asm
0x180010e20  push    rbx
0x180010e22  push    rbp
0x180010e23  push    rsi
0x180010e24  push    rdi
0x180010e25  push    r12
0x180010e27  push    r13
0x180010e29  push    r14
0x180010e2b  push    r15
0x180010e2d  mov     r14d, [rdx+14h]
0x180010e31  lea     r13, ?ht@CHuffmanTable@@0QBUhuffmantab@1@B; CHuffmanTable::huffmantab const near * const CHuffmanTable::ht
0x180010e38  mov     r12d, [rdx+20h]
0x180010e3c  xor     esi, esi
0x180010e3e  mov     edi, [rdx+18h]
0x180010e41  dec     r14d
0x180010e44  mov     r11, [rdx+30h]
0x180010e48  mov     r10, rdx
0x180010e4b  mov     r15, rcx
0x180010e4e  mov     ebp, r12d
0x180010e51  mov     ebx, [r10+24h]
0x180010e55  mov     eax, ebx
0x180010e57  sar     eax, 3
0x180010e5a  mov     edx, ebx
0x180010e5c  and     eax, 0FFFFFFFEh
0x180010e5f  and     edx, 0Fh
0x180010e62  mov     r8d, eax
0x180010e65  mov     ecx, edx
0x180010e67  movzx   r9d, byte ptr [rax+r11]
0x180010e6c  inc     eax
0x180010e6e  shl     r9w, 8
0x180010e73  movzx   eax, byte ptr [rax+r11]
0x180010e78  or      r9w, ax
0x180010e7c  shl     r9w, cl
0x180010e80  mov     ecx, 10h
0x180010e85  sub     ecx, edx
0x180010e87  cmp     ecx, 2
0x180010e8a  jnb     short loc_180010EB4
0x180010e8c  mov     eax, [r10+10h]
0x180010e90  lea     edx, [r8+2]
0x180010e94  dec     eax
0x180010e96  and     edx, eax
0x180010e98  movzx   eax, byte ptr [rdx+r11]
0x180010e9d  shl     ax, 8
0x180010ea1  inc     edx
0x180010ea3  movzx   edx, byte ptr [rdx+r11]
0x180010ea8  or      ax, dx
0x180010eab  shr     ax, cl
0x180010eae  or      ax, r9w
0x180010eb2  jmp     short loc_180010EB8
0x180010eb4  movzx   eax, r9w
0x180010eb8  movzx   ecx, ax
0x180010ebb  lea     edx, [rbx+2]
0x180010ebe  shr     rcx, 0Eh
0x180010ec2  and     edx, r14d
0x180010ec5  mov     [r10+24h], edx
0x180010ec9  add     ebp, 2
0x180010ecc  mov     [r10+20h], ebp
0x180010ed0  add     edi, 0FFFFFFFEh
0x180010ed3  mov     [r10+18h], edi
0x180010ed7  mov     rax, [r15+10h]
0x180010edb  lea     rcx, [rcx+rsi*4]
0x180010edf  lea     r8, ds:0[rcx*4]
0x180010ee7  mov     eax, [rax+8]
0x180010eea  add     rax, rax
0x180010eed  mov     rax, [r13+rax*8+8]
0x180010ef2  mov     ecx, [r8+rax]
0x180010ef6  mov     eax, ecx
0x180010ef8  shr     eax, 8
0x180010efb  test    ecx, 0FF00h
0x180010f01  jnz     short loc_180010F0B
0x180010f03  movzx   esi, cl
0x180010f06  jmp     loc_180010E51
0x180010f0b  movzx   ecx, al
0x180010f0e  sub     ecx, ebp
0x180010f10  add     ecx, r12d
0x180010f13  sub     edi, ecx
0x180010f15  mov     [r10+18h], edi
0x180010f19  lea     eax, [rcx+rbp]
0x180010f1c  mov     [r10+20h], eax
0x180010f20  lea     eax, [rcx+rdx]
0x180010f23  and     eax, r14d
0x180010f26  mov     [r10+24h], eax
0x180010f2a  mov     rax, [r15+10h]
0x180010f2e  mov     eax, [rax+8]
0x180010f31  add     rax, rax
0x180010f34  mov     rax, [r13+rax*8+8]
0x180010f39  movzx   ecx, byte ptr [r8+rax]
0x180010f3e  mov     al, 1
0x180010f40  mov     [r15+8], ecx
0x180010f44  pop     r15
0x180010f46  pop     r14
0x180010f48  pop     r13
0x180010f4a  pop     r12
0x180010f4c  pop     rdi
0x180010f4d  pop     rsi
0x180010f4e  pop     rbp
0x180010f4f  pop     rbx
0x180010f50  retn
```
