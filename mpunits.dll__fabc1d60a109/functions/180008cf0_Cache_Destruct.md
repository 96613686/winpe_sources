# Cache_Destruct

- ea: `0x180008cf0`
- end: `0x180008d36`
- name: `Cache_Destruct`
- size: `70`
- prototype: `__int64 __fastcall(PSLIST_HEADER ListHead)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180013930`
- `0x18002e650`

## callees

- `0x180008cf0`
- `0x180045010`

## import_xrefs

- `msvcrt!free` at `0x180008d23`
- `msvcrt!free` at `0x180008d23`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180008d00`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180008d00`

## pseudocode

```c
PSLIST_ENTRY __fastcall Cache_Destruct(PSLIST_HEADER ListHead)
{
  PSLIST_ENTRY result; // rax
  PSLIST_ENTRY v3; // rdi

  while ( 1 )
  {
    result = InterlockedPopEntrySList(ListHead);
    v3 = result;
    if ( !result )
      break;
    _InterlockedDecrement64((volatile signed __int64 *)&ListHead[1]);
    ((void (__fastcall *)(struct _SLIST_ENTRY *))ListHead[3].Alignment)(&result[1]);
    free(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180008cf0  mov     [rsp+arg_0], rbx
0x180008cf5  push    rdi
0x180008cf6  sub     rsp, 20h
0x180008cfa  mov     rbx, rcx
0x180008cfd  mov     rcx, rbx; ListHead
0x180008d00  call    cs:__imp_InterlockedPopEntrySList
0x180008d06  mov     rdi, rax
0x180008d09  test    rax, rax
0x180008d0c  jz      short loc_180008D2B
0x180008d0e  lock dec qword ptr [rbx+10h]
0x180008d13  lea     rcx, [rax+10h]
0x180008d17  mov     rax, [rbx+30h]
0x180008d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d20  mov     rcx, rdi; Block
0x180008d23  call    cs:__imp_free
0x180008d29  jmp     short loc_180008CFD
0x180008d2b  mov     rbx, [rsp+28h+arg_0]
0x180008d30  add     rsp, 20h
0x180008d34  pop     rdi
0x180008d35  retn
```
