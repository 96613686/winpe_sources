# NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)

- ea: `0x1800141e4`
- end: `0x1800142d8`
- name: `?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z`
- size: `244`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, LPCWSTR pszProperty, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800142e0`
- `0x180015e94`
- `0x18001608c`
- `0x18001dc5c`

## callees

- `0x18000b0fc`
- `0x180013270`
- `0x1800141e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800142b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800142b8`
- `ncrypt!NCryptGetProperty` at `0x18001421b`
- `ncrypt!NCryptGetProperty` at `0x18001428b`
- `ncrypt!NCryptGetProperty` at `0x18001421b`
- `ncrypt!NCryptGetProperty` at `0x18001428b`

## string_xrefs

- `0x180014231`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001429c`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

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
0x1800141e4  push    rbx
0x1800141e6  push    rbp
0x1800141e7  push    rsi
0x1800141e8  push    rdi
0x1800141e9  push    r14
0x1800141eb  sub     rsp, 40h
0x1800141ef  mov     rsi, r9
0x1800141f2  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800141fa  mov     r14, r8
0x1800141fd  mov     [rsp+68h+cbOutput], 0
0x180014205  lea     rax, [rsp+68h+cbOutput]
0x18001420a  xor     r9d, r9d; cbOutput
0x18001420d  xor     r8d, r8d; pbOutput
0x180014210  mov     [rsp+68h+pcbResult], rax; int
0x180014215  mov     rdi, rdx
0x180014218  mov     rbp, rcx
0x18001421b  call    cs:__imp_NCryptGetProperty
0x180014221  mov     ebx, eax
0x180014223  test    eax, eax
0x180014225  jns     short loc_180014247
0x180014227  mov     edx, 0B2h; void *
0x18001422c  mov     rcx, [rsp+68h]; this
0x180014231  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180014238  mov     r9d, ebx; char *
0x18001423b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014240  mov     eax, ebx
0x180014242  jmp     loc_1800142CD
0x180014247  mov     edx, [rsp+68h+cbOutput]
0x18001424b  lea     rcx, [rsp+68h+pbOutput]
0x180014250  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180014255  mov     rbx, [rsp+68h+pbOutput]
0x18001425a  test    rbx, rbx
0x18001425d  jnz     short loc_18001426B
0x18001425f  mov     ebx, 8007000Eh
0x180014264  mov     edx, 0B5h
0x180014269  jmp     short loc_18001422C
0x18001426b  mov     r9d, [rsp+68h+cbOutput]; cbOutput
0x180014270  lea     rax, [rsp+68h+cbOutput]
0x180014275  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18001427d  mov     r8, rbx; pbOutput
0x180014280  mov     rdx, rdi; pszProperty
0x180014283  mov     [rsp+68h+pcbResult], rax; int
0x180014288  mov     rcx, rbp; hObject
0x18001428b  call    cs:__imp_NCryptGetProperty
0x180014291  mov     edi, eax
0x180014293  test    eax, eax
0x180014295  jns     short loc_1800142C2
0x180014297  mov     rcx, [rsp+68h]; this
0x18001429c  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800142a3  mov     r9d, eax; char *
0x1800142a6  mov     edx, 0BDh; void *
0x1800142ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800142b0  test    rbx, rbx
0x1800142b3  jz      short loc_1800142BE
0x1800142b5  mov     rcx, rbx; hMem
0x1800142b8  call    cs:__imp_LocalFree
0x1800142be  mov     eax, edi
0x1800142c0  jmp     short loc_1800142CD
0x1800142c2  mov     eax, [rsp+68h+cbOutput]
0x1800142c6  mov     [r14], rbx
0x1800142c9  mov     [rsi], eax
0x1800142cb  xor     eax, eax
0x1800142cd  add     rsp, 40h
0x1800142d1  pop     r14
0x1800142d3  pop     rdi
0x1800142d4  pop     rsi
0x1800142d5  pop     rbp
0x1800142d6  pop     rbx
0x1800142d7  retn
```
