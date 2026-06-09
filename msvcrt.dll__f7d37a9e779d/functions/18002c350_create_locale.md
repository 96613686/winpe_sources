# _create_locale

- ea: `0x18002c350`
- end: `0x18002c446`
- name: `_create_locale`
- size: `246`
- prototype: `_locale_t __cdecl(int Category, const char *Locale)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180007f00`
- `0x18001d300`
- `0x18001d50c`
- `0x1800245b8`
- `0x18002bdf0`
- `0x18002c15c`
- `0x18002c298`
- `0x18002c350`
- `0x18002c9e8`

## pseudocode

```c
_locale_t __cdecl create_locale(int Category, const char *Locale)
{
  __crt_locale_pointers *v4; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  struct __crt_locale_data *locinfo; // rcx
  struct __crt_multibyte_data *mbcinfo; // rcx
  int v10; // eax

  if ( (unsigned int)Category > 5 || !Locale )
    return 0;
  v4 = (__crt_locale_pointers *)calloc_crt(16, 1);
  if ( !v4 )
  {
LABEL_4:
    *errno() = 12;
    return 0;
  }
  v6 = calloc_crt(352, 1);
  v4->locinfo = (struct __crt_locale_data *)v6;
  if ( !v6 )
  {
LABEL_7:
    free(v4);
    goto LABEL_4;
  }
  v7 = calloc_crt(544, 1);
  locinfo = v4->locinfo;
  v4->mbcinfo = (struct __crt_multibyte_data *)v7;
  if ( !v7 )
  {
    free(locinfo);
    goto LABEL_7;
  }
  copytlocinfo_nolock(locinfo, &_initiallocinfo);
  if ( setlocale_nolock(v4->locinfo, (unsigned int)Category, Locale) )
  {
    if ( !(unsigned int)setmbcp_nolock(*((unsigned int *)v4->locinfo + 1), v4->mbcinfo) )
    {
      v10 = 2;
      do
      {
        *(_DWORD *)v4->mbcinfo = 1;
        --v10;
      }
      while ( v10 );
      return v4;
    }
    mbcinfo = v4->mbcinfo;
  }
  else
  {
    mbcinfo = v4->mbcinfo;
  }
  free(mbcinfo);
  _removelocaleref(v4->locinfo);
  _freetlocinfo(v4->locinfo);
  free(v4);
  return 0;
}

```

## disassembly

```asm
0x18002c350  push    rbx
0x18002c352  push    rbp
0x18002c353  push    rsi
0x18002c354  push    rdi
0x18002c355  sub     rsp, 28h
0x18002c359  mov     rdi, rdx
0x18002c35c  mov     esi, ecx
0x18002c35e  cmp     ecx, 5
0x18002c361  ja      short loc_18002C38A
0x18002c363  test    rdx, rdx
0x18002c366  jz      short loc_18002C38A
0x18002c368  mov     ebp, 1
0x18002c36d  mov     edx, ebp
0x18002c36f  lea     ecx, [rbp+0Fh]
0x18002c372  call    _calloc_crt
0x18002c377  mov     rbx, rax
0x18002c37a  test    rax, rax
0x18002c37d  jnz     short loc_18002C395
0x18002c37f  call    _errno
0x18002c384  mov     dword ptr [rax], 0Ch
0x18002c38a  xor     eax, eax
0x18002c38c  add     rsp, 28h
0x18002c390  pop     rdi
0x18002c391  pop     rsi
0x18002c392  pop     rbp
0x18002c393  pop     rbx
0x18002c394  retn
0x18002c395  mov     rdx, rbp
0x18002c398  mov     ecx, 160h
0x18002c39d  call    _calloc_crt
0x18002c3a2  mov     [rbx], rax
0x18002c3a5  test    rax, rax
0x18002c3a8  jnz     short loc_18002C3B4
0x18002c3aa  mov     rcx, rbx; Block
0x18002c3ad  call    free
0x18002c3b2  jmp     short loc_18002C37F
0x18002c3b4  mov     rdx, rbp
0x18002c3b7  mov     ecx, 220h
0x18002c3bc  call    _calloc_crt
0x18002c3c1  mov     rcx, [rbx]; Block
0x18002c3c4  mov     [rbx+8], rax
0x18002c3c8  test    rax, rax
0x18002c3cb  jnz     short loc_18002C3D4
0x18002c3cd  call    free
0x18002c3d2  jmp     short loc_18002C3AA
0x18002c3d4  lea     rdx, __initiallocinfo
0x18002c3db  call    _copytlocinfo_nolock
0x18002c3e0  mov     rcx, [rbx]
0x18002c3e3  mov     r8, rdi
0x18002c3e6  mov     edx, esi
0x18002c3e8  call    _setlocale_nolock
0x18002c3ed  mov     rdx, [rbx+8]
0x18002c3f1  test    rax, rax
0x18002c3f4  jnz     short loc_18002C3FB
0x18002c3f6  mov     rcx, rdx
0x18002c3f9  jmp     short loc_18002C40E
0x18002c3fb  mov     rcx, [rbx]
0x18002c3fe  mov     ecx, [rcx+4]
0x18002c401  call    _setmbcp_nolock
0x18002c406  test    eax, eax
0x18002c408  jz      short loc_18002C42F
0x18002c40a  mov     rcx, [rbx+8]; Block
0x18002c40e  call    free
0x18002c413  mov     rcx, [rbx]
0x18002c416  call    __removelocaleref
0x18002c41b  mov     rcx, [rbx]
0x18002c41e  call    __freetlocinfo
0x18002c423  mov     rcx, rbx; Block
0x18002c426  call    free
0x18002c42b  xor     ebx, ebx
0x18002c42d  jmp     short loc_18002C43E
0x18002c42f  mov     eax, 2
0x18002c434  mov     rcx, [rbx+8]
0x18002c438  mov     [rcx], ebp
0x18002c43a  sub     eax, ebp
0x18002c43c  jnz     short loc_18002C434
0x18002c43e  mov     rax, rbx
0x18002c441  jmp     loc_18002C38C
```
