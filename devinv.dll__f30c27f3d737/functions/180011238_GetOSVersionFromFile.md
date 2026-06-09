# GetOSVersionFromFile

- ea: `0x180011238`
- end: `0x180011420`
- name: `GetOSVersionFromFile`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800139e0`

## callees

- `0x180005e40`
- `0x18000dbc8`
- `0x180011238`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011341`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011341`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011324`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011324`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001129c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800112e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001129c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800112e1`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001138b`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001138b`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180011366`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180011366`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180011313`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180011313`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800112cf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800112cf`

## string_xrefs

- `0x1800112af`: `\kernel32.dll`
- `0x1800112f1`: `\ntdll.dll`

## pseudocode

```c
__int64 __fastcall GetOSVersionFromFile(_DWORD *a1, _DWORD *a2, unsigned int *a3, _DWORD *a4, unsigned int *a5)
{
  unsigned __int64 v8; // rdx
  int v9; // ebx
  unsigned __int64 v10; // rdx
  DWORD FileVersionInfoSizeW; // r14d
  HANDLE ProcessHeap; // rax
  void *v13; // rsi
  void *v14; // rax
  void *v15; // rdi
  unsigned __int16 *v16; // rcx
  _DWORD *v17; // rdx
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int puLen; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpBuffer; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD *v23; // [rsp+30h] [rbp-D0h]
  unsigned int *v24; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v23 = a2;
  v24 = a5;
  lpBuffer = 0;
  puLen = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
    return (unsigned int)-2147418113;
  v9 = StringCchCatW(Buffer, v8, L"\\kernel32.dll");
  if ( v9 < 0 )
    return (unsigned int)v9;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
      return (unsigned int)-2147418113;
    v9 = StringCchCatW(Buffer, v10, L"\\ntdll.dll");
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(Buffer, 0);
  if ( !FileVersionInfoSizeW )
    return (unsigned int)-2147418113;
  ProcessHeap = GetProcessHeap();
  v13 = ProcessHeap;
  if ( !ProcessHeap )
    return (unsigned int)-2147418113;
  v14 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSizeW);
  v15 = v14;
  if ( v14 )
  {
    if ( GetFileVersionInfoW(Buffer, 0, FileVersionInfoSizeW, v14) && VerQueryValueW(v15, L"\\", &lpBuffer, &puLen) )
    {
      v16 = (unsigned __int16 *)lpBuffer;
      v17 = v23;
      *a1 = *((unsigned __int16 *)lpBuffer + 5);
      *v17 = v16[4];
      v18 = v16[7];
      *v24 = v18;
      if ( v18 >= 0x23F0 )
        v19 = 0;
      else
        v19 = v18 % 0xA;
      *a3 = v19;
      *a4 = 0;
    }
    else
    {
      v9 = -2147418113;
    }
    HeapFree(v13, 0, v15);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011238  push    rbp
0x18001123a  push    rbx
0x18001123b  push    rsi
0x18001123c  push    rdi
0x18001123d  push    r12
0x18001123f  push    r13
0x180011241  push    r14
0x180011243  push    r15
0x180011245  lea     rbp, [rsp-168h]
0x18001124d  sub     rsp, 268h
0x180011254  mov     rax, cs:__security_cookie
0x18001125b  xor     rax, rsp
0x18001125e  mov     [rbp+1A0h+var_50], rax
0x180011265  mov     rax, [rbp+1A0h+arg_20]
0x18001126c  mov     r13, rcx
0x18001126f  mov     [rsp+2A0h+var_270], rdx
0x180011274  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180011279  mov     edi, 104h
0x18001127e  mov     [rsp+2A0h+var_268], rax
0x180011283  mov     edx, edi; uSize
0x180011285  mov     [rsp+2A0h+lpBuffer], 0
0x18001128e  mov     r12, r9
0x180011291  mov     [rsp+2A0h+puLen], 0
0x180011299  mov     r15, r8
0x18001129c  call    cs:__imp_GetSystemDirectoryW
0x1800112a2  dec     eax
0x1800112a4  lea     esi, [rdi-2]
0x1800112a7  cmp     eax, esi
0x1800112a9  ja      loc_1800113F6
0x1800112af  lea     r8, aKernel32Dll; "\\kernel32.dll"
0x1800112b6  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x1800112bb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800112c0  mov     ebx, eax
0x1800112c2  test    eax, eax
0x1800112c4  js      loc_1800113FB
0x1800112ca  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x1800112cf  call    cs:__imp_GetFileAttributesW
0x1800112d5  cmp     eax, 0FFFFFFFFh
0x1800112d8  jnz     short loc_18001130C
0x1800112da  mov     edx, edi; uSize
0x1800112dc  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x1800112e1  call    cs:__imp_GetSystemDirectoryW
0x1800112e7  dec     eax
0x1800112e9  cmp     eax, esi
0x1800112eb  ja      loc_1800113F6
0x1800112f1  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x1800112f8  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x1800112fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011302  mov     ebx, eax
0x180011304  test    eax, eax
0x180011306  js      loc_1800113FB
0x18001130c  xor     edx, edx; lpdwHandle
0x18001130e  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x180011313  call    cs:__imp_GetFileVersionInfoSizeW
0x180011319  mov     r14d, eax
0x18001131c  test    eax, eax
0x18001131e  jz      loc_1800113F6
0x180011324  call    cs:__imp_GetProcessHeap
0x18001132a  mov     rsi, rax
0x18001132d  test    rax, rax
0x180011330  jz      loc_1800113F6
0x180011336  mov     r8d, r14d; dwBytes
0x180011339  mov     edx, 8; dwFlags
0x18001133e  mov     rcx, rax; hHeap
0x180011341  call    cs:__imp_HeapAlloc
0x180011347  mov     rdi, rax
0x18001134a  test    rax, rax
0x18001134d  jnz     short loc_180011359
0x18001134f  mov     ebx, 8007000Eh
0x180011354  jmp     loc_1800113FB
0x180011359  mov     r9, rdi; lpData
0x18001135c  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x180011361  mov     r8d, r14d; dwLen
0x180011364  xor     edx, edx; dwHandle
0x180011366  call    cs:__imp_GetFileVersionInfoW
0x18001136c  test    eax, eax
0x18001136e  jnz     short loc_180011377
0x180011370  mov     ebx, 8000FFFFh
0x180011375  jmp     short loc_1800113E6
0x180011377  lea     r9, [rsp+2A0h+puLen]; puLen
0x18001137c  mov     rcx, rdi; pBlock
0x18001137f  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x180011384  lea     rdx, SubBlock; "\\"
0x18001138b  call    cs:__imp_VerQueryValueW
0x180011391  test    eax, eax
0x180011393  jz      short loc_180011370
0x180011395  mov     rcx, [rsp+2A0h+lpBuffer]
0x18001139a  mov     rdx, [rsp+2A0h+var_270]
0x18001139f  movzx   eax, word ptr [rcx+0Ah]
0x1800113a3  mov     [r13+0], eax
0x1800113a7  movzx   eax, word ptr [rcx+8]
0x1800113ab  mov     [rdx], eax
0x1800113ad  movzx   r8d, word ptr [rcx+0Eh]
0x1800113b2  mov     rax, [rsp+2A0h+var_268]
0x1800113b7  mov     [rax], r8d
0x1800113ba  cmp     r8d, 23F0h
0x1800113c1  jnb     short loc_1800113D8
0x1800113c3  mov     eax, 0CCCCCCCDh
0x1800113c8  mul     r8d
0x1800113cb  shr     edx, 3
0x1800113ce  lea     eax, [rdx+rdx*4]
0x1800113d1  add     eax, eax
0x1800113d3  sub     r8d, eax
0x1800113d6  jmp     short loc_1800113DB
0x1800113d8  xor     r8d, r8d
0x1800113db  mov     [r15], r8d
0x1800113de  mov     dword ptr [r12], 0
0x1800113e6  mov     r8, rdi; lpMem
0x1800113e9  xor     edx, edx; dwFlags
0x1800113eb  mov     rcx, rsi; hHeap
0x1800113ee  call    cs:__imp_HeapFree
0x1800113f4  jmp     short loc_1800113FB
0x1800113f6  mov     ebx, 8000FFFFh
0x1800113fb  mov     eax, ebx
0x1800113fd  mov     rcx, [rbp+1A0h+var_50]
0x180011404  xor     rcx, rsp; StackCookie
0x180011407  call    __security_check_cookie
0x18001140c  add     rsp, 268h
0x180011413  pop     r15
0x180011415  pop     r14
0x180011417  pop     r13
0x180011419  pop     r12
0x18001141b  pop     rdi
0x18001141c  pop     rsi
0x18001141d  pop     rbx
0x18001141e  pop     rbp
0x18001141f  retn
```
