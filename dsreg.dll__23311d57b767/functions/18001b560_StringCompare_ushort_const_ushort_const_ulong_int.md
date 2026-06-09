# StringCompare(ushort const *,ushort const *,ulong,int *)

- ea: `0x18001b560`
- end: `0x18001b695`
- name: `?StringCompare@@YAJPEBG0KPEAH@Z`
- size: `309`
- prototype: `__int64 __fastcall(LPCWCH lpString1, const unsigned __int16 *, unsigned int, int *)`
- caller_count: `34`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c0d0`
- `0x1800108e0`
- `0x180022ed0`
- `0x1800264a8`
- `0x180026a24`
- `0x18002708c`
- `0x180029e68`
- `0x18002d2d8`
- `0x180032618`
- `0x180042c18`
- `0x1800439d4`
- `0x1800496d0`
- `0x180049f70`
- `0x18004cd68`
- `0x18004d1b4`
- `0x18004eeb0`
- `0x180053630`
- `0x18005c95c`
- `0x1800618b0`
- `0x180065f28`
- `0x180074c58`
- `0x180076b40`
- `0x180076b8c`
- `0x18007a110`
- `0x18007ba88`
- `0x180080674`
- `0x1800822b0`
- `0x180085640`
- `0x180086538`
- `0x1800966a8`
- `0x180096ad4`
- `0x180096d08`
- `0x1800a13f0`
- `0x1800b2e10`

## callees

- `0x1800084f4`
- `0x18001b560`
- `0x1800307c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b61a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b61a`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18001b5a4`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18001b5a4`

## string_xrefs

- `0x18001b5f2`: `StringCompare`
- `0x18001b60c`: `StringCompare`
- `0x18001b658`: `StringCompare`
- `0x18001b65f`: `StringCompare`
- `0x18001b62e`: `CompareStringInternal`
- `0x18001b625`: `CompareStringEx`

## pseudocode

```c
__int64 __fastcall StringCompare(LPCWCH lpString1, const unsigned __int16 *a2, DWORD a3, int *a4)
{
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // eax
  signed int LastError; // ebx
  bool v11; // sf

  if ( !a4 )
  {
    LastError = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"StringCompare", L"equal");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"StringCompare", L"equal");
    return (unsigned int)LastError;
  }
  v5 = CompareStringEx(&cchOriginalDestLength, a3, lpString1, -1, a2, -1, 0, 0, 0);
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1359;
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"CompareStringInternal",
      L"CompareStringEx",
      (unsigned int)LastError);
    v8 = 0;
    v11 = LastError < 0;
    if ( LastError <= 0 )
    {
LABEL_15:
      if ( v11 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"StringCompare",
          L"StringCompare",
          (unsigned int)LastError);
        return (unsigned int)LastError;
      }
      goto LABEL_8;
    }
LABEL_18:
    LastError = (unsigned __int16)LastError | 0x80070000;
    v11 = LastError < 0;
    goto LABEL_15;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v8 = 1;
    goto LABEL_7;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v8 = 2;
    goto LABEL_7;
  }
  if ( v7 != 1 )
  {
    v8 = 0;
    LOWORD(LastError) = 1359;
    goto LABEL_18;
  }
  v8 = 3;
LABEL_7:
  LastError = 0;
LABEL_8:
  *a4 = v8 == 2;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001b560  mov     r11, rsp
0x18001b563  push    rbx
0x18001b564  push    rdi
0x18001b565  sub     rsp, 58h
0x18001b569  mov     rdi, r9
0x18001b56c  mov     eax, r8d
0x18001b56f  test    r9, r9
0x18001b572  jz      short loc_18001B5E6
0x18001b574  mov     qword ptr [r11-28h], 0
0x18001b57c  or      r9d, 0FFFFFFFFh; cchCount1
0x18001b580  mov     qword ptr [r11-30h], 0
0x18001b588  mov     r8, rcx; lpString1
0x18001b58b  mov     qword ptr [r11-38h], 0
0x18001b593  lea     rcx, cchOriginalDestLength; lpLocaleName
0x18001b59a  mov     [r11-40h], r9d
0x18001b59e  mov     [r11-48h], rdx
0x18001b5a2  mov     edx, eax; dwCmpFlags
0x18001b5a4  call    cs:__imp_CompareStringEx
0x18001b5aa  mov     ecx, eax
0x18001b5ac  test    eax, eax
0x18001b5ae  jz      short loc_18001B61A
0x18001b5b0  sub     ecx, 1
0x18001b5b3  jz      short loc_18001B5DF
0x18001b5b5  sub     ecx, 1
0x18001b5b8  jz      loc_18001B68B
0x18001b5be  cmp     ecx, 1
0x18001b5c1  jnz     loc_18001B677
0x18001b5c7  lea     eax, [rcx+2]
0x18001b5ca  xor     ebx, ebx
0x18001b5cc  xor     ecx, ecx
0x18001b5ce  cmp     eax, 2
0x18001b5d1  setz    cl
0x18001b5d4  mov     [rdi], ecx
0x18001b5d6  mov     eax, ebx
0x18001b5d8  add     rsp, 58h
0x18001b5dc  pop     rdi
0x18001b5dd  pop     rbx
0x18001b5de  retn
0x18001b5df  mov     eax, 1
0x18001b5e4  jmp     short loc_18001B5CA
0x18001b5e6  lea     r8, aEqual; "equal"
0x18001b5ed  mov     ebx, 80070057h
0x18001b5f2  lea     rdx, aStringcompare; "StringCompare"
0x18001b5f9  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18001b600  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001b605  lea     rdx, aEqual; "equal"
0x18001b60c  lea     rcx, aStringcompare; "StringCompare"
0x18001b613  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18001b618  jmp     short loc_18001B5D6
0x18001b61a  call    cs:__imp_GetLastError
0x18001b620  mov     ecx, 54Fh
0x18001b625  lea     r8, aComparestringe; "CompareStringEx"
0x18001b62c  test    eax, eax
0x18001b62e  lea     rdx, aComparestringi; "CompareStringInternal"
0x18001b635  mov     ebx, eax
0x18001b637  cmovz   ebx, ecx
0x18001b63a  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001b641  mov     r9d, ebx
0x18001b644  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001b649  xor     eax, eax
0x18001b64b  test    ebx, ebx
0x18001b64d  jg      short loc_18001B67E
0x18001b64f  jns     loc_18001B5CC
0x18001b655  mov     r9d, ebx
0x18001b658  lea     r8, aStringcompare; "StringCompare"
0x18001b65f  lea     rdx, aStringcompare; "StringCompare"
0x18001b666  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18001b66d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001b672  jmp     loc_18001B5D6
0x18001b677  xor     eax, eax
0x18001b679  mov     ebx, 54Fh
0x18001b67e  movzx   ebx, bx
0x18001b681  or      ebx, 80070000h
0x18001b687  test    ebx, ebx
0x18001b689  jmp     short loc_18001B64F
0x18001b68b  mov     eax, 2
0x18001b690  jmp     loc_18001B5CA
```
