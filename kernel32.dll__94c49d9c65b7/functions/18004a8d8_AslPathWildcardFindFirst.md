# AslPathWildcardFindFirst

- ea: `0x18004a8d8`
- end: `0x18004ae38`
- name: `AslPathWildcardFindFirst`
- size: `1376`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, loader_planting`

## callers

- `0x180078100`

## callees

- `0x18001ece0`
- `0x180021144`
- `0x1800212e4`
- `0x180032a3c`
- `0x180033588`
- `0x180041dd0`
- `0x180043d10`
- `0x18004a8d8`
- `0x18004e0c0`
- `0x18004e1b4`
- `0x180054d6c`
- `0x180055710`
- `0x18007053c`
- `0x180070bcc`
- `0x18007a7dd`
- `0x18007a819`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18004a96f`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18004a96f`
- `ntdll!RtlFreeUnicodeString` at `0x18004adda`
- `ntdll!RtlFreeUnicodeString` at `0x18004adda`
- `ntdll!RtlReAllocateHeap` at `0x18004abbc`
- `ntdll!RtlReAllocateHeap` at `0x18004ad28`
- `ntdll!RtlReAllocateHeap` at `0x18004abbc`
- `ntdll!RtlReAllocateHeap` at `0x18004ad28`
- `ntdll!RtlInitUnicodeString` at `0x18004ac3f`
- `ntdll!RtlInitUnicodeString` at `0x18004ac3f`
- `ntdll!RtlFreeHeap` at `0x18004abde`
- `ntdll!RtlFreeHeap` at `0x18004abde`
- `ntdll!RtlAllocateHeap` at `0x18004a9ff`
- `ntdll!RtlAllocateHeap` at `0x18004aae6`
- `ntdll!RtlAllocateHeap` at `0x18004ab9c`
- `ntdll!RtlAllocateHeap` at `0x18004ad08`
- `ntdll!RtlAllocateHeap` at `0x18004a9ff`
- `ntdll!RtlAllocateHeap` at `0x18004aae6`
- `ntdll!RtlAllocateHeap` at `0x18004ab9c`
- `ntdll!RtlAllocateHeap` at `0x18004ad08`

## string_xrefs

- `0x18004adb4`: `AslpPathWildcardPushNode failed [%x]`
- `0x18004a97f`: `Failed to convert dos path to nt path [%x]`
- `0x18004ac08`: `AslpPathWildcardInitStack`
- `0x18004a9a4`: `AslPathCleanUstr failed [%x]`
- `0x18004aa60`: `AslPathWildcardFindFirst`
- `0x18004adc5`: `AslPathWildcardFindFirst`
- `0x18004aa35`: `RtlStringCbCopyNW failed [%x]`
- `0x18004aab7`: `RtlStringCbCopyNW failed [%x]`
- `0x18004ac19`: `AslpPathWildcardInitStack failed [%x]`
- `0x18004aa53`: `Failed to split the wildcard path`
- `0x18004ac71`: `AslpPathWildcardAllocMatchNode failed to create root of path [%x]`

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
0x18004a8d8  mov     [rsp-38h+arg_10], rbx
0x18004a8dd  mov     [rsp-38h+Size], rdx
0x18004a8e2  mov     [rsp-38h+arg_0], rcx
0x18004a8e7  push    rbp
0x18004a8e8  push    rsi
0x18004a8e9  push    rdi
0x18004a8ea  push    r12
0x18004a8ec  push    r13
0x18004a8ee  push    r14
0x18004a8f0  push    r15
0x18004a8f2  mov     rbp, rsp
0x18004a8f5  sub     rsp, 80h
0x18004a8fc  xor     r15d, r15d
0x18004a8ff  mov     r12, r9
0x18004a902  mov     rsi, r8
0x18004a905  mov     r13, rcx
0x18004a908  test    rcx, rcx
0x18004a90b  jnz     short loc_18004A917
0x18004a90d  mov     eax, 0C00000EFh
0x18004a912  jmp     loc_18004AE1D
0x18004a917  test    rsi, rsi
0x18004a91a  jz      loc_18004AE18
0x18004a920  cmp     [r8], r15w
0x18004a924  jz      loc_18004AE18
0x18004a92a  test    r12, r12
0x18004a92d  jnz     short loc_18004A939
0x18004a92f  mov     eax, 0C00000F2h
0x18004a934  jmp     loc_18004AE1D
0x18004a939  xorps   xmm0, xmm0
0x18004a93c  mov     [r9], r15
0x18004a93f  xorps   xmm1, xmm1
0x18004a942  mov     [rcx], r15w
0x18004a946  xor     r9d, r9d
0x18004a949  mov     [rbp+var_50], r15
0x18004a94d  mov     rcx, rsi
0x18004a950  mov     word ptr [rbp+Size], r15w
0x18004a955  xor     r8d, r8d
0x18004a958  lea     rdx, [rbp+UnicodeString]
0x18004a95c  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18004a960  mov     r14, r15
0x18004a963  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004a967  movups  [rbp+var_20], xmm1
0x18004a96b  movups  [rbp+var_10], xmm1
0x18004a96f  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18004a975  mov     ebx, eax
0x18004a977  test    eax, eax
0x18004a979  jns     short loc_18004A991
0x18004a97b  mov     dword ptr [rsp+80h+var_60], eax
0x18004a97f  lea     r9, aFailedToConver_0; "Failed to convert dos path to nt path ["...
0x18004a986  mov     r8d, 8C6h
0x18004a98c  jmp     loc_18004ADC5
0x18004a991  lea     rcx, [rbp+UnicodeString]
0x18004a995  call    AslPathCleanUstr
0x18004a99a  mov     ebx, eax
0x18004a99c  test    eax, eax
0x18004a99e  jns     short loc_18004A9B6
0x18004a9a0  mov     dword ptr [rsp+80h+var_60], eax
0x18004a9a4  lea     r9, aAslpathcleanus; "AslPathCleanUstr failed [%x]"
0x18004a9ab  mov     r8d, 8D1h
0x18004a9b1  jmp     loc_18004ADC5
0x18004a9b6  movzx   ecx, [rbp+UnicodeString.Length]
0x18004a9ba  lea     r8, [rbp+Size]
0x18004a9be  mov     edx, 4
0x18004a9c3  call    RtlUShortAdd
0x18004a9c8  mov     ebx, eax
0x18004a9ca  test    eax, eax
0x18004a9cc  jns     short loc_18004A9E4
0x18004a9ce  mov     dword ptr [rsp+80h+var_60], eax
0x18004a9d2  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x18004a9d9  mov     r8d, 8D7h
0x18004a9df  jmp     loc_18004ADC5
0x18004a9e4  mov     rcx, gs:60h
0x18004a9ed  mov     edi, 8
0x18004a9f2  movzx   ebx, word ptr [rbp+Size]
0x18004a9f6  mov     edx, edi; Flags
0x18004a9f8  mov     r8d, ebx; Size
0x18004a9fb  mov     rcx, [rcx+30h]; HeapHandle
0x18004a9ff  call    cs:__imp_RtlAllocateHeap
0x18004aa05  mov     r14, rax
0x18004aa08  test    rax, rax
0x18004aa0b  jnz     short loc_18004AA17
0x18004aa0d  mov     ebx, 0C0000017h
0x18004aa12  jmp     loc_18004ADD6
0x18004aa17  movzx   r9d, [rbp+UnicodeString.Length]
0x18004aa1c  mov     rdx, rbx
0x18004aa1f  mov     r8, [rbp+UnicodeString.Buffer]
0x18004aa23  mov     rcx, r14
0x18004aa26  call    RtlStringCbCopyNW
0x18004aa2b  mov     ebx, eax
0x18004aa2d  test    eax, eax
0x18004aa2f  jns     short loc_18004AA47
0x18004aa31  mov     dword ptr [rsp+80h+var_60], eax
0x18004aa35  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x18004aa3c  mov     r8d, 8E3h
0x18004aa42  jmp     loc_18004ADC5
0x18004aa47  mov     rcx, r14; SourceString
0x18004aa4a  call    AslpPathWildcardMakeLeaves
0x18004aa4f  test    eax, eax
0x18004aa51  jnz     short loc_18004AA79
0x18004aa53  lea     r9, aFailedToSplitT; "Failed to split the wildcard path"
0x18004aa5a  mov     r8d, 8F5h
0x18004aa60  lea     rdx, aAslpathwildcar_1; "AslPathWildcardFindFirst"
0x18004aa67  mov     ebx, 0C0000039h
0x18004aa6c  lea     ecx, [rax+1]
0x18004aa6f  call    AslLogCallPrintf
0x18004aa74  jmp     loc_18004ADD6
0x18004aa79  cmp     eax, 1
0x18004aa7c  jnz     short loc_18004AAD1
0x18004aa7e  mov     rcx, [rbp+UnicodeString.Buffer]; FileName
0x18004aa82  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x18004aa8a  call    AslDoesFileExistNtPath
0x18004aa8f  test    eax, eax
0x18004aa91  jnz     short loc_18004AA9D
0x18004aa93  mov     ebx, 80000006h
0x18004aa98  jmp     loc_18004ADD6
0x18004aa9d  mov     r8, rsi
0x18004aaa0  mov     edx, 104h
0x18004aaa5  mov     rcx, r13
0x18004aaa8  call    RtlStringCchCopyW
0x18004aaad  mov     ebx, eax
0x18004aaaf  test    eax, eax
0x18004aab1  jns     short loc_18004AAC9
0x18004aab3  mov     dword ptr [rsp+80h+var_60], eax
0x18004aab7  lea     r9, aRtlstringcbcop; "RtlStringCbCopyNW failed [%x]"
0x18004aabe  mov     r8d, 907h
0x18004aac4  jmp     loc_18004ADC5
0x18004aac9  mov     ebx, r15d
0x18004aacc  jmp     loc_18004ADD6
0x18004aad1  mov     rcx, gs:60h
0x18004aada  mov     r8d, 40h ; '@'; Size
0x18004aae0  mov     edx, edi; Flags
0x18004aae2  mov     rcx, [rcx+30h]; HeapHandle
0x18004aae6  call    cs:__imp_RtlAllocateHeap
0x18004aaec  mov     [rbp+var_50], rax
0x18004aaf0  mov     rdi, rax
0x18004aaf3  test    rax, rax
0x18004aaf6  jz      loc_18004AA0D
0x18004aafc  mov     r8d, 4; MaxCount
0x18004ab02  lea     rdx, asc_1800881F8; "\\??\\"
0x18004ab09  mov     rcx, rsi; String1
0x18004ab0c  call    wcsncmp_0
0x18004ab11  test    eax, eax
0x18004ab13  mov     [rbp+Size], r15
0x18004ab17  mov     ecx, r15d
0x18004ab1a  lea     r8, [rbp+pullResult]; pullResult
0x18004ab1e  setnz   cl
0x18004ab21  xorps   xmm0, xmm0
0x18004ab24  mov     [rdi], ecx
0x18004ab26  mov     r10d, 10h
0x18004ab2c  mov     [rdi+8], r14
0x18004ab30  mov     r14, r15
0x18004ab33  movups  xmmword ptr [rdi+10h], xmm0
0x18004ab37  movups  xmmword ptr [rdi+20h], xmm0
0x18004ab3b  lea     edx, [r10+10h]; ullMultiplier
0x18004ab3f  movups  xmmword ptr [rdi+30h], xmm0
0x18004ab43  mov     rax, gs:60h
0x18004ab4c  mov     rcx, [rax+30h]
0x18004ab50  mov     [rdi+10h], rcx
0x18004ab54  xor     ecx, ecx; ullMultiplicand
0x18004ab56  mov     [rdi+30h], r10
0x18004ab5a  mov     [rdi+18h], rdx
0x18004ab5e  call    ULongLongMult
0x18004ab63  mov     r9d, 0C0000095h
0x18004ab69  test    eax, eax
0x18004ab6b  jns     short loc_18004AB72
0x18004ab6d  mov     ebx, r9d
0x18004ab70  jmp     short loc_18004ABCF
0x18004ab72  mov     rdx, [rdi+18h]; ullMultiplier
0x18004ab76  lea     r8, [rbp+Size]; pullResult
0x18004ab7a  mov     rcx, r10; ullMultiplicand
0x18004ab7d  call    ULongLongMult
0x18004ab82  test    eax, eax
0x18004ab84  js      short loc_18004AB6D
0x18004ab86  mov     r8, [rdi+38h]; Ptr
0x18004ab8a  xor     edx, edx; Flags
0x18004ab8c  mov     rsi, [rbp+Size]
0x18004ab90  mov     rcx, [rdi+10h]; Heap
0x18004ab94  test    r8, r8
0x18004ab97  jnz     short loc_18004ABB9
0x18004ab99  mov     r8, rsi; Size
0x18004ab9c  call    cs:__imp_RtlAllocateHeap
0x18004aba2  mov     rbx, rax
0x18004aba5  test    rax, rax
0x18004aba8  jz      short loc_18004ABC5
0x18004abaa  mov     r8, rsi; Size
0x18004abad  xor     edx, edx; Val
0x18004abaf  mov     rcx, rax; void *
0x18004abb2  call    memset_0
0x18004abb7  jmp     short loc_18004ABC5
0x18004abb9  mov     r9, rsi; Size
0x18004abbc  call    cs:__imp_RtlReAllocateHeap
0x18004abc2  mov     rbx, rax
0x18004abc5  test    rbx, rbx
0x18004abc8  jnz     short loc_18004AC2B
0x18004abca  mov     ebx, 0C0000017h
0x18004abcf  mov     r8, [rdi+38h]; P
0x18004abd3  test    r8, r8
0x18004abd6  jz      short loc_18004ABE4
0x18004abd8  mov     rcx, [rdi+10h]; HeapHandle
0x18004abdc  xor     edx, edx; Flags
0x18004abde  call    cs:__imp_RtlFreeHeap
0x18004abe4  xorps   xmm0, xmm0
0x18004abe7  movups  xmmword ptr [rdi+10h], xmm0
0x18004abeb  movups  xmmword ptr [rdi+20h], xmm0
0x18004abef  movups  xmmword ptr [rdi+30h], xmm0
0x18004abf3  test    ebx, ebx
0x18004abf5  jns     short loc_18004AC37
0x18004abf7  lea     r9, aRtlarrayinitia; "RtlArrayInitialize failed [%x]"
0x18004abfe  mov     dword ptr [rsp+80h+var_60], ebx
0x18004ac02  mov     r8d, 864h
0x18004ac08  lea     rdx, aAslppathwildca_6; "AslpPathWildcardInitStack"
0x18004ac0f  mov     ecx, 1
0x18004ac14  call    AslLogCallPrintf
0x18004ac19  lea     r9, aAslppathwildca_2; "AslpPathWildcardInitStack failed [%x]"
0x18004ac20  mov     r8d, 92Dh
0x18004ac26  jmp     loc_18004ADC1
0x18004ac2b  mov     [rdi+38h], rbx
0x18004ac2f  mov     qword ptr [rdi+28h], 10h
0x18004ac37  mov     rdx, [rdi+8]; SourceString
0x18004ac3b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004ac3f  call    cs:__imp_RtlInitUnicodeString
0x18004ac45  mov     r8, [rdi+8]
0x18004ac49  lea     rdx, [rbp+DestinationString]
0x18004ac4d  mov     r9d, 1
0x18004ac53  mov     [rsp+80h+var_58], r15w
0x18004ac59  lea     rcx, [rbp+var_20]
0x18004ac5d  mov     [rsp+80h+var_60], r15
0x18004ac62  call    AslpPathWildcardAllocMatchNode
0x18004ac67  mov     ebx, eax
0x18004ac69  test    eax, eax
0x18004ac6b  jns     short loc_18004AC83
0x18004ac6d  mov     dword ptr [rsp+80h+var_60], eax
0x18004ac71  lea     r9, aAslppathwildca_0; "AslpPathWildcardAllocMatchNode failed t"...
0x18004ac78  mov     r8d, 93Ah
0x18004ac7e  jmp     loc_18004ADC5
0x18004ac83  mov     r15, [rdi+20h]
0x18004ac87  cmp     r15, [rdi+28h]
0x18004ac8b  jb      loc_18004AD50
0x18004ac91  lea     rcx, [r15+1]
0x18004ac95  cmp     rcx, [rdi+28h]
0x18004ac99  ja      short loc_18004ACA5
0x18004ac9b  mov     ebx, 0C000000Dh
0x18004aca0  jmp     loc_18004AD3F
0x18004aca5  mov     rbx, [rdi+30h]
0x18004aca9  dec     rbx
0x18004acac  lea     r9, [rbx+rcx]
0x18004acb0  cmp     r9, rcx
0x18004acb3  jnb     short loc_18004ACBF
0x18004acb5  mov     ebx, 0C0000095h
0x18004acba  jmp     loc_18004AD3F
0x18004acbf  mov     rdx, [rdi+18h]; ullMultiplier
0x18004acc3  lea     r8, [rbp+pullResult]; pullResult
0x18004acc7  mov     rcx, [rdi+28h]; ullMultiplicand
0x18004accb  mov     [rbp+Size], r14
0x18004accf  call    ULongLongMult
0x18004acd4  test    eax, eax
0x18004acd6  js      short loc_18004ACB5
0x18004acd8  mov     rdx, [rdi+18h]; ullMultiplier
0x18004acdc  lea     r8, [rbp+Size]; pullResult
0x18004ace0  not     rbx
0x18004ace3  and     rbx, r9
0x18004ace6  mov     rcx, rbx; ullMultiplicand
0x18004ace9  call    ULongLongMult
0x18004acee  test    eax, eax
0x18004acf0  js      short loc_18004ACB5
0x18004acf2  mov     r8, [rdi+38h]; Ptr
0x18004acf6  xor     edx, edx; Flags
0x18004acf8  mov     r13, [rbp+Size]
0x18004acfc  mov     rcx, [rdi+10h]; Heap
0x18004ad00  test    r8, r8
0x18004ad03  jnz     short loc_18004AD25
0x18004ad05  mov     r8, r13; Size
0x18004ad08  call    cs:__imp_RtlAllocateHeap
0x18004ad0e  mov     rsi, rax
0x18004ad11  test    rax, rax
0x18004ad14  jz      short loc_18004AD31
0x18004ad16  mov     r8, r13; Size
0x18004ad19  xor     edx, edx; Val
0x18004ad1b  mov     rcx, rax; void *
0x18004ad1e  call    memset_0
0x18004ad23  jmp     short loc_18004AD31
0x18004ad25  mov     r9, r13; Size
0x18004ad28  call    cs:__imp_RtlReAllocateHeap
0x18004ad2e  mov     rsi, rax
0x18004ad31  mov     r13, [rbp+arg_0]
0x18004ad35  test    rsi, rsi
0x18004ad38  jnz     short loc_18004AD48
0x18004ad3a  mov     ebx, 0C0000017h
0x18004ad3f  xor     r15d, r15d
0x18004ad42  test    ebx, ebx
0x18004ad44  jns     short loc_18004AD8C
0x18004ad46  jmp     short loc_18004ADB4
0x18004ad48  mov     [rdi+38h], rsi
0x18004ad4c  mov     [rdi+28h], rbx
0x18004ad50  mov     rcx, [rdi+18h]; ullMultiplicand
0x18004ad54  lea     r8, [rbp+Size]; pullResult
0x18004ad58  mov     rdx, r15; ullMultiplier
0x18004ad5b  mov     [rbp+Size], r14
0x18004ad5f  call    ULongLongMult
0x18004ad64  xor     r15d, r15d
  ... truncated ...
```
