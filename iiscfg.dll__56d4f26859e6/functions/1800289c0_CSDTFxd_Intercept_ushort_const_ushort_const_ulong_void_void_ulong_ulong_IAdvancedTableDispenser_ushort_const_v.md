# CSDTFxd::Intercept(ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,IAdvancedTableDispenser *,ushort const *,void *,void * *)

- ea: `0x1800289c0`
- end: `0x180028f38`
- name: `?Intercept@CSDTFxd@@UEAAJPEBG0KPEAX1KKPEAUIAdvancedTableDispenser@@01PEAPEAX@Z`
- size: `1400`
- prototype: `__int64 __usercall@<rax>(CSDTFxd *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *, void *, unsigned int, unsigned int, struct IAdvancedTableDispenser *, const unsigned __int16 *, void *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180025cc4`
- `0x18002637c`
- `0x180026500`
- `0x1800265e0`
- `0x1800267b8`
- `0x180026d6c`
- `0x180027334`
- `0x180028010`
- `0x1800283a8`
- `0x1800289c0`
- `0x18002904c`
- `0x180030010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180028b2a`
- `KERNEL32!CompareStringW` at `0x180028b6c`
- `KERNEL32!CompareStringW` at `0x180028ba8`
- `KERNEL32!CompareStringW` at `0x180028be9`
- `KERNEL32!CompareStringW` at `0x180028c2a`
- `KERNEL32!CompareStringW` at `0x180028c68`
- `KERNEL32!CompareStringW` at `0x180028ca6`
- `KERNEL32!CompareStringW` at `0x180028b2a`
- `KERNEL32!CompareStringW` at `0x180028b6c`
- `KERNEL32!CompareStringW` at `0x180028ba8`
- `KERNEL32!CompareStringW` at `0x180028be9`
- `KERNEL32!CompareStringW` at `0x180028c2a`
- `KERNEL32!CompareStringW` at `0x180028c68`
- `KERNEL32!CompareStringW` at `0x180028ca6`

## pseudocode

```c
__int64 __fastcall CSDTFxd::Intercept(
        __int64 this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *a5,
        unsigned int *a6,
        unsigned int a7,
        __int16 a8,
        struct IAdvancedTableDispenser *a9,
        const unsigned __int16 *a10,
        void *a11,
        void **a12)
{
  __int64 v14; // rbx
  unsigned int v15; // esi
  __int64 result; // rax
  __int64 v17; // rdi
  int v18; // eax
  unsigned int v19; // ebp
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  bool v22; // zf
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  int ColumnMetaTable; // eax
  __int64 i; // rdx
  unsigned int v29; // esi
  __int64 j; // rdi
  unsigned int *v31; // rcx
  __int64 v32; // rdx
  const unsigned __int16 *v33; // r8
  unsigned int *v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rax
  unsigned int v37; // edi
  __int64 v38; // rdx
  const unsigned __int16 *v39; // r8
  _DWORD *v40; // r8
  unsigned int *v41; // r9
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rax
  __int64 v45; // rax
  _DWORD *v46; // rcx
  __int64 v47; // r9
  __int64 v48; // rcx
  unsigned int *v49; // rcx
  unsigned int v50; // r8d
  __int64 v51; // r11
  unsigned int k; // edx
  __int64 v53; // r10
  _BYTE *v54; // rcx

  v14 = this;
  if ( a11 )
    return 2147942487LL;
  v15 = 0;
  if ( a6 )
    v15 = *a6;
  if ( *(_DWORD *)(this + 52) )
    return 2147549183LL;
  if ( !a2 || !a3 || !a12 )
    return 2147942487LL;
  if ( a7 != 3 )
    return 2149648396LL;
  if ( a10 )
    return 2147942487LL;
  if ( (a8 & 0x132) != 0 )
    return 2149648397LL;
  *a12 = 0;
  if ( v15 )
  {
    v17 = 0;
    do
    {
      this = 3 * v17;
      v18 = *((_DWORD *)a5 + 6 * v17 + 3);
      if ( (v18 & 0xF0000000) == 0 )
        break;
      if ( ((v18 + 0xFFFFFFF) & 0xFFFFFFF7) == 0 )
        TBinFileMappingCache::GetFileMappingPointer(
          *((const unsigned __int16 **)a5 + 3 * v17),
          (const struct FixedTableHeap **)(v14 + 152));
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (unsigned int)v17 < v15 );
  }
  v19 = -2145318902;
  if ( (unsigned int)CSDTFxd::StringInsensitiveCompare((CSDTFxd *)this, a2, L"META") )
  {
    for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
    {
      if ( (*((_DWORD *)a5 + 6 * i + 3) & 0xF0000000) == 0 )
        return 2149648395LL;
    }
    v29 = 0;
    *(_QWORD *)(v14 + 112) = 0;
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      v31 = *(unsigned int **)(v14 + 152);
      if ( (unsigned int)j >= v31[9] )
        break;
      v32 = *(unsigned int *)((char *)&v31[12 * j] + v31[8]);
      if ( (_DWORD)v32 )
        v33 = (const unsigned __int16 *)((char *)v31 + v31[14] + v32);
      else
        v33 = 0;
      if ( !(unsigned int)CSDTFxd::StringInsensitiveCompare((CSDTFxd *)v31, a2, v33) )
      {
        _mm_lfence();
        v34 = *(unsigned int **)(v14 + 152);
        *(_QWORD *)(v14 + 112) = (char *)&v34[27 * *(unsigned int *)((char *)&v34[12 * j + 10] + v34[8])] + v34[22];
        v35 = *(unsigned int *)((char *)&v34[12 * j + 4] + v34[8]);
        if ( (_DWORD)v35 )
          v31 = (unsigned int *)((char *)v34 + v34[14] + v35);
        else
          v31 = 0;
        v29 = *v31;
        break;
      }
    }
    v36 = *(_QWORD *)(v14 + 112);
    if ( v36 )
    {
      v37 = 0;
      if ( v29 )
      {
        while ( 1 )
        {
          v38 = *(unsigned int *)(v36 + 4);
          if ( (_DWORD)v38 )
          {
            v31 = *(unsigned int **)(v14 + 152);
            v39 = (const unsigned __int16 *)((char *)v31 + v31[14] + v38);
          }
          else
          {
            v39 = 0;
          }
          if ( !(unsigned int)CSDTFxd::StringInsensitiveCompare((CSDTFxd *)v31, a3, v39) )
            break;
          *(_QWORD *)(v14 + 112) += 108LL;
          ++v37;
          v36 = *(_QWORD *)(v14 + 112);
          if ( v37 >= v29 )
            goto LABEL_73;
        }
      }
      else
      {
LABEL_73:
        if ( v37 == v29 )
          return v19;
      }
      v40 = *(_DWORD **)(v14 + 112);
      if ( (int)v40[19] <= 0 )
        return v19;
      v41 = *(unsigned int **)(v14 + 152);
      v42 = (__int64)&v41[v40[19]] + v41[26];
      *(_QWORD *)(v14 + 80) = v42;
      *(_QWORD *)(v14 + 72) = v42;
      *(_QWORD *)(v14 + 64) = (char *)&v41[21 * v40[18]] + v41[6];
      v43 = v40[23];
      if ( v43 )
        v44 = (__int64)&v41[2 * (v43 + 1)] + v41[10];
      else
        v44 = 0;
      *(_QWORD *)(v14 + 88) = v44;
      if ( v40[23] )
        v45 = (__int64)&v41[2 * v40[23]] + v41[10];
      else
        v45 = 0;
      *(_QWORD *)(v14 + 96) = v45;
      *(_DWORD *)(v14 + 40) = v40[17];
      if ( v40[8] )
        v46 = (unsigned int *)((char *)v41 + v41[14] + v40[8]);
      else
        v46 = 0;
      *(_DWORD *)(v14 + 32) = *v46;
      goto LABEL_85;
    }
    return 2147942487LL;
  }
  v20 = *a3;
  if ( v20 > 0x63 )
  {
    v23 = v20 - 100;
    v22 = v23 == 0;
  }
  else
  {
    if ( v20 == 99 || (v21 = v20 - 67) == 0 )
    {
      if ( CompareStringW(0x7Fu, 1u, a3, -1, L"COLUMNMETA", -1) != 2 )
        return v19;
      ColumnMetaTable = CSDTFxd::GetColumnMetaTable((CSDTFxd *)v14, a5, v15);
      goto LABEL_46;
    }
    v23 = v21 - 1;
    v22 = v23 == 0;
  }
  if ( v22 )
  {
    if ( CompareStringW(0x7Fu, 1u, a3, -1, L"DATABASEMETA", -1) != 2 )
      return v19;
    ColumnMetaTable = CSDTFxd::GetDatabaseMetaTable((CSDTFxd *)v14, a5, v15);
  }
  else
  {
    v24 = v23 - 5;
    if ( v24 )
    {
      v25 = v24 - 8;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          if ( v26 != 2 )
            return v19;
          if ( CompareStringW(0x7Fu, 1u, a3, -1, L"TABLEMETA", -1) == 2 )
          {
            ColumnMetaTable = CSDTFxd::GetTableMetaTable((CSDTFxd *)v14, a5, v15);
          }
          else
          {
            if ( CompareStringW(0x7Fu, 1u, a3, -1, L"TAGMETA", -1) != 2 )
              return v19;
            ColumnMetaTable = CSDTFxd::GetTagMetaTable((CSDTFxd *)v14, a5, v15);
          }
        }
        else
        {
          if ( CompareStringW(0x7Fu, 1u, a3, -1, L"RELATIONMETA", -1) != 2 )
            return v19;
          ColumnMetaTable = CSDTFxd::GetRelationMetaTable((CSDTFxd *)v14, a5, v15);
        }
      }
      else
      {
        if ( CompareStringW(0x7Fu, 1u, a3, -1, L"QUERYMETA", -1) != 2 )
          return v19;
        ColumnMetaTable = CSDTFxd::GetQueryMetaTable((CSDTFxd *)v14, a5, v15);
      }
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, a3, -1, L"INDEXMETA", -1) != 2 )
        return v19;
      ColumnMetaTable = CSDTFxd::GetIndexMetaTable((CSDTFxd *)v14, a5, v15);
    }
  }
LABEL_46:
  v19 = ColumnMetaTable;
  if ( ColumnMetaTable < 0 && ColumnMetaTable != -2145318890 )
    return v19;
  result = CSDTFxd::GetIndexMeta((CSDTFxd *)v14, a5, v15);
  if ( (int)result >= 0 )
  {
LABEL_85:
    v47 = *(_QWORD *)(v14 + 152);
    v48 = *(unsigned int *)(*(_QWORD *)(v14 + 112) + 32LL);
    if ( (_DWORD)v48 )
      v49 = (unsigned int *)(v47 + *(unsigned int *)(v47 + 56) + v48);
    else
      v49 = 0;
    v50 = *v49;
    *(_DWORD *)(v14 + 28) = *v49;
    if ( v50 )
    {
      v51 = *(_QWORD *)(v14 + 64);
      for ( k = 0; k < v50; ++k )
      {
        v53 = *(unsigned int *)(84LL * k + v51 + 24);
        if ( (_DWORD)v53 )
          v54 = (_BYTE *)(v53 + v47 + *(unsigned int *)(v47 + 56));
        else
          v54 = 0;
        if ( (*v54 & 1) != 0 )
          ++*(_DWORD *)(v14 + 44);
      }
    }
    *a12 = (void *)((v14 + 8) & -(__int64)(v14 != 0));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 52));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800289c0  push    rbx
0x1800289c2  push    rbp
0x1800289c3  push    rsi
0x1800289c4  push    rdi
0x1800289c5  push    r12
0x1800289c7  push    r13
0x1800289c9  push    r14
0x1800289cb  push    r15
0x1800289cd  sub     rsp, 38h
0x1800289d1  cmp     [rsp+78h+arg_50], 0
0x1800289da  mov     r15, r8
0x1800289dd  mov     r12, rdx
0x1800289e0  mov     rbx, rcx
0x1800289e3  jnz     loc_180028F22
0x1800289e9  mov     rax, [rsp+78h+arg_28]
0x1800289f1  xor     esi, esi
0x1800289f3  test    rax, rax
0x1800289f6  jz      short loc_1800289FA
0x1800289f8  mov     esi, [rax]
0x1800289fa  cmp     dword ptr [rcx+34h], 0
0x1800289fe  jz      short loc_180028A0A
0x180028a00  mov     eax, 8000FFFFh
0x180028a05  jmp     loc_180028F27
0x180028a0a  test    r12, r12
0x180028a0d  jz      loc_180028F22
0x180028a13  test    r15, r15
0x180028a16  jz      loc_180028F22
0x180028a1c  mov     r13, [rsp+78h+arg_58]
0x180028a24  test    r13, r13
0x180028a27  jz      loc_180028F22
0x180028a2d  cmp     [rsp+78h+arg_30], 3
0x180028a35  jz      short loc_180028A41
0x180028a37  mov     eax, 8021080Ch
0x180028a3c  jmp     loc_180028F27
0x180028a41  cmp     [rsp+78h+arg_48], 0
0x180028a4a  jnz     loc_180028F22
0x180028a50  test    dword ptr [rsp+78h+arg_38], 132h
0x180028a5b  jz      short loc_180028A67
0x180028a5d  mov     eax, 8021080Dh
0x180028a62  jmp     loc_180028F27
0x180028a67  mov     r14, [rsp+78h+arg_20]
0x180028a6f  mov     qword ptr [r13+0], 0
0x180028a77  test    esi, esi
0x180028a79  jz      short loc_180028AAF
0x180028a7b  xor     edi, edi
0x180028a7d  lea     rcx, [rdi+rdi*2]
0x180028a81  mov     eax, [r14+rcx*8+0Ch]
0x180028a86  test    eax, 0F0000000h
0x180028a8b  jz      short loc_180028AAF
0x180028a8d  add     eax, 0FFFFFFFh
0x180028a92  test    eax, 0FFFFFFF7h
0x180028a97  jnz     short loc_180028AA9
0x180028a99  mov     rcx, [r14+rcx*8]; unsigned __int16 *
0x180028a9d  lea     rdx, [rbx+98h]; struct FixedTableHeap **
0x180028aa4  call    ?GetFileMappingPointer@TBinFileMappingCache@@SAXPEBGAEAPEBVFixedTableHeap@@@Z; TBinFileMappingCache::GetFileMappingPointer(ushort const *,FixedTableHeap const * &)
0x180028aa9  inc     edi
0x180028aab  cmp     edi, esi
0x180028aad  jb      short loc_180028A7D
0x180028aaf  lea     r8, aMeta; "META"
0x180028ab6  mov     rdx, r12; unsigned __int16 *
0x180028ab9  call    ?StringInsensitiveCompare@CSDTFxd@@AEBAHPEBG0@Z; CSDTFxd::StringInsensitiveCompare(ushort const *,ushort const *)
0x180028abe  mov     ebp, 8021080Ah
0x180028ac3  test    eax, eax
0x180028ac5  jnz     loc_180028CEF
0x180028acb  movzx   ecx, word ptr [r15]
0x180028acf  cmp     ecx, 63h ; 'c'
0x180028ad2  ja      short loc_180028B48
0x180028ad4  jz      short loc_180028B0B
0x180028ad6  sub     ecx, 43h ; 'C'
0x180028ad9  jz      short loc_180028B0B
0x180028adb  sub     ecx, 1
0x180028ade  jz      loc_180028C87
0x180028ae4  sub     ecx, 5
0x180028ae7  jz      loc_180028C49
0x180028aed  sub     ecx, 8
0x180028af0  jz      loc_180028C0B
0x180028af6  sub     ecx, 1
0x180028af9  jz      loc_180028BCA
0x180028aff  cmp     ecx, 2
0x180028b02  jz      short loc_180028B4D
0x180028b04  mov     eax, ebp
0x180028b06  jmp     loc_180028F27
0x180028b0b  or      edi, 0FFFFFFFFh
0x180028b0e  lea     rax, aColumnmeta; "COLUMNMETA"
0x180028b15  mov     [rsp+78h+cchCount2], edi; cchCount2
0x180028b19  mov     r9d, edi; cchCount1
0x180028b1c  mov     r8, r15; lpString1
0x180028b1f  mov     [rsp+78h+lpString2], rax; lpString2
0x180028b24  lea     edx, [rdi+2]; dwCmpFlags
0x180028b27  lea     ecx, [rdx+7Eh]; Locale
0x180028b2a  call    cs:__imp_CompareStringW
0x180028b30  cmp     eax, 2
0x180028b33  jnz     short loc_180028B04
0x180028b35  mov     r8d, esi; unsigned int
0x180028b38  mov     rdx, r14; struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *
0x180028b3b  mov     rcx, rbx; this
0x180028b3e  call    ?GetColumnMetaTable@CSDTFxd@@AEAAJPEAU__MIDL___MIDL_itf_catalog_0000_0000_0001@@K@Z; CSDTFxd::GetColumnMetaTable(__MIDL___MIDL_itf_catalog_0000_0000_0001 *,ulong)
0x180028b43  jmp     loc_180028CC3
0x180028b48  sub     ecx, 64h ; 'd'
0x180028b4b  jmp     short loc_180028ADE
0x180028b4d  or      edi, 0FFFFFFFFh
0x180028b50  lea     rax, aTablemeta; "TABLEMETA"
0x180028b57  mov     [rsp+78h+cchCount2], edi; cchCount2
0x180028b5b  mov     r9d, edi; cchCount1
0x180028b5e  mov     r8, r15; lpString1
0x180028b61  mov     [rsp+78h+lpString2], rax; lpString2
0x180028b66  lea     edx, [rdi+2]; dwCmpFlags
0x180028b69  lea     ecx, [rdx+7Eh]; Locale
0x180028b6c  call    cs:__imp_CompareStringW
0x180028b72  cmp     eax, 2
0x180028b75  jnz     short loc_180028B8A
0x180028b77  mov     r8d, esi; unsigned int
0x180028b7a  mov     rdx, r14; struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *
0x180028b7d  mov     rcx, rbx; this
0x180028b80  call    ?GetTableMetaTable@CSDTFxd@@AEAAJPEAU__MIDL___MIDL_itf_catalog_0000_0000_0001@@K@Z; CSDTFxd::GetTableMetaTable(__MIDL___MIDL_itf_catalog_0000_0000_0001 *,ulong)
0x180028b85  jmp     loc_180028CC3
0x180028b8a  mov     edx, 1; dwCmpFlags
0x180028b8f  mov     [rsp+78h+cchCount2], edi; cchCount2
0x180028b93  lea     rax, aTagmeta; "TAGMETA"
0x180028b9a  mov     r9d, edi; cchCount1
0x180028b9d  mov     r8, r15; lpString1
0x180028ba0  mov     [rsp+78h+lpString2], rax; lpString2
0x180028ba5  lea     ecx, [rdx+7Eh]; Locale
0x180028ba8  call    cs:__imp_CompareStringW
0x180028bae  cmp     eax, 2
0x180028bb1  jnz     loc_180028B04
0x180028bb7  mov     r8d, esi; unsigned int
0x180028bba  mov     rdx, r14; struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *
0x180028bbd  mov     rcx, rbx; this
0x180028bc0  call    ?GetTagMetaTable@CSDTFxd@@AEAAJPEAU__MIDL___MIDL_itf_catalog_0000_0000_0001@@K@Z; CSDTFxd::GetTagMetaTable(__MIDL___MIDL_itf_catalog_0000_0000_0001 *,ulong)
0x180028bc5  jmp     loc_180028CC3
0x180028bca  or      edi, 0FFFFFFFFh
0x180028bcd  lea     rax, aRelationmeta; "RELATIONMETA"
0x180028bd4  mov     [rsp+78h+cchCount2], edi; cchCount2
0x180028bd8  mov     r9d, edi; cchCount1
0x180028bdb  mov     r8, r15; lpString1
0x180028bde  mov     [rsp+78h+lpString2], rax; lpString2
0x180028be3  lea     edx, [rdi+2]; dwCmpFlags
0x180028be6  lea     ecx, [rdx+7Eh]; Locale
0x180028be9  call    cs:__imp_CompareStringW
0x180028bef  cmp     eax, 2
0x180028bf2  jnz     loc_180028B04
0x180028bf8  mov     r8d, esi; unsigned int
0x180028bfb  mov     rdx, r14; struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *
0x180028bfe  mov     rcx, rbx; this
0x180028c01  call    ?GetRelationMetaTable@CSDTFxd@@AEAAJPEAU__MIDL___MIDL_itf_catalog_0000_0000_0001@@K@Z; CSDTFxd::GetRelationMetaTable(__MIDL___MIDL_itf_catalog_0000_0000_0001 *,ulong)
0x180028c06  jmp     loc_180028CC3
0x180028c0b  or      edi, 0FFFFFFFFh
0x180028c0e  lea     rax, aQuerymeta; "QUERYMETA"
0x180028c15  mov     [rsp+78h+cchCount2], edi; cchCount2
0x180028c19  mov     r9d, edi; cchCount1
0x180028c1c  mov     r8, r15; lpString1
0x180028c1f  mov     [rsp+78h+lpString2], rax; lpString2
0x180028c24  lea     edx, [rdi+2]; dwCmpFlags
0x180028c27  lea     ecx, [rdx+7Eh]; Locale
0x180028c2a  call    cs:__imp_CompareStringW
0x180028c30  cmp     eax, 2
0x180028c33  jnz     loc_180028B04
0x180028c39  mov     r8d, esi; unsigned int
0x180028c3c  mov     rdx, r14; struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *
0x180028c3f  mov     rcx, rbx; this
0x180028c42  call    ?GetQueryMetaTable@CSDTFxd@@AEAAJPEAU__MIDL___MIDL_itf_catalog_0000_0000_0001@@K@Z; CSDTFxd::GetQueryMetaTable(__MIDL___MIDL_itf_catalog_0000_0000_0001 *,ulong)
0x180028c47  jmp     short loc_180028CC3
0x180028c49  or      edi, 0FFFFFFFFh
0x180028c4c  lea     rax, aIndexmeta; "INDEXMETA"
0x180028c53  mov     [rsp+78h+cchCount2], edi; cchCount2
0x180028c57  mov     r9d, edi; cchCount1
0x180028c5a  mov     r8, r15; lpString1
0x180028c5d  mov     [rsp+78h+lpString2], rax; lpString2
0x180028c62  lea     edx, [rdi+2]; dwCmpFlags
0x180028c65  lea     ecx, [rdx+7Eh]; Locale
0x180028c68  call    cs:__imp_CompareStringW
0x180028c6e  cmp     eax, 2
0x180028c71  jnz     loc_180028B04
0x180028c77  mov     r8d, esi; unsigned int
0x180028c7a  mov     rdx, r14; struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *
0x180028c7d  mov     rcx, rbx; this
0x180028c80  call    ?GetIndexMetaTable@CSDTFxd@@AEAAJPEAU__MIDL___MIDL_itf_catalog_0000_0000_0001@@K@Z; CSDTFxd::GetIndexMetaTable(__MIDL___MIDL_itf_catalog_0000_0000_0001 *,ulong)
0x180028c85  jmp     short loc_180028CC3
0x180028c87  or      edi, 0FFFFFFFFh
0x180028c8a  lea     rax, aDatabasemeta_0; "DATABASEMETA"
0x180028c91  mov     [rsp+78h+cchCount2], edi; cchCount2
0x180028c95  mov     r9d, edi; cchCount1
0x180028c98  mov     r8, r15; lpString1
0x180028c9b  mov     [rsp+78h+lpString2], rax; lpString2
0x180028ca0  lea     edx, [rdi+2]; dwCmpFlags
0x180028ca3  lea     ecx, [rdx+7Eh]; Locale
0x180028ca6  call    cs:__imp_CompareStringW
0x180028cac  cmp     eax, 2
0x180028caf  jnz     loc_180028B04
0x180028cb5  mov     r8d, esi; unsigned int
0x180028cb8  mov     rdx, r14; struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *
0x180028cbb  mov     rcx, rbx; this
0x180028cbe  call    ?GetDatabaseMetaTable@CSDTFxd@@AEAAJPEAU__MIDL___MIDL_itf_catalog_0000_0000_0001@@K@Z; CSDTFxd::GetDatabaseMetaTable(__MIDL___MIDL_itf_catalog_0000_0000_0001 *,ulong)
0x180028cc3  mov     ebp, eax
0x180028cc5  test    eax, eax
0x180028cc7  jns     short loc_180028CD4
0x180028cc9  cmp     eax, 80210816h
0x180028cce  jnz     loc_180028B04
0x180028cd4  mov     r8d, esi; unsigned int
0x180028cd7  mov     rdx, r14; struct __MIDL___MIDL_itf_catalog_0000_0000_0001 *
0x180028cda  mov     rcx, rbx; this
0x180028cdd  call    ?GetIndexMeta@CSDTFxd@@AEAAJPEBU__MIDL___MIDL_itf_catalog_0000_0000_0001@@K@Z; CSDTFxd::GetIndexMeta(__MIDL___MIDL_itf_catalog_0000_0000_0001 const *,ulong)
0x180028ce2  test    eax, eax
0x180028ce4  jns     loc_180028E98
0x180028cea  jmp     loc_180028F27
0x180028cef  xor     edx, edx
0x180028cf1  cmp     edx, esi
0x180028cf3  jnb     short loc_180028D12
0x180028cf5  lea     rcx, [rdx+rdx*2]
0x180028cf9  test    dword ptr [r14+rcx*8+0Ch], 0F0000000h
0x180028d02  jz      short loc_180028D08
0x180028d04  inc     edx
0x180028d06  jmp     short loc_180028CF1
0x180028d08  mov     eax, 8021080Bh
0x180028d0d  jmp     loc_180028F27
0x180028d12  xor     esi, esi
0x180028d14  mov     [rbx+70h], rsi
0x180028d18  xor     edi, edi
0x180028d1a  mov     rcx, [rbx+98h]; this
0x180028d21  cmp     edi, [rcx+24h]
0x180028d24  jnb     short loc_180028DA2
0x180028d26  mov     eax, [rcx+20h]
0x180028d29  lea     r14, [rdi+rdi*2]
0x180028d2d  add     r14, r14
0x180028d30  add     rax, rcx
0x180028d33  mov     edx, [rax+r14*8]
0x180028d37  test    edx, edx
0x180028d39  jnz     short loc_180028D40
0x180028d3b  xor     r8d, r8d
0x180028d3e  jmp     short loc_180028D4A
0x180028d40  mov     r8d, [rcx+38h]
0x180028d44  add     r8, rcx
0x180028d47  add     r8, rdx; unsigned __int16 *
0x180028d4a  mov     rdx, r12; unsigned __int16 *
0x180028d4d  call    ?StringInsensitiveCompare@CSDTFxd@@AEBAHPEBG0@Z; CSDTFxd::StringInsensitiveCompare(ushort const *,ushort const *)
0x180028d52  test    eax, eax
0x180028d54  jz      short loc_180028D5A
0x180028d56  inc     edi
0x180028d58  jmp     short loc_180028D1A
0x180028d5a  lfence
0x180028d5d  mov     r8, [rbx+98h]
0x180028d64  mov     eax, [r8+20h]
0x180028d68  mov     edx, [r8+58h]
0x180028d6c  add     rax, r8
0x180028d6f  mov     eax, [rax+r14*8+28h]
0x180028d74  imul    rax, 6Ch ; 'l'
0x180028d78  add     rax, r8
0x180028d7b  add     rdx, rax
0x180028d7e  mov     [rbx+70h], rdx
0x180028d82  mov     eax, [r8+20h]
0x180028d86  add     rax, r8
0x180028d89  mov     ecx, [rax+r14*8+10h]
0x180028d8e  test    ecx, ecx
0x180028d90  jnz     short loc_180028D96
0x180028d92  xor     ecx, ecx
0x180028d94  jmp     short loc_180028DA0
0x180028d96  mov     eax, [r8+38h]
0x180028d9a  add     rax, r8
0x180028d9d  add     rcx, rax
0x180028da0  mov     esi, [rcx]
0x180028da2  mov     rax, [rbx+70h]
0x180028da6  test    rax, rax
0x180028da9  jz      loc_180028F22
0x180028daf  xor     edi, edi
0x180028db1  test    esi, esi
0x180028db3  jz      short loc_180028DED
0x180028db5  mov     edx, [rax+4]
0x180028db8  test    edx, edx
0x180028dba  jnz     short loc_180028DC1
0x180028dbc  xor     r8d, r8d
0x180028dbf  jmp     short loc_180028DD2
0x180028dc1  mov     rcx, [rbx+98h]; this
0x180028dc8  mov     r8d, [rcx+38h]
0x180028dcc  add     r8, rcx
0x180028dcf  add     r8, rdx; unsigned __int16 *
0x180028dd2  mov     rdx, r15; unsigned __int16 *
0x180028dd5  call    ?StringInsensitiveCompare@CSDTFxd@@AEBAHPEBG0@Z; CSDTFxd::StringInsensitiveCompare(ushort const *,ushort const *)
0x180028dda  test    eax, eax
0x180028ddc  jz      short loc_180028DF5
0x180028dde  add     qword ptr [rbx+70h], 6Ch ; 'l'
0x180028de3  inc     edi
0x180028de5  mov     rax, [rbx+70h]
0x180028de9  cmp     edi, esi
0x180028deb  jb      short loc_180028DB5
0x180028ded  cmp     edi, esi
0x180028def  jz      loc_180028B04
0x180028df5  mov     r8, [rbx+70h]
0x180028df9  cmp     dword ptr [r8+4Ch], 0
0x180028dfe  jle     loc_180028B04
0x180028e04  mov     edx, [r8+4Ch]
0x180028e08  mov     r9, [rbx+98h]
0x180028e0f  mov     ecx, [r9+68h]
0x180028e13  add     rcx, r9
0x180028e16  lea     rax, [rcx+rdx*4]
0x180028e1a  mov     [rbx+50h], rax
0x180028e1e  mov     [rbx+48h], rax
0x180028e22  mov     eax, [r8+48h]
0x180028e26  mov     edx, [r9+18h]
0x180028e2a  imul    rax, 54h ; 'T'
  ... truncated ...
```
