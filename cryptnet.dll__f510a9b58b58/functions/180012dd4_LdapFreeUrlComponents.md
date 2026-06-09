# LdapFreeUrlComponents

- ea: `0x180012dd4`
- end: `0x180012e16`
- name: `LdapFreeUrlComponents`
- size: `66`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011280`
- `0x180012b4c`
- `0x1800196e0`
- `0x18001d04c`

## callees

- `0x18000a990`
- `0x180012dd4`

## pseudocode

```c
void __fastcall LdapFreeUrlComponents(HLOCAL *a1)
{
  HLOCAL *v2; // rcx

  operator delete(*a1);
  operator delete(a1[2]);
  v2 = (HLOCAL *)a1[4];
  if ( v2 )
    operator delete(*v2);
  operator delete(a1[4]);
  operator delete(a1[6]);
}

```

## disassembly

```asm
0x180012dd4  push    rbx
0x180012dd6  sub     rsp, 20h
0x180012dda  mov     rbx, rcx
0x180012ddd  mov     rcx, [rcx]; hMem
0x180012de0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012de5  mov     rcx, [rbx+10h]; hMem
0x180012de9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012dee  mov     rcx, [rbx+20h]
0x180012df2  test    rcx, rcx
0x180012df5  jz      short loc_180012DFF
0x180012df7  mov     rcx, [rcx]; hMem
0x180012dfa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012dff  mov     rcx, [rbx+20h]; hMem
0x180012e03  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012e08  mov     rcx, [rbx+30h]; hMem
0x180012e0c  add     rsp, 20h
0x180012e10  pop     rbx
0x180012e11  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
