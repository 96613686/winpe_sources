# UrlValidator::WriteEncoded(ulong,ulong)

- ea: `0x180037a68`
- end: `0x180037eae`
- name: `?WriteEncoded@UrlValidator@@AEAA_NKK@Z`
- size: `1094`
- prototype: `bool __fastcall(UrlValidator *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004b684`

## callees

- `0x1800374d0`
- `0x180037a68`
- `0x180054010`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180037c2f`
- `msvcrt!_snwprintf_s` at `0x180037cea`
- `msvcrt!_snwprintf_s` at `0x180037df5`
- `msvcrt!_snwprintf_s` at `0x180037e2a`
- `msvcrt!_snwprintf_s` at `0x180037e6c`
- `msvcrt!_snwprintf_s` at `0x180037c2f`
- `msvcrt!_snwprintf_s` at `0x180037cea`
- `msvcrt!_snwprintf_s` at `0x180037df5`
- `msvcrt!_snwprintf_s` at `0x180037e2a`
- `msvcrt!_snwprintf_s` at `0x180037e6c`
- `msvcrt!memmove_s` at `0x180037b01`
- `msvcrt!memmove_s` at `0x180037b01`

## pseudocode

```c
char __fastcall UrlValidator::WriteEncoded(UrlValidator *this, unsigned int a2, int a3)
{
  int v4; // r15d
  __int64 v5; // rdi
  char *v6; // rsi
  unsigned int v7; // ecx
  unsigned int v8; // r15d
  char *v9; // rbx
  __int64 v10; // rbp
  unsigned __int16 v11; // bx
  unsigned __int16 WcharType; // r8
  unsigned __int16 v13; // r9
  bool v15; // zf
  unsigned __int8 v16; // r8
  int v17; // r14d
  unsigned __int8 v18; // dl
  unsigned __int8 v19; // r9
  unsigned __int8 v20; // bl
  __int64 v21; // r15
  size_t v22; // r11
  __int64 v23; // [rsp+20h] [rbp-78h]
  __int64 v24; // [rsp+28h] [rbp-70h]
  __int64 v25; // [rsp+30h] [rbp-68h]
  __int64 v26; // [rsp+38h] [rbp-60h]
  unsigned int v27; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-54h]
  char *v29; // [rsp+48h] [rbp-50h]
  char v30; // [rsp+A8h] [rbp+10h]
  unsigned int v31; // [rsp+B0h] [rbp+18h]
  unsigned __int16 v32; // [rsp+B8h] [rbp+20h]

  if ( !a3 )
    return 1;
  v4 = *((_DWORD *)this + 1);
  v5 = (unsigned int)(2048 - v4);
  v30 = 0;
  v31 = 0;
  v6 = (char *)this + 2 * a2 + 12;
  v7 = *((_DWORD *)this + 2);
  v8 = v4 - a2;
  v28 = v8;
  v9 = &v6[2 * v5];
  v29 = v9;
  while ( v7 < *((_DWORD *)this + 1) )
  {
    if ( *((_WORD *)this + v7 + 6) == 35 )
    {
      v31 = v7;
      v30 = 1;
      break;
    }
    ++v7;
  }
  memmove_s(&v6[2 * v5], 2LL * v8, v6, 2LL * v8);
  v10 = 0;
  v32 = 0;
  while ( (unsigned int)v10 < v8 )
  {
    v11 = *(_WORD *)&v9[2 * v10];
    WcharType = GetWcharType(v11);
    if ( (WcharType & 7) != 0 && v11 < 0x7Fu )
    {
LABEL_62:
      *(_WORD *)&v6[2 * v10] = v11;
      goto LABEL_63;
    }
    if ( (unsigned __int16)(v11 + 10240) > 0x3FFu )
    {
      v13 = v32;
    }
    else
    {
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= v8 )
        return 0;
      v13 = v11;
      v32 = v11;
      v11 = *(_WORD *)&v29[2 * v10];
      if ( (unsigned __int16)(v11 + 9216) > 0x3FFu )
        return 0;
    }
    if ( v11 > 0x2Fu )
    {
      if ( v11 == 58 )
      {
        if ( *((_DWORD *)this + 1028) != 11 )
          goto LABEL_62;
        goto LABEL_44;
      }
      if ( v11 == 61 || v11 == 63 || v11 == 95 )
        goto LABEL_62;
      v15 = v11 == 126;
    }
    else
    {
      switch ( v11 )
      {
        case '/':
        case '$':
        case '%':
          goto LABEL_62;
        case '&':
          *(_WORD *)&v6[2 * v10] = v11;
          if ( v30 && v11 == 38 && (_DWORD)v10 + 1 == v31 - *((_DWORD *)this + 2) )
          {
            if ( (unsigned int)v5 < 3 )
              return 0;
            LODWORD(v23) = 32;
            _snwprintf_s((wchar_t *const)&v6[2 * (unsigned int)v10 + 2], 4u, 0xFFFFFFFFFFFFFFFFuLL, L"%%%02x", v23);
            LODWORD(v5) = v5 - 3;
            v6 += 6;
          }
          goto LABEL_63;
        case '+':
        case '-':
          goto LABEL_62;
      }
      v15 = v11 == 46;
    }
    if ( v15 )
      goto LABEL_62;
    if ( v30 && v11 == 35 && (_DWORD)v10 == v31 - *((_DWORD *)this + 2) )
    {
      *(_WORD *)&v6[2 * v10] = 35;
      goto LABEL_63;
    }
    if ( (WcharType & 0x58) == 0 && ((WcharType & 0x20) != 0 || (WcharType & 0x200) == 0) )
      return 0;
LABEL_44:
    if ( v11 > 0x7Fu )
    {
      v27 = 0;
      if ( v11 <= 0x7FFu )
      {
        v16 = 0;
        v17 = 6;
        v18 = (v11 >> 6) | 0xC0;
        goto LABEL_53;
      }
      if ( (unsigned __int16)(v11 + 9216) > 0x3FFu )
      {
        v18 = (v11 >> 6) & 0x3F | 0x80;
        v17 = 9;
        v16 = (v11 >> 12) | 0xE0;
LABEL_53:
        v19 = 0;
        v20 = v11 & 0x3F;
      }
      else
      {
        if ( !Utf16PairToUtf32(v13, v11, &v27) )
          return 0;
        v17 = 12;
        v18 = (v27 >> 6) & 0x3F | 0x80;
        v16 = (v27 >> 12) & 0x3F | 0x80;
        v19 = (v27 >> 18) & 7 | 0xF0;
        v20 = v27 & 0x3F;
      }
      v21 = (unsigned int)(v17 - 1);
      if ( (unsigned int)v5 < (unsigned int)v21 )
        return 0;
      v22 = (unsigned int)(v17 + 1);
      if ( v17 == 6 )
      {
        LODWORD(v24) = v20 | 0x80;
        LODWORD(v23) = v18;
        _snwprintf_s((wchar_t *const)&v6[2 * v10], (unsigned int)v22, 0xFFFFFFFFFFFFFFFFuLL, L"%%%02x%%%02x", v23, v24);
        goto LABEL_59;
      }
      if ( v17 == 9 )
      {
        LODWORD(v25) = v20 | 0x80;
        LODWORD(v24) = v18;
        LODWORD(v23) = v16;
        _snwprintf_s((wchar_t *const)&v6[2 * v10], v22, 0xFFFFFFFFFFFFFFFFuLL, L"%%%02x%%%02x%%%02x", v23, v24, v25);
LABEL_59:
        LODWORD(v5) = v5 - v17 + 1;
        v6 += 2 * v21;
      }
      else
      {
        LODWORD(v26) = v20 | 0x80;
        LODWORD(v25) = v18;
        LODWORD(v24) = v16;
        LODWORD(v23) = v19;
        _snwprintf_s(
          (wchar_t *const)&v6[2 * (unsigned int)(v10 - 1)],
          (unsigned int)(v17 + 1),
          0xFFFFFFFFFFFFFFFFuLL,
          L"%%%02x%%%02x%%%02x%%%02x",
          v23,
          v24,
          v25,
          v26);
        v6 += 20;
        LODWORD(v5) = v5 - v17 + 2;
      }
      v8 = v28;
      goto LABEL_63;
    }
    if ( (unsigned int)v5 < 3 )
      return 0;
    LODWORD(v23) = v11;
    _snwprintf_s((wchar_t *const)&v6[2 * v10], 4u, 0xFFFFFFFFFFFFFFFFuLL, L"%%%02x", v23);
    LODWORD(v5) = v5 - 2;
    v6 += 4;
LABEL_63:
    v9 = v29;
    v10 = (unsigned int)(v10 + 1);
  }
  *((_DWORD *)this + 1) = 2048 - v5;
  return 1;
}

```

## disassembly

```asm
0x180037a68  push    rbx
0x180037a6a  push    rbp
0x180037a6b  push    rsi
0x180037a6c  push    rdi
0x180037a6d  push    r12
0x180037a6f  push    r13
0x180037a71  push    r14
0x180037a73  push    r15
0x180037a75  sub     rsp, 58h
0x180037a79  mov     r13, rcx
0x180037a7c  test    r8d, r8d
0x180037a7f  jz      loc_180037E9B
0x180037a85  mov     r15d, [rcx+4]
0x180037a89  mov     r12d, 800h
0x180037a8f  mov     edi, r12d
0x180037a92  mov     eax, edx
0x180037a94  sub     edi, [rcx+4]
0x180037a97  mov     r14d, 23h ; '#'
0x180037a9d  mov     [rsp+98h+arg_8], 0
0x180037aa5  mov     [rsp+98h+arg_10], 0
0x180037ab0  lea     rsi, ds:0Ch[rax*2]
0x180037ab8  add     rsi, rcx
0x180037abb  mov     ecx, [rcx+8]
0x180037abe  sub     r15d, edx
0x180037ac1  mov     [rsp+98h+var_54], r15d
0x180037ac6  lea     rbx, [rsi+rdi*2]
0x180037aca  mov     [rsp+98h+var_50], rbx
0x180037acf  cmp     ecx, [r13+4]
0x180037ad3  jnb     short loc_180037AF2
0x180037ad5  mov     eax, ecx
0x180037ad7  cmp     [r13+rax*2+0Ch], r14w
0x180037add  jz      short loc_180037AE3
0x180037adf  inc     ecx
0x180037ae1  jmp     short loc_180037ACF
0x180037ae3  mov     [rsp+98h+arg_10], ecx
0x180037aea  mov     [rsp+98h+arg_8], 1
0x180037af2  mov     edx, r15d
0x180037af5  mov     r8, rsi; Source
0x180037af8  add     rdx, rdx; DestinationSize
0x180037afb  mov     rcx, rbx; Destination
0x180037afe  mov     r9, rdx; SourceSize
0x180037b01  call    cs:__imp_memmove_s
0x180037b07  xor     ebp, ebp
0x180037b09  mov     [rsp+98h+arg_18], 0
0x180037b14  cmp     ebp, r15d
0x180037b17  jnb     loc_180037E94
0x180037b1d  movzx   ebx, word ptr [rbx+rbp*2]
0x180037b21  movzx   ecx, bx; unsigned __int16
0x180037b24  call    ?GetWcharType@@YAGG@Z; GetWcharType(ushort)
0x180037b29  movzx   r8d, ax
0x180037b2d  test    al, 7
0x180037b2f  jz      short loc_180037B3B
0x180037b31  cmp     bx, 7Fh
0x180037b35  jb      loc_180037E84
0x180037b3b  mov     eax, 2800h
0x180037b40  mov     r10d, 3FFh
0x180037b46  add     eax, ebx
0x180037b48  cmp     ax, r10w
0x180037b4c  ja      short loc_180037B81
0x180037b4e  inc     ebp
0x180037b50  cmp     ebp, r15d
0x180037b53  jnb     short loc_180037B7A
0x180037b55  movzx   r9d, bx
0x180037b59  mov     r11d, 2400h
0x180037b5f  mov     rbx, [rsp+98h+var_50]
0x180037b64  mov     [rsp+98h+arg_18], r9d
0x180037b6c  movzx   ebx, word ptr [rbx+rbp*2]
0x180037b70  lea     eax, [r11+rbx]
0x180037b74  cmp     ax, r10w
0x180037b78  jbe     short loc_180037B8F
0x180037b7a  xor     al, al
0x180037b7c  jmp     loc_180037E9D
0x180037b81  mov     r9d, [rsp+98h+arg_18]
0x180037b89  mov     r11d, 2400h
0x180037b8f  movzx   edx, bx
0x180037b92  cmp     edx, 2Fh ; '/'
0x180037b95  ja      loc_180037C41
0x180037b9b  jz      loc_180037E84
0x180037ba1  mov     ecx, edx
0x180037ba3  sub     ecx, 24h ; '$'
0x180037ba6  jz      loc_180037E84
0x180037bac  sub     ecx, 1
0x180037baf  jz      loc_180037E84
0x180037bb5  sub     ecx, 1
0x180037bb8  jz      short loc_180037BD4
0x180037bba  sub     ecx, 5
0x180037bbd  jz      loc_180037E84
0x180037bc3  sub     ecx, 2
0x180037bc6  jz      loc_180037E84
0x180037bcc  cmp     ecx, 1
0x180037bcf  jmp     loc_180037C64
0x180037bd4  cmp     [rsp+98h+arg_8], 0
0x180037bdc  mov     edx, ebp
0x180037bde  mov     [rsi+rbp*2], bx
0x180037be2  jz      loc_180037E88
0x180037be8  cmp     bx, 26h ; '&'
0x180037bec  jnz     loc_180037E88
0x180037bf2  mov     ecx, [rsp+98h+arg_10]
0x180037bf9  lea     eax, [rbp+1]
0x180037bfc  sub     ecx, [r13+8]
0x180037c00  cmp     eax, ecx
0x180037c02  jnz     loc_180037E88
0x180037c08  cmp     edi, 3
0x180037c0b  jb      loc_180037B7A
0x180037c11  inc     rdx
0x180037c14  mov     dword ptr [rsp+98h+var_78], 20h ; ' '
0x180037c1c  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180037c20  lea     r9, a02x; "%%%02x"
0x180037c27  lea     rcx, [rsi+rdx*2]; Buffer
0x180037c2b  lea     edx, [r8+5]; BufferCount
0x180037c2f  call    cs:__imp__snwprintf_s
0x180037c35  add     edi, 0FFFFFFFDh
0x180037c38  add     rsi, 6
0x180037c3c  jmp     loc_180037E88
0x180037c41  cmp     edx, 3Ah ; ':'
0x180037c44  jz      short loc_180037CB6
0x180037c46  cmp     edx, 3Dh ; '='
0x180037c49  jz      loc_180037E84
0x180037c4f  cmp     edx, 3Fh ; '?'
0x180037c52  jz      loc_180037E84
0x180037c58  cmp     edx, 5Fh ; '_'
0x180037c5b  jz      loc_180037E84
0x180037c61  cmp     edx, 7Eh ; '~'
0x180037c64  jz      loc_180037E84
0x180037c6a  cmp     [rsp+98h+arg_8], 0
0x180037c72  jz      short loc_180037C99
0x180037c74  mov     r14d, 23h ; '#'
0x180037c7a  cmp     bx, r14w
0x180037c7e  jnz     short loc_180037C99
0x180037c80  mov     eax, [rsp+98h+arg_10]
0x180037c87  sub     eax, [r13+8]
0x180037c8b  cmp     ebp, eax
0x180037c8d  jnz     short loc_180037C99
0x180037c8f  mov     [rsi+rbp*2], r14w
0x180037c94  jmp     loc_180037E88
0x180037c99  test    r8b, 58h
0x180037c9d  jnz     short loc_180037CC4
0x180037c9f  test    r8b, 20h
0x180037ca3  jnz     loc_180037B7A
0x180037ca9  bt      r8w, 9
0x180037caf  jb      short loc_180037CC4
0x180037cb1  jmp     loc_180037B7A
0x180037cb6  cmp     dword ptr [r13+1010h], 0Bh
0x180037cbe  jnz     loc_180037E84
0x180037cc4  cmp     bx, 7Fh
0x180037cc8  ja      short loc_180037CFC
0x180037cca  cmp     edi, 3
0x180037ccd  jb      loc_180037B7A
0x180037cd3  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180037cd7  mov     dword ptr [rsp+98h+var_78], edx
0x180037cdb  lea     rcx, [rsi+rbp*2]; Buffer
0x180037cdf  lea     r9, a02x; "%%%02x"
0x180037ce6  lea     edx, [r8+5]; BufferCount
0x180037cea  call    cs:__imp__snwprintf_s
0x180037cf0  add     edi, 0FFFFFFFEh
0x180037cf3  add     rsi, 4
0x180037cf7  jmp     loc_180037E88
0x180037cfc  mov     eax, 7FFh
0x180037d01  mov     [rsp+98h+arg_0], 0
0x180037d0c  mov     [rsp+98h+var_58], 0
0x180037d14  movzx   edx, bx; unsigned __int16
0x180037d17  cmp     bx, ax
0x180037d1a  ja      short loc_180037D33
0x180037d1c  mov     r8b, byte ptr [rsp+98h+arg_0+2]
0x180037d24  mov     r14d, 6
0x180037d2a  shr     dx, 6
0x180037d2e  or      dl, 0C0h
0x180037d31  jmp     short loc_180037DAA
0x180037d33  lea     eax, [r11+rbx]
0x180037d37  cmp     ax, r10w
0x180037d3b  ja      short loc_180037D8D
0x180037d3d  lea     r8, [rsp+98h+var_58]; unsigned int *
0x180037d42  movzx   ecx, r9w; unsigned __int16
0x180037d46  call    ?Utf16PairToUtf32@@YA_NGGAEAK@Z; Utf16PairToUtf32(ushort,ushort,ulong &)
0x180037d4b  test    al, al
0x180037d4d  jz      loc_180037B7A
0x180037d53  mov     ecx, [rsp+98h+var_58]
0x180037d57  mov     r14d, 0Ch
0x180037d5d  mov     edx, ecx
0x180037d5f  mov     r8d, ecx
0x180037d62  shr     edx, 6
0x180037d65  mov     r9d, ecx
0x180037d68  shr     r8d, 0Ch
0x180037d6c  and     dl, 3Fh
0x180037d6f  shr     r9d, 12h
0x180037d73  and     r8b, 3Fh
0x180037d77  and     r9b, 7
0x180037d7b  or      dl, 80h
0x180037d7e  or      r8b, 80h
0x180037d82  or      r9b, 0F0h
0x180037d86  and     cl, 3Fh
0x180037d89  mov     bl, cl
0x180037d8b  jmp     short loc_180037DB5
0x180037d8d  shr     dx, 6
0x180037d91  movzx   r8d, bx
0x180037d95  and     dl, 3Fh
0x180037d98  shr     r8w, 0Ch
0x180037d9d  or      dl, 80h
0x180037da0  mov     r14d, 9
0x180037da6  or      r8b, 0E0h
0x180037daa  mov     r9b, byte ptr [rsp+98h+arg_0+3]
0x180037db2  and     bl, 3Fh
0x180037db5  lea     r15d, [r14-1]
0x180037db9  cmp     edi, r15d
0x180037dbc  jb      loc_180037B7A
0x180037dc2  movzx   r10d, bl
0x180037dc6  lea     r11d, [r14+1]
0x180037dca  bts     r10d, 7
0x180037dcf  cmp     r14d, 6
0x180037dd3  jnz     short loc_180037DFD
0x180037dd5  movzx   r8d, dl
0x180037dd9  lea     rcx, [rsi+rbp*2]; Buffer
0x180037ddd  mov     dword ptr [rsp+98h+var_70], r10d
0x180037de2  lea     r9, a02x02x; "%%%02x%%%02x"
0x180037de9  mov     dword ptr [rsp+98h+var_78], r8d
0x180037dee  mov     edx, r11d; BufferCount
0x180037df1  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180037df5  call    cs:__imp__snwprintf_s
0x180037dfb  jmp     short loc_180037E30
0x180037dfd  movzx   edx, dl
0x180037e00  movzx   r8d, r8b
0x180037e04  cmp     r14d, 9
0x180037e08  jnz     short loc_180037E40
0x180037e0a  mov     dword ptr [rsp+98h+var_68], r10d
0x180037e0f  lea     rcx, [rsi+rbp*2]; Buffer
0x180037e13  mov     dword ptr [rsp+98h+var_70], edx
0x180037e17  lea     r9, a02x02x02x; "%%%02x%%%02x%%%02x"
0x180037e1e  mov     dword ptr [rsp+98h+var_78], r8d
0x180037e23  mov     rdx, r11; BufferCount
0x180037e26  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180037e2a  call    cs:__imp__snwprintf_s
0x180037e30  sub     edi, r14d
0x180037e33  inc     edi
0x180037e35  lea     rsi, [rsi+r15*2]
0x180037e39  mov     r15d, [rsp+98h+var_54]
0x180037e3e  jmp     short loc_180037E88
0x180037e40  mov     dword ptr [rsp+98h+var_60], r10d
0x180037e45  lea     eax, [rbp-1]
0x180037e48  mov     dword ptr [rsp+98h+var_68], edx
0x180037e4c  lea     rcx, [rsi+rax*2]; Buffer
0x180037e50  movzx   r9d, r9b
0x180037e54  mov     rdx, r11; BufferCount
0x180037e57  mov     dword ptr [rsp+98h+var_70], r8d
0x180037e5c  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180037e60  mov     dword ptr [rsp+98h+var_78], r9d
0x180037e65  lea     r9, a02x02x02x02x; "%%%02x%%%02x%%%02x%%%02x"
0x180037e6c  call    cs:__imp__snwprintf_s
0x180037e72  sub     edi, r14d
0x180037e75  cmp     r14d, 0Ch
0x180037e79  jnz     short loc_180037E33
0x180037e7b  add     rsi, 14h
0x180037e7f  add     edi, 2
0x180037e82  jmp     short loc_180037E39
0x180037e84  mov     [rsi+rbp*2], bx
0x180037e88  mov     rbx, [rsp+98h+var_50]
0x180037e8d  inc     ebp
0x180037e8f  jmp     loc_180037B14
0x180037e94  sub     r12d, edi
0x180037e97  mov     [r13+4], r12d
0x180037e9b  mov     al, 1
0x180037e9d  add     rsp, 58h
0x180037ea1  pop     r15
0x180037ea3  pop     r14
0x180037ea5  pop     r13
0x180037ea7  pop     r12
0x180037ea9  pop     rdi
0x180037eaa  pop     rsi
0x180037eab  pop     rbp
0x180037eac  pop     rbx
0x180037ead  retn
```
