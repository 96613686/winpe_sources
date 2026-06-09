# CPropertyDescription::_MakeEnumPropVariantCanonical(tagPROPVARIANT *,int *)

- ea: `0x18000bc6c`
- end: `0x18000bfd1`
- name: `?_MakeEnumPropVariantCanonical@CPropertyDescription@@AEAAJPEAUtagPROPVARIANT@@PEAH@Z`
- size: `869`
- prototype: `int(CPropertyDescription *__hidden this, struct tagPROPVARIANT *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008870`

## callees

- `0x18000b410`
- `0x18000bb60`
- `0x18000bc6c`
- `0x18000c1a0`
- `0x180017e30`
- `0x18002f9e0`
- `0x180082a30`
- `0x180082a5c`
- `0x180083800`
- `0x180083928`
- `0x18008d2f8`
- `0x18008d58c`
- `0x18008d620`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000bd65`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000bd65`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18000bea6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18000bed9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18000bea6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18000bed9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000be10`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000be10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bf04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bf04`

## pseudocode

```c
__int64 __fastcall CPropertyDescription::_MakeEnumPropVariantCanonical(
        CPropertyDescription *this,
        PROPVARIANT *a2,
        int *a3)
{
  __int64 v3; // r12
  int *v4; // r15
  unsigned int v7; // esi
  ULONG ElementCount; // eax
  BOOL v9; // edi
  unsigned __int16 v10; // r9
  ULONG v11; // r14d
  BOOL v12; // ebp
  __int64 v13; // rdx
  unsigned int v14; // r15d
  __int64 v15; // rax
  __int16 v16; // cx
  const WCHAR *v17; // rcx
  int v18; // eax
  BYTE *v19; // rcx
  __int64 v20; // rax
  const WCHAR **v22; // rax
  const PROPVARIANT *v23; // rcx
  BOOL v24; // r15d
  BOOL v25; // ebp
  const WCHAR *v26; // rax
  const PROPVARIANT *v27; // rcx
  const WCHAR *v28; // rax
  unsigned __int16 v29; // cx
  unsigned int i; // ebp
  unsigned int j; // ebp
  int v32; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v34; // [rsp+68h] [rbp+10h]
  unsigned __int64 v35; // [rsp+70h] [rbp+18h] BYREF
  LPCWSTR pszStr2; // [rsp+78h] [rbp+20h]

  v35 = (unsigned __int64)a3;
  v3 = 0;
  v4 = a3;
  *a3 = 0;
  if ( (*(_WORD *)a2 & 0x1000) != 0 )
  {
    v7 = 0;
    ElementCount = PropVariantGetElementCount(a2);
    v9 = 1;
    v10 = *(_WORD *)a2 & 0xFFF;
    v11 = ElementCount;
    if ( v10 == 31 )
    {
      v34 = 0;
      if ( !ElementCount )
        goto LABEL_22;
      while ( 1 )
      {
        pszStr2 = (LPCWSTR)*((_QWORD *)a2[2] + v3);
        if ( pszStr2 )
          break;
LABEL_20:
        ++v3;
        if ( ++v34 >= v11 )
        {
          v4 = (int *)v35;
          goto LABEL_22;
        }
      }
      v12 = 0;
      if ( (int)CPropertyDescription::_EnsureFmtEnumInfoList(this) >= 0 )
      {
        v13 = *((_QWORD *)this + 19);
        if ( *(_DWORD *)v13 )
        {
          if ( **(_DWORD **)(v13 + 8) )
          {
            v23 = *(const PROPVARIANT **)(v13 + 48);
            v24 = 1;
            v25 = 1;
            if ( v23 )
            {
              v26 = PropVariantToStringWithDefault(v23, 0);
              if ( v26 )
                v24 = StrCmpCW(pszStr2, v26) >= 0;
            }
            v27 = *(const PROPVARIANT **)(*((_QWORD *)this + 19) + 56LL);
            if ( v27 )
            {
              v28 = PropVariantToStringWithDefault(v27, 0);
              if ( v28 )
                v25 = StrCmpCW(pszStr2, v28) < 0;
            }
            if ( v24 && v25 )
            {
              v19 = (BYTE *)a2[2];
LABEL_19:
              v20 = v7++;
              *(_QWORD *)&v19[8 * v20] = pszStr2;
              goto LABEL_20;
            }
            v12 = 0;
          }
          else if ( *(_DWORD *)v13 )
          {
            v14 = 0;
            while ( 1 )
            {
              if ( v12 )
                goto LABEL_18;
              v15 = 112LL * v14 + *(_QWORD *)(v13 + 8) + 8LL;
              v16 = *(_WORD *)v15;
              if ( *(_WORD *)v15 == 31 || v16 == 8 )
              {
LABEL_13:
                v17 = &Src;
                if ( *(_QWORD *)(v15 + 8) )
                  v17 = *(const WCHAR **)(v15 + 8);
                goto LABEL_15;
              }
              if ( v16 != 16396 )
                goto LABEL_30;
              v15 = *(_QWORD *)(v15 + 8);
              if ( v15 )
                break;
LABEL_31:
              v17 = &Src;
LABEL_15:
              v18 = StrCmpICW(v17, pszStr2);
              v13 = *((_QWORD *)this + 19);
              ++v14;
              v12 = v18 == 0;
              if ( v14 >= *(_DWORD *)v13 )
              {
                if ( !v18 )
                  goto LABEL_18;
                goto LABEL_17;
              }
            }
            v16 = *(_WORD *)v15;
            if ( *(_WORD *)v15 == 8 )
              goto LABEL_13;
LABEL_30:
            if ( v16 == 16392 )
            {
              v22 = *(const WCHAR ***)(v15 + 8);
              v17 = &Src;
              if ( *v22 )
                v17 = *v22;
              goto LABEL_15;
            }
            goto LABEL_31;
          }
        }
      }
LABEL_17:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAC2,
        (unsigned int)"onecoreuap\\shell\\propsys\\propdesc.cpp",
        (const char *)0x8000FFFFLL,
        v32);
LABEL_18:
      v19 = (BYTE *)a2[2];
      if ( !v12 )
      {
        CoTaskMemFree(*(LPVOID *)&v19[8 * v3]);
        *((_QWORD *)a2[2] + v3) = 0;
        goto LABEL_20;
      }
      goto LABEL_19;
    }
    if ( (unsigned int)IsVarTypeSignedInteger(v10) )
    {
      for ( i = 0; i < v11; ++i )
      {
        v35 = 0;
        PropVariantGetElemAsInt64((const struct tagPROPVARIANT *)a2, i, (__int64 *)&v35);
        if ( (unsigned int)CPropertyDescription::_IsCanonicalEnumeratedInt(this, v35) )
          PropVariantCopyAndClearElem(a2, v7++, i);
      }
    }
    else if ( (unsigned int)IsVarTypeUnsignedInteger(v29) )
    {
      for ( j = 0; j < v11; ++j )
      {
        v35 = 0;
        PropVariantGetElemAsUInt64((const struct tagPROPVARIANT *)a2, j, &v35);
        if ( (unsigned int)CPropertyDescription::_IsCanonicalEnumeratedUInt(this, v35) )
          PropVariantCopyAndClearElem(a2, v7++, j);
      }
    }
    else
    {
      v7 = *((_DWORD *)a2 + 2);
    }
LABEL_22:
    if ( v7 )
    {
      *((_DWORD *)a2 + 2) = v7;
      v9 = v7 != v11;
    }
    else
    {
      CoTaskMemFree(a2[2]);
      a2[2] = 0;
      *(_WORD *)a2 = 0;
    }
    *v4 = v9;
  }
  else if ( !CPropertyDescription::_IsCanonicalEnumeratedSinglePropVariant(this, (const struct tagPROPVARIANT *)a2) )
  {
    PropVariantClear(a2);
    *v4 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000bc6c  mov     [rsp+arg_0], rbx
0x18000bc71  mov     [rsp+arg_10], r8
0x18000bc76  push    rbp
0x18000bc77  push    rsi
0x18000bc78  push    rdi
0x18000bc79  push    r12
0x18000bc7b  push    r13
0x18000bc7d  push    r14
0x18000bc7f  push    r15; int
0x18000bc81  sub     rsp, 20h
0x18000bc85  xor     r12d, r12d
0x18000bc88  mov     eax, 1000h
0x18000bc8d  mov     r15, r8
0x18000bc90  mov     rbx, rdx
0x18000bc93  mov     r13, rcx
0x18000bc96  mov     [r8], r12d
0x18000bc99  test    [rdx], ax
0x18000bc9c  jz      loc_18000BE04
0x18000bca2  mov     rcx, rdx; propvar
0x18000bca5  mov     esi, r12d
0x18000bca8  call    PropVariantGetElementCount
0x18000bcad  mov     r9d, 0FFFh
0x18000bcb3  lea     edi, [r12+1]
0x18000bcb8  and     r9w, [rbx]
0x18000bcbc  mov     r14d, eax
0x18000bcbf  lea     eax, [rdi+1Eh]
0x18000bcc2  cmp     r9w, ax
0x18000bcc6  jnz     loc_18000BF1B
0x18000bccc  mov     [rsp+58h+arg_8], r12d
0x18000bcd1  test    r14d, r14d
0x18000bcd4  jz      loc_18000BDD9
0x18000bcda  mov     rax, [rbx+10h]
0x18000bcde  mov     rax, [rax+r12*8]
0x18000bce2  mov     [rsp+58h+pszStr2], rax
0x18000bce7  test    rax, rax
0x18000bcea  jz      loc_18000BDBB
0x18000bcf0  mov     rcx, r13; this
0x18000bcf3  xor     ebp, ebp
0x18000bcf5  call    ?_EnsureFmtEnumInfoList@CPropertyDescription@@AEAAJXZ; CPropertyDescription::_EnsureFmtEnumInfoList(void)
0x18000bcfa  test    eax, eax
0x18000bcfc  js      loc_18000BD86
0x18000bd02  mov     rdx, [r13+98h]
0x18000bd09  cmp     [rdx], ebp
0x18000bd0b  jz      short loc_18000BD86
0x18000bd0d  mov     rax, [rdx+8]
0x18000bd11  cmp     [rax], ebp
0x18000bd13  jnz     loc_18000BE84
0x18000bd19  cmp     [rdx], ebp
0x18000bd1b  jbe     short loc_18000BD86
0x18000bd1d  xor     r15d, r15d
0x18000bd20  test    ebp, ebp
0x18000bd22  jnz     short loc_18000BDA2
0x18000bd24  mov     eax, r15d
0x18000bd27  imul    rcx, rax, 70h ; 'p'
0x18000bd2b  mov     rax, [rdx+8]
0x18000bd2f  lea     edx, [rbp+1Fh]
0x18000bd32  add     rax, 8
0x18000bd36  add     rax, rcx
0x18000bd39  movzx   ecx, word ptr [rax]
0x18000bd3c  cmp     dx, cx
0x18000bd3f  jz      short loc_18000BD4F
0x18000bd41  lea     r8d, [rbp+8]
0x18000bd45  cmp     r8w, cx
0x18000bd49  jnz     loc_18000BE33
0x18000bd4f  cmp     qword ptr [rax+8], 0
0x18000bd54  lea     rcx, Src
0x18000bd5b  cmovnz  rcx, [rax+8]; pszStr1
0x18000bd60  mov     rdx, [rsp+58h+pszStr2]; pszStr2
0x18000bd65  call    cs:__imp_StrCmpICW
0x18000bd6b  mov     rdx, [r13+98h]
0x18000bd72  xor     ebp, ebp
0x18000bd74  add     r15d, edi
0x18000bd77  test    eax, eax
0x18000bd79  setz    bpl
0x18000bd7d  cmp     r15d, [rdx]
0x18000bd80  jb      short loc_18000BD20
0x18000bd82  test    eax, eax
0x18000bd84  jz      short loc_18000BDA2
0x18000bd86  mov     rcx, [rsp+58h]; this
0x18000bd8b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\propsys\\propdesc.cp"...
0x18000bd92  mov     r9d, 8000FFFFh; char *
0x18000bd98  mov     edx, 0AC2h; void *
0x18000bd9d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bda2  mov     rcx, [rbx+10h]; this
0x18000bda6  test    ebp, ebp
0x18000bda8  jz      loc_18000BF00
0x18000bdae  mov     rdx, [rsp+58h+pszStr2]; struct tagPROPVARIANT *
0x18000bdb3  mov     eax, esi
0x18000bdb5  add     esi, edi
0x18000bdb7  mov     [rcx+rax*8], rdx
0x18000bdbb  mov     eax, [rsp+58h+arg_8]
0x18000bdbf  add     eax, edi
0x18000bdc1  inc     r12
0x18000bdc4  mov     [rsp+58h+arg_8], eax
0x18000bdc8  cmp     eax, r14d
0x18000bdcb  jb      loc_18000BCDA
0x18000bdd1  mov     r15, [rsp+58h+arg_10]
0x18000bdd6  xor     r12d, r12d
0x18000bdd9  test    esi, esi
0x18000bddb  jz      short loc_18000BE1F
0x18000bddd  cmp     esi, r14d
0x18000bde0  mov     [rbx+8], esi
0x18000bde3  mov     edi, r12d
0x18000bde6  setnz   dil
0x18000bdea  mov     [r15], edi
0x18000bded  mov     rbx, [rsp+58h+arg_0]
0x18000bdf2  xor     eax, eax
0x18000bdf4  add     rsp, 20h
0x18000bdf8  pop     r15
0x18000bdfa  pop     r14
0x18000bdfc  pop     r13
0x18000bdfe  pop     r12
0x18000be00  pop     rdi
0x18000be01  pop     rsi
0x18000be02  pop     rbp
0x18000be03  retn
0x18000be04  call    ?_IsCanonicalEnumeratedSinglePropVariant@CPropertyDescription@@AEAAHAEBUtagPROPVARIANT@@@Z; CPropertyDescription::_IsCanonicalEnumeratedSinglePropVariant(tagPROPVARIANT const &)
0x18000be09  test    eax, eax
0x18000be0b  jnz     short loc_18000BDED
0x18000be0d  mov     rcx, rbx; pvar
0x18000be10  call    cs:__imp_PropVariantClear
0x18000be16  mov     dword ptr [r15], 1
0x18000be1d  jmp     short loc_18000BDED
0x18000be1f  mov     rcx, [rbx+10h]; pv
0x18000be23  call    cs:__imp_CoTaskMemFree
0x18000be29  mov     [rbx+10h], r12
0x18000be2d  mov     [rbx], r12w
0x18000be31  jmp     short loc_18000BDEA
0x18000be33  mov     edx, 400Ch
0x18000be38  cmp     cx, dx
0x18000be3b  jz      short loc_18000BE61
0x18000be3d  mov     edx, 4008h
0x18000be42  cmp     cx, dx
0x18000be45  jz      short loc_18000BE6C
0x18000be47  lea     rcx, Src
0x18000be4e  jmp     loc_18000BD60
0x18000be53  movzx   ecx, word ptr [rax]
0x18000be56  cmp     cx, r8w
0x18000be5a  jnz     short loc_18000BE3D
0x18000be5c  jmp     loc_18000BD4F
0x18000be61  mov     rax, [rax+8]
0x18000be65  test    rax, rax
0x18000be68  jz      short loc_18000BE47
0x18000be6a  jmp     short loc_18000BE53
0x18000be6c  mov     rax, [rax+8]
0x18000be70  lea     rcx, Src
0x18000be77  cmp     qword ptr [rax], 0
0x18000be7b  cmovnz  rcx, [rax]
0x18000be7f  jmp     loc_18000BD60
0x18000be84  mov     rcx, [rdx+30h]; propvarIn
0x18000be88  mov     r15d, edi
0x18000be8b  mov     ebp, edi
0x18000be8d  test    rcx, rcx
0x18000be90  jz      short loc_18000BEB5
0x18000be92  xor     edx, edx; pszDefault
0x18000be94  call    PropVariantToStringWithDefault
0x18000be99  test    rax, rax
0x18000be9c  jz      short loc_18000BEB5
0x18000be9e  mov     rcx, [rsp+58h+pszStr2]; pszStr1
0x18000bea3  mov     rdx, rax; pszStr2
0x18000bea6  call    cs:__imp_StrCmpCW
0x18000beac  xor     r15d, r15d
0x18000beaf  test    eax, eax
0x18000beb1  setns   r15b
0x18000beb5  mov     rax, [r13+98h]
0x18000bebc  mov     rcx, [rax+38h]; propvarIn
0x18000bec0  test    rcx, rcx
0x18000bec3  jz      short loc_18000BEE7
0x18000bec5  xor     edx, edx; pszDefault
0x18000bec7  call    PropVariantToStringWithDefault
0x18000becc  test    rax, rax
0x18000becf  jz      short loc_18000BEE7
0x18000bed1  mov     rcx, [rsp+58h+pszStr2]; pszStr1
0x18000bed6  mov     rdx, rax; pszStr2
0x18000bed9  call    cs:__imp_StrCmpCW
0x18000bedf  xor     ebp, ebp
0x18000bee1  test    eax, eax
0x18000bee3  sets    bpl
0x18000bee7  test    r15d, r15d
0x18000beea  jz      short loc_18000BEF9
0x18000beec  test    ebp, ebp
0x18000beee  jz      short loc_18000BEF9
0x18000bef0  mov     rcx, [rbx+10h]
0x18000bef4  jmp     loc_18000BDAE
0x18000bef9  xor     ebp, ebp
0x18000befb  jmp     loc_18000BD86
0x18000bf00  mov     rcx, [rcx+r12*8]; pv
0x18000bf04  call    cs:__imp_CoTaskMemFree
0x18000bf0a  mov     rax, [rbx+10h]
0x18000bf0e  mov     qword ptr [rax+r12*8], 0
0x18000bf16  jmp     loc_18000BDBB
0x18000bf1b  movzx   ecx, r9w; unsigned __int16
0x18000bf1f  call    ?IsVarTypeSignedInteger@@YAHG@Z; IsVarTypeSignedInteger(ushort)
0x18000bf24  test    eax, eax
0x18000bf26  jz      short loc_18000BF74
0x18000bf28  mov     ebp, r12d
0x18000bf2b  test    r14d, r14d
0x18000bf2e  jz      loc_18000BDD9
0x18000bf34  lea     r8, [rsp+58h+arg_10]; __int64 *
0x18000bf39  mov     [rsp+58h+arg_10], r12
0x18000bf3e  mov     edx, ebp; unsigned int
0x18000bf40  mov     rcx, rbx; struct tagPROPVARIANT *
0x18000bf43  call    ?PropVariantGetElemAsInt64@@YAJAEBUtagPROPVARIANT@@KPEA_J@Z; PropVariantGetElemAsInt64(tagPROPVARIANT const &,ulong,__int64 *)
0x18000bf48  mov     rdx, [rsp+58h+arg_10]; __int64
0x18000bf4d  mov     rcx, r13; this
0x18000bf50  call    ?_IsCanonicalEnumeratedInt@CPropertyDescription@@AEAAH_J@Z; CPropertyDescription::_IsCanonicalEnumeratedInt(__int64)
0x18000bf55  test    eax, eax
0x18000bf57  jz      short loc_18000BF68
0x18000bf59  mov     r8d, ebp; unsigned int
0x18000bf5c  mov     edx, esi; unsigned int
0x18000bf5e  mov     rcx, rbx; propvar
0x18000bf61  call    ?PropVariantCopyAndClearElem@@YAJPEAUtagPROPVARIANT@@KK@Z; PropVariantCopyAndClearElem(tagPROPVARIANT *,ulong,ulong)
0x18000bf66  add     esi, edi
0x18000bf68  add     ebp, edi
0x18000bf6a  cmp     ebp, r14d
0x18000bf6d  jb      short loc_18000BF34
0x18000bf6f  jmp     loc_18000BDD9
0x18000bf74  call    ?IsVarTypeUnsignedInteger@@YAHG@Z; IsVarTypeUnsignedInteger(ushort)
0x18000bf79  test    eax, eax
0x18000bf7b  jz      short loc_18000BFC9
0x18000bf7d  mov     ebp, r12d
0x18000bf80  test    r14d, r14d
0x18000bf83  jz      loc_18000BDD9
0x18000bf89  lea     r8, [rsp+58h+arg_10]; unsigned __int64 *
0x18000bf8e  mov     [rsp+58h+arg_10], r12
0x18000bf93  mov     edx, ebp; unsigned int
0x18000bf95  mov     rcx, rbx; struct tagPROPVARIANT *
0x18000bf98  call    ?PropVariantGetElemAsUInt64@@YAJAEBUtagPROPVARIANT@@KPEA_K@Z; PropVariantGetElemAsUInt64(tagPROPVARIANT const &,ulong,unsigned __int64 *)
0x18000bf9d  mov     rdx, [rsp+58h+arg_10]; unsigned __int64
0x18000bfa2  mov     rcx, r13; this
0x18000bfa5  call    ?_IsCanonicalEnumeratedUInt@CPropertyDescription@@AEAAH_K@Z; CPropertyDescription::_IsCanonicalEnumeratedUInt(unsigned __int64)
0x18000bfaa  test    eax, eax
0x18000bfac  jz      short loc_18000BFBD
0x18000bfae  mov     r8d, ebp; unsigned int
0x18000bfb1  mov     edx, esi; unsigned int
0x18000bfb3  mov     rcx, rbx; propvar
0x18000bfb6  call    ?PropVariantCopyAndClearElem@@YAJPEAUtagPROPVARIANT@@KK@Z; PropVariantCopyAndClearElem(tagPROPVARIANT *,ulong,ulong)
0x18000bfbb  add     esi, edi
0x18000bfbd  add     ebp, edi
0x18000bfbf  cmp     ebp, r14d
0x18000bfc2  jb      short loc_18000BF89
0x18000bfc4  jmp     loc_18000BDD9
0x18000bfc9  mov     esi, [rbx+8]
0x18000bfcc  jmp     loc_18000BDD9
```
