# SetupLocalaizedMonthNames

- ea: `0x1001df30`
- end: `0x1001e172`
- name: `SetupLocalaizedMonthNames`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1001f0e0`

## callees

- `0x1000ae20`
- `0x1000b070`
- `0x1001df30`
- `0x1002b81a`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1001df4d`
- `KERNEL32!LoadLibraryW` at `0x1001df4d`
- `KERNEL32!GetProcAddress` at `0x1001df65`
- `KERNEL32!GetProcAddress` at `0x1001df65`
- `KERNEL32!FreeLibrary` at `0x1001e083`
- `KERNEL32!FreeLibrary` at `0x1001e091`
- `KERNEL32!FreeLibrary` at `0x1001e0b9`
- `KERNEL32!FreeLibrary` at `0x1001e083`
- `KERNEL32!FreeLibrary` at `0x1001e091`
- `KERNEL32!FreeLibrary` at `0x1001e0b9`

## string_xrefs

- `0x1001df48`: `MSJINT40.DLL`

## pseudocode

```c
int SetupLocalaizedMonthNames()
{
  HMODULE LibraryW; // eax
  FARPROC CchLszOfId2; // ecx
  int v2; // ebx
  int v3; // ebp
  unsigned int v4; // kr00_4
  wchar_t *v5; // eax
  size_t v6; // edi
  int v7; // ecx
  unsigned int v8; // kr04_4
  wchar_t *v9; // eax
  size_t v10; // edi
  int v11; // ecx
  int v13; // edi
  int j; // esi
  size_t v15; // ebx
  wchar_t *v16; // eax
  size_t v17; // ebx
  int v18; // ecx
  int v19; // eax
  size_t v20; // ebx
  wchar_t *v21; // eax
  size_t v22; // ebx
  int v23; // ecx
  HMODULE hLibModule; // [esp+18h] [ebp-90h]
  int i; // [esp+1Ch] [ebp-8Ch]
  int (__stdcall *v26)(); // [esp+20h] [ebp-88h]
  wchar_t pszSrc[64]; // [esp+24h] [ebp-84h] BYREF

  LibraryW = LoadLibraryW(L"MSJINT40.DLL");
  hLibModule = LibraryW;
  if ( LibraryW )
  {
    CchLszOfId2 = GetProcAddress(LibraryW, "CchLszOfId2");
    v26 = CchLszOfId2;
    if ( CchLszOfId2 )
    {
      v2 = 0;
      v3 = 10022;
      for ( i = 0; ; i += 2 )
      {
        ((void (__stdcall *)(int, wchar_t *, int))CchLszOfId2)(v3 + 12, pszSrc, 128);
        v4 = wcslen(pszSrc);
        if ( !v4 )
          break;
        v5 = (wchar_t *)MemAllocate(2 * v4 + 2);
        *(_DWORD *)((char *)&xmmword_10041B0C + v2) = v5;
        if ( !v5 )
          goto LABEL_14;
        v6 = (2 * v4 + 2) >> 1;
        StringCchCopyW(v5, v6, pszSrc);
        v7 = (__int16)v6 - 1;
        if ( (__int16)v4 < v7 )
          LOWORD(v7) = v4;
        *(_WORD *)((char *)&xmmword_10041B54 + i) = v7;
        ((void (__stdcall *)(int, wchar_t *, int))v26)(v3, pszSrc, 128);
        v8 = wcslen(pszSrc);
        if ( !v8 )
          break;
        v9 = (wchar_t *)MemAllocate(2 * v8 + 2);
        *(_DWORD *)((char *)&xmmword_10041ADC + v2) = v9;
        if ( !v9 )
        {
LABEL_14:
          FreeLibrary(hLibModule);
          return -1011;
        }
        v10 = (2 * v8 + 2) >> 1;
        StringCchCopyW(v9, v10, pszSrc);
        v11 = (__int16)v10 - 1;
        if ( (__int16)v8 < v11 )
          LOWORD(v11) = v8;
        ++v3;
        *(_WORD *)((char *)&xmmword_10041B3C + i) = v11;
        v2 += 4;
        CchLszOfId2 = v26;
        if ( v3 - 10022 >= 12 )
        {
          FreeLibrary(hLibModule);
          return 0;
        }
      }
    }
    FreeLibrary(hLibModule);
  }
  v13 = 0;
  for ( j = 0; ; ++j )
  {
    v15 = 2 * word_1003E7E8[j] + 2;
    v16 = (wchar_t *)MemAllocate(v15);
    *(_DWORD *)((char *)&xmmword_10041ADC + v13 * 4) = v16;
    if ( !v16 )
      break;
    v17 = v15 >> 1;
    StringCchCopyW(v16, v17, off_1003E788[v13]);
    v18 = (__int16)v17 - 1;
    if ( word_1003E7E8[j] < v18 )
      LOWORD(v18) = word_1003E7E8[j];
    v19 = word_1003E800[j];
    *(_WORD *)((char *)&xmmword_10041B3C + j * 2) = v18;
    v20 = 2 * v19 + 2;
    v21 = (wchar_t *)MemAllocate(v20);
    *(_DWORD *)((char *)&xmmword_10041B0C + v13 * 4) = v21;
    if ( !v21 )
      break;
    v22 = v20 >> 1;
    StringCchCopyW(v21, v22, off_1003E7B8[v13]);
    v23 = (__int16)v22 - 1;
    if ( word_1003E800[j] < v23 )
      LOWORD(v23) = word_1003E800[j];
    ++v13;
    *(_WORD *)((char *)&xmmword_10041B54 + j * 2) = v23;
    if ( v13 >= 12 )
      return 0;
  }
  return -1011;
}

```

## disassembly

```asm
0x1001df30  sub     esp, 90h
0x1001df36  mov     eax, ___security_cookie
0x1001df3b  xor     eax, esp
0x1001df3d  mov     [esp+90h+var_4], eax
0x1001df44  push    ebx
0x1001df45  push    ebp
0x1001df46  push    esi
0x1001df47  push    edi
0x1001df48  push    offset aMsjint40Dll; "MSJINT40.DLL"
0x1001df4d  call    ds:__imp__LoadLibraryW@4; LoadLibraryW(x)
0x1001df53  mov     [esp+0A0h+hLibModule], eax
0x1001df57  test    eax, eax
0x1001df59  jz      loc_1001E0BF
0x1001df5f  push    offset aCchlszofid2; "CchLszOfId2"
0x1001df64  push    eax; hModule
0x1001df65  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1001df6b  mov     ecx, eax
0x1001df6d  mov     [esp+0A0h+var_88], ecx
0x1001df71  test    ecx, ecx
0x1001df73  jz      loc_1001E0B5
0x1001df79  xor     ebx, ebx
0x1001df7b  mov     ebp, 2726h
0x1001df80  mov     [esp+0A0h+var_8C], ebx
0x1001df84  push    80h
0x1001df89  lea     eax, [esp+0A4h+pszSrc]
0x1001df8d  push    eax
0x1001df8e  lea     eax, [ebp+0Ch]
0x1001df91  push    eax
0x1001df92  call    ecx
0x1001df94  lea     esi, [esp+0A0h+pszSrc]
0x1001df98  lea     ecx, [esi+2]
0x1001df9b  jmp     short loc_1001DFA0
0x1001dfa0  mov     ax, [esi]
0x1001dfa3  add     esi, 2
0x1001dfa6  test    ax, ax
0x1001dfa9  jnz     short loc_1001DFA0
0x1001dfab  sub     esi, ecx
0x1001dfad  sar     esi, 1
0x1001dfaf  jz      loc_1001E0B5
0x1001dfb5  lea     edi, ds:2[esi*2]
0x1001dfbc  push    edi; Size
0x1001dfbd  call    _MemAllocate@4; MemAllocate(x)
0x1001dfc2  mov     dword ptr xmmword_10041B0C[ebx], eax
0x1001dfc8  test    eax, eax
0x1001dfca  jz      loc_1001E08D
0x1001dfd0  lea     ecx, [esp+0A0h+pszSrc]
0x1001dfd4  shr     edi, 1
0x1001dfd6  push    ecx; pszSrc
0x1001dfd7  push    edi; cchDest
0x1001dfd8  push    eax; pszDest
0x1001dfd9  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1001dfde  movsx   ecx, di
0x1001dfe1  dec     ecx
0x1001dfe2  movsx   eax, si
0x1001dfe5  cmp     eax, ecx
0x1001dfe7  push    80h
0x1001dfec  cmovl   ecx, eax
0x1001dfef  mov     eax, [esp+0A4h+var_8C]
0x1001dff3  mov     word ptr xmmword_10041B54[eax], cx
0x1001dffa  lea     eax, [esp+0A4h+pszSrc]
0x1001dffe  push    eax
0x1001dfff  push    ebp
0x1001e000  call    [esp+0ACh+var_88]
0x1001e004  lea     esi, [esp+0A0h+pszSrc]
0x1001e008  lea     ecx, [esi+2]
0x1001e00b  jmp     short loc_1001E010
0x1001e010  mov     ax, [esi]
0x1001e013  add     esi, 2
0x1001e016  test    ax, ax
0x1001e019  jnz     short loc_1001E010
0x1001e01b  sub     esi, ecx
0x1001e01d  sar     esi, 1
0x1001e01f  jz      loc_1001E0B5
0x1001e025  lea     edi, ds:2[esi*2]
0x1001e02c  push    edi; Size
0x1001e02d  call    _MemAllocate@4; MemAllocate(x)
0x1001e032  mov     dword ptr xmmword_10041ADC[ebx], eax
0x1001e038  test    eax, eax
0x1001e03a  jz      short loc_1001E08D
0x1001e03c  lea     ecx, [esp+0A0h+pszSrc]
0x1001e040  shr     edi, 1
0x1001e042  push    ecx; pszSrc
0x1001e043  push    edi; cchDest
0x1001e044  push    eax; pszDest
0x1001e045  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1001e04a  movsx   ecx, di
0x1001e04d  mov     edi, [esp+0A0h+var_8C]
0x1001e051  dec     ecx
0x1001e052  movsx   eax, si
0x1001e055  cmp     eax, ecx
0x1001e057  cmovl   ecx, eax
0x1001e05a  inc     ebp
0x1001e05b  mov     word ptr xmmword_10041B3C[edi], cx
0x1001e062  add     ebx, 4
0x1001e065  mov     ecx, [esp+0A0h+var_88]
0x1001e069  add     edi, 2
0x1001e06c  mov     [esp+0A0h+var_8C], edi
0x1001e070  lea     eax, [ebp-2726h]
0x1001e076  cmp     eax, 0Ch
0x1001e079  jl      loc_1001DF84
0x1001e07f  push    [esp+0A0h+hLibModule]; hLibModule
0x1001e083  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1001e089  xor     eax, eax
0x1001e08b  jmp     short loc_1001E09C
0x1001e08d  push    [esp+0A0h+hLibModule]; hLibModule
0x1001e091  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1001e097  mov     eax, 0FFFFFC0Dh
0x1001e09c  mov     ecx, [esp+0A0h+var_4]
0x1001e0a3  pop     edi
0x1001e0a4  pop     esi
0x1001e0a5  pop     ebp
0x1001e0a6  pop     ebx
0x1001e0a7  xor     ecx, esp; StackCookie
0x1001e0a9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001e0ae  add     esp, 90h
0x1001e0b4  retn
0x1001e0b5  push    [esp+0A0h+hLibModule]; hLibModule
0x1001e0b9  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1001e0bf  xor     edi, edi
0x1001e0c1  xor     esi, esi
0x1001e0c3  jmp     short loc_1001E0D0
0x1001e0d0  movsx   eax, word_1003E7E8[esi]
0x1001e0d7  lea     ebx, ds:2[eax*2]
0x1001e0de  push    ebx; Size
0x1001e0df  call    _MemAllocate@4; MemAllocate(x)
0x1001e0e4  mov     dword ptr xmmword_10041ADC[edi], eax
0x1001e0ea  test    eax, eax
0x1001e0ec  jz      short loc_1001E097
0x1001e0ee  push    off_1003E788[edi]; pszSrc
0x1001e0f4  shr     ebx, 1
0x1001e0f6  push    ebx; cchDest
0x1001e0f7  push    eax; pszDest
0x1001e0f8  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1001e0fd  movsx   eax, word_1003E7E8[esi]
0x1001e104  movsx   ecx, bx
0x1001e107  dec     ecx
0x1001e108  cmp     eax, ecx
0x1001e10a  cmovl   ecx, eax
0x1001e10d  movsx   eax, word_1003E800[esi]
0x1001e114  mov     word ptr xmmword_10041B3C[esi], cx
0x1001e11b  lea     ebx, ds:2[eax*2]
0x1001e122  push    ebx; Size
0x1001e123  call    _MemAllocate@4; MemAllocate(x)
0x1001e128  mov     dword ptr xmmword_10041B0C[edi], eax
0x1001e12e  test    eax, eax
0x1001e130  jz      loc_1001E097
0x1001e136  push    off_1003E7B8[edi]; pszSrc
0x1001e13c  shr     ebx, 1
0x1001e13e  push    ebx; cchDest
0x1001e13f  push    eax; pszDest
0x1001e140  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1001e145  movsx   eax, word_1003E800[esi]
0x1001e14c  movsx   ecx, bx
0x1001e14f  dec     ecx
0x1001e150  cmp     eax, ecx
0x1001e152  cmovl   ecx, eax
0x1001e155  add     edi, 4
0x1001e158  mov     word ptr xmmword_10041B54[esi], cx
0x1001e15f  add     esi, 2
0x1001e162  cmp     edi, 30h ; '0'
0x1001e165  jl      loc_1001E0D0
0x1001e16b  xor     eax, eax
0x1001e16d  jmp     loc_1001E09C
```
