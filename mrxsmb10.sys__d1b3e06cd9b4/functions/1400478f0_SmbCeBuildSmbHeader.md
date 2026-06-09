# SmbCeBuildSmbHeader

- ea: `0x1400478f0`
- end: `0x140047dab`
- name: `SmbCeBuildSmbHeader`
- size: `1211`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140012940`
- `0x140035a60`
- `0x14003e26c`
- `0x14003e560`
- `0x140046a50`
- `0x140046bb0`
- `0x1400512e0`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x140016640`
- `0x1400478f0`

## import_xrefs

- `mrxsmb!MRxSmbUseKernelModeSecurity` at `0x140047986`

## pseudocode

```c
__int64 __fastcall SmbCeBuildSmbHeader(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, char *a5, char **a6)
{
  __int64 v6; // rdi
  __int16 v9; // dx
  __int64 v10; // rsi
  __int64 v11; // r15
  __int64 v12; // r9
  int v13; // r8d
  __int64 v14; // r10
  __int16 v15; // cx
  __int64 v16; // rax
  int v17; // r8d
  __int16 v18; // cx
  __int16 v19; // dx
  __int16 v20; // cx
  char *v21; // r13
  int v22; // ebp
  char v23; // cl
  int v24; // eax
  _DWORD *v25; // rdx
  int v26; // edi
  _DWORD *v28; // r10
  bool v29; // zf
  __int64 v30; // rdx
  __int64 v31; // r10
  char v32; // bl
  char v33; // al
  int v34; // eax
  unsigned int v35; // [rsp+20h] [rbp-48h] BYREF
  _DWORD *v36; // [rsp+28h] [rbp-40h]
  char v37; // [rsp+78h] [rbp+10h]
  char v38; // [rsp+80h] [rbp+18h]

  v6 = a3;
  if ( a3 >= 0x20 )
  {
    v9 = 0;
    v10 = *(_QWORD *)(a1 + 80);
    v11 = *(_QWORD *)(a1 + 88);
    v38 = -1;
    v35 = a3 - 32;
    if ( v11 )
      v12 = *(_QWORD *)(v11 + 96);
    else
      v12 = 0;
    if ( *(_DWORD *)(v10 + 416) == 5 )
    {
      v13 = *(_DWORD *)(v10 + 420);
      v14 = *(_QWORD *)(a1 + 24);
      if ( (v13 & 0x40000) != 0 )
      {
        v9 = 2050;
        if ( v12 )
        {
          if ( (*(_DWORD *)(v12 + 136) & 8) != 0 || MRxSmbUseKernelModeSecurity )
            v9 = 2;
        }
      }
      v15 = v9 | 0x4000;
      if ( (v13 & 0x100000) == 0 )
        v15 = v9;
      if ( v14 )
      {
        v16 = *(_QWORD *)(v14 + 56);
        if ( v16 )
        {
          if ( (*(_DWORD *)(v16 + 156) & 0x20000) != 0 )
            v15 |= 0x400u;
        }
      }
      v9 = v15;
    }
    v17 = *(_DWORD *)(v10 + 420);
    v18 = v9 | 0x8000;
    if ( (v17 & 0x8000) == 0 )
      v18 = v9;
    v19 = v18 | 1;
    if ( (v17 & 0x80u) == 0 )
      v19 = v18;
    v20 = v19 | 2;
    if ( (v17 & 0x1000) == 0 )
      v20 = v19;
    if ( MRxSmbSecuritySignaturesEnabled )
      v20 |= 4u;
    if ( MRxSmbSecuritySignaturesRequired || (*(_BYTE *)(v10 + 673) & 1) != 0 )
      v20 |= 0x10u;
    v21 = (char *)(a2 + 4);
    *(_OWORD *)a2 = 0;
    *(_OWORD *)(a2 + 16) = 0;
    *(_DWORD *)a2 = 1112364031;
    *(_BYTE *)(a2 + 9) = 24;
    *(_WORD *)(a2 + 10) = v20;
    *(_DWORD *)(a2 + 24) = -16777217;
    *(_DWORD *)(a2 + 5) = 0;
    if ( *(_DWORD *)(v10 + 4) == 2 )
    {
      v22 = 0;
      if ( v12 )
        *(_WORD *)(a2 + 28) = *(_WORD *)(v12 + 132);
      if ( v11 )
      {
        v23 = *(_BYTE *)(v11 + 112) & 1;
        *(_WORD *)(a2 + 24) = *(_WORD *)(v11 + 114);
      }
      else
      {
        v23 = 1;
      }
      v24 = *(_DWORD *)(a1 + 72);
      v25 = (_DWORD *)(a1 + 72);
      v37 = v23;
      v36 = (_DWORD *)(a1 + 72);
      if ( (v24 & 0x100) != 0 )
      {
        v29 = *(_DWORD *)(v12 + 12) == 3;
        v28 = (_DWORD *)(a2 + 32);
        v36 = (_DWORD *)(a2 + 32);
        if ( v29 && (*(_DWORD *)(v10 + 420) & 0x10100) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
            v28 = (_DWORD *)(a2 + 32);
          }
          *v21 = 115;
          v38 = 115;
          *(_WORD *)(a2 + 24) = 0;
          v21 = (char *)v28 + 1;
          v22 = (**(__int64 (__fastcall ***)(__int64, _DWORD *, unsigned int *))(v10 + 408))(a1, v28, &v35);
          if ( v22 < 0 )
            goto LABEL_39;
          v30 = v35;
          *(_WORD *)(a2 + 35) = v6 - v35;
          v31 = v6 - v30;
          v25 = (_DWORD *)(a1 + 72);
          v28 = (_DWORD *)(a2 + v31);
          v29 = (*(_BYTE *)(v10 + 672) & 0x18) == 16;
          v36 = v28;
          v23 = v37;
          if ( v29 )
            *(_QWORD *)(a2 + 14) = *(_QWORD *)InitialSecuritySignature;
        }
      }
      else
      {
        if ( (v24 & 0x200) == 0 )
          goto LABEL_33;
        v28 = (_DWORD *)(a2 + 32);
        v36 = (_DWORD *)(a2 + 32);
      }
      if ( (*v25 & 0x200) == 0 || v23 )
        goto LABEL_40;
      if ( (*(_DWORD *)(v10 + 420) & 0x10) != 0 )
      {
        v32 = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
          v28 = v36;
        }
        v33 = 117;
      }
      else
      {
        v32 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
          v28 = v36;
        }
        v33 = 112;
      }
      v38 = v33;
      *v21 = v33;
      v22 = (*(__int64 (__fastcall **)(__int64, _DWORD *, unsigned int *))(*(_QWORD *)(v10 + 408) + 8LL))(a1, v28, &v35);
      if ( v22 >= 0 )
      {
        v25 = (_DWORD *)(a1 + 72);
        if ( v32 )
        {
          v21 = (char *)v36 + 1;
          *(_WORD *)((char *)v36 + 3) = v6 - v35;
        }
        else
        {
          v21 = 0;
        }
        goto LABEL_40;
      }
    }
    else
    {
      v22 = -1073741816;
    }
LABEL_39:
    v25 = (_DWORD *)(a1 + 72);
LABEL_40:
    v36 = v25;
LABEL_33:
    v26 = v6 - v35;
    *a6 = v21;
    *a4 = v26;
    *a5 = v38;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids,
        (unsigned int)*a4);
      v25 = v36;
    }
    if ( v22 )
    {
      v34 = *v25;
      if ( (*v25 & 0x100) != 0 )
        *(_DWORD *)(a1 + 248) = v22;
      if ( (v34 & 0x200) != 0 )
        _InterlockedExchange((volatile __int32 *)(v11 + 12), 1);
    }
    return (unsigned int)v22;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, a3);
  return 3221225507LL;
}

```

## disassembly

```asm
0x1400478f0  mov     [rsp+arg_18], r9
0x1400478f5  push    rbx
0x1400478f6  push    rdi
0x1400478f7  push    r12
0x1400478f9  push    r14
0x1400478fb  sub     rsp, 48h
0x1400478ff  mov     edi, r8d
0x140047902  mov     rbx, rdx
0x140047905  mov     r14, rcx
0x140047908  cmp     r8d, 20h ; ' '
0x14004790c  jb      loc_140047B32
0x140047912  mov     [rsp+68h+arg_0], rbp
0x140047917  lea     eax, [rdi-20h]
0x14004791a  mov     [rsp+68h+var_28], rsi
0x14004791f  xor     edx, edx
0x140047921  mov     rsi, [rcx+50h]
0x140047925  mov     [rsp+68h+var_30], r13
0x14004792a  mov     [rsp+68h+var_38], r15
0x14004792f  mov     r15, [rcx+58h]
0x140047933  mov     [rsp+68h+arg_10], 0FFh
0x14004793b  mov     [rsp+68h+var_48], eax
0x14004793f  test    r15, r15
0x140047942  jz      loc_140047B56
0x140047948  mov     r9, [r15+60h]
0x14004794c  cmp     dword ptr [rsi+1A0h], 5
0x140047953  mov     r11d, 400h
0x140047959  jnz     short loc_1400479C8
0x14004795b  mov     r8d, [rsi+1A4h]
0x140047962  mov     r10, [rcx+18h]
0x140047966  bt      r8d, 12h
0x14004796b  jnb     short loc_140047996
0x14004796d  mov     edx, 802h
0x140047972  test    r9, r9
0x140047975  jz      short loc_140047996
0x140047977  mov     eax, [r9+88h]
0x14004797e  test    al, 8
0x140047980  jnz     loc_140047B88
0x140047986  mov     rax, cs:__imp_MRxSmbUseKernelModeSecurity
0x14004798d  cmp     byte ptr [rax], 0
0x140047990  jnz     loc_140047B88
0x140047996  movzx   ecx, dx
0x140047999  or      cx, 4000h
0x14004799e  bt      r8d, 14h
0x1400479a3  cmovnb  cx, dx
0x1400479a7  test    r10, r10
0x1400479aa  jz      short loc_1400479C5
0x1400479ac  mov     rax, [r10+38h]
0x1400479b0  test    rax, rax
0x1400479b3  jz      short loc_1400479C5
0x1400479b5  test    dword ptr [rax+9Ch], 20000h
0x1400479bf  jnz     loc_140047B92
0x1400479c5  movzx   edx, cx
0x1400479c8  mov     r8d, [rsi+1A4h]
0x1400479cf  movzx   ecx, dx
0x1400479d2  mov     r10d, 8000h
0x1400479d8  or      cx, r10w
0x1400479dc  test    r10d, r8d
0x1400479df  cmovz   cx, dx
0x1400479e3  movzx   edx, cx
0x1400479e6  or      dx, 1
0x1400479ea  test    r8b, 80h
0x1400479ee  cmovz   dx, cx
0x1400479f2  movzx   ecx, dx
0x1400479f5  or      cx, 2
0x1400479f9  bt      r8d, 0Ch
0x1400479fe  cmovnb  cx, dx
0x140047a02  cmp     cs:MRxSmbSecuritySignaturesEnabled, 0
0x140047a09  jz      short loc_140047A0F
0x140047a0b  or      cx, 4
0x140047a0f  cmp     cs:MRxSmbSecuritySignaturesRequired, 0
0x140047a16  jnz     loc_140047B9B
0x140047a1c  test    byte ptr [rsi+2A1h], 1
0x140047a23  jnz     loc_140047B9B
0x140047a29  xorps   xmm0, xmm0
0x140047a2c  lea     r13, [rbx+4]
0x140047a30  movups  xmmword ptr [rbx], xmm0
0x140047a33  lea     r12, WPP_GLOBAL_Control
0x140047a3a  movups  xmmword ptr [rbx+10h], xmm0
0x140047a3e  mov     dword ptr [rbx], 424D53FFh
0x140047a44  mov     byte ptr [rbx+9], 18h
0x140047a48  mov     [rbx+0Ah], cx
0x140047a4c  mov     dword ptr [rbx+18h], 0FEFFFFFFh
0x140047a53  mov     dword ptr [rbx+5], 0
0x140047a5a  cmp     dword ptr [rsi+4], 2
0x140047a5e  jnz     loc_140047B22
0x140047a64  xor     ebp, ebp
0x140047a66  test    r9, r9
0x140047a69  jz      short loc_140047A77
0x140047a6b  movzx   eax, word ptr [r9+84h]
0x140047a73  mov     [rbx+1Ch], ax
0x140047a77  test    r15, r15
0x140047a7a  jz      loc_140047B5E
0x140047a80  movzx   ecx, byte ptr [r15+70h]
0x140047a85  movzx   eax, word ptr [r15+72h]
0x140047a8a  and     cl, 1
0x140047a8d  mov     [rbx+18h], ax
0x140047a91  mov     eax, [r14+48h]
0x140047a95  lea     rdx, [r14+48h]
0x140047a99  mov     [rsp+68h+arg_8], cl
0x140047a9d  mov     [rsp+68h+var_40], rdx
0x140047aa2  bt      eax, 8
0x140047aa6  jb      loc_140047BB2
0x140047aac  bt      eax, 9
0x140047ab0  jb      loc_140047BA4
0x140047ab6  mov     rax, [rsp+68h+arg_28]
0x140047abe  mov     r9, [rsp+68h+arg_18]
0x140047ac6  sub     edi, [rsp+68h+var_48]
0x140047aca  movzx   ecx, [rsp+68h+arg_10]
0x140047ad2  mov     [rax], r13
0x140047ad5  mov     rax, [rsp+68h+arg_20]
0x140047add  mov     [r9], edi
0x140047ae0  mov     [rax], cl
0x140047ae2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047ae9  mov     r13, [rsp+68h+var_30]
0x140047aee  mov     rsi, [rsp+68h+var_28]
0x140047af3  cmp     rcx, r12
0x140047af6  jz      short loc_140047B02
0x140047af8  test    [rcx+2Ch], r11d
0x140047afc  jnz     loc_140047D62
0x140047b02  test    ebp, ebp
0x140047b04  jnz     loc_140047D84
0x140047b0a  mov     r15, [rsp+68h+var_38]
0x140047b0f  mov     eax, ebp
0x140047b11  mov     rbp, [rsp+68h+arg_0]
0x140047b16  add     rsp, 48h
0x140047b1a  pop     r14
0x140047b1c  pop     r12
0x140047b1e  pop     rdi
0x140047b1f  pop     rbx
0x140047b20  retn
0x140047b22  mov     ebp, 0C0000008h
0x140047b27  lea     rdx, [r14+48h]
0x140047b2b  mov     [rsp+68h+var_40], rdx
0x140047b30  jmp     short loc_140047AB6
0x140047b32  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047b39  lea     r12, WPP_GLOBAL_Control
0x140047b40  cmp     rcx, r12
0x140047b43  jnz     short loc_140047B65
0x140047b45  mov     eax, 0C0000023h
0x140047b4a  add     rsp, 48h
0x140047b4e  pop     r14
0x140047b50  pop     r12
0x140047b52  pop     rdi
0x140047b53  pop     rbx
0x140047b54  retn
0x140047b56  xor     r9d, r9d
0x140047b59  jmp     loc_14004794C
0x140047b5e  mov     cl, 1
0x140047b60  jmp     loc_140047A91
0x140047b65  test    dword ptr [rcx+2Ch], 400h
0x140047b6c  jz      short loc_140047B45
0x140047b6e  mov     rcx, [rcx+18h]
0x140047b72  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x140047b79  mov     edx, 1Fh
0x140047b7e  mov     r9d, edi
0x140047b81  call    WPP_SF_d
0x140047b86  jmp     short loc_140047B45
0x140047b88  mov     edx, 2
0x140047b8d  jmp     loc_140047996
0x140047b92  or      cx, r11w
0x140047b96  jmp     loc_1400479C5
0x140047b9b  or      cx, 10h
0x140047b9f  jmp     loc_140047A29
0x140047ba4  lea     r10, [rbx+20h]
0x140047ba8  mov     [rsp+68h+var_40], r10
0x140047bad  jmp     loc_140047C81
0x140047bb2  cmp     dword ptr [r9+0Ch], 3
0x140047bb7  lea     r10, [rbx+20h]
0x140047bbb  mov     [rsp+68h+var_40], r10
0x140047bc0  jnz     loc_140047C81
0x140047bc6  test    dword ptr [rsi+1A4h], 10100h
0x140047bd0  jz      loc_140047C81
0x140047bd6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047bdd  cmp     rcx, r12
0x140047be0  jz      short loc_140047C01
0x140047be2  test    [rcx+2Ch], r11d
0x140047be6  jz      short loc_140047C01
0x140047be8  mov     rcx, [rcx+18h]
0x140047bec  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x140047bf3  mov     edx, 20h ; ' '
0x140047bf8  call    WPP_SF_
0x140047bfd  lea     r10, [rbx+20h]
0x140047c01  mov     byte ptr [r13+0], 73h ; 's'
0x140047c06  lea     r8, [rsp+68h+var_48]
0x140047c0b  xor     eax, eax
0x140047c0d  mov     [rsp+68h+arg_10], 73h ; 's'
0x140047c15  mov     [rbx+18h], ax
0x140047c19  lea     r13, [r10+1]
0x140047c1d  mov     rax, [rsi+198h]
0x140047c24  mov     rdx, r10
0x140047c27  mov     rcx, r14
0x140047c2a  mov     rax, [rax]
0x140047c2d  call    _guard_dispatch_icall
0x140047c32  mov     ebp, eax
0x140047c34  mov     r11d, 400h
0x140047c3a  test    eax, eax
0x140047c3c  js      loc_140047B27
0x140047c42  mov     edx, [rsp+68h+var_48]
0x140047c46  movzx   ecx, di
0x140047c49  sub     cx, dx
0x140047c4c  mov     r10, rdi
0x140047c4f  mov     [rbx+23h], cx
0x140047c53  sub     r10, rdx
0x140047c56  movzx   ecx, byte ptr [rsi+2A0h]
0x140047c5d  lea     rdx, [r14+48h]
0x140047c61  and     cl, 18h
0x140047c64  add     r10, rbx
0x140047c67  cmp     cl, 10h
0x140047c6a  mov     [rsp+68h+var_40], r10
0x140047c6f  movzx   ecx, [rsp+68h+arg_8]
0x140047c74  jnz     short loc_140047C81
0x140047c76  mov     rax, qword ptr cs:InitialSecuritySignature; "BSRSPYL "
0x140047c7d  mov     [rbx+0Eh], rax
0x140047c81  test    dword ptr [rdx], 200h
0x140047c87  jz      loc_140047B2B
0x140047c8d  test    cl, cl
0x140047c8f  jnz     loc_140047B2B
0x140047c95  mov     eax, [rsi+1A4h]
0x140047c9b  test    al, 10h
0x140047c9d  jz      short loc_140047CD1
0x140047c9f  mov     bl, 1
0x140047ca1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047ca8  cmp     rcx, r12
0x140047cab  jz      short loc_140047CCD
0x140047cad  test    [rcx+2Ch], r11d
0x140047cb1  jz      short loc_140047CCD
0x140047cb3  mov     rcx, [rcx+18h]
0x140047cb7  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x140047cbe  mov     edx, 21h ; '!'
0x140047cc3  call    WPP_SF_
0x140047cc8  mov     r10, [rsp+68h+var_40]
0x140047ccd  mov     al, 75h ; 'u'
0x140047ccf  jmp     short loc_140047D01
0x140047cd1  xor     bl, bl
0x140047cd3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047cda  cmp     rcx, r12
0x140047cdd  jz      short loc_140047CFF
0x140047cdf  test    [rcx+2Ch], r11d
0x140047ce3  jz      short loc_140047CFF
0x140047ce5  mov     rcx, [rcx+18h]
0x140047ce9  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x140047cf0  mov     edx, 22h ; '"'
0x140047cf5  call    WPP_SF_
0x140047cfa  mov     r10, [rsp+68h+var_40]
0x140047cff  mov     al, 70h ; 'p'
0x140047d01  mov     [rsp+68h+arg_10], al
0x140047d08  lea     r8, [rsp+68h+var_48]
0x140047d0d  mov     [r13+0], al
0x140047d11  mov     rdx, r10
0x140047d14  mov     rax, [rsi+198h]
0x140047d1b  mov     rcx, r14
0x140047d1e  mov     rax, [rax+8]
0x140047d22  call    _guard_dispatch_icall
0x140047d27  mov     ebp, eax
0x140047d29  mov     r11d, 400h
0x140047d2f  test    eax, eax
0x140047d31  js      loc_140047B27
0x140047d37  lea     rdx, [r14+48h]
0x140047d3b  test    bl, bl
0x140047d3d  jz      short loc_140047D5A
0x140047d3f  mov     r8, [rsp+68h+var_40]
0x140047d44  movzx   eax, di
0x140047d47  sub     ax, word ptr [rsp+68h+var_48]
0x140047d4c  lea     r13, [r8+1]
0x140047d50  mov     [r8+3], ax
0x140047d55  jmp     loc_140047B2B
0x140047d5a  xor     r13d, r13d
0x140047d5d  jmp     loc_140047B2B
0x140047d62  mov     r9d, [r9]
0x140047d65  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x140047d6c  mov     rcx, [rcx+18h]
0x140047d70  mov     edx, 23h ; '#'
0x140047d75  call    WPP_SF_d
0x140047d7a  mov     rdx, [rsp+68h+var_40]
0x140047d7f  jmp     loc_140047B02
0x140047d84  mov     eax, [rdx]
0x140047d86  bt      eax, 8
0x140047d8a  jnb     short loc_140047D93
0x140047d8c  mov     [r14+0F8h], ebp
0x140047d93  bt      eax, 9
0x140047d97  jnb     loc_140047B0A
0x140047d9d  mov     eax, 1
0x140047da2  xchg    eax, [r15+0Ch]
0x140047da6  jmp     loc_140047B0A
```
