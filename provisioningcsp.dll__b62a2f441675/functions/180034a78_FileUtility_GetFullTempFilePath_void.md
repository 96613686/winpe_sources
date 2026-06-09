# FileUtility::GetFullTempFilePath(void)

- ea: `0x180034a78`
- end: `0x180034d01`
- name: `?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `649`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180035150`

## callees

- `0x18000300c`
- `0x1800090e0`
- `0x180009fac`
- `0x180024508`
- `0x1800349cc`
- `0x180034a78`
- `0x1800358a0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180034c48`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180034c48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c5e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180034b9d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180034b9d`
- `CRYPT32!CryptBinaryToStringW` at `0x180034bd1`
- `CRYPT32!CryptBinaryToStringW` at `0x180034bd1`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180034bf9`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180034bf9`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180034ac2`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180034ac2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall FileUtility::GetFullTempFilePath(_QWORD *a1)
{
  int BasicProfileFolderPathAlloc; // eax
  __int64 v3; // rbx
  unsigned __int64 v4; // rdx
  size_t v5; // r14
  WCHAR *v6; // rax
  WCHAR *v7; // rsi
  __int64 v8; // rcx
  WCHAR *v9; // r8
  size_t v10; // rdx
  WCHAR v11; // r9
  WCHAR *v12; // rcx
  HRESULT v13; // eax
  const char *v14; // r9
  HRESULT v15; // eax
  void *v16; // rbx
  HANDLE ProcessHeap; // rax
  int pcchString; // [rsp+20h] [rbp-89h]
  int pcchStringa; // [rsp+20h] [rbp-89h]
  LPVOID lpMem; // [rsp+30h] [rbp-79h] BYREF
  DWORD v22; // [rsp+38h] [rbp-71h] BYREF
  LPVOID *p_lpMem; // [rsp+40h] [rbp-69h] BYREF
  __int64 v24; // [rsp+48h] [rbp-61h] BYREF
  char v25; // [rsp+50h] [rbp-59h]
  WCHAR *v26; // [rsp+58h] [rbp-51h]
  GUID pguid; // [rsp+60h] [rbp-49h] BYREF
  WCHAR pszString[40]; // [rsp+70h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  lpMem = 0;
  p_lpMem = &lpMem;
  v24 = 0;
  v25 = 1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, 0, &v24);
  if ( BasicProfileFolderPathAlloc < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      pcchString);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_lpMem);
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)lpMem + v4) );
  if ( v4 + 46 < v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      v4 + 46 < v4 ? (const char *)0x80070216LL : 0,
      pcchString);
  v5 = v4 + 46;
  v6 = (WCHAR *)operator new[](saturated_mul(v4 + 46, 2u));
  v7 = v6;
  v26 = v6;
  if ( v5 )
  {
    if ( v5 <= 0x7FFFFFFF )
    {
      v8 = 2147483646;
      v9 = (WCHAR *)lpMem;
      v10 = v5;
      do
      {
        if ( !v8 )
          break;
        v11 = *v9;
        if ( !*v9 )
          break;
        ++v9;
        *v6++ = v11;
        --v8;
        --v10;
      }
      while ( v10 );
      v12 = v6 - 1;
      if ( v10 )
        v12 = v6;
      *v12 = 0;
    }
    else
    {
      *v6 = 0;
    }
  }
  pguid = 0;
  v22 = 38;
  v13 = CoCreateGuid(&pguid);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v13,
      pcchString);
  if ( !CryptBinaryToStringW((const BYTE *)&pguid, 0x10u, 0x4000000Cu, pszString, &v22) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      v14);
  v15 = PathCchAppendEx(v7, v5, pszString, 1u);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v15,
      pcchStringa);
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  if ( *v7 )
  {
    do
      ++v3;
    while ( v7[v3] );
  }
  std::wstring::assign(a1, v7);
  operator delete[](v7);
  v16 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
  }
  return a1;
}

```

## disassembly

```asm
0x180034a78  push    rbp
0x180034a7a  push    rbx
0x180034a7b  push    rsi
0x180034a7c  push    rdi
0x180034a7d  push    r14
0x180034a7f  push    r15
0x180034a81  lea     rbp, [rsp-2Fh]
0x180034a86  sub     rsp, 0D8h
0x180034a8d  mov     rax, cs:__security_cookie
0x180034a94  xor     rax, rsp
0x180034a97  mov     [rbp+57h+var_40], rax
0x180034a9b  mov     rdi, rcx
0x180034a9e  mov     [rbp+57h+lpMem], rcx
0x180034aa2  xor     r15d, r15d
0x180034aa5  mov     [rbp+57h+lpMem], r15
0x180034aa9  lea     rax, [rbp+57h+lpMem]
0x180034aad  mov     [rbp+57h+var_C0], rax
0x180034ab1  mov     [rbp+57h+var_B8], r15
0x180034ab5  mov     [rbp+57h+var_B0], 1
0x180034ab9  lea     r8, [rbp+57h+var_B8]
0x180034abd  xor     edx, edx
0x180034abf  lea     ecx, [rdx+6]
0x180034ac2  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x180034ac9  nop     dword ptr [rax+rax+00h]
0x180034ace  mov     rcx, [rbp+5Fh]; this
0x180034ad2  test    eax, eax
0x180034ad4  js      loc_180034CB3
0x180034ada  lea     rcx, [rbp+57h+var_C0]
0x180034ade  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180034ae3  mov     rax, [rbp+57h+lpMem]
0x180034ae7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180034aeb  mov     rdx, rbx
0x180034aee  inc     rdx
0x180034af1  cmp     [rax+rdx*2], r15w
0x180034af6  jnz     short loc_180034AEE
0x180034af8  lea     rax, [rdx+2Eh]
0x180034afc  mov     r14, rbx
0x180034aff  cmp     rax, rdx
0x180034b02  cmovnb  r14, rax
0x180034b06  sbb     r9d, r9d
0x180034b09  and     r9d, 80070216h; char *
0x180034b10  mov     rcx, [rbp+5Fh]; this
0x180034b14  cmp     rax, rdx
0x180034b17  jb      loc_180034CC8
0x180034b1d  mov     eax, 2
0x180034b22  mul     r14
0x180034b25  cmovb   rax, rbx
0x180034b29  mov     rcx, rax; unsigned __int64
0x180034b2c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180034b31  mov     rsi, rax
0x180034b34  mov     [rbp+57h+var_A8], rax
0x180034b38  test    r14, r14
0x180034b3b  jz      short loc_180034B8B
0x180034b3d  cmp     r14, 7FFFFFFFh
0x180034b44  jbe     short loc_180034B4C
0x180034b46  mov     [rax], r15w
0x180034b4a  jmp     short loc_180034B8B
0x180034b4c  mov     ecx, 7FFFFFFEh
0x180034b51  mov     r8, [rbp+57h+lpMem]
0x180034b55  mov     rdx, r14
0x180034b58  test    rcx, rcx
0x180034b5b  jz      short loc_180034B7C
0x180034b5d  movzx   r9d, word ptr [r8]
0x180034b61  test    r9w, r9w
0x180034b65  jz      short loc_180034B7C
0x180034b67  add     r8, 2
0x180034b6b  mov     [rax], r9w
0x180034b6f  add     rax, 2
0x180034b73  dec     rcx
0x180034b76  sub     rdx, 1
0x180034b7a  jnz     short loc_180034B58
0x180034b7c  lea     rcx, [rax-2]
0x180034b80  test    rdx, rdx
0x180034b83  cmovnz  rcx, rax
0x180034b87  mov     [rcx], r15w
0x180034b8b  xorps   xmm0, xmm0
0x180034b8e  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180034b92  mov     [rbp+57h+var_C8], 26h ; '&'
0x180034b99  lea     rcx, [rbp+57h+pguid]; pguid
0x180034b9d  call    cs:__imp_CoCreateGuid
0x180034ba4  nop     dword ptr [rax+rax+00h]
0x180034ba9  mov     rcx, [rbp+5Fh]; this
0x180034bad  test    eax, eax
0x180034baf  js      loc_180034CDA
0x180034bb5  lea     rax, [rbp+57h+var_C8]
0x180034bb9  mov     qword ptr [rsp+100h+pcchString], rax; int
0x180034bbe  lea     r9, [rbp+57h+pszString]; pszString
0x180034bc2  mov     edx, 10h; cbBinary
0x180034bc7  mov     r8d, 4000000Ch; dwFlags
0x180034bcd  lea     rcx, [rbp+57h+pguid]; pbBinary
0x180034bd1  call    cs:__imp_CryptBinaryToStringW
0x180034bd8  nop     dword ptr [rax+rax+00h]
0x180034bdd  mov     rcx, [rbp+5Fh]; this
0x180034be1  test    eax, eax
0x180034be3  jz      loc_180034CEF
0x180034be9  mov     r9d, 1; dwFlags
0x180034bef  lea     r8, [rbp+57h+pszString]; pszMore
0x180034bf3  mov     rdx, r14; cchPath
0x180034bf6  mov     rcx, rsi; pszPath
0x180034bf9  call    cs:__imp_PathCchAppendEx
0x180034c00  nop     dword ptr [rax+rax+00h]
0x180034c05  mov     rcx, [rbp+5Fh]; this
0x180034c09  test    eax, eax
0x180034c0b  js      loc_180034C9E
0x180034c11  mov     qword ptr [rdi+18h], 7
0x180034c19  mov     [rdi+10h], r15
0x180034c1d  mov     [rdi], r15w
0x180034c21  cmp     [rsi], r15w
0x180034c25  jnz     short loc_180034C2C
0x180034c27  mov     rbx, r15
0x180034c2a  jmp     short loc_180034C36
0x180034c2c  inc     rbx
0x180034c2f  cmp     [rsi+rbx*2], r15w
0x180034c34  jnz     short loc_180034C2C
0x180034c36  mov     r8, rbx
0x180034c39  mov     rdx, rsi; Src
0x180034c3c  mov     rcx, rdi; void *
0x180034c3f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180034c44  nop
0x180034c45  mov     rcx, rsi
0x180034c48  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180034c4f  nop     dword ptr [rax+rax+00h]
0x180034c54  nop
0x180034c55  mov     rbx, [rbp+57h+lpMem]
0x180034c59  test    rbx, rbx
0x180034c5c  jz      short loc_180034C7E
0x180034c5e  call    cs:__imp_GetProcessHeap
0x180034c65  nop     dword ptr [rax+rax+00h]
0x180034c6a  mov     rcx, rax; hHeap
0x180034c6d  mov     r8, rbx; lpMem
0x180034c70  xor     edx, edx; dwFlags
0x180034c72  call    cs:__imp_HeapFree
0x180034c79  nop     dword ptr [rax+rax+00h]
0x180034c7e  mov     rax, rdi
0x180034c81  mov     rcx, [rbp+57h+var_40]
0x180034c85  xor     rcx, rsp; StackCookie
0x180034c88  call    __security_check_cookie
0x180034c8d  add     rsp, 0D8h
0x180034c94  pop     r15
0x180034c96  pop     r14
0x180034c98  pop     rdi
0x180034c99  pop     rsi
0x180034c9a  pop     rbx
0x180034c9b  pop     rbp
0x180034c9c  retn
0x180034c9e  mov     r9d, eax; char *
0x180034ca1  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180034ca8  mov     edx, 1Eh; void *
0x180034cad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034cb3  mov     r9d, eax; char *
0x180034cb6  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180034cbd  mov     edx, 0Ch; void *
0x180034cc2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034cc8  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180034ccf  mov     edx, 10h; void *
0x180034cd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034cda  mov     r9d, eax; char *
0x180034cdd  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180034ce4  mov     edx, 19h; void *
0x180034ce9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034cef  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180034cf6  mov     edx, 1Bh; void *
0x180034cfb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
