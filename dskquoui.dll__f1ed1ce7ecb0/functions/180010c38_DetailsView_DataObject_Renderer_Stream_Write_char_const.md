# DetailsView::DataObject::Renderer::Stream::Write(char const *)

- ea: `0x180010c38`
- end: `0x180010c69`
- name: `?Write@Stream@Renderer@DataObject@DetailsView@@QEAAXPEBD@Z`
- size: `49`
- prototype: `void __fastcall(DetailsView::DataObject::Renderer::Stream *__hidden this, const char *)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180008150`
- `0x180008360`
- `0x180008510`
- `0x180008640`
- `0x1800087c0`
- `0x1800087e0`
- `0x180008890`
- `0x180008e10`
- `0x180008e30`
- `0x180008e50`
- `0x18000a920`
- `0x18000a940`

## callees

- `0x180010c70`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x180010c4b`
- `KERNEL32!lstrlenA` at `0x180010c4b`

## pseudocode

```c
void __fastcall DetailsView::DataObject::Renderer::Stream::Write(
        DetailsView::DataObject::Renderer::Stream *this,
        const char *a2)
{
  unsigned int v4; // eax

  v4 = lstrlenA(a2);
  DetailsView::DataObject::Renderer::Stream::Write(this, (const unsigned __int8 *)a2, v4);
}

```

## disassembly

```asm
0x180010c38  mov     [rsp+arg_0], rbx
0x180010c3d  push    rdi
0x180010c3e  sub     rsp, 20h
0x180010c42  mov     rdi, rcx
0x180010c45  mov     rbx, rdx
0x180010c48  mov     rcx, rdx; lpString
0x180010c4b  call    cs:__imp_lstrlenA
0x180010c51  mov     rdx, rbx; unsigned __int8 *
0x180010c54  mov     rcx, rdi; this
0x180010c57  mov     r8d, eax; unsigned int
0x180010c5a  mov     rbx, [rsp+28h+arg_0]
0x180010c5f  add     rsp, 20h
0x180010c63  pop     rdi
0x180010c64  jmp     ?Write@Stream@Renderer@DataObject@DetailsView@@QEAAXPEBEI@Z; DetailsView::DataObject::Renderer::Stream::Write(uchar const *,uint)
```
