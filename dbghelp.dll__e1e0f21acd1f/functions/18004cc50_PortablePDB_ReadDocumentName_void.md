# PortablePDB::ReadDocumentName(void)

- ea: `0x18004cc50`
- end: `0x18004d204`
- name: `?ReadDocumentName@PortablePDB@@AEAAJXZ`
- size: `1460`
- prototype: `__int64 __fastcall(PortablePDB *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ac00`

## callees

- `0x180027440`
- `0x180029320`
- `0x180029550`
- `0x1800352f0`
- `0x1800492a0`
- `0x180049330`
- `0x1800493c0`
- `0x180049450`
- `0x180049540`
- `0x18004cc50`

## string_xrefs

- `0x18004d15f`: `Range error during SafeInt constructor`
- `0x18004d1a1`: `Range error during SafeInt constructor`
- `0x18004d117`: `Range error during makeSubRange`
- `0x18004d1c2`: `Range error during makeSubRange`
- `0x18004d13e`: `Range error during default makeSubRange`
- `0x18004d1e3`: `Range error during default makeSubRange`
- `0x18004d180`: `Range error during read`

## pseudocode

```c
__int64 __fastcall PortablePDB::ReadDocumentName(PortablePDB *this)
{
  char *v2; // rdi
  char *v3; // rcx
  unsigned int v4; // eax
  _QWORD *v5; // r8
  void *v6; // rdx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdx
  char v9; // bl
  char v10; // r14
  __int64 v11; // rbx
  __int64 v12; // rsi
  char *v13; // rdx
  char *v14; // r8
  char v15; // al
  char v16; // r12
  unsigned __int64 v17; // rdx
  char v18; // bl
  char v19; // r14
  __int64 v20; // rbx
  __int64 v21; // rsi
  _QWORD *v22; // r8
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rdx
  char v26; // bl
  char v27; // r14
  __int64 v28; // rbx
  __int64 v29; // rsi
  char *v30; // r15
  char *v31; // r14
  unsigned __int64 v32; // rbx
  pdb_internal::Buffer *v33; // rsi
  char *v34; // rcx
  char *v35; // rax
  int v36; // r14d
  const void **v37; // rbx
  char *v38; // rcx
  char *v39; // rax
  int v40; // eax
  char *v42; // rcx
  void *v43; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 v44; // [rsp+28h] [rbp-48h]
  char *pExceptionObject; // [rsp+30h] [rbp-40h] BYREF
  char *v46; // [rsp+38h] [rbp-38h]
  char v47; // [rsp+90h] [rbp+20h] BYREF
  char v48; // [rsp+98h] [rbp+28h] BYREF

  v2 = 0;
  v3 = (char *)this + 96;
  if ( *((_DWORD *)this + 158) == 2 )
    v4 = (unsigned __int16)ReadOnlySafeSpanPtr::peek<unsigned short>(v3, 0);
  else
    v4 = ReadOnlySafeSpanPtr::peek<unsigned long>(v3, 0);
  v5 = (_QWORD *)*((_QWORD *)this + 11);
  v6 = (void *)(*v5 + v4);
  if ( (unsigned __int64)v6 < *v5 )
    goto LABEL_65;
  v7 = v5[1];
  if ( (unsigned __int64)v6 > v7 )
  {
    std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during default makeSubRange");
    throw (std::range_error *)&pExceptionObject;
  }
  v43 = v6;
  v44 = v7;
  if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v43, 0) >= 0x80u )
  {
    if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v43, 0) & 0xC0) == 0x80 )
    {
      v9 = ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
      v8 = ((unsigned __int64)(v9 & 0x3F) << 8) | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
    }
    else
    {
      if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v43, 0) & 0xE0) != 0xC0 )
        return 13;
      v10 = ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
      v11 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
      v12 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
      v8 = ((v12 | ((v11 | ((unsigned __int64)(v10 & 0x1F) << 8)) << 8)) << 8)
         | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
    }
  }
  else
  {
    v8 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
  }
  v13 = (char *)v43 + v8;
  if ( v13 < v43 )
    goto LABEL_65;
  if ( (unsigned __int64)v43 > v44 || (unsigned __int64)v13 > v44 )
  {
    std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during makeSubRange");
    throw (std::range_error *)&pExceptionObject;
  }
  if ( v43 > v13 )
  {
    std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during SafeInt constructor");
    throw (std::range_error *)&pExceptionObject;
  }
  v14 = (char *)v43 + 1;
  v46 = v13;
  if ( (char *)v43 + 1 < v43 )
    goto LABEL_65;
  if ( v14 > v13 )
  {
    std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during read");
    throw (std::range_error *)&pExceptionObject;
  }
  if ( v14 < v43 )
    goto LABEL_65;
  v15 = *(_BYTE *)v43;
  v16 = 0;
  pExceptionObject = (char *)v43 + 1;
  v48 = v15;
  v47 = 0;
  if ( v14 != v13 )
  {
    while ( 1 )
    {
      if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&pExceptionObject, 0) >= 0x80u )
      {
        if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&pExceptionObject, 0) & 0xC0) == 0x80 )
        {
          v18 = ReadOnlySafeSpanPtr::read<unsigned char>(&pExceptionObject, 0);
          v17 = ((unsigned __int64)(v18 & 0x3F) << 8)
              | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&pExceptionObject, 0);
        }
        else
        {
          if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&pExceptionObject, 0) & 0xE0) != 0xC0 )
            return 13;
          v19 = ReadOnlySafeSpanPtr::read<unsigned char>(&pExceptionObject, 0);
          v20 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&pExceptionObject, 0);
          v21 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&pExceptionObject, 0);
          v17 = ((v21 | ((v20 | ((unsigned __int64)(v19 & 0x1F) << 8)) << 8)) << 8)
              | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&pExceptionObject, 0);
        }
      }
      else
      {
        v17 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&pExceptionObject, 0);
      }
      v22 = (_QWORD *)*((_QWORD *)this + 11);
      v23 = v17 + *v22;
      if ( v23 < *v22 )
        break;
      v24 = v22[1];
      if ( v23 > v24 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during default makeSubRange");
        throw (std::range_error *)&pExceptionObject;
      }
      v43 = (void *)(v17 + *v22);
      v44 = v24;
      if ( (unsigned __int8)ReadOnlySafeSpanPtr::peek<unsigned char>(&v43, 0) >= 0x80u )
      {
        if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v43, 0) & 0xC0) == 0x80 )
        {
          v26 = ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
          v25 = ((unsigned __int64)(v26 & 0x3F) << 8)
              | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
        }
        else
        {
          if ( (ReadOnlySafeSpanPtr::peek<unsigned char>(&v43, 0) & 0xE0) != 0xC0 )
            return 13;
          v27 = ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
          v28 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
          v29 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
          v25 = ((v29 | ((v28 | ((unsigned __int64)(v27 & 0x1F) << 8)) << 8)) << 8)
              | (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
        }
      }
      else
      {
        v25 = (unsigned __int8)ReadOnlySafeSpanPtr::read<unsigned char>(&v43, 0);
      }
      v30 = (char *)v43;
      v31 = (char *)v43 + v25;
      if ( (char *)v43 + v25 < v43 )
        break;
      v32 = v44;
      if ( (unsigned __int64)v31 > v44 )
        return 13;
      v33 = (PortablePDB *)((char *)this + 696);
      if ( v16 )
      {
        if ( *((_DWORD *)this + 176) + *((_DWORD *)this + 180) - *((_DWORD *)this + 178) < 1
          && !(unsigned int)pdb_internal::Buffer::grow((PortablePDB *)((char *)this + 696), 1) )
        {
          return 2;
        }
        v34 = (char *)*((_QWORD *)this + 89);
        if ( *((_QWORD *)this + 88) )
        {
          v35 = v34 + 1;
        }
        else
        {
          *((_QWORD *)this + 88) = 0;
          v35 = 0;
        }
        *((_QWORD *)this + 89) = v35;
        memcpy_avx(v34, &v48, 1u);
        v16 = v47;
      }
      else
      {
        v16 = 1;
        v47 = 1;
      }
      if ( (unsigned __int64)v30 > v32 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during makeSubRange");
        throw (std::range_error *)&pExceptionObject;
      }
      if ( v30 > v31 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during SafeInt constructor");
        throw (std::range_error *)&pExceptionObject;
      }
      if ( !v30 )
        return 2;
      v36 = (_DWORD)v31 - (_DWORD)v30;
      if ( v36 < 0 )
        return 2;
      v37 = (const void **)((char *)this + 712);
      if ( v36 > *((_DWORD *)this + 176) + *((_DWORD *)this + 180) - *((_DWORD *)this + 178)
        && !(unsigned int)pdb_internal::Buffer::grow((PortablePDB *)((char *)this + 696), v36) )
      {
        return 2;
      }
      v38 = (char *)*v37;
      if ( *((_QWORD *)this + 88) )
      {
        v39 = &v38[v36];
      }
      else
      {
        *((_QWORD *)this + 88) = 0;
        v39 = 0;
      }
      *v37 = v39;
      memcpy_avx(v38, v30, v36);
      if ( pExceptionObject == v46 )
        goto LABEL_56;
    }
LABEL_65:
    msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow();
  }
  v33 = (PortablePDB *)((char *)this + 696);
LABEL_56:
  v40 = *((_DWORD *)v33 + 2) + *((_DWORD *)v33 + 6) - *((_DWORD *)v33 + 4);
  v47 = 0;
  if ( v40 < 1 && !(unsigned int)pdb_internal::Buffer::grow(v33, 1) )
    return 2;
  v42 = (char *)*((_QWORD *)v33 + 2);
  if ( *((_QWORD *)v33 + 1) )
    v2 = v42 + 1;
  else
    *((_QWORD *)v33 + 1) = 0;
  *((_QWORD *)v33 + 2) = v2;
  memcpy_avx(v42, &v47, 1u);
  return 0;
}

```

## disassembly

```asm
0x18004cc50  push    rbp
0x18004cc52  push    rdi
0x18004cc53  push    r13
0x18004cc55  mov     rbp, rsp
0x18004cc58  sub     rsp, 70h
0x18004cc5c  mov     r13, rcx
0x18004cc5f  xor     edi, edi
0x18004cc61  add     rcx, 60h ; '`'
0x18004cc65  mov     edx, edi
0x18004cc67  cmp     dword ptr [r13+278h], 2
0x18004cc6f  jnz     short loc_18004CC7B
0x18004cc71  call    ??$peek@G@ReadOnlySafeSpanPtr@@QEBAGV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<ushort>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cc76  movzx   eax, ax
0x18004cc79  jmp     short loc_18004CC80
0x18004cc7b  call    ??$peek@K@ReadOnlySafeSpanPtr@@QEBAKV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<ulong>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cc80  mov     r8, [r13+58h]
0x18004cc84  mov     [rsp+70h+arg_10], rbx
0x18004cc8c  mov     [rsp+70h+var_8], rsi
0x18004cc91  mov     [rsp+70h+var_10], r12
0x18004cc96  mov     edx, eax
0x18004cc98  add     rdx, [r8]
0x18004cc9b  mov     [rsp+70h+var_18], r14
0x18004cca0  mov     [rsp+70h+var_20], r15
0x18004cca5  cmp     rdx, [r8]
0x18004cca8  jb      loc_18004D138
0x18004ccae  mov     rax, [r8+8]
0x18004ccb2  cmp     rdx, rax
0x18004ccb5  ja      loc_18004D13E
0x18004ccbb  mov     [rbp+var_50], rdx
0x18004ccbf  lea     rcx, [rbp+var_50]
0x18004ccc3  mov     rdx, rdi
0x18004ccc6  mov     [rbp+var_48], rax
0x18004ccca  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cccf  lea     rcx, [rbp+var_50]
0x18004ccd3  mov     rdx, rdi
0x18004ccd6  cmp     al, 80h
0x18004ccd8  jnb     short loc_18004CCE7
0x18004ccda  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ccdf  movzx   edx, al
0x18004cce2  jmp     loc_18004CD81
0x18004cce7  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ccec  and     al, 0C0h
0x18004ccee  lea     rcx, [rbp+var_50]
0x18004ccf2  mov     rdx, rdi
0x18004ccf5  cmp     al, 80h
0x18004ccf7  jnz     short loc_18004CD1C
0x18004ccf9  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ccfe  mov     rdx, rdi
0x18004cd01  lea     rcx, [rbp+var_50]
0x18004cd05  movzx   ebx, al
0x18004cd08  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cd0d  and     ebx, 3Fh
0x18004cd10  movzx   edx, al
0x18004cd13  shl     rbx, 8
0x18004cd17  or      rdx, rbx
0x18004cd1a  jmp     short loc_18004CD81
0x18004cd1c  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cd21  and     al, 0E0h
0x18004cd23  cmp     al, 0C0h
0x18004cd25  jnz     loc_18004D110
0x18004cd2b  mov     rdx, rdi
0x18004cd2e  lea     rcx, [rbp+var_50]
0x18004cd32  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cd37  mov     rdx, rdi
0x18004cd3a  lea     rcx, [rbp+var_50]
0x18004cd3e  movzx   r14d, al
0x18004cd42  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cd47  mov     rdx, rdi
0x18004cd4a  movzx   ebx, al
0x18004cd4d  lea     rcx, [rbp+var_50]
0x18004cd51  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cd56  mov     rdx, rdi
0x18004cd59  movzx   esi, al
0x18004cd5c  lea     rcx, [rbp+var_50]
0x18004cd60  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cd65  and     r14d, 1Fh
0x18004cd69  movzx   edx, al
0x18004cd6c  shl     r14, 8
0x18004cd70  or      r14, rbx
0x18004cd73  shl     r14, 8
0x18004cd77  or      r14, rsi
0x18004cd7a  shl     r14, 8
0x18004cd7e  or      rdx, r14
0x18004cd81  mov     rcx, [rbp+var_50]
0x18004cd85  add     rdx, rcx
0x18004cd88  cmp     rdx, rcx
0x18004cd8b  jb      loc_18004D138
0x18004cd91  mov     rax, [rbp+var_48]
0x18004cd95  cmp     rcx, rax
0x18004cd98  ja      loc_18004D117
0x18004cd9e  cmp     rdx, rax
0x18004cda1  ja      loc_18004D117
0x18004cda7  cmp     rcx, rdx
0x18004cdaa  ja      loc_18004D15F
0x18004cdb0  lea     r8, [rcx+1]
0x18004cdb4  mov     [rbp+var_38], rdx
0x18004cdb8  cmp     r8, rcx
0x18004cdbb  jb      loc_18004D138
0x18004cdc1  cmp     r8, rdx
0x18004cdc4  ja      loc_18004D180
0x18004cdca  cmp     r8, rcx
0x18004cdcd  jb      loc_18004D138
0x18004cdd3  movzx   eax, byte ptr [rcx]
0x18004cdd6  xor     r12b, r12b
0x18004cdd9  mov     [rbp+pExceptionObject], r8
0x18004cddd  mov     [rbp+arg_8], al
0x18004cde0  mov     [rbp+arg_0], r12b
0x18004cde4  cmp     r8, rdx
0x18004cde7  jz      loc_18004D090
0x18004cded  nop     dword ptr [rax]
0x18004cdf0  mov     rdx, rdi
0x18004cdf3  lea     rcx, [rbp+pExceptionObject]
0x18004cdf7  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cdfc  lea     rcx, [rbp+pExceptionObject]
0x18004ce00  mov     rdx, rdi
0x18004ce03  cmp     al, 80h
0x18004ce05  jnb     short loc_18004CE14
0x18004ce07  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ce0c  movzx   edx, al
0x18004ce0f  jmp     loc_18004CEAE
0x18004ce14  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ce19  and     al, 0C0h
0x18004ce1b  lea     rcx, [rbp+pExceptionObject]
0x18004ce1f  mov     rdx, rdi
0x18004ce22  cmp     al, 80h
0x18004ce24  jnz     short loc_18004CE49
0x18004ce26  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ce2b  mov     rdx, rdi
0x18004ce2e  lea     rcx, [rbp+pExceptionObject]
0x18004ce32  movzx   ebx, al
0x18004ce35  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ce3a  and     ebx, 3Fh
0x18004ce3d  movzx   edx, al
0x18004ce40  shl     rbx, 8
0x18004ce44  or      rdx, rbx
0x18004ce47  jmp     short loc_18004CEAE
0x18004ce49  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ce4e  and     al, 0E0h
0x18004ce50  cmp     al, 0C0h
0x18004ce52  jnz     loc_18004D110
0x18004ce58  mov     rdx, rdi
0x18004ce5b  lea     rcx, [rbp+pExceptionObject]
0x18004ce5f  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ce64  mov     rdx, rdi
0x18004ce67  lea     rcx, [rbp+pExceptionObject]
0x18004ce6b  movzx   r14d, al
0x18004ce6f  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ce74  mov     rdx, rdi
0x18004ce77  movzx   ebx, al
0x18004ce7a  lea     rcx, [rbp+pExceptionObject]
0x18004ce7e  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ce83  mov     rdx, rdi
0x18004ce86  movzx   esi, al
0x18004ce89  lea     rcx, [rbp+pExceptionObject]
0x18004ce8d  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004ce92  and     r14d, 1Fh
0x18004ce96  movzx   edx, al
0x18004ce99  shl     r14, 8
0x18004ce9d  or      r14, rbx
0x18004cea0  shl     r14, 8
0x18004cea4  or      r14, rsi
0x18004cea7  shl     r14, 8
0x18004ceab  or      rdx, r14
0x18004ceae  mov     r8, [r13+58h]
0x18004ceb2  mov     rax, [r8]
0x18004ceb5  lea     rcx, [rdx+rax]
0x18004ceb9  cmp     rcx, rax
0x18004cebc  jb      loc_18004D138
0x18004cec2  mov     rax, [r8+8]
0x18004cec6  cmp     rcx, rax
0x18004cec9  ja      loc_18004D1E3
0x18004cecf  mov     [rbp+var_50], rcx
0x18004ced3  mov     rdx, rdi
0x18004ced6  lea     rcx, [rbp+var_50]
0x18004ceda  mov     [rbp+var_48], rax
0x18004cede  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cee3  lea     rcx, [rbp+var_50]
0x18004cee7  mov     rdx, rdi
0x18004ceea  cmp     al, 80h
0x18004ceec  jnb     short loc_18004CEFB
0x18004ceee  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cef3  movzx   edx, al
0x18004cef6  jmp     loc_18004CF95
0x18004cefb  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cf00  and     al, 0C0h
0x18004cf02  lea     rcx, [rbp+var_50]
0x18004cf06  mov     rdx, rdi
0x18004cf09  cmp     al, 80h
0x18004cf0b  jnz     short loc_18004CF30
0x18004cf0d  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cf12  mov     rdx, rdi
0x18004cf15  lea     rcx, [rbp+var_50]
0x18004cf19  movzx   ebx, al
0x18004cf1c  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cf21  and     ebx, 3Fh
0x18004cf24  movzx   edx, al
0x18004cf27  shl     rbx, 8
0x18004cf2b  or      rdx, rbx
0x18004cf2e  jmp     short loc_18004CF95
0x18004cf30  call    ??$peek@E@ReadOnlySafeSpanPtr@@QEBAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cf35  and     al, 0E0h
0x18004cf37  cmp     al, 0C0h
0x18004cf39  jnz     loc_18004D110
0x18004cf3f  mov     rdx, rdi
0x18004cf42  lea     rcx, [rbp+var_50]
0x18004cf46  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cf4b  mov     rdx, rdi
0x18004cf4e  lea     rcx, [rbp+var_50]
0x18004cf52  movzx   r14d, al
0x18004cf56  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cf5b  mov     rdx, rdi
0x18004cf5e  movzx   ebx, al
0x18004cf61  lea     rcx, [rbp+var_50]
0x18004cf65  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cf6a  mov     rdx, rdi
0x18004cf6d  movzx   esi, al
0x18004cf70  lea     rcx, [rbp+var_50]
0x18004cf74  call    ??$read@E@ReadOnlySafeSpanPtr@@QEAAEV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::read<uchar>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004cf79  and     r14d, 1Fh
0x18004cf7d  movzx   edx, al
0x18004cf80  shl     r14, 8
0x18004cf84  or      r14, rbx
0x18004cf87  shl     r14, 8
0x18004cf8b  or      r14, rsi
0x18004cf8e  shl     r14, 8
0x18004cf92  or      rdx, r14
0x18004cf95  mov     r15, [rbp+var_50]
0x18004cf99  lea     r14, [r15+rdx]
0x18004cf9d  cmp     r14, r15
0x18004cfa0  jb      loc_18004D138
0x18004cfa6  mov     rbx, [rbp+var_48]
0x18004cfaa  cmp     r14, rbx
0x18004cfad  ja      loc_18004D110
0x18004cfb3  lea     rsi, [r13+2B8h]
0x18004cfba  test    r12b, r12b
0x18004cfbd  jz      short loc_18004D014
0x18004cfbf  mov     eax, [rsi+18h]
0x18004cfc2  sub     eax, [rsi+10h]
0x18004cfc5  add     eax, [rsi+8]
0x18004cfc8  cmp     eax, 1
0x18004cfcb  jge     short loc_18004CFE2
0x18004cfcd  mov     edx, 1; int
0x18004cfd2  mov     rcx, rsi; this
0x18004cfd5  call    ?grow@Buffer@pdb_internal@@AEAAHJ@Z; pdb_internal::Buffer::grow(long)
0x18004cfda  test    eax, eax
0x18004cfdc  jz      loc_18004D0BA
0x18004cfe2  cmp     qword ptr [rsi+8], 0
0x18004cfe7  mov     rcx, [rsi+10h]; void *
0x18004cfeb  jnz     short loc_18004CFF6
0x18004cfed  mov     [rsi+8], rdi
0x18004cff1  mov     rax, rdi
0x18004cff4  jmp     short loc_18004CFFA
0x18004cff6  lea     rax, [rcx+1]
0x18004cffa  mov     r8d, 1; unsigned __int64
0x18004d000  mov     [rsi+10h], rax
0x18004d004  lea     rdx, [rbp+arg_8]; void *
0x18004d008  call    ?memcpy_avx@@YAPEBXPEBX0_K@Z; memcpy_avx(void const *,void const *,unsigned __int64)
0x18004d00d  movzx   r12d, [rbp+arg_0]
0x18004d012  jmp     short loc_18004D01B
0x18004d014  mov     r12b, 1
0x18004d017  mov     [rbp+arg_0], r12b
0x18004d01b  cmp     r15, rbx
0x18004d01e  ja      loc_18004D1C2
0x18004d024  cmp     r15, r14
0x18004d027  ja      loc_18004D1A1
0x18004d02d  test    r15, r15
0x18004d030  jz      loc_18004D0BA
0x18004d036  sub     r14d, r15d
0x18004d039  js      short loc_18004D0BA
0x18004d03b  mov     eax, [rsi+18h]
0x18004d03e  lea     rbx, [rsi+10h]
0x18004d042  sub     eax, [rbx]
0x18004d044  add     eax, [rsi+8]
0x18004d047  cmp     r14d, eax
0x18004d04a  jle     short loc_18004D05B
0x18004d04c  mov     edx, r14d; int
0x18004d04f  mov     rcx, rsi; this
0x18004d052  call    ?grow@Buffer@pdb_internal@@AEAAHJ@Z; pdb_internal::Buffer::grow(long)
0x18004d057  test    eax, eax
0x18004d059  jz      short loc_18004D0BA
0x18004d05b  cmp     qword ptr [rsi+8], 0
0x18004d060  mov     rcx, [rbx]; void *
0x18004d063  movsxd  r8, r14d; unsigned __int64
0x18004d066  jnz     short loc_18004D071
0x18004d068  mov     [rsi+8], rdi
0x18004d06c  mov     rax, rdi
0x18004d06f  jmp     short loc_18004D075
0x18004d071  lea     rax, [rcx+r8]
0x18004d075  mov     rdx, r15; void *
0x18004d078  mov     [rbx], rax
0x18004d07b  call    ?memcpy_avx@@YAPEBXPEBX0_K@Z; memcpy_avx(void const *,void const *,unsigned __int64)
0x18004d080  mov     rax, [rbp+var_38]
0x18004d084  cmp     [rbp+pExceptionObject], rax
0x18004d088  jnz     loc_18004CDF0
0x18004d08e  jmp     short loc_18004D097
0x18004d090  lea     rsi, [r13+2B8h]
0x18004d097  mov     eax, [rsi+18h]
0x18004d09a  sub     eax, [rsi+10h]
0x18004d09d  add     eax, [rsi+8]
0x18004d0a0  mov     [rbp+arg_0], 0
  ... truncated ...
```
