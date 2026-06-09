# NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)

- ea: `0x180013cbc`
- end: `0x180013dc2`
- name: `?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z`
- size: `262`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, LPCWSTR pszProperty, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010c10`

## callees

- `0x18000a5b4`
- `0x180013cbc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013d13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013d13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013d7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013d7e`
- `ncrypt!NCryptGetProperty` at `0x180013cf5`
- `ncrypt!NCryptGetProperty` at `0x180013d56`
- `ncrypt!NCryptGetProperty` at `0x180013cf5`
- `ncrypt!NCryptGetProperty` at `0x180013d56`

## string_xrefs

- `0x180013d67`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180013da4`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

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
  __int64 v10; // rdi
  BYTE *v11; // rax
  BYTE *v12; // rbx
  BYTE *i; // rcx
  SECURITY_STATUS v14; // eax
  unsigned int v15; // edi
  DWORD v17; // eax
  int pcbResult; // [rsp+20h] [rbp-58h]
  int pcbResulta; // [rsp+20h] [rbp-58h]
  DWORD cbOutput[18]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  cbOutput[0] = 0;
  Property = NCryptGetProperty(hObject, pszProperty, 0, 0, cbOutput, 0);
  if ( Property < 0 )
  {
    v9 = 178;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)Property,
      pcbResult);
    return (unsigned int)Property;
  }
  v10 = cbOutput[0];
  v11 = (BYTE *)LocalAlloc(0, cbOutput[0]);
  v12 = v11;
  if ( !v11 )
  {
    Property = -2147024882;
    v9 = 181;
    goto LABEL_10;
  }
  for ( i = &v11[v10]; v11 != i; ++v11 )
    *v11 = 0;
  v14 = NCryptGetProperty(hObject, pszProperty, v12, cbOutput[0], cbOutput, 0);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v17 = cbOutput[0];
    *(_QWORD *)a3 = v12;
    *(_DWORD *)a4 = v17;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v14,
      pcbResulta);
    LocalFree(v12);
    return v15;
  }
}

```

## disassembly

```asm
0x180013cbc  push    rbx
0x180013cbe  push    rbp
0x180013cbf  push    rsi
0x180013cc0  push    rdi
0x180013cc1  push    r14
0x180013cc3  push    r15
0x180013cc5  sub     rsp, 48h
0x180013cc9  mov     rsi, r9
0x180013ccc  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180013cd4  mov     r14, r8
0x180013cd7  mov     [rsp+78h+cbOutput], 0
0x180013cdf  lea     rax, [rsp+78h+cbOutput]
0x180013ce4  xor     r9d, r9d; cbOutput
0x180013ce7  xor     r8d, r8d; pbOutput
0x180013cea  mov     [rsp+78h+pcbResult], rax; int
0x180013cef  mov     rbp, rdx
0x180013cf2  mov     r15, rcx
0x180013cf5  call    cs:__imp_NCryptGetProperty
0x180013cfb  mov     ebx, eax
0x180013cfd  test    eax, eax
0x180013cff  jns     short loc_180013D0B
0x180013d01  mov     edx, 0B2h
0x180013d06  jmp     loc_180013D9F
0x180013d0b  mov     edi, [rsp+78h+cbOutput]
0x180013d0f  xor     ecx, ecx; uFlags
0x180013d11  mov     edx, edi; uBytes
0x180013d13  call    cs:__imp_LocalAlloc
0x180013d19  mov     rbx, rax
0x180013d1c  test    rax, rax
0x180013d1f  jz      short loc_180013D95
0x180013d21  lea     rcx, [rdi+rax]
0x180013d25  cmp     rax, rcx
0x180013d28  jz      short loc_180013D36
0x180013d2a  xor     edx, edx
0x180013d2c  mov     [rax], dl
0x180013d2e  inc     rax
0x180013d31  cmp     rax, rcx
0x180013d34  jnz     short loc_180013D2A
0x180013d36  mov     r9d, [rsp+78h+cbOutput]; cbOutput
0x180013d3b  lea     rax, [rsp+78h+cbOutput]
0x180013d40  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180013d48  mov     r8, rbx; pbOutput
0x180013d4b  mov     rdx, rbp; pszProperty
0x180013d4e  mov     [rsp+78h+pcbResult], rax; int
0x180013d53  mov     rcx, r15; hObject
0x180013d56  call    cs:__imp_NCryptGetProperty
0x180013d5c  mov     edi, eax
0x180013d5e  test    eax, eax
0x180013d60  jns     short loc_180013D88
0x180013d62  mov     rcx, [rsp+78h]; this
0x180013d67  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013d6e  mov     r9d, eax; char *
0x180013d71  mov     edx, 0BDh; void *
0x180013d76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013d7b  mov     rcx, rbx; hMem
0x180013d7e  call    cs:__imp_LocalFree
0x180013d84  mov     eax, edi
0x180013d86  jmp     short loc_180013DB5
0x180013d88  mov     eax, [rsp+78h+cbOutput]
0x180013d8c  mov     [r14], rbx
0x180013d8f  mov     [rsi], eax
0x180013d91  xor     eax, eax
0x180013d93  jmp     short loc_180013DB5
0x180013d95  mov     ebx, 8007000Eh
0x180013d9a  mov     edx, 0B5h; void *
0x180013d9f  mov     rcx, [rsp+78h]; this
0x180013da4  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013dab  mov     r9d, ebx; char *
0x180013dae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013db3  mov     eax, ebx
0x180013db5  add     rsp, 48h
0x180013db9  pop     r15
0x180013dbb  pop     r14
0x180013dbd  pop     rdi
0x180013dbe  pop     rsi
0x180013dbf  pop     rbp
0x180013dc0  pop     rbx
0x180013dc1  retn
```
