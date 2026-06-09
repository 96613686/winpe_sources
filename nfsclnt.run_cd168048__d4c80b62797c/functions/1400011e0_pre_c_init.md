# pre_c_init

- ea: `0x1400011e0`
- end: `0x1400012b7`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400011e0`
- `0x1400017d4`
- `0x140009e90`

## import_xrefs

- `msvcrt!_commode` at `0x140001286`
- `msvcrt!_fmode` at `0x14000127d`
- `msvcrt!__setusermatherr` at `0x1400012aa`
- `msvcrt!__setusermatherr` at `0x1400012aa`
- `msvcrt!__set_app_type` at `0x14000125f`
- `msvcrt!__set_app_type` at `0x14000125f`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( MEMORY[0x140000000] != 23117 || *(_DWORD *)(MEMORY[0x14000003C] + 0x140000000LL) != 17744 )
    goto LABEL_2;
  if ( *(_WORD *)(MEMORY[0x14000003C] + 0x140000018LL) != 267 )
  {
    if ( *(_WORD *)(MEMORY[0x14000003C] + 0x140000018LL) == 523 )
    {
      v0 = 0;
      if ( *(_DWORD *)(MEMORY[0x14000003C] + 0x140000084LL) <= 0xEu )
        goto LABEL_11;
      v1 = *(_DWORD *)(MEMORY[0x14000003C] + 0x1400000F8LL) == 0;
      goto LABEL_10;
    }
LABEL_2:
    v0 = 0;
    goto LABEL_11;
  }
  v0 = 0;
  if ( *(_DWORD *)(MEMORY[0x14000003C] + 0x140000074LL) <= 0xEu )
    goto LABEL_11;
  v1 = *(_DWORD *)(MEMORY[0x14000003C] + 0x1400000E8LL) == 0;
LABEL_10:
  LOBYTE(v0) = !v1;
LABEL_11:
  dword_1400203C0 = v0;
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
0x1400011e0  sub     rsp, 28h
0x1400011e4  mov     eax, 5A4Dh
0x1400011e9  cmp     cs:140000000h, ax
0x1400011f0  jz      short loc_1400011F6
0x1400011f2  xor     eax, eax
0x1400011f4  jmp     short loc_14000124D
0x1400011f6  movsxd  rcx, dword ptr cs:14000003Ch
0x1400011fd  lea     rdx, cs:140000000h
0x140001204  cmp     dword ptr [rcx+rdx], 4550h
0x14000120b  jnz     short loc_1400011F2
0x14000120d  mov     eax, 10Bh
0x140001212  cmp     [rcx+rdx+18h], ax
0x140001217  jz      short loc_14000123A
0x140001219  mov     eax, 20Bh
0x14000121e  cmp     [rcx+rdx+18h], ax
0x140001223  jnz     short loc_1400011F2
0x140001225  xor     eax, eax
0x140001227  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x14000122f  jbe     short loc_14000124D
0x140001231  cmp     [rcx+rdx+0F8h], eax
0x140001238  jmp     short loc_14000124A
0x14000123a  xor     eax, eax
0x14000123c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001241  jbe     short loc_14000124D
0x140001243  cmp     [rcx+rdx+0E8h], eax
0x14000124a  setnz   al
0x14000124d  mov     ecx, 1
0x140001252  mov     cs:dword_1400203C0, eax
0x140001258  call    _get_image_app_type
0x14000125d  mov     ecx, eax; Type
0x14000125f  call    cs:__imp___set_app_type
0x140001265  mov     ecx, cs:_fmode
0x14000126b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000126f  mov     cs:__onexitend, rax
0x140001276  mov     cs:__onexitbegin, rax
0x14000127d  mov     rax, cs:__imp__fmode
0x140001284  mov     [rax], ecx
0x140001286  mov     rcx, cs:__imp__commode; Except
0x14000128d  mov     eax, cs:_commode
0x140001293  mov     [rcx], eax
0x140001295  call    _matherr
0x14000129a  cmp     cs:__defaultmatherr, 0
0x1400012a1  jnz     short loc_1400012B0
0x1400012a3  lea     rcx, _matherr; UserMathErrorFunction
0x1400012aa  call    cs:__imp___setusermatherr
0x1400012b0  xor     eax, eax
0x1400012b2  add     rsp, 28h
0x1400012b6  retn
```
