# IsDirInAllowedList(char const *,char *)

- ea: `0x180068b60`
- end: `0x180068dbc`
- name: `?IsDirInAllowedList@@YAHPEBDPEAD@Z`
- size: `604`
- prototype: `__int64 __fastcall(LPCSTR lpszLongPath, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180068410`

## callees

- `0x180002a64`
- `0x18004f560`
- `0x180068b60`
- `0x180075c5a`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsA` at `0x180068cf2`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180068cf2`
- `KERNEL32!GetShortPathNameA` at `0x180068be3`
- `KERNEL32!GetShortPathNameA` at `0x180068d17`
- `KERNEL32!GetShortPathNameA` at `0x180068be3`
- `KERNEL32!GetShortPathNameA` at `0x180068d17`
- `KERNEL32!FreeLibrary` at `0x180068d88`
- `KERNEL32!FreeLibrary` at `0x180068d88`
- `KERNEL32!GetProcAddress` at `0x180068bb2`
- `KERNEL32!GetProcAddress` at `0x180068bb2`
- `USER32!CharPrevA` at `0x180068ccf`
- `USER32!CharPrevA` at `0x180068ccf`
- `SHLWAPI!StrCmpNIA` at `0x180068d68`
- `SHLWAPI!StrCmpNIA` at `0x180068d68`

## string_xrefs

- `0x180068b94`: `Kernel32.dll`
- `0x180068ba8`: `GetLongPathNameA`

## pseudocode

```c
DWORD __fastcall IsDirInAllowedList(LPCSTR lpszLongPath, char *a2)
{
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rbp
  HMODULE LibraryA; // rax
  DWORD result; // eax
  int v8; // r14d
  char v9; // al
  char v10; // al
  char *v11; // rdi
  __int64 v12; // rax
  CHAR *p_szStart; // rdx
  __int64 v14; // rcx
  CHAR *v15; // rax
  __int64 v16; // rax
  CHAR *v17; // rbx
  DWORD ShortPathNameA; // eax
  DWORD v19; // ecx
  __int64 v20; // r8
  __int64 v21; // rax
  CHAR Dst[272]; // [rsp+20h] [rbp-358h] BYREF
  CHAR szStart; // [rsp+130h] [rbp-248h] BYREF
  char v24[271]; // [rsp+131h] [rbp-247h] BYREF
  CHAR szShortPath[272]; // [rsp+240h] [rbp-138h] BYREF

  v4 = 0;
  ProcAddress = 0;
  if ( !(unsigned int)IsNT4OrLess() )
  {
    LibraryA = (HMODULE)IsolationAwareLoadLibraryA("Kernel32.dll");
    v4 = LibraryA;
    if ( LibraryA )
      ProcAddress = GetProcAddress(LibraryA, "GetLongPathNameA");
  }
  szShortPath[0] = 0;
  if ( ProcAddress )
    result = ((__int64 (__fastcall *)(LPCSTR, CHAR *, __int64))ProcAddress)(lpszLongPath, szShortPath, 260);
  else
    result = GetShortPathNameA(lpszLongPath, szShortPath, 0x104u);
  if ( result )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = *a2;
      if ( !*a2 )
        break;
      do
      {
        if ( v9 != 32 )
          break;
        v9 = *++a2;
      }
      while ( v9 );
      v10 = *a2;
      if ( !*a2 )
        break;
      v11 = a2;
      do
      {
        if ( v10 == 59 )
          break;
        v10 = *++v11;
      }
      while ( v10 );
      if ( *v11 )
        *v11++ = 0;
      szStart = 0;
      memset_0(v24, 0, 0x104u);
      v12 = 2147483646;
      p_szStart = &szStart;
      v14 = 260;
      do
      {
        if ( !v12 )
          break;
        if ( !*a2 )
          break;
        *p_szStart++ = *a2++;
        --v12;
        --v14;
      }
      while ( v14 );
      v15 = p_szStart - 1;
      if ( v14 )
        v15 = p_szStart;
      *v15 = 0;
      if ( !v14 )
        break;
      v16 = -1;
      do
        ++v16;
      while ( v24[v16 - 1] );
      v17 = &v24[v16 - 1];
      if ( *CharPrevA(&szStart, &v24[v16 - 1]) != 92 )
        *(_WORD *)v17 = 92;
      ExpandEnvironmentStringsA(&szStart, Dst, 0x104u);
      if ( ProcAddress )
        ShortPathNameA = ((__int64 (__fastcall *)(CHAR *, CHAR *, __int64))ProcAddress)(Dst, Dst, 260);
      else
        ShortPathNameA = GetShortPathNameA(Dst, Dst, 0x104u);
      v19 = ShortPathNameA + 1;
      v20 = -1;
      if ( !ShortPathNameA )
        v19 = 0;
      do
        ++v20;
      while ( Dst[v20] );
      if ( v19 )
      {
        v21 = -1;
        do
          ++v21;
        while ( szShortPath[v21] );
        if ( (int)v20 <= (int)v21 && !StrCmpNIA(Dst, szShortPath, v20) )
        {
          v8 = 1;
          break;
        }
      }
      a2 = v11;
    }
    if ( v4 )
      FreeLibrary(v4);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180068b60  mov     [rsp+arg_18], rbx
0x180068b65  push    rbp
0x180068b66  push    rsi
0x180068b67  push    rdi
0x180068b68  sub     rsp, 360h
0x180068b6f  mov     rax, cs:__security_cookie
0x180068b76  xor     rax, rsp
0x180068b79  mov     [rsp+378h+var_28], rax
0x180068b81  mov     rbx, rdx
0x180068b84  mov     rdi, rcx
0x180068b87  xor     esi, esi
0x180068b89  xor     ebp, ebp
0x180068b8b  call    ?IsNT4OrLess@@YAHXZ; IsNT4OrLess(void)
0x180068b90  test    eax, eax
0x180068b92  jnz     short loc_180068BBB
0x180068b94  lea     rcx, aKernel32Dll_1; "Kernel32.dll"
0x180068b9b  call    IsolationAwareLoadLibraryA
0x180068ba0  mov     rsi, rax
0x180068ba3  test    rax, rax
0x180068ba6  jz      short loc_180068BBB
0x180068ba8  lea     rdx, aGetlongpathnam; "GetLongPathNameA"
0x180068baf  mov     rcx, rax; hModule
0x180068bb2  call    cs:__imp_GetProcAddress
0x180068bb8  mov     rbp, rax
0x180068bbb  mov     [rsp+378h+szShortPath], 0
0x180068bc3  mov     r8d, 104h; cchBuffer
0x180068bc9  lea     rdx, [rsp+378h+szShortPath]; lpszShortPath
0x180068bd1  mov     rcx, rdi; lpszLongPath
0x180068bd4  test    rbp, rbp
0x180068bd7  jz      short loc_180068BE3
0x180068bd9  mov     rax, rbp
0x180068bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068be1  jmp     short loc_180068BE9
0x180068be3  call    cs:__imp_GetShortPathNameA
0x180068be9  test    eax, eax
0x180068beb  jz      loc_180068D99
0x180068bf1  mov     [rsp+378h+arg_10], r14
0x180068bf9  xor     r14d, r14d
0x180068bfc  movzx   eax, byte ptr [rbx]
0x180068bff  test    al, al
0x180068c01  jz      loc_180068D80
0x180068c07  cmp     al, 20h ; ' '
0x180068c09  jnz     short loc_180068C16
0x180068c0b  movzx   eax, byte ptr [rbx+1]
0x180068c0f  inc     rbx
0x180068c12  test    al, al
0x180068c14  jnz     short loc_180068C07
0x180068c16  movzx   eax, byte ptr [rbx]
0x180068c19  test    al, al
0x180068c1b  jz      loc_180068D80
0x180068c21  mov     rdi, rbx
0x180068c24  cmp     al, 3Bh ; ';'
0x180068c26  jz      short loc_180068C33
0x180068c28  movzx   eax, byte ptr [rdi+1]
0x180068c2c  inc     rdi
0x180068c2f  test    al, al
0x180068c31  jnz     short loc_180068C24
0x180068c33  cmp     [rdi], r14b
0x180068c36  jz      short loc_180068C3E
0x180068c38  mov     [rdi], r14b
0x180068c3b  inc     rdi
0x180068c3e  xor     edx, edx; Val
0x180068c40  mov     [rsp+378h+szStart], r14b
0x180068c48  mov     r8d, 104h; Size
0x180068c4e  lea     rcx, [rsp+378h+var_247]; void *
0x180068c56  call    memset_0
0x180068c5b  mov     eax, 7FFFFFFEh
0x180068c60  lea     rdx, [rsp+378h+szStart]
0x180068c68  mov     ecx, 104h
0x180068c6d  test    rax, rax
0x180068c70  jz      short loc_180068C8D
0x180068c72  movzx   r8d, byte ptr [rbx]
0x180068c76  test    r8b, r8b
0x180068c79  jz      short loc_180068C8D
0x180068c7b  mov     [rdx], r8b
0x180068c7e  inc     rbx
0x180068c81  inc     rdx
0x180068c84  dec     rax
0x180068c87  sub     rcx, 1
0x180068c8b  jnz     short loc_180068C6D
0x180068c8d  test    rcx, rcx
0x180068c90  lea     rax, [rdx-1]
0x180068c94  cmovnz  rax, rdx
0x180068c98  mov     [rax], r14b
0x180068c9b  jz      loc_180068D80
0x180068ca1  lea     rcx, [rsp+378h+szStart]
0x180068ca9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180068cb0  inc     rax
0x180068cb3  cmp     [rcx+rax], r14b
0x180068cb7  jnz     short loc_180068CB0
0x180068cb9  lea     rbx, [rsp+378h+szStart]
0x180068cc1  add     rbx, rax
0x180068cc4  lea     rcx, [rsp+378h+szStart]; lpszStart
0x180068ccc  mov     rdx, rbx; lpszCurrent
0x180068ccf  call    cs:__imp_CharPrevA
0x180068cd5  cmp     byte ptr [rax], 5Ch ; '\'
0x180068cd8  jz      short loc_180068CDF
0x180068cda  mov     word ptr [rbx], 5Ch ; '\'
0x180068cdf  mov     r8d, 104h; nSize
0x180068ce5  lea     rdx, [rsp+378h+Dst]; lpDst
0x180068cea  lea     rcx, [rsp+378h+szStart]; lpSrc
0x180068cf2  call    cs:__imp_ExpandEnvironmentStringsA
0x180068cf8  lea     rdx, [rsp+378h+Dst]; lpszShortPath
0x180068cfd  mov     r8d, 104h; cchBuffer
0x180068d03  lea     rcx, [rsp+378h+Dst]; lpszLongPath
0x180068d08  test    rbp, rbp
0x180068d0b  jz      short loc_180068D17
0x180068d0d  mov     rax, rbp
0x180068d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d15  jmp     short loc_180068D1D
0x180068d17  call    cs:__imp_GetShortPathNameA
0x180068d1d  test    eax, eax
0x180068d1f  lea     ecx, [rax+1]
0x180068d22  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180068d29  cmovz   ecx, eax
0x180068d2c  lea     rax, [rsp+378h+Dst]
0x180068d31  inc     r8; nChar
0x180068d34  cmp     [rax+r8], r14b
0x180068d38  jnz     short loc_180068D31
0x180068d3a  test    ecx, ecx
0x180068d3c  jz      short loc_180068D72
0x180068d3e  lea     rcx, [rsp+378h+szShortPath]
0x180068d46  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180068d4d  inc     rax
0x180068d50  cmp     [rcx+rax], r14b
0x180068d54  jnz     short loc_180068D4D
0x180068d56  cmp     r8d, eax
0x180068d59  jg      short loc_180068D72
0x180068d5b  lea     rdx, [rsp+378h+szShortPath]; psz2
0x180068d63  lea     rcx, [rsp+378h+Dst]; psz1
0x180068d68  call    cs:__imp_StrCmpNIA
0x180068d6e  test    eax, eax
0x180068d70  jz      short loc_180068D7A
0x180068d72  mov     rbx, rdi
0x180068d75  jmp     loc_180068BFC
0x180068d7a  mov     r14d, 1
0x180068d80  test    rsi, rsi
0x180068d83  jz      short loc_180068D8E
0x180068d85  mov     rcx, rsi; hLibModule
0x180068d88  call    cs:__imp_FreeLibrary
0x180068d8e  mov     eax, r14d
0x180068d91  mov     r14, [rsp+378h+arg_10]
0x180068d99  mov     rcx, [rsp+378h+var_28]
0x180068da1  xor     rcx, rsp; StackCookie
0x180068da4  call    __security_check_cookie
0x180068da9  mov     rbx, [rsp+378h+arg_18]
0x180068db1  add     rsp, 360h
0x180068db8  pop     rdi
0x180068db9  pop     rsi
0x180068dba  pop     rbp
0x180068dbb  retn
```
