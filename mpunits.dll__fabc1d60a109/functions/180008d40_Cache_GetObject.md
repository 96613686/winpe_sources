# Cache_GetObject

- ea: `0x180008d40`
- end: `0x180008da3`
- name: `Cache_GetObject`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800138c0`
- `0x18002e274`
- `0x18002ee04`

## callees

- `0x180008d40`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x180008d6e`
- `msvcrt!malloc` at `0x180008d6e`
- `msvcrt!free` at `0x180008d90`
- `msvcrt!free` at `0x180008d90`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180008d4d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180008d4d`

## pseudocode

```c
PSLIST_ENTRY __fastcall Cache_GetObject(__int64 a1)
{
  PSLIST_ENTRY v2; // rbx
  struct _SLIST_ENTRY *v4; // rax

  v2 = InterlockedPopEntrySList((PSLIST_HEADER)a1);
  if ( v2 )
  {
    _InterlockedDecrement64((volatile signed __int64 *)(a1 + 16));
    return v2 + 1;
  }
  v4 = (struct _SLIST_ENTRY *)malloc(*(_QWORD *)(a1 + 32) + 16LL);
  v2 = v4;
  if ( v4 )
  {
    if ( !(*(unsigned int (__fastcall **)(struct _SLIST_ENTRY *))(a1 + 40))(v4 + 1) )
      return v2 + 1;
    free(v2);
  }
  return 0;
}

```

## disassembly

```asm
0x180008d40  mov     [rsp+arg_0], rbx
0x180008d45  push    rdi
0x180008d46  sub     rsp, 20h
0x180008d4a  mov     rdi, rcx
0x180008d4d  call    cs:__imp_InterlockedPopEntrySList
0x180008d53  mov     rbx, rax
0x180008d56  test    rax, rax
0x180008d59  jz      short loc_180008D66
0x180008d5b  lock dec qword ptr [rdi+10h]
0x180008d60  lea     rax, [rbx+10h]
0x180008d64  jmp     short loc_180008D98
0x180008d66  mov     rcx, [rdi+20h]
0x180008d6a  add     rcx, 10h; Size
0x180008d6e  call    cs:__imp_malloc
0x180008d74  mov     rbx, rax
0x180008d77  test    rax, rax
0x180008d7a  jz      short loc_180008D96
0x180008d7c  lea     rcx, [rax+10h]
0x180008d80  mov     rax, [rdi+28h]
0x180008d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d89  test    eax, eax
0x180008d8b  jz      short loc_180008D60
0x180008d8d  mov     rcx, rbx; Block
0x180008d90  call    cs:__imp_free
0x180008d96  xor     eax, eax
0x180008d98  mov     rbx, [rsp+28h+arg_0]
0x180008d9d  add     rsp, 20h
0x180008da1  pop     rdi
0x180008da2  retn
```
