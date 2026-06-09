# CRenderer::DrawLine(tagPOINT const *,long,int,ulong)

- ea: `0x1801114fc`
- end: `0x1801115fc`
- name: `?DrawLine@CRenderer@@QEAAXPEBUtagPOINT@@JHK@Z`
- size: `256`
- prototype: `void __fastcall(CRenderer *__hidden this, const struct tagPOINT *, int, int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18014e718`
- `0x1801924a0`

## callees

- `0x1801114fc`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18011157b`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801115d1`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18011157b`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801115d1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801115e0`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801115e0`

## pseudocode

```c
void __fastcall CRenderer::DrawLine(
        CRenderer *this,
        const struct tagPOINT *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  void *Pen; // rbx
  HGDIOBJ v6; // rdi
  HDC v11; // rax
  HDC v12; // rax

  Pen = 0;
  v6 = 0;
  if ( a3 )
  {
    if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42)) )
    {
      Pen = (void *)pfnCreatePen();
      if ( Pen )
      {
        v11 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
        v6 = SelectObject(v11, Pen);
      }
    }
  }
  (*(void (__fastcall **)(_QWORD, const struct tagPOINT *, _QWORD, _QWORD, unsigned int))(**((_QWORD **)this + 42)
                                                                                        + 232LL))(
    *((_QWORD *)this + 42),
    a2,
    a3,
    a4,
    a5);
  if ( Pen )
  {
    if ( v6 )
    {
      v12 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
      SelectObject(v12, v6);
    }
    DeleteObject(Pen);
  }
}

```

## disassembly

```asm
0x1801114fc  push    rbx
0x1801114fe  push    rbp
0x1801114ff  push    rsi
0x180111500  push    rdi
0x180111501  push    r12
0x180111503  push    r14
0x180111505  push    r15
0x180111507  sub     rsp, 30h
0x18011150b  mov     r15d, [rsp+68h+arg_20]
0x180111513  xor     ebx, ebx
0x180111515  xor     edi, edi
0x180111517  mov     r14d, r9d
0x18011151a  mov     ebp, r8d
0x18011151d  mov     r12, rdx
0x180111520  mov     rsi, rcx
0x180111523  test    r8d, r8d
0x180111526  jz      short loc_18011158A
0x180111528  mov     rcx, [rcx+150h]
0x18011152f  mov     rax, [rcx]
0x180111532  mov     rax, [rax+30h]
0x180111536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011153b  test    rax, rax
0x18011153e  jz      short loc_18011158A
0x180111540  mov     rax, cs:?pfnCreatePen@@3P6A_JXZEA; __int64 (*pfnCreatePen)(void)
0x180111547  xor     edx, edx
0x180111549  test    r14d, r14d
0x18011154c  mov     r8d, r15d
0x18011154f  mov     ecx, r14d
0x180111552  cmovz   edx, ebp
0x180111555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011155a  mov     rbx, rax
0x18011155d  test    rax, rax
0x180111560  jz      short loc_18011158A
0x180111562  mov     rcx, [rsi+150h]
0x180111569  mov     rdx, [rcx]
0x18011156c  mov     rax, [rdx+30h]
0x180111570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180111575  mov     rdx, rbx; h
0x180111578  mov     rcx, rax; hdc
0x18011157b  call    cs:__imp_SelectObject
0x180111582  nop     dword ptr [rax+rax+00h]
0x180111587  mov     rdi, rax
0x18011158a  mov     rcx, [rsi+150h]
0x180111591  mov     r9d, r14d
0x180111594  mov     r8d, ebp
0x180111597  mov     [rsp+68h+var_48], r15d
0x18011159c  mov     rdx, [rcx]
0x18011159f  mov     rax, [rdx+0E8h]
0x1801115a6  mov     rdx, r12
0x1801115a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801115ae  test    rbx, rbx
0x1801115b1  jz      short loc_1801115EC
0x1801115b3  test    rdi, rdi
0x1801115b6  jz      short loc_1801115DD
0x1801115b8  mov     rcx, [rsi+150h]
0x1801115bf  mov     rax, [rcx]
0x1801115c2  mov     rax, [rax+30h]
0x1801115c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801115cb  mov     rdx, rdi; h
0x1801115ce  mov     rcx, rax; hdc
0x1801115d1  call    cs:__imp_SelectObject
0x1801115d8  nop     dword ptr [rax+rax+00h]
0x1801115dd  mov     rcx, rbx; ho
0x1801115e0  call    cs:__imp_DeleteObject
0x1801115e7  nop     dword ptr [rax+rax+00h]
0x1801115ec  add     rsp, 30h
0x1801115f0  pop     r15
0x1801115f2  pop     r14
0x1801115f4  pop     r12
0x1801115f6  pop     rdi
0x1801115f7  pop     rsi
0x1801115f8  pop     rbp
0x1801115f9  pop     rbx
0x1801115fa  retn
```
