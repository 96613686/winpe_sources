# CToc::Refresh(void)

- ea: `0x18001c520`
- end: `0x18001c652`
- name: `?Refresh@CToc@@UEAAXXZ`
- size: `306`
- prototype: `void __fastcall(LONG_PTR dwNewLong)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180011104`
- `0x180019590`
- `0x1800197c8`
- `0x18001a448`
- `0x18001c520`
- `0x180078010`

## import_xrefs

- `USER32!RemovePropA` at `0x18001c61a`
- `USER32!RemovePropA` at `0x18001c61a`
- `USER32!DestroyWindow` at `0x18001c627`
- `USER32!DestroyWindow` at `0x18001c627`
- `USER32!SendMessageA` at `0x18001c584`
- `USER32!SendMessageA` at `0x18001c5e4`
- `USER32!SendMessageA` at `0x18001c584`
- `USER32!SendMessageA` at `0x18001c5e4`
- `USER32!GetParent` at `0x18001c603`
- `USER32!GetParent` at `0x18001c603`

## pseudocode

```c
void __fastcall CToc::Refresh(LONG_PTR dwNewLong)
{
  HWND v2; // rcx
  LPARAM v3; // r9
  WPARAM i; // r8
  struct _TREEITEM *v5; // rax
  HWND v6; // rcx
  struct _TREEITEM *v7; // rbx
  HWND Parent; // rbx
  struct tagTVITEMW v9; // [rsp+20h] [rbp-48h] BYREF

  v2 = *(HWND *)(dwNewLong + 424);
  memset(&v9, 0, sizeof(v9));
  if ( v2 )
  {
    if ( *(_DWORD *)(dwNewLong + 8) )
    {
      v3 = 0;
      for ( i = 0; ; i = 1 )
      {
        v5 = (struct _TREEITEM *)SendMessageA(v2, 0x110Au, i, v3);
        v6 = *(HWND *)(dwNewLong + 424);
        v7 = v5;
        if ( !v5 )
          break;
        FreeChildrenAllocations(v6, v5);
        v2 = *(HWND *)(dwNewLong + 424);
        v3 = (LPARAM)v7;
      }
      v9.hItem = 0;
      v9.mask = 4;
      if ( W_TreeView_GetItem_fn(v6, &v9) )
      {
        if ( v9.lParam )
          (**(void (__fastcall ***)(LPARAM, __int64))v9.lParam)(v9.lParam, 1);
      }
      SendMessageA(*(HWND *)(dwNewLong + 424), 0x1101u, 0, -65536);
      LoadFirstLevel(
        *(struct CTreeNode **)(dwNewLong + 16),
        *(HWND *)(dwNewLong + 424),
        (struct _TREEITEM **)(dwNewLong + 376));
    }
    else
    {
      Parent = GetParent(v2);
      RemovePropA(*(HWND *)(dwNewLong + 424), "HHDefProc");
      DestroyWindow(*(HWND *)(dwNewLong + 424));
      (*(void (__fastcall **)(LONG_PTR, HWND))(*(_QWORD *)dwNewLong + 8LL))(dwNewLong, Parent);
      CToc::InitTreeView(dwNewLong);
    }
  }
}

```

## disassembly

```asm
0x18001c520  mov     [rsp+arg_0], rbx
0x18001c525  push    rdi
0x18001c526  sub     rsp, 60h
0x18001c52a  xorps   xmm0, xmm0
0x18001c52d  xor     eax, eax
0x18001c52f  mov     rdi, rcx
0x18001c532  mov     [rsp+68h+var_48.lParam], rax
0x18001c537  mov     rcx, [rcx+1A8h]; hWnd
0x18001c53e  movups  xmmword ptr [rsp+68h+var_48.mask], xmm0
0x18001c543  movups  xmmword ptr [rsp+68h+var_48.state], xmm0
0x18001c548  movups  xmmword ptr [rsp+68h+var_48.cchTextMax], xmm0
0x18001c54d  test    rcx, rcx
0x18001c550  jz      loc_18001C647
0x18001c556  cmp     [rdi+8], eax
0x18001c559  jz      loc_18001C603
0x18001c55f  xor     r9d, r9d
0x18001c562  xor     r8d, r8d
0x18001c565  jmp     short loc_18001C57F
0x18001c567  mov     rdx, rbx; struct _TREEITEM *
0x18001c56a  call    ?FreeChildrenAllocations@@YAXPEAUHWND__@@PEAU_TREEITEM@@@Z; FreeChildrenAllocations(HWND__ *,_TREEITEM *)
0x18001c56f  mov     rcx, [rdi+1A8h]; hWnd
0x18001c576  mov     r9, rbx; lParam
0x18001c579  mov     r8d, 1; wParam
0x18001c57f  mov     edx, 110Ah; Msg
0x18001c584  call    cs:__imp_SendMessageA
0x18001c58a  mov     rcx, [rdi+1A8h]; HWND
0x18001c591  mov     rbx, rax
0x18001c594  test    rax, rax
0x18001c597  jnz     short loc_18001C567
0x18001c599  lea     rdx, [rsp+68h+var_48]; struct tagTVITEMW *
0x18001c59e  mov     [rsp+68h+var_48.hItem], rax
0x18001c5a3  mov     [rsp+68h+var_48.mask], 4
0x18001c5ab  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x18001c5b0  test    eax, eax
0x18001c5b2  jz      short loc_18001C5CE
0x18001c5b4  mov     rcx, [rsp+68h+var_48.lParam]
0x18001c5b9  test    rcx, rcx
0x18001c5bc  jz      short loc_18001C5CE
0x18001c5be  mov     rax, [rcx]
0x18001c5c1  mov     edx, 1
0x18001c5c6  mov     rax, [rax]
0x18001c5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5ce  mov     rcx, [rdi+1A8h]; hWnd
0x18001c5d5  mov     r9, 0FFFFFFFFFFFF0000h; lParam
0x18001c5dc  xor     r8d, r8d; wParam
0x18001c5df  mov     edx, 1101h; Msg
0x18001c5e4  call    cs:__imp_SendMessageA
0x18001c5ea  mov     rdx, [rdi+1A8h]; HWND
0x18001c5f1  lea     r8, [rdi+178h]; struct _TREEITEM **
0x18001c5f8  mov     rcx, [rdi+10h]; struct CTreeNode *
0x18001c5fc  call    ?LoadFirstLevel@@YAXPEAVCTreeNode@@PEAUHWND__@@PEAPEAU_TREEITEM@@@Z; LoadFirstLevel(CTreeNode *,HWND__ *,_TREEITEM * *)
0x18001c601  jmp     short loc_18001C647
0x18001c603  call    cs:__imp_GetParent
0x18001c609  mov     rcx, [rdi+1A8h]; hWnd
0x18001c610  lea     rdx, aHhdefproc; "HHDefProc"
0x18001c617  mov     rbx, rax
0x18001c61a  call    cs:__imp_RemovePropA
0x18001c620  mov     rcx, [rdi+1A8h]; hWnd
0x18001c627  call    cs:__imp_DestroyWindow
0x18001c62d  mov     rcx, [rdi]
0x18001c630  mov     rdx, rbx
0x18001c633  mov     rax, [rcx+8]
0x18001c637  mov     rcx, rdi
0x18001c63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c63f  mov     rcx, rdi; dwNewLong
0x18001c642  call    ?InitTreeView@CToc@@QEAAHXZ; CToc::InitTreeView(void)
0x18001c647  mov     rbx, [rsp+68h+arg_0]
0x18001c64c  add     rsp, 60h
0x18001c650  pop     rdi
0x18001c651  retn
```
