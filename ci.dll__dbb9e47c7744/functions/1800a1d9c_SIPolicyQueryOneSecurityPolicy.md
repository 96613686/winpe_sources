# SIPolicyQueryOneSecurityPolicy

- ea: `0x1800a1d9c`
- end: `0x1800a200c`
- name: `SIPolicyQueryOneSecurityPolicy`
- size: `624`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180078e10`
- `0x180078f64`
- `0x18007a240`
- `0x18007a508`
- `0x18007a9c0`
- `0x18007d614`
- `0x1800a09a0`
- `0x1800a1880`
- `0x1800a2194`
- `0x1800ae2d0`
- `0x1800c8760`
- `0x1800e8d5c`

## callees

- `0x18002c080`
- `0x1800a1d9c`

## import_xrefs

- `ntoskrnl!bsearch` at `0x1800a1e46`
- `ntoskrnl!bsearch` at `0x1800a1e83`
- `ntoskrnl!bsearch` at `0x1800a1eb9`
- `ntoskrnl!bsearch` at `0x1800a1e46`
- `ntoskrnl!bsearch` at `0x1800a1e83`
- `ntoskrnl!bsearch` at `0x1800a1eb9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800a1ddc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800a1df9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800a1ddc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800a1df9`

## pseudocode

```c
__int64 __fastcall SIPolicyQueryOneSecurityPolicy(
        __int64 a1,
        const UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        _DWORD *a6,
        int *a7)
{
  int v7; // eax
  __int128 v9; // rdi
  unsigned int v11; // ebx
  size_t v12; // r8
  const void *v13; // rdx
  const void **v14; // rdi
  size_t v15; // r8
  const void *v16; // rdx
  size_t v17; // r8
  const void *v18; // rdx
  int v19; // edx
  __int64 v20; // rdx
  unsigned int v21; // ecx
  int *v22; // rsi
  int v23; // eax
  unsigned int v24; // ecx
  int v25; // ecx
  __int128 Key; // [rsp+30h] [rbp-20h] BYREF
  __int128 v28; // [rsp+40h] [rbp-10h]

  v7 = *(_DWORD *)(a1 + 768);
  *((_QWORD *)&v9 + 1) = a3;
  *(_QWORD *)&v9 = a2;
  Key = 0;
  v28 = 0;
  if ( (v7 & 1) != 0
    || !RtlEqualUnicodeString(a2, &stru_18002EF58, 1u)
    || !RtlEqualUnicodeString(*((PCUNICODE_STRING *)&v9 + 1), &stru_18002EF68, 1u) )
  {
    v12 = *(unsigned int *)(a1 + 688);
    v13 = *(const void **)(a1 + 696);
    Key = v9;
    *(_QWORD *)&v28 = a4;
    v14 = (const void **)bsearch(
                           &Key,
                           v13,
                           v12,
                           0x48u,
                           (int (__cdecl *)(const void *, const void *))SIPolicySecureSettingSearchCompare);
    if ( v14 )
      goto LABEL_8;
    v15 = *(unsigned int *)(a1 + 688);
    v16 = *(const void **)(a1 + 696);
    *(_QWORD *)&v28 = a4;
    *((_QWORD *)&Key + 1) = &g_AnyFileWildCardString;
    v14 = (const void **)bsearch(
                           &Key,
                           v16,
                           v15,
                           0x48u,
                           (int (__cdecl *)(const void *, const void *))SIPolicySecureSettingSearchCompare);
    if ( v14
      || (v17 = *(unsigned int *)(a1 + 688),
          v18 = *(const void **)(a1 + 696),
          *((_QWORD *)&Key + 1) = *((_QWORD *)&v9 + 1),
          *(_QWORD *)&v28 = &g_AnyFileWildCardString,
          (v14 = (const void **)bsearch(
                                  &Key,
                                  v18,
                                  v17,
                                  0x48u,
                                  (int (__cdecl *)(const void *, const void *))SIPolicySecureSettingSearchCompare)) != 0) )
    {
LABEL_8:
      v19 = *(_DWORD *)v14;
      v11 = 0;
      if ( *(_DWORD *)v14 )
      {
        if ( *(_DWORD *)v14 != 1 )
        {
          if ( *(_DWORD *)v14 == 2 )
          {
            *a5 = v19;
            v21 = *((_DWORD *)v14 + 14);
            if ( !a6 )
              goto LABEL_19;
            v22 = a7;
            if ( *a7 < v21 )
            {
              v11 = -1073741789;
              *a7 = v21;
              return v11;
            }
            memmove(a6, v14[8], *((unsigned int *)v14 + 14));
            v23 = *((_DWORD *)v14 + 14);
          }
          else
          {
            if ( *(_DWORD *)v14 != 3 )
              return (unsigned int)-1058471933;
            *a5 = v19;
            v20 = *((unsigned __int16 *)v14 + 28);
            if ( !a6 )
            {
              v21 = v20 + 2;
LABEL_19:
              *a7 = v21;
              return v11;
            }
            v22 = a7;
            if ( (unsigned int)*a7 >= (unsigned __int64)(v20 + 2) )
            {
              memmove(a6, v14[8], *((unsigned __int16 *)v14 + 28));
              *((_WORD *)a6 + ((unsigned __int64)*((unsigned __int16 *)v14 + 28) >> 1)) = 0;
              v23 = *((unsigned __int16 *)v14 + 28) + 2;
            }
            else
            {
              v11 = -1073741789;
              v23 = v20 + 2;
            }
          }
          *v22 = v23;
          return v11;
        }
        *a5 = v19;
        if ( !a6 )
        {
          *a7 = 4;
          return v11;
        }
        v24 = *a7;
        *a7 = 4;
        if ( v24 >= 4 )
        {
          *a6 = *((_DWORD *)v14 + 14);
          return v11;
        }
      }
      else
      {
        *a5 = 0;
        if ( !a6 )
        {
          *a7 = 1;
          return v11;
        }
        v25 = *a7;
        *a7 = 1;
        if ( v25 )
        {
          *(_BYTE *)a6 = *((_BYTE *)v14 + 56);
          return v11;
        }
      }
      return (unsigned int)-1073741789;
    }
  }
  return (unsigned int)-1073741275;
}

```

## disassembly

```asm
0x1800a1d9c  push    rbp
0x1800a1d9e  push    rbx
0x1800a1d9f  push    rsi
0x1800a1da0  push    rdi
0x1800a1da1  push    r12
0x1800a1da3  push    r13
0x1800a1da5  push    r14
0x1800a1da7  mov     rbp, rsp
0x1800a1daa  sub     rsp, 50h
0x1800a1dae  mov     eax, [rcx+300h]
0x1800a1db4  xorps   xmm0, xmm0
0x1800a1db7  mov     r14, r9
0x1800a1dba  mov     rsi, r8
0x1800a1dbd  mov     rdi, rdx
0x1800a1dc0  mov     rbx, rcx
0x1800a1dc3  movups  [rbp+Key], xmm0
0x1800a1dc7  movups  [rbp+var_10], xmm0
0x1800a1dcb  test    al, 1
0x1800a1dcd  jnz     short loc_1800A1E13
0x1800a1dcf  mov     r8b, 1; CaseInSensitive
0x1800a1dd2  lea     rdx, stru_18002EF58; String2
0x1800a1dd9  mov     rcx, rdi; String1
0x1800a1ddc  call    cs:__imp_RtlEqualUnicodeString
0x1800a1de3  nop     dword ptr [rax+rax+00h]
0x1800a1de8  test    al, al
0x1800a1dea  jz      short loc_1800A1E13
0x1800a1dec  mov     r8b, 1; CaseInSensitive
0x1800a1def  lea     rdx, stru_18002EF68; String2
0x1800a1df6  mov     rcx, rsi; String1
0x1800a1df9  call    cs:__imp_RtlEqualUnicodeString
0x1800a1e00  nop     dword ptr [rax+rax+00h]
0x1800a1e05  test    al, al
0x1800a1e07  jz      short loc_1800A1E13
0x1800a1e09  mov     ebx, 0C0000225h
0x1800a1e0e  jmp     loc_1800A1FFA
0x1800a1e13  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800a1e1a  lea     r13, SIPolicySecureSettingSearchCompare
0x1800a1e21  mov     rdx, [rbx+2B8h]; Base
0x1800a1e28  lea     rcx, [rbp+Key]; Key
0x1800a1e2c  mov     r12d, 48h ; 'H'
0x1800a1e32  mov     qword ptr [rbp+Key], rdi
0x1800a1e36  mov     r9d, r12d; SizeOfElements
0x1800a1e39  mov     qword ptr [rbp+Key+8], rsi
0x1800a1e3d  mov     qword ptr [rbp+var_10], r14
0x1800a1e41  mov     [rsp+50h+PtFuncCompare], r13; PtFuncCompare
0x1800a1e46  call    cs:__imp_bsearch
0x1800a1e4d  nop     dword ptr [rax+rax+00h]
0x1800a1e52  mov     rdi, rax
0x1800a1e55  test    rax, rax
0x1800a1e58  jnz     short loc_1800A1ED1
0x1800a1e5a  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800a1e61  lea     rcx, [rbp+Key]; Key
0x1800a1e65  mov     rdx, [rbx+2B8h]; Base
0x1800a1e6c  mov     r9d, r12d; SizeOfElements
0x1800a1e6f  mov     qword ptr [rbp+var_10], r14
0x1800a1e73  lea     r14, g_AnyFileWildCardString
0x1800a1e7a  mov     qword ptr [rbp+Key+8], r14
0x1800a1e7e  mov     [rsp+50h+PtFuncCompare], r13; PtFuncCompare
0x1800a1e83  call    cs:__imp_bsearch
0x1800a1e8a  nop     dword ptr [rax+rax+00h]
0x1800a1e8f  mov     rdi, rax
0x1800a1e92  test    rax, rax
0x1800a1e95  jnz     short loc_1800A1ED1
0x1800a1e97  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800a1e9e  lea     rcx, [rbp+Key]; Key
0x1800a1ea2  mov     rdx, [rbx+2B8h]; Base
0x1800a1ea9  mov     r9d, r12d; SizeOfElements
0x1800a1eac  mov     qword ptr [rbp+Key+8], rsi
0x1800a1eb0  mov     qword ptr [rbp+var_10], r14
0x1800a1eb4  mov     [rsp+50h+PtFuncCompare], r13; PtFuncCompare
0x1800a1eb9  call    cs:__imp_bsearch
0x1800a1ec0  nop     dword ptr [rax+rax+00h]
0x1800a1ec5  mov     rdi, rax
0x1800a1ec8  test    rax, rax
0x1800a1ecb  jz      loc_1800A1E09
0x1800a1ed1  mov     edx, [rdi]
0x1800a1ed3  xor     ebx, ebx
0x1800a1ed5  mov     ecx, edx
0x1800a1ed7  test    edx, edx
0x1800a1ed9  jz      loc_1800A1FC6
0x1800a1edf  sub     ecx, 1
0x1800a1ee2  jz      loc_1800A1F97
0x1800a1ee8  sub     ecx, 1
0x1800a1eeb  jz      short loc_1800A1F53
0x1800a1eed  cmp     ecx, 1
0x1800a1ef0  jz      short loc_1800A1EFC
0x1800a1ef2  mov     ebx, 0C0E90003h
0x1800a1ef7  jmp     loc_1800A1FFA
0x1800a1efc  mov     rax, [rbp+arg_20]
0x1800a1f00  mov     r14, [rbp+arg_28]
0x1800a1f04  mov     [rax], edx
0x1800a1f06  movzx   edx, word ptr [rdi+38h]
0x1800a1f0a  test    r14, r14
0x1800a1f0d  jnz     short loc_1800A1F14
0x1800a1f0f  lea     ecx, [rdx+2]
0x1800a1f12  jmp     short loc_1800A1F65
0x1800a1f14  mov     rsi, [rbp+arg_30]
0x1800a1f18  lea     rcx, [rdx+2]
0x1800a1f1c  mov     r8, rdx; Size
0x1800a1f1f  mov     eax, [rsi]
0x1800a1f21  cmp     rax, rcx
0x1800a1f24  jnb     short loc_1800A1F30
0x1800a1f26  mov     ebx, 0C0000023h
0x1800a1f2b  lea     eax, [rdx+2]
0x1800a1f2e  jmp     short loc_1800A1F93
0x1800a1f30  mov     rdx, [rdi+40h]; Src
0x1800a1f34  mov     rcx, r14; void *
0x1800a1f37  call    memmove
0x1800a1f3c  movzx   ecx, word ptr [rdi+38h]
0x1800a1f40  xor     eax, eax
0x1800a1f42  shr     rcx, 1
0x1800a1f45  mov     [r14+rcx*2], ax
0x1800a1f4a  movzx   eax, word ptr [rdi+38h]
0x1800a1f4e  add     eax, 2
0x1800a1f51  jmp     short loc_1800A1F93
0x1800a1f53  mov     rax, [rbp+arg_20]
0x1800a1f57  mov     [rax], edx
0x1800a1f59  mov     rax, [rbp+arg_28]
0x1800a1f5d  mov     ecx, [rdi+38h]
0x1800a1f60  test    rax, rax
0x1800a1f63  jnz     short loc_1800A1F70
0x1800a1f65  mov     rax, [rbp+arg_30]
0x1800a1f69  mov     [rax], ecx
0x1800a1f6b  jmp     loc_1800A1FFA
0x1800a1f70  mov     rsi, [rbp+arg_30]
0x1800a1f74  cmp     [rsi], ecx
0x1800a1f76  jnb     short loc_1800A1F81
0x1800a1f78  mov     ebx, 0C0000023h
0x1800a1f7d  mov     [rsi], ecx
0x1800a1f7f  jmp     short loc_1800A1FFA
0x1800a1f81  mov     rdx, [rdi+40h]; Src
0x1800a1f85  mov     r8, rcx; Size
0x1800a1f88  mov     rcx, rax; void *
0x1800a1f8b  call    memmove
0x1800a1f90  mov     eax, [rdi+38h]
0x1800a1f93  mov     [rsi], eax
0x1800a1f95  jmp     short loc_1800A1FFA
0x1800a1f97  mov     rax, [rbp+arg_20]
0x1800a1f9b  mov     [rax], edx
0x1800a1f9d  mov     rdx, [rbp+arg_28]
0x1800a1fa1  mov     rax, [rbp+arg_30]
0x1800a1fa5  test    rdx, rdx
0x1800a1fa8  jnz     short loc_1800A1FB2
0x1800a1faa  mov     dword ptr [rax], 4
0x1800a1fb0  jmp     short loc_1800A1FFA
0x1800a1fb2  mov     ecx, [rax]
0x1800a1fb4  mov     dword ptr [rax], 4
0x1800a1fba  cmp     ecx, 4
0x1800a1fbd  jb      short loc_1800A1FEE
0x1800a1fbf  mov     eax, [rdi+38h]
0x1800a1fc2  mov     [rdx], eax
0x1800a1fc4  jmp     short loc_1800A1FFA
0x1800a1fc6  mov     rax, [rbp+arg_20]
0x1800a1fca  mov     [rax], edx
0x1800a1fcc  mov     rdx, [rbp+arg_28]
0x1800a1fd0  mov     rax, [rbp+arg_30]
0x1800a1fd4  test    rdx, rdx
0x1800a1fd7  jnz     short loc_1800A1FE1
0x1800a1fd9  mov     dword ptr [rax], 1
0x1800a1fdf  jmp     short loc_1800A1FFA
0x1800a1fe1  mov     ecx, [rax]
0x1800a1fe3  mov     dword ptr [rax], 1
0x1800a1fe9  cmp     ecx, 1
0x1800a1fec  jnb     short loc_1800A1FF5
0x1800a1fee  mov     ebx, 0C0000023h
0x1800a1ff3  jmp     short loc_1800A1FFA
0x1800a1ff5  mov     cl, [rdi+38h]
0x1800a1ff8  mov     [rdx], cl
0x1800a1ffa  mov     eax, ebx
0x1800a1ffc  add     rsp, 50h
0x1800a2000  pop     r14
0x1800a2002  pop     r13
0x1800a2004  pop     r12
0x1800a2006  pop     rdi
0x1800a2007  pop     rsi
0x1800a2008  pop     rbx
0x1800a2009  pop     rbp
0x1800a200a  retn
```
