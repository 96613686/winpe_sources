# _GetNCryptBlobProperty(unsigned __int64,ushort const *,ulong *,uchar * *,ulong)

- ea: `0x1800048d0`
- end: `0x1800049e3`
- name: `?_GetNCryptBlobProperty@@YAJ_KPEBGPEAKPEAPEAEK@Z`
- size: `275`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, LPCWSTR pszProperty, unsigned int *, unsigned __int8 **, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008ca4`
- `0x180008d58`

## callees

- `0x180003750`
- `0x1800048d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800049ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800049ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004945`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004945`
- `ncrypt!NCryptGetProperty` at `0x180004929`
- `ncrypt!NCryptGetProperty` at `0x180004929`

## pseudocode

```c
__int64 __fastcall _GetNCryptBlobProperty(
        NCRYPT_HANDLE hObject,
        LPCWSTR pszProperty,
        unsigned int *a3,
        unsigned __int8 **a4,
        DWORD a5)
{
  DWORD dwFlags; // r15d
  unsigned int v6; // edi
  BYTE *v7; // rbx
  SECURITY_STATUS Property; // eax
  unsigned int v13; // esi
  DWORD *pcbResult; // [rsp+20h] [rbp-58h]
  DWORD v16; // [rsp+98h] [rbp+20h] BYREF

  dwFlags = a5;
  v6 = 0;
  v7 = 0;
  *a4 = 0;
  while ( 1 )
  {
    v16 = 0;
    Property = NCryptGetProperty(hObject, pszProperty, v7, v6, &v16, dwFlags);
    v13 = Property;
    if ( Property )
    {
      LODWORD(pcbResult) = Property;
      ekTraceFmt(0x4912C2u, 1, "ERROR: NCryptGetProperty(%ws) Hr=%x\n", pszProperty, pcbResult);
      goto LABEL_10;
    }
    if ( v7 )
      break;
    v6 = v16;
    v7 = (BYTE *)LocalAlloc(0, v16);
    if ( !v7 )
    {
      v13 = -2147024882;
      ekTraceFmt(0x5C12C2u, 1, "ERROR: LocalAlloc. Return=%d\n", -2147024882);
      goto LABEL_10;
    }
  }
  if ( v6 == v16 )
  {
    *a4 = v7;
    v7 = 0;
    v13 = 0;
    *a3 = v6;
  }
  else
  {
    v13 = -2147024736;
    ekTraceFmt(0x5112C2u, 1, "ERROR: cbProp != cbPropT. Hr=%x\n", -2147024736);
  }
LABEL_10:
  LocalFree(v7);
  return v13;
}

```

## disassembly

```asm
0x1800048d0  push    rbx
0x1800048d2  push    rbp
0x1800048d3  push    rsi
0x1800048d4  push    rdi
0x1800048d5  push    r12
0x1800048d7  push    r13
0x1800048d9  push    r14
0x1800048db  push    r15
0x1800048dd  sub     rsp, 38h
0x1800048e1  mov     r15d, [rsp+78h+arg_20]
0x1800048e9  xor     edi, edi
0x1800048eb  xor     ebx, ebx
0x1800048ed  mov     r12, r9
0x1800048f0  mov     [r9], rbx
0x1800048f3  mov     r13, r8
0x1800048f6  mov     rbp, rdx
0x1800048f9  mov     r14, rcx
0x1800048fc  nop     dword ptr [rax+00h]
0x180004900  lea     rax, [rsp+78h+arg_18]
0x180004908  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x18000490d  mov     r9d, edi; cbOutput
0x180004910  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180004915  mov     r8, rbx; pbOutput
0x180004918  mov     [rsp+78h+arg_18], 0
0x180004923  mov     rdx, rbp; pszProperty
0x180004926  mov     rcx, r14; hObject
0x180004929  call    cs:__imp_NCryptGetProperty
0x18000492f  mov     esi, eax
0x180004931  test    eax, eax
0x180004933  jnz     short loc_1800049AA
0x180004935  test    rbx, rbx
0x180004938  jnz     short loc_180004973
0x18000493a  mov     edi, [rsp+78h+arg_18]
0x180004941  xor     ecx, ecx; uFlags
0x180004943  mov     edx, edi; uBytes
0x180004945  call    cs:__imp_LocalAlloc
0x18000494b  mov     rbx, rax
0x18000494e  test    rax, rax
0x180004951  jnz     short loc_180004900
0x180004953  mov     esi, 8007000Eh
0x180004958  lea     r8, aErrorLocalallo_0; "ERROR: LocalAlloc. Return=%d\n"
0x18000495f  mov     r9d, esi
0x180004962  mov     edx, 1; unsigned int
0x180004967  mov     ecx, 5C12C2h; unsigned int
0x18000496c  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004971  jmp     short loc_1800049C7
0x180004973  cmp     edi, [rsp+78h+arg_18]
0x18000497a  jz      short loc_18000499C
0x18000497c  mov     esi, 800700A0h
0x180004981  lea     r8, aErrorCbpropCbp; "ERROR: cbProp != cbPropT. Hr=%x\n"
0x180004988  mov     r9d, esi
0x18000498b  mov     edx, 1; unsigned int
0x180004990  mov     ecx, 5112C2h; unsigned int
0x180004995  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000499a  jmp     short loc_1800049C7
0x18000499c  mov     [r12], rbx
0x1800049a0  xor     ebx, ebx
0x1800049a2  xor     esi, esi
0x1800049a4  mov     [r13+0], edi
0x1800049a8  jmp     short loc_1800049C7
0x1800049aa  mov     r9, rbp
0x1800049ad  mov     dword ptr [rsp+78h+pcbResult], eax
0x1800049b1  lea     r8, aErrorNcryptget; "ERROR: NCryptGetProperty(%ws) Hr=%x\n"
0x1800049b8  mov     edx, 1; unsigned int
0x1800049bd  mov     ecx, 4912C2h; unsigned int
0x1800049c2  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800049c7  mov     rcx, rbx; hMem
0x1800049ca  call    cs:__imp_LocalFree
0x1800049d0  mov     eax, esi
0x1800049d2  add     rsp, 38h
0x1800049d6  pop     r15
0x1800049d8  pop     r14
0x1800049da  pop     r13
0x1800049dc  pop     r12
0x1800049de  pop     rdi
0x1800049df  pop     rsi
0x1800049e0  pop     rbp
0x1800049e1  pop     rbx
0x1800049e2  retn
```
