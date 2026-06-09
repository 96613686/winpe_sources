# Windows::AutoComPtr<ICbsSession>::GetInitPointer(void)

- ea: `0x140024aa0`
- end: `0x140024ab8`
- name: `?GetInitPointer@?$AutoComPtr@UICbsSession@@@Windows@@QEAAPEAPEAUICbsSession@@XZ`
- size: `24`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400244a0`
- `0x140024604`
- `0x140024de0`
- `0x140024ed0`
- `0x140024fe0`

## callees

- `0x14000731c`
- `0x140024aa0`

## pseudocode

```c
_QWORD *__fastcall Windows::AutoComPtr<ICbsSession>::GetInitPointer(_QWORD *a1)
{
  if ( *a1 )
    INTERNAL_ERROR_ACTION((int)a1);
  return a1;
}

```

## disassembly

```asm
0x140024aa0  sub     rsp, 28h
0x140024aa4  cmp     qword ptr [rcx], 0
0x140024aa8  jnz     short loc_140024AB2
0x140024aaa  mov     rax, rcx
0x140024aad  add     rsp, 28h
0x140024ab1  retn
0x140024ab2  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
