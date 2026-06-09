# AslPathCleanUstr

- ea: `0x140828d48`
- end: `0x140829030`
- name: `AslPathCleanUstr`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14074209c`

## callees

- `0x140544740`
- `0x1405461f0`
- `0x140828d48`
- `0x1408c2f88`

## string_xrefs

- `0x140828fc6`: `AslPathCleanUstr`
- `0x14082900b`: `AslPathCleanUstr`
- `0x140828fb9`: `AslPathCleanUstr failed with source pointer behind destination pointer.`
- `0x140828ffa`: `AslpPathGetFormatInfo failed [%x]`

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
0x140828d48  push    rbx
0x140828d4a  push    rbp
0x140828d4b  push    rsi
0x140828d4c  push    rdi
0x140828d4d  push    r12
0x140828d4f  push    r13
0x140828d51  push    r14
0x140828d53  push    r15
0x140828d55  sub     rsp, 38h
0x140828d59  movzx   edx, word ptr [rcx]
0x140828d5c  mov     r12d, 2
0x140828d62  movzx   eax, dx
0x140828d65  mov     rsi, rcx
0x140828d68  shr     ax, 1
0x140828d6b  movzx   r14d, ax
0x140828d6f  cmp     dx, r12w
0x140828d73  jb      loc_140828FF5
0x140828d79  mov     rcx, [rcx+8]; Str1
0x140828d7d  xor     r15d, r15d
0x140828d80  cmp     [rcx], r15w
0x140828d84  jz      loc_140828FF5
0x140828d8a  lea     r8d, [r12+6]; MaxCount
0x140828d8f  lea     edi, [r12-1]
0x140828d94  cmp     r14w, r8w
0x140828d98  jb      short loc_140828DAF
0x140828d9a  lea     rdx, aUnc; "\\??\\UNC\\"
0x140828da1  call    _wcsnicmp
0x140828da6  test    eax, eax
0x140828da8  jnz     short loc_140828DAF
0x140828daa  lea     ebx, [rdi+4]
0x140828dad  jmp     short loc_140828E24
0x140828daf  mov     ebx, 4
0x140828db4  cmp     r14w, bx
0x140828db8  jb      short loc_140828E05
0x140828dba  mov     rbp, [rsi+8]
0x140828dbe  lea     rdx, asc_140023150; "\\??\\"
0x140828dc5  mov     rcx, rbp; Str1
0x140828dc8  mov     r8d, ebx; MaxCount
0x140828dcb  call    wcsncmp
0x140828dd0  test    eax, eax
0x140828dd2  jnz     short loc_140828DD9
0x140828dd4  lea     ebx, [rax+3]
0x140828dd7  jmp     short loc_140828E24
0x140828dd9  mov     r8d, ebx; MaxCount
0x140828ddc  lea     rdx, asc_140020F58; "\\\\?\\"
0x140828de3  mov     rcx, rbp; Str1
0x140828de6  call    wcsncmp
0x140828deb  test    eax, eax
0x140828ded  jz      short loc_140828E24
0x140828def  mov     r8d, ebx; MaxCount
0x140828df2  lea     rdx, asc_1400402A0; "\\\\.\\"
0x140828df9  mov     rcx, rbp; Str1
0x140828dfc  call    wcsncmp
0x140828e01  test    eax, eax
0x140828e03  jz      short loc_140828E24
0x140828e05  cmp     r14w, r12w
0x140828e09  jbe     short loc_140828E22
0x140828e0b  mov     rcx, [rsi+8]; Str1
0x140828e0f  lea     rdx, asc_140040258; "\\\\"
0x140828e16  mov     r8d, r12d; MaxCount
0x140828e19  call    wcsncmp
0x140828e1e  test    eax, eax
0x140828e20  jz      short loc_140828E24
0x140828e22  mov     ebx, edi
0x140828e24  movzx   r8d, word ptr [rsi]
0x140828e28  mov     r11d, r15d
0x140828e2b  mov     ebp, 5Ch ; '\'
0x140828e30  mov     r12w, 2Fh ; '/'
0x140828e35  movzx   eax, r11w
0x140828e39  lea     rcx, [rax+rax]
0x140828e3d  cmp     rcx, r8
0x140828e40  jnb     short loc_140828E5F
0x140828e42  mov     rax, [rsi+8]
0x140828e46  movzx   edx, word ptr [rcx+rax]
0x140828e4a  cmp     dx, bp
0x140828e4d  jz      short loc_140828E55
0x140828e4f  cmp     dx, r12w
0x140828e53  jnz     short loc_140828E57
0x140828e55  sub     ebx, edi
0x140828e57  add     r11w, di
0x140828e5b  test    ebx, ebx
0x140828e5d  jg      short loc_140828E35
0x140828e5f  movzx   r9d, r11w
0x140828e63  movzx   r10d, r11w
0x140828e67  mov     r13d, 0FFFFh
0x140828e6d  cmp     r10w, r14w
0x140828e71  jnb     loc_140828FDB
0x140828e77  cmp     r10w, r9w
0x140828e7b  jb      loc_140828FB9
0x140828e81  mov     rcx, [rsi+8]
0x140828e85  movzx   eax, r10w
0x140828e89  movzx   edx, word ptr [rcx+rax*2]
0x140828e8d  cmp     dx, bp
0x140828e90  jz      loc_140828F93
0x140828e96  cmp     dx, r12w
0x140828e9a  jz      loc_140828F93
0x140828ea0  cmp     dx, 2Eh ; '.'
0x140828ea4  jz      short loc_140828EE2
0x140828ea6  movzx   eax, r10w
0x140828eaa  movzx   edx, word ptr [rcx+rax*2]
0x140828eae  cmp     dx, bp
0x140828eb1  jz      short loc_140828ED9
0x140828eb3  cmp     dx, r12w
0x140828eb7  jz      short loc_140828ED9
0x140828eb9  cmp     r10w, r9w
0x140828ebd  jz      short loc_140828ECB
0x140828ebf  movzx   eax, r9w
0x140828ec3  mov     [rcx+rax*2], dx
0x140828ec7  mov     rcx, [rsi+8]
0x140828ecb  add     r9w, di
0x140828ecf  add     r10w, di
0x140828ed3  cmp     r10w, r14w
0x140828ed7  jb      short loc_140828EA6
0x140828ed9  add     r10w, r13w
0x140828edd  jmp     loc_140828FB0
0x140828ee2  movzx   edx, r10w
0x140828ee6  lea     eax, [rdx+1]
0x140828ee9  cmp     eax, r14d
0x140828eec  jz      loc_140828FDB
0x140828ef2  movzx   eax, word ptr [rcx+rdx*2+2]
0x140828ef7  cmp     ax, bp
0x140828efa  jz      loc_140828F8D
0x140828f00  cmp     ax, r12w
0x140828f04  jz      loc_140828F8D
0x140828f0a  cmp     ax, 2Eh ; '.'
0x140828f0e  jnz     loc_140828FB0
0x140828f14  lea     eax, [rdx+2]
0x140828f17  cmp     eax, r14d
0x140828f1a  jz      short loc_140828F4D
0x140828f1c  movzx   eax, word ptr [rcx+rdx*2+4]
0x140828f21  cmp     ax, bp
0x140828f24  jz      short loc_140828F4D
0x140828f26  cmp     ax, r12w
0x140828f2a  jnz     loc_140828FB0
0x140828f30  jmp     short loc_140828F4D
0x140828f32  mov     rdx, [rsi+8]
0x140828f36  movzx   r8d, r9w
0x140828f3a  movzx   ecx, word ptr [rdx+r8*2]
0x140828f3f  mov     [rdx+r8*2], r15w
0x140828f44  cmp     cx, bp
0x140828f47  jz      short loc_140828F55
0x140828f49  add     r9w, r13w
0x140828f4d  cmp     r9w, r11w
0x140828f51  jnb     short loc_140828F32
0x140828f53  jmp     short loc_140828F76
0x140828f55  mov     rdx, [rsi+8]
0x140828f59  movzx   r8d, r9w
0x140828f5d  movzx   ecx, word ptr [rdx+r8*2]
0x140828f62  mov     [rdx+r8*2], r15w
0x140828f67  cmp     cx, bp
0x140828f6a  jz      short loc_140828F76
0x140828f6c  add     r9w, r13w
0x140828f70  cmp     r9w, r11w
0x140828f74  jnb     short loc_140828F55
0x140828f76  lea     eax, [rdi+r9]
0x140828f7a  add     r10w, di
0x140828f7e  cmp     r9w, r11w
0x140828f82  cmovnb  ax, r9w
0x140828f87  movzx   r9d, ax
0x140828f8b  jmp     short loc_140828FB0
0x140828f8d  add     r10w, di
0x140828f91  jmp     short loc_140828FB0
0x140828f93  test    r9w, r9w
0x140828f97  jz      short loc_140828FA4
0x140828f99  movzx   eax, r9w
0x140828f9d  cmp     [rcx+rax*2-2], bp
0x140828fa2  jz      short loc_140828FB0
0x140828fa4  movzx   eax, r9w
0x140828fa8  add     r9w, di
0x140828fac  mov     [rcx+rax*2], bp
0x140828fb0  add     r10w, di
0x140828fb4  jmp     loc_140828E6D
0x140828fb9  lea     r9, aAslpathcleanus_1; "AslPathCleanUstr failed with source poi"...
0x140828fc0  mov     r8d, 2E6h
0x140828fc6  lea     rdx, aAslpathcleanus_0; "AslPathCleanUstr"
0x140828fcd  mov     ecx, edi
0x140828fcf  call    AslLogCallPrintf
0x140828fd4  mov     ebx, 0C00000E5h
0x140828fd9  jmp     short loc_14082901C
0x140828fdb  mov     rcx, [rsi+8]
0x140828fdf  mov     ebx, r15d
0x140828fe2  movzx   edx, r9w
0x140828fe6  add     r9w, r9w
0x140828fea  mov     [rcx+rdx*2], r15w
0x140828fef  mov     [rsi], r9w
0x140828ff3  jmp     short loc_14082901C
0x140828ff5  mov     ebx, 0C00000F2h
0x140828ffa  lea     r9, aAslppathgetfor; "AslpPathGetFormatInfo failed [%x]"
0x140829001  mov     r8d, 2DAh
0x140829007  mov     [rsp+78h+var_58], ebx
0x14082900b  lea     rdx, aAslpathcleanus_0; "AslPathCleanUstr"
0x140829012  mov     ecx, 1
0x140829017  call    AslLogCallPrintf
0x14082901c  mov     eax, ebx
0x14082901e  add     rsp, 38h
0x140829022  pop     r15
0x140829024  pop     r14
0x140829026  pop     r13
0x140829028  pop     r12
0x14082902a  pop     rdi
0x14082902b  pop     rsi
0x14082902c  pop     rbp
0x14082902d  pop     rbx
0x14082902e  retn
```
