# ComputeMaxPStats

- ea: `0x1800175f4`
- end: `0x1800178e3`
- name: `ComputeMaxPStats`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180010454`

## callees

- `0x1800175f4`
- `0x1800178ec`
- `0x180017a48`
- `0x180019a40`
- `0x180019ac4`
- `0x180019e04`
- `0x180019e64`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall ComputeMaxPStats(
        __int64 a1,
        __int16 *a2,
        __int16 *a3,
        __int16 *a4,
        __int16 *a5,
        __int16 *a6,
        unsigned __int16 *a7,
        __int16 *a8,
        __int64 a9,
        __int16 a10)
{
  unsigned __int16 v10; // bx
  __int64 result; // rax
  int v14; // r14d
  int v15; // r15d
  __int16 v16; // r12
  __int16 v17; // ax
  __int16 *v18; // rcx
  __int16 v19; // ax
  __int16 v20; // ax
  __int16 v21; // ax
  __int16 v22; // ax
  __int16 v23; // ax
  unsigned __int16 *v24; // rcx
  unsigned __int16 v25; // ax
  __int16 v26; // ax
  unsigned __int16 v27; // bx
  unsigned __int16 v28; // ax
  bool v29; // cc
  unsigned int v30; // ecx
  unsigned int v31; // eax
  unsigned int v32; // edx
  _WORD v33[2]; // [rsp+60h] [rbp-91h] BYREF
  _WORD v34[2]; // [rsp+64h] [rbp-8Dh] BYREF
  _WORD v35[2]; // [rsp+68h] [rbp-89h] BYREF
  unsigned __int16 v36; // [rsp+6Ch] [rbp-85h] BYREF
  _WORD v37[2]; // [rsp+70h] [rbp-81h] BYREF
  unsigned __int16 NumGlyphs; // [rsp+74h] [rbp-7Dh]
  int v39; // [rsp+78h] [rbp-79h] BYREF
  __int16 *v40; // [rsp+80h] [rbp-71h]
  __int64 v41; // [rsp+88h] [rbp-69h]
  __int16 *v42; // [rsp+90h] [rbp-61h]
  __int16 *v43; // [rsp+98h] [rbp-59h]
  unsigned __int16 *v44; // [rsp+A0h] [rbp-51h]
  __int16 *v45; // [rsp+A8h] [rbp-49h]
  _OWORD v46[3]; // [rsp+B0h] [rbp-41h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-11h]

  v10 = 0;
  v41 = a9;
  *a2 = 0;
  *a3 = 0;
  *a6 = 0;
  *a4 = 0;
  *a5 = 0;
  *a7 = 0;
  *a8 = 0;
  v45 = a8;
  v42 = a4;
  v40 = a3;
  v43 = a5;
  v44 = a7;
  memset(v46, 0, sizeof(v46));
  v47 = 0;
  v34[0] = 0;
  v35[0] = 0;
  v33[0] = 0;
  v39 = 0;
  NumGlyphs = GetNumGlyphs(a1);
  if ( !NumGlyphs )
    return 1009;
  v14 = TTTableOffset(a1, "loca");
  if ( !v14 )
    return 1035;
  v15 = TTTableOffset(a1, "glyf");
  if ( !v15 )
    return 1031;
  if ( !(unsigned int)GetGeneric(a1, v46, 0) )
    return 1032;
  v16 = WORD1(v47);
  while ( v10 < NumGlyphs )
  {
    result = GetGlyphStats(a1, v10, (unsigned int)v34, (unsigned int)v35, (__int64)v33, v16, v14, v15, (__int64)&v39);
    if ( (_WORD)result )
      return result;
    if ( v39 )
    {
      v17 = v34[0];
      if ( v34[0] < 0 )
      {
        if ( v34[0] != 0xFFFF )
          return 1061;
        v33[0] = 0;
        v37[0] = 0;
        v36 = 0;
        GetCompositeGlyphStats(
          a1,
          v10,
          (unsigned int)v34,
          (unsigned int)v35,
          (__int64)v33,
          (__int64)&v36,
          (__int64)v37,
          v16,
          v14,
          v15,
          v41,
          a10);
        v21 = v34[0];
        if ( (unsigned __int16)*v42 > v34[0] )
          v21 = *v42;
        *v42 = v21;
        v22 = v35[0];
        if ( (unsigned __int16)*v43 > v35[0] )
          v22 = *v43;
        *v43 = v22;
        v23 = v33[0];
        if ( (unsigned __int16)*a6 > v33[0] )
          v23 = *a6;
        v24 = v44;
        *a6 = v23;
        v25 = v36;
        if ( *v24 > v36 )
          v25 = *v24;
        *v24 = v25;
        v26 = v37[0];
        if ( (unsigned __int16)*v45 > v37[0] )
          v26 = *v45;
        *v45 = v26;
      }
      else
      {
        if ( (unsigned __int16)*a2 > v34[0] )
          v17 = *a2;
        v18 = v40;
        *a2 = v17;
        v19 = v35[0];
        if ( (unsigned __int16)*v18 > v35[0] )
          v19 = *v18;
        *v18 = v19;
        v20 = v33[0];
        if ( (unsigned __int16)*a6 > v33[0] )
          v20 = *a6;
        *a6 = v20;
      }
    }
    ++v10;
  }
  v27 = TTTableLength(a1, "prep");
  v28 = TTTableLength(a1, "fpgm");
  v29 = v27 <= v28;
  v30 = v28;
  v31 = (unsigned __int16)*a6;
  v32 = v27;
  if ( v29 )
    v32 = v30;
  if ( v32 > v31 )
    LOWORD(v31) = v32;
  *a6 = v31;
  return 0;
}

```

## disassembly

```asm
0x1800175f4  push    rbp
0x1800175f6  push    rbx
0x1800175f7  push    rsi
0x1800175f8  push    rdi
0x1800175f9  push    r12
0x1800175fb  push    r13
0x1800175fd  push    r14
0x1800175ff  push    r15
0x180017601  lea     rbp, [rsp-7]
0x180017606  sub     rsp, 0F8h
0x18001760d  mov     rax, cs:__security_cookie
0x180017614  xor     rax, rsp
0x180017617  mov     [rbp+3Fh+var_48], rax
0x18001761b  mov     r10, [rbp+3Fh+arg_30]
0x18001761f  xor     ebx, ebx
0x180017621  mov     rax, [rbp+3Fh+arg_40]
0x180017628  xorps   xmm0, xmm0
0x18001762b  mov     rsi, [rbp+3Fh+arg_28]
0x18001762f  mov     r13, rdx
0x180017632  mov     rdx, [rbp+3Fh+arg_20]
0x180017636  mov     rdi, rcx
0x180017639  mov     rcx, [rbp+3Fh+arg_38]
0x180017640  mov     [rbp+3Fh+var_A8], rax
0x180017644  xor     eax, eax
0x180017646  mov     [r13+0], bx
0x18001764b  mov     [r8], bx
0x18001764f  mov     [rsi], bx
0x180017652  mov     [r9], bx
0x180017656  mov     [rdx], bx
0x180017659  mov     [r10], bx
0x18001765d  mov     [rcx], bx
0x180017660  mov     [rbp+3Fh+var_88], rcx
0x180017664  mov     rcx, rdi
0x180017667  mov     [rbp+3Fh+var_A0], r9
0x18001766b  mov     [rbp+3Fh+var_B0], r8
0x18001766f  mov     [rbp+3Fh+var_98], rdx
0x180017673  mov     [rbp+3Fh+var_90], r10
0x180017677  movups  [rbp+3Fh+var_80], xmm0
0x18001767b  mov     [rbp+3Fh+var_50], rax
0x18001767f  movups  [rbp+3Fh+var_70], xmm0
0x180017683  mov     [rsp+130h+var_CC], bx
0x180017688  movups  [rbp+3Fh+var_60], xmm0
0x18001768c  mov     [rsp+130h+var_C8], bx
0x180017691  mov     [rsp+130h+var_D0], bx
0x180017696  mov     [rbp+3Fh+var_B8], ebx
0x180017699  call    GetNumGlyphs
0x18001769e  mov     [rbp+3Fh+var_BC], ax
0x1800176a2  test    ax, ax
0x1800176a5  jnz     short loc_1800176B1
0x1800176a7  mov     eax, 3F1h
0x1800176ac  jmp     loc_1800178C3
0x1800176b1  lea     rdx, aLoca; "loca"
0x1800176b8  mov     rcx, rdi
0x1800176bb  call    TTTableOffset
0x1800176c0  mov     r14d, eax
0x1800176c3  test    eax, eax
0x1800176c5  jnz     short loc_1800176D1
0x1800176c7  mov     eax, 40Bh
0x1800176cc  jmp     loc_1800178C3
0x1800176d1  lea     rdx, aGlyf; "glyf"
0x1800176d8  mov     rcx, rdi
0x1800176db  call    TTTableOffset
0x1800176e0  mov     r15d, eax
0x1800176e3  test    eax, eax
0x1800176e5  jnz     short loc_1800176F1
0x1800176e7  mov     eax, 407h
0x1800176ec  jmp     loc_1800178C3
0x1800176f1  xor     r8d, r8d
0x1800176f4  lea     rdx, [rbp+3Fh+var_80]
0x1800176f8  mov     rcx, rdi
0x1800176fb  call    GetGeneric
0x180017700  test    eax, eax
0x180017702  jnz     short loc_18001770E
0x180017704  mov     eax, 408h
0x180017709  jmp     loc_1800178C3
0x18001770e  movzx   r12d, word ptr [rbp+3Fh+var_50+2]
0x180017713  mov     rcx, rdi
0x180017716  cmp     bx, [rbp+3Fh+var_BC]
0x18001771a  jnb     loc_18001788D
0x180017720  lea     rax, [rbp+3Fh+var_B8]
0x180017724  movzx   edx, bx
0x180017727  mov     [rsp+130h+var_F0], rax
0x18001772c  lea     r9, [rsp+130h+var_C8]
0x180017731  mov     [rsp+130h+var_F8], r15d
0x180017736  lea     rax, [rsp+130h+var_D0]
0x18001773b  mov     dword ptr [rsp+130h+var_100], r14d
0x180017740  lea     r8, [rsp+130h+var_CC]
0x180017745  mov     word ptr [rsp+130h+var_108], r12w
0x18001774b  mov     [rsp+130h+var_110], rax
0x180017750  call    GetGlyphStats
0x180017755  xor     ecx, ecx
0x180017757  test    ax, ax
0x18001775a  jnz     loc_1800178C3
0x180017760  cmp     [rbp+3Fh+var_B8], ecx
0x180017763  jz      loc_18001787E
0x180017769  movzx   eax, [rsp+130h+var_CC]
0x18001776e  test    ax, ax
0x180017771  js      short loc_1800177AD
0x180017773  cmp     [r13+0], ax
0x180017778  jbe     short loc_18001777F
0x18001777a  movzx   eax, word ptr [r13+0]
0x18001777f  mov     rcx, [rbp+3Fh+var_B0]
0x180017783  mov     [r13+0], ax
0x180017788  movzx   eax, [rsp+130h+var_C8]
0x18001778d  cmp     [rcx], ax
0x180017790  jbe     short loc_180017795
0x180017792  movzx   eax, word ptr [rcx]
0x180017795  mov     [rcx], ax
0x180017798  movzx   eax, [rsp+130h+var_D0]
0x18001779d  cmp     [rsi], ax
0x1800177a0  jbe     short loc_1800177A5
0x1800177a2  movzx   eax, word ptr [rsi]
0x1800177a5  mov     [rsi], ax
0x1800177a8  jmp     loc_18001787E
0x1800177ad  cmp     ax, 0FFFFh
0x1800177b1  jnz     loc_180017886
0x1800177b7  movzx   eax, [rbp+3Fh+arg_48]
0x1800177be  lea     r9, [rsp+130h+var_C8]
0x1800177c3  mov     [rsp+130h+var_D8], ax
0x1800177c8  lea     r8, [rsp+130h+var_CC]
0x1800177cd  mov     rax, [rbp+3Fh+var_A8]
0x1800177d1  movzx   edx, bx
0x1800177d4  mov     [rsp+130h+var_E0], rax
0x1800177d9  lea     rax, [rsp+130h+var_C0]
0x1800177de  mov     [rsp+130h+var_E8], r15d
0x1800177e3  mov     dword ptr [rsp+130h+var_F0], r14d
0x1800177e8  mov     word ptr [rsp+130h+var_F8], r12w
0x1800177ee  mov     [rsp+130h+var_100], rax
0x1800177f3  lea     rax, [rsp+130h+var_C4]
0x1800177f8  mov     [rsp+130h+var_108], rax
0x1800177fd  lea     rax, [rsp+130h+var_D0]
0x180017802  mov     [rsp+130h+var_D0], cx
0x180017807  mov     [rsp+130h+var_C0], cx
0x18001780c  mov     [rsp+130h+var_C4], cx
0x180017811  mov     rcx, rdi
0x180017814  mov     [rsp+130h+var_110], rax
0x180017819  call    GetCompositeGlyphStats
0x18001781e  mov     rcx, [rbp+3Fh+var_A0]
0x180017822  movzx   eax, [rsp+130h+var_CC]
0x180017827  cmp     [rcx], ax
0x18001782a  jbe     short loc_18001782F
0x18001782c  movzx   eax, word ptr [rcx]
0x18001782f  mov     [rcx], ax
0x180017832  mov     rcx, [rbp+3Fh+var_98]
0x180017836  movzx   eax, [rsp+130h+var_C8]
0x18001783b  cmp     [rcx], ax
0x18001783e  jbe     short loc_180017843
0x180017840  movzx   eax, word ptr [rcx]
0x180017843  mov     [rcx], ax
0x180017846  movzx   eax, [rsp+130h+var_D0]
0x18001784b  cmp     [rsi], ax
0x18001784e  jbe     short loc_180017853
0x180017850  movzx   eax, word ptr [rsi]
0x180017853  mov     rcx, [rbp+3Fh+var_90]
0x180017857  mov     [rsi], ax
0x18001785a  movzx   eax, [rsp+130h+var_C4]
0x18001785f  cmp     [rcx], ax
0x180017862  jbe     short loc_180017867
0x180017864  movzx   eax, word ptr [rcx]
0x180017867  mov     [rcx], ax
0x18001786a  mov     rcx, [rbp+3Fh+var_88]
0x18001786e  movzx   eax, [rsp+130h+var_C0]
0x180017873  cmp     [rcx], ax
0x180017876  jbe     short loc_18001787B
0x180017878  movzx   eax, word ptr [rcx]
0x18001787b  mov     [rcx], ax
0x18001787e  inc     bx
0x180017881  jmp     loc_180017713
0x180017886  mov     eax, 425h
0x18001788b  jmp     short loc_1800178C3
0x18001788d  lea     rdx, aPrep; "prep"
0x180017894  call    TTTableLength
0x180017899  lea     rdx, aFpgm; "fpgm"
0x1800178a0  mov     rcx, rdi
0x1800178a3  mov     ebx, eax
0x1800178a5  call    TTTableLength
0x1800178aa  cmp     bx, ax
0x1800178ad  movzx   ecx, ax
0x1800178b0  movzx   eax, word ptr [rsi]
0x1800178b3  movzx   edx, bx
0x1800178b6  cmovbe  edx, ecx
0x1800178b9  cmp     edx, eax
0x1800178bb  cmova   eax, edx
0x1800178be  mov     [rsi], ax
0x1800178c1  xor     eax, eax
0x1800178c3  mov     rcx, [rbp+3Fh+var_48]
0x1800178c7  xor     rcx, rsp; StackCookie
0x1800178ca  call    __security_check_cookie
0x1800178cf  add     rsp, 0F8h
0x1800178d6  pop     r15
0x1800178d8  pop     r14
0x1800178da  pop     r13
0x1800178dc  pop     r12
0x1800178de  pop     rdi
0x1800178df  pop     rsi
0x1800178e0  pop     rbx
0x1800178e1  pop     rbp
0x1800178e2  retn
```
