# AslPathWildcardFindFirst

- ea: `0x1800be468`
- end: `0x1800be9c8`
- name: `AslPathWildcardFindFirst`
- size: `1376`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800a9c60`

## callees

- `0x180041774`
- `0x18004281c`
- `0x180042e38`
- `0x180076f20`
- `0x1800ab19c`
- `0x1800bdfe0`
- `0x1800be468`
- `0x1800be9d0`
- `0x1800bf7f8`
- `0x1800bfa84`
- `0x1800bfb78`
- `0x1800bfbd4`
- `0x1800bfee4`
- `0x1800bff54`
- `0x1800c0334`
- `0x1800c58e0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800be7cf`
- `ntdll!RtlInitUnicodeString` at `0x1800be7cf`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800be4ff`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800be4ff`
- `ntdll!RtlAllocateHeap` at `0x1800be58f`
- `ntdll!RtlAllocateHeap` at `0x1800be676`
- `ntdll!RtlAllocateHeap` at `0x1800be72c`
- `ntdll!RtlAllocateHeap` at `0x1800be898`
- `ntdll!RtlAllocateHeap` at `0x1800be58f`
- `ntdll!RtlAllocateHeap` at `0x1800be676`
- `ntdll!RtlAllocateHeap` at `0x1800be72c`
- `ntdll!RtlAllocateHeap` at `0x1800be898`
- `ntdll!RtlReAllocateHeap` at `0x1800be74c`
- `ntdll!RtlReAllocateHeap` at `0x1800be8b8`
- `ntdll!RtlReAllocateHeap` at `0x1800be74c`
- `ntdll!RtlReAllocateHeap` at `0x1800be8b8`
- `ntdll!RtlFreeHeap` at `0x1800be76e`
- `ntdll!RtlFreeHeap` at `0x1800be76e`
- `ntdll!RtlFreeUnicodeString` at `0x1800be96a`
- `ntdll!RtlFreeUnicodeString` at `0x1800be96a`

## string_xrefs

- `0x1800be5f0`: `AslPathWildcardFindFirst`
- `0x1800be955`: `AslPathWildcardFindFirst`
- `0x1800be534`: `AslPathCleanUstr failed [%x]`
- `0x1800be798`: `AslpPathWildcardInitStack`
- `0x1800be50f`: `Failed to convert dos path to nt path [%x]`
- `0x1800be5e3`: `Failed to split the wildcard path`
- `0x1800be7a9`: `AslpPathWildcardInitStack failed [%x]`
- `0x1800be5c5`: `RtlStringCbCopyNW failed [%x]`
- `0x1800be647`: `RtlStringCbCopyNW failed [%x]`
- `0x1800be801`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`
- `0x1800be944`: `AslpPathWildcardPushNode failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindFirst(_WORD *a1, ULONGLONG a2, const wchar_t *a3, __int64 *a4)
{
  __int64 v6; // r13
  const WCHAR *v8; // r14
  int v9; // eax
  int Next; // ebx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  const WCHAR *Heap; // rax
  int v15; // eax
  int Leaves; // eax
  WCHAR *Buffer; // rcx
  int v18; // eax
  __int64 v19; // rdi
  int v20; // eax
  HRESULT v21; // eax
  ULONGLONG v22; // r10
  int v23; // r9d
  void *v24; // r8
  size_t v25; // rsi
  void *v26; // rcx
  PVOID v27; // rax
  PVOID v28; // rbx
  void *v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  int matched; // eax
  ULONGLONG v33; // r15
  __int64 v34; // rbx
  ULONGLONG v35; // rdx
  ULONGLONG v36; // rcx
  __int64 v37; // r9
  ULONGLONG v38; // rbx
  void *v39; // r8
  size_t v40; // r13
  void *v41; // rcx
  PVOID v42; // rax
  PVOID v43; // rsi
  ULONGLONG v44; // rcx
  _OWORD *v45; // rdx
  __int64 v46; // [rsp+20h] [rbp-60h]
  _DWORD *v47; // [rsp+30h] [rbp-50h] BYREF
  ULONGLONG pullResult; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  __int128 v51; // [rsp+60h] [rbp-20h] BYREF
  __int128 v52; // [rsp+70h] [rbp-10h]
  ULONGLONG Size; // [rsp+C8h] [rbp+48h] BYREF

  Size = a2;
  v6 = (__int64)a1;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 || !*a3 )
    return 3221225713LL;
  if ( !a4 )
    return 3221225714LL;
  *a4 = 0;
  *a1 = 0;
  v47 = 0;
  LOWORD(Size) = 0;
  UnicodeString = 0;
  v8 = 0;
  DestinationString = 0;
  v51 = 0;
  v52 = 0;
  v9 = RtlDosPathNameToNtPathName_U_WithStatus(a3, &UnicodeString, 0, 0);
  Next = v9;
  if ( v9 >= 0 )
  {
    v11 = AslPathCleanUstr(&UnicodeString);
    Next = v11;
    if ( v11 < 0 )
    {
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2257, "AslPathCleanUstr failed [%x]", v11);
      goto LABEL_62;
    }
    v12 = RtlUShortAdd(UnicodeString.Length, 4, &Size);
    Next = v12;
    if ( v12 < 0 )
    {
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2263, "RtlUShortAdd failed [%x]", v12);
      goto LABEL_62;
    }
    v13 = (unsigned __int16)Size;
    Heap = (const WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)Size);
    v8 = Heap;
    if ( !Heap )
      goto LABEL_14;
    v15 = RtlStringCbCopyNW(Heap, v13, UnicodeString.Buffer, UnicodeString.Length);
    Next = v15;
    if ( v15 < 0 )
    {
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2275, "RtlStringCbCopyNW failed [%x]", v15);
      goto LABEL_62;
    }
    Leaves = AslpPathWildcardMakeLeaves(v8);
    if ( !Leaves )
    {
      Next = -1073741767;
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2293, "Failed to split the wildcard path");
      goto LABEL_62;
    }
    if ( Leaves == 1 )
    {
      Buffer = UnicodeString.Buffer;
      *a4 = -1;
      if ( (unsigned int)AslDoesFileExistNtPath(Buffer) )
      {
        v18 = RtlStringCchCopyW(v6, 260, a3);
        Next = v18;
        if ( v18 >= 0 )
          Next = 0;
        else
          AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2311, "RtlStringCbCopyNW failed [%x]", v18);
      }
      else
      {
        Next = -2147483642;
      }
      goto LABEL_62;
    }
    v47 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
    v19 = (__int64)v47;
    if ( !v47 )
    {
LABEL_14:
      Next = -1073741801;
      goto LABEL_62;
    }
    v20 = wcsncmp_0(a3, L"\\??\\", 4u);
    Size = 0;
    *v47 = v20 != 0;
    *(_QWORD *)(v19 + 8) = v8;
    v8 = 0;
    *(_OWORD *)(v19 + 16) = 0;
    *(_OWORD *)(v19 + 32) = 0;
    *(_OWORD *)(v19 + 48) = 0;
    *(_QWORD *)(v19 + 16) = NtCurrentPeb()->ProcessHeap;
    *(_QWORD *)(v19 + 48) = 16;
    *(_QWORD *)(v19 + 24) = 32;
    v21 = ULongLongMult(0, 0x20u, &pullResult);
    v23 = -1073741675;
    if ( v21 < 0 || ULongLongMult(v22, *(_QWORD *)(v19 + 24), &Size) < 0 )
    {
      Next = v23;
    }
    else
    {
      v24 = *(void **)(v19 + 56);
      v25 = Size;
      v26 = *(void **)(v19 + 16);
      if ( v24 )
      {
        v28 = RtlReAllocateHeap(v26, 0, v24, Size);
      }
      else
      {
        v27 = RtlAllocateHeap(v26, 0, Size);
        v28 = v27;
        if ( v27 )
          memset_0(v27, 0, v25);
      }
      if ( v28 )
      {
        *(_QWORD *)(v19 + 56) = v28;
        *(_QWORD *)(v19 + 40) = 16;
        goto LABEL_40;
      }
      Next = -1073741801;
    }
    v29 = *(void **)(v19 + 56);
    if ( v29 )
      RtlFreeHeap(*(HANDLE *)(v19 + 16), 0, v29);
    *(_OWORD *)(v19 + 16) = 0;
    *(_OWORD *)(v19 + 32) = 0;
    *(_OWORD *)(v19 + 48) = 0;
    if ( Next < 0 )
    {
      AslLogCallPrintf(1, "AslpPathWildcardInitStack", 2148, "RtlArrayInitialize failed [%x]", Next);
      v30 = "AslpPathWildcardInitStack failed [%x]";
      v31 = 2349;
LABEL_61:
      LODWORD(v46) = Next;
      AslLogCallPrintf(1, "AslPathWildcardFindFirst", v31, v30, v46);
      goto LABEL_62;
    }
LABEL_40:
    RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v19 + 8));
    matched = AslpPathWildcardAllocMatchNode(
                (unsigned int)&v51,
                (unsigned int)&DestinationString,
                *(_QWORD *)(v19 + 8),
                1,
                0,
                0);
    Next = matched;
    if ( matched < 0 )
    {
      LODWORD(v46) = matched;
      AslLogCallPrintf(
        1,
        "AslPathWildcardFindFirst",
        2362,
        "AslpPathWildcardAllocMatchNode failed to create root of path [%x]",
        v46);
      goto LABEL_62;
    }
    v33 = *(_QWORD *)(v19 + 32);
    if ( v33 >= *(_QWORD *)(v19 + 40) )
    {
      if ( v33 + 1 <= *(_QWORD *)(v19 + 40) )
      {
        Next = -1073741811;
LABEL_60:
        v30 = "AslpPathWildcardPushNode failed [%x]";
        v31 = 2368;
        goto LABEL_61;
      }
      v34 = *(_QWORD *)(v19 + 48) - 1LL;
      if ( *(_QWORD *)(v19 + 48) + v33 < v33 + 1
        || (v35 = *(_QWORD *)(v19 + 24), v36 = *(_QWORD *)(v19 + 40), Size = 0, ULongLongMult(v36, v35, &pullResult) < 0)
        || (v38 = v37 & ~v34, ULongLongMult(v38, *(_QWORD *)(v19 + 24), &Size) < 0) )
      {
        Next = -1073741675;
        goto LABEL_60;
      }
      v39 = *(void **)(v19 + 56);
      v40 = Size;
      v41 = *(void **)(v19 + 16);
      if ( v39 )
      {
        v43 = RtlReAllocateHeap(v41, 0, v39, Size);
      }
      else
      {
        v42 = RtlAllocateHeap(v41, 0, Size);
        v43 = v42;
        if ( v42 )
          memset_0(v42, 0, v40);
      }
      v6 = (__int64)a1;
      if ( !v43 )
      {
        Next = -1073741801;
        goto LABEL_60;
      }
      *(_QWORD *)(v19 + 56) = v43;
      *(_QWORD *)(v19 + 40) = v38;
    }
    v44 = *(_QWORD *)(v19 + 24);
    Size = 0;
    if ( ULongLongMult(v44, v33, &Size) >= 0 )
    {
      v45 = (_OWORD *)(*(_QWORD *)(v19 + 56) + Size);
      if ( (unsigned __int64)v45 >= *(_QWORD *)(v19 + 56) )
      {
        *v45 = v51;
        v45[1] = v52;
        ++*(_QWORD *)(v19 + 32);
        *a4 = v19;
        v51 = 0;
        v52 = 0;
        Next = AslPathWildcardFindNext(v6, 260, v19);
        goto LABEL_62;
      }
    }
    Next = -1073741675;
    goto LABEL_60;
  }
  AslLogCallPrintf(1, "AslPathWildcardFindFirst", 2246, "Failed to convert dos path to nt path [%x]", v9);
LABEL_62:
  RtlFreeUnicodeString(&UnicodeString);
  if ( v8 )
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
  if ( Next < 0 )
  {
    AslpPathWildcardFreeFindContext(&v47);
    AslpPathWildcardFreeMatchNode(&v51);
    *a4 = 0;
  }
  return (unsigned int)Next;
}

```

## disassembly

```asm
0x1800be468  mov     [rsp-38h+arg_10], rbx
0x1800be46d  mov     [rsp-38h+Size], rdx
0x1800be472  mov     [rsp-38h+arg_0], rcx
0x1800be477  push    rbp
0x1800be478  push    rsi
0x1800be479  push    rdi
0x1800be47a  push    r12
0x1800be47c  push    r13
0x1800be47e  push    r14
0x1800be480  push    r15
0x1800be482  mov     rbp, rsp
0x1800be485  sub     rsp, 80h
0x1800be48c  xor     r15d, r15d
0x1800be48f  mov     r12, r9
0x1800be492  mov     rsi, r8
0x1800be495  mov     r13, rcx
0x1800be498  test    rcx, rcx
0x1800be49b  jnz     short loc_1800BE4A7
0x1800be49d  mov     eax, 0C00000EFh
0x1800be4a2  jmp     loc_1800BE9AD
0x1800be4a7  test    rsi, rsi
0x1800be4aa  jz      loc_1800BE9A8
0x1800be4b0  cmp     [r8], r15w
0x1800be4b4  jz      loc_1800BE9A8
0x1800be4ba  test    r12, r12
0x1800be4bd  jnz     short loc_1800BE4C9
0x1800be4bf  mov     eax, 0C00000F2h
0x1800be4c4  jmp     loc_1800BE9AD
0x1800be4c9  xorps   xmm0, xmm0
0x1800be4cc  mov     [r9], r15
0x1800be4cf  xorps   xmm1, xmm1
0x1800be4d2  mov     [rcx], r15w
0x1800be4d6  xor     r9d, r9d
0x1800be4d9  mov     [rbp+var_50], r15
0x1800be4dd  mov     rcx, rsi
0x1800be4e0  mov     word ptr [rbp+Size], r15w
0x1800be4e5  xor     r8d, r8d
0x1800be4e8  lea     rdx, [rbp+UnicodeString]
0x1800be4ec  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800be4f0  mov     r14, r15
0x1800be4f3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800be4f7  movups  [rbp+var_20], xmm1
0x1800be4fb  movups  [rbp+var_10], xmm1
0x1800be4ff  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800be505  mov     ebx, eax
0x1800be507  test    eax, eax
0x1800be509  jns     short loc_1800BE521
0x1800be50b  mov     dword ptr [rsp+80h+var_60], eax
0x1800be50f  lea     r9, aFailedToConver_1; "Failed to convert dos path to nt path ["...
0x1800be516  mov     r8d, 8C6h
0x1800be51c  jmp     loc_1800BE955
0x1800be521  lea     rcx, [rbp+UnicodeString]
0x1800be525  call    AslPathCleanUstr
0x1800be52a  mov     ebx, eax
0x1800be52c  test    eax, eax
0x1800be52e  jns     short loc_1800BE546
0x1800be530  mov     dword ptr [rsp+80h+var_60], eax
0x1800be534  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x1800be53b  mov     r8d, 8D1h
0x1800be541  jmp     loc_1800BE955
0x1800be546  movzx   ecx, [rbp+UnicodeString.Length]
0x1800be54a  lea     r8, [rbp+Size]
0x1800be54e  mov     edx, 4
0x1800be553  call    RtlUShortAdd
0x1800be558  mov     ebx, eax
0x1800be55a  test    eax, eax
0x1800be55c  jns     short loc_1800BE574
0x1800be55e  mov     dword ptr [rsp+80h+var_60], eax
0x1800be562  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x1800be569  mov     r8d, 8D7h
0x1800be56f  jmp     loc_1800BE955
0x1800be574  mov     rcx, gs:60h
0x1800be57d  mov     edi, 8
0x1800be582  movzx   ebx, word ptr [rbp+Size]
0x1800be586  mov     edx, edi; Flags
0x1800be588  mov     r8d, ebx; Size
0x1800be58b  mov     rcx, [rcx+30h]; HeapHandle
0x1800be58f  call    cs:__imp_RtlAllocateHeap
0x1800be595  mov     r14, rax
0x1800be598  test    rax, rax
0x1800be59b  jnz     short loc_1800BE5A7
0x1800be59d  mov     ebx, 0C0000017h
0x1800be5a2  jmp     loc_1800BE966
0x1800be5a7  movzx   r9d, [rbp+UnicodeString.Length]
0x1800be5ac  mov     rdx, rbx
0x1800be5af  mov     r8, [rbp+UnicodeString.Buffer]
0x1800be5b3  mov     rcx, r14
0x1800be5b6  call    RtlStringCbCopyNW
0x1800be5bb  mov     ebx, eax
0x1800be5bd  test    eax, eax
0x1800be5bf  jns     short loc_1800BE5D7
0x1800be5c1  mov     dword ptr [rsp+80h+var_60], eax
0x1800be5c5  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x1800be5cc  mov     r8d, 8E3h
0x1800be5d2  jmp     loc_1800BE955
0x1800be5d7  mov     rcx, r14; SourceString
0x1800be5da  call    AslpPathWildcardMakeLeaves
0x1800be5df  test    eax, eax
0x1800be5e1  jnz     short loc_1800BE609
0x1800be5e3  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x1800be5ea  mov     r8d, 8F5h
0x1800be5f0  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x1800be5f7  mov     ebx, 0C0000039h
0x1800be5fc  lea     ecx, [rax+1]
0x1800be5ff  call    AslLogCallPrintf
0x1800be604  jmp     loc_1800BE966
0x1800be609  cmp     eax, 1
0x1800be60c  jnz     short loc_1800BE661
0x1800be60e  mov     rcx, [rbp+UnicodeString.Buffer]; FileName
0x1800be612  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x1800be61a  call    AslDoesFileExistNtPath
0x1800be61f  test    eax, eax
0x1800be621  jnz     short loc_1800BE62D
0x1800be623  mov     ebx, 80000006h
0x1800be628  jmp     loc_1800BE966
0x1800be62d  mov     r8, rsi
0x1800be630  mov     edx, 104h
0x1800be635  mov     rcx, r13
0x1800be638  call    RtlStringCchCopyW
0x1800be63d  mov     ebx, eax
0x1800be63f  test    eax, eax
0x1800be641  jns     short loc_1800BE659
0x1800be643  mov     dword ptr [rsp+80h+var_60], eax
0x1800be647  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x1800be64e  mov     r8d, 907h
0x1800be654  jmp     loc_1800BE955
0x1800be659  mov     ebx, r15d
0x1800be65c  jmp     loc_1800BE966
0x1800be661  mov     rcx, gs:60h
0x1800be66a  mov     r8d, 40h ; '@'; Size
0x1800be670  mov     edx, edi; Flags
0x1800be672  mov     rcx, [rcx+30h]; HeapHandle
0x1800be676  call    cs:__imp_RtlAllocateHeap
0x1800be67c  mov     [rbp+var_50], rax
0x1800be680  mov     rdi, rax
0x1800be683  test    rax, rax
0x1800be686  jz      loc_1800BE59D
0x1800be68c  mov     r8d, 4; MaxCount
0x1800be692  lea     rdx, asc_1800E1070; "\\??\\"
0x1800be699  mov     rcx, rsi; String1
0x1800be69c  call    wcsncmp_0
0x1800be6a1  test    eax, eax
0x1800be6a3  mov     [rbp+Size], r15
0x1800be6a7  mov     ecx, r15d
0x1800be6aa  lea     r8, [rbp+pullResult]; pullResult
0x1800be6ae  setnz   cl
0x1800be6b1  xorps   xmm0, xmm0
0x1800be6b4  mov     [rdi], ecx
0x1800be6b6  mov     r10d, 10h
0x1800be6bc  mov     [rdi+8], r14
0x1800be6c0  mov     r14, r15
0x1800be6c3  movups  xmmword ptr [rdi+10h], xmm0
0x1800be6c7  movups  xmmword ptr [rdi+20h], xmm0
0x1800be6cb  lea     edx, [r10+10h]; ullMultiplier
0x1800be6cf  movups  xmmword ptr [rdi+30h], xmm0
0x1800be6d3  mov     rax, gs:60h
0x1800be6dc  mov     rcx, [rax+30h]
0x1800be6e0  mov     [rdi+10h], rcx
0x1800be6e4  xor     ecx, ecx; ullMultiplicand
0x1800be6e6  mov     [rdi+30h], r10
0x1800be6ea  mov     [rdi+18h], rdx
0x1800be6ee  call    ULongLongMult
0x1800be6f3  mov     r9d, 0C0000095h
0x1800be6f9  test    eax, eax
0x1800be6fb  jns     short loc_1800BE702
0x1800be6fd  mov     ebx, r9d
0x1800be700  jmp     short loc_1800BE75F
0x1800be702  mov     rdx, [rdi+18h]; ullMultiplier
0x1800be706  lea     r8, [rbp+Size]; pullResult
0x1800be70a  mov     rcx, r10; ullMultiplicand
0x1800be70d  call    ULongLongMult
0x1800be712  test    eax, eax
0x1800be714  js      short loc_1800BE6FD
0x1800be716  mov     r8, [rdi+38h]; Ptr
0x1800be71a  xor     edx, edx; Flags
0x1800be71c  mov     rsi, [rbp+Size]
0x1800be720  mov     rcx, [rdi+10h]; Heap
0x1800be724  test    r8, r8
0x1800be727  jnz     short loc_1800BE749
0x1800be729  mov     r8, rsi; Size
0x1800be72c  call    cs:__imp_RtlAllocateHeap
0x1800be732  mov     rbx, rax
0x1800be735  test    rax, rax
0x1800be738  jz      short loc_1800BE755
0x1800be73a  mov     r8, rsi; Size
0x1800be73d  xor     edx, edx; Val
0x1800be73f  mov     rcx, rax; void *
0x1800be742  call    memset_0
0x1800be747  jmp     short loc_1800BE755
0x1800be749  mov     r9, rsi; Size
0x1800be74c  call    cs:__imp_RtlReAllocateHeap
0x1800be752  mov     rbx, rax
0x1800be755  test    rbx, rbx
0x1800be758  jnz     short loc_1800BE7BB
0x1800be75a  mov     ebx, 0C0000017h
0x1800be75f  mov     r8, [rdi+38h]; P
0x1800be763  test    r8, r8
0x1800be766  jz      short loc_1800BE774
0x1800be768  mov     rcx, [rdi+10h]; HeapHandle
0x1800be76c  xor     edx, edx; Flags
0x1800be76e  call    cs:__imp_RtlFreeHeap
0x1800be774  xorps   xmm0, xmm0
0x1800be777  movups  xmmword ptr [rdi+10h], xmm0
0x1800be77b  movups  xmmword ptr [rdi+20h], xmm0
0x1800be77f  movups  xmmword ptr [rdi+30h], xmm0
0x1800be783  test    ebx, ebx
0x1800be785  jns     short loc_1800BE7C7
0x1800be787  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x1800be78e  mov     dword ptr [rsp+80h+var_60], ebx
0x1800be792  mov     r8d, 864h
0x1800be798  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x1800be79f  mov     ecx, 1
0x1800be7a4  call    AslLogCallPrintf
0x1800be7a9  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x1800be7b0  mov     r8d, 92Dh
0x1800be7b6  jmp     loc_1800BE951
0x1800be7bb  mov     [rdi+38h], rbx
0x1800be7bf  mov     qword ptr [rdi+28h], 10h
0x1800be7c7  mov     rdx, [rdi+8]; SourceString
0x1800be7cb  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800be7cf  call    cs:__imp_RtlInitUnicodeString
0x1800be7d5  mov     r8, [rdi+8]
0x1800be7d9  lea     rdx, [rbp+DestinationString]
0x1800be7dd  mov     r9d, 1
0x1800be7e3  mov     [rsp+80h+var_58], r15w
0x1800be7e9  lea     rcx, [rbp+var_20]
0x1800be7ed  mov     [rsp+80h+var_60], r15
0x1800be7f2  call    AslpPathWildcardAllocMatchNode
0x1800be7f7  mov     ebx, eax
0x1800be7f9  test    eax, eax
0x1800be7fb  jns     short loc_1800BE813
0x1800be7fd  mov     dword ptr [rsp+80h+var_60], eax
0x1800be801  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x1800be808  mov     r8d, 93Ah
0x1800be80e  jmp     loc_1800BE955
0x1800be813  mov     r15, [rdi+20h]
0x1800be817  cmp     r15, [rdi+28h]
0x1800be81b  jb      loc_1800BE8E0
0x1800be821  lea     rcx, [r15+1]
0x1800be825  cmp     rcx, [rdi+28h]
0x1800be829  ja      short loc_1800BE835
0x1800be82b  mov     ebx, 0C000000Dh
0x1800be830  jmp     loc_1800BE8CF
0x1800be835  mov     rbx, [rdi+30h]
0x1800be839  dec     rbx
0x1800be83c  lea     r9, [rbx+rcx]
0x1800be840  cmp     r9, rcx
0x1800be843  jnb     short loc_1800BE84F
0x1800be845  mov     ebx, 0C0000095h
0x1800be84a  jmp     loc_1800BE8CF
0x1800be84f  mov     rdx, [rdi+18h]; ullMultiplier
0x1800be853  lea     r8, [rbp+pullResult]; pullResult
0x1800be857  mov     rcx, [rdi+28h]; ullMultiplicand
0x1800be85b  mov     [rbp+Size], r14
0x1800be85f  call    ULongLongMult
0x1800be864  test    eax, eax
0x1800be866  js      short loc_1800BE845
0x1800be868  mov     rdx, [rdi+18h]; ullMultiplier
0x1800be86c  lea     r8, [rbp+Size]; pullResult
0x1800be870  not     rbx
0x1800be873  and     rbx, r9
0x1800be876  mov     rcx, rbx; ullMultiplicand
0x1800be879  call    ULongLongMult
0x1800be87e  test    eax, eax
0x1800be880  js      short loc_1800BE845
0x1800be882  mov     r8, [rdi+38h]; Ptr
0x1800be886  xor     edx, edx; Flags
0x1800be888  mov     r13, [rbp+Size]
0x1800be88c  mov     rcx, [rdi+10h]; Heap
0x1800be890  test    r8, r8
0x1800be893  jnz     short loc_1800BE8B5
0x1800be895  mov     r8, r13; Size
0x1800be898  call    cs:__imp_RtlAllocateHeap
0x1800be89e  mov     rsi, rax
0x1800be8a1  test    rax, rax
0x1800be8a4  jz      short loc_1800BE8C1
0x1800be8a6  mov     r8, r13; Size
0x1800be8a9  xor     edx, edx; Val
0x1800be8ab  mov     rcx, rax; void *
0x1800be8ae  call    memset_0
0x1800be8b3  jmp     short loc_1800BE8C1
0x1800be8b5  mov     r9, r13; Size
0x1800be8b8  call    cs:__imp_RtlReAllocateHeap
0x1800be8be  mov     rsi, rax
0x1800be8c1  mov     r13, [rbp+arg_0]
0x1800be8c5  test    rsi, rsi
0x1800be8c8  jnz     short loc_1800BE8D8
0x1800be8ca  mov     ebx, 0C0000017h
0x1800be8cf  xor     r15d, r15d
0x1800be8d2  test    ebx, ebx
0x1800be8d4  jns     short loc_1800BE91C
0x1800be8d6  jmp     short loc_1800BE944
0x1800be8d8  mov     [rdi+38h], rsi
0x1800be8dc  mov     [rdi+28h], rbx
0x1800be8e0  mov     rcx, [rdi+18h]; ullMultiplicand
0x1800be8e4  lea     r8, [rbp+Size]; pullResult
0x1800be8e8  mov     rdx, r15; ullMultiplier
0x1800be8eb  mov     [rbp+Size], r14
0x1800be8ef  call    ULongLongMult
0x1800be8f4  xor     r15d, r15d
  ... truncated ...
```
