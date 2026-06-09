# ReadFileDSNW

- ea: `0x180012e90`
- end: `0x1800131a6`
- name: `ReadFileDSNW`
- size: `790`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const WCHAR *, const WCHAR *, WCHAR *lpReturnedString, unsigned __int16, _WORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180009750`
- `0x18000c440`

## callees

- `0x180002940`
- `0x180002e14`
- `0x180004bac`
- `0x180012b14`
- `0x180012e90`
- `0x1800135e4`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180013054`
- `msvcrt!_wcsicmp` at `0x180013054`
- `msvcrt!malloc` at `0x1800130a1`
- `msvcrt!malloc` at `0x1800130a1`
- `KERNEL32!GetPrivateProfileStringW` at `0x180012fcc`
- `KERNEL32!GetPrivateProfileStringW` at `0x18001302e`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800130d3`
- `KERNEL32!GetPrivateProfileStringW` at `0x180012fcc`
- `KERNEL32!GetPrivateProfileStringW` at `0x18001302e`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800130d3`

## pseudocode

```c
__int64 __fastcall ReadFileDSNW(
        __int64 a1,
        const wchar_t *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        WCHAR *lpReturnedString,
        unsigned __int16 a6,
        _WORD *a7)
{
  WCHAR *v7; // r14
  const WCHAR *v8; // rsi
  int v11; // ecx
  unsigned __int64 v12; // rax
  __int64 v14; // rcx
  size_t v15; // r11
  __int64 v16; // rcx
  unsigned __int16 v17; // di
  int v18; // ecx
  WCHAR *v19; // rax
  int v20; // edx
  int v21; // ecx
  DWORD nSize; // r13d
  DWORD PrivateProfileStringW; // eax
  __int16 v24; // r9
  DWORD v25; // ebp
  DWORD v26; // r15d
  int v27; // eax
  int v28; // ecx
  size_t v29; // r15
  WCHAR *v30; // rsi
  DWORD v31; // eax
  WCHAR *v32; // rcx
  WCHAR v33; // ax
  int v34; // [rsp+30h] [rbp-4C8h]
  DWORD v35; // [rsp+34h] [rbp-4C4h]
  WCHAR ReturnedString; // [rsp+50h] [rbp-4A8h] BYREF
  char v38[78]; // [rsp+52h] [rbp-4A6h] BYREF
  wchar_t pszDest[520]; // [rsp+A0h] [rbp-458h] BYREF

  v7 = lpReturnedString;
  v8 = a3;
  ReturnedString = 0;
  memset_0(v38, 0, sizeof(v38));
  if ( !a2 || !*a2 )
  {
    v11 = 12;
    goto LABEL_46;
  }
  if ( a4 && !v8 )
  {
    v11 = 5;
LABEL_46:
    PostInstError(v11);
    return -1;
  }
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  if ( v12 < 0x208 )
  {
    StringCchCopyW(pszDest, 0x208u, a2);
    v17 = EnforceDSNExtension(v14, pszDest, v15);
    if ( v17 != 0xFFFF )
    {
      v17 = ValidateFileDSNName(v16, pszDest);
      if ( (v17 & 0xFFFE) == 0 )
      {
        if ( lpReturnedString )
        {
          GetPrivateProfileStringW(v8, a4, aE527f950Fae511, &ReturnedString, 0x28u, pszDest);
          v19 = aE527f950Fae511;
          do
          {
            v20 = *(WCHAR *)((char *)v19 + (char *)&ReturnedString - (char *)aE527f950Fae511);
            v21 = *v19 - v20;
            if ( v21 )
              break;
            ++v19;
          }
          while ( v20 );
          if ( v21 )
          {
            nSize = a6;
            PrivateProfileStringW = GetPrivateProfileStringW(v8, a4, aE527f950Fae511, lpReturnedString, a6, pszDest);
            v24 = 0;
            v35 = PrivateProfileStringW;
            v25 = PrivateProfileStringW;
            v26 = PrivateProfileStringW;
            if ( !a4 || (v27 = _wcsicmp(a4, L"PWD"), v24 = 0, v34 = 1, v27) )
              v34 = 0;
            while ( 1 )
            {
              if ( !v8 || (v28 = 1, !a4) )
                v28 = 2;
              if ( v25 != nSize - v28 )
                break;
              nSize *= 2;
              if ( nSize > 0x7FFF || (v29 = 2LL * nSize, (v30 = (WCHAR *)malloc(v29)) == 0) )
              {
                v17 = -1;
                v18 = 21;
                goto LABEL_14;
              }
              v31 = GetPrivateProfileStringW(a3, a4, &SubKey, v30, nSize, pszDest);
              v32 = v30;
              v25 = v31;
              if ( v34 && v29 )
              {
                do
                {
                  *(_BYTE *)v30 = 0;
                  v30 = (WCHAR *)((char *)v30 + 1);
                  --v29;
                }
                while ( v29 );
              }
              OFree(v32);
              v26 = v35;
              v24 = 0;
              if ( v25 == v35 )
                goto LABEL_37;
              v8 = a3;
            }
            if ( v26 != v25 )
            {
              v17 = 1;
              PostInstError(22);
            }
LABEL_37:
            if ( v25 && !a4 )
            {
              while ( 1 )
              {
                if ( *v7 == v24 )
                {
                  v33 = v7[1];
                  *v7 = 59;
                  if ( !v33 )
                    break;
                }
                ++v7;
              }
            }
            if ( a7 )
              *a7 = v25;
          }
          else
          {
            PostInstError(11);
            return (unsigned __int16)-1;
          }
        }
        else
        {
          v17 = -1;
          v18 = 2;
LABEL_14:
          PostInstError(v18);
        }
      }
    }
    return v17;
  }
  else
  {
    PostInstError(9);
    return 0xFFFF;
  }
}

```

## disassembly

```asm
0x180012e90  mov     [rsp+arg_0], rbx
0x180012e95  push    rbp
0x180012e96  push    rsi
0x180012e97  push    rdi
0x180012e98  push    r12
0x180012e9a  push    r13
0x180012e9c  push    r14
0x180012e9e  push    r15
0x180012ea0  sub     rsp, 4C0h
0x180012ea7  mov     rax, cs:__security_cookie
0x180012eae  xor     rax, rsp
0x180012eb1  mov     [rsp+4F8h+var_48], rax
0x180012eb9  mov     rax, [rsp+4F8h+arg_30]
0x180012ec1  lea     rcx, [rsp+4F8h+var_4A6]; void *
0x180012ec6  mov     r14, [rsp+4F8h+lpReturnedString]
0x180012ece  xor     ebp, ebp
0x180012ed0  mov     rsi, r8
0x180012ed3  mov     [rsp+4F8h+lpAppName], r8
0x180012ed8  mov     rdi, rdx
0x180012edb  mov     [rsp+4F8h+var_4B8], rax
0x180012ee0  xor     edx, edx; Val
0x180012ee2  mov     [rsp+4F8h+ReturnedString], bp
0x180012ee7  lea     r8d, [rbp+4Eh]; Size
0x180012eeb  mov     r12, r9
0x180012eee  call    memset_0
0x180012ef3  test    rdi, rdi
0x180012ef6  jz      loc_18001316D
0x180012efc  cmp     [rdi], bp
0x180012eff  jz      loc_18001316D
0x180012f05  test    r12, r12
0x180012f08  jz      short loc_180012F17
0x180012f0a  test    rsi, rsi
0x180012f0d  jnz     short loc_180012F17
0x180012f0f  lea     ecx, [rsi+5]
0x180012f12  jmp     loc_180013172
0x180012f17  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012f1b  mov     rax, rbx
0x180012f1e  inc     rax
0x180012f21  cmp     [rdi+rax*2], bp
0x180012f25  jnz     short loc_180012F1E
0x180012f27  mov     r11d, 208h
0x180012f2d  cmp     rax, r11
0x180012f30  jb      short loc_180012F44
0x180012f32  mov     ecx, 9
0x180012f37  call    PostInstError
0x180012f3c  movzx   eax, bx
0x180012f3f  jmp     loc_18001317B
0x180012f44  mov     r8, rdi; pszSrc
0x180012f47  lea     rcx, [rsp+4F8h+pszDest]; pszDest
0x180012f4f  mov     rdx, r11; cchDest
0x180012f52  call    StringCchCopyW
0x180012f57  mov     r8, r11
0x180012f5a  lea     rdx, [rsp+4F8h+pszDest]
0x180012f62  call    EnforceDSNExtension
0x180012f67  movzx   edi, ax
0x180012f6a  cmp     ax, bx
0x180012f6d  jz      loc_180013168
0x180012f73  lea     rdx, [rsp+4F8h+pszDest]
0x180012f7b  call    ValidateFileDSNName
0x180012f80  movzx   edi, ax
0x180012f83  test    ax, 0FFFEh
0x180012f87  jnz     loc_180013168
0x180012f8d  test    r14, r14
0x180012f90  jnz     short loc_180012FA2
0x180012f92  mov     edi, ebx
0x180012f94  lea     ecx, [r14+2]
0x180012f98  call    PostInstError
0x180012f9d  jmp     loc_180013168
0x180012fa2  lea     rax, [rsp+4F8h+pszDest]
0x180012faa  mov     rdx, r12; lpKeyName
0x180012fad  mov     [rsp+4F8h+lpFileName], rax; lpFileName
0x180012fb2  lea     r15, aE527f950Fae511; "e527f950-fae5-11cf-a24b-00a0c9054392"
0x180012fb9  mov     r8, r15; lpDefault
0x180012fbc  mov     [rsp+4F8h+nSize], 28h ; '('; nSize
0x180012fc4  lea     r9, [rsp+4F8h+ReturnedString]; lpReturnedString
0x180012fc9  mov     rcx, rsi; lpAppName
0x180012fcc  call    cs:__imp_GetPrivateProfileStringW
0x180012fd2  lea     r8, [rsp+4F8h+ReturnedString]
0x180012fd7  mov     rax, r15
0x180012fda  sub     r8, r15
0x180012fdd  movzx   ecx, word ptr [rax]
0x180012fe0  movzx   edx, word ptr [rax+r8]
0x180012fe5  sub     ecx, edx
0x180012fe7  jnz     short loc_180012FF1
0x180012fe9  add     rax, 2
0x180012fed  test    edx, edx
0x180012fef  jnz     short loc_180012FDD
0x180012ff1  test    ecx, ecx
0x180012ff3  jnz     short loc_180013007
0x180012ff5  mov     ecx, 0Bh
0x180012ffa  call    PostInstError
0x180012fff  movzx   edi, bx
0x180013002  jmp     loc_180013168
0x180013007  movzx   r13d, [rsp+4F8h+arg_28]
0x180013010  lea     rax, [rsp+4F8h+pszDest]
0x180013018  mov     [rsp+4F8h+lpFileName], rax; lpFileName
0x18001301d  mov     r9, r14; lpReturnedString
0x180013020  mov     r8, r15; lpDefault
0x180013023  mov     [rsp+4F8h+nSize], r13d; nSize
0x180013028  mov     rdx, r12; lpKeyName
0x18001302b  mov     rcx, rsi; lpAppName
0x18001302e  call    cs:__imp_GetPrivateProfileStringW
0x180013034  xor     r9d, r9d
0x180013037  mov     [rsp+4F8h+var_4C4], eax
0x18001303b  mov     edx, 1
0x180013040  mov     ebp, eax
0x180013042  mov     r15d, eax
0x180013045  test    r12, r12
0x180013048  jz      short loc_180013069
0x18001304a  lea     rdx, aPwd; "PWD"
0x180013051  mov     rcx, r12; String1
0x180013054  call    cs:__imp__wcsicmp
0x18001305a  xor     r9d, r9d
0x18001305d  lea     edx, [r9+1]
0x180013061  mov     [rsp+4F8h+var_4C8], edx
0x180013065  test    eax, eax
0x180013067  jz      short loc_18001306E
0x180013069  mov     [rsp+4F8h+var_4C8], r9d
0x18001306e  test    rsi, rsi
0x180013071  jz      short loc_18001307A
0x180013073  mov     ecx, edx
0x180013075  test    r12, r12
0x180013078  jnz     short loc_18001307F
0x18001307a  mov     ecx, 2
0x18001307f  mov     eax, r13d
0x180013082  sub     eax, ecx
0x180013084  cmp     ebp, eax
0x180013086  jnz     loc_180013123
0x18001308c  add     r13d, r13d
0x18001308f  cmp     r13d, 7FFFh
0x180013096  ja      short loc_180013116
0x180013098  mov     r15d, r13d
0x18001309b  add     r15, r15
0x18001309e  mov     rcx, r15; Size
0x1800130a1  call    cs:__imp_malloc
0x1800130a7  mov     rsi, rax
0x1800130aa  test    rax, rax
0x1800130ad  jz      short loc_180013116
0x1800130af  mov     rcx, [rsp+4F8h+lpAppName]; lpAppName
0x1800130b4  lea     rax, [rsp+4F8h+pszDest]
0x1800130bc  mov     [rsp+4F8h+lpFileName], rax; lpFileName
0x1800130c1  lea     r8, SubKey; lpDefault
0x1800130c8  mov     r9, rsi; lpReturnedString
0x1800130cb  mov     [rsp+4F8h+nSize], r13d; nSize
0x1800130d0  mov     rdx, r12; lpKeyName
0x1800130d3  call    cs:__imp_GetPrivateProfileStringW
0x1800130d9  cmp     [rsp+4F8h+var_4C8], 0
0x1800130de  mov     rcx, rsi
0x1800130e1  mov     ebp, eax
0x1800130e3  jz      short loc_1800130F6
0x1800130e5  test    r15, r15
0x1800130e8  jz      short loc_1800130F6
0x1800130ea  mov     byte ptr [rsi], 0
0x1800130ed  inc     rsi
0x1800130f0  sub     r15, 1
0x1800130f4  jnz     short loc_1800130EA
0x1800130f6  call    OFree
0x1800130fb  mov     r15d, [rsp+4F8h+var_4C4]
0x180013100  xor     r9d, r9d
0x180013103  cmp     ebp, r15d
0x180013106  jz      short loc_180013135
0x180013108  mov     rsi, [rsp+4F8h+lpAppName]
0x18001310d  lea     edx, [r9+1]
0x180013111  jmp     loc_18001306E
0x180013116  movzx   edi, bx
0x180013119  mov     ecx, 15h
0x18001311e  jmp     loc_180012F98
0x180013123  cmp     r15d, ebp
0x180013126  jz      short loc_180013135
0x180013128  mov     ecx, 16h
0x18001312d  movzx   edi, dx
0x180013130  call    PostInstError
0x180013135  test    ebp, ebp
0x180013137  jz      short loc_18001315B
0x180013139  test    r12, r12
0x18001313c  jnz     short loc_18001315B
0x18001313e  lea     rcx, [r14+2]
0x180013142  cmp     [r14], r9w
0x180013146  jnz     short loc_180013156
0x180013148  movzx   eax, word ptr [rcx]
0x18001314b  mov     word ptr [r14], 3Bh ; ';'
0x180013151  test    ax, ax
0x180013154  jz      short loc_18001315B
0x180013156  mov     r14, rcx
0x180013159  jmp     short loc_18001313E
0x18001315b  mov     rax, [rsp+4F8h+var_4B8]
0x180013160  test    rax, rax
0x180013163  jz      short loc_180013168
0x180013165  mov     [rax], bp
0x180013168  movzx   eax, di
0x18001316b  jmp     short loc_18001317B
0x18001316d  mov     ecx, 0Ch
0x180013172  call    PostInstError
0x180013177  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001317b  mov     rcx, [rsp+4F8h+var_48]
0x180013183  xor     rcx, rsp; StackCookie
0x180013186  call    __security_check_cookie
0x18001318b  mov     rbx, [rsp+4F8h+arg_0]
0x180013193  add     rsp, 4C0h
0x18001319a  pop     r15
0x18001319c  pop     r14
0x18001319e  pop     r13
0x1800131a0  pop     r12
0x1800131a2  pop     rdi
0x1800131a3  pop     rsi
0x1800131a4  pop     rbp
0x1800131a5  retn
```
