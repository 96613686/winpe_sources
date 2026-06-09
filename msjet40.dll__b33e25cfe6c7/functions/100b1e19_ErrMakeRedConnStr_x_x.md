# ErrMakeRedConnStr(x,x)

- ea: `0x100b1e19`
- end: `0x100b1fed`
- name: `_ErrMakeRedConnStr@8`
- size: `468`
- prototype: `int __thiscall(void *Src)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x100b259b`
- `0x100b52e2`
- `0x100ccf50`

## callees

- `0x100129b0`
- `0x1001ea70`
- `0x10095d8d`
- `0x100b1e19`
- `0x101248f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b1e8f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b1fa8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b1fbf`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b1e8f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b1fa8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b1fbf`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100b1e7c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100b1eaf`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100b1e7c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100b1eaf`

## string_xrefs

- `0x100b1f01`: `MS Access`
- `0x100b1f4f`: `MS Access`

## pseudocode

```c
int __fastcall ErrMakeRedConnStr(_WORD *Src, unsigned int a2)
{
  int v3; // edi
  _WORD *v4; // esi
  __int16 v6; // cx
  int v7; // esi
  __int16 v8; // dx
  int v9; // eax
  wchar_t *v10; // eax
  const wchar_t *v11; // eax
  bool v12; // zf
  int v13; // eax
  _WORD *v14; // ecx
  unsigned int v16; // ecx
  wchar_t *v18; // eax
  wchar_t *v19; // eax
  int v20; // [esp+8h] [ebp-Ch] BYREF
  wchar_t *Str; // [esp+Ch] [ebp-8h] BYREF
  unsigned int v22; // [esp+10h] [ebp-4h]

  v22 = a2;
  v3 = 0;
  if ( !Src )
    return v3;
  v4 = Src;
  while ( *v4++ )
    ;
  v6 = *Src;
  v7 = v4 - (Src + 1);
  v8 = 39;
  v9 = v7;
  if ( v6 == 39 || (v8 = 34, v6 == 34) )
  {
    if ( Src[v9 - 1] == v8 )
    {
      Src[v9 - 1] = 0;
      memmove(Src, Src + 1, v9 * 2 - 2);
      v7 -= 2;
    }
  }
  if ( _wcschr(Src, 0x3Bu) )
  {
    if ( *Src != 59 && WCSNICMP(9) && WCSNICMP(7) && WCSNICMP(7) )
      return v3;
    FindConnStrItem(&Str, &v20);
    if ( !v20 )
      return -3060;
    v18 = _wcsrchr(Str, 0x5Cu);
    if ( v18 )
      v19 = v18 + 1;
    else
      v19 = Str;
    Str = (wchar_t *)(_wcsrchr(v19, 0x2Eu) == 0);
    v16 = v22;
    if ( v7 + 4 * (int)Str + 1 <= v22 )
      goto LABEL_19;
    return -3054;
  }
  v10 = _wcsrchr(Src, 0x5Cu);
  if ( v10 )
    v11 = v10 + 1;
  else
    v11 = Src;
  v12 = _wcschr(v11, 0x2Eu) == 0;
  Str = (wchar_t *)v12;
  v13 = 24;
  if ( !v12 )
    v13 = 20;
  if ( v7 + v13 > v22 )
    return -3054;
  v14 = Src;
  while ( *v14++ )
    ;
  memmove(Src + 19, Src, 2 * (v14 - (Src + 1)) + 2);
  v16 = v22;
  *(_DWORD *)Src = *(_DWORD *)L"MS Access";
  *((_DWORD *)Src + 1) = *(_DWORD *)L" Access";
  *((_DWORD *)Src + 2) = *(_DWORD *)L"ccess";
  *((_DWORD *)Src + 3) = *(_DWORD *)L"ess";
  Src[8] = wszAccess[8];
  Src[9] = 59;
  *((_DWORD *)Src + 5) = *(_DWORD *)L"DATABASE=";
  *((_DWORD *)Src + 6) = *(_DWORD *)L"TABASE=";
  *((_DWORD *)Src + 7) = *(_DWORD *)L"BASE=";
  *((_DWORD *)Src + 8) = *(_DWORD *)L"SE=";
  Src[18] = wszDbEq[8];
  v3 = 0;
LABEL_19:
  if ( Str )
    WCSCAT2(Src, L".mdb", v16);
  return v3;
}

```

## disassembly

```asm
0x100b1e19  mov     edi, edi
0x100b1e1b  push    ebp
0x100b1e1c  mov     ebp, esp
0x100b1e1e  sub     esp, 0Ch
0x100b1e21  push    ebx
0x100b1e22  mov     [ebp+var_4], edx
0x100b1e25  mov     ebx, ecx
0x100b1e27  xor     edx, edx
0x100b1e29  push    edi
0x100b1e2a  mov     edi, edx
0x100b1e2c  test    ebx, ebx
0x100b1e2e  jz      loc_100B1F3F
0x100b1e34  push    esi
0x100b1e35  mov     esi, ebx
0x100b1e37  lea     ecx, [esi+2]
0x100b1e3a  mov     ax, [esi]
0x100b1e3d  add     esi, 2
0x100b1e40  cmp     ax, dx
0x100b1e43  jnz     short loc_100B1E3A
0x100b1e45  sub     esi, ecx
0x100b1e47  movzx   ecx, word ptr [ebx]
0x100b1e4a  sar     esi, 1
0x100b1e4c  push    27h ; '''
0x100b1e4e  pop     edx
0x100b1e4f  lea     eax, [esi+esi]
0x100b1e52  cmp     cx, dx
0x100b1e55  jnz     short loc_100B1E9F
0x100b1e57  cmp     [eax+ebx-2], dx
0x100b1e5c  jnz     short loc_100B1E79
0x100b1e5e  xor     ecx, ecx
0x100b1e60  mov     [eax+ebx-2], cx
0x100b1e65  add     eax, 0FFFFFFFEh
0x100b1e68  push    eax; Size
0x100b1e69  lea     eax, [ebx+2]
0x100b1e6c  push    eax; Src
0x100b1e6d  push    ebx; void *
0x100b1e6e  call    _memmove
0x100b1e73  add     esp, 0Ch
0x100b1e76  add     esi, 0FFFFFFFEh
0x100b1e79  push    3Bh ; ';'; Ch
0x100b1e7b  push    ebx; Str
0x100b1e7c  call    ds:__imp__wcschr
0x100b1e82  pop     ecx
0x100b1e83  pop     ecx
0x100b1e84  test    eax, eax
0x100b1e86  jnz     loc_100B1F45
0x100b1e8c  push    5Ch ; '\'; Ch
0x100b1e8e  push    ebx; Str
0x100b1e8f  call    ds:__imp__wcsrchr
0x100b1e95  pop     ecx
0x100b1e96  pop     ecx
0x100b1e97  test    eax, eax
0x100b1e99  jnz     short loc_100B1EA9
0x100b1e9b  mov     eax, ebx
0x100b1e9d  jmp     short loc_100B1EAC
0x100b1e9f  push    22h ; '"'
0x100b1ea1  pop     edx
0x100b1ea2  cmp     cx, dx
0x100b1ea5  jnz     short loc_100B1E79
0x100b1ea7  jmp     short loc_100B1E57
0x100b1ea9  add     eax, 2
0x100b1eac  push    2Eh ; '.'; Ch
0x100b1eae  push    eax; Str
0x100b1eaf  call    ds:__imp__wcschr
0x100b1eb5  pop     ecx
0x100b1eb6  pop     ecx
0x100b1eb7  mov     ecx, eax
0x100b1eb9  xor     eax, eax
0x100b1ebb  test    ecx, ecx
0x100b1ebd  push    18h
0x100b1ebf  setz    al
0x100b1ec2  test    ecx, ecx
0x100b1ec4  mov     [ebp+Str], eax
0x100b1ec7  pop     eax
0x100b1ec8  push    14h
0x100b1eca  pop     edx
0x100b1ecb  cmovnz  eax, edx
0x100b1ece  add     eax, esi
0x100b1ed0  cmp     eax, [ebp+var_4]
0x100b1ed3  ja      loc_100B1FE3
0x100b1ed9  mov     ecx, ebx
0x100b1edb  xor     esi, esi
0x100b1edd  lea     edx, [ecx+2]
0x100b1ee0  mov     ax, [ecx]
0x100b1ee3  add     ecx, 2
0x100b1ee6  cmp     ax, si
0x100b1ee9  jnz     short loc_100B1EE0
0x100b1eeb  sub     ecx, edx
0x100b1eed  sar     ecx, 1
0x100b1eef  lea     eax, ds:2[ecx*2]
0x100b1ef6  push    eax; Size
0x100b1ef7  lea     eax, [ebx+26h]
0x100b1efa  push    ebx; Src
0x100b1efb  push    eax; void *
0x100b1efc  call    _memmove
0x100b1f01  mov     esi, offset _wszAccess; "MS Access"
0x100b1f06  mov     ecx, [ebp+var_4]
0x100b1f09  mov     edi, ebx
0x100b1f0b  add     esp, 0Ch
0x100b1f0e  movsd
0x100b1f0f  push    3Bh ; ';'
0x100b1f11  pop     eax
0x100b1f12  movsd
0x100b1f13  movsd
0x100b1f14  movsd
0x100b1f15  movsw
0x100b1f17  mov     [ebx+12h], ax
0x100b1f1b  lea     edi, [ebx+14h]
0x100b1f1e  mov     esi, offset _wszDbEq; "DATABASE="
0x100b1f23  movsd
0x100b1f24  movsd
0x100b1f25  movsd
0x100b1f26  movsd
0x100b1f27  movsw
0x100b1f29  xor     edi, edi
0x100b1f2b  cmp     [ebp+Str], 0
0x100b1f2f  jz      short loc_100B1F3E
0x100b1f31  push    ecx
0x100b1f32  mov     edx, offset _wszDefaultExt; ".mdb"
0x100b1f37  mov     ecx, ebx
0x100b1f39  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b1f3e  pop     esi
0x100b1f3f  mov     eax, edi
0x100b1f41  pop     edi
0x100b1f42  pop     ebx
0x100b1f43  leave
0x100b1f44  retn
0x100b1f45  push    3Bh ; ';'
0x100b1f47  pop     eax
0x100b1f48  cmp     [ebx], ax
0x100b1f4b  jz      short loc_100B1F83
0x100b1f4d  push    9
0x100b1f4f  mov     edx, offset _wszAccess; "MS Access"
0x100b1f54  mov     ecx, ebx
0x100b1f56  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100b1f5b  test    eax, eax
0x100b1f5d  jz      short loc_100B1F83
0x100b1f5f  push    7
0x100b1f61  mov     edx, offset aJet2X; "Jet 2.x"
0x100b1f66  mov     ecx, ebx
0x100b1f68  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100b1f6d  test    eax, eax
0x100b1f6f  jz      short loc_100B1F83
0x100b1f71  push    7
0x100b1f73  mov     edx, offset aJet3X; "Jet 3.x"
0x100b1f78  mov     ecx, ebx
0x100b1f7a  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100b1f7f  test    eax, eax
0x100b1f81  jnz     short loc_100B1F3E
0x100b1f83  lea     eax, [ebp+var_C]
0x100b1f86  mov     edx, offset _wszDbEq; "DATABASE="
0x100b1f8b  push    eax
0x100b1f8c  lea     eax, [ebp+Str]
0x100b1f8f  mov     ecx, ebx
0x100b1f91  push    eax
0x100b1f92  call    _FindConnStrItem@16; FindConnStrItem(x,x,x,x)
0x100b1f97  cmp     [ebp+var_C], edi
0x100b1f9a  jnz     short loc_100B1FA3
0x100b1f9c  mov     edi, 0FFFFF40Ch
0x100b1fa1  jmp     short loc_100B1F3E
0x100b1fa3  push    5Ch ; '\'; Ch
0x100b1fa5  push    [ebp+Str]; Str
0x100b1fa8  call    ds:__imp__wcsrchr
0x100b1fae  pop     ecx
0x100b1faf  pop     ecx
0x100b1fb0  test    eax, eax
0x100b1fb2  jnz     short loc_100B1FB9
0x100b1fb4  mov     eax, [ebp+Str]
0x100b1fb7  jmp     short loc_100B1FBC
0x100b1fb9  add     eax, 2
0x100b1fbc  push    2Eh ; '.'; Ch
0x100b1fbe  push    eax; Str
0x100b1fbf  call    ds:__imp__wcsrchr
0x100b1fc5  neg     eax
0x100b1fc7  pop     ecx
0x100b1fc8  sbb     eax, eax
0x100b1fca  inc     eax
0x100b1fcb  mov     [ebp+Str], eax
0x100b1fce  pop     ecx
0x100b1fcf  mov     ecx, [ebp+var_4]
0x100b1fd2  lea     eax, ds:1[eax*4]
0x100b1fd9  add     eax, esi
0x100b1fdb  cmp     eax, ecx
0x100b1fdd  jbe     loc_100B1F2B
0x100b1fe3  mov     edi, 0FFFFF412h
0x100b1fe8  jmp     loc_100B1F3E
```
