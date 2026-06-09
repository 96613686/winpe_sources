# AslPathCleanUstr

- ea: `0x140826dd8`
- end: `0x1408270c0`
- name: `AslPathCleanUstr`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14073d8dc`

## callees

- `0x14053d080`
- `0x14053eb30`
- `0x140826dd8`
- `0x14097d158`

## string_xrefs

- `0x140827049`: `AslPathCleanUstr failed with source pointer behind destination pointer.`
- `0x140827056`: `AslPathCleanUstr`
- `0x14082709b`: `AslPathCleanUstr`
- `0x14082708a`: `AslpPathGetFormatInfo failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathCleanUstr(unsigned __int16 *a1)
{
  int v2; // r14d
  const wchar_t *v3; // rcx
  int v4; // ebx
  const wchar_t *v5; // rbp
  unsigned __int16 v6; // r11
  unsigned __int64 v7; // rcx
  __int16 v8; // dx
  unsigned __int16 v9; // r9
  unsigned __int16 i; // r10
  __int64 v11; // rcx
  __int16 v12; // dx
  __int16 v13; // dx
  __int16 v14; // ax
  __int16 v15; // ax
  __int64 v16; // rdx
  __int16 v17; // cx
  __int64 v18; // rdx
  __int16 v19; // cx
  unsigned __int16 v20; // ax
  __int64 v21; // rax
  unsigned int v22; // ebx

  v2 = *a1 >> 1;
  if ( *a1 < 2u || (v3 = (const wchar_t *)*((_QWORD *)a1 + 1), !*v3) )
  {
    v22 = -1073741582;
    AslLogCallPrintf(1, (unsigned int)"AslPathCleanUstr", 730, (unsigned int)"AslpPathGetFormatInfo failed [%x]");
    return v22;
  }
  if ( (unsigned __int16)v2 < 8u || wcsnicmp(v3, L"\\??\\UNC\\", 8u) )
  {
    v4 = 4;
    if ( (unsigned __int16)v2 >= 4u )
    {
      v5 = (const wchar_t *)*((_QWORD *)a1 + 1);
      if ( !wcsncmp(v5, L"\\??\\", 4u) )
      {
        v4 = 3;
        goto LABEL_14;
      }
      if ( !wcsncmp(v5, L"\\\\?\\", 4u) || !wcsncmp(v5, L"\\\\.\\", 4u) )
        goto LABEL_14;
    }
    if ( (unsigned __int16)v2 <= 2u || wcsncmp(*((const wchar_t **)a1 + 1), L"\\\\", 2u) )
      v4 = 1;
  }
  else
  {
    v4 = 5;
  }
LABEL_14:
  v6 = 0;
  do
  {
    v7 = 2LL * v6;
    if ( v7 >= *a1 )
      break;
    v8 = *(_WORD *)(v7 + *((_QWORD *)a1 + 1));
    if ( v8 == 92 || v8 == 47 )
      --v4;
    ++v6;
  }
  while ( v4 > 0 );
  v9 = v6;
  for ( i = v6; i < (unsigned __int16)v2; ++i )
  {
    if ( i < v9 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslPathCleanUstr",
        742,
        (unsigned int)"AslPathCleanUstr failed with source pointer behind destination pointer.");
      return (unsigned int)-1073741595;
    }
    v11 = *((_QWORD *)a1 + 1);
    v12 = *(_WORD *)(v11 + 2LL * i);
    if ( v12 == 92 || v12 == 47 )
    {
      if ( !v9 || *(_WORD *)(v11 + 2LL * v9 - 2) != 92 )
      {
        v21 = v9++;
        *(_WORD *)(v11 + 2 * v21) = 92;
      }
    }
    else if ( v12 == 46 )
    {
      if ( i + 1 == v2 )
        break;
      v14 = *(_WORD *)(v11 + 2LL * i + 2);
      if ( v14 == 92 || v14 == 47 )
      {
        ++i;
      }
      else if ( v14 == 46 )
      {
        if ( i + 2 == v2 || (v15 = *(_WORD *)(v11 + 2LL * i + 4), v15 == 92) || v15 == 47 )
        {
          while ( v9 >= v6 )
          {
            v16 = *((_QWORD *)a1 + 1);
            v17 = *(_WORD *)(v16 + 2LL * v9);
            *(_WORD *)(v16 + 2LL * v9) = 0;
            if ( v17 == 92 )
            {
              do
              {
                v18 = *((_QWORD *)a1 + 1);
                v19 = *(_WORD *)(v18 + 2LL * v9);
                *(_WORD *)(v18 + 2LL * v9) = 0;
                if ( v19 == 92 )
                  break;
                --v9;
              }
              while ( v9 >= v6 );
              break;
            }
            --v9;
          }
          v20 = v9 + 1;
          ++i;
          if ( v9 >= v6 )
            v20 = v9;
          v9 = v20;
        }
      }
    }
    else
    {
      do
      {
        v13 = *(_WORD *)(v11 + 2LL * i);
        if ( v13 == 92 || v13 == 47 )
          break;
        if ( i != v9 )
        {
          *(_WORD *)(v11 + 2LL * v9) = v13;
          v11 = *((_QWORD *)a1 + 1);
        }
        ++v9;
        ++i;
      }
      while ( i < (unsigned __int16)v2 );
      --i;
    }
  }
  v22 = 0;
  *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v9) = 0;
  *a1 = 2 * v9;
  return v22;
}

```

## disassembly

```asm
0x140826dd8  push    rbx
0x140826dda  push    rbp
0x140826ddb  push    rsi
0x140826ddc  push    rdi
0x140826ddd  push    r12
0x140826ddf  push    r13
0x140826de1  push    r14
0x140826de3  push    r15
0x140826de5  sub     rsp, 38h
0x140826de9  movzx   edx, word ptr [rcx]
0x140826dec  mov     r12d, 2
0x140826df2  movzx   eax, dx
0x140826df5  mov     rsi, rcx
0x140826df8  shr     ax, 1
0x140826dfb  movzx   r14d, ax
0x140826dff  cmp     dx, r12w
0x140826e03  jb      loc_140827085
0x140826e09  mov     rcx, [rcx+8]; Str1
0x140826e0d  xor     r15d, r15d
0x140826e10  cmp     [rcx], r15w
0x140826e14  jz      loc_140827085
0x140826e1a  lea     r8d, [r12+6]; MaxCount
0x140826e1f  lea     edi, [r12-1]
0x140826e24  cmp     r14w, r8w
0x140826e28  jb      short loc_140826E3F
0x140826e2a  lea     rdx, aUnc; "\\??\\UNC\\"
0x140826e31  call    _wcsnicmp
0x140826e36  test    eax, eax
0x140826e38  jnz     short loc_140826E3F
0x140826e3a  lea     ebx, [rdi+4]
0x140826e3d  jmp     short loc_140826EB4
0x140826e3f  mov     ebx, 4
0x140826e44  cmp     r14w, bx
0x140826e48  jb      short loc_140826E95
0x140826e4a  mov     rbp, [rsi+8]
0x140826e4e  lea     rdx, asc_140023188; "\\??\\"
0x140826e55  mov     rcx, rbp; Str1
0x140826e58  mov     r8d, ebx; MaxCount
0x140826e5b  call    wcsncmp
0x140826e60  test    eax, eax
0x140826e62  jnz     short loc_140826E69
0x140826e64  lea     ebx, [rax+3]
0x140826e67  jmp     short loc_140826EB4
0x140826e69  mov     r8d, ebx; MaxCount
0x140826e6c  lea     rdx, asc_140020F10; "\\\\?\\"
0x140826e73  mov     rcx, rbp; Str1
0x140826e76  call    wcsncmp
0x140826e7b  test    eax, eax
0x140826e7d  jz      short loc_140826EB4
0x140826e7f  mov     r8d, ebx; MaxCount
0x140826e82  lea     rdx, asc_140040650; "\\\\.\\"
0x140826e89  mov     rcx, rbp; Str1
0x140826e8c  call    wcsncmp
0x140826e91  test    eax, eax
0x140826e93  jz      short loc_140826EB4
0x140826e95  cmp     r14w, r12w
0x140826e99  jbe     short loc_140826EB2
0x140826e9b  mov     rcx, [rsi+8]; Str1
0x140826e9f  lea     rdx, asc_140040644; "\\\\"
0x140826ea6  mov     r8d, r12d; MaxCount
0x140826ea9  call    wcsncmp
0x140826eae  test    eax, eax
0x140826eb0  jz      short loc_140826EB4
0x140826eb2  mov     ebx, edi
0x140826eb4  movzx   r8d, word ptr [rsi]
0x140826eb8  mov     r11d, r15d
0x140826ebb  mov     ebp, 5Ch ; '\'
0x140826ec0  mov     r12w, 2Fh ; '/'
0x140826ec5  movzx   eax, r11w
0x140826ec9  lea     rcx, [rax+rax]
0x140826ecd  cmp     rcx, r8
0x140826ed0  jnb     short loc_140826EEF
0x140826ed2  mov     rax, [rsi+8]
0x140826ed6  movzx   edx, word ptr [rcx+rax]
0x140826eda  cmp     dx, bp
0x140826edd  jz      short loc_140826EE5
0x140826edf  cmp     dx, r12w
0x140826ee3  jnz     short loc_140826EE7
0x140826ee5  sub     ebx, edi
0x140826ee7  add     r11w, di
0x140826eeb  test    ebx, ebx
0x140826eed  jg      short loc_140826EC5
0x140826eef  movzx   r9d, r11w
0x140826ef3  movzx   r10d, r11w
0x140826ef7  mov     r13d, 0FFFFh
0x140826efd  cmp     r10w, r14w
0x140826f01  jnb     loc_14082706B
0x140826f07  cmp     r10w, r9w
0x140826f0b  jb      loc_140827049
0x140826f11  mov     rcx, [rsi+8]
0x140826f15  movzx   eax, r10w
0x140826f19  movzx   edx, word ptr [rcx+rax*2]
0x140826f1d  cmp     dx, bp
0x140826f20  jz      loc_140827023
0x140826f26  cmp     dx, r12w
0x140826f2a  jz      loc_140827023
0x140826f30  cmp     dx, 2Eh ; '.'
0x140826f34  jz      short loc_140826F72
0x140826f36  movzx   eax, r10w
0x140826f3a  movzx   edx, word ptr [rcx+rax*2]
0x140826f3e  cmp     dx, bp
0x140826f41  jz      short loc_140826F69
0x140826f43  cmp     dx, r12w
0x140826f47  jz      short loc_140826F69
0x140826f49  cmp     r10w, r9w
0x140826f4d  jz      short loc_140826F5B
0x140826f4f  movzx   eax, r9w
0x140826f53  mov     [rcx+rax*2], dx
0x140826f57  mov     rcx, [rsi+8]
0x140826f5b  add     r9w, di
0x140826f5f  add     r10w, di
0x140826f63  cmp     r10w, r14w
0x140826f67  jb      short loc_140826F36
0x140826f69  add     r10w, r13w
0x140826f6d  jmp     loc_140827040
0x140826f72  movzx   edx, r10w
0x140826f76  lea     eax, [rdx+1]
0x140826f79  cmp     eax, r14d
0x140826f7c  jz      loc_14082706B
0x140826f82  movzx   eax, word ptr [rcx+rdx*2+2]
0x140826f87  cmp     ax, bp
0x140826f8a  jz      loc_14082701D
0x140826f90  cmp     ax, r12w
0x140826f94  jz      loc_14082701D
0x140826f9a  cmp     ax, 2Eh ; '.'
0x140826f9e  jnz     loc_140827040
0x140826fa4  lea     eax, [rdx+2]
0x140826fa7  cmp     eax, r14d
0x140826faa  jz      short loc_140826FDD
0x140826fac  movzx   eax, word ptr [rcx+rdx*2+4]
0x140826fb1  cmp     ax, bp
0x140826fb4  jz      short loc_140826FDD
0x140826fb6  cmp     ax, r12w
0x140826fba  jnz     loc_140827040
0x140826fc0  jmp     short loc_140826FDD
0x140826fc2  mov     rdx, [rsi+8]
0x140826fc6  movzx   r8d, r9w
0x140826fca  movzx   ecx, word ptr [rdx+r8*2]
0x140826fcf  mov     [rdx+r8*2], r15w
0x140826fd4  cmp     cx, bp
0x140826fd7  jz      short loc_140826FE5
0x140826fd9  add     r9w, r13w
0x140826fdd  cmp     r9w, r11w
0x140826fe1  jnb     short loc_140826FC2
0x140826fe3  jmp     short loc_140827006
0x140826fe5  mov     rdx, [rsi+8]
0x140826fe9  movzx   r8d, r9w
0x140826fed  movzx   ecx, word ptr [rdx+r8*2]
0x140826ff2  mov     [rdx+r8*2], r15w
0x140826ff7  cmp     cx, bp
0x140826ffa  jz      short loc_140827006
0x140826ffc  add     r9w, r13w
0x140827000  cmp     r9w, r11w
0x140827004  jnb     short loc_140826FE5
0x140827006  lea     eax, [rdi+r9]
0x14082700a  add     r10w, di
0x14082700e  cmp     r9w, r11w
0x140827012  cmovnb  ax, r9w
0x140827017  movzx   r9d, ax
0x14082701b  jmp     short loc_140827040
0x14082701d  add     r10w, di
0x140827021  jmp     short loc_140827040
0x140827023  test    r9w, r9w
0x140827027  jz      short loc_140827034
0x140827029  movzx   eax, r9w
0x14082702d  cmp     [rcx+rax*2-2], bp
0x140827032  jz      short loc_140827040
0x140827034  movzx   eax, r9w
0x140827038  add     r9w, di
0x14082703c  mov     [rcx+rax*2], bp
0x140827040  add     r10w, di
0x140827044  jmp     loc_140826EFD
0x140827049  lea     r9, aAslpathcleanus_1; "AslPathCleanUstr failed with source poi"...
0x140827050  mov     r8d, 2E6h
0x140827056  lea     rdx, aAslpathcleanus_0; "AslPathCleanUstr"
0x14082705d  mov     ecx, edi
0x14082705f  call    AslLogCallPrintf
0x140827064  mov     ebx, 0C00000E5h
0x140827069  jmp     short loc_1408270AC
0x14082706b  mov     rcx, [rsi+8]
0x14082706f  mov     ebx, r15d
0x140827072  movzx   edx, r9w
0x140827076  add     r9w, r9w
0x14082707a  mov     [rcx+rdx*2], r15w
0x14082707f  mov     [rsi], r9w
0x140827083  jmp     short loc_1408270AC
0x140827085  mov     ebx, 0C00000F2h
0x14082708a  lea     r9, aAslppathgetfor; "AslpPathGetFormatInfo failed [%x]"
0x140827091  mov     r8d, 2DAh
0x140827097  mov     [rsp+78h+var_58], ebx
0x14082709b  lea     rdx, aAslpathcleanus_0; "AslPathCleanUstr"
0x1408270a2  mov     ecx, 1
0x1408270a7  call    AslLogCallPrintf
0x1408270ac  mov     eax, ebx
0x1408270ae  add     rsp, 38h
0x1408270b2  pop     r15
0x1408270b4  pop     r14
0x1408270b6  pop     r13
0x1408270b8  pop     r12
0x1408270ba  pop     rdi
0x1408270bb  pop     rsi
0x1408270bc  pop     rbp
0x1408270bd  pop     rbx
0x1408270be  retn
```
