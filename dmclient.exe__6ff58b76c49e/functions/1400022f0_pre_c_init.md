# pre_c_init

- ea: `0x1400022f0`
- end: `0x1400023c7`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400022f0`
- `0x140002894`
- `0x1400028f0`

## import_xrefs

- `msvcrt!_fmode` at `0x14000238d`
- `msvcrt!_commode` at `0x140002396`
- `msvcrt!__setusermatherr` at `0x1400023ba`
- `msvcrt!__setusermatherr` at `0x1400023ba`
- `msvcrt!__set_app_type` at `0x14000236f`
- `msvcrt!__set_app_type` at `0x14000236f`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( _ImageBase != 23117 || *(_DWORD *)((char *)&_ImageBase + (int)off_14000003C) != 17744 )
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
  dword_140027440 = v0;
  image_app_type = (unsigned int)get_image_app_type(1);
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
0x1400022f0  sub     rsp, 28h
0x1400022f4  mov     eax, 5A4Dh
0x1400022f9  cmp     cs:__ImageBase, ax
0x140002300  jz      short loc_140002306
0x140002302  xor     eax, eax
0x140002304  jmp     short loc_14000235D
0x140002306  movsxd  rcx, cs:off_14000003C
0x14000230d  lea     rdx, __ImageBase
0x140002314  cmp     dword ptr [rcx+rdx], 4550h
0x14000231b  jnz     short loc_140002302
0x14000231d  mov     eax, 10Bh
0x140002322  cmp     [rcx+rdx+18h], ax
0x140002327  jz      short loc_14000234A
0x140002329  mov     eax, 20Bh
0x14000232e  cmp     [rcx+rdx+18h], ax
0x140002333  jnz     short loc_140002302
0x140002335  xor     eax, eax
0x140002337  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x14000233f  jbe     short loc_14000235D
0x140002341  cmp     [rcx+rdx+0F8h], eax
0x140002348  jmp     short loc_14000235A
0x14000234a  xor     eax, eax
0x14000234c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140002351  jbe     short loc_14000235D
0x140002353  cmp     [rcx+rdx+0E8h], eax
0x14000235a  setnz   al
0x14000235d  mov     ecx, 1
0x140002362  mov     cs:dword_140027440, eax
0x140002368  call    _get_image_app_type
0x14000236d  mov     ecx, eax; Type
0x14000236f  call    cs:__imp___set_app_type
0x140002375  mov     ecx, cs:_fmode
0x14000237b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000237f  mov     cs:__onexitend, rax
0x140002386  mov     cs:__onexitbegin, rax
0x14000238d  mov     rax, cs:__imp__fmode
0x140002394  mov     [rax], ecx
0x140002396  mov     rcx, cs:__imp__commode; Except
0x14000239d  mov     eax, cs:_commode
0x1400023a3  mov     [rcx], eax
0x1400023a5  call    _matherr
0x1400023aa  cmp     cs:__defaultmatherr, 0
0x1400023b1  jnz     short loc_1400023C0
0x1400023b3  lea     rcx, _matherr; UserMathErrorFunction
0x1400023ba  call    cs:__imp___setusermatherr
0x1400023c0  xor     eax, eax
0x1400023c2  add     rsp, 28h
0x1400023c6  retn
```
