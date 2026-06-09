# NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)

- ea: `0x180042894`
- end: `0x180042988`
- name: `?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z`
- size: `244`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, LPCWSTR pszProperty, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180027b94`
- `0x1800295f0`
- `0x180042990`

## callees

- `0x180006538`
- `0x1800065c0`
- `0x180042894`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042968`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042968`
- `ncrypt!NCryptGetProperty` at `0x1800428cb`
- `ncrypt!NCryptGetProperty` at `0x18004293b`
- `ncrypt!NCryptGetProperty` at `0x1800428cb`
- `ncrypt!NCryptGetProperty` at `0x18004293b`

## string_xrefs

- `0x1800428e1`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18004294c`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetNCryptBinaryBlob(
        NCRYPT_HANDLE hObject,
        LPCWSTR pszProperty,
        unsigned __int16 *a3,
        unsigned __int8 **a4)
{
  SECURITY_STATUS Property; // ebx
  __int64 v9; // rdx
  PBYTE v11; // rbx
  SECURITY_STATUS v12; // eax
  unsigned int v13; // edi
  DWORD v14; // eax
  int pcbResult; // [rsp+20h] [rbp-48h]
  int pcbResulta; // [rsp+20h] [rbp-48h]
  DWORD cbOutput; // [rsp+30h] [rbp-38h] BYREF
  PBYTE pbOutput[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  cbOutput = 0;
  Property = NCryptGetProperty(hObject, pszProperty, 0, 0, &cbOutput, 0);
  if ( Property < 0 )
  {
    v9 = 178;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)Property,
      pcbResult);
    return (unsigned int)Property;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(pbOutput, cbOutput);
  v11 = pbOutput[0];
  if ( !pbOutput[0] )
  {
    Property = -2147024882;
    v9 = 181;
    goto LABEL_3;
  }
  v12 = NCryptGetProperty(hObject, pszProperty, pbOutput[0], cbOutput, &cbOutput, 0);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = cbOutput;
    *(_QWORD *)a3 = v11;
    *(_DWORD *)a4 = v14;
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
0x180042894  push    rbx
0x180042896  push    rbp
0x180042897  push    rsi
0x180042898  push    rdi
0x180042899  push    r14
0x18004289b  sub     rsp, 40h
0x18004289f  mov     rsi, r9
0x1800428a2  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800428aa  mov     r14, r8
0x1800428ad  mov     [rsp+68h+cbOutput], 0
0x1800428b5  lea     rax, [rsp+68h+cbOutput]
0x1800428ba  xor     r9d, r9d; cbOutput
0x1800428bd  xor     r8d, r8d; pbOutput
0x1800428c0  mov     [rsp+68h+pcbResult], rax; int
0x1800428c5  mov     rdi, rdx
0x1800428c8  mov     rbp, rcx
0x1800428cb  call    cs:__imp_NCryptGetProperty
0x1800428d1  mov     ebx, eax
0x1800428d3  test    eax, eax
0x1800428d5  jns     short loc_1800428F7
0x1800428d7  mov     edx, 0B2h; void *
0x1800428dc  mov     rcx, [rsp+68h]; this
0x1800428e1  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800428e8  mov     r9d, ebx; char *
0x1800428eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800428f0  mov     eax, ebx
0x1800428f2  jmp     loc_18004297D
0x1800428f7  mov     edx, [rsp+68h+cbOutput]
0x1800428fb  lea     rcx, [rsp+68h+pbOutput]
0x180042900  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180042905  mov     rbx, [rsp+68h+pbOutput]
0x18004290a  test    rbx, rbx
0x18004290d  jnz     short loc_18004291B
0x18004290f  mov     ebx, 8007000Eh
0x180042914  mov     edx, 0B5h
0x180042919  jmp     short loc_1800428DC
0x18004291b  mov     r9d, [rsp+68h+cbOutput]; cbOutput
0x180042920  lea     rax, [rsp+68h+cbOutput]
0x180042925  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18004292d  mov     r8, rbx; pbOutput
0x180042930  mov     rdx, rdi; pszProperty
0x180042933  mov     [rsp+68h+pcbResult], rax; int
0x180042938  mov     rcx, rbp; hObject
0x18004293b  call    cs:__imp_NCryptGetProperty
0x180042941  mov     edi, eax
0x180042943  test    eax, eax
0x180042945  jns     short loc_180042972
0x180042947  mov     rcx, [rsp+68h]; this
0x18004294c  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180042953  mov     r9d, eax; char *
0x180042956  mov     edx, 0BDh; void *
0x18004295b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042960  test    rbx, rbx
0x180042963  jz      short loc_18004296E
0x180042965  mov     rcx, rbx; hMem
0x180042968  call    cs:__imp_LocalFree
0x18004296e  mov     eax, edi
0x180042970  jmp     short loc_18004297D
0x180042972  mov     eax, [rsp+68h+cbOutput]
0x180042976  mov     [r14], rbx
0x180042979  mov     [rsi], eax
0x18004297b  xor     eax, eax
0x18004297d  add     rsp, 40h
0x180042981  pop     r14
0x180042983  pop     rdi
0x180042984  pop     rsi
0x180042985  pop     rbp
0x180042986  pop     rbx
0x180042987  retn
```
