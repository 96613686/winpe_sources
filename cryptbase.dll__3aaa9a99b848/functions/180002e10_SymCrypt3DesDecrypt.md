# SymCrypt3DesDecrypt

- ea: `0x180002e10`
- end: `0x1800032ed`
- name: `SymCrypt3DesDecrypt`
- size: `1245`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a50`

## callees

- `0x180002e10`

## pseudocode

```c
__int64 __fastcall SymCrypt3DesDecrypt(__int64 a1, _DWORD *a2, _DWORD *a3)
{
  int v3; // r9d
  int v5; // eax
  __int64 v7; // rsi
  __int64 v8; // rbx
  unsigned int v9; // r8d
  int v10; // edx
  int v11; // r8d
  int v12; // edx
  unsigned int v13; // eax
  int v14; // r8d
  int v15; // eax
  int v16; // edx
  int v17; // ecx
  int v18; // edx
  int v19; // ecx
  int v20; // eax
  int v21; // edx
  int v22; // eax
  unsigned int v23; // r10d
  int v24; // r11d
  unsigned int v25; // r10d
  unsigned int v26; // r11d
  unsigned int v27; // r8d
  unsigned __int64 v28; // r8
  unsigned int v29; // r9d
  __int64 i; // rbx
  unsigned int v31; // r8d
  unsigned __int64 v32; // r8
  unsigned int v33; // r9d
  unsigned int v34; // r8d
  unsigned __int64 v35; // r9
  unsigned int v36; // eax
  int v37; // r10d
  unsigned int v38; // r8d
  int v39; // r10d
  int v40; // r8d
  int v41; // eax
  int v42; // r10d
  int v43; // r8d
  int v44; // edx
  int v45; // r8d
  int v46; // edx
  unsigned int v47; // eax
  int v48; // r8d
  int v49; // edx
  __int64 result; // rax

  v3 = a2[1];
  v5 = __ROL4__(*a2, 4);
  v7 = 14;
  v8 = 14;
  v9 = (v3 ^ v5) & 0xF0F0F0F0;
  v10 = v3 ^ v9;
  v11 = v5 ^ v9;
  v12 = __ROL4__(v10, 20);
  v13 = (v11 ^ v12) & 0xFFF0000F;
  v14 = v13 ^ v11;
  v15 = __ROL4__(v12 ^ v13, 14);
  v16 = (v14 ^ v15) & 0x33333333;
  v17 = v14 ^ v16;
  v18 = v15 ^ v16;
  v19 = __ROL4__(v17, 22);
  v20 = (v18 ^ v19) & 0x3FC03FC;
  v21 = v20 ^ v18;
  v22 = __ROL4__(v19 ^ v20, 9);
  v23 = (v21 ^ v22) & 0xAAAAAAAA;
  v24 = v21 ^ v23;
  v25 = v22 ^ v23;
  v26 = __ROL4__(v24, 1);
  do
  {
    v27 = __ROR4__(*(_DWORD *)(a1 + 8 * v8 + 268) ^ v25, 4);
    v26 ^= *(_DWORD *)((char *)SymCryptDesSpbox + ((v25 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * v8 + 264)) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v27 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64]
                     + (((v25 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * v8 + 264)) >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128]
                     + (((v25 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * v8 + 264)) >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192]
                     + (((v25 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * v8 + 264)) >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v27 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v27 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v27 >> 24) & 0xFC));
    v28 = v26 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * v8 + 256);
    v29 = __ROR4__(*(_DWORD *)(a1 + 8 * v8 + 260) ^ v26, 4);
    v8 -= 2;
    v25 ^= *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v29 & 0xFC))
         ^ *(_DWORD *)((char *)SymCryptDesSpbox + ((unsigned __int8)v28 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v29 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v29 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v29 >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64] + ((v28 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128] + ((v28 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192] + ((v28 >> 24) & 0xFC));
  }
  while ( v8 != -2 );
  for ( i = 0; i != 16; i += 2 )
  {
    v31 = __ROR4__(*(_DWORD *)(a1 + 8 * i + 132) ^ v26, 4);
    v25 ^= *(_DWORD *)((char *)SymCryptDesSpbox + ((v26 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * i + 128)) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v31 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64]
                     + (((v26 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * i + 128)) >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128]
                     + (((v26 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * i + 128)) >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192]
                     + (((v26 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * i + 128)) >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v31 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v31 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v31 >> 24) & 0xFC));
    v32 = v25 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * i + 136);
    v33 = __ROR4__(*(_DWORD *)(a1 + 8 * i + 140) ^ v25, 4);
    v26 ^= *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v33 & 0xFC))
         ^ *(_DWORD *)((char *)SymCryptDesSpbox + ((unsigned __int8)v32 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v33 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v33 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v33 >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64] + ((v32 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128] + ((v32 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192] + ((v32 >> 24) & 0xFC));
  }
  do
  {
    v34 = __ROR4__(*(_DWORD *)(a1 + 8 * v7 + 12) ^ v25, 4);
    v26 ^= *(_DWORD *)((char *)SymCryptDesSpbox + ((*(unsigned int *)(a1 + 8 * v7 + 8) ^ (unsigned __int64)v25) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v34 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64]
                     + (((*(unsigned int *)(a1 + 8 * v7 + 8) ^ (unsigned __int64)v25) >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128]
                     + (((*(unsigned int *)(a1 + 8 * v7 + 8) ^ (unsigned __int64)v25) >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192]
                     + (((*(unsigned int *)(a1 + 8 * v7 + 8) ^ (unsigned __int64)v25) >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v34 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v34 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v34 >> 24) & 0xFC));
    v35 = v26 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * v7);
    v36 = __ROR4__(*(_DWORD *)(a1 + 8 * v7 + 4) ^ v26, 4);
    v7 -= 2;
    v25 ^= *(_DWORD *)((char *)SymCryptDesSpbox + ((unsigned __int8)v35 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v36 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64] + ((v35 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128] + ((v35 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192] + ((v35 >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v36 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v36 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v36 >> 24) & 0xFC));
  }
  while ( v7 != -2 );
  v37 = __ROR4__(v25, 1);
  v38 = (v26 ^ v37) & 0xAAAAAAAA;
  v39 = v38 ^ v37;
  v40 = __ROR4__(v26 ^ v38, 9);
  v41 = (v39 ^ v40) & 0x3FC03FC;
  v42 = v41 ^ v39;
  v43 = __ROR4__(v41 ^ v40, 22);
  v44 = (v42 ^ v43) & 0x33333333;
  v45 = v44 ^ v43;
  v46 = __ROR4__(v42 ^ v44, 14);
  v47 = (v45 ^ v46) & 0xFFF0000F;
  v48 = v47 ^ v45;
  v49 = __ROR4__(v47 ^ v46, 20);
  result = (unsigned int)__ROR4__(v48 ^ (v48 ^ v49) & 0xF0F0F0F0, 4);
  *a3 = result;
  a3[1] = (v48 ^ v49) & 0xF0F0F0F0 ^ v49;
  return result;
}

```

## disassembly

```asm
0x180002e10  push    rbx
0x180002e12  push    rbp
0x180002e13  push    rsi
0x180002e14  push    rdi
0x180002e15  push    r14
0x180002e17  push    r15
0x180002e19  mov     eax, [rdx]
0x180002e1b  lea     r15, SymCryptDesSpbox
0x180002e22  mov     r9d, [rdx+4]
0x180002e26  mov     rbp, rcx
0x180002e29  rol     eax, 4
0x180002e2c  mov     rdi, r8
0x180002e2f  mov     edx, eax
0x180002e31  mov     esi, 0Eh
0x180002e36  xor     edx, r9d
0x180002e39  mov     ebx, esi
0x180002e3b  and     edx, 0F0F0F0F0h
0x180002e41  mov     r14d, 0FCh
0x180002e47  mov     r8d, edx
0x180002e4a  xor     edx, r9d
0x180002e4d  xor     r8d, eax
0x180002e50  rol     edx, 14h
0x180002e53  mov     eax, edx
0x180002e55  xor     eax, r8d
0x180002e58  and     eax, 0FFF0000Fh
0x180002e5d  xor     r8d, eax
0x180002e60  xor     eax, edx
0x180002e62  rol     eax, 0Eh
0x180002e65  mov     ecx, eax
0x180002e67  xor     ecx, r8d
0x180002e6a  and     ecx, 33333333h
0x180002e70  mov     edx, ecx
0x180002e72  xor     ecx, r8d
0x180002e75  xor     edx, eax
0x180002e77  rol     ecx, 16h
0x180002e7a  mov     eax, ecx
0x180002e7c  xor     eax, edx
0x180002e7e  and     eax, 3FC03FCh
0x180002e83  xor     edx, eax
0x180002e85  xor     eax, ecx
0x180002e87  rol     eax, 9
0x180002e8a  mov     r11d, eax
0x180002e8d  xor     r11d, edx
0x180002e90  and     r11d, 0AAAAAAAAh
0x180002e97  mov     r10d, r11d
0x180002e9a  xor     r11d, edx
0x180002e9d  xor     r10d, eax
0x180002ea0  rol     r11d, 1
0x180002ea3  mov     r9d, [rbp+rbx*8+108h]
0x180002eab  mov     r8d, r10d
0x180002eae  xor     r8d, [rbp+rbx*8+10Ch]
0x180002eb6  ror     r8d, 4
0x180002eba  mov     ecx, r8d
0x180002ebd  mov     eax, r10d
0x180002ec0  xor     r9, rax
0x180002ec3  shr     rcx, 18h
0x180002ec7  and     rcx, r14
0x180002eca  mov     eax, r8d
0x180002ecd  shr     rax, 10h
0x180002ed1  and     rax, r14
0x180002ed4  mov     edx, [rcx+r15+700h]
0x180002edc  xor     edx, [rax+r15+500h]
0x180002ee4  mov     eax, r8d
0x180002ee7  shr     rax, 8
0x180002eeb  and     r8, r14
0x180002eee  and     rax, r14
0x180002ef1  xor     edx, [rax+r15+300h]
0x180002ef9  mov     rax, r9
0x180002efc  shr     rax, 18h
0x180002f00  and     rax, r14
0x180002f03  xor     edx, [rax+r15+600h]
0x180002f0b  mov     rax, r9
0x180002f0e  shr     rax, 10h
0x180002f12  and     rax, r14
0x180002f15  xor     edx, [rax+r15+400h]
0x180002f1d  mov     rax, r9
0x180002f20  shr     rax, 8
0x180002f24  and     r9, r14
0x180002f27  and     rax, r14
0x180002f2a  xor     edx, [rax+r15+200h]
0x180002f32  xor     edx, [r8+r15+100h]
0x180002f3a  xor     edx, [r9+r15]
0x180002f3e  mov     r8d, [rbp+rbx*8+100h]
0x180002f46  xor     r11d, edx
0x180002f49  mov     r9d, r11d
0x180002f4c  mov     ecx, r11d
0x180002f4f  xor     r9d, [rbp+rbx*8+104h]
0x180002f57  xor     r8, rcx
0x180002f5a  ror     r9d, 4
0x180002f5e  mov     rcx, r8
0x180002f61  shr     rcx, 18h
0x180002f65  mov     rax, r8
0x180002f68  shr     rax, 10h
0x180002f6c  and     rcx, r14
0x180002f6f  and     rax, r14
0x180002f72  sub     rbx, 2
0x180002f76  mov     edx, [rcx+r15+600h]
0x180002f7e  xor     edx, [rax+r15+400h]
0x180002f86  mov     rax, r8
0x180002f89  shr     rax, 8
0x180002f8d  and     r8, r14
0x180002f90  and     rax, r14
0x180002f93  xor     edx, [rax+r15+200h]
0x180002f9b  mov     eax, r9d
0x180002f9e  shr     rax, 18h
0x180002fa2  and     rax, r14
0x180002fa5  xor     edx, [rax+r15+700h]
0x180002fad  mov     eax, r9d
0x180002fb0  shr     rax, 10h
0x180002fb4  and     rax, r14
0x180002fb7  xor     edx, [rax+r15+500h]
0x180002fbf  mov     eax, r9d
0x180002fc2  shr     rax, 8
0x180002fc6  and     r9, r14
0x180002fc9  and     rax, r14
0x180002fcc  xor     edx, [rax+r15+300h]
0x180002fd4  xor     edx, [r8+r15]
0x180002fd8  xor     edx, [r9+r15+100h]
0x180002fe0  xor     r10d, edx
0x180002fe3  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x180002fe7  jnz     loc_180002EA3
0x180002fed  xor     ebx, ebx
0x180002fef  mov     r9d, [rbp+rbx*8+80h]
0x180002ff7  mov     r8d, r11d
0x180002ffa  xor     r8d, [rbp+rbx*8+84h]
0x180003002  ror     r8d, 4
0x180003006  mov     ecx, r8d
0x180003009  mov     eax, r11d
0x18000300c  xor     r9, rax
0x18000300f  shr     rcx, 18h
0x180003013  and     rcx, r14
0x180003016  mov     eax, r8d
0x180003019  shr     rax, 10h
0x18000301d  and     rax, r14
0x180003020  mov     edx, [rcx+r15+700h]
0x180003028  xor     edx, [rax+r15+500h]
0x180003030  mov     eax, r8d
0x180003033  shr     rax, 8
0x180003037  and     r8, r14
0x18000303a  and     rax, r14
0x18000303d  xor     edx, [rax+r15+300h]
0x180003045  mov     rax, r9
0x180003048  shr     rax, 18h
0x18000304c  and     rax, r14
0x18000304f  xor     edx, [rax+r15+600h]
0x180003057  mov     rax, r9
0x18000305a  shr     rax, 10h
0x18000305e  and     rax, r14
0x180003061  xor     edx, [rax+r15+400h]
0x180003069  mov     rax, r9
0x18000306c  shr     rax, 8
0x180003070  and     r9, r14
0x180003073  and     rax, r14
0x180003076  xor     edx, [rax+r15+200h]
0x18000307e  xor     edx, [r8+r15+100h]
0x180003086  xor     edx, [r9+r15]
0x18000308a  mov     r8d, [rbp+rbx*8+88h]
0x180003092  xor     r10d, edx
0x180003095  mov     r9d, r10d
0x180003098  mov     ecx, r10d
0x18000309b  xor     r9d, [rbp+rbx*8+8Ch]
0x1800030a3  xor     r8, rcx
0x1800030a6  ror     r9d, 4
0x1800030aa  mov     rcx, r8
0x1800030ad  shr     rcx, 18h
0x1800030b1  mov     rax, r8
0x1800030b4  shr     rax, 10h
0x1800030b8  and     rcx, r14
0x1800030bb  and     rax, r14
0x1800030be  add     rbx, 2
0x1800030c2  mov     edx, [rcx+r15+600h]
0x1800030ca  xor     edx, [rax+r15+400h]
0x1800030d2  mov     rax, r8
0x1800030d5  shr     rax, 8
0x1800030d9  and     r8, r14
0x1800030dc  and     rax, r14
0x1800030df  xor     edx, [rax+r15+200h]
0x1800030e7  mov     eax, r9d
0x1800030ea  shr     rax, 18h
0x1800030ee  and     rax, r14
0x1800030f1  xor     edx, [rax+r15+700h]
0x1800030f9  mov     eax, r9d
0x1800030fc  shr     rax, 10h
0x180003100  and     rax, r14
0x180003103  xor     edx, [rax+r15+500h]
0x18000310b  mov     eax, r9d
0x18000310e  shr     rax, 8
0x180003112  and     r9, r14
0x180003115  and     rax, r14
0x180003118  xor     edx, [rax+r15+300h]
0x180003120  xor     edx, [r8+r15]
0x180003124  xor     edx, [r9+r15+100h]
0x18000312c  xor     r11d, edx
0x18000312f  cmp     rbx, 10h
0x180003133  jnz     loc_180002FEF
0x180003139  mov     eax, [rbp+rsi*8+8]
0x18000313d  mov     r8d, r10d
0x180003140  xor     r8d, [rbp+rsi*8+0Ch]
0x180003145  ror     r8d, 4
0x180003149  mov     ecx, r8d
0x18000314c  mov     r9d, r10d
0x18000314f  xor     r9, rax
0x180003152  shr     rcx, 18h
0x180003156  and     rcx, r14
0x180003159  mov     eax, r8d
0x18000315c  shr     rax, 10h
0x180003160  and     rax, r14
0x180003163  mov     edx, [rcx+r15+700h]
0x18000316b  xor     edx, [rax+r15+500h]
0x180003173  mov     eax, r8d
0x180003176  shr     rax, 8
0x18000317a  and     r8, r14
0x18000317d  and     rax, r14
0x180003180  xor     edx, [rax+r15+300h]
0x180003188  mov     rax, r9
0x18000318b  shr     rax, 18h
0x18000318f  and     rax, r14
0x180003192  xor     edx, [rax+r15+600h]
0x18000319a  mov     rax, r9
0x18000319d  shr     rax, 10h
0x1800031a1  and     rax, r14
0x1800031a4  xor     edx, [rax+r15+400h]
0x1800031ac  mov     rax, r9
0x1800031af  shr     rax, 8
0x1800031b3  and     r9, r14
0x1800031b6  and     rax, r14
0x1800031b9  xor     edx, [rax+r15+200h]
0x1800031c1  xor     edx, [r8+r15+100h]
0x1800031c9  xor     edx, [r9+r15]
0x1800031cd  mov     r9d, [rbp+rsi*8+0]
0x1800031d2  xor     r11d, edx
0x1800031d5  mov     eax, r11d
0x1800031d8  mov     ecx, r11d
0x1800031db  xor     eax, [rbp+rsi*8+4]
0x1800031df  xor     r9, rcx
0x1800031e2  ror     eax, 4
0x1800031e5  sub     rsi, 2
0x1800031e9  mov     ecx, eax
0x1800031eb  mov     r8d, eax
0x1800031ee  shr     rax, 10h
0x1800031f2  and     rax, r14
0x1800031f5  shr     rcx, 18h
0x1800031f9  and     rcx, r14
0x1800031fc  mov     edx, [rcx+r15+700h]
0x180003204  xor     edx, [rax+r15+500h]
0x18000320c  mov     eax, r8d
0x18000320f  shr     rax, 8
0x180003213  and     r8, r14
0x180003216  and     rax, r14
0x180003219  xor     edx, [rax+r15+300h]
0x180003221  mov     rax, r9
0x180003224  shr     rax, 18h
0x180003228  and     rax, r14
0x18000322b  xor     edx, [rax+r15+600h]
0x180003233  mov     rax, r9
0x180003236  shr     rax, 10h
0x18000323a  and     rax, r14
0x18000323d  xor     edx, [rax+r15+400h]
0x180003245  mov     rax, r9
0x180003248  shr     rax, 8
0x18000324c  and     r9, r14
0x18000324f  and     rax, r14
0x180003252  xor     edx, [rax+r15+200h]
0x18000325a  xor     edx, [r8+r15+100h]
0x180003262  xor     edx, [r9+r15]
0x180003266  xor     r10d, edx
0x180003269  cmp     rsi, 0FFFFFFFFFFFFFFFEh
0x18000326d  jnz     loc_180003139
0x180003273  ror     r10d, 1
0x180003276  mov     r8d, r10d
0x180003279  xor     r8d, r11d
0x18000327c  and     r8d, 0AAAAAAAAh
0x180003283  xor     r10d, r8d
0x180003286  xor     r8d, r11d
0x180003289  ror     r8d, 9
0x18000328d  mov     eax, r8d
0x180003290  xor     eax, r10d
0x180003293  and     eax, 3FC03FCh
0x180003298  xor     r8d, eax
0x18000329b  xor     r10d, eax
0x18000329e  ror     r8d, 16h
0x1800032a2  mov     edx, r8d
0x1800032a5  xor     edx, r10d
0x1800032a8  and     edx, 33333333h
0x1800032ae  xor     r8d, edx
0x1800032b1  xor     edx, r10d
0x1800032b4  ror     edx, 0Eh
0x1800032b7  mov     eax, edx
0x1800032b9  xor     eax, r8d
0x1800032bc  and     eax, 0FFF0000Fh
0x1800032c1  xor     edx, eax
0x1800032c3  xor     r8d, eax
0x1800032c6  ror     edx, 14h
0x1800032c9  mov     ecx, edx
0x1800032cb  xor     ecx, r8d
0x1800032ce  and     ecx, 0F0F0F0F0h
0x1800032d4  mov     eax, ecx
0x1800032d6  xor     eax, r8d
0x1800032d9  ror     eax, 4
0x1800032dc  xor     edx, ecx
  ... truncated ...
```
