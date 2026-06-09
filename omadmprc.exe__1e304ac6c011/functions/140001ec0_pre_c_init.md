# pre_c_init

- ea: `0x140001ec0`
- end: `0x140001f97`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001ec0`
- `0x1400024e4`
- `0x140002540`

## import_xrefs

- `msvcrt!_commode` at `0x140001f66`
- `msvcrt!_fmode` at `0x140001f5d`
- `msvcrt!__setusermatherr` at `0x140001f8a`
- `msvcrt!__setusermatherr` at `0x140001f8a`
- `msvcrt!__set_app_type` at `0x140001f3f`
- `msvcrt!__set_app_type` at `0x140001f3f`

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
  dword_140023AB8 = v0;
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
0x140001ec0  sub     rsp, 28h
0x140001ec4  mov     eax, 5A4Dh
0x140001ec9  cmp     word ptr cs:__ImageBase.unused, ax
0x140001ed0  jz      short loc_140001ED6
0x140001ed2  xor     eax, eax
0x140001ed4  jmp     short loc_140001F2D
0x140001ed6  movsxd  rcx, cs:off_14000003C
0x140001edd  lea     rdx, __ImageBase
0x140001ee4  cmp     dword ptr [rcx+rdx], 4550h
0x140001eeb  jnz     short loc_140001ED2
0x140001eed  mov     eax, 10Bh
0x140001ef2  cmp     [rcx+rdx+18h], ax
0x140001ef7  jz      short loc_140001F1A
0x140001ef9  mov     eax, 20Bh
0x140001efe  cmp     [rcx+rdx+18h], ax
0x140001f03  jnz     short loc_140001ED2
0x140001f05  xor     eax, eax
0x140001f07  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x140001f0f  jbe     short loc_140001F2D
0x140001f11  cmp     [rcx+rdx+0F8h], eax
0x140001f18  jmp     short loc_140001F2A
0x140001f1a  xor     eax, eax
0x140001f1c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001f21  jbe     short loc_140001F2D
0x140001f23  cmp     [rcx+rdx+0E8h], eax
0x140001f2a  setnz   al
0x140001f2d  mov     ecx, 2
0x140001f32  mov     cs:dword_140023AB8, eax
0x140001f38  call    _get_image_app_type
0x140001f3d  mov     ecx, eax; Type
0x140001f3f  call    cs:__imp___set_app_type
0x140001f45  mov     ecx, cs:_fmode
0x140001f4b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001f4f  mov     cs:__onexitend, rax
0x140001f56  mov     cs:__onexitbegin, rax
0x140001f5d  mov     rax, cs:__imp__fmode
0x140001f64  mov     [rax], ecx
0x140001f66  mov     rcx, cs:__imp__commode; Except
0x140001f6d  mov     eax, cs:_commode
0x140001f73  mov     [rcx], eax
0x140001f75  call    _matherr
0x140001f7a  cmp     cs:__defaultmatherr, 0
0x140001f81  jnz     short loc_140001F90
0x140001f83  lea     rcx, _matherr; UserMathErrorFunction
0x140001f8a  call    cs:__imp___setusermatherr
0x140001f90  xor     eax, eax
0x140001f92  add     rsp, 28h
0x140001f96  retn
```
