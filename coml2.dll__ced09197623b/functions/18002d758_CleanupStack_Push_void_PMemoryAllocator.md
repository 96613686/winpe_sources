# CleanupStack::Push(void *,PMemoryAllocator *)

- ea: `0x18002d758`
- end: `0x18002d830`
- name: `?Push@CleanupStack@@QEAAJPEAXPEAVPMemoryAllocator@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(CleanupStack *__hidden this, void *, struct PMemoryAllocator *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002aca0`
- `0x18002c174`
- `0x18002d838`
- `0x18003ca7c`

## callees

- `0x18002d758`
- `0x180043100`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d78f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d78f`

## pseudocode

```c
__int64 __fastcall CleanupStack::Push(CleanupStack *this, void *a2, struct PMemoryAllocator *a3)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rdi

  if ( !a2 )
    return 3221225495LL;
  if ( *(_DWORD *)(*((_QWORD *)this + 43) + 320LL) >= 0x14u )
  {
    v7 = CoTaskMemAlloc(0x158u);
    v8 = v7;
    if ( !v7 )
    {
      (*(void (__fastcall **)(struct PMemoryAllocator *, void *))(*(_QWORD *)a3 + 8LL))(a3, a2);
      return 3221225495LL;
    }
    memset_0(v7, 0, 0x158u);
    v8[41] = *((_QWORD *)this + 43);
    *(_QWORD *)(*((_QWORD *)this + 43) + 336LL) = v8;
    *((_QWORD *)this + 43) = v8;
    *((_DWORD *)v8 + 80) = 0;
  }
  *(_QWORD *)(*((_QWORD *)this + 43) + 16LL * *(unsigned int *)(*((_QWORD *)this + 43) + 320LL)) = a2;
  *(_QWORD *)(*((_QWORD *)this + 43) + 16LL * (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 43) + 320LL))++ + 8) = a3;
  return 0;
}

```

## disassembly

```asm
0x18002d758  push    rbx
0x18002d75a  push    rsi
0x18002d75b  push    rdi
0x18002d75c  push    r14
0x18002d75e  sub     rsp, 28h
0x18002d762  mov     r14, r8
0x18002d765  mov     rsi, rdx
0x18002d768  mov     rbx, rcx
0x18002d76b  test    rdx, rdx
0x18002d76e  jnz     short loc_18002D77A
0x18002d770  mov     eax, 0C0000017h
0x18002d775  jmp     loc_18002D826
0x18002d77a  mov     rax, [rcx+158h]
0x18002d781  cmp     dword ptr [rax+140h], 14h
0x18002d788  jb      short loc_18002D7EE
0x18002d78a  mov     ecx, 158h; cb
0x18002d78f  call    cs:__imp_CoTaskMemAlloc
0x18002d795  mov     rdi, rax
0x18002d798  test    rax, rax
0x18002d79b  jnz     short loc_18002D7B1
0x18002d79d  mov     rax, [r14]
0x18002d7a0  mov     rdx, rsi
0x18002d7a3  mov     rcx, r14
0x18002d7a6  mov     rax, [rax+8]
0x18002d7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7af  jmp     short loc_18002D770
0x18002d7b1  xor     edx, edx; Val
0x18002d7b3  mov     r8d, 158h; Size
0x18002d7b9  mov     rcx, rdi; void *
0x18002d7bc  call    memset_0
0x18002d7c1  mov     rax, [rbx+158h]
0x18002d7c8  mov     [rdi+148h], rax
0x18002d7cf  mov     rax, [rbx+158h]
0x18002d7d6  mov     [rax+150h], rdi
0x18002d7dd  mov     [rbx+158h], rdi
0x18002d7e4  mov     dword ptr [rdi+140h], 0
0x18002d7ee  mov     rcx, [rbx+158h]
0x18002d7f5  mov     eax, [rcx+140h]
0x18002d7fb  add     rax, rax
0x18002d7fe  mov     [rcx+rax*8], rsi
0x18002d802  mov     rcx, [rbx+158h]
0x18002d809  mov     eax, [rcx+140h]
0x18002d80f  add     rax, rax
0x18002d812  mov     [rcx+rax*8+8], r14
0x18002d817  mov     rax, [rbx+158h]
0x18002d81e  inc     dword ptr [rax+140h]
0x18002d824  xor     eax, eax
0x18002d826  add     rsp, 28h
0x18002d82a  pop     r14
0x18002d82c  pop     rdi
0x18002d82d  pop     rsi
0x18002d82e  pop     rbx
0x18002d82f  retn
```
