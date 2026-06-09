# CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x140018588`
- end: `0x1400187db`
- name: `?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400187e4`

## callees

- `0x1400020b0`
- `0x14000898c`
- `0x140018588`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001876c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001876c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14001866b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140018758`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14001866b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140018758`

## pseudocode

```c
__int64 __fastcall CreateNestedDirectory(const WCHAR *lpPathName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  LPCWSTR v3; // rbx
  LPCWSTR v4; // rax
  __int64 v5; // rdx
  WCHAR v6; // cx
  __int64 v7; // rcx
  _WORD *v8; // rax
  signed int LastError; // eax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  WCHAR *v13; // rax
  WCHAR *v14; // rcx
  __int16 v15; // cx
  __int16 *v16; // rbx
  __int16 *v17; // rdi
  bool v18; // zf
  struct _SECURITY_ATTRIBUTES *v19; // rdx
  bool v20; // sf
  unsigned int v21; // ecx
  WCHAR PathName[3]; // [rsp+20h] [rbp-248h] BYREF
  __int16 v24; // [rsp+26h] [rbp-242h] BYREF

  v3 = lpPathName;
  if ( !lpPathName )
    return (unsigned int)-2147024735;
  v4 = lpPathName;
  v5 = 0x7FFFFFFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  if ( v5 )
  {
    if ( ((0x7FFFFFFF - v5) & (unsigned __int64)-(__int64)(v5 != 0)) >= 2 && lpPathName[1] == 58 )
    {
      v6 = *lpPathName;
      if ( (unsigned __int16)(*v3 - 97) <= 0x19u || (unsigned __int16)(v6 - 65) <= 0x19u )
        goto LABEL_58;
    }
  }
  v7 = 0x7FFFFFFF;
  v8 = v3;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  if ( v7
    && ((0x7FFFFFFF - v7) & ((unsigned __int128)-(__int128)(unsigned __int64)v7 >> 64)) >= 2
    && *v3 == 92
    && v3[1] == 92 )
  {
LABEL_58:
    if ( CreateDirectoryW(v3, lpSecurityAttributes) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( LastError == -2147024893 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v3[v10] );
        v11 = 260;
        if ( v3[v10 - 1] == 92 )
        {
          v12 = 2147483646;
          v13 = PathName;
          do
          {
            if ( !v12 )
              break;
            if ( !*v3 )
              break;
            *v13++ = *v3++;
            --v12;
            --v11;
          }
          while ( v11 );
          v14 = v13 - 1;
          if ( v11 )
            v14 = v13;
          LastError = v11 == 0 ? 0x8007007A : 0;
          *v14 = 0;
        }
        else
        {
          LastError = StringCchPrintfW(PathName, 0x104u, L"%s\\", v3);
        }
        if ( LastError < 0 )
        {
          LastError = -2147024690;
        }
        else
        {
          v15 = v24;
          if ( v24 )
          {
            v16 = &v24;
            do
            {
              v17 = v16 + 1;
              if ( v15 == 92 )
              {
                v18 = *v17 == 0;
                v19 = lpSecurityAttributes;
                *v16 = 0;
                if ( !v18 )
                  v19 = 0;
                if ( CreateDirectoryW(PathName, v19) )
                {
                  LastError = 0;
                }
                else
                {
                  LastError = GetLastError();
                  v20 = LastError < 0;
                  if ( LastError > 0 )
                  {
                    LastError = (unsigned __int16)LastError | 0x80070000;
                    v20 = LastError < 0;
                  }
                  if ( !v20 )
                    LastError = -2147467259;
                }
                *v16 = 92;
              }
              ++v16;
              v15 = *v17;
            }
            while ( *v17 );
          }
        }
      }
    }
    v21 = 0;
    if ( LastError != -2147024713 )
      return (unsigned int)LastError;
  }
  else
  {
    return (unsigned int)-2147024735;
  }
  return v21;
}

```

## disassembly

```asm
0x140018588  mov     [rsp+arg_10], rbx
0x14001858d  push    rbp
0x14001858e  push    rsi
0x14001858f  push    rdi
0x140018590  push    r12
0x140018592  push    r14
0x140018594  sub     rsp, 240h
0x14001859b  mov     rax, cs:__security_cookie
0x1400185a2  xor     rax, rsp
0x1400185a5  mov     [rsp+268h+var_38], rax
0x1400185ad  xor     ebp, ebp
0x1400185af  mov     rsi, rdx
0x1400185b2  mov     rbx, rcx
0x1400185b5  test    rcx, rcx
0x1400185b8  jz      loc_1400187AC
0x1400185be  mov     r8d, 7FFFFFFFh
0x1400185c4  mov     rax, rcx
0x1400185c7  mov     edx, r8d
0x1400185ca  cmp     [rax], bp
0x1400185cd  jz      short loc_1400185D9
0x1400185cf  add     rax, 2
0x1400185d3  sub     rdx, 1
0x1400185d7  jnz     short loc_1400185CA
0x1400185d9  mov     rcx, r8
0x1400185dc  mov     rax, rdx
0x1400185df  sub     rcx, rdx
0x1400185e2  mov     r14d, 5Ch ; '\'
0x1400185e8  neg     rax
0x1400185eb  sbb     r9, r9
0x1400185ee  and     r9, rcx
0x1400185f1  test    rdx, rdx
0x1400185f4  jz      short loc_140018619
0x1400185f6  cmp     r9, 2
0x1400185fa  jb      short loc_140018619
0x1400185fc  cmp     word ptr [rbx+2], 3Ah ; ':'
0x140018601  jnz     short loc_140018619
0x140018603  movzx   ecx, word ptr [rbx]
0x140018606  lea     eax, [rcx-61h]
0x140018609  cmp     ax, 19h
0x14001860d  jbe     short loc_140018665
0x14001860f  sub     cx, 41h ; 'A'
0x140018613  cmp     cx, 19h
0x140018617  jbe     short loc_140018665
0x140018619  mov     rcx, r8
0x14001861c  mov     rax, rbx
0x14001861f  cmp     [rax], bp
0x140018622  jz      short loc_14001862E
0x140018624  add     rax, 2
0x140018628  sub     rcx, 1
0x14001862c  jnz     short loc_14001861F
0x14001862e  sub     r8, rcx
0x140018631  mov     rax, rcx
0x140018634  neg     rax
0x140018637  sbb     rdx, rdx
0x14001863a  and     rdx, r8
0x14001863d  test    rcx, rcx
0x140018640  jz      loc_1400187AC
0x140018646  cmp     rdx, 2
0x14001864a  jb      loc_1400187AC
0x140018650  cmp     [rbx], r14w
0x140018654  jnz     loc_1400187AC
0x14001865a  cmp     [rbx+2], r14w
0x14001865f  jnz     loc_1400187AC
0x140018665  mov     rdx, rsi; lpSecurityAttributes
0x140018668  mov     rcx, rbx; lpPathName
0x14001866b  call    cs:__imp_CreateDirectoryW
0x140018672  nop     dword ptr [rax+rax+00h]
0x140018677  test    eax, eax
0x140018679  jz      short loc_140018682
0x14001867b  mov     eax, ebp
0x14001867d  jmp     loc_1400187A0
0x140018682  call    cs:__imp_GetLastError
0x140018689  nop     dword ptr [rax+rax+00h]
0x14001868e  test    eax, eax
0x140018690  jle     short loc_14001869A
0x140018692  movzx   eax, ax
0x140018695  or      eax, 80070000h
0x14001869a  test    eax, eax
0x14001869c  mov     r12d, 80004005h
0x1400186a2  cmovns  eax, r12d
0x1400186a6  cmp     eax, 80070003h
0x1400186ab  jnz     loc_1400187A0
0x1400186b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400186b5  inc     rax
0x1400186b8  cmp     [rbx+rax*2], bp
0x1400186bc  jnz     short loc_1400186B5
0x1400186be  mov     edx, 104h; unsigned __int64
0x1400186c3  cmp     [rbx+rax*2-2], r14w
0x1400186c9  jnz     short loc_140018715
0x1400186cb  mov     ecx, 7FFFFFFEh
0x1400186d0  lea     rax, [rsp+268h+PathName]
0x1400186d5  test    rcx, rcx
0x1400186d8  jz      short loc_1400186F9
0x1400186da  movzx   r8d, word ptr [rbx]
0x1400186de  test    r8w, r8w
0x1400186e2  jz      short loc_1400186F9
0x1400186e4  mov     [rax], r8w
0x1400186e8  add     rbx, 2
0x1400186ec  add     rax, 2
0x1400186f0  dec     rcx
0x1400186f3  sub     rdx, 1
0x1400186f7  jnz     short loc_1400186D5
0x1400186f9  lea     rcx, [rax-2]
0x1400186fd  test    rdx, rdx
0x140018700  cmovnz  rcx, rax
0x140018704  neg     rdx
0x140018707  sbb     eax, eax
0x140018709  not     eax
0x14001870b  and     eax, 8007007Ah
0x140018710  mov     [rcx], bp
0x140018713  jmp     short loc_140018729
0x140018715  mov     r9, rbx
0x140018718  lea     r8, aS_0; "%s\\"
0x14001871f  lea     rcx, [rsp+268h+PathName]; unsigned __int16 *
0x140018724  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140018729  test    eax, eax
0x14001872b  js      short loc_14001879B
0x14001872d  movzx   ecx, [rsp+268h+var_242]
0x140018732  test    cx, cx
0x140018735  jz      short loc_1400187A0
0x140018737  lea     rbx, [rsp+268h+var_242]
0x14001873c  lea     rdi, [rbx+2]
0x140018740  cmp     cx, r14w
0x140018744  jnz     short loc_14001878E
0x140018746  cmp     [rdi], bp
0x140018749  lea     rcx, [rsp+268h+PathName]; lpPathName
0x14001874e  mov     rdx, rsi
0x140018751  mov     [rbx], bp
0x140018754  cmovnz  rdx, rbp; lpSecurityAttributes
0x140018758  call    cs:__imp_CreateDirectoryW
0x14001875f  nop     dword ptr [rax+rax+00h]
0x140018764  test    eax, eax
0x140018766  jz      short loc_14001876C
0x140018768  mov     eax, ebp
0x14001876a  jmp     short loc_14001878A
0x14001876c  call    cs:__imp_GetLastError
0x140018773  nop     dword ptr [rax+rax+00h]
0x140018778  test    eax, eax
0x14001877a  jle     short loc_140018786
0x14001877c  movzx   eax, ax
0x14001877f  or      eax, 80070000h
0x140018784  test    eax, eax
0x140018786  cmovns  eax, r12d
0x14001878a  mov     [rbx], r14w
0x14001878e  mov     rbx, rdi
0x140018791  movzx   ecx, word ptr [rbx]
0x140018794  test    cx, cx
0x140018797  jnz     short loc_14001873C
0x140018799  jmp     short loc_1400187A0
0x14001879b  mov     eax, 800700CEh
0x1400187a0  cmp     eax, 800700B7h
0x1400187a5  mov     ecx, ebp
0x1400187a7  cmovnz  ecx, eax
0x1400187aa  jmp     short loc_1400187B1
0x1400187ac  mov     ecx, 800700A1h
0x1400187b1  mov     eax, ecx
0x1400187b3  mov     rcx, [rsp+268h+var_38]
0x1400187bb  xor     rcx, rsp; StackCookie
0x1400187be  call    __security_check_cookie
0x1400187c3  mov     rbx, [rsp+268h+arg_10]
0x1400187cb  add     rsp, 240h
0x1400187d2  pop     r14
0x1400187d4  pop     r12
0x1400187d6  pop     rdi
0x1400187d7  pop     rsi
0x1400187d8  pop     rbp
0x1400187d9  retn
```
