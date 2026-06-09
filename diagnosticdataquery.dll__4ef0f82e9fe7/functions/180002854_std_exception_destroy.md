# __std_exception_destroy

- ea: `0x180002854`
- end: `0x18000287c`
- name: `__std_exception_destroy`
- size: `40`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ef4`
- `0x180001f10`
- `0x180005ed0`
- `0x180006080`

## callees

- `0x180002854`
- `0x180005146`

## pseudocode

```c
void __fastcall _std_exception_destroy(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
    free_0(*(void **)a1);
  *(_BYTE *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x180002854  push    rbx
0x180002856  sub     rsp, 20h
0x18000285a  cmp     byte ptr [rcx+8], 0
0x18000285e  mov     rbx, rcx
0x180002861  jz      short loc_18000286B
0x180002863  mov     rcx, [rcx]; Block
0x180002866  call    free_0
0x18000286b  mov     byte ptr [rbx+8], 0
0x18000286f  mov     qword ptr [rbx], 0
0x180002876  add     rsp, 20h
0x18000287a  pop     rbx
0x18000287b  retn
```
