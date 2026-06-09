# CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180016834`
- end: `0x180016959`
- name: `?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000caa0`

## callees

- `0x180003330`
- `0x1800063e0`
- `0x180009900`
- `0x18000a540`
- `0x18000fa10`
- `0x180016834`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016876`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800168fb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016876`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800168fb`

## pseudocode

```c
__int64 __fastcall CreateNestedDirectory(const unsigned __int16 *a1, LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  BOOL DirectoryW; // eax
  int v5; // eax
  __int64 v6; // rax
  __int16 v7; // cx
  __int16 *v8; // rbx
  __int16 *v9; // rdi
  bool v10; // zf
  struct _SECURITY_ATTRIBUTES *v11; // rdx
  BOOL v12; // eax
  unsigned int v13; // ecx
  WCHAR PathName[3]; // [rsp+20h] [rbp-238h] BYREF
  __int16 v16; // [rsp+26h] [rbp-232h] BYREF

  if ( (unsigned int)IsFullPath(a1) )
  {
    DirectoryW = CreateDirectoryW(a1, lpSecurityAttributes);
    v5 = ResultFromWin32Bool(DirectoryW);
    if ( v5 == -2147024893 )
    {
      v6 = -1;
      do
        ++v6;
      while ( a1[v6] );
      if ( a1[v6 - 1] == 92 )
        v5 = StringCchCopyW(PathName, 0x104u, a1);
      else
        v5 = StringCchPrintfW(PathName, 0x104u, L"%s\\", a1);
      if ( v5 < 0 )
      {
        v5 = -2147024690;
      }
      else
      {
        v7 = v16;
        if ( v16 )
        {
          v8 = &v16;
          do
          {
            v9 = v8 + 1;
            if ( v7 == 92 )
            {
              v10 = *v9 == 0;
              v11 = lpSecurityAttributes;
              *v8 = 0;
              if ( !v10 )
                v11 = 0;
              v12 = CreateDirectoryW(PathName, v11);
              v5 = ResultFromWin32Bool(v12);
              *v8 = 92;
            }
            ++v8;
            v7 = *v9;
          }
          while ( *v9 );
        }
      }
    }
    v13 = 0;
    if ( v5 != -2147024713 )
      return (unsigned int)v5;
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
0x180016834  mov     [rsp+arg_10], rbx
0x180016839  mov     [rsp+arg_18], rbp
0x18001683e  push    rsi
0x18001683f  push    rdi
0x180016840  push    r14
0x180016842  sub     rsp, 240h
0x180016849  mov     rax, cs:__security_cookie
0x180016850  xor     rax, rsp
0x180016853  mov     [rsp+258h+var_28], rax
0x18001685b  mov     rsi, rdx
0x18001685e  mov     rbx, rcx
0x180016861  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x180016866  xor     ebp, ebp
0x180016868  test    eax, eax
0x18001686a  jz      loc_18001692A
0x180016870  mov     rdx, rsi; lpSecurityAttributes
0x180016873  mov     rcx, rbx; lpPathName
0x180016876  call    cs:__imp_CreateDirectoryW
0x18001687c  mov     ecx, eax; int
0x18001687e  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180016883  cmp     eax, 80070003h
0x180016888  jnz     loc_18001691E
0x18001688e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016892  inc     rax
0x180016895  cmp     [rbx+rax*2], bp
0x180016899  jnz     short loc_180016892
0x18001689b  mov     r14d, 5Ch ; '\'
0x1800168a1  lea     rcx, [rsp+258h+PathName]; unsigned __int16 *
0x1800168a6  mov     edx, 104h; unsigned __int64
0x1800168ab  cmp     [rbx+rax*2-2], r14w
0x1800168b1  jnz     short loc_1800168BD
0x1800168b3  mov     r8, rbx; unsigned __int16 *
0x1800168b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800168bb  jmp     short loc_1800168CC
0x1800168bd  mov     r9, rbx
0x1800168c0  lea     r8, aS; "%s\\"
0x1800168c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800168cc  test    eax, eax
0x1800168ce  js      short loc_180016919
0x1800168d0  movzx   ecx, [rsp+258h+var_232]
0x1800168d5  test    cx, cx
0x1800168d8  jz      short loc_18001691E
0x1800168da  lea     rbx, [rsp+258h+var_232]
0x1800168df  lea     rdi, [rbx+2]
0x1800168e3  cmp     cx, r14w
0x1800168e7  jnz     short loc_18001690C
0x1800168e9  cmp     [rdi], bp
0x1800168ec  lea     rcx, [rsp+258h+PathName]; lpPathName
0x1800168f1  mov     rdx, rsi
0x1800168f4  mov     [rbx], bp
0x1800168f7  cmovnz  rdx, rbp; lpSecurityAttributes
0x1800168fb  call    cs:__imp_CreateDirectoryW
0x180016901  mov     ecx, eax; int
0x180016903  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180016908  mov     [rbx], r14w
0x18001690c  mov     rbx, rdi
0x18001690f  movzx   ecx, word ptr [rbx]
0x180016912  test    cx, cx
0x180016915  jnz     short loc_1800168DF
0x180016917  jmp     short loc_18001691E
0x180016919  mov     eax, 800700CEh
0x18001691e  cmp     eax, 800700B7h
0x180016923  mov     ecx, ebp
0x180016925  cmovnz  ecx, eax
0x180016928  jmp     short loc_18001692F
0x18001692a  mov     ecx, 800700A1h
0x18001692f  mov     eax, ecx
0x180016931  mov     rcx, [rsp+258h+var_28]
0x180016939  xor     rcx, rsp; StackCookie
0x18001693c  call    __security_check_cookie
0x180016941  lea     r11, [rsp+258h+var_18]
0x180016949  mov     rbx, [r11+30h]
0x18001694d  mov     rbp, [r11+38h]
0x180016951  mov     rsp, r11
0x180016954  pop     r14
0x180016956  pop     rdi
0x180016957  pop     rsi
0x180016958  retn
```
