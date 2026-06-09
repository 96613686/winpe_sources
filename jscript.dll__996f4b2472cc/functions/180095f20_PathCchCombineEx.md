# PathCchCombineEx

- ea: `0x180095f20`
- end: `0x1800961ae`
- name: `PathCchCombineEx`
- size: `654`
- prototype: `HRESULT __stdcall(PWSTR pszPathOut, size_t cchPathOut, PCWSTR pszPathIn, PCWSTR pszMore, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180094e60`

## callees

- `0x18004b43c`
- `0x180095444`
- `0x180095e68`
- `0x180095f20`
- `0x180096430`
- `0x1800966e0`

## import_xrefs

- `msvcrt!iswalpha` at `0x18009603c`
- `msvcrt!iswalpha` at `0x18009603c`
- `KERNEL32!LocalAlloc` at `0x180095fe9`
- `KERNEL32!LocalAlloc` at `0x180095fe9`
- `KERNEL32!LocalFree` at `0x18009616e`
- `KERNEL32!LocalFree` at `0x18009616e`

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
0x180095f20  mov     [rsp-8+arg_8], rbx
0x180095f25  push    rbp
0x180095f26  push    rsi
0x180095f27  push    rdi
0x180095f28  push    r12
0x180095f2a  push    r13
0x180095f2c  push    r14
0x180095f2e  push    r15
0x180095f30  lea     rbp, [rsp-150h]
0x180095f38  sub     rsp, 250h
0x180095f3f  mov     rax, cs:__security_cookie
0x180095f46  xor     rax, rsp
0x180095f49  mov     [rbp+180h+var_40], rax
0x180095f50  xor     r11d, r11d
0x180095f53  mov     r14, r9
0x180095f56  mov     r12, r8
0x180095f59  mov     r13, rcx
0x180095f5c  test    rcx, rcx
0x180095f5f  jz      loc_18009617E
0x180095f65  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180095f69  mov     edi, r11d
0x180095f6c  mov     r8d, 104h
0x180095f72  mov     edx, 8000h; unsigned __int64
0x180095f77  test    r12, r12
0x180095f7a  jnz     short loc_180095F8E
0x180095f7c  mov     r15d, r11d
0x180095f7f  test    r9, r9
0x180095f82  jnz     short loc_180095FBD
0x180095f84  mov     ebx, 80070057h
0x180095f89  jmp     loc_18009613E
0x180095f8e  mov     rax, rcx
0x180095f91  inc     rax
0x180095f94  cmp     [r12+rax*2], r11w
0x180095f99  jnz     short loc_180095F91
0x180095f9b  cmp     rax, rdx
0x180095f9e  jb      short loc_180095FAA
0x180095fa0  mov     ebx, 800700CEh
0x180095fa5  jmp     loc_18009613E
0x180095faa  test    rax, rax
0x180095fad  lea     r15, [rax+1]
0x180095fb1  mov     rbx, r11
0x180095fb4  cmovz   r15, rax
0x180095fb8  test    r14, r14
0x180095fbb  jz      short loc_180095FD7
0x180095fbd  mov     rbx, rcx
0x180095fc0  inc     rbx
0x180095fc3  cmp     [r9+rbx*2], r11w
0x180095fc8  jnz     short loc_180095FC0
0x180095fca  cmp     rbx, rdx
0x180095fcd  jnb     short loc_180095FA0
0x180095fcf  test    rbx, rbx
0x180095fd2  jz      short loc_180095FD7
0x180095fd4  inc     rbx
0x180095fd7  lea     rsi, [rbx+r15]
0x180095fdb  cmp     rsi, r8
0x180095fde  jbe     short loc_180096007
0x180095fe0  lea     rdx, [rsi+rsi]; uBytes
0x180095fe4  mov     ecx, 40h ; '@'; uFlags
0x180095fe9  call    cs:__imp_LocalAlloc
0x180095ff0  nop     dword ptr [rax+rax+00h]
0x180095ff5  mov     rdi, rax
0x180095ff8  test    rax, rax
0x180095ffb  jnz     short loc_180096015
0x180095ffd  mov     ebx, 8007000Eh
0x180096002  jmp     loc_18009613E
0x180096007  mov     [rsp+280h+var_250], r11w
0x18009600d  lea     rdi, [rsp+280h+var_250]
0x180096012  mov     rsi, r8
0x180096015  test    r15, r15
0x180096018  jz      loc_180096125
0x18009601e  test    rbx, rbx
0x180096021  jnz     short loc_18009602B
0x180096023  mov     r8, r12
0x180096026  jmp     loc_18009612D
0x18009602b  cmp     word ptr [r14], 5Ch ; '\'
0x180096030  jnz     short loc_180096038
0x180096032  lea     r15, [r14+2]
0x180096036  jmp     short loc_18009605E
0x180096038  movzx   ecx, word ptr [r14]; C
0x18009603c  call    cs:__imp_iswalpha
0x180096043  nop     dword ptr [rax+rax+00h]
0x180096048  xor     r11d, r11d
0x18009604b  test    eax, eax
0x18009604d  jz      loc_1800960DD
0x180096053  lea     r15, [r14+2]
0x180096057  cmp     word ptr [r15], 3Ah ; ':'
0x18009605c  jnz     short loc_1800960DD
0x18009605e  cmp     word ptr [r14], 5Ch ; '\'
0x180096063  jnz     loc_18009612A
0x180096069  cmp     word ptr [r15], 5Ch ; '\'
0x18009606e  jz      loc_18009612A
0x180096074  mov     r8, r12; unsigned __int16 *
0x180096077  mov     rdx, rsi; unsigned __int64
0x18009607a  mov     rcx, rdi; unsigned __int16 *
0x18009607d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180096082  mov     ebx, eax
0x180096084  test    eax, eax
0x180096086  js      loc_18009613E
0x18009608c  mov     rdx, rsi; cchPath
0x18009608f  mov     rcx, rdi; pszPath
0x180096092  call    PathCchStripToRoot
0x180096097  mov     ebx, eax
0x180096099  test    eax, eax
0x18009609b  js      loc_18009613E
0x1800960a1  lea     r9, [rsp+280h+pcchRemaining]; pcchRemaining
0x1800960a6  mov     [rsp+280h+ppszEnd], 0
0x1800960af  lea     r8, [rsp+280h+ppszEnd]; ppszEnd
0x1800960b4  mov     [rsp+280h+pcchRemaining], 0
0x1800960bd  mov     rdx, rsi; cchPath
0x1800960c0  mov     rcx, rdi; pszPath
0x1800960c3  call    PathCchAddBackslashEx
0x1800960c8  mov     ebx, eax
0x1800960ca  test    eax, eax
0x1800960cc  js      short loc_18009613E
0x1800960ce  mov     rdx, [rsp+280h+pcchRemaining]
0x1800960d3  mov     r8, r15
0x1800960d6  mov     rcx, [rsp+280h+ppszEnd]
0x1800960db  jmp     short loc_180096133
0x1800960dd  mov     r8, r12; unsigned __int16 *
0x1800960e0  mov     rdx, rsi; unsigned __int64
0x1800960e3  mov     rcx, rdi; unsigned __int16 *
0x1800960e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800960eb  mov     ebx, eax
0x1800960ed  test    eax, eax
0x1800960ef  js      short loc_18009613E
0x1800960f1  lea     r9, [rsp+280h+ppszEnd]; pcchRemaining
0x1800960f6  mov     [rsp+280h+pcchRemaining], r11
0x1800960fb  lea     r8, [rsp+280h+pcchRemaining]; ppszEnd
0x180096100  mov     [rsp+280h+ppszEnd], r11
0x180096105  mov     rdx, rsi; cchPath
0x180096108  mov     rcx, rdi; pszPath
0x18009610b  call    PathCchAddBackslashEx
0x180096110  mov     ebx, eax
0x180096112  test    eax, eax
0x180096114  js      short loc_18009613E
0x180096116  mov     rdx, [rsp+280h+ppszEnd]
0x18009611b  mov     r8, r14
0x18009611e  mov     rcx, [rsp+280h+pcchRemaining]
0x180096123  jmp     short loc_180096133
0x180096125  test    rbx, rbx
0x180096128  jz      short loc_180096154
0x18009612a  mov     r8, r14; unsigned __int16 *
0x18009612d  mov     rcx, rdi; unsigned __int16 *
0x180096130  mov     rdx, rsi; unsigned __int64
0x180096133  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180096138  mov     ebx, eax
0x18009613a  test    eax, eax
0x18009613c  jns     short loc_180096154
0x18009613e  lea     r8, String; unsigned __int16 *
0x180096145  mov     edx, 104h; unsigned __int64
0x18009614a  mov     rcx, r13; unsigned __int16 *
0x18009614d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180096152  jmp     short loc_180096161
0x180096154  mov     r8, rdi; unsigned __int16 *
0x180096157  mov     rcx, r13; unsigned __int16 *
0x18009615a  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x18009615f  mov     ebx, eax
0x180096161  lea     rax, [rsp+280h+var_250]
0x180096166  cmp     rdi, rax
0x180096169  jz      short loc_18009617A
0x18009616b  mov     rcx, rdi; hMem
0x18009616e  call    cs:__imp_LocalFree
0x180096175  nop     dword ptr [rax+rax+00h]
0x18009617a  mov     eax, ebx
0x18009617c  jmp     short loc_180096183
0x18009617e  mov     eax, 80070057h
0x180096183  mov     rcx, [rbp+180h+var_40]
0x18009618a  xor     rcx, rsp; StackCookie
0x18009618d  call    __security_check_cookie
0x180096192  mov     rbx, [rsp+280h+arg_8]
0x18009619a  add     rsp, 250h
0x1800961a1  pop     r15
0x1800961a3  pop     r14
0x1800961a5  pop     r13
0x1800961a7  pop     r12
0x1800961a9  pop     rdi
0x1800961aa  pop     rsi
0x1800961ab  pop     rbp
0x1800961ac  retn
```
