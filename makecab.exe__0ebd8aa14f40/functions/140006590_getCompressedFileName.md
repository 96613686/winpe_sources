# getCompressedFileName

- ea: `0x140006590`
- end: `0x1400066ec`
- name: `getCompressedFileName`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007e18`

## callees

- `0x140006590`
- `0x140008620`
- `0x140009aac`
- `0x14000dfd8`

## import_xrefs

- `USER32!CharNextExA` at `0x14000665d`
- `USER32!CharNextExA` at `0x14000665d`

## string_xrefs

- `0x1400065ad`: `CompressedFileExtensionChar`

## pseudocode

```c
__int64 __fastcall getCompressedFileName(__int64 a1, LPSTR a2, __int64 a3, const CHAR *a4, __int64 a5)
{
  CHAR v7; // r12
  __int64 JustFileNameAndExt; // r10
  __int64 v9; // rax
  CHAR *v10; // r8
  __int64 v11; // rcx
  LPSTR v12; // rdx
  LPSTR v13; // rax
  unsigned __int64 v14; // rsi
  __int64 v15; // rdi
  CHAR v16; // al
  CHAR *v17; // rbx
  int v18; // eax
  int v19; // edx
  int i; // ecx
  __int64 result; // rax

  v7 = **(_BYTE **)(VarFind(*(_QWORD *)(a1 + 16), "CompressedFileExtensionChar", a5) + 8);
  JustFileNameAndExt = getJustFileNameAndExt(a4);
  if ( JustFileNameAndExt )
  {
    v9 = 2147483646;
    v10 = (CHAR *)JustFileNameAndExt;
    v11 = 256;
    v12 = a2;
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v12++ = *v10++;
      --v9;
      --v11;
    }
    while ( v11 );
    v13 = v12 - 1;
    if ( v11 )
      v13 = v12;
    *v13 = 0;
    if ( v11 )
    {
      v14 = -1;
      v15 = -1;
      do
        ++v15;
      while ( *(_BYTE *)(JustFileNameAndExt + v15) );
      v16 = *a2;
      v17 = &a2[(int)v15];
      while ( v16 )
      {
        if ( v16 == 46 && (unsigned __int8)(a2[1] - 46) > 1u && a2[1] != 92 )
          v17 = a2 + 1;
        a2 = CharNextExA(0, a2, 0);
        v16 = *a2;
      }
      do
        ++v14;
      while ( v17[v14] );
      v18 = v15 + 1;
      if ( v14 >= 3 )
        v18 = v15;
      if ( *v17 )
      {
        v19 = v18;
        for ( i = 0; i < 2; ++i )
        {
          v18 = v19;
          if ( !*v17 )
            break;
          ++v17;
        }
      }
      else if ( *(v17 - 1) != 46 )
      {
        *v17++ = 46;
        ++v18;
      }
      if ( v18 < 256 )
      {
        *v17 = v7;
        result = 1;
        v17[1] = 0;
        return result;
      }
    }
    ErrSet(a5, "File name too long: %1", "%s", a4);
  }
  return 0;
}

```

## disassembly

```asm
0x140006590  push    rbx
0x140006592  push    rsi
0x140006593  push    rdi
0x140006594  push    r12
0x140006596  push    r14
0x140006598  push    r15
0x14000659a  sub     rsp, 28h
0x14000659e  mov     r8, [rsp+58h+arg_20]
0x1400065a6  mov     r14, rdx
0x1400065a9  mov     rcx, [rcx+10h]
0x1400065ad  lea     rdx, aCompressedfile; "CompressedFileExtensionChar"
0x1400065b4  mov     r15, r9
0x1400065b7  call    VarFind
0x1400065bc  mov     rdx, [rsp+58h+arg_20]
0x1400065c4  mov     rcx, [rax+8]
0x1400065c8  mov     r12b, [rcx]
0x1400065cb  mov     rcx, r15; lpCurrentChar
0x1400065ce  call    getJustFileNameAndExt
0x1400065d3  mov     r10, rax
0x1400065d6  test    rax, rax
0x1400065d9  jz      loc_1400066DC
0x1400065df  mov     eax, 7FFFFFFEh
0x1400065e4  mov     r8, r10
0x1400065e7  mov     ecx, 100h
0x1400065ec  mov     rdx, r14
0x1400065ef  test    rax, rax
0x1400065f2  jz      short loc_14000660E
0x1400065f4  mov     r9b, [r8]
0x1400065f7  test    r9b, r9b
0x1400065fa  jz      short loc_14000660E
0x1400065fc  mov     [rdx], r9b
0x1400065ff  inc     r8
0x140006602  inc     rdx
0x140006605  dec     rax
0x140006608  sub     rcx, 1
0x14000660c  jnz     short loc_1400065EF
0x14000660e  test    rcx, rcx
0x140006611  lea     rax, [rdx-1]
0x140006615  cmovnz  rax, rdx
0x140006619  mov     byte ptr [rax], 0
0x14000661c  jz      loc_1400066BE
0x140006622  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140006626  mov     rdi, rsi
0x140006629  inc     rdi
0x14000662c  cmp     byte ptr [r10+rdi], 0
0x140006631  jnz     short loc_140006629
0x140006633  mov     al, [r14]
0x140006636  movsxd  rbx, edi
0x140006639  add     rbx, r14
0x14000663c  jmp     short loc_140006668
0x14000663e  cmp     al, 2Eh ; '.'
0x140006640  jnz     short loc_140006655
0x140006642  lea     rcx, [r14+1]
0x140006646  mov     al, [rcx]
0x140006648  sub     al, 2Eh ; '.'
0x14000664a  cmp     al, 1
0x14000664c  jbe     short loc_140006655
0x14000664e  cmp     byte ptr [rcx], 5Ch ; '\'
0x140006651  cmovnz  rbx, rcx
0x140006655  xor     ecx, ecx; CodePage
0x140006657  xor     r8d, r8d; dwFlags
0x14000665a  mov     rdx, r14; lpCurrentChar
0x14000665d  call    cs:__imp_CharNextExA
0x140006663  mov     r14, rax
0x140006666  mov     al, [rax]
0x140006668  test    al, al
0x14000666a  jnz     short loc_14000663E
0x14000666c  inc     rsi
0x14000666f  cmp     byte ptr [rbx+rsi], 0
0x140006673  jnz     short loc_14000666C
0x140006675  cmp     rsi, 3
0x140006679  lea     eax, [rdi+1]
0x14000667c  cmovnb  eax, edi
0x14000667f  cmp     byte ptr [rbx], 0
0x140006682  jnz     short loc_140006694
0x140006684  cmp     byte ptr [rbx-1], 2Eh ; '.'
0x140006688  jz      short loc_1400066A9
0x14000668a  mov     byte ptr [rbx], 2Eh ; '.'
0x14000668d  inc     rbx
0x140006690  inc     eax
0x140006692  jmp     short loc_1400066A9
0x140006694  mov     edx, eax
0x140006696  xor     ecx, ecx
0x140006698  cmp     byte ptr [rbx], 0
0x14000669b  mov     eax, edx
0x14000669d  jz      short loc_1400066A9
0x14000669f  inc     rbx
0x1400066a2  inc     ecx
0x1400066a4  cmp     ecx, 2
0x1400066a7  jl      short loc_140006698
0x1400066a9  cmp     eax, 100h
0x1400066ae  jge     short loc_1400066BE
0x1400066b0  mov     [rbx], r12b
0x1400066b3  mov     eax, 1
0x1400066b8  mov     byte ptr [rbx+1], 0
0x1400066bc  jmp     short loc_1400066DE
0x1400066be  mov     rcx, [rsp+58h+arg_20]
0x1400066c6  lea     r8, aS_4; "%s"
0x1400066cd  mov     r9, r15
0x1400066d0  lea     rdx, aFileNameTooLon; "File name too long: %1"
0x1400066d7  call    ErrSet
0x1400066dc  xor     eax, eax
0x1400066de  add     rsp, 28h
0x1400066e2  pop     r15
0x1400066e4  pop     r14
0x1400066e6  pop     r12
0x1400066e8  pop     rdi
0x1400066e9  pop     rsi
0x1400066ea  pop     rbx
0x1400066eb  retn
```
