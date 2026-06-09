# CPreferredKeys::CPreferredKey::CopyBuffer(uchar * *,ulong *)

- ea: `0x180030864`
- end: `0x18003094b`
- name: `?CopyBuffer@CPreferredKey@CPreferredKeys@@QEAAJPEAPEAEPEAK@Z`
- size: `231`
- prototype: `__int64 __fastcall(const void **this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180030954`

## callees

- `0x180007f10`
- `0x180030864`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800308a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800308a0`

## string_xrefs

- `0x1800308ba`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800308f8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x18003091d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall CPreferredKeys::CPreferredKey::CopyBuffer(const void **this, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned __int8 *v6; // rax

  if ( a2 && a3 )
  {
    if ( this[3] && *((_DWORD *)this + 8) )
    {
      v6 = (unsigned __int8 *)LocalAlloc(0, *((unsigned int *)this + 8));
      *a2 = v6;
      if ( v6 )
      {
        memcpy_0(v6, this[3], *((unsigned int *)this + 8));
        *a3 = *((_DWORD *)this + 8);
        return 0;
      }
      else
      {
        DebugTraceError(
          3221225495LL,
          "STATUS_NO_MEMORY",
          "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
          3818);
        return 3221225495LL;
      }
    }
    else
    {
      DebugTraceError(
        3221226021LL,
        "STATUS_NOT_FOUND",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
        3811);
      return 3221226021LL;
    }
  }
  else
  {
    DebugTraceError(
      3221225485LL,
      "STATUS_INVALID_PARAMETER",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      3805);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180030864  mov     [rsp+arg_0], rbx
0x180030869  mov     [rsp+arg_8], rsi
0x18003086e  push    rdi
0x18003086f  sub     rsp, 20h
0x180030873  mov     rdi, r8
0x180030876  mov     rsi, rdx
0x180030879  mov     rbx, rcx
0x18003087c  test    rdx, rdx
0x18003087f  jz      loc_180030917
0x180030885  test    r8, r8
0x180030888  jz      loc_180030917
0x18003088e  cmp     qword ptr [rcx+18h], 0
0x180030893  jz      short loc_1800308F2
0x180030895  cmp     dword ptr [rcx+20h], 0
0x180030899  jz      short loc_1800308F2
0x18003089b  mov     edx, [rcx+20h]; uBytes
0x18003089e  xor     ecx, ecx; uFlags
0x1800308a0  call    cs:__imp_LocalAlloc
0x1800308a7  nop     dword ptr [rax+rax+00h]
0x1800308ac  mov     [rsi], rax
0x1800308af  test    rax, rax
0x1800308b2  jnz     short loc_1800308D9
0x1800308b4  mov     r9d, 0EEAh
0x1800308ba  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800308c1  lea     rdx, aStatusNoMemory; "STATUS_NO_MEMORY"
0x1800308c8  mov     ecx, 0C0000017h
0x1800308cd  call    DebugTraceError
0x1800308d2  mov     eax, 0C0000017h
0x1800308d7  jmp     short loc_18003093A
0x1800308d9  mov     r8d, [rbx+20h]; Size
0x1800308dd  mov     rcx, rax; void *
0x1800308e0  mov     rdx, [rbx+18h]; Src
0x1800308e4  call    memcpy_0
0x1800308e9  mov     eax, [rbx+20h]
0x1800308ec  mov     [rdi], eax
0x1800308ee  xor     eax, eax
0x1800308f0  jmp     short loc_18003093A
0x1800308f2  mov     r9d, 0EE3h
0x1800308f8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800308ff  lea     rdx, aStatusNotFound; "STATUS_NOT_FOUND"
0x180030906  mov     ecx, 0C0000225h
0x18003090b  call    DebugTraceError
0x180030910  mov     eax, 0C0000225h
0x180030915  jmp     short loc_18003093A
0x180030917  mov     r9d, 0EDDh
0x18003091d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180030924  lea     rdx, aStatusInvalidP; "STATUS_INVALID_PARAMETER"
0x18003092b  mov     ecx, 0C000000Dh
0x180030930  call    DebugTraceError
0x180030935  mov     eax, 0C000000Dh
0x18003093a  mov     rbx, [rsp+28h+arg_0]
0x18003093f  mov     rsi, [rsp+28h+arg_8]
0x180030944  add     rsp, 20h
0x180030948  pop     rdi
0x180030949  retn
```
