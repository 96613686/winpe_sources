# SymCrypt3DesEncrypt

- ea: `0x1800032f4`
- end: `0x1800037c8`
- name: `SymCrypt3DesEncrypt`
- size: `1236`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002350`

## callees

- `0x1800032f4`

## pseudocode

```c
__int64 __fastcall SymCrypt3DesEncrypt(__int64 a1, _DWORD *a2, _DWORD *a3)
{
  int v3; // r9d
  int v5; // eax
  unsigned int v7; // r8d
  int v8; // edx
  int v9; // r8d
  int v10; // edx
  unsigned int v11; // eax
  int v12; // r8d
  int v13; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // edx
  int v17; // ecx
  int v18; // eax
  int v19; // edx
  int v20; // eax
  unsigned int v21; // r10d
  unsigned int v22; // r11d
  unsigned int v23; // r10d
  __int64 i; // rbx
  unsigned int v25; // r9d
  unsigned __int64 v26; // r8
  unsigned __int64 v27; // r9
  __int64 j; // rbx
  unsigned int v29; // r8d
  unsigned __int64 v30; // r9
  unsigned int v31; // eax
  __int64 k; // rbx
  unsigned int v33; // r9d
  unsigned __int64 v34; // r8
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
  v7 = (v3 ^ v5) & 0xF0F0F0F0;
  v8 = v3 ^ v7;
  v9 = v5 ^ v7;
  v10 = __ROL4__(v8, 20);
  v11 = (v9 ^ v10) & 0xFFF0000F;
  v12 = v11 ^ v9;
  v13 = __ROL4__(v10 ^ v11, 14);
  v14 = (v12 ^ v13) & 0x33333333;
  v15 = v12 ^ v14;
  v16 = v13 ^ v14;
  v17 = __ROL4__(v15, 22);
  v18 = (v16 ^ v17) & 0x3FC03FC;
  v19 = v18 ^ v16;
  v20 = __ROL4__(v17 ^ v18, 9);
  v21 = (v19 ^ v20) & 0xAAAAAAAA;
  v22 = __ROL4__(v19 ^ v21, 1);
  v23 = v20 ^ v21;
  for ( i = 0; i != 16; i += 2 )
  {
    v25 = __ROR4__(*(_DWORD *)(a1 + 8 * i + 4) ^ v23, 4);
    v26 = v23 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * i);
    v22 ^= *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v25 & 0xFC))
         ^ *(_DWORD *)((char *)SymCryptDesSpbox + ((unsigned __int8)v26 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v25 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v25 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v25 >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64] + ((v26 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128] + ((v26 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192] + ((v26 >> 24) & 0xFC));
    v27 = *(unsigned int *)(a1 + 8 * i + 8) ^ (unsigned __int64)v22;
    LODWORD(v26) = __ROR4__(*(_DWORD *)(a1 + 8 * i + 12) ^ v22, 4);
    v23 ^= *(_DWORD *)((char *)SymCryptDesSpbox + ((unsigned __int8)v27 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v26 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64] + ((v27 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128] + ((v27 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192] + ((v27 >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)(unsigned int)v26 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)(unsigned int)v26 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)(unsigned int)v26 >> 24) & 0xFC));
  }
  for ( j = 14; j != -2; j -= 2 )
  {
    v29 = __ROR4__(*(_DWORD *)(a1 + 8 * j + 140) ^ v22, 4);
    v23 ^= *(_DWORD *)((char *)SymCryptDesSpbox + ((v22 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * j + 136)) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v29 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64]
                     + (((v22 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * j + 136)) >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128]
                     + (((v22 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * j + 136)) >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192]
                     + (((v22 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * j + 136)) >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v29 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v29 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v29 >> 24) & 0xFC));
    v30 = v23 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * j + 128);
    v31 = __ROR4__(*(_DWORD *)(a1 + 8 * j + 132) ^ v23, 4);
    v22 ^= *(_DWORD *)((char *)SymCryptDesSpbox + ((unsigned __int8)v30 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v31 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64] + ((v30 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128] + ((v30 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192] + ((v30 >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v31 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v31 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v31 >> 24) & 0xFC));
  }
  for ( k = 0; k != 16; k += 2 )
  {
    v33 = __ROR4__(*(_DWORD *)(a1 + 8 * k + 260) ^ v23, 4);
    v34 = v23 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * k + 256);
    v22 ^= *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v33 & 0xFC))
         ^ *(_DWORD *)((char *)SymCryptDesSpbox + ((unsigned __int8)v34 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v33 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v33 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v33 >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64] + ((v34 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128] + ((v34 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192] + ((v34 >> 24) & 0xFC));
    v35 = v22 ^ (unsigned __int64)*(unsigned int *)(a1 + 8 * k + 264);
    v36 = __ROR4__(*(_DWORD *)(a1 + 8 * k + 268) ^ v22, 4);
    v23 ^= *(_DWORD *)((char *)SymCryptDesSpbox + ((unsigned __int8)v35 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[32] + ((unsigned __int8)v36 & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[64] + ((v35 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[128] + ((v35 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[192] + ((v35 >> 24) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[96] + (((unsigned __int64)v36 >> 8) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[160] + (((unsigned __int64)v36 >> 16) & 0xFC))
         ^ *(_DWORD *)((char *)&SymCryptDesSpbox[224] + (((unsigned __int64)v36 >> 24) & 0xFC));
  }
  v37 = __ROR4__(v23, 1);
  v38 = (v22 ^ v37) & 0xAAAAAAAA;
  v39 = v38 ^ v37;
  v40 = __ROR4__(v22 ^ v38, 9);
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
0x1800032f4  push    rbx
0x1800032f6  push    rbp
0x1800032f7  push    rsi
0x1800032f8  push    rdi
0x1800032f9  push    r14
0x1800032fb  mov     eax, [rdx]
0x1800032fd  lea     r14, SymCryptDesSpbox
0x180003304  mov     r9d, [rdx+4]
0x180003308  mov     rsi, rcx
0x18000330b  rol     eax, 4
0x18000330e  mov     rdi, r8
0x180003311  mov     edx, eax
0x180003313  mov     ebp, 0FCh
0x180003318  xor     edx, r9d
0x18000331b  and     edx, 0F0F0F0F0h
0x180003321  mov     r8d, edx
0x180003324  xor     edx, r9d
0x180003327  xor     r8d, eax
0x18000332a  rol     edx, 14h
0x18000332d  mov     eax, edx
0x18000332f  xor     eax, r8d
0x180003332  and     eax, 0FFF0000Fh
0x180003337  xor     r8d, eax
0x18000333a  xor     eax, edx
0x18000333c  rol     eax, 0Eh
0x18000333f  mov     ecx, eax
0x180003341  xor     ecx, r8d
0x180003344  and     ecx, 33333333h
0x18000334a  mov     edx, ecx
0x18000334c  xor     ecx, r8d
0x18000334f  xor     edx, eax
0x180003351  rol     ecx, 16h
0x180003354  mov     eax, ecx
0x180003356  xor     eax, edx
0x180003358  and     eax, 3FC03FCh
0x18000335d  xor     edx, eax
0x18000335f  xor     eax, ecx
0x180003361  rol     eax, 9
0x180003364  mov     r11d, eax
0x180003367  xor     r11d, edx
0x18000336a  and     r11d, 0AAAAAAAAh
0x180003371  mov     r10d, r11d
0x180003374  xor     r11d, edx
0x180003377  rol     r11d, 1
0x18000337a  xor     r10d, eax
0x18000337d  xor     ebx, ebx
0x18000337f  mov     r8d, [rsi+rbx*8]
0x180003383  mov     r9d, r10d
0x180003386  xor     r9d, [rsi+rbx*8+4]
0x18000338b  ror     r9d, 4
0x18000338f  mov     eax, r10d
0x180003392  xor     r8, rax
0x180003395  mov     rcx, r8
0x180003398  mov     rax, r8
0x18000339b  shr     rax, 10h
0x18000339f  and     rax, rbp
0x1800033a2  shr     rcx, 18h
0x1800033a6  and     rcx, rbp
0x1800033a9  mov     edx, [rcx+r14+600h]
0x1800033b1  xor     edx, [rax+r14+400h]
0x1800033b9  mov     rax, r8
0x1800033bc  shr     rax, 8
0x1800033c0  and     r8, rbp
0x1800033c3  and     rax, rbp
0x1800033c6  xor     edx, [rax+r14+200h]
0x1800033ce  mov     eax, r9d
0x1800033d1  shr     rax, 18h
0x1800033d5  and     rax, rbp
0x1800033d8  xor     edx, [rax+r14+700h]
0x1800033e0  mov     eax, r9d
0x1800033e3  shr     rax, 10h
0x1800033e7  and     rax, rbp
0x1800033ea  xor     edx, [rax+r14+500h]
0x1800033f2  mov     eax, r9d
0x1800033f5  shr     rax, 8
0x1800033f9  and     r9, rbp
0x1800033fc  and     rax, rbp
0x1800033ff  xor     edx, [rax+r14+300h]
0x180003407  xor     edx, [r8+r14]
0x18000340b  xor     edx, [r9+r14+100h]
0x180003413  mov     eax, [rsi+rbx*8+8]
0x180003417  xor     r11d, edx
0x18000341a  mov     r8d, r11d
0x18000341d  mov     r9d, r11d
0x180003420  xor     r8d, [rsi+rbx*8+0Ch]
0x180003425  xor     r9, rax
0x180003428  ror     r8d, 4
0x18000342c  add     rbx, 2
0x180003430  mov     ecx, r8d
0x180003433  mov     eax, r8d
0x180003436  shr     rax, 10h
0x18000343a  and     rax, rbp
0x18000343d  shr     rcx, 18h
0x180003441  and     rcx, rbp
0x180003444  mov     edx, [rcx+r14+700h]
0x18000344c  xor     edx, [rax+r14+500h]
0x180003454  mov     eax, r8d
0x180003457  shr     rax, 8
0x18000345b  and     r8, rbp
0x18000345e  and     rax, rbp
0x180003461  xor     edx, [rax+r14+300h]
0x180003469  mov     rax, r9
0x18000346c  shr     rax, 18h
0x180003470  and     rax, rbp
0x180003473  xor     edx, [rax+r14+600h]
0x18000347b  mov     rax, r9
0x18000347e  shr     rax, 10h
0x180003482  and     rax, rbp
0x180003485  xor     edx, [rax+r14+400h]
0x18000348d  mov     rax, r9
0x180003490  shr     rax, 8
0x180003494  and     r9, rbp
0x180003497  and     rax, rbp
0x18000349a  xor     edx, [rax+r14+200h]
0x1800034a2  xor     edx, [r8+r14+100h]
0x1800034aa  xor     edx, [r9+r14]
0x1800034ae  xor     r10d, edx
0x1800034b1  cmp     rbx, 10h
0x1800034b5  jnz     loc_18000337F
0x1800034bb  mov     ebx, 0Eh
0x1800034c0  mov     r9d, [rsi+rbx*8+88h]
0x1800034c8  mov     r8d, r11d
0x1800034cb  xor     r8d, [rsi+rbx*8+8Ch]
0x1800034d3  ror     r8d, 4
0x1800034d7  mov     ecx, r8d
0x1800034da  mov     eax, r11d
0x1800034dd  xor     r9, rax
0x1800034e0  shr     rcx, 18h
0x1800034e4  and     rcx, rbp
0x1800034e7  mov     eax, r8d
0x1800034ea  shr     rax, 10h
0x1800034ee  and     rax, rbp
0x1800034f1  mov     edx, [rcx+r14+700h]
0x1800034f9  xor     edx, [rax+r14+500h]
0x180003501  mov     eax, r8d
0x180003504  shr     rax, 8
0x180003508  and     r8, rbp
0x18000350b  and     rax, rbp
0x18000350e  xor     edx, [rax+r14+300h]
0x180003516  mov     rax, r9
0x180003519  shr     rax, 18h
0x18000351d  and     rax, rbp
0x180003520  xor     edx, [rax+r14+600h]
0x180003528  mov     rax, r9
0x18000352b  shr     rax, 10h
0x18000352f  and     rax, rbp
0x180003532  xor     edx, [rax+r14+400h]
0x18000353a  mov     rax, r9
0x18000353d  shr     rax, 8
0x180003541  and     r9, rbp
0x180003544  and     rax, rbp
0x180003547  xor     edx, [rax+r14+200h]
0x18000354f  xor     edx, [r8+r14+100h]
0x180003557  xor     edx, [r9+r14]
0x18000355b  mov     r9d, [rsi+rbx*8+80h]
0x180003563  xor     r10d, edx
0x180003566  mov     eax, r10d
0x180003569  mov     ecx, r10d
0x18000356c  xor     eax, [rsi+rbx*8+84h]
0x180003573  xor     r9, rcx
0x180003576  ror     eax, 4
0x180003579  sub     rbx, 2
0x18000357d  mov     ecx, eax
0x18000357f  mov     r8d, eax
0x180003582  shr     rax, 10h
0x180003586  and     rax, rbp
0x180003589  shr     rcx, 18h
0x18000358d  and     rcx, rbp
0x180003590  mov     edx, [rcx+r14+700h]
0x180003598  xor     edx, [rax+r14+500h]
0x1800035a0  mov     eax, r8d
0x1800035a3  shr     rax, 8
0x1800035a7  and     r8, rbp
0x1800035aa  and     rax, rbp
0x1800035ad  xor     edx, [rax+r14+300h]
0x1800035b5  mov     rax, r9
0x1800035b8  shr     rax, 18h
0x1800035bc  and     rax, rbp
0x1800035bf  xor     edx, [rax+r14+600h]
0x1800035c7  mov     rax, r9
0x1800035ca  shr     rax, 10h
0x1800035ce  and     rax, rbp
0x1800035d1  xor     edx, [rax+r14+400h]
0x1800035d9  mov     rax, r9
0x1800035dc  shr     rax, 8
0x1800035e0  and     r9, rbp
0x1800035e3  and     rax, rbp
0x1800035e6  xor     edx, [rax+r14+200h]
0x1800035ee  xor     edx, [r8+r14+100h]
0x1800035f6  xor     edx, [r9+r14]
0x1800035fa  xor     r11d, edx
0x1800035fd  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x180003601  jnz     loc_1800034C0
0x180003607  xor     ebx, ebx
0x180003609  mov     r8d, [rsi+rbx*8+100h]
0x180003611  mov     r9d, r10d
0x180003614  xor     r9d, [rsi+rbx*8+104h]
0x18000361c  ror     r9d, 4
0x180003620  mov     eax, r10d
0x180003623  xor     r8, rax
0x180003626  mov     rcx, r8
0x180003629  mov     rax, r8
0x18000362c  shr     rax, 10h
0x180003630  and     rax, rbp
0x180003633  shr     rcx, 18h
0x180003637  and     rcx, rbp
0x18000363a  mov     edx, [rcx+r14+600h]
0x180003642  xor     edx, [rax+r14+400h]
0x18000364a  mov     rax, r8
0x18000364d  shr     rax, 8
0x180003651  and     r8, rbp
0x180003654  and     rax, rbp
0x180003657  xor     edx, [rax+r14+200h]
0x18000365f  mov     eax, r9d
0x180003662  shr     rax, 18h
0x180003666  and     rax, rbp
0x180003669  xor     edx, [rax+r14+700h]
0x180003671  mov     eax, r9d
0x180003674  shr     rax, 10h
0x180003678  and     rax, rbp
0x18000367b  xor     edx, [rax+r14+500h]
0x180003683  mov     eax, r9d
0x180003686  shr     rax, 8
0x18000368a  and     r9, rbp
0x18000368d  and     rax, rbp
0x180003690  xor     edx, [rax+r14+300h]
0x180003698  xor     edx, [r8+r14]
0x18000369c  xor     edx, [r9+r14+100h]
0x1800036a4  mov     r9d, [rsi+rbx*8+108h]
0x1800036ac  xor     r11d, edx
0x1800036af  mov     eax, r11d
0x1800036b2  mov     ecx, r11d
0x1800036b5  xor     eax, [rsi+rbx*8+10Ch]
0x1800036bc  xor     r9, rcx
0x1800036bf  ror     eax, 4
0x1800036c2  add     rbx, 2
0x1800036c6  mov     ecx, eax
0x1800036c8  mov     r8d, eax
0x1800036cb  shr     rax, 10h
0x1800036cf  and     rax, rbp
0x1800036d2  shr     rcx, 18h
0x1800036d6  and     rcx, rbp
0x1800036d9  mov     edx, [rcx+r14+700h]
0x1800036e1  xor     edx, [rax+r14+500h]
0x1800036e9  mov     eax, r8d
0x1800036ec  shr     rax, 8
0x1800036f0  and     r8, rbp
0x1800036f3  and     rax, rbp
0x1800036f6  xor     edx, [rax+r14+300h]
0x1800036fe  mov     rax, r9
0x180003701  shr     rax, 18h
0x180003705  and     rax, rbp
0x180003708  xor     edx, [rax+r14+600h]
0x180003710  mov     rax, r9
0x180003713  shr     rax, 10h
0x180003717  and     rax, rbp
0x18000371a  xor     edx, [rax+r14+400h]
0x180003722  mov     rax, r9
0x180003725  shr     rax, 8
0x180003729  and     r9, rbp
0x18000372c  and     rax, rbp
0x18000372f  xor     edx, [rax+r14+200h]
0x180003737  xor     edx, [r8+r14+100h]
0x18000373f  xor     edx, [r9+r14]
0x180003743  xor     r10d, edx
0x180003746  cmp     rbx, 10h
0x18000374a  jnz     loc_180003609
0x180003750  ror     r10d, 1
0x180003753  mov     r8d, r10d
0x180003756  xor     r8d, r11d
0x180003759  and     r8d, 0AAAAAAAAh
0x180003760  xor     r10d, r8d
0x180003763  xor     r8d, r11d
0x180003766  ror     r8d, 9
0x18000376a  mov     eax, r8d
0x18000376d  xor     eax, r10d
0x180003770  and     eax, 3FC03FCh
0x180003775  xor     r8d, eax
0x180003778  xor     r10d, eax
0x18000377b  ror     r8d, 16h
0x18000377f  mov     edx, r8d
0x180003782  xor     edx, r10d
0x180003785  and     edx, 33333333h
0x18000378b  xor     r8d, edx
0x18000378e  xor     edx, r10d
0x180003791  ror     edx, 0Eh
0x180003794  mov     eax, edx
0x180003796  xor     eax, r8d
0x180003799  and     eax, 0FFF0000Fh
0x18000379e  xor     edx, eax
0x1800037a0  xor     r8d, eax
0x1800037a3  ror     edx, 14h
0x1800037a6  mov     ecx, edx
0x1800037a8  xor     ecx, r8d
0x1800037ab  and     ecx, 0F0F0F0F0h
0x1800037b1  mov     eax, ecx
0x1800037b3  xor     eax, r8d
0x1800037b6  ror     eax, 4
0x1800037b9  xor     edx, ecx
0x1800037bb  mov     [rdi], eax
  ... truncated ...
```
