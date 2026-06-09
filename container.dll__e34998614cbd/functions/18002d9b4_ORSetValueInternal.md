# ORSetValueInternal

- ea: `0x18002d9b4`
- end: `0x18002de01`
- name: `ORSetValueInternal`
- size: `1101`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x18002c9fc`

## callees

- `0x180003542`
- `0x18000354e`
- `0x1800035e4`
- `0x180003614`
- `0x18000362c`
- `0x18002d854`
- `0x18002d9b4`
- `0x18002de08`
- `0x18002f708`
- `0x18002f9dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dafe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dafe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002db47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002db47`

## string_xrefs

- `0x18002db99`: `SymbolicLinkValue`

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
0x18002d9b4  mov     [rsp-38h+arg_18], rbx
0x18002d9b9  mov     [rsp-38h+arg_10], r8d
0x18002d9be  mov     [rsp-38h+Src], rdx
0x18002d9c3  push    rbp
0x18002d9c4  push    rsi
0x18002d9c5  push    rdi
0x18002d9c6  push    r12
0x18002d9c8  push    r13
0x18002d9ca  push    r14
0x18002d9cc  push    r15
0x18002d9ce  mov     rbp, rsp
0x18002d9d1  sub     rsp, 60h
0x18002d9d5  mov     r12, r9
0x18002d9d8  mov     eax, 746Eh
0x18002d9dd  xor     r9d, r9d
0x18002d9e0  xorps   xmm0, xmm0
0x18002d9e3  mov     rsi, rdx
0x18002d9e6  mov     r14, rcx
0x18002d9e9  mov     r15d, r9d
0x18002d9ec  mov     [rbp+Size], r9
0x18002d9f0  mov     r13d, r9d
0x18002d9f3  mov     [rbp+var_30], r9
0x18002d9f7  mov     edi, r9d
0x18002d9fa  mov     [rbp+arg_28], r9d
0x18002d9fe  movups  xmmword ptr [rbp+var_18], xmm0
0x18002da02  cmp     [rcx+1Ch], ax
0x18002da06  jnz     loc_18002DDF7
0x18002da0c  mov     r15, [rcx+10h]
0x18002da10  cmp     dword ptr [r15], 0BEE0BEE0h
0x18002da17  jnz     loc_18002DDF7
0x18002da1d  mov     edi, [rbp+arg_20]
0x18002da20  test    r12, r12
0x18002da23  jnz     short loc_18002DA35
0x18002da25  test    edi, edi
0x18002da27  jz      short loc_18002DA35
0x18002da29  lea     ebx, [r9+57h]
0x18002da2d  mov     edi, r9d
0x18002da30  jmp     loc_18002DACE
0x18002da35  mov     rax, [rcx+28h]
0x18002da39  mov     edx, 1
0x18002da3e  mov     cl, [rax+0Dh]
0x18002da41  and     cl, 3
0x18002da44  cmp     cl, dl
0x18002da46  jnz     short loc_18002DA4D
0x18002da48  lea     ebx, [rdx+4]
0x18002da4b  jmp     short loc_18002DA2D
0x18002da4d  test    dl, dil
0x18002da50  jnz     loc_18002DB40
0x18002da56  lea     eax, [r8-1]
0x18002da5a  cmp     eax, edx
0x18002da5c  jbe     short loc_18002DA68
0x18002da5e  cmp     r8d, 7
0x18002da62  jnz     loc_18002DB40
0x18002da68  test    r12, r12
0x18002da6b  jz      loc_18002DB40
0x18002da71  mov     edx, edi
0x18002da73  shr     edx, 1
0x18002da75  jz      loc_18002DB40
0x18002da7b  lea     eax, [rdx-1]
0x18002da7e  lea     r8, [r12+rax*2]
0x18002da82  cmp     [r8], r9w
0x18002da86  jz      loc_18002DB40
0x18002da8c  lea     rbx, [rdx+rdx]
0x18002da90  lea     rcx, [rbx+r12]
0x18002da94  mov     rax, rcx
0x18002da97  xor     rax, r8
0x18002da9a  test    rax, 0FFFFFFFFFFFFF000h
0x18002daa0  jnz     loc_18002DB40
0x18002daa6  cmp     [rcx], r9w
0x18002daaa  jnz     loc_18002DB40
0x18002dab0  lea     rcx, [rdi+2]; Size
0x18002dab4  mov     edx, 10h; Alignment
0x18002dab9  call    _o__aligned_malloc_0
0x18002dabe  mov     r13, rax
0x18002dac1  test    rax, rax
0x18002dac4  jnz     short loc_18002DB25
0x18002dac6  mov     ebx, 8
0x18002dacb  mov     edi, [rbp+arg_28]
0x18002dace  lea     rdx, [rbp+var_30]
0x18002dad2  mov     rcx, r15
0x18002dad5  call    ORFreeOrNop
0x18002dada  lea     rdx, [rbp+var_18+8]
0x18002dade  mov     rcx, r15
0x18002dae1  call    ORFreeOrNop
0x18002dae6  test    r13, r13
0x18002dae9  jz      short loc_18002DAF3
0x18002daeb  mov     rcx, r13; Block
0x18002daee  call    _aligned_free
0x18002daf3  test    edi, edi
0x18002daf5  jz      short loc_18002DB0A
0x18002daf7  lea     rcx, [r15+88h]; lpCriticalSection
0x18002dafe  call    cs:__imp_LeaveCriticalSection
0x18002db05  nop     dword ptr [rax+rax+00h]
0x18002db0a  mov     eax, ebx
0x18002db0c  mov     rbx, [rsp+60h+arg_18]
0x18002db14  add     rsp, 60h
0x18002db18  pop     r15
0x18002db1a  pop     r14
0x18002db1c  pop     r13
0x18002db1e  pop     r12
0x18002db20  pop     rdi
0x18002db21  pop     rsi
0x18002db22  pop     rbp
0x18002db23  retn
0x18002db25  mov     r8, rbx; Size
0x18002db28  mov     rdx, r12; Src
0x18002db2b  mov     rcx, r13; void *
0x18002db2e  call    memcpy_0
0x18002db33  xor     eax, eax
0x18002db35  mov     r12, r13
0x18002db38  mov     [rbx+r13], ax
0x18002db3d  add     edi, 2
0x18002db40  lea     rcx, [r15+88h]; lpCriticalSection
0x18002db47  call    cs:__imp_EnterCriticalSection
0x18002db4e  nop     dword ptr [rax+rax+00h]
0x18002db53  xor     ecx, ecx
0x18002db55  mov     edx, 1
0x18002db5a  mov     [rbp+arg_28], edx
0x18002db5d  cmp     [r14+1Eh], cx
0x18002db62  jz      short loc_18002DB70
0x18002db64  mov     ebx, 3FAh
0x18002db69  mov     edi, edx
0x18002db6b  jmp     loc_18002DACE
0x18002db70  mov     rax, [r14+28h]
0x18002db74  test    byte ptr [rax+2], 10h
0x18002db78  jz      short loc_18002DBB3
0x18002db7a  mov     ebx, 6
0x18002db7f  cmp     [rbp+arg_10], ebx
0x18002db82  jnz     short loc_18002DBA9
0x18002db84  test    dl, dil
0x18002db87  jnz     short loc_18002DBA9
0x18002db89  cmp     edi, 0FFFFh
0x18002db8f  ja      short loc_18002DBA9
0x18002db91  test    rsi, rsi
0x18002db94  jz      short loc_18002DBA9
0x18002db96  mov     rdx, rsi; String2
0x18002db99  lea     rcx, aSymboliclinkva; "SymbolicLinkValue"
0x18002dba0  call    _wcsicmp
0x18002dba5  test    eax, eax
0x18002dba7  jz      short loc_18002DBB3
0x18002dba9  mov     ebx, 57h ; 'W'
0x18002dbae  jmp     loc_18002DACB
0x18002dbb3  lea     r8, [rbp+Size]
0x18002dbb7  mov     rdx, r14
0x18002dbba  mov     rcx, rsi
0x18002dbbd  call    ORFindValue
0x18002dbc2  mov     ebx, eax
0x18002dbc4  xor     eax, eax
0x18002dbc6  test    ebx, ebx
0x18002dbc8  jz      loc_18002DDA1
0x18002dbce  cmp     ebx, 2
0x18002dbd1  jnz     loc_18002DACB
0x18002dbd7  test    rsi, rsi
0x18002dbda  jz      short loc_18002DC0A
0x18002dbdc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002dbe0  inc     rbx
0x18002dbe3  cmp     [rsi+rbx*2], ax
0x18002dbe7  jnz     short loc_18002DBE0
0x18002dbe9  add     rbx, rbx
0x18002dbec  mov     eax, 0FFFFh
0x18002dbf1  cmp     rbx, rax
0x18002dbf4  ja      short loc_18002DBFC
0x18002dbf6  mov     word ptr [rbp+var_18], bx
0x18002dbfa  jmp     short loc_18002DC11
0x18002dbfc  mov     word ptr [rbp+var_18], ax
0x18002dc00  mov     ebx, 216h
0x18002dc05  jmp     loc_18002DACB
0x18002dc0a  movzx   ebx, ax
0x18002dc0d  mov     word ptr [rbp+var_18], ax
0x18002dc11  mov     eax, 7FFFh
0x18002dc16  cmp     bx, ax
0x18002dc19  ja      short loc_18002DBA9
0x18002dc1b  mov     edx, 10h; Alignment
0x18002dc20  lea     ecx, [rdx+20h]; Size
0x18002dc23  call    _o__aligned_malloc_0
0x18002dc28  mov     rsi, rax
0x18002dc2b  test    rax, rax
0x18002dc2e  jz      loc_18002DAC6
0x18002dc34  xorps   xmm0, xmm0
0x18002dc37  mov     [rbp+var_30], rax
0x18002dc3b  movups  xmmword ptr [rax], xmm0
0x18002dc3e  mov     edx, 10h; Alignment
0x18002dc43  mov     word ptr [rbp+var_18+2], bx
0x18002dc47  movups  xmmword ptr [rax+10h], xmm0
0x18002dc4b  movups  xmmword ptr [rax+20h], xmm0
0x18002dc4f  movzx   eax, bx
0x18002dc52  mov     ecx, eax; Size
0x18002dc54  mov     [rbp+Size], rax
0x18002dc58  call    _o__aligned_malloc_0
0x18002dc5d  mov     [rbp+var_18+8], rax
0x18002dc61  test    rax, rax
0x18002dc64  jz      loc_18002DAC6
0x18002dc6a  mov     r8, [rbp+Size]; Size
0x18002dc6e  mov     rcx, rax; void *
0x18002dc71  mov     rdx, [rbp+Src]; Src
0x18002dc75  call    memcpy_0
0x18002dc7a  mov     r8, [r15+10h]
0x18002dc7e  lea     r9, [rbp+var_18]
0x18002dc82  mov     rdx, [rbp+Size]
0x18002dc86  mov     rcx, [rbp+var_18+8]
0x18002dc8a  call    ORCompressCopyName
0x18002dc8f  movzx   eax, ax
0x18002dc92  mov     edx, 10h; Alignment
0x18002dc97  mov     dword ptr [rbp+Size], eax
0x18002dc9a  add     eax, 14h
0x18002dc9d  mov     ecx, eax; Size
0x18002dc9f  mov     [rbp+var_28], rax
0x18002dca3  call    _o__aligned_malloc_0
0x18002dca8  mov     [rbp+var_20], rax
0x18002dcac  test    rax, rax
0x18002dcaf  jz      loc_18002DAC6
0x18002dcb5  mov     r8, [rbp+var_28]; Size
0x18002dcb9  xor     edx, edx; Val
0x18002dcbb  mov     rcx, rax; void *
0x18002dcbe  call    memset_0
0x18002dcc3  mov     r8, [rbp+var_20]
0x18002dcc7  mov     edx, 0FFFEh
0x18002dccc  mov     eax, [rbp+arg_10]
0x18002dccf  mov     [rsi+18h], r8
0x18002dcd3  movzx   ecx, word ptr [r8+10h]
0x18002dcd8  mov     [r8+0Ch], eax
0x18002dcdc  movzx   eax, cx
0x18002dcdf  and     ax, dx
0x18002dce2  mov     word ptr [r8], 6B76h
0x18002dce8  mov     edx, dword ptr [rbp+Size]
0x18002dceb  or      cx, 1
0x18002dcef  cmp     dx, bx
0x18002dcf2  mov     [r8+2], dx
0x18002dcf7  cmovnb  cx, ax
0x18002dcfb  movzx   eax, dx
0x18002dcfe  mov     rdx, [rbp+var_18+8]; Src
0x18002dd02  mov     [r8+10h], cx
0x18002dd07  lea     rcx, [r8+14h]; void *
0x18002dd0b  mov     r8d, eax; Size
0x18002dd0e  mov     [rbp+var_20], rax
0x18002dd12  call    memcpy_0
0x18002dd17  mov     eax, [rbp+arg_10]
0x18002dd1a  mov     r9d, edi
0x18002dd1d  mov     r8, r12
0x18002dd20  mov     [rsp+60h+var_40], eax
0x18002dd24  mov     rdx, rsi
0x18002dd27  mov     rcx, r15
0x18002dd2a  call    ORUpdateValue
0x18002dd2f  mov     ebx, eax
0x18002dd31  test    eax, eax
0x18002dd33  jnz     loc_18002DACB
0x18002dd39  mov     rdx, [r14+28h]
0x18002dd3d  cmp     [rdx+40h], edi
0x18002dd40  jnb     short loc_18002DD45
0x18002dd42  mov     [rdx+40h], edi
0x18002dd45  mov     rax, [rsi+18h]
0x18002dd49  mov     r8d, 1
0x18002dd4f  test    [rax+10h], r8b
0x18002dd53  jz      short loc_18002DD6B
0x18002dd55  mov     rcx, [rbp+var_20]
0x18002dd59  mov     eax, [rdx+3Ch]
0x18002dd5c  add     rcx, rcx
0x18002dd5f  cmp     rax, rcx
0x18002dd62  jnb     short loc_18002DD76
0x18002dd64  mov     eax, dword ptr [rbp+Size]
0x18002dd67  add     eax, eax
0x18002dd69  jmp     short loc_18002DD73
0x18002dd6b  mov     eax, dword ptr [rbp+Size]
0x18002dd6e  cmp     [rdx+3Ch], eax
0x18002dd71  jnb     short loc_18002DD76
0x18002dd73  mov     [rdx+3Ch], eax
0x18002dd76  add     [rdx+24h], r8d
0x18002dd7a  lea     rax, [r14+80h]
0x18002dd81  mov     rdx, [rax+8]
0x18002dd85  cmp     [rdx], rax
0x18002dd88  jz      short loc_18002DD91
0x18002dd8a  mov     ecx, 3
0x18002dd8f  int     29h; Win8: RtlFailFast(ecx)
0x18002dd91  mov     [rsi], rax
0x18002dd94  mov     [rsi+8], rdx
0x18002dd98  mov     [rdx], rsi
0x18002dd9b  mov     [rax+8], rsi
0x18002dd9f  jmp     short loc_18002DDD7
0x18002dda1  mov     ecx, [rbp+arg_10]
0x18002dda4  mov     r9d, edi
0x18002dda7  mov     rdx, [rbp+Size]
0x18002ddab  mov     r8, r12
0x18002ddae  mov     [rsp+60h+var_40], ecx
0x18002ddb2  mov     rax, [rdx+18h]
0x18002ddb6  mov     [rax+0Ch], ecx
0x18002ddb9  mov     rcx, r15
0x18002ddbc  call    ORUpdateValue
0x18002ddc1  mov     ebx, eax
0x18002ddc3  test    eax, eax
0x18002ddc5  jnz     loc_18002DACB
0x18002ddcb  mov     rax, [r14+28h]
0x18002ddcf  cmp     [rax+40h], edi
0x18002ddd2  jnb     short loc_18002DDD7
0x18002ddd4  mov     [rax+40h], edi
0x18002ddd7  mov     eax, 1
0x18002dddc  add     [r14+0A8h], rax
0x18002dde3  mov     edi, eax
0x18002dde5  xor     ebx, ebx
0x18002dde7  mov     [r15+0B4h], eax
0x18002ddee  mov     [rbp+var_30], rbx
  ... truncated ...
```
