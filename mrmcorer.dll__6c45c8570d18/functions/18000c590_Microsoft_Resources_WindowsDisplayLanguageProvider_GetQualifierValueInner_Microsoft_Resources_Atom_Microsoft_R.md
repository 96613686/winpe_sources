# Microsoft::Resources::WindowsDisplayLanguageProvider::GetQualifierValueInner(Microsoft::Resources::Atom,Microsoft::Resources::IProviderDataSources const *,Microsoft::Resources::StringResult *)

- ea: `0x18000c590`
- end: `0x18000c797`
- name: `?GetQualifierValueInner@WindowsDisplayLanguageProvider@Resources@Microsoft@@UEBAJUAtom@23@PEBVIProviderDataSources@23@PEAVStringResult@23@@Z`
- size: `519`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000c590`
- `0x18000c880`
- `0x180028510`
- `0x18002c8d0`
- `0x180030c6c`
- `0x180031e04`
- `0x180083aa8`
- `0x1800862f0`
- `0x180086f7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c72a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c72a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c719`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c662`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000c5f6`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000c757`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000c5f6`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18000c757`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::WindowsDisplayLanguageProvider::GetQualifierValueInner(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  Microsoft::Resources *v5; // rbx
  WCHAR *v6; // rdi
  bool v7; // zf
  ULONG v8; // ecx
  __int64 v9; // rax
  ULONG v10; // edx
  int v11; // eax
  void *v12; // rdx
  unsigned int v13; // edi
  signed int v15; // eax
  unsigned int LastError; // ebx
  void *v17; // rdx
  __int64 v18; // rdx
  SIZE_T v19; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v21; // rax
  const char *v22; // r9
  ULONG pcchLanguagesBuffer; // [rsp+20h] [rbp-99h] BYREF
  ULONG pulNumLanguages; // [rsp+24h] [rbp-95h] BYREF
  _QWORD v25[3]; // [rsp+28h] [rbp-91h] BYREF
  WCHAR pwszLanguagesBuffer[88]; // [rsp+40h] [rbp-79h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  pulNumLanguages = 0;
  memset_0(pwszLanguagesBuffer, 0, 0xACu);
  v5 = 0;
  pcchLanguagesBuffer = 86;
  v25[0] = 0;
  if ( !GetThreadPreferredUILanguages(0x38u, &pulNumLanguages, pwszLanguagesBuffer, &pcchLanguagesBuffer) )
  {
    if ( GetLastError() == 122 )
    {
      if ( is_mul_ok(pcchLanguagesBuffer, 2u) )
      {
        if ( 2LL * pcchLanguagesBuffer )
        {
          v19 = DefArray_Size(2, pcchLanguagesBuffer);
          ProcessHeap = GetProcessHeap();
          v21 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v19);
          v6 = v21;
          if ( v21 )
          {
            wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void Microsoft::Resources::DefFreeMemory(void *)>>::reset(
              v25,
              v21);
            if ( GetThreadPreferredUILanguages(0x38u, &pulNumLanguages, v6, &pcchLanguagesBuffer) )
            {
              v5 = (Microsoft::Resources *)v25[0];
              goto LABEL_3;
            }
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x91,
                          (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\baseproviders.cpp",
                          v22);
            wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void Microsoft::Resources::DefFreeMemory(void *)>>::reset(
              v25,
              0);
            return LastError;
          }
        }
      }
      LastError = -2147024882;
      v18 = 141;
    }
    else
    {
      v15 = GetLastError();
      LastError = v15;
      if ( v15 > 0 )
        LastError = (unsigned __int16)v15 | 0x80070000;
      if ( (LastError & 0x80000000) == 0 )
        return LastError;
      v18 = 149;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\baseproviders.cpp",
      (const char *)LastError,
      pcchLanguagesBuffer);
    return LastError;
  }
  v6 = pwszLanguagesBuffer;
LABEL_3:
  v7 = pcchLanguagesBuffer == 3;
  v8 = pcchLanguagesBuffer - 3;
  pcchLanguagesBuffer -= 3;
  if ( !v7 )
  {
    v9 = v8;
    v10 = v8;
    do
    {
      if ( !v6[v9] )
      {
        v6[v10] = 59;
        v8 = pcchLanguagesBuffer;
      }
      v7 = v8-- == 1;
      pcchLanguagesBuffer = v8;
      v10 = v8;
      v9 = v8;
    }
    while ( !v7 );
  }
  v11 = DefStringResult_SetCopy(*a4, v6);
  v13 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\baseproviders.cpp",
      (const char *)(unsigned int)v11,
      pcchLanguagesBuffer);
    if ( v5 )
      Microsoft::Resources::DefFreeMemory(v5, v17);
    return v13;
  }
  else
  {
    if ( v5 )
      Microsoft::Resources::DefFreeMemory(v5, v12);
    return 0;
  }
}

```

## disassembly

```asm
0x18000c590  mov     [rsp-8+arg_0], rbx
0x18000c595  mov     [rsp-8+arg_8], rsi
0x18000c59a  push    rbp
0x18000c59b  push    rdi
0x18000c59c  push    r14
0x18000c59e  lea     rbp, [rsp-47h]
0x18000c5a3  sub     rsp, 100h
0x18000c5aa  mov     rax, cs:__security_cookie
0x18000c5b1  xor     rax, rsp
0x18000c5b4  mov     [rbp+57h+var_20], rax
0x18000c5b8  xor     r14d, r14d
0x18000c5bb  lea     rcx, [rbp+57h+pwszLanguagesBuffer]; void *
0x18000c5bf  xor     edx, edx; Val
0x18000c5c1  mov     [rsp+110h+pulNumLanguages], r14d
0x18000c5c6  mov     r8d, 0ACh; Size
0x18000c5cc  mov     rsi, r9
0x18000c5cf  call    memset_0
0x18000c5d4  mov     ebx, r14d
0x18000c5d7  mov     [rsp+110h+pcchLanguagesBuffer], 56h ; 'V'; int
0x18000c5df  lea     r9, [rsp+110h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18000c5e4  mov     [rsp+110h+var_E8], rbx
0x18000c5e9  lea     r8, [rbp+57h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x18000c5ed  lea     rdx, [rsp+110h+pulNumLanguages]; pulNumLanguages
0x18000c5f2  lea     ecx, [r14+38h]; dwFlags
0x18000c5f6  call    cs:__imp_GetThreadPreferredUILanguages
0x18000c5fc  test    eax, eax
0x18000c5fe  jz      short loc_18000C657
0x18000c600  lea     rdi, [rbp+57h+pwszLanguagesBuffer]
0x18000c604  mov     ecx, [rsp+110h+pcchLanguagesBuffer]
0x18000c608  add     ecx, 0FFFFFFFDh
0x18000c60b  mov     [rsp+110h+pcchLanguagesBuffer], ecx
0x18000c60f  jz      short loc_18000C635
0x18000c611  mov     eax, ecx
0x18000c613  mov     edx, ecx
0x18000c615  cmp     [rdi+rax*2], r14w
0x18000c61a  jnz     short loc_18000C628
0x18000c61c  mov     eax, edx
0x18000c61e  mov     word ptr [rdi+rax*2], 3Bh ; ';'
0x18000c624  mov     ecx, [rsp+110h+pcchLanguagesBuffer]
0x18000c628  add     ecx, 0FFFFFFFFh
0x18000c62b  mov     [rsp+110h+pcchLanguagesBuffer], ecx; int
0x18000c62f  mov     edx, ecx
0x18000c631  mov     eax, ecx
0x18000c633  jnz     short loc_18000C615
0x18000c635  mov     rcx, [rsi]
0x18000c638  mov     rdx, rdi
0x18000c63b  call    DefStringResult_SetCopy
0x18000c640  mov     edi, eax
0x18000c642  test    eax, eax
0x18000c644  js      short loc_18000C6A5
0x18000c646  test    rbx, rbx
0x18000c649  jz      short loc_18000C653
0x18000c64b  mov     rcx, rbx; this
0x18000c64e  call    ?DefFreeMemory@Resources@Microsoft@@YAXPEAX@Z; Microsoft::Resources::DefFreeMemory(void *)
0x18000c653  xor     eax, eax
0x18000c655  jmp     short loc_18000C681
0x18000c657  call    cs:__imp_GetLastError
0x18000c65d  cmp     eax, 7Ah ; 'z'
0x18000c660  jz      short loc_18000C6CE
0x18000c662  call    cs:__imp_GetLastError
0x18000c668  mov     ebx, eax
0x18000c66a  test    eax, eax
0x18000c66c  jle     short loc_18000C677
0x18000c66e  movzx   ebx, ax
0x18000c671  or      ebx, 80070000h
0x18000c677  test    ebx, ebx
0x18000c679  js      loc_18000C78D
0x18000c67f  mov     eax, ebx
0x18000c681  mov     rcx, [rbp+57h+var_20]
0x18000c685  xor     rcx, rsp; StackCookie
0x18000c688  call    __security_check_cookie
0x18000c68d  lea     r11, [rsp+110h+var_10]
0x18000c695  mov     rbx, [r11+20h]
0x18000c699  mov     rsi, [r11+28h]
0x18000c69d  mov     rsp, r11
0x18000c6a0  pop     r14
0x18000c6a2  pop     rdi
0x18000c6a3  pop     rbp
0x18000c6a4  retn
0x18000c6a5  mov     rcx, [rbp+5Fh]; this
0x18000c6a9  lea     r8, aMinkernelMrtMr_5; "minkernel\\mrt\\mrm\\mrmmin\\baseprovid"...
0x18000c6b0  mov     r9d, edi; char *
0x18000c6b3  mov     edx, 0A8h; void *
0x18000c6b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6bd  test    rbx, rbx
0x18000c6c0  jz      short loc_18000C6CA
0x18000c6c2  mov     rcx, rbx; this
0x18000c6c5  call    ?DefFreeMemory@Resources@Microsoft@@YAXPEAX@Z; Microsoft::Resources::DefFreeMemory(void *)
0x18000c6ca  mov     eax, edi
0x18000c6cc  jmp     short loc_18000C681
0x18000c6ce  mov     r9d, [rsp+110h+pcchLanguagesBuffer]
0x18000c6d3  mov     r10d, 2
0x18000c6d9  mov     eax, r10d
0x18000c6dc  mul     r9
0x18000c6df  test    rdx, rdx
0x18000c6e2  jnz     short loc_18000C6E9
0x18000c6e4  test    rax, rax
0x18000c6e7  jnz     short loc_18000C70B
0x18000c6e9  mov     ebx, 8007000Eh
0x18000c6ee  mov     edx, 8Dh; void *
0x18000c6f3  mov     rcx, [rbp+5Fh]; this
0x18000c6f7  lea     r8, aMinkernelMrtMr_5; "minkernel\\mrt\\mrm\\mrmmin\\baseprovid"...
0x18000c6fe  mov     r9d, ebx; char *
0x18000c701  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c706  jmp     loc_18000C67F
0x18000c70b  mov     rdx, r9
0x18000c70e  mov     rcx, r10
0x18000c711  call    _DefArray_Size
0x18000c716  mov     rbx, rax
0x18000c719  call    cs:__imp_GetProcessHeap
0x18000c71f  mov     r8, rbx; dwBytes
0x18000c722  mov     edx, 8; dwFlags
0x18000c727  mov     rcx, rax; hHeap
0x18000c72a  call    cs:__imp_HeapAlloc
0x18000c730  mov     rdi, rax
0x18000c733  test    rax, rax
0x18000c736  jz      short loc_18000C6E9
0x18000c738  mov     rdx, rax
0x18000c73b  lea     rcx, [rsp+110h+var_E8]
0x18000c740  call    ?reset@?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?DefFreeMemory@Resources@Microsoft@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&Microsoft::Resources::DefFreeMemory(void *)>>::reset(ushort *)
0x18000c745  lea     r9, [rsp+110h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18000c74a  mov     r8, rdi; pwszLanguagesBuffer
0x18000c74d  lea     rdx, [rsp+110h+pulNumLanguages]; pulNumLanguages
0x18000c752  mov     ecx, 38h ; '8'; dwFlags
0x18000c757  call    cs:__imp_GetThreadPreferredUILanguages
0x18000c75d  test    eax, eax
0x18000c75f  jnz     loc_1800C0182
0x18000c765  mov     rcx, [rbp+5Fh]; this
0x18000c769  lea     r8, aMinkernelMrtMr_5; "minkernel\\mrt\\mrm\\mrmmin\\baseprovid"...
0x18000c770  mov     edx, 91h; void *
0x18000c775  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c77a  xor     edx, edx
0x18000c77c  lea     rcx, [rsp+110h+var_E8]
0x18000c781  mov     ebx, eax
0x18000c783  call    ?reset@?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?DefFreeMemory@Resources@Microsoft@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&Microsoft::Resources::DefFreeMemory(void *)>>::reset(ushort *)
0x18000c788  jmp     loc_18000C67F
0x18000c78d  mov     edx, 95h
0x18000c792  jmp     loc_18000C6F3
0x1800c0182  mov     rbx, [rsp+110h+var_E8]
0x1800c0187  jmp     loc_18000C604
```
