# _ResourceStringAllocCopyExCoAlloc

- ea: `0x18000427c`
- end: `0x1800042a5`
- name: `_ResourceStringAllocCopyExCoAlloc`
- size: `41`
- prototype: `__int64 __fastcall(__int64, SIZE_T, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800041cc`

## callees

- `0x18000427c`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180004288`
- `ole32!CoTaskMemAlloc` at `0x180004288`

## pseudocode

```c
__int64 __fastcall ResourceStringAllocCopyExCoAlloc(__int64 a1, SIZE_T a2, _QWORD *a3)
{
  LPVOID v4; // rax

  v4 = CoTaskMemAlloc(a2);
  if ( !v4 )
    return 2147942414LL;
  *a3 = v4;
  return 0;
}

```

## disassembly

```asm
0x18000427c  push    rbx
0x18000427e  sub     rsp, 20h
0x180004282  mov     rcx, rdx; cb
0x180004285  mov     rbx, r8
0x180004288  call    cs:__imp_CoTaskMemAlloc
0x18000428e  test    rax, rax
0x180004291  jz      short loc_18000429A
0x180004293  mov     [rbx], rax
0x180004296  xor     eax, eax
0x180004298  jmp     short loc_18000429F
0x18000429a  mov     eax, 8007000Eh
0x18000429f  add     rsp, 20h
0x1800042a3  pop     rbx
0x1800042a4  retn
```
