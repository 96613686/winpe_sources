# DynArraySetString

- ea: `0x14000f638`
- end: `0x14000f6ff`
- name: `DynArraySetString`
- size: `199`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400056ec`
- `0x14000d694`
- `0x14000e560`

## callees

- `0x14000ce50`
- `0x14000d2d0`
- `0x14000f0c0`
- `0x14000f638`
- `0x14000f8e8`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000f671`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000f671`

## pseudocode

```c
__int64 __fastcall DynArraySetString(__int64 a1, __int64 a2, const WCHAR *a3, int a4)
{
  __int64 Item; // rax
  __int64 v7; // rdi
  unsigned int v8; // esi
  __int64 v9; // rax
  __int64 Memory; // rax

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
      FreeMemory(v7 + 16);
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
        StringCopyW(*(_QWORD *)(v7 + 16), a3, v8);
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000f638  push    rbx
0x14000f63a  push    rbp
0x14000f63b  push    rsi
0x14000f63c  push    rdi
0x14000f63d  push    r14
0x14000f63f  sub     rsp, 20h
0x14000f643  mov     r14, r8
0x14000f646  mov     esi, r9d
0x14000f649  xor     r8d, r8d
0x14000f64c  call    __DynArrayGetItem
0x14000f651  mov     rdi, rax
0x14000f654  test    rax, rax
0x14000f657  jz      loc_14000F6F1
0x14000f65d  test    dword ptr [rax+4], 0FFFDFFFFh
0x14000f664  jnz     loc_14000F6F1
0x14000f66a  test    esi, esi
0x14000f66c  jnz     short loc_14000F67F
0x14000f66e  mov     rcx, r14; lpString
0x14000f671  call    cs:__imp_lstrlenW
0x14000f678  nop     dword ptr [rax+rax+00h]
0x14000f67d  mov     esi, eax
0x14000f67f  inc     esi
0x14000f681  cmp     dword ptr [rdi+4], 0
0x14000f685  jnz     short loc_14000F6A6
0x14000f687  lea     ebx, [rsi+rsi]
0x14000f68a  mov     ecx, ebx; dwBytes
0x14000f68c  call    AllocateMemory
0x14000f691  mov     [rdi+10h], rax
0x14000f695  test    rax, rax
0x14000f698  jz      short loc_14000F6F1
0x14000f69a  mov     dword ptr [rdi+4], 20000h
0x14000f6a1  mov     [rdi+8], ebx
0x14000f6a4  jmp     short loc_14000F6DB
0x14000f6a6  mov     eax, [rdi+8]
0x14000f6a9  mov     ecx, esi
0x14000f6ab  add     rcx, rcx
0x14000f6ae  cmp     rax, rcx
0x14000f6b1  jnb     short loc_14000F6DB
0x14000f6b3  lea     rbx, [rdi+10h]
0x14000f6b7  mov     rcx, rbx
0x14000f6ba  call    FreeMemory
0x14000f6bf  lea     ebp, [rsi+rsi]
0x14000f6c2  mov     qword ptr [rbx], 0
0x14000f6c9  mov     ecx, ebp; dwBytes
0x14000f6cb  call    AllocateMemory
0x14000f6d0  mov     [rbx], rax
0x14000f6d3  test    rax, rax
0x14000f6d6  jz      short loc_14000F6F1
0x14000f6d8  mov     [rdi+8], ebp
0x14000f6db  mov     rcx, [rdi+10h]
0x14000f6df  mov     r8d, esi
0x14000f6e2  mov     rdx, r14
0x14000f6e5  call    StringCopyW
0x14000f6ea  mov     eax, 1
0x14000f6ef  jmp     short loc_14000F6F3
0x14000f6f1  xor     eax, eax
0x14000f6f3  add     rsp, 20h
0x14000f6f7  pop     r14
0x14000f6f9  pop     rdi
0x14000f6fa  pop     rsi
0x14000f6fb  pop     rbp
0x14000f6fc  pop     rbx
0x14000f6fd  retn
```
