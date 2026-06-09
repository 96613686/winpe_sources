# AslpEnvResolveVars

- ea: `0x1408286b0`
- end: `0x1408289e3`
- name: `AslpEnvResolveVars`
- size: `819`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PCWSTR pszSrc@<rcx>, __int16, __int16, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1408280e8`

## callees

- `0x1402dc448`
- `0x1404a9868`
- `0x14053d080`
- `0x1408286b0`
- `0x14097d158`

## string_xrefs

- `0x140828917`: `RtlStringCchCopyW failed [%x]`
- `0x14082893d`: `RtlStringCchCopyW failed [%x]`
- `0x1408289b0`: `RtlStringCchCopyW failed [%x]`
- `0x140828841`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`
- `0x140828951`: `ResolvedPath is NULL or zero size [%#x]`

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
0x1408286b0  mov     [rsp+arg_8], rbx
0x1408286b5  mov     [rsp+pszDest], r8
0x1408286ba  mov     [rsp+arg_0], rcx
0x1408286bf  push    rbp
0x1408286c0  push    rsi
0x1408286c1  push    rdi
0x1408286c2  push    r12
0x1408286c4  push    r13
0x1408286c6  push    r14
0x1408286c8  push    r15
0x1408286ca  sub     rsp, 30h
0x1408286ce  xor     ebx, ebx
0x1408286d0  mov     r14d, r9d
0x1408286d3  xor     r13d, r13d
0x1408286d6  xor     esi, esi
0x1408286d8  mov     ebp, edx
0x1408286da  xor     r15d, r15d
0x1408286dd  mov     rdi, r8
0x1408286e0  lea     rdx, cs:140000000h
0x1408286e7  cmp     r15, 4
0x1408286eb  jnb     loc_14082897C
0x1408286f1  test    ebx, ebx
0x1408286f3  jnz     loc_1408289BF
0x1408286f9  lea     r12, [r15+r15*2]
0x1408286fd  shl     r12, 3
0x140828701  mov     eax, [r12+rdx+0E0D8B0h]
0x140828709  cmp     ebp, eax
0x14082870b  jbe     loc_1408288DB
0x140828711  mov     rdx, [r12+rdx+0E0D8A0h]; Str2
0x140828719  mov     r8d, eax; MaxCount
0x14082871c  call    _wcsnicmp
0x140828721  lea     rdx, cs:140000000h
0x140828728  test    eax, eax
0x14082872a  jnz     loc_1408288D6
0x140828730  mov     esi, [r12+rdx+0E0D8B4h]
0x140828738  sub     esi, [r12+rdx+0E0D8B0h]
0x140828740  add     esi, ebp
0x140828742  cmp     esi, r14d
0x140828745  ja      loc_140828975
0x14082874b  test    rdi, rdi
0x14082874e  jz      loc_14082894C
0x140828754  test    r14d, r14d
0x140828757  jz      loc_14082894C
0x14082875d  test    r15, r15
0x140828760  jnz     loc_14082887F
0x140828766  xor     edi, edi
0x140828768  cmp     rdi, 8
0x14082876c  jnb     loc_140828830
0x140828772  movzx   eax, [rsp+68h+arg_20]
0x14082877a  mov     r11, rdi
0x14082877d  add     r11, r11
0x140828780  cmp     rva word_140E0D900[rdx+r11*8], ax
0x140828789  jnz     loc_140828828
0x14082878f  movzx   eax, [rsp+68h+arg_28]
0x140828797  cmp     rva word_140E0D902[rdx+r11*8], ax
0x1408287a0  jnz     loc_140828828
0x1408287a6  mov     r13, [rsp+68h+pszDest]
0x1408287ae  lea     r8, aSystemroot_5; "%systemroot%"
0x1408287b5  mov     rcx, r13; pszDest
0x1408287b8  mov     rdx, r14; cchDest
0x1408287bb  call    RtlStringCchCopyW
0x1408287c0  mov     ebx, eax
0x1408287c2  test    eax, eax
0x1408287c4  js      loc_140828913
0x1408287ca  lea     r8, cs:140000000h
0x1408287d1  mov     rdx, r14; cchDest
0x1408287d4  mov     r8, rva off_140E0D908[r8+r11*8]; pszSrc
0x1408287dc  mov     rcx, r13; pszDest
0x1408287df  call    RtlStringCchCatW
0x1408287e4  mov     ebx, eax
0x1408287e6  test    eax, eax
0x1408287e8  js      loc_140828900
0x1408287ee  mov     rcx, [rsp+68h+arg_0]
0x1408287f3  lea     rax, cs:140000000h
0x1408287fa  mov     eax, [r12+rax+0E0D8B0h]
0x140828802  mov     rdx, r14; cchDest
0x140828805  lea     r8, [rcx+rax*2]; pszSrc
0x140828809  mov     rcx, r13; pszDest
0x14082880c  call    RtlStringCchCatW
0x140828811  mov     ebx, eax
0x140828813  test    eax, eax
0x140828815  js      loc_1408288ED
0x14082881b  mov     r13d, 1
0x140828821  lea     rdx, cs:140000000h
0x140828828  inc     rdi
0x14082882b  jmp     loc_140828768
0x140828830  test    r13d, r13d
0x140828833  jnz     loc_1408288E3
0x140828839  movzx   ecx, [rsp+68h+arg_20]
0x140828841  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x140828848  movzx   eax, [rsp+68h+arg_28]
0x140828850  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x140828857  mov     [rsp+68h+var_40], eax
0x14082885b  mov     r8d, 432h
0x140828861  mov     [rsp+68h+var_48], ecx
0x140828865  lea     ecx, [r13+1]
0x140828869  call    AslLogCallPrintf
0x14082886e  mov     rdi, [rsp+68h+pszDest]
0x140828876  lea     rdx, cs:140000000h
0x14082887d  jmp     short loc_140828884
0x14082887f  test    r13d, r13d
0x140828882  jnz     short loc_1408288D1
0x140828884  mov     r8, [r12+rdx+0E0D8A8h]; pszSrc
0x14082888c  mov     rcx, rdi; pszDest
0x14082888f  mov     rdx, r14; cchDest
0x140828892  call    RtlStringCchCopyW
0x140828897  mov     ebx, eax
0x140828899  test    eax, eax
0x14082889b  js      loc_140828939
0x1408288a1  mov     rcx, [rsp+68h+arg_0]
0x1408288a6  lea     rax, cs:140000000h
0x1408288ad  mov     eax, [r12+rax+0E0D8B0h]
0x1408288b5  mov     rdx, r14; cchDest
0x1408288b8  lea     r8, [rcx+rax*2]; pszSrc
0x1408288bc  mov     rcx, rdi; pszDest
0x1408288bf  call    RtlStringCchCatW
0x1408288c4  mov     ebx, eax
0x1408288c6  test    eax, eax
0x1408288c8  js      short loc_140828926
0x1408288ca  lea     rdx, cs:140000000h
0x1408288d1  mov     ebx, 1
0x1408288d6  mov     rcx, [rsp+68h+arg_0]
0x1408288db  inc     r15
0x1408288de  jmp     loc_1408286E7
0x1408288e3  mov     rdi, [rsp+68h+pszDest]
0x1408288eb  jmp     short loc_1408288D1
0x1408288ed  mov     [rsp+68h+var_48], eax
0x1408288f1  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x1408288f8  mov     r8d, 427h
0x1408288fe  jmp     short loc_140828962
0x140828900  mov     [rsp+68h+var_48], eax
0x140828904  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14082890b  mov     r8d, 421h
0x140828911  jmp     short loc_140828962
0x140828913  mov     [rsp+68h+var_48], eax
0x140828917  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14082891e  mov     r8d, 41Bh
0x140828924  jmp     short loc_140828962
0x140828926  mov     [rsp+68h+var_48], eax
0x14082892a  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x140828931  mov     r8d, 449h
0x140828937  jmp     short loc_140828962
0x140828939  mov     [rsp+68h+var_48], eax
0x14082893d  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140828944  mov     r8d, 443h
0x14082894a  jmp     short loc_140828962
0x14082894c  mov     ebx, 0C000000Dh
0x140828951  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x140828958  mov     [rsp+68h+var_48], ebx
0x14082895c  mov     r8d, 40Bh
0x140828962  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x140828969  mov     ecx, 1
0x14082896e  call    AslLogCallPrintf
0x140828973  jmp     short loc_1408289CB
0x140828975  mov     ebx, 0C0000023h
0x14082897a  jmp     short loc_1408289C1
0x14082897c  test    ebx, ebx
0x14082897e  jnz     short loc_1408289BF
0x140828980  cmp     ebp, r14d
0x140828983  jbe     short loc_140828996
0x140828985  mov     rax, [rsp+68h+arg_30]
0x14082898d  mov     ebx, 0C0000023h
0x140828992  mov     [rax], ebp
0x140828994  jmp     short loc_1408289CB
0x140828996  mov     r8, rcx; pszSrc
0x140828999  mov     rdx, r14; cchDest
0x14082899c  mov     rcx, rdi; pszDest
0x14082899f  mov     esi, ebp
0x1408289a1  call    RtlStringCchCopyW
0x1408289a6  mov     ebx, eax
0x1408289a8  test    eax, eax
0x1408289aa  jns     short loc_1408289BF
0x1408289ac  mov     [rsp+68h+var_48], eax
0x1408289b0  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x1408289b7  mov     r8d, 469h
0x1408289bd  jmp     short loc_140828962
0x1408289bf  xor     ebx, ebx
0x1408289c1  mov     rax, [rsp+68h+arg_30]
0x1408289c9  mov     [rax], esi
0x1408289cb  mov     eax, ebx
0x1408289cd  mov     rbx, [rsp+68h+arg_8]
0x1408289d2  add     rsp, 30h
0x1408289d6  pop     r15
0x1408289d8  pop     r14
0x1408289da  pop     r13
0x1408289dc  pop     r12
0x1408289de  pop     rdi
0x1408289df  pop     rsi
0x1408289e0  pop     rbp
0x1408289e1  retn
```
