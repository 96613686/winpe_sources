# DynArrayAppendString

- ea: `0x14000e7a4`
- end: `0x14000e831`
- name: `DynArrayAppendString`
- size: `141`
- prototype: `__int64 __fastcall(_DWORD *, const WCHAR *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140007170`
- `0x140007834`
- `0x140007be0`
- `0x140008320`
- `0x14000d114`

## callees

- `0x14000c62c`
- `0x14000c9c0`
- `0x14000e450`
- `0x14000e7a4`
- `0x14000ea5c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e7c9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e7c9`

## pseudocode

```c
__int64 __fastcall DynArrayAppendString(_DWORD *a1, const WCHAR *a2)
{
  unsigned int v4; // r14d
  LPVOID Memory; // rax
  LPVOID v6; // rdi
  __int64 result; // rax
  LPVOID v8; // [rsp+40h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( *a1 == 9 )
    {
      v4 = lstrlenW(a2) + 1;
      Memory = AllocateMemory(2 * v4);
      v8 = Memory;
      v6 = Memory;
      if ( Memory )
      {
        StringCopyW(Memory, a2, v4);
        result = _DynArrayAppend(a1, 0x20000, 2 * v4, v6);
        if ( (_DWORD)result != -1 )
          return result;
        FreeMemory(&v8);
      }
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14000e7a4  mov     [rsp+arg_8], rbx
0x14000e7a9  mov     [rsp+arg_10], rbp
0x14000e7ae  push    rsi
0x14000e7af  push    rdi
0x14000e7b0  push    r14
0x14000e7b2  sub     rsp, 20h
0x14000e7b6  mov     rsi, rdx
0x14000e7b9  mov     rbx, rcx
0x14000e7bc  test    rcx, rcx
0x14000e7bf  jz      short loc_14000E81B
0x14000e7c1  cmp     dword ptr [rcx], 9
0x14000e7c4  jnz     short loc_14000E81B
0x14000e7c6  mov     rcx, rdx; lpString
0x14000e7c9  call    cs:__imp_lstrlenW
0x14000e7cf  lea     r14d, [rax+1]
0x14000e7d3  lea     ebp, [r14+r14]
0x14000e7d7  mov     ecx, ebp; dwBytes
0x14000e7d9  call    AllocateMemory
0x14000e7de  mov     [rsp+38h+arg_0], rax
0x14000e7e3  mov     rdi, rax
0x14000e7e6  test    rax, rax
0x14000e7e9  jz      short loc_14000E81B
0x14000e7eb  mov     r8d, r14d
0x14000e7ee  mov     rdx, rsi
0x14000e7f1  mov     rcx, rax
0x14000e7f4  call    StringCopyW
0x14000e7f9  mov     r9, rdi
0x14000e7fc  mov     r8d, ebp
0x14000e7ff  mov     edx, 20000h
0x14000e804  mov     rcx, rbx
0x14000e807  call    __DynArrayAppend
0x14000e80c  cmp     eax, 0FFFFFFFFh
0x14000e80f  jnz     short loc_14000E81E
0x14000e811  lea     rcx, [rsp+38h+arg_0]
0x14000e816  call    FreeMemory
0x14000e81b  or      eax, 0FFFFFFFFh
0x14000e81e  mov     rbx, [rsp+38h+arg_8]
0x14000e823  mov     rbp, [rsp+38h+arg_10]
0x14000e828  add     rsp, 20h
0x14000e82c  pop     r14
0x14000e82e  pop     rdi
0x14000e82f  pop     rsi
0x14000e830  retn
```
