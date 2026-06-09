# GenADTG::SaveColumnData(ushort,ADTGTOKENTYPEENUM,unsigned __int64 *,uchar *)

- ea: `0x180007838`
- end: `0x180007b28`
- name: `?SaveColumnData@GenADTG@@AEAAXGW4ADTGTOKENTYPEENUM@@PEA_KPEAE@Z`
- size: `752`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180008b90`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x1800028b8`
- `0x180003c38`
- `0x180004384`
- `0x180007838`
- `0x180009678`
- `0x18001b008`
- `0x18002dca4`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180007a0e`
- `KERNEL32!MultiByteToWideChar` at `0x180007a0e`

## pseudocode

```c
void __fastcall GenADTG::SaveColumnData(__int64 a1, unsigned __int16 a2, unsigned int a3, _QWORD *a4, __int64 a5)
{
  __int64 v5; // r10
  __int64 v7; // rdi
  __int64 v9; // rbx
  unsigned int v10; // ecx
  int v11; // eax
  const CHAR *v12; // r14
  unsigned __int16 v13; // dx
  __int64 v14; // r10
  int v15; // r11d
  unsigned __int64 v16; // r15
  unsigned int cchWideChar; // edi
  unsigned int v18; // ecx
  const unsigned __int8 *v19; // rdx
  unsigned int v20; // r8d
  __int16 v21; // cx
  unsigned __int128 v22; // rax
  unsigned __int8 *v23; // rax
  WCHAR *lpWideCharStr; // rbx
  unsigned __int16 v25; // ax
  unsigned __int16 v26; // ax
  bool v27; // zf
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  char v35; // [rsp+78h] [rbp+48h] BYREF
  unsigned int v36; // [rsp+80h] [rbp+50h] BYREF

  v36 = a3;
  v5 = *(_QWORD *)(a1 + 56);
  v7 = a5;
  v9 = 88LL * a2;
  v35 = 0;
  v36 = 0;
  v10 = *(_DWORD *)(*(unsigned int *)(v9 + v5 + 24) + a5);
  if ( v10 <= 0xD )
  {
    v11 = 8209;
    if ( _bittest(&v11, v10) )
    {
      v12 = (const CHAR *)(a5 + *(unsigned int *)(v9 + v5 + 8));
      if ( (*(_WORD *)(v9 + v5 + 84) & 0x4000) != 0 )
        v12 = *(const CHAR **)v12;
      if ( (CMetaData::mdGetFlags((CMetaData *)(a1 + 128), *(_WORD *)(v9 + v5) - 1) & 0x2000) == 0
        && CMetaData::mdGetType((CMetaData *)(a1 + 128), v13) != 136 )
      {
        v16 = (unsigned int)(v15 + 1);
        if ( ((unsigned __int8)(v15 + 1) & *(_BYTE *)(v9 + v14 + 56)) != 0 )
        {
          v18 = *(_DWORD *)(v7 + *(_QWORD *)(v9 + v14 + 16));
          v36 = v18;
          if ( (*(_WORD *)(v9 + v14 + 84) & 0x4000) != 0 )
          {
            v20 = 4;
            v19 = (const unsigned __int8 *)&v36;
          }
          else
          {
            if ( v18 > 0xFF )
            {
              v19 = (const unsigned __int8 *)&v36;
              v15 = 4;
            }
            else
            {
              v35 = v18;
              v19 = (const unsigned __int8 *)&v35;
            }
            v20 = v15;
          }
          GenADTG::SaveToBuffer((GenADTG *)a1, v19, v20);
          cchWideChar = v36;
        }
        else
        {
          cchWideChar = *(_DWORD *)(v9 + v14 + 72);
          v36 = cchWideChar;
          if ( *(_WORD *)(v9 + v14 + 84) == 129 )
          {
            --cchWideChar;
LABEL_12:
            v36 = cchWideChar;
            goto LABEL_20;
          }
          if ( *(_WORD *)(v9 + v14 + 84) == 130 )
          {
            cchWideChar -= 2;
            goto LABEL_12;
          }
        }
LABEL_20:
        v21 = *(_WORD *)(v9 + *(_QWORD *)(a1 + 56) + 84) & 0xBFFF;
        if ( g_fUnicode && v21 == 129 )
        {
          if ( cchWideChar > *(_DWORD *)(a1 + 272) )
          {
            operator delete(*(unsigned __int8 **)(a1 + 264));
            if ( cchWideChar < 0x10000 )
              cchWideChar = (cchWideChar & 0xFFFFFF00) + 256;
            v22 = cchWideChar * (unsigned __int128)v16;
            if ( !is_mul_ok(cchWideChar, v16) )
              LODWORD(v22) = -1;
            v23 = MMMAlloc(v22, DWORD2(v22));
            *(_QWORD *)(a1 + 264) = v23;
            OnNullThrowOOM(v23);
            *(_DWORD *)(a1 + 272) = cchWideChar;
            cchWideChar = v36;
          }
          lpWideCharStr = *(WCHAR **)(a1 + 264);
          v25 = MultiByteToWideChar(0, 0, v12, cchWideChar, lpWideCharStr, cchWideChar);
          v12 = (const CHAR *)lpWideCharStr;
          cchWideChar = 2 * v25;
          v36 = cchWideChar;
          goto LABEL_29;
        }
        if ( v21 == 12 )
        {
          if ( (*(_WORD *)v12 & 0xF000) != 0 )
            v26 = -1;
          else
            v26 = *(_WORD *)v12;
          if ( v26 > 0xBu )
          {
            if ( v26 != 14 )
            {
              v28 = v26 - 14 - v16;
              if ( v28 )
              {
                v29 = v28 - 1;
                if ( v29 )
                {
                  v30 = v29 - 1;
                  if ( v30 )
                  {
                    v31 = v30 - 1;
                    if ( v31 )
                    {
                      v32 = v31 - 1;
                      if ( v32 )
                      {
                        v33 = v32 - 1;
                        if ( v33 )
                        {
                          v34 = v33 - 1;
                          if ( v34 )
                          {
                            v27 = v34 == 1;
LABEL_54:
                            if ( !v27 )
                            {
                              if ( ((unsigned __int8)v16 & (unsigned __int8)bidGblFlags) != 0 && off_1800494D8[0] )
                                bidTraceW(off_1800491C0[0], 2302976, off_1800494D8[0], 2147749405LL, 2249);
                              ThrowHR(-2147217891);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          else if ( v26 != 11 && v26 && v26 != 1 && v26 != 2 && v26 != 3 && v26 != 4 && v26 != 5 && v26 != 6 && v26 != 7 )
          {
            v27 = v26 == 10;
            goto LABEL_54;
          }
        }
LABEL_29:
        GenADTG::SaveToBuffer((GenADTG *)a1, (const unsigned __int8 *)v12, cchWideChar);
        return;
      }
      *a4 = *(_QWORD *)v12;
    }
  }
}

```

## disassembly

```asm
0x180007838  mov     [rsp-38h+arg_0], rbx
0x18000783d  mov     [rsp-38h+arg_10], r8d
0x180007842  push    rbp
0x180007843  push    rsi
0x180007844  push    rdi
0x180007845  push    r12
0x180007847  push    r13
0x180007849  push    r14
0x18000784b  push    r15
0x18000784d  mov     rbp, rsp
0x180007850  sub     rsp, 30h
0x180007854  mov     r10, [rcx+38h]
0x180007858  mov     rsi, rcx
0x18000785b  mov     rdi, [rbp+arg_20]
0x18000785f  mov     r15, r9
0x180007862  movzx   eax, dx
0x180007865  imul    rbx, rax, 58h ; 'X'
0x180007869  mov     [rbp+arg_8], 0
0x18000786d  mov     [rbp+arg_10], 0
0x180007874  mov     eax, [rbx+r10+18h]
0x180007879  mov     ecx, [rax+rdi]
0x18000787c  cmp     ecx, 0Dh
0x18000787f  ja      loc_180007B12
0x180007885  mov     eax, 2011h
0x18000788a  bt      eax, ecx
0x18000788d  jnb     loc_180007B12
0x180007893  mov     r14d, [rbx+r10+8]
0x180007898  mov     eax, 4000h
0x18000789d  add     r14, rdi
0x1800078a0  test    [rbx+r10+54h], ax
0x1800078a6  jz      short loc_1800078AB
0x1800078a8  mov     r14, [r14]
0x1800078ab  movzx   eax, word ptr [rbx+r10]
0x1800078b0  lea     r13, [rsi+80h]
0x1800078b7  mov     r11d, 1
0x1800078bd  mov     rcx, r13; this
0x1800078c0  sub     ax, r11w
0x1800078c4  movzx   edx, ax; unsigned __int16
0x1800078c7  movzx   r12d, ax
0x1800078cb  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x1800078d0  bt      eax, 0Dh
0x1800078d4  jb      loc_180007B0C
0x1800078da  mov     rcx, r13; this
0x1800078dd  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x1800078e2  mov     ecx, 88h
0x1800078e7  cmp     ax, cx
0x1800078ea  jz      loc_180007B0C
0x1800078f0  lea     r15d, [r11+1]
0x1800078f4  lea     r12d, [rcx-7]
0x1800078f8  test    [rbx+r10+38h], r15b
0x1800078fd  jnz     short loc_180007928
0x1800078ff  mov     edi, [rbx+r10+48h]
0x180007904  mov     [rbp+arg_10], edi
0x180007907  cmp     [rbx+r10+54h], r12w
0x18000790d  jnz     short loc_180007913
0x18000790f  dec     edi
0x180007911  jmp     short loc_180007923
0x180007913  mov     eax, 82h
0x180007918  cmp     [rbx+r10+54h], ax
0x18000791e  jnz     short loc_180007975
0x180007920  add     edi, 0FFFFFFFEh
0x180007923  mov     [rbp+arg_10], edi
0x180007926  jmp     short loc_180007975
0x180007928  mov     rax, [rbx+r10+10h]
0x18000792d  mov     ecx, [rdi+rax]
0x180007930  mov     eax, 4000h
0x180007935  mov     [rbp+arg_10], ecx
0x180007938  test    [rbx+r10+54h], ax
0x18000793e  jnz     short loc_180007960
0x180007940  cmp     ecx, 0FFh
0x180007946  ja      short loc_180007951
0x180007948  mov     [rbp+arg_8], cl
0x18000794b  lea     rdx, [rbp+arg_8]
0x18000794f  jmp     short loc_18000795B
0x180007951  lea     rdx, [rbp+arg_10]
0x180007955  mov     r11d, 4
0x18000795b  mov     r8d, r11d
0x18000795e  jmp     short loc_18000796A
0x180007960  mov     r8d, 4; unsigned int
0x180007966  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x18000796a  mov     rcx, rsi; this
0x18000796d  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007972  mov     edi, [rbp+arg_10]
0x180007975  mov     rax, [rsi+38h]
0x180007979  mov     ecx, 0BFFFh
0x18000797e  and     cx, [rbx+rax+54h]
0x180007983  cmp     cs:?g_fUnicode@@3HA, 0; int g_fUnicode
0x18000798a  jz      loc_180007A38
0x180007990  cmp     cx, r12w
0x180007994  jnz     loc_180007A38
0x18000799a  cmp     edi, [rsi+110h]
0x1800079a0  jbe     short loc_1800079F4
0x1800079a2  mov     rcx, [rsi+108h]; void *
0x1800079a9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800079ae  cmp     edi, 10000h
0x1800079b4  jnb     short loc_1800079C2
0x1800079b6  and     edi, 0FFFFFF00h
0x1800079bc  add     edi, 100h
0x1800079c2  mov     ecx, edi
0x1800079c4  mov     rax, r15
0x1800079c7  mul     rcx
0x1800079ca  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800079d1  cmovb   rax, rcx
0x1800079d5  mov     ecx, eax; unsigned int
0x1800079d7  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800079dc  mov     rcx, rax; void *
0x1800079df  mov     [rsi+108h], rax
0x1800079e6  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800079eb  mov     [rsi+110h], edi
0x1800079f1  mov     edi, [rbp+arg_10]
0x1800079f4  mov     rbx, [rsi+108h]
0x1800079fb  mov     r9d, edi; cbMultiByte
0x1800079fe  mov     [rsp+30h+cchWideChar], edi; cchWideChar
0x180007a02  mov     r8, r14; lpMultiByteStr
0x180007a05  xor     edx, edx; dwFlags
0x180007a07  mov     [rsp+30h+lpWideCharStr], rbx; lpWideCharStr
0x180007a0c  xor     ecx, ecx; CodePage
0x180007a0e  call    cs:__imp_MultiByteToWideChar
0x180007a15  nop     dword ptr [rax+rax+00h]
0x180007a1a  movzx   edi, ax
0x180007a1d  mov     r14, rbx
0x180007a20  add     edi, edi
0x180007a22  mov     [rbp+arg_10], edi
0x180007a25  mov     r8d, edi; unsigned int
0x180007a28  mov     rdx, r14; unsigned __int8 *
0x180007a2b  mov     rcx, rsi; this
0x180007a2e  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180007a33  jmp     loc_180007B12
0x180007a38  cmp     cx, 0Ch
0x180007a3c  jnz     short loc_180007A25
0x180007a3e  mov     eax, 0F000h
0x180007a43  test    [r14], ax
0x180007a47  jz      short loc_180007A50
0x180007a49  mov     eax, 0FFFFh
0x180007a4e  jmp     short loc_180007A54
0x180007a50  movzx   eax, word ptr [r14]
0x180007a54  movzx   ecx, ax
0x180007a57  cmp     ecx, 0Bh
0x180007a5a  ja      short loc_180007A8A
0x180007a5c  jz      short loc_180007A25
0x180007a5e  test    ecx, ecx
0x180007a60  jz      short loc_180007A25
0x180007a62  sub     ecx, 1
0x180007a65  jz      short loc_180007A25
0x180007a67  sub     ecx, 1
0x180007a6a  jz      short loc_180007A25
0x180007a6c  sub     ecx, 1
0x180007a6f  jz      short loc_180007A25
0x180007a71  sub     ecx, 1
0x180007a74  jz      short loc_180007A25
0x180007a76  sub     ecx, 1
0x180007a79  jz      short loc_180007A25
0x180007a7b  sub     ecx, 1
0x180007a7e  jz      short loc_180007A25
0x180007a80  sub     ecx, 1
0x180007a83  jz      short loc_180007A25
0x180007a85  cmp     ecx, 3
0x180007a88  jmp     short loc_180007AC1
0x180007a8a  sub     ecx, 0Eh
0x180007a8d  jz      short loc_180007A25
0x180007a8f  sub     ecx, r15d
0x180007a92  jz      short loc_180007A25
0x180007a94  sub     ecx, 1
0x180007a97  jz      short loc_180007A25
0x180007a99  sub     ecx, 1
0x180007a9c  jz      short loc_180007A25
0x180007a9e  sub     ecx, 1
0x180007aa1  jz      short loc_180007A25
0x180007aa3  sub     ecx, 1
0x180007aa6  jz      loc_180007A25
0x180007aac  sub     ecx, 1
0x180007aaf  jz      loc_180007A25
0x180007ab5  sub     ecx, 1
0x180007ab8  jz      loc_180007A25
0x180007abe  cmp     ecx, 1
0x180007ac1  jz      loc_180007A25
0x180007ac7  test    byte ptr cs:_bidGblFlags, r15b
0x180007ace  mov     ebx, 80040E1Dh
0x180007ad3  jz      short loc_180007B04
0x180007ad5  mov     rax, cs:off_1800494D8; "<GenADTG::SaveColumnData|ADO|ERR>  HRES"...
0x180007adc  test    rax, rax
0x180007adf  jz      short loc_180007B04
0x180007ae1  mov     r8, cs:off_1800494D8; "<GenADTG::SaveColumnData|ADO|ERR>  HRES"...
0x180007ae8  mov     r9d, ebx
0x180007aeb  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180007af2  mov     edx, 232400h
0x180007af7  mov     dword ptr [rsp+30h+lpWideCharStr], 8C9h
0x180007aff  call    _bidTraceW
0x180007b04  mov     ecx, ebx; int
0x180007b06  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180007b0c  mov     rax, [r14]
0x180007b0f  mov     [r15], rax
0x180007b12  mov     rbx, [rsp+30h+arg_0]
0x180007b17  add     rsp, 30h
0x180007b1b  pop     r15
0x180007b1d  pop     r14
0x180007b1f  pop     r13
0x180007b21  pop     r12
0x180007b23  pop     rdi
0x180007b24  pop     rsi
0x180007b25  pop     rbp
0x180007b26  retn
```
