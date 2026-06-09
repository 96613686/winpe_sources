# CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180006d44`
- end: `0x180006e66`
- name: `?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000659c`
- `0x180011200`
- `0x18003f6f4`

## callees

- `0x180006580`
- `0x180006d44`
- `0x180012290`
- `0x180021980`
- `0x180032aa8`
- `0x18003a730`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006d83`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006e08`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006d83`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180006e08`

## pseudocode

```c
__int64 __fastcall CreateNestedDirectory(const unsigned __int16 *a1, LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  const WCHAR *v4; // rcx
  BOOL DirectoryW; // eax
  int v6; // eax
  __int64 v7; // rax
  __int16 v8; // cx
  __int16 *v9; // rbx
  __int16 *v10; // rdi
  bool v11; // zf
  struct _SECURITY_ATTRIBUTES *v12; // rdx
  BOOL v13; // eax
  unsigned int v14; // ecx
  WCHAR PathName[3]; // [rsp+20h] [rbp-238h] BYREF
  __int16 v17; // [rsp+26h] [rbp-232h] BYREF

  if ( (unsigned int)IsFullPath(a1) )
  {
    DirectoryW = CreateDirectoryW(v4, lpSecurityAttributes);
    v6 = ResultFromWin32Bool(DirectoryW);
    if ( v6 == -2147024893 )
    {
      v7 = -1;
      do
        ++v7;
      while ( a1[v7] );
      if ( a1[v7 - 1] == 92 )
        v6 = StringCchCopyW(PathName, 0x104u, a1);
      else
        v6 = StringCchPrintfW(PathName, 0x104u, L"%s\\", a1);
      if ( v6 < 0 )
      {
        v6 = -2147024690;
      }
      else
      {
        v8 = v17;
        if ( v17 )
        {
          v9 = &v17;
          do
          {
            v10 = v9 + 1;
            if ( v8 == 92 )
            {
              v11 = *v10 == 0;
              v12 = lpSecurityAttributes;
              *v9 = 0;
              if ( !v11 )
                v12 = 0;
              v13 = CreateDirectoryW(PathName, v12);
              v6 = ResultFromWin32Bool(v13);
              *v9 = 92;
            }
            ++v9;
            v8 = *v10;
          }
          while ( *v10 );
        }
      }
    }
    v14 = 0;
    if ( v6 != -2147024713 )
      return (unsigned int)v6;
  }
  else
  {
    return (unsigned int)-2147024735;
  }
  return v14;
}

```

## disassembly

```asm
0x180006d44  mov     [rsp+arg_10], rbx
0x180006d49  mov     [rsp+arg_18], rbp
0x180006d4e  push    rsi
0x180006d4f  push    rdi
0x180006d50  push    r14
0x180006d52  sub     rsp, 240h
0x180006d59  mov     rax, cs:__security_cookie
0x180006d60  xor     rax, rsp
0x180006d63  mov     [rsp+258h+var_28], rax
0x180006d6b  mov     rsi, rdx
0x180006d6e  mov     rbx, rcx
0x180006d71  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x180006d76  xor     ebp, ebp
0x180006d78  test    eax, eax
0x180006d7a  jz      loc_180006E37
0x180006d80  mov     rdx, rsi; lpSecurityAttributes
0x180006d83  call    cs:__imp_CreateDirectoryW
0x180006d89  mov     ecx, eax; int
0x180006d8b  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180006d90  cmp     eax, 80070003h
0x180006d95  jnz     loc_180006E2B
0x180006d9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006d9f  inc     rax
0x180006da2  cmp     [rbx+rax*2], bp
0x180006da6  jnz     short loc_180006D9F
0x180006da8  mov     r14d, 5Ch ; '\'
0x180006dae  lea     rcx, [rsp+258h+PathName]; unsigned __int16 *
0x180006db3  mov     edx, 104h; unsigned __int64
0x180006db8  cmp     [rbx+rax*2-2], r14w
0x180006dbe  jnz     short loc_180006DCA
0x180006dc0  mov     r8, rbx; unsigned __int16 *
0x180006dc3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006dc8  jmp     short loc_180006DD9
0x180006dca  mov     r9, rbx
0x180006dcd  lea     r8, aS_0; "%s\\"
0x180006dd4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006dd9  test    eax, eax
0x180006ddb  js      short loc_180006E26
0x180006ddd  movzx   ecx, [rsp+258h+var_232]
0x180006de2  test    cx, cx
0x180006de5  jz      short loc_180006E2B
0x180006de7  lea     rbx, [rsp+258h+var_232]
0x180006dec  lea     rdi, [rbx+2]
0x180006df0  cmp     cx, r14w
0x180006df4  jnz     short loc_180006E19
0x180006df6  cmp     [rdi], bp
0x180006df9  lea     rcx, [rsp+258h+PathName]; lpPathName
0x180006dfe  mov     rdx, rsi
0x180006e01  mov     [rbx], bp
0x180006e04  cmovnz  rdx, rbp; lpSecurityAttributes
0x180006e08  call    cs:__imp_CreateDirectoryW
0x180006e0e  mov     ecx, eax; int
0x180006e10  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180006e15  mov     [rbx], r14w
0x180006e19  mov     rbx, rdi
0x180006e1c  movzx   ecx, word ptr [rbx]
0x180006e1f  test    cx, cx
0x180006e22  jnz     short loc_180006DEC
0x180006e24  jmp     short loc_180006E2B
0x180006e26  mov     eax, 800700CEh
0x180006e2b  cmp     eax, 800700B7h
0x180006e30  mov     ecx, ebp
0x180006e32  cmovnz  ecx, eax
0x180006e35  jmp     short loc_180006E3C
0x180006e37  mov     ecx, 800700A1h
0x180006e3c  mov     eax, ecx
0x180006e3e  mov     rcx, [rsp+258h+var_28]
0x180006e46  xor     rcx, rsp; StackCookie
0x180006e49  call    __security_check_cookie
0x180006e4e  lea     r11, [rsp+258h+var_18]
0x180006e56  mov     rbx, [r11+30h]
0x180006e5a  mov     rbp, [r11+38h]
0x180006e5e  mov     rsp, r11
0x180006e61  pop     r14
0x180006e63  pop     rdi
0x180006e64  pop     rsi
0x180006e65  retn
```
