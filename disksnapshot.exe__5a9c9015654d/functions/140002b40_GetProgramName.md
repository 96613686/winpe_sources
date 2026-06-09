# GetProgramName

- ea: `0x140002b40`
- end: `0x140002c24`
- name: `GetProgramName`
- size: `228`
- prototype: `LPWSTR()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002c2c`

## callees

- `0x140002b40`
- `0x14000c554`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x140002b68`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x140002b68`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140002c07`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140002c07`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140002bb8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140002be6`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140002bb8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140002be6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140002b99`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140002b99`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140002b5f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140002b76`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140002b5f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140002b76`

## pseudocode

```c
LPWSTR GetProgramName()
{
  LPWSTR CommandLineW; // rax
  __int64 v1; // rax
  wchar_t *v2; // rbx
  const wchar_t *v4; // rdi
  wchar_t v5; // dx
  wchar_t *v6; // rax
  wchar_t *v7; // rax
  wchar_t *v8; // rsi
  wchar_t *v9; // rax
  signed __int64 v10; // rcx

  if ( !qword_140014230 )
  {
    CommandLineW = GetCommandLineW();
    v1 = _o__wcsdup(CommandLineW);
    v2 = (wchar_t *)v1;
    if ( !v1 )
      return GetCommandLineW();
    v4 = (const wchar_t *)(v1 + 2);
    v5 = 34;
    if ( *(_WORD *)v1 != 34 )
      v5 = 32;
    v6 = wcschr((const wchar_t *)(v1 + 2), v5);
    if ( v6 )
      *v6 = 0;
    if ( *v2 != 34 )
      v4 = v2;
    v7 = wcsrchr(v4, 0x2Eu);
    v8 = v7;
    if ( v7 && !wcscmp_0(v7, L".exe") )
      *v8 = 0;
    v9 = wcsrchr(v4, 0x5Cu);
    v10 = (signed __int64)(v9 + 1);
    if ( !v9 )
      v10 = (signed __int64)v4;
    if ( _InterlockedCompareExchange64(&qword_140014230, v10, 0) )
      free(v2);
  }
  return (LPWSTR)qword_140014230;
}

```

## disassembly

```asm
0x140002b40  mov     [rsp+arg_0], rbx
0x140002b45  mov     [rsp+arg_8], rsi
0x140002b4a  push    rdi
0x140002b4b  sub     rsp, 20h
0x140002b4f  mov     rax, cs:qword_140014230
0x140002b56  test    rax, rax
0x140002b59  jnz     loc_140002C0D
0x140002b5f  call    cs:__imp_GetCommandLineW
0x140002b65  mov     rcx, rax
0x140002b68  call    cs:__imp__o__wcsdup
0x140002b6e  mov     rbx, rax
0x140002b71  test    rax, rax
0x140002b74  jnz     short loc_140002B81
0x140002b76  call    cs:__imp_GetCommandLineW
0x140002b7c  jmp     loc_140002C14
0x140002b81  mov     esi, 22h ; '"'
0x140002b86  lea     rdi, [rax+2]
0x140002b8a  cmp     [rbx], si
0x140002b8d  mov     edx, esi
0x140002b8f  mov     rcx, rdi; Str
0x140002b92  lea     eax, [rsi-2]
0x140002b95  cmovnz  dx, ax; Ch
0x140002b99  call    cs:__imp_wcschr
0x140002b9f  test    rax, rax
0x140002ba2  jz      short loc_140002BA9
0x140002ba4  xor     ecx, ecx
0x140002ba6  mov     [rax], cx
0x140002ba9  cmp     [rbx], si
0x140002bac  mov     edx, 2Eh ; '.'; Ch
0x140002bb1  cmovnz  rdi, rbx
0x140002bb5  mov     rcx, rdi; Str
0x140002bb8  call    cs:__imp_wcsrchr
0x140002bbe  mov     rsi, rax
0x140002bc1  test    rax, rax
0x140002bc4  jz      short loc_140002BDE
0x140002bc6  lea     rdx, aExe; ".exe"
0x140002bcd  mov     rcx, rax; String1
0x140002bd0  call    wcscmp_0
0x140002bd5  test    eax, eax
0x140002bd7  jnz     short loc_140002BDE
0x140002bd9  xor     ecx, ecx
0x140002bdb  mov     [rsi], cx
0x140002bde  mov     edx, 5Ch ; '\'; Ch
0x140002be3  mov     rcx, rdi; Str
0x140002be6  call    cs:__imp_wcsrchr
0x140002bec  test    rax, rax
0x140002bef  lea     rcx, [rax+2]
0x140002bf3  cmovz   rcx, rdi
0x140002bf7  xor     eax, eax
0x140002bf9  lock cmpxchg cs:qword_140014230, rcx
0x140002c02  jz      short loc_140002C0D
0x140002c04  mov     rcx, rbx; Block
0x140002c07  call    cs:__imp_free
0x140002c0d  mov     rax, cs:qword_140014230
0x140002c14  mov     rbx, [rsp+28h+arg_0]
0x140002c19  mov     rsi, [rsp+28h+arg_8]
0x140002c1e  add     rsp, 20h
0x140002c22  pop     rdi
0x140002c23  retn
```
