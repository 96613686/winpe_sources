# Cache_DepositBack

- ea: `0x180008c90`
- end: `0x180008ce0`
- name: `Cache_DepositBack`
- size: `80`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180013ad0`
- `0x18002e540`
- `0x18002e98c`
- `0x18002e9d0`
- `0x18002eb20`

## callees

- `0x180008c90`
- `0x180045010`

## import_xrefs

- `msvcrt!free` at `0x180008cca`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180008cd9`

## pseudocode

```c
void __fastcall Cache_DepositBack(__int64 a1, __int64 a2)
{
  void *v2; // rbx

  v2 = (void *)(a2 - 16);
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 16)) <= *(_QWORD *)(a1 + 24) )
  {
    InterlockedPushEntrySList((PSLIST_HEADER)a1, (PSLIST_ENTRY)(a2 - 16));
  }
  else
  {
    _InterlockedDecrement64((volatile signed __int64 *)(a1 + 16));
    (*(void (__fastcall **)(__int64))(a1 + 48))(a2);
    free(v2);
  }
}

```

## disassembly

```asm
0x180008c90  push    rbx
0x180008c92  sub     rsp, 20h
0x180008c96  mov     r8, rcx
0x180008c99  lea     rbx, [rdx-10h]
0x180008c9d  mov     eax, 1
0x180008ca2  lock xadd [rcx+10h], rax
0x180008ca8  inc     rax
0x180008cab  cmp     rax, [rcx+18h]
0x180008caf  jle     short loc_180008CD1
0x180008cb1  lock dec qword ptr [rcx+10h]
0x180008cb6  mov     rcx, rdx
0x180008cb9  mov     rax, [r8+30h]
0x180008cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc2  mov     rcx, rbx
0x180008cc5  add     rsp, 20h
0x180008cc9  pop     rbx
0x180008cca  jmp     cs:__imp_free
0x180008cd1  mov     rdx, rbx
0x180008cd4  add     rsp, 20h
0x180008cd8  pop     rbx
0x180008cd9  jmp     cs:__imp_InterlockedPushEntrySList
```
