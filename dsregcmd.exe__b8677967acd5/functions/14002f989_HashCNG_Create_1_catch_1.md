# _HashCNG::Create_::_1_::catch$1

- ea: `0x14002f989`
- end: `0x14002f9c4`
- name: `_HashCNG::Create_::_1_::catch$1`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000c7d8`
- `0x14002c3e8`
- `0x14002f989`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14002f9b4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x14002f9b4`

## string_xrefs

- `0x14002f996`: `HashCNG:Create failed`

## pseudocode

```c
void __fastcall __noreturn HashCNG::Create_::_1_::catch_1(__int64 a1, __int64 a2)
{
  void *v3; // rcx

  Log::Verbose(*(const struct ILogContext **)(a2 + 232), L"HashCNG:Create failed");
  v3 = *(void **)(a2 + 72);
  if ( v3 )
    BCryptCloseAlgorithmProvider(v3, 0);
  throw;
}

```

## disassembly

```asm
0x14002f989  mov     [rsp+arg_8], rdx
0x14002f98e  push    rbp
0x14002f98f  sub     rsp, 40h
0x14002f993  mov     rbp, rdx
0x14002f996  lea     rdx, aHashcngCreateF; "HashCNG:Create failed"
0x14002f99d  mov     rcx, [rbp+0E8h]; struct ILogContext *
0x14002f9a4  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14002f9a9  mov     rcx, [rbp+48h]; hAlgorithm
0x14002f9ad  test    rcx, rcx
0x14002f9b0  jz      short loc_14002F9BA
0x14002f9b2  xor     edx, edx; dwFlags
0x14002f9b4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14002f9ba  xor     edx, edx; pThrowInfo
0x14002f9bc  xor     ecx, ecx; pExceptionObject
0x14002f9be  call    _CxxThrowException_0
```
