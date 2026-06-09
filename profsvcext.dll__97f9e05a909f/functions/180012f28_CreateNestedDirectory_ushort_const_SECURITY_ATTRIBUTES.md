# CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180012f28`
- end: `0x18001308d`
- name: `?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180012ea4`
- `0x18001a030`
- `0x18001d96c`

## callees

- `0x1800045d0`
- `0x180008e5c`
- `0x180008ea0`
- `0x18000a074`
- `0x18000a520`
- `0x1800102e0`
- `0x180012f28`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180012faa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001302f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180012faa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001302f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
  unsigned __int64 v15; // [rsp+20h] [rbp-248h] BYREF
  WCHAR PathName[3]; // [rsp+30h] [rbp-238h] BYREF
  __int16 v17; // [rsp+36h] [rbp-232h] BYREF

  v15 = 0;
  if ( (int)StringCchLengthW(a1, 0x7FFFFFFFu, &v15) >= 0
    && v15 >= 2
    && a1[1] == 58
    && ((unsigned __int16)(*a1 - 97) <= 0x19u || (unsigned __int16)(*a1 - 65) <= 0x19u)
    || (unsigned int)IsUNCPath(a1) )
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
        v7 = v17;
        if ( v17 )
        {
          v8 = &v17;
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
0x180012f28  mov     [rsp+arg_10], rbx
0x180012f2d  mov     [rsp+arg_18], rbp
0x180012f32  push    rsi
0x180012f33  push    rdi
0x180012f34  push    r14
0x180012f36  sub     rsp, 250h
0x180012f3d  mov     rax, cs:__security_cookie
0x180012f44  xor     rax, rsp
0x180012f47  mov     [rsp+268h+var_28], rax
0x180012f4f  mov     rsi, rdx
0x180012f52  lea     r8, [rsp+268h+var_248]; unsigned __int64 *
0x180012f57  xor     ebp, ebp
0x180012f59  mov     edx, 7FFFFFFFh; unsigned __int64
0x180012f5e  mov     [rsp+268h+var_248], rbp
0x180012f63  mov     rbx, rcx
0x180012f66  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180012f6b  test    eax, eax
0x180012f6d  js      short loc_180012F94
0x180012f6f  cmp     [rsp+268h+var_248], 2
0x180012f75  jb      short loc_180012F94
0x180012f77  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180012f7c  jnz     short loc_180012F94
0x180012f7e  movzx   ecx, word ptr [rbx]
0x180012f81  lea     eax, [rcx-61h]
0x180012f84  cmp     ax, 19h
0x180012f88  jbe     short loc_180012FA4
0x180012f8a  sub     cx, 41h ; 'A'
0x180012f8e  cmp     cx, 19h
0x180012f92  jbe     short loc_180012FA4
0x180012f94  mov     rcx, rbx; unsigned __int16 *
0x180012f97  call    ?IsUNCPath@@YAHPEBG@Z; IsUNCPath(ushort const *)
0x180012f9c  test    eax, eax
0x180012f9e  jz      loc_18001305E
0x180012fa4  mov     rdx, rsi; lpSecurityAttributes
0x180012fa7  mov     rcx, rbx; lpPathName
0x180012faa  call    cs:__imp_CreateDirectoryW
0x180012fb0  mov     ecx, eax; int
0x180012fb2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180012fb7  cmp     eax, 80070003h
0x180012fbc  jnz     loc_180013052
0x180012fc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012fc6  inc     rax
0x180012fc9  cmp     [rbx+rax*2], bp
0x180012fcd  jnz     short loc_180012FC6
0x180012fcf  mov     r14d, 5Ch ; '\'
0x180012fd5  lea     rcx, [rsp+268h+PathName]; unsigned __int16 *
0x180012fda  mov     edx, 104h; unsigned __int64
0x180012fdf  cmp     [rbx+rax*2-2], r14w
0x180012fe5  jnz     short loc_180012FF1
0x180012fe7  mov     r8, rbx; unsigned __int16 *
0x180012fea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012fef  jmp     short loc_180013000
0x180012ff1  mov     r9, rbx
0x180012ff4  lea     r8, aS; "%s\\"
0x180012ffb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013000  test    eax, eax
0x180013002  js      short loc_18001304D
0x180013004  movzx   ecx, [rsp+268h+var_232]
0x180013009  test    cx, cx
0x18001300c  jz      short loc_180013052
0x18001300e  lea     rbx, [rsp+268h+var_232]
0x180013013  lea     rdi, [rbx+2]
0x180013017  cmp     cx, r14w
0x18001301b  jnz     short loc_180013040
0x18001301d  cmp     [rdi], bp
0x180013020  lea     rcx, [rsp+268h+PathName]; lpPathName
0x180013025  mov     rdx, rsi
0x180013028  mov     [rbx], bp
0x18001302b  cmovnz  rdx, rbp; lpSecurityAttributes
0x18001302f  call    cs:__imp_CreateDirectoryW
0x180013035  mov     ecx, eax; int
0x180013037  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18001303c  mov     [rbx], r14w
0x180013040  mov     rbx, rdi
0x180013043  movzx   ecx, word ptr [rbx]
0x180013046  test    cx, cx
0x180013049  jnz     short loc_180013013
0x18001304b  jmp     short loc_180013052
0x18001304d  mov     eax, 800700CEh
0x180013052  cmp     eax, 800700B7h
0x180013057  mov     ecx, ebp
0x180013059  cmovnz  ecx, eax
0x18001305c  jmp     short loc_180013063
0x18001305e  mov     ecx, 800700A1h
0x180013063  mov     eax, ecx
0x180013065  mov     rcx, [rsp+268h+var_28]
0x18001306d  xor     rcx, rsp; StackCookie
0x180013070  call    __security_check_cookie
0x180013075  lea     r11, [rsp+268h+var_18]
0x18001307d  mov     rbx, [r11+30h]
0x180013081  mov     rbp, [r11+38h]
0x180013085  mov     rsp, r11
0x180013088  pop     r14
0x18001308a  pop     rdi
0x18001308b  pop     rsi
0x18001308c  retn
```
