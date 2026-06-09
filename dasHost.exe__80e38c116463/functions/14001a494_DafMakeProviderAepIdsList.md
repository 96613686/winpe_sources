# DafMakeProviderAepIdsList

- ea: `0x14001a494`
- end: `0x14001a6bc`
- name: `DafMakeProviderAepIdsList`
- size: `552`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPCWCH lpString2, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400160d8`

## callees

- `0x1400020d0`
- `0x140009060`
- `0x140009090`
- `0x14001a3a8`
- `0x14001a494`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a64e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a64e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14001a558`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14001a558`

## pseudocode

```c
__int64 __fastcall DafMakeProviderAepIdsList(unsigned __int16 *a1, LPCWCH lpString2, _QWORD *a3)
{
  const WCHAR *v4; // r14
  unsigned __int16 *v5; // rsi
  unsigned int ProviderNameFromAepId; // edi
  int i; // edx
  SIZE_T v8; // rbx
  char *v9; // rax
  void *v10; // rbp
  __int64 v11; // r13
  BOOL v12; // ebx
  int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // r15
  unsigned __int16 *v16; // rdx
  __int64 v17; // r8
  unsigned __int16 *v18; // rax
  __int64 v19; // r14
  signed int LastError; // eax
  void *v21; // rax
  char *v24; // [rsp+80h] [rbp+18h]

  *a3 = 0;
  v4 = lpString2;
  v5 = a1;
  if ( !*a1 )
    return (unsigned int)-2147024809;
  for ( i = 0; a1[i] || a1[i + 1]; ++i )
    ;
  v8 = 2LL * (unsigned int)(i + 2);
  v9 = (char *)DAF_user_alloc(v8);
  v10 = v9;
  if ( !v9 )
    return (unsigned int)-2147024882;
  v24 = v9;
  v11 = 0;
  memset_0(v9, 0, v8);
  while ( 1 )
  {
    v12 = 1;
    if ( !v4 )
      goto LABEL_14;
    ProviderNameFromAepId = DafGetProviderNameFromAepId(v5);
    if ( ProviderNameFromAepId )
      goto LABEL_34;
    v13 = CompareStringOrdinal(0, -1, v4, -1, 1);
    MIDL_user_free(0);
    if ( !v13 )
      break;
    v12 = v13 == 2;
LABEL_14:
    LODWORD(v14) = 0;
    if ( *v5 )
    {
      while ( !(_DWORD)v14 || v5[(unsigned int)(v14 - 1)] != 35 )
      {
        v14 = (unsigned int)(v14 + 1);
        if ( !v5[v14] )
          goto LABEL_18;
      }
    }
    else
    {
LABEL_18:
      LODWORD(v14) = 0;
    }
    v15 = (unsigned int)v14;
    v16 = &v5[(unsigned int)v14];
    if ( !v16 )
    {
      ProviderNameFromAepId = -2147024809;
      goto LABEL_34;
    }
    v17 = 512;
    v18 = v16;
    do
    {
      if ( !*v18 )
        break;
      ++v18;
      --v17;
    }
    while ( v17 );
    ProviderNameFromAepId = v17 == 0 ? 0x80070057 : 0;
    v19 = (512 - v17) & -(__int64)(v17 != 0);
    if ( !v17 )
      goto LABEL_34;
    if ( v12 )
    {
      memcpy_0(v24, v16, 2 * v19);
      v24 += 2 * v19 + 2;
      v11 += v19 + 1;
    }
    v5 += v15 + v19 + 1;
    if ( !*v5 )
    {
      v21 = DAF_user_alloc(2 * v11 + 2);
      *a3 = v21;
      if ( v21 )
        memcpy_0(v21, v10, 2 * v11 + 2);
      else
        ProviderNameFromAepId = -2147024882;
      goto LABEL_34;
    }
    v4 = lpString2;
  }
  LastError = GetLastError();
  ProviderNameFromAepId = LastError;
  if ( LastError > 0 )
    ProviderNameFromAepId = (unsigned __int16)LastError | 0x80070000;
LABEL_34:
  MIDL_user_free(v10);
  return ProviderNameFromAepId;
}

```

## disassembly

```asm
0x14001a494  mov     [rsp+arg_18], rbx
0x14001a499  mov     [rsp+arg_8], rdx
0x14001a49e  push    rbp
0x14001a49f  push    rsi
0x14001a4a0  push    rdi
0x14001a4a1  push    r12
0x14001a4a3  push    r13
0x14001a4a5  push    r14
0x14001a4a7  push    r15
0x14001a4a9  sub     rsp, 30h
0x14001a4ad  xor     r15d, r15d
0x14001a4b0  mov     r12, r8
0x14001a4b3  mov     [r8], r15
0x14001a4b6  mov     r14, rdx
0x14001a4b9  mov     rsi, rcx
0x14001a4bc  mov     [rsp+68h+lpString1], r15
0x14001a4c1  cmp     r15w, [rcx]
0x14001a4c5  jnz     short loc_14001A4D1
0x14001a4c7  mov     edi, 80070057h
0x14001a4cc  jmp     loc_14001A6A2
0x14001a4d1  mov     edx, r15d
0x14001a4d4  mov     eax, edx
0x14001a4d6  lea     ecx, [rdx+1]
0x14001a4d9  cmp     [rsi+rax*2], r15w
0x14001a4de  jnz     short loc_14001A4E7
0x14001a4e0  cmp     [rsi+rcx*2], r15w
0x14001a4e5  jz      short loc_14001A4EB
0x14001a4e7  mov     edx, ecx
0x14001a4e9  jmp     short loc_14001A4D4
0x14001a4eb  lea     ebx, [rdx+2]
0x14001a4ee  add     rbx, rbx
0x14001a4f1  mov     rcx, rbx
0x14001a4f4  call    DAF_user_alloc
0x14001a4f9  mov     rbp, rax
0x14001a4fc  test    rax, rax
0x14001a4ff  jnz     short loc_14001A50B
0x14001a501  mov     edi, 8007000Eh
0x14001a506  jmp     loc_14001A6A2
0x14001a50b  mov     r8, rbx; Size
0x14001a50e  mov     [rsp+68h+arg_10], rbp
0x14001a516  xor     edx, edx; Val
0x14001a518  mov     rcx, rbp; void *
0x14001a51b  mov     r13, r15
0x14001a51e  call    memset_0
0x14001a523  mov     ebx, 1
0x14001a528  test    r14, r14
0x14001a52b  jz      short loc_14001A57E
0x14001a52d  lea     rdx, [rsp+68h+lpString1]
0x14001a532  mov     rcx, rsi; unsigned __int16 *
0x14001a535  call    DafGetProviderNameFromAepId
0x14001a53a  mov     edi, eax
0x14001a53c  test    eax, eax
0x14001a53e  jnz     loc_14001A69A
0x14001a544  mov     rcx, [rsp+68h+lpString1]; lpString1
0x14001a549  or      eax, 0FFFFFFFFh
0x14001a54c  mov     r9d, eax; cchCount2
0x14001a54f  mov     [rsp+68h+bIgnoreCase], ebx; bIgnoreCase
0x14001a553  mov     edx, eax; cchCount1
0x14001a555  mov     r8, r14; lpString2
0x14001a558  call    cs:__imp_CompareStringOrdinal
0x14001a55e  mov     rcx, [rsp+68h+lpString1]; void *
0x14001a563  mov     edi, eax
0x14001a565  call    MIDL_user_free
0x14001a56a  mov     [rsp+68h+lpString1], r15
0x14001a56f  test    edi, edi
0x14001a571  jz      loc_14001A64E
0x14001a577  cmp     edi, 2
0x14001a57a  cmovnz  ebx, r15d
0x14001a57e  mov     edx, r15d
0x14001a581  cmp     [rsi], r15w
0x14001a585  jz      short loc_14001A59E
0x14001a587  test    edx, edx
0x14001a589  jz      short loc_14001A595
0x14001a58b  lea     eax, [rdx-1]
0x14001a58e  cmp     word ptr [rsi+rax*2], 23h ; '#'
0x14001a593  jz      short loc_14001A5A1
0x14001a595  inc     edx
0x14001a597  cmp     [rsi+rdx*2], r15w
0x14001a59c  jnz     short loc_14001A587
0x14001a59e  mov     edx, r15d
0x14001a5a1  mov     r15d, edx
0x14001a5a4  xor     r9d, r9d
0x14001a5a7  lea     rdx, [rsi+r15*2]; Src
0x14001a5ab  test    rdx, rdx
0x14001a5ae  jz      loc_14001A695
0x14001a5b4  mov     r8d, 200h
0x14001a5ba  mov     rax, rdx
0x14001a5bd  cmp     [rax], r9w
0x14001a5c1  jz      short loc_14001A5CD
0x14001a5c3  add     rax, 2
0x14001a5c7  sub     r8, 1
0x14001a5cb  jnz     short loc_14001A5BD
0x14001a5cd  mov     rax, r8
0x14001a5d0  mov     ecx, 200h
0x14001a5d5  neg     rax
0x14001a5d8  mov     rax, r8
0x14001a5db  sbb     edi, edi
0x14001a5dd  sub     rcx, r8
0x14001a5e0  not     edi
0x14001a5e2  and     edi, 80070057h
0x14001a5e8  neg     rax
0x14001a5eb  sbb     r14, r14
0x14001a5ee  and     r14, rcx
0x14001a5f1  test    r8, r8
0x14001a5f4  jz      loc_14001A69A
0x14001a5fa  test    ebx, ebx
0x14001a5fc  jz      short loc_14001A62F
0x14001a5fe  mov     rcx, [rsp+68h+arg_10]; void *
0x14001a606  lea     rbx, [r14+r14]
0x14001a60a  mov     r8, rbx; Size
0x14001a60d  call    memcpy_0
0x14001a612  mov     rax, [rsp+68h+arg_10]
0x14001a61a  inc     r13
0x14001a61d  add     rax, 2
0x14001a621  add     rax, rbx
0x14001a624  mov     [rsp+68h+arg_10], rax
0x14001a62c  add     r13, r14
0x14001a62f  lea     rax, [r15+r14]
0x14001a633  xor     r15d, r15d
0x14001a636  lea     rsi, [rsi+rax*2]
0x14001a63a  add     rsi, 2
0x14001a63e  cmp     [rsi], r15w
0x14001a642  jz      short loc_14001A665
0x14001a644  mov     r14, [rsp+68h+arg_8]
0x14001a649  jmp     loc_14001A523
0x14001a64e  call    cs:__imp_GetLastError
0x14001a654  mov     edi, eax
0x14001a656  test    eax, eax
0x14001a658  jle     short loc_14001A69A
0x14001a65a  movzx   edi, ax
0x14001a65d  or      edi, 80070000h
0x14001a663  jmp     short loc_14001A69A
0x14001a665  lea     rbx, ds:2[r13*2]
0x14001a66d  mov     rcx, rbx
0x14001a670  call    DAF_user_alloc
0x14001a675  mov     [r12], rax
0x14001a679  test    rax, rax
0x14001a67c  jnz     short loc_14001A685
0x14001a67e  mov     edi, 8007000Eh
0x14001a683  jmp     short loc_14001A69A
0x14001a685  mov     r8, rbx; Size
0x14001a688  mov     rdx, rbp; Src
0x14001a68b  mov     rcx, rax; void *
0x14001a68e  call    memcpy_0
0x14001a693  jmp     short loc_14001A69A
0x14001a695  mov     edi, 80070057h
0x14001a69a  mov     rcx, rbp; void *
0x14001a69d  call    MIDL_user_free
0x14001a6a2  mov     rbx, [rsp+68h+arg_18]
0x14001a6aa  mov     eax, edi
0x14001a6ac  add     rsp, 30h
0x14001a6b0  pop     r15
0x14001a6b2  pop     r14
0x14001a6b4  pop     r13
0x14001a6b6  pop     r12
0x14001a6b8  pop     rdi
0x14001a6b9  pop     rsi
0x14001a6ba  pop     rbp
0x14001a6bb  retn
```
