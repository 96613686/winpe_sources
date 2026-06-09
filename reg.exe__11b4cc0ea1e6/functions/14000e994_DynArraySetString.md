# DynArraySetString

- ea: `0x14000e994`
- end: `0x14000ea54`
- name: `DynArraySetString`
- size: `192`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400053e0`
- `0x14000cd48`
- `0x14000da24`

## callees

- `0x14000c62c`
- `0x14000c9c0`
- `0x14000e450`
- `0x14000e994`
- `0x14000ec3c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e9cd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000e9cd`

## pseudocode

```c
__int64 __fastcall DynArraySetString(__int64 a1, unsigned int a2, WCHAR *a3, int a4)
{
  __int64 Item; // rax
  __int64 v7; // rdi
  unsigned int v8; // esi
  LPVOID v9; // rax
  LPVOID Memory; // rax

  Item = _DynArrayGetItem(a1, a2, 0);
  v7 = Item;
  if ( Item && (*(_DWORD *)(Item + 4) & 0xFFFDFFFF) == 0 )
  {
    if ( !a4 )
      a4 = lstrlenW(a3);
    v8 = a4 + 1;
    if ( *(_DWORD *)(v7 + 4) )
    {
      if ( *(unsigned int *)(v7 + 8) >= 2 * (unsigned __int64)v8 )
        goto LABEL_11;
      FreeMemory((void **)(v7 + 16));
      *(_QWORD *)(v7 + 16) = 0;
      Memory = AllocateMemory(2 * v8);
      *(_QWORD *)(v7 + 16) = Memory;
      if ( Memory )
      {
        *(_DWORD *)(v7 + 8) = 2 * v8;
        goto LABEL_11;
      }
    }
    else
    {
      v9 = AllocateMemory(2 * v8);
      *(_QWORD *)(v7 + 16) = v9;
      if ( v9 )
      {
        *(_DWORD *)(v7 + 4) = 0x20000;
        *(_DWORD *)(v7 + 8) = 2 * v8;
LABEL_11:
        StringCopyW(*(_WORD **)(v7 + 16), a3, v8);
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000e994  push    rbx
0x14000e996  push    rbp
0x14000e997  push    rsi
0x14000e998  push    rdi
0x14000e999  push    r14
0x14000e99b  sub     rsp, 20h
0x14000e99f  mov     r14, r8
0x14000e9a2  mov     esi, r9d
0x14000e9a5  xor     r8d, r8d
0x14000e9a8  call    __DynArrayGetItem
0x14000e9ad  mov     rdi, rax
0x14000e9b0  test    rax, rax
0x14000e9b3  jz      loc_14000EA47
0x14000e9b9  test    dword ptr [rax+4], 0FFFDFFFFh
0x14000e9c0  jnz     loc_14000EA47
0x14000e9c6  test    esi, esi
0x14000e9c8  jnz     short loc_14000E9D5
0x14000e9ca  mov     rcx, r14; lpString
0x14000e9cd  call    cs:__imp_lstrlenW
0x14000e9d3  mov     esi, eax
0x14000e9d5  inc     esi
0x14000e9d7  cmp     dword ptr [rdi+4], 0
0x14000e9db  jnz     short loc_14000E9FC
0x14000e9dd  lea     ebx, [rsi+rsi]
0x14000e9e0  mov     ecx, ebx; dwBytes
0x14000e9e2  call    AllocateMemory
0x14000e9e7  mov     [rdi+10h], rax
0x14000e9eb  test    rax, rax
0x14000e9ee  jz      short loc_14000EA47
0x14000e9f0  mov     dword ptr [rdi+4], 20000h
0x14000e9f7  mov     [rdi+8], ebx
0x14000e9fa  jmp     short loc_14000EA31
0x14000e9fc  mov     eax, [rdi+8]
0x14000e9ff  mov     ecx, esi
0x14000ea01  add     rcx, rcx
0x14000ea04  cmp     rax, rcx
0x14000ea07  jnb     short loc_14000EA31
0x14000ea09  lea     rbx, [rdi+10h]
0x14000ea0d  mov     rcx, rbx
0x14000ea10  call    FreeMemory
0x14000ea15  lea     ebp, [rsi+rsi]
0x14000ea18  mov     qword ptr [rbx], 0
0x14000ea1f  mov     ecx, ebp; dwBytes
0x14000ea21  call    AllocateMemory
0x14000ea26  mov     [rbx], rax
0x14000ea29  test    rax, rax
0x14000ea2c  jz      short loc_14000EA47
0x14000ea2e  mov     [rdi+8], ebp
0x14000ea31  mov     rcx, [rdi+10h]
0x14000ea35  mov     r8d, esi
0x14000ea38  mov     rdx, r14
0x14000ea3b  call    StringCopyW
0x14000ea40  mov     eax, 1
0x14000ea45  jmp     short loc_14000EA49
0x14000ea47  xor     eax, eax
0x14000ea49  add     rsp, 20h
0x14000ea4d  pop     r14
0x14000ea4f  pop     rdi
0x14000ea50  pop     rsi
0x14000ea51  pop     rbp
0x14000ea52  pop     rbx
0x14000ea53  retn
```
