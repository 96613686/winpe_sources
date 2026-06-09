# _CxxThrowException

- ea: `0x180002cec`
- end: `0x180002d92`
- name: `_CxxThrowException`
- size: `166`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f54`
- `0x180001f7c`
- `0x1800033d8`
- `0x180007ad0`
- `0x180008550`

## callees

- `0x180002cec`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002d7c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002d7c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x180002d3b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x180002d3b`

## pseudocode

```c
void __stdcall __noreturn CxxThrowException(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _ThrowInfo *v2; // rbx
  ULONG_PTR v4; // rdi
  __int64 v5; // rcx
  PVOID v6; // rax
  PVOID BaseOfImage; // [rsp+20h] [rbp-38h] BYREF
  ULONG_PTR Arguments[6]; // [rsp+28h] [rbp-30h] BYREF

  v2 = pThrowInfo;
  v4 = 429065504;
  if ( pThrowInfo && (pThrowInfo->attributes & 0x10) != 0 )
  {
    v5 = *(_QWORD *)pExceptionObject - 8LL;
    v2 = *(_ThrowInfo **)(*(_QWORD *)v5 + 48LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 64LL))(v5);
  }
  v6 = 0;
  BaseOfImage = 0;
  if ( v2 )
  {
    v6 = RtlPcToFileHeader(v2, &BaseOfImage);
    BaseOfImage = v6;
    if ( (v2->attributes & 8) != 0 || !v6 )
      v4 = 26820608;
  }
  Arguments[0] = v4;
  Arguments[1] = (ULONG_PTR)pExceptionObject;
  Arguments[2] = (ULONG_PTR)v2;
  Arguments[3] = (ULONG_PTR)v6;
  RaiseException(0xE06D7363, 1u, 4u, Arguments);
}

```

## disassembly

```asm
0x180002cec  mov     [rsp+arg_10], rbx
0x180002cf1  mov     [rsp+arg_18], rsi
0x180002cf6  push    rdi
0x180002cf7  sub     rsp, 50h
0x180002cfb  mov     rbx, rdx
0x180002cfe  mov     rsi, rcx
0x180002d01  mov     edi, 19930520h
0x180002d06  test    rdx, rdx
0x180002d09  jz      short loc_180002D27
0x180002d0b  test    byte ptr [rdx], 10h
0x180002d0e  jz      short loc_180002D27
0x180002d10  mov     rcx, [rcx]
0x180002d13  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180002d17  mov     rax, [rcx]
0x180002d1a  mov     rbx, [rax+30h]
0x180002d1e  mov     rax, [rax+40h]
0x180002d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d27  xor     eax, eax
0x180002d29  mov     [rsp+58h+BaseOfImage], rax
0x180002d2e  test    rbx, rbx
0x180002d31  jz      short loc_180002D55
0x180002d33  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x180002d38  mov     rcx, rbx; PcValue
0x180002d3b  call    cs:__imp_RtlPcToFileHeader
0x180002d41  mov     [rsp+58h+BaseOfImage], rax
0x180002d46  test    byte ptr [rbx], 8
0x180002d49  jnz     short loc_180002D50
0x180002d4b  test    rax, rax
0x180002d4e  jnz     short loc_180002D55
0x180002d50  mov     edi, 1994000h
0x180002d55  mov     edx, 1; dwExceptionFlags
0x180002d5a  mov     [rsp+58h+Arguments], rdi
0x180002d5f  lea     r9, [rsp+58h+Arguments]; lpArguments
0x180002d64  mov     [rsp+58h+var_28], rsi
0x180002d69  mov     ecx, 0E06D7363h; dwExceptionCode
0x180002d6e  mov     [rsp+58h+var_20], rbx
0x180002d73  mov     [rsp+58h+var_18], rax
0x180002d78  lea     r8d, [rdx+3]; nNumberOfArguments
0x180002d7c  call    cs:__imp_RaiseException
0x180002d82  mov     rbx, [rsp+58h+arg_10]
0x180002d87  mov     rsi, [rsp+58h+arg_18]
0x180002d8c  add     rsp, 50h
0x180002d90  pop     rdi
0x180002d91  retn
```
