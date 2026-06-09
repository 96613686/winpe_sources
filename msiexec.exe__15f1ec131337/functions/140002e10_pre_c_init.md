# pre_c_init

- ea: `0x140002e10`
- end: `0x140002ee7`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002e10`
- `0x140003654`
- `0x1400036b0`

## import_xrefs

- `msvcrt!__setusermatherr` at `0x140002eda`
- `msvcrt!__setusermatherr` at `0x140002eda`
- `msvcrt!_fmode` at `0x140002ead`
- `msvcrt!__set_app_type` at `0x140002e8f`
- `msvcrt!__set_app_type` at `0x140002e8f`
- `msvcrt!_commode` at `0x140002eb6`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( LOWORD(_ImageBase.unused) != 23117 || *(int *)((char *)&_ImageBase.unused + (int)off_14000003C) != 17744 )
    goto LABEL_2;
  if ( *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) != 267 )
  {
    if ( *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) == 523 )
    {
      v0 = 0;
      if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 68] <= 0xEu )
        goto LABEL_11;
      v1 = *(int *)((char *)&dword_1400000F8 + (int)off_14000003C) == 0;
      goto LABEL_10;
    }
LABEL_2:
    v0 = 0;
    goto LABEL_11;
  }
  v0 = 0;
  if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 52] <= 0xEu )
    goto LABEL_11;
  v1 = *(_DWORD *)&byte_140000040[(int)off_14000003C + 168] == 0;
LABEL_10:
  LOBYTE(v0) = !v1;
LABEL_11:
  dword_1400101E0 = v0;
  image_app_type = (unsigned int)get_image_app_type(2);
  __set_app_type(image_app_type);
  _onexitend = -1;
  _onexitbegin = -1;
  _fmode = fmode;
  _commode = commode;
  matherr(*(struct _exception **)&_commode);
  if ( !_defaultmatherr )
    __setusermatherr(matherr);
  return 0;
}

```

## disassembly

```asm
0x140002e10  sub     rsp, 28h
0x140002e14  mov     eax, 5A4Dh
0x140002e19  cmp     word ptr cs:__ImageBase.unused, ax
0x140002e20  jz      short loc_140002E26
0x140002e22  xor     eax, eax
0x140002e24  jmp     short loc_140002E7D
0x140002e26  movsxd  rcx, cs:off_14000003C
0x140002e2d  lea     rdx, __ImageBase
0x140002e34  cmp     dword ptr [rcx+rdx], 4550h
0x140002e3b  jnz     short loc_140002E22
0x140002e3d  mov     eax, 10Bh
0x140002e42  cmp     [rcx+rdx+18h], ax
0x140002e47  jz      short loc_140002E6A
0x140002e49  mov     eax, 20Bh
0x140002e4e  cmp     [rcx+rdx+18h], ax
0x140002e53  jnz     short loc_140002E22
0x140002e55  xor     eax, eax
0x140002e57  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x140002e5f  jbe     short loc_140002E7D
0x140002e61  cmp     [rcx+rdx+0F8h], eax
0x140002e68  jmp     short loc_140002E7A
0x140002e6a  xor     eax, eax
0x140002e6c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140002e71  jbe     short loc_140002E7D
0x140002e73  cmp     [rcx+rdx+0E8h], eax
0x140002e7a  setnz   al
0x140002e7d  mov     ecx, 2
0x140002e82  mov     cs:dword_1400101E0, eax
0x140002e88  call    _get_image_app_type
0x140002e8d  mov     ecx, eax; Type
0x140002e8f  call    cs:__imp___set_app_type
0x140002e95  mov     ecx, cs:_fmode
0x140002e9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002e9f  mov     cs:__onexitend, rax
0x140002ea6  mov     cs:__onexitbegin, rax
0x140002ead  mov     rax, cs:__imp__fmode
0x140002eb4  mov     [rax], ecx
0x140002eb6  mov     rcx, cs:__imp__commode; Except
0x140002ebd  mov     eax, cs:_commode
0x140002ec3  mov     [rcx], eax
0x140002ec5  call    _matherr
0x140002eca  cmp     cs:__defaultmatherr, 0
0x140002ed1  jnz     short loc_140002EE0
0x140002ed3  lea     rcx, _matherr; UserMathErrorFunction
0x140002eda  call    cs:__imp___setusermatherr
0x140002ee0  xor     eax, eax
0x140002ee2  add     rsp, 28h
0x140002ee6  retn
```
