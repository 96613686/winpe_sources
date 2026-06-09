# ErrIsamRenameColumn(x,x,x,x)

- ea: `0x10029600`
- end: `0x10029744`
- name: `_ErrIsamRenameColumn@16`
- size: `324`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x100270d0`
- `0x10029600`
- `0x10054c30`
- `0x1005e7e8`

## pseudocode

```c
int __stdcall ErrIsamRenameColumn(void *a1, int *a2, unsigned __int16 *a3, unsigned __int16 *Src)
{
  struct Instance *v4; // eax
  int v5; // ecx
  Table *v6; // eax
  int v7; // ecx
  int v8; // eax
  int v9; // eax
  int v10; // esi
  const unsigned __int16 *v12; // [esp+0h] [ebp-34h]
  unsigned int v13[3]; // [esp+4h] [ebp-30h] BYREF
  void *Block; // [esp+10h] [ebp-24h]
  void *v15; // [esp+14h] [ebp-20h]
  _DWORD v16[2]; // [esp+18h] [ebp-1Ch] BYREF
  int v17; // [esp+20h] [ebp-14h]
  void *v18; // [esp+24h] [ebp-10h]
  void *v19; // [esp+28h] [ebp-Ch]
  Table *v20; // [esp+2Ch] [ebp-8h]
  struct Instance *v21; // [esp+30h] [ebp-4h]

  v16[0] = 1;
  ValidateName(v12, (struct Err *)v13[0]);
  v4 = (struct Instance *)(*(int (__thiscall **)(int *))(*a2 + 56))(a2);
  v5 = *a2;
  v21 = v4;
  v6 = (Table *)(*(int (__thiscall **)(int *))(v5 + 60))(a2);
  v7 = *a2;
  v20 = v6;
  if ( (*(int (__thiscall **)(int *))(v7 + 72))(a2) != 3 )
  {
    v8 = *a2;
    v13[0] = 1;
    (*(void (__thiscall **)(int *, int, unsigned int *))(v8 + 20))(a2, 3, v13);
    if ( (v13[0] & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v15 )
        operator delete[](v15);
    }
  }
  Table::RenameColumn(v20, v21, a3, Src, (struct Err *)v16);
  v9 = v16[0];
  if ( (v16[0] & 1) != 0 )
  {
    v10 = 0;
  }
  else
  {
    if ( (v16[0] & 8) != 0 && v17 && a1 )
    {
      (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
        *(_DWORD *)(pJetInfoBlock + 44),
        a1,
        v18,
        v19,
        0,
        v17,
        0,
        0,
        0);
      v9 = v16[0];
    }
    v10 = v16[1];
    if ( (v9 & 1) != 0 )
      v10 = 0;
  }
  if ( (v9 & 0xFFFFFFFE) != 0 )
  {
    if ( v18 )
      operator delete[](v18);
    if ( v19 )
      operator delete[](v19);
  }
  return v10;
}

```

## disassembly

```asm
0x10029600  mov     edi, edi
0x10029602  push    ebp
0x10029603  mov     ebp, esp
0x10029605  sub     esp, 30h
0x10029608  mov     ecx, [ebp+Src]
0x1002960b  lea     edx, [ebp+var_1C]
0x1002960e  push    esi; unsigned int
0x1002960f  mov     [ebp+var_1C], 1
0x10029616  call    ?ValidateName@@YGXPBGAAVErr@@@Z; ValidateName(ushort const *,Err &)
0x1002961b  mov     eax, [ebp+var_1C]
0x1002961e  test    al, 8
0x10029620  jnz     loc_100296C8
0x10029626  push    edi; void *
0x10029627  mov     edi, [ebp+arg_4]
0x1002962a  mov     eax, [edi]
0x1002962c  mov     esi, [eax+38h]
0x1002962f  mov     ecx, esi
0x10029631  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029637  mov     ecx, edi
0x10029639  call    esi
0x1002963b  mov     ecx, [edi]
0x1002963d  mov     [ebp+var_4], eax
0x10029640  mov     esi, [ecx+3Ch]
0x10029643  mov     ecx, esi
0x10029645  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002964b  mov     ecx, edi
0x1002964d  call    esi
0x1002964f  mov     ecx, [edi]
0x10029651  mov     [ebp+var_8], eax
0x10029654  mov     esi, [ecx+48h]
0x10029657  mov     ecx, esi
0x10029659  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002965f  mov     ecx, edi
0x10029661  call    esi
0x10029663  cmp     eax, 3
0x10029666  jz      short loc_100296AF
0x10029668  mov     eax, [edi]
0x1002966a  lea     ecx, [ebp+var_30]
0x1002966d  push    ecx; unsigned int
0x1002966e  push    3; void *
0x10029670  mov     [ebp+var_30], 1
0x10029677  mov     esi, [eax+14h]
0x1002967a  mov     ecx, esi
0x1002967c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029682  mov     ecx, edi
0x10029684  call    esi
0x10029686  test    [ebp+var_30], 0FFFFFFFEh
0x1002968d  jz      short loc_100296AF
0x1002968f  mov     eax, [ebp+Block]
0x10029692  test    eax, eax
0x10029694  jz      short loc_1002969F
0x10029696  push    eax; Block
0x10029697  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002969c  add     esp, 4
0x1002969f  mov     eax, [ebp+var_20]
0x100296a2  test    eax, eax
0x100296a4  jz      short loc_100296AF
0x100296a6  push    eax; Block
0x100296a7  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100296ac  add     esp, 4
0x100296af  mov     ecx, [ebp+var_8]; this
0x100296b2  lea     eax, [ebp+var_1C]
0x100296b5  push    eax; struct Err *
0x100296b6  push    [ebp+Src]; Src
0x100296b9  push    [ebp+arg_8]; unsigned __int16 *
0x100296bc  push    [ebp+var_4]; struct Instance *
0x100296bf  call    ?RenameColumn@Table@@QAEXPAVInstance@@PBG1AAVErr@@@Z; Table::RenameColumn(Instance *,ushort const *,ushort const *,Err &)
0x100296c4  mov     eax, [ebp+var_1C]
0x100296c7  pop     edi
0x100296c8  test    al, 1
0x100296ca  jz      short loc_100296D0
0x100296cc  xor     esi, esi
0x100296ce  jmp     short loc_10029714
0x100296d0  test    al, 8
0x100296d2  jz      short loc_10029707
0x100296d4  mov     edx, [ebp+var_14]
0x100296d7  test    edx, edx
0x100296d9  jz      short loc_10029707
0x100296db  mov     ecx, [ebp+arg_0]
0x100296de  test    ecx, ecx
0x100296e0  jz      short loc_10029707
0x100296e2  mov     eax, _pJetInfoBlock
0x100296e7  push    0
0x100296e9  push    0
0x100296eb  push    0
0x100296ed  mov     esi, [eax+2Ch]
0x100296f0  push    edx
0x100296f1  push    0
0x100296f3  push    [ebp+var_C]
0x100296f6  push    [ebp+var_10]; unsigned int
0x100296f9  push    ecx; void *
0x100296fa  mov     ecx, esi
0x100296fc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029702  call    esi
0x10029704  mov     eax, [ebp+var_1C]
0x10029707  mov     esi, [ebp+var_18]
0x1002970a  test    al, 1
0x1002970c  mov     ecx, 0
0x10029711  cmovnz  esi, ecx
0x10029714  test    eax, 0FFFFFFFEh
0x10029719  jz      short loc_1002973B
0x1002971b  mov     eax, [ebp+var_10]
0x1002971e  test    eax, eax
0x10029720  jz      short loc_1002972B
0x10029722  push    eax; Block
0x10029723  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029728  add     esp, 4
0x1002972b  mov     eax, [ebp+var_C]
0x1002972e  test    eax, eax
0x10029730  jz      short loc_1002973B
0x10029732  push    eax; Block
0x10029733  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10029738  add     esp, 4
0x1002973b  mov     eax, esi
0x1002973d  pop     esi
0x1002973e  mov     esp, ebp
0x10029740  pop     ebp
0x10029741  retn    10h
```
