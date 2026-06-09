# ErrIsamOpenTempTable(x,x,x,x,x,x)

- ea: `0x1002bf00`
- end: `0x1002c22b`
- name: `_ErrIsamOpenTempTable@24`
- size: `811`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x1002bf00`
- `0x10044e20`
- `0x10046a10`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f450`

## pseudocode

```c
void *__stdcall ErrIsamOpenTempTable(
        Session *a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        _DWORD *a5,
        unsigned int *a6)
{
  void *v6; // esp
  int v7; // eax
  int v8; // edx
  unsigned int *v9; // ecx
  unsigned int v10; // esi
  unsigned int v13; // eax
  int v14; // edx
  unsigned __int16 v15; // ax
  int v16; // edx
  int v17; // eax
  bool v18; // sf
  __int16 v19; // cx
  unsigned int *v20; // eax
  unsigned __int8 v21; // al
  unsigned int v22; // eax
  __int16 v23; // ax
  struct Cursor *v24; // eax
  unsigned int v25; // ecx
  struct Cursor *v26; // edi
  void *v27; // esi
  unsigned int v29[3]; // [esp+0h] [ebp-4Ch] BYREF
  void *Block[4]; // [esp+Ch] [ebp-40h] BYREF
  void *v31; // [esp+1Ch] [ebp-30h]
  int v32; // [esp+20h] [ebp-2Ch]
  int v33; // [esp+24h] [ebp-28h] BYREF
  __int16 v34; // [esp+28h] [ebp-24h]
  unsigned int v35; // [esp+2Ch] [ebp-20h]
  unsigned int *v36; // [esp+30h] [ebp-1Ch]
  char v37; // [esp+34h] [ebp-18h]
  unsigned int v38; // [esp+38h] [ebp-14h]
  int v39; // [esp+3Ch] [ebp-10h]
  int v40; // [esp+44h] [ebp-8h]

  Block[0] = (void *)1;
  v6 = alloca(36 * a3);
  v7 = 0;
  v8 = 0;
  v9 = v29;
  v32 = 0;
  v10 = 0;
  v36 = v29;
  v40 = 0;
  if ( !a3 )
    goto LABEL_23;
  while ( 1 )
  {
    v13 = *(_DWORD *)(a2 + 8);
    if ( v13 >= 0x10 )
      break;
    v14 = 9 * v10;
    LOBYTE(v9[v14]) = byte_10003C00[v13];
    v36[v14 + 1] = *(_DWORD *)(a2 + 16);
    LOBYTE(v36[v14 + 2]) = (*(_BYTE *)(a2 + 20) & 1) == 0;
    v36[v14 + 3] = 1;
    v36[v14 + 4] = *(_DWORD *)(a2 + 12);
    v15 = Collate::CodePageFromLocale(v29[0]);
    *(unsigned int *)((char *)v36 + v16 + 20) = v15;
    *((_BYTE *)v36 + v16 + 28) &= ~1u;
    *((_BYTE *)v36 + v16 + 28) &= ~2u;
    *((_BYTE *)v36 + v16 + 28) &= ~4u;
    *((_BYTE *)v36 + v16 + 28) &= ~8u;
    *((_BYTE *)v36 + v16 + 28) &= ~0x10u;
    *((_BYTE *)v36 + v16 + 28) &= ~0x20u;
    *((_BYTE *)v36 + v16 + 28) |= 0x40u;
    *((_BYTE *)v36 + v16 + 29) &= ~1u;
    *((_BYTE *)v36 + v16 + 28) |= 0x80u;
    *((_BYTE *)v36 + v16 + 29) &= ~2u;
    *((_BYTE *)v36 + v16 + 29) &= ~4u;
    *(unsigned int *)((char *)v36 + v16 + 24) = 0;
    v17 = *(_DWORD *)(a2 + 20);
    if ( (v17 & 0x40) != 0 )
    {
      v18 = (v17 & 0x80u) != 0;
      v19 = 43;
      v20 = v36;
      if ( v18 )
        v19 = 45;
      ++v32;
    }
    else
    {
      v20 = v36;
      v19 = 32;
    }
    *(_WORD *)((char *)v20 + v16 + 32) = v19;
    v9 = v36;
    v21 = *((_BYTE *)v36 + v16);
    if ( v21 == 12 || v21 == 11 )
      v8 = ++v40;
    else
      v8 = v40;
    a2 += 24;
    v22 = v10 + (v21 << 24);
    ++v10;
    *a6++ = v22;
    if ( v10 >= a3 )
      goto LABEL_21;
  }
  if ( (int)Block[0] < 8 )
  {
    if ( ((int)Block[0] & 0xFFFFFFFE) != 0 )
    {
      if ( Block[3] )
        operator delete[](Block[3]);
      if ( v31 )
        operator delete[](v31);
    }
    v8 = v40;
    *(_OWORD *)Block = _xmm;
    v31 = 0;
  }
LABEL_21:
  v7 = v32;
  if ( !v32 || (v33 = 6, v8) )
LABEL_23:
    v33 = 5;
  v35 = a3;
  v38 = v38 & 0xFFFFFFF0 | (a4 >> 2) & 1 | (2 * ((a4 >> 3) & 1 | (2 * (a4 & 1 | (v7 != 0 ? 2 : 0)))));
  if ( (a4 & 4) != 0 )
  {
    if ( (a4 & 1) != 0 )
      v23 = 93;
    else
      v23 = 91;
  }
  else
  {
    v23 = 32;
  }
  v34 = v23;
  v39 = 0;
  v37 = v37 & 0xE0 | ((a4 & 2) != 0);
  v24 = Session::OpenTempTable(a1, &v33, (struct Err *)Block);
  v25 = (unsigned int)Block[0];
  v26 = v24;
  if ( ((int)Block[0] & 8) == 0 )
  {
    if ( (*(int (__thiscall **)(_DWORD, Session *, _DWORD *, struct Cursor *, char *))(pJetInfoBlock + 36))(
           *(_DWORD *)(pJetInfoBlock + 36),
           a1,
           a5,
           v24,
           &vtfndefIsam) >= 0 )
    {
      (*(void (__thiscall **)(struct Cursor *, _DWORD))(*(_DWORD *)v26 + 88))(v26, *a5);
    }
    else if ( v26 )
    {
      (**(void (__thiscall ***)(struct Cursor *, int))v26)(v26, 1);
    }
    v25 = (unsigned int)Block[0];
  }
  if ( (v25 & 1) != 0 )
  {
    v27 = 0;
  }
  else
  {
    if ( (v25 & 8) != 0 && Block[2] && a1 )
    {
      (*(void (__thiscall **)(_DWORD, Session *, void *, void *, _DWORD, void *, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
        *(_DWORD *)(pJetInfoBlock + 44),
        a1,
        Block[3],
        v31,
        0,
        Block[2],
        0,
        0,
        0);
      v25 = (unsigned int)Block[0];
    }
    v27 = Block[1];
    if ( (v25 & 1) != 0 )
      v27 = 0;
  }
  if ( (v25 & 0xFFFFFFFE) != 0 )
  {
    if ( Block[3] )
      operator delete[](Block[3]);
    if ( v31 )
      operator delete[](v31);
  }
  return v27;
}

```

## disassembly

```asm
0x1002bf00  mov     edi, edi
0x1002bf02  push    ebp
0x1002bf03  mov     ebp, esp
0x1002bf05  sub     esp, 40h
0x1002bf08  mov     eax, ___security_cookie
0x1002bf0d  xor     eax, ebp
0x1002bf0f  mov     [ebp+var_4], eax
0x1002bf12  push    ebx
0x1002bf13  mov     ebx, [ebp+arg_8]
0x1002bf16  push    esi
0x1002bf17  push    edi; unsigned int
0x1002bf18  mov     [ebp+Block], 1
0x1002bf1f  lea     eax, [ebx+ebx*8]
0x1002bf22  shl     eax, 2
0x1002bf25  call    __alloca_probe_16
0x1002bf2a  xor     eax, eax
0x1002bf2c  xor     edx, edx
0x1002bf2e  mov     ecx, esp
0x1002bf30  mov     [ebp+var_2C], eax
0x1002bf33  xor     esi, esi
0x1002bf35  mov     [ebp+var_1C], ecx
0x1002bf38  mov     [ebp+var_8], edx
0x1002bf3b  test    ebx, ebx
0x1002bf3d  jz      loc_1002C0C4
0x1002bf43  mov     ebx, [ebp+arg_14]
0x1002bf46  mov     edi, [ebp+arg_4]
0x1002bf49  nop     dword ptr [eax+00000000h]
0x1002bf50  mov     eax, [edi+8]
0x1002bf53  cmp     eax, 10h
0x1002bf56  jnb     loc_1002C06E
0x1002bf5c  mov     al, ds:byte_10003C00[eax]
0x1002bf62  lea     edx, [esi+esi*8]
0x1002bf65  shl     edx, 2
0x1002bf68  mov     [edx+ecx], al
0x1002bf6b  mov     eax, [ebp+var_1C]
0x1002bf6e  mov     ecx, [edi+10h]
0x1002bf71  mov     [edx+eax+4], ecx
0x1002bf75  mov     cl, [edi+14h]
0x1002bf78  mov     eax, [ebp+var_1C]
0x1002bf7b  not     cl
0x1002bf7d  and     cl, 1
0x1002bf80  mov     [edx+eax+8], cl
0x1002bf84  mov     eax, [ebp+var_1C]
0x1002bf87  mov     dword ptr [edx+eax+0Ch], 1
0x1002bf8f  mov     eax, [ebp+var_1C]
0x1002bf92  mov     ecx, [edi+0Ch]
0x1002bf95  mov     [edx+eax+10h], ecx
0x1002bf99  mov     ecx, [edi+0Ch]
0x1002bf9c  call    ?CodePageFromLocale@Collate@@SGGK@Z; Collate::CodePageFromLocale(ulong)
0x1002bfa1  movzx   ecx, ax
0x1002bfa4  mov     eax, [ebp+var_1C]
0x1002bfa7  mov     [edx+eax+14h], ecx
0x1002bfab  mov     eax, [ebp+var_1C]
0x1002bfae  and     byte ptr [edx+eax+1Ch], 0FEh
0x1002bfb3  mov     eax, [ebp+var_1C]
0x1002bfb6  and     byte ptr [edx+eax+1Ch], 0FDh
0x1002bfbb  mov     eax, [ebp+var_1C]
0x1002bfbe  and     byte ptr [edx+eax+1Ch], 0FBh
0x1002bfc3  mov     eax, [ebp+var_1C]
0x1002bfc6  and     byte ptr [edx+eax+1Ch], 0F7h
0x1002bfcb  mov     eax, [ebp+var_1C]
0x1002bfce  and     byte ptr [edx+eax+1Ch], 0EFh
0x1002bfd3  mov     eax, [ebp+var_1C]
0x1002bfd6  and     byte ptr [edx+eax+1Ch], 0DFh
0x1002bfdb  mov     eax, [ebp+var_1C]
0x1002bfde  or      byte ptr [edx+eax+1Ch], 40h
0x1002bfe3  mov     eax, [ebp+var_1C]
0x1002bfe6  and     byte ptr [edx+eax+1Dh], 0FEh
0x1002bfeb  mov     eax, [ebp+var_1C]
0x1002bfee  or      byte ptr [edx+eax+1Ch], 80h
0x1002bff3  mov     eax, [ebp+var_1C]
0x1002bff6  and     byte ptr [edx+eax+1Dh], 0FDh
0x1002bffb  mov     eax, [ebp+var_1C]
0x1002bffe  and     byte ptr [edx+eax+1Dh], 0FBh
0x1002c003  mov     eax, [ebp+var_1C]
0x1002c006  mov     dword ptr [edx+eax+18h], 0
0x1002c00e  mov     eax, [edi+14h]
0x1002c011  test    al, 40h
0x1002c013  jz      short loc_1002C02B
0x1002c015  test    al, al
0x1002c017  mov     ecx, 2Bh ; '+'
0x1002c01c  mov     eax, [ebp+var_1C]
0x1002c01f  jns     short loc_1002C026
0x1002c021  mov     ecx, 2Dh ; '-'
0x1002c026  inc     [ebp+var_2C]
0x1002c029  jmp     short loc_1002C033
0x1002c02b  mov     eax, [ebp+var_1C]
0x1002c02e  mov     ecx, 20h ; ' '
0x1002c033  mov     [edx+eax+20h], cx
0x1002c038  mov     ecx, [ebp+var_1C]
0x1002c03b  mov     al, [edx+ecx]
0x1002c03e  cmp     al, 0Ch
0x1002c040  jz      short loc_1002C046
0x1002c042  cmp     al, 0Bh
0x1002c044  jnz     short loc_1002C04F
0x1002c046  mov     edx, [ebp+var_8]
0x1002c049  inc     edx
0x1002c04a  mov     [ebp+var_8], edx
0x1002c04d  jmp     short loc_1002C052
0x1002c04f  mov     edx, [ebp+var_8]
0x1002c052  movzx   eax, al
0x1002c055  add     edi, 18h
0x1002c058  shl     eax, 18h
0x1002c05b  add     eax, esi
0x1002c05d  inc     esi
0x1002c05e  mov     [ebx], eax
0x1002c060  add     ebx, 4
0x1002c063  cmp     esi, [ebp+arg_8]
0x1002c066  jb      loc_1002BF50
0x1002c06c  jmp     short loc_1002C0B2
0x1002c06e  mov     eax, [ebp+Block]
0x1002c071  cmp     eax, 8
0x1002c074  jge     short loc_1002C0B2
0x1002c076  test    eax, 0FFFFFFFEh
0x1002c07b  jz      short loc_1002C09D
0x1002c07d  mov     eax, [ebp+Block+0Ch]
0x1002c080  test    eax, eax
0x1002c082  jz      short loc_1002C08D
0x1002c084  push    eax; Block
0x1002c085  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002c08a  add     esp, 4
0x1002c08d  mov     eax, [ebp+var_30]
0x1002c090  test    eax, eax
0x1002c092  jz      short loc_1002C09D
0x1002c094  push    eax; Block
0x1002c095  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002c09a  add     esp, 4
0x1002c09d  movaps  xmm0, ds:__xmm@0000000000000000fffffa1900000008
0x1002c0a4  mov     edx, [ebp+var_8]
0x1002c0a7  movups  xmmword ptr [ebp+Block], xmm0
0x1002c0ab  mov     [ebp+var_30], 0
0x1002c0b2  mov     eax, [ebp+var_2C]
0x1002c0b5  test    eax, eax
0x1002c0b7  jz      short loc_1002C0C4
0x1002c0b9  mov     [ebp+var_28], 6
0x1002c0c0  test    edx, edx
0x1002c0c2  jz      short loc_1002C0CB
0x1002c0c4  mov     [ebp+var_28], 5
0x1002c0cb  mov     edx, [ebp+arg_C]
0x1002c0ce  mov     esi, edx
0x1002c0d0  mov     ecx, [ebp+arg_8]
0x1002c0d3  and     esi, 1
0x1002c0d6  mov     [ebp+var_20], ecx
0x1002c0d9  xor     ecx, ecx
0x1002c0db  cmp     ecx, eax
0x1002c0dd  mov     eax, edx
0x1002c0df  sbb     ecx, ecx
0x1002c0e1  shr     eax, 3
0x1002c0e4  and     ecx, 2
0x1002c0e7  and     eax, 1
0x1002c0ea  or      ecx, esi
0x1002c0ec  add     ecx, ecx
0x1002c0ee  or      ecx, eax
0x1002c0f0  mov     eax, edx
0x1002c0f2  shr     eax, 2
0x1002c0f5  add     ecx, ecx
0x1002c0f7  and     eax, 1
0x1002c0fa  or      ecx, eax
0x1002c0fc  mov     eax, [ebp+var_14]
0x1002c0ff  and     eax, 0FFFFFFF0h
0x1002c102  or      ecx, eax
0x1002c104  mov     [ebp+var_14], ecx
0x1002c107  test    dl, 4
0x1002c10a  jz      short loc_1002C11E
0x1002c10c  test    esi, esi
0x1002c10e  jz      short loc_1002C117
0x1002c110  mov     eax, 5Dh ; ']'
0x1002c115  jmp     short loc_1002C123
0x1002c117  mov     eax, 5Bh ; '['
0x1002c11c  jmp     short loc_1002C123
0x1002c11e  mov     eax, 20h ; ' '
0x1002c123  mov     ebx, [ebp+arg_0]
0x1002c126  mov     ecx, ebx; this
0x1002c128  mov     [ebp+var_24], ax
0x1002c12c  mov     al, [ebp+var_18]
0x1002c12f  shr     edx, 1
0x1002c131  and     al, 0E0h
0x1002c133  and     dl, 1
0x1002c136  mov     [ebp+var_10], 0
0x1002c13d  or      dl, al
0x1002c13f  lea     eax, [ebp+Block]
0x1002c142  push    eax; struct Err *
0x1002c143  lea     eax, [ebp+var_28]
0x1002c146  mov     [ebp+var_18], dl
0x1002c149  push    eax; void *
0x1002c14a  call    ?OpenTempTable@Session@@QAEPAVCursor@@PAXAAVErr@@@Z; Session::OpenTempTable(void *,Err &)
0x1002c14f  mov     ecx, [ebp+Block]
0x1002c152  mov     edi, eax
0x1002c154  test    cl, 8
0x1002c157  jnz     short loc_1002C19F
0x1002c159  mov     ecx, _pJetInfoBlock
0x1002c15f  push    offset _vtfndefIsam
0x1002c164  push    edi
0x1002c165  push    [ebp+arg_10]; unsigned int
0x1002c168  mov     esi, [ecx+24h]
0x1002c16b  mov     ecx, esi
0x1002c16d  push    ebx; void *
0x1002c16e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002c174  call    esi
0x1002c176  test    eax, eax
0x1002c178  jns     short loc_1002C186
0x1002c17a  test    edi, edi
0x1002c17c  jz      short loc_1002C19C
0x1002c17e  mov     eax, [edi]
0x1002c180  push    1
0x1002c182  mov     esi, [eax]
0x1002c184  jmp     short loc_1002C190
0x1002c186  mov     eax, [edi]
0x1002c188  mov     ecx, [ebp+arg_10]
0x1002c18b  mov     esi, [eax+58h]
0x1002c18e  push    dword ptr [ecx]; void *
0x1002c190  mov     ecx, esi
0x1002c192  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002c198  mov     ecx, edi
0x1002c19a  call    esi
0x1002c19c  mov     ecx, [ebp+Block]
0x1002c19f  test    cl, 1
0x1002c1a2  jz      short loc_1002C1A8
0x1002c1a4  xor     esi, esi
0x1002c1a6  jmp     short loc_1002C1EB
0x1002c1a8  test    cl, 8
0x1002c1ab  jz      short loc_1002C1DD
0x1002c1ad  mov     edx, [ebp+Block+8]
0x1002c1b0  test    edx, edx
0x1002c1b2  jz      short loc_1002C1DD
0x1002c1b4  test    ebx, ebx
0x1002c1b6  jz      short loc_1002C1DD
0x1002c1b8  mov     eax, _pJetInfoBlock
0x1002c1bd  push    0
0x1002c1bf  push    0
0x1002c1c1  push    0
0x1002c1c3  mov     esi, [eax+2Ch]
0x1002c1c6  mov     ecx, esi
0x1002c1c8  push    edx
0x1002c1c9  push    0
0x1002c1cb  push    [ebp+var_30]
0x1002c1ce  push    [ebp+Block+0Ch]; unsigned int
0x1002c1d1  push    ebx; void *
0x1002c1d2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002c1d8  call    esi
0x1002c1da  mov     ecx, [ebp+Block]
0x1002c1dd  mov     esi, [ebp+Block+4]
0x1002c1e0  test    cl, 1
0x1002c1e3  mov     eax, 0
0x1002c1e8  cmovnz  esi, eax
0x1002c1eb  test    ecx, 0FFFFFFFEh
0x1002c1f1  jz      short loc_1002C213
0x1002c1f3  mov     eax, [ebp+Block+0Ch]
0x1002c1f6  test    eax, eax
0x1002c1f8  jz      short loc_1002C203
0x1002c1fa  push    eax; Block
0x1002c1fb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002c200  add     esp, 4
0x1002c203  mov     eax, [ebp+var_30]
0x1002c206  test    eax, eax
0x1002c208  jz      short loc_1002C213
0x1002c20a  push    eax; Block
0x1002c20b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002c210  add     esp, 4
0x1002c213  mov     eax, esi
0x1002c215  lea     esp, [ebp-4Ch]
0x1002c218  pop     edi
0x1002c219  pop     esi
0x1002c21a  pop     ebx
0x1002c21b  mov     ecx, [ebp+var_4]
0x1002c21e  xor     ecx, ebp; StackCookie
0x1002c220  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002c225  mov     esp, ebp
0x1002c227  pop     ebp
0x1002c228  retn    18h
```
