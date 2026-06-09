# CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180010d5c`
- end: `0x180010e84`
- name: `?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000ad78`
- `0x1800105f0`
- `0x180010810`

## callees

- `0x180004030`
- `0x180006400`
- `0x180010d5c`
- `0x18001a784`
- `0x18001d2f0`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010d97`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010e1c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010d97`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180010e1c`

## pseudocode

```c
__int64 __fastcall CreateNestedDirectory(const unsigned __int16 *a1, struct _SECURITY_ATTRIBUTES *a2)
{
  int Error; // eax
  __int64 v4; // rax
  __int16 v5; // cx
  __int16 *v6; // rbx
  unsigned int v7; // ecx
  WCHAR PathName[3]; // [rsp+20h] [rbp-228h] BYREF
  __int16 v10; // [rsp+26h] [rbp-222h] BYREF

  if ( (unsigned int)IsFullPath(a1) )
  {
    if ( CreateDirectoryW(a1, 0) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error == -2147024893 )
      {
        v4 = -1;
        do
          ++v4;
        while ( a1[v4] );
        if ( a1[v4 - 1] == 92 )
          Error = StringCchCopyW(PathName, 0x104u, a1);
        else
          Error = StringCchPrintfW(PathName, 0x104u, L"%s\\", a1);
        if ( Error < 0 )
        {
          Error = -2147024690;
        }
        else
        {
          v5 = v10;
          if ( v10 )
          {
            v6 = &v10;
            do
            {
              if ( v5 == 92 )
              {
                *v6 = 0;
                if ( CreateDirectoryW(PathName, 0) )
                  Error = 0;
                else
                  Error = ResultFromKnownLastError();
                *v6 = 92;
              }
              v5 = *++v6;
            }
            while ( *v6 );
          }
        }
      }
    }
    v7 = 0;
    if ( Error != -2147024713 )
      return (unsigned int)Error;
  }
  else
  {
    return (unsigned int)-2147024735;
  }
  return v7;
}

```

## disassembly

```asm
0x180010d5c  mov     [rsp+arg_8], rbx
0x180010d61  mov     [rsp+arg_10], rsi
0x180010d66  push    rdi
0x180010d67  sub     rsp, 240h
0x180010d6e  mov     rax, cs:__security_cookie
0x180010d75  xor     rax, rsp
0x180010d78  mov     [rsp+248h+var_18], rax
0x180010d80  mov     rbx, rcx
0x180010d83  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x180010d88  xor     edi, edi
0x180010d8a  test    eax, eax
0x180010d8c  jz      loc_180010E57
0x180010d92  xor     edx, edx; lpSecurityAttributes
0x180010d94  mov     rcx, rbx; lpPathName
0x180010d97  call    cs:__imp_CreateDirectoryW
0x180010d9e  nop     dword ptr [rax+rax+00h]
0x180010da3  test    eax, eax
0x180010da5  jz      short loc_180010DAE
0x180010da7  mov     eax, edi
0x180010da9  jmp     loc_180010E4B
0x180010dae  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180010db3  cmp     eax, 80070003h
0x180010db8  jnz     loc_180010E4B
0x180010dbe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010dc2  inc     rax
0x180010dc5  cmp     [rbx+rax*2], di
0x180010dc9  jnz     short loc_180010DC2
0x180010dcb  mov     esi, 5Ch ; '\'
0x180010dd0  lea     rcx, [rsp+248h+PathName]; unsigned __int16 *
0x180010dd5  mov     edx, 104h; unsigned __int64
0x180010dda  cmp     [rbx+rax*2-2], si
0x180010ddf  jnz     short loc_180010DEB
0x180010de1  mov     r8, rbx; unsigned __int16 *
0x180010de4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010de9  jmp     short loc_180010DFA
0x180010deb  mov     r9, rbx
0x180010dee  lea     r8, aS_0; "%s\\"
0x180010df5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010dfa  test    eax, eax
0x180010dfc  js      short loc_180010E46
0x180010dfe  movzx   ecx, [rsp+248h+var_222]
0x180010e03  test    cx, cx
0x180010e06  jz      short loc_180010E4B
0x180010e08  lea     rbx, [rsp+248h+var_222]
0x180010e0d  cmp     cx, si
0x180010e10  jnz     short loc_180010E38
0x180010e12  xor     edx, edx; lpSecurityAttributes
0x180010e14  mov     [rbx], di
0x180010e17  lea     rcx, [rsp+248h+PathName]; lpPathName
0x180010e1c  call    cs:__imp_CreateDirectoryW
0x180010e23  nop     dword ptr [rax+rax+00h]
0x180010e28  test    eax, eax
0x180010e2a  jz      short loc_180010E30
0x180010e2c  mov     eax, edi
0x180010e2e  jmp     short loc_180010E35
0x180010e30  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180010e35  mov     [rbx], si
0x180010e38  add     rbx, 2
0x180010e3c  movzx   ecx, word ptr [rbx]
0x180010e3f  test    cx, cx
0x180010e42  jnz     short loc_180010E0D
0x180010e44  jmp     short loc_180010E4B
0x180010e46  mov     eax, 800700CEh
0x180010e4b  cmp     eax, 800700B7h
0x180010e50  mov     ecx, edi
0x180010e52  cmovnz  ecx, eax
0x180010e55  jmp     short loc_180010E5C
0x180010e57  mov     ecx, 800700A1h
0x180010e5c  mov     eax, ecx
0x180010e5e  mov     rcx, [rsp+248h+var_18]
0x180010e66  xor     rcx, rsp; StackCookie
0x180010e69  call    __security_check_cookie
0x180010e6e  lea     r11, [rsp+248h+var_8]
0x180010e76  mov     rbx, [r11+18h]
0x180010e7a  mov     rsi, [r11+20h]
0x180010e7e  mov     rsp, r11
0x180010e81  pop     rdi
0x180010e82  retn
```
