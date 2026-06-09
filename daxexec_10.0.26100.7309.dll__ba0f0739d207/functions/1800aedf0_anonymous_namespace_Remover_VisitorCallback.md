# _anonymous_namespace_::Remover::VisitorCallback

- ea: `0x1800aedf0`
- end: `0x1800aef2e`
- name: `_anonymous_namespace_::Remover::VisitorCallback`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800aedf0`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aee36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aee7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aeed1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aee36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aee7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aeed1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800aee56`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800aeec1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800aee56`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800aeec1`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800aee23`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800aee69`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800aee23`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800aee69`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::Remover::VisitorCallback(__int64 a1, const WCHAR *a2, int *a3)
{
  int v5; // edx
  DWORD LastError; // ebx
  unsigned int v8; // edi
  unsigned int (__fastcall *v9)(const WCHAR *, _QWORD, _QWORD, _QWORD); // rax

  v5 = *a3;
  if ( (*a3 & 0x10) != 0 )
  {
    LastError = 0;
    v8 = 1;
    if ( !RemoveDirectoryW(a2) )
    {
      LastError = GetLastError();
      if ( LastError == 5 && (*a3 & 1) != 0 )
      {
        if ( SetFileAttributesW(a2, *a3 & 0xFFFFFFFE) && RemoveDirectoryW(a2) )
          LastError = 0;
        else
          LastError = GetLastError();
      }
    }
    if ( (*a3 & 0x410) == 0x410 && a3[9] != -2147483624 && a3[9] != -1879044072 )
      v8 = 2;
  }
  else
  {
    if ( ((v5 & 1) == 0 || SetFileAttributesW(a2, v5 & 0xFFFFFFFE))
      && (*(unsigned int (__fastcall **)(const WCHAR *))a1)(a2) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    v8 = 0;
  }
  v9 = *(unsigned int (__fastcall **)(const WCHAR *, _QWORD, _QWORD, _QWORD))(a1 + 8);
  if ( v9 )
    return v9(a2, v8, LastError, *(_QWORD *)(a1 + 16));
  return LastError;
}

```

## disassembly

```asm
0x1800aedf0  mov     rax, rsp
0x1800aedf3  mov     [rax+8], rbx
0x1800aedf7  mov     [rax+10h], rbp
0x1800aedfb  mov     [rax+18h], rsi
0x1800aedff  mov     [rax+20h], rdi
0x1800aee03  push    r14
0x1800aee05  sub     rsp, 30h
0x1800aee09  mov     rbp, rdx
0x1800aee0c  mov     rsi, r8
0x1800aee0f  mov     edx, [r8]
0x1800aee12  mov     r14, rcx
0x1800aee15  test    dl, 10h
0x1800aee18  jz      loc_1800AEEB1
0x1800aee1e  mov     rcx, rbp; lpPathName
0x1800aee21  xor     ebx, ebx
0x1800aee23  call    cs:__imp_RemoveDirectoryW
0x1800aee2a  nop     dword ptr [rax+rax+00h]
0x1800aee2f  lea     edi, [rbx+1]
0x1800aee32  test    eax, eax
0x1800aee34  jnz     short loc_1800AEE8B
0x1800aee36  call    cs:__imp_GetLastError
0x1800aee3d  nop     dword ptr [rax+rax+00h]
0x1800aee42  mov     ebx, eax
0x1800aee44  cmp     eax, 5
0x1800aee47  jnz     short loc_1800AEE8B
0x1800aee49  mov     edx, [rsi]
0x1800aee4b  test    dil, dl
0x1800aee4e  jz      short loc_1800AEE8B
0x1800aee50  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800aee53  mov     rcx, rbp; lpFileName
0x1800aee56  call    cs:__imp_SetFileAttributesW
0x1800aee5d  nop     dword ptr [rax+rax+00h]
0x1800aee62  test    eax, eax
0x1800aee64  jz      short loc_1800AEE7D
0x1800aee66  mov     rcx, rbp; lpPathName
0x1800aee69  call    cs:__imp_RemoveDirectoryW
0x1800aee70  nop     dword ptr [rax+rax+00h]
0x1800aee75  test    eax, eax
0x1800aee77  jz      short loc_1800AEE7D
0x1800aee79  xor     ebx, ebx
0x1800aee7b  jmp     short loc_1800AEE8B
0x1800aee7d  call    cs:__imp_GetLastError
0x1800aee84  nop     dword ptr [rax+rax+00h]
0x1800aee89  mov     ebx, eax
0x1800aee8b  mov     eax, [rsi]
0x1800aee8d  mov     ecx, 410h
0x1800aee92  and     eax, ecx
0x1800aee94  cmp     eax, ecx
0x1800aee96  jnz     short loc_1800AEEF4
0x1800aee98  cmp     dword ptr [rsi+24h], 80000018h
0x1800aee9f  jz      short loc_1800AEEF4
0x1800aeea1  cmp     dword ptr [rsi+24h], 90001018h
0x1800aeea8  jz      short loc_1800AEEF4
0x1800aeeaa  mov     edi, 2
0x1800aeeaf  jmp     short loc_1800AEEF4
0x1800aeeb1  mov     edi, 1
0x1800aeeb6  test    dil, dl
0x1800aeeb9  jz      short loc_1800AEEE1
0x1800aeebb  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800aeebe  mov     rcx, rbp; lpFileName
0x1800aeec1  call    cs:__imp_SetFileAttributesW
0x1800aeec8  nop     dword ptr [rax+rax+00h]
0x1800aeecd  test    eax, eax
0x1800aeecf  jnz     short loc_1800AEEE1
0x1800aeed1  call    cs:__imp_GetLastError
0x1800aeed8  nop     dword ptr [rax+rax+00h]
0x1800aeedd  mov     ebx, eax
0x1800aeedf  jmp     short loc_1800AEEF2
0x1800aeee1  mov     rax, [r14]
0x1800aeee4  mov     rcx, rbp
0x1800aeee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeeec  test    eax, eax
0x1800aeeee  jz      short loc_1800AEED1
0x1800aeef0  xor     ebx, ebx
0x1800aeef2  xor     edi, edi
0x1800aeef4  mov     rax, [r14+8]
0x1800aeef8  test    rax, rax
0x1800aeefb  jz      short loc_1800AEF10
0x1800aeefd  mov     r9, [r14+10h]
0x1800aef01  mov     r8d, ebx
0x1800aef04  mov     edx, edi
0x1800aef06  mov     rcx, rbp
0x1800aef09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aef0e  mov     ebx, eax
0x1800aef10  mov     rbp, [rsp+38h+arg_8]
0x1800aef15  mov     eax, ebx
0x1800aef17  mov     rbx, [rsp+38h+arg_0]
0x1800aef1c  mov     rsi, [rsp+38h+arg_10]
0x1800aef21  mov     rdi, [rsp+38h+arg_18]
0x1800aef26  add     rsp, 30h
0x1800aef2a  pop     r14
0x1800aef2c  retn
```
