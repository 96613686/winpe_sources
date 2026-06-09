# ErrIsamOpenDatabase(x,x,x,x,x)

- ea: `0x10027d60`
- end: `0x10027e62`
- name: `_ErrIsamOpenDatabase@20`
- size: `258`
- prototype: `int __stdcall(void *, int, int, void *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10026140`
- `0x10027d60`
- `0x10035e10`
- `0x10044630`
- `0x1005e7e8`

## pseudocode

```c
int __stdcall ErrIsamOpenDatabase(
        void *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        void *a4,
        unsigned int a5)
{
  unsigned int v5; // edi
  int v6; // edx
  int v7; // ebx
  unsigned __int16 *i; // eax
  int v9; // ecx
  struct Session *v10; // eax
  Instance *v11; // ebx
  int v12; // esi
  int v14[3]; // [esp+Ch] [ebp-14h] BYREF
  void *Block; // [esp+18h] [ebp-8h]
  void *v16; // [esp+1Ch] [ebp-4h]

  v5 = 0;
  v14[0] = 1;
  if ( (a5 & 1) != 0 )
    v6 = (a5 & 0x40) != 0 ? 3 : 0;
  else
    v6 = 1;
  if ( (a5 & 0xA) != 0 )
  {
    v7 = v6 == 0;
    v5 = (a5 >> 3) & 1;
  }
  else
  {
    v7 = 2;
  }
  for ( i = a3; i; ++i )
  {
    v9 = *i;
    if ( !(_WORD)v9 )
      break;
    if ( v9 == 59 )
    {
      if ( !i[1] )
        i = 0;
      break;
    }
  }
  v10 = Session::OpenDatabase((int)a1, a2, (int)i, v5, v6, v7, (Err *)v14);
  v11 = v10;
  if ( (v14[0] & 8) != 0
    || (v12 = (*(int (__thiscall **)(_DWORD, void *, struct Session *, int *))(pJetInfoBlock + 40))(
                *(_DWORD *)(pJetInfoBlock + 40),
                a4,
                v10,
                vdbfndefIsam),
        v12 >= 0) )
  {
    if ( (v14[0] & 1) != 0 )
      v12 = 0;
    else
      v12 = RealJetError(a1);
  }
  else
  {
    Instance::Release(v11);
  }
  if ( (v14[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v16 )
      operator delete[](v16);
  }
  return v12;
}

```

## disassembly

```asm
0x10027d60  mov     edi, edi
0x10027d62  push    ebp
0x10027d63  mov     ebp, esp
0x10027d65  sub     esp, 14h
0x10027d68  mov     ecx, [ebp+arg_10]
0x10027d6b  push    ebx
0x10027d6c  push    esi
0x10027d6d  push    edi
0x10027d6e  xor     edi, edi
0x10027d70  mov     [ebp+var_14], 1
0x10027d77  test    cl, 1
0x10027d7a  jz      short loc_10027D8C
0x10027d7c  mov     eax, ecx
0x10027d7e  and     al, 40h
0x10027d80  movzx   edx, al
0x10027d83  neg     edx
0x10027d85  sbb     edx, edx
0x10027d87  and     edx, 3
0x10027d8a  jmp     short loc_10027D91
0x10027d8c  mov     edx, 1
0x10027d91  test    cl, 0Ah
0x10027d94  jz      short loc_10027DA7
0x10027d96  xor     ebx, ebx
0x10027d98  mov     edi, ecx
0x10027d9a  test    edx, edx
0x10027d9c  setz    bl
0x10027d9f  shr     edi, 3
0x10027da2  and     edi, 1
0x10027da5  jmp     short loc_10027DAC
0x10027da7  mov     ebx, 2
0x10027dac  mov     eax, [ebp+arg_8]
0x10027daf  test    eax, eax
0x10027db1  jz      short loc_10027DD0
0x10027db3  movzx   ecx, word ptr [eax]
0x10027db6  test    cx, cx
0x10027db9  jz      short loc_10027DD0
0x10027dbb  cmp     ecx, 3Bh ; ';'
0x10027dbe  jz      short loc_10027DC7
0x10027dc0  add     eax, 2
0x10027dc3  jnz     short loc_10027DB3
0x10027dc5  jmp     short loc_10027DD0
0x10027dc7  xor     ecx, ecx
0x10027dc9  cmp     [eax+2], cx
0x10027dcd  cmovz   eax, ecx
0x10027dd0  lea     ecx, [ebp+var_14]
0x10027dd3  push    ecx
0x10027dd4  push    ebx
0x10027dd5  push    edx
0x10027dd6  push    edi
0x10027dd7  mov     edi, [ebp+arg_0]
0x10027dda  mov     ecx, edi
0x10027ddc  push    eax
0x10027ddd  push    [ebp+arg_4]
0x10027de0  call    ?OpenDatabase@Session@@QAEPAVInstance@@PBG0W4DBOpenFreq@@W4DBIntent@@W4DBShare@@AAVErr@@@Z; Session::OpenDatabase(ushort const *,ushort const *,DBOpenFreq,DBIntent,DBShare,Err &)
0x10027de5  test    byte ptr [ebp+var_14], 8
0x10027de9  mov     ebx, eax
0x10027deb  jnz     short loc_10027E18
0x10027ded  mov     ecx, _pJetInfoBlock
0x10027df3  push    offset _vdbfndefIsam
0x10027df8  push    ebx; unsigned int
0x10027df9  push    [ebp+arg_C]; void *
0x10027dfc  mov     esi, [ecx+28h]
0x10027dff  mov     ecx, esi
0x10027e01  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10027e07  call    esi
0x10027e09  mov     esi, eax
0x10027e0b  test    esi, esi
0x10027e0d  jns     short loc_10027E18
0x10027e0f  mov     ecx, ebx; this
0x10027e11  call    ?Release@Instance@@QAEXXZ; Instance::Release(void)
0x10027e16  jmp     short loc_10027E2E
0x10027e18  test    byte ptr [ebp+var_14], 1
0x10027e1c  jz      short loc_10027E22
0x10027e1e  xor     esi, esi
0x10027e20  jmp     short loc_10027E2E
0x10027e22  lea     edx, [ebp+var_14]
0x10027e25  mov     ecx, edi; void *
0x10027e27  call    RealJetError
0x10027e2c  mov     esi, eax
0x10027e2e  test    [ebp+var_14], 0FFFFFFFEh
0x10027e35  jz      short loc_10027E57
0x10027e37  mov     eax, [ebp+Block]
0x10027e3a  test    eax, eax
0x10027e3c  jz      short loc_10027E47
0x10027e3e  push    eax; Block
0x10027e3f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027e44  add     esp, 4
0x10027e47  mov     eax, [ebp+var_4]
0x10027e4a  test    eax, eax
0x10027e4c  jz      short loc_10027E57
0x10027e4e  push    eax; Block
0x10027e4f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10027e54  add     esp, 4
0x10027e57  pop     edi
0x10027e58  mov     eax, esi
0x10027e5a  pop     esi
0x10027e5b  pop     ebx
0x10027e5c  mov     esp, ebp
0x10027e5e  pop     ebp
0x10027e5f  retn    14h
```
