# AslpEnvResolveVars

- ea: `0x14082a620`
- end: `0x14082a953`
- name: `AslpEnvResolveVars`
- size: `819`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PCWSTR pszSrc@<rcx>, __int16, __int16, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14082a058`

## callees

- `0x140438468`
- `0x1404b8748`
- `0x140544740`
- `0x14082a620`
- `0x1408c2f88`

## string_xrefs

- `0x14082a887`: `RtlStringCchCopyW failed [%x]`
- `0x14082a8ad`: `RtlStringCchCopyW failed [%x]`
- `0x14082a920`: `RtlStringCchCopyW failed [%x]`
- `0x14082a7b1`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`
- `0x14082a8c1`: `ResolvedPath is NULL or zero size [%#x]`

## pseudocode

```c
__int64 __fastcall AslpEnvResolveVars(
        NTSTRSAFE_PCWSTR pszSrc,
        unsigned int a2,
        wchar_t *a3,
        unsigned int a4,
        __int16 a5,
        __int16 a6,
        unsigned int *a7)
{
  int v7; // ebx
  size_t v8; // r14
  int v9; // r13d
  unsigned int v10; // esi
  unsigned __int64 v12; // r15
  wchar_t *v13; // rdi
  __int64 v14; // r12
  unsigned int v15; // eax
  unsigned __int64 i; // rdi
  NTSTATUS v17; // ebx
  __int64 v18; // r11
  const char *v19; // r9
  int v20; // r8d
  const wchar_t *v22; // [rsp+70h] [rbp+8h]

  v22 = pszSrc;
  v7 = 0;
  v8 = a4;
  v9 = 0;
  v10 = 0;
  v12 = 0;
  v13 = a3;
  while ( v12 < 4 )
  {
    if ( v7 )
      goto LABEL_41;
    v14 = 3 * v12;
    v15 = qword_140E0D8B0[3 * v12];
    if ( a2 > v15 )
    {
      if ( !wcsnicmp(pszSrc, off_140E0D8A0[v14], v15) )
      {
        v10 = a2 + HIDWORD(qword_140E0D8B0[v14]) - LODWORD(qword_140E0D8B0[v14]);
        if ( v10 > (unsigned int)v8 )
        {
          v17 = -1073741789;
          goto LABEL_42;
        }
        if ( !v13 || !(_DWORD)v8 )
        {
          v17 = -1073741811;
          v19 = "ResolvedPath is NULL or zero size [%#x]";
          v20 = 1035;
          goto LABEL_34;
        }
        if ( v12 )
        {
          if ( !v9 )
          {
LABEL_22:
            v17 = RtlStringCchCopyW(v13, v8, (&off_140E0D8A8)[v14]);
            if ( v17 < 0 )
            {
              v19 = "RtlStringCchCopyW failed [%x]";
              v20 = 1091;
              goto LABEL_34;
            }
            v17 = RtlStringCchCatW(v13, v8, &v22[LODWORD(qword_140E0D8B0[v14])]);
            if ( v17 < 0 )
            {
              v19 = "RtlStringCchCatW failed [%x]";
              v20 = 1097;
LABEL_34:
              AslLogCallPrintf(1, (unsigned int)"AslpEnvResolveVars", v20, (_DWORD)v19);
              return (unsigned int)v17;
            }
          }
        }
        else
        {
          for ( i = 0; i < 8; ++i )
          {
            if ( word_140E0D900[8 * i] == a5 && word_140E0D902[8 * i] == a6 )
            {
              v17 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              if ( v17 < 0 )
              {
                v19 = "RtlStringCchCopyW failed [%x]";
                v20 = 1051;
                goto LABEL_34;
              }
              v17 = RtlStringCchCatW(a3, v8, (&off_140E0D908)[v18]);
              if ( v17 < 0 )
              {
                v19 = "RtlStringCchCatW failed [%x]";
                v20 = 1057;
                goto LABEL_34;
              }
              v17 = RtlStringCchCatW(a3, v8, &v22[LODWORD(qword_140E0D8B0[v14])]);
              if ( v17 < 0 )
              {
                v19 = "RtlStringCchCatW failed [%x]";
                v20 = 1063;
                goto LABEL_34;
              }
              v9 = 1;
            }
          }
          if ( !v9 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"AslpEnvResolveVars",
              1074,
              (unsigned int)"Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Hos"
                            "t: %x4 Current: %x4");
            v13 = a3;
            goto LABEL_22;
          }
          v13 = a3;
        }
        v7 = 1;
      }
      pszSrc = v22;
    }
    ++v12;
  }
  if ( !v7 )
  {
    if ( a2 > (unsigned int)v8 )
    {
      v17 = -1073741789;
      *a7 = a2;
      return (unsigned int)v17;
    }
    v10 = a2;
    v17 = RtlStringCchCopyW(v13, v8, pszSrc);
    if ( v17 < 0 )
    {
      v19 = "RtlStringCchCopyW failed [%x]";
      v20 = 1129;
      goto LABEL_34;
    }
  }
LABEL_41:
  v17 = 0;
LABEL_42:
  *a7 = v10;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14082a620  mov     [rsp+arg_8], rbx
0x14082a625  mov     [rsp+pszDest], r8
0x14082a62a  mov     [rsp+arg_0], rcx
0x14082a62f  push    rbp
0x14082a630  push    rsi
0x14082a631  push    rdi
0x14082a632  push    r12
0x14082a634  push    r13
0x14082a636  push    r14
0x14082a638  push    r15
0x14082a63a  sub     rsp, 30h
0x14082a63e  xor     ebx, ebx
0x14082a640  mov     r14d, r9d
0x14082a643  xor     r13d, r13d
0x14082a646  xor     esi, esi
0x14082a648  mov     ebp, edx
0x14082a64a  xor     r15d, r15d
0x14082a64d  mov     rdi, r8
0x14082a650  lea     rdx, cs:140000000h
0x14082a657  cmp     r15, 4
0x14082a65b  jnb     loc_14082A8EC
0x14082a661  test    ebx, ebx
0x14082a663  jnz     loc_14082A92F
0x14082a669  lea     r12, [r15+r15*2]
0x14082a66d  shl     r12, 3
0x14082a671  mov     eax, [r12+rdx+0E0D8B0h]
0x14082a679  cmp     ebp, eax
0x14082a67b  jbe     loc_14082A84B
0x14082a681  mov     rdx, [r12+rdx+0E0D8A0h]; Str2
0x14082a689  mov     r8d, eax; MaxCount
0x14082a68c  call    _wcsnicmp
0x14082a691  lea     rdx, cs:140000000h
0x14082a698  test    eax, eax
0x14082a69a  jnz     loc_14082A846
0x14082a6a0  mov     esi, [r12+rdx+0E0D8B4h]
0x14082a6a8  sub     esi, [r12+rdx+0E0D8B0h]
0x14082a6b0  add     esi, ebp
0x14082a6b2  cmp     esi, r14d
0x14082a6b5  ja      loc_14082A8E5
0x14082a6bb  test    rdi, rdi
0x14082a6be  jz      loc_14082A8BC
0x14082a6c4  test    r14d, r14d
0x14082a6c7  jz      loc_14082A8BC
0x14082a6cd  test    r15, r15
0x14082a6d0  jnz     loc_14082A7EF
0x14082a6d6  xor     edi, edi
0x14082a6d8  cmp     rdi, 8
0x14082a6dc  jnb     loc_14082A7A0
0x14082a6e2  movzx   eax, [rsp+68h+arg_20]
0x14082a6ea  mov     r11, rdi
0x14082a6ed  add     r11, r11
0x14082a6f0  cmp     rva word_140E0D900[rdx+r11*8], ax
0x14082a6f9  jnz     loc_14082A798
0x14082a6ff  movzx   eax, [rsp+68h+arg_28]
0x14082a707  cmp     rva word_140E0D902[rdx+r11*8], ax
0x14082a710  jnz     loc_14082A798
0x14082a716  mov     r13, [rsp+68h+pszDest]
0x14082a71e  lea     r8, aSystemroot_5; "%systemroot%"
0x14082a725  mov     rcx, r13; pszDest
0x14082a728  mov     rdx, r14; cchDest
0x14082a72b  call    RtlStringCchCopyW
0x14082a730  mov     ebx, eax
0x14082a732  test    eax, eax
0x14082a734  js      loc_14082A883
0x14082a73a  lea     r8, cs:140000000h
0x14082a741  mov     rdx, r14; cchDest
0x14082a744  mov     r8, rva off_140E0D908[r8+r11*8]; pszSrc
0x14082a74c  mov     rcx, r13; pszDest
0x14082a74f  call    RtlStringCchCatW
0x14082a754  mov     ebx, eax
0x14082a756  test    eax, eax
0x14082a758  js      loc_14082A870
0x14082a75e  mov     rcx, [rsp+68h+arg_0]
0x14082a763  lea     rax, cs:140000000h
0x14082a76a  mov     eax, [r12+rax+0E0D8B0h]
0x14082a772  mov     rdx, r14; cchDest
0x14082a775  lea     r8, [rcx+rax*2]; pszSrc
0x14082a779  mov     rcx, r13; pszDest
0x14082a77c  call    RtlStringCchCatW
0x14082a781  mov     ebx, eax
0x14082a783  test    eax, eax
0x14082a785  js      loc_14082A85D
0x14082a78b  mov     r13d, 1
0x14082a791  lea     rdx, cs:140000000h
0x14082a798  inc     rdi
0x14082a79b  jmp     loc_14082A6D8
0x14082a7a0  test    r13d, r13d
0x14082a7a3  jnz     loc_14082A853
0x14082a7a9  movzx   ecx, [rsp+68h+arg_20]
0x14082a7b1  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x14082a7b8  movzx   eax, [rsp+68h+arg_28]
0x14082a7c0  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x14082a7c7  mov     [rsp+68h+var_40], eax
0x14082a7cb  mov     r8d, 432h
0x14082a7d1  mov     [rsp+68h+var_48], ecx
0x14082a7d5  lea     ecx, [r13+1]
0x14082a7d9  call    AslLogCallPrintf
0x14082a7de  mov     rdi, [rsp+68h+pszDest]
0x14082a7e6  lea     rdx, cs:140000000h
0x14082a7ed  jmp     short loc_14082A7F4
0x14082a7ef  test    r13d, r13d
0x14082a7f2  jnz     short loc_14082A841
0x14082a7f4  mov     r8, [r12+rdx+0E0D8A8h]; pszSrc
0x14082a7fc  mov     rcx, rdi; pszDest
0x14082a7ff  mov     rdx, r14; cchDest
0x14082a802  call    RtlStringCchCopyW
0x14082a807  mov     ebx, eax
0x14082a809  test    eax, eax
0x14082a80b  js      loc_14082A8A9
0x14082a811  mov     rcx, [rsp+68h+arg_0]
0x14082a816  lea     rax, cs:140000000h
0x14082a81d  mov     eax, [r12+rax+0E0D8B0h]
0x14082a825  mov     rdx, r14; cchDest
0x14082a828  lea     r8, [rcx+rax*2]; pszSrc
0x14082a82c  mov     rcx, rdi; pszDest
0x14082a82f  call    RtlStringCchCatW
0x14082a834  mov     ebx, eax
0x14082a836  test    eax, eax
0x14082a838  js      short loc_14082A896
0x14082a83a  lea     rdx, cs:140000000h
0x14082a841  mov     ebx, 1
0x14082a846  mov     rcx, [rsp+68h+arg_0]
0x14082a84b  inc     r15
0x14082a84e  jmp     loc_14082A657
0x14082a853  mov     rdi, [rsp+68h+pszDest]
0x14082a85b  jmp     short loc_14082A841
0x14082a85d  mov     [rsp+68h+var_48], eax
0x14082a861  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14082a868  mov     r8d, 427h
0x14082a86e  jmp     short loc_14082A8D2
0x14082a870  mov     [rsp+68h+var_48], eax
0x14082a874  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14082a87b  mov     r8d, 421h
0x14082a881  jmp     short loc_14082A8D2
0x14082a883  mov     [rsp+68h+var_48], eax
0x14082a887  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14082a88e  mov     r8d, 41Bh
0x14082a894  jmp     short loc_14082A8D2
0x14082a896  mov     [rsp+68h+var_48], eax
0x14082a89a  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14082a8a1  mov     r8d, 449h
0x14082a8a7  jmp     short loc_14082A8D2
0x14082a8a9  mov     [rsp+68h+var_48], eax
0x14082a8ad  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14082a8b4  mov     r8d, 443h
0x14082a8ba  jmp     short loc_14082A8D2
0x14082a8bc  mov     ebx, 0C000000Dh
0x14082a8c1  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x14082a8c8  mov     [rsp+68h+var_48], ebx
0x14082a8cc  mov     r8d, 40Bh
0x14082a8d2  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x14082a8d9  mov     ecx, 1
0x14082a8de  call    AslLogCallPrintf
0x14082a8e3  jmp     short loc_14082A93B
0x14082a8e5  mov     ebx, 0C0000023h
0x14082a8ea  jmp     short loc_14082A931
0x14082a8ec  test    ebx, ebx
0x14082a8ee  jnz     short loc_14082A92F
0x14082a8f0  cmp     ebp, r14d
0x14082a8f3  jbe     short loc_14082A906
0x14082a8f5  mov     rax, [rsp+68h+arg_30]
0x14082a8fd  mov     ebx, 0C0000023h
0x14082a902  mov     [rax], ebp
0x14082a904  jmp     short loc_14082A93B
0x14082a906  mov     r8, rcx; pszSrc
0x14082a909  mov     rdx, r14; cchDest
0x14082a90c  mov     rcx, rdi; pszDest
0x14082a90f  mov     esi, ebp
0x14082a911  call    RtlStringCchCopyW
0x14082a916  mov     ebx, eax
0x14082a918  test    eax, eax
0x14082a91a  jns     short loc_14082A92F
0x14082a91c  mov     [rsp+68h+var_48], eax
0x14082a920  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14082a927  mov     r8d, 469h
0x14082a92d  jmp     short loc_14082A8D2
0x14082a92f  xor     ebx, ebx
0x14082a931  mov     rax, [rsp+68h+arg_30]
0x14082a939  mov     [rax], esi
0x14082a93b  mov     eax, ebx
0x14082a93d  mov     rbx, [rsp+68h+arg_8]
0x14082a942  add     rsp, 30h
0x14082a946  pop     r15
0x14082a948  pop     r14
0x14082a94a  pop     r13
0x14082a94c  pop     r12
0x14082a94e  pop     rdi
0x14082a94f  pop     rsi
0x14082a950  pop     rbp
0x14082a951  retn
```
