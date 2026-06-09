# pre_c_init

- ea: `0x1400017a0`
- end: `0x140001877`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400017a0`
- `0x140002104`
- `0x140002160`

## import_xrefs

- `msvcrt!__setusermatherr` at `0x14000186a`
- `msvcrt!__setusermatherr` at `0x14000186a`
- `msvcrt!_commode` at `0x140001846`
- `msvcrt!_fmode` at `0x14000183d`
- `msvcrt!__set_app_type` at `0x14000181f`
- `msvcrt!__set_app_type` at `0x14000181f`

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
      v1 = *(_DWORD *)&byte_140000040[(int)off_14000003C + 184] == 0;
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
  dword_14001C300 = v0;
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
0x1400017a0  sub     rsp, 28h
0x1400017a4  mov     eax, 5A4Dh
0x1400017a9  cmp     word ptr cs:__ImageBase.unused, ax
0x1400017b0  jz      short loc_1400017B6
0x1400017b2  xor     eax, eax
0x1400017b4  jmp     short loc_14000180D
0x1400017b6  movsxd  rcx, cs:off_14000003C
0x1400017bd  lea     rdx, __ImageBase
0x1400017c4  cmp     dword ptr [rcx+rdx], 4550h
0x1400017cb  jnz     short loc_1400017B2
0x1400017cd  mov     eax, 10Bh
0x1400017d2  cmp     [rcx+rdx+18h], ax
0x1400017d7  jz      short loc_1400017FA
0x1400017d9  mov     eax, 20Bh
0x1400017de  cmp     [rcx+rdx+18h], ax
0x1400017e3  jnz     short loc_1400017B2
0x1400017e5  xor     eax, eax
0x1400017e7  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x1400017ef  jbe     short loc_14000180D
0x1400017f1  cmp     [rcx+rdx+0F8h], eax
0x1400017f8  jmp     short loc_14000180A
0x1400017fa  xor     eax, eax
0x1400017fc  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001801  jbe     short loc_14000180D
0x140001803  cmp     [rcx+rdx+0E8h], eax
0x14000180a  setnz   al
0x14000180d  mov     ecx, 2
0x140001812  mov     cs:dword_14001C300, eax
0x140001818  call    _get_image_app_type
0x14000181d  mov     ecx, eax; Type
0x14000181f  call    cs:__imp___set_app_type
0x140001825  mov     ecx, cs:_fmode
0x14000182b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000182f  mov     cs:__onexitend, rax
0x140001836  mov     cs:__onexitbegin, rax
0x14000183d  mov     rax, cs:__imp__fmode
0x140001844  mov     [rax], ecx
0x140001846  mov     rcx, cs:__imp__commode; Except
0x14000184d  mov     eax, cs:_commode
0x140001853  mov     [rcx], eax
0x140001855  call    _matherr
0x14000185a  cmp     cs:__defaultmatherr, 0
0x140001861  jnz     short loc_140001870
0x140001863  lea     rcx, _matherr; UserMathErrorFunction
0x14000186a  call    cs:__imp___setusermatherr
0x140001870  xor     eax, eax
0x140001872  add     rsp, 28h
0x140001876  retn
```
