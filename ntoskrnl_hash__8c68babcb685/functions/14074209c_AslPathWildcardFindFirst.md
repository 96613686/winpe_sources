# AslPathWildcardFindFirst

- ea: `0x14074209c`
- end: `0x14074262b`
- name: `AslPathWildcardFindFirst`
- size: `1423`
- prototype: `__int64 __fastcall(NTSTRSAFE_PWSTR pszDest, ULONGLONG, const wchar_t *, _QWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path`

## callers

- `0x14073a320`

## callees

- `0x140403380`
- `0x140438468`
- `0x14043a410`
- `0x140456670`
- `0x14045a2fc`
- `0x1405461f0`
- `0x1406f6f80`
- `0x1406f7380`
- `0x14074209c`
- `0x1407431f8`
- `0x140743950`
- `0x140827d64`
- `0x140828d48`
- `0x140829754`
- `0x140829974`
- `0x140829a4c`
- `0x1408bf658`
- `0x1408c14bc`
- `0x1408c2f88`
- `0x14094b120`
- `0x1409bb9d0`
- `0x140bb1320`
- `0x140bb19f0`

## string_xrefs

- `0x1407425b4`: `AslpPathWildcardPushNode failed [%x]`
- `0x140742148`: `AslPathWildcardFindFirst`
- `0x1407425c5`: `AslPathWildcardFindFirst`
- `0x14074213b`: `RtlCreateUnicodeString failed`
- `0x140742422`: `AslpPathWildcardInitStack`
- `0x140742433`: `AslpPathWildcardInitStack failed [%x]`
- `0x1407423d3`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`
- `0x1407421f0`: `RtlStringCbCopyNW failed [%x]`
- `0x140742263`: `RtlStringCbCopyNW failed [%x]`
- `0x140742213`: `Failed to split the wildcard path`
- `0x140742171`: `AslPathCleanUstr failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindFirst(NTSTRSAFE_PWSTR pszDest, ULONGLONG a2, const wchar_t *a3, _QWORD *a4)
{
  const WCHAR *v8; // r14
  NTSTATUS matched; // ebx
  const char *v10; // r9
  int v11; // r8d
  const char *v12; // r9
  int v13; // r8d
  __int64 v14; // rcx
  size_t v15; // rbx
  wchar_t *v16; // rax
  int Leaves; // eax
  __int64 v18; // rcx
  wchar_t *Buffer; // rcx
  _DWORD *v20; // rdi
  HRESULT v21; // eax
  ULONGLONG v22; // r10
  int v23; // r9d
  size_t v24; // rsi
  void *v25; // r15
  PVOID PoolWithTag; // rax
  void *v27; // rbx
  void *v28; // rcx
  ULONGLONG v29; // r13
  unsigned __int64 v30; // r9
  __int64 v31; // rsi
  ULONGLONG v32; // rdx
  ULONGLONG v33; // rcx
  __int64 v34; // r10
  ULONGLONG v35; // rsi
  SIZE_T v36; // r15
  PVOID v37; // rax
  void *v38; // rbx
  PVOID v39; // rax
  ULONGLONG v40; // rcx
  ULONGLONG v41; // rcx
  ULONGLONG v42; // rdx
  __int64 v43; // rcx
  ULONGLONG pullResult; // [rsp+30h] [rbp-50h] BYREF
  _DWORD *v45; // [rsp+38h] [rbp-48h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-30h] BYREF
  UNICODE_STRING v48; // [rsp+60h] [rbp-20h] BYREF
  __int128 v49; // [rsp+70h] [rbp-10h]
  ULONGLONG pusResult; // [rsp+C8h] [rbp+48h] BYREF

  pusResult = a2;
  if ( !pszDest )
    return 3221225711LL;
  if ( !a3 || !*a3 )
    return 3221225713LL;
  if ( !a4 )
    return 3221225714LL;
  *pszDest = 0;
  v45 = 0;
  LOWORD(pusResult) = 0;
  *a4 = 0;
  DestinationString = 0;
  v8 = 0;
  SourceString = 0;
  v48 = 0;
  v49 = 0;
  if ( RtlCreateUnicodeString(&DestinationString, a3) )
  {
    matched = AslPathCleanUstr(&DestinationString);
    if ( matched < 0 )
    {
      v12 = "AslPathCleanUstr failed [%x]";
      v13 = 2257;
      goto LABEL_66;
    }
    matched = RtlUShortAdd(DestinationString.Length, 4u, (USHORT *)&pusResult);
    if ( matched < 0 )
    {
      v12 = "RtlUShortAdd failed [%x]";
      v13 = 2263;
      goto LABEL_66;
    }
    v15 = (unsigned __int16)pusResult;
    v16 = (wchar_t *)AslAlloc(v14, (unsigned __int16)pusResult);
    v8 = v16;
    if ( !v16 )
      goto LABEL_15;
    matched = RtlStringCbCopyNW(v16, v15, DestinationString.Buffer, DestinationString.Length);
    if ( matched < 0 )
    {
      v12 = "RtlStringCbCopyNW failed [%x]";
      v13 = 2275;
      goto LABEL_66;
    }
    Leaves = AslpPathWildcardMakeLeaves(v8);
    if ( !Leaves )
    {
      matched = -1073741767;
      v10 = "Failed to split the wildcard path";
      v11 = 2293;
      goto LABEL_9;
    }
    if ( Leaves == 1 )
    {
      Buffer = DestinationString.Buffer;
      *a4 = -1;
      if ( !(unsigned int)AslDoesFileExistNtPath(Buffer) )
      {
        matched = -2147483642;
        goto LABEL_67;
      }
      matched = RtlStringCchCopyW(pszDest, 0x104u, a3);
      if ( matched >= 0 )
      {
        matched = 0;
        goto LABEL_67;
      }
      v12 = "RtlStringCbCopyNW failed [%x]";
      v13 = 2311;
LABEL_66:
      AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindFirst", v13, (_DWORD)v12);
      goto LABEL_67;
    }
    v45 = (_DWORD *)AslAlloc(v18, 64);
    v20 = v45;
    if ( !v45 )
    {
LABEL_15:
      matched = -1073741801;
      goto LABEL_67;
    }
    *v45 = wcsncmp(a3, L"\\??\\", 4u) != 0;
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
      matched = v23;
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
          goto LABEL_37;
        }
      }
      else if ( PoolWithTag )
      {
        memset_0(PoolWithTag, 0, v24);
LABEL_37:
        *((_QWORD *)v20 + 7) = v27;
        *((_QWORD *)v20 + 5) = 16;
        goto LABEL_38;
      }
      matched = -1073741801;
    }
    v28 = (void *)*((_QWORD *)v20 + 7);
    if ( v28 )
      ExFreePoolWithTag(v28, 0x72615452u);
    *((_OWORD *)v20 + 1) = 0;
    *((_OWORD *)v20 + 2) = 0;
    *((_OWORD *)v20 + 3) = 0;
    if ( matched < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslpPathWildcardInitStack",
        2148,
        (unsigned int)"RtlArrayInitialize failed [%x]");
      v12 = "AslpPathWildcardInitStack failed [%x]";
      v13 = 2349;
      goto LABEL_66;
    }
LABEL_38:
    RtlInitUnicodeString(&SourceString, *((PCWSTR *)v20 + 1));
    matched = AslpPathWildcardAllocMatchNode(&v48, &SourceString, 0, 0);
    if ( matched < 0 )
    {
      v12 = "AslpPathWildcardAllocMatchNode failed to create root of path [%x]";
      v13 = 2362;
      goto LABEL_66;
    }
    v29 = *((_QWORD *)v20 + 4);
    v30 = *((_QWORD *)v20 + 5);
    if ( v29 < v30 )
      goto LABEL_60;
    if ( v29 + 1 <= v30 )
    {
      matched = -1073741811;
LABEL_65:
      v12 = "AslpPathWildcardPushNode failed [%x]";
      v13 = 2368;
      goto LABEL_66;
    }
    v31 = *((_QWORD *)v20 + 6) - 1LL;
    if ( *((_QWORD *)v20 + 6) + v29 < v29 + 1
      || (v32 = *((_QWORD *)v20 + 3),
          v33 = *((_QWORD *)v20 + 5),
          pusResult = 0,
          pullResult = 0,
          ULongLongMult(v33, v32, &pusResult) < 0)
      || (v35 = v34 & ~v31, ULongLongMult(v35, *((_QWORD *)v20 + 3), &pullResult) < 0) )
    {
      matched = -1073741675;
      goto LABEL_65;
    }
    v36 = pullResult;
    pullResult = *((_QWORD *)v20 + 7);
    if ( pullResult )
    {
      v39 = ExAllocatePoolWithTag(PagedPool, v36, 0x72615452u);
      v38 = v39;
      if ( v39 )
      {
        memset_0(v39, 0, v36);
        if ( pusResult < v36 )
          v36 = pusResult;
        memmove(v38, (const void *)pullResult, v36);
        ExFreePoolWithTag((PVOID)pullResult, 0x72615452u);
        goto LABEL_59;
      }
    }
    else
    {
      v37 = ExAllocatePoolWithTag(PagedPool, v36, 0x72615452u);
      v38 = v37;
      if ( v37 )
      {
        memset_0(v37, 0, v36);
LABEL_59:
        *((_QWORD *)v20 + 7) = v38;
        *((_QWORD *)v20 + 5) = v35;
LABEL_60:
        v40 = *((_QWORD *)v20 + 3);
        pusResult = 0;
        if ( ULongLongMult(v40, v29, &pusResult) >= 0 )
        {
          v41 = *((_QWORD *)v20 + 7);
          v42 = v41 + pusResult;
          if ( v41 + pusResult >= v41 )
          {
            *(UNICODE_STRING *)v42 = v48;
            *(_OWORD *)(v42 + 16) = v49;
            ++*((_QWORD *)v20 + 4);
            *a4 = v20;
            v48 = 0;
            v49 = 0;
            matched = AslPathWildcardFindNext(pszDest, v42, v20);
            goto LABEL_67;
          }
        }
        matched = -1073741675;
        goto LABEL_65;
      }
    }
    matched = -1073741801;
    goto LABEL_65;
  }
  matched = -1073741801;
  v10 = "RtlCreateUnicodeString failed";
  v11 = 2236;
LABEL_9:
  AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindFirst", v11, (_DWORD)v10);
LABEL_67:
  RtlFreeAnsiString(&DestinationString);
  if ( v8 )
    AslFree(v43, v8);
  if ( matched < 0 )
  {
    AslpPathWildcardFreeFindContext(&v45);
    AslpPathWildcardFreeMatchNode(&v48);
    *a4 = 0;
  }
  return (unsigned int)matched;
}

```

## disassembly

```asm
0x14074209c  mov     [rsp-38h+arg_10], rbx
0x1407420a1  mov     [rsp-38h+pusResult], rdx
0x1407420a6  mov     [rsp-38h+arg_0], rcx
0x1407420ab  push    rbp
0x1407420ac  push    rsi
0x1407420ad  push    rdi
0x1407420ae  push    r12
0x1407420b0  push    r13
0x1407420b2  push    r14
0x1407420b4  push    r15
0x1407420b6  mov     rbp, rsp
0x1407420b9  sub     rsp, 80h
0x1407420c0  xor     r15d, r15d
0x1407420c3  mov     r12, r9
0x1407420c6  mov     rsi, r8
0x1407420c9  mov     rdi, rcx
0x1407420cc  test    rcx, rcx
0x1407420cf  jnz     short loc_1407420DB
0x1407420d1  mov     eax, 0C00000EFh
0x1407420d6  jmp     loc_14074260F
0x1407420db  test    rsi, rsi
0x1407420de  jz      loc_14074260A
0x1407420e4  cmp     [r8], r15w
0x1407420e8  jz      loc_14074260A
0x1407420ee  test    r12, r12
0x1407420f1  jnz     short loc_1407420FD
0x1407420f3  mov     eax, 0C00000F2h
0x1407420f8  jmp     loc_14074260F
0x1407420fd  xorps   xmm0, xmm0
0x140742100  mov     [rcx], r15w
0x140742104  xorps   xmm1, xmm1
0x140742107  mov     [rbp+var_48], r15
0x14074210b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14074210f  mov     word ptr [rbp+pusResult], r15w
0x140742114  mov     rdx, rsi; SourceString
0x140742117  mov     [r9], r15
0x14074211a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14074211e  mov     r14, r15
0x140742121  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x140742125  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x140742129  movups  [rbp+var_10], xmm1
0x14074212d  call    RtlCreateUnicodeString
0x140742132  test    al, al
0x140742134  jnz     short loc_14074215E
0x140742136  mov     ebx, 0C0000017h
0x14074213b  lea     r9, aRtlcreateunico_0; "RtlCreateUnicodeString failed"
0x140742142  mov     r8d, 8BCh
0x140742148  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x14074214f  mov     ecx, 1
0x140742154  call    AslLogCallPrintf
0x140742159  jmp     loc_1407425D6
0x14074215e  lea     rcx, [rbp+DestinationString]
0x140742162  call    AslPathCleanUstr
0x140742167  mov     ebx, eax
0x140742169  test    eax, eax
0x14074216b  jns     short loc_140742183
0x14074216d  mov     dword ptr [rsp+80h+pszSrc], eax
0x140742171  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x140742178  mov     r8d, 8D1h
0x14074217e  jmp     loc_1407425C5
0x140742183  movzx   ecx, [rbp+DestinationString.Length]; usAugend
0x140742187  lea     r8, [rbp+pusResult]; pusResult
0x14074218b  mov     r13d, 4
0x140742191  mov     edx, r13d; usAddend
0x140742194  call    RtlUShortAdd
0x140742199  mov     ebx, eax
0x14074219b  test    eax, eax
0x14074219d  jns     short loc_1407421B5
0x14074219f  mov     dword ptr [rsp+80h+pszSrc], eax
0x1407421a3  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x1407421aa  mov     r8d, 8D7h
0x1407421b0  jmp     loc_1407425C5
0x1407421b5  movzx   ebx, word ptr [rbp+pusResult]
0x1407421b9  mov     edx, ebx
0x1407421bb  call    AslAlloc
0x1407421c0  mov     r14, rax
0x1407421c3  test    rax, rax
0x1407421c6  jnz     short loc_1407421D2
0x1407421c8  mov     ebx, 0C0000017h
0x1407421cd  jmp     loc_1407425D6
0x1407421d2  movzx   r9d, [rbp+DestinationString.Length]; cbToCopy
0x1407421d7  mov     rdx, rbx; cbDest
0x1407421da  mov     r8, [rbp+DestinationString.Buffer]; pszSrc
0x1407421de  mov     rcx, r14; pszDest
0x1407421e1  call    RtlStringCbCopyNW
0x1407421e6  mov     ebx, eax
0x1407421e8  test    eax, eax
0x1407421ea  jns     short loc_140742202
0x1407421ec  mov     dword ptr [rsp+80h+pszSrc], eax
0x1407421f0  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x1407421f7  mov     r8d, 8E3h
0x1407421fd  jmp     loc_1407425C5
0x140742202  mov     rcx, r14; SourceString
0x140742205  call    AslpPathWildcardMakeLeaves
0x14074220a  test    eax, eax
0x14074220c  jnz     short loc_140742225
0x14074220e  mov     ebx, 0C0000039h
0x140742213  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x14074221a  mov     r8d, 8F5h
0x140742220  jmp     loc_140742148
0x140742225  cmp     eax, 1
0x140742228  jnz     short loc_14074227D
0x14074222a  mov     rcx, [rbp+DestinationString.Buffer]; SourceString
0x14074222e  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x140742236  call    AslDoesFileExistNtPath
0x14074223b  test    eax, eax
0x14074223d  jnz     short loc_140742249
0x14074223f  mov     ebx, 80000006h
0x140742244  jmp     loc_1407425D6
0x140742249  mov     r8, rsi; pszSrc
0x14074224c  mov     edx, 104h; cchDest
0x140742251  mov     rcx, rdi; pszDest
0x140742254  call    RtlStringCchCopyW
0x140742259  mov     ebx, eax
0x14074225b  test    eax, eax
0x14074225d  jns     short loc_140742275
0x14074225f  mov     dword ptr [rsp+80h+pszSrc], eax
0x140742263  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x14074226a  mov     r8d, 907h
0x140742270  jmp     loc_1407425C5
0x140742275  mov     ebx, r15d
0x140742278  jmp     loc_1407425D6
0x14074227d  mov     edx, 40h ; '@'
0x140742282  call    AslAlloc
0x140742287  mov     [rbp+var_48], rax
0x14074228b  mov     rdi, rax
0x14074228e  test    rax, rax
0x140742291  jz      loc_1407421C8
0x140742297  mov     r8d, r13d; MaxCount
0x14074229a  lea     rdx, asc_140023150; "\\??\\"
0x1407422a1  mov     rcx, rsi; Str1
0x1407422a4  call    wcsncmp
0x1407422a9  mov     ecx, r15d
0x1407422ac  lea     r8, [rbp+pusResult]; pullResult
0x1407422b0  test    eax, eax
0x1407422b2  mov     r10d, 10h
0x1407422b8  setnz   cl
0x1407422bb  mov     [rdi], ecx
0x1407422bd  xor     ecx, ecx; ullMultiplicand
0x1407422bf  mov     [rdi+8], r14
0x1407422c3  lea     edx, [r10+10h]; ullMultiplier
0x1407422c7  mov     [rdi+10h], r15
0x1407422cb  mov     r14, r15
0x1407422ce  mov     [rdi+30h], r10
0x1407422d2  mov     [rdi+20h], r15
0x1407422d6  mov     [rdi+28h], r15
0x1407422da  mov     [rdi+38h], r15
0x1407422de  mov     [rdi+18h], rdx
0x1407422e2  mov     [rbp+pusResult], r15
0x1407422e6  mov     [rbp+pullResult], r15
0x1407422ea  call    ULongLongMult
0x1407422ef  mov     r9d, 0C0000095h
0x1407422f5  mov     r13d, 72615452h
0x1407422fb  test    eax, eax
0x1407422fd  jns     short loc_140742307
0x1407422ff  mov     ebx, r9d
0x140742302  jmp     loc_1407423ED
0x140742307  mov     rdx, [rdi+18h]; ullMultiplier
0x14074230b  lea     r8, [rbp+pullResult]; pullResult
0x14074230f  mov     rcx, r10; ullMultiplicand
0x140742312  call    ULongLongMult
0x140742317  test    eax, eax
0x140742319  js      short loc_1407422FF
0x14074231b  mov     rsi, [rbp+pullResult]
0x14074231f  mov     r8d, r13d; Tag
0x140742322  mov     r15, [rdi+38h]
0x140742326  mov     rdx, rsi; NumberOfBytes
0x140742329  mov     ecx, 1; PoolType
0x14074232e  call    ExAllocatePoolWithTag
0x140742333  mov     rbx, rax
0x140742336  test    r15, r15
0x140742339  jnz     short loc_140742353
0x14074233b  test    rax, rax
0x14074233e  jz      loc_1407423E8
0x140742344  mov     r8, rsi; Size
0x140742347  xor     edx, edx; Val
0x140742349  mov     rcx, rax; void *
0x14074234c  call    memset_0
0x140742351  jmp     short loc_14074238E
0x140742353  test    rax, rax
0x140742356  jz      loc_1407423E5
0x14074235c  mov     r8, rsi; Size
0x14074235f  xor     edx, edx; Val
0x140742361  mov     rcx, rbx; void *
0x140742364  call    memset_0
0x140742369  cmp     [rbp+pusResult], rsi
0x14074236d  mov     rdx, r15; Src
0x140742370  mov     rcx, rbx; void *
0x140742373  cmovb   rsi, [rbp+pusResult]
0x140742378  mov     r8, rsi; Size
0x14074237b  call    memmove
0x140742380  mov     edx, r13d; Tag
0x140742383  mov     rcx, r15; P
0x140742386  call    ExFreePoolWithTag
0x14074238b  xor     r15d, r15d
0x14074238e  mov     [rdi+38h], rbx
0x140742392  mov     qword ptr [rdi+28h], 10h
0x14074239a  mov     rdx, [rdi+8]; SourceString
0x14074239e  lea     rcx, [rbp+SourceString]; DestinationString
0x1407423a2  call    RtlInitUnicodeString
0x1407423a7  mov     r8, [rdi+8]
0x1407423ab  lea     rdx, [rbp+SourceString]; SourceString
0x1407423af  mov     r9d, 1
0x1407423b5  mov     [rsp+80h+var_58], r15w; __int16
0x1407423bb  lea     rcx, [rbp+var_20]; DestinationString
0x1407423bf  mov     [rsp+80h+pszSrc], r15; pszSrc
0x1407423c4  call    AslpPathWildcardAllocMatchNode
0x1407423c9  mov     ebx, eax
0x1407423cb  test    eax, eax
0x1407423cd  jns     short loc_140742445
0x1407423cf  mov     dword ptr [rsp+80h+pszSrc], eax
0x1407423d3  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x1407423da  mov     r8d, 93Ah
0x1407423e0  jmp     loc_1407425C5
0x1407423e5  xor     r15d, r15d
0x1407423e8  mov     ebx, 0C0000017h
0x1407423ed  mov     rcx, [rdi+38h]; P
0x1407423f1  test    rcx, rcx
0x1407423f4  jz      short loc_1407423FE
0x1407423f6  mov     edx, r13d; Tag
0x1407423f9  call    ExFreePoolWithTag
0x1407423fe  xorps   xmm0, xmm0
0x140742401  movups  xmmword ptr [rdi+10h], xmm0
0x140742405  movups  xmmword ptr [rdi+20h], xmm0
0x140742409  movups  xmmword ptr [rdi+30h], xmm0
0x14074240d  test    ebx, ebx
0x14074240f  jns     short loc_14074239A
0x140742411  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x140742418  mov     dword ptr [rsp+80h+pszSrc], ebx
0x14074241c  mov     r8d, 864h
0x140742422  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x140742429  mov     ecx, 1
0x14074242e  call    AslLogCallPrintf
0x140742433  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x14074243a  mov     r8d, 92Dh
0x140742440  jmp     loc_1407425C1
0x140742445  mov     r13, [rdi+20h]
0x140742449  mov     r9, [rdi+28h]
0x14074244d  cmp     r13, r9
0x140742450  jb      loc_140742547
0x140742456  lea     rcx, [r13+1]
0x14074245a  cmp     rcx, r9
0x14074245d  ja      short loc_140742469
0x14074245f  mov     ebx, 0C000000Dh
0x140742464  jmp     loc_1407425A9
0x140742469  mov     rsi, [rdi+30h]
0x14074246d  dec     rsi
0x140742470  lea     r10, [rsi+rcx]
0x140742474  cmp     r10, rcx
0x140742477  jnb     short loc_140742483
0x140742479  mov     ebx, 0C0000095h
0x14074247e  jmp     loc_1407425A9
0x140742483  mov     rdx, [rdi+18h]; ullMultiplier
0x140742487  lea     r8, [rbp+pusResult]; pullResult
0x14074248b  mov     rcx, r9; ullMultiplicand
0x14074248e  mov     [rbp+pusResult], r15
0x140742492  mov     [rbp+pullResult], r15
0x140742496  call    ULongLongMult
0x14074249b  test    eax, eax
0x14074249d  js      short loc_140742479
0x14074249f  mov     rdx, [rdi+18h]; ullMultiplier
0x1407424a3  lea     r8, [rbp+pullResult]; pullResult
0x1407424a7  not     rsi
0x1407424aa  and     rsi, r10
0x1407424ad  mov     rcx, rsi; ullMultiplicand
0x1407424b0  call    ULongLongMult
0x1407424b5  test    eax, eax
0x1407424b7  js      short loc_140742479
0x1407424b9  mov     rax, [rdi+38h]
0x1407424bd  mov     r8d, 72615452h; Tag
0x1407424c3  mov     r15, [rbp+pullResult]
0x1407424c7  mov     ecx, 1; PoolType
0x1407424cc  mov     [rbp+pullResult], rax
0x1407424d0  mov     rdx, r15; NumberOfBytes
0x1407424d3  test    rax, rax
0x1407424d6  jnz     short loc_1407424F8
0x1407424d8  call    ExAllocatePoolWithTag
0x1407424dd  mov     rbx, rax
0x1407424e0  test    rax, rax
0x1407424e3  jz      loc_1407425A1
0x1407424e9  mov     r8, r15; Size
0x1407424ec  xor     edx, edx; Val
0x1407424ee  mov     rcx, rax; void *
0x1407424f1  call    memset_0
0x1407424f6  jmp     short loc_14074253C
0x1407424f8  call    ExAllocatePoolWithTag
0x1407424fd  mov     rbx, rax
0x140742500  test    rax, rax
0x140742503  jz      loc_1407425A1
0x140742509  mov     r8, r15; Size
0x14074250c  xor     edx, edx; Val
0x14074250e  mov     rcx, rax; void *
0x140742511  call    memset_0
0x140742516  cmp     [rbp+pusResult], r15
0x14074251a  mov     rcx, rbx; void *
0x14074251d  mov     rdx, [rbp+pullResult]; Src
0x140742521  cmovb   r15, [rbp+pusResult]
0x140742526  mov     r8, r15; Size
0x140742529  call    memmove
0x14074252e  mov     rcx, [rbp+pullResult]; P
  ... truncated ...
```
