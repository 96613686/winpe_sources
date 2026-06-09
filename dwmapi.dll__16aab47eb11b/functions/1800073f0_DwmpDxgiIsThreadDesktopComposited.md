# DwmpDxgiIsThreadDesktopComposited

- ea: `0x1800073f0`
- end: `0x180007424`
- name: `DwmpDxgiIsThreadDesktopComposited`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003370`
- `0x1800073f0`

## import_xrefs

- `USER32!IsThreadDesktopComposited` at `0x1800073fe`
- `USER32!IsThreadDesktopComposited` at `0x1800073fe`

## pseudocode

```c
__int64 __fastcall DwmpDxgiIsThreadDesktopComposited(_DWORD *a1)
{
  if ( a1 )
  {
    *a1 = IsThreadDesktopComposited();
    return 0;
  }
  else
  {
    DoStackCaptureDirect(-2147024809, 0x417u);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800073f0  push    rbx
0x1800073f2  sub     rsp, 20h
0x1800073f6  mov     rbx, rcx
0x1800073f9  test    rcx, rcx
0x1800073fc  jz      short loc_18000740E
0x1800073fe  call    cs:__imp_IsThreadDesktopComposited
0x180007404  mov     [rbx], eax
0x180007406  xor     eax, eax
0x180007408  add     rsp, 20h
0x18000740c  pop     rbx
0x18000740d  retn
0x18000740e  mov     edx, 417h; unsigned int
0x180007413  mov     ecx, 80070057h; int
0x180007418  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18000741d  mov     eax, 80070057h
0x180007422  jmp     short loc_180007408
```
