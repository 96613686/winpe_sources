# WSTReferenceContext(_WST_CONTEXT *)

- ea: `0x18000ec70`
- end: `0x18000ec93`
- name: `?WSTReferenceContext@@YAXPEAU_WST_CONTEXT@@@Z`
- size: `35`
- prototype: `void __fastcall(struct _WST_CONTEXT *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180009db0`
- `0x18000a29c`
- `0x18000cd24`
- `0x180014150`
- `0x180018770`
- `0x18001d1b8`
- `0x18001d2a4`

## callees

- `0x18000ec70`
- `0x18001a390`

## pseudocode

```c
void __fastcall WSTReferenceContext(struct _WST_CONTEXT *a1)
{
  if ( a1 )
  {
    if ( *(_QWORD *)a1 == 0x545854434F545357LL )
      _InterlockedIncrement((volatile signed __int32 *)a1 + 3);
  }
}

```

## disassembly

```asm
0x18000ec70  sub     rsp, 28h
0x18000ec74  test    rcx, rcx
0x18000ec77  jz      short loc_18000EC8E
0x18000ec79  mov     rax, 545854434F545357h
0x18000ec83  cmp     [rcx], rax
0x18000ec86  jnz     short loc_18000EC8E
0x18000ec88  lock inc dword ptr [rcx+0Ch]
0x18000ec8c  jmp     short $+2
0x18000ec8e  add     rsp, 28h
0x18000ec92  retn
0x18001efc0  push    rbp
0x18001efc2  sub     rsp, 20h
0x18001efc6  mov     rbp, rdx
0x18001efc9  call    ?WSTExceptionFilter@@YAKXZ; WSTExceptionFilter(void)
0x18001efce  nop
0x18001efcf  add     rsp, 20h
0x18001efd3  pop     rbp
0x18001efd4  retn
```
