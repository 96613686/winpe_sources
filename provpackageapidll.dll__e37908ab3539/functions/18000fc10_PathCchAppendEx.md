# PathCchAppendEx

- ea: `0x18000fc10`
- end: `0x18000fc86`
- name: `PathCchAppendEx`
- size: `118`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath, PCWSTR pszMore, ULONG dwFlags)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180016710`
- `0x180017898`

## callees

- `0x18000f81c`
- `0x18000fc10`
- `0x18000fc8c`
- `0x180018434`

## pseudocode

```c
HRESULT __stdcall PathCchAppendEx(PWSTR pszPath, size_t cchPath, PCWSTR pszMore, ULONG dwFlags)
{
  PCWSTR v4; // rbx
  ULONG v8; // [rsp+20h] [rbp-18h]

  v4 = pszMore;
  if ( pszMore && !(unsigned int)PathIsUnc2((unsigned __int16 *)pszMore) && wcsncmp_0(v4, L"\\\\?\\", 4u) )
  {
    while ( *v4 == 92 )
      ++v4;
  }
  return PathCchCombineEx(pszPath, cchPath, pszPath, v4, v8);
}

```

## disassembly

```asm
0x18000fc10  mov     [rsp+arg_0], rbx
0x18000fc15  mov     [rsp+arg_8], rsi
0x18000fc1a  push    rdi
0x18000fc1b  sub     rsp, 30h
0x18000fc1f  mov     rbx, r8
0x18000fc22  mov     rsi, rdx
0x18000fc25  mov     rdi, rcx
0x18000fc28  test    r8, r8
0x18000fc2b  jz      short loc_18000FC65
0x18000fc2d  lea     r8, IsBackslash
0x18000fc34  xor     edx, edx
0x18000fc36  mov     rcx, rbx; unsigned __int16 *
0x18000fc39  call    PathIsUnc2
0x18000fc3e  test    eax, eax
0x18000fc40  jnz     short loc_18000FC65
0x18000fc42  lea     r8d, [rax+4]; MaxCount
0x18000fc46  mov     rcx, rbx; String1
0x18000fc49  lea     rdx, asc_18001EE88; "\\\\?\\"
0x18000fc50  call    wcsncmp_0
0x18000fc55  test    eax, eax
0x18000fc57  jz      short loc_18000FC65
0x18000fc59  jmp     short loc_18000FC5F
0x18000fc5b  add     rbx, 2
0x18000fc5f  cmp     word ptr [rbx], 5Ch ; '\'
0x18000fc63  jz      short loc_18000FC5B
0x18000fc65  mov     r9, rbx; pszMore
0x18000fc68  mov     r8, rdi; pszPathIn
0x18000fc6b  mov     rdx, rsi; cchPathOut
0x18000fc6e  mov     rcx, rdi; pszPathOut
0x18000fc71  call    PathCchCombineEx
0x18000fc76  mov     rbx, [rsp+38h+arg_0]
0x18000fc7b  mov     rsi, [rsp+38h+arg_8]
0x18000fc80  add     rsp, 30h
0x18000fc84  pop     rdi
0x18000fc85  retn
```
