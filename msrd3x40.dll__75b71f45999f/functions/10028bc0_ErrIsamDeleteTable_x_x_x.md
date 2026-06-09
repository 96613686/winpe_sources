# ErrIsamDeleteTable(x,x,x)

- ea: `0x10028bc0`
- end: `0x10028d23`
- name: `_ErrIsamDeleteTable@12`
- size: `355`
- prototype: `int __stdcall(void *, Instance *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10028bc0`
- `0x10037190`
- `0x10037b10`
- `0x1005e7e8`

## pseudocode

```c
int __stdcall ErrIsamDeleteTable(void *a1, Instance *a2, unsigned __int16 *a3)
{
  int v3; // edi
  int v4; // eax
  int v5; // esi
  int v6; // eax
  int v8; // [esp+Ch] [ebp-18h] BYREF
  int v9; // [esp+10h] [ebp-14h]
  int v10; // [esp+14h] [ebp-10h]
  void *Block; // [esp+18h] [ebp-Ch]
  void *v12; // [esp+1Ch] [ebp-8h]
  unsigned int v13; // [esp+20h] [ebp-4h] BYREF

  v3 = *((_DWORD *)a2 + 5);
  v8 = 1;
  Instance::ReadObjectRecord(a2, L"Tables", a3, (void **)&v8);
  v4 = v8;
  if ( (v8 & 8) == 0 )
  {
    (*(void (__thiscall **)(int, _DWORD, unsigned int *, int, _DWORD, int *))(*(_DWORD *)v3 + 108))(
      v3,
      *((_DWORD *)a2 + 8),
      &v13,
      4,
      0,
      &v8);
    v4 = v8;
  }
  if ( (v4 & 1) != 0 )
  {
    v5 = 0;
  }
  else
  {
    if ( (v4 & 8) != 0 && v10 && a1 )
    {
      (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
        *(_DWORD *)(pJetInfoBlock + 44),
        a1,
        Block,
        v12,
        0,
        v10,
        0,
        0,
        0);
      v4 = v8;
    }
    v5 = v9;
    if ( (v4 & 1) != 0 )
      v5 = 0;
  }
  if ( (v4 & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v12 )
      operator delete[](v12);
  }
  if ( v5 >= 0 )
  {
    v8 = 1;
    Instance::DeleteObject(a2, v13, (struct Err *)&v8);
    v6 = v8;
    if ( (v8 & 1) != 0 )
    {
      v5 = 0;
    }
    else
    {
      if ( (v8 & 8) != 0 && v10 && a1 )
      {
        (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
          *(_DWORD *)(pJetInfoBlock + 44),
          a1,
          Block,
          v12,
          0,
          v10,
          0,
          0,
          0);
        v6 = v8;
      }
      v5 = v9;
      if ( (v6 & 1) != 0 )
        v5 = 0;
    }
    if ( (v6 & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v12 )
        operator delete[](v12);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x10028bc0  mov     edi, edi
0x10028bc2  push    ebp
0x10028bc3  mov     ebp, esp
0x10028bc5  sub     esp, 18h
0x10028bc8  push    ebx
0x10028bc9  mov     ebx, [ebp+arg_4]
0x10028bcc  lea     eax, [ebp+var_18]
0x10028bcf  push    esi
0x10028bd0  push    edi
0x10028bd1  push    eax; struct Err *
0x10028bd2  push    [ebp+arg_8]; unsigned __int16 *
0x10028bd5  mov     edi, [ebx+14h]
0x10028bd8  mov     ecx, ebx; this
0x10028bda  push    offset aTables; "Tables"
0x10028bdf  mov     [ebp+var_18], 1
0x10028be6  call    ?ReadObjectRecord@Instance@@QAEXPBG0AAVErr@@@Z; Instance::ReadObjectRecord(ushort const *,ushort const *,Err &)
0x10028beb  mov     eax, [ebp+var_18]
0x10028bee  test    al, 8
0x10028bf0  jnz     short loc_10028C15
0x10028bf2  mov     esi, [edi]
0x10028bf4  lea     eax, [ebp+var_18]
0x10028bf7  push    eax
0x10028bf8  push    0
0x10028bfa  push    4
0x10028bfc  mov     esi, [esi+6Ch]
0x10028bff  lea     eax, [ebp+var_4]
0x10028c02  push    eax; unsigned int
0x10028c03  push    dword ptr [ebx+20h]; void *
0x10028c06  mov     ecx, esi
0x10028c08  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028c0e  mov     ecx, edi
0x10028c10  call    esi
0x10028c12  mov     eax, [ebp+var_18]
0x10028c15  mov     edi, [ebp+arg_0]
0x10028c18  test    al, 1
0x10028c1a  jz      short loc_10028C20
0x10028c1c  xor     esi, esi
0x10028c1e  jmp     short loc_10028C61
0x10028c20  test    al, 8
0x10028c22  jz      short loc_10028C54
0x10028c24  mov     ecx, [ebp+var_10]
0x10028c27  test    ecx, ecx
0x10028c29  jz      short loc_10028C54
0x10028c2b  test    edi, edi
0x10028c2d  jz      short loc_10028C54
0x10028c2f  mov     eax, _pJetInfoBlock
0x10028c34  push    0
0x10028c36  push    0
0x10028c38  push    0
0x10028c3a  mov     esi, [eax+2Ch]
0x10028c3d  push    ecx
0x10028c3e  push    0
0x10028c40  push    [ebp+var_8]
0x10028c43  mov     ecx, esi
0x10028c45  push    [ebp+Block]; unsigned int
0x10028c48  push    edi; void *
0x10028c49  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028c4f  call    esi
0x10028c51  mov     eax, [ebp+var_18]
0x10028c54  mov     esi, [ebp+var_14]
0x10028c57  test    al, 1
0x10028c59  mov     ecx, 0
0x10028c5e  cmovnz  esi, ecx
0x10028c61  test    eax, 0FFFFFFFEh
0x10028c66  jz      short loc_10028C88
0x10028c68  mov     eax, [ebp+Block]
0x10028c6b  test    eax, eax
0x10028c6d  jz      short loc_10028C78
0x10028c6f  push    eax; Block
0x10028c70  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10028c75  add     esp, 4
0x10028c78  mov     eax, [ebp+var_8]
0x10028c7b  test    eax, eax
0x10028c7d  jz      short loc_10028C88
0x10028c7f  push    eax; Block
0x10028c80  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10028c85  add     esp, 4
0x10028c88  test    esi, esi
0x10028c8a  js      loc_10028D18
0x10028c90  lea     eax, [ebp+var_18]
0x10028c93  mov     [ebp+var_18], 1
0x10028c9a  push    eax; struct Err *
0x10028c9b  push    [ebp+var_4]; unsigned int
0x10028c9e  mov     ecx, ebx; this
0x10028ca0  call    ?DeleteObject@Instance@@QAEXKAAVErr@@@Z; Instance::DeleteObject(ulong,Err &)
0x10028ca5  mov     eax, [ebp+var_18]
0x10028ca8  test    al, 1
0x10028caa  jz      short loc_10028CB0
0x10028cac  xor     esi, esi
0x10028cae  jmp     short loc_10028CF1
0x10028cb0  test    al, 8
0x10028cb2  jz      short loc_10028CE4
0x10028cb4  mov     ecx, [ebp+var_10]
0x10028cb7  test    ecx, ecx
0x10028cb9  jz      short loc_10028CE4
0x10028cbb  test    edi, edi
0x10028cbd  jz      short loc_10028CE4
0x10028cbf  mov     eax, _pJetInfoBlock
0x10028cc4  push    0
0x10028cc6  push    0
0x10028cc8  push    0
0x10028cca  mov     esi, [eax+2Ch]
0x10028ccd  push    ecx
0x10028cce  push    0
0x10028cd0  push    [ebp+var_8]
0x10028cd3  mov     ecx, esi
0x10028cd5  push    [ebp+Block]; unsigned int
0x10028cd8  push    edi; void *
0x10028cd9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10028cdf  call    esi
0x10028ce1  mov     eax, [ebp+var_18]
0x10028ce4  mov     esi, [ebp+var_14]
0x10028ce7  test    al, 1
0x10028ce9  mov     ecx, 0
0x10028cee  cmovnz  esi, ecx
0x10028cf1  test    eax, 0FFFFFFFEh
0x10028cf6  jz      short loc_10028D18
0x10028cf8  mov     eax, [ebp+Block]
0x10028cfb  test    eax, eax
0x10028cfd  jz      short loc_10028D08
0x10028cff  push    eax; Block
0x10028d00  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10028d05  add     esp, 4
0x10028d08  mov     eax, [ebp+var_8]
0x10028d0b  test    eax, eax
0x10028d0d  jz      short loc_10028D18
0x10028d0f  push    eax; Block
0x10028d10  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10028d15  add     esp, 4
0x10028d18  pop     edi
0x10028d19  mov     eax, esi
0x10028d1b  pop     esi
0x10028d1c  pop     ebx
0x10028d1d  mov     esp, ebp
0x10028d1f  pop     ebp
0x10028d20  retn    0Ch
```
