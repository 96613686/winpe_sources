# WriteFileDSNW

- ea: `0x1800136b0`
- end: `0x1800137db`
- name: `WriteFileDSNW`
- size: `299`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const WCHAR *, const WCHAR *, const WCHAR *lpString)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18000a150`
- `0x180013270`

## callees

- `0x180002e14`
- `0x180004bac`
- `0x180012b14`
- `0x1800136b0`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `KERNEL32!WritePrivateProfileStringW` at `0x18001370d`
- `KERNEL32!WritePrivateProfileStringW` at `0x18001377a`
- `KERNEL32!WritePrivateProfileStringW` at `0x18001379b`
- `KERNEL32!WritePrivateProfileStringW` at `0x18001370d`
- `KERNEL32!WritePrivateProfileStringW` at `0x18001377a`
- `KERNEL32!WritePrivateProfileStringW` at `0x18001379b`

## pseudocode

```c
__int64 __fastcall WriteFileDSNW(
        __int64 a1,
        const wchar_t *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        const WCHAR *lpString)
{
  unsigned __int64 v8; // rcx
  int v9; // ecx
  unsigned int v10; // r11d
  __int64 v11; // rcx
  unsigned __int16 v12; // bx
  WCHAR FileName; // [rsp+20h] [rbp-448h] BYREF
  _BYTE v15[1038]; // [rsp+22h] [rbp-446h] BYREF

  FileName = 0;
  memset_0(v15, 0, sizeof(v15));
  WritePrivateProfileStringW(0, 0, 0, &FileName);
  if ( !a2 )
    goto LABEL_11;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( v8 > 0x104 )
  {
LABEL_11:
    v9 = 12;
    goto LABEL_12;
  }
  if ( !a3 )
  {
    v9 = 5;
LABEL_12:
    PostInstError(v9);
    return 0xFFFF;
  }
  StringCchCopyW(&FileName, 0x208u, a2);
  v12 = EnforceDSNExtension(v11, &FileName, v10);
  if ( v12 == 0xFFFF )
    return 0xFFFF;
  if ( !WritePrivateProfileStringW(a3, a4, lpString, &FileName) )
  {
    v12 = -1;
    PostInstError(12);
  }
  WritePrivateProfileStringW(0, 0, 0, &FileName);
  return v12;
}

```

## disassembly

```asm
0x1800136b0  mov     [rsp+arg_0], rbx
0x1800136b5  push    rbp
0x1800136b6  push    rsi
0x1800136b7  push    rdi
0x1800136b8  push    r14
0x1800136ba  push    r15
0x1800136bc  sub     rsp, 440h
0x1800136c3  mov     rax, cs:__security_cookie
0x1800136ca  xor     rax, rsp
0x1800136cd  mov     [rsp+468h+var_38], rax
0x1800136d5  mov     rbp, [rsp+468h+lpString]
0x1800136dd  lea     rcx, [rsp+468h+var_446]; void *
0x1800136e2  mov     rdi, r8
0x1800136e5  mov     rbx, rdx
0x1800136e8  xor     r15d, r15d
0x1800136eb  xor     edx, edx; Val
0x1800136ed  mov     r8d, 40Eh; Size
0x1800136f3  mov     [rsp+468h+FileName], r15w
0x1800136f9  mov     rsi, r9
0x1800136fc  call    memset_0
0x180013701  lea     r9, [rsp+468h+FileName]; lpFileName
0x180013706  xor     r8d, r8d; lpString
0x180013709  xor     edx, edx; lpKeyName
0x18001370b  xor     ecx, ecx; lpAppName
0x18001370d  call    cs:__imp_WritePrivateProfileStringW
0x180013713  or      r14, 0FFFFFFFFFFFFFFFFh
0x180013717  test    rbx, rbx
0x18001371a  jz      loc_1800137A6
0x180013720  mov     rcx, r14
0x180013723  inc     rcx
0x180013726  cmp     [rbx+rcx*2], r15w
0x18001372b  jnz     short loc_180013723
0x18001372d  cmp     rcx, 104h
0x180013734  ja      short loc_1800137A6
0x180013736  test    rdi, rdi
0x180013739  jnz     short loc_180013740
0x18001373b  lea     ecx, [rdi+5]
0x18001373e  jmp     short loc_1800137AB
0x180013740  mov     r11d, 208h
0x180013746  lea     rcx, [rsp+468h+FileName]; pszDest
0x18001374b  mov     edx, r11d; cchDest
0x18001374e  mov     r8, rbx; pszSrc
0x180013751  call    StringCchCopyW
0x180013756  mov     r8d, r11d
0x180013759  lea     rdx, [rsp+468h+FileName]
0x18001375e  call    EnforceDSNExtension
0x180013763  movzx   ebx, ax
0x180013766  cmp     ax, r14w
0x18001376a  jz      short loc_1800137B0
0x18001376c  lea     r9, [rsp+468h+FileName]; lpFileName
0x180013771  mov     r8, rbp; lpString
0x180013774  mov     rdx, rsi; lpKeyName
0x180013777  mov     rcx, rdi; lpAppName
0x18001377a  call    cs:__imp_WritePrivateProfileStringW
0x180013780  test    eax, eax
0x180013782  jnz     short loc_18001378F
0x180013784  lea     ecx, [rax+0Ch]
0x180013787  mov     ebx, r14d
0x18001378a  call    PostInstError
0x18001378f  lea     r9, [rsp+468h+FileName]; lpFileName
0x180013794  xor     r8d, r8d; lpString
0x180013797  xor     edx, edx; lpKeyName
0x180013799  xor     ecx, ecx; lpAppName
0x18001379b  call    cs:__imp_WritePrivateProfileStringW
0x1800137a1  movzx   eax, bx
0x1800137a4  jmp     short loc_1800137B4
0x1800137a6  mov     ecx, 0Ch
0x1800137ab  call    PostInstError
0x1800137b0  movzx   eax, r14w
0x1800137b4  mov     rcx, [rsp+468h+var_38]
0x1800137bc  xor     rcx, rsp; StackCookie
0x1800137bf  call    __security_check_cookie
0x1800137c4  mov     rbx, [rsp+468h+arg_0]
0x1800137cc  add     rsp, 440h
0x1800137d3  pop     r15
0x1800137d5  pop     r14
0x1800137d7  pop     rdi
0x1800137d8  pop     rsi
0x1800137d9  pop     rbp
0x1800137da  retn
```
