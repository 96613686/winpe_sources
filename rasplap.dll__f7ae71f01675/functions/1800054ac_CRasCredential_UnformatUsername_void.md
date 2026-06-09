# CRasCredential::_UnformatUsername(void)

- ea: `0x1800054ac`
- end: `0x180005640`
- name: `?_UnformatUsername@CRasCredential@@AEAAJXZ`
- size: `404`
- prototype: `__int64 __fastcall(CRasCredential *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004e74`

## callees

- `0x1800016e0`
- `0x180004d68`
- `0x1800054ac`
- `0x180005680`
- `0x1800056d4`

## import_xrefs

- `msvcrt!wcschr` at `0x1800054dc`
- `msvcrt!wcschr` at `0x1800054ec`
- `msvcrt!wcschr` at `0x1800054dc`
- `msvcrt!wcschr` at `0x1800054ec`
- `KERNEL32!GetComputerNameW` at `0x1800055f9`
- `KERNEL32!GetComputerNameW` at `0x1800055f9`

## pseudocode

```c
__int64 __fastcall CRasCredential::_UnformatUsername(CRasCredential *this)
{
  wchar_t *v1; // rdi
  wchar_t *v3; // rbx
  wchar_t *v4; // rax
  wchar_t *v5; // rsi
  __int64 v6; // rcx
  unsigned __int64 v7; // r11
  unsigned int v8; // ebx
  __int64 v9; // rcx
  char *v10; // rax
  __int64 v11; // r11
  DWORD nSize; // [rsp+40h] [rbp+8h] BYREF

  v1 = (wchar_t *)((char *)this + 556);
  if ( !*((_WORD *)this + 278) )
    return 1;
  v3 = wcschr((const wchar_t *)this + 278, 0x40u);
  v4 = wcschr(v1, 0x5Cu);
  v5 = v4;
  v6 = -1;
  do
    ++v6;
  while ( v1[v6] );
  v7 = (unsigned __int64)&v1[v6 - 1];
  if ( v3 )
  {
    if ( !v4 && v3 > v1 && (unsigned __int64)v3 < v7 )
    {
      v8 = StringCchCopyW(v1, 0x101u, v1);
      v9 = 32;
      v10 = (char *)this + 1584;
      do
      {
        *v10++ = 0;
        --v9;
      }
      while ( v9 );
      return v8;
    }
    return (unsigned int)-2147467259;
  }
  if ( !v4 )
  {
    v8 = 0;
    if ( *((_WORD *)this + 792) )
      return v8;
    LOBYTE(nSize) = 0;
    if ( (int)IsBuiltInAdministrator(v1, (bool *)&nSize) >= 0 && (_BYTE)nSize )
    {
      nSize = 16;
      return !GetComputerNameW((LPWSTR)this + 792, &nSize) ? 0x80004005 : 0;
    }
    if ( (unsigned int)GetDefaultDomain((char *)this + 1584, 16) )
      return v8;
    return (unsigned int)-2147467259;
  }
  if ( v4 <= v1 || (unsigned __int64)v4 >= v7 )
    return (unsigned int)-2147467259;
  v8 = StringCchCopyNW((STRSAFE_LPWSTR)this + 792, 0x10u, v1, (((char *)v4 - (char *)v1 - 2) >> 1) + 1);
  if ( (v8 & 0x80000000) == 0 )
    return (unsigned int)StringCchCopyNW(v1, 0x101u, v5 + 1, ((v11 - (__int64)(v5 + 1)) >> 1) + 1);
  return v8;
}

```

## disassembly

```asm
0x1800054ac  mov     [rsp+arg_8], rbx
0x1800054b1  mov     [rsp+arg_10], rbp
0x1800054b6  push    rsi
0x1800054b7  push    rdi
0x1800054b8  push    r14
0x1800054ba  sub     rsp, 20h
0x1800054be  lea     rdi, [rcx+22Ch]
0x1800054c5  xor     r14d, r14d
0x1800054c8  mov     rbp, rcx
0x1800054cb  cmp     [rdi], r14w
0x1800054cf  jz      loc_180005626
0x1800054d5  lea     edx, [r14+40h]; Ch
0x1800054d9  mov     rcx, rdi; Str
0x1800054dc  call    cs:__imp_wcschr
0x1800054e2  lea     edx, [r14+5Ch]; Ch
0x1800054e6  mov     rcx, rdi; Str
0x1800054e9  mov     rbx, rax
0x1800054ec  call    cs:__imp_wcschr
0x1800054f2  mov     rsi, rax
0x1800054f5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800054f9  inc     rcx
0x1800054fc  cmp     [rdi+rcx*2], r14w
0x180005501  jnz     short loc_1800054F9
0x180005503  lea     r11, [rdi-2]
0x180005507  lea     r11, [r11+rcx*2]
0x18000550b  test    rbx, rbx
0x18000550e  jz      short loc_180005558
0x180005510  test    rsi, rsi
0x180005513  jnz     loc_18000561F
0x180005519  cmp     rbx, rdi
0x18000551c  jbe     loc_18000561F
0x180005522  cmp     rbx, r11
0x180005525  jnb     loc_18000561F
0x18000552b  mov     r8, rdi; pszSrc
0x18000552e  mov     edx, 101h; cchDest
0x180005533  mov     rcx, rdi; pszDest
0x180005536  call    StringCchCopyW
0x18000553b  mov     ebx, eax
0x18000553d  lea     ecx, [rsi+20h]
0x180005540  lea     rax, [rbp+630h]
0x180005547  mov     [rax], r14b
0x18000554a  inc     rax
0x18000554d  sub     rcx, 1
0x180005551  jnz     short loc_180005547
0x180005553  jmp     loc_18000562B
0x180005558  test    rsi, rsi
0x18000555b  jz      short loc_1800055BC
0x18000555d  cmp     rsi, rdi
0x180005560  jbe     loc_18000561F
0x180005566  cmp     rsi, r11
0x180005569  jnb     loc_18000561F
0x18000556f  mov     r9, rsi
0x180005572  lea     rcx, [rbp+630h]; pszDest
0x180005579  sub     r9, rdi
0x18000557c  mov     r8, rdi; pszSrc
0x18000557f  sub     r9, 2
0x180005583  mov     edx, 10h; cchDest
0x180005588  sar     r9, 1
0x18000558b  inc     r9; cchToCopy
0x18000558e  call    StringCchCopyNW
0x180005593  mov     ebx, eax
0x180005595  test    eax, eax
0x180005597  js      loc_18000562B
0x18000559d  lea     r8, [rsi+2]; pszSrc
0x1800055a1  mov     edx, 101h; cchDest
0x1800055a6  sub     r11, r8
0x1800055a9  mov     rcx, rdi; pszDest
0x1800055ac  sar     r11, 1
0x1800055af  lea     r9, [r11+1]; cchToCopy
0x1800055b3  call    StringCchCopyNW
0x1800055b8  mov     ebx, eax
0x1800055ba  jmp     short loc_18000562B
0x1800055bc  lea     rsi, [rbp+630h]
0x1800055c3  mov     ebx, r14d
0x1800055c6  cmp     [rsi], r14w
0x1800055ca  jnz     short loc_18000562B
0x1800055cc  lea     rdx, [rsp+38h+nSize]
0x1800055d1  mov     byte ptr [rsp+38h+nSize], r14b
0x1800055d6  mov     rcx, rdi; lpString1
0x1800055d9  call    _IsBuiltInAdministrator
0x1800055de  test    eax, eax
0x1800055e0  js      short loc_18000560E
0x1800055e2  cmp     byte ptr [rsp+38h+nSize], r14b
0x1800055e7  jz      short loc_18000560E
0x1800055e9  lea     rdx, [rsp+38h+nSize]; nSize
0x1800055ee  mov     [rsp+38h+nSize], 10h
0x1800055f6  mov     rcx, rsi; lpBuffer
0x1800055f9  call    cs:__imp_GetComputerNameW
0x1800055ff  neg     eax
0x180005601  mov     ebx, 80004005h
0x180005606  sbb     ecx, ecx
0x180005608  not     ecx
0x18000560a  and     ebx, ecx
0x18000560c  jmp     short loc_18000562B
0x18000560e  mov     edx, 10h
0x180005613  mov     rcx, rsi
0x180005616  call    _GetDefaultDomain
0x18000561b  test    eax, eax
0x18000561d  jnz     short loc_18000562B
0x18000561f  mov     ebx, 80004005h
0x180005624  jmp     short loc_18000562B
0x180005626  mov     ebx, 1
0x18000562b  mov     rbp, [rsp+38h+arg_10]
0x180005630  mov     eax, ebx
0x180005632  mov     rbx, [rsp+38h+arg_8]
0x180005637  add     rsp, 20h
0x18000563b  pop     r14
0x18000563d  pop     rdi
0x18000563e  pop     rsi
0x18000563f  retn
```
