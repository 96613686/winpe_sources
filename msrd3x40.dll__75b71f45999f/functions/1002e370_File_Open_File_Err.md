# File::Open(File &,Err &)

- ea: `0x1002e370`
- end: `0x1002e4d4`
- name: `?Open@File@@QAEXAAV1@AAVErr@@@Z`
- size: `356`
- prototype: `void __thiscall(File *__hidden this, struct File *, struct Err *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x10022310`

## callees

- `0x10025ee0`
- `0x1002e370`
- `0x1002e4e0`
- `0x1002ebe0`
- `0x1005e7e8`
- `0x1005e7f3`

## pseudocode

```c
void __thiscall File::Open(File *this, struct File *a2, void **a3)
{
  _WORD *v3; // ebx
  struct Err *v4; // esi
  _WORD *v5; // edi
  int v6; // eax
  __int16 v7; // ax
  _WORD *v8; // edx
  _WORD *v9; // ecx
  __int16 v10; // bx
  _WORD *v11; // esi
  int v12; // eax
  __int16 v13; // ax
  int v14; // [esp-4h] [ebp-18h]
  _WORD *v16; // [esp+10h] [ebp-4h]

  v3 = (_WORD *)*((_DWORD *)a2 + 1);
  v16 = v3;
  v4 = (struct Err *)a3;
  v5 = operator new[](0x20Au);
  v6 = (int)*a3;
  if ( ((unsigned __int8)*a3 & 8) != 0 )
  {
    if ( v6 < 8 )
    {
      if ( (v6 & 0xFFFFFFFE) != 0 )
      {
        if ( a3[3] )
          operator delete[](a3[3]);
        if ( a3[4] )
          operator delete[](a3[4]);
      }
      *a3 = (void *)8;
      a3[1] = (void *)-1011;
      a3[2] = 0;
      a3[3] = 0;
      a3[4] = 0;
    }
  }
  else
  {
    v7 = *v3;
    v8 = 0;
    *v5 = *v3;
    v9 = v5;
    v10 = v7;
    if ( !v7 )
      goto LABEL_18;
    v11 = v16;
    do
    {
      if ( v10 == 92 || (v12 = (unsigned __int16)*v9, v12 == 47) )
      {
        v8 = 0;
      }
      else if ( v12 == 46 )
      {
        v8 = v9;
      }
      v13 = v11[1];
      ++v11;
      ++v9;
      v10 = v13;
      *v9 = v13;
    }
    while ( v13 );
    v4 = (struct Err *)a3;
    if ( !v8 )
LABEL_18:
      v8 = v9;
    if ( v8 + 4 <= v5 + 260 )
    {
      *(_DWORD *)v8 = 7077934;
      *((_DWORD *)v8 + 1) = 6422628;
      v8[4] = 0;
    }
    else
    {
      operator delete[](v5);
      v5 = 0;
      Err::SetError(v4, -1023, v14);
    }
  }
  if ( (*(_BYTE *)v4 & 8) == 0 )
  {
    *((_DWORD *)this + 4) |= 8u;
    File::ReallyOpen(this, v5, v4);
    if ( (*(_BYTE *)v4 & 8) != 0
      || (File::Close(this, v4), (*(_BYTE *)v4 & 8) != 0)
      || (File::ReallyOpen(this, v5, v4), (*(_BYTE *)v4 & 8) != 0) )
    {
      if ( *((_WORD **)this + 1) == v5 )
        *((_DWORD *)this + 1) = 0;
      if ( v5 )
        operator delete[](v5);
    }
  }
}

```

## disassembly

```asm
0x1002e370  mov     edi, edi
0x1002e372  push    ebp
0x1002e373  mov     ebp, esp
0x1002e375  sub     esp, 8
0x1002e378  mov     eax, [ebp+arg_0]
0x1002e37b  push    ebx
0x1002e37c  push    esi
0x1002e37d  push    edi
0x1002e37e  mov     ebx, [eax+4]
0x1002e381  push    20Ah; unsigned int
0x1002e386  mov     [ebp+var_8], ecx
0x1002e389  mov     [ebp+var_4], ebx
0x1002e38c  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1002e391  mov     esi, [ebp+arg_4]
0x1002e394  mov     edi, eax
0x1002e396  add     esp, 4
0x1002e399  mov     eax, [esi]
0x1002e39b  test    al, 8
0x1002e39d  jz      short loc_1002E3F6
0x1002e39f  cmp     eax, 8
0x1002e3a2  jge     loc_1002E47D
0x1002e3a8  test    eax, 0FFFFFFFEh
0x1002e3ad  jz      short loc_1002E3CF
0x1002e3af  mov     eax, [esi+0Ch]
0x1002e3b2  test    eax, eax
0x1002e3b4  jz      short loc_1002E3BF
0x1002e3b6  push    eax; Block
0x1002e3b7  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e3bc  add     esp, 4
0x1002e3bf  mov     eax, [esi+10h]
0x1002e3c2  test    eax, eax
0x1002e3c4  jz      short loc_1002E3CF
0x1002e3c6  push    eax; Block
0x1002e3c7  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e3cc  add     esp, 4
0x1002e3cf  mov     dword ptr [esi], 8
0x1002e3d5  mov     dword ptr [esi+4], 0FFFFFC0Dh
0x1002e3dc  mov     dword ptr [esi+8], 0
0x1002e3e3  mov     dword ptr [esi+0Ch], 0
0x1002e3ea  mov     dword ptr [esi+10h], 0
0x1002e3f1  jmp     loc_1002E47D
0x1002e3f6  movzx   eax, word ptr [ebx]
0x1002e3f9  xor     edx, edx
0x1002e3fb  mov     [edi], ax
0x1002e3fe  mov     ecx, edi
0x1002e400  mov     ebx, eax
0x1002e402  test    ax, ax
0x1002e405  jz      short loc_1002E446
0x1002e407  mov     esi, [ebp+var_4]
0x1002e40a  nop     word ptr [eax+eax+00h]
0x1002e410  cmp     bx, 5Ch ; '\'
0x1002e414  jz      short loc_1002E429
0x1002e416  movzx   eax, word ptr [ecx]
0x1002e419  mov     ebx, eax
0x1002e41b  cmp     eax, 2Fh ; '/'
0x1002e41e  jz      short loc_1002E429
0x1002e420  cmp     ebx, 2Eh ; '.'
0x1002e423  jnz     short loc_1002E42B
0x1002e425  mov     edx, ecx
0x1002e427  jmp     short loc_1002E42B
0x1002e429  xor     edx, edx
0x1002e42b  movzx   eax, word ptr [esi+2]
0x1002e42f  add     esi, 2
0x1002e432  add     ecx, 2
0x1002e435  mov     ebx, eax
0x1002e437  mov     [ecx], ax
0x1002e43a  test    ax, ax
0x1002e43d  jnz     short loc_1002E410
0x1002e43f  mov     esi, [ebp+arg_4]
0x1002e442  test    edx, edx
0x1002e444  jnz     short loc_1002E448
0x1002e446  mov     edx, ecx
0x1002e448  lea     ecx, [edx+8]
0x1002e44b  lea     eax, [edi+208h]
0x1002e451  cmp     ecx, eax
0x1002e453  jbe     short loc_1002E46B
0x1002e455  push    edi; Block
0x1002e456  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e45b  push    0FFFFFC01h
0x1002e460  mov     ecx, esi
0x1002e462  xor     edi, edi
0x1002e464  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002e469  jmp     short loc_1002E47D
0x1002e46b  xor     eax, eax
0x1002e46d  mov     dword ptr [edx], 6C002Eh
0x1002e473  mov     dword ptr [edx+4], 620064h
0x1002e47a  mov     [ecx], ax
0x1002e47d  test    byte ptr [esi], 8
0x1002e480  jnz     short loc_1002E4CB
0x1002e482  mov     ebx, [ebp+var_8]
0x1002e485  mov     ecx, ebx; this
0x1002e487  push    esi; struct Err *
0x1002e488  push    edi; lpFileName
0x1002e489  or      dword ptr [ebx+10h], 8
0x1002e48d  call    ?ReallyOpen@File@@AAEXPAGAAVErr@@@Z; File::ReallyOpen(ushort *,Err &)
0x1002e492  test    byte ptr [esi], 8
0x1002e495  jnz     short loc_1002E4B2
0x1002e497  push    esi; struct Err *
0x1002e498  mov     ecx, ebx; this
0x1002e49a  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x1002e49f  test    byte ptr [esi], 8
0x1002e4a2  jnz     short loc_1002E4B2
0x1002e4a4  push    esi; struct Err *
0x1002e4a5  push    edi; lpFileName
0x1002e4a6  mov     ecx, ebx; this
0x1002e4a8  call    ?ReallyOpen@File@@AAEXPAGAAVErr@@@Z; File::ReallyOpen(ushort *,Err &)
0x1002e4ad  test    byte ptr [esi], 8
0x1002e4b0  jz      short loc_1002E4CB
0x1002e4b2  cmp     [ebx+4], edi
0x1002e4b5  jnz     short loc_1002E4BE
0x1002e4b7  mov     dword ptr [ebx+4], 0
0x1002e4be  test    edi, edi
0x1002e4c0  jz      short loc_1002E4CB
0x1002e4c2  push    edi; Block
0x1002e4c3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e4c8  add     esp, 4
0x1002e4cb  pop     edi
0x1002e4cc  pop     esi
0x1002e4cd  pop     ebx
0x1002e4ce  mov     esp, ebp
0x1002e4d0  pop     ebp
0x1002e4d1  retn    8
```
