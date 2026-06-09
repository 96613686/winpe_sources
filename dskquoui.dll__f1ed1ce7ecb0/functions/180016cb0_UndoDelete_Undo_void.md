# UndoDelete::Undo(void)

- ea: `0x180016cb0`
- end: `0x180016d92`
- name: `?Undo@UndoDelete@@UEAAJXZ`
- size: `226`
- prototype: `__int64 __fastcall(UndoDelete *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800022b4`
- `0x180011208`
- `0x180016cb0`
- `0x18001f010`

## import_xrefs

- `USER32!SendMessageW` at `0x180016d62`
- `USER32!SendMessageW` at `0x180016d62`

## pseudocode

```c
Undo *__fastcall UndoDelete::Undo(Undo *this)
{
  int v2; // esi
  __int64 v3; // rcx
  HWND v4; // rdi
  PointerList *v5; // rbx
  const void *v6; // rdx
  LPARAM lParam; // [rsp+20h] [rbp-88h] BYREF
  int v9; // [rsp+28h] [rbp-80h]
  __int64 v10; // [rsp+2Ch] [rbp-7Ch]
  __int64 v11; // [rsp+38h] [rbp-70h]
  int v12; // [rsp+44h] [rbp-64h]

  (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 2) + 120LL))(
    *((_QWORD *)this + 2),
    *((_QWORD *)this + 4),
    1);
  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 2) + 112LL))(
         *((_QWORD *)this + 2),
         *((_QWORD *)this + 5),
         1);
  if ( v2 >= 0 )
  {
    v3 = *((_QWORD *)this + 3);
    v4 = *(HWND *)(v3 + 64);
    v5 = *(PointerList **)(v3 + 56);
    memset_0(&lParam, 0, 0x58u);
    v6 = (const void *)*((_QWORD *)this + 2);
    lParam = 11;
    v10 = 0;
    v9 = 0;
    v11 = -1;
    v12 = -1;
    PointerList::Insert(v5, v6, 0);
    if ( (unsigned int)SendMessageW(v4, 0x104Du, 0, (LPARAM)&lParam) == -1 )
      v2 = -2147467259;
    else
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 8LL))(*((_QWORD *)this + 2));
  }
  return (Undo *)(unsigned int)v2;
}

```

## disassembly

```asm
0x180016cb0  push    rbx
0x180016cb2  push    rbp
0x180016cb3  push    rsi
0x180016cb4  push    rdi
0x180016cb5  sub     rsp, 88h
0x180016cbc  mov     rbp, rcx
0x180016cbf  mov     ebx, 1
0x180016cc4  mov     rcx, [rcx+10h]
0x180016cc8  mov     r8d, ebx
0x180016ccb  mov     rdx, [rbp+20h]
0x180016ccf  mov     rax, [rcx]
0x180016cd2  mov     rax, [rax+78h]
0x180016cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cdb  mov     rcx, [rbp+10h]
0x180016cdf  mov     r8d, ebx
0x180016ce2  mov     rdx, [rbp+28h]
0x180016ce6  mov     rax, [rcx]
0x180016ce9  mov     rax, [rax+70h]
0x180016ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cf2  mov     esi, eax
0x180016cf4  test    eax, eax
0x180016cf6  js      loc_180016D84
0x180016cfc  mov     rcx, [rbp+18h]
0x180016d00  xor     edx, edx; Val
0x180016d02  mov     rdi, [rcx+40h]
0x180016d06  lea     r8d, [rdx+58h]; Size
0x180016d0a  mov     rbx, [rcx+38h]
0x180016d0e  lea     rcx, [rsp+0A8h+lParam]; void *
0x180016d13  call    memset_0
0x180016d18  mov     rdx, [rbp+10h]; void *
0x180016d1c  xor     r8d, r8d; unsigned int
0x180016d1f  mov     rcx, rbx; this
0x180016d22  mov     [rsp+0A8h+lParam], 0Bh
0x180016d2b  mov     [rsp+0A8h+var_7C], 0
0x180016d34  mov     [rsp+0A8h+var_80], 0
0x180016d3c  mov     [rsp+0A8h+var_70], 0FFFFFFFFFFFFFFFFh
0x180016d45  mov     [rsp+0A8h+var_64], 0FFFFFFFFh
0x180016d4d  call    ?Insert@PointerList@@QEAAXPEBXI@Z; PointerList::Insert(void const *,uint)
0x180016d52  lea     r9, [rsp+0A8h+lParam]; lParam
0x180016d57  xor     r8d, r8d; wParam
0x180016d5a  mov     edx, 104Dh; Msg
0x180016d5f  mov     rcx, rdi; hWnd
0x180016d62  call    cs:__imp_SendMessageW
0x180016d68  cmp     eax, 0FFFFFFFFh
0x180016d6b  jz      short loc_180016D7F
0x180016d6d  mov     rcx, [rbp+10h]
0x180016d71  mov     rax, [rcx]
0x180016d74  mov     rax, [rax+8]
0x180016d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d7d  jmp     short loc_180016D84
0x180016d7f  mov     esi, 80004005h
0x180016d84  mov     eax, esi
0x180016d86  add     rsp, 88h
0x180016d8d  pop     rdi
0x180016d8e  pop     rsi
0x180016d8f  pop     rbp
0x180016d90  pop     rbx
0x180016d91  retn
```
