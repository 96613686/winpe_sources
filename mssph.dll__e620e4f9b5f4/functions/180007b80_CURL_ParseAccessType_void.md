# CURL::ParseAccessType(void)

- ea: `0x180007b80`
- end: `0x180007f44`
- name: `?ParseAccessType@CURL@@IEAAXXZ`
- size: `964`
- prototype: `void __fastcall(CURL *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007810`
- `0x1800207f0`
- `0x180022cc8`

## callees

- `0x180007b80`
- `0x1800080b0`
- `0x18000ad60`
- `0x18000b860`
- `0x18000bdec`
- `0x18001e194`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180007c84`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180007c84`

## string_xrefs

- `0x180007cc6`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
void __fastcall CURL::ParseAccessType(CURL *this)
{
  __int16 v2; // cx
  __int16 v3; // cx
  int v4; // ebp
  int v5; // eax
  int v6; // r11d
  __int16 v7; // ax
  _DWORD *v8; // rcx
  _WORD *v9; // rsi
  __int16 *v10; // r12
  _WORD *v11; // r15
  _WORD *v12; // r13
  _WORD *v13; // r10
  wchar_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // rdi
  unsigned int v17; // r9d
  __int64 v18; // r10
  __int64 v19; // rdx
  int v20; // edx
  __int16 v21; // si
  __int64 v22; // rdx
  __int64 v23; // r8
  __int16 v24; // ax
  __int16 v25; // cx
  __int16 v26; // ax
  _WORD *v27; // rax
  int AnySlash; // eax
  __int16 v29; // ax
  __int16 v30; // ax
  unsigned int v31[2]; // [rsp+20h] [rbp-38h] BYREF
  char *v32; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v34; // [rsp+60h] [rbp+8h]

  v2 = *((_WORD *)this + 231);
  if ( (v2 & 1) == 0 )
    return;
  v3 = v2 & 0xFFFE;
  *((_DWORD *)this + 110) = 3;
  *((_WORD *)this + 231) = v3;
  if ( (v3 & 0x20) != 0 )
  {
    v7 = *((_WORD *)this + 22);
    v8 = (_DWORD *)((char *)this + 44);
    v9 = (_WORD *)((char *)this + 454);
    v6 = -1;
    v34 = -1;
    v10 = (__int16 *)((char *)this + 44);
    v11 = (_WORD *)((char *)this + 454);
    v12 = (_WORD *)((char *)this + 454);
  }
  else
  {
    v4 = CLMString::Find((CURL *)((char *)this + 24), 0x23u, 0);
    v5 = CLMString::Find((CURL *)((char *)this + 24), 0x3Fu, 0);
    v34 = v5;
    v6 = v5;
    if ( v4 == -1 || v5 < v4 && v5 != -1 )
      v4 = v5;
    v7 = *((_WORD *)this + 22);
    v8 = (_DWORD *)((char *)this + 44);
    v9 = (_WORD *)((char *)this + 454);
    v10 = (__int16 *)((char *)this + 44);
    v11 = (_WORD *)((char *)this + 454);
    v12 = (_WORD *)((char *)this + 454);
    if ( v4 != -1 )
    {
      v13 = (_WORD *)((char *)this + 456);
      *((_WORD *)this + 228) = v7 - v4;
      goto LABEL_11;
    }
  }
  LOWORD(v4) = v7;
  v13 = (_WORD *)((char *)this + 456);
LABEL_11:
  *v9 = v4;
  if ( !*v8 )
    goto LABEL_48;
  v14 = wcschr(*((const wchar_t **)this + 4), 0x3Au);
  if ( !v14
    || (v15 = *((_QWORD *)this + 4), v16 = ((__int64)v14 - v15) >> 1, (_DWORD)v16 == -1)
    || (int)v16 > (unsigned __int16)*v9 )
  {
    v6 = v34;
    v13 = (_WORD *)((char *)this + 456);
LABEL_48:
    if ( *v11 < 2u )
      goto LABEL_57;
    v27 = (_WORD *)*((_QWORD *)this + 4);
    if ( *v27 == 92 )
    {
      if ( v27[1] != 92 )
        goto LABEL_57;
    }
    else if ( *v27 != 47 || v27[1] != 47 )
    {
LABEL_57:
      v29 = *v10;
      if ( v6 == -1 )
      {
        *v11 = v29;
        v30 = 0;
      }
      else
      {
        *v11 = v6;
        v30 = v29 - v6;
      }
      *v13 = v30;
      return;
    }
    *((_WORD *)this + 220) = 0;
    AnySlash = CLMString::FindAnySlash((CURL *)((char *)this + 24), 3u);
    if ( AnySlash == -1 )
    {
      *((_WORD *)this + 233) = 2;
      v13 = (_WORD *)((char *)this + 456);
    }
    else
    {
      *((_WORD *)this + 233) = AnySlash;
    }
    goto LABEL_57;
  }
  v17 = *((_DWORD *)this + 11);
  if ( (unsigned int)v16 > v17 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x40C,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
      (const char *)0xCE,
      v31[0]);
  v31[0] = 0;
  v31[1] = ((__int64)v14 - v15) >> 1;
  v32 = (char *)this + 24;
  if ( !(_DWORD)v16 )
    goto LABEL_23;
  v18 = *((_QWORD *)this + 4);
  v19 = 0;
  while ( !(unsigned int)IsSlash(*(_WORD *)(v18 + 2 * v19)) )
  {
    v19 = (unsigned int)(v20 + 1);
    if ( (unsigned int)v19 >= (unsigned int)v16 )
      goto LABEL_23;
  }
  if ( v20 == -1 )
  {
LABEL_23:
    v21 = v34;
    if ( (_DWORD)v16 != 1
      || v17 > 3 && (unsigned int)IsSlash(*(_WORD *)(v15 + 4)) && (unsigned int)IsSlash(*(_WORD *)(v23 + 2 * v22)) )
    {
      *((_WORD *)this + 221) = v16 + 1;
      if ( CLMSubStr::CompareNoCase((CLMSubStr *)v31, off_1800357E8) )
      {
        if ( !CLMSubStr::CompareNoCase((CLMSubStr *)v31, off_1800357B8) )
        {
          *((_WORD *)this + 220) = 1;
          return;
        }
        if ( CLMSubStr::CompareNoCase((CLMSubStr *)v31, off_1800357D0) )
        {
          if ( CLMSubStr::CompareNoCase((CLMSubStr *)v31, off_180035800) )
          {
            if ( CLMSubStr::CompareNoCase((CLMSubStr *)v31, off_180035818) )
            {
              if ( (_DWORD)v16 )
                *((_WORD *)this + 220) = 6;
              else
                *((_WORD *)this + 220) = 3;
            }
            else
            {
              *((_WORD *)this + 220) = 9;
            }
          }
          else
          {
            *((_WORD *)this + 220) = 8;
          }
        }
        else
        {
          *((_WORD *)this + 220) = 7;
        }
      }
      else
      {
        *((_WORD *)this + 220) = 0;
      }
      v26 = *v10;
      if ( v34 == -1 )
      {
        *v11 = v26;
        *((_WORD *)this + 228) = 0;
      }
      else
      {
        *v11 = v34;
        *((_WORD *)this + 228) = v26 - v34;
      }
    }
    else
    {
      *((_WORD *)this + 231) &= ~4u;
      *((_DWORD *)this + 112) = 0;
      *((_WORD *)this + 222) = 0;
      *((_WORD *)this + 220) = 0;
      v24 = *v10;
      *((_WORD *)this + 233) = 2;
      if ( v34 == -1 )
      {
        v25 = 0;
        v21 = v24;
      }
      else
      {
        v25 = v24 - v34;
      }
      *v12 = v21;
      *((_WORD *)this + 228) = v25;
    }
  }
}

```

## disassembly

```asm
0x180007b80  mov     rax, rsp
0x180007b83  push    rbx
0x180007b84  sub     rsp, 50h
0x180007b88  mov     rbx, rcx
0x180007b8b  movzx   ecx, word ptr [rcx+1CEh]
0x180007b92  test    cl, 1
0x180007b95  jz      loc_180007F3E
0x180007b9b  mov     [rax+10h], rbp
0x180007b9f  mov     [rax+18h], rsi
0x180007ba3  mov     [rax-20h], r14
0x180007ba7  mov     [rax+20h], rdi
0x180007bab  mov     [rax-10h], r12
0x180007baf  mov     [rax-18h], r13
0x180007bb3  mov     [rax-28h], r15
0x180007bb7  mov     eax, 0FFFEh
0x180007bbc  and     cx, ax
0x180007bbf  mov     dword ptr [rbx+1B8h], 3
0x180007bc9  mov     [rbx+1CEh], cx
0x180007bd0  test    cl, 20h
0x180007bd3  jnz     short loc_180007C3D
0x180007bd5  mov     edx, 23h ; '#'; wchar_t
0x180007bda  lea     rcx, [rbx+18h]; this
0x180007bde  xor     r8d, r8d; unsigned int
0x180007be1  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x180007be6  mov     edx, 3Fh ; '?'; wchar_t
0x180007beb  lea     rcx, [rbx+18h]; this
0x180007bef  xor     r8d, r8d; unsigned int
0x180007bf2  mov     ebp, eax
0x180007bf4  call    ?Find@CLMString@@QEBAH_WI@Z; CLMString::Find(wchar_t,uint)
0x180007bf9  mov     [rsp+58h+arg_0], eax
0x180007bfd  mov     r11d, eax
0x180007c00  cmp     ebp, 0FFFFFFFFh
0x180007c03  jz      short loc_180007C0E
0x180007c05  cmp     eax, ebp
0x180007c07  jge     short loc_180007C10
0x180007c09  cmp     eax, 0FFFFFFFFh
0x180007c0c  jz      short loc_180007C10
0x180007c0e  mov     ebp, eax
0x180007c10  movzx   eax, word ptr [rbx+2Ch]
0x180007c14  lea     rcx, [rbx+2Ch]
0x180007c18  lea     rsi, [rbx+1C6h]
0x180007c1f  mov     r12, rcx
0x180007c22  mov     r15, rsi
0x180007c25  mov     r13, rsi
0x180007c28  cmp     ebp, 0FFFFFFFFh
0x180007c2b  jz      short loc_180007C60
0x180007c2d  lea     r10, [rbx+1C8h]
0x180007c34  sub     ax, bp
0x180007c37  mov     [r10], ax
0x180007c3b  jmp     short loc_180007C6A
0x180007c3d  movzx   eax, word ptr [rbx+2Ch]
0x180007c41  lea     rcx, [rbx+2Ch]
0x180007c45  lea     rsi, [rbx+1C6h]
0x180007c4c  mov     r11d, 0FFFFFFFFh
0x180007c52  mov     [rsp+58h+arg_0], r11d
0x180007c57  mov     r12, rcx
0x180007c5a  mov     r15, rsi
0x180007c5d  mov     r13, rsi
0x180007c60  movzx   ebp, ax
0x180007c63  lea     r10, [rbx+1C8h]
0x180007c6a  mov     [rsi], bp
0x180007c6d  cmp     dword ptr [rcx], 0
0x180007c70  mov     rbp, [rsp+58h+arg_8]
0x180007c75  jbe     loc_180007EA4
0x180007c7b  mov     rcx, [rbx+20h]; Str
0x180007c7f  mov     edx, 3Ah ; ':'; Ch
0x180007c84  call    cs:__imp_wcschr
0x180007c8a  mov     rdi, rax
0x180007c8d  test    rax, rax
0x180007c90  jz      loc_180007E98
0x180007c96  mov     r8, [rbx+20h]
0x180007c9a  sub     rdi, r8
0x180007c9d  sar     rdi, 1
0x180007ca0  cmp     edi, 0FFFFFFFFh
0x180007ca3  jz      loc_180007E98
0x180007ca9  movzx   eax, word ptr [rsi]
0x180007cac  cmp     edi, eax
0x180007cae  jg      loc_180007E98
0x180007cb4  mov     r9d, [rbx+2Ch]
0x180007cb8  lea     rax, [rbx+18h]
0x180007cbc  cmp     edi, r9d
0x180007cbf  jbe     short loc_180007CDE
0x180007cc1  mov     rcx, [rsp+58h]; this
0x180007cc6  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180007ccd  mov     r9d, 0CEh; char *
0x180007cd3  mov     edx, 40Ch; void *
0x180007cd8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180007cde  mov     [rsp+58h+var_38], 0
0x180007ce6  mov     [rsp+58h+var_34], edi
0x180007cea  mov     [rsp+58h+var_30], rax
0x180007cef  test    edi, edi
0x180007cf1  jz      short loc_180007D1F
0x180007cf3  mov     r10, [rax+8]
0x180007cf7  xor     edx, edx
0x180007cf9  nop     dword ptr [rax+00000000h]
0x180007d00  movzx   ecx, word ptr [r10+rdx*2]; wchar_t
0x180007d05  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x180007d0a  test    eax, eax
0x180007d0c  jnz     short loc_180007D16
0x180007d0e  inc     edx
0x180007d10  cmp     edx, edi
0x180007d12  jb      short loc_180007D00
0x180007d14  jmp     short loc_180007D1F
0x180007d16  cmp     edx, 0FFFFFFFFh
0x180007d19  jnz     loc_180007F20
0x180007d1f  mov     esi, [rsp+58h+arg_0]
0x180007d23  cmp     edi, 1
0x180007d26  jnz     short loc_180007DA3
0x180007d28  lea     edx, [rdi+2]
0x180007d2b  cmp     r9d, edx
0x180007d2e  jbe     short loc_180007D4F
0x180007d30  lea     eax, [rdi+1]
0x180007d33  movzx   ecx, word ptr [r8+rax*2]; wchar_t
0x180007d38  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x180007d3d  test    eax, eax
0x180007d3f  jz      short loc_180007D4F
0x180007d41  movzx   ecx, word ptr [r8+rdx*2]; wchar_t
0x180007d46  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x180007d4b  test    eax, eax
0x180007d4d  jnz     short loc_180007DA3
0x180007d4f  mov     eax, 0FFFBh
0x180007d54  inc     di
0x180007d57  and     [rbx+1CEh], ax
0x180007d5e  xor     eax, eax
0x180007d60  mov     [rbx+1C0h], eax
0x180007d66  mov     [rbx+1BCh], ax
0x180007d6d  mov     [rbx+1B8h], ax
0x180007d74  movzx   eax, word ptr [r12]
0x180007d79  mov     [rbx+1D2h], di
0x180007d80  cmp     esi, 0FFFFFFFFh
0x180007d83  jz      short loc_180007D8D
0x180007d85  sub     ax, si
0x180007d88  movzx   ecx, ax
0x180007d8b  jmp     short loc_180007D92
0x180007d8d  xor     ecx, ecx
0x180007d8f  movzx   esi, ax
0x180007d92  mov     [r13+0], si
0x180007d97  mov     [rbx+1C8h], cx
0x180007d9e  jmp     loc_180007F20
0x180007da3  lea     eax, [rdi+1]
0x180007da6  mov     [rbx+1BAh], ax
0x180007dad  lea     rcx, [rsp+58h+var_38]; this
0x180007db2  mov     rdx, cs:off_1800357E8; wchar_t *
0x180007db9  call    ?CompareNoCase@CLMSubStr@@QEBAHPEB_W@Z; CLMSubStr::CompareNoCase(wchar_t const *)
0x180007dbe  test    eax, eax
0x180007dc0  jnz     short loc_180007DCE
0x180007dc2  mov     [rbx+1B8h], ax
0x180007dc9  jmp     loc_180007E69
0x180007dce  mov     rdx, cs:off_1800357B8; wchar_t *
0x180007dd5  lea     rcx, [rsp+58h+var_38]; this
0x180007dda  call    ?CompareNoCase@CLMSubStr@@QEBAHPEB_W@Z; CLMSubStr::CompareNoCase(wchar_t const *)
0x180007ddf  test    eax, eax
0x180007de1  jnz     short loc_180007DF1
0x180007de3  mov     word ptr [rbx+1B8h], 1
0x180007dec  jmp     loc_180007F20
0x180007df1  mov     rdx, cs:off_1800357D0; wchar_t *
0x180007df8  lea     rcx, [rsp+58h+var_38]; this
0x180007dfd  call    ?CompareNoCase@CLMSubStr@@QEBAHPEB_W@Z; CLMSubStr::CompareNoCase(wchar_t const *)
0x180007e02  test    eax, eax
0x180007e04  jnz     short loc_180007E11
0x180007e06  mov     word ptr [rbx+1B8h], 7
0x180007e0f  jmp     short loc_180007E69
0x180007e11  mov     rdx, cs:off_180035800; wchar_t *
0x180007e18  lea     rcx, [rsp+58h+var_38]; this
0x180007e1d  call    ?CompareNoCase@CLMSubStr@@QEBAHPEB_W@Z; CLMSubStr::CompareNoCase(wchar_t const *)
0x180007e22  test    eax, eax
0x180007e24  jnz     short loc_180007E31
0x180007e26  mov     word ptr [rbx+1B8h], 8
0x180007e2f  jmp     short loc_180007E69
0x180007e31  mov     rdx, cs:off_180035818; wchar_t *
0x180007e38  lea     rcx, [rsp+58h+var_38]; this
0x180007e3d  call    ?CompareNoCase@CLMSubStr@@QEBAHPEB_W@Z; CLMSubStr::CompareNoCase(wchar_t const *)
0x180007e42  test    eax, eax
0x180007e44  jnz     short loc_180007E51
0x180007e46  mov     word ptr [rbx+1B8h], 9
0x180007e4f  jmp     short loc_180007E69
0x180007e51  test    edi, edi
0x180007e53  jnz     short loc_180007E60
0x180007e55  mov     word ptr [rbx+1B8h], 3
0x180007e5e  jmp     short loc_180007E69
0x180007e60  mov     word ptr [rbx+1B8h], 6
0x180007e69  movzx   eax, word ptr [r12]
0x180007e6e  cmp     esi, 0FFFFFFFFh
0x180007e71  jz      short loc_180007E86
0x180007e73  sub     ax, si
0x180007e76  mov     [r15], si
0x180007e7a  mov     [rbx+1C8h], ax
0x180007e81  jmp     loc_180007F20
0x180007e86  mov     [r15], ax
0x180007e8a  xor     eax, eax
0x180007e8c  mov     [rbx+1C8h], ax
0x180007e93  jmp     loc_180007F20
0x180007e98  mov     r11d, [rsp+58h+arg_0]
0x180007e9d  lea     r10, [rbx+1C8h]
0x180007ea4  cmp     word ptr [r15], 2
0x180007ea9  jb      short loc_180007F01
0x180007eab  mov     rax, [rbx+20h]
0x180007eaf  movzx   ecx, word ptr [rax]
0x180007eb2  cmp     cx, 5Ch ; '\'
0x180007eb6  jnz     short loc_180007EC0
0x180007eb8  cmp     [rax+2], cx
0x180007ebc  jnz     short loc_180007F01
0x180007ebe  jmp     short loc_180007ECC
0x180007ec0  cmp     cx, 2Fh ; '/'
0x180007ec4  jnz     short loc_180007F01
0x180007ec6  cmp     [rax+2], cx
0x180007eca  jnz     short loc_180007F01
0x180007ecc  xor     eax, eax
0x180007ece  lea     rcx, [rbx+18h]; this
0x180007ed2  mov     edx, 3; unsigned int
0x180007ed7  mov     [rbx+1B8h], ax
0x180007ede  call    ?FindAnySlash@CLMString@@QEBAHI@Z; CLMString::FindAnySlash(uint)
0x180007ee3  cmp     eax, 0FFFFFFFFh
0x180007ee6  jnz     short loc_180007EFA
0x180007ee8  mov     word ptr [rbx+1D2h], 2
0x180007ef1  lea     r10, [rbx+1C8h]
0x180007ef8  jmp     short loc_180007F01
0x180007efa  mov     [rbx+1D2h], ax
0x180007f01  movzx   eax, word ptr [r12]
0x180007f06  cmp     r11d, 0FFFFFFFFh
0x180007f0a  jz      short loc_180007F16
0x180007f0c  mov     [r15], r11w
0x180007f10  sub     ax, r11w
0x180007f14  jmp     short loc_180007F1C
0x180007f16  mov     [r15], ax
0x180007f1a  xor     eax, eax
0x180007f1c  mov     [r10], ax
0x180007f20  mov     rdi, [rsp+58h+arg_18]
0x180007f25  mov     r13, [rsp+58h+var_18]
0x180007f2a  mov     r12, [rsp+58h+var_10]
0x180007f2f  mov     r15, [rsp+58h+var_28]
0x180007f34  mov     rsi, [rsp+58h+arg_10]
0x180007f39  mov     r14, [rsp+58h+var_20]
0x180007f3e  add     rsp, 50h
0x180007f42  pop     rbx
0x180007f43  retn
```
