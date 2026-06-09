# ErrIsamCreateDatabase(x,x,x,x,x)

- ea: `0x10027f20`
- end: `0x10028023`
- name: `_ErrIsamCreateDatabase@20`
- size: `259`
- prototype: `int __stdcall(void *, int, int, void *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10026140`
- `0x10027f20`
- `0x10035e10`
- `0x10044340`
- `0x1005e7e8`

## pseudocode

```c
int __stdcall ErrIsamCreateDatabase(Session *a1, const WCHAR *a2, int a3, void *a4, __int16 a5)
{
  int v5; // eax
  int v6; // esi
  int v7; // eax
  struct Instance *Database; // edi
  int v10[3]; // [esp+8h] [ebp-14h] BYREF
  void *Block; // [esp+14h] [ebp-8h]
  void *v12; // [esp+18h] [ebp-4h]

  v5 = 1;
  v10[0] = 1;
  if ( *((_DWORD *)a1 + 14) )
  {
    v6 = -1108;
  }
  else if ( a3 )
  {
    if ( (a5 & 0x24) != 0 )
    {
      v6 = -1019;
    }
    else
    {
      if ( (a5 & 0x80u) == 0 )
        v7 = a5 & 1 | 2;
      else
        v7 = 4;
      Database = Session::CreateDatabase(a1, a2, a3, a3, v7, (struct Err *)v10);
      v5 = v10[0];
      if ( (v10[0] & 8) != 0 )
      {
        if ( (v10[0] & 1) != 0 )
        {
          v6 = 0;
        }
        else
        {
          v6 = RealJetError(a1);
          v5 = v10[0];
        }
      }
      else
      {
        if ( (a5 & 0x100) != 0 )
          *(_DWORD *)(*((_DWORD *)Database + 4) + 964) = 1;
        v6 = (*(int (__thiscall **)(_DWORD, void *, struct Instance *, int *))(pJetInfoBlock + 40))(
               *(_DWORD *)(pJetInfoBlock + 40),
               a4,
               Database,
               vdbfndefIsam);
        if ( v6 < 0 )
          Instance::Release(Database);
        v5 = v10[0];
      }
    }
  }
  else
  {
    v6 = -1064;
  }
  if ( (v5 & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v12 )
      operator delete[](v12);
  }
  return v6;
}

```

## disassembly

```asm
0x10027f20  mov     edi, edi
0x10027f22  push    ebp
0x10027f23  mov     ebp, esp
0x10027f25  sub     esp, 14h
0x10027f28  push    esi
0x10027f29  mov     esi, [ebp+arg_0]
0x10027f2c  mov     eax, 1
0x10027f31  push    edi
0x10027f32  mov     [ebp+var_14], eax
0x10027f35  cmp     dword ptr [esi+38h], 0
0x10027f39  jz      short loc_10027F45
0x10027f3b  mov     esi, 0FFFFFBACh
0x10027f40  jmp     loc_10027FF2
0x10027f45  mov     ecx, [ebp+arg_8]
0x10027f48  test    ecx, ecx
0x10027f4a  jnz     short loc_10027F56
0x10027f4c  mov     esi, 0FFFFFBD8h
0x10027f51  jmp     loc_10027FF2
0x10027f56  push    ebx
0x10027f57  mov     ebx, [ebp+arg_10]
0x10027f5a  test    bl, 24h
0x10027f5d  jnz     loc_10027FEC
0x10027f63  test    bl, bl
0x10027f65  jns     short loc_10027F6E
0x10027f67  mov     eax, 4
0x10027f6c  jmp     short loc_10027F77
0x10027f6e  movzx   eax, bl
0x10027f71  and     eax, 1
0x10027f74  or      eax, 2
0x10027f77  lea     edx, [ebp+var_14]
0x10027f7a  push    edx
0x10027f7b  push    eax
0x10027f7c  push    ecx
0x10027f7d  push    ecx
0x10027f7e  push    [ebp+arg_4]
0x10027f81  mov     ecx, esi
0x10027f83  call    ?CreateDatabase@Session@@QAEPAVInstance@@PBG0W4DBVersion@@W4DBType@@AAVErr@@@Z; Session::CreateDatabase(ushort const *,ushort const *,DBVersion,DBType,Err &)
0x10027f88  mov     edi, eax
0x10027f8a  mov     eax, [ebp+var_14]
0x10027f8d  test    al, 8
0x10027f8f  jnz     short loc_10027FD3
0x10027f91  test    ebx, 100h
0x10027f97  jz      short loc_10027FA6
0x10027f99  mov     ecx, [edi+10h]
0x10027f9c  mov     dword ptr [ecx+3C4h], 1
0x10027fa6  mov     eax, _pJetInfoBlock
0x10027fab  push    offset _vdbfndefIsam
0x10027fb0  push    edi; unsigned int
0x10027fb1  push    [ebp+arg_C]; void *
0x10027fb4  mov     esi, [eax+28h]
0x10027fb7  mov     ecx, esi
0x10027fb9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10027fbf  call    esi
0x10027fc1  mov     esi, eax
0x10027fc3  test    esi, esi
0x10027fc5  jns     short loc_10027FCE
0x10027fc7  mov     ecx, edi; this
0x10027fc9  call    ?Release@Instance@@QAEXXZ; Instance::Release(void)
0x10027fce  mov     eax, [ebp+var_14]
0x10027fd1  jmp     short loc_10027FF1
0x10027fd3  test    al, 1
0x10027fd5  jz      short loc_10027FDB
0x10027fd7  xor     esi, esi
0x10027fd9  jmp     short loc_10027FF1
0x10027fdb  lea     edx, [ebp+var_14]
0x10027fde  mov     ecx, esi; void *
0x10027fe0  call    RealJetError
0x10027fe5  mov     esi, eax
0x10027fe7  mov     eax, [ebp+var_14]
0x10027fea  jmp     short loc_10027FF1
0x10027fec  mov     esi, 0FFFFFC05h
0x10027ff1  pop     ebx
0x10027ff2  test    eax, 0FFFFFFFEh
0x10027ff7  jz      short loc_10028019
0x10027ff9  mov     eax, [ebp+Block]
0x10027ffc  test    eax, eax
0x10027ffe  jz      short loc_10028009
0x10028000  push    eax; Block
0x10028001  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10028006  add     esp, 4
0x10028009  mov     eax, [ebp+var_4]
0x1002800c  test    eax, eax
0x1002800e  jz      short loc_10028019
0x10028010  push    eax; Block
0x10028011  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10028016  add     esp, 4
0x10028019  pop     edi
0x1002801a  mov     eax, esi
0x1002801c  pop     esi
0x1002801d  mov     esp, ebp
0x1002801f  pop     ebp
0x10028020  retn    14h
```
