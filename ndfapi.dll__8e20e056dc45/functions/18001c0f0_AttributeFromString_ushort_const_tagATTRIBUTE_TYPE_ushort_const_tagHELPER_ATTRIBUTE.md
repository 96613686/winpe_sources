# AttributeFromString(ushort const *,tagATTRIBUTE_TYPE,ushort const *,tagHELPER_ATTRIBUTE &)

- ea: `0x18001c0f0`
- end: `0x18001c548`
- name: `?AttributeFromString@@YAKPEBGW4tagATTRIBUTE_TYPE@@0AEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `1112`
- prototype: `__int64 __fastcall(const unsigned __int16 *, ATTRIBUTE_TYPE, unsigned __int16 *, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180011934`

## callees

- `0x180007ee4`
- `0x18000f800`
- `0x18001c010`
- `0x18001c0f0`
- `0x18001c8b8`
- `0x18001ca2c`
- `0x18001f652`

## import_xrefs

- `msvcrt!_errno` at `0x18001c167`
- `msvcrt!_errno` at `0x18001c187`
- `msvcrt!_errno` at `0x18001c1c7`
- `msvcrt!_errno` at `0x18001c1e7`
- `msvcrt!_errno` at `0x18001c215`
- `msvcrt!_errno` at `0x18001c235`
- `msvcrt!_errno` at `0x18001c267`
- `msvcrt!_errno` at `0x18001c287`
- `msvcrt!_errno` at `0x18001c2ba`
- `msvcrt!_errno` at `0x18001c2da`
- `msvcrt!_errno` at `0x18001c30b`
- `msvcrt!_errno` at `0x18001c32b`
- `msvcrt!_errno` at `0x18001c361`
- `msvcrt!_errno` at `0x18001c381`
- `msvcrt!_errno` at `0x18001c4f4`
- `msvcrt!_errno` at `0x18001c167`
- `msvcrt!_errno` at `0x18001c187`
- `msvcrt!_errno` at `0x18001c1c7`
- `msvcrt!_errno` at `0x18001c1e7`
- `msvcrt!_errno` at `0x18001c215`
- `msvcrt!_errno` at `0x18001c235`
- `msvcrt!_errno` at `0x18001c267`
- `msvcrt!_errno` at `0x18001c287`
- `msvcrt!_errno` at `0x18001c2ba`
- `msvcrt!_errno` at `0x18001c2da`
- `msvcrt!_errno` at `0x18001c30b`
- `msvcrt!_errno` at `0x18001c32b`
- `msvcrt!_errno` at `0x18001c361`
- `msvcrt!_errno` at `0x18001c381`
- `msvcrt!_errno` at `0x18001c4f4`
- `msvcrt!_wcstoi64` at `0x18001c17e`
- `msvcrt!_wcstoi64` at `0x18001c1de`
- `msvcrt!_wcstoi64` at `0x18001c22c`
- `msvcrt!_wcstoi64` at `0x18001c27e`
- `msvcrt!_wcstoi64` at `0x18001c2d1`
- `msvcrt!_wcstoi64` at `0x18001c322`
- `msvcrt!_wcstoi64` at `0x18001c378`
- `msvcrt!_wcstoi64` at `0x18001c519`
- `msvcrt!_wcstoi64` at `0x18001c17e`
- `msvcrt!_wcstoi64` at `0x18001c1de`
- `msvcrt!_wcstoi64` at `0x18001c22c`
- `msvcrt!_wcstoi64` at `0x18001c27e`
- `msvcrt!_wcstoi64` at `0x18001c2d1`
- `msvcrt!_wcstoi64` at `0x18001c322`
- `msvcrt!_wcstoi64` at `0x18001c378`
- `msvcrt!_wcstoi64` at `0x18001c519`
- `msvcrt!_wcstoui64` at `0x18001c4eb`
- `msvcrt!_wcstoui64` at `0x18001c4eb`
- `msvcrt!wcschr` at `0x18001c4ce`
- `msvcrt!wcschr` at `0x18001c4ce`
- `ole32!CoTaskMemAlloc` at `0x18001c432`
- `ole32!CoTaskMemAlloc` at `0x18001c432`
- `ole32!CLSIDFromString` at `0x18001c49d`
- `ole32!CLSIDFromString` at `0x18001c49d`

## pseudocode

```c
__int64 __fastcall AttributeFromString(
        const unsigned __int16 *a1,
        ATTRIBUTE_TYPE a2,
        unsigned __int16 *a3,
        struct tagHELPER_ATTRIBUTE *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  int v10; // ecx
  unsigned int v11; // edx
  unsigned int v12; // eax
  LONGLONG v13; // rbx
  unsigned __int64 v15; // rax
  unsigned int v16; // r12d
  BYTE *v17; // rax
  int v18; // ebx
  wchar_t *EndPtr[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( a2 > AT_INT64 )
  {
    if ( a2 != AT_UINT64 )
    {
      switch ( a2 )
      {
        case AT_STRING:
          v11 = (unsigned __int16)StringCopyWithAlloc(&a4->PWStr, a3);
          goto LABEL_41;
        case AT_GUID:
          v11 = (CLSIDFromString(a3, &a4->Guid) >> 31) & 0x57;
          goto LABEL_41;
        case AT_LIFE_TIME:
          return 50;
        case AT_SOCKADDR:
          v12 = ParseString<tagSOCK_ADDR>(a3, (LPSOCKADDR)&a4->Boolean);
          goto LABEL_38;
      }
      if ( a2 != AT_OCTET_STRING )
        return 87;
      a4->Boolean = 0;
      v15 = -1;
      a4->OctetString.lpValue = 0;
      do
        ++v15;
      while ( a3[v15] );
      if ( v15 )
      {
        v16 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v15 >> 1);
        v17 = (BYTE *)CoTaskMemAlloc(v16);
        a4->OctetString.lpValue = v17;
        v11 = 14;
        if ( v17 )
        {
          memset_0(v17, 0, v16);
          v18 = 0;
          if ( !HexToBin(a3, a4->OctetString.lpValue, v16, &a4->DWord) )
            v18 = 87;
          v11 = v18;
        }
        goto LABEL_41;
      }
LABEL_55:
      v11 = 0;
      goto LABEL_41;
    }
    if ( wcschr(a3, 0x2Du) )
      goto LABEL_40;
    EndPtr[0] = 0;
    v13 = _wcstoui64(a3, EndPtr, 0);
    if ( *_errno() == 34 && v13 && (v13 == -1 || _wcstoi64(a3, 0, 0) < 0) )
      goto LABEL_40;
LABEL_69:
    if ( !EndPtr[0] || *EndPtr[0] )
      goto LABEL_40;
    a4->Int64 = v13;
    goto LABEL_55;
  }
  if ( a2 == AT_INT64 )
  {
    *_errno() = 0;
    EndPtr[0] = 0;
    v13 = _wcstoi64(a3, EndPtr, 0);
    if ( *_errno() == 34 )
      goto LABEL_40;
    goto LABEL_69;
  }
  if ( a2 != AT_BOOLEAN )
  {
    switch ( a2 )
    {
      case AT_INT8:
        *_errno() = 0;
        EndPtr[0] = 0;
        v8 = _wcstoi64(a3, EndPtr, 0);
        if ( *_errno() != 34 && EndPtr[0] && !*EndPtr[0] )
        {
          a4->Char = v8;
          v9 = (char)v8;
          goto LABEL_14;
        }
        break;
      case AT_UINT8:
        *_errno() = 0;
        EndPtr[0] = 0;
        v8 = _wcstoi64(a3, EndPtr, 0);
        if ( *_errno() != 34 && EndPtr[0] && !*EndPtr[0] )
        {
          v9 = (unsigned __int8)v8;
          a4->Char = v8;
          goto LABEL_14;
        }
        break;
      case AT_INT16:
        *_errno() = 0;
        EndPtr[0] = 0;
        v8 = _wcstoi64(a3, EndPtr, 0);
        if ( *_errno() != 34 && EndPtr[0] && !*EndPtr[0] )
        {
          a4->Short = v8;
          v9 = (__int16)v8;
          goto LABEL_14;
        }
        break;
      case AT_UINT16:
        *_errno() = 0;
        EndPtr[0] = 0;
        v8 = _wcstoi64(a3, EndPtr, 0);
        if ( *_errno() != 34 && EndPtr[0] && !*EndPtr[0] )
        {
          v9 = (unsigned __int16)v8;
          a4->Short = v8;
          goto LABEL_14;
        }
        break;
      case AT_INT32:
        *_errno() = 0;
        EndPtr[0] = 0;
        v8 = _wcstoi64(a3, EndPtr, 0);
        if ( *_errno() != 34 && EndPtr[0] && !*EndPtr[0] )
        {
          a4->Boolean = v8;
          v9 = (int)v8;
          goto LABEL_14;
        }
        break;
      case AT_UINT32:
        *_errno() = 0;
        EndPtr[0] = 0;
        v8 = _wcstoi64(a3, EndPtr, 0);
        if ( *_errno() != 34 && EndPtr[0] && !*EndPtr[0] )
        {
          v9 = (unsigned int)v8;
          a4->Boolean = v8;
LABEL_14:
          v10 = 0;
          if ( v9 != v8 )
            v10 = 87;
          v11 = v10;
          goto LABEL_41;
        }
        break;
      default:
        return 87;
    }
LABEL_40:
    v11 = 87;
    goto LABEL_41;
  }
  v12 = ParseStringBool(a3, &a4->Boolean);
LABEL_38:
  v11 = v12;
LABEL_41:
  if ( !v11 )
  {
    a4->type = a2;
    if ( a1 )
      return (unsigned __int16)StringCopyWithAlloc(&a4->pwszName, a1);
  }
  return v11;
}

```

## disassembly

```asm
0x18001c0f0  push    rbp
0x18001c0f2  push    rbx
0x18001c0f3  push    rsi
0x18001c0f4  push    rdi
0x18001c0f5  push    r12
0x18001c0f7  push    r13
0x18001c0f9  push    r14
0x18001c0fb  push    r15
0x18001c0fd  mov     rbp, rsp
0x18001c100  sub     rsp, 38h
0x18001c104  xor     r12d, r12d
0x18001c107  mov     rsi, r9
0x18001c10a  mov     rdi, r8
0x18001c10d  mov     r14d, edx
0x18001c110  mov     r13, rcx
0x18001c113  cmp     edx, 8
0x18001c116  jg      loc_18001C3C3
0x18001c11c  jz      loc_18001C361
0x18001c122  mov     r9d, edx
0x18001c125  sub     r9d, 1
0x18001c129  jz      loc_18001C351
0x18001c12f  sub     r9d, 1
0x18001c133  jz      loc_18001C30B
0x18001c139  sub     r9d, 1
0x18001c13d  jz      loc_18001C2BA
0x18001c143  sub     r9d, 1
0x18001c147  jz      loc_18001C267
0x18001c14d  sub     r9d, 1
0x18001c151  jz      loc_18001C215
0x18001c157  sub     r9d, 1
0x18001c15b  jz      short loc_18001C1C7
0x18001c15d  cmp     r9d, 1
0x18001c161  jnz     loc_18001C3F8
0x18001c167  call    cs:__imp__errno
0x18001c16d  xor     r8d, r8d; Radix
0x18001c170  lea     rdx, [rbp+EndPtr]; EndPtr
0x18001c174  mov     rcx, rdi; String
0x18001c177  mov     [rax], r12d
0x18001c17a  mov     [rbp+EndPtr], r12
0x18001c17e  call    cs:__imp__wcstoi64
0x18001c184  mov     rbx, rax
0x18001c187  call    cs:__imp__errno
0x18001c18d  cmp     dword ptr [rax], 22h ; '"'
0x18001c190  jz      loc_18001C390
0x18001c196  mov     rax, [rbp+EndPtr]
0x18001c19a  test    rax, rax
0x18001c19d  jz      loc_18001C390
0x18001c1a3  cmp     [rax], r12w
0x18001c1a7  jnz     loc_18001C390
0x18001c1ad  mov     eax, ebx
0x18001c1af  mov     [rsi+10h], eax
0x18001c1b2  mov     edx, 57h ; 'W'
0x18001c1b7  cmp     rax, rbx
0x18001c1ba  mov     ecx, r12d
0x18001c1bd  cmovnz  ecx, edx
0x18001c1c0  mov     edx, ecx
0x18001c1c2  jmp     loc_18001C395
0x18001c1c7  call    cs:__imp__errno
0x18001c1cd  xor     r8d, r8d; Radix
0x18001c1d0  lea     rdx, [rbp+EndPtr]; EndPtr
0x18001c1d4  mov     rcx, rdi; String
0x18001c1d7  mov     [rax], r12d
0x18001c1da  mov     [rbp+EndPtr], r12
0x18001c1de  call    cs:__imp__wcstoi64
0x18001c1e4  mov     rbx, rax
0x18001c1e7  call    cs:__imp__errno
0x18001c1ed  cmp     dword ptr [rax], 22h ; '"'
0x18001c1f0  jz      loc_18001C390
0x18001c1f6  mov     rax, [rbp+EndPtr]
0x18001c1fa  test    rax, rax
0x18001c1fd  jz      loc_18001C390
0x18001c203  cmp     [rax], r12w
0x18001c207  jnz     loc_18001C390
0x18001c20d  mov     [rsi+10h], ebx
0x18001c210  movsxd  rax, ebx
0x18001c213  jmp     short loc_18001C1B2
0x18001c215  call    cs:__imp__errno
0x18001c21b  xor     r8d, r8d; Radix
0x18001c21e  lea     rdx, [rbp+EndPtr]; EndPtr
0x18001c222  mov     rcx, rdi; String
0x18001c225  mov     [rax], r12d
0x18001c228  mov     [rbp+EndPtr], r12
0x18001c22c  call    cs:__imp__wcstoi64
0x18001c232  mov     rbx, rax
0x18001c235  call    cs:__imp__errno
0x18001c23b  cmp     dword ptr [rax], 22h ; '"'
0x18001c23e  jz      loc_18001C390
0x18001c244  mov     rax, [rbp+EndPtr]
0x18001c248  test    rax, rax
0x18001c24b  jz      loc_18001C390
0x18001c251  cmp     [rax], r12w
0x18001c255  jnz     loc_18001C390
0x18001c25b  movzx   eax, bx
0x18001c25e  mov     [rsi+10h], ax
0x18001c262  jmp     loc_18001C1B2
0x18001c267  call    cs:__imp__errno
0x18001c26d  xor     r8d, r8d; Radix
0x18001c270  lea     rdx, [rbp+EndPtr]; EndPtr
0x18001c274  mov     rcx, rdi; String
0x18001c277  mov     [rax], r12d
0x18001c27a  mov     [rbp+EndPtr], r12
0x18001c27e  call    cs:__imp__wcstoi64
0x18001c284  mov     rbx, rax
0x18001c287  call    cs:__imp__errno
0x18001c28d  cmp     dword ptr [rax], 22h ; '"'
0x18001c290  jz      loc_18001C390
0x18001c296  mov     rax, [rbp+EndPtr]
0x18001c29a  test    rax, rax
0x18001c29d  jz      loc_18001C390
0x18001c2a3  cmp     [rax], r12w
0x18001c2a7  jnz     loc_18001C390
0x18001c2ad  mov     [rsi+10h], bx
0x18001c2b1  movsx   rax, bx
0x18001c2b5  jmp     loc_18001C1B2
0x18001c2ba  call    cs:__imp__errno
0x18001c2c0  xor     r8d, r8d; Radix
0x18001c2c3  lea     rdx, [rbp+EndPtr]; EndPtr
0x18001c2c7  mov     rcx, rdi; String
0x18001c2ca  mov     [rax], r12d
0x18001c2cd  mov     [rbp+EndPtr], r12
0x18001c2d1  call    cs:__imp__wcstoi64
0x18001c2d7  mov     rbx, rax
0x18001c2da  call    cs:__imp__errno
0x18001c2e0  cmp     dword ptr [rax], 22h ; '"'
0x18001c2e3  jz      loc_18001C390
0x18001c2e9  mov     rax, [rbp+EndPtr]
0x18001c2ed  test    rax, rax
0x18001c2f0  jz      loc_18001C390
0x18001c2f6  cmp     [rax], r12w
0x18001c2fa  jnz     loc_18001C390
0x18001c300  movzx   eax, bl
0x18001c303  mov     [rsi+10h], al
0x18001c306  jmp     loc_18001C1B2
0x18001c30b  call    cs:__imp__errno
0x18001c311  xor     r8d, r8d; Radix
0x18001c314  lea     rdx, [rbp+EndPtr]; EndPtr
0x18001c318  mov     rcx, rdi; String
0x18001c31b  mov     [rax], r12d
0x18001c31e  mov     [rbp+EndPtr], r12
0x18001c322  call    cs:__imp__wcstoi64
0x18001c328  mov     rbx, rax
0x18001c32b  call    cs:__imp__errno
0x18001c331  cmp     dword ptr [rax], 22h ; '"'
0x18001c334  jz      short loc_18001C390
0x18001c336  mov     rax, [rbp+EndPtr]
0x18001c33a  test    rax, rax
0x18001c33d  jz      short loc_18001C390
0x18001c33f  cmp     [rax], r12w
0x18001c343  jnz     short loc_18001C390
0x18001c345  mov     [rsi+10h], bl
0x18001c348  movsx   rax, bl
0x18001c34c  jmp     loc_18001C1B2
0x18001c351  lea     rdx, [rsi+10h]; int *
0x18001c355  mov     rcx, rdi; String1
0x18001c358  call    ?ParseStringBool@@YAKPEBGAEAH@Z; ParseStringBool(ushort const *,int &)
0x18001c35d  mov     edx, eax
0x18001c35f  jmp     short loc_18001C395
0x18001c361  call    cs:__imp__errno
0x18001c367  xor     r8d, r8d; Radix
0x18001c36a  lea     rdx, [rbp+EndPtr]; EndPtr
0x18001c36e  mov     rcx, rdi; String
0x18001c371  mov     [rax], r12d
0x18001c374  mov     [rbp+EndPtr], r12
0x18001c378  call    cs:__imp__wcstoi64
0x18001c37e  mov     rbx, rax
0x18001c381  call    cs:__imp__errno
0x18001c387  cmp     dword ptr [rax], 22h ; '"'
0x18001c38a  jnz     loc_18001C528
0x18001c390  mov     edx, 57h ; 'W'
0x18001c395  test    edx, edx
0x18001c397  jnz     short loc_18001C3B0
0x18001c399  mov     [rsi+8], r14d
0x18001c39d  test    r13, r13
0x18001c3a0  jz      short loc_18001C3B0
0x18001c3a2  mov     rdx, r13; unsigned __int16 *
0x18001c3a5  mov     rcx, rsi; unsigned __int16 **
0x18001c3a8  call    ?StringCopyWithAlloc@@YAJPEAPEAGPEBG@Z; StringCopyWithAlloc(ushort * *,ushort const *)
0x18001c3ad  movzx   edx, ax
0x18001c3b0  mov     eax, edx
0x18001c3b2  add     rsp, 38h
0x18001c3b6  pop     r15
0x18001c3b8  pop     r14
0x18001c3ba  pop     r13
0x18001c3bc  pop     r12
0x18001c3be  pop     rdi
0x18001c3bf  pop     rsi
0x18001c3c0  pop     rbx
0x18001c3c1  pop     rbp
0x18001c3c2  retn
0x18001c3c3  mov     ecx, r14d
0x18001c3c6  sub     ecx, 9
0x18001c3c9  jz      loc_18001C4C6
0x18001c3cf  sub     ecx, 1
0x18001c3d2  jz      loc_18001C4B2
0x18001c3d8  sub     ecx, 1
0x18001c3db  jz      loc_18001C496
0x18001c3e1  sub     ecx, 1
0x18001c3e4  jz      loc_18001C48C
0x18001c3ea  sub     ecx, 1
0x18001c3ed  jz      loc_18001C47B
0x18001c3f3  cmp     ecx, 1
0x18001c3f6  jz      short loc_18001C3FF
0x18001c3f8  mov     edx, 57h ; 'W'
0x18001c3fd  jmp     short loc_18001C3B0
0x18001c3ff  mov     [r9+10h], r12d
0x18001c403  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c407  mov     [r9+18h], r12
0x18001c40b  inc     rax
0x18001c40e  cmp     [r8+rax*2], r12w
0x18001c413  jnz     short loc_18001C40B
0x18001c415  test    rax, rax
0x18001c418  jnz     short loc_18001C422
0x18001c41a  mov     edx, r12d
0x18001c41d  jmp     loc_18001C395
0x18001c422  shr     rax, 1
0x18001c425  mov     rcx, rax
0x18001c428  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001c42d  mov     ecx, eax; cb
0x18001c42f  mov     r12d, eax
0x18001c432  call    cs:__imp_CoTaskMemAlloc
0x18001c438  mov     [rsi+18h], rax
0x18001c43c  mov     edx, 0Eh
0x18001c441  test    rax, rax
0x18001c444  jz      loc_18001C395
0x18001c44a  mov     r8d, r12d; Size
0x18001c44d  xor     edx, edx; Val
0x18001c44f  mov     rcx, rax; void *
0x18001c452  call    memset_0
0x18001c457  mov     rdx, [rsi+18h]; unsigned __int8 *
0x18001c45b  lea     r9, [rsi+10h]; unsigned int *
0x18001c45f  mov     r8d, r12d; unsigned int
0x18001c462  mov     rcx, rdi; unsigned __int16 *
0x18001c465  xor     ebx, ebx
0x18001c467  call    ?HexToBin@@YAHPEBGPEAEKPEAK@Z; HexToBin(ushort const *,uchar *,ulong,ulong *)
0x18001c46c  lea     edx, [rbx+57h]
0x18001c46f  test    eax, eax
0x18001c471  cmovz   ebx, edx
0x18001c474  mov     edx, ebx
0x18001c476  jmp     loc_18001C395
0x18001c47b  lea     rdx, [r9+10h]; lpAddress
0x18001c47f  mov     rcx, rdi; AddressString
0x18001c482  call    ??$ParseString@UtagSOCK_ADDR@@@@YAKPEBGAEAUtagSOCK_ADDR@@@Z; ParseString<tagSOCK_ADDR>(ushort const *,tagSOCK_ADDR &)
0x18001c487  jmp     loc_18001C35D
0x18001c48c  mov     edx, 32h ; '2'
0x18001c491  jmp     loc_18001C3B0
0x18001c496  lea     rdx, [r9+10h]; pclsid
0x18001c49a  mov     rcx, rdi; lpsz
0x18001c49d  call    cs:__imp_CLSIDFromString
0x18001c4a3  sar     eax, 1Fh
0x18001c4a6  mov     edx, 57h ; 'W'
0x18001c4ab  and     edx, eax
0x18001c4ad  jmp     loc_18001C395
0x18001c4b2  lea     rcx, [r9+10h]; unsigned __int16 **
0x18001c4b6  mov     rdx, rdi; unsigned __int16 *
0x18001c4b9  call    ?StringCopyWithAlloc@@YAJPEAPEAGPEBG@Z; StringCopyWithAlloc(ushort * *,ushort const *)
0x18001c4be  movzx   edx, ax
0x18001c4c1  jmp     loc_18001C395
0x18001c4c6  mov     edx, 2Dh ; '-'; Ch
0x18001c4cb  mov     rcx, rdi; Str
0x18001c4ce  call    cs:__imp_wcschr
0x18001c4d4  test    rax, rax
0x18001c4d7  jnz     loc_18001C390
0x18001c4dd  xor     r8d, r8d; Radix
0x18001c4e0  mov     [rbp+EndPtr], r12
0x18001c4e4  lea     rdx, [rbp+EndPtr]; EndPtr
0x18001c4e8  mov     rcx, rdi; String
0x18001c4eb  call    cs:__imp__wcstoui64
0x18001c4f1  mov     rbx, rax
0x18001c4f4  call    cs:__imp__errno
0x18001c4fa  cmp     dword ptr [rax], 22h ; '"'
0x18001c4fd  jnz     short loc_18001C528
0x18001c4ff  test    rbx, rbx
0x18001c502  jz      short loc_18001C528
0x18001c504  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c508  cmp     rbx, rax
0x18001c50b  jz      loc_18001C390
0x18001c511  xor     r8d, r8d; Radix
0x18001c514  xor     edx, edx; EndPtr
0x18001c516  mov     rcx, rdi; String
0x18001c519  call    cs:__imp__wcstoi64
0x18001c51f  test    rax, rax
0x18001c522  js      loc_18001C390
0x18001c528  mov     rax, [rbp+EndPtr]
0x18001c52c  test    rax, rax
0x18001c52f  jz      loc_18001C390
0x18001c535  cmp     [rax], r12w
0x18001c539  jnz     loc_18001C390
0x18001c53f  mov     [rsi+10h], rbx
0x18001c543  jmp     loc_18001C41A
```
