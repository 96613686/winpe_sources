# ErrIsamCreateIndex(x,x,x,x,x,x,x)

- ea: `0x100299d0`
- end: `0x10029b68`
- name: `_ErrIsamCreateIndex@28`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x100270d0`
- `0x100299d0`
- `0x10055260`
- `0x1005e7e8`

## pseudocode

```c
int __stdcall ErrIsamCreateIndex(void *a1, int *a2, int a3, char a4, int a5, int a6, int a7)
{
  int v7; // eax
  int v8; // ecx
  char v9; // cl
  int v10; // eax
  int v11; // eax
  int v12; // esi
  const unsigned __int16 *v14; // [esp+0h] [ebp-38h]
  unsigned int v15[3]; // [esp+4h] [ebp-34h] BYREF
  void *Block; // [esp+10h] [ebp-28h]
  void *v17; // [esp+14h] [ebp-24h]
  _DWORD v18[2]; // [esp+18h] [ebp-20h] BYREF
  int v19; // [esp+20h] [ebp-18h]
  void *v20; // [esp+24h] [ebp-14h]
  void *v21; // [esp+28h] [ebp-10h]
  int v22; // [esp+2Ch] [ebp-Ch]
  int v23; // [esp+30h] [ebp-8h]
  char v24; // [esp+37h] [ebp-1h] BYREF

  v18[0] = 1;
  ValidateName(v14, (struct Err *)v15[0]);
  v7 = (*(int (__thiscall **)(int *))(*a2 + 56))(a2);
  v8 = *a2;
  v23 = v7;
  v22 = (*(int (__thiscall **)(int *))(v8 + 60))(a2);
  v9 = v24 & 0xE2 | a4 & 1 | (4 * (((a4 & 8) != 0) | (2 * (((a4 & 0x10) != 0) | (2 * ((a4 & 4) != 0)))))) | 0x13;
  if ( (a4 & 2) == 0 )
    v9 = v24 & 0xE0 | a4 & 1 | (4 * (((a4 & 8) != 0) | (2 * (((a4 & 0x10) != 0) | (2 * ((a4 & 4) != 0))))));
  v24 = v9;
  if ( (*(int (__thiscall **)(int *))(*a2 + 72))(a2) != 3 )
  {
    v10 = *a2;
    v15[0] = 1;
    (*(void (__thiscall **)(int *, int, unsigned int *))(v10 + 20))(a2, 3, v15);
    if ( (v15[0] & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v17 )
        operator delete[](v17);
    }
  }
  Table::AddIndex(v22, v23, a3, &v24, a5, a7, v18, 0);
  v11 = v18[0];
  if ( (v18[0] & 1) != 0 )
  {
    v12 = 0;
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
      v11 = v18[0];
    }
    v12 = v18[1];
    if ( (v11 & 1) != 0 )
      v12 = 0;
  }
  if ( (v11 & 0xFFFFFFFE) != 0 )
  {
    if ( v20 )
      operator delete[](v20);
    if ( v21 )
      operator delete[](v21);
  }
  return v12;
}

```

## disassembly

```asm
0x100299d0  mov     edi, edi
0x100299d2  push    ebp
0x100299d3  mov     ebp, esp
0x100299d5  sub     esp, 34h
0x100299d8  mov     ecx, [ebp+arg_8]
0x100299db  lea     edx, [ebp+var_20]
0x100299de  push    esi; unsigned int
0x100299df  mov     [ebp+var_20], 1
0x100299e6  call    ?ValidateName@@YGXPBGAAVErr@@@Z; ValidateName(ushort const *,Err &)
0x100299eb  mov     eax, [ebp+var_20]
0x100299ee  test    al, 8
0x100299f0  jnz     loc_10029AEC
0x100299f6  push    ebx; void *
0x100299f7  mov     ebx, [ebp+arg_4]
0x100299fa  mov     eax, [ebx]
0x100299fc  mov     esi, [eax+38h]
0x100299ff  mov     ecx, esi
0x10029a01  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029a07  mov     ecx, ebx
0x10029a09  call    esi
0x10029a0b  mov     ecx, [ebx]
0x10029a0d  mov     [ebp+var_8], eax
0x10029a10  mov     esi, [ecx+3Ch]
0x10029a13  mov     ecx, esi
0x10029a15  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029a1b  mov     ecx, ebx
0x10029a1d  call    esi
0x10029a1f  mov     ebx, [ebp+arg_C]
0x10029a22  mov     edx, ebx
0x10029a24  shr     edx, 2
0x10029a27  mov     ecx, ebx
0x10029a29  mov     [ebp+var_C], eax
0x10029a2c  and     dl, 1
0x10029a2f  add     dl, dl
0x10029a31  shr     ecx, 4
0x10029a34  and     cl, 1
0x10029a37  mov     eax, ebx
0x10029a39  or      dl, cl
0x10029a3b  shr     eax, 3
0x10029a3e  and     al, 1
0x10029a40  add     dl, dl
0x10029a42  or      dl, al
0x10029a44  mov     al, bl
0x10029a46  and     al, 1
0x10029a48  shl     dl, 2
0x10029a4b  or      dl, al
0x10029a4d  mov     al, [ebp+var_1]
0x10029a50  and     al, 0E2h
0x10029a52  or      dl, al
0x10029a54  mov     al, dl
0x10029a56  or      dl, 13h
0x10029a59  and     al, 0FDh
0x10029a5b  movzx   ecx, dl
0x10029a5e  test    bl, 2
0x10029a61  movzx   eax, al
0x10029a64  mov     ebx, [ebp+arg_4]
0x10029a67  cmovz   ecx, eax
0x10029a6a  mov     [ebp+var_1], cl
0x10029a6d  mov     eax, [ebx]
0x10029a6f  mov     esi, [eax+48h]
0x10029a72  mov     ecx, esi
0x10029a74  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029a7a  mov     ecx, ebx
0x10029a7c  call    esi
0x10029a7e  cmp     eax, 3
0x10029a81  jz      short loc_10029ACA
0x10029a83  mov     eax, [ebx]
0x10029a85  lea     ecx, [ebp+var_34]
0x10029a88  push    ecx; unsigned int
0x10029a89  push    3; void *
0x10029a8b  mov     [ebp+var_34], 1
0x10029a92  mov     esi, [eax+14h]
0x10029a95  mov     ecx, esi
0x10029a97  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029a9d  mov     ecx, ebx
0x10029a9f  call    esi
0x10029aa1  test    [ebp+var_34], 0FFFFFFFEh
0x10029aa8  jz      short loc_10029ACA
0x10029aaa  mov     eax, [ebp+Block]
0x10029aad  test    eax, eax
0x10029aaf  jz      short loc_10029ABA
0x10029ab1  push    eax; Block
0x10029ab2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029ab7  add     esp, 4
0x10029aba  mov     eax, [ebp+var_24]
0x10029abd  test    eax, eax
0x10029abf  jz      short loc_10029ACA
0x10029ac1  push    eax; Block
0x10029ac2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029ac7  add     esp, 4
0x10029aca  mov     ecx, [ebp+var_C]
0x10029acd  lea     eax, [ebp+var_20]
0x10029ad0  push    0
0x10029ad2  push    eax
0x10029ad3  push    [ebp+arg_18]
0x10029ad6  lea     eax, [ebp+var_1]
0x10029ad9  push    [ebp+arg_10]
0x10029adc  push    eax
0x10029add  push    [ebp+arg_8]
0x10029ae0  push    [ebp+var_8]
0x10029ae3  call    ?AddIndex@Table@@QAEPAVIndex@@PAVInstance@@PBGPAUtagTblIdxDef@@1IAAVErr@@W4TblRefOrIdx@@@Z; Table::AddIndex(Instance *,ushort const *,tagTblIdxDef *,ushort const *,uint,Err &,TblRefOrIdx)
0x10029ae8  mov     eax, [ebp+var_20]
0x10029aeb  pop     ebx
0x10029aec  test    al, 1
0x10029aee  jz      short loc_10029AF4
0x10029af0  xor     esi, esi
0x10029af2  jmp     short loc_10029B38
0x10029af4  test    al, 8
0x10029af6  jz      short loc_10029B2B
0x10029af8  mov     edx, [ebp+var_18]
0x10029afb  test    edx, edx
0x10029afd  jz      short loc_10029B2B
0x10029aff  mov     ecx, [ebp+arg_0]
0x10029b02  test    ecx, ecx
0x10029b04  jz      short loc_10029B2B
0x10029b06  mov     eax, _pJetInfoBlock
0x10029b0b  push    0
0x10029b0d  push    0
0x10029b0f  push    0
0x10029b11  mov     esi, [eax+2Ch]
0x10029b14  push    edx
0x10029b15  push    0
0x10029b17  push    [ebp+var_10]
0x10029b1a  push    [ebp+var_14]; unsigned int
0x10029b1d  push    ecx; void *
0x10029b1e  mov     ecx, esi
0x10029b20  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029b26  call    esi
0x10029b28  mov     eax, [ebp+var_20]
0x10029b2b  mov     esi, [ebp+var_1C]
0x10029b2e  test    al, 1
0x10029b30  mov     ecx, 0
0x10029b35  cmovnz  esi, ecx
0x10029b38  test    eax, 0FFFFFFFEh
0x10029b3d  jz      short loc_10029B5F
0x10029b3f  mov     eax, [ebp+var_14]
0x10029b42  test    eax, eax
0x10029b44  jz      short loc_10029B4F
0x10029b46  push    eax; Block
0x10029b47  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029b4c  add     esp, 4
0x10029b4f  mov     eax, [ebp+var_10]
0x10029b52  test    eax, eax
0x10029b54  jz      short loc_10029B5F
0x10029b56  push    eax; Block
0x10029b57  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029b5c  add     esp, 4
0x10029b5f  mov     eax, esi
0x10029b61  pop     esi
0x10029b62  mov     esp, ebp
0x10029b64  pop     ebp
0x10029b65  retn    1Ch
```
