# ErrIsamRenameIndex(x,x,x,x)

- ea: `0x10029b70`
- end: `0x10029cc0`
- name: `_ErrIsamRenameIndex@16`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10025ee0`
- `0x100270d0`
- `0x10029b70`
- `0x10055bc0`
- `0x1005e7e8`

## pseudocode

```c
int __stdcall ErrIsamRenameIndex(void *a1, int *a2, char *a3, const unsigned __int16 *a4)
{
  struct Instance *v4; // ebx
  int v5; // ecx
  int v6; // eax
  int v7; // ebx
  void *v8; // edi
  void *v9; // ecx
  int v10; // esi
  const unsigned __int16 *v12; // [esp+0h] [ebp-38h]
  struct Err *v13; // [esp+4h] [ebp-34h]
  unsigned int v14[3]; // [esp+Ch] [ebp-2Ch] BYREF
  void *Block; // [esp+18h] [ebp-20h]
  void *v16; // [esp+1Ch] [ebp-1Ch]
  _DWORD v17[2]; // [esp+20h] [ebp-18h] BYREF
  int v18; // [esp+28h] [ebp-10h]
  void *v19; // [esp+2Ch] [ebp-Ch]
  void *v20; // [esp+30h] [ebp-8h]
  _DWORD *v21; // [esp+34h] [ebp-4h]

  v17[0] = 1;
  ValidateName(v12, v13);
  v4 = (struct Instance *)(*(int (__thiscall **)(int *))(*a2 + 56))(a2);
  v21 = (_DWORD *)(*(int (__thiscall **)(int *))(*a2 + 60))(a2);
  if ( v4 )
  {
    if ( (*(int (__thiscall **)(int *))(*a2 + 72))(a2) != 3 )
    {
      v6 = *a2;
      v14[0] = 1;
      (*(void (__thiscall **)(int *, int, unsigned int *))(v6 + 20))(a2, 3, v14);
      if ( (v14[0] & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v16 )
          operator delete[](v16);
      }
    }
    Table::RenameIndex(v21, v4, a3, a4, (struct Err *)v17, 0);
  }
  else
  {
    Err::SetError(v17, -1906, v5);
  }
  v7 = v17[0];
  v8 = v20;
  v9 = v19;
  if ( (v17[0] & 1) != 0 )
  {
    v10 = 0;
  }
  else
  {
    if ( (v17[0] & 8) != 0 && v18 && a1 )
    {
      (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
        *(_DWORD *)(pJetInfoBlock + 44),
        a1,
        v19,
        v20,
        0,
        v18,
        0,
        0,
        0);
      v9 = v19;
    }
    v10 = v17[1];
  }
  if ( (v7 & 0xFFFFFFFE) != 0 )
  {
    if ( v9 )
      operator delete[](v9);
    if ( v8 )
      operator delete[](v8);
  }
  return v10;
}

```

## disassembly

```asm
0x10029b70  mov     edi, edi
0x10029b72  push    ebp
0x10029b73  mov     ebp, esp
0x10029b75  sub     esp, 2Ch
0x10029b78  mov     ecx, [ebp+arg_C]
0x10029b7b  lea     edx, [ebp+var_18]
0x10029b7e  push    ebx
0x10029b7f  push    esi; unsigned int
0x10029b80  push    edi; void *
0x10029b81  mov     [ebp+var_18], 1
0x10029b88  call    ?ValidateName@@YGXPBGAAVErr@@@Z; ValidateName(ushort const *,Err &)
0x10029b8d  mov     ebx, [ebp+var_18]
0x10029b90  test    bl, 8
0x10029b93  jnz     loc_10029C4C
0x10029b99  mov     edi, [ebp+arg_4]
0x10029b9c  mov     eax, [edi]
0x10029b9e  mov     esi, [eax+38h]
0x10029ba1  mov     ecx, esi
0x10029ba3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029ba9  mov     ecx, edi
0x10029bab  call    esi
0x10029bad  mov     ecx, [edi]
0x10029baf  mov     ebx, eax
0x10029bb1  mov     esi, [ecx+3Ch]
0x10029bb4  mov     ecx, esi
0x10029bb6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029bbc  mov     ecx, edi
0x10029bbe  call    esi
0x10029bc0  mov     [ebp+var_4], eax
0x10029bc3  test    ebx, ebx
0x10029bc5  jnz     short loc_10029BD7
0x10029bc7  push    ecx
0x10029bc8  push    0FFFFF88Eh
0x10029bcd  lea     ecx, [ebp+var_18]
0x10029bd0  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10029bd5  jmp     short loc_10029C49
0x10029bd7  mov     eax, [edi]
0x10029bd9  mov     esi, [eax+48h]
0x10029bdc  mov     ecx, esi
0x10029bde  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029be4  mov     ecx, edi
0x10029be6  call    esi
0x10029be8  cmp     eax, 3
0x10029beb  jz      short loc_10029C34
0x10029bed  mov     eax, [edi]
0x10029bef  lea     ecx, [ebp+var_2C]
0x10029bf2  push    ecx; unsigned int
0x10029bf3  push    3; void *
0x10029bf5  mov     [ebp+var_2C], 1
0x10029bfc  mov     esi, [eax+14h]
0x10029bff  mov     ecx, esi
0x10029c01  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029c07  mov     ecx, edi
0x10029c09  call    esi
0x10029c0b  test    [ebp+var_2C], 0FFFFFFFEh
0x10029c12  jz      short loc_10029C34
0x10029c14  mov     eax, [ebp+Block]
0x10029c17  test    eax, eax
0x10029c19  jz      short loc_10029C24
0x10029c1b  push    eax; Block
0x10029c1c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029c21  add     esp, 4
0x10029c24  mov     eax, [ebp+var_1C]
0x10029c27  test    eax, eax
0x10029c29  jz      short loc_10029C34
0x10029c2b  push    eax; Block
0x10029c2c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029c31  add     esp, 4
0x10029c34  mov     ecx, [ebp+var_4]
0x10029c37  lea     eax, [ebp+var_18]
0x10029c3a  push    0
0x10029c3c  push    eax
0x10029c3d  push    [ebp+arg_C]
0x10029c40  push    [ebp+arg_8]
0x10029c43  push    ebx
0x10029c44  call    ?RenameIndex@Table@@QAEXPAVInstance@@PBG1AAVErr@@W4TblRefOrIdx@@@Z; Table::RenameIndex(Instance *,ushort const *,ushort const *,Err &,TblRefOrIdx)
0x10029c49  mov     ebx, [ebp+var_18]
0x10029c4c  mov     edi, [ebp+var_8]
0x10029c4f  mov     ecx, [ebp+var_C]
0x10029c52  test    bl, 1
0x10029c55  jz      short loc_10029C5B
0x10029c57  xor     esi, esi
0x10029c59  jmp     short loc_10029C93
0x10029c5b  test    bl, 8
0x10029c5e  jz      short loc_10029C90
0x10029c60  cmp     [ebp+var_10], 0
0x10029c64  jz      short loc_10029C90
0x10029c66  mov     edx, [ebp+arg_0]
0x10029c69  test    edx, edx
0x10029c6b  jz      short loc_10029C90
0x10029c6d  mov     eax, _pJetInfoBlock
0x10029c72  push    0
0x10029c74  push    0
0x10029c76  push    0
0x10029c78  push    [ebp+var_10]
0x10029c7b  mov     esi, [eax+2Ch]
0x10029c7e  push    0
0x10029c80  push    edi
0x10029c81  push    ecx; unsigned int
0x10029c82  push    edx; void *
0x10029c83  mov     ecx, esi
0x10029c85  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029c8b  call    esi
0x10029c8d  mov     ecx, [ebp+var_C]
0x10029c90  mov     esi, [ebp+var_14]
0x10029c93  test    ebx, 0FFFFFFFEh
0x10029c99  jz      short loc_10029CB5
0x10029c9b  test    ecx, ecx
0x10029c9d  jz      short loc_10029CA8
0x10029c9f  push    ecx; Block
0x10029ca0  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029ca5  add     esp, 4
0x10029ca8  test    edi, edi
0x10029caa  jz      short loc_10029CB5
0x10029cac  push    edi; Block
0x10029cad  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029cb2  add     esp, 4
0x10029cb5  pop     edi
0x10029cb6  mov     eax, esi
0x10029cb8  pop     esi
0x10029cb9  pop     ebx
0x10029cba  mov     esp, ebp
0x10029cbc  pop     ebp
0x10029cbd  retn    10h
```
