# SetReason

- ea: `0x14000da24`
- end: `0x14000da9d`
- name: `SetReason`
- size: `121`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140002b70`
- `0x1400030b8`
- `0x14000375c`
- `0x140007170`
- `0x140007834`
- `0x140008788`
- `0x1400096a8`
- `0x14000998c`
- `0x140009ae4`
- `0x14000a0a0`
- `0x14000d978`
- `0x14000daa4`

## callees

- `0x14000d114`
- `0x14000da24`
- `0x14000e994`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000da4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000da90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000da4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000da90`

## pseudocode

```c
__int64 __fastcall SetReason(__int64 a1)
{
  DWORD LastError; // edi
  DWORD v3; // ecx

  LastError = GetLastError();
  if ( !a1 )
  {
    if ( GetLastError() )
      return 0;
    v3 = 87;
LABEL_4:
    SetLastError(v3);
    return 0;
  }
  if ( !(unsigned int)InitGlobals() )
    return 0;
  if ( !(unsigned int)DynArraySetString(qword_140014218, 0, a1, 0) )
  {
    if ( GetLastError() )
      return 0;
    v3 = 8;
    goto LABEL_4;
  }
  SetLastError(LastError);
  return 1;
}

```

## disassembly

```asm
0x14000da24  mov     [rsp+arg_0], rbx
0x14000da29  push    rdi
0x14000da2a  sub     rsp, 20h
0x14000da2e  mov     rbx, rcx
0x14000da31  call    cs:__imp_GetLastError
0x14000da37  mov     edi, eax
0x14000da39  test    rbx, rbx
0x14000da3c  jnz     short loc_14000DA5E
0x14000da3e  call    cs:__imp_GetLastError
0x14000da44  test    eax, eax
0x14000da46  jnz     short loc_14000DA51
0x14000da48  lea     ecx, [rbx+57h]; dwErrCode
0x14000da4b  call    cs:__imp_SetLastError
0x14000da51  xor     eax, eax
0x14000da53  mov     rbx, [rsp+28h+arg_0]
0x14000da58  add     rsp, 20h
0x14000da5c  pop     rdi
0x14000da5d  retn
0x14000da5e  call    InitGlobals
0x14000da63  test    eax, eax
0x14000da65  jz      short loc_14000DA51
0x14000da67  mov     rcx, cs:qword_140014218
0x14000da6e  xor     r9d, r9d
0x14000da71  mov     r8, rbx
0x14000da74  xor     edx, edx
0x14000da76  call    DynArraySetString
0x14000da7b  test    eax, eax
0x14000da7d  jnz     short loc_14000DA8E
0x14000da7f  call    cs:__imp_GetLastError
0x14000da85  test    eax, eax
0x14000da87  jnz     short loc_14000DA51
0x14000da89  lea     ecx, [rax+8]
0x14000da8c  jmp     short loc_14000DA4B
0x14000da8e  mov     ecx, edi; dwErrCode
0x14000da90  call    cs:__imp_SetLastError
0x14000da96  mov     eax, 1
0x14000da9b  jmp     short loc_14000DA53
```
