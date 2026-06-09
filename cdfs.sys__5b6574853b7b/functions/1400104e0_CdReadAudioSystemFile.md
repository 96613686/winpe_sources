# CdReadAudioSystemFile

- ea: `0x1400104e0`
- end: `0x1400106f9`
- name: `CdReadAudioSystemFile`
- size: `537`
- prototype: `__int64 __fastcall(int, int, int, int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f27c`

## callees

- `0x140003000`
- `0x140003300`
- `0x1400104e0`

## pseudocode

```c
void *__fastcall CdReadAudioSystemFile(__int64 a1, _WORD *a2, __int64 a3, unsigned int a4, char *a5)
{
  char *v5; // r14
  unsigned int v6; // r13d
  __int64 v7; // r9
  void *result; // rax
  __int64 v9; // r12
  int v10; // ecx
  __int64 v11; // rax
  int v12; // r13d
  __int64 v13; // rbx
  int v14; // ebp
  __int64 v15; // rbx
  char *v16; // rsi
  unsigned __int8 v17; // cl
  unsigned int v18; // [rsp+20h] [rbp-98h]
  int v19; // [rsp+24h] [rbp-94h]
  unsigned int v20; // [rsp+28h] [rbp-90h]
  __int128 Src; // [rsp+38h] [rbp-80h] BYREF
  _OWORD v24[7]; // [rsp+48h] [rbp-70h]

  v5 = a5;
  v6 = a4;
  v7 = a1;
  if ( *a2 == 771 )
  {
    Src = 0;
    BYTE8(Src) = 0;
    LOBYTE(Src) = 1;
    v24[0] = 0;
    if ( v6 >= 0xA )
      v6 = 10;
    WORD3(Src) = 1;
    *(_OWORD *)((char *)v24 + 13) = 0;
    return memmove(a5, &Src, v6);
  }
  else
  {
    v9 = 0;
    if ( a3 )
    {
      v11 = 0;
      do
      {
        LODWORD(v9) = v9 + 35;
        v11 += 2048;
      }
      while ( v11 < a3 );
      v9 = (unsigned int)(v9 - 2);
      v19 = 0;
      v10 = 0;
    }
    else
    {
      v19 = 68;
      *(_OWORD *)a5 = 0;
      v10 = 2;
      *((_OWORD *)a5 + 1) = 0;
      *a5 = 34;
      *((_WORD *)a5 + 16) = 1;
      a5[25] = 2;
      *((_WORD *)a5 + 9) = 351;
      a5[20] = 1;
      *(_OWORD *)(a5 + 34) = 0;
      *(_OWORD *)(a5 + 50) = 0;
      a5[59] |= 2u;
      a5[34] = 34;
      *((_WORD *)a5 + 33) = 257;
      *((_WORD *)a5 + 26) = 351;
      a5[54] = 1;
    }
    v18 = v10;
    v20 = 2048;
    do
    {
      v12 = v19;
      do
      {
        v13 = *(_QWORD *)(v7 + 16);
        if ( (unsigned int)v9 >= *(_DWORD *)(v13 + 532) )
          break;
        v14 = CdAudioDirentSize;
        v15 = *(_QWORD *)(v13 + 520);
        v16 = &v5[v12];
        memset(v16, 0, (unsigned int)CdAudioDirentSize);
        v7 = a1;
        *v16 = v14;
        v12 += v14;
        v16[32] = 11;
        qmemcpy(v16 + 33, "Track00.cda", 11);
        *((_WORD *)v16 + 9) = 351;
        v16[20] = 1;
        v17 = *(_BYTE *)(v15 + 8 * v9 + 6) / 0xAu;
        v16[39] = *(_BYTE *)(v15 + 8 * v9 + 6) % 0xAu + 48;
        v16[38] = v17 % 0xAu + 48;
        v16[52] = v9;
        v9 = (unsigned int)(v9 + 1);
        *((_DWORD *)v16 + 12) = 1096286272;
        ++v18;
      }
      while ( v18 < 0x23 );
      memset(&v5[v12], 0, (unsigned int)(2048 - v12));
      v7 = a1;
      v18 = 0;
      result = 0;
      v5 += 2048;
      v19 = 0;
      v20 += 2048;
    }
    while ( v20 <= a4 );
  }
  return result;
}

```

## disassembly

```asm
0x1400104e0  push    rbx
0x1400104e2  push    rbp
0x1400104e3  push    rsi
0x1400104e4  push    rdi
0x1400104e5  push    r12
0x1400104e7  push    r13
0x1400104e9  push    r14
0x1400104eb  push    r15
0x1400104ed  sub     rsp, 78h
0x1400104f1  mov     r14, [rsp+0B8h+arg_20]
0x1400104f9  mov     eax, 303h
0x1400104fe  mov     r13d, r9d
0x140010501  mov     [rsp+0B8h+var_8C], r9d
0x140010506  mov     r9, rcx
0x140010509  mov     [rsp+0B8h+var_88], rcx
0x14001050e  mov     r15d, 1
0x140010514  cmp     [rdx], ax
0x140010517  jnz     short loc_14001055C
0x140010519  xorps   xmm0, xmm0
0x14001051c  lea     rdx, [rsp+0B8h+Src]; Src
0x140010521  xor     eax, eax
0x140010523  mov     rcx, r14; void *
0x140010526  movups  [rsp+0B8h+Src], xmm0
0x14001052b  mov     byte ptr [rsp+0B8h+Src+8], al
0x14001052f  lea     eax, [r15+9]
0x140010533  cmp     r13d, eax
0x140010536  mov     byte ptr [rsp+0B8h+Src], r15b
0x14001053b  movups  [rsp+0B8h+var_70], xmm0
0x140010540  cmovnb  r13d, eax
0x140010544  mov     word ptr [rsp+0B8h+Src+6], r15w
0x14001054a  mov     r8d, r13d; Size
0x14001054d  movups  [rsp+0B8h+var_70+0Dh], xmm0
0x140010552  call    memmove
0x140010557  jmp     loc_1400106E7
0x14001055c  xor     r12d, r12d
0x14001055f  mov     ebx, 800h
0x140010564  test    r8, r8
0x140010567  jnz     short loc_1400105C1
0x140010569  xorps   xmm0, xmm0
0x14001056c  mov     [rsp+0B8h+var_94], 44h ; 'D'
0x140010574  movups  xmmword ptr [r14], xmm0
0x140010578  lea     ecx, [r12+2]
0x14001057d  movups  xmmword ptr [r14+10h], xmm0
0x140010582  mov     byte ptr [r14], 22h ; '"'
0x140010586  mov     [r14+20h], r15w
0x14001058b  mov     [r14+19h], cl
0x14001058f  mov     word ptr [r14+12h], 15Fh
0x140010596  mov     [r14+14h], r15b
0x14001059a  movups  xmmword ptr [r14+22h], xmm0
0x14001059f  movups  xmmword ptr [r14+32h], xmm0
0x1400105a4  or      [r14+3Bh], cl
0x1400105a8  mov     byte ptr [r14+22h], 22h ; '"'
0x1400105ad  mov     word ptr [r14+42h], 101h
0x1400105b4  mov     word ptr [r14+34h], 15Fh
0x1400105bb  mov     [r14+36h], r15b
0x1400105bf  jmp     short loc_1400105DB
0x1400105c1  xor     eax, eax
0x1400105c3  add     r12d, 23h ; '#'
0x1400105c7  add     rax, rbx
0x1400105ca  cmp     rax, r8
0x1400105cd  jl      short loc_1400105C3
0x1400105cf  xor     eax, eax
0x1400105d1  add     r12d, 0FFFFFFFEh
0x1400105d5  mov     [rsp+0B8h+var_94], eax
0x1400105d9  xor     ecx, ecx
0x1400105db  mov     [rsp+0B8h+var_98], ecx
0x1400105df  mov     [rsp+0B8h+var_90], ebx
0x1400105e3  mov     r13d, [rsp+0B8h+var_94]
0x1400105e8  mov     rbx, [r9+10h]
0x1400105ec  cmp     r12d, [rbx+214h]
0x1400105f3  jnb     loc_1400106A7
0x1400105f9  mov     ebp, cs:CdAudioDirentSize
0x1400105ff  xor     edx, edx; Val
0x140010601  mov     rbx, [rbx+208h]
0x140010608  mov     r8d, ebp; Size
0x14001060b  mov     esi, r13d
0x14001060e  add     rsi, r14
0x140010611  mov     rcx, rsi; void *
0x140010614  call    memset
0x140010619  mov     r9, [rsp+0B8h+var_88]
0x14001061e  mov     r10d, 0CCCCCCCDh
0x140010624  mov     [rsi], bpl
0x140010627  add     r13d, ebp
0x14001062a  mov     byte ptr [rsi+20h], 0Bh
0x14001062e  movsd   xmm0, cs:CdAudioFileName
0x140010636  movsd   qword ptr [rsi+21h], xmm0
0x14001063b  mov     eax, dword ptr cs:CdAudioFileName+7
0x140010641  mov     [rsi+28h], eax
0x140010644  mov     eax, r10d
0x140010647  mov     word ptr [rsi+12h], 15Fh
0x14001064d  mov     [rsi+14h], r15b
0x140010651  movzx   r8d, byte ptr [rbx+r12*8+6]
0x140010657  mul     r8d
0x14001065a  shr     edx, 3
0x14001065d  movzx   ecx, dl
0x140010660  lea     eax, [rdx+rdx*4]
0x140010663  add     eax, eax
0x140010665  sub     r8d, eax
0x140010668  mov     eax, r10d
0x14001066b  mul     ecx
0x14001066d  add     r8b, 30h ; '0'
0x140010671  shr     edx, 3
0x140010674  mov     [rsi+27h], r8b
0x140010678  lea     eax, [rdx+rdx*4]
0x14001067b  add     eax, eax
0x14001067d  sub     ecx, eax
0x14001067f  add     cl, 30h ; '0'
0x140010682  mov     [rsi+26h], cl
0x140010685  mov     ecx, [rsp+0B8h+var_98]
0x140010689  add     ecx, r15d
0x14001068c  mov     [rsi+34h], r12b
0x140010690  add     r12d, r15d
0x140010693  mov     dword ptr [rsi+30h], 41580040h
0x14001069a  mov     [rsp+0B8h+var_98], ecx
0x14001069e  cmp     ecx, 23h ; '#'
0x1400106a1  jb      loc_1400105E8
0x1400106a7  mov     ebx, 800h
0x1400106ac  mov     ecx, r13d
0x1400106af  mov     r8d, ebx
0x1400106b2  add     rcx, r14; void *
0x1400106b5  sub     r8d, r13d; Size
0x1400106b8  xor     edx, edx; Val
0x1400106ba  call    memset
0x1400106bf  mov     r9, [rsp+0B8h+var_88]
0x1400106c4  xor     ecx, ecx
0x1400106c6  mov     [rsp+0B8h+var_98], ecx
0x1400106ca  xor     eax, eax
0x1400106cc  mov     ecx, [rsp+0B8h+var_90]
0x1400106d0  add     r14, rbx
0x1400106d3  add     ecx, ebx
0x1400106d5  mov     [rsp+0B8h+var_94], eax
0x1400106d9  mov     [rsp+0B8h+var_90], ecx
0x1400106dd  cmp     ecx, [rsp+0B8h+var_8C]
0x1400106e1  jbe     loc_1400105E3
0x1400106e7  add     rsp, 78h
0x1400106eb  pop     r15
0x1400106ed  pop     r14
0x1400106ef  pop     r13
0x1400106f1  pop     r12
0x1400106f3  pop     rdi
0x1400106f4  pop     rsi
0x1400106f5  pop     rbp
0x1400106f6  pop     rbx
0x1400106f7  retn
```
