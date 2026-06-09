# CEXTLOG::ConvertDataToString(ulong,void *,char *,ulong)

- ea: `0x180003d48`
- end: `0x180003fc5`
- name: `?ConvertDataToString@CEXTLOG@@IEAAKKPEAXPEADK@Z`
- size: `637`
- prototype: `__int64 __fastcall(CEXTLOG *this, int, int *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005020`

## callees

- `0x180002114`
- `0x180003d48`
- `0x18000ec56`
- `0x18000eca0`
- `0x18000ed30`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180003e91`
- `msvcrt!sprintf_s` at `0x180003e91`
- `msvcrt!_itoa_s` at `0x180003f2c`
- `msvcrt!_itoa_s` at `0x180003f2c`
- `msvcrt!_ultoa_s` at `0x180003eae`
- `msvcrt!_ultoa_s` at `0x180003f03`
- `msvcrt!_ultoa_s` at `0x180003eae`
- `msvcrt!_ultoa_s` at `0x180003f03`
- `msvcrt!_ltoa_s` at `0x180003eda`
- `msvcrt!_ltoa_s` at `0x180003eda`

## pseudocode

```c
__int64 __fastcall CEXTLOG::ConvertDataToString(CEXTLOG *this, int a2, int *a3, char *a4, unsigned int a5)
{
  char *v7; // rsi
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  __int64 v14; // rdi
  int v15; // r8d
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  unsigned int v20; // eax
  double v21; // xmm3_8
  char Buffer[64]; // [rsp+20h] [rbp+0h] BYREF

  if ( !a3 )
  {
    v7 = (char *)&szDash;
    LODWORD(v14) = 1;
    goto LABEL_41;
  }
  v7 = Buffer;
  if ( !a2 )
  {
    _itoa_s(*a3, Buffer, 0x40u, 10);
    v14 = -1;
    do
      ++v14;
    while ( Buffer[v14] );
    goto LABEL_41;
  }
  v8 = a2 - 1;
  if ( !v8 )
  {
    _ultoa_s(*a3, Buffer, 0x40u, 10);
    v14 = -1;
    do
      ++v14;
    while ( Buffer[v14] );
    goto LABEL_41;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    _ltoa_s(*a3, Buffer, 0x40u, 10);
    v14 = -1;
    do
      ++v14;
    while ( Buffer[v14] );
    goto LABEL_41;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    _ultoa_s(*a3, Buffer, 0x40u, 10);
    v14 = -1;
    do
      ++v14;
    while ( Buffer[v14] );
    goto LABEL_41;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v21 = *(float *)a3;
    goto LABEL_27;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v21 = *(double *)a3;
LABEL_27:
    LODWORD(v14) = sprintf_s(Buffer, 0x40u, "%f", v21);
    goto LABEL_41;
  }
  v13 = v12 - 1;
  if ( v13 )
  {
    if ( v13 == 1 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)a3 + v14) );
      if ( (unsigned int)v14 > 0x1000 )
      {
        v7 = szDotDot;
        LODWORD(v14) = 3;
      }
      else
      {
        v15 = 2 * v14 + 2;
        v16 = v15 + 15LL;
        if ( v16 <= v15 )
          v16 = 0xFFFFFFFFFFFFFF0LL;
        v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
        v18 = alloca(v17);
        v19 = alloca(v17);
        v7 = AtlW2AHelper(Buffer, (const unsigned __int16 *)a3, v15);
      }
    }
    else
    {
      LODWORD(v14) = 0;
    }
  }
  else
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)a3 + v14) );
    v7 = szDotDot;
    v20 = v14;
    if ( (unsigned int)v14 > 0x1000 )
      LODWORD(v14) = 3;
    if ( v20 <= 0x1000 )
      v7 = (char *)a3;
  }
LABEL_41:
  if ( (unsigned int)v14 >= a5 )
  {
    if ( a5 <= 3 )
    {
      LODWORD(v14) = -1;
    }
    else
    {
      LODWORD(v14) = 3;
      *(_WORD *)a4 = *(_WORD *)szDotDot;
      a4[2] = byte_18001745E;
      a4[3] = 32;
    }
  }
  else
  {
    memcpy_0(a4, v7, (unsigned int)v14);
    a4[(unsigned int)v14] = 32;
  }
  return (unsigned int)(v14 + 1);
}

```

## disassembly

```asm
0x180003d48  push    rbp
0x180003d4a  push    rdi
0x180003d4b  push    r12
0x180003d4d  push    r14
0x180003d4f  push    r15
0x180003d51  sub     rsp, 70h
0x180003d55  lea     rbp, [rsp+20h]
0x180003d5a  mov     [rbp+70h+arg_0], rbx
0x180003d61  mov     [rbp+70h+arg_8], rsi
0x180003d68  mov     rax, cs:__security_cookie
0x180003d6f  xor     rax, rbp
0x180003d72  mov     [rbp+70h+var_30], rax
0x180003d76  xor     r15d, r15d
0x180003d79  mov     r14, r9
0x180003d7c  mov     rbx, r8
0x180003d7f  mov     r12d, 3
0x180003d85  test    r8, r8
0x180003d88  jz      loc_180003F45
0x180003d8e  lea     rsi, [rbp+70h+Buffer]
0x180003d92  test    edx, edx
0x180003d94  jz      loc_180003F1C
0x180003d9a  sub     edx, 1
0x180003d9d  jz      loc_180003EF3
0x180003da3  sub     edx, 1
0x180003da6  jz      loc_180003ECA
0x180003dac  sub     edx, 1
0x180003daf  jz      loc_180003E9E
0x180003db5  sub     edx, 1
0x180003db8  jz      loc_180003E74
0x180003dbe  sub     edx, 1
0x180003dc1  jz      loc_180003E6D
0x180003dc7  sub     edx, 1
0x180003dca  jz      short loc_180003E41
0x180003dcc  cmp     edx, 1
0x180003dcf  jz      short loc_180003DD9
0x180003dd1  mov     edi, r15d
0x180003dd4  jmp     loc_180003F51
0x180003dd9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003ddd  inc     rdi
0x180003de0  cmp     [r8+rdi*2], r15w
0x180003de5  jnz     short loc_180003DDD
0x180003de7  mov     ecx, 1000h
0x180003dec  cmp     edi, ecx
0x180003dee  ja      short loc_180003E32
0x180003df0  lea     r8d, ds:2[rdi*2]
0x180003df8  movsxd  rax, r8d
0x180003dfb  lea     rcx, [rax+0Fh]
0x180003dff  cmp     rcx, rax
0x180003e02  ja      short loc_180003E0E
0x180003e04  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180003e0e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180003e12  mov     rax, rcx
0x180003e15  call    _alloca_probe
0x180003e1a  sub     rsp, rcx
0x180003e1d  mov     rdx, rbx; unsigned __int16 *
0x180003e20  lea     rcx, [rsp+90h+Buffer]; char *
0x180003e25  call    ?AtlW2AHelper@@YAPEADPEADPEBGH@Z; AtlW2AHelper(char *,ushort const *,int)
0x180003e2a  mov     rsi, rax
0x180003e2d  jmp     loc_180003F51
0x180003e32  lea     rsi, ?szDotDot@@3PADA; char near * szDotDot
0x180003e39  mov     edi, r12d
0x180003e3c  jmp     loc_180003F51
0x180003e41  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003e45  inc     rdi
0x180003e48  cmp     [r8+rdi], r15b
0x180003e4c  jnz     short loc_180003E45
0x180003e4e  mov     ecx, 1000h
0x180003e53  lea     rsi, ?szDotDot@@3PADA; char near * szDotDot
0x180003e5a  cmp     edi, ecx
0x180003e5c  mov     eax, edi
0x180003e5e  cmova   edi, r12d
0x180003e62  cmp     eax, ecx
0x180003e64  cmovbe  rsi, rbx
0x180003e68  jmp     loc_180003F51
0x180003e6d  movsd   xmm3, qword ptr [r8]
0x180003e72  jmp     short loc_180003E7C
0x180003e74  movss   xmm3, dword ptr [r8]
0x180003e79  cvtps2pd xmm3, xmm3
0x180003e7c  movq    r9, xmm3
0x180003e81  lea     r8, asc_18001358C; "%f"
0x180003e88  mov     edx, 40h ; '@'; BufferCount
0x180003e8d  lea     rcx, [rbp+70h+Buffer]; Buffer
0x180003e91  call    cs:__imp_sprintf_s
0x180003e97  mov     edi, eax
0x180003e99  jmp     loc_180003F51
0x180003e9e  mov     ecx, [rbx]; Value
0x180003ea0  lea     rdx, [rbp+70h+Buffer]; Buffer
0x180003ea4  mov     r9d, 0Ah; Radix
0x180003eaa  lea     r8d, [r9+36h]; BufferCount
0x180003eae  call    cs:__imp__ultoa_s
0x180003eb4  lea     rax, [rbp+70h+Buffer]
0x180003eb8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003ebc  inc     rdi
0x180003ebf  cmp     [rax+rdi], r15b
0x180003ec3  jnz     short loc_180003EBC
0x180003ec5  jmp     loc_180003F51
0x180003eca  mov     ecx, [rbx]; Value
0x180003ecc  lea     rdx, [rbp+70h+Buffer]; Buffer
0x180003ed0  mov     r9d, 0Ah; Radix
0x180003ed6  lea     r8d, [r9+36h]; BufferCount
0x180003eda  call    cs:__imp__ltoa_s
0x180003ee0  lea     rax, [rbp+70h+Buffer]
0x180003ee4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003ee8  inc     rdi
0x180003eeb  cmp     [rax+rdi], r15b
0x180003eef  jnz     short loc_180003EE8
0x180003ef1  jmp     short loc_180003F51
0x180003ef3  mov     ecx, [rbx]; Value
0x180003ef5  lea     rdx, [rbp+70h+Buffer]; Buffer
0x180003ef9  mov     r9d, 0Ah; Radix
0x180003eff  lea     r8d, [r9+36h]; BufferCount
0x180003f03  call    cs:__imp__ultoa_s
0x180003f09  lea     rax, [rbp+70h+Buffer]
0x180003f0d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003f11  inc     rdi
0x180003f14  cmp     [rax+rdi], r15b
0x180003f18  jnz     short loc_180003F11
0x180003f1a  jmp     short loc_180003F51
0x180003f1c  mov     ecx, [rbx]; Value
0x180003f1e  lea     rdx, [rbp+70h+Buffer]; Buffer
0x180003f22  mov     r9d, 0Ah; Radix
0x180003f28  lea     r8d, [r9+36h]; BufferCount
0x180003f2c  call    cs:__imp__itoa_s
0x180003f32  lea     rax, [rbp+70h+Buffer]
0x180003f36  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003f3a  inc     rdi
0x180003f3d  cmp     [rax+rdi], r15b
0x180003f41  jnz     short loc_180003F3A
0x180003f43  jmp     short loc_180003F51
0x180003f45  lea     rsi, ?szDash@@3PADA; char near * szDash
0x180003f4c  mov     edi, 1
0x180003f51  cmp     edi, [rbp+70h+arg_20]
0x180003f57  jnb     short loc_180003F70
0x180003f59  mov     r8d, edi; Size
0x180003f5c  mov     rdx, rsi; Src
0x180003f5f  mov     rcx, r14; void *
0x180003f62  mov     ebx, edi
0x180003f64  call    memcpy_0
0x180003f69  mov     byte ptr [rbx+r14], 20h ; ' '
0x180003f6e  jmp     short loc_180003F9B
0x180003f70  cmp     [rbp+70h+arg_20], r12d
0x180003f77  jbe     short loc_180003F98
0x180003f79  movzx   eax, cs:?szDotDot@@3PADA; char near * szDotDot
0x180003f80  mov     edi, r12d
0x180003f83  mov     [r14], ax
0x180003f87  mov     al, cs:byte_18001745E
0x180003f8d  mov     [r14+2], al
0x180003f91  mov     byte ptr [r14+3], 20h ; ' '
0x180003f96  jmp     short loc_180003F9B
0x180003f98  or      edi, 0FFFFFFFFh
0x180003f9b  lea     eax, [rdi+1]
0x180003f9e  mov     rcx, [rbp+70h+var_30]
0x180003fa2  xor     rcx, rbp; StackCookie
0x180003fa5  call    __security_check_cookie
0x180003faa  mov     rbx, [rbp+70h+arg_0]
0x180003fb1  mov     rsi, [rbp+70h+arg_8]
0x180003fb8  lea     rsp, [rbp+50h]
0x180003fbc  pop     r15
0x180003fbe  pop     r14
0x180003fc0  pop     r12
0x180003fc2  pop     rdi
0x180003fc3  pop     rbp
0x180003fc4  retn
```
