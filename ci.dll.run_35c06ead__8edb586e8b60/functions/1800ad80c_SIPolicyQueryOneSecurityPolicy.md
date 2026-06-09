# SIPolicyQueryOneSecurityPolicy

- ea: `0x1800ad80c`
- end: `0x1800ada7c`
- name: `SIPolicyQueryOneSecurityPolicy`
- size: `624`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007912c`
- `0x180079280`
- `0x18007a550`
- `0x18007a818`
- `0x18007b140`
- `0x18007e028`
- `0x180091448`
- `0x1800ad228`
- `0x1800ad2f0`
- `0x1800ae170`
- `0x1800c8770`
- `0x1800e9414`

## callees

- `0x18002c200`
- `0x1800ad80c`

## import_xrefs

- `ntoskrnl!bsearch` at `0x1800ad8b6`
- `ntoskrnl!bsearch` at `0x1800ad8f3`
- `ntoskrnl!bsearch` at `0x1800ad929`
- `ntoskrnl!bsearch` at `0x1800ad8b6`
- `ntoskrnl!bsearch` at `0x1800ad8f3`
- `ntoskrnl!bsearch` at `0x1800ad929`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ad84c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ad869`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ad84c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ad869`

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
    || !RtlEqualUnicodeString(a2, &stru_18002F200, 1u)
    || !RtlEqualUnicodeString(*((PCUNICODE_STRING *)&v9 + 1), &stru_18002F210, 1u) )
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
0x1800ad80c  push    rbp
0x1800ad80e  push    rbx
0x1800ad80f  push    rsi
0x1800ad810  push    rdi
0x1800ad811  push    r12
0x1800ad813  push    r13
0x1800ad815  push    r14
0x1800ad817  mov     rbp, rsp
0x1800ad81a  sub     rsp, 50h
0x1800ad81e  mov     eax, [rcx+300h]
0x1800ad824  xorps   xmm0, xmm0
0x1800ad827  mov     r14, r9
0x1800ad82a  mov     rsi, r8
0x1800ad82d  mov     rdi, rdx
0x1800ad830  mov     rbx, rcx
0x1800ad833  movups  [rbp+Key], xmm0
0x1800ad837  movups  [rbp+var_10], xmm0
0x1800ad83b  test    al, 1
0x1800ad83d  jnz     short loc_1800AD883
0x1800ad83f  mov     r8b, 1; CaseInSensitive
0x1800ad842  lea     rdx, stru_18002F200; String2
0x1800ad849  mov     rcx, rdi; String1
0x1800ad84c  call    cs:__imp_RtlEqualUnicodeString
0x1800ad853  nop     dword ptr [rax+rax+00h]
0x1800ad858  test    al, al
0x1800ad85a  jz      short loc_1800AD883
0x1800ad85c  mov     r8b, 1; CaseInSensitive
0x1800ad85f  lea     rdx, stru_18002F210; String2
0x1800ad866  mov     rcx, rsi; String1
0x1800ad869  call    cs:__imp_RtlEqualUnicodeString
0x1800ad870  nop     dword ptr [rax+rax+00h]
0x1800ad875  test    al, al
0x1800ad877  jz      short loc_1800AD883
0x1800ad879  mov     ebx, 0C0000225h
0x1800ad87e  jmp     loc_1800ADA6A
0x1800ad883  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800ad88a  lea     r13, SIPolicySecureSettingSearchCompare
0x1800ad891  mov     rdx, [rbx+2B8h]; Base
0x1800ad898  lea     rcx, [rbp+Key]; Key
0x1800ad89c  mov     r12d, 48h ; 'H'
0x1800ad8a2  mov     qword ptr [rbp+Key], rdi
0x1800ad8a6  mov     r9d, r12d; SizeOfElements
0x1800ad8a9  mov     qword ptr [rbp+Key+8], rsi
0x1800ad8ad  mov     qword ptr [rbp+var_10], r14
0x1800ad8b1  mov     [rsp+50h+PtFuncCompare], r13; PtFuncCompare
0x1800ad8b6  call    cs:__imp_bsearch
0x1800ad8bd  nop     dword ptr [rax+rax+00h]
0x1800ad8c2  mov     rdi, rax
0x1800ad8c5  test    rax, rax
0x1800ad8c8  jnz     short loc_1800AD941
0x1800ad8ca  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800ad8d1  lea     rcx, [rbp+Key]; Key
0x1800ad8d5  mov     rdx, [rbx+2B8h]; Base
0x1800ad8dc  mov     r9d, r12d; SizeOfElements
0x1800ad8df  mov     qword ptr [rbp+var_10], r14
0x1800ad8e3  lea     r14, g_AnyFileWildCardString
0x1800ad8ea  mov     qword ptr [rbp+Key+8], r14
0x1800ad8ee  mov     [rsp+50h+PtFuncCompare], r13; PtFuncCompare
0x1800ad8f3  call    cs:__imp_bsearch
0x1800ad8fa  nop     dword ptr [rax+rax+00h]
0x1800ad8ff  mov     rdi, rax
0x1800ad902  test    rax, rax
0x1800ad905  jnz     short loc_1800AD941
0x1800ad907  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800ad90e  lea     rcx, [rbp+Key]; Key
0x1800ad912  mov     rdx, [rbx+2B8h]; Base
0x1800ad919  mov     r9d, r12d; SizeOfElements
0x1800ad91c  mov     qword ptr [rbp+Key+8], rsi
0x1800ad920  mov     qword ptr [rbp+var_10], r14
0x1800ad924  mov     [rsp+50h+PtFuncCompare], r13; PtFuncCompare
0x1800ad929  call    cs:__imp_bsearch
0x1800ad930  nop     dword ptr [rax+rax+00h]
0x1800ad935  mov     rdi, rax
0x1800ad938  test    rax, rax
0x1800ad93b  jz      loc_1800AD879
0x1800ad941  mov     edx, [rdi]
0x1800ad943  xor     ebx, ebx
0x1800ad945  mov     ecx, edx
0x1800ad947  test    edx, edx
0x1800ad949  jz      loc_1800ADA36
0x1800ad94f  sub     ecx, 1
0x1800ad952  jz      loc_1800ADA07
0x1800ad958  sub     ecx, 1
0x1800ad95b  jz      short loc_1800AD9C3
0x1800ad95d  cmp     ecx, 1
0x1800ad960  jz      short loc_1800AD96C
0x1800ad962  mov     ebx, 0C0E90003h
0x1800ad967  jmp     loc_1800ADA6A
0x1800ad96c  mov     rax, [rbp+arg_20]
0x1800ad970  mov     r14, [rbp+arg_28]
0x1800ad974  mov     [rax], edx
0x1800ad976  movzx   edx, word ptr [rdi+38h]
0x1800ad97a  test    r14, r14
0x1800ad97d  jnz     short loc_1800AD984
0x1800ad97f  lea     ecx, [rdx+2]
0x1800ad982  jmp     short loc_1800AD9D5
0x1800ad984  mov     rsi, [rbp+arg_30]
0x1800ad988  lea     rcx, [rdx+2]
0x1800ad98c  mov     r8, rdx; Size
0x1800ad98f  mov     eax, [rsi]
0x1800ad991  cmp     rax, rcx
0x1800ad994  jnb     short loc_1800AD9A0
0x1800ad996  mov     ebx, 0C0000023h
0x1800ad99b  lea     eax, [rdx+2]
0x1800ad99e  jmp     short loc_1800ADA03
0x1800ad9a0  mov     rdx, [rdi+40h]; Src
0x1800ad9a4  mov     rcx, r14; void *
0x1800ad9a7  call    memmove
0x1800ad9ac  movzx   ecx, word ptr [rdi+38h]
0x1800ad9b0  xor     eax, eax
0x1800ad9b2  shr     rcx, 1
0x1800ad9b5  mov     [r14+rcx*2], ax
0x1800ad9ba  movzx   eax, word ptr [rdi+38h]
0x1800ad9be  add     eax, 2
0x1800ad9c1  jmp     short loc_1800ADA03
0x1800ad9c3  mov     rax, [rbp+arg_20]
0x1800ad9c7  mov     [rax], edx
0x1800ad9c9  mov     rax, [rbp+arg_28]
0x1800ad9cd  mov     ecx, [rdi+38h]
0x1800ad9d0  test    rax, rax
0x1800ad9d3  jnz     short loc_1800AD9E0
0x1800ad9d5  mov     rax, [rbp+arg_30]
0x1800ad9d9  mov     [rax], ecx
0x1800ad9db  jmp     loc_1800ADA6A
0x1800ad9e0  mov     rsi, [rbp+arg_30]
0x1800ad9e4  cmp     [rsi], ecx
0x1800ad9e6  jnb     short loc_1800AD9F1
0x1800ad9e8  mov     ebx, 0C0000023h
0x1800ad9ed  mov     [rsi], ecx
0x1800ad9ef  jmp     short loc_1800ADA6A
0x1800ad9f1  mov     rdx, [rdi+40h]; Src
0x1800ad9f5  mov     r8, rcx; Size
0x1800ad9f8  mov     rcx, rax; void *
0x1800ad9fb  call    memmove
0x1800ada00  mov     eax, [rdi+38h]
0x1800ada03  mov     [rsi], eax
0x1800ada05  jmp     short loc_1800ADA6A
0x1800ada07  mov     rax, [rbp+arg_20]
0x1800ada0b  mov     [rax], edx
0x1800ada0d  mov     rdx, [rbp+arg_28]
0x1800ada11  mov     rax, [rbp+arg_30]
0x1800ada15  test    rdx, rdx
0x1800ada18  jnz     short loc_1800ADA22
0x1800ada1a  mov     dword ptr [rax], 4
0x1800ada20  jmp     short loc_1800ADA6A
0x1800ada22  mov     ecx, [rax]
0x1800ada24  mov     dword ptr [rax], 4
0x1800ada2a  cmp     ecx, 4
0x1800ada2d  jb      short loc_1800ADA5E
0x1800ada2f  mov     eax, [rdi+38h]
0x1800ada32  mov     [rdx], eax
0x1800ada34  jmp     short loc_1800ADA6A
0x1800ada36  mov     rax, [rbp+arg_20]
0x1800ada3a  mov     [rax], edx
0x1800ada3c  mov     rdx, [rbp+arg_28]
0x1800ada40  mov     rax, [rbp+arg_30]
0x1800ada44  test    rdx, rdx
0x1800ada47  jnz     short loc_1800ADA51
0x1800ada49  mov     dword ptr [rax], 1
0x1800ada4f  jmp     short loc_1800ADA6A
0x1800ada51  mov     ecx, [rax]
0x1800ada53  mov     dword ptr [rax], 1
0x1800ada59  cmp     ecx, 1
0x1800ada5c  jnb     short loc_1800ADA65
0x1800ada5e  mov     ebx, 0C0000023h
0x1800ada63  jmp     short loc_1800ADA6A
0x1800ada65  mov     cl, [rdi+38h]
0x1800ada68  mov     [rdx], cl
0x1800ada6a  mov     eax, ebx
0x1800ada6c  add     rsp, 50h
0x1800ada70  pop     r14
0x1800ada72  pop     r13
0x1800ada74  pop     r12
0x1800ada76  pop     rdi
0x1800ada77  pop     rsi
0x1800ada78  pop     rbx
0x1800ada79  pop     rbp
0x1800ada7a  retn
```
