# update_box_0

- ea: `0x18002ebe0`
- end: `0x18002ef5a`
- name: `update_box_0`
- size: `890`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18002e0b0`
- `0x18002e7f0`

## callees

- `0x18002ebe0`

## pseudocode

```c
__int64 __fastcall update_box_0(__int64 a1, int *a2)
{
  int v3; // r15d
  int v5; // esi
  int v6; // edi
  __int64 v7; // r14
  __int64 result; // rax
  int v9; // r10d
  __int64 v10; // r11
  int v11; // ebx
  int v12; // r8d
  int v13; // edx
  _WORD *v14; // rcx
  int v15; // ebx
  int v16; // r8d
  int v17; // edx
  _WORD *v18; // rcx
  int v19; // ebx
  int v20; // r8d
  int v21; // edx
  _WORD *v22; // rcx
  int v23; // ebx
  int v24; // r8d
  int v25; // edx
  _WORD *v26; // rcx
  int v27; // ebx
  int v28; // r8d
  int v29; // edx
  _WORD *v30; // rcx
  unsigned int v31; // ebx
  int v32; // r8d
  int v33; // edx
  _WORD *v34; // rcx
  __int64 v35; // rdx
  int v36; // r9d
  int v37; // r8d
  int v38; // r8d
  int v39; // ebx
  int v40; // r9d
  _WORD *i; // rdx
  bool v42; // zf
  int v43; // ecx

  v3 = *a2;
  v5 = a2[1];
  v6 = a2[2];
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 592) + 56LL);
  result = (unsigned int)a2[5];
  v9 = a2[3];
  v10 = a2[4];
  if ( v5 > *a2 )
  {
    v11 = *a2;
    while ( v6 > v9 )
    {
LABEL_9:
      if ( ++v11 > v5 )
        goto LABEL_12;
    }
    v12 = v6;
    while ( 1 )
    {
      v13 = v10;
      v14 = (_WORD *)(*(_QWORD *)(v7 + 8LL * v11) + 2 * v10 + ((__int64)v12 << 6));
      if ( (int)v10 <= (int)result )
        break;
LABEL_8:
      if ( ++v12 > v9 )
        goto LABEL_9;
    }
    while ( !*v14 )
    {
      ++v14;
      if ( ++v13 > (int)result )
        goto LABEL_8;
    }
    v3 = v11;
    *a2 = v11;
    if ( v5 > v11 )
    {
LABEL_12:
      v15 = v5;
      while ( v6 > v9 )
      {
LABEL_19:
        if ( --v15 < v3 )
          goto LABEL_22;
      }
      v16 = v6;
      while ( 1 )
      {
        v17 = v10;
        v18 = (_WORD *)(*(_QWORD *)(v7 + 8LL * v15) + 2 * v10 + ((__int64)v16 << 6));
        if ( (int)v10 <= (int)result )
          break;
LABEL_18:
        if ( ++v16 > v9 )
          goto LABEL_19;
      }
      while ( !*v18 )
      {
        ++v18;
        if ( ++v17 > (int)result )
          goto LABEL_18;
      }
      v5 = v15;
      a2[1] = v15;
    }
  }
LABEL_22:
  if ( v9 > v6 )
  {
    v19 = v6;
    while ( 1 )
    {
      v20 = v3;
      if ( v3 <= v5 )
        break;
LABEL_29:
      if ( ++v19 > v9 )
        goto LABEL_32;
    }
    while ( 1 )
    {
      v21 = v10;
      v22 = (_WORD *)(2 * (v10 + 32LL * v19) + *(_QWORD *)(v7 + 8LL * v20));
      if ( (int)v10 <= (int)result )
        break;
LABEL_28:
      if ( ++v20 > v5 )
        goto LABEL_29;
    }
    while ( !*v22 )
    {
      ++v22;
      if ( ++v21 > (int)result )
        goto LABEL_28;
    }
    v6 = v19;
    a2[2] = v19;
    if ( v9 > v19 )
    {
LABEL_32:
      v23 = v9;
      while ( 1 )
      {
        v24 = v3;
        if ( v3 <= v5 )
          break;
LABEL_38:
        if ( --v23 < v6 )
          goto LABEL_41;
      }
      while ( 1 )
      {
        v25 = v10;
        v26 = (_WORD *)(2 * (v10 + 32LL * v23) + *(_QWORD *)(v7 + 8LL * v24));
        if ( (int)v10 <= (int)result )
          break;
LABEL_37:
        if ( ++v24 > v5 )
          goto LABEL_38;
      }
      while ( !*v26 )
      {
        ++v26;
        if ( ++v25 > (int)result )
          goto LABEL_37;
      }
      v9 = v23;
      a2[3] = v23;
    }
  }
LABEL_41:
  if ( (int)result > (int)v10 )
  {
    v27 = v10;
    while ( 1 )
    {
      v28 = v3;
      if ( v3 <= v5 )
        break;
LABEL_48:
      if ( ++v27 > (int)result )
        goto LABEL_51;
    }
    while ( 1 )
    {
      v29 = v6;
      v30 = (_WORD *)(2 * (v27 + 32LL * v6) + *(_QWORD *)(v7 + 8LL * v28));
      if ( v6 <= v9 )
        break;
LABEL_47:
      if ( ++v28 > v5 )
        goto LABEL_48;
    }
    while ( !*v30 )
    {
      ++v29;
      v30 += 32;
      if ( v29 > v9 )
        goto LABEL_47;
    }
    LODWORD(v10) = v27;
    a2[4] = v27;
    if ( (int)result > v27 )
    {
LABEL_51:
      v31 = result;
      while ( 1 )
      {
        v32 = v3;
        if ( v3 <= v5 )
          break;
LABEL_57:
        if ( (int)--v31 < (int)v10 )
          goto LABEL_60;
      }
      while ( 1 )
      {
        v33 = v6;
        v34 = (_WORD *)(2 * ((int)v31 + 32LL * v6) + *(_QWORD *)(v7 + 8LL * v32));
        if ( v6 <= v9 )
          break;
LABEL_56:
        if ( ++v32 > v5 )
          goto LABEL_57;
      }
      while ( !*v34 )
      {
        ++v33;
        v34 += 32;
        if ( v33 > v9 )
          goto LABEL_56;
      }
      result = v31;
      a2[5] = v31;
    }
  }
LABEL_60:
  v35 = 4LL * *(int *)(a1 + 64);
  v36 = dword_180077DA8[*(int *)((char *)&dword_180077C70 + v35)] * (v5 - v3);
  v37 = dword_180077DA8[*(int *)((char *)&dword_180077CC0 + v35)] * (v9 - v6);
  LODWORD(v35) = (dword_180077DA8[*(int *)((char *)&dword_180077D10 + v35)] * ((_DWORD)result - (_DWORD)v10)) << 7;
  LODWORD(v35) = (v37 << 6) * (v37 << 6) + v35 * v35;
  v38 = 0;
  for ( a2[6] = (v36 << 7) * (v36 << 7) + v35; v3 <= v5; ++v3 )
  {
    if ( v6 <= v9 )
    {
      v39 = v6;
      do
      {
        v40 = v10;
        for ( i = (_WORD *)(*(_QWORD *)(v7 + 8LL * v3) + 2LL * (int)v10 + ((__int64)v39 << 6));
              v40 <= (int)result;
              v38 = v43 )
        {
          v42 = *i == 0;
          v43 = v38 + 1;
          ++i;
          if ( v42 )
            v43 = v38;
          ++v40;
        }
        ++v39;
      }
      while ( v39 <= v9 );
    }
  }
  a2[7] = v38;
  return result;
}

```

## disassembly

```asm
0x18002ebe0  push    rbx
0x18002ebe2  push    rbp
0x18002ebe3  push    rsi
0x18002ebe4  push    rdi
0x18002ebe5  push    r12
0x18002ebe7  push    r14
0x18002ebe9  push    r15
0x18002ebeb  mov     rax, [rcx+250h]
0x18002ebf2  mov     r12, rdx
0x18002ebf5  mov     r15d, [rdx]
0x18002ebf8  mov     rbp, rcx
0x18002ebfb  mov     esi, [rdx+4]
0x18002ebfe  mov     edi, [rdx+8]
0x18002ec01  mov     r14, [rax+38h]
0x18002ec05  mov     eax, [rdx+14h]
0x18002ec08  mov     r10d, [rdx+0Ch]
0x18002ec0c  movsxd  r11, dword ptr [rdx+10h]
0x18002ec10  cmp     esi, r15d
0x18002ec13  jle     loc_18002ECDA
0x18002ec19  mov     ebx, r15d
0x18002ec1c  nop     dword ptr [rax+00h]
0x18002ec20  cmp     edi, r10d
0x18002ec23  jg      short loc_18002EC6A
0x18002ec25  movsxd  rcx, ebx
0x18002ec28  mov     r8d, edi
0x18002ec2b  mov     rcx, [r14+rcx*8]
0x18002ec2f  lea     r9, [rcx+r11*2]
0x18002ec33  nop     dword ptr [rax+00h]
0x18002ec37  nop     word ptr [rax+rax+00000000h]
0x18002ec40  movsxd  rcx, r8d
0x18002ec43  mov     edx, r11d
0x18002ec46  shl     rcx, 6
0x18002ec4a  add     rcx, r9
0x18002ec4d  cmp     r11d, eax
0x18002ec50  jg      short loc_18002EC62
0x18002ec52  cmp     word ptr [rcx], 0
0x18002ec56  jnz     short loc_18002EC72
0x18002ec58  add     rcx, 2
0x18002ec5c  inc     edx
0x18002ec5e  cmp     edx, eax
0x18002ec60  jle     short loc_18002EC52
0x18002ec62  inc     r8d
0x18002ec65  cmp     r8d, r10d
0x18002ec68  jle     short loc_18002EC40
0x18002ec6a  inc     ebx
0x18002ec6c  cmp     ebx, esi
0x18002ec6e  jle     short loc_18002EC20
0x18002ec70  jmp     short loc_18002EC7D
0x18002ec72  mov     r15d, ebx
0x18002ec75  mov     [r12], ebx
0x18002ec79  cmp     esi, ebx
0x18002ec7b  jle     short loc_18002ECDA
0x18002ec7d  mov     ebx, esi
0x18002ec7f  nop
0x18002ec80  cmp     edi, r10d
0x18002ec83  jg      short loc_18002ECCA
0x18002ec85  movsxd  rcx, ebx
0x18002ec88  mov     r8d, edi
0x18002ec8b  mov     rcx, [r14+rcx*8]
0x18002ec8f  lea     r9, [rcx+r11*2]
0x18002ec93  nop     dword ptr [rax+00h]
0x18002ec97  nop     word ptr [rax+rax+00000000h]
0x18002eca0  movsxd  rcx, r8d
0x18002eca3  mov     edx, r11d
0x18002eca6  shl     rcx, 6
0x18002ecaa  add     rcx, r9
0x18002ecad  cmp     r11d, eax
0x18002ecb0  jg      short loc_18002ECC2
0x18002ecb2  cmp     word ptr [rcx], 0
0x18002ecb6  jnz     short loc_18002ECD3
0x18002ecb8  add     rcx, 2
0x18002ecbc  inc     edx
0x18002ecbe  cmp     edx, eax
0x18002ecc0  jle     short loc_18002ECB2
0x18002ecc2  inc     r8d
0x18002ecc5  cmp     r8d, r10d
0x18002ecc8  jle     short loc_18002ECA0
0x18002ecca  dec     ebx
0x18002eccc  cmp     ebx, r15d
0x18002eccf  jge     short loc_18002EC80
0x18002ecd1  jmp     short loc_18002ECDA
0x18002ecd3  mov     esi, ebx
0x18002ecd5  mov     [r12+4], ebx
0x18002ecda  cmp     r10d, edi
0x18002ecdd  jle     loc_18002ED9A
0x18002ece3  mov     ebx, edi
0x18002ece5  mov     r8d, r15d
0x18002ece8  cmp     r15d, esi
0x18002eceb  jg      short loc_18002ED2A
0x18002eced  movsxd  r9, ebx
0x18002ecf0  shl     r9, 5
0x18002ecf4  add     r9, r11
0x18002ecf7  add     r9, r9
0x18002ecfa  nop     word ptr [rax+rax+00h]
0x18002ed00  movsxd  rcx, r8d
0x18002ed03  mov     edx, r11d
0x18002ed06  mov     rcx, [r14+rcx*8]
0x18002ed0a  add     rcx, r9
0x18002ed0d  cmp     r11d, eax
0x18002ed10  jg      short loc_18002ED22
0x18002ed12  cmp     word ptr [rcx], 0
0x18002ed16  jnz     short loc_18002ED33
0x18002ed18  add     rcx, 2
0x18002ed1c  inc     edx
0x18002ed1e  cmp     edx, eax
0x18002ed20  jle     short loc_18002ED12
0x18002ed22  inc     r8d
0x18002ed25  cmp     r8d, esi
0x18002ed28  jle     short loc_18002ED00
0x18002ed2a  inc     ebx
0x18002ed2c  cmp     ebx, r10d
0x18002ed2f  jle     short loc_18002ECE5
0x18002ed31  jmp     short loc_18002ED3F
0x18002ed33  mov     edi, ebx
0x18002ed35  mov     [r12+8], ebx
0x18002ed3a  cmp     r10d, ebx
0x18002ed3d  jle     short loc_18002ED9A
0x18002ed3f  mov     ebx, r10d
0x18002ed42  mov     r8d, r15d
0x18002ed45  cmp     r15d, esi
0x18002ed48  jg      short loc_18002ED8A
0x18002ed4a  movsxd  r9, ebx
0x18002ed4d  shl     r9, 5
0x18002ed51  add     r9, r11
0x18002ed54  add     r9, r9
0x18002ed57  nop     word ptr [rax+rax+00000000h]
0x18002ed60  movsxd  rcx, r8d
0x18002ed63  mov     edx, r11d
0x18002ed66  mov     rcx, [r14+rcx*8]
0x18002ed6a  add     rcx, r9
0x18002ed6d  cmp     r11d, eax
0x18002ed70  jg      short loc_18002ED82
0x18002ed72  cmp     word ptr [rcx], 0
0x18002ed76  jnz     short loc_18002ED92
0x18002ed78  add     rcx, 2
0x18002ed7c  inc     edx
0x18002ed7e  cmp     edx, eax
0x18002ed80  jle     short loc_18002ED72
0x18002ed82  inc     r8d
0x18002ed85  cmp     r8d, esi
0x18002ed88  jle     short loc_18002ED60
0x18002ed8a  dec     ebx
0x18002ed8c  cmp     ebx, edi
0x18002ed8e  jge     short loc_18002ED42
0x18002ed90  jmp     short loc_18002ED9A
0x18002ed92  mov     r10d, ebx
0x18002ed95  mov     [r12+0Ch], ebx
0x18002ed9a  cmp     eax, r11d
0x18002ed9d  jle     loc_18002EE5A
0x18002eda3  mov     ebx, r11d
0x18002eda6  mov     r8d, r15d
0x18002eda9  cmp     r15d, esi
0x18002edac  jg      short loc_18002EDEA
0x18002edae  movsxd  r9, edi
0x18002edb1  shl     r9, 5
0x18002edb5  movsxd  rcx, ebx
0x18002edb8  add     r9, rcx
0x18002edbb  add     r9, r9
0x18002edbe  xchg    ax, ax
0x18002edc0  movsxd  rcx, r8d
0x18002edc3  mov     edx, edi
0x18002edc5  mov     rcx, [r14+rcx*8]
0x18002edc9  add     rcx, r9
0x18002edcc  cmp     edi, r10d
0x18002edcf  jg      short loc_18002EDE2
0x18002edd1  cmp     word ptr [rcx], 0
0x18002edd5  jnz     short loc_18002EDF2
0x18002edd7  inc     edx
0x18002edd9  add     rcx, 40h ; '@'
0x18002eddd  cmp     edx, r10d
0x18002ede0  jle     short loc_18002EDD1
0x18002ede2  inc     r8d
0x18002ede5  cmp     r8d, esi
0x18002ede8  jle     short loc_18002EDC0
0x18002edea  inc     ebx
0x18002edec  cmp     ebx, eax
0x18002edee  jle     short loc_18002EDA6
0x18002edf0  jmp     short loc_18002EDFE
0x18002edf2  mov     r11d, ebx
0x18002edf5  mov     [r12+10h], ebx
0x18002edfa  cmp     eax, ebx
0x18002edfc  jle     short loc_18002EE5A
0x18002edfe  mov     ebx, eax
0x18002ee00  mov     r8d, r15d
0x18002ee03  cmp     r15d, esi
0x18002ee06  jg      short loc_18002EE4A
0x18002ee08  movsxd  r9, edi
0x18002ee0b  shl     r9, 5
0x18002ee0f  movsxd  rcx, ebx
0x18002ee12  add     r9, rcx
0x18002ee15  add     r9, r9
0x18002ee18  nop     dword ptr [rax+rax+00000000h]
0x18002ee20  movsxd  rcx, r8d
0x18002ee23  mov     edx, edi
0x18002ee25  mov     rcx, [r14+rcx*8]
0x18002ee29  add     rcx, r9
0x18002ee2c  cmp     edi, r10d
0x18002ee2f  jg      short loc_18002EE42
0x18002ee31  cmp     word ptr [rcx], 0
0x18002ee35  jnz     short loc_18002EE53
0x18002ee37  inc     edx
0x18002ee39  add     rcx, 40h ; '@'
0x18002ee3d  cmp     edx, r10d
0x18002ee40  jle     short loc_18002EE31
0x18002ee42  inc     r8d
0x18002ee45  cmp     r8d, esi
0x18002ee48  jle     short loc_18002EE20
0x18002ee4a  dec     ebx
0x18002ee4c  cmp     ebx, r11d
0x18002ee4f  jge     short loc_18002EE00
0x18002ee51  jmp     short loc_18002EE5A
0x18002ee53  mov     eax, ebx
0x18002ee55  mov     [r12+14h], ebx
0x18002ee5a  movsxd  rcx, dword ptr [rbp+40h]
0x18002ee5e  lea     rbx, __ImageBase
0x18002ee65  mov     r9d, esi
0x18002ee68  mov     r8d, r10d
0x18002ee6b  sub     r8d, edi
0x18002ee6e  sub     r9d, r15d
0x18002ee71  lea     rdx, ds:0[rcx*4]
0x18002ee79  movsxd  rcx, dword ptr [rdx+rbx+77C70h]
0x18002ee81  imul    r9d, ds:rva dword_180077DA8[rbx+rcx*4]
0x18002ee8a  movsxd  rcx, dword ptr [rdx+rbx+77CC0h]
0x18002ee92  imul    r8d, ds:rva dword_180077DA8[rbx+rcx*4]
0x18002ee9b  movsxd  rcx, dword ptr [rdx+rbx+77D10h]
0x18002eea3  mov     edx, eax
0x18002eea5  sub     edx, r11d
0x18002eea8  shl     r9d, 7
0x18002eeac  imul    r9d, r9d
0x18002eeb0  imul    edx, ds:rva dword_180077DA8[rbx+rcx*4]
0x18002eeb8  shl     r8d, 6
0x18002eebc  imul    r8d, r8d
0x18002eec0  shl     edx, 7
0x18002eec3  imul    edx, edx
0x18002eec6  add     edx, r8d
0x18002eec9  xor     r8d, r8d
0x18002eecc  add     edx, r9d
0x18002eecf  mov     [r12+18h], edx
0x18002eed4  cmp     r15d, esi
0x18002eed7  jg      short loc_18002EF4A
0x18002eed9  nop     dword ptr [rax+00000000h]
0x18002eee0  cmp     edi, r10d
0x18002eee3  jg      short loc_18002EF42
0x18002eee5  movsxd  rcx, r15d
0x18002eee8  mov     ebx, edi
0x18002eeea  movsxd  rdx, r11d
0x18002eeed  mov     rcx, [r14+rcx*8]
0x18002eef1  lea     rbp, [rcx+rdx*2]
0x18002eef5  nop     word ptr [rax+rax+00000000h]
0x18002ef00  movsxd  rdx, ebx
0x18002ef03  mov     r9d, r11d
0x18002ef06  shl     rdx, 6
0x18002ef0a  add     rdx, rbp
0x18002ef0d  cmp     r11d, eax
0x18002ef10  jg      short loc_18002EF3B
0x18002ef12  nop     dword ptr [rax+00h]
0x18002ef16  nop     word ptr [rax+rax+00000000h]
0x18002ef20  cmp     word ptr [rdx], 0
0x18002ef24  lea     ecx, [r8+1]
0x18002ef28  lea     rdx, [rdx+2]
0x18002ef2c  cmovz   ecx, r8d
0x18002ef30  inc     r9d
0x18002ef33  mov     r8d, ecx
0x18002ef36  cmp     r9d, eax
0x18002ef39  jle     short loc_18002EF20
0x18002ef3b  inc     ebx
0x18002ef3d  cmp     ebx, r10d
0x18002ef40  jle     short loc_18002EF00
0x18002ef42  inc     r15d
0x18002ef45  cmp     r15d, esi
0x18002ef48  jle     short loc_18002EEE0
0x18002ef4a  mov     [r12+1Ch], r8d
0x18002ef4f  pop     r15
0x18002ef51  pop     r14
0x18002ef53  pop     r12
0x18002ef55  pop     rdi
0x18002ef56  pop     rsi
0x18002ef57  pop     rbp
0x18002ef58  pop     rbx
0x18002ef59  retn
```
