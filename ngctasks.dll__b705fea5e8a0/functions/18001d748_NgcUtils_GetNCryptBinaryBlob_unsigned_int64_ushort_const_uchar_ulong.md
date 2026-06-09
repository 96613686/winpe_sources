# NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)

- ea: `0x18001d748`
- end: `0x18001d853`
- name: `?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z`
- size: `267`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, LPCWSTR pszProperty, unsigned __int16 *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016b24`
- `0x18001cff4`

## callees

- `0x18000cc34`
- `0x180017440`
- `0x18001d748`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d832`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d832`
- `ncrypt!NCryptGetProperty` at `0x18001d77f`
- `ncrypt!NCryptGetProperty` at `0x18001d804`
- `ncrypt!NCryptGetProperty` at `0x18001d77f`
- `ncrypt!NCryptGetProperty` at `0x18001d804`

## string_xrefs

- `0x18001d793`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001d7d0`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001d818`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcUtils::GetNCryptBinaryBlob(
        NCRYPT_HANDLE hObject,
        LPCWSTR pszProperty,
        unsigned __int16 *a3,
        unsigned __int8 **a4)
{
  SECURITY_STATUS Property; // eax
  unsigned int v9; // ebx
  PBYTE v11; // rbx
  SECURITY_STATUS v12; // eax
  unsigned int v13; // edi
  int pcbResult; // [rsp+20h] [rbp-48h]
  int pcbResulta; // [rsp+20h] [rbp-48h]
  DWORD cbOutput; // [rsp+30h] [rbp-38h] BYREF
  PBYTE pbOutput[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  cbOutput = 0;
  Property = NCryptGetProperty(hObject, pszProperty, 0, 0, &cbOutput, 0);
  v9 = Property;
  if ( Property < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)Property,
      pcbResult);
    return v9;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(pbOutput, cbOutput);
  v11 = pbOutput[0];
  if ( !pbOutput[0] )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)0x8007000ELL,
      pcbResult);
    return v9;
  }
  v12 = NCryptGetProperty(hObject, pszProperty, pbOutput[0], cbOutput, &cbOutput, 0);
  v13 = v12;
  if ( v12 >= 0 )
  {
    *(_QWORD *)a3 = v11;
    *(_DWORD *)a4 = cbOutput;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v12,
      pcbResulta);
    if ( v11 )
      LocalFree(v11);
    return v13;
  }
}

```

## disassembly

```asm
0x18001d748  push    rbx
0x18001d74a  push    rbp
0x18001d74b  push    rsi
0x18001d74c  push    rdi
0x18001d74d  push    r14
0x18001d74f  sub     rsp, 40h
0x18001d753  mov     rsi, r9
0x18001d756  mov     r14, r8
0x18001d759  mov     rdi, rdx
0x18001d75c  mov     rbp, rcx
0x18001d75f  mov     [rsp+68h+cbOutput], 0
0x18001d767  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18001d76f  lea     rax, [rsp+68h+cbOutput]
0x18001d774  mov     [rsp+68h+pcbResult], rax; int
0x18001d779  xor     r9d, r9d; cbOutput
0x18001d77c  xor     r8d, r8d; pbOutput
0x18001d77f  call    cs:__imp_NCryptGetProperty
0x18001d785  mov     ebx, eax
0x18001d787  test    eax, eax
0x18001d789  jns     short loc_18001D7AB
0x18001d78b  mov     rcx, [rsp+68h]; this
0x18001d790  mov     r9d, eax; char *
0x18001d793  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d79a  mov     edx, 0B2h; void *
0x18001d79f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d7a4  mov     eax, ebx
0x18001d7a6  jmp     loc_18001D848
0x18001d7ab  mov     edx, [rsp+68h+cbOutput]
0x18001d7af  lea     rcx, [rsp+68h+pbOutput]
0x18001d7b4  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001d7b9  mov     rbx, [rsp+68h+pbOutput]
0x18001d7be  test    rbx, rbx
0x18001d7c1  jnz     short loc_18001D7E4
0x18001d7c3  mov     rcx, [rsp+68h]; this
0x18001d7c8  mov     ebx, 8007000Eh
0x18001d7cd  mov     r9d, ebx; char *
0x18001d7d0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d7d7  mov     edx, 0B5h; void *
0x18001d7dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d7e1  nop
0x18001d7e2  jmp     short loc_18001D7A4
0x18001d7e4  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18001d7ec  lea     rax, [rsp+68h+cbOutput]
0x18001d7f1  mov     [rsp+68h+pcbResult], rax; int
0x18001d7f6  mov     r9d, [rsp+68h+cbOutput]; cbOutput
0x18001d7fb  mov     r8, rbx; pbOutput
0x18001d7fe  mov     rdx, rdi; pszProperty
0x18001d801  mov     rcx, rbp; hObject
0x18001d804  call    cs:__imp_NCryptGetProperty
0x18001d80a  mov     edi, eax
0x18001d80c  test    eax, eax
0x18001d80e  jns     short loc_18001D83D
0x18001d810  mov     rcx, [rsp+68h]; this
0x18001d815  mov     r9d, eax; char *
0x18001d818  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d81f  mov     edx, 0BDh; void *
0x18001d824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d829  nop
0x18001d82a  test    rbx, rbx
0x18001d82d  jz      short loc_18001D839
0x18001d82f  mov     rcx, rbx; hMem
0x18001d832  call    cs:__imp_LocalFree
0x18001d838  nop
0x18001d839  mov     eax, edi
0x18001d83b  jmp     short loc_18001D848
0x18001d83d  mov     [r14], rbx
0x18001d840  mov     eax, [rsp+68h+cbOutput]
0x18001d844  mov     [rsi], eax
0x18001d846  xor     eax, eax
0x18001d848  add     rsp, 40h
0x18001d84c  pop     r14
0x18001d84e  pop     rdi
0x18001d84f  pop     rsi
0x18001d850  pop     rbp
0x18001d851  pop     rbx
0x18001d852  retn
```
