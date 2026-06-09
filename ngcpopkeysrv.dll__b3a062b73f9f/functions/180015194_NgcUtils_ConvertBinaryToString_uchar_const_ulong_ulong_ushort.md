# NgcUtils::ConvertBinaryToString(uchar const *,ulong,ulong,ushort * *)

- ea: `0x180015194`
- end: `0x180015281`
- name: `?ConvertBinaryToString@NgcUtils@@YAJPEBEKKPEAPEAG@Z`
- size: `237`
- prototype: `__int64 __fastcall(BYTE *pbBinary, const unsigned __int8 *, unsigned int, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014498`
- `0x18001ba2c`

## callees

- `0x18000b0dc`
- `0x18000b0fc`
- `0x18000db5c`
- `0x180014e40`
- `0x180015194`

## import_xrefs

- `CRYPT32!CryptBinaryToStringW` at `0x1800151c2`
- `CRYPT32!CryptBinaryToStringW` at `0x18001523a`
- `CRYPT32!CryptBinaryToStringW` at `0x1800151c2`
- `CRYPT32!CryptBinaryToStringW` at `0x18001523a`

## string_xrefs

- `0x1800151d1`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180015207`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180015249`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::ConvertBinaryToString(BYTE *pbBinary, const unsigned __int8 *a2, DWORD a3, LPWSTR *a4)
{
  const char *v7; // r9
  LPWSTR v9; // rbx
  unsigned int LastError; // ebx
  const char *v11; // r9
  int pcchString; // [rsp+20h] [rbp-48h]
  LPWSTR pszString[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD v15; // [rsp+78h] [rbp+10h] BYREF

  v15 = 0;
  if ( !CryptBinaryToStringW(pbBinary, 0x20u, a3, 0, &v15) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xEC,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
             v7);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    pszString,
    0,
    v15);
  v9 = pszString[0];
  if ( pszString[0] )
  {
    if ( CryptBinaryToStringW(pbBinary, 0x20u, a3, pszString[0], &v15) )
    {
      *a4 = v9;
      LastError = 0;
      pszString[0] = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xF6,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
                    v11);
    }
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)0x8007000ELL,
      pcchString);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pszString);
  return LastError;
}

```

## disassembly

```asm
0x180015194  mov     [rsp+arg_8], edx
0x180015198  push    rbx
0x180015199  push    rbp
0x18001519a  push    rsi
0x18001519b  push    rdi
0x18001519c  sub     rsp, 48h
0x1800151a0  mov     rdi, r9
0x1800151a3  mov     [rsp+68h+arg_8], 0
0x1800151ab  xor     r9d, r9d; pszString
0x1800151ae  lea     rax, [rsp+68h+arg_8]
0x1800151b3  mov     esi, r8d
0x1800151b6  mov     qword ptr [rsp+68h+pcchString], rax; int
0x1800151bb  mov     rbp, rcx
0x1800151be  lea     edx, [r9+20h]; cbBinary
0x1800151c2  call    cs:__imp_CryptBinaryToStringW
0x1800151c8  test    eax, eax
0x1800151ca  jnz     short loc_1800151E7
0x1800151cc  mov     rcx, [rsp+68h]; this
0x1800151d1  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800151d8  mov     edx, 0ECh; void *
0x1800151dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800151e2  jmp     loc_180015278
0x1800151e7  mov     r8d, [rsp+68h+arg_8]
0x1800151ec  lea     rcx, [rsp+68h+pszString]
0x1800151f1  xor     edx, edx
0x1800151f3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800151f8  mov     rbx, [rsp+68h+pszString]
0x1800151fd  test    rbx, rbx
0x180015200  jnz     short loc_180015222
0x180015202  mov     rcx, [rsp+68h]; this
0x180015207  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001520e  mov     ebx, 8007000Eh
0x180015213  mov     edx, 0EFh; void *
0x180015218  mov     r9d, ebx; char *
0x18001521b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015220  jmp     short loc_18001526C
0x180015222  lea     rax, [rsp+68h+arg_8]
0x180015227  mov     r9, rbx; pszString
0x18001522a  mov     r8d, esi; dwFlags
0x18001522d  mov     qword ptr [rsp+68h+pcchString], rax; pcchString
0x180015232  mov     edx, 20h ; ' '; cbBinary
0x180015237  mov     rcx, rbp; pbBinary
0x18001523a  call    cs:__imp_CryptBinaryToStringW
0x180015240  test    eax, eax
0x180015242  jnz     short loc_18001525E
0x180015244  mov     rcx, [rsp+68h]; this
0x180015249  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180015250  mov     edx, 0F6h; void *
0x180015255  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001525a  mov     ebx, eax
0x18001525c  jmp     short loc_18001526C
0x18001525e  mov     [rdi], rbx
0x180015261  xor     ebx, ebx
0x180015263  mov     [rsp+68h+pszString], 0
0x18001526c  lea     rcx, [rsp+68h+pszString]
0x180015271  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015276  mov     eax, ebx
0x180015278  add     rsp, 48h
0x18001527c  pop     rdi
0x18001527d  pop     rsi
0x18001527e  pop     rbp
0x18001527f  pop     rbx
0x180015280  retn
```
