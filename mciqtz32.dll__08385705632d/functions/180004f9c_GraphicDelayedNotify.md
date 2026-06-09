# GraphicDelayedNotify

- ea: `0x180004f9c`
- end: `0x180004fd5`
- name: `GraphicDelayedNotify`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f60`
- `0x180002b78`
- `0x180003074`
- `0x180003408`
- `0x1800034b0`
- `0x180003d40`
- `0x180004314`
- `0x18000485c`

## callees

- `0x180004f9c`

## import_xrefs

- `USER32!PostMessageW` at `0x180004fc2`
- `USER32!PostMessageW` at `0x180004fc2`

## pseudocode

```c
BOOL __fastcall GraphicDelayedNotify(__int64 a1, unsigned int a2)
{
  HWND v3; // rcx
  BOOL result; // eax

  v3 = *(HWND *)a1;
  if ( v3 )
  {
    if ( !gfEvil )
      result = PostMessageW(v3, 0x3B9u, a2, *(unsigned int *)(a1 + 8));
    *(_QWORD *)a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004f9c  push    rbx
0x180004f9e  sub     rsp, 20h
0x180004fa2  mov     rbx, rcx
0x180004fa5  mov     rcx, [rcx]; hWnd
0x180004fa8  test    rcx, rcx
0x180004fab  jz      short loc_180004FCF
0x180004fad  cmp     cs:?gfEvil@@3HA, 0; int gfEvil
0x180004fb4  jnz     short loc_180004FC8
0x180004fb6  mov     r9d, [rbx+8]; lParam
0x180004fba  mov     r8d, edx; wParam
0x180004fbd  mov     edx, 3B9h; Msg
0x180004fc2  call    cs:__imp_PostMessageW
0x180004fc8  mov     qword ptr [rbx], 0
0x180004fcf  add     rsp, 20h
0x180004fd3  pop     rbx
0x180004fd4  retn
```
