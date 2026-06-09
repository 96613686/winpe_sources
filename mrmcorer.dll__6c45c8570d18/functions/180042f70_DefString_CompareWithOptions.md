# DefString_CompareWithOptions

- ea: `0x180042f70`
- end: `0x180042fef`
- name: `DefString_CompareWithOptions`
- size: `127`
- prototype: ``
- caller_count: `38`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001028c`
- `0x18002d0c0`
- `0x1800449b4`
- `0x18004619c`
- `0x180046e78`
- `0x18004bd38`
- `0x1800579d0`
- `0x18006b6b0`
- `0x18006b8f0`
- `0x1800790a0`
- `0x18007af30`
- `0x18008bdb0`
- `0x18008c120`
- `0x18008c370`
- `0x180090310`
- `0x1800908e0`
- `0x1800909b0`
- `0x1800924d0`
- `0x1800961f0`
- `0x180096690`
- `0x180096950`
- `0x180098e30`
- `0x180099d50`
- `0x180099ed0`
- `0x18009cb40`
- `0x18009e598`
- `0x1800a56c0`
- `0x1800a5c80`
- `0x1800a6370`
- `0x1800a709c`
- `0x1800a7884`
- `0x1800a8650`
- `0x1800a9570`
- `0x1800a9b9c`
- `0x1800a9e5c`
- `0x1800b9760`
- `0x1800b9930`
- `0x1800b9c80`

## callees

- `0x180042f70`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042f90`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042fd0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042f90`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180042fd0`

## pseudocode

```c
__int64 __fastcall DefString_CompareWithOptions(const WCHAR *a1, const WCHAR *a2, int a3)
{
  int v3; // ecx
  __int64 result; // rax

  if ( a3 )
  {
    if ( a3 != 1 )
      return 0x7FFFFFFF;
    v3 = CompareStringOrdinal(a1, -1, a2, -1, 1) - 2;
    result = 0x7FFFFFFF;
    if ( v3 != 0x7FFFFFFF )
    {
      if ( v3 >= 0 )
        return v3 > 0;
      return 0xFFFFFFFFLL;
    }
  }
  else
  {
    v3 = CompareStringOrdinal(a1, -1, a2, -1, 0) - 2;
    result = 0x7FFFFFFF;
    if ( v3 != 0x7FFFFFFF )
    {
      if ( v3 >= 0 )
        return v3 > 0;
      return 0xFFFFFFFFLL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180042f70  sub     rsp, 38h
0x180042f74  test    r8d, r8d
0x180042f77  jz      short loc_180042FBC
0x180042f79  cmp     r8d, 1
0x180042f7d  jnz     short loc_180042FE8
0x180042f7f  mov     [rsp+38h+bIgnoreCase], r8d; bIgnoreCase
0x180042f84  mov     r9d, 0FFFFFFFFh; cchCount2
0x180042f8a  mov     r8, rdx; lpString2
0x180042f8d  mov     edx, r9d; cchCount1
0x180042f90  call    cs:__imp_CompareStringOrdinal
0x180042f96  lea     ecx, [rax-2]; lpString1
0x180042f99  mov     eax, 7FFFFFFFh
0x180042f9e  cmp     ecx, eax
0x180042fa0  jz      short loc_180042FAD
0x180042fa2  test    ecx, ecx
0x180042fa4  js      short loc_180042FB2
0x180042fa6  xor     eax, eax
0x180042fa8  test    ecx, ecx
0x180042faa  setnle  al
0x180042fad  add     rsp, 38h
0x180042fb1  retn
0x180042fb2  mov     eax, 0FFFFFFFFh
0x180042fb7  add     rsp, 38h
0x180042fbb  retn
0x180042fbc  mov     r9d, 0FFFFFFFFh; cchCount2
0x180042fc2  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x180042fca  mov     r8, rdx; lpString2
0x180042fcd  mov     edx, r9d; cchCount1
0x180042fd0  call    cs:__imp_CompareStringOrdinal
0x180042fd6  lea     ecx, [rax-2]
0x180042fd9  mov     eax, 7FFFFFFFh
0x180042fde  cmp     ecx, eax
0x180042fe0  jz      short loc_180042FAD
0x180042fe2  test    ecx, ecx
0x180042fe4  jns     short loc_180042FA6
0x180042fe6  jmp     short loc_180042FB2
0x180042fe8  mov     eax, 7FFFFFFFh
0x180042fed  jmp     short loc_180042FAD
```
