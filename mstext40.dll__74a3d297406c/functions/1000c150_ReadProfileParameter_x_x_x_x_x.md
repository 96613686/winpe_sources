# ReadProfileParameter(x,x,x,x,x)

- ea: `0x1000c150`
- end: `0x1000c2e4`
- name: `_ReadProfileParameter@20`
- size: `404`
- prototype: `int __stdcall(LPCWCH, LPCWCH lpWideCharStr, LPCWCH, LPWSTR, DWORD nSize)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x10019860`
- `0x10019ce0`
- `0x10019f20`

## callees

- `0x1000b070`
- `0x1000b200`
- `0x1000c150`

## import_xrefs

- `KERNEL32!GetPrivateProfileStringA` at `0x1000c291`
- `KERNEL32!GetPrivateProfileStringA` at `0x1000c291`
- `KERNEL32!WideCharToMultiByte` at `0x1000c1a1`
- `KERNEL32!WideCharToMultiByte` at `0x1000c1e4`
- `KERNEL32!WideCharToMultiByte` at `0x1000c27a`
- `KERNEL32!WideCharToMultiByte` at `0x1000c1a1`
- `KERNEL32!WideCharToMultiByte` at `0x1000c1e4`
- `KERNEL32!WideCharToMultiByte` at `0x1000c27a`
- `KERNEL32!MultiByteToWideChar` at `0x1000c2c0`
- `KERNEL32!MultiByteToWideChar` at `0x1000c2c0`

## pseudocode

```c
int __stdcall ReadProfileParameter(LPCWCH a1, LPCWCH lpWideCharStr, LPCWCH a3, LPWSTR a4, DWORD nSize)
{
  unsigned int v5; // esi
  CHAR *v6; // eax
  const CHAR *v7; // edi
  unsigned int v8; // esi
  CHAR *v9; // eax
  const CHAR *v10; // ebx
  CHAR *v11; // ebp
  unsigned int v13; // esi
  CHAR *v14; // eax
  const CHAR *v15; // esi
  CHAR Default; // [esp+13h] [ebp-1h] BYREF
  const CHAR *v17; // [esp+20h] [ebp+Ch]
  LPCWCH PrivateProfileStringA; // [esp+20h] [ebp+Ch]

  *a4 = 0;
  Default = 0;
  v5 = wcslen(lpWideCharStr);
  v6 = (CHAR *)MemAllocate(2 * v5 + 1);
  v7 = v6;
  if ( !v6 )
    return -1;
  WideCharToMultiByte(0, 0, lpWideCharStr, v5 + 1, v6, 2 * v5 + 1, 0, 0);
  v8 = wcslen(a3);
  v9 = (CHAR *)MemAllocate(2 * v8 + 1);
  v10 = v9;
  if ( !v9 )
  {
LABEL_5:
    MemFree(v7);
    return -1;
  }
  WideCharToMultiByte(0, 0, a3, v8 + 1, v9, 2 * v8 + 1, 0, 0);
  v11 = (CHAR *)MemAllocate(nSize + 1);
  if ( !v11 )
  {
    MemFree(v10);
    goto LABEL_5;
  }
  v13 = wcslen(a1);
  v14 = (CHAR *)MemAllocate(2 * v13 + 1);
  v17 = v14;
  if ( v14 )
  {
    WideCharToMultiByte(0, 0, a1, v13 + 1, v14, 2 * v13 + 1, 0, 0);
    v15 = v17;
    PrivateProfileStringA = (LPCWCH)GetPrivateProfileStringA(v7, v10, &Default, v11, nSize, v17);
    MemFree(v15);
    MultiByteToWideChar(0, 0, v11, strlen(v11) + 1, a4, nSize + 1);
    MemFree(v11);
    MemFree(v10);
    MemFree(v7);
    return (int)PrivateProfileStringA;
  }
  else
  {
    MemFree(v10);
    MemFree(v7);
    MemFree(v11);
    return -1;
  }
}

```

## disassembly

```asm
0x1000c150  push    ecx
0x1000c151  mov     eax, [esp+4+arg_C]
0x1000c155  xor     ecx, ecx
0x1000c157  push    ebx
0x1000c158  push    ebp
0x1000c159  mov     ebp, [esp+0Ch+lpWideCharStr]
0x1000c15d  push    esi
0x1000c15e  mov     esi, ebp
0x1000c160  mov     [eax], cx
0x1000c163  push    edi
0x1000c164  mov     [esp+14h+Default], 0
0x1000c169  lea     ecx, [esi+2]
0x1000c16c  lea     esp, [esp+0]
0x1000c170  mov     ax, [esi]
0x1000c173  add     esi, 2
0x1000c176  test    ax, ax
0x1000c179  jnz     short loc_1000C170
0x1000c17b  sub     esi, ecx
0x1000c17d  sar     esi, 1
0x1000c17f  lea     ebx, ds:1[esi*2]
0x1000c186  push    ebx; Size
0x1000c187  call    _MemAllocate@4; MemAllocate(x)
0x1000c18c  mov     edi, eax
0x1000c18e  test    edi, edi
0x1000c190  jz      short loc_1000C20B
0x1000c192  push    0; lpUsedDefaultChar
0x1000c194  push    0; lpDefaultChar
0x1000c196  push    ebx; cbMultiByte
0x1000c197  push    edi; lpMultiByteStr
0x1000c198  lea     eax, [esi+1]
0x1000c19b  push    eax; cchWideChar
0x1000c19c  push    ebp; lpWideCharStr
0x1000c19d  push    0; dwFlags
0x1000c19f  push    0; CodePage
0x1000c1a1  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c1a7  mov     esi, [esp+14h+arg_8]
0x1000c1ab  lea     ecx, [esi+2]
0x1000c1ae  mov     edi, edi
0x1000c1b0  mov     ax, [esi]
0x1000c1b3  add     esi, 2
0x1000c1b6  test    ax, ax
0x1000c1b9  jnz     short loc_1000C1B0
0x1000c1bb  sub     esi, ecx
0x1000c1bd  sar     esi, 1
0x1000c1bf  lea     ebp, ds:1[esi*2]
0x1000c1c6  push    ebp; Size
0x1000c1c7  call    _MemAllocate@4; MemAllocate(x)
0x1000c1cc  mov     ebx, eax
0x1000c1ce  test    ebx, ebx
0x1000c1d0  jz      short loc_1000C205
0x1000c1d2  push    0; lpUsedDefaultChar
0x1000c1d4  push    0; lpDefaultChar
0x1000c1d6  push    ebp; cbMultiByte
0x1000c1d7  push    ebx; lpMultiByteStr
0x1000c1d8  lea     eax, [esi+1]
0x1000c1db  push    eax; cchWideChar
0x1000c1dc  push    [esp+28h+arg_8]; lpWideCharStr
0x1000c1e0  push    0; dwFlags
0x1000c1e2  push    0; CodePage
0x1000c1e4  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c1ea  mov     eax, [esp+14h+nSize]
0x1000c1ee  inc     eax
0x1000c1ef  push    eax; Size
0x1000c1f0  mov     [esp+18h+lpWideCharStr], eax
0x1000c1f4  call    _MemAllocate@4; MemAllocate(x)
0x1000c1f9  mov     ebp, eax
0x1000c1fb  test    ebp, ebp
0x1000c1fd  jnz     short loc_1000C216
0x1000c1ff  push    ebx
0x1000c200  call    _MemFree@4; MemFree(x)
0x1000c205  push    edi
0x1000c206  call    _MemFree@4; MemFree(x)
0x1000c20b  pop     edi
0x1000c20c  pop     esi
0x1000c20d  pop     ebp
0x1000c20e  or      eax, 0FFFFFFFFh
0x1000c211  pop     ebx
0x1000c212  pop     ecx
0x1000c213  retn    14h
0x1000c216  mov     esi, [esp+14h+arg_0]
0x1000c21a  lea     ecx, [esi+2]
0x1000c21d  lea     ecx, [ecx+0]
0x1000c220  mov     ax, [esi]
0x1000c223  add     esi, 2
0x1000c226  test    ax, ax
0x1000c229  jnz     short loc_1000C220
0x1000c22b  sub     esi, ecx
0x1000c22d  sar     esi, 1
0x1000c22f  lea     eax, ds:1[esi*2]
0x1000c236  push    eax; Size
0x1000c237  call    _MemAllocate@4; MemAllocate(x)
0x1000c23c  mov     [esp+14h+arg_8], eax
0x1000c240  test    eax, eax
0x1000c242  jnz     short loc_1000C261
0x1000c244  push    ebx
0x1000c245  call    _MemFree@4; MemFree(x)
0x1000c24a  push    edi
0x1000c24b  call    _MemFree@4; MemFree(x)
0x1000c250  push    ebp
0x1000c251  call    _MemFree@4; MemFree(x)
0x1000c256  pop     edi
0x1000c257  pop     esi
0x1000c258  pop     ebp
0x1000c259  or      eax, 0FFFFFFFFh
0x1000c25c  pop     ebx
0x1000c25d  pop     ecx
0x1000c25e  retn    14h
0x1000c261  push    0; lpUsedDefaultChar
0x1000c263  push    0; lpDefaultChar
0x1000c265  lea     ecx, ds:1[esi*2]
0x1000c26c  push    ecx; cbMultiByte
0x1000c26d  push    eax; lpMultiByteStr
0x1000c26e  lea     eax, [esi+1]
0x1000c271  push    eax; cchWideChar
0x1000c272  push    [esp+28h+arg_0]; lpWideCharStr
0x1000c276  push    0; dwFlags
0x1000c278  push    0; CodePage
0x1000c27a  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c280  mov     esi, [esp+14h+arg_8]
0x1000c284  lea     eax, [esp+14h+Default]
0x1000c288  push    esi; lpFileName
0x1000c289  push    [esp+18h+nSize]; nSize
0x1000c28d  push    ebp; lpReturnedString
0x1000c28e  push    eax; lpDefault
0x1000c28f  push    ebx; lpKeyName
0x1000c290  push    edi; lpAppName
0x1000c291  call    ds:__imp__GetPrivateProfileStringA@24; GetPrivateProfileStringA(x,x,x,x,x,x)
0x1000c297  push    esi
0x1000c298  mov     [esp+18h+arg_8], eax
0x1000c29c  call    _MemFree@4; MemFree(x)
0x1000c2a1  mov     ecx, ebp
0x1000c2a3  lea     edx, [ecx+1]
0x1000c2a6  mov     al, [ecx]
0x1000c2a8  inc     ecx
0x1000c2a9  test    al, al
0x1000c2ab  jnz     short loc_1000C2A6
0x1000c2ad  push    [esp+14h+lpWideCharStr]; cchWideChar
0x1000c2b1  sub     ecx, edx
0x1000c2b3  push    [esp+18h+arg_C]; lpWideCharStr
0x1000c2b7  lea     eax, [ecx+1]
0x1000c2ba  push    eax; cbMultiByte
0x1000c2bb  push    ebp; lpMultiByteStr
0x1000c2bc  push    0; dwFlags
0x1000c2be  push    0; CodePage
0x1000c2c0  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x1000c2c6  push    ebp
0x1000c2c7  call    _MemFree@4; MemFree(x)
0x1000c2cc  push    ebx
0x1000c2cd  call    _MemFree@4; MemFree(x)
0x1000c2d2  push    edi
0x1000c2d3  call    _MemFree@4; MemFree(x)
0x1000c2d8  mov     eax, [esp+14h+arg_8]
0x1000c2dc  pop     edi
0x1000c2dd  pop     esi
0x1000c2de  pop     ebp
0x1000c2df  pop     ebx
0x1000c2e0  pop     ecx
0x1000c2e1  retn    14h
```
