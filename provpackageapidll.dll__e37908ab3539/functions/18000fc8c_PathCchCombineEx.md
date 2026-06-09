# PathCchCombineEx

- ea: `0x18000fc8c`
- end: `0x18000ff1c`
- name: `PathCchCombineEx`
- size: `656`
- prototype: `HRESULT __stdcall(PWSTR pszPathOut, size_t cchPathOut, PCWSTR pszPathIn, PCWSTR pszMore, ULONG dwFlags)`
- caller_count: `16`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800078e8`
- `0x180007f78`
- `0x18000d0c4`
- `0x18000d350`
- `0x18000d708`
- `0x18000da5c`
- `0x18000e948`
- `0x18000fc10`
- `0x180014c70`
- `0x180015930`
- `0x180016050`
- `0x180016710`
- `0x180016c50`
- `0x1800170d0`
- `0x180017608`
- `0x180017898`

## callees

- `0x180001510`
- `0x180005424`
- `0x18000f040`
- `0x18000fb58`
- `0x18000fc8c`
- `0x1800100a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000fdb3`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000fdb3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fd66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fd66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000feea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000feea`

## pseudocode

```c
HRESULT __stdcall PathCchCombineEx(
        PWSTR pszPathOut,
        size_t cchPathOut,
        PCWSTR pszPathIn,
        PCWSTR pszMore,
        ULONG dwFlags)
{
  unsigned __int16 *v8; // rdi
  unsigned __int64 v9; // r15
  HRESULT v10; // ebx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rsi
  unsigned __int16 *v14; // r8
  PCWSTR v15; // r15
  unsigned __int64 v16; // rdx
  unsigned __int16 *v17; // rcx
  WCHAR *v18; // r11
  size_t pcchRemaining; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszEnd; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v22; // [rsp+30h] [rbp-D0h]
  _WORD v23[264]; // [rsp+40h] [rbp-C0h] BYREF

  v22 = pszPathOut;
  if ( !pszPathOut || cchPathOut - 1 > 0x7FFF )
    return -2147024809;
  v8 = 0;
  if ( pszPathIn )
  {
    v11 = -1;
    do
      ++v11;
    while ( pszPathIn[v11] );
    if ( v11 >= 0x8000 )
      goto LABEL_9;
    v9 = v11 + 1;
    v12 = 0;
    if ( !v11 )
      v9 = 0;
    if ( !pszMore )
    {
LABEL_18:
      v13 = v12 + v9;
      if ( v12 + v9 <= 0x104 )
      {
        v23[0] = 0;
        v8 = v23;
        v13 = 260;
      }
      else
      {
        v8 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v13);
        if ( !v8 )
        {
          v10 = -2147024882;
          goto LABEL_42;
        }
      }
      if ( v9 )
      {
        if ( !v12 )
        {
          v14 = (unsigned __int16 *)pszPathIn;
LABEL_40:
          v17 = v8;
          v16 = v13;
          goto LABEL_41;
        }
        if ( *pszMore == 92 )
        {
          v15 = pszMore + 1;
        }
        else if ( !(unsigned int)_o_iswalpha(*pszMore) || (v15 = pszMore + 1, pszMore[1] != 58) )
        {
          v10 = StringCchCopyW(v8, v13, (unsigned __int16 *)pszPathIn);
          if ( v10 < 0 )
            goto LABEL_42;
          pcchRemaining = (size_t)v18;
          ppszEnd = v18;
          v10 = PathCchAddBackslashEx(v8, v13, (PWSTR *)&pcchRemaining, (size_t *)&ppszEnd);
          if ( v10 < 0 )
            goto LABEL_42;
          v16 = (unsigned __int64)ppszEnd;
          v14 = (unsigned __int16 *)pszMore;
          v17 = (unsigned __int16 *)pcchRemaining;
          goto LABEL_41;
        }
        if ( *pszMore == 92 && *v15 != 92 )
        {
          v10 = StringCchCopyW(v8, v13, (unsigned __int16 *)pszPathIn);
          if ( v10 < 0 )
            goto LABEL_42;
          v10 = PathCchStripToRoot(v8, v13);
          if ( v10 < 0 )
            goto LABEL_42;
          ppszEnd = 0;
          pcchRemaining = 0;
          v10 = PathCchAddBackslashEx(v8, v13, &ppszEnd, &pcchRemaining);
          if ( v10 < 0 )
            goto LABEL_42;
          v16 = pcchRemaining;
          v14 = (unsigned __int16 *)v15;
          v17 = ppszEnd;
LABEL_41:
          v10 = StringCchCopyW(v17, v16, v14);
          if ( v10 < 0 )
            goto LABEL_42;
LABEL_43:
          v10 = PathCchCanonicalizeEx(v22, cchPathOut, v8, PATHCCH_ALLOW_LONG_PATHS);
          goto LABEL_44;
        }
      }
      else if ( !v12 )
      {
        goto LABEL_43;
      }
      v14 = (unsigned __int16 *)pszMore;
      goto LABEL_40;
    }
LABEL_13:
    v12 = -1;
    do
      ++v12;
    while ( pszMore[v12] );
    if ( v12 < 0x8000 )
    {
      if ( v12 )
        ++v12;
      goto LABEL_18;
    }
LABEL_9:
    v10 = -2147024690;
    goto LABEL_42;
  }
  v9 = 0;
  if ( pszMore )
    goto LABEL_13;
  v10 = -2147024809;
LABEL_42:
  StringCchCopyW(v22, cchPathOut, (unsigned __int16 *)&dword_18001EDA4);
LABEL_44:
  if ( v8 != v23 )
    LocalFree(v8);
  return v10;
}

```

## disassembly

```asm
0x18000fc8c  push    rbp
0x18000fc8e  push    rbx
0x18000fc8f  push    rsi
0x18000fc90  push    rdi
0x18000fc91  push    r12
0x18000fc93  push    r13
0x18000fc95  push    r14
0x18000fc97  push    r15
0x18000fc99  lea     rbp, [rsp-168h]
0x18000fca1  sub     rsp, 268h
0x18000fca8  mov     rax, cs:__security_cookie
0x18000fcaf  xor     rax, rsp
0x18000fcb2  mov     [rbp+1A0h+var_50], rax
0x18000fcb9  xor     r11d, r11d
0x18000fcbc  mov     [rsp+2A0h+var_270], rcx
0x18000fcc1  mov     r14, r9
0x18000fcc4  mov     r12, r8
0x18000fcc7  mov     r13, rdx
0x18000fcca  test    rcx, rcx
0x18000fccd  jz      loc_18000FEF4
0x18000fcd3  lea     rax, [rdx-1]
0x18000fcd7  cmp     rax, 7FFFh
0x18000fcdd  ja      loc_18000FEF4
0x18000fce3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000fce7  mov     edi, r11d
0x18000fcea  mov     edx, 8000h
0x18000fcef  test    r8, r8
0x18000fcf2  jnz     short loc_18000FD06
0x18000fcf4  mov     r15d, r11d
0x18000fcf7  test    r9, r9
0x18000fcfa  jnz     short loc_18000FD35
0x18000fcfc  mov     ebx, 80070057h
0x18000fd01  jmp     loc_18000FEAF
0x18000fd06  mov     rax, rcx
0x18000fd09  inc     rax
0x18000fd0c  cmp     [r8+rax*2], r11w
0x18000fd11  jnz     short loc_18000FD09
0x18000fd13  cmp     rax, rdx
0x18000fd16  jb      short loc_18000FD22
0x18000fd18  mov     ebx, 800700CEh
0x18000fd1d  jmp     loc_18000FEAF
0x18000fd22  test    rax, rax
0x18000fd25  lea     r15, [rax+1]
0x18000fd29  mov     rbx, r11
0x18000fd2c  cmovz   r15, rax
0x18000fd30  test    r14, r14
0x18000fd33  jz      short loc_18000FD4F
0x18000fd35  mov     rbx, rcx
0x18000fd38  inc     rbx
0x18000fd3b  cmp     [r9+rbx*2], r11w
0x18000fd40  jnz     short loc_18000FD38
0x18000fd42  cmp     rbx, rdx
0x18000fd45  jnb     short loc_18000FD18
0x18000fd47  test    rbx, rbx
0x18000fd4a  jz      short loc_18000FD4F
0x18000fd4c  inc     rbx
0x18000fd4f  lea     rsi, [rbx+r15]
0x18000fd53  mov     ecx, 104h
0x18000fd58  cmp     rsi, rcx
0x18000fd5b  jbe     short loc_18000FD7E
0x18000fd5d  lea     rdx, [rsi+rsi]; uBytes
0x18000fd61  mov     ecx, 40h ; '@'; uFlags
0x18000fd66  call    cs:__imp_LocalAlloc
0x18000fd6c  mov     rdi, rax
0x18000fd6f  test    rax, rax
0x18000fd72  jnz     short loc_18000FD8C
0x18000fd74  mov     ebx, 8007000Eh
0x18000fd79  jmp     loc_18000FEAF
0x18000fd7e  mov     [rsp+2A0h+var_260], r11w
0x18000fd84  lea     rdi, [rsp+2A0h+var_260]
0x18000fd89  mov     rsi, rcx
0x18000fd8c  test    r15, r15
0x18000fd8f  jz      loc_18000FE96
0x18000fd95  test    rbx, rbx
0x18000fd98  jnz     short loc_18000FDA2
0x18000fd9a  mov     r8, r12
0x18000fd9d  jmp     loc_18000FE9E
0x18000fda2  cmp     word ptr [r14], 5Ch ; '\'
0x18000fda7  jnz     short loc_18000FDAF
0x18000fda9  lea     r15, [r14+2]
0x18000fdad  jmp     short loc_18000FDCF
0x18000fdaf  movzx   ecx, word ptr [r14]
0x18000fdb3  call    cs:__imp__o_iswalpha
0x18000fdb9  xor     r11d, r11d
0x18000fdbc  test    eax, eax
0x18000fdbe  jz      loc_18000FE4E
0x18000fdc4  lea     r15, [r14+2]
0x18000fdc8  cmp     word ptr [r15], 3Ah ; ':'
0x18000fdcd  jnz     short loc_18000FE4E
0x18000fdcf  cmp     word ptr [r14], 5Ch ; '\'
0x18000fdd4  jnz     loc_18000FE9B
0x18000fdda  cmp     word ptr [r15], 5Ch ; '\'
0x18000fddf  jz      loc_18000FE9B
0x18000fde5  mov     r8, r12; unsigned __int16 *
0x18000fde8  mov     rdx, rsi; unsigned __int64
0x18000fdeb  mov     rcx, rdi; unsigned __int16 *
0x18000fdee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fdf3  mov     ebx, eax
0x18000fdf5  test    eax, eax
0x18000fdf7  js      loc_18000FEAF
0x18000fdfd  mov     rdx, rsi; cchPath
0x18000fe00  mov     rcx, rdi; pszPath
0x18000fe03  call    PathCchStripToRoot
0x18000fe08  mov     ebx, eax
0x18000fe0a  test    eax, eax
0x18000fe0c  js      loc_18000FEAF
0x18000fe12  lea     r9, [rsp+2A0h+pcchRemaining]; pcchRemaining
0x18000fe17  mov     [rsp+2A0h+ppszEnd], 0
0x18000fe20  lea     r8, [rsp+2A0h+ppszEnd]; ppszEnd
0x18000fe25  mov     [rsp+2A0h+pcchRemaining], 0
0x18000fe2e  mov     rdx, rsi; cchPath
0x18000fe31  mov     rcx, rdi; pszPath
0x18000fe34  call    PathCchAddBackslashEx
0x18000fe39  mov     ebx, eax
0x18000fe3b  test    eax, eax
0x18000fe3d  js      short loc_18000FEAF
0x18000fe3f  mov     rdx, [rsp+2A0h+pcchRemaining]
0x18000fe44  mov     r8, r15
0x18000fe47  mov     rcx, [rsp+2A0h+ppszEnd]
0x18000fe4c  jmp     short loc_18000FEA4
0x18000fe4e  mov     r8, r12; unsigned __int16 *
0x18000fe51  mov     rdx, rsi; unsigned __int64
0x18000fe54  mov     rcx, rdi; unsigned __int16 *
0x18000fe57  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fe5c  mov     ebx, eax
0x18000fe5e  test    eax, eax
0x18000fe60  js      short loc_18000FEAF
0x18000fe62  lea     r9, [rsp+2A0h+ppszEnd]; pcchRemaining
0x18000fe67  mov     [rsp+2A0h+pcchRemaining], r11
0x18000fe6c  lea     r8, [rsp+2A0h+pcchRemaining]; ppszEnd
0x18000fe71  mov     [rsp+2A0h+ppszEnd], r11
0x18000fe76  mov     rdx, rsi; cchPath
0x18000fe79  mov     rcx, rdi; pszPath
0x18000fe7c  call    PathCchAddBackslashEx
0x18000fe81  mov     ebx, eax
0x18000fe83  test    eax, eax
0x18000fe85  js      short loc_18000FEAF
0x18000fe87  mov     rdx, [rsp+2A0h+ppszEnd]
0x18000fe8c  mov     r8, r14
0x18000fe8f  mov     rcx, [rsp+2A0h+pcchRemaining]
0x18000fe94  jmp     short loc_18000FEA4
0x18000fe96  test    rbx, rbx
0x18000fe99  jz      short loc_18000FEC5
0x18000fe9b  mov     r8, r14; unsigned __int16 *
0x18000fe9e  mov     rcx, rdi; unsigned __int16 *
0x18000fea1  mov     rdx, rsi; unsigned __int64
0x18000fea4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fea9  mov     ebx, eax
0x18000feab  test    eax, eax
0x18000fead  jns     short loc_18000FEC5
0x18000feaf  mov     rcx, [rsp+2A0h+var_270]; unsigned __int16 *
0x18000feb4  lea     r8, dword_18001EDA4; unsigned __int16 *
0x18000febb  mov     rdx, r13; unsigned __int64
0x18000febe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fec3  jmp     short loc_18000FEDD
0x18000fec5  mov     rcx, [rsp+2A0h+var_270]; unsigned __int16 *
0x18000feca  mov     r9d, 1; enum PATHCCH_OPTIONS
0x18000fed0  mov     r8, rdi; unsigned __int16 *
0x18000fed3  mov     rdx, r13; unsigned __int64
0x18000fed6  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x18000fedb  mov     ebx, eax
0x18000fedd  lea     rax, [rsp+2A0h+var_260]
0x18000fee2  cmp     rdi, rax
0x18000fee5  jz      short loc_18000FEF0
0x18000fee7  mov     rcx, rdi; hMem
0x18000feea  call    cs:__imp_LocalFree
0x18000fef0  mov     eax, ebx
0x18000fef2  jmp     short loc_18000FEF9
0x18000fef4  mov     eax, 80070057h
0x18000fef9  mov     rcx, [rbp+1A0h+var_50]
0x18000ff00  xor     rcx, rsp; StackCookie
0x18000ff03  call    __security_check_cookie
0x18000ff08  add     rsp, 268h
0x18000ff0f  pop     r15
0x18000ff11  pop     r14
0x18000ff13  pop     r13
0x18000ff15  pop     r12
0x18000ff17  pop     rdi
0x18000ff18  pop     rsi
0x18000ff19  pop     rbx
0x18000ff1a  pop     rbp
0x18000ff1b  retn
```
