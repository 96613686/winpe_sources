# AslPathWildcardFindFirst

- ea: `0x14073d8dc`
- end: `0x14073de6b`
- name: `AslPathWildcardFindFirst`
- size: `1423`
- prototype: `__int64 __fastcall(NTSTRSAFE_PWSTR pszDest)`
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path`

## callers

- `0x140735b60`

## callees

- `0x1402dc448`
- `0x1403f2d50`
- `0x140425870`
- `0x1404432a8`
- `0x140446e5c`
- `0x14053eb30`
- `0x1406f4480`
- `0x1406f4880`
- `0x14073d8dc`
- `0x14073ea34`
- `0x14073f18c`
- `0x140825df4`
- `0x140826dd8`
- `0x1408277e4`
- `0x140827a04`
- `0x140827adc`
- `0x1408eeff0`
- `0x140979890`
- `0x14097b68c`
- `0x14097d158`
- `0x1409b3930`
- `0x140bae320`
- `0x140bae8e0`

## string_xrefs

- `0x14073ddf4`: `AslpPathWildcardPushNode failed [%x]`
- `0x14073d988`: `AslPathWildcardFindFirst`
- `0x14073de05`: `AslPathWildcardFindFirst`
- `0x14073d9b1`: `AslPathCleanUstr failed [%x]`
- `0x14073d97b`: `RtlCreateUnicodeString failed`
- `0x14073dc62`: `AslpPathWildcardInitStack`
- `0x14073dc13`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`
- `0x14073dc73`: `AslpPathWildcardInitStack failed [%x]`
- `0x14073da53`: `Failed to split the wildcard path`
- `0x14073da30`: `RtlStringCbCopyNW failed [%x]`
- `0x14073daa3`: `RtlStringCbCopyNW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindFirst(NTSTRSAFE_PWSTR pszDest, ULONGLONG a2, const wchar_t *a3, _QWORD *a4)
{
  const WCHAR *v8; // r14
  int Next; // ebx
  int v10; // eax
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  size_t v13; // rbx
  wchar_t *v14; // rax
  NTSTATUS v15; // eax
  int Leaves; // eax
  __int64 v17; // rcx
  wchar_t *Buffer; // rcx
  NTSTATUS v19; // eax
  _DWORD *v20; // rdi
  HRESULT v21; // eax
  ULONGLONG v22; // r10
  int v23; // r9d
  size_t v24; // rsi
  void *v25; // r15
  PVOID PoolWithTag; // rax
  void *v27; // rbx
  int matched; // eax
  void *v29; // rcx
  const char *v30; // r9
  int v31; // r8d
  ULONGLONG v32; // r13
  unsigned __int64 v33; // r9
  __int64 v34; // rsi
  ULONGLONG v35; // rdx
  ULONGLONG v36; // rcx
  __int64 v37; // r10
  ULONGLONG v38; // rsi
  SIZE_T v39; // r15
  PVOID v40; // rax
  void *v41; // rbx
  PVOID v42; // rax
  ULONGLONG v43; // rcx
  ULONGLONG v44; // rcx
  ULONGLONG v45; // rdx
  __int64 v46; // rcx
  NTSTRSAFE_PCWSTR pszSrc; // [rsp+20h] [rbp-60h]
  ULONGLONG pullResult; // [rsp+30h] [rbp-50h] BYREF
  _DWORD *v49; // [rsp+38h] [rbp-48h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-30h] BYREF
  UNICODE_STRING v52; // [rsp+60h] [rbp-20h] BYREF
  __int128 v53; // [rsp+70h] [rbp-10h]
  ULONGLONG pusResult; // [rsp+C8h] [rbp+48h] BYREF

  pusResult = a2;
  if ( !pszDest )
    return 3221225711LL;
  if ( !a3 || !*a3 )
    return 3221225713LL;
  if ( !a4 )
    return 3221225714LL;
  *pszDest = 0;
  v49 = 0;
  LOWORD(pusResult) = 0;
  *a4 = 0;
  DestinationString = 0;
  v8 = 0;
  SourceString = 0;
  v52 = 0;
  v53 = 0;
  if ( RtlCreateUnicodeString(&DestinationString, a3) )
  {
    v10 = AslPathCleanUstr(&DestinationString);
    Next = v10;
    if ( v10 < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslPathWildcardFindFirst",
        2257,
        (unsigned int)"AslPathCleanUstr failed [%x]",
        v10);
      goto LABEL_66;
    }
    v11 = RtlUShortAdd(DestinationString.Length, 4u, (USHORT *)&pusResult);
    Next = v11;
    if ( v11 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindFirst", 2263, (unsigned int)"RtlUShortAdd failed [%x]", v11);
      goto LABEL_66;
    }
    v13 = (unsigned __int16)pusResult;
    v14 = (wchar_t *)AslAlloc(v12, (unsigned __int16)pusResult);
    v8 = v14;
    if ( !v14 )
      goto LABEL_14;
    v15 = RtlStringCbCopyNW(v14, v13, DestinationString.Buffer, DestinationString.Length);
    Next = v15;
    if ( v15 < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslPathWildcardFindFirst",
        2275,
        (unsigned int)"RtlStringCbCopyNW failed [%x]",
        v15);
      goto LABEL_66;
    }
    Leaves = AslpPathWildcardMakeLeaves(v8);
    if ( !Leaves )
    {
      Next = -1073741767;
      AslLogCallPrintf(
        1,
        (unsigned int)"AslPathWildcardFindFirst",
        2293,
        (unsigned int)"Failed to split the wildcard path");
      goto LABEL_66;
    }
    if ( Leaves == 1 )
    {
      Buffer = DestinationString.Buffer;
      *a4 = -1;
      if ( (unsigned int)AslDoesFileExistNtPath(Buffer) )
      {
        v19 = RtlStringCchCopyW(pszDest, 0x104u, a3);
        Next = v19;
        if ( v19 >= 0 )
          Next = 0;
        else
          AslLogCallPrintf(
            1,
            (unsigned int)"AslPathWildcardFindFirst",
            2311,
            (unsigned int)"RtlStringCbCopyNW failed [%x]",
            v19);
      }
      else
      {
        Next = -2147483642;
      }
      goto LABEL_66;
    }
    v49 = (_DWORD *)AslAlloc(v17, 64);
    v20 = v49;
    if ( !v49 )
    {
LABEL_14:
      Next = -1073741801;
      goto LABEL_66;
    }
    *v49 = wcsncmp(a3, L"\\??\\", 4u) != 0;
    *((_QWORD *)v20 + 1) = v8;
    *((_QWORD *)v20 + 2) = 0;
    v8 = 0;
    *((_QWORD *)v20 + 6) = 16;
    *((_QWORD *)v20 + 4) = 0;
    *((_QWORD *)v20 + 5) = 0;
    *((_QWORD *)v20 + 7) = 0;
    *((_QWORD *)v20 + 3) = 32;
    pusResult = 0;
    pullResult = 0;
    v21 = ULongLongMult(0, 0x20u, &pusResult);
    v23 = -1073741675;
    if ( v21 < 0 || ULongLongMult(v22, *((_QWORD *)v20 + 3), &pullResult) < 0 )
    {
      Next = v23;
    }
    else
    {
      v24 = pullResult;
      v25 = (void *)*((_QWORD *)v20 + 7);
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, pullResult, 0x72615452u);
      v27 = PoolWithTag;
      if ( v25 )
      {
        if ( PoolWithTag )
        {
          memset_0(PoolWithTag, 0, v24);
          if ( pusResult < v24 )
            v24 = pusResult;
          memmove(v27, v25, v24);
          ExFreePoolWithTag(v25, 0x72615452u);
          goto LABEL_36;
        }
      }
      else if ( PoolWithTag )
      {
        memset_0(PoolWithTag, 0, v24);
LABEL_36:
        *((_QWORD *)v20 + 7) = v27;
        *((_QWORD *)v20 + 5) = 16;
        goto LABEL_37;
      }
      Next = -1073741801;
    }
    v29 = (void *)*((_QWORD *)v20 + 7);
    if ( v29 )
      ExFreePoolWithTag(v29, 0x72615452u);
    *((_OWORD *)v20 + 1) = 0;
    *((_OWORD *)v20 + 2) = 0;
    *((_OWORD *)v20 + 3) = 0;
    if ( Next < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslpPathWildcardInitStack",
        2148,
        (unsigned int)"RtlArrayInitialize failed [%x]",
        Next);
      v30 = "AslpPathWildcardInitStack failed [%x]";
      v31 = 2349;
LABEL_65:
      LODWORD(pszSrc) = Next;
      AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindFirst", v31, (_DWORD)v30, pszSrc);
      goto LABEL_66;
    }
LABEL_37:
    RtlInitUnicodeString(&SourceString, *((PCWSTR *)v20 + 1));
    matched = AslpPathWildcardAllocMatchNode(&v52, &SourceString, 0, 0);
    Next = matched;
    if ( matched < 0 )
    {
      LODWORD(pszSrc) = matched;
      AslLogCallPrintf(
        1,
        (unsigned int)"AslPathWildcardFindFirst",
        2362,
        (unsigned int)"AslpPathWildcardAllocMatchNode failed to create root of path [%x]",
        pszSrc);
      goto LABEL_66;
    }
    v32 = *((_QWORD *)v20 + 4);
    v33 = *((_QWORD *)v20 + 5);
    if ( v32 < v33 )
      goto LABEL_59;
    if ( v32 + 1 <= v33 )
    {
      Next = -1073741811;
LABEL_64:
      v30 = "AslpPathWildcardPushNode failed [%x]";
      v31 = 2368;
      goto LABEL_65;
    }
    v34 = *((_QWORD *)v20 + 6) - 1LL;
    if ( *((_QWORD *)v20 + 6) + v32 < v32 + 1
      || (v35 = *((_QWORD *)v20 + 3),
          v36 = *((_QWORD *)v20 + 5),
          pusResult = 0,
          pullResult = 0,
          ULongLongMult(v36, v35, &pusResult) < 0)
      || (v38 = v37 & ~v34, ULongLongMult(v38, *((_QWORD *)v20 + 3), &pullResult) < 0) )
    {
      Next = -1073741675;
      goto LABEL_64;
    }
    v39 = pullResult;
    pullResult = *((_QWORD *)v20 + 7);
    if ( pullResult )
    {
      v42 = ExAllocatePoolWithTag(PagedPool, v39, 0x72615452u);
      v41 = v42;
      if ( v42 )
      {
        memset_0(v42, 0, v39);
        if ( pusResult < v39 )
          v39 = pusResult;
        memmove(v41, (const void *)pullResult, v39);
        ExFreePoolWithTag((PVOID)pullResult, 0x72615452u);
        goto LABEL_58;
      }
    }
    else
    {
      v40 = ExAllocatePoolWithTag(PagedPool, v39, 0x72615452u);
      v41 = v40;
      if ( v40 )
      {
        memset_0(v40, 0, v39);
LABEL_58:
        *((_QWORD *)v20 + 7) = v41;
        *((_QWORD *)v20 + 5) = v38;
LABEL_59:
        v43 = *((_QWORD *)v20 + 3);
        pusResult = 0;
        if ( ULongLongMult(v43, v32, &pusResult) >= 0 )
        {
          v44 = *((_QWORD *)v20 + 7);
          v45 = v44 + pusResult;
          if ( v44 + pusResult >= v44 )
          {
            *(UNICODE_STRING *)v45 = v52;
            *(_OWORD *)(v45 + 16) = v53;
            ++*((_QWORD *)v20 + 4);
            *a4 = v20;
            v52 = 0;
            v53 = 0;
            Next = AslPathWildcardFindNext(pszDest, v45, (ULONGLONG *)v20);
            goto LABEL_66;
          }
        }
        Next = -1073741675;
        goto LABEL_64;
      }
    }
    Next = -1073741801;
    goto LABEL_64;
  }
  Next = -1073741801;
  AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindFirst", 2236, (unsigned int)"RtlCreateUnicodeString failed");
LABEL_66:
  RtlFreeAnsiString(&DestinationString);
  if ( v8 )
    AslFree(v46, v8);
  if ( Next < 0 )
  {
    AslpPathWildcardFreeFindContext(&v49);
    AslpPathWildcardFreeMatchNode(&v52);
    *a4 = 0;
  }
  return (unsigned int)Next;
}

```

## disassembly

```asm
0x14073d8dc  mov     [rsp-38h+arg_10], rbx
0x14073d8e1  mov     [rsp-38h+pusResult], rdx
0x14073d8e6  mov     [rsp-38h+arg_0], rcx
0x14073d8eb  push    rbp
0x14073d8ec  push    rsi
0x14073d8ed  push    rdi
0x14073d8ee  push    r12
0x14073d8f0  push    r13
0x14073d8f2  push    r14
0x14073d8f4  push    r15
0x14073d8f6  mov     rbp, rsp
0x14073d8f9  sub     rsp, 80h
0x14073d900  xor     r15d, r15d
0x14073d903  mov     r12, r9
0x14073d906  mov     rsi, r8
0x14073d909  mov     rdi, rcx
0x14073d90c  test    rcx, rcx
0x14073d90f  jnz     short loc_14073D91B
0x14073d911  mov     eax, 0C00000EFh
0x14073d916  jmp     loc_14073DE4F
0x14073d91b  test    rsi, rsi
0x14073d91e  jz      loc_14073DE4A
0x14073d924  cmp     [r8], r15w
0x14073d928  jz      loc_14073DE4A
0x14073d92e  test    r12, r12
0x14073d931  jnz     short loc_14073D93D
0x14073d933  mov     eax, 0C00000F2h
0x14073d938  jmp     loc_14073DE4F
0x14073d93d  xorps   xmm0, xmm0
0x14073d940  mov     [rcx], r15w
0x14073d944  xorps   xmm1, xmm1
0x14073d947  mov     [rbp+var_48], r15
0x14073d94b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14073d94f  mov     word ptr [rbp+pusResult], r15w
0x14073d954  mov     rdx, rsi; SourceString
0x14073d957  mov     [r9], r15
0x14073d95a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14073d95e  mov     r14, r15
0x14073d961  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x14073d965  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x14073d969  movups  [rbp+var_10], xmm1
0x14073d96d  call    RtlCreateUnicodeString
0x14073d972  test    al, al
0x14073d974  jnz     short loc_14073D99E
0x14073d976  mov     ebx, 0C0000017h
0x14073d97b  lea     r9, aRtlcreateunico_0; "RtlCreateUnicodeString failed"
0x14073d982  mov     r8d, 8BCh
0x14073d988  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x14073d98f  mov     ecx, 1
0x14073d994  call    AslLogCallPrintf
0x14073d999  jmp     loc_14073DE16
0x14073d99e  lea     rcx, [rbp+DestinationString]
0x14073d9a2  call    AslPathCleanUstr
0x14073d9a7  mov     ebx, eax
0x14073d9a9  test    eax, eax
0x14073d9ab  jns     short loc_14073D9C3
0x14073d9ad  mov     dword ptr [rsp+80h+pszSrc], eax
0x14073d9b1  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x14073d9b8  mov     r8d, 8D1h
0x14073d9be  jmp     loc_14073DE05
0x14073d9c3  movzx   ecx, [rbp+DestinationString.Length]; usAugend
0x14073d9c7  lea     r8, [rbp+pusResult]; pusResult
0x14073d9cb  mov     r13d, 4
0x14073d9d1  mov     edx, r13d; usAddend
0x14073d9d4  call    RtlUShortAdd
0x14073d9d9  mov     ebx, eax
0x14073d9db  test    eax, eax
0x14073d9dd  jns     short loc_14073D9F5
0x14073d9df  mov     dword ptr [rsp+80h+pszSrc], eax
0x14073d9e3  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x14073d9ea  mov     r8d, 8D7h
0x14073d9f0  jmp     loc_14073DE05
0x14073d9f5  movzx   ebx, word ptr [rbp+pusResult]
0x14073d9f9  mov     edx, ebx
0x14073d9fb  call    AslAlloc
0x14073da00  mov     r14, rax
0x14073da03  test    rax, rax
0x14073da06  jnz     short loc_14073DA12
0x14073da08  mov     ebx, 0C0000017h
0x14073da0d  jmp     loc_14073DE16
0x14073da12  movzx   r9d, [rbp+DestinationString.Length]; cbToCopy
0x14073da17  mov     rdx, rbx; cbDest
0x14073da1a  mov     r8, [rbp+DestinationString.Buffer]; pszSrc
0x14073da1e  mov     rcx, r14; pszDest
0x14073da21  call    RtlStringCbCopyNW
0x14073da26  mov     ebx, eax
0x14073da28  test    eax, eax
0x14073da2a  jns     short loc_14073DA42
0x14073da2c  mov     dword ptr [rsp+80h+pszSrc], eax
0x14073da30  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x14073da37  mov     r8d, 8E3h
0x14073da3d  jmp     loc_14073DE05
0x14073da42  mov     rcx, r14; SourceString
0x14073da45  call    AslpPathWildcardMakeLeaves
0x14073da4a  test    eax, eax
0x14073da4c  jnz     short loc_14073DA65
0x14073da4e  mov     ebx, 0C0000039h
0x14073da53  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x14073da5a  mov     r8d, 8F5h
0x14073da60  jmp     loc_14073D988
0x14073da65  cmp     eax, 1
0x14073da68  jnz     short loc_14073DABD
0x14073da6a  mov     rcx, [rbp+DestinationString.Buffer]; SourceString
0x14073da6e  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x14073da76  call    AslDoesFileExistNtPath
0x14073da7b  test    eax, eax
0x14073da7d  jnz     short loc_14073DA89
0x14073da7f  mov     ebx, 80000006h
0x14073da84  jmp     loc_14073DE16
0x14073da89  mov     r8, rsi; pszSrc
0x14073da8c  mov     edx, 104h; cchDest
0x14073da91  mov     rcx, rdi; pszDest
0x14073da94  call    RtlStringCchCopyW
0x14073da99  mov     ebx, eax
0x14073da9b  test    eax, eax
0x14073da9d  jns     short loc_14073DAB5
0x14073da9f  mov     dword ptr [rsp+80h+pszSrc], eax
0x14073daa3  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x14073daaa  mov     r8d, 907h
0x14073dab0  jmp     loc_14073DE05
0x14073dab5  mov     ebx, r15d
0x14073dab8  jmp     loc_14073DE16
0x14073dabd  mov     edx, 40h ; '@'
0x14073dac2  call    AslAlloc
0x14073dac7  mov     [rbp+var_48], rax
0x14073dacb  mov     rdi, rax
0x14073dace  test    rax, rax
0x14073dad1  jz      loc_14073DA08
0x14073dad7  mov     r8d, r13d; MaxCount
0x14073dada  lea     rdx, asc_140023188; "\\??\\"
0x14073dae1  mov     rcx, rsi; Str1
0x14073dae4  call    wcsncmp
0x14073dae9  mov     ecx, r15d
0x14073daec  lea     r8, [rbp+pusResult]; pullResult
0x14073daf0  test    eax, eax
0x14073daf2  mov     r10d, 10h
0x14073daf8  setnz   cl
0x14073dafb  mov     [rdi], ecx
0x14073dafd  xor     ecx, ecx; ullMultiplicand
0x14073daff  mov     [rdi+8], r14
0x14073db03  lea     edx, [r10+10h]; ullMultiplier
0x14073db07  mov     [rdi+10h], r15
0x14073db0b  mov     r14, r15
0x14073db0e  mov     [rdi+30h], r10
0x14073db12  mov     [rdi+20h], r15
0x14073db16  mov     [rdi+28h], r15
0x14073db1a  mov     [rdi+38h], r15
0x14073db1e  mov     [rdi+18h], rdx
0x14073db22  mov     [rbp+pusResult], r15
0x14073db26  mov     [rbp+pullResult], r15
0x14073db2a  call    ULongLongMult
0x14073db2f  mov     r9d, 0C0000095h
0x14073db35  mov     r13d, 72615452h
0x14073db3b  test    eax, eax
0x14073db3d  jns     short loc_14073DB47
0x14073db3f  mov     ebx, r9d
0x14073db42  jmp     loc_14073DC2D
0x14073db47  mov     rdx, [rdi+18h]; ullMultiplier
0x14073db4b  lea     r8, [rbp+pullResult]; pullResult
0x14073db4f  mov     rcx, r10; ullMultiplicand
0x14073db52  call    ULongLongMult
0x14073db57  test    eax, eax
0x14073db59  js      short loc_14073DB3F
0x14073db5b  mov     rsi, [rbp+pullResult]
0x14073db5f  mov     r8d, r13d; Tag
0x14073db62  mov     r15, [rdi+38h]
0x14073db66  mov     rdx, rsi; NumberOfBytes
0x14073db69  mov     ecx, 1; PoolType
0x14073db6e  call    ExAllocatePoolWithTag
0x14073db73  mov     rbx, rax
0x14073db76  test    r15, r15
0x14073db79  jnz     short loc_14073DB93
0x14073db7b  test    rax, rax
0x14073db7e  jz      loc_14073DC28
0x14073db84  mov     r8, rsi; Size
0x14073db87  xor     edx, edx; Val
0x14073db89  mov     rcx, rax; void *
0x14073db8c  call    memset_0
0x14073db91  jmp     short loc_14073DBCE
0x14073db93  test    rax, rax
0x14073db96  jz      loc_14073DC25
0x14073db9c  mov     r8, rsi; Size
0x14073db9f  xor     edx, edx; Val
0x14073dba1  mov     rcx, rbx; void *
0x14073dba4  call    memset_0
0x14073dba9  cmp     [rbp+pusResult], rsi
0x14073dbad  mov     rdx, r15; Src
0x14073dbb0  mov     rcx, rbx; void *
0x14073dbb3  cmovb   rsi, [rbp+pusResult]
0x14073dbb8  mov     r8, rsi; Size
0x14073dbbb  call    memmove
0x14073dbc0  mov     edx, r13d; Tag
0x14073dbc3  mov     rcx, r15; P
0x14073dbc6  call    ExFreePoolWithTag
0x14073dbcb  xor     r15d, r15d
0x14073dbce  mov     [rdi+38h], rbx
0x14073dbd2  mov     qword ptr [rdi+28h], 10h
0x14073dbda  mov     rdx, [rdi+8]; SourceString
0x14073dbde  lea     rcx, [rbp+SourceString]; DestinationString
0x14073dbe2  call    RtlInitUnicodeString
0x14073dbe7  mov     r8, [rdi+8]
0x14073dbeb  lea     rdx, [rbp+SourceString]; SourceString
0x14073dbef  mov     r9d, 1
0x14073dbf5  mov     [rsp+80h+var_58], r15w; __int16
0x14073dbfb  lea     rcx, [rbp+var_20]; DestinationString
0x14073dbff  mov     [rsp+80h+pszSrc], r15; pszSrc
0x14073dc04  call    AslpPathWildcardAllocMatchNode
0x14073dc09  mov     ebx, eax
0x14073dc0b  test    eax, eax
0x14073dc0d  jns     short loc_14073DC85
0x14073dc0f  mov     dword ptr [rsp+80h+pszSrc], eax
0x14073dc13  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x14073dc1a  mov     r8d, 93Ah
0x14073dc20  jmp     loc_14073DE05
0x14073dc25  xor     r15d, r15d
0x14073dc28  mov     ebx, 0C0000017h
0x14073dc2d  mov     rcx, [rdi+38h]; P
0x14073dc31  test    rcx, rcx
0x14073dc34  jz      short loc_14073DC3E
0x14073dc36  mov     edx, r13d; Tag
0x14073dc39  call    ExFreePoolWithTag
0x14073dc3e  xorps   xmm0, xmm0
0x14073dc41  movups  xmmword ptr [rdi+10h], xmm0
0x14073dc45  movups  xmmword ptr [rdi+20h], xmm0
0x14073dc49  movups  xmmword ptr [rdi+30h], xmm0
0x14073dc4d  test    ebx, ebx
0x14073dc4f  jns     short loc_14073DBDA
0x14073dc51  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x14073dc58  mov     dword ptr [rsp+80h+pszSrc], ebx
0x14073dc5c  mov     r8d, 864h
0x14073dc62  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x14073dc69  mov     ecx, 1
0x14073dc6e  call    AslLogCallPrintf
0x14073dc73  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x14073dc7a  mov     r8d, 92Dh
0x14073dc80  jmp     loc_14073DE01
0x14073dc85  mov     r13, [rdi+20h]
0x14073dc89  mov     r9, [rdi+28h]
0x14073dc8d  cmp     r13, r9
0x14073dc90  jb      loc_14073DD87
0x14073dc96  lea     rcx, [r13+1]
0x14073dc9a  cmp     rcx, r9
0x14073dc9d  ja      short loc_14073DCA9
0x14073dc9f  mov     ebx, 0C000000Dh
0x14073dca4  jmp     loc_14073DDE9
0x14073dca9  mov     rsi, [rdi+30h]
0x14073dcad  dec     rsi
0x14073dcb0  lea     r10, [rsi+rcx]
0x14073dcb4  cmp     r10, rcx
0x14073dcb7  jnb     short loc_14073DCC3
0x14073dcb9  mov     ebx, 0C0000095h
0x14073dcbe  jmp     loc_14073DDE9
0x14073dcc3  mov     rdx, [rdi+18h]; ullMultiplier
0x14073dcc7  lea     r8, [rbp+pusResult]; pullResult
0x14073dccb  mov     rcx, r9; ullMultiplicand
0x14073dcce  mov     [rbp+pusResult], r15
0x14073dcd2  mov     [rbp+pullResult], r15
0x14073dcd6  call    ULongLongMult
0x14073dcdb  test    eax, eax
0x14073dcdd  js      short loc_14073DCB9
0x14073dcdf  mov     rdx, [rdi+18h]; ullMultiplier
0x14073dce3  lea     r8, [rbp+pullResult]; pullResult
0x14073dce7  not     rsi
0x14073dcea  and     rsi, r10
0x14073dced  mov     rcx, rsi; ullMultiplicand
0x14073dcf0  call    ULongLongMult
0x14073dcf5  test    eax, eax
0x14073dcf7  js      short loc_14073DCB9
0x14073dcf9  mov     rax, [rdi+38h]
0x14073dcfd  mov     r8d, 72615452h; Tag
0x14073dd03  mov     r15, [rbp+pullResult]
0x14073dd07  mov     ecx, 1; PoolType
0x14073dd0c  mov     [rbp+pullResult], rax
0x14073dd10  mov     rdx, r15; NumberOfBytes
0x14073dd13  test    rax, rax
0x14073dd16  jnz     short loc_14073DD38
0x14073dd18  call    ExAllocatePoolWithTag
0x14073dd1d  mov     rbx, rax
0x14073dd20  test    rax, rax
0x14073dd23  jz      loc_14073DDE1
0x14073dd29  mov     r8, r15; Size
0x14073dd2c  xor     edx, edx; Val
0x14073dd2e  mov     rcx, rax; void *
0x14073dd31  call    memset_0
0x14073dd36  jmp     short loc_14073DD7C
0x14073dd38  call    ExAllocatePoolWithTag
0x14073dd3d  mov     rbx, rax
0x14073dd40  test    rax, rax
0x14073dd43  jz      loc_14073DDE1
0x14073dd49  mov     r8, r15; Size
0x14073dd4c  xor     edx, edx; Val
0x14073dd4e  mov     rcx, rax; void *
0x14073dd51  call    memset_0
0x14073dd56  cmp     [rbp+pusResult], r15
0x14073dd5a  mov     rcx, rbx; void *
0x14073dd5d  mov     rdx, [rbp+pullResult]; Src
0x14073dd61  cmovb   r15, [rbp+pusResult]
0x14073dd66  mov     r8, r15; Size
0x14073dd69  call    memmove
0x14073dd6e  mov     rcx, [rbp+pullResult]; P
  ... truncated ...
```
