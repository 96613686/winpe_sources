# mjpeg_dxva_decode

- ea: `0x180043e94`
- end: `0x180044293`
- name: `mjpeg_dxva_decode`
- size: `1023`
- prototype: `__int64 __fastcall(struct jpeg_decompress_struct *, bool, __int64 *, _DWORD *, _DWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001ff0c`

## callees

- `0x180024220`
- `0x180024bf4`
- `0x18003a794`
- `0x1800438e4`
- `0x180043ad0`
- `0x180043c04`
- `0x180043c98`
- `0x180043e94`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall mjpeg_dxva_decode(
        struct jpeg_decompress_struct *a1,
        bool a2,
        __int64 *a3,
        _DWORD *a4,
        _DWORD *a5,
        unsigned __int64 a6,
        unsigned __int64 a7)
{
  __int64 v11; // r8
  __int64 result; // rax
  __int64 v13; // rdx
  int v14; // esi
  __int64 v15; // rax
  __int64 v16; // r13
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int64 v19; // r10
  __int64 v20; // rax
  __int64 v21; // rdx
  void *v22; // r11
  __int64 v23; // rcx
  struct _DXVA_PicParams_MJPEG *v24; // rsi
  __int64 v25; // rdx
  unsigned int Size; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Size_4; // [rsp+34h] [rbp-CCh] BYREF
  struct _DXVA_PicParams_MJPEG *v28; // [rsp+38h] [rbp-C8h] BYREF
  struct _DXVA_QMatrix_MJPEG *v29; // [rsp+40h] [rbp-C0h] BYREF
  struct _DXVA_HuffmanTable_MJPEG *v30; // [rsp+48h] [rbp-B8h] BYREF
  void *v31; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v32[8]; // [rsp+60h] [rbp-A0h] BYREF
  struct _DXVA_PicParams_MJPEG *v33; // [rsp+68h] [rbp-98h]
  int v34; // [rsp+70h] [rbp-90h]
  void *v35; // [rsp+88h] [rbp-78h]
  int v36; // [rsp+90h] [rbp-70h]
  struct _DXVA_QMatrix_MJPEG *v37; // [rsp+98h] [rbp-68h]
  int v38; // [rsp+A0h] [rbp-60h]
  struct _DXVA_HuffmanTable_MJPEG *v39; // [rsp+A8h] [rbp-58h]
  int v40; // [rsp+B0h] [rbp-50h]
  _OWORD v41[3]; // [rsp+E0h] [rbp-20h] BYREF
  int v42; // [rsp+110h] [rbp+10h]

  Size = 64;
  memset_0(v32, 0, 0x80u);
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v42 = 0;
  memset(v41, 0, sizeof(v41));
  if ( !a3 || !(*(__int64 (__fastcall **)(__int64 *))(*a3 + 400))(a3) )
    return 2147500033LL;
  *a4 = -1;
  *a5 = -1;
  if ( (int)DXVADescFromPictureInfo(a1, a2, (struct DXVAVideoDesc *)v41) < 0 )
    return 3222130769LL;
  LOBYTE(v11) = 1;
  if ( (*(int (__fastcall **)(__int64 *, _OWORD *, __int64))(*a3 + 304))(a3, v41, v11) < 0 )
    return 3222130833LL;
  v13 = (*(unsigned __int16 (__fastcall **)(__int64 *, _DWORD *))(*a3 + 408))(a3, a5);
  *a4 = v13;
  if ( (_DWORD)v13 == 0xFFFF )
  {
    (*(void (__fastcall **)(__int64 *, __int64))(*a3 + 376))(a3, 64);
    v13 = (*(unsigned __int16 (__fastcall **)(__int64 *, _DWORD *))(*a3 + 408))(a3, a4);
    *a4 = v13;
    if ( (_DWORD)v13 == 0xFFFF )
      return 2147942414LL;
  }
  result = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(*a3 + 88))(a3, v13, 0);
  if ( (int)result >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct _DXVA_PicParams_MJPEG **, unsigned int *))(*a3 + 112))(
            a3,
            0,
            &v28,
            &Size);
    if ( v14 < 0 )
      goto LABEL_24;
    memset_0(v28, 0, Size);
    MJPEG_FillPicParams(a1, v28);
    v15 = *a3;
    Size = 512;
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(v15 + 168))(a3, 4, 512);
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct _DXVA_QMatrix_MJPEG **, unsigned int *))(*a3 + 112))(
            a3,
            4,
            &v29,
            &Size);
    if ( v14 < 0 )
      goto LABEL_24;
    memset_0(v29, 0, Size);
    MJPEG_FillQuantizationMatrix(a1, v29);
    v16 = *(_QWORD *)(*((_QWORD *)a1 + 5) + 8LL);
    v38 = 512;
    v33 = v28;
    v37 = v29;
    v34 = 64;
    if ( *((_BYTE *)a1 + 3448) )
    {
      v17 = *a3;
      Size = 2176;
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(v17 + 168))(a3, 9, 2176);
      v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, struct _DXVA_HuffmanTable_MJPEG **, unsigned int *))(*a3 + 112))(
              a3,
              9,
              &v30,
              &Size);
      if ( v14 < 0 )
        goto LABEL_24;
      memset_0(v30, 0, Size);
      MJPEG_FillHuffmanTable(a1, v30);
      v39 = v30;
      v40 = 2176;
    }
    v18 = *a3;
    v31 = 0;
    Size_4 = 0;
    (*(void (__fastcall **)(__int64 *, __int64, unsigned __int64))(v18 + 168))(a3, 6, a7);
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, void **, unsigned int *))(*a3 + 112))(a3, 6, &v31, &Size_4);
    if ( v14 >= 0 )
    {
      v19 = Size_4;
      if ( Size_4 >= (unsigned __int64)(v16 + 16) )
      {
        v20 = *((int *)a1 + 100);
        v21 = *((_QWORD *)a1 + 5);
        v22 = v31;
        v35 = v31;
        v23 = 2 * v20 + 8;
        v36 = a7;
        if ( *(_QWORD *)v21 - v23 < a6 )
          return 3222130849LL;
        v24 = v28;
        v25 = (unsigned int)(v23 + *(_DWORD *)(v21 + 8));
        *((_DWORD *)v28 + 8) = v25;
        if ( v25 + **((_QWORD **)a1 + 5) - v23 - a6 > a7 || (unsigned int)v25 > v19 )
          return 2147500035LL;
        memcpy_0(v22, (const void *)(**((_QWORD **)a1 + 5) - v23), (unsigned int)v25);
        *((_DWORD *)v24 + 4) = 0;
        return (*(__int64 (__fastcall **)(__int64 *, _QWORD, _BYTE *))(*a3 + 96))(a3, (unsigned int)*a4, v32);
      }
    }
LABEL_24:
    (*(void (__fastcall **)(__int64 *, _QWORD))(*a3 + 104))(a3, (unsigned int)*a4);
    return (unsigned int)v14;
  }
  return result;
}

```

## disassembly

```asm
0x180043e94  mov     [rsp-8+arg_8], rbx
0x180043e99  push    rbp
0x180043e9a  push    rsi
0x180043e9b  push    rdi
0x180043e9c  push    r12
0x180043e9e  push    r13
0x180043ea0  push    r14
0x180043ea2  push    r15
0x180043ea4  lea     rbp, [rsp-20h]
0x180043ea9  sub     rsp, 120h
0x180043eb0  mov     rax, cs:__security_cookie
0x180043eb7  xor     rax, rsp
0x180043eba  mov     [rbp+50h+var_38], rax
0x180043ebe  mov     rsi, [rbp+50h+arg_20]
0x180043ec5  mov     rbx, r8
0x180043ec8  mov     r12, [rbp+50h+arg_28]
0x180043ecf  mov     r15b, dl
0x180043ed2  mov     rdi, rcx
0x180043ed5  mov     dword ptr [rsp+150h+Size], 40h ; '@'
0x180043edd  xor     edx, edx; Val
0x180043edf  lea     rcx, [rsp+150h+var_F0]; void *
0x180043ee4  mov     r8d, 80h; Size
0x180043eea  mov     r14, r9
0x180043eed  call    memset_0
0x180043ef2  xor     r13d, r13d
0x180043ef5  xorps   xmm0, xmm0
0x180043ef8  xor     eax, eax
0x180043efa  mov     [rsp+150h+var_118], r13
0x180043eff  mov     [rsp+150h+var_110], r13
0x180043f04  mov     [rsp+150h+var_108], r13
0x180043f09  mov     [rbp+50h+var_40], eax
0x180043f0c  movups  [rbp+50h+var_70], xmm0
0x180043f10  movups  [rbp+50h+var_60], xmm0
0x180043f14  movups  [rbp+50h+var_50], xmm0
0x180043f18  test    rbx, rbx
0x180043f1b  jz      loc_180044267
0x180043f21  mov     rax, [rbx]
0x180043f24  mov     rcx, rbx
0x180043f27  mov     rax, [rax+190h]
0x180043f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f33  test    rax, rax
0x180043f36  jz      loc_180044267
0x180043f3c  or      eax, 0FFFFFFFFh
0x180043f3f  lea     r8, [rbp+50h+var_70]; struct DXVAVideoDesc *
0x180043f43  mov     [r14], eax
0x180043f46  mov     dl, r15b; bool
0x180043f49  mov     rcx, rdi; struct jpeg_decompress_struct *
0x180043f4c  mov     [rsi], eax
0x180043f4e  call    ?DXVADescFromPictureInfo@@YAJAEAUjpeg_decompress_struct@@_NAEAUDXVAVideoDesc@@@Z; DXVADescFromPictureInfo(jpeg_decompress_struct &,bool,DXVAVideoDesc &)
0x180043f53  test    eax, eax
0x180043f55  jns     short loc_180043F61
0x180043f57  mov     eax, 0C00DD051h
0x180043f5c  jmp     loc_18004426C
0x180043f61  mov     rax, [rbx]
0x180043f64  lea     rdx, [rbp+50h+var_70]
0x180043f68  mov     r8b, 1
0x180043f6b  mov     rcx, rbx
0x180043f6e  mov     rax, [rax+130h]
0x180043f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f7a  test    eax, eax
0x180043f7c  jns     short loc_180043F88
0x180043f7e  mov     eax, 0C00DD091h
0x180043f83  jmp     loc_18004426C
0x180043f88  mov     rax, [rbx]
0x180043f8b  mov     rdx, rsi
0x180043f8e  mov     rcx, rbx
0x180043f91  mov     rax, [rax+198h]
0x180043f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f9d  movzx   edx, ax
0x180043fa0  mov     esi, 0FFFFh
0x180043fa5  mov     [r14], edx
0x180043fa8  cmp     edx, esi
0x180043faa  jnz     short loc_180043FEC
0x180043fac  mov     rax, [rbx]
0x180043faf  mov     edx, 40h ; '@'
0x180043fb4  mov     rcx, rbx
0x180043fb7  mov     rax, [rax+178h]
0x180043fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fc3  mov     rax, [rbx]
0x180043fc6  mov     rdx, r14
0x180043fc9  mov     rcx, rbx
0x180043fcc  mov     rax, [rax+198h]
0x180043fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fd8  movzx   edx, ax
0x180043fdb  mov     [r14], edx
0x180043fde  cmp     edx, esi
0x180043fe0  jnz     short loc_180043FEC
0x180043fe2  mov     eax, 8007000Eh
0x180043fe7  jmp     loc_18004426C
0x180043fec  mov     rax, [rbx]
0x180043fef  xor     r8d, r8d
0x180043ff2  mov     rcx, rbx
0x180043ff5  mov     rax, [rax+58h]
0x180043ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ffe  test    eax, eax
0x180044000  js      loc_18004426C
0x180044006  mov     rax, [rbx]
0x180044009  lea     r9, [rsp+150h+Size]
0x18004400e  lea     r8, [rsp+150h+var_118]
0x180044013  xor     edx, edx
0x180044015  mov     rcx, rbx
0x180044018  mov     rax, [rax+70h]
0x18004401c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044021  mov     esi, eax
0x180044023  test    eax, eax
0x180044025  js      loc_180044251
0x18004402b  mov     r8d, dword ptr [rsp+150h+Size]; Size
0x180044030  xor     edx, edx; Val
0x180044032  mov     rcx, [rsp+150h+var_118]; void *
0x180044037  call    memset_0
0x18004403c  mov     rdx, [rsp+150h+var_118]; struct _DXVA_PicParams_MJPEG *
0x180044041  mov     rcx, rdi; struct jpeg_decompress_struct *
0x180044044  call    ?MJPEG_FillPicParams@@YAXPEAUjpeg_decompress_struct@@PEAU_DXVA_PicParams_MJPEG@@@Z; MJPEG_FillPicParams(jpeg_decompress_struct *,_DXVA_PicParams_MJPEG *)
0x180044049  mov     rax, [rbx]
0x18004404c  mov     r15d, 200h
0x180044052  mov     esi, 4
0x180044057  mov     dword ptr [rsp+150h+Size], r15d
0x18004405c  mov     r8d, r15d
0x18004405f  mov     edx, esi
0x180044061  mov     rcx, rbx
0x180044064  mov     rax, [rax+0A8h]
0x18004406b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044070  mov     rax, [rbx]
0x180044073  lea     r9, [rsp+150h+Size]
0x180044078  lea     r8, [rsp+150h+var_110]
0x18004407d  mov     edx, esi
0x18004407f  mov     rcx, rbx
0x180044082  mov     rax, [rax+70h]
0x180044086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004408b  mov     esi, eax
0x18004408d  test    eax, eax
0x18004408f  js      loc_180044251
0x180044095  mov     r8d, dword ptr [rsp+150h+Size]; Size
0x18004409a  xor     edx, edx; Val
0x18004409c  mov     rcx, [rsp+150h+var_110]; void *
0x1800440a1  call    memset_0
0x1800440a6  mov     rdx, [rsp+150h+var_110]; struct _DXVA_QMatrix_MJPEG *
0x1800440ab  mov     rcx, rdi; struct jpeg_decompress_struct *
0x1800440ae  call    ?MJPEG_FillQuantizationMatrix@@YAXPEAUjpeg_decompress_struct@@PEAU_DXVA_QMatrix_MJPEG@@@Z; MJPEG_FillQuantizationMatrix(jpeg_decompress_struct *,_DXVA_QMatrix_MJPEG *)
0x1800440b3  mov     rax, [rdi+28h]
0x1800440b7  mov     r13, [rax+8]
0x1800440bb  mov     rax, [rsp+150h+var_118]
0x1800440c0  mov     [rbp+50h+var_B0], r15d
0x1800440c4  xor     r15d, r15d
0x1800440c7  mov     [rsp+150h+var_E8], rax
0x1800440cc  mov     rax, [rsp+150h+var_110]
0x1800440d1  mov     [rbp+50h+var_B8], rax
0x1800440d5  mov     [rsp+150h+var_E0], 40h ; '@'
0x1800440dd  cmp     [rdi+0D78h], r15b
0x1800440e4  jz      short loc_18004415D
0x1800440e6  mov     rax, [rbx]
0x1800440e9  lea     esi, [r15+9]
0x1800440ed  mov     ecx, 880h
0x1800440f2  mov     edx, esi
0x1800440f4  mov     dword ptr [rsp+150h+Size], ecx
0x1800440f8  mov     r8d, ecx
0x1800440fb  mov     rcx, rbx
0x1800440fe  mov     rax, [rax+0A8h]
0x180044105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004410a  mov     rax, [rbx]
0x18004410d  lea     r9, [rsp+150h+Size]
0x180044112  lea     r8, [rsp+150h+var_108]
0x180044117  mov     edx, esi
0x180044119  mov     rcx, rbx
0x18004411c  mov     rax, [rax+70h]
0x180044120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044125  mov     esi, eax
0x180044127  test    eax, eax
0x180044129  js      loc_180044251
0x18004412f  mov     r8d, dword ptr [rsp+150h+Size]; Size
0x180044134  xor     edx, edx; Val
0x180044136  mov     rcx, [rsp+150h+var_108]; void *
0x18004413b  call    memset_0
0x180044140  mov     rdx, [rsp+150h+var_108]; struct _DXVA_HuffmanTable_MJPEG *
0x180044145  mov     rcx, rdi; struct jpeg_decompress_struct *
0x180044148  call    ?MJPEG_FillHuffmanTable@@YAXPEAUjpeg_decompress_struct@@PEAU_DXVA_HuffmanTable_MJPEG@@@Z; MJPEG_FillHuffmanTable(jpeg_decompress_struct *,_DXVA_HuffmanTable_MJPEG *)
0x18004414d  mov     rax, [rsp+150h+var_108]
0x180044152  mov     [rbp+50h+var_A8], rax
0x180044156  mov     [rbp+50h+var_A0], 880h
0x18004415d  mov     rax, [rbx]
0x180044160  mov     esi, 6
0x180044165  mov     [rsp+150h+var_100], r15
0x18004416a  mov     edx, esi
0x18004416c  mov     dword ptr [rsp+150h+Size+4], r15d
0x180044171  mov     rcx, rbx
0x180044174  mov     r15, [rbp+50h+arg_30]
0x18004417b  mov     rax, [rax+0A8h]
0x180044182  mov     r8, r15
0x180044185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004418a  mov     rax, [rbx]
0x18004418d  lea     r9, [rsp+150h+Size+4]
0x180044192  lea     r8, [rsp+150h+var_100]
0x180044197  mov     edx, esi
0x180044199  mov     rcx, rbx
0x18004419c  mov     rax, [rax+70h]
0x1800441a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441a5  mov     esi, eax
0x1800441a7  test    eax, eax
0x1800441a9  js      loc_180044251
0x1800441af  mov     r10d, dword ptr [rsp+150h+Size+4]
0x1800441b4  lea     rax, [r13+10h]
0x1800441b8  cmp     r10, rax
0x1800441bb  jb      loc_180044251
0x1800441c1  movsxd  rax, dword ptr [rdi+190h]
0x1800441c8  mov     rdx, [rdi+28h]
0x1800441cc  mov     r11, [rsp+150h+var_100]
0x1800441d1  mov     [rbp+50h+var_C8], r11
0x1800441d5  lea     rcx, ds:8[rax*2]
0x1800441dd  mov     [rbp+50h+var_C0], r15d
0x1800441e1  mov     rax, [rdx]
0x1800441e4  sub     rax, rcx
0x1800441e7  cmp     rax, r12
0x1800441ea  jnb     short loc_1800441F3
0x1800441ec  mov     eax, 0C00DD0A1h
0x1800441f1  jmp     short loc_18004426C
0x1800441f3  mov     edx, [rdx+8]
0x1800441f6  mov     rsi, [rsp+150h+var_118]
0x1800441fb  add     edx, ecx
0x1800441fd  mov     r8d, edx; Size
0x180044200  mov     [rsi+20h], edx
0x180044203  mov     rax, [rdi+28h]
0x180044207  mov     r9, [rax]
0x18004420a  sub     r9, rcx
0x18004420d  sub     r9, r12
0x180044210  lea     rax, [rdx+r9]
0x180044214  cmp     rax, r15
0x180044217  ja      short loc_18004424A
0x180044219  cmp     r8, r10
0x18004421c  ja      short loc_18004424A
0x18004421e  lea     rdx, [r9+r12]; Src
0x180044222  mov     rcx, r11; void *
0x180044225  call    memcpy_0
0x18004422a  mov     dword ptr [rsi+10h], 0
0x180044231  lea     r8, [rsp+150h+var_F0]
0x180044236  mov     rax, [rbx]
0x180044239  mov     rcx, rbx
0x18004423c  mov     edx, [r14]
0x18004423f  mov     rax, [rax+60h]
0x180044243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044248  jmp     short loc_18004426C
0x18004424a  mov     eax, 80004003h
0x18004424f  jmp     short loc_18004426C
0x180044251  mov     rax, [rbx]
0x180044254  mov     rcx, rbx
0x180044257  mov     edx, [r14]
0x18004425a  mov     rax, [rax+68h]
0x18004425e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044263  mov     eax, esi
0x180044265  jmp     short loc_18004426C
0x180044267  mov     eax, 80004001h
0x18004426c  mov     rcx, [rbp+50h+var_38]
0x180044270  xor     rcx, rsp; StackCookie
0x180044273  call    __security_check_cookie
0x180044278  mov     rbx, [rsp+150h+arg_8]
0x180044280  add     rsp, 120h
0x180044287  pop     r15
0x180044289  pop     r14
0x18004428b  pop     r13
0x18004428d  pop     r12
0x18004428f  pop     rdi
0x180044290  pop     rsi
0x180044291  pop     rbp
0x180044292  retn
```
