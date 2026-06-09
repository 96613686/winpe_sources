# CFontPreview::SetBackgroundColor(ulong)

- ea: `0x1800248d0`
- end: `0x180024910`
- name: `?SetBackgroundColor@CFontPreview@@UEAAJK@Z`
- size: `64`
- prototype: `int(CFontPreview *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800248d0`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800248eb`
- `GDI32!DeleteObject` at `0x1800248eb`
- `GDI32!CreateSolidBrush` at `0x1800248f6`
- `GDI32!CreateSolidBrush` at `0x1800248f6`

## pseudocode

```c
__int64 __fastcall CFontPreview::SetBackgroundColor(CFontPreview *this, COLORREF a2)
{
  void *v4; // rcx

  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 )
    DeleteObject(v4);
  *((_DWORD *)this + 31) = a2;
  *((_QWORD *)this + 16) = CreateSolidBrush(a2);
  return 0;
}

```

## disassembly

```asm
0x1800248d0  mov     [rsp+arg_0], rbx
0x1800248d5  push    rdi
0x1800248d6  sub     rsp, 20h
0x1800248da  mov     rbx, rcx
0x1800248dd  mov     edi, edx
0x1800248df  mov     rcx, [rcx+80h]; ho
0x1800248e6  test    rcx, rcx
0x1800248e9  jz      short loc_1800248F1
0x1800248eb  call    cs:__imp_DeleteObject
0x1800248f1  mov     ecx, edi; color
0x1800248f3  mov     [rbx+7Ch], edi
0x1800248f6  call    cs:__imp_CreateSolidBrush
0x1800248fc  mov     [rbx+80h], rax
0x180024903  xor     eax, eax
0x180024905  mov     rbx, [rsp+28h+arg_0]
0x18002490a  add     rsp, 20h
0x18002490e  pop     rdi
0x18002490f  retn
```
