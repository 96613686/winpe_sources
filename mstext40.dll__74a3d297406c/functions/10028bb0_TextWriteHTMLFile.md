# TextWriteHTMLFile

- ea: `0x10028bb0`
- end: `0x10028ede`
- name: `TextWriteHTMLFile`
- size: `814`
- prototype: `int __stdcall(int, int, void *, int, int, int)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x10026500`
- `0x100268c0`
- `0x10026b10`
- `0x10026bf0`
- `0x10026c60`
- `0x10028ee0`
- `0x10028f80`
- `0x10029000`

## callees

- `0x1001d870`
- `0x10028bb0`
- `0x10029520`
- `0x100295f0`
- `0x1002b81a`
- `0x1002ced0`

## pseudocode

```c
int __stdcall TextWriteHTMLFile(int a1, int a2, unsigned __int16 *a3, int a4, int a5, char a6)
{
  unsigned __int16 *v6; // edi
  int v7; // ebx
  int v8; // ebp
  int v9; // edx
  unsigned __int16 *v10; // ecx
  int v11; // edx
  unsigned __int16 v12; // ax
  int v13; // edx
  unsigned __int16 *v14; // ecx
  int v15; // esi
  unsigned __int16 v16; // ax
  wchar_t *v17; // edi
  int v18; // ecx
  unsigned __int16 *v19; // eax
  unsigned __int16 *v20; // eax
  int v21; // edx
  int v22; // edi
  unsigned __int16 v23; // si
  int v24; // ecx
  unsigned __int16 *v25; // eax
  unsigned __int16 *v26; // eax
  int v27; // edx
  char *v28; // edi
  unsigned __int16 v29; // si
  WCHAR WideCharStr[2]; // [esp+8h] [ebp-168h] BYREF
  size_t Size; // [esp+Ch] [ebp-164h] BYREF
  int v33; // [esp+10h] [ebp-160h] BYREF
  int v34; // [esp+14h] [ebp-15Ch]
  unsigned __int16 v35[2]; // [esp+18h] [ebp-158h] BYREF
  __int16 Src; // [esp+1Ch] [ebp-154h] BYREF
  char v37[34]; // [esp+1Eh] [ebp-152h] BYREF
  CHAR MultiByteStr[300]; // [esp+40h] [ebp-130h] BYREF

  Size = 0;
  v34 = a1;
  v6 = a3;
  if ( !a4 )
    return 0;
  if ( !a5 )
    return BFWriteFile(a1, a3, 2 * a4);
  v7 = a2;
  v8 = a6 & 2;
LABEL_4:
  while ( 1 )
  {
    Size = 300;
    TextConvertFromUnicode(v7, v6, &a4, MultiByteStr, (int)&Size);
    if ( !v8 )
      break;
    if ( a4 != 1 )
      break;
    v33 = 1;
    TextConvertToUnicode(v7, 0, MultiByteStr, &Size, WideCharStr, (int)&v33, 0);
    if ( WideCharStr[0] == *v6
      && WideCharStr[0] != 34
      && WideCharStr[0] != 60
      && WideCharStr[0] != 62
      && WideCharStr[0] != 38
      && WideCharStr[0] >= 0x20u )
    {
      break;
    }
    v9 = 0;
    while ( word_1003F234[4 * v9] != *v6 )
    {
      if ( (unsigned int)++v9 >= 0x14E )
      {
        v10 = v35;
        v11 = 20;
        while ( v11 != -2147483626 )
        {
          v12 = *(unsigned __int16 *)((char *)v10 + (char *)L"&#;" - (char *)v35);
          if ( !v12 )
            break;
          *v10++ = v12;
          if ( !--v11 )
          {
            --v10;
            break;
          }
        }
        *v10 = 0;
        *(_DWORD *)WideCharStr = *v6;
        if ( WideCharStr[0] )
        {
          do
          {
            memmove(v37, &Src, 0x10u);
            v13 = WideCharStr[0] % 10;
            *(_DWORD *)WideCharStr = WideCharStr[0] / 10;
            Src = v13 + 48;
          }
          while ( WideCharStr[0] );
          v7 = a2;
        }
        v6 = v35;
        a4 = wcslen(v35);
        goto LABEL_4;
      }
    }
    v14 = v35;
    v15 = 20;
    while ( v15 != -2147483626 )
    {
      v16 = *(unsigned __int16 *)((char *)v14 + (char *)L"&" - (char *)v35);
      if ( !v16 )
        break;
      *v14++ = v16;
      if ( !--v15 )
      {
        --v14;
        break;
      }
    }
    v17 = (&off_1003F230)[2 * v9];
    *v14 = 0;
    v18 = 20;
    v19 = v35;
    while ( *v19 )
    {
      ++v19;
      if ( !--v18 )
        goto LABEL_39;
    }
    v20 = &v35[20 - v18];
    v21 = 2147483646;
    v22 = (char *)v17 - (char *)v20;
    while ( v21 )
    {
      v23 = *(unsigned __int16 *)((char *)v20 + v22);
      if ( !v23 )
        break;
      *v20 = v23;
      --v21;
      ++v20;
      if ( !--v18 )
      {
        --v20;
        break;
      }
    }
    *v20 = 0;
LABEL_39:
    v24 = 20;
    v25 = v35;
    while ( *v25 )
    {
      ++v25;
      if ( !--v24 )
        goto LABEL_49;
    }
    v26 = &v35[20 - v24];
    v27 = 2147483646;
    v28 = (char *)((char *)L";" - (char *)v26);
    while ( v27 )
    {
      v29 = *(unsigned __int16 *)((char *)v26 + (_DWORD)v28);
      if ( !v29 )
        break;
      *v26 = v29;
      --v27;
      ++v26;
      if ( !--v24 )
      {
        --v26;
        break;
      }
    }
    *v26 = 0;
LABEL_49:
    v6 = v35;
    a4 = wcslen(v35);
  }
  return BFWriteFile(v34, MultiByteStr, Size);
}

```

## disassembly

```asm
0x10028bb0  sub     esp, 168h
0x10028bb6  mov     eax, ___security_cookie
0x10028bbb  xor     eax, esp
0x10028bbd  mov     [esp+168h+var_4], eax
0x10028bc4  mov     eax, [esp+168h+arg_C]
0x10028bcb  mov     [esp+168h+Size], 0
0x10028bd3  push    esi
0x10028bd4  mov     esi, [esp+16Ch+arg_0]
0x10028bdb  mov     [esp+16Ch+var_15C], esi
0x10028bdf  push    edi
0x10028be0  mov     edi, [esp+170h+arg_8]
0x10028be7  test    eax, eax
0x10028be9  jz      loc_10028EC3
0x10028bef  cmp     [esp+170h+arg_10], 0
0x10028bf7  jz      loc_10028EB7
0x10028bfd  push    ebx
0x10028bfe  mov     ebx, [esp+174h+arg_4]
0x10028c05  push    ebp
0x10028c06  mov     ebp, [esp+178h+arg_14]
0x10028c0d  and     ebp, 2
0x10028c10  lea     eax, [esp+178h+Size]
0x10028c14  mov     [esp+178h+Size], 12Ch
0x10028c1c  push    eax; int
0x10028c1d  lea     eax, [esp+17Ch+MultiByteStr]
0x10028c21  push    eax; lpMultiByteStr
0x10028c22  lea     eax, [esp+180h+arg_C]
0x10028c29  push    eax; int
0x10028c2a  push    edi; Src
0x10028c2b  push    ebx; int
0x10028c2c  call    _TextConvertFromUnicode@20; TextConvertFromUnicode(x,x,x,x,x)
0x10028c31  test    ebp, ebp
0x10028c33  jz      loc_10028EA1
0x10028c39  cmp     [esp+178h+arg_C], 1
0x10028c41  jnz     loc_10028EA1
0x10028c47  push    0; int
0x10028c49  lea     eax, [esp+17Ch+var_160]
0x10028c4d  mov     [esp+17Ch+var_160], 1
0x10028c55  push    eax; int
0x10028c56  lea     eax, [esp+180h+WideCharStr]
0x10028c5a  push    eax; lpWideCharStr
0x10028c5b  lea     eax, [esp+184h+Size]
0x10028c5f  push    eax; int
0x10028c60  lea     eax, [esp+188h+MultiByteStr]
0x10028c64  push    eax; Src
0x10028c65  push    0; int
0x10028c67  push    ebx; int
0x10028c68  call    _TextConvertToUnicode@28; TextConvertToUnicode(x,x,x,x,x,x,x)
0x10028c6d  movzx   ecx, word ptr [edi]
0x10028c70  mov     eax, dword ptr [esp+178h+WideCharStr]
0x10028c74  cmp     ax, cx
0x10028c77  jnz     short loc_10028C9B
0x10028c79  cmp     ax, 22h ; '"'
0x10028c7d  jz      short loc_10028C9B
0x10028c7f  cmp     ax, 3Ch ; '<'
0x10028c83  jz      short loc_10028C9B
0x10028c85  cmp     ax, 3Eh ; '>'
0x10028c89  jz      short loc_10028C9B
0x10028c8b  cmp     ax, 26h ; '&'
0x10028c8f  jz      short loc_10028C9B
0x10028c91  cmp     ax, 20h ; ' '
0x10028c95  jnb     loc_10028EA1
0x10028c9b  xor     edx, edx
0x10028c9d  lea     ecx, [ecx+0]
0x10028ca0  cmp     word_1003F234[edx*8], cx
0x10028ca8  jz      loc_10028D6B
0x10028cae  inc     edx
0x10028caf  cmp     edx, 14Eh
0x10028cb5  jb      short loc_10028CA0
0x10028cb7  lea     ecx, [esp+178h+var_158]
0x10028cbb  mov     esi, offset asc_10004958; "&#;"
0x10028cc0  mov     eax, ecx
0x10028cc2  mov     edx, 14h
0x10028cc7  sub     esi, eax
0x10028cc9  lea     esp, [esp+0]
0x10028cd0  lea     eax, [edx+7FFFFFEAh]
0x10028cd6  test    eax, eax
0x10028cd8  jz      short loc_10028CEE
0x10028cda  movzx   eax, word ptr [esi+ecx]
0x10028cde  test    ax, ax
0x10028ce1  jz      short loc_10028CEE
0x10028ce3  mov     [ecx], ax
0x10028ce6  add     ecx, 2
0x10028ce9  dec     edx
0x10028cea  jnz     short loc_10028CD0
0x10028cec  jmp     short loc_10028CF2
0x10028cee  test    edx, edx
0x10028cf0  jnz     short loc_10028CF5
0x10028cf2  sub     ecx, 2
0x10028cf5  xor     eax, eax
0x10028cf7  mov     [ecx], ax
0x10028cfa  movzx   eax, word ptr [edi]
0x10028cfd  mov     dword ptr [esp+178h+WideCharStr], eax
0x10028d01  test    ax, ax
0x10028d04  jz      short loc_10028D47
0x10028d06  mov     ebx, 0Ah
0x10028d0b  jmp     short loc_10028D10
0x10028d10  push    10h; Size
0x10028d12  lea     eax, [esp+17Ch+Src]
0x10028d16  push    eax; Src
0x10028d17  lea     eax, [esp+180h+var_152]
0x10028d1b  push    eax; void *
0x10028d1c  call    _memmove
0x10028d21  movzx   eax, [esp+184h+WideCharStr]
0x10028d26  add     esp, 0Ch
0x10028d29  cdq
0x10028d2a  idiv    ebx
0x10028d2c  movzx   eax, ax
0x10028d2f  mov     dword ptr [esp+178h+WideCharStr], eax
0x10028d33  lea     ecx, [edx+30h]
0x10028d36  mov     [esp+178h+Src], cx
0x10028d3b  test    ax, ax
0x10028d3e  jnz     short loc_10028D10
0x10028d40  mov     ebx, [esp+178h+arg_4]
0x10028d47  lea     edi, [esp+178h+var_158]
0x10028d4b  mov     ecx, edi
0x10028d4d  lea     edx, [ecx+2]
0x10028d50  mov     ax, [ecx]
0x10028d53  add     ecx, 2
0x10028d56  test    ax, ax
0x10028d59  jnz     short loc_10028D50
0x10028d5b  sub     ecx, edx
0x10028d5d  sar     ecx, 1
0x10028d5f  mov     [esp+178h+arg_C], ecx
0x10028d66  jmp     loc_10028C10
0x10028d6b  lea     ecx, [esp+178h+var_158]
0x10028d6f  mov     edi, offset asc_10004954; "&"
0x10028d74  mov     eax, ecx
0x10028d76  mov     esi, 14h
0x10028d7b  sub     edi, eax
0x10028d7d  lea     ecx, [ecx+0]
0x10028d80  lea     eax, [esi+7FFFFFEAh]
0x10028d86  test    eax, eax
0x10028d88  jz      short loc_10028D9E
0x10028d8a  movzx   eax, word ptr [edi+ecx]
0x10028d8e  test    ax, ax
0x10028d91  jz      short loc_10028D9E
0x10028d93  mov     [ecx], ax
0x10028d96  add     ecx, 2
0x10028d99  dec     esi
0x10028d9a  jnz     short loc_10028D80
0x10028d9c  jmp     short loc_10028DA2
0x10028d9e  test    esi, esi
0x10028da0  jnz     short loc_10028DA5
0x10028da2  sub     ecx, 2
0x10028da5  mov     edi, off_1003F230[edx*8]; "zwsp"
0x10028dac  xor     eax, eax
0x10028dae  mov     [ecx], ax
0x10028db1  lea     ecx, [eax+14h]
0x10028db4  lea     eax, [esp+178h+var_158]
0x10028db8  cmp     word ptr [eax], 0
0x10028dbc  jz      short loc_10028DC6
0x10028dbe  add     eax, 2
0x10028dc1  dec     ecx
0x10028dc2  jnz     short loc_10028DB8
0x10028dc4  jmp     short loc_10028E15
0x10028dc6  test    ecx, ecx
0x10028dc8  jz      short loc_10028E15
0x10028dca  mov     edx, 14h
0x10028dcf  lea     eax, [esp+178h+var_158]
0x10028dd3  sub     edx, ecx
0x10028dd5  mov     ecx, 14h
0x10028dda  lea     eax, [eax+edx*2]
0x10028ddd  sub     ecx, edx
0x10028ddf  jz      short loc_10028E0D
0x10028de1  add     edx, 7FFFFFEAh
0x10028de7  add     edx, ecx
0x10028de9  sub     edi, eax
0x10028deb  jmp     short loc_10028DF0
0x10028df0  test    edx, edx
0x10028df2  jz      short loc_10028E09
0x10028df4  movzx   esi, word ptr [edi+eax]
0x10028df8  test    si, si
0x10028dfb  jz      short loc_10028E09
0x10028dfd  mov     [eax], si
0x10028e00  dec     edx
0x10028e01  add     eax, 2
0x10028e04  dec     ecx
0x10028e05  jnz     short loc_10028DF0
0x10028e07  jmp     short loc_10028E0D
0x10028e09  test    ecx, ecx
0x10028e0b  jnz     short loc_10028E10
0x10028e0d  sub     eax, 2
0x10028e10  xor     ecx, ecx
0x10028e12  mov     [eax], cx
0x10028e15  mov     ecx, 14h
0x10028e1a  lea     eax, [esp+178h+var_158]
0x10028e1e  mov     edi, edi
0x10028e20  cmp     word ptr [eax], 0
0x10028e24  jz      short loc_10028E2E
0x10028e26  add     eax, 2
0x10028e29  dec     ecx
0x10028e2a  jnz     short loc_10028E20
0x10028e2c  jmp     short loc_10028E7D
0x10028e2e  test    ecx, ecx
0x10028e30  jz      short loc_10028E7D
0x10028e32  mov     edx, 14h
0x10028e37  lea     eax, [esp+178h+var_158]
0x10028e3b  sub     edx, ecx
0x10028e3d  mov     ecx, 14h
0x10028e42  lea     eax, [eax+edx*2]
0x10028e45  sub     ecx, edx
0x10028e47  jz      short loc_10028E75
0x10028e49  add     edx, 7FFFFFEAh
0x10028e4f  mov     edi, offset asc_100029F8; ";"
0x10028e54  add     edx, ecx
0x10028e56  sub     edi, eax
0x10028e58  test    edx, edx
0x10028e5a  jz      short loc_10028E71
0x10028e5c  movzx   esi, word ptr [edi+eax]
0x10028e60  test    si, si
0x10028e63  jz      short loc_10028E71
0x10028e65  mov     [eax], si
0x10028e68  dec     edx
0x10028e69  add     eax, 2
0x10028e6c  dec     ecx
0x10028e6d  jnz     short loc_10028E58
0x10028e6f  jmp     short loc_10028E75
0x10028e71  test    ecx, ecx
0x10028e73  jnz     short loc_10028E78
0x10028e75  sub     eax, 2
0x10028e78  xor     ecx, ecx
0x10028e7a  mov     [eax], cx
0x10028e7d  lea     edi, [esp+178h+var_158]
0x10028e81  mov     ecx, edi
0x10028e83  lea     edx, [ecx+2]
0x10028e86  mov     ax, [ecx]
0x10028e89  add     ecx, 2
0x10028e8c  test    ax, ax
0x10028e8f  jnz     short loc_10028E86
0x10028e91  sub     ecx, edx
0x10028e93  sar     ecx, 1
0x10028e95  mov     [esp+178h+arg_C], ecx
0x10028e9c  jmp     loc_10028C10
0x10028ea1  push    [esp+178h+Size]; Size
0x10028ea5  lea     eax, [esp+17Ch+MultiByteStr]
0x10028ea9  push    eax; Src
0x10028eaa  push    [esp+180h+var_15C]; int
0x10028eae  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10028eb3  pop     ebp
0x10028eb4  pop     ebx
0x10028eb5  jmp     short loc_10028EC5
0x10028eb7  add     eax, eax
0x10028eb9  push    eax; Size
0x10028eba  push    edi; Src
0x10028ebb  push    esi; int
0x10028ebc  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10028ec1  jmp     short loc_10028EC5
0x10028ec3  xor     eax, eax
0x10028ec5  mov     ecx, [esp+170h+var_4]
0x10028ecc  pop     edi
0x10028ecd  pop     esi
0x10028ece  xor     ecx, esp; StackCookie
0x10028ed0  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10028ed5  add     esp, 168h
0x10028edb  retn    18h
```
