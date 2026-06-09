# CreateGlyphSetFromMITable(_CMAPINFO *,_MbcsToIndex *,ushort,ulong * *)

- ea: `0x140070dc8`
- end: `0x140070fda`
- name: `?CreateGlyphSetFromMITable@@YAKPEAU_CMAPINFO@@PEAU_MbcsToIndex@@GPEAPEAK@Z`
- size: `530`
- prototype: `unsigned int __fastcall(struct _CMAPINFO *, struct _MbcsToIndex *, unsigned __int16, unsigned int **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400711f0`
- `0x140071458`

## callees

- `0x14004dbb0`
- `0x140066e98`
- `0x140070dc8`
- `0x14007680c`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140070ee6`
- `KERNEL32!GlobalFree` at `0x140070f2a`
- `KERNEL32!GlobalFree` at `0x140070fc0`
- `KERNEL32!GlobalFree` at `0x140070ee6`
- `KERNEL32!GlobalFree` at `0x140070f2a`
- `KERNEL32!GlobalFree` at `0x140070fc0`
- `KERNEL32!GlobalAlloc` at `0x140070def`
- `KERNEL32!GlobalAlloc` at `0x140070f19`
- `KERNEL32!GlobalAlloc` at `0x140070def`
- `KERNEL32!GlobalAlloc` at `0x140070f19`

## pseudocode

```c
__int64 __fastcall CreateGlyphSetFromMITable(
        struct _CMAPINFO *a1,
        struct _MbcsToIndex *a2,
        unsigned __int16 a3,
        unsigned int **a4)
{
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  unsigned int CodePageFromSpecId; // eax
  unsigned __int16 v11; // si
  unsigned int v12; // r12d
  int v13; // r8d
  unsigned int v14; // edx
  unsigned int v15; // r14d
  __int64 i; // rcx
  unsigned int v17; // eax
  unsigned int v18; // ebp
  unsigned int v20; // esi
  unsigned int *v21; // rax
  unsigned int *v22; // r15
  unsigned int *v23; // r8
  unsigned int *v24; // r9
  unsigned __int16 v25; // r10
  _DWORD *v26; // rdx
  unsigned int v27; // eax
  int v28[18]; // [rsp+30h] [rbp-48h] BYREF

  v8 = GlobalAlloc(0, 0xC0000u);
  v9 = v8;
  if ( !v8 )
  {
LABEL_18:
    if ( !a4 )
      return 0;
LABEL_19:
    *a4 = 0;
    return 0;
  }
  memset_0(v8, 0, 0xC0000u);
  CodePageFromSpecId = GetCodePageFromSpecId(*((_WORD *)a1 + 4));
  v11 = 0;
  v12 = CodePageFromSpecId;
  if ( a3 )
  {
    while ( (unsigned int)EngMultiByteToWideCharEx(v12, v28, 4, (char *)a2 + 8 * v11, 2, 0) != -1 )
    {
      if ( !v9[3 * LOWORD(v28[0])] )
      {
        v9[3 * LOWORD(v28[0])] = 1;
        LOWORD(v9[3 * LOWORD(v28[0]) + 1]) = v28[0];
        v9[3 * LOWORD(v28[0]) + 2] = *((_DWORD *)a2 + 2 * v11 + 1);
      }
      if ( ++v11 >= a3 )
        goto LABEL_7;
    }
    goto LABEL_17;
  }
LABEL_7:
  v13 = 0;
  v14 = 0;
  v15 = 0;
  for ( i = 0; i != 0xFFFF; ++i )
  {
    if ( v9[3 * i] )
    {
      v13 = 1;
      ++v15;
    }
    else
    {
      v17 = v14 + 1;
      if ( !v13 )
        v17 = v14;
      v13 = 0;
      v14 = v17;
    }
  }
  v18 = v14 + 1;
  if ( !v13 )
    v18 = v14;
  if ( !v18 )
  {
LABEL_17:
    GlobalFree(v9);
    goto LABEL_18;
  }
  v20 = 4 * (v15 + 4 * (v18 + 1));
  if ( a4 )
  {
    v21 = (unsigned int *)GlobalAlloc(0, v20);
    v22 = v21;
    if ( !v21 )
    {
      GlobalFree(v9);
      goto LABEL_19;
    }
    memset_0(v21, 0, v20);
    *v22 = v20;
    v22[1] = 4;
    v23 = v22 + 4;
    v24 = &v22[4 * v18 + 4];
    v22[3] = v18;
    v25 = 0;
    v22[2] = v15;
    v26 = v9;
    do
    {
      while ( !*v26 )
        v26 += 3;
      *(_WORD *)v23 = *((_WORD *)v26 + 2);
      *((_WORD *)v23 + 1) = 0;
      for ( *((_QWORD *)v23 + 1) = v24; *v26; ++v24 )
      {
        ++*((_WORD *)v23 + 1);
        v27 = v26[2];
        v26 += 3;
        *v24 = v27;
      }
      ++v25;
      v23 += 4;
    }
    while ( v25 < v18 );
    GlobalFree(v9);
    *a4 = v22;
  }
  return v20;
}

```

## disassembly

```asm
0x140070dc8  push    rbx
0x140070dca  push    rbp
0x140070dcb  push    rsi
0x140070dcc  push    rdi
0x140070dcd  push    r12
0x140070dcf  push    r14
0x140070dd1  push    r15
0x140070dd3  sub     rsp, 40h
0x140070dd7  mov     r15, rdx
0x140070dda  mov     rsi, rcx
0x140070ddd  mov     r14d, 0C0000h
0x140070de3  xor     ecx, ecx; uFlags
0x140070de5  mov     edx, r14d; dwBytes
0x140070de8  mov     rbx, r9
0x140070deb  movzx   ebp, r8w
0x140070def  call    cs:__imp_GlobalAlloc
0x140070df5  mov     rdi, rax
0x140070df8  test    rax, rax
0x140070dfb  jz      loc_140070EEC
0x140070e01  mov     r8d, r14d; Size
0x140070e04  xor     edx, edx; Val
0x140070e06  mov     rcx, rax; void *
0x140070e09  call    memset_0
0x140070e0e  movzx   ecx, word ptr [rsi+8]; unsigned __int16
0x140070e12  call    ?GetCodePageFromSpecId@@YAIG@Z; GetCodePageFromSpecId(ushort)
0x140070e17  xor     esi, esi
0x140070e19  xor     ecx, ecx
0x140070e1b  mov     r12d, eax
0x140070e1e  lea     r9d, [rsi+1]
0x140070e22  cmp     cx, bp
0x140070e25  jnb     short loc_140070EA0
0x140070e27  movzx   ecx, si
0x140070e2a  lea     rdx, [rsp+78h+var_48]
0x140070e2f  mov     [rsp+78h+var_50], 0
0x140070e37  mov     r8d, 4
0x140070e3d  mov     [rsp+78h+var_58], 2
0x140070e45  lea     r14, [r15+rcx*8]
0x140070e49  mov     ecx, r12d
0x140070e4c  mov     r9, r14
0x140070e4f  call    EngMultiByteToWideCharEx
0x140070e54  cmp     eax, 0FFFFFFFFh
0x140070e57  jz      loc_140070EE3
0x140070e5d  movzx   eax, word ptr [rsp+78h+var_48]
0x140070e62  mov     r9d, 1
0x140070e68  lea     rcx, [rax+rax*2]
0x140070e6c  cmp     dword ptr [rdi+rcx*4], 0
0x140070e70  jnz     short loc_140070E97
0x140070e72  mov     [rdi+rcx*4], r9d
0x140070e76  mov     eax, [rsp+78h+var_48]
0x140070e7a  movzx   ecx, ax
0x140070e7d  lea     rdx, [rcx+rcx*2]
0x140070e81  mov     [rdi+rdx*4+4], ax
0x140070e86  movzx   eax, word ptr [rsp+78h+var_48]
0x140070e8b  lea     rcx, [rax+rax*2]
0x140070e8f  mov     eax, [r14+4]
0x140070e93  mov     [rdi+rcx*4+8], eax
0x140070e97  add     si, r9w
0x140070e9b  cmp     si, bp
0x140070e9e  jb      short loc_140070E27
0x140070ea0  xor     r8d, r8d
0x140070ea3  xor     edx, edx
0x140070ea5  xor     r14d, r14d
0x140070ea8  xor     ecx, ecx
0x140070eaa  lea     rax, [rcx+rcx*2]
0x140070eae  cmp     dword ptr [rdi+rax*4], 0
0x140070eb2  jnz     short loc_140070EC4
0x140070eb4  test    r8d, r8d
0x140070eb7  lea     eax, [rdx+1]
0x140070eba  cmovz   eax, edx
0x140070ebd  xor     r8d, r8d
0x140070ec0  mov     edx, eax
0x140070ec2  jmp     short loc_140070ECA
0x140070ec4  mov     r8d, r9d
0x140070ec7  add     r14d, r9d
0x140070eca  add     rcx, r9
0x140070ecd  cmp     rcx, 0FFFFh
0x140070ed4  jnz     short loc_140070EAA
0x140070ed6  test    r8d, r8d
0x140070ed9  lea     ebp, [rdx+1]
0x140070edc  cmovz   ebp, edx
0x140070edf  test    ebp, ebp
0x140070ee1  jnz     short loc_140070EFF
0x140070ee3  mov     rcx, rdi; hMem
0x140070ee6  call    cs:__imp_GlobalFree
0x140070eec  test    rbx, rbx
0x140070eef  jz      short loc_140070EF8
0x140070ef1  mov     qword ptr [rbx], 0
0x140070ef8  xor     eax, eax
0x140070efa  jmp     loc_140070FCB
0x140070eff  lea     esi, [rbp+1]
0x140070f02  lea     esi, [r14+rsi*4]
0x140070f06  shl     esi, 2
0x140070f09  test    rbx, rbx
0x140070f0c  jz      loc_140070FC9
0x140070f12  mov     edx, esi; dwBytes
0x140070f14  xor     ecx, ecx; uFlags
0x140070f16  mov     r12d, esi
0x140070f19  call    cs:__imp_GlobalAlloc
0x140070f1f  mov     r15, rax
0x140070f22  test    rax, rax
0x140070f25  jnz     short loc_140070F32
0x140070f27  mov     rcx, rdi; hMem
0x140070f2a  call    cs:__imp_GlobalFree
0x140070f30  jmp     short loc_140070EF1
0x140070f32  mov     r8, r12; Size
0x140070f35  xor     edx, edx; Val
0x140070f37  mov     rcx, r15; void *
0x140070f3a  call    memset_0
0x140070f3f  lea     r9d, [rbp-1]
0x140070f43  mov     [r15], esi
0x140070f46  add     r9, 2
0x140070f4a  mov     dword ptr [r15+4], 4
0x140070f52  shl     r9, 4
0x140070f56  lea     r8, [r15+10h]
0x140070f5a  add     r9, r15
0x140070f5d  mov     [r15+0Ch], ebp
0x140070f61  xor     r10d, r10d
0x140070f64  mov     [r15+8], r14d
0x140070f68  mov     rdx, rdi
0x140070f6b  test    ebp, ebp
0x140070f6d  jz      short loc_140070FBD
0x140070f6f  lea     r11d, [r10+1]
0x140070f73  jmp     short loc_140070F79
0x140070f75  add     rdx, 0Ch
0x140070f79  cmp     dword ptr [rdx], 0
0x140070f7c  jz      short loc_140070F75
0x140070f7e  movzx   eax, word ptr [rdx+4]
0x140070f82  mov     [r8], ax
0x140070f86  xor     eax, eax
0x140070f88  mov     [r8+2], ax
0x140070f8d  mov     [r8+8], r9
0x140070f91  cmp     [rdx], eax
0x140070f93  jz      short loc_140070FAD
0x140070f95  add     [r8+2], r11w
0x140070f9a  mov     eax, [rdx+8]
0x140070f9d  add     rdx, 0Ch
0x140070fa1  mov     [r9], eax
0x140070fa4  add     r9, 4
0x140070fa8  cmp     dword ptr [rdx], 0
0x140070fab  jnz     short loc_140070F95
0x140070fad  add     r10w, r11w
0x140070fb1  add     r8, 10h
0x140070fb5  movzx   ecx, r10w
0x140070fb9  cmp     ecx, ebp
0x140070fbb  jb      short loc_140070F79
0x140070fbd  mov     rcx, rdi; hMem
0x140070fc0  call    cs:__imp_GlobalFree
0x140070fc6  mov     [rbx], r15
0x140070fc9  mov     eax, esi
0x140070fcb  add     rsp, 40h
0x140070fcf  pop     r15
0x140070fd1  pop     r14
0x140070fd3  pop     r12
0x140070fd5  pop     rdi
0x140070fd6  pop     rsi
0x140070fd7  pop     rbp
0x140070fd8  pop     rbx
0x140070fd9  retn
```
