# ReadStringDelimited_5

- ea: `0x180057500`
- end: `0x180057674`
- name: `ReadStringDelimited_5`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800576b0`

## callees

- `0x180057314`
- `0x180057500`

## pseudocode

```c
__int64 __fastcall ReadStringDelimited_5(
        char a1,
        unsigned __int8 **a2,
        int *a3,
        _DWORD *a4,
        _QWORD *SrcCh,
        int a6,
        FILE *Stream,
        __crt_locale_pointers *Locale,
        _DWORD *a9)
{
  char v12; // bl
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // r8
  unsigned __int8 v15; // dl
  char v16; // al
  unsigned __int8 *v17; // rcx
  unsigned __int8 *v18; // r8
  unsigned __int8 v19; // al
  unsigned __int8 v20; // r9
  unsigned __int8 v21; // cl
  unsigned __int8 v22; // r10
  unsigned __int8 v23; // r11
  int v25[4]; // [rsp+50h] [rbp-48h] BYREF
  __int128 v26; // [rsp+60h] [rbp-38h]

  *(_OWORD *)v25 = 0;
  v12 = a1;
  v26 = 0;
  v13 = *a2;
  v14 = *a2 + 1;
  *a2 = v14;
  if ( *v14 == 94 )
  {
    v15 = v14[1];
    v12 = a1 | 8;
  }
  else
  {
    v15 = *v14;
  }
  if ( *v14 != 94 )
    v14 = v13;
  v16 = HIBYTE(v25[2]);
  if ( v15 == 93 )
    v16 = 32;
  v17 = v14 + 1;
  HIBYTE(v25[2]) = v16;
  if ( v15 != 93 )
    v17 = v14;
  v18 = v17 + 1;
  v19 = v17[1];
  if ( v19 != 93 )
  {
    v20 = v15 != 93 ? 0 : 0x5D;
    do
    {
      ++v18;
      if ( v19 == 45 && v20 && (v21 = *v18, *v18 != 93) )
      {
        ++v18;
        v22 = v20;
        v23 = v21;
        if ( v20 >= v21 )
        {
          v23 = v20;
          v22 = v21;
        }
        while ( v22 <= v23 )
        {
          *((_BYTE *)v25 + ((unsigned __int64)v22 >> 3)) |= 1 << (v22 & 7);
          ++v22;
        }
        v20 = 0;
      }
      else
      {
        v20 = v19;
        *((_BYTE *)v25 + ((unsigned __int64)v19 >> 3)) |= 1 << (v19 & 7);
      }
      v19 = *v18;
    }
    while ( *v18 != 93 );
  }
  *a2 = v18;
  return ReadString_5(v12, (__int64)v25, a3, a4, SrcCh, a6, Stream, Locale, a9);
}

```

## disassembly

```asm
0x180057500  mov     rax, rsp
0x180057503  mov     [rax+8], rbx
0x180057507  mov     [rax+20h], rbp
0x18005750b  push    rsi
0x18005750c  push    rdi
0x18005750d  push    r12
0x18005750f  push    r14
0x180057511  push    r15
0x180057513  sub     rsp, 70h
0x180057517  mov     r14, [rsp+98h+arg_20]
0x18005751f  xorps   xmm0, xmm0
0x180057522  mov     r15, [rsp+98h+arg_30]
0x18005752a  mov     rbp, r8
0x18005752d  mov     r12, [rsp+98h+arg_38]
0x180057535  mov     rsi, r9
0x180057538  movups  xmmword ptr [rax-48h], xmm0
0x18005753c  mov     rdi, rdx
0x18005753f  mov     ebx, ecx
0x180057541  movups  xmmword ptr [rax-38h], xmm0
0x180057545  mov     rax, [rdx]
0x180057548  lea     r8, [rax+1]
0x18005754c  mov     [rdx], r8
0x18005754f  cmp     byte ptr [r8], 5Eh ; '^'
0x180057553  jnz     short loc_18005755E
0x180057555  mov     dl, [r8+1]
0x180057559  or      ebx, 8
0x18005755c  jmp     short loc_180057561
0x18005755e  mov     dl, [r8]
0x180057561  cmp     byte ptr [r8], 5Eh ; '^'
0x180057565  mov     r9d, 20h ; ' '
0x18005756b  cmovnz  r8, rax
0x18005756f  movzx   eax, [rsp+98h+var_3D]
0x180057574  cmp     dl, 5Dh ; ']'
0x180057577  cmovz   eax, r9d
0x18005757b  lea     rcx, [r8+1]
0x18005757f  mov     [rsp+98h+var_3D], al
0x180057583  cmovnz  rcx, r8
0x180057587  lea     r8, [rcx+1]
0x18005758b  mov     al, [r8]
0x18005758e  cmp     al, 5Dh ; ']'
0x180057590  jz      loc_18005761F
0x180057596  cmp     dl, 5Dh ; ']'
0x180057599  setnz   r9b
0x18005759d  dec     r9b
0x1800575a0  and     r9b, 5Dh
0x1800575a4  inc     r8
0x1800575a7  cmp     al, 2Dh ; '-'
0x1800575a9  jnz     short loc_1800575FC
0x1800575ab  test    r9b, r9b
0x1800575ae  jz      short loc_1800575FC
0x1800575b0  movzx   ecx, byte ptr [r8]
0x1800575b4  cmp     cl, 5Dh ; ']'
0x1800575b7  jz      short loc_1800575FC
0x1800575b9  inc     r8
0x1800575bc  movzx   eax, r9b
0x1800575c0  cmp     r9b, cl
0x1800575c3  movzx   r10d, r9b
0x1800575c7  mov     r11d, ecx
0x1800575ca  cmovnb  r11d, eax
0x1800575ce  cmovnb  r10d, ecx
0x1800575d2  jmp     short loc_1800575F2
0x1800575d4  movzx   edx, r10b
0x1800575d8  shr     rdx, 3
0x1800575dc  movzx   eax, r10b
0x1800575e0  and     eax, 7
0x1800575e3  movsx   ecx, byte ptr [rsp+rdx+98h+var_48]
0x1800575e8  bts     ecx, eax
0x1800575eb  mov     byte ptr [rsp+rdx+98h+var_48], cl
0x1800575ef  inc     r10b
0x1800575f2  cmp     r10b, r11b
0x1800575f5  jbe     short loc_1800575D4
0x1800575f7  xor     r9b, r9b
0x1800575fa  jmp     short loc_180057618
0x1800575fc  movzx   edx, al
0x1800575ff  mov     r9b, al
0x180057602  shr     rdx, 3
0x180057606  movzx   eax, al
0x180057609  and     eax, 7
0x18005760c  movsx   ecx, byte ptr [rsp+rdx+98h+var_48]
0x180057611  bts     ecx, eax
0x180057614  mov     byte ptr [rsp+rdx+98h+var_48], cl
0x180057618  mov     al, [r8]
0x18005761b  cmp     al, 5Dh ; ']'
0x18005761d  jnz     short loc_1800575A4
0x18005761f  mov     rax, [rsp+98h+arg_40]
0x180057627  lea     rdx, [rsp+98h+var_48]; int
0x18005762c  mov     [rsp+98h+var_58], rax; __int64
0x180057631  mov     r9, rsi; int
0x180057634  mov     eax, [rsp+98h+arg_28]
0x18005763b  mov     ecx, ebx; int
0x18005763d  mov     [rsp+98h+Locale], r12; Locale
0x180057642  mov     [rsp+98h+Stream], r15; Stream
0x180057647  mov     [rdi], r8
0x18005764a  mov     r8, rbp; int
0x18005764d  mov     [rsp+98h+var_70], eax; int
0x180057651  mov     qword ptr [rsp+98h+SrcCh], r14; SrcCh
0x180057656  call    ReadString_5
0x18005765b  lea     r11, [rsp+98h+var_28]
0x180057660  mov     rbx, [r11+30h]
0x180057664  mov     rbp, [r11+48h]
0x180057668  mov     rsp, r11
0x18005766b  pop     r15
0x18005766d  pop     r14
0x18005766f  pop     r12
0x180057671  pop     rdi
0x180057672  pop     rsi
0x180057673  retn
```
