# CBrush::~CBrush(void)

- ea: `0x18014e37c`
- end: `0x18014e3d9`
- name: `??1CBrush@@QEAA@XZ`
- size: `93`
- prototype: `void __fastcall(CBrush *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18012214c`

## callees

- `0x18014e37c`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014e3b1`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014e3b1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014e3c1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014e3c1`

## pseudocode

```c
void __fastcall CBrush::~CBrush(CBrush *this)
{
  void *v2; // rbx
  HDC v3; // rax

  if ( *((_QWORD *)this + 2) )
  {
    v2 = (void *)*((_QWORD *)this + 1);
    v3 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 336LL) + 48LL))(*(_QWORD *)(*((_QWORD *)this + 3) + 336LL));
    SelectObject(v3, v2);
    DeleteObject(*((HGDIOBJ *)this + 2));
  }
}

```

## disassembly

```asm
0x18014e37c  mov     [rsp+arg_0], rbx
0x18014e381  push    rdi
0x18014e382  sub     rsp, 20h
0x18014e386  cmp     qword ptr [rcx+10h], 0
0x18014e38b  mov     rdi, rcx
0x18014e38e  jz      short loc_18014E3CD
0x18014e390  mov     rax, [rcx+18h]
0x18014e394  mov     rbx, [rcx+8]
0x18014e398  mov     rcx, [rax+150h]
0x18014e39f  mov     rax, [rcx]
0x18014e3a2  mov     rax, [rax+30h]
0x18014e3a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e3ab  mov     rdx, rbx; h
0x18014e3ae  mov     rcx, rax; hdc
0x18014e3b1  call    cs:__imp_SelectObject
0x18014e3b8  nop     dword ptr [rax+rax+00h]
0x18014e3bd  mov     rcx, [rdi+10h]; ho
0x18014e3c1  call    cs:__imp_DeleteObject
0x18014e3c8  nop     dword ptr [rax+rax+00h]
0x18014e3cd  mov     rbx, [rsp+28h+arg_0]
0x18014e3d2  add     rsp, 20h
0x18014e3d6  pop     rdi
0x18014e3d7  retn
```
