# pre_c_init

- ea: `0x1400100d0`
- end: `0x1400101a7`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400100d0`
- `0x1400108b4`
- `0x14001ca30`

## import_xrefs

- `msvcrt!__set_app_type` at `0x14001014f`
- `msvcrt!__set_app_type` at `0x14001014f`
- `msvcrt!__setusermatherr` at `0x14001019a`
- `msvcrt!__setusermatherr` at `0x14001019a`
- `msvcrt!_fmode` at `0x14001016d`
- `msvcrt!_commode` at `0x140010176`

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
  dword_140029260 = v0;
  image_app_type = (unsigned int)get_image_app_type(2);
  __set_app_type(image_app_type);
  _onexitend = -1;
  _onexitbegin = -1;
  _fmode = fmode;
  _commode = commode;
  CAudioPlaybackEventCallback::OnReplayIterationCompleted(*(struct _exception **)&_commode);
  if ( !_defaultmatherr )
    __setusermatherr((_UserMathErrorFunctionPointer)CAudioPlaybackEventCallback::OnReplayIterationCompleted);
  return 0;
}

```

## disassembly

```asm
0x1400100d0  sub     rsp, 28h
0x1400100d4  mov     eax, 5A4Dh
0x1400100d9  cmp     word ptr cs:__ImageBase.unused, ax
0x1400100e0  jz      short loc_1400100E6
0x1400100e2  xor     eax, eax
0x1400100e4  jmp     short loc_14001013D
0x1400100e6  movsxd  rcx, cs:off_14000003C
0x1400100ed  lea     rdx, __ImageBase
0x1400100f4  cmp     dword ptr [rcx+rdx], 4550h
0x1400100fb  jnz     short loc_1400100E2
0x1400100fd  mov     eax, 10Bh
0x140010102  cmp     [rcx+rdx+18h], ax
0x140010107  jz      short loc_14001012A
0x140010109  mov     eax, 20Bh
0x14001010e  cmp     [rcx+rdx+18h], ax
0x140010113  jnz     short loc_1400100E2
0x140010115  xor     eax, eax
0x140010117  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x14001011f  jbe     short loc_14001013D
0x140010121  cmp     [rcx+rdx+0F8h], eax
0x140010128  jmp     short loc_14001013A
0x14001012a  xor     eax, eax
0x14001012c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140010131  jbe     short loc_14001013D
0x140010133  cmp     [rcx+rdx+0E8h], eax
0x14001013a  setnz   al
0x14001013d  mov     ecx, 2
0x140010142  mov     cs:dword_140029260, eax
0x140010148  call    _get_image_app_type
0x14001014d  mov     ecx, eax; Type
0x14001014f  call    cs:__imp___set_app_type
0x140010155  mov     ecx, cs:_fmode
0x14001015b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001015f  mov     cs:__onexitend, rax
0x140010166  mov     cs:__onexitbegin, rax
0x14001016d  mov     rax, cs:__imp__fmode
0x140010174  mov     [rax], ecx
0x140010176  mov     rcx, cs:__imp__commode; struct _exception *
0x14001017d  mov     eax, cs:_commode
0x140010183  mov     [rcx], eax
0x140010185  call    ?OnReplayIterationCompleted@CAudioPlaybackEventCallback@@UEAAJXZ; CAudioPlaybackEventCallback::OnReplayIterationCompleted(void)
0x14001018a  cmp     cs:__defaultmatherr, 0
0x140010191  jnz     short loc_1400101A0
0x140010193  lea     rcx, ?OnReplayIterationCompleted@CAudioPlaybackEventCallback@@UEAAJXZ; UserMathErrorFunction
0x14001019a  call    cs:__imp___setusermatherr
0x1400101a0  xor     eax, eax
0x1400101a2  add     rsp, 28h
0x1400101a6  retn
```
