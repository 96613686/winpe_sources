# ErrIsamCreateReference(x,x,x,x,x,x,x)

- ea: `0x10029e50`
- end: `0x1002a0b4`
- name: `_ErrIsamCreateReference@28`
- size: `612`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10025ee0`
- `0x10026060`
- `0x100270d0`
- `0x10029e50`
- `0x10056280`
- `0x1005e7e8`

## pseudocode

```c
int __stdcall ErrIsamCreateReference(void *a1, int *a2, int a3, int a4, const WCHAR *a5, _WORD *a6, unsigned int a7)
{
  struct Instance *v7; // eax
  int v8; // ecx
  struct Table *v9; // eax
  unsigned int v10; // ebx
  int v11; // ecx
  int v12; // eax
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  int v15; // ebx
  int v16; // eax
  int v17; // esi
  const unsigned __int16 *v19; // [esp+0h] [ebp-40h]
  unsigned int v20[3]; // [esp+4h] [ebp-3Ch] BYREF
  void *Block; // [esp+10h] [ebp-30h]
  void *v22; // [esp+14h] [ebp-2Ch]
  _DWORD v23[2]; // [esp+18h] [ebp-28h] BYREF
  int v24; // [esp+20h] [ebp-20h]
  void *v25; // [esp+24h] [ebp-1Ch]
  void *v26; // [esp+28h] [ebp-18h]
  struct Table *v27; // [esp+2Ch] [ebp-14h]
  struct Instance *v28; // [esp+30h] [ebp-10h]
  int v29; // [esp+34h] [ebp-Ch]
  int v30; // [esp+38h] [ebp-8h]
  char v31; // [esp+3Fh] [ebp-1h] BYREF

  v23[0] = 1;
  ValidateName(v19, (struct Err *)v20[0]);
  v29 = 0;
  v30 = 0;
  v7 = (struct Instance *)(*(int (__thiscall **)(int *))(*a2 + 56))(a2);
  v8 = *a2;
  v28 = v7;
  v9 = (struct Table *)(*(int (__thiscall **)(int *))(v8 + 60))(a2);
  v10 = a7;
  LOBYTE(v11) = v31 & 0xFE;
  v27 = v9;
  v31 = v31 & 0xFE | a7 & 1;
  if ( (a7 & 0x10000) != 0 )
  {
    v10 = a7 & 0xFFFEFFFF;
    Err::SetWarning((Err *)v23, 5011);
  }
  if ( (v10 & 0xFFFF00FC) != 0 )
    Err::SetError(v23, -1003, v11);
  v12 = v23[0];
  if ( (v23[0] & 8) != 0 )
    goto LABEL_20;
  v13 = v10 & 0xF00;
  if ( v13 < 0x200 )
  {
    if ( (v10 & 0xF00) == 0 )
    {
      v29 = 0;
      goto LABEL_12;
    }
    if ( v13 == 256 )
    {
      v29 = 1;
      goto LABEL_12;
    }
  }
  Err::SetError(v23, -1003, v10 & 0xF00);
  v12 = v23[0];
LABEL_12:
  v14 = v10 & 0xF000;
  if ( v14 < 0x2000 )
  {
    if ( (v10 & 0xF000) == 0 )
    {
      v30 = 0;
      goto LABEL_18;
    }
    if ( v14 == 4096 )
    {
      v30 = 1;
      goto LABEL_18;
    }
  }
  Err::SetError(v23, -1003, v10 & 0xF000);
  v12 = v23[0];
LABEL_18:
  if ( (v10 & 2) != 0 )
  {
    Err::SetError(v23, -1003, v14);
    v12 = v23[0];
LABEL_20:
    v15 = 0;
    goto LABEL_21;
  }
  v15 = 1;
LABEL_21:
  if ( (v12 & 8) == 0 )
  {
    if ( (*(int (__thiscall **)(int *))(*a2 + 72))(a2) != 3 )
    {
      v16 = *a2;
      v20[0] = 1;
      (*(void (__thiscall **)(int *, int, unsigned int *))(v16 + 20))(a2, 3, v20);
      if ( (v20[0] & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v22 )
          operator delete[](v22);
      }
    }
    Table::AddReference(v27, v28, a3, a4, a5, a6, &v31, v29, v30, v15, v23);
    v12 = v23[0];
  }
  if ( (v12 & 1) != 0 )
  {
    v17 = 0;
  }
  else
  {
    if ( (v12 & 8) != 0 && v24 && a1 )
    {
      (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
        *(_DWORD *)(pJetInfoBlock + 44),
        a1,
        v25,
        v26,
        0,
        v24,
        0,
        0,
        0);
      v12 = v23[0];
    }
    v17 = v23[1];
    if ( (v12 & 1) != 0 )
      v17 = 0;
  }
  if ( (v12 & 0xFFFFFFFE) != 0 )
  {
    if ( v25 )
      operator delete[](v25);
    if ( v26 )
      operator delete[](v26);
  }
  return v17;
}

```

## disassembly

```asm
0x10029e50  mov     edi, edi
0x10029e52  push    ebp
0x10029e53  mov     ebp, esp
0x10029e55  sub     esp, 3Ch
0x10029e58  mov     ecx, [ebp+arg_8]
0x10029e5b  lea     edx, [ebp+var_28]
0x10029e5e  push    esi; unsigned __int16 *
0x10029e5f  mov     [ebp+var_28], 1
0x10029e66  call    ?ValidateName@@YGXPBGAAVErr@@@Z; ValidateName(ushort const *,Err &)
0x10029e6b  mov     eax, [ebp+var_28]
0x10029e6e  test    al, 8
0x10029e70  jnz     loc_1002A02E
0x10029e76  push    ebx; unsigned int
0x10029e77  push    edi; void *
0x10029e78  mov     edi, [ebp+arg_4]
0x10029e7b  mov     [ebp+var_C], 0
0x10029e82  mov     [ebp+var_8], 0
0x10029e89  mov     eax, [edi]
0x10029e8b  mov     esi, [eax+38h]
0x10029e8e  mov     ecx, esi
0x10029e90  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029e96  mov     ecx, edi
0x10029e98  call    esi
0x10029e9a  mov     ecx, [edi]
0x10029e9c  mov     [ebp+var_10], eax
0x10029e9f  mov     esi, [ecx+3Ch]
0x10029ea2  mov     ecx, esi
0x10029ea4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029eaa  mov     ecx, edi
0x10029eac  call    esi
0x10029eae  mov     ebx, [ebp+arg_18]
0x10029eb1  mov     dl, bl
0x10029eb3  mov     cl, [ebp+var_1]
0x10029eb6  and     dl, 1
0x10029eb9  and     cl, 0FEh
0x10029ebc  mov     [ebp+var_14], eax
0x10029ebf  or      dl, cl
0x10029ec1  mov     [ebp+var_1], dl
0x10029ec4  test    ebx, 10000h
0x10029eca  jz      short loc_10029EDF
0x10029ecc  push    1393h; int
0x10029ed1  lea     ecx, [ebp+var_28]; this
0x10029ed4  and     ebx, 0FFFEFFFFh
0x10029eda  call    ?SetWarning@Err@@QAEXJ@Z; Err::SetWarning(long)
0x10029edf  test    ebx, 0FFFF00FCh
0x10029ee5  jz      short loc_10029EF5
0x10029ee7  push    ecx
0x10029ee8  push    0FFFFFC15h
0x10029eed  lea     ecx, [ebp+var_28]
0x10029ef0  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10029ef5  mov     eax, [ebp+var_28]
0x10029ef8  test    al, 8
0x10029efa  jnz     loc_10029F9C
0x10029f00  mov     ecx, ebx
0x10029f02  and     ecx, 0F00h
0x10029f08  cmp     ecx, 200h
0x10029f0e  ja      short loc_10029F30
0x10029f10  jz      short loc_10029F30
0x10029f12  test    ecx, ecx
0x10029f14  jz      short loc_10029F27
0x10029f16  cmp     ecx, 100h
0x10029f1c  jnz     short loc_10029F30
0x10029f1e  mov     [ebp+var_C], 1
0x10029f25  jmp     short loc_10029F41
0x10029f27  mov     [ebp+var_C], 0
0x10029f2e  jmp     short loc_10029F41
0x10029f30  push    ecx
0x10029f31  push    0FFFFFC15h
0x10029f36  lea     ecx, [ebp+var_28]
0x10029f39  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10029f3e  mov     eax, [ebp+var_28]
0x10029f41  mov     ecx, ebx
0x10029f43  and     ecx, 0F000h
0x10029f49  cmp     ecx, 2000h
0x10029f4f  ja      short loc_10029F71
0x10029f51  jz      short loc_10029F71
0x10029f53  test    ecx, ecx
0x10029f55  jz      short loc_10029F68
0x10029f57  cmp     ecx, 1000h
0x10029f5d  jnz     short loc_10029F71
0x10029f5f  mov     [ebp+var_8], 1
0x10029f66  jmp     short loc_10029F82
0x10029f68  mov     [ebp+var_8], 0
0x10029f6f  jmp     short loc_10029F82
0x10029f71  push    ecx
0x10029f72  push    0FFFFFC15h
0x10029f77  lea     ecx, [ebp+var_28]
0x10029f7a  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10029f7f  mov     eax, [ebp+var_28]
0x10029f82  test    bl, 2
0x10029f85  jz      loc_1002A036
0x10029f8b  push    ecx
0x10029f8c  push    0FFFFFC15h
0x10029f91  lea     ecx, [ebp+var_28]
0x10029f94  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10029f99  mov     eax, [ebp+var_28]
0x10029f9c  xor     ebx, ebx
0x10029f9e  test    al, 8
0x10029fa0  jnz     loc_1002A02C
0x10029fa6  mov     eax, [edi]
0x10029fa8  mov     esi, [eax+48h]
0x10029fab  mov     ecx, esi
0x10029fad  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029fb3  mov     ecx, edi
0x10029fb5  call    esi
0x10029fb7  cmp     eax, 3
0x10029fba  jz      short loc_1002A003
0x10029fbc  mov     eax, [edi]
0x10029fbe  lea     ecx, [ebp+var_3C]
0x10029fc1  push    ecx; unsigned int
0x10029fc2  push    3; void *
0x10029fc4  mov     [ebp+var_3C], 1
0x10029fcb  mov     esi, [eax+14h]
0x10029fce  mov     ecx, esi
0x10029fd0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029fd6  mov     ecx, edi
0x10029fd8  call    esi
0x10029fda  test    [ebp+var_3C], 0FFFFFFFEh
0x10029fe1  jz      short loc_1002A003
0x10029fe3  mov     eax, [ebp+Block]
0x10029fe6  test    eax, eax
0x10029fe8  jz      short loc_10029FF3
0x10029fea  push    eax; Block
0x10029feb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029ff0  add     esp, 4
0x10029ff3  mov     eax, [ebp+var_2C]
0x10029ff6  test    eax, eax
0x10029ff8  jz      short loc_1002A003
0x10029ffa  push    eax; Block
0x10029ffb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002a000  add     esp, 4
0x1002a003  mov     ecx, [ebp+var_14]
0x1002a006  lea     eax, [ebp+var_28]
0x1002a009  push    eax
0x1002a00a  push    ebx
0x1002a00b  push    [ebp+var_8]
0x1002a00e  lea     eax, [ebp+var_1]
0x1002a011  push    [ebp+var_C]
0x1002a014  push    eax
0x1002a015  push    [ebp+arg_14]
0x1002a018  push    [ebp+arg_10]
0x1002a01b  push    [ebp+arg_C]
0x1002a01e  push    [ebp+arg_8]
0x1002a021  push    [ebp+var_10]
0x1002a024  call    ?AddReference@Table@@QAEXPAVInstance@@PBG1PAG1PAUtagTblIdxDef@@W4IdxRefUpdate@@W4IdxRefDelete@@W4IdxRefEnforce@@AAVErr@@@Z; Table::AddReference(Instance *,ushort const *,ushort const *,ushort *,ushort const *,tagTblIdxDef *,IdxRefUpdate,IdxRefDelete,IdxRefEnforce,Err &)
0x1002a029  mov     eax, [ebp+var_28]
0x1002a02c  pop     edi
0x1002a02d  pop     ebx
0x1002a02e  test    al, 1
0x1002a030  jz      short loc_1002A040
0x1002a032  xor     esi, esi
0x1002a034  jmp     short loc_1002A084
0x1002a036  mov     ebx, 1
0x1002a03b  jmp     loc_10029F9E
0x1002a040  test    al, 8
0x1002a042  jz      short loc_1002A077
0x1002a044  mov     edx, [ebp+var_20]
0x1002a047  test    edx, edx
0x1002a049  jz      short loc_1002A077
0x1002a04b  mov     ecx, [ebp+arg_0]
0x1002a04e  test    ecx, ecx
0x1002a050  jz      short loc_1002A077
0x1002a052  mov     eax, _pJetInfoBlock
0x1002a057  push    0
0x1002a059  push    0
0x1002a05b  push    0
0x1002a05d  mov     esi, [eax+2Ch]
0x1002a060  push    edx
0x1002a061  push    0
0x1002a063  push    [ebp+var_18]
0x1002a066  push    [ebp+var_1C]; unsigned int
0x1002a069  push    ecx; void *
0x1002a06a  mov     ecx, esi
0x1002a06c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002a072  call    esi
0x1002a074  mov     eax, [ebp+var_28]
0x1002a077  mov     esi, [ebp+var_24]
0x1002a07a  test    al, 1
0x1002a07c  mov     ecx, 0
0x1002a081  cmovnz  esi, ecx
0x1002a084  test    eax, 0FFFFFFFEh
0x1002a089  jz      short loc_1002A0AB
0x1002a08b  mov     eax, [ebp+var_1C]
0x1002a08e  test    eax, eax
0x1002a090  jz      short loc_1002A09B
0x1002a092  push    eax; Block
0x1002a093  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002a098  add     esp, 4
0x1002a09b  mov     eax, [ebp+var_18]
0x1002a09e  test    eax, eax
0x1002a0a0  jz      short loc_1002A0AB
0x1002a0a2  push    eax; Block
0x1002a0a3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002a0a8  add     esp, 4
0x1002a0ab  mov     eax, esi
0x1002a0ad  pop     esi
0x1002a0ae  mov     esp, ebp
0x1002a0b0  pop     ebp
0x1002a0b1  retn    1Ch
```
