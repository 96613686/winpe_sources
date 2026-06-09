# DynArrayAppendString

- ea: `0x14000f43c`
- end: `0x14000f4d0`
- name: `DynArrayAppendString`
- size: `148`
- prototype: `__int64 __fastcall(_DWORD *, const WCHAR *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1400075ac`
- `0x140007cbc`
- `0x1400080a4`
- `0x140008838`
- `0x14000dab0`

## callees

- `0x14000ce50`
- `0x14000d2d0`
- `0x14000f0c0`
- `0x14000f43c`
- `0x14000f708`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000f461`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000f461`

## pseudocode

```c
__int64 __fastcall DynArrayAppendString(_DWORD *a1, const WCHAR *a2)
{
  unsigned int v4; // r14d
  __int64 Memory; // rax
  __int64 v6; // rdi
  __int64 result; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF

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
0x14000f43c  mov     [rsp+arg_8], rbx
0x14000f441  mov     [rsp+arg_10], rbp
0x14000f446  push    rsi
0x14000f447  push    rdi
0x14000f448  push    r14
0x14000f44a  sub     rsp, 20h
0x14000f44e  mov     rsi, rdx
0x14000f451  mov     rbx, rcx
0x14000f454  test    rcx, rcx
0x14000f457  jz      short loc_14000F4B9
0x14000f459  cmp     dword ptr [rcx], 9
0x14000f45c  jnz     short loc_14000F4B9
0x14000f45e  mov     rcx, rdx; lpString
0x14000f461  call    cs:__imp_lstrlenW
0x14000f468  nop     dword ptr [rax+rax+00h]
0x14000f46d  lea     r14d, [rax+1]
0x14000f471  lea     ebp, [r14+r14]
0x14000f475  mov     ecx, ebp; dwBytes
0x14000f477  call    AllocateMemory
0x14000f47c  mov     [rsp+38h+arg_0], rax
0x14000f481  mov     rdi, rax
0x14000f484  test    rax, rax
0x14000f487  jz      short loc_14000F4B9
0x14000f489  mov     r8d, r14d
0x14000f48c  mov     rdx, rsi
0x14000f48f  mov     rcx, rax
0x14000f492  call    StringCopyW
0x14000f497  mov     r9, rdi
0x14000f49a  mov     r8d, ebp
0x14000f49d  mov     edx, 20000h
0x14000f4a2  mov     rcx, rbx
0x14000f4a5  call    __DynArrayAppend
0x14000f4aa  cmp     eax, 0FFFFFFFFh
0x14000f4ad  jnz     short loc_14000F4BC
0x14000f4af  lea     rcx, [rsp+38h+arg_0]
0x14000f4b4  call    FreeMemory
0x14000f4b9  or      eax, 0FFFFFFFFh
0x14000f4bc  mov     rbx, [rsp+38h+arg_8]
0x14000f4c1  mov     rbp, [rsp+38h+arg_10]
0x14000f4c6  add     rsp, 20h
0x14000f4ca  pop     r14
0x14000f4cc  pop     rdi
0x14000f4cd  pop     rsi
0x14000f4ce  retn
```
