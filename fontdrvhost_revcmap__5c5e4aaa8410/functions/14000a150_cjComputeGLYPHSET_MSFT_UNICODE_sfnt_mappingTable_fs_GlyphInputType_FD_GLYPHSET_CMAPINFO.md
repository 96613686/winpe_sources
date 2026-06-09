# cjComputeGLYPHSET_MSFT_UNICODE(sfnt_mappingTable *,fs_GlyphInputType *,_FD_GLYPHSET *,_CMAPINFO *)

- ea: `0x14000a150`
- end: `0x14000a532`
- name: `?cjComputeGLYPHSET_MSFT_UNICODE@@YAKPEAUsfnt_mappingTable@@PEAUfs_GlyphInputType@@PEAU_FD_GLYPHSET@@PEAU_CMAPINFO@@@Z`
- size: `994`
- prototype: `unsigned int __fastcall(struct sfnt_mappingTable *, struct fs_GlyphInputType *, struct _FD_GLYPHSET *, struct _CMAPINFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a018`

## callees

- `0x14000a150`
- `0x14002ea60`
- `0x140075de0`
- `0x14007680c`

## pseudocode

```c
__int64 __fastcall cjComputeGLYPHSET_MSFT_UNICODE(
        struct sfnt_mappingTable *a1,
        struct fs_GlyphInputType *a2,
        struct _FD_GLYPHSET *a3,
        struct _CMAPINFO *a4)
{
  struct _FD_GLYPHSET *v4; // rdi
  struct _CMAPINFO *v6; // r14
  __int16 v7; // r9
  unsigned int v8; // edx
  unsigned int v9; // esi
  __int64 result; // rax
  int v11; // r15d
  WCRUN *v12; // r11
  WCRUN *v13; // r8
  __int64 v14; // r13
  WCRUN *awcrun; // rbp
  WCRUN *v16; // rbx
  __int16 v17; // bp
  WCRUN *v18; // rsi
  int v19; // eax
  __int64 v20; // rcx
  unsigned __int16 v21; // di
  unsigned __int16 v22; // r14
  int v23; // r8d
  __int64 cGlyphs; // rax
  __int64 v25; // rax
  ULONG v26; // ecx
  int v27; // [rsp+44h] [rbp-2B4h]
  int v28; // [rsp+48h] [rbp-2B0h]
  int v29; // [rsp+4Ch] [rbp-2ACh]
  unsigned int v30; // [rsp+50h] [rbp-2A8h]
  WCRUN *v31; // [rsp+58h] [rbp-2A0h]
  int v32; // [rsp+60h] [rbp-298h]
  WCRUN *v34; // [rsp+70h] [rbp-288h]
  char *v35; // [rsp+78h] [rbp-280h]
  char *v36; // [rsp+80h] [rbp-278h]
  WCRUN *v38; // [rsp+90h] [rbp-268h]
  _BYTE v39[256]; // [rsp+A0h] [rbp-258h] BYREF
  _BYTE v40[256]; // [rsp+1A0h] [rbp-158h] BYREF

  v4 = a3;
  v32 = (int)a2;
  v6 = a4;
  memset_0(v40, 0, sizeof(v40));
  v7 = (*(_DWORD *)v6 >> 2) & 1;
  v8 = ((*(_DWORD *)v6 >> 2) & 1) + *((_DWORD *)v6 + 1);
  v27 = (*(_DWORD *)v6 >> 2) & 1;
  v9 = 4 * (*((_DWORD *)v6 + 3) + 4 + 4 * v8);
  v30 = v9;
  if ( !v4 )
    return v9;
  v11 = *(_DWORD *)v6 & 3;
  v12 = 0;
  v13 = 0;
  v36 = (char *)a1 + 14;
  v14 = (unsigned __int16)(*((unsigned __int8 *)a1 + 6) << 7) | (unsigned __int8)(*((_BYTE *)a1 + 7) >> 1);
  v34 = 0;
  v31 = 0;
  v29 = v11;
  v35 = (char *)a1 + 2 * v14 + 16;
  if ( *(_WORD *)&v35[2 * v14 - 2] == 0xFFFF && (unsigned int)v14 > 1 )
    LOWORD(v14) = v14 - 1;
  awcrun = v4->awcrun;
  v38 = v4->awcrun;
  v16 = v4->awcrun;
  if ( (_WORD)v14 )
  {
    v17 = 0;
    v18 = &v4->awcrun[v8];
    LOWORD(v19) = 0;
    v28 = 0;
    while ( 1 )
    {
      v20 = 2LL * (unsigned __int16)v19;
      v21 = _byteswap_ushort(*(_WORD *)&v35[v20]);
      v22 = _byteswap_ushort(*(_WORD *)&v36[v20]);
      if ( v11 == 3 )
      {
        if ( (unsigned __int16)v17 < 0xB7u && v21 > 0xB7u )
        {
          v16->phg = (HGLYPH *)&v18->wcLow;
          v34 = v16;
          *(_DWORD *)&v16->wcLow = 65719;
          ++v16;
          v18 = (WCRUN *)((char *)v18 + 4);
        }
        if ( v21 <= 0x2219u )
        {
          if ( v22 >= 0x2219u )
            v13 = v16;
          v31 = v13;
        }
      }
      v16->wcLow = v21;
      v16->phg = (HGLYPH *)&v18->wcLow;
      v16->cGlyphs = v22 - v21 + 1;
      if ( !v7 || v21 > 0x5Cu )
        break;
      if ( v22 < 0x5Cu )
      {
        v17 = v22;
        goto LABEL_40;
      }
      memset_0(v39, 0, sizeof(v39));
      if ( v21 == 92 )
      {
        v16->cGlyphs = v22 - v21;
        v21 = 93;
        v17 = v22;
        v16->wcLow = 93;
      }
      else if ( v22 == 92 )
      {
        v17 = 91;
        v16->cGlyphs = 92 - v21;
      }
      else
      {
        v23 = (unsigned __int16)(92 - v21);
        v16->cGlyphs = v23;
        if ( (unsigned int)fs_WinNTGetGlyphIDs(v32, (unsigned int)v39, v23, v21, 0, 0, (__int64)v18) )
          return 0;
        cGlyphs = v16->cGlyphs;
        ++v16;
        v17 = v22;
        v18 = (WCRUN *)((char *)v18 + 4 * cGlyphs);
        v21 = 93;
        v16->wcLow = 93;
        v16->phg = (HGLYPH *)&v18->wcLow;
        v16->cGlyphs = v22 - 92;
      }
      v6 = a4;
      v7 = 0;
      LOWORD(v27) = 0;
      --*((_DWORD *)a4 + 3);
      if ( v16->cGlyphs )
        goto LABEL_28;
LABEL_31:
      HIWORD(v19) = HIWORD(v28);
      v13 = v31;
      LOWORD(v19) = v28 + 1;
      v11 = v29;
      v28 = v19;
      if ( (unsigned __int16)v19 >= (unsigned __int16)v14 )
      {
        v4 = a3;
        v12 = v34;
        v9 = v30;
        awcrun = v38;
        goto LABEL_33;
      }
    }
    v17 = v22;
LABEL_28:
    if ( v21 == 0xFFFF )
    {
      *(_DWORD *)&v18->wcLow = 0;
    }
    else
    {
LABEL_40:
      if ( (unsigned int)fs_WinNTGetGlyphIDs(v32, (unsigned int)v40, v16->cGlyphs, v21, 0, 0, (__int64)v18) )
        return 0;
    }
    v25 = v16->cGlyphs;
    ++v16;
    v7 = v27;
    v6 = a4;
    v18 = (WCRUN *)((char *)v18 + 4 * v25);
    goto LABEL_31;
  }
LABEL_33:
  if ( v11 == 3 && v12 )
  {
    if ( v13 )
      v12->phg[183LL - v12->wcLow] = v13->phg[8729LL - v13->wcLow];
  }
  v4->cjThis = v9;
  result = v9;
  v4->flAccel = 4;
  v26 = *((_DWORD *)v6 + 3);
  v4->cRuns = v16 - awcrun;
  v4->cGlyphsSupported = v26;
  return result;
}

```

## disassembly

```asm
0x14000a150  push    rbx
0x14000a152  push    rsi
0x14000a153  push    rdi
0x14000a154  push    r14
0x14000a156  push    r15
0x14000a158  sub     rsp, 2D0h
0x14000a15f  mov     rax, cs:__security_cookie
0x14000a166  xor     rax, rsp
0x14000a169  mov     [rsp+2F8h+var_58], rax
0x14000a171  mov     rdi, r8
0x14000a174  mov     [rsp+2F8h+var_270], r8
0x14000a17c  mov     [rsp+2F8h+var_298], rdx
0x14000a181  mov     rbx, rcx
0x14000a184  xor     edx, edx; Val
0x14000a186  mov     [rsp+2F8h+var_290], r9
0x14000a18b  mov     r8d, 100h; Size
0x14000a191  lea     rcx, [rsp+2F8h+var_158]; void *
0x14000a199  mov     r14, r9
0x14000a19c  call    memset_0
0x14000a1a1  mov     r15d, [r14]
0x14000a1a4  mov     eax, r15d
0x14000a1a7  mov     edx, [r14+4]
0x14000a1ab  mov     esi, [r14+0Ch]
0x14000a1af  add     esi, 4
0x14000a1b2  shr     eax, 2
0x14000a1b5  and     ax, 1
0x14000a1b9  movzx   r9d, ax
0x14000a1bd  add     edx, r9d
0x14000a1c0  mov     [rsp+2F8h+var_2B4], r9d
0x14000a1c5  lea     esi, [rsi+rdx*4]
0x14000a1c8  shl     esi, 2
0x14000a1cb  mov     [rsp+2F8h+var_2A8], esi
0x14000a1cf  test    rdi, rdi
0x14000a1d2  jnz     short loc_14000A1DB
0x14000a1d4  mov     eax, esi
0x14000a1d6  jmp     loc_14000A4D2
0x14000a1db  movzx   eax, byte ptr [rbx+7]
0x14000a1df  xor     r10d, r10d
0x14000a1e2  shr     al, 1
0x14000a1e4  and     r15d, 3
0x14000a1e8  movzx   ecx, al
0x14000a1eb  mov     r11d, r10d
0x14000a1ee  movzx   eax, byte ptr [rbx+6]
0x14000a1f2  mov     r8d, r10d
0x14000a1f5  shl     ax, 7
0x14000a1f9  or      cx, ax
0x14000a1fc  mov     [rsp+2F8h+var_30], rbp
0x14000a204  lea     rax, [rbx+0Eh]
0x14000a208  mov     [rsp+2F8h+var_38], r12
0x14000a210  mov     [rsp+2F8h+var_278], rax
0x14000a218  lea     rax, [rbx+10h]
0x14000a21c  mov     [rsp+2F8h+var_40], r13
0x14000a224  movzx   r13d, cx
0x14000a228  mov     ecx, 0FFFFh
0x14000a22d  mov     [rsp+2F8h+var_288], r10
0x14000a232  mov     [rsp+2F8h+var_2A0], r10
0x14000a237  mov     [rsp+2F8h+var_2AC], r15d
0x14000a23c  lea     rax, [rax+r13*2]
0x14000a240  mov     [rsp+2F8h+var_280], rax
0x14000a245  cmp     [rax+r13*2-2], cx
0x14000a24b  jnz     short loc_14000A257
0x14000a24d  cmp     r13d, 1
0x14000a251  jbe     short loc_14000A257
0x14000a253  dec     r13w
0x14000a257  lea     rbp, [rdi+10h]
0x14000a25b  cmp     r10w, r13w
0x14000a25f  mov     [rsp+2F8h+var_268], rbp
0x14000a267  mov     rbx, rbp
0x14000a26a  mov     r12d, 0B7h
0x14000a270  mov     r10d, 2219h
0x14000a276  jnb     loc_14000A470
0x14000a27c  mov     esi, edx
0x14000a27e  xor     ebp, ebp
0x14000a280  inc     rsi
0x14000a283  shl     rsi, 4
0x14000a287  add     rsi, rdi
0x14000a28a  xor     eax, eax
0x14000a28c  mov     [rsp+2F8h+var_2B0], eax
0x14000a290  movzx   eax, ax
0x14000a293  lea     rcx, [rax+rax]
0x14000a297  mov     rax, [rsp+2F8h+var_280]
0x14000a29c  movzx   edi, byte ptr [rcx+rax+1]
0x14000a2a1  movzx   eax, byte ptr [rcx+rax]
0x14000a2a5  shl     ax, 8
0x14000a2a9  or      di, ax
0x14000a2ac  mov     rax, [rsp+2F8h+var_278]
0x14000a2b4  movzx   r14d, byte ptr [rcx+rax+1]
0x14000a2ba  movzx   eax, byte ptr [rcx+rax]
0x14000a2be  shl     ax, 8
0x14000a2c2  or      r14w, ax
0x14000a2c6  mov     word ptr [rsp+2F8h+var_2B8], r14w
0x14000a2cc  cmp     r15d, 3
0x14000a2d0  jnz     short loc_14000A308
0x14000a2d2  cmp     bp, r12w
0x14000a2d6  jnb     short loc_14000A2F5
0x14000a2d8  cmp     di, r12w
0x14000a2dc  jbe     short loc_14000A2F5
0x14000a2de  mov     [rbx+8], rsi
0x14000a2e2  mov     [rsp+2F8h+var_288], rbx
0x14000a2e7  mov     dword ptr [rbx], 100B7h
0x14000a2ed  add     rbx, 10h
0x14000a2f1  add     rsi, 4
0x14000a2f5  cmp     di, r10w
0x14000a2f9  ja      short loc_14000A308
0x14000a2fb  cmp     r14w, r10w
0x14000a2ff  cmovnb  r8, rbx
0x14000a303  mov     [rsp+2F8h+var_2A0], r8
0x14000a308  movzx   r15d, r14w
0x14000a30c  mov     [rbx], di
0x14000a30f  sub     r15w, di
0x14000a313  mov     [rbx+8], rsi
0x14000a317  lea     ebp, [r15+1]
0x14000a31b  mov     [rbx+2], bp
0x14000a31f  test    r9w, r9w
0x14000a323  jz      loc_14000A404
0x14000a329  cmp     di, 5Ch ; '\'
0x14000a32d  ja      loc_14000A404
0x14000a333  cmp     r14w, 5Ch ; '\'
0x14000a338  jb      loc_14000A4F1
0x14000a33e  xor     edx, edx; Val
0x14000a340  lea     rcx, [rsp+2F8h+var_258]; void *
0x14000a348  mov     r8d, 100h; Size
0x14000a34e  call    memset_0
0x14000a353  cmp     di, 5Ch ; '\'
0x14000a357  jnz     short loc_14000A370
0x14000a359  dec     bp
0x14000a35c  mov     ecx, 5Dh ; ']'
0x14000a361  mov     [rbx+2], bp
0x14000a365  mov     edi, ecx
0x14000a367  mov     ebp, [rsp+2F8h+var_2B8]
0x14000a36b  mov     [rbx], cx
0x14000a36e  jmp     short loc_14000A3E8
0x14000a370  cmp     r14w, 5Ch ; '\'
0x14000a375  jnz     short loc_14000A383
0x14000a377  mov     ebp, 5Bh ; '['
0x14000a37c  mov     [rbx+2], r15w
0x14000a381  jmp     short loc_14000A3E8
0x14000a383  mov     rcx, [rsp+2F8h+var_298]
0x14000a388  lea     rdx, [rsp+2F8h+var_258]
0x14000a390  xor     r10d, r10d
0x14000a393  mov     [rsp+2F8h+var_2C8], rsi
0x14000a398  mov     r8d, 5Ch ; '\'
0x14000a39e  mov     [rsp+2F8h+var_2D0], r10
0x14000a3a3  sub     r8w, di
0x14000a3a7  mov     [rsp+2F8h+var_2D8], r10d
0x14000a3ac  movzx   r9d, di
0x14000a3b0  mov     [rbx+2], r8w
0x14000a3b5  call    fs_WinNTGetGlyphIDs
0x14000a3ba  test    eax, eax
0x14000a3bc  jnz     loc_14000A52E
0x14000a3c2  movzx   eax, word ptr [rbx+2]
0x14000a3c6  add     rbx, 10h
0x14000a3ca  mov     ebp, [rsp+2F8h+var_2B8]
0x14000a3ce  lea     rsi, [rsi+rax*4]
0x14000a3d2  mov     eax, 5Dh ; ']'
0x14000a3d7  movzx   edi, ax
0x14000a3da  mov     [rbx], ax
0x14000a3dd  lea     eax, [rbp-5Ch]
0x14000a3e0  mov     [rbx+8], rsi
0x14000a3e4  mov     [rbx+2], ax
0x14000a3e8  mov     r14, [rsp+2F8h+var_290]
0x14000a3ed  xor     eax, eax
0x14000a3ef  movzx   r9d, ax
0x14000a3f3  mov     [rsp+2F8h+var_2B4], r9d
0x14000a3f8  dec     dword ptr [r14+0Ch]
0x14000a3fc  cmp     ax, [rbx+2]
0x14000a400  jz      short loc_14000A432
0x14000a402  jmp     short loc_14000A408
0x14000a404  mov     ebp, [rsp+2F8h+var_2B8]
0x14000a408  mov     eax, 0FFFFh
0x14000a40d  cmp     di, ax
0x14000a410  jb      loc_14000A4F5
0x14000a416  mov     dword ptr [rsi], 0
0x14000a41c  movzx   eax, word ptr [rbx+2]
0x14000a420  add     rbx, 10h
0x14000a424  mov     r9d, [rsp+2F8h+var_2B4]
0x14000a429  mov     r14, [rsp+2F8h+var_290]
0x14000a42e  lea     rsi, [rsi+rax*4]
0x14000a432  mov     eax, [rsp+2F8h+var_2B0]
0x14000a436  mov     r10d, 2219h
0x14000a43c  mov     r8, [rsp+2F8h+var_2A0]
0x14000a441  inc     ax
0x14000a444  mov     r15d, [rsp+2F8h+var_2AC]
0x14000a449  mov     [rsp+2F8h+var_2B0], eax
0x14000a44d  cmp     ax, r13w
0x14000a451  jb      loc_14000A290
0x14000a457  mov     rdi, [rsp+2F8h+var_270]
0x14000a45f  mov     r11, [rsp+2F8h+var_288]
0x14000a464  mov     esi, [rsp+2F8h+var_2A8]
0x14000a468  mov     rbp, [rsp+2F8h+var_268]
0x14000a470  cmp     r15d, 3
0x14000a474  jnz     short loc_14000A49E
0x14000a476  test    r11, r11
0x14000a479  jz      short loc_14000A49E
0x14000a47b  test    r8, r8
0x14000a47e  jz      short loc_14000A49E
0x14000a480  movzx   eax, word ptr [r8]
0x14000a484  mov     rcx, [r8+8]
0x14000a488  sub     r10, rax
0x14000a48b  movzx   eax, word ptr [r11]
0x14000a48f  mov     rdx, [r11+8]
0x14000a493  sub     r12, rax
0x14000a496  mov     ecx, [rcx+r10*4]
0x14000a49a  mov     [rdx+r12*4], ecx
0x14000a49e  sub     rbx, rbp
0x14000a4a1  mov     [rdi], esi
0x14000a4a3  sar     rbx, 4
0x14000a4a7  mov     eax, esi
0x14000a4a9  mov     dword ptr [rdi+4], 4
0x14000a4b0  mov     ecx, [r14+0Ch]
0x14000a4b4  mov     [rdi+0Ch], ebx
0x14000a4b7  mov     [rdi+8], ecx
0x14000a4ba  mov     r12, [rsp+2F8h+var_38]
0x14000a4c2  mov     rbp, [rsp+2F8h+var_30]
0x14000a4ca  mov     r13, [rsp+2F8h+var_40]
0x14000a4d2  mov     rcx, [rsp+2F8h+var_58]
0x14000a4da  xor     rcx, rsp; StackCookie
0x14000a4dd  call    __security_check_cookie
0x14000a4e2  add     rsp, 2D0h
0x14000a4e9  pop     r15
0x14000a4eb  pop     r14
0x14000a4ed  pop     rdi
0x14000a4ee  pop     rsi
0x14000a4ef  pop     rbx
0x14000a4f0  retn
0x14000a4f1  mov     ebp, [rsp+2F8h+var_2B8]
0x14000a4f5  movzx   r8d, word ptr [rbx+2]
0x14000a4fa  lea     rdx, [rsp+2F8h+var_158]
0x14000a502  mov     rcx, [rsp+2F8h+var_298]
0x14000a507  movzx   r9d, di
0x14000a50b  mov     [rsp+2F8h+var_2C8], rsi
0x14000a510  mov     [rsp+2F8h+var_2D0], 0
0x14000a519  mov     [rsp+2F8h+var_2D8], 0
0x14000a521  call    fs_WinNTGetGlyphIDs
0x14000a526  test    eax, eax
0x14000a528  jz      loc_14000A41C
0x14000a52e  xor     eax, eax
0x14000a530  jmp     short loc_14000A4BA
```
