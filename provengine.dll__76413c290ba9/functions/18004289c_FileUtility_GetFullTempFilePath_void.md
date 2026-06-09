# FileUtility::GetFullTempFilePath(void)

- ea: `0x18004289c`
- end: `0x180042aff`
- name: `?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `611`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180042f20`

## callees

- `0x180002e70`
- `0x18000a0f8`
- `0x18000b030`
- `0x180021cd8`
- `0x180021cf4`
- `0x18004289c`
- `0x180043750`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180042a4d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180042a4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004291f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042a5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004291f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042a5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004292d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042a6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004292d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042a6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042917`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800429b4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800429b4`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180042a04`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180042a04`
- `CRYPT32!CryptBinaryToStringW` at `0x1800429e2`
- `CRYPT32!CryptBinaryToStringW` at `0x1800429e2`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800428ef`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800428ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall FileUtility::GetFullTempFilePath(_QWORD *a1)
{
  int BasicProfileFolderPathAlloc; // eax
  void *v3; // r15
  LPVOID *v4; // rdi
  void *v5; // r14
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // r14
  unsigned __int16 *v11; // rbx
  HRESULT v12; // eax
  const char *v13; // r9
  HRESULT v14; // eax
  void *v15; // rbx
  HANDLE v16; // rax
  int pcchString; // [rsp+20h] [rbp-89h]
  int pcchStringa; // [rsp+20h] [rbp-89h]
  LPVOID lpMem; // [rsp+30h] [rbp-79h] BYREF
  DWORD v21; // [rsp+38h] [rbp-71h] BYREF
  LPVOID *p_lpMem; // [rsp+40h] [rbp-69h]
  void *v23; // [rsp+48h] [rbp-61h] BYREF
  char v24; // [rsp+50h] [rbp-59h]
  unsigned __int16 *v25; // [rsp+60h] [rbp-49h]
  GUID pguid; // [rsp+68h] [rbp-41h] BYREF
  WCHAR pszString[40]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  lpMem = 0;
  p_lpMem = &lpMem;
  v23 = 0;
  v24 = 1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, 0, &v23);
  if ( BasicProfileFolderPathAlloc < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      pcchString);
  if ( v24 )
  {
    v3 = v23;
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
  v11 = (unsigned __int16 *)operator new[](saturated_mul(v9 + 46, 2u));
  v25 = v11;
  StringCchCopyW(v11, v10, (const unsigned __int16 *)lpMem);
  pguid = 0;
  v21 = 38;
  v12 = CoCreateGuid(&pguid);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v12,
      pcchString);
  if ( !CryptBinaryToStringW((const BYTE *)&pguid, 0x10u, 0x4000000Cu, pszString, &v21) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      v13);
  v14 = PathCchAppendEx(v11, v10, pszString, 1u);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v14,
      pcchStringa);
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  if ( *v11 )
  {
    do
      ++v8;
    while ( v11[v8] );
  }
  else
  {
    v8 = 0;
  }
  std::wstring::assign(a1, (char *)v11, v8);
  operator delete[](v11);
  v15 = lpMem;
  if ( lpMem )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
  }
  return a1;
}

```

## disassembly

```asm
0x18004289c  mov     [rsp-8+arg_8], rbx
0x1800428a1  mov     [rsp-8+arg_10], rsi
0x1800428a6  push    rbp
0x1800428a7  push    rdi
0x1800428a8  push    r12
0x1800428aa  push    r14
0x1800428ac  push    r15
0x1800428ae  lea     rbp, [rsp-37h]
0x1800428b3  sub     rsp, 0E0h
0x1800428ba  mov     rax, cs:__security_cookie
0x1800428c1  xor     rax, rsp
0x1800428c4  mov     [rbp+57h+var_30], rax
0x1800428c8  mov     rsi, rcx
0x1800428cb  mov     [rbp+57h+lpMem], rcx
0x1800428cf  xor     r12d, r12d
0x1800428d2  mov     [rbp+57h+lpMem], r12
0x1800428d6  lea     rax, [rbp+57h+lpMem]
0x1800428da  mov     [rbp+57h+var_C0], rax
0x1800428de  mov     [rbp+57h+var_B8], r12
0x1800428e2  mov     [rbp+57h+var_B0], 1
0x1800428e6  lea     r8, [rbp+57h+var_B8]
0x1800428ea  xor     edx, edx
0x1800428ec  lea     ecx, [rdx+6]
0x1800428ef  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x1800428f5  mov     rcx, [rbp+5Fh]; this
0x1800428f9  test    eax, eax
0x1800428fb  js      loc_180042AB1
0x180042901  cmp     [rbp+57h+var_B0], r12b
0x180042905  jz      short loc_18004293E
0x180042907  mov     r15, [rbp+57h+var_B8]
0x18004290b  mov     rdi, [rbp+57h+var_C0]
0x18004290f  mov     r14, [rdi]
0x180042912  test    r14, r14
0x180042915  jz      short loc_18004293B
0x180042917  call    cs:__imp_GetLastError
0x18004291d  mov     ebx, eax
0x18004291f  call    cs:__imp_GetProcessHeap
0x180042925  mov     rcx, rax; hHeap
0x180042928  mov     r8, r14; lpMem
0x18004292b  xor     edx, edx; dwFlags
0x18004292d  call    cs:__imp_HeapFree
0x180042933  mov     ecx, ebx; dwErrCode
0x180042935  call    cs:__imp_SetLastError
0x18004293b  mov     [rdi], r15
0x18004293e  mov     rax, [rbp+57h+lpMem]
0x180042942  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180042946  mov     rdx, rdi
0x180042949  inc     rdx
0x18004294c  cmp     [rax+rdx*2], r12w
0x180042951  jnz     short loc_180042949
0x180042953  lea     rax, [rdx+2Eh]
0x180042957  mov     r14, rdi
0x18004295a  cmp     rax, rdx
0x18004295d  cmovnb  r14, rax
0x180042961  sbb     r9d, r9d
0x180042964  and     r9d, 80070216h; char *
0x18004296b  mov     rcx, [rbp+5Fh]; this
0x18004296f  cmp     rax, rdx
0x180042972  jb      loc_180042AC6
0x180042978  mov     eax, 2
0x18004297d  mul     r14
0x180042980  cmovb   rax, rdi
0x180042984  mov     rcx, rax; unsigned __int64
0x180042987  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004298c  mov     rbx, rax
0x18004298f  mov     [rbp+57h+var_A0], rax
0x180042993  mov     r8, [rbp+57h+lpMem]; unsigned __int16 *
0x180042997  mov     rdx, r14; unsigned __int64
0x18004299a  mov     rcx, rax; unsigned __int16 *
0x18004299d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800429a2  xorps   xmm0, xmm0
0x1800429a5  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800429a9  mov     [rbp+57h+var_C8], 26h ; '&'
0x1800429b0  lea     rcx, [rbp+57h+pguid]; pguid
0x1800429b4  call    cs:__imp_CoCreateGuid
0x1800429ba  mov     rcx, [rbp+5Fh]; this
0x1800429be  test    eax, eax
0x1800429c0  js      loc_180042AD8
0x1800429c6  lea     rax, [rbp+57h+var_C8]
0x1800429ca  mov     qword ptr [rsp+100h+pcchString], rax; int
0x1800429cf  lea     r9, [rbp+57h+pszString]; pszString
0x1800429d3  mov     edx, 10h; cbBinary
0x1800429d8  mov     r8d, 4000000Ch; dwFlags
0x1800429de  lea     rcx, [rbp+57h+pguid]; pbBinary
0x1800429e2  call    cs:__imp_CryptBinaryToStringW
0x1800429e8  mov     rcx, [rbp+5Fh]; this
0x1800429ec  test    eax, eax
0x1800429ee  jz      loc_180042AED
0x1800429f4  mov     r9d, 1; dwFlags
0x1800429fa  lea     r8, [rbp+57h+pszString]; pszMore
0x1800429fe  mov     rdx, r14; cchPath
0x180042a01  mov     rcx, rbx; pszPath
0x180042a04  call    cs:__imp_PathCchAppendEx
0x180042a0a  mov     rcx, [rbp+5Fh]; this
0x180042a0e  test    eax, eax
0x180042a10  js      loc_180042A9C
0x180042a16  mov     qword ptr [rsi+18h], 7
0x180042a1e  mov     [rsi+10h], r12
0x180042a22  mov     [rsi], r12w
0x180042a26  cmp     [rbx], r12w
0x180042a2a  jnz     short loc_180042A31
0x180042a2c  mov     rdi, r12
0x180042a2f  jmp     short loc_180042A3B
0x180042a31  inc     rdi
0x180042a34  cmp     [rbx+rdi*2], r12w
0x180042a39  jnz     short loc_180042A31
0x180042a3b  mov     r8, rdi
0x180042a3e  mov     rdx, rbx; Src
0x180042a41  mov     rcx, rsi; void *
0x180042a44  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180042a49  nop
0x180042a4a  mov     rcx, rbx
0x180042a4d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180042a53  nop
0x180042a54  mov     rbx, [rbp+57h+lpMem]
0x180042a58  test    rbx, rbx
0x180042a5b  jz      short loc_180042A71
0x180042a5d  call    cs:__imp_GetProcessHeap
0x180042a63  mov     rcx, rax; hHeap
0x180042a66  mov     r8, rbx; lpMem
0x180042a69  xor     edx, edx; dwFlags
0x180042a6b  call    cs:__imp_HeapFree
0x180042a71  mov     rax, rsi
0x180042a74  mov     rcx, [rbp+57h+var_30]
0x180042a78  xor     rcx, rsp; StackCookie
0x180042a7b  call    __security_check_cookie
0x180042a80  lea     r11, [rsp+100h+var_20]
0x180042a88  mov     rbx, [r11+38h]
0x180042a8c  mov     rsi, [r11+40h]
0x180042a90  mov     rsp, r11
0x180042a93  pop     r15
0x180042a95  pop     r14
0x180042a97  pop     r12
0x180042a99  pop     rdi
0x180042a9a  pop     rbp
0x180042a9b  retn
0x180042a9c  mov     r9d, eax; char *
0x180042a9f  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180042aa6  mov     edx, 1Eh; void *
0x180042aab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042ab1  mov     r9d, eax; char *
0x180042ab4  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180042abb  mov     edx, 0Ch; void *
0x180042ac0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042ac6  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180042acd  mov     edx, 10h; void *
0x180042ad2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042ad8  mov     r9d, eax; char *
0x180042adb  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180042ae2  mov     edx, 19h; void *
0x180042ae7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042aed  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180042af4  mov     edx, 1Bh; void *
0x180042af9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
