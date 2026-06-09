# SymCryptDesExpandSingleKey

- ea: `0x180003840`
- end: `0x180003a7b`
- name: `SymCryptDesExpandSingleKey`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800037d0`

## callees

- `0x180003840`

## pseudocode

```c
__int64 __fastcall SymCryptDesExpandSingleKey(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // r8d
  int v4; // r9d
  unsigned int v5; // r8d
  unsigned int v6; // ecx
  int v7; // edx
  int v8; // eax
  unsigned int v9; // edx
  int v10; // ecx
  int v11; // r11d
  unsigned int v12; // ecx
  int v13; // r11d
  int v14; // eax
  unsigned int v15; // r11d
  int v16; // edx
  int v17; // ecx
  int v18; // eax
  unsigned int v19; // r11d
  unsigned int v20; // ebx
  __int64 i; // rdi
  int v22; // r11d
  unsigned int v23; // ecx
  unsigned int v24; // eax
  unsigned int v25; // r10d
  int v26; // edx
  __int64 result; // rax

  v2 = a2[1];
  v4 = (*a2 ^ (v2 >> 4)) & 0xF0F0F0F;
  v5 = v2
     ^ (16 * v4)
     ^ (v2
      ^ (16 * v4)
      ^ ((v2 ^ (16 * v4)) >> 18))
     & 0x3333
     ^ (((v2 ^ (16 * v4) ^ ((v2 ^ (16 * v4)) >> 18)) & 0x3333) << 18);
  v6 = *a2
     ^ v4
     ^ (*a2
      ^ v4
      ^ ((*a2 ^ (unsigned int)v4) >> 18))
     & 0x3333
     ^ (((*a2 ^ v4 ^ ((*a2 ^ (unsigned int)v4) >> 18)) & 0x3333) << 18);
  v7 = (v6 ^ (v5 >> 1)) & 0x55555555;
  v8 = v5 ^ (2 * v7);
  v9 = v6 ^ v7;
  v10 = (v8 ^ (v9 >> 8)) & 0xFF00FF;
  v11 = v10 << 8;
  v12 = v8 ^ v10;
  v13 = v9 ^ v11;
  v14 = (v13 ^ (v12 >> 1)) & 0x55555555;
  v15 = v14 ^ v13;
  v16 = v12 ^ (2 * v14);
  v17 = (unsigned __int8)(v12 ^ (2 * v14) ^ BYTE2(v16));
  v18 = (v15 >> 4) & 0xF000000;
  v19 = v15 & 0xFFFFFFF;
  v20 = v18 | (v16 ^ v17 ^ (v17 << 16)) & 0xFFFFFF;
  for ( i = 0; i != 16; ++i )
  {
    if ( *((_BYTE *)qword_1800044F0 + i) )
    {
      v22 = (v19 >> 2) | (v19 << 26);
      v23 = v20 << 26;
      v24 = v20 >> 2;
    }
    else
    {
      v22 = (v19 >> 1) | (v19 << 27);
      v23 = v20 << 27;
      v24 = v20 >> 1;
    }
    v19 = v22 & 0xFFFFFFF;
    v20 = (v24 | v23) & 0xFFFFFFF;
    v25 = SymCryptDesKeySelect[v19 & 0x3F]
        | dword_180004F00[((unsigned __int8)v19 & 0xC0 | (unsigned __int64)((v19 >> 1) & 0xF00)) >> 6]
        | dword_180005000[(v19 & 0x1E000 | (unsigned __int64)((v19 >> 1) & 0x60000)) >> 13]
        | dword_180005100[(v19 & 0x100000 | ((v19 & 0xC00000 | (unsigned __int64)((v19 >> 1) & 0x7000000)) >> 1)) >> 20];
    v26 = dword_180005200[((unsigned __int8)v24 | (unsigned __int8)v23) & 0x3F]
        | dword_180005400[(v20 >> 15) & 0x3F]
        | dword_180005500[((v24 | v23) & 0x1E00000 | (unsigned __int64)((v20 >> 1) & 0x6000000)) >> 21]
        | dword_180005300[(((unsigned __int16)v24 | (unsigned __int16)v23) & 0x180
                         | ((unsigned __int64)v20 >> 1) & 0x1E00) >> 7];
    result = (unsigned __int16)v25;
    *(_DWORD *)(a1 + 8 * i) = __ROL4__((unsigned __int16)v25 | (v26 << 16), 2);
    *(_DWORD *)(a1 + 8 * i + 4) = __ROL4__(HIWORD(v25) | v26 & 0xFFFF0000, 6);
  }
  return result;
}

```

## disassembly

```asm
0x180003840  push    rbx
0x180003842  push    rbp
0x180003843  push    rsi
0x180003844  push    rdi
0x180003845  mov     eax, [rdx]
0x180003847  lea     rbp, __ImageBase
0x18000384e  mov     r8d, [rdx+4]
0x180003852  mov     rsi, rcx
0x180003855  mov     edx, r8d
0x180003858  mov     ecx, 3333h
0x18000385d  shr     edx, 4
0x180003860  xor     edx, eax
0x180003862  and     edx, 0F0F0F0Fh
0x180003868  mov     r9d, edx
0x18000386b  shl     edx, 4
0x18000386e  xor     r9d, eax
0x180003871  xor     edx, r8d
0x180003874  mov     eax, edx
0x180003876  shr     eax, 12h
0x180003879  xor     eax, edx
0x18000387b  and     eax, ecx
0x18000387d  mov     r8d, eax
0x180003880  shl     r8d, 12h
0x180003884  xor     r8d, eax
0x180003887  mov     eax, r9d
0x18000388a  shr     eax, 12h
0x18000388d  xor     r8d, edx
0x180003890  xor     eax, r9d
0x180003893  and     eax, ecx
0x180003895  mov     ecx, eax
0x180003897  shl     ecx, 12h
0x18000389a  xor     ecx, eax
0x18000389c  mov     eax, r8d
0x18000389f  shr     eax, 1
0x1800038a1  xor     ecx, r9d
0x1800038a4  xor     eax, ecx
0x1800038a6  mov     r9d, 55555555h
0x1800038ac  and     eax, r9d
0x1800038af  mov     edx, eax
0x1800038b1  add     eax, eax
0x1800038b3  xor     eax, r8d
0x1800038b6  xor     edx, ecx
0x1800038b8  mov     r11d, edx
0x1800038bb  shr     r11d, 8
0x1800038bf  xor     r11d, eax
0x1800038c2  and     r11d, 0FF00FFh
0x1800038c9  mov     ecx, r11d
0x1800038cc  shl     r11d, 8
0x1800038d0  xor     ecx, eax
0x1800038d2  xor     r11d, edx
0x1800038d5  mov     eax, ecx
0x1800038d7  shr     eax, 1
0x1800038d9  xor     eax, r11d
0x1800038dc  and     eax, r9d
0x1800038df  xor     r11d, eax
0x1800038e2  lea     edx, [rax+rax]
0x1800038e5  xor     edx, ecx
0x1800038e7  mov     eax, edx
0x1800038e9  shr     eax, 10h
0x1800038ec  xor     eax, edx
0x1800038ee  movzx   ecx, al
0x1800038f1  mov     eax, r11d
0x1800038f4  shr     eax, 4
0x1800038f7  mov     ebx, ecx
0x1800038f9  shl     ebx, 10h
0x1800038fc  and     eax, 0F000000h
0x180003901  xor     ebx, ecx
0x180003903  and     r11d, 0FFFFFFFh
0x18000390a  xor     ebx, edx
0x18000390c  and     ebx, 0FFFFFFh
0x180003912  or      ebx, eax
0x180003914  xor     edi, edi
0x180003916  cmp     byte ptr [rdi+rbp+44F0h], 0
0x18000391e  mov     ecx, r11d
0x180003921  mov     eax, r11d
0x180003924  jz      short loc_18000393E
0x180003926  shl     ecx, 1Ah
0x180003929  mov     r11d, ecx
0x18000392c  shr     eax, 2
0x18000392f  or      r11d, eax
0x180003932  mov     ecx, ebx
0x180003934  shl     ecx, 1Ah
0x180003937  mov     eax, ebx
0x180003939  shr     eax, 2
0x18000393c  jmp     short loc_180003952
0x18000393e  shl     ecx, 1Bh
0x180003941  mov     r11d, ecx
0x180003944  shr     eax, 1
0x180003946  or      r11d, eax
0x180003949  mov     ecx, ebx
0x18000394b  shl     ecx, 1Bh
0x18000394e  mov     eax, ebx
0x180003950  shr     eax, 1
0x180003952  mov     ebx, ecx
0x180003954  and     r11d, 0FFFFFFFh
0x18000395b  or      ebx, eax
0x18000395d  mov     r8d, r11d
0x180003960  shr     r8, 1
0x180003963  and     ebx, 0FFFFFFFh
0x180003969  mov     rdx, r8
0x18000396c  mov     eax, r11d
0x18000396f  and     edx, 7000000h
0x180003975  mov     r9d, r11d
0x180003978  and     eax, 0C00000h
0x18000397d  mov     rcx, r8
0x180003980  or      rdx, rax
0x180003983  and     ecx, 60000h
0x180003989  shr     rdx, 1
0x18000398c  and     r8d, 0F00h
0x180003993  mov     eax, r11d
0x180003996  and     r9d, 3Fh
0x18000399a  and     eax, 100000h
0x18000399f  or      rdx, rax
0x1800039a2  mov     eax, r11d
0x1800039a5  shr     rdx, 14h
0x1800039a9  and     eax, 1E000h
0x1800039ae  or      rcx, rax
0x1800039b1  mov     eax, r11d
0x1800039b4  and     eax, 0C0h
0x1800039b9  shr     rcx, 0Dh
0x1800039bd  or      r8, rax
0x1800039c0  mov     eax, ebx
0x1800039c2  mov     r10d, ss:rva dword_180005100[rbp+rdx*4]
0x1800039ca  and     eax, 180h
0x1800039cf  shr     r8, 6
0x1800039d3  or      r10d, ss:rva dword_180005000[rbp+rcx*4]
0x1800039db  mov     edx, ebx
0x1800039dd  shr     rdx, 1
0x1800039e0  or      r10d, ss:rva dword_180004F00[rbp+r8*4]
0x1800039e8  mov     rcx, rdx
0x1800039eb  or      r10d, ss:rva SymCryptDesKeySelect[rbp+r9*4]
0x1800039f3  and     edx, 6000000h
0x1800039f9  and     ecx, 1E00h
0x1800039ff  mov     r8d, ebx
0x180003a02  or      rcx, rax
0x180003a05  and     r8d, 3Fh
0x180003a09  shr     rcx, 7
0x180003a0d  mov     eax, ebx
0x180003a0f  and     eax, 1E00000h
0x180003a14  or      rdx, rax
0x180003a17  shr     rdx, 15h
0x180003a1b  mov     eax, ss:rva dword_180005500[rbp+rdx*4]
0x180003a22  mov     edx, ss:rva dword_180005300[rbp+rcx*4]
0x180003a29  or      edx, eax
0x180003a2b  mov     eax, ebx
0x180003a2d  shr     rax, 0Fh
0x180003a31  and     eax, 3Fh
0x180003a34  or      edx, ss:rva dword_180005400[rbp+rax*4]
0x180003a3b  or      edx, ss:rva dword_180005200[rbp+r8*4]
0x180003a43  mov     ecx, edx
0x180003a45  movzx   eax, r10w
0x180003a49  shl     ecx, 10h
0x180003a4c  and     edx, 0FFFF0000h
0x180003a52  shr     r10d, 10h
0x180003a56  or      ecx, eax
0x180003a58  or      edx, r10d
0x180003a5b  rol     ecx, 2
0x180003a5e  rol     edx, 6
0x180003a61  mov     [rsi+rdi*8], ecx
0x180003a64  mov     [rsi+rdi*8+4], edx
0x180003a68  inc     rdi
0x180003a6b  cmp     rdi, 10h
0x180003a6f  jnz     loc_180003916
0x180003a75  pop     rdi
0x180003a76  pop     rsi
0x180003a77  pop     rbp
0x180003a78  pop     rbx
0x180003a79  retn
```
