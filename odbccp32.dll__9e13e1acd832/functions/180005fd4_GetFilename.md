# GetFilename

- ea: `0x180005fd4`
- end: `0x18000617b`
- name: `GetFilename`
- size: `423`
- prototype: `__int64 __fastcall(wchar_t *String1, wchar_t *String2, STRSAFE_LPWSTR pszDest, __int64, STRSAFE_LPWSTR pszDesta)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180006184`
- `0x180007628`

## callees

- `0x180002940`
- `0x180002e14`
- `0x180004bac`
- `0x180005fd4`
- `0x1800074c4`

## import_xrefs

- `msvcrt!_wmakepath_s` at `0x1800060f3`
- `msvcrt!_wmakepath_s` at `0x180006125`
- `msvcrt!_wmakepath_s` at `0x1800060f3`
- `msvcrt!_wmakepath_s` at `0x180006125`
- `msvcrt!_wcsnicmp` at `0x180006018`
- `msvcrt!_wcsnicmp` at `0x180006018`
- `msvcrt!_wsplitpath_s` at `0x1800060b3`
- `msvcrt!_wsplitpath_s` at `0x1800060b3`
- `msvcrt!calloc` at `0x18000604a`
- `msvcrt!calloc` at `0x18000604a`

## pseudocode

```c
__int64 __fastcall GetFilename(
        wchar_t *String1,
        wchar_t *String2,
        STRSAFE_LPWSTR pszDest,
        __int64 a4,
        STRSAFE_LPWSTR pszDesta)
{
  __int64 v6; // rdi
  __int64 v9; // rbp
  __int64 v10; // rax
  wchar_t *v11; // rax
  wchar_t *v12; // rdi
  __int64 v13; // rcx
  const wchar_t *v14; // r13
  unsigned int v15; // esi
  const wchar_t *v16; // r15
  const wchar_t *v17; // r12
  _WORD *v18; // r11

  v6 = -1;
  do
    ++v6;
  while ( String2[v6] );
  while ( 1 )
  {
    if ( !*String1 )
    {
      v13 = 8;
      goto LABEL_22;
    }
    v9 = (int)v6;
    if ( !_wcsnicmp(String1, String2, (int)v6) && String1[(int)v6] == 61 )
      break;
    v10 = -1;
    do
      ++v10;
    while ( String1[v10] );
    String1 += v10 + 1;
  }
  v11 = (wchar_t *)calloc(0x80Eu, 1u);
  v12 = v11;
  if ( !v11 )
  {
    MemError();
    v13 = 21;
LABEL_22:
    PostInstError(v13);
    return 0;
  }
  v14 = v11 + 260;
  v15 = 0;
  v16 = v11 + 263;
  v17 = v11 + 519;
  _wsplitpath_s(&String1[v9 + 1], v11 + 260, 3u, v11 + 263, 0x100u, v11 + 519, 0x100u, v11 + 775, 0x100u);
  if ( *v14 || *v16 )
  {
    if ( pszDest )
    {
      _wmakepath_s(v12, 0x104u, v14, v16, 0, 0);
      StringCchCopyW(pszDest, 0x104u, v12);
    }
  }
  else if ( pszDest )
  {
    *pszDest = 0;
  }
  _wmakepath_s(v12, 0x104u, 0, 0, v17, v17 + 256);
  if ( pszDesta )
  {
    StringCchCopyW(pszDesta, 0x104u, v12);
    if ( *v18 )
      v15 = 1;
  }
  OFree(v12);
  return v15;
}

```

## disassembly

```asm
0x180005fd4  push    rbx
0x180005fd6  push    rbp
0x180005fd7  push    rsi
0x180005fd8  push    rdi
0x180005fd9  push    r12
0x180005fdb  push    r13
0x180005fdd  push    r14
0x180005fdf  push    r15
0x180005fe1  sub     rsp, 58h
0x180005fe5  or      r12, 0FFFFFFFFFFFFFFFFh
0x180005fe9  mov     r14, r8
0x180005fec  mov     rdi, r12
0x180005fef  xor     r15d, r15d
0x180005ff2  mov     rsi, rdx
0x180005ff5  mov     rbx, rcx
0x180005ff8  inc     rdi
0x180005ffb  cmp     [rdx+rdi*2], r15w
0x180006000  jnz     short loc_180005FF8
0x180006002  cmp     [rbx], r15w
0x180006006  jz      loc_18000615E
0x18000600c  movsxd  rbp, edi
0x18000600f  mov     rdx, rsi; String2
0x180006012  mov     r8, rbp; MaxCount
0x180006015  mov     rcx, rbx; String1
0x180006018  call    cs:__imp__wcsnicmp
0x18000601e  test    eax, eax
0x180006020  jnz     short loc_180006029
0x180006022  cmp     word ptr [rbx+rbp*2], 3Dh ; '='
0x180006027  jz      short loc_180006040
0x180006029  mov     rax, r12
0x18000602c  inc     rax
0x18000602f  cmp     [rbx+rax*2], r15w
0x180006034  jnz     short loc_18000602C
0x180006036  lea     rbx, [rbx+rax*2]
0x18000603a  add     rbx, 2
0x18000603e  jmp     short loc_180006002
0x180006040  mov     edx, 1; Size
0x180006045  mov     ecx, 80Eh; Count
0x18000604a  call    cs:__imp_calloc
0x180006050  mov     rdi, rax
0x180006053  test    rax, rax
0x180006056  jnz     short loc_180006065
0x180006058  call    MemError
0x18000605d  lea     ecx, [rdi+15h]
0x180006060  jmp     loc_180006163
0x180006065  lea     r13, [rax+208h]
0x18000606c  mov     edx, 100h
0x180006071  mov     [rsp+98h+ExtCount], rdx; ExtCount
0x180006076  mov     esi, r15d
0x180006079  lea     r15, [r13+6]
0x18000607d  inc     rbp
0x180006080  lea     r12, [r15+200h]
0x180006087  mov     r9, r15; Dir
0x18000608a  lea     rax, [r12+200h]
0x180006092  mov     r8d, 3; DriveCount
0x180006098  mov     [rsp+98h+Ext], rax; Ext
0x18000609d  mov     [rsp+98h+FilenameCount], rdx; FilenameCount
0x1800060a2  lea     rcx, [rbx+rbp*2]; FullPath
0x1800060a6  mov     [rsp+98h+Filename], r12; Filename
0x1800060ab  mov     [rsp+98h+DirCount], rdx; DirCount
0x1800060b0  mov     rdx, r13; Drive
0x1800060b3  call    cs:__imp__wsplitpath_s
0x1800060b9  xor     ebx, ebx
0x1800060bb  mov     ebp, 104h
0x1800060c0  cmp     [r13+0], bx
0x1800060c5  jnz     short loc_1800060D8
0x1800060c7  cmp     [r15], bx
0x1800060cb  jnz     short loc_1800060D8
0x1800060cd  test    r14, r14
0x1800060d0  jz      short loc_180006107
0x1800060d2  mov     [r14], bx
0x1800060d6  jmp     short loc_180006107
0x1800060d8  test    r14, r14
0x1800060db  jz      short loc_180006107
0x1800060dd  mov     [rsp+98h+Filename], rbx; Ext
0x1800060e2  mov     r9, r15; Dir
0x1800060e5  mov     r8, r13; Drive
0x1800060e8  mov     [rsp+98h+DirCount], rbx; Filename
0x1800060ed  mov     rdx, rbp; BufferCount
0x1800060f0  mov     rcx, rdi; Buffer
0x1800060f3  call    cs:__imp__wmakepath_s
0x1800060f9  mov     r8, rdi; pszSrc
0x1800060fc  mov     rdx, rbp; cchDest
0x1800060ff  mov     rcx, r14; pszDest
0x180006102  call    StringCchCopyW
0x180006107  lea     rax, [r12+200h]
0x18000610f  xor     r9d, r9d; Dir
0x180006112  mov     [rsp+98h+Filename], rax; Ext
0x180006117  xor     r8d, r8d; Drive
0x18000611a  mov     rdx, rbp; BufferCount
0x18000611d  mov     [rsp+98h+DirCount], r12; Filename
0x180006122  mov     rcx, rdi; Buffer
0x180006125  call    cs:__imp__wmakepath_s
0x18000612b  mov     r11, [rsp+98h+pszDest]
0x180006133  test    r11, r11
0x180006136  jz      short loc_180006152
0x180006138  mov     r8, rdi; pszSrc
0x18000613b  mov     rdx, rbp; cchDest
0x18000613e  mov     rcx, r11; pszDest
0x180006141  call    StringCchCopyW
0x180006146  cmp     [r11], bx
0x18000614a  mov     eax, 1
0x18000614f  cmovnz  esi, eax
0x180006152  mov     rcx, rdi
0x180006155  call    OFree
0x18000615a  mov     eax, esi
0x18000615c  jmp     short loc_18000616A
0x18000615e  mov     ecx, 8
0x180006163  call    PostInstError
0x180006168  xor     eax, eax
0x18000616a  add     rsp, 58h
0x18000616e  pop     r15
0x180006170  pop     r14
0x180006172  pop     r13
0x180006174  pop     r12
0x180006176  pop     rdi
0x180006177  pop     rsi
0x180006178  pop     rbp
0x180006179  pop     rbx
0x18000617a  retn
```
