# CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x1800086c4`
- end: `0x180008810`
- name: `?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `332`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800075d0`

## callees

- `0x1800086c4`
- `0x180009b58`
- `0x180015138`
- `0x180016090`
- `0x18001da30`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800086ff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800087b5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800086ff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800087b5`

## pseudocode

```c
__int64 __fastcall CreateNestedDirectory(LPCWSTR lpPathName, struct _SECURITY_ATTRIBUTES *a2)
{
  const WCHAR *v2; // rbx
  BOOL DirectoryW; // eax
  signed int v4; // eax
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  WCHAR *v8; // rax
  WCHAR *v9; // rcx
  __int16 v10; // cx
  __int16 *v11; // rbx
  BOOL v12; // eax
  unsigned int v13; // ecx
  WCHAR PathName[3]; // [rsp+20h] [rbp-228h] BYREF
  __int16 v16; // [rsp+26h] [rbp-222h] BYREF

  v2 = lpPathName;
  if ( (unsigned int)IsFullPath(lpPathName) )
  {
    DirectoryW = CreateDirectoryW(v2, 0);
    v4 = ResultFromWin32Bool(DirectoryW);
    if ( v4 == -2147024893 )
    {
      v5 = -1;
      do
        ++v5;
      while ( v2[v5] );
      v6 = 260;
      if ( v2[v5 - 1] == 92 )
      {
        v7 = 2147483646;
        v8 = PathName;
        do
        {
          if ( !v7 )
            break;
          if ( !*v2 )
            break;
          *v8++ = *v2++;
          --v7;
          --v6;
        }
        while ( v6 );
        v9 = v8 - 1;
        if ( v6 )
          v9 = v8;
        v4 = v6 == 0 ? 0x8007007A : 0;
        *v9 = 0;
      }
      else
      {
        v4 = StringCchPrintfW(PathName, 0x104u, L"%s\\", v2);
      }
      if ( v4 < 0 )
      {
        v4 = -2147024690;
      }
      else
      {
        v10 = v16;
        if ( v16 )
        {
          v11 = &v16;
          do
          {
            if ( v10 == 92 )
            {
              *v11 = 0;
              v12 = CreateDirectoryW(PathName, 0);
              v4 = ResultFromWin32Bool(v12);
              *v11 = 92;
            }
            v10 = *++v11;
          }
          while ( *v11 );
        }
      }
    }
    v13 = 0;
    if ( v4 != -2147024713 )
      return (unsigned int)v4;
  }
  else
  {
    return (unsigned int)-2147024735;
  }
  return v13;
}

```

## disassembly

```asm
0x1800086c4  mov     [rsp+arg_8], rbx
0x1800086c9  mov     [rsp+arg_10], rsi
0x1800086ce  push    rdi
0x1800086cf  sub     rsp, 240h
0x1800086d6  mov     rax, cs:__security_cookie
0x1800086dd  xor     rax, rsp
0x1800086e0  mov     [rsp+248h+var_18], rax
0x1800086e8  mov     rbx, rcx
0x1800086eb  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x1800086f0  xor     edi, edi
0x1800086f2  test    eax, eax
0x1800086f4  jz      loc_1800087E4
0x1800086fa  xor     edx, edx; lpSecurityAttributes
0x1800086fc  mov     rcx, rbx; lpPathName
0x1800086ff  call    cs:__imp_CreateDirectoryW
0x180008705  mov     ecx, eax; int
0x180008707  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000870c  cmp     eax, 80070003h
0x180008711  jnz     loc_1800087D8
0x180008717  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000871b  inc     rax
0x18000871e  cmp     [rbx+rax*2], di
0x180008722  jnz     short loc_18000871B
0x180008724  mov     esi, 5Ch ; '\'
0x180008729  mov     edx, 104h; unsigned __int64
0x18000872e  cmp     [rbx+rax*2-2], si
0x180008733  jnz     short loc_18000877F
0x180008735  mov     ecx, 7FFFFFFEh
0x18000873a  lea     rax, [rsp+248h+PathName]
0x18000873f  test    rcx, rcx
0x180008742  jz      short loc_180008763
0x180008744  movzx   r8d, word ptr [rbx]
0x180008748  test    r8w, r8w
0x18000874c  jz      short loc_180008763
0x18000874e  mov     [rax], r8w
0x180008752  add     rbx, 2
0x180008756  add     rax, 2
0x18000875a  dec     rcx
0x18000875d  sub     rdx, 1
0x180008761  jnz     short loc_18000873F
0x180008763  lea     rcx, [rax-2]
0x180008767  test    rdx, rdx
0x18000876a  cmovnz  rcx, rax
0x18000876e  neg     rdx
0x180008771  sbb     eax, eax
0x180008773  not     eax
0x180008775  and     eax, 8007007Ah
0x18000877a  mov     [rcx], di
0x18000877d  jmp     short loc_180008793
0x18000877f  mov     r9, rbx
0x180008782  lea     r8, aS; "%s\\"
0x180008789  lea     rcx, [rsp+248h+PathName]; unsigned __int16 *
0x18000878e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008793  test    eax, eax
0x180008795  js      short loc_1800087D3
0x180008797  movzx   ecx, [rsp+248h+var_222]
0x18000879c  test    cx, cx
0x18000879f  jz      short loc_1800087D8
0x1800087a1  lea     rbx, [rsp+248h+var_222]
0x1800087a6  cmp     cx, si
0x1800087a9  jnz     short loc_1800087C5
0x1800087ab  xor     edx, edx; lpSecurityAttributes
0x1800087ad  mov     [rbx], di
0x1800087b0  lea     rcx, [rsp+248h+PathName]; lpPathName
0x1800087b5  call    cs:__imp_CreateDirectoryW
0x1800087bb  mov     ecx, eax; int
0x1800087bd  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800087c2  mov     [rbx], si
0x1800087c5  add     rbx, 2
0x1800087c9  movzx   ecx, word ptr [rbx]
0x1800087cc  test    cx, cx
0x1800087cf  jnz     short loc_1800087A6
0x1800087d1  jmp     short loc_1800087D8
0x1800087d3  mov     eax, 800700CEh
0x1800087d8  cmp     eax, 800700B7h
0x1800087dd  mov     ecx, edi
0x1800087df  cmovnz  ecx, eax
0x1800087e2  jmp     short loc_1800087E9
0x1800087e4  mov     ecx, 800700A1h
0x1800087e9  mov     eax, ecx
0x1800087eb  mov     rcx, [rsp+248h+var_18]
0x1800087f3  xor     rcx, rsp; StackCookie
0x1800087f6  call    __security_check_cookie
0x1800087fb  lea     r11, [rsp+248h+var_8]
0x180008803  mov     rbx, [r11+18h]
0x180008807  mov     rsi, [r11+20h]
0x18000880b  mov     rsp, r11
0x18000880e  pop     rdi
0x18000880f  retn
```
