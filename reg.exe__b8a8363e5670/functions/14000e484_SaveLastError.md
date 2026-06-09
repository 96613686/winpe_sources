# SaveLastError

- ea: `0x14000e484`
- end: `0x14000e558`
- name: `SaveLastError`
- size: `212`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140002ce4`
- `0x14000a0e0`
- `0x14000a358`
- `0x14000ce50`
- `0x14000e268`
- `0x14000e75c`
- `0x14000e798`

## callees

- `0x14000dab0`
- `0x14000e484`
- `0x14000e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e49e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e49e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e530`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e524`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e543`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e524`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e543`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000e4f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000e505`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000e4f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000e505`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000e4ca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000e4ca`

## pseudocode

```c
__int64 SaveLastError()
{
  DWORD LastError; // eax
  unsigned int v1; // ebx
  WCHAR *Buffer; // [rsp+50h] [rbp+8h] BYREF

  Buffer = 0;
  if ( (unsigned int)InitGlobals() )
  {
    LastError = GetLastError();
    if ( FormatMessageW(0x1300u, 0, LastError, 0, (LPWSTR)&Buffer, 0, 0) )
    {
      if ( Buffer )
      {
        v1 = SetReason(Buffer);
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
0x14000e484  push    rbx
0x14000e486  sub     rsp, 40h
0x14000e48a  xor     ebx, ebx
0x14000e48c  mov     [rsp+48h+Buffer], rbx
0x14000e491  call    InitGlobals
0x14000e496  test    eax, eax
0x14000e498  jz      loc_14000E54F
0x14000e49e  call    cs:__imp_GetLastError
0x14000e4a5  nop     dword ptr [rax+rax+00h]
0x14000e4aa  mov     [rsp+48h+Arguments], rbx; Arguments
0x14000e4af  xor     r9d, r9d; dwLanguageId
0x14000e4b2  mov     r8d, eax; dwMessageId
0x14000e4b5  mov     [rsp+48h+nSize], ebx; nSize
0x14000e4b9  lea     rax, [rsp+48h+Buffer]
0x14000e4be  xor     edx, edx; lpSource
0x14000e4c0  mov     ecx, 1300h; dwFlags
0x14000e4c5  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x14000e4ca  call    cs:__imp_FormatMessageW
0x14000e4d1  nop     dword ptr [rax+rax+00h]
0x14000e4d6  mov     rcx, [rsp+48h+Buffer]; hMem
0x14000e4db  test    eax, eax
0x14000e4dd  jz      short loc_14000E500
0x14000e4df  test    rcx, rcx
0x14000e4e2  jz      short loc_14000E530
0x14000e4e4  call    SetReason
0x14000e4e9  mov     rcx, [rsp+48h+Buffer]; hMem
0x14000e4ee  mov     ebx, eax
0x14000e4f0  call    cs:__imp_LocalFree
0x14000e4f7  nop     dword ptr [rax+rax+00h]
0x14000e4fc  mov     eax, ebx
0x14000e4fe  jmp     short loc_14000E551
0x14000e500  test    rcx, rcx
0x14000e503  jz      short loc_14000E530
0x14000e505  call    cs:__imp_LocalFree
0x14000e50c  nop     dword ptr [rax+rax+00h]
0x14000e511  call    cs:__imp_GetLastError
0x14000e518  nop     dword ptr [rax+rax+00h]
0x14000e51d  test    eax, eax
0x14000e51f  jnz     short loc_14000E530
0x14000e521  lea     ecx, [rax+8]; dwErrCode
0x14000e524  call    cs:__imp_SetLastError
0x14000e52b  nop     dword ptr [rax+rax+00h]
0x14000e530  call    cs:__imp_GetLastError
0x14000e537  nop     dword ptr [rax+rax+00h]
0x14000e53c  test    eax, eax
0x14000e53e  jnz     short loc_14000E54F
0x14000e540  lea     ecx, [rax+8]; dwErrCode
0x14000e543  call    cs:__imp_SetLastError
0x14000e54a  nop     dword ptr [rax+rax+00h]
0x14000e54f  xor     eax, eax
0x14000e551  add     rsp, 40h
0x14000e555  pop     rbx
0x14000e556  retn
```
