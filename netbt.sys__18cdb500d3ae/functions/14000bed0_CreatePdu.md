# CreatePdu

- ea: `0x14000bed0`
- end: `0x14000c284`
- name: `CreatePdu`
- size: `948`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d594`
- `0x14001d580`

## callees

- `0x14000be64`
- `0x14000bed0`
- `0x140031140`
- `0x140031440`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000bf33`
- `ntoskrnl!ExAllocatePool2` at `0x14000bf33`

## pseudocode

```c
char *__fastcall CreatePdu(
        _BYTE *a1,
        _BYTE *a2,
        __int64 a3,
        __int16 a4,
        int a5,
        _QWORD *a6,
        unsigned int *a7,
        __int64 a8)
{
  __int64 v11; // rax
  bool v12; // zf
  size_t v13; // r14
  int v14; // ebp
  unsigned int v15; // ebp
  char *result; // rax
  char *v17; // rdi
  __int16 v18; // ax

  v11 = -1;
  do
    v12 = a2[++v11] == 0;
  while ( !v12 );
  v13 = (unsigned int)(v11 + 1);
  v14 = 49;
  if ( a5 )
    v14 = 67;
  v15 = v13 + v14;
  result = (char *)ExAllocatePool2(64, (unsigned __int16)v15, 1484022350);
  v17 = result;
  if ( result )
  {
    memset(result, 0, v15);
    v18 = *(_WORD *)(a8 + 128);
    if ( !v18 )
      v18 = __ROR2__(GetTransactId(), 8);
    *(_WORD *)v17 = v18;
    v17[5] = 1;
    v17[7] = 0;
    v17[9] = 0;
    v17[12] = 32;
    v17[13] = (*a1 >> 4) + 65;
    v17[14] = (*a1 & 0xF) + 65;
    v17[15] = (a1[1] >> 4) + 65;
    v17[16] = (a1[1] & 0xF) + 65;
    v17[17] = (a1[2] >> 4) + 65;
    v17[18] = (a1[2] & 0xF) + 65;
    v17[19] = (a1[3] >> 4) + 65;
    v17[20] = (a1[3] & 0xF) + 65;
    v17[21] = (a1[4] >> 4) + 65;
    v17[22] = (a1[4] & 0xF) + 65;
    v17[23] = (a1[5] >> 4) + 65;
    v17[24] = (a1[5] & 0xF) + 65;
    v17[25] = (a1[6] >> 4) + 65;
    v17[26] = (a1[6] & 0xF) + 65;
    v17[27] = (a1[7] >> 4) + 65;
    v17[28] = (a1[7] & 0xF) + 65;
    v17[29] = (a1[8] >> 4) + 65;
    v17[30] = (a1[8] & 0xF) + 65;
    v17[31] = (a1[9] >> 4) + 65;
    v17[32] = (a1[9] & 0xF) + 65;
    v17[33] = (a1[10] >> 4) + 65;
    v17[34] = (a1[10] & 0xF) + 65;
    v17[35] = (a1[11] >> 4) + 65;
    v17[36] = (a1[11] & 0xF) + 65;
    v17[37] = (a1[12] >> 4) + 65;
    v17[38] = (a1[12] & 0xF) + 65;
    v17[39] = (a1[13] >> 4) + 65;
    v17[40] = (a1[13] & 0xF) + 65;
    v17[41] = (a1[14] >> 4) + 65;
    v17[42] = (a1[14] & 0xF) + 65;
    v17[43] = (a1[15] >> 4) + 65;
    v17[44] = (a1[15] & 0xF) + 65;
    if ( (unsigned int)v13 > 1 )
    {
      memmove(v17 + 45, a2, v13);
    }
    else
    {
      v17[45] = 0;
      v13 = 1;
    }
    *(_DWORD *)&v17[v13 + 45] = 16785408;
    *a6 = v17;
    *a7 = v15;
    if ( !a5 )
    {
      result = v17;
      *((_WORD *)v17 + 1) = ((NodeType & 1) << 12) + 1;
      v17[11] = 0;
      return result;
    }
    if ( a5 != 4 && a5 != 5 )
    {
      if ( a5 == 7 )
      {
LABEL_17:
        if ( a5 == 7 )
        {
          *((_WORD *)v17 + 1) = 48;
          *(_DWORD *)&v17[v13 + 55] = 0;
        }
        v12 = pWinsInfo == 0;
        v17[11] = 1;
        if ( !v12 && (*(_DWORD *)(a8 + 240) & 2) != 0 )
          v17[7] = -1;
        *(_WORD *)&v17[v13 + 49] = 3264;
        *(_DWORD *)&v17[v13 + 51] = 16785408;
        *(_WORD *)&v17[v13 + 59] = 1536;
        *(_WORD *)&v17[v13 + 61] = __ROR2__(word_140039626 | (a4 << 15), 8);
        *(_DWORD *)&v17[v13 + 63] = 0;
        return &v17[v13 + 63];
      }
      if ( a5 != 8 )
        return &v17[v13 + 63];
    }
    *((_WORD *)v17 + 1) = (a5 != 5) + 40;
    *(_DWORD *)&v17[v13 + 55] = -527236096;
    goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x14000bed0  mov     [rsp+arg_8], rbx
0x14000bed5  mov     [rsp+arg_10], rbp
0x14000beda  push    rsi
0x14000bedb  push    rdi
0x14000bedc  push    r12
0x14000bede  push    r14
0x14000bee0  push    r15
0x14000bee2  sub     rsp, 20h
0x14000bee6  movzx   r15d, r9w
0x14000beea  mov     rbx, rdx
0x14000beed  mov     r12, rcx
0x14000bef0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000bef7  nop     word ptr [rax+rax+00000000h]
0x14000bf00  cmp     byte ptr [rdx+rax+1], 0
0x14000bf05  lea     rax, [rax+1]
0x14000bf09  jnz     short loc_14000BF00
0x14000bf0b  mov     esi, [rsp+48h+arg_20]
0x14000bf0f  lea     r14d, [rax+1]
0x14000bf13  mov     ecx, 43h ; 'C'
0x14000bf18  test    esi, esi
0x14000bf1a  mov     ebp, 31h ; '1'
0x14000bf1f  mov     r8d, 5874624Eh
0x14000bf25  cmovnz  ebp, ecx
0x14000bf28  mov     ecx, 40h ; '@'
0x14000bf2d  add     ebp, r14d
0x14000bf30  movzx   edx, bp
0x14000bf33  call    cs:__imp_ExAllocatePool2
0x14000bf3a  nop     dword ptr [rax+rax+00h]
0x14000bf3f  mov     rdi, rax
0x14000bf42  test    rax, rax
0x14000bf45  jnz     short loc_14000BF5F
0x14000bf47  mov     rbx, [rsp+48h+arg_8]
0x14000bf4c  mov     rbp, [rsp+48h+arg_10]
0x14000bf51  add     rsp, 20h
0x14000bf55  pop     r15
0x14000bf57  pop     r14
0x14000bf59  pop     r12
0x14000bf5b  pop     rdi
0x14000bf5c  pop     rsi
0x14000bf5d  retn
0x14000bf5f  mov     r8d, ebp; Size
0x14000bf62  xor     edx, edx; Val
0x14000bf64  mov     rcx, rdi; void *
0x14000bf67  mov     [rsp+48h+arg_0], r13
0x14000bf6c  call    memset
0x14000bf71  mov     r13, [rsp+48h+arg_38]
0x14000bf79  movzx   eax, word ptr [r13+80h]
0x14000bf81  test    ax, ax
0x14000bf84  jz      loc_14000C239
0x14000bf8a  mov     [rdi], ax
0x14000bf8d  mov     byte ptr [rdi+5], 1
0x14000bf91  mov     byte ptr [rdi+7], 0
0x14000bf95  mov     byte ptr [rdi+9], 0
0x14000bf99  mov     byte ptr [rdi+0Ch], 20h ; ' '
0x14000bf9d  movzx   eax, byte ptr [r12]
0x14000bfa2  shr     al, 4
0x14000bfa5  add     al, 41h ; 'A'
0x14000bfa7  mov     [rdi+0Dh], al
0x14000bfaa  movzx   eax, byte ptr [r12]
0x14000bfaf  and     al, 0Fh
0x14000bfb1  add     al, 41h ; 'A'
0x14000bfb3  mov     [rdi+0Eh], al
0x14000bfb6  movzx   eax, byte ptr [r12+1]
0x14000bfbc  shr     al, 4
0x14000bfbf  add     al, 41h ; 'A'
0x14000bfc1  mov     [rdi+0Fh], al
0x14000bfc4  movzx   eax, byte ptr [r12+1]
0x14000bfca  and     al, 0Fh
0x14000bfcc  add     al, 41h ; 'A'
0x14000bfce  mov     [rdi+10h], al
0x14000bfd1  movzx   eax, byte ptr [r12+2]
0x14000bfd7  shr     al, 4
0x14000bfda  add     al, 41h ; 'A'
0x14000bfdc  mov     [rdi+11h], al
0x14000bfdf  movzx   eax, byte ptr [r12+2]
0x14000bfe5  and     al, 0Fh
0x14000bfe7  add     al, 41h ; 'A'
0x14000bfe9  mov     [rdi+12h], al
0x14000bfec  movzx   eax, byte ptr [r12+3]
0x14000bff2  shr     al, 4
0x14000bff5  add     al, 41h ; 'A'
0x14000bff7  mov     [rdi+13h], al
0x14000bffa  movzx   eax, byte ptr [r12+3]
0x14000c000  and     al, 0Fh
0x14000c002  add     al, 41h ; 'A'
0x14000c004  mov     [rdi+14h], al
0x14000c007  movzx   eax, byte ptr [r12+4]
0x14000c00d  shr     al, 4
0x14000c010  add     al, 41h ; 'A'
0x14000c012  mov     [rdi+15h], al
0x14000c015  movzx   eax, byte ptr [r12+4]
0x14000c01b  and     al, 0Fh
0x14000c01d  add     al, 41h ; 'A'
0x14000c01f  mov     [rdi+16h], al
0x14000c022  movzx   eax, byte ptr [r12+5]
0x14000c028  shr     al, 4
0x14000c02b  add     al, 41h ; 'A'
0x14000c02d  mov     [rdi+17h], al
0x14000c030  movzx   eax, byte ptr [r12+5]
0x14000c036  and     al, 0Fh
0x14000c038  add     al, 41h ; 'A'
0x14000c03a  mov     [rdi+18h], al
0x14000c03d  movzx   eax, byte ptr [r12+6]
0x14000c043  shr     al, 4
0x14000c046  add     al, 41h ; 'A'
0x14000c048  mov     [rdi+19h], al
0x14000c04b  movzx   eax, byte ptr [r12+6]
0x14000c051  and     al, 0Fh
0x14000c053  add     al, 41h ; 'A'
0x14000c055  mov     [rdi+1Ah], al
0x14000c058  movzx   eax, byte ptr [r12+7]
0x14000c05e  shr     al, 4
0x14000c061  add     al, 41h ; 'A'
0x14000c063  mov     [rdi+1Bh], al
0x14000c066  movzx   eax, byte ptr [r12+7]
0x14000c06c  and     al, 0Fh
0x14000c06e  add     al, 41h ; 'A'
0x14000c070  mov     [rdi+1Ch], al
0x14000c073  movzx   eax, byte ptr [r12+8]
0x14000c079  shr     al, 4
0x14000c07c  add     al, 41h ; 'A'
0x14000c07e  mov     [rdi+1Dh], al
0x14000c081  movzx   eax, byte ptr [r12+8]
0x14000c087  and     al, 0Fh
0x14000c089  add     al, 41h ; 'A'
0x14000c08b  mov     [rdi+1Eh], al
0x14000c08e  movzx   eax, byte ptr [r12+9]
0x14000c094  shr     al, 4
0x14000c097  add     al, 41h ; 'A'
0x14000c099  mov     [rdi+1Fh], al
0x14000c09c  movzx   eax, byte ptr [r12+9]
0x14000c0a2  and     al, 0Fh
0x14000c0a4  add     al, 41h ; 'A'
0x14000c0a6  mov     [rdi+20h], al
0x14000c0a9  movzx   eax, byte ptr [r12+0Ah]
0x14000c0af  shr     al, 4
0x14000c0b2  add     al, 41h ; 'A'
0x14000c0b4  mov     [rdi+21h], al
0x14000c0b7  movzx   eax, byte ptr [r12+0Ah]
0x14000c0bd  and     al, 0Fh
0x14000c0bf  add     al, 41h ; 'A'
0x14000c0c1  mov     [rdi+22h], al
0x14000c0c4  movzx   eax, byte ptr [r12+0Bh]
0x14000c0ca  shr     al, 4
0x14000c0cd  add     al, 41h ; 'A'
0x14000c0cf  mov     [rdi+23h], al
0x14000c0d2  movzx   eax, byte ptr [r12+0Bh]
0x14000c0d8  and     al, 0Fh
0x14000c0da  add     al, 41h ; 'A'
0x14000c0dc  mov     [rdi+24h], al
0x14000c0df  movzx   eax, byte ptr [r12+0Ch]
0x14000c0e5  shr     al, 4
0x14000c0e8  add     al, 41h ; 'A'
0x14000c0ea  mov     [rdi+25h], al
0x14000c0ed  movzx   eax, byte ptr [r12+0Ch]
0x14000c0f3  and     al, 0Fh
0x14000c0f5  add     al, 41h ; 'A'
0x14000c0f7  mov     [rdi+26h], al
0x14000c0fa  movzx   eax, byte ptr [r12+0Dh]
0x14000c100  shr     al, 4
0x14000c103  add     al, 41h ; 'A'
0x14000c105  mov     [rdi+27h], al
0x14000c108  movzx   eax, byte ptr [r12+0Dh]
0x14000c10e  and     al, 0Fh
0x14000c110  add     al, 41h ; 'A'
0x14000c112  mov     [rdi+28h], al
0x14000c115  movzx   eax, byte ptr [r12+0Eh]
0x14000c11b  shr     al, 4
0x14000c11e  add     al, 41h ; 'A'
0x14000c120  mov     [rdi+29h], al
0x14000c123  movzx   eax, byte ptr [r12+0Eh]
0x14000c129  and     al, 0Fh
0x14000c12b  add     al, 41h ; 'A'
0x14000c12d  mov     [rdi+2Ah], al
0x14000c130  movzx   eax, byte ptr [r12+0Fh]
0x14000c136  shr     al, 4
0x14000c139  add     al, 41h ; 'A'
0x14000c13b  mov     [rdi+2Bh], al
0x14000c13e  movzx   eax, byte ptr [r12+0Fh]
0x14000c144  and     al, 0Fh
0x14000c146  add     al, 41h ; 'A'
0x14000c148  mov     [rdi+2Ch], al
0x14000c14b  cmp     r14d, 1
0x14000c14f  ja      loc_14000C258
0x14000c155  mov     byte ptr [rdi+2Dh], 0
0x14000c159  mov     r14d, 1
0x14000c15f  mov     rax, [rsp+48h+arg_28]
0x14000c164  mov     dword ptr [rdi+r14+2Dh], 1002000h
0x14000c16d  mov     [rax], rdi
0x14000c170  mov     rax, [rsp+48h+arg_30]
0x14000c178  mov     [rax], ebp
0x14000c17a  test    esi, esi
0x14000c17c  jnz     short loc_14000C1AC
0x14000c17e  movzx   ecx, cs:NodeType
0x14000c185  mov     eax, 1000h
0x14000c18a  and     cx, 1
0x14000c18e  movzx   edx, cx
0x14000c191  imul    edx, eax
0x14000c194  mov     rax, rdi
0x14000c197  inc     dx
0x14000c19a  mov     [rdi+2], dx
0x14000c19e  mov     r13, [rsp+48h+arg_0]
0x14000c1a3  mov     [rdi+0Bh], sil
0x14000c1a7  jmp     loc_14000BF47
0x14000c1ac  mov     ecx, esi
0x14000c1ae  sub     ecx, 4
0x14000c1b1  jz      short loc_14000C1C2
0x14000c1b3  sub     ecx, 1
0x14000c1b6  jz      short loc_14000C1C2
0x14000c1b8  sub     ecx, 2
0x14000c1bb  jz      short loc_14000C1DB
0x14000c1bd  cmp     ecx, 1
0x14000c1c0  jnz     short loc_14000C228
0x14000c1c2  xor     eax, eax
0x14000c1c4  cmp     esi, 5
0x14000c1c7  setnz   al
0x14000c1ca  add     ax, 28h ; '('
0x14000c1ce  mov     [rdi+2], ax
0x14000c1d2  mov     dword ptr [rdi+r14+37h], 0E0930400h
0x14000c1db  cmp     esi, 7
0x14000c1de  jz      short loc_14000C247
0x14000c1e0  cmp     cs:pWinsInfo, 0
0x14000c1e8  mov     byte ptr [rdi+0Bh], 1
0x14000c1ec  jnz     short loc_14000C26C
0x14000c1ee  shl     r15w, 0Fh
0x14000c1f3  mov     word ptr [rdi+r14+31h], 0CC0h
0x14000c1fb  mov     dword ptr [rdi+r14+33h], 1002000h
0x14000c204  mov     word ptr [rdi+r14+3Bh], 600h
0x14000c20c  or      r15w, cs:word_140039626
0x14000c214  ror     r15w, 8
0x14000c219  mov     [rdi+r14+3Dh], r15w
0x14000c21f  mov     dword ptr [rdi+r14+3Fh], 0
0x14000c228  mov     r13, [rsp+48h+arg_0]
0x14000c22d  lea     rax, [rdi+3Fh]
0x14000c231  add     rax, r14
0x14000c234  jmp     loc_14000BF47
0x14000c239  call    GetTransactId
0x14000c23e  ror     ax, 8
0x14000c242  jmp     loc_14000BF8A
0x14000c247  mov     word ptr [rdi+2], 30h ; '0'
0x14000c24d  mov     dword ptr [rdi+r14+37h], 0
0x14000c256  jmp     short loc_14000C1E0
0x14000c258  mov     r8, r14; Size
0x14000c25b  lea     rcx, [rdi+2Dh]; void *
0x14000c25f  mov     rdx, rbx; Src
0x14000c262  call    memmove
0x14000c267  jmp     loc_14000C15F
0x14000c26c  mov     eax, [r13+0F0h]
0x14000c273  test    al, 2
0x14000c275  jz      loc_14000C1EE
0x14000c27b  mov     byte ptr [rdi+7], 0FFh
0x14000c27f  jmp     loc_14000C1EE
```
