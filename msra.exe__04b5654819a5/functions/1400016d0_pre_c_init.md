# pre_c_init

- ea: `0x1400016d0`
- end: `0x1400017a7`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400016d0`
- `0x140002234`
- `0x140002290`

## import_xrefs

- `msvcrt!_commode` at `0x140001776`
- `msvcrt!_fmode` at `0x14000176d`
- `msvcrt!__setusermatherr` at `0x14000179a`
- `msvcrt!__setusermatherr` at `0x14000179a`
- `msvcrt!__set_app_type` at `0x14000174f`
- `msvcrt!__set_app_type` at `0x14000174f`

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
  dword_140063A10 = v0;
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
0x1400016d0  sub     rsp, 28h
0x1400016d4  mov     eax, 5A4Dh
0x1400016d9  cmp     word ptr cs:__ImageBase.unused, ax
0x1400016e0  jz      short loc_1400016E6
0x1400016e2  xor     eax, eax
0x1400016e4  jmp     short loc_14000173D
0x1400016e6  movsxd  rcx, cs:off_14000003C
0x1400016ed  lea     rdx, __ImageBase
0x1400016f4  cmp     dword ptr [rcx+rdx], 4550h
0x1400016fb  jnz     short loc_1400016E2
0x1400016fd  mov     eax, 10Bh
0x140001702  cmp     [rcx+rdx+18h], ax
0x140001707  jz      short loc_14000172A
0x140001709  mov     eax, 20Bh
0x14000170e  cmp     [rcx+rdx+18h], ax
0x140001713  jnz     short loc_1400016E2
0x140001715  xor     eax, eax
0x140001717  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x14000171f  jbe     short loc_14000173D
0x140001721  cmp     [rcx+rdx+0F8h], eax
0x140001728  jmp     short loc_14000173A
0x14000172a  xor     eax, eax
0x14000172c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001731  jbe     short loc_14000173D
0x140001733  cmp     [rcx+rdx+0E8h], eax
0x14000173a  setnz   al
0x14000173d  mov     ecx, 2
0x140001742  mov     cs:dword_140063A10, eax
0x140001748  call    _get_image_app_type
0x14000174d  mov     ecx, eax; Type
0x14000174f  call    cs:__imp___set_app_type
0x140001755  mov     ecx, cs:_fmode
0x14000175b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000175f  mov     cs:__onexitend, rax
0x140001766  mov     cs:__onexitbegin, rax
0x14000176d  mov     rax, cs:__imp__fmode
0x140001774  mov     [rax], ecx
0x140001776  mov     rcx, cs:__imp__commode; Except
0x14000177d  mov     eax, cs:_commode
0x140001783  mov     [rcx], eax
0x140001785  call    _matherr
0x14000178a  cmp     cs:__defaultmatherr, 0
0x140001791  jnz     short loc_1400017A0
0x140001793  lea     rcx, _matherr; UserMathErrorFunction
0x14000179a  call    cs:__imp___setusermatherr
0x1400017a0  xor     eax, eax
0x1400017a2  add     rsp, 28h
0x1400017a6  retn
```
