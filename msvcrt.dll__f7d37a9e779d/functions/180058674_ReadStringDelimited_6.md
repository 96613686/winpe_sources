# ReadStringDelimited_6

- ea: `0x180058674`
- end: `0x1800587e5`
- name: `ReadStringDelimited_6`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800587f0`

## callees

- `0x180058438`
- `0x180058674`

## pseudocode

```c
__int64 __fastcall ReadStringDelimited_6(
        char a1,
        unsigned __int8 **a2,
        int *a3,
        _DWORD *a4,
        _WORD **SrcCh,
        int a6,
        FILE *Stream,
        __int64 a8,
        __crt_locale_pointers *Locale,
        _DWORD *a10)
{
  unsigned __int8 *v10; // rax
  unsigned __int8 *v14; // rdx
  char v15; // bl
  bool v16; // zf
  unsigned __int8 v17; // r9
  char v18; // al
  unsigned __int8 *v19; // rcx
  unsigned __int8 *v20; // r8
  unsigned __int8 v21; // al
  unsigned __int8 v22; // r9
  unsigned __int8 v23; // cl
  unsigned __int8 v24; // r10
  unsigned __int8 v25; // r11
  int v27[4]; // [rsp+50h] [rbp-58h] BYREF
  __int128 v28; // [rsp+60h] [rbp-48h]

  v10 = *a2;
  v14 = *a2 + 1;
  v15 = a1;
  *a2 = v14;
  v16 = *v14 == 94;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  if ( v16 )
  {
    v17 = v14[1];
    v15 = a1 | 8;
  }
  else
  {
    v17 = *v14;
  }
  if ( *v14 != 94 )
    v14 = v10;
  v18 = HIBYTE(v27[2]);
  if ( v17 == 93 )
    v18 = 32;
  v19 = v14 + 1;
  HIBYTE(v27[2]) = v18;
  if ( v17 != 93 )
    v19 = v14;
  v20 = v19 + 1;
  v21 = v19[1];
  if ( v21 != 93 )
  {
    v22 = v17 != 93 ? 0 : 0x5D;
    do
    {
      ++v20;
      if ( v21 == 45 && v22 && (v23 = *v20, *v20 != 93) )
      {
        ++v20;
        v24 = v22;
        v25 = v23;
        if ( v22 >= v23 )
        {
          v25 = v22;
          v24 = v23;
        }
        while ( v24 <= v25 )
        {
          *((_BYTE *)v27 + ((unsigned __int64)v24 >> 3)) |= 1 << (v24 & 7);
          ++v24;
        }
        v22 = 0;
      }
      else
      {
        v22 = v21;
        *((_BYTE *)v27 + ((unsigned __int64)v21 >> 3)) |= 1 << (v21 & 7);
      }
      v21 = *v20;
    }
    while ( *v20 != 93 );
  }
  *a2 = v20;
  return ReadString_6(v15, (__int64)v27, a3, a4, SrcCh, a6, Stream, a8, Locale, a10);
}

```

## disassembly

```asm
0x180058674  push    rbx
0x180058676  push    rbp
0x180058677  push    rsi
0x180058678  push    rdi
0x180058679  push    r12
0x18005867b  push    r14
0x18005867d  push    r15
0x18005867f  sub     rsp, 70h
0x180058683  mov     rax, [rdx]
0x180058686  mov     rdi, rdx
0x180058689  mov     r14, [rsp+0A8h+arg_20]
0x180058691  xorps   xmm0, xmm0
0x180058694  mov     r15, [rsp+0A8h+arg_30]
0x18005869c  mov     rsi, r9
0x18005869f  mov     r12, [rsp+0A8h+arg_40]
0x1800586a7  mov     rbp, r8
0x1800586aa  lea     rdx, [rax+1]
0x1800586ae  mov     ebx, ecx
0x1800586b0  mov     [rdi], rdx
0x1800586b3  cmp     byte ptr [rdx], 5Eh ; '^'
0x1800586b6  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x1800586bb  movups  [rsp+0A8h+var_48], xmm0
0x1800586c0  jnz     short loc_1800586CB
0x1800586c2  mov     r9b, [rdx+1]
0x1800586c6  or      ebx, 8
0x1800586c9  jmp     short loc_1800586CE
0x1800586cb  mov     r9b, [rdx]
0x1800586ce  cmp     byte ptr [rdx], 5Eh ; '^'
0x1800586d1  mov     r8d, 20h ; ' '
0x1800586d7  cmovnz  rdx, rax
0x1800586db  movzx   eax, byte ptr [rsp+0A8h+var_58+0Bh]
0x1800586e0  cmp     r9b, 5Dh ; ']'
0x1800586e4  cmovz   eax, r8d
0x1800586e8  lea     rcx, [rdx+1]
0x1800586ec  mov     byte ptr [rsp+0A8h+var_58+0Bh], al
0x1800586f0  cmovnz  rcx, rdx
0x1800586f4  lea     r8, [rcx+1]
0x1800586f8  mov     al, [r8]
0x1800586fb  cmp     al, 5Dh ; ']'
0x1800586fd  jz      loc_18005878D
0x180058703  cmp     r9b, 5Dh ; ']'
0x180058707  setnz   r9b
0x18005870b  dec     r9b
0x18005870e  and     r9b, 5Dh
0x180058712  inc     r8
0x180058715  cmp     al, 2Dh ; '-'
0x180058717  jnz     short loc_18005876A
0x180058719  test    r9b, r9b
0x18005871c  jz      short loc_18005876A
0x18005871e  movzx   ecx, byte ptr [r8]
0x180058722  cmp     cl, 5Dh ; ']'
0x180058725  jz      short loc_18005876A
0x180058727  inc     r8
0x18005872a  movzx   eax, r9b
0x18005872e  cmp     r9b, cl
0x180058731  movzx   r10d, r9b
0x180058735  mov     r11d, ecx
0x180058738  cmovnb  r11d, eax
0x18005873c  cmovnb  r10d, ecx
0x180058740  jmp     short loc_180058760
0x180058742  movzx   edx, r10b
0x180058746  shr     rdx, 3
0x18005874a  movzx   eax, r10b
0x18005874e  and     eax, 7
0x180058751  movsx   ecx, byte ptr [rsp+rdx+0A8h+var_58]
0x180058756  bts     ecx, eax
0x180058759  mov     byte ptr [rsp+rdx+0A8h+var_58], cl
0x18005875d  inc     r10b
0x180058760  cmp     r10b, r11b
0x180058763  jbe     short loc_180058742
0x180058765  xor     r9b, r9b
0x180058768  jmp     short loc_180058786
0x18005876a  movzx   edx, al
0x18005876d  mov     r9b, al
0x180058770  shr     rdx, 3
0x180058774  movzx   eax, al
0x180058777  and     eax, 7
0x18005877a  movsx   ecx, byte ptr [rsp+rdx+0A8h+var_58]
0x18005877f  bts     ecx, eax
0x180058782  mov     byte ptr [rsp+rdx+0A8h+var_58], cl
0x180058786  mov     al, [r8]
0x180058789  cmp     al, 5Dh ; ']'
0x18005878b  jnz     short loc_180058712
0x18005878d  mov     rax, [rsp+0A8h+arg_48]
0x180058795  lea     rdx, [rsp+0A8h+var_58]; int
0x18005879a  mov     [rsp+0A8h+var_60], rax; __int64
0x18005879f  mov     r9, rsi; int
0x1800587a2  mov     rax, [rsp+0A8h+arg_38]
0x1800587aa  mov     ecx, ebx; int
0x1800587ac  mov     [rsp+0A8h+Locale], r12; Locale
0x1800587b1  mov     [rsp+0A8h+var_70], rax; __int64
0x1800587b6  mov     eax, [rsp+0A8h+arg_28]
0x1800587bd  mov     [rsp+0A8h+Stream], r15; Stream
0x1800587c2  mov     [rdi], r8
0x1800587c5  mov     r8, rbp; int
0x1800587c8  mov     [rsp+0A8h+var_80], eax; int
0x1800587cc  mov     qword ptr [rsp+0A8h+SrcCh], r14; SrcCh
0x1800587d1  call    ReadString_6
0x1800587d6  add     rsp, 70h
0x1800587da  pop     r15
0x1800587dc  pop     r14
0x1800587de  pop     r12
0x1800587e0  pop     rdi
0x1800587e1  pop     rsi
0x1800587e2  pop     rbp
0x1800587e3  pop     rbx
0x1800587e4  retn
```
