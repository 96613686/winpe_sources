# CURL::ParseHost(void)

- ea: `0x180037ef8`
- end: `0x180038223`
- name: `?ParseHost@CURL@@IEAAXXZ`
- size: `811`
- prototype: `void __fastcall(CURL *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003796c`

## callees

- `0x180003640`
- `0x180006270`
- `0x180011cdc`
- `0x180036a08`
- `0x180036a24`
- `0x1800378ec`
- `0x180037c08`
- `0x180037ef8`
- `0x180038ab0`
- `0x180038b28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800381c6`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800381c6`

## string_xrefs

- `0x180038188`: `onecoreuap\base\appmodel\search\common\pkmutill\url.cxx`

## pseudocode

```c
void __fastcall CURL::ParseHost(CURL *this)
{
  __int16 v1; // ax
  __int64 v3; // rdx
  unsigned int v4; // r10d
  unsigned int v5; // r9d
  __int64 v6; // r11
  __int16 v7; // dx
  int v8; // r8d
  int v9; // r9d
  __int16 v10; // dx
  __int64 v11; // rdx
  __int64 v12; // rsi
  int v13; // edx
  __int16 v14; // dx
  int v15; // eax
  int v16; // r10d
  int v17; // r11d
  __int16 v18; // bx
  unsigned int v19; // edx
  int v20; // eax
  int v21; // r10d
  __int64 v22; // r8
  int AnySlash; // eax
  int v24; // r10d
  unsigned int v25; // r11d
  int v26; // esi
  int v27; // eax
  __int16 v28; // r14
  __int64 v29; // r8
  unsigned int *v30; // r8
  __int64 v31; // r9
  unsigned __int64 v32; // rdx
  __int64 v33; // rax
  void *v34; // rsp
  __int64 v35; // rbx
  int v36[4]; // [rsp+20h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+68h]

  v1 = *((_WORD *)this + 231);
  if ( (v1 & 4) == 0 )
    return;
  *((_WORD *)this + 231) = v1 & 0xFFFB;
  CURL::ParseAccessType(this);
  v3 = *((unsigned __int16 *)this + 221);
  v4 = *((unsigned __int16 *)this + 227);
  if ( *((_WORD *)this + 220) )
  {
    if ( v4 >= (int)v3 + 2
      && (unsigned int)IsSlash(*(_WORD *)(*((_QWORD *)this + 4) + 2 * v3))
      && (unsigned int)IsSlash(*(_WORD *)(v22 + 2LL * (unsigned int)(v3 + 1))) )
    {
      *((_WORD *)this + 221) = v3 + 2;
      AnySlash = CLMString::FindAnySlash((CURL *)((char *)this + 24), (unsigned __int16)(v3 + 2));
      v26 = AnySlash;
      if ( AnySlash == -1 || AnySlash > v24 )
        v26 = v24;
      v27 = CLMString::Find((CURL *)((char *)this + 24), 0x3Au, v25);
      v28 = v27;
      if ( v27 == -1 || (v29 = (unsigned int)(v27 + 1), (int)v29 >= v26) )
      {
        v28 = v26;
      }
      else
      {
        v30 = (unsigned int *)CLMString::Mid((char *)this + 24, v36, v29, (unsigned int)(v26 - v29));
        v31 = v30[1];
        v32 = 2LL * (unsigned int)(v31 + 1);
        v33 = v32 + 15;
        if ( v32 + 15 < v32 )
          v33 = 0xFFFFFFFFFFFFFF0LL;
        v34 = alloca(v33 & 0xFFFFFFFFFFFFFFF0uLL);
        if ( !v36 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x20B,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\url.cxx",
            (const char *)0x8007000ELL,
            v36[0]);
        v35 = 2 * v31;
        memcpy_0(v36, (const void *)(*(_QWORD *)(*((_QWORD *)v30 + 1) + 8LL) + 2LL * *v30), 2 * v31);
        *(_WORD *)((char *)v36 + v35) = 0;
        *((_DWORD *)this + 117) = _o__wtol(v36);
        *((_WORD *)this + 231) &= ~2u;
      }
      *((_WORD *)this + 222) = v28 - *((_WORD *)this + 221);
    }
    else
    {
      LOWORD(v26) = v3;
    }
    *((_WORD *)this + 225) = v26;
    *((_WORD *)this + 233) = v26;
    return;
  }
  v5 = *((unsigned __int16 *)this + 221);
  if ( (unsigned int)v3 < v4 )
  {
    v6 = *((_QWORD *)this + 4);
    do
    {
      if ( !(unsigned int)IsSlash(*(_WORD *)(v6 + 2LL * v5)) )
        break;
      ++v8;
      v5 = v9 + 1;
    }
    while ( v5 < v4 );
    if ( v8 == 4 )
    {
      v10 = v7 + 2;
LABEL_13:
      *((_WORD *)this + 221) = v10;
      goto LABEL_14;
    }
    if ( ((v8 - 3) & 0xFFFFFFFD) == 0 )
    {
      v10 = v7 + 3;
      goto LABEL_13;
    }
    if ( v8 == 6 )
    {
      v10 = v7 + 4;
      goto LABEL_13;
    }
  }
LABEL_14:
  v11 = *((unsigned __int16 *)this + 221);
  *((_WORD *)this + 225) = v11;
  if ( v4 < (int)v11 + 2 )
    goto LABEL_22;
  v12 = *((_QWORD *)this + 4);
  if ( !(unsigned int)IsSlash(*(_WORD *)(v12 + 2 * v11))
    || !(unsigned int)IsSlash(*(_WORD *)(v12 + 2LL * (unsigned int)(v13 + 1))) )
  {
    goto LABEL_22;
  }
  *((_WORD *)this + 221) = v14 + 2;
  v15 = CLMString::FindAnySlash((CURL *)((char *)this + 24), (unsigned __int16)(v14 + 2));
  v18 = v15;
  if ( v15 == -1 || v15 > v16 )
  {
    *((_WORD *)this + 222) = v16 - v17;
  }
  else
  {
    *((_WORD *)this + 222) = v15 - v17;
    if ( (_WORD)v15 - (_WORD)v17 == 2 && *(_WORD *)(v12 + 2LL * (unsigned int)(v17 + 1)) == 58 )
    {
      *((_WORD *)this + 225) = v17;
LABEL_22:
      *((_WORD *)this + 224) = 0;
      *((_WORD *)this + 222) = 0;
      return;
    }
    v19 = (unsigned __int16)(v15 + 1);
    *((_WORD *)this + 223) = v19;
    v20 = CLMString::FindAnySlash((CURL *)((char *)this + 24), v19);
    if ( v20 == -1 || v20 > v21 )
      LOWORD(v20) = v21;
    *((_WORD *)this + 224) = v20 - v18 - 1;
  }
}

```

## disassembly

```asm
0x180037ef8  push    rbp
0x180037efa  push    rbx
0x180037efb  push    rsi
0x180037efc  push    rdi
0x180037efd  push    r12
0x180037eff  push    r13
0x180037f01  push    r14
0x180037f03  push    r15
0x180037f05  sub     rsp, 48h
0x180037f09  lea     rbp, [rsp+20h]
0x180037f0e  mov     rax, cs:__security_cookie
0x180037f15  xor     rax, rbp
0x180037f18  mov     [rbp+60h+var_50], rax
0x180037f1c  movzx   eax, word ptr [rcx+1CEh]
0x180037f23  mov     ebx, 4
0x180037f28  mov     rdi, rcx
0x180037f2b  test    bl, al
0x180037f2d  jz      loc_180038206
0x180037f33  mov     ecx, 0FFFBh
0x180037f38  and     ax, cx
0x180037f3b  mov     rcx, rdi; this
0x180037f3e  mov     [rdi+1CEh], ax
0x180037f45  call    ?ParseAccessType@CURL@@IEAAXXZ; CURL::ParseAccessType(void)
0x180037f4a  movzx   edx, word ptr [rdi+1BAh]
0x180037f51  xor     r12d, r12d
0x180037f54  movzx   r10d, word ptr [rdi+1C6h]
0x180037f5c  cmp     [rdi+1B8h], r12w
0x180037f64  jnz     loc_1800380AD
0x180037f6a  lea     r13d, [rbx-3]
0x180037f6e  mov     r9d, edx
0x180037f71  cmp     edx, r10d
0x180037f74  jnb     short loc_180037FC5
0x180037f76  mov     r11, [rdi+20h]
0x180037f7a  mov     r8d, r12d
0x180037f7d  mov     ecx, r9d
0x180037f80  movzx   ecx, word ptr [r11+rcx*2]; wchar_t
0x180037f85  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x180037f8a  test    eax, eax
0x180037f8c  jz      short loc_180037F99
0x180037f8e  add     r8d, r13d
0x180037f91  add     r9d, r13d
0x180037f94  cmp     r9d, r10d
0x180037f97  jb      short loc_180037F7D
0x180037f99  cmp     r8d, ebx
0x180037f9c  jnz     short loc_180037FA4
0x180037f9e  add     dx, 2
0x180037fa2  jmp     short loc_180037FBE
0x180037fa4  lea     eax, [r8-3]
0x180037fa8  test    eax, 0FFFFFFFDh
0x180037fad  jz      short loc_180037FBA
0x180037faf  cmp     r8d, 6
0x180037fb3  jnz     short loc_180037FC5
0x180037fb5  add     dx, bx
0x180037fb8  jmp     short loc_180037FBE
0x180037fba  add     dx, 3
0x180037fbe  mov     [rdi+1BAh], dx
0x180037fc5  movzx   edx, word ptr [rdi+1BAh]
0x180037fcc  mov     [rdi+1C2h], dx
0x180037fd3  lea     eax, [rdx+2]
0x180037fd6  cmp     r10d, eax
0x180037fd9  jb      short loc_18003804F
0x180037fdb  mov     rsi, [rdi+20h]
0x180037fdf  movzx   ecx, word ptr [rsi+rdx*2]; wchar_t
0x180037fe3  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x180037fe8  test    eax, eax
0x180037fea  jz      short loc_18003804F
0x180037fec  lea     eax, [rdx+1]
0x180037fef  movzx   ecx, word ptr [rsi+rax*2]; wchar_t
0x180037ff3  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x180037ff8  test    eax, eax
0x180037ffa  jz      short loc_18003804F
0x180037ffc  add     dx, 2
0x180038000  lea     rcx, [rdi+18h]; this
0x180038004  movzx   r11d, dx
0x180038008  mov     edx, r11d; unsigned int
0x18003800b  mov     [rdi+1BAh], r11w
0x180038013  call    ?FindAnySlash@CLMString@@QEBAHI@Z; CLMString::FindAnySlash(uint)
0x180038018  mov     ebx, eax
0x18003801a  cmp     eax, 0FFFFFFFFh
0x18003801d  jz      short loc_18003809C
0x18003801f  cmp     eax, r10d
0x180038022  jg      short loc_18003809C
0x180038024  movzx   ecx, bx
0x180038027  sub     cx, r11w
0x18003802b  mov     [rdi+1BCh], cx
0x180038032  cmp     cx, 2
0x180038036  jnz     short loc_180038064
0x180038038  lea     eax, [r11+1]
0x18003803c  mov     edx, 3Ah ; ':'
0x180038041  cmp     [rsi+rax*2], dx
0x180038045  jnz     short loc_180038064
0x180038047  mov     [rdi+1C2h], r11w
0x18003804f  mov     [rdi+1C0h], r12w
0x180038057  mov     [rdi+1BCh], r12w
0x18003805f  jmp     loc_180038206
0x180038064  lea     eax, [rbx+r13]
0x180038068  movzx   edx, ax; unsigned int
0x18003806b  lea     rcx, [rdi+18h]; this
0x18003806f  mov     [rdi+1BEh], dx
0x180038076  call    ?FindAnySlash@CLMString@@QEBAHI@Z; CLMString::FindAnySlash(uint)
0x18003807b  cmp     eax, 0FFFFFFFFh
0x18003807e  jz      short loc_180038085
0x180038080  cmp     eax, r10d
0x180038083  jle     short loc_180038089
0x180038085  movzx   eax, r10w
0x180038089  sub     ax, bx
0x18003808c  sub     ax, r13w
0x180038090  mov     [rdi+1C0h], ax
0x180038097  jmp     loc_180038206
0x18003809c  sub     r10w, r11w
0x1800380a0  mov     [rdi+1BCh], r10w
0x1800380a8  jmp     loc_180038206
0x1800380ad  lea     eax, [rdx+2]
0x1800380b0  cmp     r10d, eax
0x1800380b3  jb      loc_1800381F5
0x1800380b9  mov     r8, [rdi+20h]
0x1800380bd  movzx   ecx, word ptr [r8+rdx*2]; wchar_t
0x1800380c2  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x1800380c7  test    eax, eax
0x1800380c9  jz      loc_1800381F5
0x1800380cf  lea     eax, [rdx+1]
0x1800380d2  movzx   ecx, word ptr [r8+rax*2]; wchar_t
0x1800380d7  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x1800380dc  test    eax, eax
0x1800380de  jz      loc_1800381F5
0x1800380e4  add     dx, 2
0x1800380e8  lea     rbx, [rdi+18h]
0x1800380ec  movzx   r11d, dx
0x1800380f0  mov     rcx, rbx; this
0x1800380f3  mov     edx, r11d; unsigned int
0x1800380f6  mov     [rdi+1BAh], r11w
0x1800380fe  call    ?FindAnySlash@CLMString@@QEBAHI@Z; CLMString::FindAnySlash(uint)
0x180038103  mov     esi, eax
0x180038105  cmp     eax, 0FFFFFFFFh
0x180038108  jz      short loc_18003810F
0x18003810a  cmp     eax, r10d
0x18003810d  jle     short loc_180038112
0x18003810f  mov     esi, r10d
0x180038112  mov     edx, 3Ah ; ':'; wchar_t
0x180038117  mov     r8d, r11d; unsigned int
0x18003811a  mov     rcx, rbx; this
0x18003811d  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x180038122  mov     r14d, eax
0x180038125  cmp     eax, 0FFFFFFFFh
0x180038128  jz      loc_1800381E0
0x18003812e  lea     r8d, [rax+1]
0x180038132  cmp     r8d, esi
0x180038135  jge     loc_1800381E0
0x18003813b  mov     r9d, esi
0x18003813e  lea     rdx, [rbp+60h+var_60]
0x180038142  sub     r9d, r8d
0x180038145  mov     rcx, rbx
0x180038148  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x18003814d  mov     r8, rax
0x180038150  mov     r9d, [rax+4]
0x180038154  lea     edx, [r9+1]
0x180038158  add     rdx, rdx
0x18003815b  lea     rax, [rdx+0Fh]
0x18003815f  cmp     rax, rdx
0x180038162  ja      short loc_18003816E
0x180038164  mov     rax, 0FFFFFFFFFFFFFF0h
0x18003816e  and     rax, 0FFFFFFFFFFFFFFF0h
0x180038172  call    _alloca_probe
0x180038177  sub     rsp, rax
0x18003817a  lea     r15, [rsp+80h+var_60]
0x18003817f  test    r15, r15
0x180038182  jnz     short loc_1800381A0
0x180038184  mov     rcx, [rbp+68h]; this
0x180038188  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\com"...
0x18003818f  mov     r9d, 8007000Eh; char *
0x180038195  mov     edx, 20Bh; void *
0x18003819a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800381a0  mov     rax, [r8+8]
0x1800381a4  lea     rbx, [r9+r9]
0x1800381a8  mov     edx, [r8]
0x1800381ab  mov     rcx, r15; void *
0x1800381ae  mov     r8, rbx; Size
0x1800381b1  mov     rax, [rax+8]
0x1800381b5  lea     rdx, [rax+rdx*2]; Src
0x1800381b9  call    memcpy_0
0x1800381be  mov     rcx, r15
0x1800381c1  mov     [rbx+r15], r12w
0x1800381c6  call    cs:__imp__o__wtol
0x1800381cc  mov     [rdi+1D4h], eax
0x1800381d2  mov     eax, 0FFFDh
0x1800381d7  and     [rdi+1CEh], ax
0x1800381de  jmp     short loc_1800381E3
0x1800381e0  mov     r14d, esi
0x1800381e3  sub     r14w, [rdi+1BAh]
0x1800381eb  mov     [rdi+1BCh], r14w
0x1800381f3  jmp     short loc_1800381F8
0x1800381f5  movzx   esi, dx
0x1800381f8  mov     [rdi+1C2h], si
0x1800381ff  mov     [rdi+1D2h], si
0x180038206  mov     rcx, [rbp+60h+var_50]
0x18003820a  xor     rcx, rbp; StackCookie
0x18003820d  call    __security_check_cookie
0x180038212  lea     rsp, [rbp+28h]
0x180038216  pop     r15
0x180038218  pop     r14
0x18003821a  pop     r13
0x18003821c  pop     r12
0x18003821e  pop     rdi
0x18003821f  pop     rsi
0x180038220  pop     rbx
0x180038221  pop     rbp
0x180038222  retn
```
