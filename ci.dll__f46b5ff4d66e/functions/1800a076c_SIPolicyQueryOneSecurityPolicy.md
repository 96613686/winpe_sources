# SIPolicyQueryOneSecurityPolicy

- ea: `0x1800a076c`
- end: `0x1800a09dc`
- name: `SIPolicyQueryOneSecurityPolicy`
- size: `624`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180077860`
- `0x1800779b4`
- `0x180078c90`
- `0x180078f58`
- `0x180079410`
- `0x18007c064`
- `0x18009f370`
- `0x1800a0250`
- `0x1800a0b64`
- `0x1800ace50`
- `0x1800c72e0`
- `0x1800e77b0`

## callees

- `0x18002c040`
- `0x1800a076c`

## import_xrefs

- `ntoskrnl!bsearch` at `0x1800a0816`
- `ntoskrnl!bsearch` at `0x1800a0853`
- `ntoskrnl!bsearch` at `0x1800a0889`
- `ntoskrnl!bsearch` at `0x1800a0816`
- `ntoskrnl!bsearch` at `0x1800a0853`
- `ntoskrnl!bsearch` at `0x1800a0889`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800a07ac`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800a07c9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800a07ac`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800a07c9`

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
0x1800a076c  push    rbp
0x1800a076e  push    rbx
0x1800a076f  push    rsi
0x1800a0770  push    rdi
0x1800a0771  push    r12
0x1800a0773  push    r13
0x1800a0775  push    r14
0x1800a0777  mov     rbp, rsp
0x1800a077a  sub     rsp, 50h
0x1800a077e  mov     eax, [rcx+300h]
0x1800a0784  xorps   xmm0, xmm0
0x1800a0787  mov     r14, r9
0x1800a078a  mov     rsi, r8
0x1800a078d  mov     rdi, rdx
0x1800a0790  mov     rbx, rcx
0x1800a0793  movups  [rbp+Key], xmm0
0x1800a0797  movups  [rbp+var_10], xmm0
0x1800a079b  test    al, 1
0x1800a079d  jnz     short loc_1800A07E3
0x1800a079f  mov     r8b, 1; CaseInSensitive
0x1800a07a2  lea     rdx, stru_18002EF58; String2
0x1800a07a9  mov     rcx, rdi; String1
0x1800a07ac  call    cs:__imp_RtlEqualUnicodeString
0x1800a07b3  nop     dword ptr [rax+rax+00h]
0x1800a07b8  test    al, al
0x1800a07ba  jz      short loc_1800A07E3
0x1800a07bc  mov     r8b, 1; CaseInSensitive
0x1800a07bf  lea     rdx, stru_18002EF68; String2
0x1800a07c6  mov     rcx, rsi; String1
0x1800a07c9  call    cs:__imp_RtlEqualUnicodeString
0x1800a07d0  nop     dword ptr [rax+rax+00h]
0x1800a07d5  test    al, al
0x1800a07d7  jz      short loc_1800A07E3
0x1800a07d9  mov     ebx, 0C0000225h
0x1800a07de  jmp     loc_1800A09CA
0x1800a07e3  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800a07ea  lea     r13, SIPolicySecureSettingSearchCompare
0x1800a07f1  mov     rdx, [rbx+2B8h]; Base
0x1800a07f8  lea     rcx, [rbp+Key]; Key
0x1800a07fc  mov     r12d, 48h ; 'H'
0x1800a0802  mov     qword ptr [rbp+Key], rdi
0x1800a0806  mov     r9d, r12d; SizeOfElements
0x1800a0809  mov     qword ptr [rbp+Key+8], rsi
0x1800a080d  mov     qword ptr [rbp+var_10], r14
0x1800a0811  mov     [rsp+50h+PtFuncCompare], r13; PtFuncCompare
0x1800a0816  call    cs:__imp_bsearch
0x1800a081d  nop     dword ptr [rax+rax+00h]
0x1800a0822  mov     rdi, rax
0x1800a0825  test    rax, rax
0x1800a0828  jnz     short loc_1800A08A1
0x1800a082a  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800a0831  lea     rcx, [rbp+Key]; Key
0x1800a0835  mov     rdx, [rbx+2B8h]; Base
0x1800a083c  mov     r9d, r12d; SizeOfElements
0x1800a083f  mov     qword ptr [rbp+var_10], r14
0x1800a0843  lea     r14, g_AnyFileWildCardString
0x1800a084a  mov     qword ptr [rbp+Key+8], r14
0x1800a084e  mov     [rsp+50h+PtFuncCompare], r13; PtFuncCompare
0x1800a0853  call    cs:__imp_bsearch
0x1800a085a  nop     dword ptr [rax+rax+00h]
0x1800a085f  mov     rdi, rax
0x1800a0862  test    rax, rax
0x1800a0865  jnz     short loc_1800A08A1
0x1800a0867  mov     r8d, [rbx+2B0h]; NumOfElements
0x1800a086e  lea     rcx, [rbp+Key]; Key
0x1800a0872  mov     rdx, [rbx+2B8h]; Base
0x1800a0879  mov     r9d, r12d; SizeOfElements
0x1800a087c  mov     qword ptr [rbp+Key+8], rsi
0x1800a0880  mov     qword ptr [rbp+var_10], r14
0x1800a0884  mov     [rsp+50h+PtFuncCompare], r13; PtFuncCompare
0x1800a0889  call    cs:__imp_bsearch
0x1800a0890  nop     dword ptr [rax+rax+00h]
0x1800a0895  mov     rdi, rax
0x1800a0898  test    rax, rax
0x1800a089b  jz      loc_1800A07D9
0x1800a08a1  mov     edx, [rdi]
0x1800a08a3  xor     ebx, ebx
0x1800a08a5  mov     ecx, edx
0x1800a08a7  test    edx, edx
0x1800a08a9  jz      loc_1800A0996
0x1800a08af  sub     ecx, 1
0x1800a08b2  jz      loc_1800A0967
0x1800a08b8  sub     ecx, 1
0x1800a08bb  jz      short loc_1800A0923
0x1800a08bd  cmp     ecx, 1
0x1800a08c0  jz      short loc_1800A08CC
0x1800a08c2  mov     ebx, 0C0E90003h
0x1800a08c7  jmp     loc_1800A09CA
0x1800a08cc  mov     rax, [rbp+arg_20]
0x1800a08d0  mov     r14, [rbp+arg_28]
0x1800a08d4  mov     [rax], edx
0x1800a08d6  movzx   edx, word ptr [rdi+38h]
0x1800a08da  test    r14, r14
0x1800a08dd  jnz     short loc_1800A08E4
0x1800a08df  lea     ecx, [rdx+2]
0x1800a08e2  jmp     short loc_1800A0935
0x1800a08e4  mov     rsi, [rbp+arg_30]
0x1800a08e8  lea     rcx, [rdx+2]
0x1800a08ec  mov     r8, rdx; Size
0x1800a08ef  mov     eax, [rsi]
0x1800a08f1  cmp     rax, rcx
0x1800a08f4  jnb     short loc_1800A0900
0x1800a08f6  mov     ebx, 0C0000023h
0x1800a08fb  lea     eax, [rdx+2]
0x1800a08fe  jmp     short loc_1800A0963
0x1800a0900  mov     rdx, [rdi+40h]; Src
0x1800a0904  mov     rcx, r14; void *
0x1800a0907  call    memmove
0x1800a090c  movzx   ecx, word ptr [rdi+38h]
0x1800a0910  xor     eax, eax
0x1800a0912  shr     rcx, 1
0x1800a0915  mov     [r14+rcx*2], ax
0x1800a091a  movzx   eax, word ptr [rdi+38h]
0x1800a091e  add     eax, 2
0x1800a0921  jmp     short loc_1800A0963
0x1800a0923  mov     rax, [rbp+arg_20]
0x1800a0927  mov     [rax], edx
0x1800a0929  mov     rax, [rbp+arg_28]
0x1800a092d  mov     ecx, [rdi+38h]
0x1800a0930  test    rax, rax
0x1800a0933  jnz     short loc_1800A0940
0x1800a0935  mov     rax, [rbp+arg_30]
0x1800a0939  mov     [rax], ecx
0x1800a093b  jmp     loc_1800A09CA
0x1800a0940  mov     rsi, [rbp+arg_30]
0x1800a0944  cmp     [rsi], ecx
0x1800a0946  jnb     short loc_1800A0951
0x1800a0948  mov     ebx, 0C0000023h
0x1800a094d  mov     [rsi], ecx
0x1800a094f  jmp     short loc_1800A09CA
0x1800a0951  mov     rdx, [rdi+40h]; Src
0x1800a0955  mov     r8, rcx; Size
0x1800a0958  mov     rcx, rax; void *
0x1800a095b  call    memmove
0x1800a0960  mov     eax, [rdi+38h]
0x1800a0963  mov     [rsi], eax
0x1800a0965  jmp     short loc_1800A09CA
0x1800a0967  mov     rax, [rbp+arg_20]
0x1800a096b  mov     [rax], edx
0x1800a096d  mov     rdx, [rbp+arg_28]
0x1800a0971  mov     rax, [rbp+arg_30]
0x1800a0975  test    rdx, rdx
0x1800a0978  jnz     short loc_1800A0982
0x1800a097a  mov     dword ptr [rax], 4
0x1800a0980  jmp     short loc_1800A09CA
0x1800a0982  mov     ecx, [rax]
0x1800a0984  mov     dword ptr [rax], 4
0x1800a098a  cmp     ecx, 4
0x1800a098d  jb      short loc_1800A09BE
0x1800a098f  mov     eax, [rdi+38h]
0x1800a0992  mov     [rdx], eax
0x1800a0994  jmp     short loc_1800A09CA
0x1800a0996  mov     rax, [rbp+arg_20]
0x1800a099a  mov     [rax], edx
0x1800a099c  mov     rdx, [rbp+arg_28]
0x1800a09a0  mov     rax, [rbp+arg_30]
0x1800a09a4  test    rdx, rdx
0x1800a09a7  jnz     short loc_1800A09B1
0x1800a09a9  mov     dword ptr [rax], 1
0x1800a09af  jmp     short loc_1800A09CA
0x1800a09b1  mov     ecx, [rax]
0x1800a09b3  mov     dword ptr [rax], 1
0x1800a09b9  cmp     ecx, 1
0x1800a09bc  jnb     short loc_1800A09C5
0x1800a09be  mov     ebx, 0C0000023h
0x1800a09c3  jmp     short loc_1800A09CA
0x1800a09c5  mov     cl, [rdi+38h]
0x1800a09c8  mov     [rdx], cl
0x1800a09ca  mov     eax, ebx
0x1800a09cc  add     rsp, 50h
0x1800a09d0  pop     r14
0x1800a09d2  pop     r13
0x1800a09d4  pop     r12
0x1800a09d6  pop     rdi
0x1800a09d7  pop     rsi
0x1800a09d8  pop     rbx
0x1800a09d9  pop     rbp
0x1800a09da  retn
```
