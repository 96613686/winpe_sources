# CopyStringNullSafeW(ushort const *,ushort * *)

- ea: `0x18000f520`
- end: `0x18000f6ce`
- name: `?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z`
- size: `430`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180025788`

## callees

- `0x18000f520`
- `0x180027278`
- `0x180027448`
- `0x18002bc58`
- `0x18002e664`
- `0x18002e814`
- `0x18002f710`

## string_xrefs

- `0x18000f646`: `CopyStringW`
- `0x18000f6a4`: `CopyStringW`
- `0x18000f580`: `CopyStringSafeW`
- `0x18000f59b`: `CopyStringSafeW`
- `0x18000f5a2`: `CopyStringNullSafeW`
- `0x18000f67a`: `CopyStringNullSafeW`
- `0x18000f694`: `CopyStringNullSafeW`

## pseudocode

```c
__int64 __fastcall CopyStringNullSafeW(const unsigned __int16 *Source, unsigned __int16 **a2)
{
  __int64 v2; // rsi
  __int64 result; // rax
  const unsigned __int16 *v6; // rax
  __int64 v7; // rcx
  signed int v8; // edi
  const wchar_t *v9; // rbp
  unsigned int v10; // esi
  __int64 v11; // rsi
  unsigned __int64 v12; // rax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  rsize_t v15; // rsi
  unsigned int v16; // eax
  __int64 v17; // [rsp+20h] [rbp-18h]

  if ( !a2 )
  {
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
    return 2147942487LL;
  }
  *a2 = 0;
  result = 0;
  if ( Source )
  {
    v17 = v2;
    v6 = Source;
    v7 = 0x7FFFFFFF;
    while ( *v6 )
    {
      ++v6;
      if ( !--v7 )
      {
        v8 = -2147024809;
        v9 = L"StringCchLengthW";
        goto LABEL_7;
      }
    }
    v11 = 0x7FFFFFFF - v7;
    *a2 = 0;
    v12 = 2 * (0x7FFFFFFF - v7 + 1);
    if ( !is_mul_ok(0x7FFFFFFF - v7 + 1, 2u) )
      v12 = -1;
    v13 = (unsigned __int16 *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    v14 = v13;
    if ( v13 )
    {
      v15 = 2 * v11;
      v16 = memcpy_s_0(v13, v15, Source, v15);
      v8 = v16;
      if ( !v16 )
      {
        v14[v15 / 2] = 0;
        *a2 = v14;
        operator delete(0);
        return 0;
      }
      v9 = L"CopyStringW";
      Logger::TraceError(L"%s: wmemcpy_s failed with error code: 0x%08x.", L"CopyStringW", v16);
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      operator delete(v14);
      if ( v8 >= 0 )
        return (unsigned int)v8;
LABEL_7:
      v10 = v8;
    }
    else
    {
      v9 = L"CopyStringW";
      v8 = -2147024882;
      v10 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CopyStringW");
      operator delete(0);
    }
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"CopyStringSafeW", v9, v10, v17);
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"CopyStringNullSafeW",
      L"CopyStringSafeW",
      (unsigned int)v8);
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000f520  push    rdi
0x18000f522  push    r14
0x18000f524  sub     rsp, 28h
0x18000f528  mov     r14, rdx
0x18000f52b  mov     rdi, rcx
0x18000f52e  test    rdx, rdx
0x18000f531  jz      loc_18000F66E
0x18000f537  mov     [rsp+38h+arg_18], rbp
0x18000f53c  xor     ebp, ebp
0x18000f53e  mov     [rdx], rbp
0x18000f541  mov     eax, ebp
0x18000f543  test    rcx, rcx
0x18000f546  jz      loc_18000F639
0x18000f54c  mov     [rsp+38h+var_18], rsi
0x18000f551  mov     rax, rdi
0x18000f554  mov     esi, 7FFFFFFFh
0x18000f559  mov     [rsp+38h+arg_10], rbx
0x18000f55e  mov     ecx, esi
0x18000f560  cmp     [rax], bp
0x18000f563  jz      short loc_18000F5B9
0x18000f565  add     rax, 2
0x18000f569  sub     rcx, 1
0x18000f56d  jnz     short loc_18000F560
0x18000f56f  mov     edi, 80070057h
0x18000f574  lea     rbp, aStringcchlengt; "StringCchLengthW"
0x18000f57b  mov     esi, edi
0x18000f57d  mov     r9d, esi
0x18000f580  lea     rdx, aCopystringsafe; "CopyStringSafeW"
0x18000f587  mov     r8, rbp
0x18000f58a  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18000f591  mov     ebx, edi
0x18000f593  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000f598  mov     r9d, edi
0x18000f59b  lea     r8, aCopystringsafe; "CopyStringSafeW"
0x18000f5a2  lea     rdx, aCopystringnull; "CopyStringNullSafeW"
0x18000f5a9  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18000f5b0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000f5b5  mov     eax, ebx
0x18000f5b7  jmp     short loc_18000F62F
0x18000f5b9  sub     rsi, rcx
0x18000f5bc  mov     [rdx], rbp
0x18000f5bf  mov     eax, 2
0x18000f5c4  lea     rcx, [rsi+1]
0x18000f5c8  mul     rcx
0x18000f5cb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f5d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f5d9  cmovb   rax, rcx
0x18000f5dd  mov     rcx, rax; unsigned __int64
0x18000f5e0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000f5e5  mov     rbx, rax
0x18000f5e8  test    rax, rax
0x18000f5eb  jz      loc_18000F6A4
0x18000f5f1  add     rsi, rsi
0x18000f5f4  mov     r8, rdi; Source
0x18000f5f7  mov     r9, rsi; SourceSize
0x18000f5fa  mov     rdx, rsi; DestinationSize
0x18000f5fd  mov     rcx, rax; Destination
0x18000f600  call    memcpy_s_0
0x18000f605  mov     edi, eax
0x18000f607  test    eax, eax
0x18000f609  jnz     short loc_18000F646
0x18000f60b  mov     [rsi+rbx], bp
0x18000f60f  xor     ecx, ecx; Block
0x18000f611  mov     [r14], rbx
0x18000f614  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f619  mov     eax, ebp
0x18000f61b  jmp     short loc_18000F62F
0x18000f61d  mov     rcx, rbx; Block
0x18000f620  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f625  test    edi, edi
0x18000f627  js      loc_18000F57B
0x18000f62d  mov     eax, edi
0x18000f62f  mov     rbx, [rsp+38h+arg_10]
0x18000f634  mov     rsi, [rsp+38h+var_18]
0x18000f639  mov     rbp, [rsp+38h+arg_18]
0x18000f63e  add     rsp, 28h
0x18000f642  pop     r14
0x18000f644  pop     rdi
0x18000f645  retn
0x18000f646  lea     rbp, aCopystringw; "CopyStringW"
0x18000f64d  mov     r8d, edi
0x18000f650  mov     rdx, rbp
0x18000f653  lea     rcx, aSWmemcpySFaile; "%s: wmemcpy_s failed with error code: 0"...
0x18000f65a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000f65f  test    edi, edi
0x18000f661  jle     short loc_18000F61D
0x18000f663  movzx   edi, di
0x18000f666  or      edi, 80070000h
0x18000f66c  jmp     short loc_18000F61D
0x18000f66e  lea     r8, aPpszout; "ppszOut"
0x18000f675  mov     edi, 80070057h
0x18000f67a  lea     rdx, aCopystringnull; "CopyStringNullSafeW"
0x18000f681  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000f688  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000f68d  lea     rdx, aPpszout; "ppszOut"
0x18000f694  lea     rcx, aCopystringnull; "CopyStringNullSafeW"
0x18000f69b  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000f6a0  mov     eax, edi
0x18000f6a2  jmp     short loc_18000F63E
0x18000f6a4  lea     rbp, aCopystringw; "CopyStringW"
0x18000f6ab  mov     edi, 8007000Eh
0x18000f6b0  mov     rdx, rbp
0x18000f6b3  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000f6ba  mov     esi, edi
0x18000f6bc  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000f6c1  mov     rcx, rbx; Block
0x18000f6c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f6c9  jmp     loc_18000F57D
```
