# pStrBufCreate

- ea: `0x18000828c`
- end: `0x1800082f5`
- name: `pStrBufCreate`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005bcc`

## callees

- `0x180008248`
- `0x18000828c`
- `0x1800082fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082b6`
- `KERNEL32!HeapAlloc` at `0x1800082a5`
- `KERNEL32!HeapAlloc` at `0x1800082a5`

## pseudocode

```c
void *__fastcall pStrBufCreate(unsigned int a1)
{
  _QWORD *v2; // rax
  void *v3; // rbx

  v2 = HeapAlloc(hHeap, 0, 0x10u);
  v3 = v2;
  if ( !v2 )
  {
    SetLastError(8u);
LABEL_4:
    StrBufDestroyA(v3);
    return 0;
  }
  *v2 = 0;
  v2[1] = 0;
  if ( !(unsigned int)pStrBufGrow(v2, a1) )
    goto LABEL_4;
  return v3;
}

```

## disassembly

```asm
0x18000828c  mov     [rsp+arg_0], rbx
0x180008291  push    rdi
0x180008292  sub     rsp, 20h
0x180008296  xor     edx, edx; dwFlags
0x180008298  mov     edi, ecx
0x18000829a  mov     rcx, cs:hHeap; hHeap
0x1800082a1  lea     r8d, [rdx+10h]; dwBytes
0x1800082a5  call    cs:__imp_HeapAlloc
0x1800082ab  mov     rbx, rax
0x1800082ae  test    rax, rax
0x1800082b1  jnz     short loc_1800082BE
0x1800082b3  lea     ecx, [rax+8]; dwErrCode
0x1800082b6  call    cs:__imp_SetLastError
0x1800082bc  jmp     short loc_1800082DB
0x1800082be  mov     edx, edi
0x1800082c0  mov     qword ptr [rax], 0
0x1800082c7  mov     rcx, rbx
0x1800082ca  mov     qword ptr [rax+8], 0
0x1800082d2  call    pStrBufGrow
0x1800082d7  test    eax, eax
0x1800082d9  jnz     short loc_1800082E7
0x1800082db  mov     rcx, rbx; lpMem
0x1800082de  call    StrBufDestroyA
0x1800082e3  xor     eax, eax
0x1800082e5  jmp     short loc_1800082EA
0x1800082e7  mov     rax, rbx
0x1800082ea  mov     rbx, [rsp+28h+arg_0]
0x1800082ef  add     rsp, 20h
0x1800082f3  pop     rdi
0x1800082f4  retn
```
