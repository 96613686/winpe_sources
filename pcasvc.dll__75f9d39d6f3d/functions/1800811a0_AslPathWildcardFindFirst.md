# AslPathWildcardFindFirst

- ea: `0x1800811a0`
- end: `0x180081700`
- name: `AslPathWildcardFindFirst`
- size: `1376`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800e81a0`

## callees

- `0x180012920`
- `0x180019c84`
- `0x18001db24`
- `0x1800212b0`
- `0x18003769c`
- `0x180054cc0`
- `0x1800557e4`
- `0x18007a9cf`
- `0x180080038`
- `0x180080cf8`
- `0x1800811a0`
- `0x1800839d0`
- `0x180083c5c`
- `0x180083d50`
- `0x1800847d4`
- `0x1800f1eea`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800814a6`
- `ntdll!RtlFreeHeap` at `0x1800814a6`
- `ntdll!RtlReAllocateHeap` at `0x180081484`
- `ntdll!RtlReAllocateHeap` at `0x1800815f0`
- `ntdll!RtlReAllocateHeap` at `0x180081484`
- `ntdll!RtlReAllocateHeap` at `0x1800815f0`
- `ntdll!RtlInitUnicodeString` at `0x180081507`
- `ntdll!RtlInitUnicodeString` at `0x180081507`
- `ntdll!RtlFreeUnicodeString` at `0x1800816a2`
- `ntdll!RtlFreeUnicodeString` at `0x1800816a2`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180081237`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180081237`
- `ntdll!RtlAllocateHeap` at `0x1800812c7`
- `ntdll!RtlAllocateHeap` at `0x1800813ae`
- `ntdll!RtlAllocateHeap` at `0x180081464`
- `ntdll!RtlAllocateHeap` at `0x1800815d0`
- `ntdll!RtlAllocateHeap` at `0x1800812c7`
- `ntdll!RtlAllocateHeap` at `0x1800813ae`
- `ntdll!RtlAllocateHeap` at `0x180081464`
- `ntdll!RtlAllocateHeap` at `0x1800815d0`

## string_xrefs

- `0x18008167c`: `AslpPathWildcardPushNode failed [%x]`
- `0x1800814d0`: `AslpPathWildcardInitStack`
- `0x180081247`: `Failed to convert dos path to nt path [%x]`
- `0x180081328`: `AslPathWildcardFindFirst`
- `0x18008168d`: `AslPathWildcardFindFirst`
- `0x18008126c`: `AslPathCleanUstr failed [%x]`
- `0x1800812fd`: `RtlStringCbCopyNW failed [%x]`
- `0x18008137f`: `RtlStringCbCopyNW failed [%x]`
- `0x18008131b`: `Failed to split the wildcard path`
- `0x1800814e1`: `AslpPathWildcardInitStack failed [%x]`
- `0x180081539`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindFirst(_WORD *a1, ULONGLONG a2, const wchar_t *a3, __int64 *a4)
{
  __int64 v6; // r13
  const WCHAR *v8; // r14
  int matched; // ebx
  const char *v10; // r9
  int v11; // r8d
  __int64 v12; // rbx
  const WCHAR *Heap; // rax
  int Leaves; // eax
  WCHAR *Buffer; // rcx
  __int64 v16; // rdi
  int v17; // eax
  HRESULT v18; // eax
  ULONGLONG v19; // r10
  int v20; // r9d
  void *v21; // r8
  size_t v22; // rsi
  void *v23; // rcx
  PVOID v24; // rax
  PVOID v25; // rbx
  void *v26; // r8
  ULONGLONG v27; // r15
  __int64 v28; // rbx
  ULONGLONG v29; // rdx
  ULONGLONG v30; // rcx
  __int64 v31; // r9
  ULONGLONG v32; // rbx
  void *v33; // r8
  size_t v34; // r13
  void *v35; // rcx
  PVOID v36; // rax
  PVOID v37; // rsi
  ULONGLONG v38; // rcx
  _OWORD *v39; // rdx
  _DWORD *v40; // [rsp+30h] [rbp-50h] BYREF
  ULONGLONG pullResult; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  __int128 v44; // [rsp+60h] [rbp-20h] BYREF
  __int128 v45; // [rsp+70h] [rbp-10h]
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
  v40 = 0;
  LOWORD(Size) = 0;
  UnicodeString = 0;
  v8 = 0;
  DestinationString = 0;
  v44 = 0;
  v45 = 0;
  matched = RtlDosPathNameToNtPathName_U_WithStatus(a3, &UnicodeString, 0, 0);
  if ( matched < 0 )
  {
    v10 = "Failed to convert dos path to nt path [%x]";
    v11 = 2246;
LABEL_61:
    AslLogCallPrintf(1, (unsigned int)"AslPathWildcardFindFirst", v11, (_DWORD)v10);
    goto LABEL_62;
  }
  matched = AslPathCleanUstr(&UnicodeString);
  if ( matched < 0 )
  {
    v10 = "AslPathCleanUstr failed [%x]";
    v11 = 2257;
    goto LABEL_61;
  }
  matched = RtlUShortAdd(UnicodeString.Length, 4, &Size);
  if ( matched < 0 )
  {
    v10 = "RtlUShortAdd failed [%x]";
    v11 = 2263;
    goto LABEL_61;
  }
  v12 = (unsigned __int16)Size;
  Heap = (const WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)Size);
  v8 = Heap;
  if ( !Heap )
    goto LABEL_14;
  matched = RtlStringCbCopyNW(Heap, v12, UnicodeString.Buffer, UnicodeString.Length);
  if ( matched < 0 )
  {
    v10 = "RtlStringCbCopyNW failed [%x]";
    v11 = 2275;
    goto LABEL_61;
  }
  Leaves = AslpPathWildcardMakeLeaves(v8);
  if ( !Leaves )
  {
    matched = -1073741767;
    AslLogCallPrintf(
      1,
      (unsigned int)"AslPathWildcardFindFirst",
      2293,
      (unsigned int)"Failed to split the wildcard path");
    goto LABEL_62;
  }
  if ( Leaves != 1 )
  {
    v40 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
    v16 = (__int64)v40;
    if ( !v40 )
    {
LABEL_14:
      matched = -1073741801;
      goto LABEL_62;
    }
    v17 = wcsncmp_0(a3, L"\\??\\", 4u);
    Size = 0;
    *v40 = v17 != 0;
    *(_QWORD *)(v16 + 8) = v8;
    v8 = 0;
    *(_OWORD *)(v16 + 16) = 0;
    *(_OWORD *)(v16 + 32) = 0;
    *(_OWORD *)(v16 + 48) = 0;
    *(_QWORD *)(v16 + 16) = NtCurrentPeb()->ProcessHeap;
    *(_QWORD *)(v16 + 48) = 16;
    *(_QWORD *)(v16 + 24) = 32;
    v18 = ULongLongMult(0, 0x20u, &pullResult);
    v20 = -1073741675;
    if ( v18 < 0 || ULongLongMult(v19, *(_QWORD *)(v16 + 24), &Size) < 0 )
    {
      matched = v20;
    }
    else
    {
      v21 = *(void **)(v16 + 56);
      v22 = Size;
      v23 = *(void **)(v16 + 16);
      if ( v21 )
      {
        v25 = RtlReAllocateHeap(v23, 0, v21, Size);
      }
      else
      {
        v24 = RtlAllocateHeap(v23, 0, Size);
        v25 = v24;
        if ( v24 )
          memset_0(v24, 0, v22);
      }
      if ( v25 )
      {
        *(_QWORD *)(v16 + 56) = v25;
        *(_QWORD *)(v16 + 40) = 16;
        goto LABEL_40;
      }
      matched = -1073741801;
    }
    v26 = *(void **)(v16 + 56);
    if ( v26 )
      RtlFreeHeap(*(HANDLE *)(v16 + 16), 0, v26);
    *(_OWORD *)(v16 + 16) = 0;
    *(_OWORD *)(v16 + 32) = 0;
    *(_OWORD *)(v16 + 48) = 0;
    if ( matched < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslpPathWildcardInitStack",
        2148,
        (unsigned int)"RtlArrayInitialize failed [%x]");
      v10 = "AslpPathWildcardInitStack failed [%x]";
      v11 = 2349;
      goto LABEL_61;
    }
LABEL_40:
    RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v16 + 8));
    matched = AslpPathWildcardAllocMatchNode(
                (unsigned int)&v44,
                (unsigned int)&DestinationString,
                *(_QWORD *)(v16 + 8),
                1,
                0,
                0);
    if ( matched < 0 )
    {
      v10 = "AslpPathWildcardAllocMatchNode failed to create root of path [%x]";
      v11 = 2362;
      goto LABEL_61;
    }
    v27 = *(_QWORD *)(v16 + 32);
    if ( v27 >= *(_QWORD *)(v16 + 40) )
    {
      if ( v27 + 1 <= *(_QWORD *)(v16 + 40) )
      {
        matched = -1073741811;
        goto LABEL_60;
      }
      v28 = *(_QWORD *)(v16 + 48) - 1LL;
      if ( *(_QWORD *)(v16 + 48) + v27 < v27 + 1
        || (v29 = *(_QWORD *)(v16 + 24), v30 = *(_QWORD *)(v16 + 40), Size = 0, ULongLongMult(v30, v29, &pullResult) < 0)
        || (v32 = v31 & ~v28, ULongLongMult(v32, *(_QWORD *)(v16 + 24), &Size) < 0) )
      {
        matched = -1073741675;
        goto LABEL_60;
      }
      v33 = *(void **)(v16 + 56);
      v34 = Size;
      v35 = *(void **)(v16 + 16);
      if ( v33 )
      {
        v37 = RtlReAllocateHeap(v35, 0, v33, Size);
      }
      else
      {
        v36 = RtlAllocateHeap(v35, 0, Size);
        v37 = v36;
        if ( v36 )
          memset_0(v36, 0, v34);
      }
      v6 = (__int64)a1;
      if ( !v37 )
      {
        matched = -1073741801;
        goto LABEL_60;
      }
      *(_QWORD *)(v16 + 56) = v37;
      *(_QWORD *)(v16 + 40) = v32;
    }
    v38 = *(_QWORD *)(v16 + 24);
    Size = 0;
    if ( ULongLongMult(v38, v27, &Size) >= 0 )
    {
      v39 = (_OWORD *)(*(_QWORD *)(v16 + 56) + Size);
      if ( (unsigned __int64)v39 >= *(_QWORD *)(v16 + 56) )
      {
        *v39 = v44;
        v39[1] = v45;
        ++*(_QWORD *)(v16 + 32);
        *a4 = v16;
        v44 = 0;
        v45 = 0;
        matched = AslPathWildcardFindNext(v6, 260, v16);
        goto LABEL_62;
      }
    }
    matched = -1073741675;
LABEL_60:
    v10 = "AslpPathWildcardPushNode failed [%x]";
    v11 = 2368;
    goto LABEL_61;
  }
  Buffer = UnicodeString.Buffer;
  *a4 = -1;
  if ( (unsigned int)AslDoesFileExistNtPath(Buffer) )
  {
    matched = RtlStringCchCopyW(v6, 260, a3);
    if ( matched < 0 )
    {
      v10 = "RtlStringCbCopyNW failed [%x]";
      v11 = 2311;
      goto LABEL_61;
    }
    matched = 0;
  }
  else
  {
    matched = -2147483642;
  }
LABEL_62:
  RtlFreeUnicodeString(&UnicodeString);
  if ( v8 )
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
  if ( matched < 0 )
  {
    AslpPathWildcardFreeFindContext(&v40);
    AslpPathWildcardFreeMatchNode(&v44);
    *a4 = 0;
  }
  return (unsigned int)matched;
}

```

## disassembly

```asm
0x1800811a0  mov     [rsp-38h+arg_10], rbx
0x1800811a5  mov     [rsp-38h+Size], rdx
0x1800811aa  mov     [rsp-38h+arg_0], rcx
0x1800811af  push    rbp
0x1800811b0  push    rsi
0x1800811b1  push    rdi
0x1800811b2  push    r12
0x1800811b4  push    r13
0x1800811b6  push    r14
0x1800811b8  push    r15
0x1800811ba  mov     rbp, rsp
0x1800811bd  sub     rsp, 80h
0x1800811c4  xor     r15d, r15d
0x1800811c7  mov     r12, r9
0x1800811ca  mov     rsi, r8
0x1800811cd  mov     r13, rcx
0x1800811d0  test    rcx, rcx
0x1800811d3  jnz     short loc_1800811DF
0x1800811d5  mov     eax, 0C00000EFh
0x1800811da  jmp     loc_1800816E5
0x1800811df  test    rsi, rsi
0x1800811e2  jz      loc_1800816E0
0x1800811e8  cmp     [r8], r15w
0x1800811ec  jz      loc_1800816E0
0x1800811f2  test    r12, r12
0x1800811f5  jnz     short loc_180081201
0x1800811f7  mov     eax, 0C00000F2h
0x1800811fc  jmp     loc_1800816E5
0x180081201  xorps   xmm0, xmm0
0x180081204  mov     [r9], r15
0x180081207  xorps   xmm1, xmm1
0x18008120a  mov     [rcx], r15w
0x18008120e  xor     r9d, r9d
0x180081211  mov     [rbp+var_50], r15
0x180081215  mov     rcx, rsi
0x180081218  mov     word ptr [rbp+Size], r15w
0x18008121d  xor     r8d, r8d
0x180081220  lea     rdx, [rbp+UnicodeString]
0x180081224  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180081228  mov     r14, r15
0x18008122b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18008122f  movups  [rbp+var_20], xmm1
0x180081233  movups  [rbp+var_10], xmm1
0x180081237  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18008123d  mov     ebx, eax
0x18008123f  test    eax, eax
0x180081241  jns     short loc_180081259
0x180081243  mov     dword ptr [rsp+80h+var_60], eax
0x180081247  lea     r9, aFailedToConver_12; "Failed to convert dos path to nt path ["...
0x18008124e  mov     r8d, 8C6h
0x180081254  jmp     loc_18008168D
0x180081259  lea     rcx, [rbp+UnicodeString]
0x18008125d  call    AslPathCleanUstr
0x180081262  mov     ebx, eax
0x180081264  test    eax, eax
0x180081266  jns     short loc_18008127E
0x180081268  mov     dword ptr [rsp+80h+var_60], eax
0x18008126c  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x180081273  mov     r8d, 8D1h
0x180081279  jmp     loc_18008168D
0x18008127e  movzx   ecx, [rbp+UnicodeString.Length]
0x180081282  lea     r8, [rbp+Size]
0x180081286  mov     edx, 4
0x18008128b  call    RtlUShortAdd
0x180081290  mov     ebx, eax
0x180081292  test    eax, eax
0x180081294  jns     short loc_1800812AC
0x180081296  mov     dword ptr [rsp+80h+var_60], eax
0x18008129a  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x1800812a1  mov     r8d, 8D7h
0x1800812a7  jmp     loc_18008168D
0x1800812ac  mov     rcx, gs:60h
0x1800812b5  mov     edi, 8
0x1800812ba  movzx   ebx, word ptr [rbp+Size]
0x1800812be  mov     edx, edi; Flags
0x1800812c0  mov     r8d, ebx; Size
0x1800812c3  mov     rcx, [rcx+30h]; HeapHandle
0x1800812c7  call    cs:__imp_RtlAllocateHeap
0x1800812cd  mov     r14, rax
0x1800812d0  test    rax, rax
0x1800812d3  jnz     short loc_1800812DF
0x1800812d5  mov     ebx, 0C0000017h
0x1800812da  jmp     loc_18008169E
0x1800812df  movzx   r9d, [rbp+UnicodeString.Length]
0x1800812e4  mov     rdx, rbx
0x1800812e7  mov     r8, [rbp+UnicodeString.Buffer]
0x1800812eb  mov     rcx, r14
0x1800812ee  call    RtlStringCbCopyNW
0x1800812f3  mov     ebx, eax
0x1800812f5  test    eax, eax
0x1800812f7  jns     short loc_18008130F
0x1800812f9  mov     dword ptr [rsp+80h+var_60], eax
0x1800812fd  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x180081304  mov     r8d, 8E3h
0x18008130a  jmp     loc_18008168D
0x18008130f  mov     rcx, r14; SourceString
0x180081312  call    AslpPathWildcardMakeLeaves
0x180081317  test    eax, eax
0x180081319  jnz     short loc_180081341
0x18008131b  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x180081322  mov     r8d, 8F5h
0x180081328  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x18008132f  mov     ebx, 0C0000039h
0x180081334  lea     ecx, [rax+1]
0x180081337  call    AslLogCallPrintf
0x18008133c  jmp     loc_18008169E
0x180081341  cmp     eax, 1
0x180081344  jnz     short loc_180081399
0x180081346  mov     rcx, [rbp+UnicodeString.Buffer]; FileName
0x18008134a  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180081352  call    AslDoesFileExistNtPath
0x180081357  test    eax, eax
0x180081359  jnz     short loc_180081365
0x18008135b  mov     ebx, 80000006h
0x180081360  jmp     loc_18008169E
0x180081365  mov     r8, rsi
0x180081368  mov     edx, 104h
0x18008136d  mov     rcx, r13
0x180081370  call    RtlStringCchCopyW
0x180081375  mov     ebx, eax
0x180081377  test    eax, eax
0x180081379  jns     short loc_180081391
0x18008137b  mov     dword ptr [rsp+80h+var_60], eax
0x18008137f  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x180081386  mov     r8d, 907h
0x18008138c  jmp     loc_18008168D
0x180081391  mov     ebx, r15d
0x180081394  jmp     loc_18008169E
0x180081399  mov     rcx, gs:60h
0x1800813a2  mov     r8d, 40h ; '@'; Size
0x1800813a8  mov     edx, edi; Flags
0x1800813aa  mov     rcx, [rcx+30h]; HeapHandle
0x1800813ae  call    cs:__imp_RtlAllocateHeap
0x1800813b4  mov     [rbp+var_50], rax
0x1800813b8  mov     rdi, rax
0x1800813bb  test    rax, rax
0x1800813be  jz      loc_1800812D5
0x1800813c4  mov     r8d, 4; MaxCount
0x1800813ca  lea     rdx, asc_1801034A0; "\\??\\"
0x1800813d1  mov     rcx, rsi; String1
0x1800813d4  call    wcsncmp_0
0x1800813d9  test    eax, eax
0x1800813db  mov     [rbp+Size], r15
0x1800813df  mov     ecx, r15d
0x1800813e2  lea     r8, [rbp+pullResult]; pullResult
0x1800813e6  setnz   cl
0x1800813e9  xorps   xmm0, xmm0
0x1800813ec  mov     [rdi], ecx
0x1800813ee  mov     r10d, 10h
0x1800813f4  mov     [rdi+8], r14
0x1800813f8  mov     r14, r15
0x1800813fb  movups  xmmword ptr [rdi+10h], xmm0
0x1800813ff  movups  xmmword ptr [rdi+20h], xmm0
0x180081403  lea     edx, [r10+10h]; ullMultiplier
0x180081407  movups  xmmword ptr [rdi+30h], xmm0
0x18008140b  mov     rax, gs:60h
0x180081414  mov     rcx, [rax+30h]
0x180081418  mov     [rdi+10h], rcx
0x18008141c  xor     ecx, ecx; ullMultiplicand
0x18008141e  mov     [rdi+30h], r10
0x180081422  mov     [rdi+18h], rdx
0x180081426  call    ULongLongMult
0x18008142b  mov     r9d, 0C0000095h
0x180081431  test    eax, eax
0x180081433  jns     short loc_18008143A
0x180081435  mov     ebx, r9d
0x180081438  jmp     short loc_180081497
0x18008143a  mov     rdx, [rdi+18h]; ullMultiplier
0x18008143e  lea     r8, [rbp+Size]; pullResult
0x180081442  mov     rcx, r10; ullMultiplicand
0x180081445  call    ULongLongMult
0x18008144a  test    eax, eax
0x18008144c  js      short loc_180081435
0x18008144e  mov     r8, [rdi+38h]; Ptr
0x180081452  xor     edx, edx; Flags
0x180081454  mov     rsi, [rbp+Size]
0x180081458  mov     rcx, [rdi+10h]; Heap
0x18008145c  test    r8, r8
0x18008145f  jnz     short loc_180081481
0x180081461  mov     r8, rsi; Size
0x180081464  call    cs:__imp_RtlAllocateHeap
0x18008146a  mov     rbx, rax
0x18008146d  test    rax, rax
0x180081470  jz      short loc_18008148D
0x180081472  mov     r8, rsi; Size
0x180081475  xor     edx, edx; Val
0x180081477  mov     rcx, rax; void *
0x18008147a  call    memset_0
0x18008147f  jmp     short loc_18008148D
0x180081481  mov     r9, rsi; Size
0x180081484  call    cs:__imp_RtlReAllocateHeap
0x18008148a  mov     rbx, rax
0x18008148d  test    rbx, rbx
0x180081490  jnz     short loc_1800814F3
0x180081492  mov     ebx, 0C0000017h
0x180081497  mov     r8, [rdi+38h]; P
0x18008149b  test    r8, r8
0x18008149e  jz      short loc_1800814AC
0x1800814a0  mov     rcx, [rdi+10h]; HeapHandle
0x1800814a4  xor     edx, edx; Flags
0x1800814a6  call    cs:__imp_RtlFreeHeap
0x1800814ac  xorps   xmm0, xmm0
0x1800814af  movups  xmmword ptr [rdi+10h], xmm0
0x1800814b3  movups  xmmword ptr [rdi+20h], xmm0
0x1800814b7  movups  xmmword ptr [rdi+30h], xmm0
0x1800814bb  test    ebx, ebx
0x1800814bd  jns     short loc_1800814FF
0x1800814bf  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x1800814c6  mov     dword ptr [rsp+80h+var_60], ebx
0x1800814ca  mov     r8d, 864h
0x1800814d0  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x1800814d7  mov     ecx, 1
0x1800814dc  call    AslLogCallPrintf
0x1800814e1  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x1800814e8  mov     r8d, 92Dh
0x1800814ee  jmp     loc_180081689
0x1800814f3  mov     [rdi+38h], rbx
0x1800814f7  mov     qword ptr [rdi+28h], 10h
0x1800814ff  mov     rdx, [rdi+8]; SourceString
0x180081503  lea     rcx, [rbp+DestinationString]; DestinationString
0x180081507  call    cs:__imp_RtlInitUnicodeString
0x18008150d  mov     r8, [rdi+8]
0x180081511  lea     rdx, [rbp+DestinationString]
0x180081515  mov     r9d, 1
0x18008151b  mov     [rsp+80h+var_58], r15w
0x180081521  lea     rcx, [rbp+var_20]
0x180081525  mov     [rsp+80h+var_60], r15
0x18008152a  call    AslpPathWildcardAllocMatchNode
0x18008152f  mov     ebx, eax
0x180081531  test    eax, eax
0x180081533  jns     short loc_18008154B
0x180081535  mov     dword ptr [rsp+80h+var_60], eax
0x180081539  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x180081540  mov     r8d, 93Ah
0x180081546  jmp     loc_18008168D
0x18008154b  mov     r15, [rdi+20h]
0x18008154f  cmp     r15, [rdi+28h]
0x180081553  jb      loc_180081618
0x180081559  lea     rcx, [r15+1]
0x18008155d  cmp     rcx, [rdi+28h]
0x180081561  ja      short loc_18008156D
0x180081563  mov     ebx, 0C000000Dh
0x180081568  jmp     loc_180081607
0x18008156d  mov     rbx, [rdi+30h]
0x180081571  dec     rbx
0x180081574  lea     r9, [rbx+rcx]
0x180081578  cmp     r9, rcx
0x18008157b  jnb     short loc_180081587
0x18008157d  mov     ebx, 0C0000095h
0x180081582  jmp     loc_180081607
0x180081587  mov     rdx, [rdi+18h]; ullMultiplier
0x18008158b  lea     r8, [rbp+pullResult]; pullResult
0x18008158f  mov     rcx, [rdi+28h]; ullMultiplicand
0x180081593  mov     [rbp+Size], r14
0x180081597  call    ULongLongMult
0x18008159c  test    eax, eax
0x18008159e  js      short loc_18008157D
0x1800815a0  mov     rdx, [rdi+18h]; ullMultiplier
0x1800815a4  lea     r8, [rbp+Size]; pullResult
0x1800815a8  not     rbx
0x1800815ab  and     rbx, r9
0x1800815ae  mov     rcx, rbx; ullMultiplicand
0x1800815b1  call    ULongLongMult
0x1800815b6  test    eax, eax
0x1800815b8  js      short loc_18008157D
0x1800815ba  mov     r8, [rdi+38h]; Ptr
0x1800815be  xor     edx, edx; Flags
0x1800815c0  mov     r13, [rbp+Size]
0x1800815c4  mov     rcx, [rdi+10h]; Heap
0x1800815c8  test    r8, r8
0x1800815cb  jnz     short loc_1800815ED
0x1800815cd  mov     r8, r13; Size
0x1800815d0  call    cs:__imp_RtlAllocateHeap
0x1800815d6  mov     rsi, rax
0x1800815d9  test    rax, rax
0x1800815dc  jz      short loc_1800815F9
0x1800815de  mov     r8, r13; Size
0x1800815e1  xor     edx, edx; Val
0x1800815e3  mov     rcx, rax; void *
0x1800815e6  call    memset_0
0x1800815eb  jmp     short loc_1800815F9
0x1800815ed  mov     r9, r13; Size
0x1800815f0  call    cs:__imp_RtlReAllocateHeap
0x1800815f6  mov     rsi, rax
0x1800815f9  mov     r13, [rbp+arg_0]
0x1800815fd  test    rsi, rsi
0x180081600  jnz     short loc_180081610
0x180081602  mov     ebx, 0C0000017h
0x180081607  xor     r15d, r15d
0x18008160a  test    ebx, ebx
0x18008160c  jns     short loc_180081654
0x18008160e  jmp     short loc_18008167C
0x180081610  mov     [rdi+38h], rsi
0x180081614  mov     [rdi+28h], rbx
0x180081618  mov     rcx, [rdi+18h]; ullMultiplicand
0x18008161c  lea     r8, [rbp+Size]; pullResult
0x180081620  mov     rdx, r15; ullMultiplier
0x180081623  mov     [rbp+Size], r14
0x180081627  call    ULongLongMult
0x18008162c  xor     r15d, r15d
  ... truncated ...
```
