# InString

- ea: `0x14000d990`
- end: `0x14000daaa`
- name: `InString`
- size: `282`
- prototype: `__int64 __fastcall(LPCWSTR lpString, LPCWSTR)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x1400031f4`
- `0x140003e34`
- `0x14000426c`
- `0x14000456c`
- `0x140004e84`
- `0x140006e6c`
- `0x14000799c`
- `0x14000957c`
- `0x14000a0e0`
- `0x14000a358`
- `0x14000a6d8`

## callees

- `0x14000cdc4`
- `0x14000d214`
- `0x14000d3e8`
- `0x14000d990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d9e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d9e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000da8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000da8e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d9b8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000da03`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d9b8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000da03`

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
0x14000d990  push    rbx
0x14000d992  push    rbp
0x14000d993  push    rsi
0x14000d994  push    rdi
0x14000d995  push    r14
0x14000d997  push    r15
0x14000d999  sub     rsp, 28h
0x14000d99d  mov     rbx, rdx
0x14000d9a0  mov     rdi, rcx
0x14000d9a3  test    rcx, rcx
0x14000d9a6  jz      loc_14000DA7B
0x14000d9ac  test    rdx, rdx
0x14000d9af  jz      loc_14000DA7B
0x14000d9b5  mov     rcx, rdx; lpString
0x14000d9b8  call    cs:__imp_lstrlenW
0x14000d9bf  nop     dword ptr [rax+rax+00h]
0x14000d9c4  mov     ebp, 1
0x14000d9c9  xor     edx, edx
0x14000d9cb  mov     r9d, ebp
0x14000d9ce  xor     ecx, ecx
0x14000d9d0  lea     r14d, [rax+4]
0x14000d9d4  mov     r8d, r14d
0x14000d9d7  call    GetInternalTemporaryBuffer
0x14000d9dc  mov     rsi, rax
0x14000d9df  test    rax, rax
0x14000d9e2  jnz     short loc_14000DA00
0x14000d9e4  call    cs:__imp_GetLastError
0x14000d9eb  nop     dword ptr [rax+rax+00h]
0x14000d9f0  test    eax, eax
0x14000d9f2  jnz     loc_14000DA9A
0x14000d9f8  lea     ecx, [rax+8]
0x14000d9fb  jmp     loc_14000DA8E
0x14000da00  mov     rcx, rdi; lpString
0x14000da03  call    cs:__imp_lstrlenW
0x14000da0a  nop     dword ptr [rax+rax+00h]
0x14000da0f  mov     r9d, ebp
0x14000da12  xor     edx, edx
0x14000da14  mov     ecx, ebp
0x14000da16  lea     r15d, [rax+4]
0x14000da1a  mov     r8d, r15d
0x14000da1d  call    GetInternalTemporaryBuffer
0x14000da22  mov     rbp, rax
0x14000da25  test    rax, rax
0x14000da28  jz      short loc_14000D9E4
0x14000da2a  mov     edx, r14d; cchDest
0x14000da2d  lea     r8, aS_0; "|%s|"
0x14000da34  mov     r9, rbx
0x14000da37  mov     rcx, rsi; pszDest
0x14000da3a  call    StringCchPrintfW
0x14000da3f  test    eax, eax
0x14000da41  jns     short loc_14000DA48
0x14000da43  movzx   ecx, ax
0x14000da46  jmp     short loc_14000DA8E
0x14000da48  mov     edx, r15d; cchDest
0x14000da4b  lea     r8, aS_0; "|%s|"
0x14000da52  mov     r9, rdi
0x14000da55  mov     rcx, rbp; pszDest
0x14000da58  call    StringCchPrintfW
0x14000da5d  test    eax, eax
0x14000da5f  js      short loc_14000DA43
0x14000da61  xor     r9d, r9d
0x14000da64  mov     rdx, rbp
0x14000da67  mov     rcx, rsi
0x14000da6a  call    FindString2
0x14000da6f  xor     ecx, ecx
0x14000da71  cmp     eax, 0FFFFFFFFh
0x14000da74  setnz   cl
0x14000da77  mov     eax, ecx
0x14000da79  jmp     short loc_14000DA9C
0x14000da7b  call    cs:__imp_GetLastError
0x14000da82  nop     dword ptr [rax+rax+00h]
0x14000da87  test    eax, eax
0x14000da89  jnz     short loc_14000DA9A
0x14000da8b  lea     ecx, [rax+57h]; dwErrCode
0x14000da8e  call    cs:__imp_SetLastError
0x14000da95  nop     dword ptr [rax+rax+00h]
0x14000da9a  xor     eax, eax
0x14000da9c  add     rsp, 28h
0x14000daa0  pop     r15
0x14000daa2  pop     r14
0x14000daa4  pop     rdi
0x14000daa5  pop     rsi
0x14000daa6  pop     rbp
0x14000daa7  pop     rbx
0x14000daa8  retn
```
