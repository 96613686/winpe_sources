# FileUtility::GetFullTempFilePath(void)

- ea: `0x14000be30`
- end: `0x14000c0d7`
- name: `?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `679`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14000d760`

## callees

- `0x140002288`
- `0x140008b88`
- `0x140008e50`
- `0x14000a3b8`
- `0x14000be30`
- `0x14000ded0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x14000c025`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000c025`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bec1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c043`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bec1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c043`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000beb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c035`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000beb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c035`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bec9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000beab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000beab`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000bf8c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000bf8c`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x14000bfdc`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x14000bfdc`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x14000be83`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x14000be83`
- `CRYPT32!CryptBinaryToStringW` at `0x14000bfba`
- `CRYPT32!CryptBinaryToStringW` at `0x14000bfba`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall FileUtility::GetFullTempFilePath(_QWORD *a1)
{
  int BasicProfileFolderPathAlloc; // eax
  void *v3; // r15
  LPVOID *v4; // rdi
  void *v5; // r14
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v8; // rbx
  unsigned __int64 v9; // rdx
  size_t v10; // r14
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  __int64 v13; // rcx
  WCHAR *v14; // r8
  size_t v15; // rdx
  WCHAR v16; // r9
  WCHAR *v17; // rcx
  HRESULT v18; // eax
  const char *v19; // r9
  HRESULT v20; // eax
  void *v21; // rbx
  HANDLE v22; // rax
  int pcchString; // [rsp+20h] [rbp-89h]
  int pcchStringa; // [rsp+20h] [rbp-89h]
  LPVOID lpMem; // [rsp+30h] [rbp-79h] BYREF
  DWORD v27; // [rsp+38h] [rbp-71h] BYREF
  LPVOID *p_lpMem; // [rsp+40h] [rbp-69h]
  void *v29; // [rsp+48h] [rbp-61h] BYREF
  char v30; // [rsp+50h] [rbp-59h]
  WCHAR *v31; // [rsp+60h] [rbp-49h]
  GUID pguid; // [rsp+68h] [rbp-41h] BYREF
  WCHAR pszString[40]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  lpMem = 0;
  p_lpMem = &lpMem;
  v29 = 0;
  v30 = 1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, 0, &v29);
  if ( BasicProfileFolderPathAlloc < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      pcchString);
  if ( v30 )
  {
    v3 = v29;
    v4 = p_lpMem;
    v5 = *p_lpMem;
    if ( *p_lpMem )
    {
      LastError = GetLastError();
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      SetLastError(LastError);
    }
    *v4 = v3;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)lpMem + v9) );
  if ( v9 + 46 < v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      v9 + 46 < v9 ? (const char *)0x80070216LL : 0,
      pcchString);
  v10 = v9 + 46;
  v11 = (WCHAR *)operator new[](saturated_mul(v9 + 46, 2u));
  v12 = v11;
  v31 = v11;
  if ( v10 )
  {
    if ( v10 <= 0x7FFFFFFF )
    {
      v13 = 2147483646;
      v14 = (WCHAR *)lpMem;
      v15 = v10;
      do
      {
        if ( !v13 )
          break;
        v16 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        *v11++ = v16;
        --v13;
        --v15;
      }
      while ( v15 );
      v17 = v11 - 1;
      if ( v15 )
        v17 = v11;
      *v17 = 0;
    }
    else
    {
      *v11 = 0;
    }
  }
  pguid = 0;
  v27 = 38;
  v18 = CoCreateGuid(&pguid);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v18,
      pcchString);
  if ( !CryptBinaryToStringW((const BYTE *)&pguid, 0x10u, 0x4000000Cu, pszString, &v27) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      v19);
  v20 = PathCchAppendEx(v12, v10, pszString, 1u);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v20,
      pcchStringa);
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  if ( *v12 )
  {
    do
      ++v8;
    while ( v12[v8] );
  }
  std::wstring::assign(a1, v12);
  operator delete[](v12);
  v21 = lpMem;
  if ( lpMem )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
  }
  return a1;
}

```

## disassembly

```asm
0x14000be30  mov     [rsp-8+arg_8], rbx
0x14000be35  mov     [rsp-8+arg_10], rsi
0x14000be3a  push    rbp
0x14000be3b  push    rdi
0x14000be3c  push    r12
0x14000be3e  push    r14
0x14000be40  push    r15
0x14000be42  lea     rbp, [rsp-37h]
0x14000be47  sub     rsp, 0E0h
0x14000be4e  mov     rax, cs:__security_cookie
0x14000be55  xor     rax, rsp
0x14000be58  mov     [rbp+57h+var_30], rax
0x14000be5c  mov     rsi, rcx
0x14000be5f  mov     [rbp+57h+lpMem], rcx
0x14000be63  xor     r12d, r12d
0x14000be66  mov     [rbp+57h+lpMem], r12
0x14000be6a  lea     rax, [rbp+57h+lpMem]
0x14000be6e  mov     [rbp+57h+var_C0], rax
0x14000be72  mov     [rbp+57h+var_B8], r12
0x14000be76  mov     [rbp+57h+var_B0], 1
0x14000be7a  lea     r8, [rbp+57h+var_B8]
0x14000be7e  xor     edx, edx
0x14000be80  lea     ecx, [rdx+6]
0x14000be83  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x14000be89  mov     rcx, [rbp+5Fh]; this
0x14000be8d  test    eax, eax
0x14000be8f  js      loc_14000C089
0x14000be95  cmp     [rbp+57h+var_B0], r12b
0x14000be99  jz      short loc_14000BED2
0x14000be9b  mov     r15, [rbp+57h+var_B8]
0x14000be9f  mov     rdi, [rbp+57h+var_C0]
0x14000bea3  mov     r14, [rdi]
0x14000bea6  test    r14, r14
0x14000bea9  jz      short loc_14000BECF
0x14000beab  call    cs:__imp_GetLastError
0x14000beb1  mov     ebx, eax
0x14000beb3  call    cs:__imp_GetProcessHeap
0x14000beb9  mov     rcx, rax; hHeap
0x14000bebc  mov     r8, r14; lpMem
0x14000bebf  xor     edx, edx; dwFlags
0x14000bec1  call    cs:__imp_HeapFree
0x14000bec7  mov     ecx, ebx; dwErrCode
0x14000bec9  call    cs:__imp_SetLastError
0x14000becf  mov     [rdi], r15
0x14000bed2  mov     rax, [rbp+57h+lpMem]
0x14000bed6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000beda  mov     rdx, rbx
0x14000bedd  inc     rdx
0x14000bee0  cmp     [rax+rdx*2], r12w
0x14000bee5  jnz     short loc_14000BEDD
0x14000bee7  lea     rax, [rdx+2Eh]
0x14000beeb  mov     r14, rbx
0x14000beee  cmp     rax, rdx
0x14000bef1  cmovnb  r14, rax
0x14000bef5  sbb     r9d, r9d
0x14000bef8  and     r9d, 80070216h; char *
0x14000beff  mov     rcx, [rbp+5Fh]; this
0x14000bf03  cmp     rax, rdx
0x14000bf06  jb      loc_14000C09E
0x14000bf0c  mov     eax, 2
0x14000bf11  mul     r14
0x14000bf14  cmovb   rax, rbx
0x14000bf18  mov     rcx, rax; unsigned __int64
0x14000bf1b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000bf20  mov     rdi, rax
0x14000bf23  mov     [rbp+57h+var_A0], rax
0x14000bf27  test    r14, r14
0x14000bf2a  jz      short loc_14000BF7A
0x14000bf2c  cmp     r14, 7FFFFFFFh
0x14000bf33  jbe     short loc_14000BF3B
0x14000bf35  mov     [rax], r12w
0x14000bf39  jmp     short loc_14000BF7A
0x14000bf3b  mov     ecx, 7FFFFFFEh
0x14000bf40  mov     r8, [rbp+57h+lpMem]
0x14000bf44  mov     rdx, r14
0x14000bf47  test    rcx, rcx
0x14000bf4a  jz      short loc_14000BF6B
0x14000bf4c  movzx   r9d, word ptr [r8]
0x14000bf50  test    r9w, r9w
0x14000bf54  jz      short loc_14000BF6B
0x14000bf56  add     r8, 2
0x14000bf5a  mov     [rax], r9w
0x14000bf5e  add     rax, 2
0x14000bf62  dec     rcx
0x14000bf65  sub     rdx, 1
0x14000bf69  jnz     short loc_14000BF47
0x14000bf6b  lea     rcx, [rax-2]
0x14000bf6f  test    rdx, rdx
0x14000bf72  cmovnz  rcx, rax
0x14000bf76  mov     [rcx], r12w
0x14000bf7a  xorps   xmm0, xmm0
0x14000bf7d  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x14000bf81  mov     [rbp+57h+var_C8], 26h ; '&'
0x14000bf88  lea     rcx, [rbp+57h+pguid]; pguid
0x14000bf8c  call    cs:__imp_CoCreateGuid
0x14000bf92  mov     rcx, [rbp+5Fh]; this
0x14000bf96  test    eax, eax
0x14000bf98  js      loc_14000C0B0
0x14000bf9e  lea     rax, [rbp+57h+var_C8]
0x14000bfa2  mov     qword ptr [rsp+100h+pcchString], rax; int
0x14000bfa7  lea     r9, [rbp+57h+pszString]; pszString
0x14000bfab  mov     edx, 10h; cbBinary
0x14000bfb0  mov     r8d, 4000000Ch; dwFlags
0x14000bfb6  lea     rcx, [rbp+57h+pguid]; pbBinary
0x14000bfba  call    cs:__imp_CryptBinaryToStringW
0x14000bfc0  mov     rcx, [rbp+5Fh]; this
0x14000bfc4  test    eax, eax
0x14000bfc6  jz      loc_14000C0C5
0x14000bfcc  mov     r9d, 1; dwFlags
0x14000bfd2  lea     r8, [rbp+57h+pszString]; pszMore
0x14000bfd6  mov     rdx, r14; cchPath
0x14000bfd9  mov     rcx, rdi; pszPath
0x14000bfdc  call    cs:__imp_PathCchAppendEx
0x14000bfe2  mov     rcx, [rbp+5Fh]; this
0x14000bfe6  test    eax, eax
0x14000bfe8  js      loc_14000C074
0x14000bfee  mov     qword ptr [rsi+18h], 7
0x14000bff6  mov     [rsi+10h], r12
0x14000bffa  mov     [rsi], r12w
0x14000bffe  cmp     [rdi], r12w
0x14000c002  jnz     short loc_14000C009
0x14000c004  mov     rbx, r12
0x14000c007  jmp     short loc_14000C013
0x14000c009  inc     rbx
0x14000c00c  cmp     [rdi+rbx*2], r12w
0x14000c011  jnz     short loc_14000C009
0x14000c013  mov     r8, rbx
0x14000c016  mov     rdx, rdi; Src
0x14000c019  mov     rcx, rsi; void *
0x14000c01c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000c021  nop
0x14000c022  mov     rcx, rdi
0x14000c025  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14000c02b  nop
0x14000c02c  mov     rbx, [rbp+57h+lpMem]
0x14000c030  test    rbx, rbx
0x14000c033  jz      short loc_14000C049
0x14000c035  call    cs:__imp_GetProcessHeap
0x14000c03b  mov     rcx, rax; hHeap
0x14000c03e  mov     r8, rbx; lpMem
0x14000c041  xor     edx, edx; dwFlags
0x14000c043  call    cs:__imp_HeapFree
0x14000c049  mov     rax, rsi
0x14000c04c  mov     rcx, [rbp+57h+var_30]
0x14000c050  xor     rcx, rsp; StackCookie
0x14000c053  call    __security_check_cookie
0x14000c058  lea     r11, [rsp+100h+var_20]
0x14000c060  mov     rbx, [r11+38h]
0x14000c064  mov     rsi, [r11+40h]
0x14000c068  mov     rsp, r11
0x14000c06b  pop     r15
0x14000c06d  pop     r14
0x14000c06f  pop     r12
0x14000c071  pop     rdi
0x14000c072  pop     rbp
0x14000c073  retn
0x14000c074  mov     r9d, eax; char *
0x14000c077  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x14000c07e  mov     edx, 1Eh; void *
0x14000c083  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c089  mov     r9d, eax; char *
0x14000c08c  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x14000c093  mov     edx, 0Ch; void *
0x14000c098  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c09e  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x14000c0a5  mov     edx, 10h; void *
0x14000c0aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c0b0  mov     r9d, eax; char *
0x14000c0b3  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x14000c0ba  mov     edx, 19h; void *
0x14000c0bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14000c0c5  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x14000c0cc  mov     edx, 1Bh; void *
0x14000c0d1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
