# CPreferredKeys::CPreferredKey::CopyLegacyKey(uchar * *,ulong *,_GUID *)

- ea: `0x180030a70`
- end: `0x180030ba1`
- name: `?CopyLegacyKey@CPreferredKey@CPreferredKeys@@QEAAJPEAPEAEPEAKPEAU_GUID@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(CPreferredKeys::CPreferredKey *__hidden this, unsigned __int8 **, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180030ba8`

## callees

- `0x180007f10`
- `0x180030a70`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030af2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030af2`

## string_xrefs

- `0x180030ab0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180030b0c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180030b51`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180030b76`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall CPreferredKeys::CPreferredKey::CopyLegacyKey(
        CPreferredKeys::CPreferredKey *this,
        unsigned __int8 **a2,
        unsigned int *a3,
        struct _GUID *a4)
{
  __int64 result; // rax
  __int64 v8; // rbx
  int v9; // ebp
  SIZE_T v10; // r15
  unsigned __int8 *v11; // rax
  struct _GUID v12; // xmm0

  if ( a2 && a3 && a4 )
  {
    if ( CPreferredKeys::s_preferredKeyW2K == 1 )
    {
      v8 = qword_18004C848;
      if ( qword_18004C848 && dword_18004C850 )
      {
        v9 = dword_18004C850 - 4;
        v10 = (unsigned int)(dword_18004C850 - 4);
        v11 = (unsigned __int8 *)LocalAlloc(0, v10);
        *a2 = v11;
        if ( v11 )
        {
          memcpy_0(v11, (const void *)(v8 + 4), v10);
          v12 = (struct _GUID)xmmword_18004C834;
          *a3 = v9;
          result = 0;
          *a4 = v12;
        }
        else
        {
          DebugTraceError(
            3221225495LL,
            "STATUS_NO_MEMORY",
            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
            3889);
          return 3221225495LL;
        }
      }
      else
      {
        DebugTraceError(
          3221226021LL,
          "STATUS_NOT_FOUND",
          "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
          3879);
        return 3221226021LL;
      }
    }
    else
    {
      DebugTraceError(
        3221225659LL,
        "STATUS_NOT_SUPPORTED",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
        3873);
      return 3221225659LL;
    }
  }
  else
  {
    DebugTraceError(
      3221225485LL,
      "STATUS_INVALID_PARAMETER",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      3867);
    return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x180030a70  push    rbx
0x180030a72  push    rbp
0x180030a73  push    rsi
0x180030a74  push    rdi
0x180030a75  push    r14
0x180030a77  push    r15
0x180030a79  sub     rsp, 28h
0x180030a7d  mov     rdi, r9
0x180030a80  mov     rsi, r8
0x180030a83  mov     r14, rdx
0x180030a86  test    rdx, rdx
0x180030a89  jz      loc_180030B70
0x180030a8f  test    r8, r8
0x180030a92  jz      loc_180030B70
0x180030a98  test    r9, r9
0x180030a9b  jz      loc_180030B70
0x180030aa1  cmp     cs:?s_preferredKeyW2K@CPreferredKeys@@0VCPreferredKey@1@A, 1; CPreferredKeys::CPreferredKey CPreferredKeys::s_preferredKeyW2K
0x180030aa8  jz      short loc_180030AD2
0x180030aaa  mov     r9d, 0F21h
0x180030ab0  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030ab7  lea     rdx, aStatusNotSuppo; "STATUS_NOT_SUPPORTED"
0x180030abe  mov     ecx, 0C00000BBh
0x180030ac3  call    DebugTraceError
0x180030ac8  mov     eax, 0C00000BBh
0x180030acd  jmp     loc_180030B93
0x180030ad2  mov     rbx, cs:qword_18004C848
0x180030ad9  test    rbx, rbx
0x180030adc  jz      short loc_180030B4B
0x180030ade  mov     eax, cs:dword_18004C850
0x180030ae4  test    eax, eax
0x180030ae6  jz      short loc_180030B4B
0x180030ae8  lea     ebp, [rax-4]
0x180030aeb  xor     ecx, ecx; uFlags
0x180030aed  mov     edx, ebp; uBytes
0x180030aef  mov     r15d, ebp
0x180030af2  call    cs:__imp_LocalAlloc
0x180030af9  nop     dword ptr [rax+rax+00h]
0x180030afe  mov     [r14], rax
0x180030b01  test    rax, rax
0x180030b04  jnz     short loc_180030B2B
0x180030b06  mov     r9d, 0F31h
0x180030b0c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030b13  lea     rdx, aStatusNoMemory; "STATUS_NO_MEMORY"
0x180030b1a  mov     ecx, 0C0000017h
0x180030b1f  call    DebugTraceError
0x180030b24  mov     eax, 0C0000017h
0x180030b29  jmp     short loc_180030B93
0x180030b2b  lea     rdx, [rbx+4]; Src
0x180030b2f  mov     r8, r15; Size
0x180030b32  mov     rcx, rax; void *
0x180030b35  call    memcpy_0
0x180030b3a  movups  xmm0, cs:xmmword_18004C834
0x180030b41  mov     [rsi], ebp
0x180030b43  xor     eax, eax
0x180030b45  movdqu  xmmword ptr [rdi], xmm0
0x180030b49  jmp     short loc_180030B93
0x180030b4b  mov     r9d, 0F27h
0x180030b51  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030b58  lea     rdx, aStatusNotFound; "STATUS_NOT_FOUND"
0x180030b5f  mov     ecx, 0C0000225h
0x180030b64  call    DebugTraceError
0x180030b69  mov     eax, 0C0000225h
0x180030b6e  jmp     short loc_180030B93
0x180030b70  mov     r9d, 0F1Bh
0x180030b76  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030b7d  lea     rdx, aStatusInvalidP; "STATUS_INVALID_PARAMETER"
0x180030b84  mov     ecx, 0C000000Dh
0x180030b89  call    DebugTraceError
0x180030b8e  mov     eax, 0C000000Dh
0x180030b93  add     rsp, 28h
0x180030b97  pop     r15
0x180030b99  pop     r14
0x180030b9b  pop     rdi
0x180030b9c  pop     rsi
0x180030b9d  pop     rbp
0x180030b9e  pop     rbx
0x180030b9f  retn
```
