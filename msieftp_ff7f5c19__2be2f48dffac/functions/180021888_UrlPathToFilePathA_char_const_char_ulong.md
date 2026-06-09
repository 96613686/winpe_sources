# UrlPathToFilePathA(char const *,char *,ulong)

- ea: `0x180021888`
- end: `0x1800219c3`
- name: `?UrlPathToFilePathA@@YAJPEBDPEADK@Z`
- size: `315`
- prototype: `int(const char *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800254f0`

## callees

- `0x180002240`
- `0x180021888`
- `0x180027040`

## import_xrefs

- `SHLWAPI!PathRemoveBlanksA` at `0x180021904`
- `SHLWAPI!PathRemoveBlanksA` at `0x180021904`
- `SHLWAPI!StrChrA` at `0x1800218f0`
- `SHLWAPI!StrChrA` at `0x1800218f0`
- `SHLWAPI!__imp_PathIsValidCharA` at `0x180021934`
- `SHLWAPI!__imp_PathIsValidCharA` at `0x180021934`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002196a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002196a`

## pseudocode

```c
__int64 __fastcall UrlPathToFilePathA(char *a1, char *a2)
{
  unsigned int v2; // ebp
  char *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  char *v6; // rax
  PSTR v7; // rax
  PSTR v8; // rsi
  __int64 v9; // rcx
  CHAR v10; // al
  char *v11; // rdi
  char *v12; // rdi
  WCHAR WideCharStr[264]; // [rsp+30h] [rbp-248h] BYREF

  v2 = 0;
  v3 = a2;
  if ( a1 != a2 )
  {
    v4 = 260;
    v5 = 2147483646;
    v6 = v3;
    while ( v5 )
    {
      if ( *a1 )
      {
        *v6++ = *a1++;
        --v5;
        if ( --v4 )
          continue;
      }
      if ( !v4 )
        --v6;
      break;
    }
    *v6 = 0;
  }
  while ( 1 )
  {
    v7 = StrChrA(v3, 0x2Fu);
    v8 = v7;
    if ( v7 )
      *v7 = 0;
    PathRemoveBlanksA(v3);
    v10 = *v3;
    if ( *v3 )
    {
      if ( v10 == 46 && (!v3[1] || v3[1] == 46 && !v3[2]) )
      {
        *v3 = 45;
        v10 = 45;
      }
      v11 = v3;
      do
      {
        LOBYTE(v9) = v10;
        if ( !(unsigned int)PathIsValidCharA(v9, 484) )
          *v11 = 45;
        v10 = *++v11;
      }
      while ( *v11 );
      v12 = v3;
      while ( MultiByteToWideChar(0, 0, v3, -1, WideCharStr, 260) > 0 && (unsigned int)PathIsInvalidW(WideCharStr) )
      {
        if ( !*v12 )
          goto LABEL_26;
        *v12++ = 45;
      }
    }
    else
    {
LABEL_26:
      v2 = -2147467259;
    }
    if ( !v8 )
      return v2;
    *v8 = 92;
    v3 = v8 + 1;
  }
}

```

## disassembly

```asm
0x180021888  push    rbx
0x18002188a  push    rbp
0x18002188b  push    rsi
0x18002188c  push    rdi
0x18002188d  sub     rsp, 258h
0x180021894  mov     rax, cs:__security_cookie
0x18002189b  xor     rax, rsp
0x18002189e  mov     [rsp+278h+var_38], rax
0x1800218a6  xor     ebp, ebp
0x1800218a8  mov     rbx, rdx
0x1800218ab  cmp     rcx, rdx
0x1800218ae  jz      short loc_1800218E8
0x1800218b0  mov     edx, 104h
0x1800218b5  mov     r8d, 7FFFFFFEh
0x1800218bb  mov     rax, rbx
0x1800218be  test    r8, r8
0x1800218c1  jz      short loc_1800218E5
0x1800218c3  mov     r9b, [rcx]
0x1800218c6  test    r9b, r9b
0x1800218c9  jz      short loc_1800218DD
0x1800218cb  mov     [rax], r9b
0x1800218ce  inc     rcx
0x1800218d1  inc     rax
0x1800218d4  dec     r8
0x1800218d7  sub     rdx, 1
0x1800218db  jnz     short loc_1800218BE
0x1800218dd  test    rdx, rdx
0x1800218e0  jnz     short loc_1800218E5
0x1800218e2  dec     rax
0x1800218e5  mov     [rax], bpl
0x1800218e8  mov     edx, 2Fh ; '/'; wMatch
0x1800218ed  mov     rcx, rbx; pszStart
0x1800218f0  call    cs:__imp_StrChrA
0x1800218f6  mov     rsi, rax
0x1800218f9  test    rax, rax
0x1800218fc  jz      short loc_180021901
0x1800218fe  mov     byte ptr [rax], 0
0x180021901  mov     rcx, rbx; pszPath
0x180021904  call    cs:__imp_PathRemoveBlanksA
0x18002190a  mov     al, [rbx]
0x18002190c  test    al, al
0x18002190e  jz      short loc_18002198F
0x180021910  cmp     al, 2Eh ; '.'
0x180021912  jnz     short loc_18002192A
0x180021914  cmp     byte ptr [rbx+1], 0
0x180021918  jz      short loc_180021925
0x18002191a  cmp     [rbx+1], al
0x18002191d  jnz     short loc_18002192A
0x18002191f  cmp     byte ptr [rbx+2], 0
0x180021923  jnz     short loc_18002192A
0x180021925  mov     byte ptr [rbx], 2Dh ; '-'
0x180021928  mov     al, 2Dh ; '-'
0x18002192a  mov     rdi, rbx
0x18002192d  mov     edx, 1E4h
0x180021932  mov     cl, al
0x180021934  call    cs:__imp_PathIsValidCharA
0x18002193a  test    eax, eax
0x18002193c  jnz     short loc_180021941
0x18002193e  mov     byte ptr [rdi], 2Dh ; '-'
0x180021941  inc     rdi
0x180021944  mov     al, [rdi]
0x180021946  test    al, al
0x180021948  jnz     short loc_18002192D
0x18002194a  mov     rdi, rbx
0x18002194d  lea     rax, [rsp+278h+WideCharStr]
0x180021952  mov     [rsp+278h+cchWideChar], 104h; cchWideChar
0x18002195a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002195e  mov     [rsp+278h+lpWideCharStr], rax; lpWideCharStr
0x180021963  mov     r8, rbx; lpMultiByteStr
0x180021966  xor     edx, edx; dwFlags
0x180021968  xor     ecx, ecx; CodePage
0x18002196a  call    cs:__imp_MultiByteToWideChar
0x180021970  test    eax, eax
0x180021972  jle     short loc_180021994
0x180021974  lea     rcx, [rsp+278h+WideCharStr]; unsigned __int16 *
0x180021979  call    PathIsInvalidW
0x18002197e  test    eax, eax
0x180021980  jz      short loc_180021994
0x180021982  cmp     byte ptr [rdi], 0
0x180021985  jz      short loc_18002198F
0x180021987  mov     byte ptr [rdi], 2Dh ; '-'
0x18002198a  inc     rdi
0x18002198d  jmp     short loc_18002194D
0x18002198f  mov     ebp, 80004005h
0x180021994  test    rsi, rsi
0x180021997  jz      short loc_1800219A5
0x180021999  mov     byte ptr [rsi], 5Ch ; '\'
0x18002199c  lea     rbx, [rsi+1]
0x1800219a0  jmp     loc_1800218E8
0x1800219a5  mov     eax, ebp
0x1800219a7  mov     rcx, [rsp+278h+var_38]
0x1800219af  xor     rcx, rsp; StackCookie
0x1800219b2  call    __security_check_cookie
0x1800219b7  add     rsp, 258h
0x1800219be  pop     rdi
0x1800219bf  pop     rsi
0x1800219c0  pop     rbp
0x1800219c1  pop     rbx
0x1800219c2  retn
```
