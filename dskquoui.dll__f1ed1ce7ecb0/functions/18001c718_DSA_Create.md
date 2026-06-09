# DSA_Create

- ea: `0x18001c718`
- end: `0x18001c764`
- name: `DSA_Create`
- size: `76`
- prototype: `HDSA __stdcall(int cbItem, int cItemGrow)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d800`

## callees

- `0x18001c718`
- `0x18001cc10`
- `0x18001f010`

## pseudocode

```c
HDSA __stdcall DSA_Create(int cbItem, int cItemGrow)
{
  HDSA result; // rax

  result = (HDSA)qword_1800282B8;
  if ( qword_1800282B8 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_1800282B8, (const CHAR *)0x140);
    result = (HDSA)qword_1800282B8;
  }
  if ( result )
    return (HDSA)((__int64 (__fastcall *)(_QWORD, _QWORD))result)((unsigned int)cbItem, (unsigned int)cItemGrow);
  return result;
}

```

## disassembly

```asm
0x18001c718  mov     [rsp+arg_0], rbx
0x18001c71d  push    rdi
0x18001c71e  sub     rsp, 20h
0x18001c722  mov     rax, cs:qword_1800282B8
0x18001c729  mov     ebx, edx
0x18001c72b  mov     edi, ecx
0x18001c72d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c731  jnz     short loc_18001C74B
0x18001c733  mov     edx, 140h
0x18001c738  lea     rcx, qword_1800282B8
0x18001c73f  call    _GetProcFromComCtl32
0x18001c744  mov     rax, cs:qword_1800282B8
0x18001c74b  test    rax, rax
0x18001c74e  jz      short loc_18001C759
0x18001c750  mov     edx, ebx
0x18001c752  mov     ecx, edi
0x18001c754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c759  mov     rbx, [rsp+28h+arg_0]
0x18001c75e  add     rsp, 20h
0x18001c762  pop     rdi
0x18001c763  retn
```
