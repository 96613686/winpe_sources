# EnforceDSNExtension

- ea: `0x180012b14`
- end: `0x180012c90`
- name: `EnforceDSNExtension`
- size: `380`
- prototype: `__int64 __fastcall(__int64, wchar_t *, size_t)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180004800`
- `0x180012e90`
- `0x180013270`
- `0x1800135e4`
- `0x1800136b0`

## callees

- `0x180002e14`
- `0x180004afc`
- `0x180004bac`
- `0x180012b14`
- `0x180012c98`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012b66`
- `msvcrt!_wcsicmp` at `0x180012b66`
- `msvcrt!_wsplitpath_s` at `0x180012bc9`
- `msvcrt!_wsplitpath_s` at `0x180012bc9`

## pseudocode

```c
__int64 __fastcall EnforceDSNExtension(__int64 a1, wchar_t *a2, size_t a3)
{
  unsigned __int64 v4; // rbx
  __int64 v6; // rcx
  wchar_t Dir[264]; // [rsp+50h] [rbp-458h] BYREF
  wchar_t Drive[264]; // [rsp+260h] [rbp-248h] BYREF

  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( v4 < 4 )
  {
LABEL_6:
    StringCchCopyW(&a2[v4], a3 - v4, L".dsn");
    v4 += 4LL;
    goto LABEL_7;
  }
  if ( _wcsicmp(L".dsn", &a2[v4 - 4]) )
  {
    if ( v4 >= 0x100 )
      goto LABEL_18;
    goto LABEL_6;
  }
LABEL_7:
  _wsplitpath_s(a2, Drive, 0x104u, Dir, 0x104u, 0, 0, 0, 0);
  if ( Drive[0] || Dir[0] )
    return 0;
  GetFileDsnDir(Dir, 0x104u);
  v6 = -1;
  do
    ++v6;
  while ( Dir[v6] );
  if ( v4 < 260 - v6 )
  {
    if ( !v6 || Dir[v6 - 1] == 92 )
      goto LABEL_16;
    if ( v4 < 259 - v6 )
    {
      StringCchCatW(Dir, 0x104u, L"\\");
LABEL_16:
      StringCchCatW(Dir, 0x104u, a2);
      StringCchCopyW(a2, a3, Dir);
      return 0;
    }
  }
LABEL_18:
  PostInstError(12);
  return 0xFFFF;
}

```

## disassembly

```asm
0x180012b14  mov     [rsp+arg_0], rbx
0x180012b19  push    rbp
0x180012b1a  push    rsi
0x180012b1b  push    rdi
0x180012b1c  push    r14
0x180012b1e  push    r15
0x180012b20  sub     rsp, 480h
0x180012b27  mov     rax, cs:__security_cookie
0x180012b2e  xor     rax, rsp
0x180012b31  mov     [rsp+4A8h+var_38], rax
0x180012b39  or      r15, 0FFFFFFFFFFFFFFFFh
0x180012b3d  mov     rsi, r8
0x180012b40  mov     rbx, r15
0x180012b43  xor     ebp, ebp
0x180012b45  mov     rdi, rdx
0x180012b48  inc     rbx
0x180012b4b  cmp     [rdx+rbx*2], bp
0x180012b4f  jnz     short loc_180012B48
0x180012b51  cmp     rbx, 4
0x180012b55  jb      short loc_180012B7D
0x180012b57  add     rdx, 0FFFFFFFFFFFFFFF8h
0x180012b5b  lea     rcx, aDsn_1; ".dsn"
0x180012b62  lea     rdx, [rdx+rbx*2]; String2
0x180012b66  call    cs:__imp__wcsicmp
0x180012b6c  test    eax, eax
0x180012b6e  jz      short loc_180012B97
0x180012b70  cmp     rbx, 100h
0x180012b77  jnb     loc_180012C80
0x180012b7d  mov     rdx, rsi
0x180012b80  lea     r8, aDsn_1; ".dsn"
0x180012b87  sub     rdx, rbx; cchDest
0x180012b8a  lea     rcx, [rdi+rbx*2]; pszDest
0x180012b8e  call    StringCchCopyW
0x180012b93  add     rbx, 4
0x180012b97  mov     [rsp+4A8h+ExtCount], rbp; ExtCount
0x180012b9c  lea     r9, [rsp+4A8h+Dir]; Dir
0x180012ba1  mov     [rsp+4A8h+Ext], rbp; Ext
0x180012ba6  lea     rdx, [rsp+4A8h+Drive]; Drive
0x180012bae  mov     r14d, 104h
0x180012bb4  mov     [rsp+4A8h+FilenameCount], rbp; FilenameCount
0x180012bb9  mov     [rsp+4A8h+Filename], rbp; Filename
0x180012bbe  mov     r8d, r14d; DriveCount
0x180012bc1  mov     rcx, rdi; FullPath
0x180012bc4  mov     [rsp+4A8h+DirCount], r14; DirCount
0x180012bc9  call    cs:__imp__wsplitpath_s
0x180012bcf  cmp     [rsp+4A8h+Drive], bp
0x180012bd7  jnz     short loc_180012C57
0x180012bd9  cmp     [rsp+4A8h+Dir], bp
0x180012bde  jnz     short loc_180012C57
0x180012be0  mov     edx, r14d; uSize
0x180012be3  lea     rcx, [rsp+4A8h+Dir]; lpBuffer
0x180012be8  call    GetFileDsnDir
0x180012bed  lea     rax, [rsp+4A8h+Dir]
0x180012bf2  mov     rcx, r15
0x180012bf5  inc     rcx
0x180012bf8  cmp     [rax+rcx*2], bp
0x180012bfc  jnz     short loc_180012BF5
0x180012bfe  mov     rax, r14
0x180012c01  sub     rax, rcx
0x180012c04  cmp     rbx, rax
0x180012c07  jnb     short loc_180012C80
0x180012c09  test    rcx, rcx
0x180012c0c  jz      short loc_180012C37
0x180012c0e  cmp     [rsp+rcx*2+4A8h+var_45A], 5Ch ; '\'
0x180012c14  jz      short loc_180012C37
0x180012c16  mov     eax, 103h
0x180012c1b  sub     rax, rcx
0x180012c1e  cmp     rbx, rax
0x180012c21  jnb     short loc_180012C80
0x180012c23  lea     r8, SubBlock; "\\"
0x180012c2a  mov     rdx, r14; cchDest
0x180012c2d  lea     rcx, [rsp+4A8h+Dir]; pszDest
0x180012c32  call    StringCchCatW
0x180012c37  mov     r8, rdi; pszSrc
0x180012c3a  lea     rcx, [rsp+4A8h+Dir]; pszDest
0x180012c3f  mov     rdx, r14; cchDest
0x180012c42  call    StringCchCatW
0x180012c47  lea     r8, [rsp+4A8h+Dir]; pszSrc
0x180012c4c  mov     rdx, rsi; cchDest
0x180012c4f  mov     rcx, rdi; pszDest
0x180012c52  call    StringCchCopyW
0x180012c57  mov     eax, ebp
0x180012c59  mov     rcx, [rsp+4A8h+var_38]
0x180012c61  xor     rcx, rsp; StackCookie
0x180012c64  call    __security_check_cookie
0x180012c69  mov     rbx, [rsp+4A8h+arg_0]
0x180012c71  add     rsp, 480h
0x180012c78  pop     r15
0x180012c7a  pop     r14
0x180012c7c  pop     rdi
0x180012c7d  pop     rsi
0x180012c7e  pop     rbp
0x180012c7f  retn
0x180012c80  mov     ecx, 0Ch
0x180012c85  call    PostInstError
0x180012c8a  movzx   eax, r15w
0x180012c8e  jmp     short loc_180012C59
```
