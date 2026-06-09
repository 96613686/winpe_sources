# PathCchCombineEx

- ea: `0x180093b44`
- end: `0x180093dbf`
- name: `PathCchCombineEx`
- size: `635`
- prototype: `HRESULT __stdcall(PWSTR pszPathOut, size_t cchPathOut, PCWSTR pszPathIn, PCWSTR pszMore, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180092b10`

## callees

- `0x18004a6ac`
- `0x180093084`
- `0x180093a8c`
- `0x180093b44`
- `0x180094028`
- `0x1800942d0`

## import_xrefs

- `msvcrt!iswalpha` at `0x180093c5a`
- `msvcrt!iswalpha` at `0x180093c5a`
- `KERNEL32!LocalAlloc` at `0x180093c0d`
- `KERNEL32!LocalAlloc` at `0x180093c0d`
- `KERNEL32!LocalFree` at `0x180093d86`
- `KERNEL32!LocalFree` at `0x180093d86`

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
  __int64 v9; // rdx
  unsigned __int64 v10; // r15
  int v11; // ebx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rsi
  const unsigned __int16 *v15; // r8
  PCWSTR v16; // r15
  unsigned __int64 v17; // rdx
  unsigned __int16 *v18; // rcx
  WCHAR *v19; // r11
  size_t pcchRemaining; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszEnd; // [rsp+28h] [rbp-D8h] BYREF
  _WORD v23[264]; // [rsp+30h] [rbp-D0h] BYREF

  if ( !pszPathOut )
    return -2147024809;
  v8 = 0;
  v9 = 0x8000;
  if ( pszPathIn )
  {
    v12 = -1;
    do
      ++v12;
    while ( pszPathIn[v12] );
    if ( v12 >= 0x8000 )
      goto LABEL_8;
    v10 = v12 + 1;
    v13 = 0;
    if ( !v12 )
      v10 = 0;
    if ( !pszMore )
    {
LABEL_17:
      v14 = v13 + v10;
      if ( v13 + v10 <= 0x104 )
      {
        v23[0] = 0;
        v8 = v23;
        v14 = 260;
      }
      else
      {
        v8 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v14);
        if ( !v8 )
        {
          v11 = -2147024882;
          goto LABEL_41;
        }
      }
      if ( v10 )
      {
        if ( !v13 )
        {
          v15 = pszPathIn;
LABEL_39:
          v18 = v8;
          v17 = v14;
          goto LABEL_40;
        }
        if ( *pszMore == 92 )
        {
          v16 = pszMore + 1;
        }
        else if ( !iswalpha(*pszMore) || (v16 = pszMore + 1, pszMore[1] != 58) )
        {
          v11 = StringCchCopyW(v8, v14, pszPathIn);
          if ( v11 < 0 )
            goto LABEL_41;
          pcchRemaining = (size_t)v19;
          ppszEnd = v19;
          v11 = PathCchAddBackslashEx(v8, v14, (PWSTR *)&pcchRemaining, (size_t *)&ppszEnd);
          if ( v11 < 0 )
            goto LABEL_41;
          v17 = (unsigned __int64)ppszEnd;
          v15 = pszMore;
          v18 = (unsigned __int16 *)pcchRemaining;
          goto LABEL_40;
        }
        if ( *pszMore == 92 && *v16 != 92 )
        {
          v11 = StringCchCopyW(v8, v14, pszPathIn);
          if ( v11 < 0 )
            goto LABEL_41;
          v11 = PathCchStripToRoot(v8, v14);
          if ( v11 < 0 )
            goto LABEL_41;
          ppszEnd = 0;
          pcchRemaining = 0;
          v11 = PathCchAddBackslashEx(v8, v14, &ppszEnd, &pcchRemaining);
          if ( v11 < 0 )
            goto LABEL_41;
          v17 = pcchRemaining;
          v15 = v16;
          v18 = ppszEnd;
LABEL_40:
          v11 = StringCchCopyW(v18, v17, v15);
          if ( v11 < 0 )
            goto LABEL_41;
LABEL_42:
          v11 = PathCchCanonicalizeEx(pszPathOut, v9, v8, (enum PATHCCH_OPTIONS)pszMore);
          goto LABEL_43;
        }
      }
      else if ( !v13 )
      {
        goto LABEL_42;
      }
      v15 = pszMore;
      goto LABEL_39;
    }
LABEL_12:
    v13 = -1;
    do
      ++v13;
    while ( pszMore[v13] );
    if ( v13 < 0x8000 )
    {
      if ( v13 )
        ++v13;
      goto LABEL_17;
    }
LABEL_8:
    v11 = -2147024690;
    goto LABEL_41;
  }
  v10 = 0;
  if ( pszMore )
    goto LABEL_12;
  v11 = -2147024809;
LABEL_41:
  StringCchCopyW(pszPathOut, 0x104u, &String);
LABEL_43:
  if ( v8 != v23 )
    LocalFree(v8);
  return v11;
}

```

## disassembly

```asm
0x180093b44  mov     [rsp-8+arg_8], rbx
0x180093b49  push    rbp
0x180093b4a  push    rsi
0x180093b4b  push    rdi
0x180093b4c  push    r12
0x180093b4e  push    r13
0x180093b50  push    r14
0x180093b52  push    r15
0x180093b54  lea     rbp, [rsp-150h]
0x180093b5c  sub     rsp, 250h
0x180093b63  mov     rax, cs:__security_cookie
0x180093b6a  xor     rax, rsp
0x180093b6d  mov     [rbp+180h+var_40], rax
0x180093b74  xor     r11d, r11d
0x180093b77  mov     r14, r9
0x180093b7a  mov     r12, r8
0x180093b7d  mov     r13, rcx
0x180093b80  test    rcx, rcx
0x180093b83  jz      loc_180093D90
0x180093b89  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180093b8d  mov     edi, r11d
0x180093b90  mov     r8d, 104h
0x180093b96  mov     edx, 8000h; unsigned __int64
0x180093b9b  test    r12, r12
0x180093b9e  jnz     short loc_180093BB2
0x180093ba0  mov     r15d, r11d
0x180093ba3  test    r9, r9
0x180093ba6  jnz     short loc_180093BE1
0x180093ba8  mov     ebx, 80070057h
0x180093bad  jmp     loc_180093D56
0x180093bb2  mov     rax, rcx
0x180093bb5  inc     rax
0x180093bb8  cmp     [r12+rax*2], r11w
0x180093bbd  jnz     short loc_180093BB5
0x180093bbf  cmp     rax, rdx
0x180093bc2  jb      short loc_180093BCE
0x180093bc4  mov     ebx, 800700CEh
0x180093bc9  jmp     loc_180093D56
0x180093bce  test    rax, rax
0x180093bd1  lea     r15, [rax+1]
0x180093bd5  mov     rbx, r11
0x180093bd8  cmovz   r15, rax
0x180093bdc  test    r14, r14
0x180093bdf  jz      short loc_180093BFB
0x180093be1  mov     rbx, rcx
0x180093be4  inc     rbx
0x180093be7  cmp     [r9+rbx*2], r11w
0x180093bec  jnz     short loc_180093BE4
0x180093bee  cmp     rbx, rdx
0x180093bf1  jnb     short loc_180093BC4
0x180093bf3  test    rbx, rbx
0x180093bf6  jz      short loc_180093BFB
0x180093bf8  inc     rbx
0x180093bfb  lea     rsi, [rbx+r15]
0x180093bff  cmp     rsi, r8
0x180093c02  jbe     short loc_180093C25
0x180093c04  lea     rdx, [rsi+rsi]; uBytes
0x180093c08  mov     ecx, 40h ; '@'; uFlags
0x180093c0d  call    cs:__imp_LocalAlloc
0x180093c13  mov     rdi, rax
0x180093c16  test    rax, rax
0x180093c19  jnz     short loc_180093C33
0x180093c1b  mov     ebx, 8007000Eh
0x180093c20  jmp     loc_180093D56
0x180093c25  mov     [rsp+280h+var_250], r11w
0x180093c2b  lea     rdi, [rsp+280h+var_250]
0x180093c30  mov     rsi, r8
0x180093c33  test    r15, r15
0x180093c36  jz      loc_180093D3D
0x180093c3c  test    rbx, rbx
0x180093c3f  jnz     short loc_180093C49
0x180093c41  mov     r8, r12
0x180093c44  jmp     loc_180093D45
0x180093c49  cmp     word ptr [r14], 5Ch ; '\'
0x180093c4e  jnz     short loc_180093C56
0x180093c50  lea     r15, [r14+2]
0x180093c54  jmp     short loc_180093C76
0x180093c56  movzx   ecx, word ptr [r14]; C
0x180093c5a  call    cs:__imp_iswalpha
0x180093c60  xor     r11d, r11d
0x180093c63  test    eax, eax
0x180093c65  jz      loc_180093CF5
0x180093c6b  lea     r15, [r14+2]
0x180093c6f  cmp     word ptr [r15], 3Ah ; ':'
0x180093c74  jnz     short loc_180093CF5
0x180093c76  cmp     word ptr [r14], 5Ch ; '\'
0x180093c7b  jnz     loc_180093D42
0x180093c81  cmp     word ptr [r15], 5Ch ; '\'
0x180093c86  jz      loc_180093D42
0x180093c8c  mov     r8, r12; unsigned __int16 *
0x180093c8f  mov     rdx, rsi; unsigned __int64
0x180093c92  mov     rcx, rdi; unsigned __int16 *
0x180093c95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180093c9a  mov     ebx, eax
0x180093c9c  test    eax, eax
0x180093c9e  js      loc_180093D56
0x180093ca4  mov     rdx, rsi; cchPath
0x180093ca7  mov     rcx, rdi; pszPath
0x180093caa  call    PathCchStripToRoot
0x180093caf  mov     ebx, eax
0x180093cb1  test    eax, eax
0x180093cb3  js      loc_180093D56
0x180093cb9  lea     r9, [rsp+280h+pcchRemaining]; pcchRemaining
0x180093cbe  mov     [rsp+280h+ppszEnd], 0
0x180093cc7  lea     r8, [rsp+280h+ppszEnd]; ppszEnd
0x180093ccc  mov     [rsp+280h+pcchRemaining], 0
0x180093cd5  mov     rdx, rsi; cchPath
0x180093cd8  mov     rcx, rdi; pszPath
0x180093cdb  call    PathCchAddBackslashEx
0x180093ce0  mov     ebx, eax
0x180093ce2  test    eax, eax
0x180093ce4  js      short loc_180093D56
0x180093ce6  mov     rdx, [rsp+280h+pcchRemaining]
0x180093ceb  mov     r8, r15
0x180093cee  mov     rcx, [rsp+280h+ppszEnd]
0x180093cf3  jmp     short loc_180093D4B
0x180093cf5  mov     r8, r12; unsigned __int16 *
0x180093cf8  mov     rdx, rsi; unsigned __int64
0x180093cfb  mov     rcx, rdi; unsigned __int16 *
0x180093cfe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180093d03  mov     ebx, eax
0x180093d05  test    eax, eax
0x180093d07  js      short loc_180093D56
0x180093d09  lea     r9, [rsp+280h+ppszEnd]; pcchRemaining
0x180093d0e  mov     [rsp+280h+pcchRemaining], r11
0x180093d13  lea     r8, [rsp+280h+pcchRemaining]; ppszEnd
0x180093d18  mov     [rsp+280h+ppszEnd], r11
0x180093d1d  mov     rdx, rsi; cchPath
0x180093d20  mov     rcx, rdi; pszPath
0x180093d23  call    PathCchAddBackslashEx
0x180093d28  mov     ebx, eax
0x180093d2a  test    eax, eax
0x180093d2c  js      short loc_180093D56
0x180093d2e  mov     rdx, [rsp+280h+ppszEnd]
0x180093d33  mov     r8, r14
0x180093d36  mov     rcx, [rsp+280h+pcchRemaining]
0x180093d3b  jmp     short loc_180093D4B
0x180093d3d  test    rbx, rbx
0x180093d40  jz      short loc_180093D6C
0x180093d42  mov     r8, r14; unsigned __int16 *
0x180093d45  mov     rcx, rdi; unsigned __int16 *
0x180093d48  mov     rdx, rsi; unsigned __int64
0x180093d4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180093d50  mov     ebx, eax
0x180093d52  test    eax, eax
0x180093d54  jns     short loc_180093D6C
0x180093d56  lea     r8, String; unsigned __int16 *
0x180093d5d  mov     edx, 104h; unsigned __int64
0x180093d62  mov     rcx, r13; unsigned __int16 *
0x180093d65  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180093d6a  jmp     short loc_180093D79
0x180093d6c  mov     r8, rdi; unsigned __int16 *
0x180093d6f  mov     rcx, r13; unsigned __int16 *
0x180093d72  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x180093d77  mov     ebx, eax
0x180093d79  lea     rax, [rsp+280h+var_250]
0x180093d7e  cmp     rdi, rax
0x180093d81  jz      short loc_180093D8C
0x180093d83  mov     rcx, rdi; hMem
0x180093d86  call    cs:__imp_LocalFree
0x180093d8c  mov     eax, ebx
0x180093d8e  jmp     short loc_180093D95
0x180093d90  mov     eax, 80070057h
0x180093d95  mov     rcx, [rbp+180h+var_40]
0x180093d9c  xor     rcx, rsp; StackCookie
0x180093d9f  call    __security_check_cookie
0x180093da4  mov     rbx, [rsp+280h+arg_8]
0x180093dac  add     rsp, 250h
0x180093db3  pop     r15
0x180093db5  pop     r14
0x180093db7  pop     r13
0x180093db9  pop     r12
0x180093dbb  pop     rdi
0x180093dbc  pop     rsi
0x180093dbd  pop     rbp
0x180093dbe  retn
```
