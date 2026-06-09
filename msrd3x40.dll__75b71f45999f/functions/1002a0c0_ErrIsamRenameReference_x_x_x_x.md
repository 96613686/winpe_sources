# ErrIsamRenameReference(x,x,x,x)

- ea: `0x1002a0c0`
- end: `0x1002a1fc`
- name: `_ErrIsamRenameReference@16`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x100270d0`
- `0x1002a0c0`
- `0x10055bc0`
- `0x1005e7e8`

## pseudocode

```c
int __stdcall ErrIsamRenameReference(void *a1, int *a2, char *a3, const unsigned __int16 *a4)
{
  struct Instance *v4; // ebx
  _DWORD *v5; // eax
  int v6; // ecx
  int v7; // eax
  int v8; // ebx
  void *v9; // edi
  void *v10; // ecx
  int v11; // esi
  const unsigned __int16 *v13; // [esp+0h] [ebp-38h]
  struct Err *v14; // [esp+4h] [ebp-34h]
  unsigned int v15[3]; // [esp+Ch] [ebp-2Ch] BYREF
  void *Block; // [esp+18h] [ebp-20h]
  void *v17; // [esp+1Ch] [ebp-1Ch]
  _DWORD v18[2]; // [esp+20h] [ebp-18h] BYREF
  int v19; // [esp+28h] [ebp-10h]
  void *v20; // [esp+2Ch] [ebp-Ch]
  void *v21; // [esp+30h] [ebp-8h]
  _DWORD *v22; // [esp+34h] [ebp-4h]

  v18[0] = 1;
  ValidateName(v13, v14);
  v4 = (struct Instance *)(*(int (__thiscall **)(int *))(*a2 + 56))(a2);
  v5 = (_DWORD *)(*(int (__thiscall **)(int *))(*a2 + 60))(a2);
  v6 = *a2;
  v22 = v5;
  if ( (*(int (__thiscall **)(int *))(v6 + 72))(a2) != 3 )
  {
    v7 = *a2;
    v15[0] = 1;
    (*(void (__thiscall **)(int *, int, unsigned int *))(v7 + 20))(a2, 3, v15);
    if ( (v15[0] & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v17 )
        operator delete[](v17);
    }
  }
  Table::RenameIndex(v22, v4, a3, a4, (struct Err *)v18, 1);
  v8 = v18[0];
  v9 = v21;
  v10 = v20;
  if ( (v18[0] & 1) != 0 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v18[0] & 8) != 0 && v19 && a1 )
    {
      (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
        *(_DWORD *)(pJetInfoBlock + 44),
        a1,
        v20,
        v21,
        0,
        v19,
        0,
        0,
        0);
      v10 = v20;
    }
    v11 = v18[1];
  }
  if ( (v8 & 0xFFFFFFFE) != 0 )
  {
    if ( v10 )
      operator delete[](v10);
    if ( v9 )
      operator delete[](v9);
  }
  return v11;
}

```

## disassembly

```asm
0x1002a0c0  mov     edi, edi
0x1002a0c2  push    ebp
0x1002a0c3  mov     ebp, esp
0x1002a0c5  sub     esp, 2Ch
0x1002a0c8  mov     ecx, [ebp+arg_C]
0x1002a0cb  lea     edx, [ebp+var_18]
0x1002a0ce  push    ebx
0x1002a0cf  push    esi; unsigned int
0x1002a0d0  push    edi; void *
0x1002a0d1  mov     [ebp+var_18], 1
0x1002a0d8  call    ?ValidateName@@YGXPBGAAVErr@@@Z; ValidateName(ushort const *,Err &)
0x1002a0dd  mov     ebx, [ebp+var_18]
0x1002a0e0  test    bl, 8
0x1002a0e3  jnz     loc_1002A188
0x1002a0e9  mov     edi, [ebp+arg_4]
0x1002a0ec  mov     eax, [edi]
0x1002a0ee  mov     esi, [eax+38h]
0x1002a0f1  mov     ecx, esi
0x1002a0f3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002a0f9  mov     ecx, edi
0x1002a0fb  call    esi
0x1002a0fd  mov     ecx, [edi]
0x1002a0ff  mov     ebx, eax
0x1002a101  mov     esi, [ecx+3Ch]
0x1002a104  mov     ecx, esi
0x1002a106  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002a10c  mov     ecx, edi
0x1002a10e  call    esi
0x1002a110  mov     ecx, [edi]
0x1002a112  mov     [ebp+var_4], eax
0x1002a115  mov     esi, [ecx+48h]
0x1002a118  mov     ecx, esi
0x1002a11a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002a120  mov     ecx, edi
0x1002a122  call    esi
0x1002a124  cmp     eax, 3
0x1002a127  jz      short loc_1002A170
0x1002a129  mov     eax, [edi]
0x1002a12b  lea     ecx, [ebp+var_2C]
0x1002a12e  push    ecx; unsigned int
0x1002a12f  push    3; void *
0x1002a131  mov     [ebp+var_2C], 1
0x1002a138  mov     esi, [eax+14h]
0x1002a13b  mov     ecx, esi
0x1002a13d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002a143  mov     ecx, edi
0x1002a145  call    esi
0x1002a147  test    [ebp+var_2C], 0FFFFFFFEh
0x1002a14e  jz      short loc_1002A170
0x1002a150  mov     eax, [ebp+Block]
0x1002a153  test    eax, eax
0x1002a155  jz      short loc_1002A160
0x1002a157  push    eax; Block
0x1002a158  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002a15d  add     esp, 4
0x1002a160  mov     eax, [ebp+var_1C]
0x1002a163  test    eax, eax
0x1002a165  jz      short loc_1002A170
0x1002a167  push    eax; Block
0x1002a168  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002a16d  add     esp, 4
0x1002a170  mov     ecx, [ebp+var_4]
0x1002a173  lea     eax, [ebp+var_18]
0x1002a176  push    1
0x1002a178  push    eax
0x1002a179  push    [ebp+arg_C]
0x1002a17c  push    [ebp+arg_8]
0x1002a17f  push    ebx
0x1002a180  call    ?RenameIndex@Table@@QAEXPAVInstance@@PBG1AAVErr@@W4TblRefOrIdx@@@Z; Table::RenameIndex(Instance *,ushort const *,ushort const *,Err &,TblRefOrIdx)
0x1002a185  mov     ebx, [ebp+var_18]
0x1002a188  mov     edi, [ebp+var_8]
0x1002a18b  mov     ecx, [ebp+var_C]
0x1002a18e  test    bl, 1
0x1002a191  jz      short loc_1002A197
0x1002a193  xor     esi, esi
0x1002a195  jmp     short loc_1002A1CF
0x1002a197  test    bl, 8
0x1002a19a  jz      short loc_1002A1CC
0x1002a19c  cmp     [ebp+var_10], 0
0x1002a1a0  jz      short loc_1002A1CC
0x1002a1a2  mov     edx, [ebp+arg_0]
0x1002a1a5  test    edx, edx
0x1002a1a7  jz      short loc_1002A1CC
0x1002a1a9  mov     eax, _pJetInfoBlock
0x1002a1ae  push    0
0x1002a1b0  push    0
0x1002a1b2  push    0
0x1002a1b4  push    [ebp+var_10]
0x1002a1b7  mov     esi, [eax+2Ch]
0x1002a1ba  push    0
0x1002a1bc  push    edi
0x1002a1bd  push    ecx; unsigned int
0x1002a1be  push    edx; void *
0x1002a1bf  mov     ecx, esi
0x1002a1c1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002a1c7  call    esi
0x1002a1c9  mov     ecx, [ebp+var_C]
0x1002a1cc  mov     esi, [ebp+var_14]
0x1002a1cf  test    ebx, 0FFFFFFFEh
0x1002a1d5  jz      short loc_1002A1F1
0x1002a1d7  test    ecx, ecx
0x1002a1d9  jz      short loc_1002A1E4
0x1002a1db  push    ecx; Block
0x1002a1dc  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002a1e1  add     esp, 4
0x1002a1e4  test    edi, edi
0x1002a1e6  jz      short loc_1002A1F1
0x1002a1e8  push    edi; Block
0x1002a1e9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002a1ee  add     esp, 4
0x1002a1f1  pop     edi
0x1002a1f2  mov     eax, esi
0x1002a1f4  pop     esi
0x1002a1f5  pop     ebx
0x1002a1f6  mov     esp, ebp
0x1002a1f8  pop     ebp
0x1002a1f9  retn    10h
```
