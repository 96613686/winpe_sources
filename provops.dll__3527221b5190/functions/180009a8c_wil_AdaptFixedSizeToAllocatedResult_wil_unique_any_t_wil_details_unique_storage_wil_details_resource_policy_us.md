# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180009a8c`
- end: `0x180009cd7`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800161e4`

## callees

- `0x180007674`
- `0x18000863c`
- `0x180009a8c`
- `0x18000c538`
- `0x180033e9a`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bbc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009b68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009bb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009bd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009b68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009bb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009bd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c75`

## string_xrefs

- `0x180009c8c`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        char *a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax
  void *v6; // rbx
  unsigned __int64 v7; // rax
  char *v8; // rax
  __int64 v9; // rdx
  unsigned __int64 *v10; // r15
  char *v11; // rsi
  void *v12; // r12
  DWORD LastError; // edi
  __int64 v14; // rcx
  int v15; // edi
  void *v16; // rsi
  DWORD v17; // edi
  int v18; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 *v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  char v23; // [rsp+50h] [rbp-B0h] BYREF
  void *v24; // [rsp+58h] [rbp-A8h] BYREF
  char v25; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[512]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  memset_0(v26, 0, sizeof(v26));
  v20 = 0;
  v21 = &v20;
  v22 = 256;
  hMem = v26;
  v4 = *(_QWORD *)(a2 + 112);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
  result = (*(__int64 (__fastcall **)(__int64, HLOCAL *, __int64 *, unsigned __int64 **))(*(_QWORD *)v4 + 32LL))(
             v4,
             &hMem,
             &v22,
             &v21);
  if ( (int)result >= 0 )
  {
    v6 = 0;
    v7 = v20;
    if ( v20 > 0x100 )
    {
      while ( 1 )
      {
        v10 = (unsigned __int64 *)v7;
        v11 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                        &hMem,
                        0,
                        v7 - 1);
        if ( &v23 != v11 )
        {
          v12 = *(void **)v11;
          if ( v6 )
          {
            LastError = GetLastError();
            LocalFree(v6);
            SetLastError(LastError);
          }
          v6 = v12;
          *(_QWORD *)v11 = 0;
        }
        if ( hMem )
          LocalFree(hMem);
        if ( !v6 )
          break;
        v22 = (__int64)&v20;
        v21 = v10;
        v24 = v6;
        v14 = *(_QWORD *)(a2 + 112);
        if ( !v14 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
        v15 = (*(__int64 (__fastcall **)(__int64, void **, unsigned __int64 **, __int64 *))(*(_QWORD *)v14 + 32LL))(
                v14,
                &v24,
                &v21,
                &v22);
        if ( v15 < 0 )
        {
          LocalFree(v6);
          return (unsigned int)v15;
        }
        v7 = v20;
        if ( v20 <= (unsigned __int64)v10 )
          goto LABEL_20;
      }
      v9 = 378;
      goto LABEL_28;
    }
    v8 = (char *)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                   &hMem,
                   v26,
                   v20 - 1);
    if ( &v23 != v8 )
    {
      v6 = *(void **)v8;
      *(_QWORD *)v8 = 0;
    }
    if ( hMem )
      LocalFree(hMem);
    if ( !v6 )
    {
      v9 = 367;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)0x8007000ELL,
        v18);
      return 2147942414LL;
    }
LABEL_20:
    if ( a1 == &v25 )
    {
      LocalFree(v6);
    }
    else
    {
      v16 = *(void **)a1;
      if ( *(_QWORD *)a1 )
      {
        v17 = GetLastError();
        LocalFree(v16);
        SetLastError(v17);
      }
      *(_QWORD *)a1 = v6;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009a8c  mov     [rsp-8+arg_10], rbx
0x180009a91  push    rbp
0x180009a92  push    rsi
0x180009a93  push    rdi
0x180009a94  push    r12
0x180009a96  push    r13
0x180009a98  push    r14
0x180009a9a  push    r15
0x180009a9c  lea     rbp, [rsp-180h]
0x180009aa4  sub     rsp, 280h
0x180009aab  mov     rax, cs:__security_cookie
0x180009ab2  xor     rax, rsp
0x180009ab5  mov     [rbp+1B0h+var_40], rax
0x180009abc  mov     r13, rdx
0x180009abf  mov     r14, rcx
0x180009ac2  xor     edx, edx; Val
0x180009ac4  mov     r8d, 200h; Size
0x180009aca  lea     rcx, [rsp+2B0h+var_240]; void *
0x180009acf  call    memset_0
0x180009ad4  mov     [rsp+2B0h+var_278], 0
0x180009add  lea     rax, [rsp+2B0h+var_278]
0x180009ae2  mov     [rsp+2B0h+var_270], rax
0x180009ae7  mov     edi, 100h
0x180009aec  mov     [rsp+2B0h+var_268], rdi
0x180009af1  lea     rax, [rsp+2B0h+var_240]
0x180009af6  mov     [rsp+2B0h+hMem], rax
0x180009afb  mov     rcx, [r13+70h]; this
0x180009aff  test    rcx, rcx
0x180009b02  jz      loc_180009CD1
0x180009b08  mov     rax, [rcx]
0x180009b0b  lea     r9, [rsp+2B0h+var_270]
0x180009b10  lea     r8, [rsp+2B0h+var_268]
0x180009b15  lea     rdx, [rsp+2B0h+hMem]
0x180009b1a  mov     rax, [rax+20h]
0x180009b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b23  test    eax, eax
0x180009b25  js      loc_180009CA1
0x180009b2b  xor     ebx, ebx
0x180009b2d  mov     rax, [rsp+2B0h+var_278]
0x180009b32  cmp     rax, rdi
0x180009b35  ja      short loc_180009B81
0x180009b37  lea     r8, [rax-1]
0x180009b3b  lea     rdx, [rsp+2B0h+var_240]
0x180009b40  lea     rcx, [rsp+2B0h+hMem]
0x180009b45  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180009b4a  lea     rcx, [rsp+2B0h+var_260]
0x180009b4f  cmp     rcx, rax
0x180009b52  jz      short loc_180009B5E
0x180009b54  mov     rbx, [rax]
0x180009b57  mov     qword ptr [rax], 0
0x180009b5e  mov     rcx, [rsp+2B0h+hMem]; hMem
0x180009b63  test    rcx, rcx
0x180009b66  jz      short loc_180009B6E
0x180009b68  call    cs:__imp_LocalFree
0x180009b6e  test    rbx, rbx
0x180009b71  jnz     loc_180009C35
0x180009b77  mov     edx, 16Fh
0x180009b7c  jmp     loc_180009C84
0x180009b81  mov     r15, rax
0x180009b84  lea     r8, [rax-1]
0x180009b88  xor     edx, edx
0x180009b8a  lea     rcx, [rsp+2B0h+hMem]
0x180009b8f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180009b94  mov     rsi, rax
0x180009b97  lea     rax, [rsp+2B0h+var_260]
0x180009b9c  cmp     rax, rsi
0x180009b9f  jz      short loc_180009BCC
0x180009ba1  mov     r12, [rsi]
0x180009ba4  test    rbx, rbx
0x180009ba7  jz      short loc_180009BC2
0x180009ba9  call    cs:__imp_GetLastError
0x180009baf  mov     edi, eax
0x180009bb1  mov     rcx, rbx; hMem
0x180009bb4  call    cs:__imp_LocalFree
0x180009bba  mov     ecx, edi; dwErrCode
0x180009bbc  call    cs:__imp_SetLastError
0x180009bc2  mov     rbx, r12
0x180009bc5  mov     qword ptr [rsi], 0
0x180009bcc  mov     rcx, [rsp+2B0h+hMem]; hMem
0x180009bd1  test    rcx, rcx
0x180009bd4  jz      short loc_180009BDC
0x180009bd6  call    cs:__imp_LocalFree
0x180009bdc  test    rbx, rbx
0x180009bdf  jz      loc_180009C7F
0x180009be5  lea     rax, [rsp+2B0h+var_278]
0x180009bea  mov     [rsp+2B0h+var_268], rax
0x180009bef  mov     [rsp+2B0h+var_270], r15
0x180009bf4  mov     [rsp+2B0h+var_258], rbx
0x180009bf9  mov     rcx, [r13+70h]; this
0x180009bfd  test    rcx, rcx
0x180009c00  jz      loc_180009CCB
0x180009c06  mov     rax, [rcx]
0x180009c09  lea     r9, [rsp+2B0h+var_268]
0x180009c0e  lea     r8, [rsp+2B0h+var_270]
0x180009c13  lea     rdx, [rsp+2B0h+var_258]
0x180009c18  mov     rax, [rax+20h]
0x180009c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c21  mov     edi, eax
0x180009c23  test    eax, eax
0x180009c25  js      short loc_180009C72
0x180009c27  mov     rax, [rsp+2B0h+var_278]
0x180009c2c  cmp     rax, r15
0x180009c2f  ja      loc_180009B81
0x180009c35  lea     rax, [rsp+2B0h+var_250]
0x180009c3a  cmp     r14, rax
0x180009c3d  jz      short loc_180009C65
0x180009c3f  mov     rsi, [r14]
0x180009c42  test    rsi, rsi
0x180009c45  jz      short loc_180009C60
0x180009c47  call    cs:__imp_GetLastError
0x180009c4d  mov     edi, eax
0x180009c4f  mov     rcx, rsi; hMem
0x180009c52  call    cs:__imp_LocalFree
0x180009c58  mov     ecx, edi; dwErrCode
0x180009c5a  call    cs:__imp_SetLastError
0x180009c60  mov     [r14], rbx
0x180009c63  jmp     short loc_180009C6E
0x180009c65  mov     rcx, rbx; hMem
0x180009c68  call    cs:__imp_LocalFree
0x180009c6e  xor     eax, eax
0x180009c70  jmp     short loc_180009CA1
0x180009c72  mov     rcx, rbx; hMem
0x180009c75  call    cs:__imp_LocalFree
0x180009c7b  mov     eax, edi
0x180009c7d  jmp     short loc_180009CA1
0x180009c7f  mov     edx, 17Ah; void *
0x180009c84  mov     ebx, 8007000Eh
0x180009c89  mov     r9d, ebx; char *
0x180009c8c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009c93  mov     rcx, [rbp+1B8h]; this
0x180009c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c9f  mov     eax, ebx
0x180009ca1  mov     rcx, [rbp+1B0h+var_40]
0x180009ca8  xor     rcx, rsp; StackCookie
0x180009cab  call    __security_check_cookie
0x180009cb0  mov     rbx, [rsp+2B0h+arg_10]
0x180009cb8  add     rsp, 280h
0x180009cbf  pop     r15
0x180009cc1  pop     r14
0x180009cc3  pop     r13
0x180009cc5  pop     r12
0x180009cc7  pop     rdi
0x180009cc8  pop     rsi
0x180009cc9  pop     rbp
0x180009cca  retn
0x180009ccb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009cd1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
