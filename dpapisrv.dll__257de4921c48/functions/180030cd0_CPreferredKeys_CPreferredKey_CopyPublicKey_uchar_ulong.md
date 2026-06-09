# CPreferredKeys::CPreferredKey::CopyPublicKey(uchar * *,ulong *)

- ea: `0x180030cd0`
- end: `0x180030de9`
- name: `?CopyPublicKey@CPreferredKey@CPreferredKeys@@QEAAJPEAPEAEPEAK@Z`
- size: `281`
- prototype: `__int64 __fastcall(CPreferredKeys::CPreferredKey *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180030df0`

## callees

- `0x180007f10`
- `0x180030cd0`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030d44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030d44`

## string_xrefs

- `0x180030d02`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180030d61`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180030d9b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180030dc0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall CPreferredKeys::CPreferredKey::CopyPublicKey(
        CPreferredKeys::CPreferredKey *this,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  __int64 result; // rax
  __int64 v6; // rbx
  SIZE_T v7; // rbp
  __int64 v8; // r14
  unsigned __int8 *v9; // rax

  if ( a2 && a3 )
  {
    if ( CPreferredKeys::s_preferredKey == 2 )
    {
      v6 = qword_18004C8D8;
      if ( qword_18004C8D8 && dword_18004C8E0 )
      {
        v7 = *(unsigned int *)(qword_18004C8D8 + 8);
        v8 = *(unsigned int *)(qword_18004C8D8 + 4);
        v9 = (unsigned __int8 *)LocalAlloc(0, v7);
        *a2 = v9;
        if ( v9 )
        {
          memcpy_0(v9, (const void *)(v8 + v6 + 12), v7);
          result = 0;
          *a3 = v7;
        }
        else
        {
          DebugTraceError(
            3221225495LL,
            "STATUS_NO_MEMORY",
            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
            3853);
          return 3221225495LL;
        }
      }
      else
      {
        DebugTraceError(
          3221226021LL,
          "STATUS_NOT_FOUND",
          "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
          3843);
        return 3221226021LL;
      }
    }
    else
    {
      DebugTraceError(
        3221225659LL,
        "STATUS_NOT_SUPPORTED",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
        3837);
      return 3221225659LL;
    }
  }
  else
  {
    DebugTraceError(
      3221225485LL,
      "STATUS_INVALID_PARAMETER",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      3831);
    return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x180030cd0  push    rbx
0x180030cd2  push    rbp
0x180030cd3  push    rsi
0x180030cd4  push    rdi
0x180030cd5  push    r14
0x180030cd7  sub     rsp, 20h
0x180030cdb  mov     rdi, r8
0x180030cde  mov     rsi, rdx
0x180030ce1  test    rdx, rdx
0x180030ce4  jz      loc_180030DBA
0x180030cea  test    r8, r8
0x180030ced  jz      loc_180030DBA
0x180030cf3  cmp     cs:?s_preferredKey@CPreferredKeys@@0VCPreferredKey@1@A, 2; CPreferredKeys::CPreferredKey CPreferredKeys::s_preferredKey
0x180030cfa  jz      short loc_180030D24
0x180030cfc  mov     r9d, 0EFDh
0x180030d02  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030d09  lea     rdx, aStatusNotSuppo; "STATUS_NOT_SUPPORTED"
0x180030d10  mov     ecx, 0C00000BBh
0x180030d15  call    DebugTraceError
0x180030d1a  mov     eax, 0C00000BBh
0x180030d1f  jmp     loc_180030DDD
0x180030d24  mov     rbx, cs:qword_18004C8D8
0x180030d2b  test    rbx, rbx
0x180030d2e  jz      short loc_180030D95
0x180030d30  cmp     cs:dword_18004C8E0, 0
0x180030d37  jz      short loc_180030D95
0x180030d39  mov     ebp, [rbx+8]
0x180030d3c  xor     ecx, ecx; uFlags
0x180030d3e  mov     r14d, [rbx+4]
0x180030d42  mov     edx, ebp; uBytes
0x180030d44  call    cs:__imp_LocalAlloc
0x180030d4b  nop     dword ptr [rax+rax+00h]
0x180030d50  mov     [rsi], rax
0x180030d53  mov     rcx, rax; void *
0x180030d56  test    rax, rax
0x180030d59  jnz     short loc_180030D80
0x180030d5b  mov     r9d, 0F0Dh
0x180030d61  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030d68  lea     rdx, aStatusNoMemory; "STATUS_NO_MEMORY"
0x180030d6f  mov     ecx, 0C0000017h
0x180030d74  call    DebugTraceError
0x180030d79  mov     eax, 0C0000017h
0x180030d7e  jmp     short loc_180030DDD
0x180030d80  lea     rdx, [rbx+0Ch]
0x180030d84  mov     r8, rbp; Size
0x180030d87  add     rdx, r14; Src
0x180030d8a  call    memcpy_0
0x180030d8f  xor     eax, eax
0x180030d91  mov     [rdi], ebp
0x180030d93  jmp     short loc_180030DDD
0x180030d95  mov     r9d, 0F03h
0x180030d9b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030da2  lea     rdx, aStatusNotFound; "STATUS_NOT_FOUND"
0x180030da9  mov     ecx, 0C0000225h
0x180030dae  call    DebugTraceError
0x180030db3  mov     eax, 0C0000225h
0x180030db8  jmp     short loc_180030DDD
0x180030dba  mov     r9d, 0EF7h
0x180030dc0  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030dc7  lea     rdx, aStatusInvalidP; "STATUS_INVALID_PARAMETER"
0x180030dce  mov     ecx, 0C000000Dh
0x180030dd3  call    DebugTraceError
0x180030dd8  mov     eax, 0C000000Dh
0x180030ddd  add     rsp, 20h
0x180030de1  pop     r14
0x180030de3  pop     rdi
0x180030de4  pop     rsi
0x180030de5  pop     rbp
0x180030de6  pop     rbx
0x180030de7  retn
```
