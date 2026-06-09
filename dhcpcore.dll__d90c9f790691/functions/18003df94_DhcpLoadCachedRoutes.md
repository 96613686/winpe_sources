# DhcpLoadCachedRoutes

- ea: `0x18003df94`
- end: `0x18003e21f`
- name: `DhcpLoadCachedRoutes`
- size: `651`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180025678`
- `0x1800407c0`

## callees

- `0x1800057f0`
- `0x180006440`
- `0x18000d1b8`
- `0x18000d530`
- `0x18001250c`
- `0x18003df94`
- `0x180047e3c`
- `0x18004d1a0`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003e049`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003e049`

## pseudocode

```c
__int64 __fastcall DhcpLoadCachedRoutes(__int64 a1, __int64 a2)
{
  void *v2; // rsi
  void *v3; // r12
  void *v4; // r15
  SIZE_T v7; // rbx
  void *v8; // rax
  unsigned int v9; // ebx
  ULONGLONG v10; // r14
  unsigned int *Option; // rax
  unsigned int v12; // ebx
  unsigned int v13; // ecx
  _QWORD *v14; // rax
  _QWORD *v15; // r13
  unsigned int v16; // r14d
  void *v17; // rax
  int v19; // [rsp+30h] [rbp-20h] BYREF
  void *v20; // [rsp+38h] [rbp-18h] BYREF
  void *v21; // [rsp+40h] [rbp-10h] BYREF
  void *v22; // [rsp+48h] [rbp-8h] BYREF
  void *Src; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v25; // [rsp+A8h] [rbp+58h]

  v2 = 0;
  v24 = 0;
  v3 = 0;
  Src = 0;
  v4 = 0;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  v19 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 41, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, *(_QWORD *)(a1 + 24));
  if ( !*(_DWORD *)(a2 + 44) && (unsigned int)RetreiveGatewaysList(a1, &v24, &Src) )
  {
    v7 = 4LL * v24;
    v8 = DhcpAlloc(v7);
    v20 = v8;
    v2 = v8;
    if ( !v8 )
    {
LABEL_6:
      v9 = 8;
      goto LABEL_30;
    }
    memcpy_0(v8, Src, v7);
  }
  v25 = 0;
  v10 = GetTickCount64() / 0x3E8;
  if ( !*(_DWORD *)(a2 + 56) )
  {
    Option = (unsigned int *)DhcpFindOption(
                               (_QWORD **)(a1 + 696),
                               0x21u,
                               0,
                               *(const void **)(a1 + 736),
                               *(_DWORD *)(a1 + 744),
                               0);
    Src = Option;
    if ( Option )
    {
      if ( *((_QWORD *)Option + 5) >= v10 )
      {
        v12 = Option[14];
        if ( v12 )
        {
          if ( (v12 & 7) == 0 )
          {
            v21 = DhcpAlloc(v12);
            v3 = v21;
            if ( !v21 )
              goto LABEL_6;
            v25 = v12 >> 3;
            memcpy_0(v21, *((const void **)Src + 6), *((unsigned int *)Src + 14));
          }
        }
      }
    }
  }
  v13 = 0;
  v9 = 0;
  if ( !*(_DWORD *)(a2 + 76) )
  {
    v14 = DhcpFindOption((_QWORD **)(a1 + 696), 0x79u, 0, *(const void **)(a1 + 736), *(_DWORD *)(a1 + 744), 0);
    v15 = v14;
    if ( v14 && v14[5] >= v10 && (v16 = *((_DWORD *)v14 + 14)) != 0 )
    {
      v9 = CheckCLRoutes(v16, v14[6], &v19);
      if ( v9 )
      {
        v13 = 0;
      }
      else
      {
        v17 = DhcpAlloc(v16);
        v22 = v17;
        v4 = v17;
        if ( !v17 )
          goto LABEL_6;
        memcpy_0(v17, (const void *)v15[6], *((unsigned int *)v15 + 14));
        v13 = v16;
      }
    }
    else
    {
      v13 = 0;
    }
  }
  if ( v2 )
  {
    *(_DWORD *)(a2 + 44) = v24;
    *(_QWORD *)(a2 + 48) = v2;
    v20 = 0;
  }
  if ( v3 )
  {
    *(_DWORD *)(a2 + 56) = v25;
    *(_QWORD *)(a2 + 64) = v3;
    v21 = 0;
  }
  if ( v4 )
  {
    *(_DWORD *)(a2 + 72) = v19;
    *(_DWORD *)(a2 + 76) = v13;
    *(_QWORD *)(a2 + 80) = v4;
    v22 = 0;
  }
LABEL_30:
  DhcpPunycodeFree(&v20);
  DhcpPunycodeFree(&v21);
  DhcpPunycodeFree(&v22);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 42, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18003df94  mov     [rsp-38h+arg_0], rbx
0x18003df99  push    rbp
0x18003df9a  push    rsi
0x18003df9b  push    rdi
0x18003df9c  push    r12
0x18003df9e  push    r13
0x18003dfa0  push    r14
0x18003dfa2  push    r15
0x18003dfa4  mov     rbp, rsp
0x18003dfa7  sub     rsp, 50h
0x18003dfab  xor     esi, esi
0x18003dfad  mov     [rbp+arg_10], 0
0x18003dfb4  xor     r12d, r12d
0x18003dfb7  mov     [rbp+Src], 0
0x18003dfbf  xor     r15d, r15d
0x18003dfc2  mov     [rbp+var_18], rsi
0x18003dfc6  mov     [rbp+var_8], r15
0x18003dfca  mov     rdi, rdx
0x18003dfcd  mov     r13, rcx
0x18003dfd0  mov     [rbp+var_10], r12
0x18003dfd4  mov     [rbp+var_20], esi
0x18003dfd7  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003dfde  jz      short loc_18003DFF8
0x18003dfe0  mov     r9, [r13+18h]
0x18003dfe4  lea     edx, [rsi+29h]
0x18003dfe7  mov     ecx, 404h
0x18003dfec  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18003dff3  call    WPP_SF_q
0x18003dff8  cmp     [rdi+2Ch], esi
0x18003dffb  jnz     short loc_18003E045
0x18003dffd  lea     r8, [rbp+Src]
0x18003e001  mov     rcx, r13
0x18003e004  lea     rdx, [rbp+arg_10]
0x18003e008  call    RetreiveGatewaysList
0x18003e00d  test    eax, eax
0x18003e00f  jz      short loc_18003E045
0x18003e011  mov     ebx, [rbp+arg_10]
0x18003e014  shl     rbx, 2
0x18003e018  mov     rcx, rbx
0x18003e01b  call    DhcpAlloc
0x18003e020  mov     [rbp+var_18], rax
0x18003e024  mov     rsi, rax
0x18003e027  test    rax, rax
0x18003e02a  jnz     short loc_18003E036
0x18003e02c  mov     ebx, 8
0x18003e031  jmp     loc_18003E1C8
0x18003e036  mov     rdx, [rbp+Src]; Src
0x18003e03a  mov     r8, rbx; Size
0x18003e03d  mov     rcx, rax; void *
0x18003e040  call    memcpy_0
0x18003e045  mov     [rbp+arg_18], r12d
0x18003e049  call    cs:__imp_GetTickCount64
0x18003e04f  mov     r14, rax
0x18003e052  mov     rax, 624DD2F1A9FBE77h
0x18003e05c  mul     r14
0x18003e05f  sub     r14, rdx
0x18003e062  shr     r14, 1
0x18003e065  add     r14, rdx
0x18003e068  shr     r14, 9
0x18003e06c  cmp     [rdi+38h], r12d
0x18003e070  jnz     short loc_18003E0EA
0x18003e072  mov     eax, [r13+2E8h]
0x18003e079  lea     rcx, [r13+2B8h]
0x18003e080  mov     r9, [r13+2E0h]
0x18003e087  xor     r8d, r8d
0x18003e08a  mov     [rsp+50h+var_28], r12d
0x18003e08f  mov     [rsp+50h+var_30], eax
0x18003e093  lea     edx, [r8+21h]
0x18003e097  call    DhcpFindOption
0x18003e09c  mov     [rbp+Src], rax
0x18003e0a0  test    rax, rax
0x18003e0a3  jz      short loc_18003E0EA
0x18003e0a5  cmp     [rax+28h], r14
0x18003e0a9  jb      short loc_18003E0EA
0x18003e0ab  mov     ebx, [rax+38h]
0x18003e0ae  test    ebx, ebx
0x18003e0b0  jz      short loc_18003E0EA
0x18003e0b2  test    bl, 7
0x18003e0b5  jnz     short loc_18003E0EA
0x18003e0b7  mov     ecx, ebx
0x18003e0b9  call    DhcpAlloc
0x18003e0be  mov     [rbp+var_10], rax
0x18003e0c2  mov     r12, rax
0x18003e0c5  test    rax, rax
0x18003e0c8  jz      loc_18003E02C
0x18003e0ce  mov     rdx, [rbp+Src]
0x18003e0d2  mov     eax, ebx
0x18003e0d4  shr     eax, 3
0x18003e0d7  mov     rcx, r12; void *
0x18003e0da  mov     [rbp+arg_18], eax
0x18003e0dd  mov     r8d, [rdx+38h]; Size
0x18003e0e1  mov     rdx, [rdx+30h]; Src
0x18003e0e5  call    memcpy_0
0x18003e0ea  xor     ecx, ecx
0x18003e0ec  xor     ebx, ebx
0x18003e0ee  cmp     [rdi+4Ch], ecx
0x18003e0f1  jnz     loc_18003E180
0x18003e0f7  mov     eax, [r13+2E8h]
0x18003e0fe  lea     rcx, [r13+2B8h]
0x18003e105  mov     r9, [r13+2E0h]
0x18003e10c  lea     edx, [rbx+79h]
0x18003e10f  mov     [rsp+50h+var_28], ebx
0x18003e113  xor     r8d, r8d
0x18003e116  mov     [rsp+50h+var_30], eax
0x18003e11a  call    DhcpFindOption
0x18003e11f  mov     r13, rax
0x18003e122  test    rax, rax
0x18003e125  jz      short loc_18003E179
0x18003e127  cmp     [rax+28h], r14
0x18003e12b  jb      short loc_18003E179
0x18003e12d  mov     r14d, [rax+38h]
0x18003e131  test    r14d, r14d
0x18003e134  jz      short loc_18003E179
0x18003e136  mov     rdx, [rax+30h]
0x18003e13a  lea     r8, [rbp+var_20]
0x18003e13e  mov     ecx, r14d
0x18003e141  call    CheckCLRoutes
0x18003e146  mov     ebx, eax
0x18003e148  test    eax, eax
0x18003e14a  jnz     short loc_18003E17D
0x18003e14c  mov     ecx, r14d
0x18003e14f  call    DhcpAlloc
0x18003e154  mov     [rbp+var_8], rax
0x18003e158  mov     r15, rax
0x18003e15b  test    rax, rax
0x18003e15e  jz      loc_18003E02C
0x18003e164  mov     r8d, [r13+38h]; Size
0x18003e168  mov     rcx, rax; void *
0x18003e16b  mov     rdx, [r13+30h]; Src
0x18003e16f  call    memcpy_0
0x18003e174  mov     ecx, r14d
0x18003e177  jmp     short loc_18003E180
0x18003e179  mov     ecx, ebx
0x18003e17b  jmp     short loc_18003E180
0x18003e17d  mov     ecx, r15d
0x18003e180  test    rsi, rsi
0x18003e183  jz      short loc_18003E197
0x18003e185  mov     eax, [rbp+arg_10]
0x18003e188  mov     [rdi+2Ch], eax
0x18003e18b  mov     [rdi+30h], rsi
0x18003e18f  mov     [rbp+var_18], 0
0x18003e197  test    r12, r12
0x18003e19a  jz      short loc_18003E1AE
0x18003e19c  mov     eax, [rbp+arg_18]
0x18003e19f  mov     [rdi+38h], eax
0x18003e1a2  mov     [rdi+40h], r12
0x18003e1a6  mov     [rbp+var_10], 0
0x18003e1ae  test    r15, r15
0x18003e1b1  jz      short loc_18003E1C8
0x18003e1b3  mov     eax, [rbp+var_20]
0x18003e1b6  mov     [rdi+48h], eax
0x18003e1b9  mov     [rdi+4Ch], ecx
0x18003e1bc  mov     [rdi+50h], r15
0x18003e1c0  mov     [rbp+var_8], 0
0x18003e1c8  lea     rcx, [rbp+var_18]
0x18003e1cc  call    DhcpPunycodeFree
0x18003e1d1  lea     rcx, [rbp+var_10]
0x18003e1d5  call    DhcpPunycodeFree
0x18003e1da  lea     rcx, [rbp+var_8]
0x18003e1de  call    DhcpPunycodeFree
0x18003e1e3  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003e1ea  jz      short loc_18003E205
0x18003e1ec  mov     edx, 2Ah ; '*'
0x18003e1f1  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18003e1f8  mov     ecx, 404h
0x18003e1fd  mov     r9d, ebx
0x18003e200  call    WPP_SF_D
0x18003e205  mov     eax, ebx
0x18003e207  mov     rbx, [rsp+50h+arg_0]
0x18003e20f  add     rsp, 50h
0x18003e213  pop     r15
0x18003e215  pop     r14
0x18003e217  pop     r13
0x18003e219  pop     r12
0x18003e21b  pop     rdi
0x18003e21c  pop     rsi
0x18003e21d  pop     rbp
0x18003e21e  retn
```
