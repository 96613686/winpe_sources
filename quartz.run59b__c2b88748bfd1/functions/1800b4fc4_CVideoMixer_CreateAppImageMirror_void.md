# CVideoMixer::CreateAppImageMirror(void)

- ea: `0x1800b4fc4`
- end: `0x1800b5328`
- name: `?CreateAppImageMirror@CVideoMixer@@AEAAJXZ`
- size: `868`
- prototype: `__int64 __fastcall(CVideoMixer *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800b32ac`

## callees

- `0x18002d864`
- `0x1800388a0`
- `0x180039250`
- `0x1800b4fc4`
- `0x1800b5330`
- `0x1800c2874`
- `0x18015e010`

## import_xrefs

- `GDI32!DeleteDC` at `0x1800b52ab`
- `GDI32!DeleteDC` at `0x18015c71f`
- `GDI32!DeleteDC` at `0x1800b52ab`
- `GDI32!DeleteDC` at `0x18015c71f`
- `GDI32!CreateCompatibleDC` at `0x1800b51ed`
- `GDI32!CreateCompatibleDC` at `0x1800b51ed`
- `GDI32!SelectObject` at `0x1800b521e`
- `GDI32!SelectObject` at `0x1800b5285`
- `GDI32!SelectObject` at `0x1800b521e`
- `GDI32!SelectObject` at `0x1800b5285`
- `GDI32!BitBlt` at `0x1800b5271`
- `GDI32!BitBlt` at `0x1800b5271`

## pseudocode

```c
__int64 __fastcall CVideoMixer::CreateAppImageMirror(CVideoMixer *this)
{
  HDC hdcSrc; // r14
  unsigned int v3; // edx
  unsigned int v4; // edx
  int v5; // ecx
  int v6; // edi
  unsigned int v7; // edx
  unsigned int v8; // eax
  bool v9; // sf
  HDC CompatibleDC; // rax
  HGDIOBJ v11; // r15
  BOOL v12; // ebx
  int v13; // ecx
  int v15; // [rsp+50h] [rbp-E8h] BYREF
  struct IDirectDrawSurface7 *v16; // [rsp+58h] [rbp-E0h] BYREF
  HDC hdc; // [rsp+60h] [rbp-D8h] BYREF
  _DWORD v18[2]; // [rsp+68h] [rbp-D0h] BYREF
  HDC v19; // [rsp+70h] [rbp-C8h]
  int v20; // [rsp+80h] [rbp-B8h] BYREF
  int v21; // [rsp+84h] [rbp-B4h] BYREF
  int v22; // [rsp+88h] [rbp-B0h]
  int Pow2; // [rsp+8Ch] [rbp-ACh]
  int v24; // [rsp+D0h] [rbp-68h]
  int v25; // [rsp+D4h] [rbp-64h]
  __int128 v26; // [rsp+D8h] [rbp-60h]
  int v27; // [rsp+E8h] [rbp-50h]
  int v28; // [rsp+ECh] [rbp-4Ch]
  int v29; // [rsp+F0h] [rbp-48h]
  int v30; // [rsp+F4h] [rbp-44h]

  v16 = 0;
  hdcSrc = 0;
  v19 = 0;
  hdc = 0;
  v20 = 136;
  memset_0(&v21, 0, 0x84u);
  v3 = *((_DWORD *)this + 559);
  if ( (*((_BYTE *)this + 112) & 1) != 0 )
  {
    Pow2 = VMR9::NextPow2((VMR9 *)*((unsigned int *)this + 558), v3);
    v22 = VMR9::NextPow2((VMR9 *)v4, v4);
  }
  else
  {
    Pow2 = *((_DWORD *)this + 558);
    v22 = v3;
  }
  v21 = 7;
  v29 = 4096;
  v30 = 24;
  v5 = *((_DWORD *)this + 560);
  if ( (v5 & 3) != 0 )
  {
    v21 = 4103;
    v24 = 32;
    v25 = 64;
    v26 = xmmword_18017C948;
    v27 = 255;
    v28 = 0;
    if ( (v5 & 1) != 0 )
    {
      v25 = 65;
      v28 = -16777216;
    }
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, int *, struct IDirectDrawSurface7 **, _QWORD))(**((_QWORD **)this + 15) + 48LL))(
         *((_QWORD *)this + 15),
         &v20,
         &v16,
         0);
  v15 = v6;
  if ( v6 < 0
    || (*((float *)this + 550) = 1.0 / (float)Pow2,
        *((float *)this + 551) = 1.0 / (float)v22,
        v7 = *((_DWORD *)this + 543),
        v7 == -1) )
  {
LABEL_11:
    v9 = v6 < 0;
    goto LABEL_12;
  }
  v8 = DDColorMatch(v16, v7, &v15);
  *((_DWORD *)this + 544) = v8;
  v6 = v15;
  v9 = v15 < 0;
  if ( !v15 )
  {
    v18[0] = v8;
    v18[1] = v8;
    v6 = ((__int64 (__fastcall *)(struct IDirectDrawSurface7 *, __int64, _DWORD *))v16->lpVtbl->SetColorKey)(
           v16,
           8,
           v18);
    v15 = v6;
    if ( v6 < 0 )
      goto LABEL_22;
    goto LABEL_11;
  }
LABEL_12:
  if ( !v9 )
  {
    v6 = ((__int64 (__fastcall *)(struct IDirectDrawSurface7 *, HDC *))v16->lpVtbl->GetDC)(v16, &hdc);
    v15 = v6;
    if ( v6 >= 0 )
    {
      CompatibleDC = CreateCompatibleDC(hdc);
      hdcSrc = CompatibleDC;
      v19 = CompatibleDC;
      if ( !CompatibleDC )
      {
        v6 = -2147024882;
LABEL_16:
        v15 = v6;
        goto LABEL_22;
      }
      v11 = SelectObject(CompatibleDC, *((HGDIOBJ *)this + 278));
      if ( !v11 )
      {
        v6 = -2147467259;
        goto LABEL_16;
      }
      v12 = BitBlt(hdc, 0, 0, *((_DWORD *)this + 558), *((_DWORD *)this + 559), hdcSrc, 0, 0, 0xCC0020u);
      SelectObject(hdcSrc, v11);
      v13 = v6;
      if ( !v12 )
        v13 = -2147467259;
      v6 = v13;
      v15 = v13;
    }
  }
LABEL_22:
  if ( hdcSrc )
    DeleteDC(hdcSrc);
  if ( hdc )
    ((void (__fastcall *)(struct IDirectDrawSurface7 *))v16->lpVtbl->ReleaseDC)(v16);
  if ( v6 )
  {
    RELEASE<IDDVideoAcceleratorContainer>(&v16);
  }
  else
  {
    RELEASE<IDDVideoAcceleratorContainer>((char *)this + 2192);
    *((_QWORD *)this + 274) = v16;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b4fc4  mov     [rsp+arg_8], rbx
0x1800b4fc9  mov     [rsp+arg_10], rsi
0x1800b4fce  push    rdi
0x1800b4fcf  push    r14
0x1800b4fd1  push    r15
0x1800b4fd3  sub     rsp, 120h
0x1800b4fda  mov     rax, cs:__security_cookie
0x1800b4fe1  xor     rax, rsp
0x1800b4fe4  mov     [rsp+138h+var_28], rax
0x1800b4fec  mov     rsi, rcx
0x1800b4fef  mov     [rsp+138h+var_E0], 0
0x1800b4ff8  xor     r14d, r14d
0x1800b4ffb  mov     [rsp+138h+var_C8], r14
0x1800b5000  mov     [rsp+138h+hdc], r14
0x1800b5005  mov     [rsp+138h+var_B8], 88h
0x1800b5010  xor     edx, edx; Val
0x1800b5012  mov     r8d, 84h; Size
0x1800b5018  lea     rcx, [rsp+138h+var_B4]; void *
0x1800b5020  call    memset_0
0x1800b5025  mov     ecx, [rsi+8B8h]; this
0x1800b502b  mov     edx, [rsi+8BCh]; unsigned int
0x1800b5031  test    byte ptr [rsi+70h], 1
0x1800b5035  jz      short loc_1800B5053
0x1800b5037  call    ?NextPow2@VMR9@@YAII@Z; VMR9::NextPow2(uint)
0x1800b503c  mov     [rsp+138h+var_AC], eax
0x1800b5043  mov     ecx, edx; this
0x1800b5045  call    ?NextPow2@VMR9@@YAII@Z; VMR9::NextPow2(uint)
0x1800b504a  mov     [rsp+138h+var_B0], eax
0x1800b5051  jmp     short loc_1800B5061
0x1800b5053  mov     [rsp+138h+var_AC], ecx
0x1800b505a  mov     [rsp+138h+var_B0], edx
0x1800b5061  mov     [rsp+138h+var_B4], 7
0x1800b506c  mov     [rsp+138h+var_48], 1000h
0x1800b5077  mov     [rsp+138h+var_44], 18h
0x1800b5082  mov     ecx, [rsi+8C0h]
0x1800b5088  test    cl, 3
0x1800b508b  jz      short loc_1800B50F0
0x1800b508d  mov     [rsp+138h+var_B4], 1007h
0x1800b5098  mov     [rsp+138h+var_68], 20h ; ' '
0x1800b50a3  mov     [rsp+138h+var_64], 40h ; '@'
0x1800b50ae  movups  xmm0, cs:xmmword_18017C948
0x1800b50b5  movups  [rsp+138h+var_60], xmm0
0x1800b50bd  mov     eax, cs:dword_18017C958
0x1800b50c3  mov     [rsp+138h+var_50], eax
0x1800b50ca  mov     [rsp+138h+var_4C], 0
0x1800b50d5  test    cl, 1
0x1800b50d8  jz      short loc_1800B50F0
0x1800b50da  mov     [rsp+138h+var_64], 41h ; 'A'
0x1800b50e5  mov     [rsp+138h+var_4C], 0FF000000h
0x1800b50f0  mov     rcx, [rsi+78h]
0x1800b50f4  mov     rax, [rcx]
0x1800b50f7  xor     r9d, r9d
0x1800b50fa  lea     r8, [rsp+138h+var_E0]
0x1800b50ff  lea     rdx, [rsp+138h+var_B8]
0x1800b5107  mov     rax, [rax+30h]
0x1800b510b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5110  mov     edi, eax
0x1800b5112  mov     [rsp+138h+var_E8], eax
0x1800b5116  test    eax, eax
0x1800b5118  js      loc_1800B51B9
0x1800b511e  mov     eax, [rsp+138h+var_AC]
0x1800b5125  xorps   xmm1, xmm1
0x1800b5128  cvtsi2ss xmm1, rax
0x1800b512d  movss   xmm2, cs:__real@3f800000
0x1800b5135  movaps  xmm0, xmm2
0x1800b5138  divss   xmm0, xmm1
0x1800b513c  movss   dword ptr [rsi+898h], xmm0
0x1800b5144  mov     eax, [rsp+138h+var_B0]
0x1800b514b  xorps   xmm1, xmm1
0x1800b514e  cvtsi2ss xmm1, rax
0x1800b5153  divss   xmm2, xmm1
0x1800b5157  movss   dword ptr [rsi+89Ch], xmm2
0x1800b515f  mov     edx, [rsi+87Ch]; unsigned int
0x1800b5165  cmp     edx, 0FFFFFFFFh
0x1800b5168  jz      short loc_1800B51B9
0x1800b516a  lea     r8, [rsp+138h+var_E8]; int *
0x1800b516f  mov     rcx, [rsp+138h+var_E0]; struct IDirectDrawSurface7 *
0x1800b5174  call    ?DDColorMatch@@YAKPEAUIDirectDrawSurface7@@KAEAJ@Z; DDColorMatch(IDirectDrawSurface7 *,ulong,long &)
0x1800b5179  mov     [rsi+880h], eax
0x1800b517f  mov     edi, [rsp+138h+var_E8]
0x1800b5183  test    edi, edi
0x1800b5185  jnz     short loc_1800B51BB
0x1800b5187  mov     [rsp+138h+var_D0], eax
0x1800b518b  mov     [rsp+138h+var_CC], eax
0x1800b518f  mov     rcx, [rsp+138h+var_E0]
0x1800b5194  mov     rax, [rcx]
0x1800b5197  lea     r8, [rsp+138h+var_D0]
0x1800b519c  lea     edx, [rdi+8]
0x1800b519f  mov     rax, [rax+0E8h]
0x1800b51a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b51ab  mov     edi, eax
0x1800b51ad  mov     [rsp+138h+var_E8], eax
0x1800b51b1  test    eax, eax
0x1800b51b3  js      loc_1800B52A3
0x1800b51b9  test    edi, edi
0x1800b51bb  js      loc_1800B52A3
0x1800b51c1  mov     rcx, [rsp+138h+var_E0]
0x1800b51c6  mov     rax, [rcx]
0x1800b51c9  lea     rdx, [rsp+138h+hdc]
0x1800b51ce  mov     rax, [rax+88h]
0x1800b51d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b51da  mov     edi, eax
0x1800b51dc  mov     [rsp+138h+var_E8], eax
0x1800b51e0  test    eax, eax
0x1800b51e2  js      loc_1800B52A3
0x1800b51e8  mov     rcx, [rsp+138h+hdc]; hdc
0x1800b51ed  call    cs:__imp_CreateCompatibleDC
0x1800b51f4  nop     dword ptr [rax+rax+00h]
0x1800b51f9  mov     r14, rax
0x1800b51fc  mov     [rsp+138h+var_C8], rax
0x1800b5201  test    rax, rax
0x1800b5204  jnz     short loc_1800B5214
0x1800b5206  mov     edi, 8007000Eh
0x1800b520b  mov     [rsp+138h+var_E8], edi
0x1800b520f  jmp     loc_1800B52A3
0x1800b5214  mov     rdx, [rsi+8B0h]; h
0x1800b521b  mov     rcx, r14; hdc
0x1800b521e  call    cs:__imp_SelectObject
0x1800b5225  nop     dword ptr [rax+rax+00h]
0x1800b522a  mov     r15, rax
0x1800b522d  test    rax, rax
0x1800b5230  jnz     short loc_1800B5239
0x1800b5232  mov     edi, 80004005h
0x1800b5237  jmp     short loc_1800B520B
0x1800b5239  mov     [rsp+138h+rop], 0CC0020h; rop
0x1800b5241  mov     [rsp+138h+y1], 0; y1
0x1800b5249  mov     [rsp+138h+x1], 0; x1
0x1800b5251  mov     [rsp+138h+hdcSrc], r14; hdcSrc
0x1800b5256  mov     eax, [rsi+8BCh]
0x1800b525c  mov     [rsp+138h+cy], eax; cy
0x1800b5260  mov     r9d, [rsi+8B8h]; cx
0x1800b5267  xor     r8d, r8d; y
0x1800b526a  xor     edx, edx; x
0x1800b526c  mov     rcx, [rsp+138h+hdc]; hdc
0x1800b5271  call    cs:__imp_BitBlt
0x1800b5278  nop     dword ptr [rax+rax+00h]
0x1800b527d  mov     ebx, eax
0x1800b527f  mov     rdx, r15; h
0x1800b5282  mov     rcx, r14; hdc
0x1800b5285  call    cs:__imp_SelectObject
0x1800b528c  nop     dword ptr [rax+rax+00h]
0x1800b5291  mov     ecx, edi
0x1800b5293  mov     edi, 80004005h
0x1800b5298  test    ebx, ebx
0x1800b529a  cmovz   ecx, edi
0x1800b529d  mov     edi, ecx
0x1800b529f  mov     [rsp+138h+var_E8], ecx
0x1800b52a3  test    r14, r14
0x1800b52a6  jz      short loc_1800B52B7
0x1800b52a8  mov     rcx, r14; hdc
0x1800b52ab  call    cs:__imp_DeleteDC
0x1800b52b2  nop     dword ptr [rax+rax+00h]
0x1800b52b7  mov     rdx, [rsp+138h+hdc]
0x1800b52bc  test    rdx, rdx
0x1800b52bf  jz      short loc_1800B52D5
0x1800b52c1  mov     rcx, [rsp+138h+var_E0]
0x1800b52c6  mov     rax, [rcx]
0x1800b52c9  mov     rax, [rax+0D0h]
0x1800b52d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b52d5  test    edi, edi
0x1800b52d7  jnz     short loc_1800B52F2
0x1800b52d9  lea     rbx, [rsi+890h]
0x1800b52e0  mov     rcx, rbx
0x1800b52e3  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b52e8  mov     rax, [rsp+138h+var_E0]
0x1800b52ed  mov     [rbx], rax
0x1800b52f0  jmp     short loc_1800B52FC
0x1800b52f2  lea     rcx, [rsp+138h+var_E0]
0x1800b52f7  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b52fc  mov     eax, edi
0x1800b52fe  mov     rcx, [rsp+138h+var_28]
0x1800b5306  xor     rcx, rsp; StackCookie
0x1800b5309  call    __security_check_cookie
0x1800b530e  lea     r11, [rsp+138h+var_18]
0x1800b5316  mov     rbx, [r11+28h]
0x1800b531a  mov     rsi, [r11+30h]
0x1800b531e  mov     rsp, r11
0x1800b5321  pop     r15
0x1800b5323  pop     r14
0x1800b5325  pop     rdi
0x1800b5326  retn
0x18015c70d  push    rbp
0x18015c70f  sub     rsp, 50h
0x18015c713  mov     rbp, rdx
0x18015c716  mov     rcx, [rbp+70h]; hdc
0x18015c71a  test    rcx, rcx
0x18015c71d  jz      short loc_18015C72C
0x18015c71f  call    cs:__imp_DeleteDC
0x18015c726  nop     dword ptr [rax+rax+00h]
0x18015c72b  nop
0x18015c72c  mov     rdx, [rbp+60h]
0x18015c730  test    rdx, rdx
0x18015c733  jz      short loc_18015C749
0x18015c735  mov     rcx, [rbp+58h]
0x18015c739  mov     rax, [rcx]
0x18015c73c  mov     rax, [rax+0D0h]
0x18015c743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c748  nop
0x18015c749  add     rsp, 50h
0x18015c74d  pop     rbp
0x18015c74e  retn
```
