# CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180010c70`
- end: `0x180010d9f`
- name: `?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180010734`
- `0x180016150`
- `0x180040e94`

## callees

- `0x180010c70`
- `0x180011c00`
- `0x1800172e0`
- `0x180024540`
- `0x1800336f4`
- `0x18003bc70`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010caf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010d3a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010caf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010d3a`

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
0x180010c70  mov     [rsp+arg_10], rbx
0x180010c75  mov     [rsp+arg_18], rbp
0x180010c7a  push    rsi
0x180010c7b  push    rdi
0x180010c7c  push    r14
0x180010c7e  sub     rsp, 240h
0x180010c85  mov     rax, cs:__security_cookie
0x180010c8c  xor     rax, rsp
0x180010c8f  mov     [rsp+258h+var_28], rax
0x180010c97  mov     rsi, rdx
0x180010c9a  mov     rbx, rcx
0x180010c9d  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x180010ca2  xor     ebp, ebp
0x180010ca4  test    eax, eax
0x180010ca6  jz      loc_180010D6F
0x180010cac  mov     rdx, rsi; lpSecurityAttributes
0x180010caf  call    cs:__imp_CreateDirectoryW
0x180010cb6  nop     dword ptr [rax+rax+00h]
0x180010cbb  mov     ecx, eax; int
0x180010cbd  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180010cc2  cmp     eax, 80070003h
0x180010cc7  jnz     loc_180010D63
0x180010ccd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010cd1  inc     rax
0x180010cd4  cmp     [rbx+rax*2], bp
0x180010cd8  jnz     short loc_180010CD1
0x180010cda  mov     r14d, 5Ch ; '\'
0x180010ce0  lea     rcx, [rsp+258h+PathName]; unsigned __int16 *
0x180010ce5  mov     edx, 104h; unsigned __int64
0x180010cea  cmp     [rbx+rax*2-2], r14w
0x180010cf0  jnz     short loc_180010CFC
0x180010cf2  mov     r8, rbx; unsigned __int16 *
0x180010cf5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010cfa  jmp     short loc_180010D0B
0x180010cfc  mov     r9, rbx
0x180010cff  lea     r8, aS_0; "%s\\"
0x180010d06  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010d0b  test    eax, eax
0x180010d0d  js      short loc_180010D5E
0x180010d0f  movzx   ecx, [rsp+258h+var_232]
0x180010d14  test    cx, cx
0x180010d17  jz      short loc_180010D63
0x180010d19  lea     rbx, [rsp+258h+var_232]
0x180010d1e  lea     rdi, [rbx+2]
0x180010d22  cmp     cx, r14w
0x180010d26  jnz     short loc_180010D51
0x180010d28  cmp     [rdi], bp
0x180010d2b  lea     rcx, [rsp+258h+PathName]; lpPathName
0x180010d30  mov     rdx, rsi
0x180010d33  mov     [rbx], bp
0x180010d36  cmovnz  rdx, rbp; lpSecurityAttributes
0x180010d3a  call    cs:__imp_CreateDirectoryW
0x180010d41  nop     dword ptr [rax+rax+00h]
0x180010d46  mov     ecx, eax; int
0x180010d48  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180010d4d  mov     [rbx], r14w
0x180010d51  mov     rbx, rdi
0x180010d54  movzx   ecx, word ptr [rbx]
0x180010d57  test    cx, cx
0x180010d5a  jnz     short loc_180010D1E
0x180010d5c  jmp     short loc_180010D63
0x180010d5e  mov     eax, 800700CEh
0x180010d63  cmp     eax, 800700B7h
0x180010d68  mov     ecx, ebp
0x180010d6a  cmovnz  ecx, eax
0x180010d6d  jmp     short loc_180010D74
0x180010d6f  mov     ecx, 800700A1h
0x180010d74  mov     eax, ecx
0x180010d76  mov     rcx, [rsp+258h+var_28]
0x180010d7e  xor     rcx, rsp; StackCookie
0x180010d81  call    __security_check_cookie
0x180010d86  lea     r11, [rsp+258h+var_18]
0x180010d8e  mov     rbx, [r11+30h]
0x180010d92  mov     rbp, [r11+38h]
0x180010d96  mov     rsp, r11
0x180010d99  pop     r14
0x180010d9b  pop     rdi
0x180010d9c  pop     rsi
0x180010d9d  retn
```
