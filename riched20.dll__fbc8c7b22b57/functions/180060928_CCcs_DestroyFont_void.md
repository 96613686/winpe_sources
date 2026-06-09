# CCcs::DestroyFont(void)

- ea: `0x180060928`
- end: `0x180060955`
- name: `?DestroyFont@CCcs@@AEAAXXZ`
- size: `45`
- prototype: `void __fastcall(CCcs *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180048790`
- `0x18006095c`
- `0x180060bb0`

## callees

- `0x180060928`

## import_xrefs

- `GDI32!DeleteObject` at `0x18006093a`
- `GDI32!DeleteObject` at `0x18006093a`

## pseudocode

```c
void __fastcall CCcs::DestroyFont(CCcs *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    DeleteObject(v2);
    *((_QWORD *)this + 9) = 0;
  }
}

```

## disassembly

```asm
0x180060928  push    rbx
0x18006092a  sub     rsp, 20h
0x18006092e  mov     rbx, rcx
0x180060931  mov     rcx, [rcx+48h]; ho
0x180060935  test    rcx, rcx
0x180060938  jz      short loc_18006094E
0x18006093a  call    cs:__imp_DeleteObject
0x180060941  nop     dword ptr [rax+rax+00h]
0x180060946  mov     qword ptr [rbx+48h], 0
0x18006094e  add     rsp, 20h
0x180060952  pop     rbx
0x180060953  retn
```
