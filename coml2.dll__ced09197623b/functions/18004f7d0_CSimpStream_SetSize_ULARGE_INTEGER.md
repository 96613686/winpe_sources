# CSimpStream::SetSize(_ULARGE_INTEGER)

- ea: `0x18004f7d0`
- end: `0x18004f88a`
- name: `?SetSize@CSimpStream@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(CSimpStream *__hidden this, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180026bc4`
- `0x18004f7d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f801`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f7f4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f82f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f854`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f85c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f7f4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f82f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f854`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f85c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18004f83e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18004f83e`

## pseudocode

```c
__int64 __fastcall CSimpStream::SetSize(HANDLE *this, union _ULARGE_INTEGER a2)
{
  unsigned int v4; // esi
  DWORD LastError; // eax
  BOOL v7; // eax
  HANDLE v8; // rcx

  v4 = SetFilePointer(this[5], 0, 0, 1u);
  if ( v4 == -1 )
    goto LABEL_2;
  if ( v4 >= 0x7FFFFF00 || a2.QuadPart >= 2147483392 - v4 )
    return 2147680529LL;
  if ( SetFilePointer(this[5], a2.LowPart + *((_DWORD *)this + 5), 0, 0) == -1 )
  {
LABEL_2:
    LastError = GetLastError();
    return Win32ErrorToScode(LastError);
  }
  v7 = SetEndOfFile(this[5]);
  v8 = this[5];
  if ( !v7 )
  {
    SetFilePointer(v8, v4, 0, 0);
    goto LABEL_2;
  }
  if ( SetFilePointer(v8, v4, 0, 0) == -1 )
  {
    *((_DWORD *)this + 6) = a2.LowPart + *((_DWORD *)this + 5);
    goto LABEL_2;
  }
  return 0;
}

```

## disassembly

```asm
0x18004f7d0  mov     [rsp+arg_0], rbx
0x18004f7d5  mov     [rsp+arg_8], rsi
0x18004f7da  push    rdi
0x18004f7db  sub     rsp, 20h
0x18004f7df  mov     rbx, rdx
0x18004f7e2  mov     rdi, rcx
0x18004f7e5  mov     rcx, [rcx+28h]; hFile
0x18004f7e9  xor     edx, edx; lDistanceToMove
0x18004f7eb  mov     r9d, 1; dwMoveMethod
0x18004f7f1  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004f7f4  call    cs:__imp_SetFilePointer
0x18004f7fa  mov     esi, eax
0x18004f7fc  cmp     eax, 0FFFFFFFFh
0x18004f7ff  jnz     short loc_18004F810
0x18004f801  call    cs:__imp_GetLastError
0x18004f807  mov     ecx, eax; unsigned int
0x18004f809  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004f80e  jmp     short loc_18004F87A
0x18004f810  mov     eax, 7FFFFF00h
0x18004f815  cmp     esi, eax
0x18004f817  jnb     short loc_18004F875
0x18004f819  sub     eax, esi
0x18004f81b  cmp     rbx, rax
0x18004f81e  jnb     short loc_18004F875
0x18004f820  mov     edx, [rdi+14h]
0x18004f823  xor     r9d, r9d; dwMoveMethod
0x18004f826  mov     rcx, [rdi+28h]; hFile
0x18004f82a  add     edx, ebx; lDistanceToMove
0x18004f82c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004f82f  call    cs:__imp_SetFilePointer
0x18004f835  cmp     eax, 0FFFFFFFFh
0x18004f838  jz      short loc_18004F801
0x18004f83a  mov     rcx, [rdi+28h]; hFile
0x18004f83e  call    cs:__imp_SetEndOfFile
0x18004f844  mov     rcx, [rdi+28h]; hFile
0x18004f848  xor     r9d, r9d; dwMoveMethod
0x18004f84b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004f84e  mov     edx, esi; lDistanceToMove
0x18004f850  test    eax, eax
0x18004f852  jnz     short loc_18004F85C
0x18004f854  call    cs:__imp_SetFilePointer
0x18004f85a  jmp     short loc_18004F801
0x18004f85c  call    cs:__imp_SetFilePointer
0x18004f862  cmp     eax, 0FFFFFFFFh
0x18004f865  jnz     short loc_18004F871
0x18004f867  mov     ecx, [rdi+14h]
0x18004f86a  add     ecx, ebx
0x18004f86c  mov     [rdi+18h], ecx
0x18004f86f  jmp     short loc_18004F801
0x18004f871  xor     eax, eax
0x18004f873  jmp     short loc_18004F87A
0x18004f875  mov     eax, 80030111h
0x18004f87a  mov     rbx, [rsp+28h+arg_0]
0x18004f87f  mov     rsi, [rsp+28h+arg_8]
0x18004f884  add     rsp, 20h
0x18004f888  pop     rdi
0x18004f889  retn
```
