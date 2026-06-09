# cjComputeGLYPHSET_OLDBIDI(fs_GlyphInputType *,_FD_GLYPHSET * *,ulong)

- ea: `0x140004d00`
- end: `0x140004ff0`
- name: `?cjComputeGLYPHSET_OLDBIDI@@YAKPEAUfs_GlyphInputType@@PEAPEAU_FD_GLYPHSET@@K@Z`
- size: `752`
- prototype: `unsigned int __fastcall(struct fs_GlyphInputType *, struct _FD_GLYPHSET **, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a018`

## callees

- `0x140004ab4`
- `0x140004d00`
- `0x140013310`
- `0x140075de0`
- `0x14007680c`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140004f23`
- `KERNEL32!GlobalFree` at `0x140004f23`
- `KERNEL32!GlobalAlloc` at `0x140004db9`
- `KERNEL32!GlobalAlloc` at `0x140004db9`

## pseudocode

```c
__int64 __fastcall cjComputeGLYPHSET_OLDBIDI(struct fs_GlyphInputType *a1, struct _FD_GLYPHSET **a2, int a3)
{
  __int16 v3; // bx
  unsigned __int16 v5; // r13
  int v6; // eax
  __int64 *v7; // rcx
  int v8; // esi
  int v9; // r15d
  ULONG cjThis; // edi
  __int64 *v11; // r14
  __int64 v12; // rax
  struct _FD_GLYPHSET *v13; // rax
  struct _FD_GLYPHSET *v14; // rbx
  __int64 v15; // r12
  HGLYPH *v16; // rdi
  int i; // esi
  __int64 v18; // rcx
  int j; // ecx
  __int64 v20; // rax
  const struct sfac_ClientRec *v21; // rax
  unsigned __int16 v22; // dx
  const unsigned __int16 *v23; // r9
  unsigned __int16 v24; // r11
  WCHAR v25; // r11
  int v26; // esi
  const struct sfac_ClientRec *v27; // rax
  unsigned __int16 v28; // dx
  const unsigned __int16 *v29; // r9
  __int16 v30; // r11
  __int64 v32; // rax
  HGLYPH *v33; // rdx
  unsigned __int16 v34[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+34h] [rbp-CCh]
  SIZE_T v36; // [rsp+38h] [rbp-C8h] BYREF
  int v37; // [rsp+40h] [rbp-C0h] BYREF
  struct fs_GlyphInputType *v38; // [rsp+48h] [rbp-B8h]
  __int64 v39; // [rsp+50h] [rbp-B0h]
  HGLYPH *v40; // [rsp+58h] [rbp-A8h]
  struct _FD_GLYPHSET **v41; // [rsp+60h] [rbp-A0h]
  _BYTE v42[256]; // [rsp+70h] [rbp-90h] BYREF

  v3 = a3;
  v41 = a2;
  v38 = a1;
  v35 = a3;
  v34[0] = 0;
  v5 = 0;
  memset_0(v42, 0, sizeof(v42));
  *a2 = 0;
  v6 = v3 & 0xFF00;
  switch ( v6 )
  {
    case 61440:
      v7 = (__int64 *)a0123456789;
      break;
    case 61696:
      v7 = (__int64 *)" ";
      break;
    case 61952:
      v7 = qword_1400A4AE0;
      break;
    default:
      return 0;
  }
  v8 = 0;
  v9 = 0;
  cjThis = 0;
  v11 = v7;
  while ( *((_WORD *)v7 + 1) )
  {
    v12 = *((unsigned __int16 *)v7 + 1);
    ++v9;
    v8 += v12;
    v7 = (__int64 *)((char *)v7 + 2 * v12 + 4);
  }
  v36 = (unsigned int)(4 * (v8 + 256 + 4 * (v9 + 2)));
  v13 = (struct _FD_GLYPHSET *)GlobalAlloc(0, v36);
  v14 = v13;
  if ( v13 )
  {
    v13->cjThis = v36;
    v13->cGlyphsSupported = v8 + 256;
    v13->cRuns = v9 + 1;
    v15 = v9;
    v13->flAccel = 4;
    v16 = (ULONG *)((char *)&v13[1].cjThis + v15 * 16);
    v40 = &v16[v8];
    memset_0(v40, 0, 0x400u);
    for ( i = 0; i < v9; ++i )
    {
      v18 = i;
      v14->awcrun[v18].wcLow = *(_WORD *)v11;
      v14->awcrun[v18].cGlyphs = *((_WORD *)v11 + 1);
      v14->awcrun[v18].phg = v16;
      for ( j = 0; ; j = v36 + 1 )
      {
        v20 = *((unsigned __int16 *)v11 + 1);
        LODWORD(v36) = j;
        if ( j >= (int)v20 )
          break;
        v39 = j;
        v37 = 0;
        v21 = (const struct sfac_ClientRec *)fs_SetUpKey(v38, v42, 2, &v37);
        if ( v21 )
        {
          if ( (unsigned int)sfac_GetMultiGlyphIDs(v21, v22, v24, v23, v34) )
            goto LABEL_19;
          v5 = v34[0];
        }
        else if ( v37 )
        {
          goto LABEL_19;
        }
        v32 = v39;
        v33 = v40;
        *v16++ = v5;
        v33[*((unsigned __int16 *)v11 + v32 + 2)] = v5;
      }
      v11 = (__int64 *)((char *)v11 + 2 * v20 + 4);
    }
    v25 = v35;
    v14->awcrun[v15].cGlyphs = 256;
    v26 = 0;
    v14->awcrun[v15].wcLow = v25;
    v14->awcrun[v15].phg = v16;
    while ( v26 < 256 )
    {
      if ( !*v16 )
      {
        LODWORD(v36) = 0;
        v27 = (const struct sfac_ClientRec *)fs_SetUpKey(v38, v42, 2, &v36);
        if ( v27 )
        {
          if ( (unsigned int)sfac_GetMultiGlyphIDs(v27, v28, v30 + (unsigned __int16)v26, v29, v34) )
            goto LABEL_19;
          v5 = v34[0];
        }
        else if ( (_DWORD)v36 )
        {
LABEL_19:
          GlobalFree(v14);
          return 0;
        }
        *v16 = v5;
      }
      ++v16;
      ++v26;
    }
    cjThis = v14->cjThis;
    *v41 = v14;
  }
  return cjThis;
}

```

## disassembly

```asm
0x140004d00  mov     [rsp-8+arg_18], rbx
0x140004d05  push    rbp
0x140004d06  push    rsi
0x140004d07  push    rdi
0x140004d08  push    r12
0x140004d0a  push    r13
0x140004d0c  push    r14
0x140004d0e  push    r15
0x140004d10  lea     rbp, [rsp-80h]
0x140004d15  sub     rsp, 180h
0x140004d1c  mov     rax, cs:__security_cookie
0x140004d23  xor     rax, rsp
0x140004d26  mov     [rbp+0B0h+var_40], rax
0x140004d2a  mov     ebx, r8d
0x140004d2d  mov     [rsp+1B0h+var_150], rdx
0x140004d32  mov     rdi, rdx
0x140004d35  mov     [rsp+1B0h+var_168], rcx
0x140004d3a  xor     r12d, r12d
0x140004d3d  mov     [rsp+1B0h+var_17C], ebx
0x140004d41  xor     edx, edx; Val
0x140004d43  mov     [rsp+1B0h+var_180], r12w
0x140004d49  mov     r8d, 100h; Size
0x140004d4f  lea     rcx, [rsp+1B0h+var_140]; void *
0x140004d54  mov     r13d, r12d
0x140004d57  call    memset_0
0x140004d5c  mov     eax, ebx
0x140004d5e  mov     [rdi], r12
0x140004d61  and     eax, 0FF00h
0x140004d66  cmp     eax, 0F000h
0x140004d6b  jnz     loc_140004FC6
0x140004d71  lea     rcx, a0123456789; " ! !\"#$%&'()*+,-./0123456789:;<=>?@["
0x140004d78  mov     esi, r12d
0x140004d7b  mov     r15d, r12d
0x140004d7e  mov     edi, r12d
0x140004d81  mov     r14, rcx
0x140004d84  jmp     short loc_140004D97
0x140004d86  movzx   eax, word ptr [rcx+2]
0x140004d8a  inc     r15d
0x140004d8d  add     esi, eax
0x140004d8f  lea     rcx, [rcx+rax*2]
0x140004d93  lea     rcx, [rcx+4]
0x140004d97  cmp     [rcx+2], r12w
0x140004d9c  jnz     short loc_140004D86
0x140004d9e  lea     eax, [r15+2]
0x140004da2  xor     ecx, ecx; uFlags
0x140004da4  lea     r12d, [rsi+100h]
0x140004dab  lea     eax, [r12+rax*4]
0x140004daf  shl     eax, 2
0x140004db2  mov     edx, eax; dwBytes
0x140004db4  mov     [rsp+1B0h+var_178], rax
0x140004db9  call    cs:__imp_GlobalAlloc
0x140004dbf  mov     rbx, rax
0x140004dc2  test    rax, rax
0x140004dc5  jz      loc_140004FBF
0x140004dcb  mov     rax, [rsp+1B0h+var_178]
0x140004dd0  xor     edx, edx; Val
0x140004dd2  mov     [rbx], eax
0x140004dd4  mov     r8d, 400h; Size
0x140004dda  mov     [rbx+8], r12d
0x140004dde  lea     eax, [r15+1]
0x140004de2  mov     [rbx+0Ch], eax
0x140004de5  movsxd  r12, r15d
0x140004de8  shl     r12, 4
0x140004dec  movsxd  rax, esi
0x140004def  mov     dword ptr [rbx+4], 4
0x140004df6  lea     rdi, [r12+20h]
0x140004dfb  add     rdi, rbx
0x140004dfe  lea     rax, [rdi+rax*4]
0x140004e02  mov     rcx, rax; void *
0x140004e05  mov     [rsp+1B0h+var_158], rax
0x140004e0a  call    memset_0
0x140004e0f  xor     esi, esi
0x140004e11  cmp     esi, r15d
0x140004e14  jge     loc_140004EAF
0x140004e1a  movzx   eax, word ptr [r14]
0x140004e1e  movsxd  rcx, esi
0x140004e21  add     rcx, rcx
0x140004e24  mov     [rbx+rcx*8+10h], ax
0x140004e29  movzx   eax, word ptr [r14+2]
0x140004e2e  mov     [rbx+rcx*8+12h], ax
0x140004e33  mov     [rbx+rcx*8+18h], rdi
0x140004e38  xor     ecx, ecx
0x140004e3a  movzx   eax, word ptr [r14+2]
0x140004e3f  mov     dword ptr [rsp+1B0h+var_178], ecx
0x140004e43  cmp     ecx, eax
0x140004e45  jge     loc_140004F77
0x140004e4b  movzx   r11d, word ptr [rsp+1B0h+var_17C]
0x140004e51  lea     r9, [rsp+1B0h+var_170]
0x140004e56  movsxd  rcx, ecx
0x140004e59  lea     rdx, [rsp+1B0h+var_140]
0x140004e5e  mov     [rsp+1B0h+var_160], rcx
0x140004e63  mov     r8d, 2
0x140004e69  mov     [rsp+1B0h+var_170], 0
0x140004e71  add     r11w, [r14+rcx*2+4]
0x140004e77  mov     rcx, [rsp+1B0h+var_168]
0x140004e7c  call    fs_SetUpKey
0x140004e81  test    rax, rax
0x140004e84  jz      loc_140004F86
0x140004e8a  lea     rcx, [rsp+1B0h+var_180]
0x140004e8f  movzx   r8d, r11w; unsigned __int16
0x140004e93  mov     [rsp+1B0h+var_190], rcx; unsigned __int16 *
0x140004e98  mov     rcx, rax; struct sfac_ClientRec *
0x140004e9b  call    ?sfac_GetMultiGlyphIDs@@YAHPEBUsfac_ClientRec@@GGPEBGPEAG@Z; sfac_GetMultiGlyphIDs(sfac_ClientRec const *,ushort,ushort,ushort const *,ushort *)
0x140004ea0  test    eax, eax
0x140004ea2  jnz     short loc_140004F20
0x140004ea4  movzx   r13d, [rsp+1B0h+var_180]
0x140004eaa  jmp     loc_140004F8D
0x140004eaf  mov     r11d, [rsp+1B0h+var_17C]
0x140004eb4  mov     r14d, 100h
0x140004eba  mov     [r12+rbx+12h], r14w
0x140004ec0  xor     esi, esi
0x140004ec2  mov     [r12+rbx+10h], r11w
0x140004ec8  mov     [r12+rbx+18h], rdi
0x140004ecd  cmp     esi, r14d
0x140004ed0  jge     loc_140004FB5
0x140004ed6  cmp     dword ptr [rdi], 0
0x140004ed9  jnz     loc_140004F6C
0x140004edf  mov     rcx, [rsp+1B0h+var_168]
0x140004ee4  lea     r9, [rsp+1B0h+var_178]
0x140004ee9  mov     r8d, 2
0x140004eef  mov     dword ptr [rsp+1B0h+var_178], 0
0x140004ef7  lea     rdx, [rsp+1B0h+var_140]
0x140004efc  call    fs_SetUpKey
0x140004f01  test    rax, rax
0x140004f04  jz      short loc_140004F5F
0x140004f06  lea     rcx, [rsp+1B0h+var_180]
0x140004f0b  mov     [rsp+1B0h+var_190], rcx; unsigned __int16 *
0x140004f10  lea     r8d, [r11+rsi]; unsigned __int16
0x140004f14  mov     rcx, rax; struct sfac_ClientRec *
0x140004f17  call    ?sfac_GetMultiGlyphIDs@@YAHPEBUsfac_ClientRec@@GGPEBGPEAG@Z; sfac_GetMultiGlyphIDs(sfac_ClientRec const *,ushort,ushort,ushort const *,ushort *)
0x140004f1c  test    eax, eax
0x140004f1e  jz      short loc_140004F52
0x140004f20  mov     rcx, rbx; hMem
0x140004f23  call    cs:__imp_GlobalFree
0x140004f29  xor     eax, eax
0x140004f2b  mov     rcx, [rbp+0B0h+var_40]
0x140004f2f  xor     rcx, rsp; StackCookie
0x140004f32  call    __security_check_cookie
0x140004f37  mov     rbx, [rsp+1B0h+arg_18]
0x140004f3f  add     rsp, 180h
0x140004f46  pop     r15
0x140004f48  pop     r14
0x140004f4a  pop     r13
0x140004f4c  pop     r12
0x140004f4e  pop     rdi
0x140004f4f  pop     rsi
0x140004f50  pop     rbp
0x140004f51  retn
0x140004f52  movzx   r13d, [rsp+1B0h+var_180]
0x140004f58  mov     r11d, [rsp+1B0h+var_17C]
0x140004f5d  jmp     short loc_140004F66
0x140004f5f  cmp     dword ptr [rsp+1B0h+var_178], 0
0x140004f64  jnz     short loc_140004F20
0x140004f66  movzx   eax, r13w
0x140004f6a  mov     [rdi], eax
0x140004f6c  add     rdi, 4
0x140004f70  inc     esi
0x140004f72  jmp     loc_140004ECD
0x140004f77  lea     r14, [r14+rax*2]
0x140004f7b  add     r14, 4
0x140004f7f  inc     esi
0x140004f81  jmp     loc_140004E11
0x140004f86  cmp     [rsp+1B0h+var_170], 0
0x140004f8b  jnz     short loc_140004F20
0x140004f8d  mov     rax, [rsp+1B0h+var_160]
0x140004f92  mov     rdx, [rsp+1B0h+var_158]
0x140004f97  movzx   ecx, r13w
0x140004f9b  mov     [rdi], ecx
0x140004f9d  add     rdi, 4
0x140004fa1  movzx   eax, word ptr [r14+rax*2+4]
0x140004fa7  mov     [rdx+rax*4], ecx
0x140004faa  mov     ecx, dword ptr [rsp+1B0h+var_178]
0x140004fae  inc     ecx
0x140004fb0  jmp     loc_140004E3A
0x140004fb5  mov     rax, [rsp+1B0h+var_150]
0x140004fba  mov     edi, [rbx]
0x140004fbc  mov     [rax], rbx
0x140004fbf  mov     eax, edi
0x140004fc1  jmp     loc_140004F2B
0x140004fc6  cmp     eax, 0F100h
0x140004fcb  jz      short loc_140004FE4
0x140004fcd  cmp     eax, 0F200h
0x140004fd2  jnz     loc_140004F29
0x140004fd8  lea     rcx, qword_1400A4AE0
0x140004fdf  jmp     loc_140004D78
0x140004fe4  lea     rcx, asc_1400A4960; " "
0x140004feb  jmp     loc_140004D78
```
