# ORSetValueInternal

- ea: `0x140025f20`
- end: `0x14002636d`
- name: `ORSetValueInternal`
- size: `1101`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140022d64`
- `0x140025f00`

## callees

- `0x1400029c6`
- `0x1400029d2`
- `0x140002aa8`
- `0x140002b2c`
- `0x14002593c`
- `0x140025f20`
- `0x140026374`
- `0x140026bbc`
- `0x140026fa8`
- `0x14002e8cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400260b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400260b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002606a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002606a`

## string_xrefs

- `0x140026105`: `SymbolicLinkValue`

## pseudocode

```c
__int64 __fastcall ORSetValueInternal(__int64 a1, void *a2, int a3, const void *a4, unsigned int a5, int a6)
{
  const void *v6; // r12
  __int64 v9; // r15
  char *v10; // r13
  int v11; // edi
  unsigned int v12; // edi
  unsigned int v13; // ebx
  __int64 v14; // rdx
  unsigned __int64 v15; // r8
  size_t v16; // rbx
  char *v17; // rax
  __int64 v19; // rbx
  unsigned __int64 v20; // rbx
  _OWORD *v21; // rax
  _QWORD *v22; // rsi
  void *v23; // rax
  void *v24; // rax
  _WORD *v25; // r8
  int v26; // eax
  __int16 v27; // cx
  __int16 v28; // ax
  unsigned __int16 v29; // dx
  __int16 v30; // cx
  bool v31; // cf
  unsigned __int64 v32; // rax
  const void *v33; // rdx
  _DWORD *v34; // rdx
  int v35; // eax
  _QWORD *v36; // rdx
  size_t v37; // rdx
  __int64 v38; // rax
  int v39; // [rsp+20h] [rbp-40h]
  _OWORD *v40; // [rsp+30h] [rbp-30h] BYREF
  size_t v41; // [rsp+38h] [rbp-28h]
  unsigned __int64 v42; // [rsp+40h] [rbp-20h]
  void *v43[2]; // [rsp+48h] [rbp-18h] BYREF
  size_t Size; // [rsp+A0h] [rbp+40h] BYREF
  void *Src; // [rsp+A8h] [rbp+48h]
  int v46; // [rsp+B0h] [rbp+50h]

  v46 = a3;
  Src = a2;
  v6 = a4;
  v9 = 0;
  Size = 0;
  v10 = 0;
  v40 = 0;
  v11 = 0;
  a6 = 0;
  *(_OWORD *)v43 = 0;
  if ( *(_WORD *)(a1 + 28) == 29806 )
  {
    v9 = *(_QWORD *)(a1 + 16);
    if ( *(_DWORD *)v9 == -1092567328 )
    {
      v12 = a5;
      if ( !a4 && a5 )
      {
        v13 = 87;
LABEL_6:
        v11 = 0;
        goto LABEL_20;
      }
      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 40) + 13LL) & 3) == 1 )
      {
        v13 = 5;
        goto LABEL_6;
      }
      if ( (a5 & 1) == 0 && ((unsigned int)(a3 - 1) <= 1 || a3 == 7) )
      {
        if ( a4 )
        {
          v14 = a5 >> 1;
          if ( a5 >> 1 )
          {
            v15 = (unsigned __int64)a4 + 2 * (unsigned int)(v14 - 1);
            if ( *(_WORD *)v15 )
            {
              v16 = 2 * v14;
              if ( ((v15 ^ ((unsigned __int64)a4 + 2 * v14)) & 0xFFFFFFFFFFFFF000uLL) == 0 && !*((_WORD *)a4 + v14) )
              {
                v17 = (char *)o__aligned_malloc_0(a5 + 2LL, 0x10u);
                v10 = v17;
                if ( !v17 )
                {
LABEL_18:
                  v13 = 8;
LABEL_19:
                  v11 = a6;
                  goto LABEL_20;
                }
                memcpy_0(v17, v6, v16);
                v6 = v10;
                *(_WORD *)&v10[v16] = 0;
                v12 += 2;
              }
            }
          }
        }
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 136));
      a6 = 1;
      if ( *(_WORD *)(a1 + 30) )
      {
        v13 = 1018;
        v11 = 1;
        goto LABEL_20;
      }
      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 40) + 2LL) & 0x10) != 0
        && (v46 != 6 || (v12 & 1) != 0 || v12 > 0xFFFF || !a2 || wcsicmp(L"SymbolicLinkValue", (const wchar_t *)a2)) )
      {
LABEL_34:
        v13 = 87;
        goto LABEL_19;
      }
      v13 = ORFindValue(a2, a1, &Size);
      if ( !v13 )
      {
        v37 = Size;
        v39 = v46;
        *(_DWORD *)(*(_QWORD *)(Size + 24) + 12LL) = v46;
        v13 = ORUpdateValue(v9, v37, v6, v12, v39);
        if ( v13 )
          goto LABEL_19;
        v38 = *(_QWORD *)(a1 + 40);
        if ( *(_DWORD *)(v38 + 64) < v12 )
          *(_DWORD *)(v38 + 64) = v12;
        goto LABEL_64;
      }
      if ( v13 != 2 )
        goto LABEL_19;
      if ( a2 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *((_WORD *)a2 + v19) );
        v20 = 2 * v19;
        if ( v20 > 0xFFFF )
        {
          LOWORD(v43[0]) = -1;
          v13 = 534;
          goto LABEL_19;
        }
        LOWORD(v43[0]) = v20;
      }
      else
      {
        LOWORD(v20) = 0;
        LOWORD(v43[0]) = 0;
      }
      if ( (unsigned __int16)v20 > 0x7FFFu )
        goto LABEL_34;
      v21 = o__aligned_malloc_0(0x30u, 0x10u);
      v22 = v21;
      if ( !v21 )
        goto LABEL_18;
      v40 = v21;
      *v21 = 0;
      WORD1(v43[0]) = v20;
      v21[1] = 0;
      v21[2] = 0;
      Size = (unsigned __int16)v20;
      v23 = o__aligned_malloc_0((unsigned __int16)v20, 0x10u);
      v43[1] = v23;
      if ( !v23 )
        goto LABEL_18;
      memcpy_0(v23, Src, Size);
      LODWORD(Size) = (unsigned __int16)ORCompressCopyName(v43[1], Size, *(_QWORD *)(v9 + 16), v43);
      v41 = (unsigned int)(Size + 20);
      v24 = o__aligned_malloc_0((unsigned int)v41, 0x10u);
      v42 = (unsigned __int64)v24;
      if ( !v24 )
        goto LABEL_18;
      memset_0(v24, 0, v41);
      v25 = (_WORD *)v42;
      v26 = v46;
      v22[3] = v42;
      v27 = v25[8];
      *((_DWORD *)v25 + 3) = v26;
      v28 = v27 & 0xFFFE;
      *v25 = 27510;
      v29 = Size;
      v30 = v27 | 1;
      v31 = (unsigned __int16)Size < (unsigned __int16)v20;
      v25[1] = Size;
      if ( !v31 )
        v30 = v28;
      v32 = v29;
      v33 = v43[1];
      v25[8] = v30;
      v42 = v32;
      memcpy_0(v25 + 10, v33, (unsigned int)v32);
      v13 = ORUpdateValue(v9, v22, v6, v12, v46);
      if ( v13 )
        goto LABEL_19;
      v34 = *(_DWORD **)(a1 + 40);
      if ( v34[16] < v12 )
        v34[16] = v12;
      if ( (*(_BYTE *)(v22[3] + 16LL) & 1) != 0 )
      {
        if ( (unsigned int)v34[15] < 2 * v42 )
        {
          v35 = 2 * Size;
LABEL_57:
          v34[15] = v35;
        }
      }
      else
      {
        v35 = Size;
        if ( v34[15] < (unsigned int)Size )
          goto LABEL_57;
      }
      ++v34[9];
      v36 = *(_QWORD **)(a1 + 136);
      if ( *v36 != a1 + 128 )
        __fastfail(3u);
      *v22 = a1 + 128;
      v22[1] = v36;
      *v36 = v22;
      *(_QWORD *)(a1 + 136) = v22;
LABEL_64:
      ++*(_QWORD *)(a1 + 168);
      v11 = 1;
      v13 = 0;
      *(_DWORD *)(v9 + 180) = 1;
      v40 = 0;
      goto LABEL_20;
    }
  }
  v13 = 6;
LABEL_20:
  ORFreeOrNop(v9, &v40);
  ORFreeOrNop(v9, &v43[1]);
  if ( v10 )
    aligned_free(v10);
  if ( v11 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 136));
  return v13;
}

```

## disassembly

```asm
0x140025f20  mov     [rsp-38h+arg_18], rbx
0x140025f25  mov     [rsp-38h+arg_10], r8d
0x140025f2a  mov     [rsp-38h+Src], rdx
0x140025f2f  push    rbp
0x140025f30  push    rsi
0x140025f31  push    rdi
0x140025f32  push    r12
0x140025f34  push    r13
0x140025f36  push    r14
0x140025f38  push    r15
0x140025f3a  mov     rbp, rsp
0x140025f3d  sub     rsp, 60h
0x140025f41  mov     r12, r9
0x140025f44  mov     eax, 746Eh
0x140025f49  xor     r9d, r9d
0x140025f4c  xorps   xmm0, xmm0
0x140025f4f  mov     rsi, rdx
0x140025f52  mov     r14, rcx
0x140025f55  mov     r15d, r9d
0x140025f58  mov     [rbp+Size], r9
0x140025f5c  mov     r13d, r9d
0x140025f5f  mov     [rbp+var_30], r9
0x140025f63  mov     edi, r9d
0x140025f66  mov     [rbp+arg_28], r9d
0x140025f6a  movups  xmmword ptr [rbp+var_18], xmm0
0x140025f6e  cmp     [rcx+1Ch], ax
0x140025f72  jnz     loc_140026363
0x140025f78  mov     r15, [rcx+10h]
0x140025f7c  cmp     dword ptr [r15], 0BEE0BEE0h
0x140025f83  jnz     loc_140026363
0x140025f89  mov     edi, [rbp+arg_20]
0x140025f8c  test    r12, r12
0x140025f8f  jnz     short loc_140025FA1
0x140025f91  test    edi, edi
0x140025f93  jz      short loc_140025FA1
0x140025f95  lea     ebx, [r9+57h]
0x140025f99  mov     edi, r9d
0x140025f9c  jmp     loc_14002603A
0x140025fa1  mov     rax, [rcx+28h]
0x140025fa5  mov     edx, 1
0x140025faa  mov     cl, [rax+0Dh]
0x140025fad  and     cl, 3
0x140025fb0  cmp     cl, dl
0x140025fb2  jnz     short loc_140025FB9
0x140025fb4  lea     ebx, [rdx+4]
0x140025fb7  jmp     short loc_140025F99
0x140025fb9  test    dl, dil
0x140025fbc  jnz     loc_1400260AC
0x140025fc2  lea     eax, [r8-1]
0x140025fc6  cmp     eax, edx
0x140025fc8  jbe     short loc_140025FD4
0x140025fca  cmp     r8d, 7
0x140025fce  jnz     loc_1400260AC
0x140025fd4  test    r12, r12
0x140025fd7  jz      loc_1400260AC
0x140025fdd  mov     edx, edi
0x140025fdf  shr     edx, 1
0x140025fe1  jz      loc_1400260AC
0x140025fe7  lea     eax, [rdx-1]
0x140025fea  lea     r8, [r12+rax*2]
0x140025fee  cmp     [r8], r9w
0x140025ff2  jz      loc_1400260AC
0x140025ff8  lea     rbx, [rdx+rdx]
0x140025ffc  lea     rcx, [rbx+r12]
0x140026000  mov     rax, rcx
0x140026003  xor     rax, r8
0x140026006  test    rax, 0FFFFFFFFFFFFF000h
0x14002600c  jnz     loc_1400260AC
0x140026012  cmp     [rcx], r9w
0x140026016  jnz     loc_1400260AC
0x14002601c  lea     rcx, [rdi+2]; Size
0x140026020  mov     edx, 10h; Alignment
0x140026025  call    _o__aligned_malloc_0
0x14002602a  mov     r13, rax
0x14002602d  test    rax, rax
0x140026030  jnz     short loc_140026091
0x140026032  mov     ebx, 8
0x140026037  mov     edi, [rbp+arg_28]
0x14002603a  lea     rdx, [rbp+var_30]
0x14002603e  mov     rcx, r15
0x140026041  call    ORFreeOrNop
0x140026046  lea     rdx, [rbp+var_18+8]
0x14002604a  mov     rcx, r15
0x14002604d  call    ORFreeOrNop
0x140026052  test    r13, r13
0x140026055  jz      short loc_14002605F
0x140026057  mov     rcx, r13; Block
0x14002605a  call    _aligned_free
0x14002605f  test    edi, edi
0x140026061  jz      short loc_140026076
0x140026063  lea     rcx, [r15+88h]; lpCriticalSection
0x14002606a  call    cs:__imp_LeaveCriticalSection
0x140026071  nop     dword ptr [rax+rax+00h]
0x140026076  mov     eax, ebx
0x140026078  mov     rbx, [rsp+60h+arg_18]
0x140026080  add     rsp, 60h
0x140026084  pop     r15
0x140026086  pop     r14
0x140026088  pop     r13
0x14002608a  pop     r12
0x14002608c  pop     rdi
0x14002608d  pop     rsi
0x14002608e  pop     rbp
0x14002608f  retn
0x140026091  mov     r8, rbx; Size
0x140026094  mov     rdx, r12; Src
0x140026097  mov     rcx, r13; void *
0x14002609a  call    memcpy_0
0x14002609f  xor     eax, eax
0x1400260a1  mov     r12, r13
0x1400260a4  mov     [rbx+r13], ax
0x1400260a9  add     edi, 2
0x1400260ac  lea     rcx, [r15+88h]; lpCriticalSection
0x1400260b3  call    cs:__imp_EnterCriticalSection
0x1400260ba  nop     dword ptr [rax+rax+00h]
0x1400260bf  xor     ecx, ecx
0x1400260c1  mov     edx, 1
0x1400260c6  mov     [rbp+arg_28], edx
0x1400260c9  cmp     [r14+1Eh], cx
0x1400260ce  jz      short loc_1400260DC
0x1400260d0  mov     ebx, 3FAh
0x1400260d5  mov     edi, edx
0x1400260d7  jmp     loc_14002603A
0x1400260dc  mov     rax, [r14+28h]
0x1400260e0  test    byte ptr [rax+2], 10h
0x1400260e4  jz      short loc_14002611F
0x1400260e6  mov     ebx, 6
0x1400260eb  cmp     [rbp+arg_10], ebx
0x1400260ee  jnz     short loc_140026115
0x1400260f0  test    dl, dil
0x1400260f3  jnz     short loc_140026115
0x1400260f5  cmp     edi, 0FFFFh
0x1400260fb  ja      short loc_140026115
0x1400260fd  test    rsi, rsi
0x140026100  jz      short loc_140026115
0x140026102  mov     rdx, rsi; String2
0x140026105  lea     rcx, aSymboliclinkva; "SymbolicLinkValue"
0x14002610c  call    _wcsicmp
0x140026111  test    eax, eax
0x140026113  jz      short loc_14002611F
0x140026115  mov     ebx, 57h ; 'W'
0x14002611a  jmp     loc_140026037
0x14002611f  lea     r8, [rbp+Size]
0x140026123  mov     rdx, r14
0x140026126  mov     rcx, rsi
0x140026129  call    ORFindValue
0x14002612e  mov     ebx, eax
0x140026130  xor     eax, eax
0x140026132  test    ebx, ebx
0x140026134  jz      loc_14002630D
0x14002613a  cmp     ebx, 2
0x14002613d  jnz     loc_140026037
0x140026143  test    rsi, rsi
0x140026146  jz      short loc_140026176
0x140026148  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002614c  inc     rbx
0x14002614f  cmp     [rsi+rbx*2], ax
0x140026153  jnz     short loc_14002614C
0x140026155  add     rbx, rbx
0x140026158  mov     eax, 0FFFFh
0x14002615d  cmp     rbx, rax
0x140026160  ja      short loc_140026168
0x140026162  mov     word ptr [rbp+var_18], bx
0x140026166  jmp     short loc_14002617D
0x140026168  mov     word ptr [rbp+var_18], ax
0x14002616c  mov     ebx, 216h
0x140026171  jmp     loc_140026037
0x140026176  movzx   ebx, ax
0x140026179  mov     word ptr [rbp+var_18], ax
0x14002617d  mov     eax, 7FFFh
0x140026182  cmp     bx, ax
0x140026185  ja      short loc_140026115
0x140026187  mov     edx, 10h; Alignment
0x14002618c  lea     ecx, [rdx+20h]; Size
0x14002618f  call    _o__aligned_malloc_0
0x140026194  mov     rsi, rax
0x140026197  test    rax, rax
0x14002619a  jz      loc_140026032
0x1400261a0  xorps   xmm0, xmm0
0x1400261a3  mov     [rbp+var_30], rax
0x1400261a7  movups  xmmword ptr [rax], xmm0
0x1400261aa  mov     edx, 10h; Alignment
0x1400261af  mov     word ptr [rbp+var_18+2], bx
0x1400261b3  movups  xmmword ptr [rax+10h], xmm0
0x1400261b7  movups  xmmword ptr [rax+20h], xmm0
0x1400261bb  movzx   eax, bx
0x1400261be  mov     ecx, eax; Size
0x1400261c0  mov     [rbp+Size], rax
0x1400261c4  call    _o__aligned_malloc_0
0x1400261c9  mov     [rbp+var_18+8], rax
0x1400261cd  test    rax, rax
0x1400261d0  jz      loc_140026032
0x1400261d6  mov     r8, [rbp+Size]; Size
0x1400261da  mov     rcx, rax; void *
0x1400261dd  mov     rdx, [rbp+Src]; Src
0x1400261e1  call    memcpy_0
0x1400261e6  mov     r8, [r15+10h]
0x1400261ea  lea     r9, [rbp+var_18]
0x1400261ee  mov     rdx, [rbp+Size]
0x1400261f2  mov     rcx, [rbp+var_18+8]
0x1400261f6  call    ORCompressCopyName
0x1400261fb  movzx   eax, ax
0x1400261fe  mov     edx, 10h; Alignment
0x140026203  mov     dword ptr [rbp+Size], eax
0x140026206  add     eax, 14h
0x140026209  mov     ecx, eax; Size
0x14002620b  mov     [rbp+var_28], rax
0x14002620f  call    _o__aligned_malloc_0
0x140026214  mov     [rbp+var_20], rax
0x140026218  test    rax, rax
0x14002621b  jz      loc_140026032
0x140026221  mov     r8, [rbp+var_28]; Size
0x140026225  xor     edx, edx; Val
0x140026227  mov     rcx, rax; void *
0x14002622a  call    memset_0
0x14002622f  mov     r8, [rbp+var_20]
0x140026233  mov     edx, 0FFFEh
0x140026238  mov     eax, [rbp+arg_10]
0x14002623b  mov     [rsi+18h], r8
0x14002623f  movzx   ecx, word ptr [r8+10h]
0x140026244  mov     [r8+0Ch], eax
0x140026248  movzx   eax, cx
0x14002624b  and     ax, dx
0x14002624e  mov     word ptr [r8], 6B76h
0x140026254  mov     edx, dword ptr [rbp+Size]
0x140026257  or      cx, 1
0x14002625b  cmp     dx, bx
0x14002625e  mov     [r8+2], dx
0x140026263  cmovnb  cx, ax
0x140026267  movzx   eax, dx
0x14002626a  mov     rdx, [rbp+var_18+8]; Src
0x14002626e  mov     [r8+10h], cx
0x140026273  lea     rcx, [r8+14h]; void *
0x140026277  mov     r8d, eax; Size
0x14002627a  mov     [rbp+var_20], rax
0x14002627e  call    memcpy_0
0x140026283  mov     eax, [rbp+arg_10]
0x140026286  mov     r9d, edi
0x140026289  mov     r8, r12
0x14002628c  mov     [rsp+60h+var_40], eax
0x140026290  mov     rdx, rsi
0x140026293  mov     rcx, r15
0x140026296  call    ORUpdateValue
0x14002629b  mov     ebx, eax
0x14002629d  test    eax, eax
0x14002629f  jnz     loc_140026037
0x1400262a5  mov     rdx, [r14+28h]
0x1400262a9  cmp     [rdx+40h], edi
0x1400262ac  jnb     short loc_1400262B1
0x1400262ae  mov     [rdx+40h], edi
0x1400262b1  mov     rax, [rsi+18h]
0x1400262b5  mov     r8d, 1
0x1400262bb  test    [rax+10h], r8b
0x1400262bf  jz      short loc_1400262D7
0x1400262c1  mov     rcx, [rbp+var_20]
0x1400262c5  mov     eax, [rdx+3Ch]
0x1400262c8  add     rcx, rcx
0x1400262cb  cmp     rax, rcx
0x1400262ce  jnb     short loc_1400262E2
0x1400262d0  mov     eax, dword ptr [rbp+Size]
0x1400262d3  add     eax, eax
0x1400262d5  jmp     short loc_1400262DF
0x1400262d7  mov     eax, dword ptr [rbp+Size]
0x1400262da  cmp     [rdx+3Ch], eax
0x1400262dd  jnb     short loc_1400262E2
0x1400262df  mov     [rdx+3Ch], eax
0x1400262e2  add     [rdx+24h], r8d
0x1400262e6  lea     rax, [r14+80h]
0x1400262ed  mov     rdx, [rax+8]
0x1400262f1  cmp     [rdx], rax
0x1400262f4  jz      short loc_1400262FD
0x1400262f6  mov     ecx, 3
0x1400262fb  int     29h; Win8: RtlFailFast(ecx)
0x1400262fd  mov     [rsi], rax
0x140026300  mov     [rsi+8], rdx
0x140026304  mov     [rdx], rsi
0x140026307  mov     [rax+8], rsi
0x14002630b  jmp     short loc_140026343
0x14002630d  mov     ecx, [rbp+arg_10]
0x140026310  mov     r9d, edi
0x140026313  mov     rdx, [rbp+Size]
0x140026317  mov     r8, r12
0x14002631a  mov     [rsp+60h+var_40], ecx
0x14002631e  mov     rax, [rdx+18h]
0x140026322  mov     [rax+0Ch], ecx
0x140026325  mov     rcx, r15
0x140026328  call    ORUpdateValue
0x14002632d  mov     ebx, eax
0x14002632f  test    eax, eax
0x140026331  jnz     loc_140026037
0x140026337  mov     rax, [r14+28h]
0x14002633b  cmp     [rax+40h], edi
0x14002633e  jnb     short loc_140026343
0x140026340  mov     [rax+40h], edi
0x140026343  mov     eax, 1
0x140026348  add     [r14+0A8h], rax
0x14002634f  mov     edi, eax
0x140026351  xor     ebx, ebx
0x140026353  mov     [r15+0B4h], eax
0x14002635a  mov     [rbp+var_30], rbx
  ... truncated ...
```
