# InString

- ea: `0x14000d010`
- end: `0x14000d10b`
- name: `InString`
- size: `251`
- prototype: `__int64 __fastcall(LPCWSTR lpString, LPCWSTR)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x1400030b8`
- `0x140003c48`
- `0x14000406c`
- `0x140004354`
- `0x140004bbc`
- `0x140006a5c`
- `0x14000752c`
- `0x140008fe8`
- `0x140009ae4`
- `0x140009d40`
- `0x14000a0a0`

## callees

- `0x14000c5a0`
- `0x14000c924`
- `0x14000caa8`
- `0x14000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d0e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d0e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d0f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d0f6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d038`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d077`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d038`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d077`

## pseudocode

```c
_BOOL8 __fastcall InString(LPCWSTR lpString, LPCWSTR a2)
{
  unsigned int v4; // r14d
  wchar_t *InternalTemporaryBuffer; // rsi
  DWORD v6; // ecx
  unsigned int v7; // r15d
  wchar_t *v8; // rbp
  HRESULT v9; // eax
  __int64 v10; // r8

  if ( lpString && a2 )
  {
    v4 = lstrlenW(a2) + 4;
    InternalTemporaryBuffer = (wchar_t *)GetInternalTemporaryBuffer(0, 0, v4, 1);
    if ( InternalTemporaryBuffer )
    {
      v7 = lstrlenW(lpString) + 4;
      v8 = (wchar_t *)GetInternalTemporaryBuffer(1u, 0, v7, 1);
      if ( v8 )
      {
        v9 = StringCchPrintfW(InternalTemporaryBuffer, v4, L"|%s|", a2);
        if ( v9 >= 0 )
        {
          v9 = StringCchPrintfW(v8, v7, L"|%s|", lpString);
          if ( v9 >= 0 )
            return (unsigned int)FindString2(InternalTemporaryBuffer, v8, v10, 0) != -1;
        }
        v6 = (unsigned __int16)v9;
        goto LABEL_13;
      }
    }
    if ( !GetLastError() )
    {
      v6 = 8;
LABEL_13:
      SetLastError(v6);
    }
  }
  else if ( !GetLastError() )
  {
    v6 = 87;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x14000d010  push    rbx
0x14000d012  push    rbp
0x14000d013  push    rsi
0x14000d014  push    rdi
0x14000d015  push    r14
0x14000d017  push    r15
0x14000d019  sub     rsp, 28h
0x14000d01d  mov     rbx, rdx
0x14000d020  mov     rdi, rcx
0x14000d023  test    rcx, rcx
0x14000d026  jz      loc_14000D0E9
0x14000d02c  test    rdx, rdx
0x14000d02f  jz      loc_14000D0E9
0x14000d035  mov     rcx, rdx; lpString
0x14000d038  call    cs:__imp_lstrlenW
0x14000d03e  mov     ebp, 1
0x14000d043  xor     edx, edx
0x14000d045  mov     r9d, ebp
0x14000d048  xor     ecx, ecx
0x14000d04a  lea     r14d, [rax+4]
0x14000d04e  mov     r8d, r14d
0x14000d051  call    GetInternalTemporaryBuffer
0x14000d056  mov     rsi, rax
0x14000d059  test    rax, rax
0x14000d05c  jnz     short loc_14000D074
0x14000d05e  call    cs:__imp_GetLastError
0x14000d064  test    eax, eax
0x14000d066  jnz     loc_14000D0FC
0x14000d06c  lea     ecx, [rax+8]
0x14000d06f  jmp     loc_14000D0F6
0x14000d074  mov     rcx, rdi; lpString
0x14000d077  call    cs:__imp_lstrlenW
0x14000d07d  mov     r9d, ebp
0x14000d080  xor     edx, edx
0x14000d082  mov     ecx, ebp
0x14000d084  lea     r15d, [rax+4]
0x14000d088  mov     r8d, r15d
0x14000d08b  call    GetInternalTemporaryBuffer
0x14000d090  mov     rbp, rax
0x14000d093  test    rax, rax
0x14000d096  jz      short loc_14000D05E
0x14000d098  mov     edx, r14d; cchDest
0x14000d09b  lea     r8, aS_0; "|%s|"
0x14000d0a2  mov     r9, rbx
0x14000d0a5  mov     rcx, rsi; pszDest
0x14000d0a8  call    StringCchPrintfW
0x14000d0ad  test    eax, eax
0x14000d0af  jns     short loc_14000D0B6
0x14000d0b1  movzx   ecx, ax
0x14000d0b4  jmp     short loc_14000D0F6
0x14000d0b6  mov     edx, r15d; cchDest
0x14000d0b9  lea     r8, aS_0; "|%s|"
0x14000d0c0  mov     r9, rdi
0x14000d0c3  mov     rcx, rbp; pszDest
0x14000d0c6  call    StringCchPrintfW
0x14000d0cb  test    eax, eax
0x14000d0cd  js      short loc_14000D0B1
0x14000d0cf  xor     r9d, r9d
0x14000d0d2  mov     rdx, rbp
0x14000d0d5  mov     rcx, rsi
0x14000d0d8  call    FindString2
0x14000d0dd  xor     ecx, ecx
0x14000d0df  cmp     eax, 0FFFFFFFFh
0x14000d0e2  setnz   cl
0x14000d0e5  mov     eax, ecx
0x14000d0e7  jmp     short loc_14000D0FE
0x14000d0e9  call    cs:__imp_GetLastError
0x14000d0ef  test    eax, eax
0x14000d0f1  jnz     short loc_14000D0FC
0x14000d0f3  lea     ecx, [rax+57h]; dwErrCode
0x14000d0f6  call    cs:__imp_SetLastError
0x14000d0fc  xor     eax, eax
0x14000d0fe  add     rsp, 28h
0x14000d102  pop     r15
0x14000d104  pop     r14
0x14000d106  pop     rdi
0x14000d107  pop     rsi
0x14000d108  pop     rbp
0x14000d109  pop     rbx
0x14000d10a  retn
```
