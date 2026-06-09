# AslPathWildcardFindFirst

- ea: `0x18004ef04`
- end: `0x18004f4a1`
- name: `AslPathWildcardFindFirst`
- size: `1437`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, loader_planting`

## callers

- `0x18007ff50`

## callees

- `0x18001cb8c`
- `0x18001ef8c`
- `0x18001f138`
- `0x180034c90`
- `0x18003582c`
- `0x180045dd0`
- `0x1800481e4`
- `0x18004ef04`
- `0x180053b94`
- `0x180053c8c`
- `0x180059d64`
- `0x18005a52c`
- `0x180078160`
- `0x180078848`
- `0x18008275d`
- `0x180082799`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18004ef9b`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18004ef9b`
- `ntdll!RtlFreeUnicodeString` at `0x18004f43c`
- `ntdll!RtlFreeUnicodeString` at `0x18004f43c`
- `ntdll!RtlReAllocateHeap` at `0x18004f200`
- `ntdll!RtlReAllocateHeap` at `0x18004f384`
- `ntdll!RtlReAllocateHeap` at `0x18004f200`
- `ntdll!RtlReAllocateHeap` at `0x18004f384`
- `ntdll!RtlInitUnicodeString` at `0x18004f28f`
- `ntdll!RtlInitUnicodeString` at `0x18004f28f`
- `ntdll!RtlFreeHeap` at `0x18004f228`
- `ntdll!RtlFreeHeap` at `0x18004f228`
- `ntdll!RtlAllocateHeap` at `0x18004f031`
- `ntdll!RtlAllocateHeap` at `0x18004f11e`
- `ntdll!RtlAllocateHeap` at `0x18004f1da`
- `ntdll!RtlAllocateHeap` at `0x18004f35e`
- `ntdll!RtlAllocateHeap` at `0x18004f031`
- `ntdll!RtlAllocateHeap` at `0x18004f11e`
- `ntdll!RtlAllocateHeap` at `0x18004f1da`
- `ntdll!RtlAllocateHeap` at `0x18004f35e`

## string_xrefs

- `0x18004f416`: `AslpPathWildcardPushNode failed [%x]`
- `0x18004f258`: `AslpPathWildcardInitStack`
- `0x18004f098`: `AslPathWildcardFindFirst`
- `0x18004f427`: `AslPathWildcardFindFirst`
- `0x18004efb1`: `Failed to convert dos path to nt path [%x]`
- `0x18004efd6`: `AslPathCleanUstr failed [%x]`
- `0x18004f08b`: `Failed to split the wildcard path`
- `0x18004f06d`: `RtlStringCbCopyNW failed [%x]`
- `0x18004f0ef`: `RtlStringCbCopyNW failed [%x]`
- `0x18004f2c7`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`
- `0x18004f269`: `AslpPathWildcardInitStack failed [%x]`

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
0x18004ef04  mov     [rsp-38h+arg_10], rbx
0x18004ef09  mov     [rsp-38h+Size], rdx
0x18004ef0e  mov     [rsp-38h+arg_0], rcx
0x18004ef13  push    rbp
0x18004ef14  push    rsi
0x18004ef15  push    rdi
0x18004ef16  push    r12
0x18004ef18  push    r13
0x18004ef1a  push    r14
0x18004ef1c  push    r15
0x18004ef1e  mov     rbp, rsp
0x18004ef21  sub     rsp, 80h
0x18004ef28  xor     r15d, r15d
0x18004ef2b  mov     r12, r9
0x18004ef2e  mov     rsi, r8
0x18004ef31  mov     r13, rcx
0x18004ef34  test    rcx, rcx
0x18004ef37  jnz     short loc_18004EF43
0x18004ef39  mov     eax, 0C00000EFh
0x18004ef3e  jmp     loc_18004F485
0x18004ef43  test    rsi, rsi
0x18004ef46  jz      loc_18004F480
0x18004ef4c  cmp     [r8], r15w
0x18004ef50  jz      loc_18004F480
0x18004ef56  test    r12, r12
0x18004ef59  jnz     short loc_18004EF65
0x18004ef5b  mov     eax, 0C00000F2h
0x18004ef60  jmp     loc_18004F485
0x18004ef65  xorps   xmm0, xmm0
0x18004ef68  mov     [r9], r15
0x18004ef6b  xorps   xmm1, xmm1
0x18004ef6e  mov     [rcx], r15w
0x18004ef72  xor     r9d, r9d
0x18004ef75  mov     [rbp+var_50], r15
0x18004ef79  mov     rcx, rsi
0x18004ef7c  mov     word ptr [rbp+Size], r15w
0x18004ef81  xor     r8d, r8d
0x18004ef84  lea     rdx, [rbp+UnicodeString]
0x18004ef88  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18004ef8c  mov     r14, r15
0x18004ef8f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004ef93  movups  [rbp+var_20], xmm1
0x18004ef97  movups  [rbp+var_10], xmm1
0x18004ef9b  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18004efa2  nop     dword ptr [rax+rax+00h]
0x18004efa7  mov     ebx, eax
0x18004efa9  test    eax, eax
0x18004efab  jns     short loc_18004EFC3
0x18004efad  mov     dword ptr [rsp+80h+var_60], eax
0x18004efb1  lea     r9, aFailedToConver_0; "Failed to convert dos path to nt path ["...
0x18004efb8  mov     r8d, 8C6h
0x18004efbe  jmp     loc_18004F427
0x18004efc3  lea     rcx, [rbp+UnicodeString]
0x18004efc7  call    AslPathCleanUstr
0x18004efcc  mov     ebx, eax
0x18004efce  test    eax, eax
0x18004efd0  jns     short loc_18004EFE8
0x18004efd2  mov     dword ptr [rsp+80h+var_60], eax
0x18004efd6  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x18004efdd  mov     r8d, 8D1h
0x18004efe3  jmp     loc_18004F427
0x18004efe8  movzx   ecx, [rbp+UnicodeString.Length]
0x18004efec  lea     r8, [rbp+Size]
0x18004eff0  mov     edx, 4
0x18004eff5  call    RtlUShortAdd
0x18004effa  mov     ebx, eax
0x18004effc  test    eax, eax
0x18004effe  jns     short loc_18004F016
0x18004f000  mov     dword ptr [rsp+80h+var_60], eax
0x18004f004  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x18004f00b  mov     r8d, 8D7h
0x18004f011  jmp     loc_18004F427
0x18004f016  mov     rcx, gs:60h
0x18004f01f  mov     edi, 8
0x18004f024  movzx   ebx, word ptr [rbp+Size]
0x18004f028  mov     edx, edi; Flags
0x18004f02a  mov     r8d, ebx; Size
0x18004f02d  mov     rcx, [rcx+30h]; HeapHandle
0x18004f031  call    cs:__imp_RtlAllocateHeap
0x18004f038  nop     dword ptr [rax+rax+00h]
0x18004f03d  mov     r14, rax
0x18004f040  test    rax, rax
0x18004f043  jnz     short loc_18004F04F
0x18004f045  mov     ebx, 0C0000017h
0x18004f04a  jmp     loc_18004F438
0x18004f04f  movzx   r9d, [rbp+UnicodeString.Length]
0x18004f054  mov     rdx, rbx
0x18004f057  mov     r8, [rbp+UnicodeString.Buffer]
0x18004f05b  mov     rcx, r14
0x18004f05e  call    RtlStringCbCopyNW
0x18004f063  mov     ebx, eax
0x18004f065  test    eax, eax
0x18004f067  jns     short loc_18004F07F
0x18004f069  mov     dword ptr [rsp+80h+var_60], eax
0x18004f06d  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x18004f074  mov     r8d, 8E3h
0x18004f07a  jmp     loc_18004F427
0x18004f07f  mov     rcx, r14; SourceString
0x18004f082  call    AslpPathWildcardMakeLeaves
0x18004f087  test    eax, eax
0x18004f089  jnz     short loc_18004F0B1
0x18004f08b  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x18004f092  mov     r8d, 8F5h
0x18004f098  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x18004f09f  mov     ebx, 0C0000039h
0x18004f0a4  lea     ecx, [rax+1]
0x18004f0a7  call    AslLogCallPrintf
0x18004f0ac  jmp     loc_18004F438
0x18004f0b1  cmp     eax, 1
0x18004f0b4  jnz     short loc_18004F109
0x18004f0b6  mov     rcx, [rbp+UnicodeString.Buffer]; FileName
0x18004f0ba  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x18004f0c2  call    AslDoesFileExistNtPath
0x18004f0c7  test    eax, eax
0x18004f0c9  jnz     short loc_18004F0D5
0x18004f0cb  mov     ebx, 80000006h
0x18004f0d0  jmp     loc_18004F438
0x18004f0d5  mov     r8, rsi
0x18004f0d8  mov     edx, 104h
0x18004f0dd  mov     rcx, r13
0x18004f0e0  call    RtlStringCchCopyW
0x18004f0e5  mov     ebx, eax
0x18004f0e7  test    eax, eax
0x18004f0e9  jns     short loc_18004F101
0x18004f0eb  mov     dword ptr [rsp+80h+var_60], eax
0x18004f0ef  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x18004f0f6  mov     r8d, 907h
0x18004f0fc  jmp     loc_18004F427
0x18004f101  mov     ebx, r15d
0x18004f104  jmp     loc_18004F438
0x18004f109  mov     rcx, gs:60h
0x18004f112  mov     r8d, 40h ; '@'; Size
0x18004f118  mov     edx, edi; Flags
0x18004f11a  mov     rcx, [rcx+30h]; HeapHandle
0x18004f11e  call    cs:__imp_RtlAllocateHeap
0x18004f125  nop     dword ptr [rax+rax+00h]
0x18004f12a  mov     [rbp+var_50], rax
0x18004f12e  mov     rdi, rax
0x18004f131  test    rax, rax
0x18004f134  jz      loc_18004F045
0x18004f13a  mov     r8d, 4; MaxCount
0x18004f140  lea     rdx, asc_180090038; "\\??\\"
0x18004f147  mov     rcx, rsi; String1
0x18004f14a  call    wcsncmp_0
0x18004f14f  test    eax, eax
0x18004f151  mov     [rbp+Size], r15
0x18004f155  mov     ecx, r15d
0x18004f158  lea     r8, [rbp+pullResult]; pullResult
0x18004f15c  setnz   cl
0x18004f15f  xorps   xmm0, xmm0
0x18004f162  mov     [rdi], ecx
0x18004f164  mov     r10d, 10h
0x18004f16a  mov     [rdi+8], r14
0x18004f16e  mov     r14, r15
0x18004f171  movups  xmmword ptr [rdi+10h], xmm0
0x18004f175  movups  xmmword ptr [rdi+20h], xmm0
0x18004f179  lea     edx, [r10+10h]; ullMultiplier
0x18004f17d  movups  xmmword ptr [rdi+30h], xmm0
0x18004f181  mov     rax, gs:60h
0x18004f18a  mov     rcx, [rax+30h]
0x18004f18e  mov     [rdi+10h], rcx
0x18004f192  xor     ecx, ecx; ullMultiplicand
0x18004f194  mov     [rdi+30h], r10
0x18004f198  mov     [rdi+18h], rdx
0x18004f19c  call    ULongLongMult
0x18004f1a1  mov     r9d, 0C0000095h
0x18004f1a7  test    eax, eax
0x18004f1a9  jns     short loc_18004F1B0
0x18004f1ab  mov     ebx, r9d
0x18004f1ae  jmp     short loc_18004F219
0x18004f1b0  mov     rdx, [rdi+18h]; ullMultiplier
0x18004f1b4  lea     r8, [rbp+Size]; pullResult
0x18004f1b8  mov     rcx, r10; ullMultiplicand
0x18004f1bb  call    ULongLongMult
0x18004f1c0  test    eax, eax
0x18004f1c2  js      short loc_18004F1AB
0x18004f1c4  mov     r8, [rdi+38h]; Ptr
0x18004f1c8  xor     edx, edx; Flags
0x18004f1ca  mov     rsi, [rbp+Size]
0x18004f1ce  mov     rcx, [rdi+10h]; Heap
0x18004f1d2  test    r8, r8
0x18004f1d5  jnz     short loc_18004F1FD
0x18004f1d7  mov     r8, rsi; Size
0x18004f1da  call    cs:__imp_RtlAllocateHeap
0x18004f1e1  nop     dword ptr [rax+rax+00h]
0x18004f1e6  mov     rbx, rax
0x18004f1e9  test    rax, rax
0x18004f1ec  jz      short loc_18004F20F
0x18004f1ee  mov     r8, rsi; Size
0x18004f1f1  xor     edx, edx; Val
0x18004f1f3  mov     rcx, rax; void *
0x18004f1f6  call    memset_0
0x18004f1fb  jmp     short loc_18004F20F
0x18004f1fd  mov     r9, rsi; Size
0x18004f200  call    cs:__imp_RtlReAllocateHeap
0x18004f207  nop     dword ptr [rax+rax+00h]
0x18004f20c  mov     rbx, rax
0x18004f20f  test    rbx, rbx
0x18004f212  jnz     short loc_18004F27B
0x18004f214  mov     ebx, 0C0000017h
0x18004f219  mov     r8, [rdi+38h]; P
0x18004f21d  test    r8, r8
0x18004f220  jz      short loc_18004F234
0x18004f222  mov     rcx, [rdi+10h]; HeapHandle
0x18004f226  xor     edx, edx; Flags
0x18004f228  call    cs:__imp_RtlFreeHeap
0x18004f22f  nop     dword ptr [rax+rax+00h]
0x18004f234  xorps   xmm0, xmm0
0x18004f237  movups  xmmword ptr [rdi+10h], xmm0
0x18004f23b  movups  xmmword ptr [rdi+20h], xmm0
0x18004f23f  movups  xmmword ptr [rdi+30h], xmm0
0x18004f243  test    ebx, ebx
0x18004f245  jns     short loc_18004F287
0x18004f247  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x18004f24e  mov     dword ptr [rsp+80h+var_60], ebx
0x18004f252  mov     r8d, 864h
0x18004f258  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x18004f25f  mov     ecx, 1
0x18004f264  call    AslLogCallPrintf
0x18004f269  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x18004f270  mov     r8d, 92Dh
0x18004f276  jmp     loc_18004F423
0x18004f27b  mov     [rdi+38h], rbx
0x18004f27f  mov     qword ptr [rdi+28h], 10h
0x18004f287  mov     rdx, [rdi+8]; SourceString
0x18004f28b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004f28f  call    cs:__imp_RtlInitUnicodeString
0x18004f296  nop     dword ptr [rax+rax+00h]
0x18004f29b  mov     r8, [rdi+8]
0x18004f29f  lea     rdx, [rbp+DestinationString]
0x18004f2a3  mov     r9d, 1
0x18004f2a9  mov     [rsp+80h+var_58], r15w
0x18004f2af  lea     rcx, [rbp+var_20]
0x18004f2b3  mov     [rsp+80h+var_60], r15
0x18004f2b8  call    AslpPathWildcardAllocMatchNode
0x18004f2bd  mov     ebx, eax
0x18004f2bf  test    eax, eax
0x18004f2c1  jns     short loc_18004F2D9
0x18004f2c3  mov     dword ptr [rsp+80h+var_60], eax
0x18004f2c7  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x18004f2ce  mov     r8d, 93Ah
0x18004f2d4  jmp     loc_18004F427
0x18004f2d9  mov     r15, [rdi+20h]
0x18004f2dd  cmp     r15, [rdi+28h]
0x18004f2e1  jb      loc_18004F3B2
0x18004f2e7  lea     rcx, [r15+1]
0x18004f2eb  cmp     rcx, [rdi+28h]
0x18004f2ef  ja      short loc_18004F2FB
0x18004f2f1  mov     ebx, 0C000000Dh
0x18004f2f6  jmp     loc_18004F3A1
0x18004f2fb  mov     rbx, [rdi+30h]
0x18004f2ff  dec     rbx
0x18004f302  lea     r9, [rbx+rcx]
0x18004f306  cmp     r9, rcx
0x18004f309  jnb     short loc_18004F315
0x18004f30b  mov     ebx, 0C0000095h
0x18004f310  jmp     loc_18004F3A1
0x18004f315  mov     rdx, [rdi+18h]; ullMultiplier
0x18004f319  lea     r8, [rbp+pullResult]; pullResult
0x18004f31d  mov     rcx, [rdi+28h]; ullMultiplicand
0x18004f321  mov     [rbp+Size], r14
0x18004f325  call    ULongLongMult
0x18004f32a  test    eax, eax
0x18004f32c  js      short loc_18004F30B
0x18004f32e  mov     rdx, [rdi+18h]; ullMultiplier
0x18004f332  lea     r8, [rbp+Size]; pullResult
0x18004f336  not     rbx
0x18004f339  and     rbx, r9
0x18004f33c  mov     rcx, rbx; ullMultiplicand
0x18004f33f  call    ULongLongMult
0x18004f344  test    eax, eax
0x18004f346  js      short loc_18004F30B
0x18004f348  mov     r8, [rdi+38h]; Ptr
0x18004f34c  xor     edx, edx; Flags
0x18004f34e  mov     r13, [rbp+Size]
0x18004f352  mov     rcx, [rdi+10h]; Heap
0x18004f356  test    r8, r8
0x18004f359  jnz     short loc_18004F381
0x18004f35b  mov     r8, r13; Size
0x18004f35e  call    cs:__imp_RtlAllocateHeap
0x18004f365  nop     dword ptr [rax+rax+00h]
0x18004f36a  mov     rsi, rax
0x18004f36d  test    rax, rax
0x18004f370  jz      short loc_18004F393
0x18004f372  mov     r8, r13; Size
0x18004f375  xor     edx, edx; Val
0x18004f377  mov     rcx, rax; void *
0x18004f37a  call    memset_0
0x18004f37f  jmp     short loc_18004F393
0x18004f381  mov     r9, r13; Size
0x18004f384  call    cs:__imp_RtlReAllocateHeap
0x18004f38b  nop     dword ptr [rax+rax+00h]
0x18004f390  mov     rsi, rax
0x18004f393  mov     r13, [rbp+arg_0]
0x18004f397  test    rsi, rsi
0x18004f39a  jnz     short loc_18004F3AA
0x18004f39c  mov     ebx, 0C0000017h
0x18004f3a1  xor     r15d, r15d
0x18004f3a4  test    ebx, ebx
0x18004f3a6  jns     short loc_18004F3EE
  ... truncated ...
```
