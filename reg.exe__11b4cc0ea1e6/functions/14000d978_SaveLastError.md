# SaveLastError

- ea: `0x14000d978`
- end: `0x14000da1b`
- name: `SaveLastError`
- size: `163`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140002b70`
- `0x140009ae4`
- `0x140009d40`
- `0x14000c62c`
- `0x14000d7a8`
- `0x14000dbe8`
- `0x14000dc24`

## callees

- `0x14000d114`
- `0x14000d978`
- `0x14000da24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d9ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d9ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d9fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000da0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d9fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000da0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000d9d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000d9e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000d9d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000d9e7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000d9b8`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000d9b8`

## pseudocode

```c
__int64 SaveLastError()
{
  DWORD LastError; // eax
  unsigned int v1; // ebx
  HLOCAL Buffer; // [rsp+50h] [rbp+8h] BYREF

  Buffer = 0;
  if ( (unsigned int)InitGlobals() )
  {
    LastError = GetLastError();
    if ( FormatMessageW(0x1300u, 0, LastError, 0, (LPWSTR)&Buffer, 0, 0) )
    {
      if ( Buffer )
      {
        v1 = SetReason((__int64)Buffer);
        LocalFree(Buffer);
        return v1;
      }
    }
    else if ( Buffer )
    {
      LocalFree(Buffer);
      if ( !GetLastError() )
        SetLastError(8u);
    }
    if ( !GetLastError() )
      SetLastError(8u);
  }
  return 0;
}

```

## disassembly

```asm
0x14000d978  push    rbx
0x14000d97a  sub     rsp, 40h
0x14000d97e  xor     ebx, ebx
0x14000d980  mov     [rsp+48h+Buffer], rbx
0x14000d985  call    InitGlobals
0x14000d98a  test    eax, eax
0x14000d98c  jz      loc_14000DA13
0x14000d992  call    cs:__imp_GetLastError
0x14000d998  mov     [rsp+48h+Arguments], rbx; Arguments
0x14000d99d  xor     r9d, r9d; dwLanguageId
0x14000d9a0  mov     r8d, eax; dwMessageId
0x14000d9a3  mov     [rsp+48h+nSize], ebx; nSize
0x14000d9a7  lea     rax, [rsp+48h+Buffer]
0x14000d9ac  xor     edx, edx; lpSource
0x14000d9ae  mov     ecx, 1300h; dwFlags
0x14000d9b3  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x14000d9b8  call    cs:__imp_FormatMessageW
0x14000d9be  mov     rcx, [rsp+48h+Buffer]; hMem
0x14000d9c3  test    eax, eax
0x14000d9c5  jz      short loc_14000D9E2
0x14000d9c7  test    rcx, rcx
0x14000d9ca  jz      short loc_14000DA00
0x14000d9cc  call    SetReason
0x14000d9d1  mov     rcx, [rsp+48h+Buffer]; hMem
0x14000d9d6  mov     ebx, eax
0x14000d9d8  call    cs:__imp_LocalFree
0x14000d9de  mov     eax, ebx
0x14000d9e0  jmp     short loc_14000DA15
0x14000d9e2  test    rcx, rcx
0x14000d9e5  jz      short loc_14000DA00
0x14000d9e7  call    cs:__imp_LocalFree
0x14000d9ed  call    cs:__imp_GetLastError
0x14000d9f3  test    eax, eax
0x14000d9f5  jnz     short loc_14000DA00
0x14000d9f7  lea     ecx, [rax+8]; dwErrCode
0x14000d9fa  call    cs:__imp_SetLastError
0x14000da00  call    cs:__imp_GetLastError
0x14000da06  test    eax, eax
0x14000da08  jnz     short loc_14000DA13
0x14000da0a  lea     ecx, [rax+8]; dwErrCode
0x14000da0d  call    cs:__imp_SetLastError
0x14000da13  xor     eax, eax
0x14000da15  add     rsp, 40h
0x14000da19  pop     rbx
0x14000da1a  retn
```
